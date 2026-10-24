# Chat History - ace-run (13o--mon-1)

- **TIMESTAMP:** 2026-10-24 09:49:00 EDT
- **MODEL:** codex/gpt-6-astra
- **AGENT:** 13o--mon-1

## Prompt

sase monitor start --command 'cd sase/repos/linked/sase-core && just test -p sase_core_py autonomy && sase tool run check && cd ../../../.. && just rust-dev-install && just fix && sase memory init --no-commit && .venv/bin/python -m sase autonomy explain -p "%auto" && .venv/bin/python -m sase autonomy explain -p "%auto:tale" && .venv/bin/python -m sase autonomy explain -p "%auto:epic" && .venv/bin/python -m sase autonomy list && sase tool run check' --reason 'Verify PyO3 binding repair and finish auto_questions_wait checks, generated docs, and CLI predictions'

## Response

sase tool run c52576747434c8b57718a105e8be5207
./scripts/check.sh test -p sase_core_py autonomy
   Compiling proc-macro2 v1.0.106
   Compiling quote v1.0.45
   Compiling unicode-ident v1.0.24
   Compiling libc v0.2.186
   Compiling cfg-if v1.0.4
   Compiling memchr v2.8.0
   Compiling shlex v1.3.0
   Compiling once_cell v1.21.4
   Compiling find-msvc-tools v0.1.9
   Compiling itoa v1.0.18
   Compiling log v0.4.29
   Compiling zerocopy v0.8.48
   Compiling serde_core v1.0.228
   Compiling autocfg v1.5.0
   Compiling pin-project-lite v0.2.17
   Compiling bytes v1.11.1
   Compiling regex-syntax v0.8.10
   Compiling crossbeam-utils v0.8.21
   Compiling equivalent v1.0.2
   Compiling futures-core v0.3.32
   Compiling version_check v0.9.5
   Compiling hashbrown v0.17.0
   Compiling serde v1.0.228
   Compiling siphasher v1.0.4
   Compiling smallvec v1.15.1
   Compiling futures-sink v0.3.32
   Compiling zmij v1.0.21
   Compiling stable_deref_trait v1.2.1
   Compiling target-lexicon v0.12.16
   Compiling bitflags v2.11.1
   Compiling serde_json v1.0.149
   Compiling crossbeam-epoch v0.9.21
   Compiling crossbeam-deque v0.8.8
   Compiling percent-encoding v2.3.2
   Compiling iana-time-zone v0.1.65
   Compiling futures-io v0.3.32
   Compiling tower-service v0.3.3
   Compiling futures-task v0.3.32
   Compiling ucd-trie v0.1.7
   Compiling slab v0.4.12
   Compiling lazy_static v1.5.0
   Compiling libm v0.2.16
   Compiling httparse v1.10.1
   Compiling writeable v0.6.3
   Compiling untrusted v0.9.0
   Compiling same-file v1.0.6
   Compiling heck v0.5.0
   Compiling litemap v0.8.2
   Compiling typenum v1.20.0
   Compiling utf8_iter v1.0.4
   Compiling icu_properties_data v2.2.0
   Compiling icu_normalizer_data v2.2.0
   Compiling deunicode v1.6.2
   Compiling fnv v1.0.7
   Compiling parking_lot_core v0.9.12
   Compiling httpdate v1.0.3
   Compiling tower-layer v0.3.3
   Compiling rustls v0.21.12
   Compiling ryu v1.0.23
   Compiling anstyle v1.0.14
   Compiling rayon-core v1.13.0
   Compiling either v1.19.0
   Compiling unicode-segmentation v1.13.3
   Compiling scopeguard v1.2.0
   Compiling thiserror v1.0.69
   Compiling sync_wrapper v1.0.2
   Compiling pkg-config v0.3.33
   Compiling clap_lex v1.1.1
   Compiling vcpkg v0.2.15
   Compiling rustix v1.1.4
   Compiling rustversion v1.0.22
   Compiling num-conv v0.2.1
   Compiling try-lock v0.2.5
   Compiling time-core v0.1.8
   Compiling powerfmt v0.2.0
   Compiling thiserror v2.0.18
   Compiling winnow v1.0.4
   Compiling getrandom v0.4.2
   Compiling encoding_rs v0.8.35
   Compiling cc v1.2.61
   Compiling futures-channel v0.3.32
   Compiling phf_shared v0.11.3
   Compiling num-traits v0.2.19
   Compiling linux-raw-sys v0.12.1
   Compiling aho-corasick v1.1.4
   Compiling bstr v1.13.1
   Compiling grep-matcher v0.1.9
   Compiling tracing-core v0.1.36
   Compiling indexmap v2.14.0
   Compiling mime v0.3.17
   Compiling home v0.5.12
   Compiling winnow v0.7.15
   Compiling http v1.4.0
   Compiling cpufeatures v0.2.17
   Compiling atomic-waker v1.1.2
   Compiling ahash v0.8.12
   Compiling generic-array v0.14.7
   Compiling form_urlencoded v1.2.2
   Compiling toml_writer v1.1.3+spec-1.1.0
   Compiling slug v0.1.6
   Compiling memoffset v0.9.1
   Compiling fallible-iterator v0.3.0
   Compiling unsafe-libyaml v0.2.11
   Compiling fastrand v2.4.1
   Compiling tinyvec v1.13.3
   Compiling base64 v0.21.7
   Compiling fallible-streaming-iterator v0.1.9
   Compiling base64 v0.22.1
   Compiling http v0.2.12
   Compiling thread_local v1.1.9
   Compiling unicode-casefold v0.2.0
   Compiling ipnet v2.12.0
   Compiling itertools v0.11.0
   Compiling want v0.3.1
   Compiling lock_api v0.4.14
   Compiling colored v2.2.0
   Compiling sharded-slab v0.1.7
   Compiling walkdir v2.5.0
   Compiling webpki-roots v0.25.4
   Compiling sync_wrapper v0.1.2
   Compiling clap_builder v4.6.7
   Compiling unicode-width v0.2.2
   Compiling nu-ansi-term v0.50.3
   Compiling matchit v0.7.3
   Compiling hex v0.4.3
   Compiling crossbeam-channel v0.5.17
   Compiling indoc v2.0.7
   Compiling unindent v0.2.4
   Compiling pyo3-build-config v0.22.6
   Compiling humansize v2.1.3
   Compiling deranged v0.5.8
   Compiling time-macros v0.2.27
   Compiling toml_parser v1.1.5+spec-1.1.0
   Compiling psm v0.1.24
   Compiling stacker v0.1.25
   Compiling ring v0.17.14
   Compiling libsqlite3-sys v0.30.1
   Compiling tracing-log v0.2.0
   Compiling phf v0.11.3
   Compiling getrandom v0.2.17
   Compiling errno v0.3.14
   Compiling socket2 v0.6.3
   Compiling mio v1.2.0
   Compiling memmap2 v0.9.11
   Compiling socket2 v0.5.10
   Compiling term_size v0.3.2
   Compiling rustls-pemfile v1.0.4
   Compiling fs2 v0.4.3
   Compiling toml_datetime v0.7.5+spec-1.1.0
   Compiling serde_spanned v1.1.2
   Compiling chrono v0.4.44
   Compiling num-integer v0.1.46
   Compiling unicode-normalization v0.1.25
   Compiling etcetera v0.8.0
   Compiling serde_path_to_error v0.1.20
   Compiling ppv-lite86 v0.2.21
   Compiling encoding_rs_io v0.1.8
   Compiling pem v3.0.6
   Compiling regex-automata v0.4.14
   Compiling http-body v1.0.1
   Compiling http-body v0.4.6
   Compiling pyo3-macros-backend v0.22.6
   Compiling pyo3-ffi v0.22.6
   Compiling pyo3 v0.22.6
   Compiling time v0.3.47
   Compiling rand_core v0.6.4
   Compiling block-buffer v0.10.4
   Compiling crypto-common v0.1.7
   Compiling parking_lot v0.12.5
   Compiling signal-hook-registry v1.4.8
   Compiling toml v0.9.12+spec-1.1.0
   Compiling tempfile v3.27.0
   Compiling num-bigint v0.4.6
   Compiling hashbrown v0.14.5
   Compiling http-body-util v0.1.3
   Compiling grep-searcher v0.1.17
   Compiling rand_chacha v0.3.1
   Compiling digest v0.10.7
   Compiling pest v2.9.4
   Compiling sha1 v0.10.7
   Compiling sha2 v0.10.9
   Compiling hashlink v0.9.1
   Compiling rayon v1.12.0
   Compiling rustls-webpki v0.101.7
   Compiling sct v0.7.1
   Compiling rand v0.8.6
   Compiling syn v2.0.117
   Compiling syn v3.0.9
   Compiling rusqlite v0.32.1
   Compiling regex v1.12.3
   Compiling globset v0.4.19
   Compiling matchers v0.2.0
   Compiling phf_generator v0.11.3
   Compiling pest_meta v2.9.4
   Compiling parse-zoneinfo v0.3.1
   Compiling ignore v0.4.32
   Compiling phf_codegen v0.11.3
   Compiling chrono-tz-build v0.3.0
   Compiling chrono-tz v0.9.0
   Compiling globwalk v0.9.1
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
   Compiling clap v4.6.7
   Compiling tokio v1.52.2
   Compiling futures-util v0.3.32
   Compiling tracing v0.1.44
   Compiling zerofrom-derive v0.1.7
   Compiling yoke-derive v0.8.2
   Compiling clap-cargo v0.18.3
   Compiling simple_asn1 v0.6.4
   Compiling table_formatter v0.6.1
   Compiling zerofrom v0.1.7
   Compiling tracing-subscriber v0.3.23
   Compiling tower-http v0.5.2
   Compiling yoke v0.8.2
   Compiling tera v1.20.1
   Compiling json5 v0.4.1
   Compiling serde_urlencoded v0.7.1
   Compiling dashmap v6.1.0
   Compiling serde_yaml v0.9.34+deprecated
   Compiling jsonwebtoken v9.3.1
   Compiling sase_workspace_hack v0.1.0 (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/sase/repos/linked/sase-core/crates/sase_workspace_hack)
   Compiling pyo3-macros v0.22.6
   Compiling zerovec v0.11.6
   Compiling zerotrie v0.2.4
   Compiling axum-core v0.4.5
   Compiling tinystr v0.8.3
   Compiling potential_utf v0.1.5
   Compiling icu_locale_core v2.2.0
   Compiling icu_collections v2.2.0
   Compiling tokio-util v0.7.18
   Compiling tower v0.5.3
   Compiling tokio-rustls v0.24.1
   Compiling hyper v1.9.0
   Compiling tokei v15.0.0
   Compiling h2 v0.3.27
   Compiling icu_provider v2.2.0
   Compiling hyper-util v0.1.20
   Compiling icu_normalizer v2.2.0
   Compiling icu_properties v2.2.0
   Compiling axum v0.7.9
   Compiling idna_adapter v1.2.2
   Compiling sase_core v0.42.3 (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/sase/repos/linked/sase-core/crates/sase_core)
   Compiling idna v1.1.0
   Compiling url v2.5.8
   Compiling hyper v0.14.32
   Compiling hyper-rustls v0.24.2
   Compiling reqwest v0.11.27
   Compiling sase_gateway v0.42.3 (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/sase/repos/linked/sase-core/crates/sase_gateway)
   Compiling sase_core_py v0.42.3 (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/sase/repos/linked/sase-core/crates/sase_core_py)
    Finished `test` profile [unoptimized + debuginfo] target(s) in 3m 20s
     Running unittests src/lib.rs (/home/bryan/.cache/sase/tmp/cargo-targets/gh_sase-org__sase-ws14-261024_085653/build/debug/deps/sase_core_rs-1b83b99e626872b2)

running 7 tests
test autonomy::tests::autonomy_wire_schema_version_binding ... ok
test autonomy::tests::autonomy_bindings_round_trip ... ok
test autonomy::tests::autonomy_summary_and_sentence_bindings ... ok
test autonomy::tests::autonomy_decision_log_bindings_round_trip ... ok
test autonomy::tests::autonomy_effective_record_binding_round_trip_and_registration ... ok
test autonomy::tests::autonomy_mutate_and_inherit_bindings ... ok
test autonomy::tests::autonomy_resolve_selection_rejects_bad_spellings ... ok

test result: ok. 7 passed; 0 failed; 0 ignored; 0 measured; 343 filtered out; finished in 0.03s

sase tool run 569348d66647f0867cc0c93d50d47e41
./scripts/check.sh all
    Checking cfg-if v1.0.4
   Compiling memchr v2.8.0
    Checking itoa v1.0.18
    Checking once_cell v1.21.4
    Checking pin-project-lite v0.2.17
    Checking bytes v1.11.1
    Checking log v0.4.29
   Compiling regex-syntax v0.8.10
    Checking futures-core v0.3.32
   Compiling siphasher v1.0.4
    Checking smallvec v1.15.1
    Checking futures-sink v0.3.32
    Checking hashbrown v0.17.0
    Checking equivalent v1.0.2
    Checking futures-io v0.3.32
    Checking futures-task v0.3.32
    Checking slab v0.4.12
    Checking tower-service v0.3.3
   Compiling iana-time-zone v0.1.65
   Compiling bitflags v2.11.1
    Checking tower-layer v0.3.3
   Compiling same-file v1.0.6
    Checking sync_wrapper v1.0.2
    Checking typenum v1.20.0
    Checking lazy_static v1.5.0
    Checking scopeguard v1.2.0
    Checking clap_lex v1.1.1
    Checking either v1.19.0
    Checking anstyle v1.0.14
   Compiling percent-encoding v2.3.2
    Checking ryu v1.0.23
    Checking winnow v1.0.4
    Checking libc v0.2.186
   Compiling zerocopy v0.8.48
    Checking serde_core v1.0.228
   Compiling crossbeam-utils v0.8.21
    Checking zmij v1.0.21
   Compiling num-traits v0.2.19
    Checking thiserror v1.0.69
    Checking home v0.5.12
    Checking cpufeatures v0.2.17
    Checking toml_writer v1.1.3+spec-1.1.0
    Checking winnow v0.7.15
    Checking linux-raw-sys v0.12.1
    Checking arbitrary v1.5.0
    Checking libsqlite3-sys v0.30.1
    Checking tinyvec v1.13.3
   Compiling phf_shared v0.11.3
    Checking fallible-streaming-iterator v0.1.9
    Checking itertools v0.11.0
    Checking unsafe-libyaml v0.2.11
    Checking fastrand v2.4.1
    Checking fallible-iterator v0.3.0
    Checking unicode-width v0.2.2
    Checking unicode-casefold v0.2.0
    Checking indexmap v2.14.0
   Compiling aho-corasick v1.1.4
   Compiling bstr v1.13.1
    Checking hex v0.4.3
    Checking encoding_rs v0.8.35
    Checking httparse v1.10.1
    Checking futures-channel v0.3.32
    Checking thread_local v1.1.9
    Checking generic-array v0.14.7
   Compiling getrandom v0.2.17
   Compiling stacker v0.1.25
    Checking grep-matcher v0.1.9
    Checking nu-ansi-term v0.50.3
    Checking clap_builder v4.6.7
    Checking zerofrom v0.1.7
    Checking stable_deref_trait v1.2.1
    Checking toml_parser v1.1.5+spec-1.1.0
    Checking writeable v0.6.3
    Checking untrusted v0.9.0
    Checking litemap v0.8.2
    Checking http v1.4.0
    Checking colored v2.2.0
    Checking sharded-slab v0.1.7
    Checking tracing-core v0.1.36
    Checking lock_api v0.4.14
    Checking etcetera v0.8.0
    Checking utf8_iter v1.0.4
    Checking bitflags v1.3.2
   Compiling serde_repr v0.1.20
    Checking httpdate v1.0.3
    Checking fnv v1.0.7
    Checking crossbeam-epoch v0.9.21
   Compiling chrono v0.4.44
    Checking crossbeam-channel v0.5.17
    Checking icu_normalizer_data v2.2.0
    Checking walkdir v2.5.0
    Checking icu_properties_data v2.2.0
    Checking try-lock v0.2.5
   Compiling num-conv v0.2.1
    Checking powerfmt v0.2.0
   Compiling time-core v0.1.8
    Checking num-integer v0.1.46
   Compiling serde v1.0.228
   Compiling phf v0.11.3
   Compiling ppv-lite86 v0.2.21
    Checking rustix v1.1.4
    Checking errno v0.3.14
    Checking mio v1.2.0
    Checking socket2 v0.6.3
    Checking ahash v0.8.12
    Checking parking_lot_core v0.9.12
    Checking memmap2 v0.9.11
    Checking serde_spanned v1.1.2
    Checking toml_datetime v0.7.5+spec-1.1.0
    Checking term_size v0.3.2
    Checking getrandom v0.4.2
    Checking serde_json v1.0.149
    Checking futures-util v0.3.32
    Checking unicode-normalization v0.1.25
    Checking fs2 v0.4.3
    Checking block-buffer v0.10.4
    Checking crypto-common v0.1.7
    Checking encoding_rs_io v0.1.8
    Checking regex-automata v0.4.14
    Checking fluent-uri v0.1.4
    Checking tracing v0.1.44
    Checking crossbeam-deque v0.8.8
    Checking tracing-log v0.2.0
    Checking http-body v1.0.1
    Checking socket2 v0.5.10
    Checking table_formatter v0.6.1
   Compiling rand_core v0.6.4
    Checking atomic-waker v1.1.2
    Checking mime v0.3.17
    Checking thiserror v2.0.18
    Checking base64 v0.21.7
    Checking base64 v0.22.1
   Compiling pest v2.9.4
    Checking serde_path_to_error v0.1.20
    Checking ipnet v2.12.0
    Checking http v0.2.12
    Checking clap v4.6.7
    Checking yoke v0.8.2
    Checking webpki-roots v0.25.4
    Checking form_urlencoded v1.2.2
    Checking want v0.3.1
    Checking sync_wrapper v0.1.2
    Checking matchit v0.7.3
    Checking async-stream v0.3.6
    Checking memoffset v0.9.1
    Checking num-bigint v0.4.6
    Checking deranged v0.5.8
   Compiling time-macros v0.2.27
    Checking unindent v0.2.4
    Checking ring v0.17.14
    Checking hashbrown v0.14.5
    Checking serde_yaml v0.9.34+deprecated
    Checking signal-hook-registry v1.4.8
    Checking parking_lot v0.12.5
    Checking digest v0.10.7
    Checking tempfile v3.27.0
    Checking toml v0.9.12+spec-1.1.0
    Checking lsp-types v0.97.0
    Checking futures v0.3.32
    Checking grep-searcher v0.1.17
    Checking http-body-util v0.1.3
    Checking rayon-core v1.13.0
    Checking regex v1.12.3
    Checking globset v0.4.19
    Checking matchers v0.2.0
   Compiling rand_chacha v0.3.1
   Compiling pyo3-build-config v0.22.6
    Checking rustls-pemfile v1.0.4
    Checking pem v3.0.6
    Checking zerovec v0.11.6
    Checking zerotrie v0.2.4
    Checking http-body v0.4.6
   Compiling pest_meta v2.9.4
    Checking serde_urlencoded v0.7.1
    Checking clap-cargo v0.18.3
    Checking dashmap v6.1.0
    Checking hashlink v0.9.1
    Checking time v0.3.47
    Checking sha1 v0.10.7
    Checking sha2 v0.10.9
    Checking tokio v1.52.2
    Checking axum-core v0.4.5
    Checking tower-http v0.5.2
    Checking tracing-subscriber v0.3.23
   Compiling rand v0.8.6
    Checking ignore v0.4.32
    Checking rayon v1.12.0
    Checking sct v0.7.1
    Checking rustls-webpki v0.101.7
   Compiling pyo3-ffi v0.22.6
   Compiling pyo3-macros-backend v0.22.6
   Compiling pyo3 v0.22.6
    Checking rusqlite v0.32.1
    Checking tinystr v0.8.3
    Checking potential_utf v0.1.5
   Compiling parse-zoneinfo v0.3.1
   Compiling pest_generator v2.9.4
    Checking rustls v0.21.12
    Checking simple_asn1 v0.6.4
    Checking icu_locale_core v2.2.0
   Compiling phf_generator v0.11.3
    Checking icu_collections v2.2.0
    Checking jsonwebtoken v9.3.1
   Compiling pest_derive v2.9.4
   Compiling globwalk v0.9.1
   Compiling phf_codegen v0.11.3
    Checking icu_provider v2.2.0
   Compiling json5 v0.4.1
   Compiling pyo3-macros v0.22.6
   Compiling chrono-tz-build v0.3.0
    Checking tokio-util v0.7.18
    Checking tower v0.5.3
    Checking hyper v1.9.0
    Checking tokio-rustls v0.24.1
    Checking icu_properties v2.2.0
    Checking icu_normalizer v2.2.0
   Compiling chrono-tz v0.9.0
    Checking hyper-util v0.1.20
    Checking tower-lsp-server v0.21.1
    Checking h2 v0.3.27
    Checking axum v0.7.9
    Checking idna_adapter v1.2.2
    Checking idna v1.1.0
    Checking url v2.5.8
    Checking hyper v0.14.32
   Compiling tera v1.20.1
   Compiling sase_workspace_hack v0.1.0 (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/sase/repos/linked/sase-core/crates/sase_workspace_hack)
    Checking hyper-rustls v0.24.2
   Compiling tokei v15.0.0
    Checking reqwest v0.11.27
    Checking sase_core v0.42.3 (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/sase/repos/linked/sase-core/crates/sase_core)
    Checking sase_macro_lsp v0.42.3 (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/sase/repos/linked/sase-core/crates/sase_macro_lsp)
    Checking sase_gateway v0.42.3 (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/sase/repos/linked/sase-core/crates/sase_gateway)
    Checking sase_core_py v0.42.3 (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/sase/repos/linked/sase-core/crates/sase_core_py)
    Finished `dev` profile [unoptimized + debuginfo] target(s) in 2m 51s
   Compiling bitflags v1.3.2
   Compiling futures v0.3.32
   Compiling sase_workspace_hack v0.1.0 (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/sase/repos/linked/sase-core/crates/sase_workspace_hack)
   Compiling sase_core v0.42.3 (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/sase/repos/linked/sase-core/crates/sase_core)
   Compiling sase_gateway v0.42.3 (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/sase/repos/linked/sase-core/crates/sase_gateway)
   Compiling sase_core_py v0.42.3 (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/sase/repos/linked/sase-core/crates/sase_core_py)
   Compiling fluent-uri v0.1.4
   Compiling lsp-types v0.97.0
   Compiling tower-lsp-server v0.21.1
   Compiling sase_macro_lsp v0.42.3 (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/sase/repos/linked/sase-core/crates/sase_macro_lsp)
    Finished `test` profile [unoptimized + debuginfo] target(s) in 2m 14s
     Running unittests src/lib.rs (/home/bryan/.cache/sase/tmp/cargo-targets/gh_sase-org__sase-ws14-261024_085653/build/debug/deps/sase_core-1053ddac181ee5d1)

running 5360 tests
test agent_archive::status::tests::done_bucket_means_done_outcome ... ok
test agent_archive::status::tests::failed_bucket_means_failed_outcome ... ok
test agent_archive::status::tests::every_other_bucket_means_interrupted_outcome ... ok
test agent_archive::status::tests::input_pause_statuses_bucket_as_stopped ... ok
test agent_archive::status::tests::failure_statuses_bucket_as_failed ... ok
test agent_archive::status::tests::handoff_and_transient_statuses_bucket_as_running ... ok
test agent_archive::status::tests::scheduled_statuses_keep_their_own_buckets ... ok
test agent_archive::status::tests::terminal_statuses_bucket_as_done ... ok
test agent_archive::store::tests::store_parses_bundle_filename_timestamps_like_python ... ok
test agent_archive::store::tests::store_queries_return_none_for_missing_index ... ok
test agent_archive::store::tests::store_payload_hash_matches_python ... ok
test agent_archive::store::tests::store_rebuild_progress_is_idle_without_rebuild ... ok
test agent_archive::tests::validates_archive_key_and_visibility ... ok
test agent_archive::tests::validates_capabilities_against_persisted_inputs ... ok
test agent_artifact_run_retention::tests::apply_refuses_every_mutation_request_before_filesystem_walks ... ok
test agent_auto_restart::tests::episode_falls_back_to_identity_revisions_before_refresh_log ... ok
test agent_auto_restart::tests::directive_errors_never_restart ... ok
test agent_artifact_run_retention::tests::empty_shard_preview_reports_bottom_up_across_three_levels ... ok
test agent_auto_restart::tests::episode_uses_culprit_commit_then_range ... ok
test agent_auto_restart::tests::every_ledger_transition_legal_and_illegal ... ok
test agent_auto_restart::tests::finalizer_failures_never_restart ... ok
test agent_auto_restart::tests::in_flight_states_map_to_restarting ... ok
test agent_auto_restart::tests::killed_rows_never_restart ... ok
test agent_auto_restart::tests::incident_defers_without_w4 ... ok
test agent_auto_restart::tests::incident_relaunch_when_w1_and_w4_hold ... ok
test agent_auto_restart::tests::lineage_root_prefers_auto_restart_then_chain_then_row ... ok
test agent_artifact_run_retention::tests::empty_shard_walk_preserves_unknown_directories ... ok
test agent_auto_restart::tests::ledger_stamps_claimed_at_and_history_at ... ok
test agent_auto_restart::tests::legacy_provider_frames_mean_post_provider ... ok
test agent_auto_restart::tests::plan_handoff_import_error_asks ... ok
test agent_auto_restart::tests::missing_symbol_comes_from_the_matched_error_line_not_first_quote ... ok
test agent_auto_restart::tests::provider_429_and_usage_limit_never_restart ... ok
test agent_auto_restart::tests::same_import_error_with_no_witness_declines ... ok
test agent_auto_restart::tests::third_party_import_error_does_not_match_from_log_tail_sase_logger ... ok
test agent_auto_restart::tests::post_provider_import_error_notifies ... ok
test agent_auto_restart::tests::tier1_failed_probe_without_update_witness_declines ... ok
test agent_auto_restart::tests::traceback_quoted_in_agent_output_does_not_match ... ok
test agent_auto_restart::tests::unknown_phase_asks_and_never_relaunches ... ok
test agent_auto_restart::tests::tier4_type_error_is_annotate_only ... ok
test agent_auto_restart::tests::waiter_incident_relaunch_extracts_missing_symbol_from_error_line ... ok
test agent_auto_restart::tests::workspace_origin_import_error_never_matches ... ok
test agent_auto_restart::tests::workspace_origin_with_trailing_slash_declines_even_with_witnesses ... ok
test agent_auto_restart::tests::workspace_origin_without_trailing_slash_declines ... ok
test agent_clan_record::tests::record_paths_encode_and_reject ... ok
test agent_clan_tribe::tests::absent_declarations_resolve_to_none ... ok
test agent_clan_tribe::tests::absent_summaries_resolve_to_none ... ok
test agent_clan_tribe::tests::stable_identity_breaks_equal_timestamp_summary_ties ... ok
test agent_clan_tribe::tests::stable_identity_breaks_equal_timestamp_ties ... ok
test agent_clan_tribe::tests::latest_explicit_summary_wins_and_omissions_do_not_clear ... ok
test agent_cleanup::execution::tests::bundle_filename_and_shard_match_dismissed_layout ... ok
test agent_clan_tribe::tests::latest_explicit_declaration_wins_and_omissions_do_not_clear ... ok
test agent_clan_tribe::tests::repeated_declarations_and_generations_are_scoped ... ok
test agent_cleanup::execution::tests::mark_running_hook_mentor_and_comment_suffixes_as_killed ... ok
test agent_cleanup::execution::tests::release_workspace_text_removes_empty_running_field ... ok
test agent_cleanup::execution::tests::release_workspace_text_removes_matching_claim_and_cleans_field ... ok
test agent_clan_tribe::tests::repeated_summaries_and_generations_are_scoped ... ok
test agent_cleanup::force_reuse::tests::stop_barrier_allows_verified_graceful_and_escalated_stops ... ok
test agent_cleanup::force_reuse::tests::stop_barrier_blocks_permission_failures ... ok
test agent_cleanup::force_reuse::tests::stop_barrier_blocks_when_process_is_still_live ... ok
test agent_cleanup::planner::tests::broad_scopes_keep_workflow_step_children_cascade_only ... ok
test agent_cleanup::planner::tests::broad_scopes_act_on_agent_session_member_child_rows_directly ... ok
test agent_cleanup::planner::tests::all_panels_kill_and_dismiss_partitions_targets ... ok
test agent_cleanup::planner::tests::clan_scope_deduplicates_already_selected_live_monitor ... ok
test agent_cleanup::planner::tests::clan_scope_keeps_active_parallel_agent_session_root_from_dismissal ... ok
test agent_cleanup::planner::tests::clan_scope_dismisses_sequential_agent_session_and_monitor_rows ... ok
test agent_cleanup::planner::tests::clan_scope_without_generation_selects_all_generations ... ok
test agent_cleanup::planner::tests::clan_scope_filters_generation_and_partitions_with_workflow_cascade ... ok
test agent_cleanup::planner::tests::completed_workflow_parent_gets_timestamp_and_workflow_releases ... ok
test agent_cleanup::planner::tests::custom_scope_owner_does_not_stop_unrelated_sibling_monitor ... ok
test agent_cleanup::planner::tests::direct_child_side_effects_include_child_not_siblings ... ok
test agent_cleanup::planner::tests::direct_live_monitor_selection_is_a_monitor_stop ... ok
test agent_cleanup::planner::tests::cleanup_target_parallel_flag_emits_canonical_wire_spelling ... ok
test agent_cleanup::planner::tests::direct_workflow_child_does_not_release_parent_workspace_claim ... ok
test agent_cleanup::planner::tests::dismiss_side_effects_allow_duplicate_historical_names ... ok
test agent_cleanup::planner::tests::dismissable_statuses_include_stopped ... ok
test agent_cleanup::planner::tests::dismiss_side_effects_preserve_names ... ok
test agent_cleanup::planner::tests::dismissable_statuses_include_tale_done ... ok
test agent_cleanup::planner::tests::dismissing_parallel_root_cascades_only_after_members_finish ... ok
test agent_cleanup::planner::tests::done_row_with_live_runner_stays_dismissable ... ok
test agent_cleanup::planner::tests::explicit_child_only_completed_target_becomes_dismiss_item ... ok
test agent_cleanup::planner::tests::explicit_child_only_running_target_becomes_kill_item ... ok
test agent_cleanup::planner::tests::explicit_identities_select_only_marked_targets ... ok
test agent_cleanup::planner::tests::explicit_identities_dismiss_sequential_agent_session_and_monitor_rows ... ok
test agent_cleanup::planner::tests::failed_live_runner_cascades_through_parallel_members ... ok
test agent_cleanup::planner::tests::failed_row_with_live_runner_becomes_kill_item ... ok
test agent_cleanup::planner::tests::failed_row_with_live_runner_is_not_dismissable ... ok
test agent_cleanup::planner::tests::failed_row_without_live_runner_stays_dismissable ... ok
test agent_cleanup::planner::tests::focused_panel_selects_matching_tribe_and_dismisses_completed ... ok
test agent_cleanup::planner::tests::killing_one_parallel_member_leaves_root_and_siblings_untouched ... ok
test agent_cleanup::planner::tests::no_op_plan_reports_none_severity ... ok
test agent_cleanup::planner::tests::rejects_previous_cleanup_wire_schema ... ok
test agent_cleanup::planner::tests::parallel_agent_session_root_kill_cascades_to_live_members_only ... ok
test agent_cleanup::planner::tests::schema_4_request_is_rejected_after_bump ... ok
test agent_cleanup::planner::tests::running_owner_kill_releases_owner_workspace_not_monitor_claim ... ok
test agent_cleanup::planner::tests::stopped_row_is_dismissed_not_killed_or_failed ... ok
test agent_cleanup::planner::tests::selected_owner_cascades_to_nested_live_monitor ... ok
test agent_cleanup::planner::tests::terminal_monitor_is_dismissed_not_stopped ... ok
test agent_cleanup::planner::tests::unknown_kill_kind_is_skipped ... ok
test agent_cleanup::planner::tests::tribe_scope_uses_parent_tribe_for_workflow_children_but_skips_child_directly ... ok
test agent_cleanup::planner::tests::workflow_parent_cascade_deduplicates_child_inputs ... ok
test agent_artifact_run_retention::tests::empty_shard_walk_preserves_watched_and_nonempty_dirs ... ok
test agent_cleanup::execution::tests::delete_agent_artifact_markers_removes_loader_files_only ... ok
test agent_group_archive::tests::missing_group_name_loads_as_none ... ok
test agent_artifact_run_retention::tests::preview_still_classifies_when_sources_unavailable ... ok
test agent_artifact_run_retention::tests::empty_shard_preview_respects_apply_budget ... ok
test agent_group_archive::tests::missing_ref_prompt_preview_loads_as_none ... ok
test agent_group_archive::tests::pre_contract_v2_group_still_loads_and_lists ... ok
test agent_artifact_run_retention::tests::rejects_symlinked_ancestor_before_canonicalizing_candidate ... ok
test agent_artifact_run_retention::tests::symlinked_candidate_path_reports_symlink_ancestor_for_canonical_root ... ok
test agent_clan_record::tests::overlay_applies_matching_generations_only ... ok
test agent_clan_record::tests::identical_rewrites_are_no_ops_and_do_not_touch_the_file ... ok
test agent_hold::tests::armer_kin_exclusion_covers_self_session_clan_and_descendant ... ok
test agent_hold::tests::candidate_emits_named_proc_spelling ... ok
test agent_hold::tests::future_selector_only_matches_after_arm_time ... ok
test agent_hold::tests::hood_matching_honors_component_boundaries_and_turn_suffixes ... ok
test agent_cleanup::execution::tests::save_dismissed_bundle_json_writes_sharded_pretty_json ... ok
test agent_cleanup::execution::tests::corrupt_index_is_preserved_not_overwritten ... ok
test agent_group_archive::tests::save_list_and_load_preserve_group_name ... ok
test agent_group_archive::tests::load_group_keeps_refs_when_bundle_files_are_missing ... ok
test agent_group_archive::tests::whitespace_group_name_normalizes_to_none ... ok
test agent_clan_record::tests::only_edited_writes_a_tombstone ... ok
test agent_group_archive::tests::corrupt_and_missing_group_files_are_tolerated ... ok
test agent_hold::tests::arm_stores_capture_and_rebind_preserves_it ... ok
test agent_hold::tests::legacy_records_without_capture_stay_unread ... ok
test agent_hold::tests::arm_list_rearm_and_release_round_trip ... ok
test agent_hold::tests::named_proc_matches_name_and_hood_selectors_without_agent_session_kin ... ok
test agent_clan_record::tests::capture_fills_but_never_overrides_an_edit ... ok
test agent_hold::tests::predicate_matches_membership_tribes_without_primary_tribe ... ok
test agent_hold::tests::predicate_matches_each_selector_and_scope ... ok
test agent_hold::tests::summarize_hold_capture_excludes_kin_and_out_of_scope ... ok
test agent_hold::tests::unreadable_store_path_is_treated_as_empty ... ok
test agent_hold_deadlock::tests::agent_session_wait_name_matches_role_suffixed_candidate ... ok
test agent_hold_deadlock::tests::direct_wait_name_is_a_deadlock ... ok
test agent_hold_deadlock::tests::first_harmless_branch_does_not_hide_the_second ... ok
test agent_hold_deadlock::tests::hood_does_not_match_a_member_launched_after_the_waiter ... ok
test agent_hold_deadlock::tests::hood_wait_reaches_a_hood_member_candidate ... ok
test agent_hold_deadlock::tests::longer_cycle_with_repeated_vertices_still_reaches ... ok
test agent_hold_deadlock::tests::no_cycle_is_not_a_deadlock ... ok
test agent_hold_deadlock::tests::running_armer_is_immune ... ok
test agent_hold_deadlock::tests::settled_branch_is_not_walked ... ok
test agent_hold_deadlock::tests::tribe_wait_honors_launch_cutoff ... ok
test agent_hold_deadlock::tests::unrelated_cycle_without_the_candidate_is_not_a_deadlock ... ok
test agent_hold_deadlock::tests::waiter_does_not_deadlock_on_its_own_hood_membership ... ok
test agent_identity::identity::tests::agent_session_hood_ancestors_and_membership_are_canonical ... ok
test agent_identity::identity::tests::agent_session_name_wire_accepts_both_key_spellings ... ok
test agent_identity::identity::tests::agent_session_name_wire_serializes_canonical_spelling ... ok
test agent_identity::identity::tests::explicit_owner_prevents_mismatched_strip ... ok
test agent_identity::identity::tests::globalization_normalizes_archive_and_round_trips ... ok
test agent_identity::identity::tests::historical_agent_session_classification_is_total_and_canonical ... ok
test agent_identity::identity::tests::hood_membership_never_raises_for_historical_candidates ... ok
test agent_identity::identity::tests::link_targets_distinguish_agent_session_and_solo ... ok
test agent_identity::identity::tests::localization_covers_all_owner_cases ... ok
test agent_identity::identity::tests::owned_agent_name_wire_accepts_both_key_spellings ... ok
test agent_identity::identity::tests::owner_aware_globalization_rejects_foreign_roots ... ok
test agent_identity::identity::tests::owner_aware_hood_ancestors_membership_and_links_use_semantic_remainder ... ok
test agent_identity::identity::tests::owner_roots_validate_and_parse_longest_prefix ... ok
test agent_identity::identity::tests::ownership_classification_never_parses_names ... ok
test agent_identity::identity::tests::unsafe_names_and_empty_remainders_fail ... ok
test agent_identity::identity::tests::username_and_owner_validation_matrix ... ok
test agent_identity::relationships::tests::complete_mapping_rewrites_all_run_id_fields_in_input_order ... ok
test agent_identity::relationships::tests::container_kind_accepts_legacy_family_and_serializes_session ... ok
test agent_identity::relationships::tests::graph_projection_localizes_full_owner_matrix ... ok
test agent_identity::relationships::tests::graph_projection_localizes_global_name_relationship_targets ... ok
test agent_identity::relationships::tests::graph_projection_rejects_current_owner_localization_collisions ... ok
test agent_identity::relationships::tests::historical_agent_session_names_validate_in_relationship_batches ... ok
test agent_identity::relationships::tests::mapping_must_be_complete_unique_and_exact ... ok
test agent_identity::relationships::tests::pre_contract_v2_batch_with_family_container_still_validates ... ok
test agent_identity::relationships::tests::rejects_bad_container_members_and_names ... ok
test agent_identity::relationships::tests::rejects_duplicate_runs_names_and_containers ... ok
test agent_hold::tests::lock_wait_is_bounded ... ok
test agent_identity::relationships::tests::rejects_self_duplicate_and_cyclic_edges ... ok
test agent_identity::relationships::tests::required_optional_and_cross_owner_targets_are_enforced ... ok
test agent_identity::relationships::tests::serde_contract_rejects_machine_local_and_unknown_state ... ok
test agent_identity::relationships::tests::valid_mixed_batch_returns_canonical_summary ... ok
test agent_launch::admission::tests::agent_dispatch_prompt_keeps_resolved_default_weight_implicit ... ok
test agent_launch::admission::tests::agent_dispatch_prompt_restores_agent_session_and_direct_tribe ... ok
test agent_launch::admission::tests::agent_dispatch_prompt_restores_clan_declaration_and_join ... ok
test agent_launch::admission::tests::agent_dispatch_prompt_restores_identity_with_queue_directive ... ok
test agent_launch::admission::tests::agent_dispatch_prompt_restores_workspace_and_dispatch ... ok
test agent_launch::admission::tests::agent_dispatch_prompt_round_trips_explicit_zero_weight ... ok
test agent_launch::admission::tests::condition_units_check_after_waits_and_fail_interrupted_checks ... ok
test agent_launch::admission::tests::dispatch_fingerprint_is_stable_for_same_payload ... ok
test agent_launch::admission::tests::dispatching_without_identity_fails_instead_of_redoing_spawn ... ok
test agent_launch::admission::tests::external_wait_facts_gate_admission ... ok
test agent_launch::admission::tests::next_actions_reserve_then_wait_then_dispatch_agent ... ok
test agent_launch::admission::tests::proc_hold_blocks_waiting_to_eligible_and_eligible_to_dispatch ... ok
test agent_launch::admission::tests::proc_payload_fingerprint_uses_code_digest ... ok
test agent_launch::admission::tests::reconcile_keeps_latest_phase_and_identity ... ok
test agent_launch::admission::tests::remote_dispatching_without_identity_retries_same_fingerprint ... ok
test agent_launch::admission::tests::skipped_predecessor_is_terminal_and_does_not_retarget ... ok
test agent_launch::admission::tests::summary_counts_partial_success_without_collapsing_errors ... ok
test agent_launch::auto_directive::tests::accepted_spellings_classify_to_launch_fields ... ok
test agent_launch::auto_directive::tests::rejected_spellings_name_the_spelling_and_list_modes ... ok
test agent_launch::condition::tests::argv_is_not_interpolated ... ok
test agent_identity::relationships::tests::rejects_schema_unsafe_oversized_and_owner_mismatch ... ok
test agent_hold::tests::validation_rejects_bad_inputs_and_sorts_sets ... ok
test agent_clan_record::tests::launch_defaults_resolve_per_attribute_and_honor_tombstones ... ok
test agent_hold::tests::rebind_kin_invalid_new_armer_leaves_old_record ... ok
test agent_hold::tests::list_prunes_expired_malformed_stale_schema_and_dead_armers ... ok
test agent_launch::condition::tests::classify_exit_classes ... ok
test agent_clan_record::tests::corrupt_records_leave_member_values_in_place ... ok
test agent_artifact_run_retention::tests::rejects_paths_outside_projects_root ... ok
test agent_artifact_run_retention::tests::preview_selects_terminal_runs_without_mutating ... ok
test agent_artifact_run_retention::tests::empty_shard_walk_preserves_protected_empty_run_and_parents ... ok
test agent_clan_record::tests::capture_ignores_non_clan_directories ... ok
test agent_launch::condition::tests::secret_inputs_are_stripped_and_workspace_is_not_shared ... ok
test agent_artifact_run_retention::tests::protects_recent_month_and_future_timestamp_and_selects_the_rest ... ok
test agent_artifact_run_retention::tests::empty_shard_walk_respects_removal_budget ... ok
test agent_artifact_run_retention::tests::preview_timestamp_protection_overrides_empty_candidate_reasons ... ok
test agent_launch::conditional::tests::invalid_boolean_blocks_entire_batch ... ok
test agent_launch::conditional::tests::prose_if_mentions_are_literal ... ok
test agent_launch::conditional::tests::false_boolean_omits_segments ... ok
test agent_cleanup::execution::tests::index_removals_and_additions_compose ... ok
test agent_cleanup::execution::tests::save_dismissed_bundle_json_replaces_existing_bundle ... ok
test agent_group_archive::tests::recent_groups_tolerate_corrupt_files_and_mark_revived ... ok
test agent_group_archive::tests::mark_group_revived_preserves_metadata ... ok
test agent_group_archive::tests::delete_group_removes_only_requested_metadata_record ... ok
test agent_group_archive::tests::recent_groups_replace_same_group_id ... ok
test agent_hold::tests::rebind_keeps_timing_and_replaces_key_atomically ... ok
test agent_hold::tests::rebind_absent_key_writes_nothing_and_same_key_works ... ok
test agent_launch::directive_scan::tests::new_family_marker_canonicalizes_to_legacy ... ok
test agent_launch::directive_scan::tests::unclosed_new_family_marker_is_not_a_region ... ok
test agent_launch::launch_hold::tests::launch_unit_hold_armer_builds_agent_identity_shapes ... ok
test agent_launch::launch_hold::tests::launch_unit_hold_armer_builds_proc_without_identity_fields ... ok
test agent_launch::launch_hold::tests::launch_unit_hold_key_validates_components ... ok
test agent_launch::launch_hold::tests::proc_unit_emits_canonical_proc_name ... ok
test agent_launch::proc_runtime::tests::duration_parser_matches_sase_grammar ... ok
test agent_launch::proc_runtime::tests::phases_and_origin_are_stable ... ok
test agent_launch::proc_runtime::tests::dispatch_request_emits_canonical_proc_name ... ok
test agent_launch::proc_runtime::tests::ordinary_cwd_requires_an_existing_directory ... ok
test agent_launch::proc_runtime::tests::proc_names_reject_agent_session_qualification ... ok
test agent_launch::proc_runtime::tests::sanitized_proc_env_does_not_duplicate_an_already_prefixed_interpreter_dir ... ok
test agent_launch::proc_runtime::tests::relative_cwd_rejects_parent_escape ... ok
test agent_launch::proc_runtime::tests::sanitized_proc_env_falls_back_to_default_path_without_a_base ... ok
test agent_launch::proc_runtime::tests::sanitized_proc_env_never_copies_forbidden_identity_from_the_base ... ok
test agent_launch::proc_runtime::tests::sanitized_proc_env_preserves_inherited_path_and_prefixes_interpreter_once ... ok
test agent_launch::proc_runtime::tests::relative_cwd_stays_inside_the_lease ... ok
test agent_launch::proc_runtime::tests::workspace_false_without_cwd_is_rejected ... ok
test agent_launch::proc_runtime::tests::workspace_true_without_project_is_rejected ... ok
test agent_launch::proc_runtime::tests::symlink_cwd_cannot_escape_the_lease ... ok
test agent_launch::tests::fanout::batch_predecessor_binding_validates_context ... ok
test agent_launch::directive_scan::tests::disabled_regions_accept_both_families_and_mixed_markers ... ok
test agent_launch::tests::fanout::batch_predecessor_binding_preserves_explicit_and_non_wait_targets ... ok
test agent_launch::conditional::tests::true_boolean_strips_only_directive ... ok
test agent_launch::tests::fanout::batch_predecessor_binding_without_name_keeps_identity_only_dependency ... ok
test agent_hold::tests::proc_terminal_fact_prunes_record ... ok
test agent_launch::tests::fanout::batch_predecessor_binding_consumes_zero_argument_wait_forms ... ok
test agent_launch::tests::fanout::fanout_planner_allocates_unnamed_alt_ids_after_named_ids ... ok
test agent_launch::tests::fanout::fanout_planner_brace_branch_text_keeps_commas ... ok
test agent_launch::tests::fanout::fanout_planner_adjacent_brace_directives_all_expand ... ok
test agent_launch::tests::fanout::fanout_planner_brace_composes_cartesian_with_paren_alt ... ok
test agent_launch::tests::fanout::fanout_planner_brace_named_and_numeric_branch_ids ... ok
test agent_launch::tests::fanout::fanout_planner_brace_model_branches_match_paren_parity ... ok
test agent_launch::tests::fanout::fanout_planner_brace_expands_inside_colon_value ... ok
test agent_launch::tests::fanout::fanout_planner_brace_named_text_blocks ... ok
test agent_launch::tests::fanout::fanout_planner_brace_opens_after_punctuation ... ok
test agent_launch::tests::fanout::fanout_planner_brace_opens_mid_word ... ok
test agent_launch::tests::fanout::extract_first_model_value_strips_known_effort_suffix ... ok
test agent_launch::tests::fanout::fanout_planner_brace_shorthand_splits_pipe_branches ... ok
test agent_launch::tests::fanout::fanout_planner_brace_single_branch_has_implicit_empty_variant ... ok
test agent_launch::conditional::tests::literal_zones_do_not_trigger_boolean_filter ... ok
test agent_launch::tests::fanout::batch_predecessor_binding_ignores_literal_regions ... ok
test agent_launch::conditional::tests::boolean_and_script_body_conflict ... ok
test agent_launch::tests::fanout::fanout_planner_brace_single_branch_mid_word ... ok
test agent_launch::tests::fanout::fanout_planner_brace_model_branches_report_model_slots ... ok
test agent_launch::tests::fanout::fanout_planner_brace_nested_pipes_do_not_split ... ok
test agent_launch::tests::fanout::fanout_planner_concatenated_opener_stays_literal ... ok
test agent_launch::tests::fanout::fanout_planner_correlated_group_mixes_named_and_unnamed_ids ... ok
test agent_launch::tests::fanout::fanout_planner_correlates_shared_named_alt_keys ... ok
test agent_launch::tests::fanout::fanout_planner_cartesian_products_independent_correlated_groups ... ok
test agent_launch::tests::fanout::fanout_planner_brace_value_fanout_after_directive_colon ... ok
test agent_launch::tests::fanout::fanout_planner_composes_cartesian_alt_ids ... ok
test agent_launch::tests::fanout::fanout_planner_brace_value_fanout_after_effort_e_alias ... ok
test agent_launch::tests::fanout::fanout_planner_correlates_transitive_alt_keys ... ok
test agent_launch::tests::fanout::fanout_planner_empty_branch_collapses_multiple_spaces ... ok
test agent_launch::tests::fanout::fanout_planner_deprecated_time_directive_is_not_special ... ok
test agent_launch::tests::fanout::fanout_planner_deeply_nested_brace_never_panics ... ok
test agent_launch::tests::fanout::fanout_planner_empty_branch_preserves_newlines_and_indentation ... ok
test agent_launch::tests::fanout::fanout_planner_empty_branch_removes_leading_space ... ok
test agent_launch::tests::fanout::fanout_planner_empty_branch_collapses_between_words ... ok
test agent_launch::tests::fanout::fanout_planner_does_not_support_removed_name_spellings ... ok
test agent_launch::tests::fanout::fanout_planner_empty_branch_removes_trailing_space ... ok
test agent_launch::tests::fanout::fanout_planner_glued_references_and_tags_stay_verbatim ... ok
test agent_launch::tests::fanout::fanout_planner_empty_branch_removes_space_before_punctuation ... ok
test agent_launch::tests::fanout::fanout_planner_ignores_alternative_inside_adjacent_inline_code ... ok
test agent_launch::tests::fanout::fanout_planner_mid_word_named_branches_correlate ... ok
test agent_launch::tests::fanout::fanout_planner_extracts_repeat_slots ... ok
test agent_launch::tests::fanout::fanout_planner_empty_branch_preserves_following_directive_separator ... ok
test agent_launch::tests::fanout::fanout_planner_nested_brace_expands_per_branch ... ok
test agent_launch::tests::fanout::fanout_planner_model_value_fanout_after_directive_colon ... ok
test agent_launch::tests::fanout::fanout_planner_nested_brace_mid_word_operand ... ok
test agent_launch::tests::fanout::fanout_planner_ignores_wait_forms_inside_adjacent_inline_code ... ok
test agent_launch::tests::fanout::fanout_planner_model_alt_ids_preserve_named_model_branches ... ok
test agent_launch::tests::fanout::fanout_planner_nested_paren_after_brace_opener_fans_out ... ok
test agent_launch::tests::fanout::fanout_planner_opener_after_literal_brace_fans_out ... ok
test agent_launch::tests::fanout::fanout_planner_nested_variants_multiply_within_correlated_slot ... ok
test agent_launch::tests::fanout::fanout_planner_ignores_models_inside_adjacent_inline_code ... ok
test agent_launch::tests::fanout::fanout_planner_paren_forms_still_need_a_boundary ... ok
test agent_launch::tests::fanout::fanout_planner_preserves_named_alt_ids_and_values_only ... ok
test agent_launch::tests::fanout::fanout_planner_percent_before_jinja_tag_is_an_alternation ... ok
test agent_launch::tests::fanout::fanout_planner_rejects_paren_multi_model_directive ... ok
test agent_launch::tests::fanout::fanout_planner_mid_word_brace_ignores_literal_zones ... ok
test agent_launch::tests::fanout::fanout_planner_glued_branch_directives_keep_parseable_spacing ... ok
test agent_launch::tests::fanout::fanout_planner_rejects_repeated_models_with_brace_alternatives ... ok
test agent_launch::tests::fanout::fanout_planner_rejects_repeated_top_level_model_directives ... ok
test agent_launch::tests::fanout::fanout_planner_rejects_same_value_repeated_model_directives ... ok
test agent_launch::tests::fanout::fanout_planner_single_shared_key_collapses_to_one_slot ... ok
test agent_launch::tests::fanout::fanout_planner_rejects_repeated_top_level_models_with_alternatives ... ok
test agent_launch::tests::fanout::fanout_planner_splits_multi_prompt_outside_fences ... ok
test agent_launch::tests::fanout::fanout_planner_time_waits_defer_workspace ... ok
test agent_launch::tests::fanout::fanout_planner_unclosed_mid_word_brace_reports_missing_close ... ok
test agent_launch::tests::fanout::fanout_planner_t_xprompt_defer_workspace ... ok
test agent_launch::tests::fanout::fanout_planner_unclosed_brace_reports_missing_close ... ok
test agent_launch::tests::fanout::fanout_planner_single_top_level_model_is_single_launch ... ok
test agent_launch::tests::fanout::fanout_planner_preserves_repeat_bead_association ... ok
test agent_launch::tests::fanout::render_alternative_prompt_empty_branch_does_not_invent_space ... ok
test agent_launch::tests::fanout::launch_inline_scanner_preserves_argument_parser_precedence ... ok
test agent_launch::tests::typed_plan::parse_directive_args_text_block_corpus_matches_python ... ok
test agent_launch::tests::typed_plan::agent_unit_attach_keys_accept_both_spellings_and_serialize_canonical ... ok
test agent_launch::tests::typed_plan::agent_unit_legacy_json_defaults_to_plain_identity ... ok
test agent_launch::tests::typed_plan::agent_unit_identity_forms_round_trip_json ... ok
test agent_launch::tests::typed_plan::prompt_has_identity_directive_ignores_fenced_id ... ok
test agent_launch::tests::fanout::fanout_planner_strips_branch_effort_for_slot_naming ... ok
test agent_launch::tests::fanout::fanout_planner_unvalued_model_markers_do_not_count_as_repeated ... ok
test agent_launch::tests::fanout::fanout_planner_value_fanouts_compose_cartesian ... ok
test agent_launch::tests::fanout::fanout_planner_splits_model_branches_and_alternatives ... ok
test agent_launch::tests::fanout::fanout_planner_preserves_repeat_and_id_inside_literal_zones ... ok
test agent_hold::tests::arm_time_kin_rejection_covers_names_sessions_clans_and_workflows ... ok
test agent_clan_record::tests::empty_summary_is_a_no_op_and_long_summaries_truncate ... ok
test agent_hold::tests::launch_armer_ignores_agent_liveness_fact ... ok
test agent_clan_record::tests::scan_overlay_keeps_recorded_values_after_declarer_deleted ... ok
test agent_clan_record::tests::capture_honors_the_parallel_agent_session_fallback ... ok
test agent_launch::tests::typed_plan::typed_launch_future_hold_cycle_rejects_wait_on_sibling ... ok
test agent_launch::tests::typed_plan::typed_launch_clan_summary_keeps_unbalanced_inner_closer ... ok
test agent_launch::tests::typed_plan::typed_launch_parses_explicit_zero_queue_weight ... ok
test agent_launch::tests::typed_plan::typed_launch_future_hold_cycle_rejects_two_future_siblings ... ok
test agent_launch::tests::typed_plan::typed_launch_manual_auto_renders_no_auto_token ... ok
test agent_launch::tests::typed_plan::typed_launch_clan_summary_ignores_inner_text_block_marker ... ok
test agent_launch::tests::typed_plan::typed_launch_fanout_branches_may_use_different_tabs ... ok
test agent_launch::tests::typed_plan::typed_launch_composes_disjoint_queue_and_fanout ... ok
test agent_launch::tests::typed_plan::typed_launch_future_hold_without_cycle_is_allowed ... ok
test agent_launch::tests::typed_plan::typed_launch_keeps_fenced_workspace_and_dispatch_inert ... ok
test agent_launch::tests::typed_plan::typed_launch_does_not_replace_unit_workspace_with_plan_project ... ok
test agent_launch::tests::typed_plan::typed_launch_clan_double_colon_eol_binds_next_line_summary ... ok
test agent_launch::tests::typed_plan::typed_launch_keeps_fenced_tab_inert ... ok
test agent_launch::tests::typed_plan::typed_launch_future_hold_cycle_ignores_kin_sibling ... ok
test agent_launch::tests::typed_plan::typed_launch_parses_tab_and_reemits_after_hide ... ok
test agent_launch::tests::typed_plan::typed_launch_parses_capacity_multiplier_for_agent_and_proc ... ok
test agent_launch::tests::typed_plan::typed_launch_plan_builds_mixed_proc_agent_wait_graph ... ok
test agent_launch::tests::typed_plan::typed_launch_plan_rejects_invalid_if_forms_without_owned_fence ... ok
test agent_launch::tests::typed_plan::typed_launch_plan_captures_bare_fenced_proc ... ok
test agent_launch::tests::typed_plan::typed_launch_plan_rejects_bare_proc_without_body ... ok
test agent_launch::tests::typed_plan::typed_launch_plan_captures_if_fence_without_duplicate_form_error ... ok
test agent_launch::tests::typed_plan::typed_launch_plan_rejects_agent_directives_on_proc ... ok
test agent_launch::tests::typed_plan::typed_launch_plan_preserves_prose_if_proc_mentions ... ok
test agent_launch::tests::typed_plan::typed_launch_plan_preserves_clan_declaration_and_join ... ok
test agent_launch::tests::typed_plan::typed_launch_plan_resolves_forward_proc_wait ... ok
test agent_launch::tests::typed_plan::typed_launch_plan_keeps_fenced_proc_options ... ok
test agent_launch::tests::typed_plan::typed_launch_rejects_conflicting_session_and_family_spellings ... ok
test agent_launch::tests::typed_plan::typed_launch_plan_rejects_wait_cycles ... ok
test agent_launch::tests::typed_plan::typed_launch_plan_validates_proc_project_policy ... ok
test agent_launch::tests::typed_plan::typed_launch_rejects_duplicate_tab ... ok
test agent_launch::tests::typed_plan::typed_launch_plan_rejects_conflicting_identity_forms ... ok
test agent_launch::tests::typed_plan::typed_launch_rejects_duplicate_auto ... ok
test agent_launch::tests::wires::fanout_plan_round_trips_slots ... ok
test agent_launch::tests::wires::launch_request_local_macros_alias_matches_legacy_key ... ok
test agent_launch::tests::typed_plan::typed_launch_rejects_tab_on_proc_with_specific_code ... ok
test agent_launch::tests::typed_plan::typed_launch_plan_preserves_agent_session_and_direct_tribe ... ok
test agent_launch::tests::wires::prepared_wire_preserves_null_claim_request ... ok
test agent_launch::tests::wires::timestamp_batch_allocates_unique_visible_timestamps ... ok
test agent_launch::tests::wires::launch_request_round_trips_json_shape ... ok
test agent_launch::tests::wires::timestamp_batch_rejects_invalid_format ... ok
test agent_launch::tests::typed_plan::typed_launch_parses_queue_spellings_and_round_trips ... ok
test agent_launch::tests::typed_plan::typed_launch_preserves_per_unit_workspace_and_dispatch ... ok
test agent_launch::tests::typed_plan::typed_launch_tab_paren_form_and_main_store_absent ... ok
test agent_launch::tests::workspace::allocate_and_claim_picks_first_available_workspace ... ok
test agent_launch::tests::wires::timestamp_batch_starts_after_previous_allocation ... ok
test agent_launch::tests::typed_plan::typed_launch_proc_queue_changes_content_digest ... ok
test agent_launch::tests::workspace::occupancy_proceeds_when_no_occupant_record ... ok
test agent_launch::tests::typed_plan::typed_launch_tab_changes_content_digest ... ok
test agent_launch::tests::workspace::occupancy_proceeds_when_occupant_is_caller ... ok
test agent_launch::tests::workspace::occupancy_proceeds_when_occupant_pid_is_dead ... ok
test agent_launch::tests::workspace::occupancy_refuses_and_flags_disagreement_when_running_field_missing ... ok
test agent_launch::tests::workspace::occupancy_refuses_and_flags_disagreement_when_running_pid_differs ... ok
test agent_launch::tests::workspace::occupancy_refuses_when_occupant_is_live_other_pid ... ok
test agent_launch::tests::workspace::claim_workspace_rejects_duplicate_nonzero_but_allows_zero ... ok
test agent_launch::tests::typed_plan::typed_launch_rejects_clan_tab_mismatch ... ok
test agent_launch::tests::workspace::occupancy_refuses_when_running_field_disagrees_with_dead_occupant ... ok
test agent_launch::tests::typed_plan::typed_launch_rejects_dispatch_combined_with_wait_or_agent_session ... ok
test agent_launch::tests::workspace::transfer_numbered_workspace_matches_pid_when_claim_name_changes ... ok
test agent_launch::tests::workspace::transfer_placeholder_workspace_still_matches_claim_name ... ok
test agent_launch::tests::workspace::transfer_workspace_claim_preserves_unknown_suffix_fields ... ok
test agent_launch::tests::workspace::prepare_agent_launch_deferred_and_home_claim_shapes ... ok
test agent_launch::tests::workspace::transfer_workspace_claim_matches_pid_and_preserves_claim_name ... ok
test agent_launch::tests::workspace::workspace_claims_keep_suffix_corrupt_rows_occupied ... ok
test agent_launch::tests::typed_plan::typed_launch_accepts_closed_auto_spellings ... ok
test agent_launch::tests::workspace::transfer_workspace_claim_updates_claim_name ... ok
test agent_launch::tests::workspace::prepare_agent_launch_writes_prompt_and_shapes_process_data ... ok
test agent_launch::tests::typed_plan::typed_launch_rejects_wait_queue_keywords ... ok
test agent_launch::tests::workspace::workspace_claims_parse_valid_rows_and_ignore_malformed ... ok
test agent_models::tests::empty_input_has_no_fabricated_default ... ok
test agent_models::tests::normalizes_recorded_identity_without_resolving_aliases ... ok
test agent_name_template::tests::compares_by_auto_sequence_order ... ok
test agent_models::tests::keeps_first_use_order_and_tracks_latest_repeat ... ok
test agent_name_template::tests::derives_namespace_template_shapes ... ok
test agent_name_template::tests::generates_shortlex_tokens ... ok
test agent_models::tests::providers_are_part_of_the_identity_and_non_agent_rows_are_ignored ... ok
test agent_name_template::tests::matches_template_tokens ... ok
test agent_name_template::tests::parses_keyed_markers ... ok
test agent_name_template::tests::rejects_invalid_or_multiple_markers ... ok
test agent_name_template::tests::parses_exactly_one_marker ... ok
test agent_name_template::tests::renders_template_shapes ... ok
test agent_name_template::tests::scanner_ignores_invalid_braced_and_jinja_forms ... ok
test agent_name_template::tests::scans_markers_with_round_trip_byte_spans ... ok
test agent_name_template::tests::render_and_match_are_exact_inverses ... ok
test agent_launch::tests::typed_plan::typed_launch_rejects_invalid_tab_values ... ok
test agent_ownership::planner::tests::agent_session_generation_accepts_legacy_spelling_but_emits_canonical ... ok
test agent_ownership::planner::tests::clan_generation_mismatch_blocks_claim_overwrite ... ok
test agent_ownership::planner::tests::live_and_container_owners_are_not_selected_without_authorization ... ok
test agent_ownership::planner::tests::cleanup_guard_returns_internal_reservation_state ... ok
test agent_ownership::planner::tests::cleanup_does_not_select_dotted_prefix_descendants_by_name_only ... ok
test agent_publication_batches::tests::batches_preserve_order_and_accept_exact_boundaries ... ok
test agent_launch::tests::typed_plan::typed_launch_proc_accepts_queue_spellings_and_authored_weight ... ok
test agent_publication_batches::tests::empty_and_zero_length_inputs_are_valid ... ok
test agent_ownership::planner::tests::cleanup_closure_follows_retry_and_incoming_relationships_once ... ok
test agent_ownership::planner::tests::incomplete_discovery_and_truncated_closure_block_cleanup ... ok
test agent_publication_batches::tests::rejects_one_file_larger_than_the_budget_with_metadata ... ok
test agent_ownership::planner::tests::reservations_block_batch_duplicate_aliases_and_foreign_namespace ... ok
test agent_publication_batches::tests::rejects_payload_size_overflow ... ok
test agent_ownership::planner::tests::convert_session_operation_accepts_legacy_spelling_but_emits_canonical ... ok
test agent_publication_recovery::replay::tests::apply_refuses_changed_head_and_incomplete_backup ... ok
test agent_publication_recovery::replay::tests::longer_unrelated_text_is_not_a_superset ... ok
test agent_publication_batches::tests::rejects_invalid_or_duplicate_records_before_planning ... ok
test agent_publication_recovery::replay::tests::merge_base_keeps_the_side_changed_since_base ... ok
test agent_ownership::planner::tests::reservations_reuse_current_owner_aliases_and_planned_owner ... ok
test agent_ownership::planner::tests::overlapping_roots_deduplicate_effects_with_attribution ... ok
test agent_publication_recovery::replay::tests::merge_base_still_refuses_two_sided_non_prefix_changes ... ok
test agent_publication_recovery::replay::tests::same_owner_hood_merges_and_foreign_identity_refuses ... ok
test agent_publication_recovery::replay::tests::prefix_proof_keeps_the_longer_version ... ok
test agent_publication_recovery::replay::tests::classifies_browsing_owner_content_and_archive_paths ... ok
test agent_launch::tests::typed_plan::typed_launch_rejects_open_auto_spellings_with_invalid_auto ... ok
test agent_publication_recovery::replay::tests::unsupported_schema_is_rejected ... ok
test agent_publication_recovery::tests::completion_rejects_preexisting_run_page_without_revision ... ok
test agent_publication_recovery::tests::classifies_report_strings_with_existing_precedence ... ok
test agent_publication_recovery::tests::completion_requires_session_page_and_revision_not_an_unrelated_readme ... ok
test agent_publication_recovery::tests::drain_active_rows_can_exhaust_the_budget ... ok
test agent_publication_recovery::tests::drain_error_class_filter_ignores_active_rows ... ok
test agent_publication_recovery::tests::drain_key_tie_break_is_stable ... ok
test agent_publication_recovery::tests::drain_no_match_is_empty_not_unbounded ... ok
test agent_publication_recovery::tests::duplicate_logical_keys_keep_the_first_row ... ok
test agent_publication_recovery::tests::drain_selects_preferred_then_oldest_active_then_stopped ... ok
test agent_publication_recovery::tests::error_class_filter_applies_before_the_limit ... ok
test agent_publication_recovery::tests::existing_archive_or_snapshot_without_prompt_file_are_not_losses ... ok
test agent_publication_recovery::tests::historical_member_spelling_requires_the_run_page ... ok
test agent_publication_recovery::tests::hood_scope_charges_only_attempted_keys_and_retires_repeated_format_errors ... ok
test agent_publication_recovery::tests::hood_scope_quarantines_at_the_attempt_threshold ... ok
test agent_publication_recovery::tests::invalid_limit_and_unknown_error_class_are_rejected ... ok
test agent_publication_recovery::tests::limit_filters_then_prefers_retired_over_quarantined ... ok
test agent_publication_recovery::tests::missing_classify_error_field_is_unknown ... ok
test agent_publication_recovery::tests::missing_local_prompt_source_does_not_clear_an_unknown_obligation ... ok
test agent_publication_recovery::tests::repository_and_unknown_scope_do_not_charge_rows ... ok
test agent_publication_recovery::tests::missing_retry_fields_keep_the_existing_unbounded_contract ... ok
test agent_publication_recovery::tests::select_retries_retired_only_leaves_quarantined_rows ... ok
test agent_publication_recovery::tests::select_retries_revives_only_the_requested_terminal_classes ... ok
test agent_runtime::tests::agent_session_interval_merge_unions_overlap_and_fills_monitor_gap ... ok
test agent_runtime::tests::answered_question_gap_between_segments_is_excluded ... ok
test agent_runtime::tests::approved_plan_followup_starts_a_new_active_segment ... ok
test agent_runtime::tests::admission_predicate_excludes_serial_children_only ... ok
test agent_runtime::tests::empty_input_has_zero_inactive_runtime ... ok
test agent_runtime::tests::earliest_valid_stop_or_finish_is_shared_runtime_end ... ok
test agent_runtime::tests::gaps_and_sequential_members_are_summed ... ok
test agent_runtime::tests::clan_members_launched_independently_count_individually ... ok
test agent_runtime::tests::done_marker_and_dead_pid_members_do_not_occupy ... ok
test agent_runtime::tests::dead_root_with_live_monitor_member_still_occupies_one_slot ... ok
test agent_runtime::tests::inherited_gate_id_without_gate_role_uses_ordinary_started_rule ... ok
test agent_runtime::tests::malformed_terminal_and_reversed_segments_are_rejected ... ok
test agent_runtime::tests::malformed_timestamps_do_not_contribute ... ok
test agent_runtime::tests::inherited_monitor_id_without_monitor_role_uses_ordinary_started_rule ... ok
test agent_runtime::tests::non_agent_workflow_step_record_does_not_occupy ... ok
test agent_runtime::tests::live_parallel_agent_session_members_count_individually ... ok
test agent_runtime::tests::occupancy_member_start_ignores_artifact_timestamp_even_for_monitor ... ok
test agent_runtime::tests::monitor_member_with_pid_but_no_run_started_at_occupies_one_slot ... ok
test agent_runtime::tests::plan_feedback_window_is_excised ... ok
test agent_launch::proc_runtime::tests::prepare_python_script_uses_sase_interpreter ... ok
test agent_launch::proc_runtime::tests::prepare_bash_script_uses_argv_without_interpolation ... ok
test agent_runtime::tests::overlapping_members_are_measured_once ... ok
test agent_runtime::tests::pending_gate_member_frees_its_runner_slot ... ok
test agent_launch::proc_runtime::tests::prepare_proc_script_preserves_an_inherited_user_bin_directory ... ok
test agent_runtime::tests::records_from_two_projects_sharing_an_agent_session_name_count_separately ... ok
test agent_runtime::tests::root_plus_live_serial_child_occupies_exactly_one_slot ... ok
test agent_runtime::tests::open_intervals_end_at_now_and_mark_runtime_active ... ok
test agent_runtime::tests::settled_gate_member_uses_ordinary_started_rule ... ok
test agent_runtime::tests::pending_question_window_extends_to_now_and_does_not_tick ... ok
test agent_runtime::tests::pending_question_on_sessions_only_live_turn_frees_its_slot ... ok
test agent_runtime::tests::settled_monitor_with_live_followup_still_occupies_one_slot ... ok
test agent_runtime::tests::slot_yield_needs_a_resolved_question_answer_time ... ok
test agent_runtime::tests::synthesized_terminal_never_supplies_the_runtime_end ... ok
test agent_runtime::tests::standalone_agent_occupies_one_slot ... ok
test agent_runtime::tests::unresolved_plan_caps_a_live_member_and_does_not_tick ... ok
test agent_runtime::tests::wait_policies_distinguish_plan_review_from_slot_yields ... ok
test agent_runtime::tests::two_independent_agent_sessions_occupy_two_slots ... ok
test agent_scan::index::tests::checkpoint::checkpoint_skips_missing_wal_without_opening ... ok
test agent_clan_record::tests::corrupt_files_error_and_external_rewrites_invalidate_cache ... ok
test agent_cleanup::execution::tests::index_reads_both_triple_and_dict_entry_shapes ... ok
test agent_hold::tests::launch_armer_validation_and_liveness_pruning ... ok
test agent_hold::tests::mutation_preserves_expiry_evidence_until_list_drains_it ... ok
test agent_launch::condition::tests::bash_exit_one_is_skipped ... ok
test agent_archive::store::tests::store_creates_fts5_table ... ok
test agent_archive::store::tests::store_queries_are_read_only_on_populated_wal_index ... ok
test agent_launch::condition::tests::missing_interpreter_and_digest_mismatch_are_errors ... ok
test agent_launch::condition::tests::bash_exit_two_is_condition_error ... ok
test agent_launch::condition::tests::cancel_path_settles_as_condition_error ... ok
test agent_launch::condition::tests::bash_exit_zero_is_eligible ... ok
test agent_archive::store::tests::store_quarantines_corrupt_file_and_rebuilds ... ok
test agent_clan_record::tests::concurrent_writers_keep_both_attributes ... ok
test agent_scan::index::tests::history::prompt_snippet_truncation_stays_on_utf8_char_boundary ... ok
test agent_scan::index::tests::history::refresh_stale_rows_signature_query_does_not_select_record_json ... ok
test agent_launch::condition::tests::python_reads_condition_context_and_matches_bash_skip ... ok
test agent_launch::condition::tests::output_is_truncated_and_cwd_missing_is_error ... ok
test agent_clan_record::tests::generations_keep_only_the_newest_eight ... ok
test agent_clan_record::tests::overwrite_sources_replace_and_fill_only_sources_do_not ... ok
test agent_archive::tests::query_agent_archive_returns_paged_summary_rows ... ok
test agent_launch::condition::tests::timeout_kills_process_group ... ok
test agent_cleanup::execution::tests::concurrent_index_updates_lose_no_identities ... ok
test agent_archive::store::tests::store_set_visibility_merges_projection_and_summaries ... ok
test agent_scan::index::tests::checkpoint::read_write_open_bounds_wal_and_uses_normal_sync ... ok
test agent_scan::index::tests::clan_context::explicit_workflow_state_hidden_is_still_filtered ... ok
test agent_scan::index::tests::clan_context::recent_completed_rows_remain_visible_when_not_dismissed ... ok
test agent_scan::index::tests::checkpoint::checkpoint_skips_small_wal ... ok
test agent_scan::index::tests::history::alias_history_rejects_empty_aliases ... ok
test agent_scan::index::tests::history::alias_history_prefers_canonical_raw_prompt ... ok
test agent_scan::index::tests::history::alias_history_falls_back_to_legacy_first_hop ... ok
test agent_scan::index::tests::clan_context::terminal_workflow_state_rows_are_recent_completed_rows ... ok
test agent_scan::index::tests::clan_context::anonymous_appears_as_agent_workflow_is_not_hidden ... ok
test agent_scan::index::tests::lineage::find_gate_turn_by_gate_id_prefers_newest_real_turn ... ok
test agent_scan::index::tests::history::alias_history_status_counts_projection_rows ... ok
test agent_archive::corpus::tests::compile::compile_drops_orphan_workflow_child_names ... ok
test agent_scan::index::tests::lineage::find_gate_turn_by_gate_id_ignores_inherited_id_on_descendant ... ok
test agent_scan::index::tests::readers::aliases_are_empty_when_the_index_is_missing ... ok
test agent_scan::index::tests::history::alias_history_preserves_request_order_and_empty_groups ... ok
test agent_scan::index::tests::agent_session_filter::agent_session_candidate_decodes_only_matching_rows ... ok
test agent_scan::index::tests::history::alias_history_truncates_newest_first_and_reports_counts ... ok
test agent_scan::index::tests::clan_context::indexed_clan_context_honors_latest_declarations_and_generations ... ok
test agent_scan::index::tests::lineage::find_gate_turn_by_gate_id_respects_project_scoping ... ok
test agent_scan::index::tests::readers::schema_version_is_none_when_file_is_missing ... ok
test agent_scan::index::tests::history::alias_history_filters_hidden_and_project_keys ... ok
test agent_scan::index::tests::readers::schema_version_is_none_when_file_is_unreadable ... ok
test agent_scan::index::tests::clan_context::recorded_clan_attributes_overlay_index_queries ... ok
test agent_scan::index::tests::history::output_variable_history_filters_groups_and_truncates ... ok
test agent_scan::index::tests::history::alias_history_prompt_snippets_strip_collapse_and_truncate ... ok
test agent_scan::index::tests::agent_session_filter::agent_session_candidate_selects_only_that_lane ... ok
test agent_archive::corpus::tests::query::query_lookup_returns_empty_for_orphan_workflow_child ... ok
test agent_archive::corpus::tests::compile::compile_resolves_workflow_child_owner_by_parent_timestamp ... ok
test agent_archive::store::tests::store_upsert_query_signature_and_delete_round_trip ... ok
test agent_group_archive::tests::recent_groups_are_capped_and_list_newest_first ... ok
test agent_scan::index::tests::lineage::find_gate_turn_by_gate_id_returns_none_for_unknown_id ... ok
test agent_archive::corpus::tests::query::query_lookup_resolves_child_with_own_run_id_via_parent_timestamp ... ok
test agent_scan::index::tests::history::load_agent_artifact_records_returns_full_records_for_dirs_and_aliases ... ok
test agent_scan::index::tests::lineage::related_artifact_dirs_follow_retry_and_parent_lineage ... ok
test agent_scan::index::tests::history::alias_history_revalidate_refreshes_candidate_rows ... ok
test agent_scan::index::tests::readers::schema_version_is_zero_when_meta_key_is_missing ... ok
test agent_scan::index::tests::readers::schema_version_is_zero_when_meta_table_is_missing ... ok
test agent_scan::index::tests::checkpoint::checkpoint_truncates_oversized_wal ... ok
test agent_scan::index::tests::lineage::find_gate_turn_by_gate_id_uses_indexed_lookup_not_full_decode ... ok
test agent_archive::store::tests::store_rebuilds_incompatible_schema ... ok
test agent_archive::tests::mark_agent_archive_bundles_revived_updates_projection_without_bundle_mutation ... ok
test agent_scan::index::tests::clan_context::schema_v19_upgrade_refreshes_record_json_for_model_aliases ... ok
test agent_scan::index::tests::clan_context::schema_v18_upgrade_adds_xprompts_signature_column ... ok
test agent_scan::index::tests::history::alias_history_projection_replaces_and_deletes_rows ... ok
test agent_scan::index::tests::clan_context::bounded_query_retains_dismissed_clan_declaration_as_context ... ok
test agent_scan::index::tests::clan_context::migration_recomputes_hidden_for_v1_indexes ... ok
test agent_scan::index::tests::lineage::wait_completed_records_are_indexed_as_running ... ok
test agent_scan::index::tests::machine_projection::machine_candidate_uses_meta_then_done_machine_precedence ... ok
test agent_scan::index::tests::storage::query_keeps_corrupt_existing_index_strict ... ok
test agent_archive::corpus::tests::compile::compile_derives_time_bases_runtime_and_utc_instants ... ok
test agent_scan::index::tests::machine_projection::only_monitors_filters_to_monitor_agent_session_role ... ok
test agent_scan::index::tests::lineage::resolve_agent_session_dismissal_lineage_follows_parent_to_dismissed_root ... ok
test agent_scan::index::tests::storage::replace_unusable_index_file_renames_sidecars ... ok
test agent_scan::index::tests::machine_projection::machine_candidate_includes_mixed_provenance_agent_session_relatives ... ok
test agent_scan::index::tests::machine_projection::machine_candidate_column_is_populated_and_queryable ... ok
test agent_scan::index::tests::machine_projection::machine_candidate_keeps_conflicting_source_and_owner_values ... ok
test agent_scan::index::tests::readers::projection_rejects_an_empty_column_list ... ok
test agent_scan::index::tests::terminalization::abandoned_terminalization_prefers_stopped_at_then_directory_mtime ... ok
test agent_scan::index::tests::readers::projection_rejects_unknown_column_names ... ok
test agent_scan::index::tests::machine_projection::list_record_shape_projects_only_heavy_leaves ... ok
test agent_scan::index::tests::clan_context::schema_v24_upgrade_backfills_done_outcome_projection ... ok
test agent_scan::index::tests::readers::schema_version_read_does_not_create_an_index ... ok
test agent_scan::index::tests::readers::projection_serves_catalog_and_provenance_column_sets ... ok
test agent_scan::index::tests::agent_session_filter::legacy_agent_family_column_migrates_in_place ... ok
test agent_scan::index::tests::agent_session_filter::legacy_agent_family_column_beside_agent_session_merges_in_place ... ok
test agent_scan::index::tests::history::schema_v21_upgrade_backfills_model_alias_projection ... ok
test agent_scan::index::tests::lineage::resolve_agent_session_dismissal_lineage_honors_dead_seed_own_dismissal ... ok
test agent_archive::corpus::tests::compile::compile_builds_clan_session_and_singleton_container_metadata ... ok
test agent_scan::index::tests::self_heal::full_history_revalidate_drops_deleted_artifact_instead_of_stale_json ... ok
test agent_scan::index::tests::self_heal::full_history_revalidate_discovers_unindexed_artifact_and_claims_complete ... ok
test agent_scan::index::tests::self_heal::cached_full_history_after_reconcile_reuses_watermark_without_discovery ... ok
test agent_scan::index::tests::readers::schema_version_read_does_not_migrate_a_stale_index ... ok
test agent_scan::index::tests::readers::projection_does_not_migrate_a_stale_index ... ok
test agent_scan::index::tests::self_heal::tier1_revalidate_with_candidate_filter_does_not_prefilter_all_rows ... ok
test agent_scan::index::tests::visibility::index_query_wire_round_trips_active_limit ... ok
test agent_archive::corpus::tests::compile::compile_uses_hidden_top_level_rows_and_child_name_map ... ok
test agent_scan::index::tests::self_heal::full_history_revalidate_repairs_several_stale_rows_in_one_pass ... ok
test agent_scan::index::tests::storage::cached_query_returns_rebuilt_records_without_revalidation ... ok
test agent_scan::index::tests::windowed_query::agents_list_projection_defaults_off ... ok
test agent_scan::index::tests::storage::cached_query_does_not_refresh_stale_marker_rows ... ok
test agent_scan::index::tests::self_heal::query_self_heals_appended_feedback_submitted_at ... ok
test agent_scan::index::tests::self_heal::query_self_heals_hidden_to_visible_before_visible_filter ... ok
test agent_scan::index::tests::self_heal::query_self_heals_done_creation_before_completed_filter ... ok
test agent_scan::index::tests::storage::bounded_artifact_index_delete_skips_locked_database ... ok
test agent_scan::index::tests::self_heal::query_self_heals_appended_plan_submitted_at ... ok
test agent_scan::index::tests::self_heal::query_self_heals_newly_added_run_started_at ... ok
test agent_scan::index::tests::lineage::schema_v30_upgrade_adds_and_backfills_gate_turn_id_projection ... ok
test agent_scan::index::tests::storage::read_only_open_falls_back_when_index_missing ... ok
test agent_scan::index::tests::self_heal::query_self_heals_running_to_done_transition ... ok
test agent_scan::index::tests::storage::status_reports_freelist_and_file_size ... ok
test agent_scan::index::tests::storage::read_only_open_cannot_write ... ok
test agent_scan::index::tests::self_heal::query_self_heals_waiting_deletion_to_running ... ok
test agent_scan::layout::tests::canonical_ace_run_path_is_day_sharded ... ok
test agent_scan::layout::tests::collect_prefers_sharded_duplicate_timestamp ... ok
test agent_scan::layout::tests::non_ace_run_path_stays_flat ... ok
test agent_scan::layout::tests::parse_accepts_legacy_and_sharded_paths ... ok
test agent_scan::layout::tests::parse_rejects_malformed_shard_paths ... ok
test agent_scan::layout::tests::resolve_legacy_path_to_shard_when_present ... ok
test agent_scan::index::tests::self_heal::query_skips_rescan_when_signatures_match ... ok
test agent_scan::scanner::tests::agent_meta_wire_omits_absent_auto_restart ... ok
test agent_scan::scanner::tests::agent_meta_wire_omits_absent_autonomy ... ok
test agent_scan::scanner::tests::capacity_only_keeps_active_dir_without_running_or_waiting_marker ... ok
test agent_scan::scanner::tests::capacity_only_omits_plan_path_and_used_macros ... ok
test agent_scan::scanner::tests::capacity_only_preserves_capacity_snapshot_fields ... ok
test agent_scan::scanner::tests::durable_readers_prefer_canonical_macros_and_raw_prompt ... ok
test agent_scan::scanner::tests::scanner_accepts_explicit_zero_queue_weight_but_rejects_implicit_zero ... ok
test agent_scan::scanner::tests::scanner_canonicalizes_agent_tab_and_drops_invalid_values ... ok
test agent_scan::scanner::tests::scanner_coerces_created_epics_tolerantly ... ok
test agent_scan::scanner::tests::scanner_coerces_finalizer_status_tolerantly ... ok
test agent_scan::scanner::tests::scanner_coerces_wait_epic_follows_tolerantly ... ok
test agent_scan::index::tests::self_heal::full_history_revalidate_repairs_hidden_toggle_via_dirty_directory ... ok
test agent_scan::scanner::tests::scanner_defaults_absent_alias_trail_and_origin ... ok
test agent_scan::scanner::tests::scanner_derives_legacy_auto_fields_from_autonomy_record ... ok
test agent_scan::scanner::tests::scanner_defaults_absent_monitor_next_model ... ok
test agent_scan::scanner::tests::scanner_prefers_turn_keys_and_stores_monitor_kind ... ok
test agent_scan::scanner::tests::scanner_distinguishes_absent_valid_and_invalid_queue_weight ... ok
test agent_scan::scanner::tests::capacity_only_skips_done_dirs_before_parsing_markers ... ok
test agent_scan::scanner::tests::scanner_preserves_canonical_legacy_and_dual_queue_capacity ... ok
test agent_scan::scanner::tests::scanner_reads_auto_approve_argument ... ok
test agent_scan::scanner::tests::scanner_reads_agent_session_spellings_first ... ok
test agent_scan::scanner::tests::scanner_projects_runner_claim_owner_key_and_ignores_blank ... ok
test agent_scan::scanner::tests::scanner_reads_auto_restart_object ... ok
test agent_archive::corpus::tests::compile::compile_reports_missing_rebuilding_and_unsupported_index_status ... ok
test agent_scan::scanner::tests::scanner_refreshes_stale_builtin_autonomy_policy ... ok
test agent_scan::index::tests::terminalization::done_marker_without_finished_at_or_stopped_at_indexes_null ... ok
test agent_scan::scanner::tests::scanner_round_trips_alias_trail_and_origin ... ok
test agent_scan::scanner::tests::scanner_reads_valid_queue_capacity_multiplier_from_meta_and_waiting ... ok
test agent_scan::scanner::tests::scanner_round_trips_auto_restart_through_snapshot ... ok
test agent_scan::index::tests::history::output_variable_projection_backfills_replaces_and_deletes_rows ... ok
test agent_scan::scanner::tests::scanner_round_trips_gate_turn_metadata ... ok
test agent_scan::index::tests::terminalization::explicit_done_finished_at_is_not_overridden_by_stopped_at ... ok
test agent_scan::selector::tests::parser_accepts_nested_and_escaped_paths ... ok
test agent_scan::scanner::tests::scanner_round_trips_monitor_next_model ... ok
test agent_scan::selector::tests::parser_rejects_invalid_selectors ... ok
test agent_scan::selector::tests::parser_splits_dotted_names_from_the_right ... ok
test agent_scan::index::tests::terminalization::missing_done_finished_at_indexes_from_meta_stopped_at ... ok
test agent_scan::wire::tests::agent_meta_wire_accepts_all_three_member_keys_but_emits_canonical ... ok
test agent_scan::wire::tests::agent_meta_wire_accepts_legacy_spellings_but_emits_canonical ... ok
test agent_scan::wire::tests::agent_meta_wire_defaults_created_epics_empty ... ok
test agent_scan::wire::tests::agent_meta_wire_maps_legacy_proc_turn_kind_to_monitor ... ok
test agent_scan::wire::tests::agent_meta_wire_omits_absent_auto_restart ... ok
test agent_scan::wire::tests::agent_meta_wire_omits_absent_finalizer_status ... ok
test agent_scan::index::tests::storage::rebuild_replaces_corrupt_existing_index ... ok
test agent_scan::wire::tests::agent_meta_wire_round_trips_alias_trail_and_origin ... ok
test agent_scan::wire::tests::agent_meta_wire_round_trips_auto_restart ... ok
test agent_scan::wire::tests::agent_meta_wire_round_trips_created_epics ... ok
test agent_scan::wire::tests::agent_meta_wire_round_trips_every_gate_field ... ok
test agent_scan::wire::tests::agent_meta_wire_round_trips_every_monitor_field ... ok
test agent_scan::wire::tests::agent_meta_wire_round_trips_finalizer_status_summary ... ok
test agent_scan::wire::tests::agent_meta_wire_without_gate_fields_still_parses ... ok
test agent_scan::wire::tests::agent_meta_wire_without_monitor_fields_still_parses ... ok
test agent_scan::wire::tests::done_marker_wire_round_trips_every_gate_field ... ok
test agent_scan::wire::tests::done_marker_wire_accepts_all_three_member_keys_but_emits_canonical ... ok
test agent_scan::index::tests::terminalization::settled_monitor_without_finished_at_stays_in_recent_completed_window ... ok
test agent_scan::wire::tests::done_marker_wire_without_monitor_fields_still_parses ... ok
test agent_scan::wire::tests::done_marker_wire_round_trips_every_monitor_field ... ok
test agent_scan::wire::tests::prompt_step_marker_wire_defaults_absent_alias_trail ... ok
test agent_scan::wire::tests::prompt_step_marker_wire_round_trips_alias_trail_and_origin ... ok
test agent_session::tests::absent_parent_reports_absent ... ok
test agent_session::tests::dismissed_parent_reports_dismissed ... ok
test agent_session::tests::duplicate_newest_timestamp_reports_ambiguous ... ok
test agent_session::tests::newest_terminal_visible_parent_wins ... ok
test agent_session::tests::non_terminal_parent_reports_running ... ok
test agent_session_manifest::tests::canonical_set_contains_both_page_paths ... ok
test agent_session_manifest::tests::clan_containers_add_no_pages ... ok
test agent_session_manifest::tests::exact_current_and_legacy_sets_classify ... ok
test agent_session_manifest::tests::hood_without_sessions_has_no_legacy_exception ... ok
test agent_session_manifest::tests::legacy_family_kind_counts_as_session_container ... ok
test agent_scan::index::tests::visibility::active_limit_prioritizes_waiting_rows_over_newer_stale_rows ... ok
test agent_session_manifest::tests::omitted_list_is_slim ... ok
test agent_session_manifest::tests::partial_migration_is_invalid ... ok
test agent_session_manifest::tests::rejects_bad_schema_and_snapshot ... ok
test agent_session_manifest::tests::repair_keeps_current_and_supported_legacy_lists ... ok
test agent_session_manifest::tests::repair_normalizes_safe_stale_lists_and_derives_snapshot_counts ... ok
test agent_session_manifest::tests::repair_skips_unsafe_or_ambiguous_lists ... ok
test agent_session_manifest::tests::unsorted_or_unsafe_lists_are_invalid ... ok
test agent_stats::activity::tests::rejects_invalid_range_before_opening_index ... ok
test agent_stats::activity::tests::skips_malformed_bundles_and_ignores_legacy_question_store ... ok
test agent_scan::index::tests::terminalization::terminalize_stale_active_rows_skips_fresh_missing_marker_race ... ok
test agent_stats::activity::tests::aggregates_logs_and_project_scoped_gate_bundles ... ok
test agent_scan::index::tests::terminalization::terminalize_stale_active_rows_skips_workspace_claim ... ok
test agent_stats::activity::tests::maps_both_response_shapes_and_pending_plan_bundles ... ok
test agent_stats::run::tests::query::rejects_invalid_ranges_and_bucket_explosions ... ok
test agent_stats::run::tests::query::runtime_percentiles_interpolate_sorted_durations ... ok
test agent_archive::store::tests::store_concurrent_upsert_and_compile_verify_ok ... ok
test agent_scan::index::tests::self_heal::unchanged_full_history_revalidate_commits_nothing ... ok
test agent_scan::index::tests::machine_projection::schema_v29_upgrade_adds_imported_owner_machine_projection ... ok
test agent_scan::index::tests::lineage::schema_v33_index_with_both_gate_columns_keeps_legacy_projection ... ok
test agent_scan::index::tests::machine_projection::schema_v27_upgrade_adds_and_backfills_source_machine_projection ... ok
test agent_scan::index::tests::lineage::schema_v34_upgrade_renames_gate_shell_id_column_in_place ... ok
test agent_scan::index::tests::readers::aliases_round_trip_upsert_list_and_delete ... ok
test agent_scan::index::tests::storage::late_xprompts_file_refreshes_cached_record ... ok
test agent_scan::index::tests::storage::upsert_and_delete_one_artifact_row ... ok
test agent_scan::index::tests::self_heal::query_self_heals_pending_question_creation_and_deletion ... ok
test agent_scan::index::tests::visibility::recent_completed_limit_does_not_bound_active_rows ... ok
test agent_scan::index::tests::storage::durable_canonical_selection_refreshes_indexed_record ... ok
test agent_archive::store::tests::store_queries_return_none_for_old_or_incompatible_index_without_dropping_tables ... ok
test agent_scan::index::tests::visibility::tier1_active_query_is_bounded_to_newest_incomplete_rows ... ok
test agent_scan::index::tests::terminalization::terminalize_stale_active_rows_revalidates_new_running_marker ... ok
test agent_scan::index::tests::windowed_query::agents_list_projection_derives_clan_context_from_waiting_only_scalars ... ok
test agent_stats::runner::tests::host_liveness_requires_current_matching_claim_identity ... ok
test agent_stats::runner::tests::inherited_monitor_id_does_not_fill_agent_session_gap ... ok
test agent_stats::runner::tests::monitor_handoff_gap_does_not_reopen_agent_session_interval ... ok
test agent_stats::runner::tests::open_intervals_require_liveness_and_missing_starts_are_not_invalid ... ok
test agent_stats::runner::tests::overlapping_serial_agent_session_turns_count_as_one_slot ... ok
test agent_stats::runner::tests::simultaneous_boundaries_do_not_create_phantom_occupancy ... ok
test agent_stats::runner::tests::trend_is_strictly_bounded_and_keeps_partial_final_slice ... ok
test agent_stats::wire::tests::macro_request_keys_emit_macro_spellings ... ok
test agent_stats::wire::tests::macro_stats_response_emits_macro_keys ... ok
test agent_stats::wire::tests::older_commit_stats_without_committing_runs_default ... ok
test agent_stats::wire::tests::older_macro_row_without_truncation_counts_defaults ... ok
test agent_stats::wire::tests::older_run_stats_payload_without_macros_deserializes ... ok
test agent_stats::wire::tests::older_run_stats_payload_without_runners_deserializes ... ok
test agent_stats::wire::tests::older_run_stats_request_uses_macro_defaults ... ok
test agent_stats::wire::tests::runtime_group_by_session_accepts_legacy_spelling_but_emits_canonical ... ok
test agent_tab::tests::canonicalize_rejects_reserved_empty_and_invalid ... ok
test agent_tab::tests::canonicalize_trims_lowercases_and_validates ... ok
test agent_tab::tests::catalog_blank_local_alias_falls_back_to_local ... ok
test agent_tab::tests::catalog_disambiguates_remote_alias_matching_local_name ... ok
test agent_tab::tests::catalog_disambiguates_remote_alias_named_local ... ok
test agent_tab::tests::catalog_hides_default_label_outside_machine_mode ... ok
test agent_tab::tests::catalog_keeps_local_remote_rule_with_local_alias_set ... ok
test agent_tab::tests::catalog_names_local_tab_after_local_alias ... ok
test agent_tab::tests::catalog_options_without_local_alias_still_deserializes ... ok
test agent_tab::tests::catalog_orders_default_machines_then_named ... ok
test agent_tab::tests::catalog_trims_local_alias ... ok
test agent_tab::tests::catalog_uses_configured_order_and_renamed_alias ... ok
test agent_tab::tests::effective_tab_named_wins_and_machine_rules_apply ... ok
test agent_tribe::tests::display_key_prefers_legacy_override_over_public_default ... ok
test agent_tribe::tests::display_resolution_allows_cross_layer_legacy_customization ... ok
test agent_tribe::tests::display_resolution_reports_same_layer_alias_collision ... ok
test agent_tribe::tests::identity_resolution_keeps_builtin_job_canonicalization_without_history ... ok
test agent_tribe::tests::identity_resolution_preserves_current_stored_job_assignment ... ok
test agent_tribe::tests::identity_resolution_rejects_source_ambiguous_job_aliases ... ok
test agent_tribe::tests::metadata_shape_normalization_preserves_stored_job ... ok
test agent_tribe::tests::public_job_input_canonicalizes_to_stored_chop ... ok
test artifact_consumption::tests::reader_is_tolerant_of_bad_rows_and_an_absent_file ... ok
test artifact_consumption::tests::restricted_summary_omits_unselected_and_never_consumed_refs ... ok
test artifact_consumption::tests::summary_distinguishes_events_from_distinct_agents ... ok
test artifact_file::context::tests::deduplicates_by_id_retaining_first_requested_dependency ... ok
test artifact_file::context::tests::different_projects_and_generations_are_independent_producers ... ok
test artifact_file::context::tests::empty_batch_never_opens_the_index ... ok
test artifact_file::context::tests::excludes_chat_rows_even_when_explicitly_indexed ... ok
test artifact_file::context::tests::handles_multiple_producers_within_one_dependency_in_given_order ... ok
test artifact_file::context::tests::matches_exact_producer_directory_despite_reused_agent_names ... ok
test artifact_file::context::tests::missing_index_tolerates_nonempty_batch_as_empty_result ... ok
test artifact_file::context::tests::nonempty_batch_against_unreadable_index_is_an_error ... ok
test artifact_file::context::tests::orders_by_dependency_then_producer_then_creation_time_and_id ... ok
test artifact_file::context::tests::preserves_explicit_flag ... ok
test artifact_file::context::tests::tolerates_malformed_index_lines ... ok
test artifact_file::context::tests::vcs_backed_rows_have_no_stored_path ... ok
test artifact_file::economics::tests::aggregates_mixed_rows_truncation_redundancy_and_projections ... ok
test artifact_file::economics::tests::single_day_window_has_finite_rates_and_schema_is_checked ... ok
test artifact_file::retention::tests::each_additional_predicate_filters_generation_candidates ... ok
test artifact_file::retention::tests::invalid_now_and_schema_are_rejected ... ok
test artifact_file::retention::tests::predicates_compose_clamp_generation_floor_and_limit_deterministically ... ok
test artifact_file::retention::tests::protects_explicit_and_referenced_and_separates_byte_free_rows ... ok
test artifact_file::retention::tests::retention_now_uses_its_embedded_offset_calendar_date ... ok
test artifact_file::retention::tests::zero_keep_without_other_predicates_disables_selection ... ok
test artifact_file::tests::absent_index_is_empty_and_invalid_since_is_an_error ... ok
test artifact_file::tests::embedded_offset_controls_calendar_date_but_sorting_uses_instant ... ok
test artifact_file::tests::parser_accepts_supported_range_and_skips_bad_rows ... ok
test artifact_file::tests::query_applies_every_filter_individually_and_combined ... ok
test artifact_file::tests::query_sorts_newest_first_missing_last_and_applies_limit ... ok
test artifact_file::tests::since_uses_plan_search_forms_and_excludes_missing_dates ... ok
test artifact_file::tests::unused_filter_runs_before_limit_and_tolerates_missing_ledgers ... ok
test agent_scan::index::tests::visibility::active_query_excludes_dismissed_identity_after_rebuild ... ok
test agent_scan::index::tests::storage::schema_v33_index_migrates_to_current ... ok
test artifact_file::trash::tests::refuses_symlink_escape_and_unsafe_entry_id ... ok
test agent_scan::index::tests::windowed_query::agents_list_projection_full_history_skips_non_projectable_records ... ok
test agent_scan::index::tests::windowed_query::agents_list_projection_keeps_noop_done_and_skips_hidden ... ok
test agent_scan::index::tests::windowed_query::agents_list_projection_keeps_home_running_and_workflow_records ... ok
test agent_scan::index::tests::windowed_query::index_rebuild_preserves_canonical_queue_capacity_without_waiting_marker ... ok
test agent_scan::index::tests::windowed_query::agents_list_projection_preserves_agent_session_relative_projectable_extras ... ok
test agent_archive::corpus::tests::query::query_light_rows_carry_bundle_path_stop_time_and_dismissed_at ... ok
test artifact_file::vcs::tests::checkout_head_and_historical_path_use_bounded_git ... ok
test artifact_file::vcs::tests::rejects_cache_path_escape_inputs ... ok
test agent_group_archive::tests::save_and_list_pages_saved_groups_newest_first ... ok
test artifact_link::cutover::tests::attestation_is_stable_and_head_sensitive ... ok
test artifact_link::cutover::tests::classifies_and_converts_legacy_outbox_lines ... ok
test artifact_link::cutover::tests::import_identity_is_order_stable_and_head_sensitive ... ok
test artifact_link::cutover::tests::marker_round_trips_with_canonical_json ... ok
test artifact_link::cutover::tests::progress_walks_recovery_phases ... ok
test artifact_link::events::tests::alias_chains_resolve_edges_and_cycles_or_conflicts_fail ... ok
test artifact_link::events::tests::bytes_validation_rejects_floats_and_path_mismatches ... ok
test artifact_link::cutover::tests::read_state_reports_four_states ... ok
test artifact_link::events::tests::baseline_imports_preserve_counts_and_are_one_shot_by_import_id ... ok
test artifact_link::events::tests::edge_put_supersedes_named_versions_and_uses_lexical_tie_break ... ok
test artifact_link::events::tests::event_edge_identity_normalizes_directed_and_undirected_relations ... ok
test artifact_link::events::tests::canonical_json_digest_and_path_are_byte_stable ... ok
test artifact_link::events::tests::predecessor_ids_known_on_other_edges_are_rejected ... ok
test artifact_link::events::tests::reduction_deduplicates_exact_retries_but_counts_distinct_observations ... ok
test artifact_link::events::tests::reduction_rejects_operation_id_collisions ... ok
test artifact_link::events::tests::remove_before_add_removes_only_observed_versions ... ok
test artifact_link::events::tests::stable_background_producer_contract_is_replay_stable ... ok
test artifact_link::events::tests::validation_rejects_bad_identifiers_payloads_and_edges ... ok
test artifact_link::events::tests::reduction_is_stable_for_reordered_and_duplicated_deliveries ... ok
test artifact_link::index::tests::empty_and_malformed_rows_do_not_reject_the_snapshot ... ok
test artifact_link::index::tests::colliding_agent_alias_resolves_to_earliest_row_in_row_order ... ok
test artifact_link::index::tests::empty_lookup_keys_yield_no_rows ... ok
test artifact_link::index::tests::missing_ref_is_absent_not_indexed_non_selectable ... ok
test artifact_link::index::tests::frozen_handle_supports_concurrent_reads ... ok
test artifact_file::trash::tests::byte_free_collision_and_unreadable_listing_are_deterministic ... ok
test agent_scan::index::tests::windowed_query::agents_list_projection_skips_marker_only_active_records ... ok
test artifact_link::index::tests::native_build_and_selected_query_are_measurable ... ok
test artifact_link::index::tests::neighbor_target_uses_row_project_not_first_indexed_target ... ok
test artifact_link::index::tests::parity_fixture_alias_collision_does_not_shadow_canonical ... ok
test artifact_link::index::tests::parity_fixture_self_edge_and_projected_writability ... ok
test artifact_link::index::tests::parity_fixture_first_wins_equal_uses_and_max_uses_unequal ... ok
test artifact_link::index::tests::tolerant_duplicate_winner_uses_legacy_counts_and_edges_keep_first_row ... ok
test artifact_link::index::tests::parity_fixture_skips_empty_refs_and_keeps_malformed_endpoints ... ok
test artifact_link::index::tests::project_query_preserves_first_row_patch_edges ... ok
test artifact_link::index::tests::tolerant_string_fields_match_legacy_python_str ... ok
test artifact_link::inlet::tests::empty_list_is_entries ... ok
test artifact_link::inlet::tests::mapping_links_value_is_unrecognized ... ok
test artifact_link::inlet::tests::matching_shape_is_entries ... ok
test artifact_link::inlet::tests::missing_key_is_absent ... ok
test artifact_link::inlet::tests::mkdocs_label_path_is_unrecognized ... ok
test artifact_link::inlet::tests::no_frontmatter_is_absent ... ok
test artifact_link::index::tests::tolerant_uses_match_legacy_truthiness_truncation_and_strings ... ok
test artifact_link::managed_table::tests::empty_links_table_removes_the_block ... ok
test artifact_link::managed_table::tests::links_after_plan_header_does_not_trip_header_invalid ... ok
test artifact_link::managed_table::tests::links_render_sorts_and_emits_pointer ... ok
test artifact_link::managed_table::tests::links_skip_host_document_reference_labels ... ok
test artifact_link::managed_table::tests::links_upsert_is_top_anchored_and_idempotent ... ok
test artifact_link::merge::tests::accepts_one_sided_and_identical_deletes ... ok
test artifact_link::merge::tests::accepts_one_sided_and_identical_edits ... ok
test artifact_link::merge::tests::rejects_competing_same_key_edits_and_modify_delete ... ok
test artifact_link::merge::tests::merge_is_idempotent ... ok
test artifact_link::merge::tests::unions_distinct_additions_in_deterministic_order_after_base_rows ... ok
test artifact_link::merge::tests::validates_schema_artifact_ref_and_duplicates ... ok
test artifact_link::ownership::tests::baseline_import_rows_contribute_document_owners ... ok
test artifact_link::ownership::tests::owner_requirements_partition_and_dedupe_event_refs ... ok
test artifact_link::ownership::tests::receipt_accepts_local_or_bead_durable_owners ... ok
test artifact_link::ownership::tests::receipt_classifies_per_endpoint_outcomes ... ok
test artifact_link::index::tests::parity_fixture_pins_every_link_chip_and_target_field ... ok
test artifact_link::ownership::tests::receipt_requires_resolved_roots_and_durable_receipts ... ok
test artifact_link::path::tests::bead_page_uses_readme_for_lineage_root ... ok
test artifact_link::ownership::tests::receipt_rejects_schema_or_operation_mismatches ... ok
test artifact_link::path::tests::document_kind_is_itself ... ok
test artifact_link::path::tests::published_markdown_file_is_itself ... ok
test artifact_link::path::tests::goal_has_no_markdown_file ... ok
test artifact_link::path::tests::stitch_has_no_markdown_file ... ok
test artifact_link::path::tests::unpublished_file_uses_local_pages_dir ... ok
test artifact_link::path::tests::companion_uses_stem_and_disambiguates_on_collision ... ok
test artifact_link::publication_retry::tests::deferred_attempt_does_not_consume_failure_backoff ... ok
test artifact_link::publication_retry::tests::due_policy_reports_retry_after_and_aging_warning ... ok
test artifact_link::publication_retry::tests::failed_attempts_exponentially_back_off_at_six_hours ... ok
test artifact_link::relation::tests::awaits_is_a_projection_only_agent_to_bead_relation ... ok
test artifact_link::publication_retry::tests::pending_registration_preserves_age_across_head_changes ... ok
test artifact_link::relation::tests::builtins_cover_v1_table ... ok
test artifact_link::relation::tests::every_builtin_documents_direction_and_examples ... ok
test artifact_link::relation::tests::implements_settles_the_plan_bead_direction ... ok
test artifact_link::relation::tests::inverse_label_is_from_this_document ... ok
test artifact_link::relation::tests::produced_by_and_launched_round_trip ... ok
test artifact_link::relation::tests::produced_by_covers_stitch_and_bead_sources ... ok
test artifact_link::relation::tests::reserved_slugs_point_at_bead_dep ... ok
test artifact_link::relation::tests::unknown_slug_lists_builtins ... ok
test artifact_link::row_resolution::tests::parse_link_ref_parts_strips_aliases_sigil_and_fragment ... ok
test artifact_link::row_resolution::tests::guards_do_not_resolve_virtual_or_malformed_refs ... ok
test artifact_link::row_resolution::tests::project_hint_precedes_deterministic_fallback ... ok
test artifact_link::row_resolution::tests::resolver_matches_key_probe_equivalence ... ok
test artifact_link::wire::tests::canonicalize_strips_sigil_and_rewrites_kind_aliases ... ok
test artifact_link::wire::tests::directed_same_pair_may_carry_several_relations ... ok
test artifact_link::wire::tests::prompt_ref_rewrite_increments_uses_and_keeps_created_at ... ok
test artifact_link::wire::tests::reserved_slugs_are_not_stored ... ok
test artifact_link::row_resolution::tests::resolves_class_a_row_identity_shapes ... ok
test artifact_link::wire::tests::undirected_related_dedups_either_direction ... ok
test artifact_link::wire::tests::validate_rejects_multiline_and_overlong_descriptions ... ok
test artifact_link_eligibility::policy::tests::a_real_change_makes_its_repo_qualify ... ok
test artifact_link_eligibility::policy::tests::bookkeeping_only_repos_are_ineligible ... ok
test artifact_link_eligibility::policy::tests::empty_repos_are_ineligible ... ok
test artifact_link::wire::tests::validate_rejects_self_links_and_blank_descriptions ... ok
test agent_stats::run::tests::macros::aggregates_swarm_xprompt_kind_through_stats_wire ... ok
test artifact_link_eligibility::policy::tests::rejects_blank_run_id ... ok
test artifact_link_eligibility::policy::tests::rejects_unsupported_schema_version ... ok
test artifact_link_eligibility::policy::tests::release_evidence_rejects_a_different_agent_in_the_same_session ... ok
test agent_stats::activity::tests::counts_gate_even_when_index_row_is_hidden_abandoned ... ok
test artifact_link_eligibility::policy::tests::release_evidence_rejects_a_different_run_id ... ok
test artifact_link_eligibility::policy::tests::release_evidence_requires_eligible_decision ... ok
test artifact_link_eligibility::policy::tests::release_evidence_round_trips_and_validates_against_the_same_run ... ok
test artifact_link_eligibility::policy::tests::serde_rejects_unknown_change_role ... ok
test artifact_link_eligibility::policy::tests::serde_rejects_unknown_fields ... ok
test artifact_link_eligibility::policy::tests::serde_round_trips_the_decision_wire ... ok
test artifact_object_store::tests::object_relpath_uses_digest_shard ... ok
test artifact_object_store::tests::object_paths_reject_non_full_lowercase_sha256 ... ok
test artifact_ref::entry::tests::rejects_empty_stable_id_and_bad_kind ... ok
test artifact_ref::entry::tests::rejects_malformed_revision_digest_and_property_keys ... ok
test artifact_ref::entry::tests::valid_entry_passes ... ok
test artifact_ref::expansion::tests::double_braces_escape_to_literal_braces ... ok
test artifact_ref::expansion::tests::missing_value_is_a_render_error ... ok
test artifact_ref::expansion::tests::substituted_values_are_never_rescanned ... ok
test artifact_ref::expansion::tests::unknown_placeholder_and_unbalanced_braces_are_rejected ... ok
test artifact_ref::expansion::tests::validate_returns_placeholders_in_first_seen_order_without_duplicates ... ok
test artifact_ref::file_roots::tests::file_path_payload_still_round_trips_as_a_file_path_payload ... ok
test artifact_ref::file_roots::tests::directories_and_size_overages_are_denied ... ok
test artifact_ref::file_roots::tests::exact_resolution_echoes_caller_path_through_symlinked_parent ... ok
test artifact_ref::file_roots::tests::missing_inside_root_is_missing_and_traversal_escape_is_filtered ... ok
test artifact_ref::file_roots::tests::absolute_and_home_paths_resolve_to_one_logical_path ... ok
test artifact_ref::file_roots::tests::overlapping_roots_are_ambiguous_and_glob_miss_is_filtered ... ok
test artifact_ref::filter::tests::explicit_empty_filter_allows_nothing ... ok
test artifact_ref::filter::tests::batch_filter_reports_allowed_and_filtered_in_input_order ... ok
test artifact_ref::file_roots::tests::relative_paths_and_zero_roots_are_rejected_without_guessing ... ok
test artifact_ref::filter::tests::globstar_matches_root_and_nested_paths_case_sensitively ... ok
test artifact_ref::filter::tests::malformed_patterns_and_unsafe_payloads_error ... ok
test artifact_ref::filter::tests::negative_only_allows_everything_except_vetoes ... ok
test artifact_ref::filter::tests::positives_or_together_and_negations_veto ... ok
test artifact_ref::kinds::tests::attachment_kind_is_reserved_live_and_absent_from_completion ... ok
test artifact_ref::kinds::tests::canonical_parse_rewrites_commit_and_plans_but_nothing_else ... ok
test artifact_ref::kinds::tests::catalog_lists_reserved_kinds_offered_in_completion ... ok
test artifact_ref::kinds::tests::catalog_marks_aliases_and_historical_kinds_absent_from_completion ... ok
test artifact_ref::kinds::tests::catalog_offers_public_job_alias_for_completion ... ok
test artifact_ref::kinds::tests::commit_canonicalizes_to_stitch_without_a_diagnostic ... ok
test artifact_file::vcs::tests::reports_missing_for_unknown_content_or_a_zero_history_bound ... ok
test artifact_ref::file_roots::tests::symlink_escape_fifo_and_unreadable_files_are_denied ... ok
test artifact_ref::kinds::tests::job_canonicalizes_to_stored_chop_without_a_diagnostic ... ok
test artifact_ref::kinds::tests::default_parse_is_byte_identical_for_every_historical_kind ... ok
test artifact_ref::kinds::tests::plans_canonicalizes_to_plan_with_a_diagnostic ... ok
test artifact_ref::kinds::tests::tool_kind_is_reserved_and_absent_from_completion ... ok
test artifact_ref::kinds::tests::unregistered_labels_canonicalize_to_themselves ... ok
test artifact_ref::list::tests::malformed_entry_does_not_abort_valid_neighbors ... ok
test artifact_ref::list::tests::batch_resolve_loads_the_artifact_index_once ... ok
test artifact_link::index::tests::rows_and_project_do_not_scan_unrelated_rows ... ok
test artifact_ref::list::tests::normalize_deduplicates_in_first_occurrence_order ... ok
test artifact_ref::list::tests::parse_rejects_malformed_sigiled_and_empty_entries_with_position ... ok
test artifact_ref::list::tests::parse_and_normalize_every_kind_and_fragment ... ok
test artifact_ref::location::tests::github_line_fragment_parser_covers_new_forms ... ok
test artifact_ref::provider_spec::tests::accepts_two_cell_emoji_icon ... ok
test artifact_ref::provider_spec::tests::rejects_bad_expansion_format ... ok
test artifact_ref::provider_spec::tests::rejects_bad_inventory_globs_and_publication_values ... ok
test artifact_ref::provider_spec::tests::rejects_missing_or_malformed_icon ... ok
test artifact_ref::provider_spec::tests::digest_changes_when_icon_changes ... ok
test artifact_ref::provider_spec::tests::rejects_property_type_enum_and_source_issues ... ok
test artifact_ref::provider_spec::tests::rejects_undeclared_detail_and_identity_properties ... ok
test artifact_ref::provider_spec::tests::rejects_unsupported_schema_version ... ok
test artifact_ref::provider_spec::tests::rejects_reserved_kind_and_bad_identifiers ... ok
test artifact_ref::ref_files::tests::fold_deduplicates_versions_and_unions_provenance ... ok
test artifact_ref::provider_spec::tests::valid_spec_passes_and_digest_is_stable ... ok
test artifact_ref::ref_files::tests::row_round_trips_and_parse_skips_bad_and_future_lines ... ok
test artifact_ref::ref_files::tests::validation_rejects_bad_identity_fields ... ok
test artifact_ref::location::tests::forms_that_are_not_a_location_stay_whole ... ok
test artifact_ref::location::tests::inverted_or_equal_end_line_is_dropped ... ok
test artifact_ref::location::tests::supported_forms_split_off_the_location ... ok
test artifact_ref::location::tests::omitted_optional_fields_are_skipped_in_json ... ok
test artifact_ref::repository_resolution::tests::absent_checkout_is_a_retryable_missing_checkout ... ok
test artifact_file::vcs::tests::materializes_direct_blob_then_uses_verified_cache ... ok
test artifact_ref::repository_resolution::tests::caller_attached_checkout_candidate_wins_without_repository_inventory ... ok
test artifact_ref::repository_resolution::tests::correlated_producer_workspace_resolves_without_inventory ... ok
test artifact_ref::repository_resolution::tests::deleted_producer_workspace_falls_back_to_a_live_alternate_checkout ... ok
test artifact_ref::repository_resolution::tests::no_repositories_configured_is_missing_checkout_not_a_guess ... ok
test artifact_ref::repository_resolution::tests::directory_targets_use_the_same_decision_path ... ok
test artifact_ref::repository_resolution::tests::explicitly_relative_literal_tilde_paths_still_resolve ... ok
test artifact_ref::repository_resolution::tests::drifted_path_resolves_through_bounded_suffix_search ... ok
test agent_archive::corpus::tests::query::query_filters_outcome_restorable_project_model_date_and_link_facets ... ok
test artifact_ref::repository_resolution::tests::home_payload_is_rejected_before_repository_probing ... ok
test artifact_ref::repository_resolution::tests::owner_project_mismatch_does_not_use_viewer_inventory ... ok
test artifact_ref::repository_resolution::tests::proven_missing_when_every_known_checkout_was_searched ... ok
test artifact_ref::repository_resolution::tests::out_of_inventory_source_directory_is_not_relabeled_as_owner_repo ... ok
test artifact_ref::repository_resolution::tests::owner_repository_mismatch_does_not_use_foreign_source_directory ... ok
test artifact_ref::repository_resolution::tests::explicit_owner_repository_scopes_the_search_and_skips_others ... ok
test artifact_ref::repository_resolution::tests::owner_path_globs_deny_before_any_checkout_probe ... ok
test artifact_ref::repository_resolution::tests::distinct_attached_repositories_are_ambiguous_not_first_hit ... ok
test agent_archive::corpus::tests::query::query_lookup_resolves_short_canonical_global_and_workflow_child_names ... ok
test agent_archive::corpus::tests::query::query_windows_page_flattened_rows_and_insert_expanded_members ... ok
test artifact_ref::repository_resolution::tests::same_named_directories_in_distinct_repos_are_ambiguous ... ok
test artifact_ref::repository_resolution::tests::resolves_a_source_path_in_its_owning_linked_repository ... ok
test agent_archive::corpus::tests::query::query_summaries_omit_empty_groups_and_use_compile_timezone_days ... ok
test artifact_ref::repository_resolution::tests::traversal_payload_is_rejected_before_any_search ... ok
test agent_scan::index::tests::storage::hidden_terminal_retention_prunes_dependents_and_is_idempotent ... ok
test artifact_ref::repository_resolution::tests::source_directory_resolves_a_one_component_path_beside_the_document ... ok
test artifact_ref::scanner::tests::angle_bracket_is_an_allowed_left_context ... ok
test artifact_ref::repository_resolution::tests::stale_attached_checkout_falls_through_to_live_same_repo_inventory ... ok
test artifact_ref::repository_resolution::tests::stale_source_directory_falls_through_to_live_same_repo_inventory ... ok
test artifact_ref::repository_resolution::tests::source_directory_nested_inside_valid_checkout_with_project_agreement ... ok
test agent_scan::index::tests::windowed_query::windowed_query_applies_safe_candidate_filter ... ok
test artifact_ref::repository_resolution::tests::unavailable_project_context_does_not_use_inventory ... ok
test agent_archive::corpus::tests::query::query_unknown_field_enum_value_and_group_by_are_typed_errors ... ok
test artifact_ref::scanner::tests::fragment_splits_after_the_closing_quote ... ok
test artifact_ref::scanner::tests::quoted_argument_supports_escaped_quote_and_backslash ... ok
test artifact_ref::scanner::tests::quote_artifact_ref_argument_round_trips_through_the_scanner ... ok
test artifact_ref::scanner::tests::quoted_argument_with_spaces_parses_and_round_trips ... ok
test artifact_ref::scanner::tests::quoted_trailing_punctuation_is_not_trimmed ... ok
test artifact_ref::scanner::tests::unterminated_quote_at_true_eof_ends_at_end_of_text ... ok
test artifact_ref::repository_resolution::tests::suffix_budget_exhaustion_is_a_temporary_error ... ok
test artifact_ref::scanner::tests::unterminated_quote_ends_at_the_current_line_never_at_eof ... ok
test artifact_ref::repository_resolution::tests::two_ambiguous_linked_repos_report_both_candidates ... ok
test artifact_ref::scanner::tests::xprompt_argument_delimiters_are_allowed_left_context ... ok
test artifact_ref::tests::attachment_payload_requires_exactly_one_slash ... ok
test artifact_ref::tests::canonicalization_recognizes_only_canonical_entity_pages ... ok
test artifact_ref::tests::attachment_resolves_through_the_bead_store_not_the_filesystem ... ok
test artifact_ref::tests::commit_resolution_still_considers_sidecar_repositories ... ok
test artifact_ref::tests::agent_resolution_globalizes_and_preserves_historical_names ... ok
test artifact_ref::tests::context_schema_version_is_required_for_context_operations ... ok
test artifact_ref::tests::every_kind_and_fragment_round_trips ... ok
test artifact_ref::tests::canonicalization_uses_order_and_artifact_index ... ok
test artifact_ref::tests::file_path_payloads_accept_fragments_and_stitch_shorthand_bounds ... ok
test artifact_ref::tests::bead_resolution_covers_pages_projects_and_ambiguity ... ok
test artifact_ref::tests::goal_kind_is_reserved_live_and_offered_in_completion ... ok
test agent_scan::index::tests::storage::vacuum_reclaims_freelist_pages_and_preserves_rows ... ok
test artifact_ref::tests::document_path_globs_filter_resolution_and_canonicalization ... ok
test agent_scan::index::tests::terminalization::terminalize_stale_active_rows_hides_abandoned_record ... ok
test artifact_ref::tests::filtered_root_cannot_be_bypassed_by_later_duplicate_roots ... ok
test artifact_ref::tests::filtered_drift_candidates_are_not_reported ... ok
test artifact_ref::tests::goal_kind_resolves_through_the_provider_registry ... ok
test artifact_ref::tests::indexed_vcs_backed_file_resolution_is_pure_and_reports_provenance ... ok
test artifact_ref::tests::indexed_file_resolution_accepts_supported_envelope_range ... ok
test artifact_ref::tests::namespace_resolution_is_canonical_and_local ... ok
test artifact_ref::tests::parsed_references_carry_the_current_wire_schema ... ok
test artifact_file::vcs::tests::replaces_wrong_cache_content_after_verifying_git_blob ... ok
test artifact_ref::tests::parse_rejects_invalid_shapes_and_illegal_fragments ... ok
test artifact_ref::tests::scanner_enforces_left_context_but_scans_fences ... ok
test artifact_ref::tests::validate_artifact_ref_context_accepts_the_supported_range ... ok
test artifact_ref::tests::scanner_reports_utf8_byte_spans_and_malformed_candidates ... ok
test artifact_ref::uses::tests::manifest_parse_tolerates_unknown_fields ... ok
test artifact_ref::uses::tests::rejects_empty_required_fields_and_bad_kind ... ok
test artifact_ref::uses::tests::valid_record_passes ... ok
test autonomy::tests::ask_value_reports_its_policy_key ... ok
test artifact_ref::uses::tests::manifest_round_trip_skips_bad_and_future_lines ... ok
test artifact_ref::tests::path_resolution_covers_order_drift_ambiguity_and_missing ... ok
test autonomy::tests::decision_echoes_record_identity ... ok
test autonomy::tests::approve_archive_carries_both_option_ids_in_canonical_order ... ok
test autonomy::tests::compat_rows_give_contract_outcomes ... ok
test autonomy::tests::decision_log_round_trips_filters_and_rotates ... ok
test agent_archive::store::tests::store_opens_python_created_index_without_schema_drop ... ok
test autonomy::tests::decision_sentences_render_both_examples ... ok
test autonomy::tests::digest_golden_is_stable ... ok
test autonomy::tests::explicit_profile_and_overrides_keep_their_policy ... ok
test autonomy::tests::inherit_keeps_narrows_or_refuses ... ok
test autonomy::tests::legacy_round_trip_is_stable ... ok
test autonomy::tests::missing_required_option_asks_without_partial_selection ... ok
test autonomy::tests::legacy_translation_matches_resolve_for_canonical_shapes ... ok
test autonomy::tests::fleet_auto_approved_routes_through_evaluate ... ok
test autonomy::tests::option_order_does_not_change_the_decision ... ok
test autonomy::tests::legacy_translation_covers_every_writer_shape ... ok
test autonomy::tests::mutate_covers_every_status ... ok
test autonomy::tests::projection_reproduces_writer_output ... ok
test autonomy::tests::resolve_rejects_bad_source_and_actor ... ok
test autonomy::tests::privileged_and_unknown_kinds_always_ask ... ok
test autonomy::tests::record_wire_round_trips ... ok
test autonomy::tests::resolve_rejects_unknown_spellings_with_invalid_auto ... ok
test autonomy::tests::resolve_covers_every_spelling ... ok
test autonomy::tests::stale_builtin_inheritance_and_mutation_use_effective_policy ... ok
test autonomy::tests::unmentioned_value_asks ... ok
test autonomy::tests::stale_builtin_refresh_preserves_identity_and_plan_outcomes ... ok
test axe_chop::diagnostics::tests::reports_absent_and_unavailable_output ... ok
test autonomy::tests::value_outside_capabilities_asks_without_partial_selection ... ok
test axe_chop::tests::agent_clan_guard_short_circuits_trigger_errors ... ok
test axe_chop::tests::agent_clan_guard_matches_only_explicit_active_case_sensitive_clans ... ok
test axe_chop::tests::axe_descriptions_split_into_normalized_summary_and_body ... ok
test autonomy::tests::summary_covers_every_profile ... ok
test axe_chop::tests::agent_runners_guard_counts_only_active_runner_slot_holders ... ok
test axe_chop::tests::checkpoint_success_policy_commits_only_after_success ... ok
test axe_chop::tests::chop_report_rejects_control_characters_and_overlong_text ... ok
test axe_chop::tests::chop_report_rejects_unknown_block_kinds_and_tones ... ok
test axe_chop::tests::chop_result_without_report_remains_valid_and_serializes_null ... ok
test axe_chop::tests::chop_report_rejects_ragged_rows_disallowed_glyphs_and_invalid_gauges ... ok
test axe_chop::tests::chop_report_round_trips_every_block_kind ... ok
test axe_chop::tests::chop_report_rejects_excess_blocks_and_rows ... ok
test axe_chop::tests::compound_durations_are_strict_and_positive ... ok
test axe_chop::tests::derived_agent_names_include_sanitized_bounded_run_token ... ok
test axe_chop::tests::derived_agent_names_include_target_and_order ... ok
test axe_chop::tests::derived_agent_names_keep_length_and_trailing_separator_guards ... ok
test axe_chop::tests::derived_agent_names_reject_empty_sanitized_run_token ... ok
test axe_chop::tests::earlier_guard_wins_over_agent_runners ... ok
test axe_chop::tests::fs_trigger_fails_open_on_token_computation_error_without_persisting ... ok
test axe_chop::tests::fs_trigger_fails_open_when_no_observation_is_provided ... ok
test axe_chop::tests::fs_trigger_fires_after_max_quiet_elapses_with_unchanged_token ... ok
test axe_chop::tests::fs_trigger_fires_on_missing_checkpoint_and_persists_baseline_token ... ok
test axe_chop::tests::fs_trigger_fires_when_token_changes ... ok
test agent_scan::index::tests::windowed_query::windowed_query_preserves_active_rows_and_selects_completed_budget ... ok
test axe_chop::tests::chop_report_rejects_oversize_documents ... ok
test axe_chop::tests::fs_trigger_rejects_empty_paths ... ok
test axe_chop::tests::fs_trigger_skips_when_token_unchanged_and_within_max_quiet ... ok
test axe_chop::tests::git_trigger_returns_checkpoint_observation ... ok
test axe_chop::tests::guards_short_circuit_triggers ... ok
test axe_chop::tests::legacy_changespec_guard_provider_deserializes_as_patch ... ok
test axe_chop::tests::once_per_release_removes_exact_keys_and_is_idempotent ... ok
test axe_chop::tests::once_per_release_validates_engine_and_document_schemas ... ok
test axe_chop::tests::once_per_store_rejects_duplicates_and_evicts_oldest ... ok
test axe_chop::tests::strict_axe_validation_accepts_fs_trigger_with_bare_and_glob_paths ... ok
test axe_chop::tests::strict_axe_validation_accepts_keyed_and_tagged_agent_clan_guards ... ok
test axe_chop::tests::strict_axe_validation_accepts_keyed_and_tagged_agent_runners_guards ... ok
test axe_chop::tests::clan_scoped_proposals_round_trip_without_changing_legacy_proposals ... ok
test axe_chop::tests::strict_axe_validation_accepts_missing_descriptions_by_default ... ok
test axe_chop::tests::strict_axe_validation_accepts_nonnegative_or_missing_wait_runners ... ok
test axe_chop::tests::strict_axe_validation_accepts_new_shape ... ok
test axe_chop::tests::strict_axe_validation_counts_description_limits_in_characters ... ok
test axe_chop::tests::strict_axe_validation_emits_only_the_first_description_shape_error ... ok
test axe_chop::tests::strict_axe_validation_rejects_blank_descriptions ... ok
test axe_chop::tests::strict_axe_validation_gates_description_shape_and_accepts_single_lines ... ok
test axe_chop::tests::strict_axe_validation_rejects_blank_fs_paths_and_invalid_watch_spec ... ok
test axe_chop::tests::strict_axe_validation_rejects_fs_trigger_missing_required_fields ... ok
test axe_chop::tests::strict_axe_validation_rejects_invalid_agent_clan_guards_fail_closed ... ok
test axe_chop::tests::strict_axe_validation_rejects_invalid_agent_runners_guards_fail_closed ... ok
test axe_chop::tests::strict_axe_validation_rejects_invalid_wait_runners ... ok
test axe_chop::tests::strict_axe_validation_rejects_non_positive_log_temp_max_age ... ok
test axe_chop::tests::strict_axe_validation_reports_canonical_routine_job_templates ... ok
test axe_chop::tests::strict_axe_validation_reports_migrations_duplicates_and_provenance ... ok
test axe_chop::tests::strict_axe_validation_reports_each_description_shape_error_precisely ... ok
test axe_chop::tests::result_validation_rejects_forward_wait_and_unknown_fields ... ok
test axe_chop::tests::strict_axe_validation_requires_lumberjack_and_chop_descriptions_when_enabled ... ok
test axe_chop::tests::target_expansion_filters_projects_and_separates_overrides ... ok
test axe_chop::tests::target_expansion_uses_stable_hash_without_identity_field ... ok
test axe_overrun::tests::action_succeeded_with_script_duration_is_sampled_on_that_value ... ok
test axe_overrun::tests::action_succeeded_without_script_duration_is_ignored ... ok
test axe_overrun::tests::empty_history_is_none_with_null_ratios ... ok
test axe_overrun::tests::exact_equality_counts_as_over ... ok
test axe_overrun::tests::fast_skipped_newest_run_in_front_of_over_success_is_still_over ... ok
test axe_overrun::tests::live_running_run_past_interval_is_over_from_elapsed_time ... ok
test axe_overrun::tests::negative_duration_is_dropped_not_fatal ... ok
test axe_overrun::tests::newest_sampled_run_over_is_over ... ok
test axe_overrun::tests::non_positive_interval_is_an_error ... ok
test axe_overrun::tests::older_overrun_is_locatable_by_run_idx_after_a_healthy_newest_run ... ok
test axe_overrun::tests::only_an_older_run_over_is_intermittent ... ok
test axe_overrun::tests::only_ten_percent_ratio_is_not_over_and_not_intermittent ... ok
test axe_overrun::tests::serde_rejects_unknown_fields_and_invalid_enum_values ... ok
test axe_overrun::tests::structural_validation_returns_path_specific_errors ... ok
test axe_overrun::tests::serialization_pins_public_field_order_and_round_trips ... ok
test axe_overrun::tests::unknown_status_string_is_dropped_not_fatal ... ok
test axe_overrun::tests::unparsable_started_at_is_dropped_for_every_otherwise_sampleable_status ... ok
test axe_overrun::tests::unparsable_started_at_is_dropped_not_fatal ... ok
test axe_status::tests::collection_error_is_a_normal_error_snapshot_with_exit_two ... ok
test axe_status::tests::desired_stopped_with_live_orchestrator_is_degraded ... ok
test axe_status::tests::historical_error_count_does_not_degrade_a_fresh_worker ... ok
test axe_status::tests::lifecycle_matrix_preserves_intent_separately_from_health ... ok
test axe_status::tests::live_lumberjack_without_coherent_orchestrator_is_degraded ... ok
test axe_status::tests::live_orphan_is_retained_and_dead_unconfigured_row_is_filtered ... ok
test axe_status::tests::lumberjack_state_precedence_and_heartbeat_boundaries_are_pinned ... ok
test axe_status::tests::normalization_is_independent_of_input_order_and_duplicates ... ok
test axe_status::tests::orchestrator_conflicting_live_identities_are_sorted_and_exact ... ok
test axe_status::tests::orchestrator_live_pid_without_lock_has_exact_evidence ... ok
test axe_status::tests::orchestrator_lock_without_live_pid_has_exact_evidence ... ok
test axe_status::tests::public_projection_preserves_collection_error_user_text ... ok
test axe_status::tests::serde_rejects_unknown_fields_and_invalid_enum_values ... ok
test axe_status::tests::public_projection_renames_only_owned_status_envelope_and_templates ... ok
test axe_status::tests::serialization_pins_public_field_order_nulls_lists_and_enum_values ... ok
test axe_status::tests::structural_validation_returns_path_specific_errors ... ok
test axe_chop::diagnostics::tests::byte_bound_keeps_utf8_boundary_and_marks_truncation ... ok
test axe_chop::tests::result_validation_accepts_proposals_and_rejects_workflows ... ok
test axe_chop::diagnostics::tests::normalizes_redacts_and_tails_subprocess_output ... ok
test bead::artifact_refs::tests::projection_text_scan_ignores_non_ids ... ok
test bead::artifact_refs::tests::projection_text_scan_matches_protection_coverage ... ok
test agent_scan::index::tests::visibility::hidden_inclusive_full_history_can_inspect_dismissed_rows ... ok
test agent_scan::index::tests::windowed_query::full_history_query_applies_candidate_filter_before_decoding ... ok
test bead::artifact_refs::tests::legacy_store_reports_bead_referenced_ids ... ok
test bead::artifact_refs::tests::missing_store_is_an_error ... ok
test bead::board::tests::board_snapshot_matches_separate_queries ... ok
test bead::artifact_refs::tests::store_without_references_reports_empty ... ok
test axe_chop::tests::clan_summaries_agree_per_raw_clan_before_launch ... ok
test artifact_ref::scanner::tests::document_scan_links_github_column_fragments_on_typed_refs ... ok
test artifact_ref::scanner::tests::goal_refs_scan_while_yaml_goal_labels_stay_dropped ... ok
test axe_chop::tests::clan_summary_validation_is_field_specific_and_text_block_safe ... ok
test axe_chop::tests::clan_scoped_proposals_validate_member_and_directive_shapes ... ok
test bead::cli::tests::create_command::create_missing_parent_has_no_pre_read ... ok
test artifact_ref::repository_resolution::tests::matching_revision_is_required_before_a_worktree_path_is_exact ... ok
test agent_stats::run::tests::runner_occupancy::runner_monitor_handoff_is_query_window_invariant ... ok
test bead::cli::tests::create_command::design_plan_roots_resolves_the_beads_sidecar_to_its_plans_sibling ... ok
test bead::cli::tests::create_command::design_storage_root_resolves_the_beads_sidecar_to_the_workspace ... ok
test artifact_ref::scanner::tests::document_scan_separates_visible_prompt_ref_from_canonical_target ... ok
test bead::cli::tests::create_command::search_design_matches_canonical_plan_reference ... ok
test bead::cli::tests::design_refs::show_keeps_one_line_when_a_legacy_path_resolves_to_itself ... ok
test artifact_ref::scanner::tests::document_scan_handles_unsigiled_refs_for_known_kinds ... ok
test bead::cli::tests::design_refs::show_marks_a_reference_resolved_through_month_drift ... ok
test bead::cli::tests::design_refs::show_reports_a_malformed_reference ... ok
test bead::cli::tests::design_refs::show_renders_reference_above_its_resolved_path ... ok
test bead::cli::tests::design_refs::show_resolves_a_legacy_path_against_the_working_directory ... ok
test bead::cli::tests::design_refs::show_says_plainly_when_a_reference_resolves_nowhere ... ok
test bead::cli::tests::design_refs::show_reports_an_ambiguous_reference_instead_of_guessing ... ok
test artifact_file::vcs::tests::searches_bounded_remote_history_when_recorded_sha_is_gone ... ok
test artifact_ref::scanner::tests::document_scan_recognizes_explicit_xprompt_skill_references ... ok
test bead::cli::tests::mutate_commands::mutating_handlers_report_resolution_errors_without_a_pre_read ... ok
test artifact_ref::scanner::tests::document_scan_uses_markdown_destination_for_skill_links ... ok
test agent_scan::index::tests::terminalization::terminalize_repairs_visible_abandoned_rows ... ok
test bead::cli::tests::mutate_commands::remove_missing_later_id_is_an_atomic_fast_path_error ... ok
test bead::cli::tests::parsing::close_note_author_ignores_the_bare_launcher_flag ... ok
test bead::cli::tests::parsing::close_parser_accepts_force_with_reason_and_resolution ... ok
test bead::cli::tests::parsing::create_rejects_bare_task_constructor_without_size ... ok
test bead::cli::tests::parsing::parse_create_type_rejects_retired_flag_form ... ok
test bead::cli::tests::parsing::search_regex_flag_is_fast_path_only_as_bare_flag ... ok
test bead::cli::tests::parsing::search_regex_invalid_pattern_is_usage_error_across_formats ... ok
test bead::cli::tests::parsing::update_fast_path_defers_size_flag_to_python ... ok
test agent_scan::index::tests::windowed_query::windowed_query_selects_completed_budget_when_active_exceeds_limit ... ok
test bead::cli::tests::read_commands::claimed_status_is_in_default_list_with_claim_details_and_color ... ok
test bead::cli::tests::read_commands::ready_empty_state_explains_epic_preassignment ... ok
test bead::cli::tests::read_commands::search_applies_filters_and_limit ... ok
test bead::cli::tests::read_commands::ready_lists_only_unblocked_ready_tasks_with_ready_glyph ... ok
test bead::cli::tests::read_commands::search_compact_orders_matches_newest_first ... ok
test bead::cli::tests::read_commands::search_full_reuses_show_rendering_for_single_result ... ok
test bead::cli::tests::read_commands::search_no_match_is_successful ... ok
test bead::cli::tests::read_commands::search_whitespace_query_is_usage_error ... ok
test bead::cli::tests::rendering::colored_type_cell_keeps_alignment_padding_outside_ansi_span ... ok
test bead::cli::tests::read_commands::stats_prints_ready_and_task_rows ... ok
test bead::cli::tests::rendering::list_compact_colors_shared_type_status_and_id_vocabulary ... ok
test bead::cli::tests::rendering::search_compact_color_always_highlights_matches ... ok
test bead::cli::tests::rendering::list_compact_renders_aligned_glyph_only_type_column ... ok
test bead::cli::tests::rendering::search_compact_renders_name_and_description ... ok
test bead::cli::tests::rendering::search_compact_renders_aligned_glyph_only_type_column ... ok
test bead::cli::tests::rendering::search_json_renders_stable_uncolored_envelope ... ok
test artifact_ref::repository_resolution::tests::mismatching_revision_is_unavailable_even_when_the_path_exists ... ok
test bead::cli::tests::rendering::search_regex_zero_width_only_pattern_matches_without_empty_highlights ... ok
test bead::config::tests::load_current_shape ... ok
test bead::config::tests::missing_file_returns_supplied_default ... ok
test bead::config::tests::save_matches_python_pretty_json_shape ... ok
test bead::events::tests::attachments::event_schema_version_stays_one ... ok
test artifact_ref::scanner::tests::document_scan_uses_markdown_destination_for_ordinary_links ... ok
test bead::events::tests::attachments::note_payload_validation_accepts_repeated_token ... ok
test bead::events::tests::attachments::note_payload_validation_rejects_mismatches ... ok
test bead::events::tests::attachments::note_payloads_ignore_unknown_future_fields ... ok
test bead::events::tests::attachments::note_payloads_round_trip_with_attachments ... ok
test bead::events::tests::attachments::note_payloads_without_attachments_stay_byte_identical ... ok
test bead::events::tests::attachments::reducer_sets_replaces_and_keeps_manifests ... ok
test bead::events::tests::import::inbound_link_provenance_projects_bead_as_target ... ok
test bead::events::tests::import::link_added_provenance_tracks_rewrite_removal_and_readd ... ok
test bead::events::tests::import::refs_import_as_individual_events_and_replay_idempotently ... ok
test bead::events::tests::import::links_import_round_trip_and_ignore_unknown_historical_payloads ... ok
test bead::events::tests::merge::concurrently_minted_bead_id_relocates_instead_of_wedging_the_store ... ok
test bead::cli::tests::rendering::search_regex_matches_patterns_and_highlights_ranges ... ok
test bead::events::tests::merge::concurrently_minted_child_id_renumbers_to_a_free_sibling ... ok
test artifact_ref::scanner::tests::document_scan_keeps_generated_links_table_ref_and_hosted_url ... ok
test bead::events::tests::merge::conflicting_shared_order_prefers_upstream ... ok
test bead::events::tests::merge::merging_without_a_relocation_id_still_reports_the_duplicate ... ok
test bead::events::tests::merge::non_monotonic_upstream_plus_local_note_keeps_upstream_order ... ok
test bead::events::tests::merge::reordered_validation_still_rejects_missing_rewritten_duplicated ... ok
test bead::events::tests::merge::pure_reorder_branch_canonicalizes_to_base_order ... ok
test bead::events::tests::merge::three_way_merge_preserves_independent_plus_ones_and_deduplicates_reporter ... ok
test bead::events::tests::reduction::legacy_note_parser_accepts_crlf_input ... ok
test bead::events::tests::merge::relocated_events_are_reminted_onto_their_new_stream ... ok
test bead::events::tests::merge::upstream_creation_keeps_the_id_when_local_is_newer ... ok
test bead::events::tests::reduction::legacy_note_parser_attributes_bare_prose_to_update_event ... ok
test bead::events::tests::merge::upstream_creation_keeps_the_id_when_local_is_older ... ok
test bead::events::tests::reduction::legacy_note_parser_does_not_promote_marker_looking_line_mid_paragraph ... ok
test bead::events::tests::reduction::legacy_note_parser_does_not_promote_unparseable_timestamp_marker ... ok
test bead::events::tests::reduction::legacy_note_parser_ignores_empty_and_whitespace_only_blobs ... ok
test bead::events::tests::reduction::legacy_note_parser_keeps_prose_before_first_marker_as_one_record ... ok
test bead::events::tests::reduction::legacy_note_parser_recovers_pure_appended_blob ... ok
test bead::events::tests::reduction::note_append_validation_and_rendering_are_owned_by_the_event ... ok
test bead::events::tests::reduction::note_edited_rewrites_text_and_stamps_editor ... ok
test bead::cli::tests::rendering::search_regex_json_marks_regex_mode ... ok
test bead::events::tests::reduction::note_removed_retracts_the_record ... ok
test bead::events::tests::reduction::reduction_accepts_invalid_intermediate_state_repaired_by_later_event ... ok
test bead::events::tests::reduction::reduction_collapse_prefers_earlier_created_at_over_id_order ... ok
test bead::events::tests::reduction::reduction_collapse_does_not_disturb_unrelated_issues ... ok
test bead::events::tests::reduction::reduction_still_rejects_invalid_final_state_with_validation_error ... ok
test bead::events::tests::reduction::redundant_close_is_an_exact_no_op ... ok
test bead::events::tests::wire::issue_closed_rejects_a_blank_closed_by ... ok
test bead::events::tests::reduction::reduction_collapses_duplicate_external_refs_regardless_of_stream_order ... ok
test bead::events::tests::wire::issue_closed_without_closed_by_round_trips_byte_identically ... ok
test bead::events::tests::wire::issue_update_event_fields_resolution_round_trips_all_three_encodings ... ok
test bead::fingerprint::tests::event_store_token_is_stable_without_changes ... ok
test bead::events::tests::wire::issue_update_event_fields_round_trip_every_field ... ok
test bead::fingerprint::tests::event_store_token_moves_on_new_stream ... ok
test bead::fingerprint::tests::missing_store_is_an_error ... ok
test bead::history::tests::external_ref_set_and_clear_are_recorded_in_history ... ok
test bead::history::tests::close_reopen_close_status_timeline_is_complete ... ok
test bead::history::tests::lost_notes_ignores_append_only_revision_chains ... ok
test bead::fingerprint::tests::event_store_token_ignores_the_issues_projection ... ok
test bead::history::tests::lost_notes_are_stable_by_issue_id_and_support_one_issue ... ok
test artifact_ref::scanner::tests::document_scan_keeps_urls_whole_without_inner_file_links ... ok
test bead::history::tests::lost_notes_reports_overwritten_nonempty_revisions ... ok
test bead::history::tests::merged_order_keeps_appended_predated_event_after_earlier_stream_event ... ok
test bead::history::tests::phase_history_is_read_from_parent_stream ... ok
test bead::history::tests::notes_history_preserves_each_revision_pair ... ok
test bead::history::tests::removal_ends_the_timeline ... ok
test bead::history::tests::unknown_issue_is_an_error ... ok
test bead::jsonl::tests::atomic_temp_paths_are_unique_per_process ... ok
test bead::history::tests::single_update_and_noop_report_only_real_changes ... ok
test bead::jsonl::tests::corrupt_lines_are_skipped ... ok
test bead::jsonl::tests::export_sorts_by_id_and_uses_compact_json ... ok
test bead::jsonl::tests::import_defaults_missing_model_to_empty ... ok
test bead::jsonl::tests::import_defaults_missing_plan_tiers_from_phase_children ... ok
test bead::jsonl::tests::import_preserves_model ... ok
test bead::jsonl::tests::import_rejects_model_control_characters ... ok
test bead::jsonl::tests::import_rejects_duplicate_external_refs ... ok
test bead::jsonl::tests::prune_rejects_live_flag_streams ... ok
test bead::fingerprint::tests::event_store_token_moves_on_stream_append ... ok
test bead::jsonl::tests::refs_round_trip_and_empty_refs_do_not_change_jsonl_shape ... ok
test bead::fingerprint::tests::legacy_store_token_covers_issues_jsonl ... ok
test bead::jsonl::tests::unknown_event_operation_names_the_upgrade_remedy ... ok
test artifact_file::trash::tests::byte_backed_store_list_restore_and_purge_round_trip ... ok
test agent_archive::corpus::tests::query::query_order_is_newest_activity_first_and_stable_on_ties ... ok
test agent_scan::index::tests::windowed_query::windowed_query_decodes_only_selected_candidates ... ok
test bead::mutation::publish::tests::corrections_replace_only_matching_rows ... ok
test agent_stats::run::tests::query::committing_agents_counts_distinct_names_not_runs ... ok
test artifact_ref::scanner::tests::document_scan_keeps_line_location_suffixes_inside_file_path_spans ... ok
test agent_stats::run::tests::macros::aggregates_ranked_xprompt_usage_and_focused_breakdowns ... ok
test agent_scan::index::tests::windowed_query::rebuild_indexes_scanner_equivalent_records ... ok
test artifact_file::vcs::tests::tries_later_checkouts_when_the_first_lacks_the_object ... ok
test agent_stats::run::tests::runner_occupancy::runner_inherited_monitor_id_and_artifact_stamp_do_not_move_start_back ... ok
test bead::mutation::tests::claims::bead_mutation_lock_contention_times_out ... ok
test agent_stats::run::tests::runner_occupancy::runner_recovers_synthesized_hidden_lanes_without_trusting_the_stamp ... ok
test agent_stats::run::tests::runner_occupancy::user_hidden_skipped_counts_only_runner_eligible_rows ... ok
test agent_scan::selector::tests::multiple_selectors_preserve_order_and_dedup ... ok
test agent_scan::selector::tests::exact_key_wildcard_uses_newest_artifact_only ... ok
test agent_stats::run::tests::runner_occupancy::runner_occupancy_handles_overlap_carry_in_waits_and_boundaries ... ok
test agent_stats::run::tests::runner_queries::runner_query_requires_matching_live_workspace_claim ... ok
test agent_stats::run::tests::runner_occupancy::runner_occupancy_merges_serial_agent_session_and_counts_parallel ... ok
test bead::mutation::tests::claims::claim_for_agent_launch_rejects_missing_closed_and_blank_requests ... ok
test agent_stats::run::tests::runner_queries::runner_question_wait_uses_matching_gate_response_time ... ok
test agent_scan::selector::tests::hood_and_global_selectors_collapse_repeated_runs ... ok
test agent_stats::run::tests::runner_queries::runner_eligibility_honors_agent_session_workflow_visibility_and_project ... ok
test agent_stats::run::tests::work::missing_archive_spec_is_not_malformed ... ok
test agent_stats::run::tests::runner_queries::runner_query_filters_stale_and_never_started_records ... ok
test agent_stats::run::tests::runner_queries::runner_peak_can_exceed_ten_and_long_trend_stays_bounded ... ok
test agent_stats::run::tests::runner_queries::runner_fixed_and_all_time_empty_ranges_have_distinct_contracts ... ok
test agent_scan::index::tests::checkpoint::checkpoint_reports_busy_instead_of_failing ... ok
test agent_stats::run::tests::work::excluded_commit_repo_names_skip_project_and_patch_folds_only ... ok
test agent_scan::index::tests::visibility::dismissed_replace_diffs_instead_of_rewriting_the_table ... ok
test agent_scan::selector::tests::hidden_project_limit_and_ambiguity ... ok
test agent_scan::selector::tests::nested_paths_and_failures_are_precise ... ok
test agent_scan::selector::tests::unscoped_key_wildcard_and_unnamed_rows ... ok
test agent_scan::selector::tests::unscoped_and_exact_selectors_use_newest_artifact ... ok
test bead::mutation::tests::close::batch_close_preflights_every_request_before_writing ... ok
test agent_scan::index::tests::visibility::dismissal_reconcile_uses_dismissed_parent_suffix_when_root_row_deleted ... ok
test agent_stats::run::tests::work::attributes_project_and_patch_work_with_filters_and_statuses ... ok
test bead::jsonl::tests::atomic_if_changed_skips_identical_bytes ... ok
test bead::jsonl::tests::read_skips_removed_flag_stream_without_touching_the_store ... ok
test bead::jsonl::tests::read_rejects_live_flag_stream_with_todays_message ... ok
test agent_scan::index::tests::visibility::dismissal_reconcile_backfills_dead_agent_session_members_only ... ok
test bead::jsonl::tests::write_event_store_changed_rejects_a_changed_ancestor_event ... ok
test bead::mutation::tests::close::forced_close_requires_reason_and_non_done_resolution ... ok
test bead::jsonl::tests::write_event_store_changed_rejects_a_shortened_ancestor_stream ... ok
test bead::jsonl::tests::write_event_store_changed_appends_to_legacy_stream_without_rewriting_prefix_bytes ... ok
test agent_stats::run::tests::query::aggregates_window_outcomes_metadata_and_runtime ... ok
test bead::cli::tests::create_command::create_resolves_shorthand_parent_inside_the_locked_load ... ok
test bead::cli::tests::create_command::create_plan_under_sidecar_plans_root_stores_canonical_reference ... ok
test bead::cli::tests::create_command::create_plan_under_in_tree_plans_root_stores_canonical_reference ... ok
test bead::cli::tests::create_command::create_plan_path_is_relative_through_symlinked_workspace_root ... ok
test bead::cli::tests::create_command::create_plan_path_is_relative_to_store_workspace_from_nested_cwd ... ok
test bead::cli::tests::create_command::create_reason_passes_through_and_blank_is_rejected ... ok
test bead::mutation::tests::close::unforced_close_with_open_descendant_fails_without_writing ... ok
test bead::jsonl::tests::prune_removes_tombstoned_flag_streams_and_rewrites_the_manifest ... ok
test bead::cli::tests::mutate_commands::close_summary_preserves_requested_ids_and_real_prior_status ... ok
test bead::cli::tests::mutate_commands::close_fast_path_accepts_note_and_updates_once ... ok
test bead::mutation::tests::create::create_requires_size_only_for_new_tasks ... ok
test bead::mutation::tests::create::create_rejects_model_control_characters ... ok
test bead::mutation::tests::create::create_requires_task_type_only_for_new_tasks ... ok
test bead::cli::tests::create_command::create_and_remove_are_handled_with_mutation_summaries ... ok
test bead::mutation::tests::create::create_with_missing_parent_fails_without_writing ... ok
test bead::cli::tests::mutate_commands::dep_rm_reads_the_store_once ... ok
test bead::cli::tests::mutate_commands::update_fast_path_reports_changed_and_unchanged_rows_in_one_commit ... ok
test bead::cli::tests::mutate_commands::remove_handles_multiple_ids_with_unique_output_and_requested_summary ... ok
test bead::mutation::tests::create::init_store_writes_a_root_level_store_for_a_dot_dirname ... ok
test agent_stats::run::tests::runner_queries::runner_diagnostics_separate_malformed_rows_and_invalid_intervals ... ok
test bead::mutation::tests::create::task_type_create_rejects_cross_field_and_slug_errors ... ok
test bead::attachments::tests::roster_carries_visibility_and_source ... ok
test bead::attachments::tests::roster_reports_latest_note_per_name ... ok
test bead::cli::tests::create_command::create_show_and_ref_verbs_honor_the_reference_contract ... ok
test bead::attachments::tests::references_include_initial_issue_created_notes ... ok
test bead::cli::tests::mutate_commands::dependency_remove_is_handled_with_a_batch_mutation_summary ... ok
test bead::attachments::tests::references_cover_current_and_historical_rows ... ok
test bead::attachments::tests::roster_and_references_include_plus_one_evidence ... ok
test bead::jsonl::tests::write_event_store_changed_writes_selected_streams_and_reloads ... ok
test bead::mutation::tests::claims::closed_bead_launch_note_format_includes_and_drops_run_id ... ok
test bead::mutation::tests::delegation_remove::remove_issues_rejects_an_empty_request ... ok
test agent_scan::index::tests::visibility::stale_dismissed_suffixes_do_not_consume_active_limit ... ok
test bead::cli::tests::mutate_commands::mutating_handlers_read_the_store_once ... ok
test bead::mutation::tests::close::forced_close_stamps_the_actor_on_every_swept_descendant ... ok
test bead::mutation::tests::close::forced_close_plan_sweeps_open_children_before_parent ... ok
test bead::mutation::tests::create::create_top_level_uses_current_store_max_and_persists_counter ... ok
test bead::mutation::tests::create::create_rejects_blank_and_overlong_reasons_without_writing ... ok
test bead::mutation::tests::close::reopening_grandchild_reopens_closed_ancestors_and_clears_resolution ... ok
test bead::mutation::tests::create::mark_ready_rejects_phase_and_idempotent_plan ... ok
test bead::mutation::tests::create::create_rejects_duplicate_external_ref_without_writing ... ok
test bead::mutation::tests::delegation_remove::explicitly_closing_parent_and_child_emits_one_explicit_parent_event ... ok
test bead::mutation::tests::delegation_remove::forced_close_plan_sweeps_through_nested_child_epics ... ok
test bead::mutation::tests::delegation_remove::remove_issues_deduplicates_duplicate_requests_and_events ... ok
test bead::mutation::tests::close::close_records_explicit_resolution_and_reopen_update_clears_it ... ok
test bead::mutation::tests::delegation_remove::close_skips_already_closed_issues_without_new_events ... ok
test bead::mutation::tests::delegation_remove::open_sibling_delegated_work_keeps_parent_phase_open ... ok
test bead::mutation::tests::create::create_and_update_model ... ok
test bead::mutation::tests::delegation_remove::remove_issues_removes_independent_roots_in_argument_order ... ok
test bead::mutation::tests::create::phase_with_blank_parent_creator_falls_back_to_store_owner ... ok
test bead::mutation::tests::close::absent_resolution_does_not_conflict_with_recorded_canceled_close ... ok
test bead::mutation::tests::close::conflicting_reason_aborts_before_writing ... ok
test bead::mutation::tests::close::close_note_attachments_requires_a_note ... ok
test bead::mutation::tests::claims::agent_claim_mutations_reject_missing_and_blank_requests ... ok
test bead::mutation::tests::close::repeat_close_is_write_free_and_classified_as_already_closed ... ok
test bead::mutation::tests::close::close_stamps_the_actor_on_the_delegated_parent ... ok
test agent_scan::index::tests::storage::hidden_terminal_retention_bounds_rebuild_and_preserves_anchors ... ok
test bead::mutation::tests::close::close_with_note_records_attachments_on_the_close_note ... ok
test bead::mutation::tests::create::create_persists_creation_reason_through_projection_and_replay ... ok
test bead::mutation::tests::delegation_remove::closing_child_epic_closes_completed_parent_phase ... ok
test bead::mutation::tests::close::repeat_close_with_note_writes_only_the_note ... ok
test bead::mutation::tests::claims_deps::claims_deps_launch_claim_stays_warm ... ok
test bead::mutation::tests::claims::claim_for_agent_wait_claims_open_and_is_idempotent_for_same_agent ... ok
test bead::mutation::tests::delegation_remove::nested_delegation_closes_only_phase_parents ... ok
test bead::mutation::tests::delegation_remove::remove_plan_cascades_through_nested_child_epics ... ok
test bead::mutation::tests::cache_fault_fallback::invalidated_cache_declines_cached_reads_and_mutation_succeeds ... ok
test bead::mutation::tests::close::conflicting_resolution_aborts_mixed_batch_before_writing ... ok
test bead::mutation::tests::claims::claim_for_agent_launch_rejects_invalid_submitted_at_before_writing ... ok
test bead::mutation::tests::claims_deps::claims_deps_dependency_add_remove_stay_warm ... ok
test bead::mutation::tests::claims_deps::claims_deps_ready_marking_stays_warm ... ok
test bead::mutation::tests::claims_deps::claims_deps_preclaim_stays_warm ... ok
test bead::mutation::tests::claims_deps::claims_deps_references_add_remove_stay_warm ... ok
test bead::mutation::tests::claims_deps::claims_deps_wait_and_release_stay_warm ... ok
test bead::mutation::tests::claims::preclaim_epic_work_plan_validation_is_all_or_nothing ... ok
test bead::mutation::tests::delegation_remove::removing_child_epic_does_not_close_parent_phase ... ok
test bead::mutation::tests::claims::claim_for_agent_launch_refuses_close_after_submission_without_writes ... ok
test bead::mutation::tests::claims::release_agent_claim_declines_in_progress_and_closed_without_writes ... ok
test bead::mutation::tests::links::concurrent_launch_claims_preserve_sibling_events_and_projection ... ok
test bead::mutation::tests::claims::claim_for_agent_launch_attaches_when_close_and_submission_timestamps_match ... ok
test bead::mutation::tests::delegation_remove::remove_issues_missing_later_id_leaves_store_unchanged ... ok
test bead::mutation::tests::links::concurrent_update_and_claim_preserve_both_events_and_projection ... ok
test bead::mutation::tests::claims::preclaim_epic_work_plan_updates_once_and_returns_rollback ... ok
test bead::mutation::tests::create::task_create_and_ready_updates_round_trip_through_events ... ok
test bead::mutation::tests::claims::claim_for_agent_launch_attaches_to_bead_closed_before_submission ... ok
test bead::mutation::tests::close::every_reopen_cause_archives_the_close_reason_it_used_to_destroy ... ok
test bead::mutation::tests::claims::claim_for_agent_launch_appends_a_note_on_every_closed_attach ... ok
test bead::mutation::tests::claims::release_agent_claim_is_owner_guarded_and_round_trips_to_open ... ok
test bead::mutation::tests::close::plus_one_close_record_joins_its_evidence_entry_exactly ... ok
test bead::mutation::tests::create::external_ref_create_update_clear_and_batch_conflicts_are_atomic ... ok
test bead::mutation::tests::close::reopening_a_bead_that_was_never_closed_archives_nothing ... ok
test bead::mutation::tests::claims::claim_for_agent_launch_claims_open_and_reassigns_in_progress_issue ... ok
test bead::mutation::tests::claims::claim_for_agent_wait_declines_other_claims_and_terminal_states_without_writes ... ok
test bead::mutation::tests::close::close_stamps_the_supplied_actor_on_the_envelope_and_closed_by ... ok
test bead::mutation::tests::claims_deps::claims_deps_blocker_status_comes_from_point_lookups ... ok
test bead::mutation::tests::create::create_resolves_creator_from_phase_parent_then_store_owner ... ok
test bead::mutation::tests::close::repeated_close_episodes_append_oldest_first_with_their_causes ... ok
test bead::mutation::tests::cache_fault_fallback::cache_disappearance_falls_back_to_replay_mid_mutation ... ok
test bead::mutation::tests::dependencies::create_uses_explicit_creator_for_issue_and_reference_events ... ok
test bead::mutation::tests::dependencies::reference_mutations_reject_malformed_entries_without_writing ... ok
test bead::mutation::tests::delegation_remove::remove_issues_deduplicates_overlapping_roots_in_both_orders ... ok
test bead::mutation::tests::dual_mode::dual_mode_create_matches_replay_without_full_replay ... ok
test bead::mutation::tests::lifecycle_warm::lifecycle_close_single_stays_warm ... ok
test bead::mutation::tests::dependencies::create_add_and_remove_references_use_individual_events_and_noop_cleanly ... ok
test bead::mutation::tests::lifecycle_warm::lifecycle_close_guard_rejects_open_descendant_without_writing_warm ... ok
test bead::mutation::tests::links::task_type_round_trips_through_create_events_and_projection ... ok
test bead::mutation::tests::lifecycle_warm::lifecycle_repeat_close_writes_nothing_warm ... ok
test bead::mutation::tests::lifecycle_warm::lifecycle_forced_close_sweeps_descendants_warm ... ok
test bead::mutation::tests::lifecycle_warm::lifecycle_close_batch_with_note_stays_warm ... ok
test bead::mutation::tests::links::link_projection_batch_is_transactional_on_invalid_middle_request ... ok
test bead::mutation::tests::notes_update::update_fields_resolution_preserves_omitted_clear_and_set ... ok
test bead::mutation::tests::dual_mode::dual_mode_remove_cascade_matches_replay ... ok
test bead::mutation::tests::lifecycle_warm::lifecycle_open_stays_warm ... ok
test bead::mutation::tests::dual_mode::dual_mode_close_and_open_match_replay ... ok
test bead::mutation::tests::lifecycle_warm::lifecycle_delegated_parent_completion_stays_warm ... ok
test bead::mutation::tests::notes_update::update_issues_invalid_field_value_leaves_every_target_unmodified ... ok
test bead::mutation::tests::dual_mode::dual_mode_note_append_and_update_match_replay_without_full_replay ... ok
test bead::mutation::tests::dual_mode::dual_mode_links_match_replay ... ok
test bead::mutation::tests::dependencies::remove_dependencies_rejects_an_unknown_source_without_writing ... ok
test bead::mutation::tests::notes_update::update_issues_status_closed_rejects_out_of_batch_descendant ... ok
test bead::mutation::tests::notes_update::update_issues_unknown_id_leaves_store_untouched ... ok
test bead::mutation::tests::dependencies::remove_dependencies_validates_the_whole_batch_before_writing ... ok
test bead::mutation::tests::links::link_projection_batch_uses_canonical_aliases_and_undirected_holder ... ok
test bead::mutation::tests::lifecycle_warm::lifecycle_remove_cleans_survivor_dependencies_warm ... ok
test bead::mutation::tests::dual_mode::dual_mode_ready_marking_matches_replay ... ok
test bead::mutation::tests::notes_update::update_status_closed_rejects_open_descendants ... ok
test bead::mutation::tests::lifecycle_warm::lifecycle_remove_cascade_stays_warm ... ok
test bead::mutation::tests::links::mutations_create_canonical_events_and_regenerate_projection ... ok
test bead::mutation::tests::links::link_projection_batch_skip_applies_valid_requests_and_reports_absent_holder ... ok
test bead::mutation::tests::dependencies::remove_dependencies_batches_and_deduplicates_targets ... ok
test bead::mutation::tests::dual_mode::dual_mode_claims_match_replay ... ok
test bead::mutation::tests::dependencies::remove_dependencies_records_the_full_removed_edge ... ok
test bead::mutation::tests::links::link_operation_ids_make_replay_idempotent_but_keep_distinct_reads ... ok
test bead::mutation::tests::links_evidence::warm_plus_one_records_evidence_and_dedupes ... ok
test bead::mutation::tests::links_evidence::warm_closed_task_plus_one_promotes_to_ready ... ok
test bead::mutation::tests::dual_mode::dual_mode_closed_bead_launch_attach_matches_replay ... ok
test bead::mutation::tests::links::link_projection_receipts_are_scoped_to_edge_and_direction ... ok
test bead::mutation::tests::lifecycle_warm::lifecycle_open_reopens_closed_ancestors_warm ... ok
test bead::mutation::tests::dual_mode::dual_mode_plus_one_and_snooze_match_replay ... ok
test bead::mutation::tests::links::phase_size_round_trips_through_create_update_events_and_projection ... ok
test bead::mutation::tests::dual_mode::dual_mode_note_edit_and_remove_match_replay ... ok
test bead::mutation::tests::links_evidence::warm_link_receipt_replay_writes_nothing ... ok
test bead::mutation::tests::notes_update::update_issues_closes_parent_and_child_regardless_of_argument_order ... ok
test bead::mutation::tests::links::link_projection_batch_repairs_seen_receipt_then_replays_without_rewrite ... ok
test bead::mutation::tests::lifecycle_warm::lifecycle_remove_max_suffix_is_reused_warm ... ok
test bead::mutation::tests::links::projection_writers_are_byte_stable_for_the_same_store_state ... ok
test bead::mutation::tests::links::link_projection_skip_classifies_terminal_removed_holder ... ok
test bead::mutation::tests::links::inbound_direction_link_add_and_remove_round_trip ... ok
test bead::mutation::tests::links_projection::event_store_mutation_leaves_issues_jsonl_without_a_diff ... ok
test bead::mutation::tests::dual_mode::dual_mode_dependencies_and_references_match_replay ... ok
test bead::mutation::tests::links_evidence::warm_link_projection_batch_publishes_both_streams ... ok
test bead::mutation::tests::links::link_projection_receipt_does_not_hide_changed_reduced_state ... ok
test bead::mutation::tests::notes_attachments::append_issue_note_records_attachments_and_replays ... ok
test bead::mutation::tests::links_evidence::warm_undirected_link_consolidates_onto_one_holder ... ok
test bead::mutation::tests::links_evidence::warm_link_projections_stay_warm ... ok
test bead::mutation::tests::links_evidence::warm_link_add_and_remove_stay_warm ... ok
test bead::mutation::tests::links::out_and_in_direction_links_to_same_target_do_not_collide ... ok
test bead::mutation::tests::links_evidence::warm_snooze_wake_and_cancel_stay_warm ... ok
test bead::mutation::tests::links_projection::a_pre_close_history_projection_recovers_its_reason_on_the_next_load ... ok
test bead::mutation::tests::links::link_projection_batch_matches_singleton_bytes_for_mixed_requests ... ok
test bead::mutation::tests::links_projection::open_issue_no_longer_leaves_stale_close_metadata_in_the_projection ... ok
test bead::mutation::tests::links::link_mutations_round_trip_and_keep_related_undirected ... ok
test bead::mutation::tests::lifecycle_warm::lifecycle_dual_mode_converges ... ok
test bead::mutation::tests::notes_attachments::append_issue_note_rejects_orphan_descriptor_without_writing ... ok
test bead::mutation::tests::read_model_mutations::mutation_view_overlay_covers_batch_exchange ... ok
test bead::mutation::tests::links_evidence::dual_mode_links_evidence_matches_replay ... ok
test bead::mutation::tests::read_model_mutations::partial_writer_keeps_full_manifest_count ... ok
test bead::mutation::tests::read_model_mutations::store_io_stats_prove_replay_and_validation ... ok
test bead::mutation::tests::read_model_mutations::validation_rejection_leaves_canonical_bytes_unchanged ... ok
test bead::mutation::tests::notes_update::append_issue_note_rejects_blank_entry_without_writing ... ok
test bead::mutation::tests::notes_update::append_issue_note_defaults_blank_author_to_store_owner ... ok
test bead::mutation::tests::snooze_plus_one::an_invalid_derived_state_leaves_the_event_streams_untouched ... ok
test bead::mutation::tests::snooze_plus_one::a_store_bricked_by_a_close_over_a_snooze_loads_again ... ok
test bead::mutation::tests::notes_update::append_issue_note_appends_attributed_entries_and_event ... ok
test bead::mutation::tests::snooze_plus_one::concurrent_task_plus_ones_preserve_reporters_and_deduplicate_retries ... ok
test bead::mutation::tests::snooze_plus_one::deferral_length_label_buckets_and_rounds_half_away_from_zero ... ok
test bead::mutation::tests::notes_attachments::edit_issue_note_replaces_keeps_or_detaches_manifest ... ok
test bead::mutation::tests::notes_update::edit_issue_note_rejects_unknown_note_id_without_writing ... ok
test bead::mutation::tests::notes_update::close_with_note_rejects_blank_entry_without_writing ... ok
test bead::mutation::tests::notes_update::edit_issue_note_rejects_blank_text_without_writing ... ok
test bead::mutation::tests::notes_update::remove_issue_note_rejects_unknown_note_id_without_writing ... ok
test bead::mutation::tests::notes_update::update_issues_collapses_duplicate_ids_to_one_update ... ok
test bead::mutation::tests::notes_update::update_issues_applies_same_fields_to_every_target_in_one_pass ... ok
test bead::mutation::tests::notes_update::update_issues_reopens_shared_ancestor_only_once ... ok
test bead::mutation::tests::notes_update::update_issues_mixed_batch_reports_changed_and_unchanged ... ok
test bead::mutation::tests::notes_update::update_out_of_closed_reopens_closed_ancestor ... ok
test bead::mutation::tests::notes_update::update_issues_reports_request_order_resolution_with_duplicates ... ok
test bead::mutation::tests::notes_update::update_refuses_the_snoozed_status_shortcut ... ok
test bead::mutation::tests::notes_update::remove_issue_note_retracts_the_record_and_history_still_replays_it ... ok
test bead::mutation::tests::notes_update::edit_issue_note_rewrites_text_and_preserves_original_authorship ... ok
test bead::mutation::tests::notes_update::close_with_note_appends_to_every_requested_issue_before_close ... ok
test bead::mutation::tests::notes_update::update_replaces_task_type_fields_and_replays_from_events ... ok
test bead::mutation::tests::links_evidence::warm_links_evidence_errors_leave_no_bytes ... ok
test bead::mutation::tests::notes_update::update_with_matching_fields_is_a_quiet_no_op ... ok
test bead::mutation::tests::notes_update::updating_a_snoozed_bead_off_snoozed_drops_the_record ... ok
test agent_scan::index::tests::visibility::dismissal_reconcile_is_set_based_on_large_fixture ... ok
test bead::mutation::tests::read_model_mutations::allocation_metadata_matches_oracle_with_overlay ... ok
test bead::mutation::tests::notes_update::update_issue_resolution_omitted_null_and_set_mutate_deliberately ... ok
test bead::mutation::tests::publish_direct::backdated_append_takes_synchronous_repair ... ok
test bead::mutation::tests::publish_direct::concurrent_publication_loses_cas_without_stale_pairing ... ok
test bead::mutation::tests::publish_direct::in_place_change_inside_window_is_caught_at_admission ... ok
test bead::mutation::tests::read_model_mutations::cached_create_matches_replay_without_full_scan ... ok
test bead::mutation::tests::store::legacy_jsonl_migration_first_save_writes_every_imported_stream ... ok
test bead::mutation::tests::publish_direct::warm_update_publishes_direct_without_sweep_or_snapshot ... ok
test bead::mutation::tests::publish_direct::warm_note_append_publishes_direct_without_sweep_or_snapshot ... ok
test bead::mutation::tests::publish_direct::warm_create_publishes_direct_without_sweep_or_snapshot ... ok
test bead::mutation::tests::read_model_mutations::indexed_noop_update_writes_nothing ... ok
test bead::mutation::tests::view_commit::view_commit_replay_commit_on_legacy_store ... ok
test bead::mutation::tests::read_model_mutations::dual_mode_note_update_matches ... ok
test bead::mutation::tests::read_model_mutations::indexed_mutations_match_replay_store ... ok
test bead::mutation::tests::read_model_mutations::indexed_rejection_matches_replay_bytes ... ok
test bead::mutation::tests::read_model_mutations::mutation_sweep_establishes_fresh_baseline ... ok
test bead::mutation::tests::read_model_mutations::mutation_view_cached_matches_replay ... ok
test bead::mutation::tests::read_model_mutations::indexed_note_update_skips_full_replay ... ok
test bead::mutation::tests::read_model_mutations::indexed_note_on_closed_bead_matches_replay ... ok
test bead::read::tests::claimed_dependency_is_an_active_blocker ... ok
test bead::read::tests::claimed_status_filter_is_parsed_and_counted ... ok
test bead::read::tests::doctor_ignores_transient_mutation_holder_metadata ... ok
test bead::read::tests::doctor_marks_unavailable_reference_context_as_skipped ... ok
test bead::read::tests::ready_query_returns_only_unblocked_ready_tasks ... ok
test bead::read::tests::reference_diagnostics_groups_unknown_missing_and_ambiguous_entries ... ok
test bead::read::tests::resolve_issue_id_accepts_full_ids_and_unique_suffixes ... ok
test bead::read::tests::resolve_issue_id_reports_unknown_and_ambiguous_suffixes ... ok
test bead::read::tests::stats_derive_plus_one_total_from_structured_evidence ... ok
test bead::read_model::alloc::tests::child_parsing_is_textual_not_parent_field ... ok
test bead::read_model::alloc::tests::maxima_ignore_malformed_nested_and_empty ... ok
test bead::read_model::alloc::tests::top_level_parsing_matches_replay_oracle ... ok
test bead::read_model::freshness::tests::sweep_and_token_agree_on_stable_store ... ok
test bead::read_model::location::tests::no_git_dir_means_no_cache_path ... ok
test bead::mutation::tests::read_model_mutations::mutation_view_covers_deps_refs_receipts ... ok
test bead::read_model::tests::cache_path_lives_under_the_git_dir ... ok
test bead::mutation::tests::close::mutation_and_reducer_agree_on_every_reopen_path ... ok
test bead::mutation::tests::snooze_plus_one::closing_a_snoozed_task_drops_the_record_and_the_store_reloads ... ok
test bead::mutation::tests::snooze_plus_one::cancel_task_snooze_returns_the_bead_to_ready ... ok
test bead::read_model::tests::legacy_store_has_no_cache ... ok
test bead::mutation::tests::snooze_plus_one::plus_one_invalid_manifest_writes_no_partial_event ... ok
test bead::mutation::tests::snooze_plus_one::plus_one_below_the_target_leaves_a_snoozed_bead_snoozed ... ok
test bead::mutation::tests::snooze_plus_one::plus_one_duplicate_reporter_with_attachments_is_a_noop ... ok
test bead::mutation::tests::snooze_plus_one::plus_one_ordinary_records_evidence_attachments ... ok
test bead::mutation::tests::snooze_plus_one::plus_one_without_attachments_stays_byte_identical ... ok
test bead::mutation::tests::snooze_plus_one::plus_one_at_the_target_wakes_a_snoozed_bead_with_a_preset_note ... ok
test bead::mutation::tests::snooze_plus_one::snooze_task_rejects_non_task_beads ... ok
test bead::mutation::tests::store::link_projection_batch_takes_one_load_and_save_cycle ... ok
test bead::mutation::tests::publish_direct::cache_fault_never_fails_the_mutation_or_duplicates_events ... ok
test bead::mutation::tests::snooze_plus_one::plus_one_wake_keeps_manifest_on_evidence_and_wake_note_free ... ok
test bead::mutation::tests::snooze_plus_one::snooze_task_records_wake_conditions_and_replays_from_events ... ok
test bead::read_model::tests::versions_are_current ... ok
test bead::mutation::tests::snooze_plus_one::plus_one_withheld_reopen_records_evidence_attachments ... ok
test bead::routing::tests::aliases_to_same_store_are_deduplicated ... ok
test bead::routing::tests::exact_duplicate_ids_are_ambiguous_across_distinct_stores ... ok
test bead::routing::tests::full_id_fallback_checks_exact_membership ... ok
test bead::routing::tests::local_full_id_hit_wins_without_candidates ... ok
test bead::routing::tests::shorthand_never_falls_back_to_foreign_store ... ok
test bead::routing::tests::single_store_batches_reject_mixed_owners ... ok
test bead::routing::tests::unavailable_relevant_store_is_actionable ... ok
test bead::schema::tests::drop_flag_type_migration_removes_flag_rows_and_column ... ok
test bead::schema::tests::external_ref_migration_adds_nullable_partial_unique_index ... ok
test bead::schema::tests::flag_type_admission_only_fires_on_pre_flag_pre_task_type_schema ... ok
test bead::schema::tests::fresh_schema_accepts_bookend_phase_sizes ... ok
test bead::schema::tests::fresh_schema_accepts_claimed_status ... ok
test bead::schema::tests::fresh_schema_enforces_task_and_ready_constraints ... ok
test bead::schema::tests::fresh_schema_enforces_task_type_check_and_accepts_task_rows ... ok
test bead::schema::tests::issue_type_migration_preserves_and_accepts_claimed_status ... ok
test bead::schema::tests::metadata_migration_adds_only_missing_columns ... ok
test bead::schema::tests::migration_detection_matches_python_helpers ... ok
test bead::schema::tests::plus_one_evidence_migration_defaults_legacy_rows_to_empty_json ... ok
test bead::schema::tests::refs_migration_preserves_existing_rows_and_defaults_empty ... ok
test bead::schema::tests::relax_migration_preserves_claimed_rows_and_related_data ... ok
test bead::schema::tests::resolution_migration_preserves_legacy_rows_without_backfill ... ok
test bead::schema::tests::schema_contains_current_constraints ... ok
test bead::schema::tests::snoozed_status_migration_admits_snoozed_tasks_and_keeps_close_history ... ok
test bead::schema::tests::task_ready_migration_preserves_rows_and_dependencies ... ok
test bead::schema::tests::task_type_migration_adds_columns_index_and_check ... ok
test bead::mutation::tests::read_model_mutations::indexed_mutation_falls_back_when_cache_is_corrupt ... ok
test bead::seal_watch::tests::probe_is_unavailable_for_a_missing_store ... ok
test bead::seal_watch::tests::probe_is_unavailable_without_an_event_store ... ok
test bead::mutation::tests::snooze_plus_one::snooze_task_with_no_reason_or_target_still_names_the_wake_conditions ... ok
test bead::seal_watch::tests::threshold_constants_match_the_plan ... ok
test bead::seal_watch::tests::thresholds_warn_only_above_the_line ... ok
test bead::search::tests::closed_issues_match_by_default ... ok
test bead::search::tests::field_names_constant_matches_all_collectable_fields ... ok
test bead::search::tests::filters_status_type_and_tier_together ... ok
test bead::search::tests::invalid_regex_is_a_validation_error ... ok
test bead::search::tests::issues_without_close_history_do_not_match_an_archived_reason ... ok
test bead::search::tests::limit_keeps_newest_matches ... ok
test bead::search::tests::literal_match_truth_uses_plain_case_folded_containment ... ok
test bead::search::tests::literal_search_treats_regex_metacharacters_literally ... ok
test bead::search::tests::matches_an_archived_close_reason ... ok
test bead::search::tests::matches_an_archived_resolution ... ok
test bead::search::tests::matches_case_insensitive_unicode_substrings ... ok
test bead::search::tests::matches_every_searchable_field ... ok
test bead::search::tests::no_match_returns_empty_results ... ok
test bead::search::tests::public_search_loads_store_and_returns_wire_matches ... ok
test bead::search::tests::regex_search_allows_inline_case_sensitivity ... ok
test bead::search::tests::regex_search_matches_patterns_case_insensitively_by_default ... ok
test bead::search::tests::rejects_empty_or_whitespace_query ... ok
test bead::search::tests::returns_newest_matches_before_older_matches ... ok
test bead::search::tests::zero_limit_is_unlimited ... ok
test bead::search::tests::zero_width_regex_matches_fields ... ok
test bead::search::tests::zero_width_regex_matches_truth_but_not_highlight_ranges ... ok
test bead::target_probe::tests::foreign_prefix_misses_without_reading_streams ... ok
test bead::target_probe::tests::legacy_store_is_unknown ... ok
test bead::target_probe::tests::missing_stem_misses ... ok
test bead::target_probe::tests::missing_store_is_unknown ... ok
test bead::target_probe::tests::phase_id_hits_through_its_parent_stem ... ok
test bead::target_probe::tests::root_id_hits_its_stream_file ... ok
test bead::target_probe::tests::shorthand_never_probes_a_hit ... ok
test bead::target_probe::tests::tombstoned_stem_still_routes_to_its_store ... ok
test bead::touch_index::tests::a_changed_stream_is_re_reduced_and_siblings_are_reused ... ok
test bead::touch_index::tests::a_plan_stream_attributes_touches_to_child_beads ... ok
test bead::seal_watch::tests::probe_counts_nested_tree_bytes ... ok
test bead::touch_index::tests::a_schema_two_index_is_a_miss_until_the_rebuild ... ok
test bead::touch_index::tests::a_schema_one_index_is_a_miss_until_the_rebuild ... ok
test bead::touch_index::tests::a_single_contributing_event_bounds_both_ends ... ok
test bead::touch_index::tests::a_stream_that_never_mentions_its_own_root_is_skipped ... ok
test bead::mutation::tests::store::append_note_preserves_legacy_issue_created_prefix_and_projects_structured_note ... ok
test bead::mutation::tests::snooze_plus_one::re_snoozing_replaces_the_record_and_appends_a_second_event ... ok
test bead::touch_index::tests::close_credits_the_closed_by_closer_never_the_creator ... ok
test bead::touch_index::tests::close_record_reports_resolution_reason_and_standing ... ok
test bead::touch_index::tests::created_plus_closed_row_keeps_both_reason_and_close ... ok
test bead::touch_index::tests::creation_reason_lands_only_on_the_creator_row ... ok
test bead::touch_index::tests::edit_by_another_actor_updates_text_without_moving_authorship ... ok
test bead::touch_index::tests::excluded_and_unknown_operations_contribute_no_touch ... ok
test bead::touch_index::tests::globalized_and_bare_local_actors_stay_distinct_and_trimmed ... ok
test bead::touch_index::tests::human_closed_by_produces_no_touch ... ok
test bead::mutation::tests::snooze_plus_one::snooze_task_rejects_bad_targets_times_and_statuses ... ok
test bead::touch_index::tests::legacy_close_credits_only_the_unique_same_instant_note_author ... ok
test bead::touch_index::tests::long_and_unicode_note_text_truncates_on_char_boundaries ... ok
test bead::touch_index::tests::long_creation_reason_truncates_with_a_marker ... ok
test bead::touch_index::tests::malformed_lines_and_shapes_are_skipped_not_fatal ... ok
test bead::touch_index::tests::malformed_note_payloads_keep_verbs_but_skip_previews ... ok
test bead::touch_index::tests::a_stream_that_stops_belonging_to_its_filename_is_dropped ... ok
test bead::touch_index::tests::empty_store_writes_an_empty_index_and_queries_nothing ... ok
test bead::touch_index::tests::a_schema_version_bump_is_a_cache_miss_and_forces_a_full_rebuild ... ok
test bead::touch_index::tests::note_preview_covers_append_and_selects_the_newest ... ok
test bead::touch_index::tests::non_agent_and_blank_appends_never_produce_previews ... ok
test bead::touch_index::tests::note_preview_tie_breaks_on_stable_id ... ok
test bead::touch_index::tests::owner_created_title_still_reaches_agent_rows ... ok
test bead::touch_index::tests::note_previews_stay_scoped_to_author_and_bead ... ok
test bead::touch_index::tests::index_file_shape_matches_the_documented_contract ... ok
test bead::touch_index::tests::owner_email_and_invalid_actors_never_become_touchers ... ok
test bead::touch_index::tests::reasonless_and_blank_reasons_index_as_absent ... ok
test bead::touch_index::tests::reduction_counts_verbs_and_bounds_timestamps_regardless_of_order ... ok
test bead::touch_index::tests::refresh_ignores_non_jsonl_files_and_directories ... ok
test bead::touch_index::tests::query_filters_by_exact_trimmed_actor_and_orders_newest_first ... ok
test bead::touch_index::tests::removal_falls_back_to_the_previous_note_then_to_nothing ... ok
test bead::touch_index::tests::reopened_close_loses_standing_and_the_next_closer_wins ... ok
test bead::seal_watch::tests::probe_measures_a_small_store_as_ok ... ok
test bead::touch_index::tests::stale_index_still_answers_without_touching_the_streams ... ok
test bead::touch_index::tests::new_and_vanished_streams_update_the_index ... ok
test bead::touch_index::tests::timestamps_with_offsets_normalize_to_utc_z ... ok
test bead::touch_index::tests::title_type_and_status_follow_the_newest_carrying_event ... ok
test bead::touch_index::tests::status_tracks_close_reopen_preclaim_and_snooze_events ... ok
test bead::touch_index::tests::unknown_edit_and_remove_ids_leave_previews_alone ... ok
test bead::touch_index::tests::verb_table_covers_every_operation_and_excludes_preclaim ... ok
test bead::wire::tests::bug_id_requires_changespec_name ... ok
test bead::wire::tests::claimed_status_round_trips_through_serde ... ok
test bead::wire::tests::close_history_is_allowed_on_every_issue_type ... ok
test bead::wire::tests::close_history_omits_absent_reason_and_resolution ... ok
test bead::wire::tests::close_history_round_trips_and_stays_absent_when_empty ... ok
test bead::wire::tests::close_history_validation_rejects_blank_fields ... ok
test bead::wire::tests::creation_reason_round_trips_and_stays_absent_when_empty ... ok
test bead::wire::tests::empty_optional_strings_normalize_to_none ... ok
test bead::wire::tests::empty_phase_size_normalizes_to_none_and_invalid_values_fail ... ok
test bead::wire::tests::empty_task_type_normalizes_to_none ... ok
test bead::wire::tests::external_ref_round_trips_when_non_empty ... ok
test bead::wire::tests::legacy_defaults_match_python_jsonl_loader ... ok
test bead::wire::tests::model_rejects_control_characters ... ok
test bead::wire::tests::normalize_creation_reason_keeps_history_readable_but_gates_writes ... ok
test bead::wire::tests::phase_rejects_plan_only_fields ... ok
test bead::wire::tests::phase_requires_parent ... ok
test bead::wire::tests::phase_size_round_trips_all_enum_values_and_rejects_plan_usage ... ok
test bead::wire::tests::ready_status_requires_task_type ... ok
test bead::wire::tests::resolution_round_trips_and_requires_closed_status ... ok
test bead::wire::tests::snooze_key_is_absent_when_the_bead_is_not_snoozed ... ok
test bead::wire::tests::snooze_metadata_requires_snoozed_status ... ok
test bead::wire::tests::snooze_record_validates_its_own_fields ... ok
test bead::wire::tests::snoozed_status_requires_a_task_and_a_record ... ok
test bead::touch_index::tests::refresh_fails_loudly_on_a_held_lock ... ok
test bead::wire::tests::snoozed_status_round_trips_with_its_record ... ok
test bead::wire::tests::task_plus_one_evidence_validates_structure_and_reporter_uniqueness ... ok
test bead::wire::tests::task_type_and_field_keys_must_be_bounded_snake_case ... ok
test bead::wire::tests::task_type_fields_require_task_type ... ok
test bead::wire::tests::task_type_is_rejected_on_non_task_issues ... ok
test bead::wire::tests::task_validation_allows_size_and_ready_but_rejects_plan_fields ... ok
test bead::wire::tests::task_type_round_trips_and_stays_absent_when_empty ... ok
test bead::work::tests::child_epics_are_excluded_from_parent_waves ... ok
test bead::work::tests::claimed_phase_is_still_scheduled ... ok
test bead::work::tests::closed_in_epic_blocker_is_only_a_bead_wait ... ok
test bead::work::tests::closed_only_plan_returns_land_only_work_plan ... ok
test bead::work::tests::closed_or_removed_child_plan_does_not_exclude_phase ... ok
test bead::work::tests::delegated_only_plan_has_no_waves ... ok
test bead::work::tests::delegated_phase_is_excluded_but_remains_a_bead_blocker ... ok
test bead::work::tests::detects_cycles ... ok
test bead::work::tests::epic_work_plan_copies_phase_and_land_models ... ok
test bead::work::tests::land_waits_on_every_launched_phase_in_wave_order ... ok
test bead::work::tests::missing_out_of_epic_blocker_is_satisfied_with_warning ... ok
test bead::work::tests::epic_launch_layers_match_clan_layers_for_declared_phase_waits ... ok
test bead::work::tests::parent_does_not_change_epic_launch_tag ... ok
test bead::work::tests::plans_diamond_dag_in_waves ... ok
test bead::work::tests::rejects_epic_with_no_phase_children ... ok
test bead::work::tests::rejects_open_out_of_epic_blocker ... ok
test bead::work::tests::standalone_epic_uses_epic_launch_tag ... ok
test bead::work::tests::total_phase_count_includes_closed_phases ... ok
test bead_action::tests::close_on_already_closed_bead_is_idempotent ... ok
test bead_action::tests::close_on_primary_commit_or_pr_closes_an_in_progress_bead ... ok
test bead_action::tests::close_on_proposal_is_rejected ... ok
test bead_action::tests::close_outside_identified_primary_is_rejected ... ok
test bead_action::tests::close_requires_readable_in_progress_or_closed_status ... ok
test bead_action::tests::close_without_assigned_bead_is_rejected ... ok
test bead_action::tests::closed_assigned_bead_still_requires_an_explicit_decision ... ok
test bead_action::tests::declaration_for_a_different_assignment_is_rejected ... ok
test bead_action::tests::failed_primary_lookup_does_not_grant_close ... ok
test bead_action::tests::finalizer_keep_and_close_follow_repository_identity ... ok
test bead_action::tests::json_keep_on_primary_commit_round_trips ... ok
test bead_action::tests::json_request_rejects_null_and_legacy_fields ... ok
test bead_action::tests::keep_commits_without_closing_for_every_assigned_context ... ok
test bead_action::tests::keep_without_assigned_bead_is_a_uniform_noop ... ok
test bead_action::tests::omitted_action_with_assigned_bead_is_rejected_for_every_scope ... ok
test bead_action::tests::omitted_action_without_assigned_bead_is_existing_commit_behavior ... ok
test bead_action::tests::unassociated_context_allows_omitted_or_keep_and_rejects_close ... ok
test bead_action::wire::parse_tests::bead_action_round_trips_through_serde ... ok
test bead_action::wire::parse_tests::parses_close_and_keep_and_preserves_absence ... ok
test bead_action::wire::parse_tests::rejects_boolean_null_empty_and_unknown_values ... ok
test bead_action::wire::parse_tests::rejects_legacy_do_not_close_bead_even_when_false ... ok
test clan_waves::tests::bead_edges_keep_the_land_on_the_seal_layer ... ok
test clan_waves::tests::aliases_sessions_and_retry_members_resolve_by_identity ... ok
test clan_waves::tests::clan_name_and_subhood_waits_use_launch_snapshot_semantics ... ok
test clan_waves::tests::cycles_and_their_dependents_are_unresolved_without_dropping_members ... ok
test clan_waves::tests::duplicate_names_resolve_to_every_member_key ... ok
test clan_waves::tests::diamond_and_asymmetric_overlap_keep_predecessors_in_display_order ... ok
test clan_waves::tests::epic_layers_five_numbered_waves_and_a_seal ... ok
test clan_waves::tests::ghost_only_wave_preserves_numbering_and_external_wait_counts ... ok
test clan_waves::tests::land_sharing_the_final_layer_stays_numbered ... ok
test clan_waves::tests::late_joiners_without_waits_stay_in_the_first_layer ... ok
test clan_waves::tests::research_swarm_layers_media_before_linker ... ok
test clan_waves::tests::long_chain_and_flat_fanout_report_layered_state ... ok
test clan_waves::tests::retries_stay_after_the_root_even_when_another_member_launched_between_them ... ok
test clan_waves::tests::serde_defaults_cover_optional_and_list_fields ... ok
test command_line::tokenizer::tests::adjacent_concatenation_joins ... ok
test command_line::tokenizer::tests::backslash_escapes_inside_and_outside ... ok
test command_line::tokenizer::tests::multibyte_spans_are_char_offsets ... ok
test command_line::tokenizer::tests::plain_words_span_chars ... ok
test command_line::tokenizer::tests::single_and_double_quotes ... ok
test command_line::tokenizer::tests::unterminated_quotes_run_to_end ... ok
test command_line::tokenizer::tests::whitespace_only_has_no_tokens ... ok
test commit_footer::tests::adding_tags_preserves_link_and_definition_below_complete_tag_block ... ok
test commit_footer::tests::new_links_allocate_numeric_ids_without_body_or_footer_collisions ... ok
test commit_footer::tests::ordinary_reference_definitions_and_mid_message_tags_remain_body ... ok
test commit_footer::tests::parses_linked_values_and_reference_destinations ... ok
test commit_footer::tests::parses_plain_prefixed_and_legacy_tags_with_later_duplicates ... ok
test commit_footer::tests::repeated_updates_are_idempotent_and_preserve_trailing_shape ... ok
test commit_footer::tests::replacing_or_removing_linked_tags_cleans_only_owned_definitions ... ok
test commit_footer::tests::shared_targets_reuse_one_definition_deterministically ... ok
test commit_sha::tests::equivalent_sha_matrix ... ok
test commit_sha::tests::rejects_ambiguous_or_invalid_shas ... ok
test commit_subject::tests::exempts_git_generated_and_rebase_subjects ... ok
test commit_subject::tests::exposes_stable_ordered_defaults ... ok
test commit_subject::tests::honors_custom_allowed_types ... ok
test commit_subject::tests::parses_plain_scoped_breaking_and_spaced_subjects ... ok
test commit_subject::tests::reads_only_the_trimmed_first_line ... ok
test commit_subject::tests::rejects_empty_descriptions_and_subjects ... ok
test commit_subject::tests::rejects_missing_or_malformed_type_separator ... ok
test commit_subject::tests::reports_uppercase_before_unknown_type ... ok
test config::macro_syntax::tests::both_spellings_collide_in_both_flag_states ... ok
test config::macro_syntax::tests::canonical_layer_passes_through_untouched_in_both_states ... ok
test config::macro_syntax::tests::entry_bodies_are_data_not_keys ... ok
test config::macro_syntax::tests::legacy_keys_move_even_when_switch_denied ... ok
test config::axe::tests::entry_mutation_targets_existing_legacy_timeout_source ... ok
test config::macro_syntax::tests::legacy_top_level_keys_move_when_accepted ... ok
test config::macro_syntax::tests::nested_collision_rejects ... ok
test config::macro_syntax::tests::nested_completion_and_mentor_keys_normalize ... ok
test config::macro_syntax::tests::non_mapping_layer_rejects ... ok
test config::macro_syntax::tests::presence_counts_even_for_null_and_empty_values ... ok
test config::plan::tests::edit_plan_targets_existing_legacy_source_for_public_alias ... ok
test config::plan::tests::edit_plan_targets_existing_legacy_source_for_missing_public_leaf ... ok
test config::plan::tests::edit_plan_targets_existing_public_source_for_missing_public_leaf ... ok
test config::plan::tests::edit_plan_uses_canonical_path_for_new_public_alias ... ok
test config::provenance::tests::inventory_canonical_projection_merges_both_alias_spellings ... ok
test config::provenance::tests::inventory_normalizes_axe_aliases_and_projects_public_contract ... ok
test content_layout::tests::collision_policy_is_exclusive_for_config_and_first_wins_for_macros ... ok
test config::provenance::tests::inventory_reports_same_layer_conflicting_alias_paths ... ok
test content_layout::tests::macro_layouts_write_to_sase_macros_with_retired_legacy ... ok
test content_layout::tests::macro_priority_covers_canonical_legacy_config_plugin_and_package ... ok
test content_layout::tests::memory_references_are_always_the_flat_namespaced_filename ... ok
test content_layout::tests::macro_sources_are_new_first_with_legacy_lists_unchanged ... ok
test content_layout::tests::memory_rules_reject_reserved_names_bad_stems_and_bad_tiers ... ok
test content_layout::tests::memory_tier_parses_current_and_legacy_note_types ... ok
test content_layout::tests::memory_sources_are_project_before_home_with_exclusive_read_policy ... ok
test content_layout::tests::memory_tier_serializes_current_names_and_deserializes_legacy_names ... ok
test content_layout::tests::missing_project_root_still_returns_complete_home_contract ... ok
test content_layout::tests::project_and_home_paths_keep_runtime_and_generated_content_separate ... ok
test content_layout::tests::ref_directories_are_canonical ... ok
test content_layout::tests::skill_directories_are_canonical_in_every_scope ... ok
test content_layout::tests::skill_placement_issues_name_the_move_in_both_directions ... ok
test content_layout::tests::skill_reference_names_split_provider_name_from_xprompt_reference ... ok
test content_layout::tests::skill_sources_are_ordered_first_wins_with_no_legacy_paths ... ok
test continuation::budget::tests::checkpoint_threshold_uses_reductions_before_hard_limit ... ok
test continuation::budget::tests::compacts_in_design_order ... ok
test continuation::budget::tests::fits_inside_budget ... ok
test continuation::budget::tests::refuses_when_essential_content_cannot_fit ... ok
test continuation::budget::tests::refuses_when_threshold_crosses_without_adequate_checkpoint ... ok
test continuation::completion::tests::absent_stage_source_keeps_sealing_like_legacy_callers ... ok
test continuation::completion::tests::accept_defaults_to_pass_for_older_requests ... ok
test continuation::completion::tests::consume_is_idempotent_for_bound_intents ... ok
test continuation::completion::tests::decided_protected_path_names_repository ... ok
test continuation::completion::tests::bind_is_single_use_and_command_sensitive ... ok
test continuation::completion::tests::incomplete_observations_are_ineligible ... ok
test continuation::completion::tests::empty_prior_refusals_disable_the_guard ... ok
test continuation::completion::tests::legacy_pass_seal_without_accept_fields_still_validates ... ok
test continuation::completion::tests::legacy_request_without_new_fields_still_seals ... ok
test continuation::completion::tests::matching_prior_refusal_is_refused ... ok
test continuation::completion::tests::no_new_seal_round_trips_and_differs_from_pass ... ok
test continuation::completion::tests::none_stage_source_is_refused_with_required_stages ... ok
test continuation::completion::tests::none_stage_source_lists_check_stages_for_check ... ok
test continuation::completion::tests::non_matching_prior_refusals_are_allowed ... ok
test continuation::completion::tests::old_all_repository_fingerprint_fails_closed ... ok
test continuation::completion::tests::rejects_missing_repository_decisions ... ok
test continuation::completion::tests::rejects_altered_finalizer_plan ... ok
test continuation::completion::tests::rejects_protected_and_foreign_paths ... ok
test continuation::completion::tests::rejects_stale_context_digest ... ok
test continuation::completion::tests::rejects_unsupported_executors_and_arbitrary_commands ... ok
test continuation::completion::tests::render_substitutes_only_documented_host_facts ... ok
test continuation::completion::tests::run_silent_stage_source_keeps_sealing ... ok
test continuation::completion::tests::rollback_restores_a_bound_intent ... ok
test continuation::completion::tests::scoped_fingerprint_ignores_undecided_and_orders_deterministically ... ok
test continuation::completion::tests::tampered_accept_or_policy_version_fails_closed ... ok
test continuation::completion::tests::seals_a_valid_first_party_intent ... ok
test continuation::completion::tests::undecided_incomplete_and_unknown_head_do_not_block_seal ... ok
test bead::mutation::tests::store::mutable_appends_mint_stable_content_hashed_event_ids ... ok
test bead::touch_index::tests::refresh_rebuilds_reasons_from_streams_end_to_end ... ok
test bead::touch_index::tests::unchanged_streams_reuse_cached_rows_and_skip_the_write ... ok
test continuation::completion::tests::undecided_protected_and_foreign_paths_do_not_block_seal ... ok
test bead::mutation::tests::snooze_plus_one::task_plus_one_creator_and_repeat_are_byte_identical_noops ... ok
test continuation::completion_eval::tests::model_requiring_executors_are_ineligible ... ok
test continuation::completion_eval::tests::eligible_bound_success_completes_without_model ... ok
test continuation::completion_eval::tests::decided_change_goes_stale ... ok
test continuation::completion_eval::tests::missing_decided_observation_goes_stale ... ok
test continuation::completion_eval::tests::new_undecided_obligation_reports_new_repository_obligation ... ok
test continuation::completion_eval::tests::missing_or_skipped_stages_are_ineligible ... ok
test continuation::completion_eval::tests::producer_pass_cannot_grant_eligibility_without_host_success ... ok
test continuation::completion_eval::tests::no_new_failed_nonzero_stays_eligible_without_stage_gate ... ok
test continuation::delivery::tests::concurrent_reserve_discovers_the_same_identity ... ok
test continuation::delivery::tests::empty_records_admit_requested_ordinary_branch ... ok
test continuation::delivery::tests::existing_manual_branch_does_not_admit_a_second_spawn ... ok
test continuation::delivery::tests::host_completion_may_acknowledge_from_reserved ... ok
test continuation::delivery::tests::host_completion_rejects_degraded_workspace ... ok
test continuation::delivery::tests::manual_revision_fences_unproven_dispatching_and_admits ... ok
test continuation::delivery::tests::ordinary_continue_cannot_skip_dispatching ... ok
test continuation::delivery::tests::ordinary_continue_walks_the_approved_graph ... ok
test continuation::delivery::tests::ordinary_resume_does_not_retry_unproven_dispatching ... ok
test continuation::delivery::tests::reserved_requires_identity ... ok
test continuation::delivery::tests::resume_adoption_preserves_acknowledged_records ... ok
test continuation::delivery::tests::retryable_pre_dispatch_failure_returns_to_reserved ... ok
test continuation::completion_eval::tests::undecided_head_and_path_changes_do_not_go_stale ... ok
test continuation::delivery::tests::stale_receiver_without_live_process_needs_attention ... ok
test continuation::delivery::tests::stop_before_reservation_cancels ... ok
test continuation::delivery::tests::wrong_receiver_cannot_adopt_reserved_identity ... ok
test continuation::evidence::tests::auto_completed_uses_facts_without_raw_log ... ok
test continuation::evidence::tests::auto_failed_uses_stage_diagnostics ... ok
test continuation::evidence::tests::strict_file_and_none_policies_never_embed_raw_output ... ok
test continuation::policy::tests::cli_evidence_and_model_override_policy_and_inherited_route ... ok
test continuation::policy::tests::complete_on_failed_branch_is_rejected ... ok
test continuation::policy::tests::explicit_complete_without_prepared_ref_is_rejected ... ok
test continuation::policy::tests::omitted_next_stays_fire_and_forget ... ok
test continuation::policy::tests::policy_next_action_wins_over_shared_next ... ok
test continuation::policy::tests::freeze_fingerprint_changes_when_policy_content_changes ... ok
test continuation::policy::tests::policy_none_wins_over_shared_next ... ok
test continuation::policy::tests::freeze_persists_all_branches_and_content_fingerprint ... ok
test continuation::policy::tests::stopped_and_lost_never_launch_even_when_policy_requests_continue ... ok
test continuation::policy::tests::verify_profile_completed_with_prepared_intent_completes ... ok
test continuation::policy::tests::verify_profile_failed_no_new_enters_host_completion ... ok
test continuation::policy::tests::verify_profile_failure_gets_recovery_next_action ... ok
test continuation::policy::tests::verify_profile_no_new_keeps_pass_and_non_failed_on_recovery ... ok
test continuation::policy::tests::verify_profile_without_next_or_completion_is_fire_and_forget_on_success ... ok
test continuation::replay::tests::detects_cycles ... ok
test continuation::replay::tests::rejects_conflicting_duplicate_ids ... ok
test continuation::completion_eval::tests::stale_fingerprint_new_obligations_and_degraded_workspace_recover ... ok
test continuation::replay::tests::preserves_parent_order_for_diamond_graphs ... ok
test continuation::retention::tests::live_monitor_protects_referenced_parent_and_starter ... ok
test continuation::retention::tests::recoverable_pending_delivery_protects_ancestry ... ok
test continuation::retention::tests::required_failures_and_unavailable_metadata_surface ... ok
test continuation::retention::tests::starter_dir_absent_from_scan_is_still_protected ... ok
test continuation::retention::tests::terminal_settled_run_does_not_pin_unrelated_ancestry ... ok
test continuation::schema::tests::agent_delta_rejects_injected_parent_segments ... ok
test continuation::schema::tests::graph_reports_missing_parents_without_guessing ... ok
test continuation::schema::tests::launch_requester_continuation_accepts_terminal_handoff ... ok
test continuation::completion_eval::tests::undecided_incomplete_and_unknown_head_do_not_recover ... ok
test continuation::schema::tests::launch_requester_continuation_keeps_stopped_terminal ... ok
test continuation::schema::tests::monitor_result_accepts_shell_command_longer_than_reference_limit ... ok
test continuation::schema::tests::launch_requester_continuation_validates_resume_contract ... ok
test continuation::schema::tests::monitor_result_rejects_command_part_over_command_limit ... ok
test continuation::schema::tests::node_rejects_oversized_identity ... ok
test continuation::schema::tests::node_rejects_unsupported_schema_version ... ok
test continuation::schema::tests::node_value_rejects_unknown_kind ... ok
test dependency_waves::tests::ignores_dependencies_outside_the_projected_graph ... ok
test dependency_waves::tests::keeps_cycles_and_their_dependents_in_a_deterministic_unresolved_set ... ok
test dependency_waves::tests::layers_diamond_by_longest_dependency_path_and_order_key ... ok
test disk_cleanup_outcome::tests::mixed_success_and_failure_preserves_partial_effects ... ok
test disk_cleanup_outcome::tests::protective_skip_and_capped_batch_do_not_prevent_success ... ok
test disk_cleanup_outcome::tests::unavailable_required_observation_is_incomplete ... ok
test disk_cleanup_outcome::tests::unknown_reclaimed_bytes_are_separate_from_operational_success ... ok
test disk_inventory::tests::duplicate_roots_are_reported_but_counted_once ... ok
test disk_inventory::tests::nested_roots_count_physical_bytes_once ... ok
test continuation::completion_eval::tests::no_new_still_refuses_drift_timeout_and_unbound ... ok
test disk_inventory::tests::unresolved_rows_make_coverage_partial ... ok
test disk_pressure::tests::large_volume_warns_by_proportion ... ok
test disk_pressure::tests::small_volume_warns_by_absolute_floor ... ok
test disk_pressure::tests::top_owners_are_size_sorted_and_bounded ... ok
test editor::alternation::tests::covers_mid_word_and_adjacent_openers ... ok
test editor::alternation::tests::covers_all_three_spellings_through_close_delimiter ... ok
test editor::alternation::tests::scanner_hides_separators_in_quotes_and_brackets ... ok
test editor::alternation::tests::scanner_keeps_glued_and_bare_percent_plain ... ok
test editor::alternation::tests::scanner_keeps_paren_boundary_rule_with_separators ... ok
test editor::alternation::tests::scanner_reports_branch_name_spans ... ok
test editor::alternation::tests::detects_positions_and_spans ... ok
test editor::alternation::tests::scanner_reports_mid_word_wire_record ... ok
test editor::alternation::tests::scanner_reports_only_trailing_alternation_after_real_jinja ... ok
test editor::alternation::tests::scanner_reports_openers_after_literal_brace ... ok
test editor::alternation::tests::scanner_reports_nested_depth_with_top_level_separators ... ok
test editor::alternation::tests::scanner_reports_single_branch_without_separator ... ok
test editor::alternation::tests::scanner_reports_unclosed_marker_without_close ... ok
test editor::alternation::tests::scanner_skips_literal_zones ... ok
test editor::alternation::tests::scanner_splits_on_apostrophes_like_launch ... ok
test editor::alternation::tests::scanner_uses_byte_offsets_for_non_ascii_text ... ok
test editor::alternation::tests::scanner_reports_paren_opener_after_another_opener ... ok
test editor::alternation::tests::skips_markers_in_literal_zones_and_unclosed_markers ... ok
test bead::touch_index::tests::status_classifies_fresh_stale_and_vanished ... ok
test editor::argument_spans::tests::emits_directive_argument_spans ... ok
test continuation::replay::tests::stable_blocks_render_each_serial_node_once ... ok
test editor::argument_spans::tests::double_colon_eol_emits_two_byte_delimiter_and_next_line_value ... ok
test editor::argument_spans::tests::emits_name_spans_for_xprompts_directives_and_aliases ... ok
test editor::argument_spans::tests::closed_calls_keep_validity_but_open_calls_stay_structural ... ok
test editor::argument_spans::tests::highlights_static_if_directive_arguments_outside_literals ... ok
test editor::argument_spans::tests::marks_unterminated_calls_structurally ... ok
test editor::argument_spans::tests::fills_catalog_aware_validity ... ok
test editor::argument_spans::tests::keeps_complex_values_intact ... ok
test editor::argument_spans::tests::emits_spans_for_every_xprompt_argument_syntax ... ok
test editor::argument_spans::tests::open_directive_arguments_are_structural_without_invalidity ... ok
test editor::argument_spans::tests::unterminated_calls_preserve_utf8_and_multiline_text_blocks ... ok
test editor::argument_spans::tests::skips_calls_inside_fenced_blocks ... ok
test editor::argument_spans::tests::repeatable_tail_uses_shared_positional_binding ... ok
test editor::argument_syntax_edit::tests::continuation_handles_utf16_and_multiline_positions ... ok
test editor::argument_spans::tests::still_skips_static_if_directives_inside_code_literals ... ok
test editor::argument_syntax_edit::tests::converts_directive_aliases_and_long_names ... ok
test editor::argument_syntax_edit::tests::converts_supported_double_colon_directives ... ok
test editor::argument_syntax_edit::tests::continues_closed_macro_argument_lists ... ok
test editor::argument_syntax_edit::tests::double_colon_handles_multiline_and_utf16_positions ... ok
test editor::argument_syntax_edit::tests::converts_double_colon_text_invocations ... ok
test editor::argument_syntax_edit::tests::converts_macro_reference_forms_without_catalog_io ... ok
test editor::argument_syntax_edit::tests::handles_multiline_and_utf16_positions ... ok
test editor::argument_syntax_edit::tests::rejects_double_colon_invalid_utf16_positions ... ok
test editor::argument_syntax_edit::tests::rejects_double_colon_ineligible_directives_and_contexts ... ok
test editor::argument_syntax_edit::tests::rejects_double_colon_non_space_gaps_and_malformed_delimiters ... ok
test editor::argument_syntax_edit::tests::rejects_invalid_utf16_positions ... ok
test editor::argument_syntax_edit::tests::rejects_double_colons_and_existing_arguments ... ok
test editor::argument_syntax_edit::tests::spacer_consumes_owned_space_for_input_bearing_entries ... ok
test editor::argument_syntax_edit::tests::rejects_non_invocation_and_mid_word_colons ... ok
test editor::argument_syntax_edit::tests::spacer_handles_multiline_astral_and_exact_range ... ok
test editor::argument_syntax_edit::tests::rejects_double_colon_literal_frontmatter_and_jinja_regions ... ok
test editor::argument_syntax_edit::tests::rejects_ineligible_continuation_sources_and_positions ... ok
test editor::argument_syntax_edit::tests::spacer_normalization_maps_ranges_back ... ok
test editor::argument_syntax_edit::tests::spacer_rejects_invalid_utf16_positions ... ok
test editor::argument_syntax_edit::tests::spacer_rejects_stale_mismatched_and_malformed ... ok
test editor::argument_syntax_edit::tests::rejects_literal_frontmatter_and_jinja_regions ... ok
test editor::argument_syntax_edit::tests::spacer_rejects_zero_input_and_unowned_records ... ok
test editor::argument_syntax_edit::tests::spacer_rejects_excluded_regions ... ok
test editor::at_reference::tests::bare_menu_groups_builtins_then_sorted_kinds_and_visible_paths ... ok
test editor::at_reference::tests::detects_path_shaped_kind_queries ... ok
test editor::at_reference::tests::dotfile_visibility_tracks_the_trailing_partial ... ok
test editor::at_reference::tests::detects_kind_and_payload_at_every_cursor_position ... ok
test editor::at_reference::tests::fuzzy_kind_matches_do_not_gate_file_rows ... ok
test editor::at_reference::tests::gated_menu_without_matching_paths_does_not_offer_an_empty_reveal ... ok
test editor::at_reference::tests::fuzzy_kind_menu_keeps_builtin_ties_and_reports_runs ... ok
test editor::at_reference::tests::indexed_payload_menu_matches_the_wire_inventory_path ... ok
test editor::at_reference::tests::kind_and_file_groups_filter_independently ... ok
test editor::at_reference::tests::malformed_scope_degrades_to_an_unscoped_row ... ok
test editor::at_reference::tests::payload_menu_includes_title_only_matches ... ok
test editor::at_reference::tests::payload_menu_is_path_first_and_ranks_both_match_fields ... ok
test editor::at_reference::tests::path_menu_fuzzy_matches_only_the_trailing_partial ... ok
test editor::at_reference::tests::payload_menu_preserves_empty_query_provider_order ... ok
test editor::at_reference::tests::payload_wire_defaults_new_metadata_when_deserializing_old_rows ... ok
test editor::at_reference::tests::payload_rank_breaks_quality_ties_but_unranked_rows_keep_text_order ... ok
test editor::at_reference::tests::rejects_prose_invalid_characters_and_literal_zones ... ok
test editor::at_reference::tests::qualified_match_highlights_each_field_and_drops_straddling_runs ... ok
test editor::at_reference::tests::scoped_payload_matches_repo_and_title_as_one_qualified_target ... ok
test editor::at_reference::tests::shared_extension_requires_an_all_prefix_leading_group ... ok
test editor::at_reference::tests::caps_each_group_but_records_pre_cap_counts ... ok
test editor::at_reference::tests::shared_extension_uses_only_the_leading_non_empty_group ... ok
test editor::at_reference::tests::payload_caps_report_matches_and_caller_truncation ... ok
test editor::completion::tests::artifact_ref::artifact_kind_candidates_list_builtins_in_documented_order ... ok
test editor::completion::tests::artifact_ref::artifact_replacement_ranges_are_utf16_safe_and_at_paths_stay_references ... ok
test editor::completion::tests::artifact_ref::builds_agent_payload_candidates_from_published_pages ... ok
test editor::completion::tests::artifact_ref::agent_and_indexed_file_payloads_match_mid_name_fragments ... ok
test editor::completion::tests::artifact_ref::builds_chat_and_indexed_file_payloads_but_not_remote_kinds ... ok
test editor::completion::tests::artifact_ref::commit_age_label_applies_the_utc_offset_before_the_date_falls_back ... ok
test editor::completion::tests::artifact_ref::commit_age_labels_match_prompt_bar_thresholds ... ok
test editor::completion::tests::artifact_ref::builds_dynamic_kind_and_payload_candidates ... ok
test editor::completion::tests::artifact_ref::classifies_artifact_kind_and_payload_at_every_cursor_position ... ok
test editor::completion::tests::artifact_ref::builds_bead_payload_candidates_from_published_pages ... ok
test continuation::retention::tests::over_max_nodes_but_under_retention_cap_protects_live_ancestry ... ok
test editor::completion::tests::artifact_ref::agent_prefix_query_survives_a_corpus_of_fuzzy_matches ... ok
test editor::completion::tests::artifact_ref::commit_inventory_reports_the_merged_row_cap ... ok
test editor::completion::tests::artifact_ref::commit_inventory_is_empty_for_sidecar_only_context ... ok
test continuation::retention::tests::exceeding_retention_cap_fails_with_cap_message ... ok
test editor::completion::tests::artifact_ref::commit_inventory_preserves_subject_and_multiline_body ... ok
test editor::completion::tests::artifact_ref::commit_log_failures_report_the_underlying_os_error ... ok
test editor::completion::tests::artifact_ref::commit_log_distinguishes_every_unusable_repository_outcome ... ok
test editor::completion::tests::artifact_ref::commit_merge_ties_break_by_repository_then_sha ... ok
test editor::completion::tests::artifact_ref::commit_timeout_override_accepts_only_positive_finite_seconds ... ok
test editor::completion::tests::artifact_ref::commit_timeout_reads_the_documented_environment_override ... ok
test editor::completion::tests::artifact_ref::payload_enumeration_is_bounded_and_deduplicated ... ok
test editor::completion::tests::artifact_ref::payload_inventory_applies_document_root_path_globs ... ok
test bead::touch_index::tests::missing_truncated_and_garbage_indexes_are_cache_misses_never_errors ... ok
test editor::completion::tests::artifact_ref::commit_inventory_enforces_the_per_repository_scan_limit ... ok
test editor::completion::tests::assist_candidates::agent_candidates_are_kind_aware_ordered_and_compatible ... ok
test editor::completion::tests::assist_candidates::agent_candidates_carry_documentation_only_when_present ... ok
test editor::completion::tests::assist_candidates::builds_argument_name_completions ... ok
test editor::completion::tests::assist_candidates::builds_catalog_completions_with_marker_filters ... ok
test editor::completion::tests::assist_candidates::builds_snippet_completions_by_case_insensitive_prefix ... ok
test editor::completion::tests::assist_candidates::hold_candidates_prioritize_waiting_targets_and_include_procs ... ok
test editor::completion::tests::assist_candidates::hood_value_candidates_include_explicit_and_derived_hoods ... ok
test editor::completion::tests::assist_candidates::memory_completes_only_through_the_memory_namespace ... ok
test editor::completion::tests::assist_candidates::model_at_suffix_completes_effort_vocabulary ... ok
test editor::completion::tests::assist_candidates::snippet_context_does_not_steal_higher_priority_tokens ... ok
test editor::completion::tests::assist_candidates::wait_candidates_merge_keywords_and_exclude_selected_values ... ok
test editor::completion::tests::assist_candidates::wait_context_narrows_to_active_clause_and_tracks_selected_values ... ok
test bead::mutation::tests::snooze_plus_one::re_snoozing_appends_a_second_note_naming_the_replaced_wake_time ... ok
test editor::completion::tests::directive_candidates::directive_keyword_completion_stays_out_of_positional_and_value_positions ... ok
test bead::mutation::tests::view_commit::view_commit_runner_declines_then_replays_once ... ok
test editor::completion::tests::directive_candidates::directive_keyword_completion_targets_only_the_post_comma_fragment ... ok
test editor::completion::tests::directive_candidates::effort_and_auto_directive_arguments_classify_with_candidates ... ok
test editor::completion::tests::directive_candidates::final_directive_completes_add_and_remove_instance_selectors ... ok
test editor::completion::tests::directive_candidates::final_directive_documents_provider_dependencies_and_retry_policy ... ok
test editor::completion::tests::directive_candidates::final_directive_omits_required_from_remove_and_clear_when_invalid ... ok
test editor::completion::tests::directive_candidates::final_directive_orders_required_default_optional_then_clear ... ok
test editor::completion::tests::directive_candidates::final_directive_replaces_only_the_active_parenthesized_clause ... ok
test editor::completion::tests::trigger_context::closed_placeholder_does_not_steal_following_context ... ok
test editor::completion::tests::directive_candidates::tab_directive_completes_inventory_tabs_plus_main ... ok
test editor::completion::tests::trigger_context::classifies_primary_completion_modes ... ok
test editor::completion::tests::trigger_context::placeholder_context_precedes_other_explicit_completion_modes ... ok
test editor::completion::tests::trigger_context::detects_narrow_argument_contexts ... ok
test editor::completion::tests::trigger_context::repeatable_agent_context_replaces_earlier_element_and_filters_selected ... ok
test editor::completion::tests::trigger_context::repeatable_positionals_keep_the_tail_input_and_active_element_range ... ok
test editor::completion::tests::vcs_candidates::classifies_vcs_project_trigger ... ok
test editor::completion::tests::vcs_candidates::classifies_vcs_repo_then_vcs_ref_before_xprompt_argument_hints ... ok
test editor::completion::tests::vcs_candidates::detects_vcs_ref_colon_spans ... ok
test editor::completion::tests::vcs_candidates::detects_vcs_ref_paren_hitl ... ok
test editor::completion::tests::vcs_candidates::classifies_vcs_repo_then_vcs_ref_then_xprompt_args ... ok
test editor::completion::tests::vcs_candidates::detects_vcs_repo_colon_spans ... ok
test editor::completion::tests::vcs_candidates::detects_vcs_repo_paren_hitl_and_nested_namespaces ... ok
test editor::completion::tests::vcs_candidates::trailing_trigger_emits_primary_plus_additional_edit ... ok
test editor::completion::tests::vcs_candidates::bof_trigger_merges_into_single_primary_edit ... ok
test editor::completion::tests::vcs_candidates::vcs_project_accept_inserts_patch_spelling ... ok
test editor::completion::tests::vcs_candidates::vcs_project_accept_with_catalog_targets_removes_disabled_and_home ... ok
test editor::completion::tests::artifact_ref::payload_inventory_reaches_past_the_editor_display_cap ... ok
test editor::completion::tests::vcs_candidates::vcs_project_accept_switches_projects_at_target_position ... ok
test editor::completion::tests::vcs_candidates::vcs_project_candidates_accept_entry_kind_without_legacy_kind ... ok
test editor::completion::tests::vcs_candidates::vcs_project_accept_uses_v5_tag_and_grammar_fallback ... ok
test editor::completion::tests::vcs_candidates::vcs_project_candidates_accept_legacy_changespec_kind ... ok
test editor::completion::tests::vcs_candidates::vcs_project_candidates_match_aliases ... ok
test editor::completion::tests::vcs_candidates::vcs_project_candidates_filter_for_bare_plus_query ... ok
test editor::completion::tests::vcs_candidates::vcs_project_candidates_include_patch_context ... ok
test editor::completion::tests::vcs_candidates::vcs_ref_accept_preserves_visible_space_before_document_final_newline ... ok
test editor::completion::tests::vcs_candidates::vcs_ref_builder_filters_by_query_and_alias ... ok
test editor::completion::tests::vcs_candidates::vcs_project_candidates_filter_preserves_catalog_order ... ok
test editor::completion::tests::vcs_candidates::vcs_ref_builder_groups_rows_and_replaces_root_ref ... ok
test editor::completion::tests::vcs_candidates::vcs_ref_trigger_negatives ... ok
test editor::completion::tests::vcs_candidates::vcs_ref_golden_vectors ... ok
test editor::completion::tests::vcs_candidates::vcs_repo_builder_replaces_only_the_ref_value ... ok
test editor::completion::tests::vcs_candidates::vcs_repo_golden_vectors ... ok
test editor::completion::tests::vcs_candidates::vcs_repo_trigger_negatives ... ok
test editor::definition::tests::navigates_from_a_memory_reference_to_the_memory_note ... ok
test editor::definition::tests::preserves_catalog_definition_range ... ok
test editor::definition::tests::preserves_symlinked_ancestor_in_definition_path ... ok
test editor::definition::tests::resolves_inline_and_standalone_xprompt_definitions ... ok
test editor::definition::tests::returns_none_for_missing_entries_or_source_targets ... ok
test editor::definition::tests::resolves_namespaced_shorthand_and_slash_skill_definitions ... ok
test editor::definition::tests::validates_local_file_definition_paths_conservatively ... ok
test editor::completion::tests::artifact_ref::commit_inventory_skips_unusable_checkouts_and_bug_stays_empty ... ok
test editor::completion::tests::vcs_candidates::vcs_project_edits_never_overlap ... ok
test editor::diagnostics::tests::accepts_known_frontmatter_input_type_aliases ... ok
test editor::diagnostics::tests::accepts_frontmatter_local_macros ... ok
test editor::diagnostics::tests::accepts_current_document_local_macros_and_validates_args ... ok
test editor::diagnostics::tests::artifact_diagnostics_report_malformed_and_unresolved_known_kinds ... ok
test editor::diagnostics::tests::artifact_diagnostics_report_unresolved_bead_pages ... ok
test editor::diagnostics::tests::accepts_valid_input_aliases_and_defaults ... ok
test editor::diagnostics::tests::accepts_input_descriptions_and_reports_invalid_shapes ... ok
test editor::diagnostics::tests::accepts_valid_argument_forms_and_bool_spellings ... ok
test editor::diagnostics::tests::artifact_diagnostics_shape_check_commit_and_bug_without_resolution ... ok
test editor::diagnostics::tests::artifact_diagnostics_skip_literal_ranges_and_unknown_kinds ... ok
test editor::diagnostics::tests::artifact_diagnostics_resolve_document_chat_and_file_locally ... ok
test editor::diagnostics::tests::canonical_local_section_wins_on_helper_name_conflict ... ok
test editor::diagnostics::tests::closed_alternations_and_literal_zones_have_no_diagnostic ... ok
test editor::diagnostics::tests::incomplete_forms_do_not_emit_required_arg_noise ... ok
test editor::diagnostics::tests::discovers_macros_section_helpers_and_validates_args ... ok
test editor::diagnostics::tests::closed_set_diagnostics_cover_forms_labels_and_repeatable_elements ... ok
test editor::completion::tests::vcs_candidates::vcs_project_golden_vectors ... ok
test editor::diagnostics::tests::invalid_model_argument_warns_with_preferred_replace_fix ... ok
test editor::diagnostics::tests::invalid_auto_spellings_report_invalid_auto_errors ... ok
test editor::diagnostics::tests::model_argument_is_unchecked_without_routing_snapshot ... ok
test editor::diagnostics::tests::old_diagnostic_payloads_deserialize_without_data ... ok
test editor::diagnostics::tests::path_values_allow_spaces_but_reject_line_breaks ... ok
test editor::diagnostics::tests::keywords_do_not_restore_dynamic_memory_matching ... ok
test editor::diagnostics::tests::queue_directive_diagnostics_are_retired ... ok
test editor::diagnostics::tests::local_enum_choices_keep_descriptions_and_suggest_near_misses ... ok
test editor::diagnostics::tests::reports_flow_style_frontmatter_input_type_diagnostic ... ok
test editor::diagnostics::tests::repeatable_tail_accepts_and_validates_every_element ... ok
test editor::diagnostics::tests::reports_flow_style_input_default_on_offending_scalar ... ok
test editor::diagnostics::tests::recognizes_current_directives_but_rejects_removed_spellings ... ok
test editor::diagnostics::tests::reports_frontmatter_yaml_and_shape_diagnostics ... ok
test editor::diagnostics::tests::reports_invalid_input_defaults ... ok
test editor::diagnostics::tests::reports_longform_frontmatter_input_type_diagnostic ... ok
test editor::diagnostics::tests::reports_initial_diagnostics ... ok
test editor::diagnostics::tests::reports_invalid_snippet_tags_keywords_and_skill_metadata ... ok
test editor::diagnostics::tests::reports_input_shape_name_duplicate_identifier_and_unknown_fields ... ok
test editor::diagnostics::tests::reports_unclosed_alternation_with_launch_wording ... ok
test editor::diagnostics::tests::reports_unclosed_paren_alternation_with_alt_wording ... ok
test editor::diagnostics::tests::reports_shortform_frontmatter_input_type_diagnostic ... ok
test editor::diagnostics::tests::typed_launch_diagnostics_are_unconditional ... ok
test editor::directive::tests::alt_metadata_advertises_brace_shorthand ... ok
test editor::diagnostics::tests::reports_unknown_top_level_and_invalid_name ... ok
test editor::directive::tests::auto_metadata_describes_gate_owned_resolution_and_offers_compatibility_suggestions ... ok
test editor::diagnostics::tests::slash_skills_resolve_by_provider_name_not_macro_reference ... ok
test editor::diagnostics::tests::reports_macro_argument_contract_diagnostics ... ok
test editor::diagnostics::tests::unresolvable_values_do_not_report_type_mismatches ... ok
test editor::directive::tests::clan_metadata_matches_the_editor_contract ... ok
test editor::directive::tests::bead_ranking_matches_wait_modal_order_and_filters ... ok
test editor::directive::tests::comma_adjacent_space_keeps_the_wait_list_body ... ok
test editor::directive::tests::cursor_in_prose_past_a_directive_has_no_context ... ok
test editor::directive::tests::directive_completion_t_prefix_completes_tab_only ... ok
test editor::directive::tests::effort_argument_candidates_are_the_canonical_vocabulary ... ok
test editor::directive::tests::effort_is_a_recognized_directive_with_e_alias ... ok
test editor::directive::tests::final_directive_is_public_in_name_completion ... ok
test editor::directive::tests::hidden_macros_enabled_alias_stays_out_of_name_completion ... ok
test editor::directive::tests::id_and_clan_keyword_values_and_conflicts_classify ... ok
test editor::directive::tests::id_metadata_and_completion_match_the_editor_contract ... ok
test editor::directive::tests::contract_covers_the_audited_directive_matrix ... ok
test editor::directive::tests::incomplete_and_malformed_calls_still_classify ... ok
test bead::mutation::tests::snooze_plus_one::plus_one_never_wakes_a_snoozed_bead_that_set_no_target ... ok
test editor::directive::tests::clause_candidates_cover_roles_conflicts_and_self_references ... ok
test editor::directive::tests::keyword_candidates_suppress_selected_and_conflicting_names ... ok
test editor::directive::tests::legacy_family_keyword_stays_in_contract_but_unsuggested ... ok
test editor::directive::tests::macros_enabled_alias_canonicalizes_to_legacy ... ok
test editor::directive::tests::queue_argument_candidates_use_runtime_keywords ... ok
test editor::directive::tests::quoted_wait_value_keeps_its_inner_space ... ok
test editor::directive::tests::quoted_and_text_block_commas_do_not_split_clauses ... ok
test editor::directive::tests::queue_name_completion_documents_capacity_budget ... ok
test editor::directive::tests::removed_auto_approve_aliases_do_not_resolve_or_complete ... ok
test editor::directive::tests::removed_identity_directives_do_not_resolve_or_complete ... ok
test editor::directive::tests::resolves_documented_aliases ... ok
test editor::directive::tests::unclosed_paren_body_stops_at_prose ... ok
test editor::directive::tests::utf16_positions_classify_the_active_wait_clause ... ok
test editor::directive::tests::wait_argument_candidates_use_runtime_keywords ... ok
test editor::directive::tests::wait_bead_value_is_a_keyword_value_clause ... ok
test editor::directive::tests::wait_paren_keywords_are_not_offered_in_colon_form ... ok
test editor::exclusion::tests::alternation_openers_after_literal_brace_start_no_jinja_range ... ok
test editor::exclusion::tests::real_and_unclosed_jinja_tags_still_start_ranges ... ok
test editor::directive::tests::unterminated_wait_colon_body_stops_at_prose ... ok
test editor::frontmatter::authored_inputs_tests::accepts_macros_section_without_unknown_field ... ok
test editor::frontmatter::tests::completes_dict_type_field ... ok
test editor::file::tests::orders_directories_first_and_filters_dotfiles ... ok
test editor::frontmatter::tests::completes_empty_shortform_scalar_type ... ok
test editor::file::tests::preserves_at_prefix_and_marks_symlinked_directories ... ok
test editor::frontmatter::tests::completes_longform_type_field ... ok
test editor::frontmatter::tests::completes_shortform_scalar_type_even_when_yaml_is_incomplete ... ok
test editor::frontmatter::tests::does_not_complete_type_names_in_unrelated_yaml_or_body ... ok
test editor::frontmatter::tests::field_schema_is_ordered_documented_and_parity_scoped ... ok
test editor::frontmatter::tests::hover_documents_log_skill_use_field ... ok
test editor::frontmatter::authored_inputs_tests::duplicate_local_sections_are_an_error_naming_macros ... ok
test editor::frontmatter::tests::frontmatter_input_type_wire_defaults_new_catalog_fields ... ok
test editor::frontmatter::tests::replaces_the_whole_current_type_value ... ok
test editor::frontmatter::tests::input_type_schema_matches_parser_spellings ... ok
test editor::frontmatter::tests::path_defaults_allow_spaces_and_reject_line_breaks ... ok
test editor::frontmatter::tests::unknown_type_suggests_enum_and_string_is_deprecated_warning ... ok
test editor::frontmatter::tests::validate_accepts_bare_body_without_delimiters ... ok
test editor::frontmatter::tests::validate_accepts_log_skill_use_boolean ... ok
test editor::frontmatter::tests::validate_accepts_known_good_block ... ok
test editor::frontmatter::tests::validate_field_handles_block_values ... ok
test editor::frontmatter::tests::validate_field_isolates_a_single_property ... ok
test editor::frontmatter::tests::validate_flags_choices_on_non_enum_type ... ok
test editor::frontmatter::tests::validate_flags_enum_without_choices ... ok
test editor::frontmatter::tests::validate_flags_known_bad_input_type ... ok
test editor::frontmatter::tests::validate_flags_non_boolean_log_skill_use ... ok
test editor::frontmatter::tests::validates_repeatable_input_metadata_and_final_position ... ok
test editor::frontmatter::tests::validate_quotes_yaml_typed_enum_choices_at_each_item ... ok
test editor::fuzzy::tests::basename_retry_beats_a_cross_directory_alignment ... ok
test editor::fuzzy::tests::classifies_all_match_tiers ... ok
test editor::fuzzy::tests::comparator_is_deterministic_under_shuffled_input ... ok
test editor::fuzzy::tests::empty_query_matches_and_missing_subsequence_does_not ... ok
test editor::fuzzy::tests::reports_character_ranges_for_non_ascii_text ... ok
test editor::fuzzy::tests::rewards_separator_and_camel_case_boundaries ... ok
test editor::completion::tests::artifact_ref::commit_inventory_merges_repositories_by_recency_and_assigns_rank ... ok
test editor::fuzzy::tests::tightens_site_to_the_contiguous_segment ... ok
test editor::hover::tests::agent_argument_hover_is_dispatched ... ok
test editor::hover::tests::builds_frontmatter_field_hover ... ok
test editor::frontmatter::tests::validate_flags_duplicate_choice_values ... ok
test editor::hover::tests::argument_hover_lists_choices_source_and_truncates ... ok
test editor::hover::tests::builds_macro_and_argument_hover ... ok
test editor::hover::tests::directive_argument_hover_uses_current_identity_and_clan_metadata ... ok
test editor::hover::tests::frontmatter_hover_ignores_body_and_non_field_positions ... ok
test editor::frontmatter::tests::validate_checks_enum_default_membership ... ok
test editor::hover::tests::hovers_a_macro_memory_with_its_kind_and_tier ... ok
test editor::hover::tests::hovers_a_skill_through_both_of_its_names ... ok
test editor::frontmatter::tests::validate_accepts_enum_choices_shortform_and_longform ... ok
test editor::hover::tests::model_argument_hover_shows_contract_and_route ... ok
test editor::frontmatter::tests::model_default_warns_and_effort_default_errors ... ok
test editor::jinja::assist::tests::block_locals_come_first_with_empty_prefix ... ok
test editor::jinja::assist::tests::closed_raw_block_offers_no_endraw ... ok
test editor::jinja::assist::tests::conditional_sorts_after_available ... ok
test editor::jinja::assist::tests::exact_match_wins ... ok
test editor::jinja::assist::tests::exact_match_beats_better_group ... ok
test editor::jinja::assist::tests::inline_code_opener_returns_none_at_trailing_text ... ok
test editor::jinja::assist::tests::fuzzy_prefix_prefers_match_quality_over_group ... ok
test editor::jinja::assist::tests::fenced_for_block_offers_no_endfor ... ok
test editor::jinja::assist::tests::none_slot_returns_empty_items ... ok
test editor::jinja::assist::tests::outside_tag_returns_none ... ok
test editor::jinja::assist::tests::legacy_alias_sorts_directly_after_canonical ... ok
test editor::jinja::assist::tests::members_cover_wait_and_loop_but_not_unknown ... ok
test editor::jinja::assist::tests::input_shadows_builtin_with_note ... ok
test editor::jinja::assist::tests::filters_order_by_tier ... ok
test editor::jinja::assist::tests::ranks_are_final_indexes_and_shared_extension ... ok
test editor::jinja::assist::tests::repeat_makes_n_available ... ok
test editor::jinja::assist::tests::statements_offer_closers_first ... ok
test editor::jinja::assist::tests::unclosed_raw_block_offers_endraw_first ... ok
test editor::jinja::catalog::tests::every_legacy_alias_points_at_an_existing_name ... ok
test editor::jinja::assist::tests::provider_vars_need_skill_flag ... ok
test editor::jinja::catalog::tests::every_opener_has_a_closer ... ok
test editor::jinja::catalog::tests::every_variable_has_summary_and_documentation ... ok
test editor::jinja::assist::tests::run_names_unavailable_with_inputs ... ok
test editor::jinja::assist::tests::xprompt_scope_offers_positional_and_marks_pattern ... ok
test editor::jinja::context::tests::float_member_reads_as_none ... ok
test editor::jinja::context::tests::for_iterable_position_is_variable ... ok
test editor::jinja::catalog::tests::names_are_unique_within_each_table ... ok
test editor::jinja::context::tests::if_condition_is_variable ... ok
test editor::jinja::context::tests::inert_regions_return_none ... ok
test editor::jinja::context::tests::member_namespace_is_full_dotted_path ... ok
test editor::jinja::context::tests::set_value_position_is_variable ... ok
test editor::jinja::context::tests::variable_prefix_and_range_cover_token ... ok
test editor::jinja::docs::tests::catalog_variable_extracts_example_and_legacy ... ok
test editor::jinja::docs::tests::input_marks_required_and_lists_choices ... ok
test editor::jinja::docs::tests::renders_header_source_summary_example_and_bullets ... ok
test editor::jinja::docs::tests::statement_example_renders_jinja_tags ... ok
test editor::jinja::context::tests::whole_slot_matrix ... ok
test editor::jinja::hover::tests::hovers_a_conditional_with_hint ... ok
test editor::jinja::hover::tests::hovers_a_member_filter_and_test ... ok
test editor::jinja::hover::tests::hovers_a_variable_with_docs ... ok
test editor::jinja::hover::tests::unknown_names_and_outside_tags_hover_none ... ok
test editor::jinja::scan::tests::alternation_openers_are_not_jinja_tags ... ok
test editor::jinja::scan::tests::at_prefixed_expression_tag_completes_as_jinja ... ok
test editor::jinja::scan::tests::closer_inside_string_does_not_end_tag ... ok
test editor::jinja::scan::tests::comment_hides_tag_like_text ... ok
test editor::jinja::scan::tests::cursor_after_closer_is_outside_tag ... ok
test editor::jinja::scan::tests::frontmatter_block_is_inert ... ok
test editor::jinja::scan::tests::fenced_and_inline_code_are_inert ... ok
test editor::jinja::hover::tests::hovers_an_unavailable_builtin_with_reason ... ok
test editor::jinja::scan::tests::multiline_tag_scans ... ok
test editor::jinja::scan::tests::inline_code_opener_does_not_claim_trailing_text ... ok
test editor::jinja::scan::tests::raw_body_is_inert_but_later_tags_complete ... ok
test editor::jinja::scan::tests::statement_tag_without_space_scans ... ok
test editor::jinja::scan::tests::unclosed_expression_tag_still_completes ... ok
test editor::jinja::scan::tests::unclosed_opener_runs_to_next_opener ... ok
test editor::jinja::scan::tests::whitespace_control_delimiters_form_one_tag ... ok
test editor::jinja::scope::tests::closed_raw_block_leaves_no_open_frame ... ok
test editor::jinja::scan::tests::tags_inside_literal_zones_are_not_scanned ... ok
test editor::jinja::scope::tests::fenced_for_block_does_not_leak_locals ... ok
test editor::jinja::scope::tests::for_targets_and_loop_only_inside_body ... ok
test editor::jinja::scope::tests::external_frontmatter_wins_and_dedupes ... ok
test editor::jinja::scope::tests::directive_aliases_and_zones ... ok
test editor::jinja::scope::tests::local_scope_bounds_end_at_block_close ... ok
test editor::jinja::scope::tests::macro_name_params_and_specials ... ok
test editor::jinja::scope::tests::document_scope_combines_everything ... ok
test editor::jinja::scope::tests::set_targets_visible_after_declaration ... ok
test editor::jinja::scope::tests::nested_for_if_stacks_track_open_blocks ... ok
test editor::jinja::scope::tests::frontmatter_input_forms ... ok
test editor::jinja::scope::tests::unclosed_raw_block_stays_open ... ok
test editor::jinja::scope::tests::skill_flag_from_either_source ... ok
test editor::jinja::scope::tests::with_import_and_from_names ... ok
test editor::jinja::scope_vars::tests::scope_variables_include_loop_and_globals ... ok
test editor::jinja::wire::tests::enums_serialize_snake_case ... ok
test editor::macro_arg_choices::tests::assist_and_structured_copy_metadata ... ok
test editor::jinja::scope_vars::tests::prompt_with_inputs_lists_run_names_as_unavailable ... ok
test editor::jinja::scope_vars::tests::shadowed_builtin_is_known_not_unavailable ... ok
test editor::macro_arg_choices::tests::legacy_hints_without_new_fields_deserialize ... ok
test editor::macro_args::tests::double_colon_at_end_of_line_binds_next_line_payload ... ok
test editor::macro_args::tests::parses_colon_plus_hitl_and_namespaced_forms ... ok
test editor::macro_arg_choices::tests::type_label_boundaries ... ok
test editor::macro_args::tests::finds_macro_argument_open_paren_for_matching_close ... ok
test editor::macro_args::tests::parses_parenthesized_named_and_positional_args ... ok
test editor::macro_args::tests::parses_open_parenthesized_available_body ... ok
test editor::macro_args::tests::preserves_commas_and_equals_inside_quotes_and_text_blocks ... ok
test editor::macro_args::tests::preserves_empty_elements_for_contract_validation ... ok
test editor::macro_args::tests::plus_decodes_only_on_bare_colon_arguments ... ok
test editor::macro_args::tests::text_block_closes_at_terminator_not_first_marker ... ok
test editor::macro_args::tests::text_block_compatibility_shapes_keep_parsing ... ok
test editor::macro_args::tests::research_swarm_inner_marker_stays_one_argument ... ok
test editor::macro_args::tests::shared_corpus_matches_python_parse_args ... ok
test editor::model_alias_shortcut::tests::accepts_safe_model_punctuation_and_nested_provider_values ... ok
test editor::jinja::assist::tests::empty_prefix_orders_inputs_before_sase_before_jinja ... ok
test editor::model_alias_shortcut::tests::detects_model_shortcut_context_without_alias_wrapper_fallback ... ok
test editor::model_alias_shortcut::tests::detects_start_space_and_logical_line_boundaries ... ok
test editor::model_alias_shortcut::tests::branch_tags_and_outside_text_survive_model_accept ... ok
test editor::model_alias_shortcut::tests::filter_explicit_model_shortcut_entries_keeps_models_only ... ok
test editor::model_alias_shortcut::tests::destination_spacing_mirrors_token_expansion_policy ... ok
test editor::model_alias_shortcut::tests::filter_model_alias_shortcut_entries_restricts_to_alias_kinds_in_catalog_order ... ok
test editor::model_alias_shortcut::tests::ignores_legacy_star_shortcut_tokens ... ok
test editor::model_alias_shortcut::tests::directives_in_other_segments_are_not_targets ... ok
test editor::model_alias_shortcut::tests::jinja_open_after_percent_is_an_alternation_not_a_zone ... ok
test editor::model_alias_shortcut::tests::plans_full_token_replacement_from_mid_token_caret ... ok
test editor::model_alias_shortcut::tests::plans_explicit_model_replacement_and_validates_selection ... ok
test editor::model_alias_shortcut::tests::planned_caret_always_equals_end_of_applied_edit ... ok
test editor::model_alias_shortcut::tests::adjacent_cleanup_keeps_protected_branch_targets ... ok
test editor::model_alias_shortcut::tests::rejects_embedded_escaped_tabs_and_completed_equals_pairs ... ok
test editor::macro_arg_choices::tests::golden_detection_builder_and_applied_edits ... ok
test editor::model_alias_shortcut::tests::rejects_literal_model_equals_tokens ... ok
test editor::model_alias_shortcut::tests::preserves_or_adds_whitespace_after_expansion ... ok
test editor::model_alias_shortcut::tests::rejects_literal_regions_and_frontmatter ... ok
test editor::model_alias_shortcut::tests::rejects_unsafe_shortcut_values_before_emitting_model_directive ... ok
test editor::model_alias_shortcut::tests::removes_further_directives_leaving_one ... ok
test editor::model_alias_shortcut::tests::alternation_branches_are_never_targets ... ok
test editor::model_alias_shortcut::tests::literal_zones_are_never_targets ... ok
test editor::model_alias_shortcut::tests::removes_adjacent_trailing_directives_before_newline ... ok
test editor::model_alias_shortcut::tests::removes_adjacent_trailing_directives_at_end_of_line ... ok
test editor::model_alias_shortcut::tests::replaces_earliest_directive_before_and_after_trigger ... ok
test editor::model_alias_shortcut::tests::trigger_token_overlapping_a_body_keeps_body_text ... ok
test editor::model_alias_shortcut::tests::removes_trailing_directives_on_their_own_lines ... ok
test editor::model_alias_shortcut::tests::unicode_offsets_use_utf16_for_destination_and_caret ... ok
test editor::model_alias_shortcut::tests::utf16_positions_survive_unicode_and_crlf ... ok
test editor::placeholder::tests::an_empty_common_slice_leaves_document_only_output_unchanged ... ok
test editor::model_alias_shortcut::tests::validates_selected_alias_against_current_filtered_aliases ... ok
test editor::placeholder::tests::appends_common_candidates_after_prompt_candidates_in_caller_order ... ok
test editor::model_alias_shortcut::tests::replaces_explicit_model_and_paren_forms_at_their_position ... ok
test editor::placeholder::tests::builds_deduplicated_document_order_candidates ... ok
test editor::model_alias_shortcut::tests::trigger_inside_alternation_stays_local ... ok
test editor::placeholder::tests::candidates_serialize_with_a_lowercase_source_tag ... ok
test editor::placeholder::tests::completion_edits_leave_the_cursor_after_a_closing_bracket ... ok
test editor::placeholder::tests::completion_candidates_rank_literal_spans_after_live_spans ... ok
test editor::placeholder::tests::completion_list_details_reflect_the_candidate_source ... ok
test editor::placeholder::tests::detects_context_with_and_without_a_closing_bracket ... ok
test editor::placeholder::tests::dedups_common_candidates_against_the_prompt_and_each_other ... ok
test editor::placeholder::tests::excludes_the_span_under_the_cursor ... ok
test editor::placeholder::tests::extracts_strict_single_line_spans_including_code ... ok
test editor::placeholder::tests::filters_common_candidates_with_the_same_prefix_rule ... ok
test editor::placeholder::tests::filters_prefix_case_insensitively_and_handles_utf16_ranges ... ok
test editor::placeholder::tests::rejects_context_after_an_intervening_closing_bracket ... ok
test editor::placeholder::tests::live_candidate_dedups_literal_and_common_occurrences_at_live_position ... ok
test editor::placeholder::tests::slugs_unicode_names_and_resolves_collisions_in_input_order ... ok
test editor::placeholder::tests::substitutes_only_mapped_raw_spans_without_rescanning_values ... ok
test editor::token::tests::detects_vcs_project_trigger_tokens ... ok
test editor::placeholder::tests::summarizes_exact_raw_fields_with_bounded_context ... ok
test editor::token::tests::extracts_mid_token_ranges ... ok
test editor::token::tests::extracts_expected_tokens ... ok
test editor::token::tests::maps_lsp_utf16_positions_defensively ... ok
test editor::token::tests::recognizes_canonical_and_legacy_memory_markdown_source_paths ... ok
test editor::token::tests::recognizes_prompt_widget_snippet_trigger_tokens ... ok
test editor::token::tests::vcs_project_trigger_uses_tag_left_boundaries ... ok
test editor::wire::tests::macro_argument_source_pins_canonical_output ... ok
test editor::wire::tests::completion_context_macro_variants_pin_canonical_output ... ok
test editor::wire::tests::old_target_wire_without_state_fields_defaults_to_none ... ok
test editor::wire::tests::v1_catalog_wire_still_loads_with_v5_defaults ... ok
test effort::tests::invalid_candidates_are_skipped ... ok
test effort::tests::resolves_effective_effort_precedence_and_source ... ok
test effort::tests::splits_trailing_known_effort ... ok
test editor::wire::tests::v5_catalog_wire_round_trips ... ok
test effort::tests::validates_canonical_vocabulary ... ok
test effort::tests::leaves_unknown_or_internal_at_intact ... ok
test external_pr::classify::tests::blank_marker_is_ambiguous ... ok
test external_pr::classify::tests::maps_statuses_and_archive_destination ... ok
test effort_override::tests::invalid_inputs_are_rejected ... ok
test effort_override::tests::malformed_stale_and_missing_field_state_self_cleans ... ok
test external_pr::classify::tests::owned_url_skips_and_preserves_origin ... ok
test external_pr::classify::tests::marker_orphan_adopts_marker_name ... ok
test external_pr::classify::tests::refresh_fires_for_closed_unmerged_pr ... ok
test external_pr::classify::tests::marker_repairs_reserved_stub ... ok
test external_pr::classify::tests::refresh_fires_for_merged_pr_and_moves_to_archive ... ok
test external_pr::classify::tests::refresh_fires_when_open_external_patch_status_drifts ... ok
test external_pr::classify::tests::sase_owned_patch_never_refreshes_despite_status_drift ... ok
test external_pr::classify::tests::unchanged_external_patch_skips ... ok
test external_pr::classify::tests::unknown_origin_patch_never_refreshes_despite_status_drift ... ok
test external_pr::classify::tests::unmarked_pr_adopts_external_with_slug ... ok
test external_pr::url::tests::canonicalizes_github_url_variants ... ok
test external_pr::url::tests::canonicalizes_gitlab_merge_request_urls ... ok
test external_pr::url::tests::rejects_unparseable_urls ... ok
test effort_override::tests::clear_is_idempotent ... ok
test effort_override::tests::exact_and_no_expiry_records_obey_boundary_expiry ... ok
test editor::completion::tests::artifact_ref::commit_inventory_keeps_non_sidecar_repository_kinds ... ok
test feature_flag_state::tests::competing_reconciliations_remove_a_stale_key_once ... ok
test feature_flag_state::tests::invalid_utf8_and_size_limit_are_non_destructive ... ok
test feature_flag_state::tests::failed_atomic_write_cleans_temp_and_leaves_destination ... ok
test feature_flag_state::tests::malformed_wrong_version_type_and_key_are_non_destructive ... ok
test feature_flag_state::tests::missing_state_is_an_empty_snapshot ... ok
test feature_flag_state::tests::both_booleans_round_trip_in_stable_order ... ok
test feature_flag_state::tests::failed_set_leaves_previous_state_and_no_temp_litter ... ok
test feature_flag_state::tests::lock_timeout_names_the_holder ... ok
test feature_flag_state::tests::concurrent_reconcile_and_registered_set_do_not_lose_updates ... ok
test feature_flag_state::tests::reconcile_rejects_invalid_registered_keys_before_touching_state ... ok
test feature_flag_state::tests::reconcile_missing_and_clean_state_are_idempotent ... ok
test bead::mutation::tests::snooze_plus_one::task_plus_one_is_atomic_normalized_and_promotes_closed_task ... ok
test feature_flag_state::tests::set_rejects_invalid_keys_without_creating_state ... ok
test feature_flag_state::tests::reconcile_unusable_files_are_non_destructive ... ok
test feature_flag_state::tests::reconcile_empty_registry_removes_every_valid_entry ... ok
test fenced_code::tests::boxed_displayed_inner_fence_is_one_block ... ok
test fenced_code::tests::crlf_opening_and_closing_fences_scan ... ok
test fenced_code::tests::digest_normalizes_crlf ... ok
test feature_flag_state::tests::concurrent_writers_preserve_distinct_keys ... ok
test fenced_code::tests::if_inside_ordinary_fence_is_not_owned ... ok
test fenced_code::tests::owned_if_fence_is_opaque_and_captures_code_value ... ok
test fenced_code::tests::python_info_string_and_empty_source_and_unclosed ... ok
test fenced_code::tests::tilde_and_indented_info_string_offsets_match_python ... ok
test fenced_code::tests::unclosed_fence_runs_to_eof ... ok
test fenced_code::tests::unlabelled_fence_is_bash ... ok
test fenced_code::tests::unknown_language_and_missing_fence_are_diagnostics ... ok
test file_history::blobs::tests::lru_serves_hits_and_evicts_oldest ... ok
test file_history::blobs::tests::zero_capacity_stores_nothing ... ok
test file_history::lineage::tests::delete_and_recreate_resumes_with_gap ... ok
test file_history::lineage::tests::delete_without_history_is_ignored ... ok
test file_history::lineage::tests::modify_first_is_incomplete ... ok
test file_history::lineage::tests::incremental_fold_matches_full_rebuild ... ok
test file_history::lineage::tests::rename_chain_keeps_one_lineage_with_aliases ... ok
test file_history::lineage::tests::rename_from_unknown_starts_moved_lineage ... ok
test file_history::parse::tests::empty_stream_returns_empty ... ok
test file_history::parse::tests::added_commit_parses_modes_and_zero_pre_image ... ok
test file_history::parse::tests::malformed_entry_stops_entries_not_commits ... ok
test file_history::parse::tests::record_with_bad_timestamp_is_dropped ... ok
test file_history::parse::tests::multiple_commits_stay_newest_first ... ok
test file_history::parse::tests::rename_reports_both_paths_and_score ... ok
test file_history::parse::tests::trailing_partial_record_is_dropped ... ok
test file_history::parse::tests::unicode_and_spaced_paths_survive ... ok
Initialized empty Git repository in /home/bryan/.cache/sase/tmp/agent-tmp/gh_sase-org__sase-ws14-261024_085653/.tmpHoREFR/repo/.git/
Initialized empty Git repository in /home/bryan/.cache/sase/tmp/agent-tmp/gh_sase-org__sase-ws14-261024_085653/.tmpplCquT/repo/.git/
test feature_flag_state::tests::reconcile_lock_timeout_and_write_failure_report_failed_outcomes ... ok
Initialized empty Git repository in /home/bryan/.cache/sase/tmp/agent-tmp/gh_sase-org__sase-ws14-261024_085653/.tmppQvaxq/repo/.git/
test file_history::runner::tests::batch_stdin_larger_than_the_pipe_buffer_does_not_deadlock ... ok
Initialized empty Git repository in /home/bryan/.cache/sase/tmp/agent-tmp/gh_sase-org__sase-ws14-261024_085653/.tmppliJv9/repo/.git/
test file_history::runner::tests::batch_stdin_and_stdout_both_exceed_pipe_capacity ... ok
Initialized empty Git repository in /home/bryan/.cache/sase/tmp/agent-tmp/gh_sase-org__sase-ws14-261024_085653/.tmpPWCHiP/repo/.git/
test feature_flag_state::tests::successful_write_leaves_no_temp_litter ... ok
test feature_flag_state::tests::same_value_set_is_idempotent_and_skips_rewrite ... ok
test feature_flag_state::tests::reconcile_removes_unknown_valid_keys_only ... ok
test file_history::runner::tests::full_sha_shape_is_exact ... ok
test file_history::runner::tests::git_commands_pin_signature_output_off ... ok
test file_history::runner::tests::batch_stdin_success_hashes_payload ... ok
test file_history::runner::tests::pathspecs_reject_escapes_and_magic ... ok
test file_history::runner::tests::batch_stdin_reports_nonzero_git_exit ... ok
test file_history::runner::tests::revision_tokens_reject_options_and_ranges ... ok
test file_history::runner::tests::routing_env_vars_are_removed_and_lock_vars_are_set ... ok
test file_history::runner::tests::zero_oid_is_absent ... ok
test file_history::status::tests::blob_hash_matches_git_hash_object ... ok
Initialized empty Git repository in /home/bryan/.cache/sase/tmp/agent-tmp/gh_sase-org__sase-ws14-261024_085653/.tmpT7uu5j/repo/.git/
Initialized empty Git repository in /home/bryan/.cache/sase/tmp/agent-tmp/gh_sase-org__sase-ws14-261024_085653/.tmpKuezvY/repo/.git/
Initialized empty Git repository in /home/bryan/.cache/sase/tmp/agent-tmp/gh_sase-org__sase-ws14-261024_085653/.tmpd0kiWn/repo/.git/
test effort_override::tests::every_canonical_level_round_trips_and_replaces ... ok
test file_history::runner::tests::batch_stdin_truncation_is_visible_on_zero_exit ... ok
test file_history::runner::tests::early_exit_broken_pipe_is_not_a_write_failure ... ok
test file_history::runner::tests::injected_routing_env_does_not_reroute_git ... ok
[master (root-commit) fafa7e6] big
 1 file changed, 1 insertion(+)
 create mode 100644 big.txt
test effort_override::tests::lock_wait_is_bounded ... ok
test bead::mutation::tests::snooze_plus_one::task_plus_one_fresh_observation_window_reopens_closed_task_and_clears_assignee ... ok
test file_history::runner::tests::output_larger_than_the_pipe_buffer_does_not_deadlock ... ok
test editor::completion::tests::artifact_ref::commit_log_reports_an_expired_budget_instead_of_empty_output ... ok
test feature_flag_state::tests::unknown_valid_keys_are_preserved_across_writes ... ok
test file_history::tests::rejects_bad_pathspecs_and_non_repo ... ok
test file_history::tests::blob_batch_reads_contents_caches_hits_and_missing ... ok
test file_history::tests::delete_and_recreate_continues_lineage_with_gap ... ok
test file_history::tests::lineage_agrees_with_git_follow ... ok
test file_history::tests::blob_oids_match_rev_parse_for_every_version ... ok
test editor::completion::tests::artifact_ref::payload_inventory_discloses_the_scan_bound ... ok
test finalizer::digest::tests::canonical_digest_sorts_nested_object_keys ... ok
test finalizer::outcome::tests::aggregate_failure_precedence_is_stable ... ok
test finalizer::outcome::tests::all_skipped_aggregates_success_and_all_failed_aggregates_failed ... ok
test finalizer::outcome::tests::attempt_numbers_must_be_unique_increasing_and_terminal ... ok
test finalizer::outcome::tests::deferral_payload_requires_deferred_status ... ok
test finalizer::outcome::tests::deferred_aggregate_is_a_warning_not_a_failure ... ok
test finalizer::outcome::tests::deferred_ranks_below_pending_and_refused_but_above_success ... ok
test finalizer::outcome::tests::deferred_status_requires_deferral_payload ... ok
test finalizer::outcome::tests::refused_status_requires_reason ... ok
test finalizer::outcome::tests::serde_rejects_unknown_statuses ... ok
test finalizer::remaining::tests::empty_remaining_when_everything_completed ... ok
test finalizer::remaining::tests::host_order_is_the_current_obligation_order ... ok
test finalizer::remaining::tests::preserves_completed_obligations_omitted_from_current ... ok
test finalizer::remaining::tests::rejects_identity_mismatch ... ok
test finalizer::remaining::tests::rejects_incomplete_executed_obligation_omitted_from_current ... ok
test finalizer::remaining::tests::rejects_missing_and_mismatched_host_identity ... ok
test finalizer::remaining::tests::rejects_missing_decision_and_stale_digest ... ok
test finalizer::remaining::tests::selects_new_and_queued_remaining_in_host_order ... ok
test finalizer::remaining::tests::skips_completed_obligations_still_listed_in_current ... ok
test finalizer::run_view::decode::tests::context_decode_failure_means_unknown_triggers ... ok
test finalizer::run_view::decode::tests::oversized_inputs_report_their_raw_path ... ok
test finalizer::run_view::decode::tests::tolerant_jsonl_skips_blank_malformed_and_new_versions ... ok
test finalizer::run_view::detail::tests::empty_request_is_rejected ... ok
test finalizer::run_view::detail::tests::wrong_schema_version_is_rejected ... ok
test finalizer::run_view::evidence::tests::ambiguous_commit_result_stays_text ... ok
test finalizer::run_view::precedence::tests::blocked_rule_pins_first_terminal_blocker ... ok
test finalizer::run_view::selection::tests::empty_plan_selects_nothing ... ok
test finalizer::run_view::selection::tests::replay_explains_required_and_selector_adds ... ok
test finalizer::run_view::tests::authority_drift_makes_the_run_unavailable ... ok
test finalizer::run_view::tests::cleared_plan_reports_final_none ... ok
test finalizer::run_view::tests::config_values_never_reach_the_serialized_response ... ok
test finalizer::run_view::tests::drift_entries_surface_and_raise_trouble ... ok
test finalizer::run_view::tests::failed_check_blocks_tasks_downstream ... ok
test finalizer::run_view::tests::handoff_skip_is_skipped_with_its_kind ... ok
test finalizer::run_view::tests::legacy_meta_hints_never_change_the_disposition ... ok
test finalizer::run_view::tests::non_default_instance_reports_not_default ... ok
test finalizer::run_view::tests::open_journal_with_a_dead_runner_is_interrupted ... ok
test file_history::tests::rename_across_directories_builds_one_lineage ... ok
test file_history::tests::first_parent_walk_ignores_side_branch_commits ... ok
test finalizer::run_view::tests::planned_run_on_a_live_turn_is_active ... ok
test finalizer::run_view::tests::oversized_result_names_its_raw_path ... ok
test finalizer::run_view::tests::recovery_files_surface_the_recovery_turn_and_trouble ... ok
test finalizer::run_view::tests::sealed_plan_without_artifacts_on_a_terminal_turn_is_not_reached ... ok
test finalizer::run_view::tests::terminal_result_is_authoritative_for_outcomes ... ok
test finalizer::run_view::tests::truncated_open_journal_is_interrupted ... ok
test finalizer::run_view::tests::two_cycle_reactivation_counts_earlier_segments ... ok
test finalizer::run_view::tests_detail::collapse_cr_tail_keeps_the_last_segment_of_each_line ... ok
test finalizer::run_view::tests::unselected_lint_reports_its_selector_reason ... ok
test finalizer::run_view::tests::zero_attempts_with_no_trigger_is_not_triggered ... ok
test finalizer::run_view::tests_detail::commit_deferral_reports_typed_reason_and_paths ... ok
test finalizer::run_view::tests_detail::failure_reason_falls_back_to_the_stderr_tail ... ok
test finalizer::run_view::tests_detail::command_failure_reports_attempts_journal_ops_and_reason ... ok
test finalizer::run_view::tests_detail::commit_stitch_reports_legacy_record_steps_and_headline ... ok
test finalizer::run_view::tests_detail::plugin_fixture_renders_with_no_plugin_specific_fields ... ok
test finalizer::run_view::tests_detail::success_then_failure_pins_the_later_failure ... ok
test finalizer::run_view::tests_detail::superseded_attempt_errors_never_paint_red ... ok
test finalizer::selection::tests::authenticate_finalizer_plan_rejects_independent_expected_digest ... ok
test finalizer::selection::tests::cycles_and_missing_dependencies_are_diagnostics ... ok
test finalizer::selection::tests::required_instances_are_selected_and_cannot_be_removed ... ok
test finalizer::selection::tests::selector_replay_handles_add_remove_and_clear ... ok
test finalizer::run_view::tests_detail::three_run_session_supersedes_to_the_final_success ... ok
test finalizer::selection::tests::stable_topological_order_preserves_selector_order_among_ready_nodes ... ok
test finalizer::selection::tests::validate_finalizer_plan_rejects_duplicate_or_shifted_indices ... ok
test finalizer::selection::tests::validate_finalizer_plan_accepts_resolved_plans ... ok
test finalizer::selection::tests::validate_finalizer_plan_rejects_mutated_entries_without_new_digest ... ok
test finalizer::selection::tests::validates_slug_and_size_limits ... ok
test finalizer::submission::tests::assigned_bead_changes_context_digest_and_preserves_unassociated_digest ... ok
test finalizer::selection::tests::validate_finalizer_plan_rejects_forged_or_omitted_digest ... ok
test finalizer::submission::tests::deferral_paths_must_be_nonempty_and_bounded ... ok
test finalizer::submission::tests::assigned_bead_requires_a_nonblank_bead_id ... ok
test finalizer::submission::tests::rejects_missing_duplicate_and_unexpected_payloads ... ok
test finalizer::submission::tests::rejects_stale_identity_fields ... ok
test finalizer::wire::tests::assigned_bead_is_omitted_from_canonical_json_when_absent ... ok
test finalizer::submission::tests::validates_complete_submission_and_digest_identity ... ok
test finalizer::wire::tests::assigned_bead_round_trips_and_omits_unidentified_primary ... ok
test finalizer::wire::tests::defer_refusal_policy_round_trips_through_serde ... ok
test finalizer::wire::tests::fail_stays_the_serde_default_refusal_policy ... ok
test finalizer::wire::tests::unknown_deferral_reason_is_rejected ... ok
test fleet_agent_session::tests::agent_session_id_alone_does_not_make_a_root_a_turn ... ok
test fleet_agent_session::tests::name_suffix_classifies_code_and_monitor_turns ... ok
test fleet_agent_session::tests::parent_timestamp_classifies_an_otherwise_plain_member ... ok
test fleet_agent_session::tests::plan_without_parent_timestamp_is_a_turn_not_a_root ... ok
test fleet_agent_session::tests::turn_object_monitor_and_proc_kinds_classify ... ok
test fleet_attention::tests::fingerprint_is_stable_and_sensitive_to_changes ... ok
test fleet_attention::tests::inventory_pages_pending_entries_and_filters_settled_entries ... ok
test fleet_attention::tests::inventory_returns_pending_uncorrelated_requests_without_catalog_rows ... ok
test fleet_attention::tests::inventory_revision_is_stable_across_reconnect ... ok
test fleet_attention::tests::inventory_succeeds_beyond_row_cap_with_mostly_non_actionable_rows ... ok
test fleet_attention::tests::inventory_validation_rejects_unbounded_limits_and_bad_cursor ... ok
test fleet_attention::tests::non_actionable_notifications_are_skipped ... ok
test fleet_attention::tests::notice_dedupe_suppresses_reconnect_and_announces_new_revision ... ok
test fleet_attention::tests::notice_ledger_prunes_stale_entries_outside_retention_window ... ok
test fleet_attention::tests::path_like_option_id_is_rejected ... ok
test fleet_attention::tests::precondition_allows_matching_pending_entry ... ok
test file_history::tests::path_status_reports_tracked_untracked_ignored ... ok
test fleet_attention::tests::precondition_already_settled_reports_settling_host ... ok
test fleet_attention::tests::precondition_capability_missing ... ok
test fleet_attention::tests::precondition_invalid_option ... ok
test fleet_attention::tests::precondition_stale_revision ... ok
test fleet_attention::tests::precondition_unknown_request_when_missing ... ok
test fleet_attention::tests::precondition_requires_tty_option_is_capability_missing ... ok
test fleet_attention::tests::projection_correlates_gate_by_origin_agent ... ok
test fleet_attention::tests::projection_carries_sudo_requires_tty_and_hashes_revision ... ok
test fleet_attention::tests::projection_correlates_question_by_sender ... ok
test fleet_attention::tests::projection_is_deterministic_and_sorted ... ok
test fleet_attention::tests::projection_still_rejects_rows_beyond_cap ... ok
test fleet_attention::tests::replay_accepts_unseen_key ... ok
test fleet_attention::tests::replay_conflicts_on_changed_payload ... ok
test fleet_attention::tests::replay_rejects_expired_or_tombstoned_key ... ok
test fleet_attention::tests::replay_returns_original_receipt_for_same_payload ... ok
test fleet_attention::tests::secretish_title_is_rejected ... ok
test fleet_attention::tests::uncorrelated_request_is_still_returned ... ok
test fleet_catalog::tests::agent_tab_inherits_from_root_for_members ... ok
test fleet_contract::locators::tests::canonical_logical_key_folds_legacy_segment_and_fallback_id ... ok
test fleet_contract::locators::tests::fallback_ids_compare_equal_across_spellings ... ok
test fleet_contract::locators::tests::instance_key_matches_accepts_shell_segment_and_fallback ... ok
test fleet_catalog::tests::stable_revision_changes_when_agent_tab_changes ... ok
test fleet_contract::locators::tests::locator_accepts_legacy_spelling_but_emits_canonical ... ok
test fleet_contract::locators::tests::instance_locator_accepts_shell_spelling_but_emits_turn ... ok
test fleet_attention::tests::inventory_pages_large_pending_set_beyond_row_cap ... ok
test fleet_contract::locators::tests::logical_key_matches_accepts_both_segments ... ok
test fleet_contract::status::tests::row_kinds_accept_legacy_spelling_but_emit_canonical ... ok
test fleet_contract::status::tests::session_roles_accept_legacy_spelling_but_emit_canonical ... ok
test fleet_contract::tests::catalog::catalog_query_is_bounded_and_pages_deterministically ... ok
test fleet_contract::tests::catalog::catalog_accumulation_uses_generations_and_snapshot_equality ... ok
test fleet_contract::tests::catalog::catalog_cursor_scope_or_snapshot_mismatch_returns_restart_page ... ok
test fleet_contract::tests::connection::connection_plan_validation_rejects_insecure_or_secret_bearing_data ... ok
test fleet_contract::tests::connection::time_helpers_keep_owner_runtime_and_viewer_freshness_separate ... ok
test fleet_contract::tests::cursors::cursor_replay_classifies_resync_boundaries ... ok
test fleet_contract::tests::cursors::invalidations_validate_cursor_and_revision_identity ... ok
test fleet_contract::tests::catalog::catalog_settled_dispatch_row_needs_terminal_flag_not_identity ... ok
test fleet_contract::tests::federation::federation_catalog_accepts_readable_capability_schema_versions ... ok
test fleet_contract::tests::catalog::catalog_snapshot_identity_is_scope_and_stable_content_scoped ... ok
test fleet_contract::tests::federation::federation_catalog_normalization_preserves_authoritative_counts_freshness_and_cursors ... ok
test finalizer::run_view::tests_detail::oversized_steps_flag_truncation_and_keep_parsing ... ok
test fleet_contract::tests::federation::federation_followed_batch_counts_only_resolved_requested_entries ... ok
test fleet_contract::tests::federation::federation_malformed_external_catalog_cursor_rejects_host_wire ... ok
test fleet_contract::tests::federation::federation_typed_catalog_resync_preserves_healthy_hosts ... ok
test fleet_contract::tests::follows::follow_reconciliation_promotes_singleton_to_agent_session_identity ... ok
test fleet_contract::tests::follows::focus_and_fleet_counts_stay_separate_and_propagate_unknown_hosts ... ok
test fleet_contract::tests::follows::follow_tombstones_suppress_dispatch_recreation_and_activation ... ok
test fleet_contract::tests::federation::federation_malformed_host_degrades_without_losing_healthy_hosts ... ok
test fleet_contract::tests::federation::federation_catalog_rejects_unnormalized_readable_capability_content ... ok
test fleet_contract::tests::identity::malformed_oversized_and_future_identity_files_are_left_unchanged ... ok
test fleet_contract::tests::launch::fleet_launch_intent_and_replay_are_portable_and_target_pinned ... ok
test fleet_contract::tests::locators::locator_keys_are_stable_and_names_do_not_become_identity ... ok
test fleet_contract::tests::operations::operation_fingerprint_and_replay_decisions_are_scoped ... ok
test fleet_contract::tests::projection::agent_session_role_distinguishes_root_member_and_historical_turn ... ok
test fleet_contract::tests::projection::contract_v6_rows_decode_without_agent_tab_and_v7_rows_round_trip ... ok
test fleet_contract::tests::projection::dead_or_not_process_liveness_never_counts_as_running ... ok
test fleet_contract::tests::projection::external_wire_summary_with_raw_control_character_intent_is_rejected ... ok
test fleet_contract::tests::projection::newer_than_known_contract_rows_are_rejected ... ok
test fleet_contract::tests::projection::projection_accepts_explicit_zero_queue_weight_but_rejects_implicit_zero ... ok
test fleet_contract::tests::projection::projection_applies_owner_resolved_lineage_and_normalizes_locator_schemas ... ok
test fleet_contract::tests::projection::projection_bounds_multiline_unicode_intent_to_byte_limit ... ok
test file_history::tests::snapshot_round_trip_persist_and_load ... ok
test fleet_contract::tests::projection::projection_carries_agent_tab_from_owner_facts ... ok
test fleet_contract::tests::projection::projection_carries_canonical_queue_capacity_from_metadata ... ok
test fleet_contract::tests::projection::projection_carries_owner_presentation_facts_for_remote_rendering ... ok
test fleet_contract::tests::projection::projection_normalizes_control_characters_in_multiline_raw_prompt_intent ... ok
test fleet_contract::tests::projection::projection_leaves_absent_queue_capacity_quiet_and_reads_schema_two ... ok
test fleet_contract::tests::projection::projection_normalizes_control_characters_in_plan_action_intent ... ok
test fleet_contract::tests::projection::projection_omits_intent_when_normalization_leaves_it_empty ... ok
test fleet_contract::tests::projection::projection_prefers_waiting_queue_capacity_over_metadata ... ok
test fleet_contract::tests::projection::projection_prefers_waiting_queue_weight_over_metadata ... ok
test fleet_contract::tests::projection::projection_preserves_multiplier_with_waiting_precedence ... ok
test fleet_contract::tests::projection::projection_outputs_safe_summary_and_detail_without_local_fields ... ok
test fleet_contract::tests::projection::projection_reads_legacy_queue_capacity_without_emitting_legacy_alias ... ok
test fleet_contract::tests::projection::projection_rejects_inconsistent_owner_facts_and_handles ... ok
test fleet_contract::tests::projection::v4_shaped_summary_deserializes_at_v5_and_carries_owner_facts ... ok
test fleet_contract::tests::projection::summary_accepts_readable_capability_schema_versions_but_rejects_unnormalized_content ... ok
test fleet_contract::tests::reads::batch_lookup_preserves_requested_order_and_bounds_ids ... ok
test fleet_contract::tests::reads::content_and_project_read_requests_are_bounded ... ok
test fleet_contract::tests::reads::count_rejects_equal_revision_competing_current_instances ... ok
test fleet_follow_promotion::tests::duplicate_same_agent_session_observations_are_not_ambiguous ... ok
test fleet_follow_promotion::tests::empty_observations_or_records_yield_no_promotions ... ok
test fleet_contract::tests::reads::count_contract_is_order_independent_and_deduplicates_current_instances ... ok
test fleet_follow_promotion::tests::promotes_explicit_singleton_when_exactly_one_agent_session_matches ... ok
test fleet_follow_promotion::tests::non_tui_consumer_promotions_are_accepted_by_follow_reconciliation ... ok
test fleet_follow_promotion::tests::rejects_malformed_records_and_observations ... ok
test fleet_follow_promotion::tests::rejects_unsupported_schema_version ... ok
test fleet_follow_promotion::tests::requires_same_origin_project_and_agent ... ok
test fleet_follow_promotion::tests::skips_agent_session_records_and_dispatch_records ... ok
test fleet_follow_promotion::tests::skips_pending_explicit_singletons ... ok
test fleet_follow_promotion::tests::skips_redundant_source_and_ignores_singleton_observations ... ok
test fleet_follow_promotion::tests::skips_when_observations_match_multiple_agent_sessions ... ok
test fleet_follow_promotion::tests::unfollow_tombstones_win_when_derived_promotions_are_reconciled ... ok
test fleet_mutation::tests::bulk_partition_groups_by_origin_deterministically ... ok
test fleet_mutation::tests::fork_without_prompt_is_rejected ... ok
test fleet_mutation::tests::mutation_fingerprint_changes_when_intent_changes ... ok
test fleet_mutation::tests::mutation_fingerprint_is_stable_for_identical_intents ... ok
test fleet_mutation::tests::path_like_reason_is_rejected ... ok
test fleet_mutation::tests::precondition_allows_matching_live_row ... ok
test fleet_mutation::tests::precondition_already_terminal_for_stop ... ok
test fleet_mutation::tests::precondition_capability_missing ... ok
test fleet_mutation::tests::precondition_instance_mismatch_for_superseded_run ... ok
test fleet_mutation::tests::precondition_stale_revision ... ok
test fleet_mutation::tests::precondition_unknown_row_when_missing_or_logical_mismatch ... ok
test fleet_mutation::tests::replay_accepts_unseen_key ... ok
test fleet_mutation::tests::replay_conflicts_on_changed_payload ... ok
test fleet_mutation::tests::replay_rejects_expired_or_tombstoned_key ... ok
test fleet_mutation::tests::request_fingerprint_mismatch_is_rejected ... ok
test fleet_mutation::tests::replay_returns_original_receipt_for_same_payload ... ok
test fleet_mutation::tests::stop_and_retry_reject_fork_prompt ... ok
test fleet_owner_facts::tests::done_row_reopens_only_inside_pending_review_window ... ok
test fleet_owner_facts::tests::done_status_rules_in_owner_order ... ok
test fleet_owner_facts::tests::gate_monitor_and_proc_turn_facts ... ok
test fleet_owner_facts::tests::injected_observer_matches_by_dir_or_name ... ok
test fleet_owner_facts::tests::plan_statuses_follow_owner_rules ... ok
test fleet_owner_facts::tests::pending_review_uses_injected_tier_and_skips_auto_approved ... ok
test fleet_owner_facts::tests::plan_tier_frontmatter_parses_and_normalizes ... ok
test fleet_owner_facts::tests::starting_promotes_on_run_start ... ok
test fleet_owner_facts::tests::waiting_beats_question_and_question_answers ... ok
test fleet_owner_facts::tests::turn_status_keys_accept_legacy_spelling_but_emit_canonical ... ok
test fleet_presentation::tests::alive_and_unknown_rows_always_stay_current ... ok
test fleet_presentation::tests::anchor_outside_the_window_does_not_present_recent_members ... ok
test fleet_presentation::tests::dead_active_leftover_demotes_into_recent_terminal ... ok
test fleet_presentation::tests::dead_orphan_of_dismissed_agent_session_is_excluded ... ok
test fleet_presentation::tests::dismissed_rows_are_excluded_regardless_of_protection_or_liveness ... ok
test fleet_presentation::tests::identity_mismatch_is_excluded_even_when_apparently_alive ... ok
test fleet_presentation::tests::live_and_unknown_agent_session_members_remain_current ... ok
test fleet_presentation::tests::ordering_is_stable_newest_completion_first_with_identity_tiebreak ... ok
test fleet_presentation::tests::pending_dead_creator_agent_session_member_stays_current ... ok
test fleet_presentation::tests::protected_dead_row_takes_the_bounded_terminal_path ... ok
test fleet_presentation::tests::record_without_lifecycle_evidence_is_excluded ... ok
test fleet_presentation::tests::rejects_unknown_schema_version ... ok
test file_history::tests::sync_returns_fresh_when_tip_unchanged ... ok
test fleet_presentation::tests::root_less_terminal_agent_session_is_served_whole_through_its_anchor ... ok
test fleet_presentation::tests::rows_outside_the_seven_day_window_are_excluded ... ok
test fleet_presentation::tests::served_set_puts_every_identity_in_exactly_one_bucket ... ok
test fleet_presentation::tests::terminal_agent_session_member_of_visible_agent_session_is_served_for_nesting ... ok
test fleet_presentation::tests::unanchored_orphan_members_stay_excluded_even_when_several_are_recent ... ok
test gate_decision::tests::a_current_failure_reports_accepted_failed_with_recovery_permissions ... ok
test fleet_presentation::tests::terminal_and_demoted_rows_share_one_combined_window_and_cap ... ok
test gate_decision::tests::a_dead_owner_reports_accepted_owner_lost_with_recovery_permissions ... ok
test gate_decision::tests::a_post_response_failure_is_echoed_without_changing_answered_disposition ... ok
test gate_decision::tests::a_published_response_always_wins ... ok
test gate_decision::tests::a_receipt_naming_a_different_gate_is_reported_explicitly ... ok
test gate_decision::tests::a_receipt_naming_a_different_request_hash_is_reported_explicitly ... ok
test gate_decision::tests::a_receipt_without_acceptance_id_is_rejected_before_lifecycle_policy ... ok
test gate_decision::tests::a_verified_receipt_is_accepted_unfinished_even_past_the_grace_window ... ok
test gate_decision::tests::accepts_a_fresh_decision_with_a_stable_fingerprint ... ok
test gate_decision::tests::an_unreadable_receipt_is_reported_explicitly ... ok
test gate_decision::tests::an_existing_receipt_without_acceptance_id_is_invalid ... ok
test gate_decision::tests::cancellation_outranks_a_verified_receipt ... ok
test gate_decision::tests::cancellation_reason_selects_the_matching_disposition ... ok
test gate_decision::tests::deadline_math_only_applies_once_response_receipt_and_cancellation_are_absent ... ok
test gate_decision::tests::decides_from_json_and_rejects_an_unsupported_schema_version ... ok
test gate_decision::tests::execution_claim_rejects_a_superseded_acceptance_id ... ok
test gate_decision::tests::fingerprint_is_order_sensitive_over_already_normalized_input ... ok
test gate_decision::tests::execution_claim_reowns_the_current_receipt ... ok
test gate_decision::tests::lifecycle_decides_from_json_and_rejects_an_unsupported_schema_version ... ok
test gate_decision::tests::malformed_current_failure_outcome_is_rejected ... ok
test gate_decision::tests::minting_without_acceptance_id_is_invalid ... ok
test gate_decision::tests::post_response_failure_is_not_valid_as_current_failure ... ok
test gate_decision::tests::rejects_a_conflict_while_the_existing_owner_is_live ... ok
test gate_decision::tests::rejects_a_conflicting_feedback_identity ... ok
test gate_decision::tests::rejects_a_conflicting_input_identity ... ok
test file_history::tests::sync_rebuilds_on_pathspec_change ... ok
test gate_decision::tests::replays_an_identical_resubmission_without_mutating_the_receipt ... ok
test gate_decision::tests::rejects_a_conflicting_selection_before_any_execution ... ok
test gate_decision::tests::stale_failure_outcomes_do_not_make_a_newer_receipt_supersedable ... ok
test gate_decision::tests::supersedes_a_conflict_after_a_current_failure_outcome ... ok
test gate_decision::tests::supersedes_a_conflict_after_the_existing_process_owner_is_dead ... ok
test gate_decision::tests::treats_an_unknown_existing_owner_as_live_for_conflicts ... ok
test gate_followup::tests::attempt_id_is_stable_for_the_same_gate_and_fingerprint ... ok
test gate_followup::tests::completed_successor_still_counts ... ok
test gate_followup::tests::existing_running_successor_without_receipt_is_adopted ... ok
test gate_followup::tests::ambiguous_successor_never_launches ... ok
test gate_followup::tests::explicit_resume_of_the_incident_may_launch ... ok
test gate_followup::tests::first_pass_settle_ignores_ambiguous_successor_evidence_without_attempt ... ok
test gate_followup::tests::first_pass_settle_ignores_running_or_completed_successor_evidence_without_attempt ... ok
test gate_followup::tests::first_pass_settle_may_launch_after_publishing_terminal_state ... ok
test gate_followup::tests::incident_legacy_terminal_metadata_is_interrupted ... ok
test gate_followup::tests::intentional_none_is_not_a_failed_launch ... ok
test gate_followup::tests::later_settle_of_a_terminal_gate_does_not_auto_launch ... ok
test gate_followup::tests::launched_receipt_is_a_noop ... ok
test gate_followup::tests::live_attempt_is_never_stolen ... ok
test gate_followup::tests::mismatched_attempt_fingerprint_is_ignored ... ok
test gate_followup::tests::not_launchable_stays_not_launchable ... ok
test gate_followup::tests::recorded_failure_is_resume_eligible ... ok
test gate_followup::tests::recorded_suppressed_outcome_is_idempotent ... ok
test gate_followup::tests::schema_mismatch_and_invalid_mode_are_structural_errors ... ok
test gate_followup::tests::stale_attempt_can_resume_after_ruling_out_a_successor ... ok
test gate_followup::tests::stale_launching_attempt_keeps_running_successor_adoption_on_settle ... ok
test gate_followup::tests::successor_evidence_name_accepts_legacy_spelling_but_emits_canonical ... ok
test gate_followup::tests::suppressed_auto_followup_does_not_launch ... ok
test git_lock::tests::cancelled_and_exhausted_budget_never_remove ... ok
test git_lock::tests::classifies_combined_stdout_bytes_style_text_and_alternate_index ... ok
test git_lock::tests::classifies_exit_one_and_128_index_lock_errors ... ok
test git_lock::tests::delay_parsing_rejects_nonfinite_and_negative_values ... ok
test git_lock::tests::disappeared_lock_retries_without_claiming_removal ... ok
test git_lock::tests::eager_cleanup_requires_age_and_absent_owner ... ok
test git_lock::tests::honors_shorter_caller_deadline_for_age_wait ... ok
test git_lock::tests::other_lock_is_retryable_but_never_deleted ... ok
test git_lock::tests::owner_classification_uses_descriptor_git_cwd_and_ambiguity ... ok
test git_lock::tests::path_match_requires_independent_resolution ... ok
test git_lock::tests::preserves_live_unknown_symlink_and_changed_locks ... ok
test git_lock::tests::rejects_success_timeout_signal_permission_and_incidental_mentions ... ok
test git_lock::tests::removes_aged_owner_free_lock_once ... ok
test git_lock::tests::replacement_with_old_mtime_is_a_new_identity ... ok
test git_lock::tests::retries_before_considering_removal ... ok
test git_lock::tests::waits_for_young_owner_free_lock_within_budget ... ok
test git_lock::tests::zero_delay_override_does_not_remove_a_young_lock ... ok
test git_object_sharing::tests::existing_reuse_refuses_broken_dependency_without_repair ... ok
test git_object_sharing::tests::install_noops_when_expected_dependency_is_unchanged ... ok
test git_object_sharing::tests::foreign_only_alternate_is_not_overwritten_by_install ... ok
test git_object_sharing::tests::existing_reuse_preserves_healthy_stale_dependency ... ok
test git_object_sharing::tests::maintenance_repair_allows_broken_dependency_without_clean_status ... ok
test git_object_sharing::tests::maintenance_compaction_requires_clean_status ... ok
test git_object_sharing::tests::maintenance_refuses_missing_fresh_observations ... ok
test git_object_sharing::tests::install_replaces_sase_line_and_preserves_foreign_lines ... ok
test git_object_sharing::tests::primary_among_foreign_entries_without_config_is_not_claimed ... ok
test git_object_sharing::tests::relative_alternates_resolve_from_object_database ... ok
test git_query::parsers::tests::branch_name_detached_head_returns_none ... ok
test git_query::parsers::tests::branch_name_empty_stdout_returns_none ... ok
test git_query::parsers::tests::branch_name_simple_value ... ok
test git_object_sharing::tests::remove_deletes_only_sase_owned_line ... ok
test git_object_sharing::tests::relative_alternates_resolve_through_symlinked_temp_root ... ok
test git_query::parsers::tests::branch_name_strips_surrounding_whitespace ... ok
test git_query::parsers::tests::branch_name_whitespace_only_returns_none ... ok
test git_query::parsers::tests::conflicted_files_empty_stdout_returns_empty ... ok
test git_query::parsers::tests::conflicted_files_only_blank_lines_returns_empty ... ok
test git_query::parsers::tests::conflicted_files_preserves_path_order ... ok
test git_query::parsers::tests::conflicted_files_strips_blank_lines ... ok
test git_query::parsers::tests::local_changes_clean_tree_returns_none ... ok
test git_query::parsers::tests::local_changes_dirty_tree_returns_stripped_text ... ok
test git_query::parsers::tests::local_changes_whitespace_only_returns_none ... ok
test git_query::parsers::tests::name_status_copy_with_score_carries_paired_paths ... ok
test git_query::parsers::tests::name_status_empty_stream_returns_empty ... ok
test git_query::parsers::tests::name_status_mixed_simple_and_rename_in_one_stream ... ok
test git_query::parsers::tests::name_status_rename_with_score_carries_paired_paths ... ok
test git_query::parsers::tests::name_status_simple_status_letters ... ok
test git_query::parsers::tests::name_status_skips_empty_status_tokens ... ok
test git_query::parsers::tests::name_status_trailing_nul_is_ignored ... ok
test git_query::parsers::tests::name_status_truncated_rename_falls_back_to_single_path ... ok
test git_query::parsers::tests::name_status_truncated_status_only_drops_entry ... ok
test git_query::parsers::tests::workspace_name_falls_back_to_root_when_remote_blank ... ok
test git_query::parsers::tests::workspace_name_falls_back_to_root_when_remote_none ... ok
test git_query::parsers::tests::workspace_name_https_remote_with_dot_git ... ok
test git_query::parsers::tests::workspace_name_https_remote_without_dot_git ... ok
test git_query::parsers::tests::workspace_name_path_like_remote ... ok
test git_query::parsers::tests::workspace_name_remote_dot_git_only_returns_none ... ok
test git_query::parsers::tests::workspace_name_returns_none_when_both_inputs_empty ... ok
test git_query::parsers::tests::workspace_name_remote_takes_priority_over_root ... ok
test git_query::parsers::tests::workspace_name_ssh_remote_with_dot_git ... ok
test glossary::tests::builds_effective_aliases_with_derived_plurals ... ok
test glossary::tests::builds_effective_aliases_with_term_first ... ok
test glossary::tests::entry_path_falls_back_when_source_key_path_is_empty ... ok
test glossary::tests::glossary_source_wire_accepts_v1_payload_names ... ok
test glossary::tests::glossary_source_wire_emits_v2_payload_names ... ok
test glossary::tests::filters_display_aliases_to_non_derivable_configured_aliases ... ok
test glossary::tests::pluralizes_phrases_with_conservative_ascii_rules ... ok
test file_history::tests::incremental_fold_equals_full_rebuild ... ok
test glossary::tests::literal_zone_filter_skips_candidates_but_keeps_prose_match ... ok
test glossary::tests::lookup_on_continuation_word_returns_wrapped_span ... ok
test glossary::tests::scan_skips_fenced_and_inline_code_literals ... ok
test glossary::tests::lookup_uses_utf16_editor_positions ... ok
test glossary::tests::skips_derived_plural_claimed_by_authored_alias_without_diagnostic ... ok
test glossary::tests::scans_wrapped_phrase_with_trimmed_segments ... ok
test glossary::tests::validation_diagnostics_stay_authored_for_alias_edge_cases ... ok
test glossary::tests::three_word_term_wraps_across_three_lines ... ok
test glossary::tests::scans_case_insensitively_with_longest_non_overlapping_matches ... ok
test glossary::tests::scans_derived_plural_for_term_without_configured_aliases ... ok
test goal::fast_path::tests::discovery_rejects_non_canonical_projects ... ok
test glossary::tests::single_line_match_has_one_span_equal_segment ... ok
test glossary::tests::wrapped_phrase_accepts_crlf_without_segment_carriage_returns ... ok
test goal::fast_path::tests::parse_accepts_bare_list_and_show ... ok
test goal::fast_path::tests::parse_declines_slow_path_flags ... ok
test goal::fast_path::tests::token_split_accepts_every_id_form ... ok
test goal::fast_path::tests::missing_projection_declines_to_slow_path ... ok
test glossary::tests::wrapped_phrase_does_not_cross_block_boundaries ... ok
test fleet_contract::tests::identity::identity_store_uses_private_modes ... ok
test glossary::tests::wrapped_longer_match_wins_over_shorter_at_same_start ... ok
test file_history::tests::truncated_budget_sets_flag_and_forces_incomplete ... ok
test bead::mutation::tests::snooze_plus_one::task_plus_one_stale_observation_window_records_without_reopening_closed_task ... ok
test goal::fast_path::tests::empty_ledger_lists_empty_state_with_delegation_notice ... ok
test file_history::tests::sync_rebuilds_after_history_rewrite ... ok
test fleet_contract::tests::identity::concurrent_identity_creators_converge_on_one_record ... ok
test editor::completion::tests::artifact_ref::commit_inventory_skips_sidecars_before_reporting_the_row_cap ... ok
test goal::ledger::tests::append_new_creates_marker_and_lists_hot ... ok
test goal::ledger::tests::doctor_repairs_missing_markers ... ok
test goal::ledger::tests::corrupt_event_file_isolates_one_goal ... ok
test goal::ledger::tests::merge_with_a_normalized_self_refuses ... ok
test goal::ledger::tests::corrupt_projection_reports_and_rebuilds ... ok
test goal::ledger::tests::doctor_repair_keeps_the_projection_header ... ok
test goal::ledger::tests::unknown_kind_wire_parses_as_unsupported ... ok
test goal::ledger::tests::drop_removes_marker_after_event_write ... ok
test goal::ledger::tests::normalized_edit_writes_only_under_the_canonical_id ... ok
test goal::ledger::tests::marker_superset_holds_under_fault_hook ... ok
test goal::render::markdown::tests::card_renders_sections_and_omits_empty_ones ... ok
test goal::render::markdown::tests::citation_line_matches_contract_example_and_fits ... ok
test goal::render::markdown::tests::citation_line_truncates_long_outcomes ... ok
test goal::render::markdown::tests::claims_render_with_number_and_status ... ok
test goal::render::markdown::tests::empty_card_renders_header_only ... ok
test goal::render::terminal::tests::card_renders_header_outcome_and_timeline ... ok
test goal::render::terminal::tests::colorized_list_wraps_glyph_and_ids ... ok
test goal::render::terminal::tests::compact_list_prints_one_line_per_goal ... ok
test goal::render::terminal::tests::empty_list_prints_start_hint ... ok
test goal::render::terminal::tests::footer_chips_report_unpublished_and_unreadable ... ok
test goal::render::terminal::tests::glyph_is_one_cell_wide ... ok
test goal::render::terminal::tests::tty_list_groups_lanes_with_header_and_counts ... ok
test goal::tests::actions_tests::edit_cap_counts_removals_before_additions ... ok
test goal::tests::actions_tests::drop_plans_a_canceled_settlement ... ok
test goal::tests::actions_tests::edit_empty_title_and_outcome_name_their_codes ... ok
test goal::tests::actions_tests::edit_normalizes_the_goal_id ... ok
test goal::tests::actions_tests::edit_plans_an_edited_event_on_its_head ... ok
test goal::tests::actions_tests::edit_refuses_unchanged_fields ... ok
test goal::tests::actions_tests::edit_refusals_are_stable ... ok
test goal::tests::actions_tests::edit_refuses_unknown_criteria ... ok
test goal::tests::actions_tests::merge_compares_normalized_ids_for_self ... ok
test goal::tests::actions_tests::merge_plans_source_settlement_plus_target_record ... ok
test goal::tests::actions_tests::new_plans_a_created_event ... ok
test goal::tests::actions_tests::merge_refusals_are_stable ... ok
test goal::tests::actions_tests::new_reduces_to_a_live_goal ... ok
test goal::tests::actions_tests::new_refusals_are_stable ... ok
test goal::tests::actions_tests::new_refuses_too_many_criteria ... ok
test goal::tests::actions_tests::planned_events_carry_the_actor ... ok
test goal::tests::actions_tests::reopen_plans_a_reopened_event ... ok
test goal::tests::fixtures_tests::every_fixture_id_parses ... ok
test goal::tests::fixtures_tests::every_fixture_parses_and_matches_its_kind ... ok
test goal::tests::fixtures_tests::serialized_created_event_writes_basis_null ... ok
test goal::tests::ids_tests::event_id_carries_its_timestamp ... ok
test goal::tests::ids_tests::event_id_mints_are_monotonic_in_process ... ok
test goal::tests::ids_tests::event_id_mints_at_26_crockford_chars ... ok
test goal::tests::ids_tests::event_id_parse_rejects_bad_values ... ok
test goal::tests::fixtures_tests::every_fixture_round_trips ... ok
test goal::tests::ids_tests::goal_id_mints_are_unique ... ok
test goal::tests::ids_tests::goal_id_mints_at_five_crockford_chars ... ok
test goal::tests::ids_tests::goal_id_parse_folds_uppercase ... ok
test goal::tests::ids_tests::goal_id_parse_rejects_bad_values ... ok
test goal::tests::ids_tests::test_event_id_helper_is_deterministic ... ok
test goal::tests::reduce_tests::agent_cannot_remove_user_criteria ... ok
test goal::tests::reduce_tests::claim_beaten_by_a_later_canceled_drop_is_superseded ... ok
test goal::tests::reduce_tests::claim_cycle_moves_through_review ... ok
test goal::tests::reduce_tests::concurrent_canceled_beats_a_claim ... ok
test goal::tests::reduce_tests::concurrent_claims_first_in_order_wins ... ok
test goal::tests::reduce_tests::concurrent_edits_share_stable_criterion_ids ... ok
test goal::tests::reduce_tests::concurrent_settlements_first_in_order_wins ... ok
test goal::tests::reduce_tests::content_after_a_seen_settlement_is_ignored ... ok
test goal::tests::reduce_tests::content_concurrent_with_settlement_still_applies ... ok
test goal::tests::reduce_tests::created_active_and_draft_statuses ... ok
test goal::tests::reduce_tests::human_canceled_beats_an_earlier_agent_settlement ... ok
test goal::tests::reduce_tests::idempotency_dedupe_counts_only_the_first ... ok
test goal::tests::reduce_tests::late_attachment_is_recorded_without_unsettling ... ok
test goal::tests::reduce_tests::merged_settlement_without_a_target_is_flagged ... ok
test goal::tests::reduce_tests::merged_target_record_accumulates_sources ... ok
test goal::tests::reduce_tests::missing_basis_is_a_diagnostic_not_a_failure ... ok
test goal::tests::reduce_tests::named_moves_draft_and_active_to_active ... ok
test goal::tests::reduce_tests::newer_schema_version_marks_the_goal_unreadable ... ok
test goal::tests::reduce_tests::named_on_done_is_illegal ... ok
test goal::tests::reduce_tests::publish_classes_split_sync_and_batched ... ok
test goal::tests::reduce_tests::reopen_clears_the_merge_target_but_keeps_history ... ok
test goal::tests::reduce_tests::reopen_needs_a_settled_goal ... ok
test goal::tests::reduce_tests::second_claim_while_in_review_is_illegal ... ok
test goal::tests::reduce_tests::second_created_is_an_id_collision ... ok
test goal::tests::reduce_tests::settle_flavors_land_done_or_dropped ... ok
test goal::tests::reduce_tests::unknown_kind_marks_only_that_goal_unreadable ... ok
test goal::tests::reduce_tests::wrong_goal_events_are_ignored ... ok
test goal::tests::view_tests::card_header_names_title_status_ref_and_revision ... ok
test goal::tests::view_tests::card_omits_empty_sections ... ok
test goal::tests::view_tests::draft_card_is_labeled_local ... ok
test goal::tests::view_tests::glyph_and_accent_are_frozen ... ok
test goal::tests::reduce_tests::shuffled_inputs_reduce_identically ... ok
test goal::tests::view_tests::relative_age_steps_through_units ... ok
test fleet_contract::tests::identity::installation_identity_creation_read_rotation_and_migration_are_fenced ... ok
test goal::ledger::tests::unsupported_store_fails_closed ... ok
test goal::tests::view_tests::row_carries_glyph_status_title_and_age ... ok
test goal::tests::view_tests::row_without_now_covers_its_lifespan ... ok
test goal::tests::wire_tests::kind_words_round_trip ... ok
test goal::tests::view_tests::settled_card_keeps_its_badge ... ok
test goal::tests::wire_tests::payload_dispatch_refuses_untagged_guessing ... ok
test goal::tests::wire_tests::newer_schema_version_parses_as_typed_value ... ok
test goal::tests::wire_tests::payload_dispatch_matches_envelope_kind ... ok
test goal::tests::wire_tests::status_words_and_heat ... ok
test goal::tests::wire_tests::unknown_kind_stays_typed ... ok
test goal::tests::wire_tests::unsupported_kind_parses_as_typed_value ... ok
test goal::tests::wire_tests::unknown_fields_are_ignored ... ok
test hold_directive::tests::duplicate_scope_and_ttl_are_errors_across_occurrences ... ok
test hold_directive::tests::expands_job_to_chop_without_stored_job_identity ... ok
test hold_directive::tests::enabled_flags_are_not_required ... ok
test hold_directive::tests::expands_names_to_selectors_without_turn_agent_session ... ok
test hold_directive::tests::keeps_independently_stored_job_tribe ... ok
test hold_directive::tests::rejects_required_errors ... ok
test hold_directive::tests::parses_unions_and_canonical_round_trip ... ok
test host_bridge::tests::finalizer_catalog_wire_accepts_legacy_and_extended_entry_json ... ok
test host_bridge::tests::macro_catalog_entry_wire_accepts_old_and_new_definition_path_json ... ok
test host_bridge::tests::patch_tag_entry_serializes_canonical_patch_key ... ok
test host_bridge::tests::snippet_catalog_wire_accepts_minimal_entry_json ... ok
test host_bridge::tests::static_helper_bridge_returns_finalizer_catalog_response ... ok
test host_bridge::tests::static_helper_bridge_returns_snippet_catalog_response ... ok
test host_bridge::tests::static_helper_bridge_returns_structured_catalog_response ... ok
test host_bridge::tests::static_helper_bridge_returns_vcs_repo_catalog_response ... ok
test host_liveness::tests::command_parser_accepts_sase_and_python_only ... ok
test host_liveness::tests::completed_records_are_dead_without_probing ... ok
test file_history::runner::tests::timeout_kills_child_and_joins_a_blocked_writer ... ok
test host_bridge::tests::command_helper_bridge_invokes_editor_snippet_catalog ... ok
test host_bridge::tests::command_helper_bridge_invokes_editor_finalizer_catalog ... ok
test host_liveness::tests::home_marker_match_and_mismatch ... ok
test host_liveness::tests::filesystem_probe_reads_home_marker_and_project_claims ... ok
test host_liveness::tests::missing_pid_and_invalid_pid_keep_wire_distinctions ... ok
test host_liveness::tests::matching_project_claim_is_alive ... ok
test host_bridge::tests::command_helper_bridge_invokes_editor_vcs_repo_catalog ... ok
test host_liveness::tests::status_parser_detects_zombie_and_running ... ok
test host_liveness::tests::stale_project_claim_is_identity_mismatch ... ok
test host_liveness::tests::workflow_without_claim_shape_uses_process_classifier ... ok
test host_liveness::tests::zombie_and_wrong_command_are_not_alive ... ok
test host_liveness::tests::workspace_num_without_current_claim_is_mismatch ... ok
test instruction_manifest::tests::common_digest_ignores_provider_section ... ok
test instruction_manifest::tests::common_digest_rejected_when_wrong ... ok
test instruction_manifest::tests::common_digest_filled_when_null ... ok
test instruction_manifest::tests::unsupported_schema_is_reported ... ok
test instruction_manifest::tests::provider_only_change_keeps_common_digest ... ok
test instruction_manifest::tests::v1_golden_still_normalizes_unchanged ... ok
test instruction_manifest::tests::valid_helper_normalizes ... ok
test instruction_manifest::tests::valid_interactive_normalizes ... ok
test instruction_manifest::tests::valid_root_normalizes_unchanged ... ok
test instruction_manifest::tests::valid_v2_helper_with_parent_normalizes_unchanged ... ok
test instruction_manifest::tests::valid_v2_legacy_fallback_normalizes_unchanged ... ok
test instruction_manifest::tests::valid_v2_root_with_explicit_subagent_normalizes_unchanged ... ok
test instruction_manifest::tests::wire_schema_version_is_two ... ok
test instruction_manifest::tests::valid_v2_root_with_inherits_root_subagent_normalizes ... ok
test launch_scratch_liveness::tests::ancestor_started_after_child_is_not_system_service_exempt ... ok
test launch_scratch_liveness::tests::esrch_is_treated_as_missing ... ok
test launch_scratch_liveness::tests::exempted_system_service_defaults_when_absent ... ok
test instruction_manifest::tests::invalid_fixtures_are_rejected ... ok
test instruction_manifest::tests::v2_delivery_invariants_are_enforced ... ok
test launch_scratch_liveness::tests::ancestry_cycle_is_not_system_service_exempt ... ok
test launch_scratch_liveness::tests::later_unreadable_process_stays_incomplete ... ok
test launch_scratch_liveness::tests::live_holder_matches_environ_path ... ok
test launch_scratch_liveness::tests::live_holder_matches_environ_path_through_symlink_with_missing_suffix ... ok
test launch_scratch_liveness::tests::missing_proc_root_is_unobservable ... ok
test launch_scratch_liveness::tests::live_holder_matches_launch_key_and_cwd ... ok
test launch_scratch_liveness::tests::normalize_path_canonicalizes_existing_prefix_before_missing_suffix ... ok
test launch_scratch_liveness::tests::missing_ancestor_status_is_not_system_service_exempt ... ok
test launch_scratch_liveness::tests::orphan_ppid_one_is_not_system_service_exempt ... ok
test launch_scratch_liveness::tests::own_and_exempt_pids_are_skipped ... ok
test launch_scratch_liveness::tests::pre_launch_unreadable_process_is_exempt ... ok
test launch_scratch_liveness::tests::same_uid_parent_is_not_system_service_exempt ... ok
test launch_scratch_liveness::tests::sudo_parent_is_not_system_service_exempt ... ok
test machine_hood::tests::machine_hood_of_classifies_known_machines ... ok
test machine_hood::tests::machine_hood_of_returns_none_for_unknown_or_partial ... ok
test launch_scratch_liveness::tests::sshd_like_chain_is_system_service_exempt ... ok
test machine_hood::tests::qualify_and_strip_round_trip ... ok
test machine_hood::tests::qualify_does_not_confuse_prefix_of_another_machine ... ok
test machine_hood::tests::qualify_is_idempotent ... ok
test machine_hood::tests::qualify_prepends_when_missing ... ok
test launch_scratch_liveness::tests::user_slice_top_is_not_system_service_exempt ... ok
test machine_hood::tests::qualify_preserves_agent_session_names ... ok
test launch_scratch_liveness::tests::zombie_process_is_not_counted_as_unreadable ... ok
test machine_hood::tests::strip_is_idempotent ... ok
test machine_hood::tests::strip_leaves_unqualified_and_foreign_names ... ok
test machine_hood::tests::strip_never_produces_empty_remainder ... ok
test machine_hood::tests::strip_removes_leading_hood ... ok
test machine_hood::tests::validate_accepts_lowercase_and_underscores ... ok
test machine_hood::tests::validate_rejects_empty_uppercase_digits_and_dots ... ok
test machine_setup::tests::discovery_applies_https_endpoint_overrides ... ok
test machine_setup::tests::discovery_excludes_self_by_identity_overlap_and_self_flag ... ok
test machine_setup::tests::discovery_handles_missing_and_extra_peer_fields ... ok
test machine_setup::tests::discovery_parses_status_excludes_self_and_normalizes_dns ... ok
test machine_setup::tests::discovery_reports_non_mapping_peers_and_peer_payload ... ok
test machine_setup::tests::health_classifies_compatible_fleet_advertisement ... ok
test machine_setup::tests::health_classifies_legacy_sase_without_fleet_as_unknown ... ok
test machine_setup::tests::health_classifies_non_sase_payload_as_unrelated ... ok
test machine_setup::tests::health_distinguishes_unrelated_healthy_service_from_legacy_sase ... ok
test machine_setup::tests::discovery_rejects_invalid_endpoint_override ... ok
test machine_setup::tests::health_incompatible_when_protocol_constant_is_absent ... ok
test machine_setup::tests::health_rejects_unsupported_schema_version ... ok
test machine_setup::tests::health_rejects_malformed_protocol_version_types ... ok
test machine_setup::tests::reconcile_does_not_let_untrusted_hint_overwrite_enrolled_pin ... ok
test machine_setup::tests::reconcile_rejects_unsupported_schema_version ... ok
test machine_setup::tests::review_assessment_normalizes_completed_review_without_reconciling ... ok
test machine_setup::tests::reconcile_skips_matching_identities_and_routes_pin_change_to_repair ... ok
test machine_setup::tests::review_assessment_requires_initial_review_without_completed_state ... ok
test machine_setup::tests::review_assessment_treats_completed_initial_review_as_terminal ... ok
test machine_setup::tests::review_merge_records_empty_and_deduplicated_completed_reviews ... ok
test machine_setup::tests::review_state_rejects_unsupported_schema_version ... ok
test host_liveness::tests::filesystem_probe_rechecks_stale_claims_before_mismatch ... ok
test macro_catalog::tests::authored_inputs::definition_range_prefers_macros_section ... ok
test macro_catalog::tests::authored_inputs::config_macros_key_loads_like_retired_xprompts_key ... ok
test macro_catalog::tests::authored_inputs::config_retired_key_loads_under_both_policies ... ok
test macro_catalog::tests::authored_inputs::malformed_macros_section_is_an_error_while_legacy_stays_lenient ... ok
test macro_catalog::tests::authored_inputs::markdown_frontmatter_macros_section_loads_locals ... ok
test macro_catalog::tests::authored_inputs::markdown_frontmatter_both_keys_conflict_and_retired_loads ... ok
test macro_catalog::tests::authored_inputs::nested_local_helpers_use_authored_key_rules ... ok
test macro_catalog::tests::authored_inputs::project_local_config_accepts_macros_key ... ok
test macro_catalog::tests::authored_inputs::workflow_yaml_macros_section_loads_locals ... ok
test macro_catalog::tests::catalog_sources::canonical_macros_precede_retired_xprompts_with_conflict ... ok
test macro_catalog::tests::catalog_sources::config_collision_rules_are_preserved ... ok
test macro_catalog::tests::catalog_sources::canonical_only_and_old_only_installations_both_load ... ok
test macro_catalog::tests::catalog_sources::catalog_loaders_accept_legacy_regardless_of_switch ... ok
test macro_catalog::tests::catalog_sources::denied_policy_loads_explicit_retired_and_plugin_retired ... ok
test macro_catalog::tests::catalog_sources::denied_policy_still_loads_retired_alongside_skills_memory_and_config ... ok
test macro_catalog::tests::catalog_sources::package_macro_skills_precede_xprompt_skills ... ok
test macro_catalog::tests::loading::config_workflows_are_ignored_but_file_backed_project_workflows_load ... ok
test macro_catalog::tests::loading::home_skills_use_the_skill_namespace_and_project_qualified_form ... ok
test macro_catalog::tests::authored_inputs::config_both_keys_is_an_error_even_when_empty ... ok
test macro_catalog::tests::catalog_sources::explicit_resources_beat_inferred_environment_paths ... ok
test macro_catalog::tests::catalog_sources::explicit_package_macros_win_over_xprompts ... ok
test macro_catalog::tests::loading::loads_plugin_file_and_config_catalog_sources ... ok
test macro_catalog::tests::loading::packaged_skill_frame_template_is_not_a_skill_source ... ok
test macro_catalog::tests::loading::packaged_skills_load_from_nested_xprompts_skills_only ... ok
test macro_catalog::tests::loading::rejects_misplaced_skill_definitions_in_both_directions ... ok
test macro_catalog::tests::memory::explicit_project_selection_picks_that_projects_memory_only ... ok
test macro_catalog::tests::memory::invalid_memory_notes_become_diagnostics_instead_of_silent_gaps ... ok
test macro_catalog::tests::memory::memory_notes_load_as_namespaced_no_argument_xprompt_memories ... ok
test macro_catalog::tests::loading::parity_fixture_covers_supported_catalog_sources ... ok
test macro_catalog::tests::memory::ordinary_definitions_cannot_claim_the_reserved_memory_namespace ... ok
test macro_catalog::tests::memory::project_memory_shadows_home_memory_of_the_same_stem ... ok
test macro_catalog::tests::memory::split_canonical_and_legacy_memory_state_is_a_collision_error ... ok
test file_history::tests::shallow_clone_marks_health_and_incomplete ... ok
test goal::ledger::tests::unknown_ids_refuse_without_writing ... ok
test macro_catalog::tests::catalog_sources::macro_env_precedence_is_new_first ... ok
test macro_catalog::tests::parsing::parses_markdown_frontmatter_local_xprompts_without_global_entry ... ok
test macro_catalog::tests::parsing::yaml_child_key_range_finds_immediate_quoted_children ... ok
test macro_catalog::tests::projects::canonical_project_sources_win_with_legacy_read_compatibility ... ok
test macro_catalog::tests::projects::computes_known_project_local_config_definition_range ... ok
test goal::ledger::tests::refused_edit_reports_code ... ok
test goal::ledger::tests::merge_writes_normalized_ids_for_into_and_from ... ok
test macro_catalog::tests::projects::known_projects_use_display_names_aliases_and_gp_fallback ... ok
test macro_catalog::tests::skill_definition::catalog_payloads_without_memory_fields_still_deserialize ... ok
test macro_catalog::tests::skill_definition::macro_skill_wires_pin_legacy_schema_and_shape ... ok
test macro_catalog::tests::skill_definition::pseudo_sources_do_not_get_definition_paths ... ok
test macro_catalog::tests::projects::project_config_collision_reports_split_state ... ok
test macro_catalog::tests::projects::project_catalog_uses_canonical_namespace_and_filter_refs ... ok
test macro_catalog::tests::memory::memory_entries_render_as_memory_with_a_navigable_definition ... ok
test macro_catalog::tests::loading::loads_markdown_and_workflow_with_canonical_insertions ... ok
test macro_input_types::tests::agent_has_named_type_and_value_role ... ok
test macro_input_types::tests::breif_against_brief_and_full_suggests_brief ... ok
test macro_input_types::tests::builtin_at_word_and_word_resolve_to_word ... ok
test macro_input_types::tests::catalog_contains_only_the_contract_rows ... ok
test macro_input_types::tests::check_input_value_is_noop_without_choices ... ok
test macro_input_types::tests::choice_bool_and_int_are_quote_errors ... ok
test macro_input_types::tests::choice_whitespace_null_duplicate_unknown_key_and_comma ... ok
test macro_input_types::tests::closed_set_default_rejects_non_members ... ok
test macro_input_types::tests::empty_registry_reports_plugin_not_installed ... ok
test macro_input_types::tests::enmu_suggests_enum ... ok
test macro_input_types::tests::fixture_registry_reports_declares_no_input_type ... ok
test macro_input_types::tests::integer_and_boolean_aliases_resolve ... ok
test macro_input_types::tests::pep503_normalizes_plugin_prefix ... ok
test macro_catalog::tests::parsing::filters_step_inputs_and_formats_defaults ... ok
test macro_input_types::tests::plugin_loader_accepts_valid_sibling_and_skips_bad_type ... ok
test macro_input_types::tests::plugin_loader_rejects_envelope_and_normalizes_distribution ... ok
test macro_input_types::tests::string_resolves_to_line_with_deprecated ... ok
test macro_catalog::tests::parsing::catalog_input_choices_keep_descriptions ... ok
test macro_input_types::tests::pyyaml_vector_types_non_strings_and_rejects_ordinary_words ... ok
test macro_input_types::tests::yaml_choices_round_trip_through_the_json_validator ... ok
test macro_text_block::tests::closes_at_end_of_region ... ok
test macro_input_types::tests::suggest_closest_ranks_equality_and_prefix_first ... ok
test macro_text_block::tests::closes_before_comma_of_next_argument ... ok
test macro_text_block::tests::closes_before_paren_brace_or_pipe ... ok
test macro_text_block::tests::overlapping_closer_before_paren ... ok
test macro_text_block::tests::rejects_non_opener ... ok
test macro_text_block::tests::skips_inner_marker_before_comma_terminator ... ok
test macro_text_block::tests::shared_corpus_loads ... ok
test macro_text_block::tests::unterminated_block_returns_none ... ok
test managed_origin::tests::canonical_remote_unavailable_fails ... ok
test managed_origin::tests::missing_identity_fails ... ok
test managed_origin::tests::primary_origin_resolving_to_primary_fails ... ok
test managed_origin::tests::stale_explicit_push_url_is_rewritten ... ok
test managed_origin::tests::stale_origin_is_rewritten_to_canonical_remote ... ok
test managed_origin::tests::unrelated_local_bare_remote_is_preserved ... ok
test managed_tmp::permission_repair::aged_agent_tmp_with_0555_vault_is_removed ... ok
test managed_tmp::permission_repair::dead_launch_candidate_with_nested_0555_is_removed ... ok
test managed_tmp::permission_repair::symlink_to_outside_0555_dir_is_not_followed ... ok
test managed_tmp::tests::absent_low_free_space_age_preserves_base_pressure_age ... ok
test managed_tmp::tests::age_pass_reports_successful_reclaimed_bytes ... ok
test managed_tmp::tests::broad_cleanup_roots_are_rejected ... ok
test managed_tmp::tests::dead_entry_past_grace_is_removed ... ok
test managed_tmp::tests::dead_launch_keeps_held_entry ... ok
test managed_tmp::tests::dead_launch_keeps_incomplete_observation ... ok
test managed_tmp::tests::dead_launch_unobservable_skips ... ok
test managed_tmp::tests::dead_launch_respects_removal_budget ... ok
test managed_tmp::tests::dry_run_selects_stale_entries_without_removing_them ... ok
test managed_tmp::tests::failed_age_removal_is_reported_without_claiming_reclaimed_bytes ... ok
test managed_tmp::tests::expired_build_tree_without_fresh_descendant_is_removed ... ok
test managed_tmp::tests::free_space_pressure_reaps_build_scratch_below_size_ceiling ... ok
test managed_tmp::tests::incomplete_tree_read_preserves_candidate_and_reports_incomplete ... ok
test managed_tmp::tests::launch_scratch_preserves_live_or_incomplete_candidates ... ok
test managed_tmp::tests::launch_scratch_removes_only_assigned_bucket_and_key ... ok
test managed_tmp::tests::live_build_tree_with_fresh_descendant_survives_pressure ... ok
test managed_tmp::tests::low_free_space_age_applies_to_observed_unheld_pressure_entries ... ok
test managed_tmp::tests::low_free_space_age_reaps_recent_large_target_under_free_space_trigger ... ok
test managed_tmp::tests::low_free_space_age_does_not_apply_to_size_only_pressure ... ok
test managed_tmp::tests::low_free_space_age_reaps_recent_large_target_when_size_also_triggers ... ok
test goal::ledger::tests::unreadable_goal_isolated_from_neighbors ... ok
test managed_tmp::tests::low_free_space_age_still_respects_fresh_descendant ... ok
test managed_tmp::tests::low_space_age_never_lengthens_base_pressure_age ... ok
test managed_tmp::tests::pressure_does_not_delete_unknown_bucket_with_fresh_child ... ok
test managed_tmp::tests::pressure_keeps_symlink_entries ... ok
test managed_tmp::tests::pressure_never_removes_held_entry ... ok
test managed_tmp::tests::pressure_orders_largest_first_and_oldest_within_equal_size ... ok
test managed_tmp::tests::pressure_respects_removal_budget ... ok
test managed_tmp::tests::pressure_skips_generic_agent_tmp_and_handoff_buckets ... ok
test managed_tmp::tests::pressure_stops_at_free_space_recovery_threshold ... ok
test managed_tmp::tests::pressure_uses_grace_for_unheld_entry ... ok
test managed_tmp::tests::unknown_bucket_survives_while_stale_child_is_pruned ... ok
test managed_tmp::tests::pressure_without_dead_launch_keeps_grace_young_entry ... ok
test managed_tmp_roots::tests::broad_roots_are_rejected ... ok
test macro_catalog::tests::snippets::converts_native_macro_snippet_templates ... ok
test managed_tmp_roots::tests::missing_state_lists_empty ... ok
test macro_catalog::tests::snippets::native_snippet_catalog_resolves_references_after_user_merge ... ok
test managed_tmp_roots::tests::relative_symlink_and_file_roots_are_refused ... ok
test macro_catalog::tests::parsing::projects_repeatable_agent_input_metadata ... ok
test macro_catalog::tests::snippets::loads_native_snippet_catalog_with_user_overrides ... ok
test markdown_link_refs::tests::allocate_fills_gaps_between_existing_definitions ... ok
test markdown_link_refs::tests::allocate_reserves_a_dangling_numeric_use_with_no_definition ... ok
test markdown_link_refs::tests::allocate_reuses_matching_destination_before_picking_a_new_number ... ok
test markdown_link_refs::tests::append_definitions_in_numeric_order_and_skips_matching_ones ... ok
test markdown_link_refs::tests::append_is_idempotent_and_preserves_trailing_newline_shape ... ok
test markdown_link_refs::tests::scan_collects_definitions_first_wins_and_uses_all_three_forms ... ok
test markdown_link_refs::tests::scan_ignores_footnotes_inline_links_definitions_and_literal_zones ... ok
test markdown_link_refs::tests::scan_skips_duplicate_bracket_pairs_used_as_link_text ... ok
test memory_history::query::blob_selector_tests::blob_ambiguous_prefix_errors_and_names_blob ... ok
test memory_history::query::blob_selector_tests::blob_full_oid_resolves_newest_match ... ok
test memory_history::query::blob_selector_tests::blob_missing_errors_and_names_blob ... ok
test memory_history::query::blob_selector_tests::blob_non_hex_is_invalid ... ok
test memory_history::query::blob_selector_tests::blob_tombstone_only_blob_is_missing ... ok
test memory_history::query::blob_selector_tests::blob_prefix_shorter_than_seven_is_invalid ... ok
test memory_history::query::blob_selector_tests::blob_tombstone_row_does_not_count ... ok
test memory_history::query::blob_selector_tests::blob_unique_prefix_resolves ... ok
test goal::ledger::tests::stale_basis_refuses_noncommutative_and_replans_commutative ... ok
test macro_catalog::tests::skill_definition::resolves_xprompt_skill_definition_sources ... ok
test macro_catalog::tests::parsing::parses_xprompt_workflow_and_input_descriptions ... ok
test managed_tmp_roots::tests::corrupt_state_reads_empty_and_next_write_repairs ... ok
test managed_tmp_roots::tests::register_and_list_round_trip ... ok
test managed_tmp_roots::tests::fresh_reregistration_rewrites_nothing ... ok
test goal::ledger::tests::projection_invalidates_by_signature ... ok
test managed_tmp_roots::tests::stale_reregistration_refreshes_last_seen ... ok
test managed_tmp_roots::tests::concurrent_registrations_merge ... ok
test managed_tmp_roots::tests::missing_roots_are_pruned_on_next_write ... ok
test bead::mutation::tests::store::event_backed_child_id_reuse_after_remove_matches_jsonl_semantics ... ok
test bead::mutation::tests::view_core::view_core_create_with_initial_note_stays_warm ... ok
test bead::mutation::tests::view_core::view_core_allocation_edge_cases_match_oracle ... ok
test bead::mutation::tests::store::locked_load_prunes_removed_flag_tombstone_skipped_by_reads ... ok
test bead::mutation::tests::view_core::view_core_children_order_matches_replay_on_created_at_ties ... ok
test goal::ledger::tests::probe_counts_real_opens_across_a_thousand_goals ... ok
test bead::mutation::tests::store::one_mutation_touches_only_the_mutated_stream_file ... ok
test bead::read_model::tests::backdated_append_falls_back_to_rebuild ... ok
test bead::mutation::tests::store::sase_mk_blast_radius_regression_preserves_unrelated_stream_bytes ... ok
test memory_history::tests::asset_generated_and_managed_flags ... ok
test memory_history::tests::causes::co_rendered_instruction_names_lint_source ... ok
test memory_history::tests::causes::non_instruction_versions_keep_an_empty_cause ... ok
test memory_history::tests::cache_queries::feed_query_merges_synced_scopes ... ok
test memory_history::tests::causes::config_commit_marks_config_cause ... ok
test memory_history::tests::causes::regen_only_commit_has_empty_cause ... ok
test memory_history::tests::cache_queries::resolve_historical_path_and_predating_commit ... ok
test memory_history::tests::cache_queries::compare_promotion_reports_type_change ... ok
test memory_history::tests::cache_queries::sync_round_trip_is_fresh_with_same_subjects ... ok
test memory_history::tests::cache_queries::upstream_ahead_is_none_then_one ... ok
test memory_history::tests::cache_queries::blob_selector_resolves_newest_match_on_corpus ... ok
test memory_history::tests::classify::committed_versions_classify_per_priority_table ... ok
test memory_history::tests::causes::renderer_commit_marks_renderer_cause ... ok
test memory_history::tests::cache_queries::timeline_dirty_worktree_has_uncommitted_without_ordinal ... ok
test memory_history::tests::cache_queries::corrupt_snapshot_rebuilds_and_parses ... ok
test memory_history::tests::cache_queries::key_mismatch_rebuilds_and_then_is_fresh ... ok
test memory_history::tests::cache_queries::version_selectors_and_bodies ... ok
test memory_history::tests::cache_queries::incremental_fold_equals_cold_rebuild ... ok
test memory_history::tests::classify::created_words_match_document_word_count ... ok
test goal::ledger::tests::probe_shows_zero_settled_opens ... ok
test memory_history::tests::classify::frontmatter_only_phrase_names_changed_key ... ok
test memory_history::tests::classify::content_rename_is_visible_and_pure_move_is_not_authored ... ok
test memory_history::tests::review::store_filename_lives_outside_the_snapshot_cache ... ok
test memory_history::tests::review::first_use_has_no_watermark_and_zero_new ... ok
test memory_history::tests::review::corrupt_store_reads_empty_reports_and_stays_put ... ok
test memory_history::tests::review::mark_rejects_an_empty_state_dir ... ok
test migration::digest::tests::fingerprint_is_stable_for_object_key_order ... ok
test migration::digest::tests::tree_digest_changes_when_file_content_changes ... ok
test migration::gate_bundles::tests::converts_settled_v2_and_recomputes_request_hash ... ok
test migration::gate_bundles::tests::python_canonical_hash_matches_known_v2_fixture ... ok
test migration::gate_bundles::tests::refuses_in_flight_v2_and_v1 ... ok
test migration::gate_bundles::tests::v3_is_noop ... ok
test migration::journal::tests::replay_advances_to_resume_point ... ok
test migration::journal::tests::replay_refuses_backward_journal_transition ... ok
test migration::journal::tests::replay_refuses_digest_movement ... ok
test migration::manifest::tests::expected_source_digests_include_operation_entries ... ok
test migration::manifest::tests::manifest_preserves_unknown_extension_fields ... ok
test migration::patch_records::tests::canonical_input_is_a_noop ... ok
test migration::patch_records::tests::convert_legacy_headings_sections_and_review_labels ... ok
test migration::patch_records::tests::description_body_is_not_rewritten ... ok
test migration::patch_records::tests::destination_exists_and_digest_mismatch_refuse ... ok
test migration::patch_records::tests::fingerprint_is_stable_json ... ok
test migration::patch_records::tests::gp_extension_renames_to_sase ... ok
test migration::patch_records::tests::mixed_document_converts_each_record_independently ... ok
test migration::patch_records::tests::mixed_spellings_in_one_record_refuse ... ok
test migration::procs::tests::reconcile_matches_task_id_to_canonical_proc_id ... ok
test migration::procs::tests::reconcile_reports_missing_and_conflicting_rows ... ok
test migration::residue::tests::classifier_archives_only_inert_residue_with_counterpart ... ok
test migration::residue::tests::classifier_refuses_live_references ... ok
test migration::tests::bounded_lock_wraps_store_lock ... ok
test mobile_pairing::crypto::tests::pairing_code_is_six_digits ... ok
test mobile_pairing::crypto::tests::pairing_id_has_at_least_128_bits ... ok
test mobile_pairing::crypto::tests::secret_hash_is_domain_separated_from_id_hash ... ok
test memory_history::tests::review::mark_unknown_commit_errors_without_touching_the_store ... ok
test mobile_pairing::tests::consume_missing_store_is_rejected_and_does_not_create ... ok
test mobile_pairing::tests::concurrent_valid_finish_mints_at_most_one_accept ... ok
test mobile_pairing::tests::corrupt_store_fails_closed ... ok
test mobile_pairing::tests::empty_consume_fields_are_rejected_without_creating_store ... ok
test mobile_pairing::tests::expired_challenge_burns_matching_id ... ok
test mobile_pairing::tests::failed_second_write_leaves_first_challenge_intact ... ok
test mobile_pairing::tests::insecure_lock_file_is_rejected ... ok
test mobile_pairing::tests::insecure_preexisting_store_file_is_rejected ... ok
test mobile_pairing::tests::issue_and_consume_debug_redacts_secrets ... ok
test mobile_pairing::tests::issue_then_consume_accepts_once ... ok
test mobile_pairing::tests::pairing_dir_symlink_is_rejected ... ok
test mobile_pairing::tests::schema_mismatch_is_rejected ... ok
test mobile_pairing::tests::store_file_hard_link_is_rejected ... ok
test mobile_pairing::tests::store_file_symlink_is_rejected ... ok
test mobile_pairing::tests::symlink_state_root_alias_issues_and_consumes ... ok
test mobile_pairing::tests::world_writable_containing_dir_is_rejected ... ok
test mobile_pairing::tests::wrong_code_burns_matching_id ... ok
test mobile_pairing::trust::tests::other_user_containing_dir_is_rejected ... ok
test mobile_pairing::trust::tests::owner_controlled_0755_containing_dir_is_trusted ... ok
test mobile_pairing::trust::tests::protected_dir_requires_owner_0700 ... ok
test mobile_pairing::trust::tests::protected_file_rejects_hard_links_and_wrong_mode ... ok
test mobile_pairing::trust::tests::root_owned_sticky_tmp_is_trusted ... ok
test mobile_pairing::trust::tests::root_owned_world_writable_without_sticky_is_rejected ... ok
test mobile_pairing::trust::tests::world_writable_owner_dir_is_rejected ... ok
test model_completion::tests::filters_values_aliases_and_provider_scopes_in_catalog_order ... ok
test model_completion::tests::old_catalog_rows_deserialize_with_additive_defaults ... ok
test model_completion::tests::scoped_candidates_preserve_filter_text ... ok
test model_route::tests::empty_or_blank_explicit_model_falls_through_to_config ... ok
test model_route::tests::maps_every_phase_size_to_the_public_alias ... ok
test model_route::tests::rejects_invalid_and_retired_size_names ... ok
test model_route::tests::rejects_invalid_counts_thresholds_and_targets ... ok
test model_route::tests::selects_explicit_epic_land_model_over_threshold ... ok
test model_route::tests::uses_big_target_at_and_above_threshold ... ok
test model_route::tests::wire_json_uses_config_field_source_names ... ok
test model_route::tests::zero_phase_count_is_valid_and_selects_the_normal_target ... ok
test model_validity::classifier::tests::accepts_the_corpus ... ok
test model_validity::classifier::tests::effort_step6_keeps_generic_and_provider_messages ... ok
test model_validity::classifier::tests::malformed_snapshot_is_an_error ... ok
test model_validity::classifier::tests::rejects_with_canonical_messages ... ok
test note_attachment::public_objects::tests::canonical_table_is_pinned ... ok
test note_attachment::public_objects::tests::public_and_old_path_forms_round_trip ... ok
test note_attachment::tests::audience::rule_eight_public_evidence ... ok
test note_attachment::tests::audience::rule_five_private_provenance ... ok
test note_attachment::tests::audience::rule_five_skipped_inside_public_checkout ... ok

running 1 test
test note_attachment::tests::audience::rule_four_scan_hits ... ok
test note_attachment::tests::audience::rule_nine_stdin_fails_private ... ok
test note_attachment::tests::audience::rule_one_sensitive_path_refuses ... ok
test note_attachment::tests::audience::rule_seven_unverified_media ... ok
test mobile_pairing::tests::issue_under_permissive_umask_creates_restrictive_modes ... ok

test result: ok. 1 passed; 0 failed; 0 ignored; 0 measured; 5359 filtered outtest note_attachment::tests::audience::rule_six_opaque_types ... ok
; finished in 0.00s

test note_attachment::tests::audience::rule_three_size_cap_never_widens ... ok
test note_attachment::tests::audience::rule_two_explicit_private_and_local_only ... ok
test note_attachment::tests::audience::rule_zero_private_store_never_widens ... ok
test note_attachment::tests::audience::widening_agent_refuses_human_confirms ... ok
test note_attachment::tests::byte_offsets_use_utf8_for_multibyte_prefix ... ok
test note_attachment::tests::classify_extension_table_and_fallbacks ... ok
test note_attachment::tests::classify_magic_wins_over_extension ... ok
test mobile_pairing::tests::issue_under_permissive_umask_creates_restrictive_modes ... ok
test note_attachment::tests::inverse_property_holds_for_hand_cases ... ok
test memory_history::tests::review::review_state_rejects_empty_scopes ... ok
test note_attachment::tests::manifest::auto_fetch_cap_is_inclusive ... ok
test note_attachment::tests::manifest::manifest_rejects_bad_sha ... ok
test note_attachment::tests::manifest::manifest_rejects_duplicate_names ... ok
test note_attachment::tests::manifest::manifest_rejects_missing_token ... ok
test note_attachment::tests::manifest::manifest_rejects_orphan_descriptor ... ok
test note_attachment::tests::manifest::manifest_rejects_unsanitized_name_and_bad_mime ... ok
test note_attachment::tests::manifest::manifest_validates_matching_tokens ... ok
test note_attachment::tests::manifest::manifest_validates_repeated_token_with_one_descriptor ... ok
test note_attachment::tests::manifest::placement_picks_first_accepting_tier ... ok
test note_attachment::tests::manifest::sensitive_paths_are_refused ... ok
test note_attachment::tests::manifest::tombstone_round_trips_and_validates ... ok
test note_attachment::tests::oracle_table ... ok
test note_attachment::tests::sanitize_collapses_and_preserves_extension ... ok
test note_attachment::tests::sanitize_truncates_long_names ... ok
test note_attachment::tests::scan_wire_schema_version_is_one ... ok
test note_attachment::tests::inverse_property_holds_for_seeded_corpus ... ok
test note_attachment::tests::secret_scanner::chunk_straddling_value_is_found ... ok
test note_attachment::tests::secret_scanner::clean_text_is_clean ... ok
test memory_history::tests::classify::promotion_summary_phrase_and_word_counts ... ok
test bead::read_model::tests::config_change_falls_back_to_rebuild ... ok
test note_attachment::tests::secret_scanner::known_env_value_hits ... ok
test note_attachment::tests::corpus_golden_matches_fixtures ... ok
test note_attachment::tests::secret_scanner::credential_patterns_hit ... ok
test note_attachment::tests::secret_scanner::env_dump_windows_hit ... ok
test memory_history::tests::review::marks_merge_across_scopes_in_one_store ... ok
test note_attachment::tests::secret_scanner::rules_version_is_one ... ok
test note_attachment::tests::stored_tokens_match_predicate_outside_literal_zones ... ok
test note_attachment::tests::uniquify_reuses_same_digest_and_bumps_on_conflict ... ok
test note_attachment::tests::visibility::explicit_public_survives ... ok
test note_attachment::tests::visibility::old_shaped_descriptors_reduce_to_private ... ok
test note_attachment::tests::visibility::unknown_visibility_falls_back_to_private ... ok
test note_attachment::tests::visibility::visibility_wire_is_snake_case ... ok
test note_attachment::zones::tests::home_personal_zones ... ok
test note_attachment::zones::tests::personal_and_publishable_zones ... ok
test notifications::mobile::tests::action_result_contract_snapshot_is_stable ... ok
test notifications::mobile::tests::custom_gate_notification_contract_snapshot_is_stable ... ok
test notifications::mobile::tests::epic_notification_contract_snapshot_is_stable ... ok
test notifications::mobile::tests::gate_action_request_option_inputs_round_trips ... ok
test notifications::mobile::tests::gate_action_string_mapping_is_complete ... ok
test notifications::mobile::tests::every_non_question_gate_projects_the_same_branch_wire ... ok
test notifications::mobile::tests::gate_envelope_version_acceptance_is_bounded ... ok
test notifications::mobile::tests::launch_approval_detail_exposes_preview_identity ... ok
test notifications::mobile::tests::planner_errors_are_deterministic ... ok
test notifications::mobile::tests::prefix_resolution_makes_collisions_explicit ... ok
test notifications::mobile::tests::priority_and_error_classifiers_are_disjoint ... ok
test note_attachment::zones::tests::secret_files_match_exactly ... ok
test notifications::mobile::tests::question_planner_supports_index_label_id_and_custom_answers ... ok
test notifications::mobile::tests::mobile_notification_contract_snapshot_is_stable ... ok
test notifications::mobile::tests::schema_version_3_envelope_with_declared_inputs_yields_branches ... ok
test notifications::pending_actions::tests::custom_gate_without_bundle_path_has_missing_target_state ... ok
test notifications::pending_actions::tests::custom_gate_uses_only_neutral_terminal_files ... ok
test notifications::pending_actions::tests::epic_approval_without_response_dir_has_missing_target_state ... ok
test notifications::pending_actions::tests::launch_approval_is_a_pending_action_kind ... ok
test notifications::pending_actions::tests::epic_approval_is_typed_and_resolves_through_pending_store ... ok
test notifications::pending_actions::tests::pending_state_detects_stale_and_external_plan_response ... ok
test notifications::pending_actions::tests::pending_store_merges_legacy_telegram_shape ... ok
test notifications::rules::tests::a_rule_that_sets_nothing_never_decides_anything ... ok
test notifications::rules::tests::action_criterion_matches_empty_string_for_action_less_rows ... ok
test notifications::rules::tests::bare_star_matches_everything_including_empty ... ok
test notifications::rules::tests::batch_resolution_equals_per_row_resolution_in_row_order ... ok
test notifications::rules::tests::beads_tab_rule_silences_task_triage_and_not_axe_errors ... ok
test notifications::rules::tests::bracketed_metacharacter_is_a_literal ... ok
test notifications::rules::tests::built_in_delivery_is_toast_and_bell_decided_by_no_rule ... ok
test notifications::rules::tests::class_dash_is_literal_at_either_edge ... ok
test notifications::rules::tests::classes_match_members_and_ranges ... ok
test notifications::rules::tests::criteria_accept_a_bare_string_or_a_list_and_reject_other_shapes ... ok
test notifications::rules::tests::criteria_are_all_of_and_lists_are_any_of ... ok
test notifications::rules::tests::delivery_serializes_with_a_tagged_sound ... ok
test notifications::rules::tests::earlier_rule_wins_a_field_and_later_rules_cannot_reopen_it ... ok
test notifications::rules::tests::empty_criterion_list_matches_nothing ... ok
test notifications::rules::tests::empty_pattern_matches_only_empty_text ... ok
test notifications::rules::tests::equal_priorities_keep_list_order_and_negative_priority_goes_last ... ok
test notifications::rules::tests::first_match_per_field_takes_one_field_from_each_rule ... ok
test notifications::rules::tests::gates_alias_is_normalized_only_when_it_is_the_whole_value ... ok
test notifications::rules::tests::gates_and_hitl_select_the_same_rows_in_any_case ... ok
test notifications::rules::tests::glob_has_no_implicit_substring_match ... ok
test notifications::rules::tests::glob_matches_exact_text_case_insensitively ... ok
test notifications::rules::tests::leading_close_bracket_is_a_member ... ok
test notifications::rules::tests::muted_and_snoozed_rows_are_reachable_by_their_synthetic_tabs ... ok
test notifications::rules::tests::negated_classes_exclude_members ... ok
test notifications::rules::tests::no_rules_keep_toast_and_bell_for_every_survey_row ... ok
test notifications::rules::tests::non_ascii_is_matched_per_character_and_case_folded ... ok
test bead::mutation::tests::view_core::view_core_update_external_ref_change_stays_warm ... ok
test notifications::rules::tests::omitted_or_empty_match_matches_every_row ... ok
test notifications::rules::tests::priority_moves_a_later_rule_ahead_of_an_earlier_one ... ok
test notifications::rules::tests::question_mark_matches_exactly_one_character ... ok
test notifications::rules::tests::reversed_range_contains_nothing ... ok
test notifications::rules::tests::rule_defaults_and_wire_shapes_round_trip ... ok
test notifications::rules::tests::rule_label_index_ignores_priority_reordering ... ok
test notifications::rules::tests::pathological_pattern_stays_linearish ... ok
test notifications::rules::tests::silence_everything_except_gates_needs_no_negation ... ok
test notifications::rules::tests::sound_settings_parse_reserved_words_and_paths ... ok
test notifications::rules::tests::star_backtracks_across_repeated_prefixes ... ok
test notifications::rules::tests::tags_match_any_tag_not_just_the_first ... ok
test notifications::rules::tests::suppressing_one_tab_leaves_every_other_survey_row_alone ... ok
test notifications::rules::tests::telegram_only_rule_is_effective_and_not_a_no_op ... ok
test notifications::rules::tests::telegram_defaults_to_true_and_resolves_independently ... ok
test notifications::rules::tests::telegram_rejects_non_boolean_shapes ... ok
test notifications::rules::tests::telegram_rule_after_tui_rule_still_applies ... ok
test notifications::rules::tests::telegram_suppression_serializes_and_legacy_payloads_default_true ... ok
test notifications::rules::tests::title_is_empty_and_note_matches_nothing_for_a_note_less_row ... ok
test notifications::rules::tests::unclosed_bracket_is_a_literal ... ok
test notifications::rules::tests::title_is_the_first_note_and_note_is_any_note ... ok
test notifications::rules::tests::unknown_criterion_keys_are_rejected_not_ignored ... ok
test notifications::rules::tests::unknown_rule_keys_are_rejected_not_ignored ... ok
test notifications::rules::tests::unnamed_rules_are_labelled_by_list_position ... ok
test notifications::tabs::tests::a_non_panel_row_does_not_donate_a_panel_icon ... ok
test notifications::tabs::tests::a_resurfaced_row_donates_its_color_over_a_newer_sent_row ... ok
test notifications::tabs::tests::a_panel_and_tag_collision_sorts_as_a_panel_either_way ... ok
test notifications::tabs::tests::a_resurfaced_row_donates_its_icon_over_a_newer_sent_row ... ok
test notifications::tabs::tests::a_row_donates_its_icon_only_to_its_declared_panel_tab ... ok
test notifications::tabs::tests::a_snoozed_row_leaves_its_panel_tab ... ok
test notifications::tabs::tests::a_tab_wears_the_newest_declared_color_and_ignores_junk ... ok
test notifications::tabs::tests::a_tab_wears_the_newest_declared_icon_and_ignores_junk ... ok
test notifications::tabs::tests::a_two_tag_row_lands_in_exactly_one_tab ... ok
test notifications::tabs::tests::an_absent_color_stays_absent_on_the_wire ... ok
test notifications::tabs::tests::an_absent_icon_stays_absent_on_the_wire ... ok
test notifications::tabs::tests::counts_and_tabs_agree_and_skip_read_or_silent_rows ... ok
test notifications::tabs::tests::declared_panel_outranks_hitl_errors_and_tags ... ok
test notifications::tabs::tests::hitl_then_errors_then_first_tag_then_general ... ok
test notifications::tabs::tests::labels_title_case_tag_words ... ok
test notifications::tabs::tests::oldest_activity_and_next_wake_are_minimums ... ok
test notifications::tabs::tests::snoozed_precedes_muted_for_a_muted_row_with_a_wake_time ... ok
test notifications::tabs::tests::reserved_and_malformed_panels_fall_through ... ok
test notifications::tabs::tests::tab_order_matches_the_panel ... ok
test parser::tests::description_preserves_internal_blank_lines_then_trims ... ok
test parser::tests::drops_incomplete_specs_missing_name_or_status ... ok
test parser::tests::empty_input_yields_no_specs ... ok
test parser::tests::empty_value_lines_become_none_or_empty_per_python_rules ... ok
test notifications::pending_actions::tests::cleanup_stale_pending_actions_removes_only_expired_entries ... ok
test parser::tests::indented_blank_run_in_description_does_not_end_spec ... ok
test parser::tests::invalid_utf8_returns_parse_error_wire ... ok
test notifications::pending_actions::tests::pending_store_registers_and_resolves_prefixes ... ok
test parser::tests::legacy_changespec_header_detection_requires_whitespace_then_word ... ok
test parser::tests::legacy_changespec_header_separates_specs_without_blank_lines ... ok
test parser::tests::missing_or_invalid_project_name_metadata_stays_absent ... ok
test parser::tests::missing_refs_section_defaults_to_empty ... ok
test parser::tests::multi_line_description_strips_two_space_continuation ... ok
test parser::tests::new_name_inside_a_spec_starts_a_new_spec ... ok
test parser::tests::parent_cl_pr_bug_scalars_round_trip ... ok
test note_attachment::tests::secret_scanner::long_lines_are_bounded ... ok
test parser::tests::parses_direct_name_spec_without_header ... ok
test parser::tests::parses_headered_spec_with_inline_description ... ok
test parser::tests::patch_header_detection_accepts_canonical_and_legacy_headers ... ok
test parser::tests::pr_origin_scalars_round_trip_and_absence_defaults_unknown ... ok
test parser::tests::project_basename_strips_extension_and_archive_suffix ... ok
test parser::tests::project_name_metadata_is_stamped_on_every_patch ... ok
test parser::tests::refs_parse_at_end_of_spec ... ok
test parser::tests::refs_parse_in_canonical_position_and_preserve_raw_invalid_text ... ok
test parser::tests::rust_end_line_is_real_not_placeholder ... ok
test parser::tests::save_pending_entries_flushes_at_field_boundary ... ok
test parser::tests::span_excludes_trailing_blank_separator ... ok
test parser::tests::legacy_commits_section_still_parses_as_stitches ... ok
test parser::tests::two_blank_lines_separate_specs ... ok
test pending_commit_checkpoint::tests::complete_checkpoint_is_none ... ok
test pending_commit_checkpoint::tests::foreign_agent_fails ... ok
test pending_commit_checkpoint::tests::foreign_pending_checkpoint_fails ... ok
test pending_commit_checkpoint::tests::foreign_run_fails ... ok
test parser::tests::parse_patch_project_bytes_emits_canonical_patch_wire ... ok
test pending_commit_checkpoint::tests::legacy_with_independent_proof_resumes ... ok
test pending_commit_checkpoint::tests::legacy_without_proof_fails ... ok
test pending_commit_checkpoint::tests::missing_checkpoint_is_none ... ok
test pending_commit_checkpoint::tests::missing_current_identity_fails ... ok
test pending_commit_checkpoint::tests::pending_after_hook_resumes ... ok
test parser::tests::both_parse_apis_keep_json_for_canonical_and_legacy_input ... ok
test pending_commit_checkpoint::tests::pending_dispatch_without_sha_still_resumes ... ok
test pending_commit_checkpoint::tests::same_subject_different_body_fails ... ok
test pending_commit_checkpoint::tests::subject_mismatch_fails ... ok
test pending_commit_checkpoint::tests::unpushed_without_sha_fails ... ok
test note_attachment::tests::secret_scanner::known_value_name_filtering ... ok
test perf_logs::aggregate::tests::absent_and_empty_sources_are_covered_without_failure ... ok
test note_attachment::tests::secret_scanner::over_cap_and_binary_skip ... ok
test perf_logs::aggregate::tests::byte_cap_truncates_tail_without_counting_leading_fragment ... ok
test perf_logs::aggregate::tests::malformed_timestamp_and_partial_trailing_lines_are_reported ... ok
test plan::artifact_link::tests::artifacts_is_compatible_with_either_counterpart_section ... ok
test plan::artifact_link::tests::artifacts_is_list_shaped_and_orders_between_agents_and_commits ... ok
test perf_logs::aggregate::tests::percentile_edges_use_nearest_rank_rounding ... ok
test perf_logs::aggregate::tests::record_cap_marks_source_truncated ... ok
test perf_logs::aggregate::tests::aggregates_mixed_timestamp_formats_and_window ... ok
test plan::artifact_link::tests::back_compat_single_legacy_and_mixed_cases ... ok
test plan::artifact_link::tests::bead_section_supports_linked_unlinked_and_prettier_wrapped_labels ... ok
test plan::artifact_link::tests::discontiguous_header_groups_before_body_content_are_invalid ... ok
test plan::artifact_link::tests::empty_list_section_is_omitted ... ok
test plan::artifact_link::tests::bead_upsert_keeps_bead_frontmatter ... ok
test plan::artifact_link::tests::escapes_labels_and_trailing_text ... ok
test plan::artifact_link::tests::extra_leading_blank_line_is_recognized_as_noncanonical_layout ... ok
test plan::artifact_link::tests::fenced_header_example_is_not_a_live_document_header ... ok
test plan::artifact_link::tests::known_header_labels_after_body_content_are_ordinary_bullets ... ok
test plan::artifact_link::tests::ordinary_bold_and_nested_body_bullets_are_not_header_sections ... ok
test plan::artifact_link::tests::legacy_upsert_preserves_frontmatter_body_and_other_sections ... ok
test plan::artifact_link::tests::plan_and_prompt_sections_accept_absolute_cross_repo_targets ... ok
test plan::artifact_link::tests::multi_section_round_trip_uses_fixed_order ... ok
test plan::artifact_link::tests::parses_prettier_wrapped_commit_and_preserves_unchanged_bytes ... ok
test plan::artifact_link::tests::rejects_malformed_duplicate_unknown_and_unterminated_documents ... ok
test plan::artifact_link::tests::parent_upsert_removes_only_legacy_top_level_parent ... ok
test plan::artifact_link::tests::title_before_header_means_the_bullet_is_body_content ... ok
test plan::artifact_link::tests::remove_section_keeps_the_rest_and_canonical_layout ... ok
test plan::decisions::callout::tests::adjacent_headers_start_adjacent_spans ... ok
test plan::artifact_link::tests::list_cap_is_visible_and_round_trips_logically ... ok
test plan::decisions::callout::tests::bare_memory_dir_without_a_path_is_not_a_signal ... ok
test plan::decisions::callout::tests::branch_header_with_later_equals_keeps_first_token ... ok
test plan::decisions::callout::tests::fence_boundary_ends_callouts_with_delimiter_lengths ... ok
test plan::decisions::callout::tests::fenced_headers_and_mentions_are_ignored ... ok
test plan::decisions::callout::tests::headers_missing_a_token_take_it_from_following_prose ... ok
test plan::decisions::callout::tests::headers_parse_with_branches_and_prose ... ok
test plan::decisions::callout::tests::mentions_need_whole_words ... ok
test plan::decisions::callout::tests::memory_signals_cover_init_paths_disclaimers_and_code ... ok
test plan::decisions::callout::tests::missing_id_or_branch_is_still_reported ... ok
test plan::decisions::callout::tests::prettier_joined_toggle_header_has_no_branch ... ok
test plan::decisions::callout::tests::spans_end_at_the_blockquote_boundary ... ok
test plan::decisions::callout::tests::trailing_prose_never_changes_the_parsed_header ... ok
test plan::decisions::callout::tests::unicode_prose_does_not_panic_and_reports_edits ... ok
test plan::decisions::quote::tests::contiguous_three_word_quote_verifies_with_identity ... ok
test plan::decisions::quote::tests::empty_sources_and_zero_overlap_yield_no_hint ... ok
test plan::decisions::quote::tests::greek_sigma_folds_across_positions ... ok
test plan::decisions::quote::tests::negated_sentence_is_still_a_lexical_match ... ok
test plan::decisions::quote::tests::halves_split_across_two_texts_do_not_verify ... ok
test plan::decisions::quote::tests::noncontiguous_halves_do_not_verify ... ok
test plan::decisions::quote::tests::partial_words_never_match ... ok
test plan::decisions::quote::tests::sentence_splitter_keeps_original_text ... ok
test plan::decisions::quote::tests::sentences_span_newlines_and_md_names_survive ... ok
test plan::decisions::quote::tests::two_word_quote_never_verifies_but_still_suggests ... ok
test plan::decisions::quote::tests::suggestion_ties_stay_stable_by_input_order ... ok
test plan::decisions::quote::tests::unicode_normalization_matches_across_forms ... ok
test plan::decisions::resolver::tests::payload_claim_not_found_clamps_to_false ... ok
test plan::decisions::resolver::tests::payload_clamps_unverified_memory_but_keeps_authored_default ... ok
test plan::decisions::resolver::tests::payload_correction_keeps_true_default ... ok
test plan::decisions::resolver::tests::payload_freezes_verified_memory_true ... ok
test plan::decisions::resolver::tests::payload_inherited_provenance_keeps_true_default ... ok
test plan::decisions::resolver::tests::payload_missing_facts_fail_closed ... ok
test plan::decisions::resolver::tests::payload_preserves_frozen_strand_lists ... ok
test memory_history::tests::review::unknown_watermark_commit_falls_back_to_time ... ok
test plan::decisions::resolver::tests::digest_round_trips_missing_optionals ... ok
test plan::decisions::resolver::tests::payload_rejects_unknown_provenance ... ok
test plan::decisions::resolver::tests::digest_ignores_key_order_but_moves_on_content ... ok
test plan::decisions::resolver::tests::resolve_accumulates_unknown_ids_and_invalid_values ... ok
test plan::decisions::resolver::tests::resolve_agent_boundary ... ok
test plan::decisions::resolver::tests::resolve_auto_ignores_valid_overrides_but_keeps_errors ... ok
test plan::decisions::resolver::tests::resolve_canonicalizes_choice_case_without_prefix_match ... ok
test plan::decisions::resolver::tests::payload_omits_corrects_from_json_when_none ... ok
test plan::decisions::resolver::tests::resolve_marks_clamped_omitted_memory ... ok
test plan::decisions::resolver::tests::resolve_omitted_and_explicit_defaults_agree_on_values ... ok
test plan::decisions::resolver::tests::resolve_omitted_takes_effective_defaults ... ok
test plan::decisions::resolver::tests::resolve_rejects_non_boolean_toggles ... ok
test plan::decisions::resolver::tests::toggle_helper_builds_plain_decisions ... ok
test plan::decisions::resolver::tests::resolve_rejects_unknown_caller_and_non_object ... ok
test plan::decisions::sheet::tests::block_carries_inherited_authorization_without_local_rows ... ok
test plan::decisions::sheet::tests::block_quotes_frontmatter_text_without_new_lines ... ok
test plan::decisions::sheet::tests::block_headers_name_every_surface_and_caller_honestly ... ok
test plan::decisions::sheet::tests::auto_follow_ups_only_for_unrequested_memory_off ... ok
test plan::decisions::sheet::tests::block_rejects_unknown_enums_and_malformed_inherited ... ok
test plan::decisions::sheet::tests::block_reviewer_names_branches_and_memory_grants ... ok
test plan::decisions::sheet::tests::empty_sheet_counts_zero_but_keeps_revision ... ok
test plan::decisions::sheet::tests::block_routes_declined_memory_follow_ups_by_audience ... ok
test plan::decisions::sheet::tests::sheet_canonicalizes_choice_keys_case_insensitively ... ok
test plan::decisions::sheet::tests::sheet_clamps_unverified_memory_but_keeps_authored_default ... ok
test plan::decisions::sheet::tests::sheet_pairs_values_with_effective_defaults ... ok
test plan::decisions::sheet::tests::sheet_rejects_malformed_vectors_instead_of_coercing ... ok
test plan::decisions::sheet::tests::sheet_row_keeps_unverified_quotes_out_of_authorization ... ok
test plan::decisions::sheet::tests::summary_full_dedupes_memory_selectors_in_order ... ok
test plan::decisions::sheet::tests::summary_full_matches_the_design_sentence ... ok
test plan::decisions::sheet::tests::sheet_rejects_unknown_provenance_kinds_and_shapes ... ok
test plan::decisions::sheet::tests::summary_full_names_declined_memory_honestly ... ok
test plan::decisions::sheet::tests::summary_full_omits_the_clause_without_memory_decisions ... ok
test plan::decisions::sheet::tests::summary_full_renders_every_verdict ... ok
test plan::decisions::sheet::tests::summary_rejects_unknown_verdicts_and_forms ... ok
test plan::decisions::sheet::tests::summary_short_counts_memory_changes_too ... ok
test plan::decisions::sheet_tests::correction_on_auto_stays_quiet_when_left_off ... ok
test plan::decisions::sheet_tests::sheet_quote_falls_back_to_corrects ... ok
test plan::decisions::sheet_tests::sheet_quote_prefers_requested_over_corrects ... ok
test plan::decisions::tests::absent_or_empty_decisions_add_no_fields ... ok
test parser::tests::full_section_parity_emits_structured_entries ... ok
test plan::decisions::tests::ask_rules_cover_shape_length_unicode_and_questions ... ok
test plan::decisions::tests::archived_heuristic_regression_phrases_match_sources ... ok
test plan::decisions::tests::archived_completeness_triggers_on_any_stamp ... ok
test plan::decisions::tests::decisions_work_on_epics_with_callouts ... ok
test plan::decisions::tests::decision_source_lines_point_at_block_yaml ... ok
test plan::decisions::tests::corrects_is_memory_only_bounded_exclusive_and_justifies_true ... ok
test plan::decisions::tests::decisions_must_be_an_ordered_map_of_at_most_five ... ok
test plan::decisions::tests::choice_counts_keys_and_labels_are_checked ... ok
test plan::decisions::tests::answers_and_stamps_depend_on_mode ... ok
test plan::decisions::tests::callout_branches_validate_against_definitions ... ok
test plan::decisions::tests::duplicate_yaml_keys_stay_rejected ... ok
test plan::decisions::tests::fenced_callout_boundary_does_not_absorb_later_quote ... ok
test plan::decisions::tests::prettier_joined_toggle_callout_with_equals_in_prose_validates ... ok
test plan::decisions::tests::full_toggle_choice_and_memory_wire_is_ordered ... ok
test plan::decisions::tests::phase_when_is_always_reserved ... ok
test plan::decisions::tests::defaults_are_required_and_kind_checked ... ok
test plan::decisions::tests::unknown_decision_fields_are_errors ... ok
test plan::decisions::tests::unicode_body_checks_run_through_the_public_validator ... ok
test plan::decisions::tests::unreferenced_decisions_warn_unless_mentioned ... ok
test plan::decisions::tests::why_is_bounded_and_forbidden_on_memory ... ok
test plan::decisions::tests::requested_is_memory_only_bounded_and_required_for_true ... ok
test plan::decisions::tests::memory_is_for_toggles_with_valid_selectors ... ok
test plan::decisions::tests::uncovered_memory_edits_warn_until_covered ... ok
test plan::decisions::tests::id_spelling_reserved_words_and_types_are_rejected ... ok
test plan::decisions::tests::warning_only_ask_preserves_full_decision_wire ... ok
test plan::read::tests::empty_kind_filter_selects_no_repo_plans ... ok
test plan::read::tests::derives_title_from_h1_then_humanized_name ... ok
test plan::read::tests::discovers_local_flat_and_sharded_layout ... ok
test plan::read::tests::discovers_every_repo_kind_with_labels_and_relpaths ... ok
test plan::read::tests::accepts_rfc3339_and_date_only_create_time ... ok
test plan::read::tests::canonical_plans_are_tier_classified_with_tale_fallback ... ok
test plan::read::tests::explicit_empty_corpora_disable_the_legacy_repo_scan ... ok
test plan::read::tests::explicit_document_corpora_include_one_bundle_level_shallow_first ... ok
test plan::read::tests::explicit_document_corpora_replace_legacy_scan_and_keep_own_relpaths ... ok
test plan::read::tests::falls_back_to_mtime_when_create_time_absent ... ok
test plan::read::tests::missing_roots_yield_no_plans_without_error ... ok
test plan::read::tests::ignores_non_markdown_files ... ok
test plan::read::tests::filters_repo_corpus_by_kind ... ok
test plan::read::tests::kind_filter_does_not_constrain_local_plans ... ok
test plan::read::tests::explicit_document_corpora_skip_prompt_specs_dotdirs_and_deeper_files ... ok
test plan::read::tests::explicit_plans_corpus_honors_tier_and_other_labels_ignore_it ... ok
test plan::read::tests::prompt_directory_projects_plan_bullet_label ... ok
test plan::read::tests::projects_canonical_prompt_link_label_without_polluting_plan_content ... ok
test plan::read::tests::parses_frontmatter_fields_and_normalizes_created_at ... ok
test plan::refs::tests::alias_prefix_reparses_as_canonical ... ok
test plan::refs::tests::canonicalize_uses_first_matching_root ... ok
test plan::read::tests::tolerates_malformed_and_absent_frontmatter ... ok
test plan::read::tests::sorts_files_within_a_shard ... ok
test plan::read::tests::repo_plans_precede_local_plans ... ok
test plan::refs::tests::every_legacy_form_resolves_to_the_same_file ... ok
test plan::refs::tests::typed_reference_rejects_unsafe_payloads_and_unknown_kinds ... ok
test plan::refs::tests::typed_reference_round_trips ... ok
test plan::refs::tests::unregistered_schemes_and_paths_remain_legacy ... ok
test plan::search::tests::applies_limit_after_ranking ... ok
test plan::refs::tests::validation_messages_remain_stable_after_helper_extraction ... ok
test plan::search::tests::blank_query_is_treated_as_browse ... ok
test plan::search::tests::browse_mode_returns_all_plans_sorted_by_recency ... ok
test plan::search::tests::counterpart_label_remains_searchable_as_frontmatter_metadata ... ok
test plan::search::tests::date_range_filters_inclusively_on_day_bounds ... ok
test plan::search::tests::excludes_plans_without_dates_when_date_filter_active ... ok
test plan::search::tests::explicit_sort_modes_override_defaults ... ok
test plan::search::tests::field_names_constant_matches_searchable_fields ... ok
test plan::search::tests::filters_status_source_and_date_together ... ok
test plan::search::tests::matches_case_insensitive_unicode_substrings ... ok
test plan::search::tests::no_match_returns_empty_results ... ok
test plan::search::tests::matches_every_searchable_field ... ok
test plan::search::tests::parses_relative_and_partial_date_bounds ... ok
test plan::refs::tests::missing_keeps_ordered_best_candidates ... ok
test plan::refs::tests::multiple_month_drift_matches_are_ambiguous ... ok
test plan::refs::tests::unique_month_drift_resolves ... ok
test plan::refs::tests::exact_resolution_uses_first_root ... ok
test plan::read::tests::tier_frontmatter_classifies_canonical_plans_and_filters_post_parse ... ok
test plan::search::tests::ranks_title_above_frontmatter_above_body ... ok
test plan::search::tests::recency_breaks_relevance_ties ... ok
test plan::search::tests::public_search_filters_across_explicit_corpus_labels ... ok
test plan::search::tests::rejects_invalid_date_bound ... ok
test plan::search::tests::rejects_unknown_sort_mode ... ok
test plan::search::tests::relative_months_clamp_to_month_length ... ok
test plan::search::tests::repo_outranks_local_on_equal_relevance ... ok
test plan::search::tests::source_filter_scopes_results ... ok
test plan::search::tests::status_filter_is_case_insensitive ... ok
test plan::search::tests::status_value_is_reported_as_status_not_frontmatter ... ok
test plan::search::tests::public_search_reads_ranks_and_prioritizes_repo ... ok
test plan::read::tests::mixed_transition_projects_label_only_when_paths_agree ... ok
test plan::search::tests::zero_limit_is_unlimited ... ok
test plan::search::tests::public_search_kind_filter_narrows_repo_only ... ok
test plan::validate::tests::common_field_rules_report_together_with_locations ... ok
test plan::validate::tests::a_well_formed_or_absent_header_block_raises_nothing ... ok
test plan::validate::tests::links_frontmatter_is_accepted_as_a_transient_authoring_inlet ... ok
test plan::validate::tests::epic_missing_collection_and_phase_scalar_rules_report ... ok
test plan::validate::tests::epic_top_level_rules_all_report ... ok
test plan::validate::tests::legacy_changespec_frontmatter_key_validates_as_patch ... ok
test plan::validate::tests::missing_phase_description_warns_without_changing_the_plan ... ok
test plan::validate::tests::missing_wrong_type_and_invalid_tier_are_distinct ... ok
test plan::validate::tests::both_tiers_require_a_non_empty_string_title ... ok
test plan::validate::tests::other_header_block_defects_are_located_errors ... ok
test plan::validate::tests::phase_ids_and_dependency_graph_rules_report_in_one_pass ... ok
test plan::validate::tests::phase_optional_fields_validate_types_and_model_syntax ... ok
test plan::validate::tests::phase_shape_keys_and_required_fields_report ... ok
test plan::validate::tests::parent_bead_is_optional_epic_only_and_type_checked ... ok
test plan::validate::tests::schema_is_ordered_and_contains_exact_phase_guidance ... ok
test plan::validate::tests::managed_plan_links_are_optional_on_both_tiers_and_type_checked ... ok
test plan::validate::tests::a_malformed_header_block_does_not_hide_frontmatter_diagnostics ... ok
test plan::validate::tests::tale_epic_fields_are_inert_warnings ... ok
test plan::validate::tests::unsupported_caller_tier_is_a_usage_error ... ok
test plan::validate::tests::structural_diagnostics_cover_each_rule ... ok
test plan::validate::tests::valid_tale_returns_normalized_plan_and_accepts_system_fields ... ok
test plan::validate::tests::managed_plan_proposer_is_optional_normalized_and_type_checked ... ok
test plan::validate::tests::valid_epic_returns_all_normalized_fields ... ok
test plan::validate::tests::trailing_text_in_a_link_section_is_a_located_error ... ok
test procs::runtime::tests::failed_store_read_preserves_runtime_dirs ... ok
test bead::mutation::tests::view_core::view_core_note_edit_and_remove_stay_warm ... ok
test plan::validate::tests::phase_size_is_strict_for_authoring_and_legacy_safe_for_launch ... ok
test procs::runtime::tests::missing_store_refuses_to_sweep_preexisting_runtime_tree ... ok
test procs::runtime::tests::malformed_store_refuses_to_sweep_runtime_tree ... ok
test plan::validate::tests::tale_size_is_required_strict_and_normalized ... ok
test plan::validate::tests::machine_local_project_field_validates_and_round_trips_in_every_mode ... ok
test procs::runtime::tests::mixed_validity_store_refuses_to_sweep_runtime_tree ... ok
test memory_history::tests::review::mark_counts_strict_descendants ... ok
test procs::settlement::tests::legacy_request_without_outcome_still_deserializes ... ok
test procs::runtime::tests::valid_empty_store_allows_rowless_orphan_sweep ... ok
test procs::runtime::tests::unreadable_runtime_tree_is_reported_and_preserved ... ok
test procs::runtime::tests::pruned_runtime_delete_revalidates_against_new_rows ... ok
test procs::runtime::tests::fresh_and_retained_runtime_dirs_are_preserved ... ok
test procs::settlement::tests::wrong_supervisor_cannot_begin_settlement ... ok
test procs::settlement::tests::bare_store_exit_code_is_not_an_observation ... ok
test procs::settlement::tests::first_observation_freezes_atomically_with_settling_transition ... ok
test procs::settlement::tests::conflicting_authoritative_observation_is_rejected ... ok
test memory_history::tests::classify::provenance_agent_bead_types_and_boilerplate ... ok
test procs::settlement::tests::legacy_sidecar_is_adopted_once ... ok
test procs::store::tests::invalid_service_blocks_are_rejected_on_create ... ok
test memory_history::tests::classify::reflow_has_zero_volume_and_empty_word_counts ... ok
test procs::settlement::tests::identical_replay_keeps_original_timestamp ... ok
test procs::store::tests::legacy_commandless_tui_rows_remain_readable ... ok
test bead::mutation::tests::view_core::view_core_update_reopen_reopens_ancestors_warm ... ok
test procs::store::tests::proc_reserve_wire_emits_canonical_name_keys ... ok
test procs::store::tests::proc_update_wire_emits_canonical_name_keys ... ok
test bead::mutation::tests::view_core::view_core_edit_attachments_replace_keep_and_detach ... ok
test procs::store::tests::proc_wire_emits_canonical_name_keys_and_accepts_legacy_spellings ... ok
test procs::store::tests::proc_without_service_block_serializes_without_service_key ... ok
test procs::store::tests::prompt_proc_meta_emits_canonical_name_key_and_accepts_legacy ... ok
test procs::store::tests::prompt_proc_field_accepts_both_spellings_and_emits_canonical ... ok
test procs::store::tests::detached_kind_round_trips_and_unknown_kinds_are_rejected ... ok
test procs::store::tests::conflict_keys_treat_shell_prefix_as_named_proc_prefix ... ok
test procs::store::tests::retention_gives_command_line_procs_their_own_bucket ... ok
test procs::store::tests::legacy_proc_shell_lifecycle_spelling_stores_canonical_value ... ok
test procs::store::tests::retention_keeps_newest_terminal_rows_per_named_service ... ok
test procs::store::tests::retention_keeps_tagged_named_service_procs_in_service_buckets ... ok
test procs::settlement::tests::supervisor_loss_fallback_cannot_replace_frozen_success ... ok
test procs::store::tests::held_exclusive_lock_bounds_reader_and_writer_waits ... ok
test procs::store::tests::append_and_read_round_trip_is_newest_first_and_normalizes_tags ... ok
test procs::settlement::tests::terminal_rows_are_not_converted_by_sidecar_adoption ... ok
test memory_history::tests::delete_and_recreate_keeps_subject_with_gap ... ok
test memory_history::tests::feed::co_rendered_changeset_splits_authored_and_consequence ... ok
test project_onboarding::plan_tests::add_fresh_clone_is_ready_with_checkout_manage_and_init ... ok
test project_onboarding::plan_tests::add_remote_not_found_is_blocked ... ok
test procs::store::tests::legacy_task_id_rows_are_accepted_and_rewritten_with_proc_id ... ok
test procs::store::tests::reserve_replays_identical_proc_request_and_rejects_conflicts ... ok
test memory_history::tests::pathspecs_are_sorted_deduped_and_validated ... ok
test memory_history::tests::feed::hidden_versions_leave_default_feed_and_return_with_hidden ... ok
test project_onboarding::plan_tests::add_remote_unavailable_without_matching_checkout_is_unknown ... ok
test project_onboarding::plan_tests::add_remote_unavailable_with_matching_checkout_is_a_warning ... ok
test project_onboarding::plan_tests::agent_auto_setup_does_not_adopt_a_human_journal_obligation ... ok
test project_onboarding::plan_tests::auto_setup_with_unknown_push_warns ... ok
test project_onboarding::plan_tests::auto_setup_from_an_agent_is_off ... ok
test project_onboarding::plan_tests::auto_setup_without_push_rights_warns_not_launchable ... ok
test project_onboarding::plan_tests::auto_setup_on_a_managed_repo_skips_init ... ok
test project_onboarding::plan_tests::bare_git_key_collision_is_name_taken_without_suffix ... ok
test project_onboarding::plan_tests::config_dirty_and_wrong_branch_block_manage ... ok
test project_onboarding::plan_tests::create_agent_is_human_only ... ok
test project_onboarding::plan_tests::create_remote_is_pending_when_not_found ... ok
test project_onboarding::plan_tests::create_remote_unavailable_is_unknown ... ok
test project_onboarding::plan_tests::empty_dir_is_pending_checkout ... ok
test project_onboarding::plan_tests::explicit_setup_from_an_agent_is_human_only ... ok
test project_onboarding::plan_tests::explicit_setup_off_on_unmanaged_separate_repo_warns ... ok
test project_onboarding::plan_tests::explicit_setup_on_managed_repo_keeps_init_pending ... ok
test project_onboarding::plan_tests::explicit_setup_without_push_rights_is_blocked ... ok
test project_onboarding::plan_tests::fingerprint_changes_with_requested_name_and_ignores_facts ... ok
test project_onboarding::plan_tests::fingerprint_is_stable_across_step_states ... ok
test project_onboarding::plan_tests::found_remote_without_journal_is_remote_exists ... ok
test project_onboarding::plan_tests::gh_key_collision_uses_dash_two_suffix ... ok
test project_onboarding::plan_tests::home_is_reserved_and_allocates_a_suffix ... ok
test project_onboarding::plan_tests::identity_is_pending_when_requested_name_differs ... ok
test project_onboarding::plan_tests::identity_is_skipped_when_requested_matches_record ... ok
test project_onboarding::plan_tests::in_tree_init_does_not_require_tty ... ok
test project_onboarding::plan_tests::invalid_requested_name_is_blocked ... ok
test project_onboarding::plan_tests::journal_repo_id_match_adopts_the_remote ... ok
test project_onboarding::plan_tests::journal_without_id_adopts_empty_remote_of_requested_visibility ... ok
test project_onboarding::plan_tests::journal_without_id_does_not_adopt_a_non_empty_remote ... ok
test project_onboarding::plan_tests::local_managed_counts_as_managed ... ok
test project_onboarding::plan_tests::make_current_is_pending ... ok
test project_onboarding::plan_tests::matching_clone_with_record_is_done ... ok
test project_onboarding::plan_tests::matching_clone_without_record_registers ... ok
test project_onboarding::plan_tests::matching_intent_keeps_its_setup_obligation_after_marker_write ... ok
test project_onboarding::plan_tests::mismatch_and_not_git_are_checkout_conflicts ... ok
test project_onboarding::plan_tests::no_create_rights_and_invalid_options_block_create ... ok
test project_onboarding::plan_tests::plan_schema_mismatch_is_rejected ... ok
test project_onboarding::plan_tests::own_record_is_excluded_from_collision_checks ... ok
test project_onboarding::plan_tests::recovery_ownership_does_not_waive_other_blockers ... ok
test project_onboarding::plan_tests::reenable_is_pending_for_a_disabled_record ... ok
test bead::read_model::tests::freshness_stamp_loses_to_in_place_invalidation ... ok
test memory_history::tests::feed::init_boilerplate_is_flagged_and_kept_in_default_feed ... ok
test project_onboarding::plan_tests::taken_alias_is_blocked_with_suggestion ... ok
test project_onboarding::plan_tests::resume_after_checkout_continues_at_manage ... ok
test project_onboarding::plan_tests::unknown_mode_is_rejected ... ok
test project_onboarding::plan_tests::status_is_current_when_only_handoff_is_pending ... ok
test project_onboarding::plan_tests::taken_requested_name_suggests_underscore_suffix ... ok
test project_onboarding::tests::all_numbered_local_set_stays_hidden_as_numbered_copy ... ok
test project_onboarding::tests::defaults_fill_effective_options_and_bools_normalize ... ok
test project_onboarding::tests::empty_groups_are_omitted_and_namespaces_pass_through ... ok
test project_onboarding::tests::disabled_choice_and_invalid_choice ... ok
test project_onboarding::tests::failed_journal_is_resume ... ok
test project_onboarding::tests::form_schema_mismatch_and_bad_mode_are_rejected ... ok
test project_onboarding::tests::getter_reports_schema_version ... ok
test project_onboarding::tests::fork_and_archived_are_hidden ... ok
test project_onboarding::tests::enabled_project_is_search_only_and_disabled_gets_a_group ... ok
test project_onboarding::tests::explicit_false_on_default_true_bool_is_kept_in_both_modes ... ok
test project_onboarding::tests::identity_casefold_merges_remote_and_local ... ok
test project_onboarding::tests::include_all_branches_is_available_with_template ... ok
test project_onboarding::tests::inventory_only_identity_seeds_no_selectable_row ... ok
test project_onboarding::tests::linked_inventory_forms_the_linked_group_and_chip ... ok
test project_onboarding::tests::include_all_branches_requires_template ... ok
test project_onboarding::tests::namespaces_pass_through_on_classified_output ... ok
test project_onboarding::tests::numbered_copy_and_third_party_local_are_hidden ... ok
test project_onboarding::tests::owned_local_clone_is_local_group ... ok
test project_onboarding::tests::primary_checkout_plus_numbered_sibling_stays_local_in_both_orders ... ok
test project_onboarding::tests::ranking_display_tie_is_casefolded_ascending ... ok
test project_onboarding::tests::ranking_uses_open_count_then_recency_then_display ... ok
test project_onboarding::tests::schema_mismatch_is_rejected ... ok
test project_onboarding::tests::required_empty_field_errors ... ok
test project_onboarding::tests::resume_journal_beats_other_rules_and_complete_is_ignored ... ok
test project_onboarding::tests::search_kind_accepts_typed_values ... ok
test project_onboarding::tests::sibling_project_is_hidden_as_enabled_project ... ok
test project_onboarding::tests::sidecar_by_inventory_is_hidden ... ok
test project_onboarding::tests::sidecar_by_role_suffix_is_hidden ... ok
test project_onboarding::tests::strict_conflict_when_excluded_field_is_supplied ... ok
test project_onboarding::tests::template_excludes_readme_gitignore_license_and_team ... ok
test project_spec::tests::archive_detection_accepts_canonical_and_legacy_extensions ... ok
test project_onboarding::tests::unknown_option_is_an_error ... ok
test project_onboarding::tests::user_repo_with_non_role_double_dash_stays_suggested ... ok
test project_onboarding::tests::strict_ignores_off_values_of_excluded_fields_but_keeps_conflicts ... ok
test project_spec::tests::lifecycle_project_ref_collisions_flag_case_variant_keys_and_home ... ok
test project_onboarding::tests::strict_template_plus_excluded_field_table ... ok
test project_spec::tests::lifecycle_read_accepts_canonical_disabled_state ... ok
test project_spec::tests::lifecycle_read_accepts_canonical_sibling_state ... ok
test project_spec::tests::lifecycle_read_defaults_missing_state_to_enabled ... ok
test project_spec::tests::lifecycle_read_normalizes_legacy_enabled_and_disabled_states ... ok
test project_spec::tests::lifecycle_read_warns_and_defaults_invalid_state ... ok
test project_spec::tests::lifecycle_read_warns_on_duplicate_state ... ok
test project_spec::tests::lifecycle_update_accepts_sibling_target_state ... ok
test project_spec::tests::lifecycle_update_inserts_before_first_name ... ok
test project_spec::tests::lifecycle_update_inserts_before_running_and_preserves_crlf ... ok
test project_spec::tests::lifecycle_update_normalizes_legacy_target_states ... ok
test project_spec::tests::lifecycle_update_rejects_invalid_target_state ... ok
test project_spec::tests::lifecycle_update_replaces_existing_state_line ... ok
test project_spec::tests::project_aliases_read_defaults_missing_aliases_to_empty ... ok
test project_spec::tests::project_aliases_read_sorts_dedupes_and_warns ... ok
test project_spec::tests::project_aliases_update_inserts_before_first_name ... ok
test project_spec::tests::project_aliases_update_inserts_before_running_and_preserves_crlf ... ok
test project_spec::tests::project_aliases_update_rejects_invalid_or_duplicate_aliases ... ok
test project_spec::tests::project_aliases_update_removes_existing_aliases ... ok
test project_spec::tests::project_aliases_update_replaces_existing_aliases_sorted ... ok
test project_spec::tests::project_name_read_accepts_missing_and_present_name ... ok
test project_spec::tests::project_name_read_warns_on_invalid_and_duplicate_names ... ok
test project_spec::tests::project_name_update_inserts_replaces_and_removes_name ... ok
test project_spec::tests::project_name_update_preserves_crlf_and_rejects_invalid_name ... ok
test project_spec::tests::project_spec_basename_accepts_active_and_archive_extensions ... ok
test project_spec::tests::project_spec_filenames_are_canonical_sase ... ok
test project_spec::tests::project_spec_path_conversions_emit_canonical_extension ... ok
test project_stats::aggregate::tests::model_table_always_includes_unknown_and_no_agent_zero_rows ... ok
test project_stats::aggregate::tests::resolved_rows_sort_by_count_then_provider_and_model ... ok
test project_stats::attribution::tests::absent_agent_is_no_agent_even_with_a_model_tag ... ok
test project_stats::attribution::tests::authoritative_model_tag_splits_at_the_first_slash ... ok
test project_stats::attribution::tests::empty_directory_yields_page_unpublished_for_unstamped_agent_commits ... ok
test project_stats::attribution::tests::directory_lookups_follow_sha_then_code_page_then_name_then_family ... ok
test project_stats::attribution::tests::known_aliases_are_flagged_without_rewriting_the_recorded_model ... ok
test project_stats::attribution::tests::malformed_model_tags_do_not_fall_back_to_the_directory ... ok
test project_stats::attribution::tests::plan_attribution_prefers_proposed_with_then_plan_page ... ok
test project_stats::classify_tests::classification_preserves_non_utf8_paths_without_lossy_collisions ... ok
test project_stats::classify_tests::classifies_agent_context_docs_config_tests_source_and_other ... ok
test project_stats::classify_tests::directory_rules_keep_programming_languages_in_code_roles ... ok
test project_stats::classify_tests::generated_and_vendored_heuristics_precede_ordinary_roles ... ok
test project_stats::classify_tests::explicit_attribute_values_override_or_suppress_path_heuristics ... ok
test project_stats::classify_tests::parses_all_boolean_attribute_states_without_conflating_false_and_missing ... ok
test project_stats::classify_tests::safety_exclusions_and_skipped_entry_modes_cannot_be_overridden ... ok
test project_stats::classify_tests::recognizes_known_and_bounded_env_shebang_languages ... ok
test procs::store::tests::unknown_service_values_load_and_remain_updatable ... ok
test project_spec::tests::lifecycle_project_ref_collisions_are_case_insensitive_and_reserve_home ... ok
test project_spec::tests::lifecycle_project_ref_collisions_exclude_siblings ... ok
test procs::store::tests::unknown_fields_are_tolerated_and_malformed_rows_are_dropped_on_rewrite ... ok
test project_spec::tests::lifecycle_project_records_include_aliases_and_collision_warnings ... ok
test project_spec::tests::lifecycle_project_records_classify_true_projects_and_vcs_kind ... ok
test project_spec::tests::lifecycle_project_records_filter_and_sort_projects ... ok
test memory_history::tests::feed::regen_only_agents_commit_is_regen_only ... ok
test memory_history::tests::feed::roster_add_keeps_note_authored_and_roster_consequence ... ok
test memory_history::tests::feed::roster_only_edit_folds_as_regen_only ... ok
test project_stats::code_query_tests::no_configured_code_repos_is_an_empty_population ... ok
test procs::store::tests::reserve_copies_service_block_and_update_preserves_it ... ok
test procs::store::tests::prompt_proc_meta_preserves_label_provenance ... ok
test memory_history::tests::historical_paths_alias_to_subjects ... ok
test memory_history::tests::feed::since_and_limit_cut_the_merged_list ... ok
test procs::settlement::tests::mismatched_or_corrupt_sidecar_keeps_loss_fallback ... ok
test procs::store::tests::updating_an_existing_row_to_the_detached_kind_validates ... ok
test project_stats::counter_tests::extension_selects_parser_even_when_classifier_labels_are_equal ... ok
test project_stats::counter_tests::nonblank_counter_handles_empty_whitespace_crlf_and_final_line ... ok
test project_stats::counter_tests::mixed_language_counts_include_embedded_code_and_exclude_its_comments ... ok
test project_stats::counter_tests::pinned_tokei_counts_single_line_triple_quoted_strings_as_code ... ok
test project_stats::counter_tests::sloc_excludes_comments_and_multiline_docstrings_but_retains_nonblank ... ok
test project_stats::code_query_tests::empty_repo_is_measured_zero_and_missing_repo_is_null ... ok
test project_stats::directory_tests::measured_directory_on_sase_agents_sidecar ... ignored, manual cold/warm directory measurement; not a CI timing gate
test procs::store::tests::terminal_transition_guards_and_repeat_writes_preserve_final_fields ... ok
test procs::store::tests::running_rows_survive_retention ... ok
test procs::store::tests::retention_reports_only_store_owned_logs_for_deletion ... ok
test memory_history::tests::feed::merge_orders_home_between_project_commits ... ok
test project_stats::code_query_tests::records_snapshot_is_metadata_only ... ok
test procs::store::tests::retention_keeps_newest_terminal_rows_at_and_beyond_limit ... ok
test project_stats::git::tests::empty_repository_resolves_without_fabricating_head ... ok
test project_stats::git::tests::read_blobs_empty_oids_does_not_invoke_git ... ok
test project_stats::code_query_tests::mixed_availability_keeps_measured_sources ... ok
test project_stats::code_query_tests::code_only_populates_snapshots_without_output ... ok
test procs::store::tests::named_proc_lifecycle_requires_settlement_and_single_supervisor_finish ... ok
test project_stats::code_query_tests::code_only_does_not_walk_history ... ok
test project_stats::git::tests::canonical_path_aliases_and_ordered_refs_are_respected ... ok
test project_stats::git::tests::unsafe_revision_tokens_are_rejected ... ok
test project_stats::history::tests::framing_keeps_only_complete_records_and_splits_four_separators ... ok
test project_stats::git::tests::nested_and_missing_paths_do_not_resolve_to_an_ancestor ... ok
test project_stats::code_query_tests::output_only_does_not_read_blobs_or_attributes ... ok
test project_stats::code_query_tests::role_and_language_sums_and_zero_denominator ... ok
test project_stats::code_query_tests::successful_clone_is_preferred_over_a_failed_clone ... ok
test project_stats::code_query_tests::agreeing_clones_do_not_emit_a_tip_disagreement ... ok
test project_stats::git::tests::inherited_git_dir_does_not_reroute_resolution ... ok
test project_stats::code_query_tests::combined_request_merges_status_without_promoting_failures ... ok
test project_stats::code_query_tests::failed_clone_at_another_tip_does_not_trigger_disagreement ... ok
test project_stats::plans::tests::build_index_failure_is_unmeasured_and_not_cached ... ok
test project_stats::history::tests::failed_walk_after_resolution_is_failed_not_partial ... ok
test project_stats::history::tests::cache_write_failure_does_not_discard_measured_history ... ok
test project_stats::git::tests::read_blobs_packs_by_size_and_skips_missing_or_oversize ... ok
test project_stats::code_query_tests::fingerprint_ignores_cache_warmth_and_dirty_files ... ok
test project_stats::plans::tests::blob_read_failure_is_an_error_not_an_empty_list ... ok
test project_stats::query_tests::acceptance_harness_rejects_core_and_missing_paths ... ok
test project_stats::history::tests::footer_attribution_uses_first_normalized_tags_and_link_labels ... ok
test project_stats::query_tests::all_missing_sources_serialize_null_counts ... ok
test project_stats::code_query_tests::fingerprint_changes_when_the_selected_tip_moves ... ok
test project_stats::code_query_tests::languages_merge_from_totals_not_shares ... ok
test memory_history::tests::subject_ids_after_full_history ... ok
test memory_history::tests::shim_convergence_aliases_without_a_row ... ok
test bead::read_model::tests::mutation_invalidates_and_rebuilds ... ok
test bead::mutation::tests::view_core::view_core_update_batch_external_ref_exchange_stays_warm ... ok
test project_stats::code_query_tests::clones_do_not_double_count_and_are_request_order_stable ... ok
test bead::read_model::tests::schemaless_cache_file_heals_on_next_read ... ok
test bead::read_model::tests::invalidation_never_unlinks_a_live_cache ... ok
test project_stats::query_tests::measured_history_acceptance_on_sase_checkout ... ignored, manual cold/warm measurement; not a CI timing gate
test project_stats::plans_tests::unresolved_sidecar_does_not_count_primary_repository_plans ... ok
test project_stats::directory_tests::empty_page_metadata_and_mixed_family_models ... ok
test bead::read_model::tests::rebuild_and_serve_round_trip ... ok
test project_stats::code_query_tests::records_do_not_enter_code_totals_or_models ... ok
test project_stats::query_tests::repeated_missing_paths_keep_their_issue_names ... ok
test project_stats::history::tests::full_dag_includes_both_sides_of_a_merge ... ok
test project_stats::plans_tests::sidecar_root_counts_plans_without_a_directory_prefix ... ok
test project_stats::history::tests::rewritten_history_rebuilds_instead_of_folding_old_rows ... ok
test bead::mutation::tests::proof_bounded::proof_counter_only_config_change_keeps_tail_open ... ok
test project_stats::plans_tests::sidecar_root_counts_plans_that_exceed_one_blob_batch ... ok
test project_stats::history::tests::corrupt_and_wrong_schema_entries_rebuild_from_git ... ok
test project_stats::history::tests::shallow_clone_reports_incomplete_older_coverage ... ok
test bead::read_model::tests::rewritten_stream_falls_back_to_rebuild ... ok
test project_stats::history::tests::incremental_history_matches_a_cold_full_walk ... ok
test project_stats::plans_tests::re_proposal_credits_standing_frontmatter_and_range_uses_first_add ... ok
test project_stats::query_tests::empty_repository_is_measured_zero ... ok
test project_stats::history::tests::disk_cache_reloads_after_process_memo_is_cleared ... ok
test project_stats::records_tests::empty_repository_has_zero_counts_and_null_time_bounds ... ok
test project_stats::query_tests::empty_range_on_nonempty_history_is_measured_zero ... ok
test procs::store::tests::concurrent_writers_do_not_lose_rows ... ok
test project_stats::directory_tests::index_only_agent_resolves_and_published_page_wins ... ok
test project_stats::query_tests::both_footer_spellings_and_authoritative_model_tags ... ok
test project_stats::snapshot::attributes::tests::isolated_init_uses_object_format_and_disables_user_configuration ... ok
test project_stats::query_tests::malformed_repeated_prose_and_absent_agent_model_tags ... ok
test project_stats::snapshot::attributes::tests::rejects_unknown_attribute_values ... ok
test project_stats::snapshot::attributes::tests::parses_nul_triplets_for_the_three_linguist_attributes ... ok
test project_stats::snapshot::blobs::tests::packs_batches_by_framing_and_output_budget ... ok
test project_stats::snapshot::blobs::tests::parses_present_blobs_and_rejects_missing_or_truncated ... ok
test project_stats::snapshot::blobs::tests::rejects_a_blob_that_cannot_fit_the_output_budget ... ok
test project_stats::plans_tests::first_add_survives_rename_and_later_edits_are_not_double_counted ... ok
hint: Using 'master' as the name for the initial branch. This default branch name
hint: is subject to change. To configure the initial branch name to use in all
hint: of your new repositories, which will suppress this warning, call:
hint:
hint: 	git config --global init.defaultBranch <name>
hint:
hint: Names commonly chosen instead of 'master' are 'main', 'trunk' and
hint: 'development'. The just-created branch can be renamed via this command:
hint:
hint: 	git branch -m <name>
Initialized empty Git repository in /home/bryan/.cache/sase/tmp/agent-tmp/gh_sase-org__sase-ws14-261024_085653/.tmprDL1Qj/isolated.git/
test project_stats::history::tests::cache_hit_reuses_complete_equal_tip_without_rewalking_history ... ok
test project_stats::snapshot::attributes::tests::empty_template_argument_disables_template_copying ... ok
test project_stats::query_tests::new_york_dst_author_days_are_bucketed_locally ... ok
test project_stats::query_tests::half_open_range_and_non_monotonic_clocks ... ok
test project_stats::records_tests::shallow_summary_is_partial_and_not_cached_as_complete ... ok
test project_stats::query_tests::same_tip_aliases_keep_their_selected_ref_names ... ok
test project_stats::runs_tests::missing_index_is_an_issue_and_leaves_runs_null ... ok
test project_stats::query_tests::merges_are_included_in_output_counts ... ok
test project_stats::directory_tests::sha_beats_name_and_code_member_is_preferred ... ok
test project_stats::plans_tests::plan_member_lookup_uses_plan_role_page ... ok
test project_stats::records_tests::records_summary_counts_blobs_and_author_time_bounds ... ok
test bead::mutation::tests::proof_bounded::proof_history_noop_and_invalid_batch_leave_bytes_untouched ... ok
test project_stats::query_tests::cold_warm_and_cache_disabled_results_share_fingerprint_and_data ... ok
test project_stats::records_tests::successful_metadata_is_cached_by_tip ... ok
test project_stats::query_tests::all_facets_serialize_code_and_keep_runs_null_without_an_index ... ok
test project_stats::query_tests::record_repos_are_visible_and_excluded_from_code_totals ... ok
test bead::mutation::tests::proof_bounded::proof_history_guarded_close_fails_without_writing ... ok
test bead::mutation::tests::proof_bounded::proof_history_close_with_note_stays_bounded ... ok
test project_stats::snapshot::tree::tests::parses_nul_separated_paths_without_whitespace_splitting ... ok
test project_stats::snapshot::tree::tests::preserves_non_utf8_paths ... ok
test project_stats::snapshot::tree::tests::rejects_unterminated_and_malformed_records ... ok
test project_stats::tests::code_contract_distinguishes_unavailable_from_measured_empty ... ok
test project_stats::tests::enums_use_snake_case_and_cover_contract_variants ... ok
test project_stats::tests::full_request_and_response_contracts_round_trip ... ok
test project_stats::tests::nullable_facets_are_serialized_as_explicit_nulls ... ok
test project_stats::tests::previous_cached_code_and_snapshot_shapes_still_deserialize ... ok
test project_stats::tests::request_and_response_support_every_project_state ... ok
test project_stats::tests::unavailable_code_is_present_and_fingerprint_ignores_cache_dir ... ok
test project_stats::tests::validation_checks_versions_ranges_timezone_bounds_and_identities ... ok
test project_tag::tests::accept_counts_refs_inside_rejected_glued_matches ... ok
test project_tag::tests::accept_handles_multibyte_text ... ok
test project_tag::tests::accept_keeps_alternation_branches_intact ... ok
test project_tag::tests::accept_keeps_heading_lines ... ok
test project_tag::tests::accept_keeps_line_breaks_around_end_of_line_refs ... ok
test project_tag::tests::accept_keeps_pr_spelling_at_target_or_leading ... ok
test project_tag::tests::accept_preserves_whitespace_newlines_and_unicode ... ok
test project_stats::plans_tests::local_storage_is_null_and_shared_store_filters_by_project ... ok
test project_stats::snapshot::tests::empty_repository_is_a_valid_empty_snapshot ... ok
test project_tag::tests::accept_removes_mid_line_refs_like_the_python_guard ... ok
test project_tag::tests::accept_removes_multiple_targets_leaving_one ... ok
test project_tag::tests::accept_reports_caret_just_after_insertion ... ok
test project_tag::tests::accept_skips_literal_zones ... ok
test project_tag::tests::accept_puts_selection_at_earliest_target_or_leading_position ... ok
test project_tag::tests::accept_switches_projects_within_one_segment ... ok
test project_tag::tests::accept_with_empty_workflow_names_matches_nothing ... ok
test project_tag::tests::expand_leaves_unresolvable_tags_but_reports_them ... ok
test project_tag::tests::expand_never_errors_on_plain_text ... ok
test project_tag::tests::expand_rewrites_resolved_tags_in_place ... ok
test project_tag::tests::resolve_dedupes_suggestions_fully ... ok
test project_tag::tests::resolve_matches_exact_then_casefold ... ok
test project_tag::tests::accept_uses_leading_position_with_frontmatter_and_directives ... ok
test project_tag::tests::resolve_reports_ambiguous_targets ... ok
test project_tag::tests::resolve_suggests_known_tags ... ok
test project_tag::tests::accept_targets_existing_tag_before_and_after_trigger ... ok
test project_tag::tests::scan_accepts_d1_shapes ... ok
test project_tag::tests::scan_chmod_plus_x_is_lexical_but_unresolvable ... ok
test project_tag::tests::scan_handles_multibyte_text ... ok
test project_tag::tests::scan_rejects_d1_non_tags ... ok
test project_tag::tests::trigger_fires_at_d1_boundaries ... ok
test project_tag::tests::scan_skips_literal_zones ... ok
test project_tag::tests::scan_detects_anchored_tags ... ok
test project_tag::tests::trigger_rejects_non_boundaries ... ok
test prompt_archive::tests::invalid_headers_are_per_file_parse_errors ... ok
test prompt_artifact::tests::manifest_parse_tolerates_unknown_fields ... ok
test prompt_archive::tests::month_selector_limits_discovery_without_validating_name ... ok
test prompt_artifact::tests::manifest_round_trip_skips_bad_and_future_lines ... ok
test prompt_archive::tests::inventories_sorted_prompt_markdown_files ... ok
test prompt_artifact::tests::pool_names_cover_paths_unicode_extensions_and_length ... ok
test prompt_artifact::tests::rewrite_does_not_allocate_for_absent_tokens ... ok
test prompt_artifact::tests::rewrite_reserves_existing_definitions_and_numeric_uses ... ok
test prompt_artifact::tests::rewrite_is_idempotent_and_reports_only_linked_records ... ok
test prompt_artifact::tests::rewrite_shares_labels_for_one_destination ... ok
test prompt_artifact::tests::rewrite_reuses_matching_existing_definition ... ok
test prompt_artifact::tests::rewrite_skips_literal_zones_and_existing_markdown_links ... ok
test project_stats::records_tests::merge_history_counts_all_parents_and_uses_author_time_bounds ... ok
test prompt_artifact::tests::sanitized_collisions_are_disambiguated ... ok
test bead::read_model::tests::second_read_serves_without_rebuild ... ok
test prompt_artifact::tests::rewrite_uses_expanded_reference_when_authored_token_is_absent ... ok
test project_stats::records_tests::a_new_tip_refreshes_records_instead_of_reusing_the_old_entry ... ok
test prompt_history_filter::tests::empty_query_stays_empty ... ok
test prompt_artifact::tests::selection_keeps_newest_rows_in_first_reference_order ... ok
test prompt_history_filter::tests::does_not_false_match_sase_core_or_prose ... ok
test prompt_history_filter::tests::empty_value_and_unterminated_quote_are_invalid_not_unscoped ... ok
test prompt_history_filter::tests::ambiguous_label_reports_diagnostic_and_matches_nothing ... ok
test project_stats::query_tests::unknown_and_no_agent_zero_rows_and_alias_flag ... ok
test prompt_history_filter::tests::encode_parse_round_trips_arbitrary_literal_text ... ok
test prompt_history_filter::tests::leading_whitespace_before_qualifier_is_allowed ... ok
test prompt_history_filter::tests::literal_escape_prevents_qualifier_reinterpretation ... ok
test prompt_history_filter::tests::legacy_record_with_no_active_ref_stays_unscoped ... ok
test prompt_history_filter::tests::multi_segment_row_matches_if_any_segment_belongs_to_project ... ok
test prompt_history_filter::tests::plain_substring_is_unchanged_when_no_qualifier ... ok
test prompt_history_filter::tests::invalid_query_matches_nothing ... ok
test prompt_history_filter::tests::quoted_value_supports_escapes ... ok
test prompt_history_filter::tests::resolves_canonical_key_alias_and_raw_ref ... ok
test prompt_history_filter::tests::seed_with_modifier_directive_preserves_it_after_scope ... ok
test prompt_history_filter::tests::seed_resolves_ref_to_configured_project_name ... ok
test prompt_history_filter::tests::seed_with_no_ref_and_empty_draft_is_empty ... ok
test prompt_history_filter::tests::seed_with_only_ref_leaves_caret_ready_for_text ... ok
test prompt_history_filter::tests::seed_with_no_ref_and_plain_text_is_unchanged ... ok
test prompt_history_filter::tests::seed_with_unresolved_ref_keeps_text_and_shows_hint ... ok
test prompt_history_filter::tests::unknown_value_is_ordinary_empty_not_an_error ... ok
test prompt_literals::tests::ignores_unmatched_and_multiline_runs ... ok
test prompt_literals::tests::keeps_crlf_lines_independent ... ok
test prompt_literals::tests::matches_equal_runs_while_allowing_shorter_nested_runs ... ok
test prompt_history_filter::tests::text_matches_canonical_or_display_case_insensitively ... ok
test prompt_history_filter::tests::unresolved_value_matches_exact_raw_historical_ref ... ok
test prompt_literals::tests::merges_overlapping_and_adjacent_masks_once ... ok
test prompt_literals::tests::recognizes_punctuation_and_word_adjacent_spans ... ok
test prompt_literals::tests::reports_utf8_byte_offsets ... ok
test prompt_prediction::corpus::tests::excluded_words_are_never_predicted ... ok
test prompt_prediction::corpus::tests::generated_rows_are_dropped ... ok
test prompt_prediction::corpus::tests::builder_matches_compile ... ok
test prompt_prediction::corpus::tests::duplicate_text_counts_once_with_newest_epoch ... ok
test prompt_prediction::corpus::tests::legacy_heuristic_drops_generated_rows_without_origin ... ok
test prompt_prediction::corpus::tests::mass_counts_once_per_row_but_distinct_counts_rows ... ok
test prompt_prediction::corpus::tests::prune_drops_singleton_long_contexts ... ok
test prompt_prediction::corpus::tests::project_partitions_carry_same_project_mass ... ok
test prompt_prediction::corpus::tests::recency_floor_and_freshness ... ok
test prompt_prediction::corpus::tests::recency_decay_weights_newer_rows_more ... ok
test prompt_prediction::model::tests::completion_word_keeps_typed_prefix ... ok
test prompt_prediction::corpus::tests::truncation_keeps_totals_but_limits_successors ... ok
test prompt_prediction::model::tests::blocked_reasons_surface ... ok
test prompt_prediction::model::tests::predict_blocks_backtick_and_frontmatter_at_cursor ... ok
test prompt_prediction::model::tests::continuation_stops_at_max_words ... ok
test prompt_prediction::model::tests::draft_cache_informs_next_guess ... ok
test prompt_prediction::model::tests::confident_prediction_returns_ghost ... ok
test prompt_prediction::model::tests::predict_blocks_structural_and_alternation_tails ... ok
test prompt_prediction::model::tests::rank_prefix_excludes_prefix_itself ... ok
test prompt_prediction::model::tests::rank_prefix_blocks_structural_and_alternation_tails ... ok
test prompt_prediction::model::tests::sentence_final_context_never_ghosts ... ok
test prompt_prediction::model::tests::rank_prefix_matches_and_orders ... ok
test prompt_prediction::origin::tests::bead_token_with_id_directive_is_generated ... ok
test prompt_prediction::model::tests::thin_evidence_stays_silent_but_lists_candidates ... ok
test prompt_prediction::origin::tests::bead_token_without_id_directive_is_typed ... ok
test prompt_prediction::origin::tests::clan_identity_is_generated ... ok
test prompt_prediction::origin::tests::hand_assigned_tribe_is_typed ... ok
test prompt_prediction::origin::tests::land_epic_token_is_generated ... ok
test prompt_prediction::origin::tests::leading_wait_directive_is_generated ... ok
test prompt_prediction::origin::tests::legacy_routine_directives_are_generated ... ok
test prompt_prediction::model::tests::project_boost_changes_ranking ... ok
test prompt_prediction::origin::tests::mid_text_wait_is_not_enough_alone ... ok
test prompt_prediction::origin::tests::routine_tribe_binding_is_generated ... ok
test prompt_prediction::origin::tests::plain_prose_is_typed ... ok
test prompt_prediction::origin::tests::single_turn_header_is_generated ... ok
test prompt_prediction::origin::tests::work_phase_bead_token_is_generated ... ok
test prompt_prediction::origin::tests::routine_tribe_prefix_is_typed ... ok
test prompt_prediction::origin::tests::work_task_token_is_generated ... ok
test prompt_prediction::predict::tests::confidence_names_parse ... ok
test prompt_prediction::model::tests::trailing_space_keeps_word_context ... ok
test prompt_prediction::predict::tests::draft_counts_skip_final_position ... ok
test prompt_prediction::predict::tests::backoff_prefers_longer_context ... ok
test prompt_prediction::predict::tests::deterministic_ties_break_by_key ... ok
test prompt_prediction::predict::tests::project_boost_adds_mass_but_not_support ... ok
test prompt_prediction::predict::tests::reject_conflicts_toggles_higher_order_veto ... ok
test prompt_prediction::predict::tests::evidence_order_needs_a_real_word ... ok
test prompt_prediction::predict::tests::gate_boundaries_need_full_thresholds ... ok
test prompt_prediction::replay::tests::replay_handles_empty_and_single_row ... ok
test prompt_prediction::replay::tests::midword_replay_matches_production_completion ... ok
test prompt_prediction::tests::boundary_texts_stay_identical_with_the_flag ... ok
test prompt_prediction::tests::chain_runs_on_formulaic_prompts ... ok
test prompt_prediction::replay::tests::replay_matches_production_ranking_and_gate ... ok
test prompt_prediction::tests::completion_counts_draft_without_the_partial_word ... ok
test prompt_prediction::tests::completion_gates_a_typed_prefix ... ok
test prompt_prediction::tests::completion_keeps_typed_apostrophe ... ok
test prompt_prediction::tests::completion_keeps_typed_case ... ok
test prompt_prediction::tests::completion_uppercases_all_caps_suffix ... ok
test prompt_prediction::tests::eager_covers_more_than_cautious ... ok
test prompt_prediction::tests::empty_model_is_silent ... ok
test prompt_prediction::tests::exact_word_top_gives_empty_suffix_plus_continuation ... ok
test prompt_prediction::tests::excluded_words_are_never_completed ... ok
test prompt_prediction::tests::ghost_words_come_from_gated_continuation ... ok
test prompt_prediction::tests::conservative_denominator_survives_truncation ... ok
test prompt_prediction::tests::max_words_counts_the_completed_word ... ok
test prompt_prediction::tests::performance_budgets_on_representative_corpus ... ignored
test prompt_prediction::tests::rank_prefix_serves_current_word_completion ... ok
test prompt_prediction::tests::min_prefix_chars_gates_per_preset ... ok
test prompt_prediction::tests::restricted_gate_honors_conflict_veto ... ok
test prompt_prediction::tests::restricted_gate_needs_support ... ok
test prompt_prediction::tests::restricted_ties_break_by_key ... ok
test prompt_prediction::tests::structured_contexts_never_offer ... ok
test prompt_prediction::tests::restricted_gate_needs_share_and_margin ... ok
test prompt_prediction::tests::unwordable_prefixes_block_as_today ... ok
test prompt_prediction::tokenize::tests::alternation_inside_code_span_stays_inert ... ok
test prompt_prediction::tokenize::tests::blocked_contexts_at_cursor ... ok
test prompt_prediction::tokenize::tests::alternation_spans_are_excluded_and_unclosed_blocks ... ok
test prompt_prediction::tokenize::tests::canonical_surface_falls_back_for_initial_only ... ok
test prompt_prediction::tokenize::tests::canonical_surface_prefers_non_initial_casing ... ok
test prompt_prediction::tokenize::tests::canonical_surface_tie_is_deterministic ... ok
test prompt_prediction::tokenize::tests::closing_punctuation_keeps_sentence_boundary ... ok
test prompt_prediction::tokenize::tests::colon_starts_empty_context_sequence ... ok
test prompt_prediction::tokenize::tests::cursor_blocked_in_unclosed_fence ... ok
test prompt_prediction::tokenize::tests::cursor_blocked_in_unclosed_jinja ... ok
test prompt_prediction::tokenize::tests::cursor_blocked_with_no_words ... ok
test prompt_prediction::tokenize::tests::cursor_ready_after_word ... ok
test prompt_prediction::tokenize::tests::fenced_code_is_excluded ... ok
test prompt_prediction::tokenize::tests::frontmatter_is_excluded ... ok
test prompt_prediction::tokenize::tests::inline_code_is_excluded ... ok
test prompt_prediction::tokenize::tests::jinja_is_excluded ... ok
test prompt_prediction::tokenize::tests::list_and_heading_markers_start_new_sequences ... ok
test prompt_prediction::tokenize::tests::partial_word_split ... ok
test prompt_prediction::tokenize::tests::pasted_and_separator_lines_are_boundaries ... ok
test prompt_prediction::tokenize::tests::paths_urls_and_assignments_are_dropped ... ok
test prompt_prediction::tokenize::tests::plain_sentence_tokenizes_to_one_sequence ... ok
test prompt_prediction::tokenize::tests::secrets_hashes_and_digits_are_dropped ... ok
test prompt_prediction::tokenize::tests::sentence_punctuation_starts_new_sequence ... ok
test prompt_prediction::tokenize::tests::structural_tokens_are_boundaries ... ok
test prompt_prediction::tokenize::tests::word_with_trailing_space_stays_ready ... ok
test prompt_prediction::tokenize::tests::structural_tails_block_at_query_time ... ok
test prompt_prediction::wire::tests::completion_fields_default_for_old_readers ... ok
test prompt_prediction::wire::tests::completion_wire_serde_round_trip ... ok
test prompt_prediction::wire::tests::source_role_round_trip ... ok
test prompt_prediction::wire::tests::result_wire_serde_round_trip ... ok
test prompt_prediction::wire::tests::wire_defaults_match_spec ... ok
test prose_diff::tests::code_fences_compare_by_line ... ok
test prose_diff::tests::heading_breadcrumb_is_attributed ... ok
test prose_diff::tests::identical_text_produces_no_operations ... ok
test prose_diff::tests::invalid_yaml_falls_back_to_line_delta ... ok
test prompt_prediction::replay::tests::midword_report_enforces_min_prefix_chars ... ok
test prompt_prediction::replay::tests::replay_gate_presets_order_by_coverage ... ok
test prose_diff::tests::line_maps_are_monotonic ... ok
test prose_diff::tests::pure_deletion_uses_base_heading ... ok
test prompt_prediction::replay::tests::replay_warms_then_scores_later_rows ... ok
test prose_diff::tests::reflow_only_gives_zero_word_changes ... ok
test prose_diff::tests::single_word_replacement_counts_one_each ... ok
test prompt_prediction::replay::tests::replay_skips_generated_rows ... ok
test prose_diff::tests::plain_format_has_no_frontmatter_delta ... ok
test prose_diff::tests::large_document_compares_quickly ... ok
test prose_diff::tests::type_promotion_is_detected ... ok
test project_stats::records_tests::corrupted_cache_recovers_with_a_fresh_complete_measurement ... ok
test provider_disable::tests::invalid_inputs_are_rejected ... ok
test project_stats::snapshot::tests::truncated_tree_listing_is_unavailable_not_a_zero_snapshot ... ok
test prompt_prediction::replay::tests::replay_score_every_samples_rows_but_keeps_evidence ... ok
test provider_disable::tests::canonical_active_file_is_not_rewritten ... ok
test provider_disable::tests::malformed_envelope_deletes_state ... ok
test provider_disable::tests::mode_parse_accepts_exact_wire_strings ... ok
test project_stats::query_tests::divergent_refs_across_projects_union_in_the_portfolio ... ok
test project_stats::runs_tests::if_runs_drops_projects_without_runs_in_range ... ok
test project_stats::runs_tests::include_run_only_projects_appends_unregistered_index_rows ... ok
test project_stats::snapshot::tests::committed_attributes_win_over_dirty_worktree_and_info_attributes ... ok
test project_stats::runs_tests::record_repo_names_drop_run_commits_from_patch_rows ... ok
test project_stats::history::tests::truncated_walk_retries_and_never_becomes_a_complete_cache_hit ... ok
test provider_disable::tests::exact_boundary_expiry_and_until_cleared_persistence ... ok
test provider_disable::tests::malformed_and_expired_entries_are_pruned_independently ... ok
test provider_priority::tests::actually_soft_priority_target_loses_to_non_soft_backup ... ok
test provider_priority::tests::classifier_normalizes_expired_supplied_context ... ok
test provider_disable::tests::unknown_v2_mode_is_pruned_without_deleting_valid_siblings ... ok
test provider_disable::tests::concurrent_entries_are_returned_in_provider_order ... ok
test provider_disable::tests::v1_expired_record_is_pruned_during_migration ... ok
test provider_disable::tests::v1_file_migrates_in_place_to_hard_v2 ... ok
test provider_priority::tests::invalid_values_are_rejected_without_writing ... ok
test provider_priority::tests::pool_mask_all_unavailable_admits_nobody ... ok
test provider_disable::tests::try_set_returns_existing_record_without_mutating_it ... ok
test provider_priority::tests::io_failures_are_reported ... ok
test provider_priority::tests::pool_mask_keeps_priority_winner_in_the_primary_pool ... ok
test project_stats::snapshot::tests::local_user_attributes_file_does_not_contaminate_committed_policy ... ok
test provider_priority::tests::pool_mask_prefers_non_soft_when_competing_with_actual_soft ... ok
test provider_priority::tests::pool_mask_prefers_non_soft_when_priority_is_only_in_the_tail ... ok
test provider_priority::tests::pool_mask_prefers_non_soft_when_priority_provider_is_unavailable ... ok
test provider_priority::tests::pool_mask_rotates_when_every_usable_member_is_actual_soft ... ok
test provider_priority::tests::pool_mask_uses_soft_member_when_it_is_the_only_usable_primary ... ok
test provider_priority::tests::pool_policy_preserves_classified_wire_records ... ok
test provider_priority::tests::priority_provider_soft_or_hard_disable_keeps_both_causes ... ok
test provider_priority::tests::pool_policy_rejects_empty_records_and_out_of_range_index ... ok
test provider_priority::tests::precedence_table_classifies_priority_overlay ... ok
test provider_priority::tests::read_only_context_builder_filters_expired_state ... ok
test project_stats::snapshot::tests::explicit_false_overrides_suppress_path_heuristics ... ok
test provider_usage::agy::tests::empty_groups_is_authoritative_empty ... ok
test provider_usage::agy::tests::integer_fractions_are_accepted ... ok
test provider_usage::agy::tests::bad_bucket_members_are_malformed ... ok
test provider_usage::agy::tests::invalid_request_is_a_binding_error_even_for_malformed_payload ... ok
test provider_usage::agy::tests::generic_window_tokens_derive_durations ... ok
test provider_usage::agy::tests::logged_out_envelope_is_unauthenticated ... ok
test provider_usage::agy::tests::live_payload_yields_four_family_scoped_windows ... ok
test provider_usage::agy::tests::misshapen_turn_members_are_malformed ... ok
test provider_usage::agy::tests::missing_or_unexpected_status_is_malformed ... ok
test provider_usage::agy::tests::non_auth_error_envelope_is_probe_failed ... ok
test provider_usage::agy::tests::non_object_payload_is_malformed ... ok
test provider_usage::agy::tests::omitted_fraction_with_disabled_tsv_row_omits_window ... ok
test provider_usage::agy::tests::omitted_fraction_with_zero_tsv_row_is_exhausted ... ok
test provider_usage::agy::tests::omitted_fraction_without_tsv_match_is_partial ... ok
test provider_usage::agy::tests::out_of_range_fractions_are_malformed ... ok
test provider_usage::agy::tests::request_rejects_unknown_fields ... ok
test provider_usage::agy::tests::unknown_bucket_id_degrades_to_unknown_scope ... ok
test provider_usage::agy::tests::unstarted_bucket_rolling_reset_passes_through ... ok
test provider_usage::agy::tests::turn_ran_envelopes_are_vendor_drift ... ok
test provider_usage::agy::tests::unsupported_schema_version_is_binding_error ... ok
test provider_usage::grok::tests::absent_used_object_does_not_become_zero ... ok
test provider_usage::grok::tests::empty_used_object_and_explicit_zero_cent_are_zero ... ok
test provider_usage::agy::tests::vendor_banner_text_is_never_persisted ... ok
test provider_usage::grok::tests::explicit_percent_beats_conflicting_legacy_amounts ... ok
test provider_usage::grok::tests::invalid_explicit_percent_does_not_fall_back ... ok
test provider_usage::grok::tests::legacy_ratio_still_works ... ok
test provider_usage::grok::tests::missing_reset_is_partial ... ok
test provider_usage::grok::tests::omitted_zero_guards_reject_incomplete_shapes ... ok
test bead::read_model::tests::verify_cache_matches_after_rebuild ... ok
test provider_usage::grok::tests::native_plan_label_beats_camel_case ... ok
test provider_usage::grok::tests::omitted_zero_unified_monthly_and_explicit_zero_agree ... ok
test provider_usage::grok::tests::unsupported_schema_version_is_binding_error ... ok
test provider_usage::grok::tests::over_100_percent_is_preserved ... ok
test provider_usage::muse::tests::absent_usage_member_is_authoritative_empty_not_an_error ... ok
test provider_usage::grok::tests::omitted_zero_unified_weekly_is_complete ... ok
test provider_usage::muse::tests::fractional_percent_is_preserved ... ok
test provider_usage::muse::tests::invalid_request_is_a_binding_error_even_for_malformed_payload ... ok
test provider_usage::muse::tests::live_payload_yields_session_and_weekly_windows ... ok
test provider_usage::muse::tests::malformed_usage_member_is_a_structured_error ... ok
test provider_usage::muse::tests::non_object_payload_is_a_structured_error ... ok
test provider_usage::muse::tests::request_rejects_unknown_fields ... ok
test provider_usage::muse::tests::out_of_range_members_are_malformed ... ok
test provider_usage::muse::tests::missing_required_members_are_malformed ... ok
test provider_usage::muse::tests::tier_is_never_persisted ... ok
test provider_usage::muse::tests::unrelated_members_do_not_hide_absence ... ok
test provider_usage::muse::tests::unsupported_schema_version_is_binding_error ... ok
test provider_usage::muse::tests::used_percent_above_100_is_not_clamped ... ok
test provider_usage::muse::tests::vendor_values_that_fail_validation_are_malformed_not_binding_errors ... ok
test provider_usage::tests::admission_policy::adaptive_evaluation_order ... ok
test provider_usage::tests::admission_policy::admission_validation_rejects_bad_fields ... ok
test provider_usage::muse::tests::wrong_typed_members_are_malformed ... ok
test provider_usage::tests::admission_policy::hot_sources_and_passive_suppression ... ok
test provider_usage::tests::admission_policy::jitter_is_bounded_and_deterministic ... ok
test prompt_stash::store::tests::held_exclusive_lock_bounds_reader_and_writer_waits ... ok
test provider_disable::tests::try_set_replaces_an_expired_record ... ok
test provider_priority::tests::malformed_priority_degrades_with_diagnostic_and_valid_disables_survive ... ok
test provider_disable::tests::clear_one_and_missing_clear_are_idempotent ... ok
test provider_disable::tests::first_writer_wins_under_contention_without_extending_or_losing_siblings ... ok
test provider_usage::tests::agy::indicator_agy_3p_weekly_is_weekly_but_not_anchor ... ok
test provider_usage::tests::agy::indicator_agy_arm_needs_agy_provider_and_gemini_family ... ok
test provider_usage::tests::agy::indicator_selects_agy_gemini_weekly_anchor_by_default ... ok
test project_stats::query_tests::divergent_refs_union_history_without_inflating_coverage ... ok
test provider_usage::tests::attempt_policy::adaptive_policy_class_table ... ok
test project_stats::snapshot::tests::zero_code_repository_keeps_empty_language_list ... ok
test provider_usage::tests::attempt_policy::adaptive_rate_limit_clamps_and_escalates ... ok
test provider_usage::tests::attempt_policy::attempt_validation_rejects_bad_floor_and_fingerprint ... ok
test bead::read_model::tests::tail_applies_appended_note_without_rebuild ... ok
test provider_priority::tests::replacement_and_clear_require_complete_expected_record ... ok
test provider_priority::tests::ineligible_target_preserves_existing_priority_and_disable_file ... ok
test project_stats::snapshot::tests::sha256_repositories_measure_with_their_native_object_format ... ok
test provider_usage::tests::attempt_policy::old_store_files_without_new_fields_round_trip ... ok
test provider_usage::tests::attention::collection_problem_attention_keeps_empty_problem_and_silent_unknown_arms ... ok
test provider_usage::tests::attention::rejected_outranks_very_low ... ok
test provider_usage::tests::attention::usage_attention_rank_order_places_collection_problem_above_low ... ok
test provider_usage::tests::compatibility::claude_fable_alias_observation_canonicalizes_and_collapses ... ok
test bead::mutation::tests::proof_bounded::proof_non_counter_config_change_repairs ... ok
test provider_usage::tests::freshness_health::freshness_bands_use_two_and_four_cadences ... ok
test provider_usage::tests::freshness_health::indicator_recomputes_freshness_and_reset_from_injected_clock ... ok
test provider_usage::tests::freshness_health::not_applicable_clears_numeric_conclusions ... ok
test provider_usage::tests::freshness_health::reset_at_now_has_passed ... ok
test provider_usage::tests::freshness_health::unauthenticated_is_a_collection_problem ... ok
test provider_usage::tests::freshness_health::window_applicability_is_declared_not_inferred ... ok
test provider_usage::tests::freshness_health::empty_snapshot_is_empty_health ... ok
test provider_usage::tests::indicator::indicator_classifies_claude_model_scoped_weekly_window_as_weekly ... ok
test provider_usage::tests::indicator::indicator_classifies_supported_provider_window_shapes ... ok
test provider_usage::tests::indicator::indicator_defaults_select_weekly_all_and_low_independent_windows ... ok
test provider_usage::tests::indicator::indicator_invalid_floors_are_rejected ... ok
test provider_usage::tests::indicator::indicator_floor_keeps_window_fresh_for_floored_provider_only ... ok
test bead::mutation::tests::proof_bounded::proof_history_old_version_cache_falls_back_and_heals ... ok
test provider_usage::tests::indicator::indicator_invalid_policy_diagnostics_keep_inherited_policy ... ok
test provider_usage::tests::indicator::indicator_leaves_claude_model_scoped_non_weekly_window_unknown ... ok
test provider_usage::tests::indicator::indicator_projection_order_is_provider_then_weekly_all_then_window_key ... ok
test provider_usage::tests::indicator::indicator_policy_precedence_uses_exact_then_provider_then_weekly_defaults ... ok
test provider_usage::tests::indicator::indicator_thresholds_use_unrounded_remaining_percentage ... ok
test provider_usage::tests::indicator::indicator_request_without_floors_projects_as_today ... ok
test provider_usage::tests::muse::indicator_muse_weekly_needs_muse_provider_and_account_scope ... ok
test provider_usage::tests::muse::indicator_keeps_muse_session_independent_of_weekly_all ... ok
test provider_usage::tests::muse::indicator_muse_weekly_over_quota_stays_visible_unclamped ... ok
test provider_usage::tests::muse::muse_absent_usage_projects_no_windows_and_no_zero_percent ... ok
test provider_usage::tests::refresh::collector_health_classifies_failure_boundaries_and_saturation ... ok
test provider_usage::tests::muse::indicator_selects_normalized_muse_weekly_by_default_and_not_session ... ok
test provider_usage::tests::refresh::usage_refresh_backoff_grows_and_caps ... ok
test provider_usage::tests::refresh::usage_refresh_due_respects_cadence_backoff_and_explicit ... ok
test bead::mutation::tests::proof_bounded::proof_history_open_stays_bounded ... ok
test provider_disable::tests::replacing_one_provider_preserves_siblings ... ok
test provider_usage::tests::refresh::usage_refresh_future_marker_competes_with_fresh_deadline ... ok
test provider_usage::tests::refresh::usage_refresh_future_marker_does_not_delay_ordinary_due_reasons ... ok
test project_stats::snapshot::tests::odd_filenames_and_non_utf8_paths_are_preserved ... ok
test provider_usage::tests::refresh::usage_refresh_restrictions_outweigh_future_and_reached_markers ... ok
test provider_usage::tests::snapshot_projection::authoritative_empty_ok_is_allowed ... ok
test provider_usage::tests::snapshot_projection::deterministic_ties_break_on_provider_and_window_key ... ok
test provider_usage::tests::snapshot_projection::missing_quantities_are_null_not_zero ... ok
test bead::mutation::tests::proof_bounded::proof_history_claim_and_release_stay_bounded ... ok
test provider_usage::tests::snapshot_projection::mixed_ages_use_only_fresh_windows_in_the_numeric_summary ... ok
test provider_usage::tests::snapshot_projection::reset_expiry_drops_numeric_summary_without_synthesizing_100 ... ok
test provider_usage::tests::snapshot_projection::shared_plus_model_specific_limits_do_not_replace_each_other ... ok
test provider_usage::tests::snapshot_projection::unknown_scope_makes_model_conclusion_partial ... ok
test provider_usage::tests::snapshot_projection::used_percent_fixture_preserves_raw_precision_and_overage ... ok
test provider_priority::tests::relative_exact_and_indefinite_windows_round_trip ... ok
test provider_usage::tests::admission_policy::park_and_unpark_on_fingerprint_change_end_to_end ... ok
test provider_usage::tests::admission_policy::floor_aware_freshness ... ok
test project_stats::snapshot::tests::measures_every_role_and_skips_gitlinks_and_symlinks ... ok
test project_stats::query_tests::coverage_uses_worst_health_for_a_shared_identity ... ok
test provider_usage::tests::attempt_policy::legacy_attempt_with_new_fields_still_validates_but_ignores_them ... ok
test provider_usage::tests::attempt_policy::legacy_attempts_keep_legacy_shape_and_cooldown ... ok
test provider_usage::tests::admission_policy::legacy_due_admit_read_compat ... ok
test provider_usage::tests::admission_policy::reservation_listing_returns_live_rows_only ... ok
test provider_usage::tests::validation::public_json_rejects_unknown_observation_fields ... ok
test provider_usage::tests::validation::rejects_duplicate_keys_empty_ok_and_impossible_periods ... ok
test provider_usage::tests::validation::rejects_unknown_schema_negative_used_and_future_timestamps ... ok
test provider_usage::tests::validation::rejects_duplicate_providers_and_invalid_thresholds ... ok
test provider_usage::tests::attempt_policy::observation_retry_after_clamps_and_rejects ... ok
test provider_usage::tests::validation::strips_controls_and_redacts_secret_diagnostics ... ok
test query::profile::tests::from_wire_rejects_unknown_predicate ... ok
test provider_usage::tests::validation::vendor_drift_reason_code_is_accepted_and_unknown_codes_still_reject ... ok
test query::profile::tests::from_wire_rejects_digest_mismatch ... ok
test query::searchable::tests::artifact_references_are_searchable ... ok
test query::searchable::tests::project_dir_name_basic ... ok
test query::profile::tests::profile_accepts_shorthands_alias_for_macros_key ... ok
test query::tests::ast_round_trips_through_json ... ok
test query::tests::boolean_glob_semantics_match_flat ... ok
test query::tests::boolean_precedence_works_on_generic_rows ... ok
test query::profile::tests::patch_profile_digest_matches_python_compiler ... ok
test query::tests::canonical_and_inside_or_gets_parens ... ok
test query::tests::canonical_any_special_implicit_and ... ok
test project_stats::snapshot::tests::identical_tree_reuses_the_complete_cache_without_rereading_blobs ... ok
test query::tests::boolean_profile_accepts_widened_values_and_normalizes_typed_literals ... ok
test query::tests::canonical_case_sensitive_string ... ok
test query::tests::canonical_error_suffix_running_markers ... ok
test project_stats::query_tests::shared_history_is_deduplicated_within_and_across_projects ... ok
test query::tests::canonical_escape_string_value ... ok
test query::tests::canonical_implicit_and ... ok
test query::tests::canonical_not_around_and_gets_parens ... ok
test query::tests::canonical_not_string ... ok
test query::tests::canonical_or ... ok
test query::tests::canonical_simple_string ... ok
test query::tests::canonical_property_filter_shorthands ... ok
test query::tests::canonical_status_property ... ok
test query::tests::canonical_or_inside_and_gets_parens ... ok
test query::tests::canonical_widened_boolean_value_shapes_round_trip ... ok
test query::tests::digest_mismatch_is_rejected_before_evaluation ... ok
test query::tests::flat_bare_boolean_flags_keep_existing_field_guards ... ok
test query::tests::flat_bare_boolean_flags_canonicalize_to_long_form ... ok
test query::tests::flat_bare_boolean_flags_evaluate_like_key_true ... ok
test query::tests::flat_canonical_groups_fields_then_predicates_then_text ... ok
test query::tests::flat_enum_star_is_literal ... ok
test query::tests::flat_negation_and_comma_rules ... ok
test query::tests::flat_exact_match_glob_is_anchored ... ok
test query::tests::flat_duration_bound_values_normalize_canonically ... ok
test query::tests::flat_date_and_duration_bound_keys_compare_by_host_direction ... ok
test query::tests::flat_partially_quoted_boolean_key_canonicalizes_as_quoted_text ... ok
test query::tests::flat_predicates_evaluate_absent_facts_as_false ... ok
test query::tests::flat_quoted_boolean_key_remains_free_text ... ok
test query::tests::flat_repeated_values_are_any_match_and_exclusions_negate ... ok
test bead::mutation::tests::proof_bounded::proof_history_write_to_closed_bead_stays_bounded ... ok
test bead::mutation::tests::proof_bounded::proof_history_remove_cascade_stays_bounded ... ok
test query::tests::flat_profile_parses_closed_host_predicates_without_boolean_syntax ... ok
test query::tests::host_bound_key_tables_match_python_registry ... ok
test query::tests::flat_sha_glob_is_anchored ... ok
test query::tests::invalid_profile_is_structured_error ... ok
test query::tests::generic_corpus_reuses_indexes_across_evaluations ... ok
test query::tests::parse_any_special_expands_to_or ... ok
test query::tests::flat_validates_enum_bool_and_int_literals ... ok
test query::tests::generic_rows_honor_searchable_fields_and_predicates ... ok
test query::tests::parse_bare_word ... ok
test query::tests::parse_case_sensitive_string ... ok
test query::tests::parse_error_empty_query ... ok
test query::tests::flat_substring_glob_is_unanchored ... ok
test query::tests::parse_double_not_collapses_to_two_nots ... ok
test query::tests::parse_error_missing_operand ... ok
test query::tests::parse_error_suffix_and_string ... ok
test query::tests::parse_error_unmatched_paren ... ok
test query::tests::parse_implicit_and ... ok
test query::tests::parse_implicit_and_with_parens ... ok
test query::tests::parse_not_running_agent_shorthand ... ok
test query::tests::flat_tokenizer_rejects_boolean_syntax ... ok
test query::tests::parse_not_running_process_shorthand ... ok
test query::tests::parse_not_tightest ... ok
test query::tests::parse_or_loosest ... ok
test query::tests::parse_property_match ... ok
test query::tests::parse_standalone_exclamation_is_error_suffix ... ok
test query::tests::parser_error_wire_kind_is_parser ... ok
test query::tests::patch_wrappers_match_explicit_patch_profile ... ok
test query::tests::tokenize_any_special_only_standalone ... ok
test query::tests::token_round_trips_through_json ... ok
test query::tests::tokenize_at_not_standalone_is_error ... ok
test query::tests::tokenize_bare_word_with_numbers ... ok
test query::tests::sha_field_matches_a_prefix_of_the_stored_value ... ok
test query::tests::tokenize_case_sensitive_string ... ok
test query::tests::stitches_sidecar_bare_token_is_a_boolean_flag ... ok
test bead::read_model::tests::sweep_refresh_loses_to_concurrent_commit ... ok
test query::tests::tokenize_dollar_not_standalone_is_error ... ok
test query::tests::tokenize_double_exclamation_standalone_is_not_error_suffix ... ok
test query::tests::tokenize_invalid_escape ... ok
test query::tests::tokenize_double_exclamation_not_standalone_is_two_nots ... ok
test query::tests::tokenize_invalid_property_key ... ok
test query::tests::tokenize_not_at_with_space ... ok
test query::tests::tokenize_not_dollar_with_space ... ok
test query::tests::tokenize_not_keyword_with_error_suffix ... ok
test query::tests::tokenize_origin_property ... ok
test query::tests::tokenize_paren_and_keywords ... ok
test query::tests::tokenize_property_quoted_value ... ok
test query::tests::tokenize_property_shorthands ... ok
test query::tests::tokenize_quoted_with_escapes ... ok
test query::tests::tokenize_standalone_at_and_bang ... ok
test query::tests::tokenize_status_shorthand_invalid ... ok
test query::tests::tokenize_rejects_disabled_predicate_and_any_special ... ok
test query::tests::tokenize_triple_specials ... ok
test query::tests::tokenize_unterminated_string ... ok
test query::tests::tokenize_status_shorthands ... ok
test query::tests::tokenize_rejects_undeclared_property_and_keeps_span ... ok
test query::tests::tokenizer_error_wire_kind_is_tokenizer ... ok
test query::tests::tokenize_status_shorthand_uppercase ... ok
test queue_directive::tests::accepts_capacity_multiplier_spellings_in_both_flag_states ... ok
test queue_directive::tests::capacity_aliases_prefer_canonical_and_keep_zero_distinct ... ok
test queue_directive::tests::accepts_exact_zero_weight_literals_with_or_without_capacity_budget ... ok
test queue_directive::tests::legacy_flag_helpers_always_enable_queue ... ok
test queue_directive::tests::equivalent_spellings_compose_disjoint_fields ... ok
test queue_directive::tests::capacity_multiplier_helpers_validate_format_and_resolve ... ok
test query::tests::tokenize_uses_profile_fields_and_sigils ... ok
test queue_directive::tests::multiplier_skips_parse_time_weight_capacity_check ... ok
test queue_directive::tests::newly_authored_zero_capacity_is_rejected ... ok
test queue_directive::tests::persisted_multiplier_resolves_at_admission_and_reauthors ... ok
test bead::mutation::tests::proof_bounded::proof_history_dependencies_stay_bounded ... ok
test queue_directive::tests::parses_weight_float_spellings_and_formats_canonically ... ok
test queue_directive::tests::persisted_zero_keeps_exact_effective_weight_drain_budget ... ok
test queue_directive::tests::queue_fields_read_capacity_multiplier_alias ... ok
test queue_directive::tests::parenthesized_positional_and_aliases_round_trip ... ok
test queue_directive::tests::queue_fields_read_legacy_capacity_and_write_queue_capacity ... ok
test queue_directive::tests::preserves_source_spans_on_errors ... ok
test queue_directive::tests::rejects_duplicate_integer_and_multiplier_capacity ... ok
test queue_directive::tests::rejects_duplicates_even_when_values_match ... ok
test queue_directive::tests::rejects_empty_and_plus_forms_without_previous_agent_meaning ... ok
test queue_directive::tests::rejects_invalid_and_overflow_integers ... ok
test queue_directive::tests::rejects_malformed_parentheses_extra_positionals_and_wait_keys ... ok
test queue_directive::tests::rejects_invalid_capacity_multipliers_in_both_flag_states ... ok
test queue_directive::tests::rejects_invalid_weight_values ... ok
test queue_directive::tests::weight_over_capacity_is_rejected_unconditionally ... ok
test queue_directive::tests::zero_capacity_value_is_rejected_unconditionally ... ok
test queue_directive::tests::rejects_obsolete_runners_keyword_with_capacity_migration ... ok
test referenced_by::tests::duplicate_block_collapses_to_one ... ok
test referenced_by::tests::strip_leaves_a_document_with_no_block_untouched ... ok
test referenced_by::tests::unterminated_start_marker_extends_to_eof ... ok
test referenced_by::tests::stray_end_marker_with_no_start_is_left_alone ... ok
test referenced_by::tests::render_sorts_rows_and_numbers_links_through_the_shared_allocator ... ok
test referenced_by::tests::strip_normalizes_trailing_whitespace_for_stable_digests ... ok
test referenced_by::tests::render_parse_round_trips ... ok
test referenced_by::tests::upsert_places_block_at_bottom_and_is_idempotent ... ok
test referenced_by::tests::render_caps_at_fifty_rows_and_reports_omitted ... ok
test release_steward::tests::cadence::prior_day_merge_does_not_block ... ok
test release_steward::tests::cadence::same_day_merge_blocks ... ok
test release_steward::tests::cadence::abandoned_same_day_candidate_frees_the_slot ... ok
test release_steward::tests::cadence::active_train_prevents_another_merge ... ok
test release_steward::tests::cadence::at_nine_utc_allows_merge ... ok
test release_steward::tests::cadence::utc_midnight_starts_a_new_day ... ok
test referenced_by::tests::upsert_with_empty_table_removes_the_block ... ok
test release_steward::tests::cadence::before_nine_utc_blocks_merge ... ok
test release_steward::tests::escalation::aged_blocking_opens_once_at_24h ... ok
test release_steward::tests::escalation::identity_change_resets_duration ... ok
test release_steward::tests::escalation::advisory_qualification_uses_ci_label ... ok
test release_steward::tests::escalation::immediate_install_outranks_advisory ... ok
test release_steward::tests::escalation::install_broken_escalates_immediately ... ok
test release_steward::tests::escalation::publish_conflict_escalates_immediately ... ok
test release_steward::tests::escalation::recovery_closes_the_open_issue ... ok
test release_steward::tests::escalation::same_tick_identity_does_not_duplicate_comment ... ok
test release_steward::tests::from_json_rejects_unknown_fields ... ok
test release_steward::tests::escalation::uncertain_duration_does_not_invent_24h ... ok
test release_steward::tests::escalation::later_tick_comments_plus_one ... ok
test release_steward::tests::states::ambiguous_trains_prevent_merge ... ok
test release_steward::tests::schema_mismatch_is_an_error ... ok
test release_steward::tests::states::cancelled_gate_jobs_are_not_rerun ... ok
test release_steward::tests::states::confirmed_release_is_released ... ok
test release_steward::tests::states::core_ci_red_outranks_lag ... ok
test release_steward::tests::states::core_cut_red_does_not_rerun ... ok
test release_steward::tests::states::core_lag_proposes_one_cut ... ok
test release_steward::tests::states::core_incompatible_proposes_one_metadata_refresh ... ok
test release_steward::tests::states::dependency_unpublished_blocks_publication ... ok
test release_steward::tests::states::exercise_red_is_a_typed_state ... ok
test release_steward::tests::states::gate_red_reruns_failed_tests_not_lint ... ok
test release_steward::tests::states::empty_collected_checks_are_not_green ... ok
test release_steward::tests::from_json_round_trips_a_releasable_snapshot ... ok
test release_steward::tests::states::in_flight_release_run_suppresses_resume ... ok
test release_steward::tests::states::initial_tag_proposes_release_mode ... ok
test release_steward::tests::states::in_flight_core_cut_suppresses_another ... ok
test release_steward::tests::states::install_red_does_not_block_publishable_resume ... ok
test release_steward::tests::states::install_red_is_primary_when_nothing_else_applies ... ok
test release_steward::tests::states::known_red_canary_is_not_watcher_broken ... ok
test release_steward::tests::states::legacy_pre_train_tag_is_not_an_active_train ... ok
test release_steward::tests::states::lint_only_gate_failure_does_not_rerun ... ok
test release_steward::tests::states::missing_cut_diagnostic_fails_closed ... ok
test release_steward::tests::states::merge_authority_off_keeps_releasable_and_suppresses ... ok
test release_steward::tests::states::nothing_to_release_without_pr ... ok
test release_steward::tests::states::missing_required_check_blocks_merge ... ok
test release_steward::tests::states::previous_generation_does_not_qualify_rebuild ... ok
test release_steward::tests::states::observe_only_never_marks_executed ... ok
test release_steward::tests::states::public_files_refuse_abandonment ... ok
test release_steward::tests::states::newest_generation_wins_within_one_train ... ok
test release_steward::tests::states::qualify_red_reruns_when_eligible ... ok
test release_steward::tests::states::rejected_eligible_cadence_is_invalid ... ok
test release_steward::tests::states::publish_conflict_outranks_partial ... ok
test release_steward::tests::states::releasable_proposes_merge ... ok
test release_steward::tests::states::skipped_required_check_blocks_merge ... ok
test release_steward::tests::states::publish_partial_proposes_resume ... ok
test release_steward::tests::states::spent_retry_abandons_unpublished_candidate ... ok
test release_steward::tests::states::tag_mismatch_fails_closed ... ok
test release_steward::tests::states::unreadable_required_fact_is_watcher_broken ... ok
test release_steward::tests::wire_schema_version_matches_constant ... ok
test release_steward::tests::states::unreadable_expected_checks_cannot_merge ... ok
test release_steward::tests::states::veto_from_hold_label ... ok
test repository_resolution::tests::different_owner_or_host_does_not_match ... ok
test repository_resolution::tests::duplicate_configured_remote_is_ambiguous ... ok
test repository_resolution::tests::external_project_path_precedes_remote_match ... ok
test repository_resolution::tests::external_project_path_resolves_linked_repo ... ok
test repository_resolution::tests::exact_linked_name_precedes_remote_match ... ok
test repository_resolution::tests::external_project_remote_requires_supported_full_identity ... ok
test repository_resolution::tests::normalizes_github_reference_spellings ... ok
test repository_resolution::tests::external_project_remote_resolves_linked_repo ... ok
test repository_resolution::tests::external_project_ambiguous_linked_matches_are_errors ... ok
test repository_resolution::tests::remote_identity_resolves_provider_alias ... ok
test repository_resolution::tests::rejects_malformed_and_other_provider_identities ... ok
test retryability::tests::classifies_http_5xx_as_transient ... ok
test retryability::tests::classifies_existing_clone_markers_as_transient ... ok
test retryability::tests::classifies_tls_and_proxy_failures_as_transient ... ok
test retryability::tests::gh_auth_and_not_found_are_permanent ... ok
test retryability::tests::rate_limit_uses_retry_after_delay ... ok
test retryability::tests::unclassified_failure_is_permanent ... ok
test runner_capacity::tests::candidate::candidate_decision_excludes_unadmitted_candidate_from_own_claim ... ok
test runner_capacity::tests::candidate::candidate_decision_reuses_active_lineage_or_rejects_reweight ... ok
test runner_capacity::tests::candidate::invalid_released_lineage_weight_blocks_omitted_candidate ... ok
test runner_capacity::tests::candidate::candidate_serial_successor_of_live_parallel_member_reuses_parallel_lineage ... ok
test runner_capacity::tests::candidate::persisted_owner_keeps_released_parallel_successor_off_unrelated_agent_session_claim ... ok
test runner_capacity::tests::candidate::released_lineage_inherits_weight_unless_candidate_authors_new_weight ... ok
test runner_capacity::tests::capacity_math::capacity_budget_below_global_limit_is_strict ... ok
test runner_capacity::tests::capacity_math::capacity_budget_can_exceed_global_limit ... ok
test runner_capacity::tests::capacity_math::explicit_capacity_budget_replaces_global_limit ... ok
test runner_capacity::tests::capacity_math::default_weights_match_serial_and_parallel_lane_counting ... ok
test runner_capacity::tests::capacity_math::capacity_budget_one_is_drain_barrier ... ok
test runner_capacity::tests::capacity_math::heterogeneous_and_meaningful_boundaries_use_proposed_total ... ok
test runner_capacity::tests::capacity_math::legacy_capacity_zero_translates_under_capacity_budget ... ok
test runner_capacity::tests::capacity_math::legacy_capacity_zero_with_negligible_load_admits_immediately ... ok
test runner_capacity::tests::capacity_math::one_heavy_claim_exceeds_capacity_one ... ok
test runner_capacity::tests::capacity_math::over_budget_weight_blocks_behind_full_capacity_one ... ok
test runner_capacity::tests::capacity_math::legacy_capacity_zero_with_zero_weight_is_a_true_drain_barrier ... ok
test runner_capacity::tests::capacity_math::invalid_live_claim_and_aggregate_overflow_fail_closed ... ok
test runner_capacity::tests::capacity_math::oversized_and_invalid_request_weights_are_blocked ... ok
test runner_capacity::tests::capacity_math::proposed_waiter_overflow_fails_closed ... ok
test runner_capacity::tests::capacity_math::tiny_positive_weights_are_valid_but_still_accounted ... ok
test runner_capacity::tests::capacity_math::zero_weight_capacity_budget_waiter_needs_free_capacity ... ok
test runner_capacity::tests::claims::explicit_claim_owner_separates_same_agent_session_branches ... ok
test runner_capacity::tests::claims::nested_gate_successor_reuses_starter_lineage ... ok
test runner_capacity::tests::claims::serial_successor_of_parallel_member_shares_parallel_lineage_claim ... ok
test runner_capacity::tests::claims::nested_monitor_successor_reuses_starter_lineage ... ok
test runner_capacity::tests::claims::shared_agent_session_claim_counts_once_for_capacity ... ok
test runner_capacity::tests::claims::unrelated_same_display_agent_session_claim_does_not_hide_parallel_successor ... ok
test runner_capacity::tests::claims::serial_successor_waits_only_after_agent_session_releases_claim ... ok
test runner_capacity::tests::capacity_math::proposed_total_allows_repeated_decimal_boundary ... ok
test runner_capacity::tests::holds::hold_barrier_blocks_waiting_candidate_with_metadata ... ok
test runner_capacity::tests::holds::running_candidate_is_not_reblocked_by_hold ... ok
test runner_capacity::tests::holds::hold_barrier_honors_project_and_future_selectors ... ok
test runner_capacity::tests::waiters::explicit_zero_weight_monitor_occupies_nothing_at_a_full_limit ... ok
test runner_capacity::tests::holds::multiple_holds_release_independently ... ok
test provider_usage::tests::admission_policy::hot_cadence_shortens_due_interval_but_respects_floors ... ok
test runner_capacity::tests::holds::hold_barrier_blocks_queued_candidate_decision ... ok
test runner_capacity::tests::waiters::explicit_zero_weight_waiter_respects_queue_order ... ok
test provider_usage::tests::store::usage_store_reports_bad_provider_records_without_repairing_on_read ... ok
test runner_capacity::tests::waiters::lighter_waiter_can_pass_non_fitting_heavy_waiter ... ok
test runner_capacity::tests::waiters::multiplier_capacity_resolves_for_waiters_and_preserves_legacy_behavior ... ok
test runner_capacity::tests::waiters::parked_waiters_sort_by_capacity_then_runner_shortfall_before_priority ... ok
test runner_capacity::tests::waiters::implicit_zero_negative_and_nan_record_weights_still_fail_closed ... ok
test runner_capacity::tests::waiters::deference_blocks_lower_priority_until_window_elapses ... ok
test project_stats::snapshot::tests::attribute_only_commit_reclassifies_without_rereading_unchanged_blobs ... ok
test provider_usage::tests::store::usage_store_recovers_legacy_claude_fable_cache_without_read_repair ... ok
test runner_capacity::tests::waiters::waiter_admits_when_only_other_records_are_zero_weight ... ok
test runner_capacity::tests::wire::dual_written_capacity_fields_prefer_canonical_without_duplicate_error ... ok
test runner_capacity::tests::waiters::zero_weight_claim_is_not_reusable_by_a_serial_successor ... ok
test runner_capacity::tests::wire::legacy_parallel_key_stays_input_only ... ok
test runner_capacity::tests::wire::agent_session_request_uses_canonical_keys ... ok
test runner_capacity::tests::wire::legacy_wait_runners_aliases_deserialize_to_queue_capacity ... ok
test runner_limit_override::tests::invalid_inputs_are_rejected ... ok
test runner_limit_override::tests::malformed_stale_and_invalid_state_self_cleans ... ok
test project_stats::snapshot::tests::binary_lfs_and_oversize_blobs_are_excluded_without_being_zero ... ok
test sections::tests::commits_body_lines_use_six_space_indent_and_dot_for_blank ... ok
test sections::tests::commits_drawers_attach_to_current_entry ... ok
test sections::tests::comments_basic_and_with_error_suffix ... ok
test sections::tests::deltas_requires_exactly_two_leading_spaces ... ok
test sections::tests::deltas_glyph_to_change_type_mapping ... ok
test sections::tests::commits_line_starts_new_entry_and_strips_trailing_suffix ... ok
test sections::tests::hooks_new_command_flushes_previous_hook ... ok
test sections::tests::commits_proposal_letter_carries_through ... ok
test sections::tests::hooks_command_then_status_line ... ok
test sections::tests::commits_running_agent_and_rejected_proposal_suffixes ... ok
test sections::tests::hooks_running_agent_suffix_split_from_summary ... ok
test sections::tests::mentors_legacy_profiles_without_counts_split_on_whitespace ... ok
test sections::tests::stitches_line_uses_same_entry_parser ... ok
test service::config::tests::a_non_mapping_service_value_is_fatal ... ok
test service::config::tests::a_local_layer_is_ignored_with_a_warning ... ok
test sections::tests::mentors_entry_with_count_then_status ... ok
test sections::tests::timestamps_hybrid_bracketed_yymmdd_parses ... ok
test service::config::tests::an_errored_local_layer_warns_and_is_not_fatal ... ok
test service::config::tests::an_errored_overlay_is_fatal_and_names_the_file ... ok
test sections::tests::timestamps_legacy_bracketed_format_still_parses ... ok
test service::config::tests::a_one_line_string_command_becomes_sh_c_argv ... ok
test sections::tests::timestamps_new_format_parses ... ok
test service::config::tests::an_overlay_only_partial_entry_is_unavailable_with_a_plugin_hint ... ok
test service::config::tests::an_unknown_layer_kind_is_fatal ... ok
test service::config::tests::an_overlay_replaces_a_plugin_list_whole ... ok
test service::config::tests::an_unknown_after_target_warns_and_an_after_cycle_marks_entries_unavailable ... ok
test sections::tests::mentors_draft_marker_is_stripped ... ok
test service::config::tests::field_provenance_shows_the_overriding_layer_and_its_file_path ... ok
test sections::tests::mentors_entry_ref_suffix_marks_type_entry_ref ... ok
test service::config::tests::env_merges_key_by_key_and_bad_dollar_brace_syntax_is_rejected ... ok
test sections::tests::mentors_running_status_without_timestamp_parses_as_none ... ok
test service::config::tests::overlay_enabled_false_beats_default_and_true_reenables_plugin_entry ... ok
test service::config::tests::rejections_mode_oneshot_reserved_name_builtin_mismatch_unknown_field ... ok
test service::config::tests::stop_signal_is_normalized ... ok
test service::restart::tests::below_threshold_never_reports_crash_loop ... ok
test service::restart::tests::crash_loop_notifies_once_and_rearms_after_healthy_run ... ok
test service::restart::tests::crash_loop_sticks_past_the_window_until_a_healthy_run ... ok
test service::restart::tests::invalid_inputs_are_rejected ... ok
test service::config::tests::the_default_layer_gateway_entry_is_disabled_explicitly ... ok
test service::restart::tests::never_and_stop_requested_give_up ... ok
test service::restart::tests::on_failure_gives_up_for_clean_exits_and_restarts_failures ... ok
test service::restart::tests::orchestrator_parity_backoff_doubles_caps_and_resets_after_healthy_run ... ok
test service::restart::tests::sticky_crash_loop_rearms_after_a_healthy_run ... ok
test service::restart::tests::window_pruning_removes_old_failures ... ok
test service::state::tests::proc_request_mutations_reject_bad_actions_names_and_outcomes ... ok
test service::state::tests::newer_schema_is_read_only_and_refuses_mutation ... ok
test service::state::tests::validation_rejects_bad_names_markers_actors_and_now ... ok
test service::status::tests::change_token_ignores_generation_and_heartbeat_churn ... ok
test service::status::tests::duplicate_observations_use_last_row_for_configured_and_orphan_procs ... ok
test service::status::tests::enablement_resolution_summaries_match_sources ... ok
test service::status::tests::observations_without_config_entries_become_orphans ... ok
test service::status::tests::proc_state_derivation_uses_first_matching_rule ... ok
test provider_usage::tests::store::usage_store_preserves_windows_after_failed_newer_attempt ... ok
test service::status::tests::stops_are_scoped_to_the_request_boot_id ... ok
test service::tests::service_proc_names_accept_path_safe_slugs ... ok
test service::tests::service_proc_names_reject_unsafe_values ... ok
test sidecar_publication::tests::explicit_fetch_first_retries_before_limit ... ok
test sidecar_publication::tests::explicit_non_fast_forward_retries_before_limit ... ok
test sidecar_publication::tests::generic_failed_refs_message_is_terminal ... ok
test sidecar_publication::tests::retryable_rejection_stops_at_attempt_limit ... ok
test sidecar_publication::tests::success_stops_the_policy_with_success_action ... ok
test sidecar_publication::tests::timeout_and_hook_failures_are_terminal_unknowns ... ok
test snippet_catalog::tests::alias_pair_is_an_indirect_cycle_on_explicit_identities ... ok
test snippet_catalog::tests::alias_self_cycle_lands_on_explicit_identity ... ok
test snippet_catalog::tests::aliases_use_composed_templates_and_references_can_target_aliases ... ok
test snippet_catalog::tests::analyzes_nested_positional_quoted_and_duplicate_calls ... ok
test snippet_catalog::tests::colon_form_records_positional_argument ... ok
test snippet_catalog::tests::composes_capitalized_aliases_and_preserves_remaining_case ... ok
test provider_usage::tests::store::usage_store_decodes_old_schedules_and_isolates_future_schedule_fields ... ok
test snippet_catalog::tests::composes_unicode_aliases_and_handles_unchanged_leading_scalars ... ok
test snippet_catalog::tests::explicit_capitalized_trigger_wins_alias_collision ... ok
test snippet_catalog::tests::direct_and_indirect_cycles ... ok
test snippet_catalog::tests::inbound_ordering_is_deterministic_and_unique ... ok
test snippet_catalog::tests::invalid_trigger_does_not_change_expansion ... ok
test snippet_catalog::tests::missing_target_and_boundary_rules ... ok
test snippet_catalog::tests::unicode_template_spans_use_byte_offsets ... ok
test snippet_catalog::tests::validate_snippet_trigger_rejects_empty_and_punctuation ... ok
test snippet_session::session_tests::advance_and_retreat_on_an_inactive_session_are_no_ops ... ok
test snippet_session::session_tests::apply_edit_deletes_offsets_falling_before_the_first_stop ... ok
test snippet_session::session_tests::apply_edit_normalizes_unordered_edit_bounds ... ok
test snippet_session::session_tests::apply_edit_on_an_inactive_session_is_a_no_op ... ok
test snippet_session::session_tests::apply_edit_remaps_stops_before_at_inside_and_after_the_edit ... ok
test snippet_session::session_tests::apply_session_event_advance_retreat_apply_edit_and_clear_round_trip ... ok
test snippet_session::session_tests::apply_session_event_drives_the_reported_bug_scenario_end_to_end ... ok
test snippet_catalog::tests::snippet_reference_golden_vectors ... ok
test snippet_session::session_tests::apply_session_event_expand_reports_the_new_cursor_offset ... ok
test snippet_session::session_tests::apply_session_event_plan_is_stateless_and_echoes_state_unchanged ... ok
test snippet_session::session_tests::apply_session_event_plan_substitutes_variables_before_planning ... ok
test snippet_session::session_tests::clear_ends_an_active_session ... ok
test snippet_session::session_tests::depth_cap_drops_outermost_session_on_overflow ... ok
test snippet_session::session_tests::event_kind_tags_match_the_documented_snake_case_names ... ok
test snippet_session::session_tests::event_result_serializes_with_the_documented_field_order ... ok
test snippet_session::session_tests::expand_outside_active_span_resets_instead_of_nesting ... ok
test snippet_session::session_tests::expanding_a_no_stop_plan_outside_any_session_clears_state ... ok
test snippet_session::session_tests::nesting_a_plan_with_no_stops_leaves_the_enclosing_session_untouched ... ok
test snippet_session::session_tests::nesting_at_a_stop_resumes_outer_session_after_inner_exhausts ... ok
test snippet_session::session_tests::retreat_at_start_and_advance_past_end_report_no_target ... ok
test snippet_session::session_tests::deleting_a_whole_nested_expansion_drops_it_without_corrupting_the_enclosing_session ... ok
test snippet_session::session_tests::state_serializes_with_the_documented_field_order ... ok
test snippet_session::tests::continuation_line_indentation_can_be_disabled ... ok
test snippet_session::session_tests::two_levels_of_nesting_resume_enclosing_sessions_in_order ... ok
test snippet_session::tests::continuation_lines_are_indented_and_offsets_shift ... ok
test snippet_session::tests::escaped_dollars_are_literal_and_not_tabstops ... ok
test snippet_session::tests::missing_zero_appends_implicit_final_stop ... ok
test snippet_session::tests::multi_digit_tabstops_sort_by_number ... ok
test snippet_session::tests::offsets_are_character_offsets_not_byte_offsets ... ok
test snippet_session::tests::repeated_tabstop_numbers_only_create_one_stop ... ok
test snippet_session::tests::templates_without_markers_have_no_stops ... ok
test snippet_variables::tests::dollars_in_values_are_escaped_for_the_tabstop_scanner ... ok
test snippet_variables::tests::empty_map_returns_the_template_unchanged ... ok
test snippet_variables::tests::known_variable_is_substituted ... ok
test snippet_variables::tests::malformed_tokens_are_left_untouched ... ok
test snippet_variables::tests::multiple_occurrences_are_all_substituted ... ok
test snippet_variables::tests::names_must_start_with_a_letter_or_underscore ... ok
test snippet_variables::tests::snippet_calls_are_untouched ... ok
test snippet_variables::tests::template_without_tokens_returns_unchanged ... ok
test snippet_variables::tests::unknown_variable_is_left_verbatim ... ok
test snippet_variables::tests::utf8_text_around_tokens_is_preserved ... ok
test snippet_variables::tests::variable_adjacent_to_a_tabstop_keeps_the_tabstop ... ok
test source_language::tests::diff_sniff_is_stdin_only ... ok
test source_language::tests::filename_wins_over_shebang_and_diff_prefix ... ok
test source_language::tests::extensionless_shebangs_cover_python_and_shell_dialects ... ok
test source_language::tests::justfile_is_plain_and_not_make ... ok
test source_language::tests::hints_json_roundtrip_and_schema_errors ... ok
test source_language::tests::logical_filename_uses_source_then_vcs_then_resolved ... ok
test source_language::tests::mapping_table_covers_declared_families ... ok
test source_language::tests::request_and_result_json_roundtrip ... ok
test source_language::tests::shebang_is_skipped_for_suffixed_unknown_files ... ok
test source_language::tests::stdin_diff_sniff_positive_and_negative_samples ... ok
test source_language::tests::suffix_matching_is_case_insensitive_and_basenames_are_exact ... ok
test source_language::tests::trusted_categories_override_filename_and_skip_sniffing ... ok
test source_language::tests::unknown_and_empty_names_are_not_supported_text ... ok
test source_language::tests::windows_and_unix_paths_use_basename ... ok
test source_language::tests::prefix_inspection_is_bounded_to_8_kib ... ok
test status::constants::tests::legacy_ready_to_mail_suffix_stripped ... ok
test status::constants::tests::terminal_statuses_have_no_outgoing_transitions ... ok
test status::constants::tests::unknown_statuses_rejected ... ok
test status::constants::tests::unmodified_status_passes_through ... ok
test status::constants::tests::valid_transitions_allow_known_pairs ... ok
test status::constants::tests::workspace_suffix_stripped_from_status ... ok
test status::constants::tests::workspace_suffix_does_not_block_validation ... ok
test status::field_updates::tests::apply_status_update_idempotent_when_status_already_matches ... ok
test status::field_updates::tests::apply_status_update_no_matching_patch_is_noop ... ok
test status::field_updates::tests::apply_status_update_preserves_unrelated_lines ... ok
test status::field_updates::tests::apply_status_update_replaces_only_target_status ... ok
test status::field_updates::tests::read_status_matches_first_patch ... ok
test status::field_updates::tests::read_status_matches_second_patch ... ok
test status::field_updates::tests::read_status_preserves_workspace_suffix ... ok
test status::field_updates::tests::read_status_returns_none_when_missing ... ok
test status::name::tests::next_suffix_reserves_legacy_double_underscore_slot ... ok
test status::name::tests::next_suffix_skips_existing ... ok
test status::name::tests::next_suffix_starts_at_one ... ok
test status::planner::tests::archive_action_from_archive_under_no_validate ... ok
test status::planner::tests::archive_action_none_within_archive_class ... ok
test status::planner::tests::archive_action_none_within_main_class ... ok
test status::planner::tests::archive_action_to_archive_on_submitted ... ok
test status::planner::tests::archived_terminal_no_further_transitions ... ok
test status::planner::tests::draft_to_ready_no_suffix_clears_mentors_only ... ok
test status::name::tests::has_suffix_recognises_single_and_double_underscore ... ok
test status::planner::tests::invalid_transition_error_format_matches_python ... ok
test status::planner::tests::invalid_transition_validate_false_allows ... ok
test status::planner::tests::invalid_transition_validate_true_rejects ... ok
test status::planner::tests::legacy_ready_to_mail_suffix_stripped_for_validation ... ok
test status::planner::tests::parent_constraint_skipped_for_reverted_branch ... ok
test status::planner::tests::parent_ready_does_not_block_mailed ... ok
test status::planner::tests::parent_wip_blocks_child_to_mailed ... ok
test status::planner::tests::ready_to_draft_appends_suffix_and_sets_mentor ... ok
test status::planner::tests::ready_to_draft_blocked_by_invalid_children ... ok
test status::planner::tests::ready_to_draft_picks_lowest_free_suffix ... ok
test status::planner::tests::reverted_terminal_no_further_transitions ... ok
test status::planner::tests::schema_version_mismatch_returns_error ... ok
test status::planner::tests::submitted_terminal_no_further_transitions ... ok
test status::planner::tests::unknown_status_rejected_under_validation ... ok
test status::planner::tests::wip_to_draft_no_suffix_no_mentor ... ok
test status::planner::tests::wip_to_ready_blocked_by_sibling_unreverted_children ... ok
test status::planner::tests::wip_to_ready_with_suffix_strips ... ok
test status::planner::tests::draft_to_ready_with_suffix_strips_and_clears_mentors ... ok
test status::wire::tests::json_shape_keeps_optional_fields_as_null ... ok
test status::planner::tests::workspace_suffix_normalised_for_validation ... ok
test status::wire::tests::plan_round_trips_through_json ... ok
test status::wire::tests::schema_mismatch_returns_error ... ok
test status::wire::tests::request_round_trips_through_json ... ok
test store_lock::tests::timeout_parser_accepts_positive_floats_and_rejects_bad_values ... ok
test runner_limit_override::tests::persisted_json_is_complete_and_clear_is_idempotent ... ok
test provider_usage::tests::store::usage_store_uses_private_file_permissions_and_ignores_temp_siblings ... ok
test stranded_work::tests::cause_child_landed_and_newer_agent_turn_wins ... ok
test stranded_work::tests::cause_close_failed_kept_unclosed ... ok
test provider_usage::tests::attempt_policy::adaptive_health_reports_retry_at_and_failure_reason ... ok
test stranded_work::tests::cause_failed ... ok
test stranded_work::tests::cause_followup_failed_variants ... ok
test stranded_work::tests::cause_stopped ... ok
test stranded_work::tests::cause_lost_for_dead_local_non_terminal ... ok
test stranded_work::tests::non_candidate_context_has_no_verdict ... ok
test provider_priority::tests::concurrent_priority_changes_and_auto_disables_are_serialized ... ok
test stranded_work::tests::owned_each_pending_handoff_kind ... ok
test stranded_work::tests::delegation_needs_launched_child_epic ... ok
test stranded_work::tests::owned_followup_launched_with_running_successor ... ok
test stranded_work::tests::owned_finalizing_beats_done_lifecycle ... ok
test stranded_work::tests::owned_monitor_and_gate_turn_states ... ok
test stranded_work::tests::owned_lifecycle_kinds ... ok
test stranded_work::tests::owned_monitor_followup_pending ... ok
test stranded_work::tests::owned_remote_non_terminal_is_never_lost ... ok
test stranded_work::tests::owned_recovery_in_flight_beats_failed_lifecycle ... ok
test stranded_work::tests::owner_is_newest_qualifying_member ... ok
test stranded_work::tests::propagation_walks_through_stranded_ancestors ... ok
test stranded_work::tests::settling_within_grace_and_exact_boundary ... ok
test stranded_work::tests::sase_1n6_shape ... ok
test stranded_work::tests::shuffled_input_reduces_identically ... ok
test stranded_work::tests::stranded_epic_blocks_parent_phase ... ok
test stranded_work::tests::unknown_when_no_members ... ok
test stranded_work::tests::wire_defaults_and_unknown_fields ... ok
test sudo::tests::attempt_accepts_legacy_records_without_remote_handoff ... ok
test sudo::tests::attempt_accepts_valid_remote_handoff_metadata ... ok
test sudo::tests::attempt_liveness_classifies_local_started_from_host_facts ... ok
test sudo::tests::attempt_liveness_treats_legacy_missing_fields_as_unknown ... ok
test sudo::tests::attempt_liveness_keeps_remote_and_starting_attempts_unknown ... ok
test sudo::tests::canonical_manifest_sorts_object_keys_but_preserves_command_order ... ok
test sudo::tests::exec_started_validates_against_manifest_digest ... ok
test bead::read_model::tests::tail_applies_new_issue_stream ... ok
test sudo::tests::fit_ledger_is_noop_when_it_already_fits ... ok
test sudo::tests::attempt_rejects_malformed_remote_handoff_metadata ... ok
test sudo::tests::exec_started_rejects_bad_kind_digest_pid_paths_identity_and_time ... ok
test sudo::tests::fit_ledger_rejects_impossible_budget ... ok
test sudo::tests::fit_ledger_marker_reports_omitted_utf8_bytes ... ok
test sudo::tests::fit_ledger_respects_multibyte_utf8_and_escape_expansion ... ok
test sudo::tests::ledger_diagnostic_is_runner_error_only ... ok
test sudo::tests::ledger_rejects_status_exit_code_mismatches_and_wrong_order ... ok
test sudo::tests::ledger_validates_against_manifest_order_and_hash ... ok
test sudo::tests::fit_ledger_is_idempotent ... ok
test sudo::tests::output_tail_does_not_split_utf8 ... ok
test sudo::tests::risk_badges_are_ordered_deduped_and_remote_lockout_only ... ok
test sudo::tests::fit_ledger_is_deterministic ... ok
test sudo::tests::risk_detects_system_path_writes_and_service_near_misses ... ok
test sudo::tests::manifest_digest_changes_for_execution_relevant_fields ... ok
test sudo::tests::validation_rejects_forbidden_env_and_nested_elevation ... ok
test sudo::tests::validation_rejects_relative_cwd_duplicate_id_and_missing_resume ... ok
test suffix::tests::entry_ref_recognizes_digit_optional_letter ... ok
test sudo::tests::settlement_authorization_rejects_mismatched_digest_and_commands ... ok
test suffix::tests::legacy_tilde_colon_is_plain ... ok
test suffix::tests::long_prefixes_take_priority_over_short ... ok
test suffix::tests::metahook_promotes_error_to_metahook_complete ... ok
test suffix::tests::none_input_returns_none_pair ... ok
test suffix::tests::standalone_markers_have_empty_value ... ok
test suffix::tests::unknown_prefix_returns_value_unchanged ... ok
test sudo::tests::settlement_authorization_matches_attempt_and_replays_exact_digest ... ok
test task_type::render::tests::missing_placeholder_value_is_an_error ... ok
test task_type::render::tests::empty_without_template ... ok
test task_type::render::tests::does_not_rescan_substituted_values ... ok
test task_type::snapshot::tests::parse_rejects_invalid_json ... ok
test sudo::tests::fit_ledger_water_fill_keeps_small_entries ... ok
test task_type::render::tests::renders_placeholders_verbatim ... ok
test task_type::spec::tests::accepts_flag_as_a_claimable_task_type_slug ... ok
test task_type::spec::tests::accepts_single_cell_glyph_and_hex_accent ... ok
test task_type::spec::tests::accepts_spec_with_no_body_template ... ok
test task_type::snapshot::tests::rejects_digest_mismatch_and_duplicate_slugs ... ok
test task_type::spec::tests::digest_is_stable_across_omitted_and_explicit_defaults ... ok
test task_type::spec::tests::field_types_are_the_scalar_subset_of_property_types ... ok
test task_type::spec::tests::omitted_create_refusal_does_not_change_digest ... ok
test task_type::snapshot::tests::round_trips_and_sorts_by_slug ... ok
test task_type::spec::tests::create_refusal_changes_digest_and_rejects_empty_or_overlong ... ok
test task_type::spec::tests::rejects_empty_or_unknown_roles ... ok
test task_type::spec::tests::rejects_empty_enum_values_and_invalid_regex ... ok
test task_type::spec::tests::rejects_missing_label_summary_and_when_to_use_caps ... ok
test task_type::spec::tests::rejects_reserved_and_malformed_slugs ... ok
test task_type::snapshot::tests::round_trips_optional_create_refusal_and_omits_it_when_absent ... ok
test task_type::spec::tests::rejects_malformed_glyph_and_accent ... ok
test task_type::spec::tests::rejects_unknown_default_size ... ok
test task_type::spec::tests::rejects_unsupported_schema_version ... ok
test task_type::spec::tests::rejects_duplicate_and_bad_field_names ... ok
test task_type::spec::tests::reserved_slugs_are_the_three_issue_types_and_four_filter_sentinels ... ok
test task_type::spec::tests::rejects_template_placeholders_that_are_undeclared_or_data_only ... ok
test task_type::spec::tests::valid_spec_passes_and_digest_is_stable ... ok
test task_type::spec::tests::rejects_validator_keys_on_the_wrong_field_type ... ok
test task_type::values::tests::invalid_spec_is_a_hard_error ... ok
test task_type::spec::tests::rejects_unsupported_field_types_outside_scalar_subset ... ok
test task_type::values::tests::rejects_padded_or_non_decimal_integers_and_short_dates ... ok
test task_type::values::tests::empty_required_string_is_missing ... ok
test provider_usage::tests::admission_policy::mark_hot_coalesces_and_caps ... ok
test runner_limit_override::tests::exact_and_no_expiry_records_obey_boundary_expiry ... ok
test service::state::tests::none_boot_id_semantics_match_only_none ... ok
test provider_usage::tests::store::usage_store_advances_generation_and_rejects_stale_writers ... ok
test service::state::tests::corrupt_file_is_reported_on_read_and_quarantined_on_mutate ... ok
test provider_usage::tests::admission_policy::floor_blocks_marked_due_and_reset_passed ... ok
test task_type::values::tests::reports_missing_unknown_and_invalid_together ... ok
test service::status::tests::status_snapshot_writes_reads_and_rejects_bad_files ... ok
test task_type::values::tests::valid_values_return_no_errors ... ok
test text_tail::tests::applies_line_budget_before_character_budget ... ok
test text_tail::tests::keeps_short_text_unchanged ... ok
test task_type::values::tests::reports_string_max_length_and_allows_optional_fields_to_be_absent ... ok
test text_tail::tests::trims_selected_tail_by_unicode_character_count ... ok
test text_tail::tests::zero_character_budget_returns_empty_tail_after_line_selection ... ok
test text_tail::tests::zero_line_budget_returns_empty_tail ... ok
test tool_run::canonical::tests::object_keys_are_sorted_before_hashing ... ok
test tool_run::catalog::tests::default_args_policy_is_deny ... ok
test tool_run::catalog::tests::digest_is_stable_for_reordered_optional_lists ... ok
test tool_run::catalog::tests::golden_definition_fixture_normalizes ... ok
test tool_run::catalog::tests::duration_class_does_not_move_digest ... ok
test tool_run::catalog::tests::rejects_absolute_and_parent_input_paths ... ok
test tool_run::catalog::tests::golden_duration_fixture_matches_undeclared_digest ... ok
test tool_run::catalog::tests::rejects_empty_argv_and_unknown_schema ... ok
test tool_run::catalog::tests::undeclared_duration_class_is_omitted_from_output ... ok
test tool_run::catalog::tests::unknown_duration_class_names_the_value ... ok
test tool_run::duration::tests::calibration_flags_long_floor_above_typical ... ok
test tool_run::duration::tests::calibration_flags_short_typical_meeting_long_floor ... ok
test tool_run::duration::tests::calibration_rejects_unknown_schema ... ok
test tool_run::duration::tests::calibration_stays_silent_below_minimum_samples ... ok
test tool_run::duration::tests::calibration_stays_silent_when_class_matches_typical ... ok
test tool_run::duration::tests::calibration_stays_silent_without_typical ... ok
test tool_run::duration::tests::calibration_suggests_bounded_class_for_unbounded ... ok
test tool_run::duration::tests::fit_refuses_floor_at_or_above_ceiling ... ok
test tool_run::duration::tests::fit_rejects_zero_ceiling_and_unknown_schema ... ok
test tool_run::duration::tests::fit_reports_effective_class_and_floor ... ok
test tool_run::duration::tests::fit_without_ceiling_always_fits ... ok
test tool_run::duration::tests::sync_wait_budget_echoes_positive_ceilings ... ok
test tool_run::duration::tests::sync_wait_budget_pins_the_table ... ok
test tool_run::duration::tests::sync_wait_budget_rejects_zero_and_unknown_schema ... ok
test task_type::values::tests::validates_enum_integer_and_date ... ok
test tool_run::fingerprint::tests::golden_unknown_evidence_fixture_stays_explicit ... ok
test tool_run::fingerprint::tests::rejects_physical_checkout_paths_in_dirty_entries ... ok
test tool_run::fingerprint::tests::unknown_evidence_is_explicit_not_zero ... ok
test tool_run::fingerprint::tests::sorts_repos_and_dirty_paths_before_digest ... ok
test sudo::tests::fit_ledger_result_validates_and_fits ... ok
test runner_limit_override::tests::positive_limits_round_trip_and_replace ... ok
test service::state::tests::setting_and_clearing_enablement_round_trips ... ok
test provider_usage::tests::attempt_policy::superseded_generation_schedules_pruned_on_write ... ok
test tool_run::projection::tests::bucket_precedence_covers_every_state_cause_and_verdict ... ok
test project_stats::snapshot::tests::newly_included_blob_that_was_previously_skipped_is_read ... ok
test tool_run::projection::tests::detail_rejects_bad_requests ... ok
test telemetry::store::tests::wal_initialization_lock_wait_is_bounded ... ok
test store_lock::tests::timeout_names_holder_and_does_not_materially_overshoot_deadline ... ok
test provider_usage::tests::refresh::usage_refresh_reservations_join_release_and_expire ... ok
test service::state::tests::stop_expires_under_different_boot_and_is_pruned_on_write ... ok
test provider_disable::tests::v2_round_trip_get_set_try_set_and_clear_for_each_mode ... ok
test service::state::tests::proc_requests_survive_boot_changes_and_stay_absent_when_unused ... ok
test provider_usage::tests::store::usage_store_merges_partial_updates_and_fences_tombstones ... ok
test project_stats::query_tests::two_clones_share_coverage_identity_and_keep_isolated_history ... ok
test provider_usage::tests::attempt_policy::adaptive_attempt_streaks_and_cooldown_end_to_end ... ok
test project_stats::runs_tests::migration_oracle_matches_query_run_stats_per_project_and_patch ... ok
test provider_usage::tests::refresh::usage_refresh_failure_streak_tracks_first_failure_and_clears_on_success ... ok
test service::state::tests::markers_and_host_pid_guard_work ... ok
test service::state::tests::completing_a_proc_request_is_idempotent_for_stale_generations ... ok
test provider_usage::tests::store::usage_store_projects_current_generation_collector_health_only ... ok
test provider_usage::tests::refresh::usage_refresh_mark_due_is_once_per_reason_and_survives_future_due ... ok
test tool_run::projection::tests::node_summaries_reject_bad_requests ... ok
test provider_usage::tests::attention::collection_problem_attention_requires_consistent_failure_with_cached_data ... ok
test tool_run::projection::tests::projections_report_a_missing_store ... ok
test bead::mutation::tests::proof_bounded::proof_history_remove_max_suffix_is_reused ... ok
test service::state::tests::proc_requests_bump_generation_and_clear_stops_and_completions ... ok
test tool_run::projection::tests::schema_version_mismatches_are_rejected ... ok
test tool_run::stats::tests::adhoc_runs_count_outside_groups ... ok
test tool_run::stats::tests::backtest_counts_predictions_from_lookback_priors ... ok
test tool_run::stats::tests::backtest_min_prior_boundary ... ok
test tool_run::stats::tests::backtest_misses_and_width_floor ... ok
test tool_run::stats::tests::backtest_window_slides_past_sixty_priors ... ok
test project_stats::snapshot::tests::corrupt_cache_and_wrong_classifier_version_rebuild ... ok
test tool_run::stats::tests::bare_cohort_excludes_extra_args ... ok
test tool_run::stats::tests::demand_aggregates ... ok
test tool_run::stats::tests::empty_group_reports_missing_not_zero ... ok
test tool_run::stats::tests::bare_cohort_requires_recorded_duration ... ok
test tool_run::stats::tests::every_route_branch ... ok
test tool_run::stats::tests::incomplete_fingerprint_is_unkeyed ... ok
test tool_run::stats::tests::legacy_kill_window_edges ... ok
test tool_run::stats::tests::kill_needs_ceiling_agent_and_inline_route ... ok
test tool_run::stats::tests::pressure_buckets_busy_shares_and_p90 ... ok
test tool_run::stats::tests::percentile_edges_use_nearest_rank ... ok
test tool_run::stats::tests::pressure_counts_distinct_runs_once_and_ignores_buckets_without_psi ... ok
test tool_run::stats::tests::pressure_empty_samples_leave_shares_missing ... ok
test tool_run::stats::tests::provider_labels ... ok
test tool_run::stats::tests::recorded_ceiling_kill_window_edges ... ok
test tool_run::stats::tests::repeats_after_censored_duplicates_and_unkeyed ... ok
test tool_run::stats::tests::rerun_window_edges ... ok
test tool_run::stats::tests::stage_backtests_run_per_description ... ok
test tool_run::stats::tests::stage_distributions_split_ok_failed_and_incomplete ... ok
test tool_run::stats::tests::stage_entries_without_offsets_sort_last ... ok
test tool_run::stats::tests::thresholds_echo_the_constants ... ok
test tool_run::stats::tests::trend_buckets_empty_days_and_offset ... ok
test tool_run::stats::tests::truncation_sets_flag_and_diagnostic ... ok
test project_stats::query_tests::mixed_available_unavailable_and_partial_sources ... ok
test tool_run::stats::tests::unsettled_kill_ends_at_created_plus_duration ... ok
test tool_run::stats::tests::waste_categories_are_exclusive ... ok
test provider_usage::tests::store::usage_store_unifies_claude_fable_probe_and_passive_windows ... ok
test project_stats::snapshot::tests::sloc_policy_does_not_reuse_nonblank_snapshot_and_prose_stays_nonblank ... ok
test runner_limit_override::tests::lock_wait_is_bounded ... ok
test project_stats::snapshot::tests::deletion_and_rename_reuse_unchanged_blob_oids ... ok
test project_stats::snapshot::tests::content_edit_rereads_only_the_changed_blob ... ok
test bead::read_model::tests::tail_applies_write_to_closed_bead ... ok
test provider_usage::tests::refresh::usage_refresh_admission_joins_defers_and_recovers_after_expiry ... ok
test bead::read_model::tests::warm_reads_count_serves_without_new_generations ... ok
test bead::mutation::tests::proof_bounded::proof_history_ready_marking_stays_bounded ... ok
test service::state::tests::concurrent_mutators_lose_no_updates ... ok
test tool_run::projection::tests::glance_reference_is_empty_without_a_match ... ok
test telemetry::store::tests::corrupt_store_is_quarantined_and_recreated ... ok
test tool_run::store::receipts_report::tests::empty_store_reports_zero ... ok
test procs::runtime::tests::orphan_sweep_converges_with_budget_and_validates_ids ... ok
test bead::mutation::tests::proof_bounded::proof_history_references_stay_bounded ... ok
test tool_run::projection::tests::detail_reports_missing_stores_and_runs ... ok
test tool_run::projection::tests::briefs_match_owners_and_reject_bad_requests ... ok
test bead::read_model::tests::tail_applies_removals ... ok
test bead::mutation::tests::proof_bounded::proof_history_wait_claim_and_preclaim_stay_bounded ... ok
test tool_run::store::stats_tests::days_outside_range_is_invalid ... ok
test tool_run::store::receipts_report::tests::rejects_negative_days_and_bad_schema ... ok
test tool_run::store::stats_tests::missing_store_returns_empty_report ... ok
test tool_run::store::stats_tests::perf_stats_report_ten_thousand_runs ... ignored
test telemetry::store::tests::histogram_quantile_interpolates_cumulative_buckets ... ok
test tool_run::store::demand_tests::run_without_demand_serializes_without_the_field ... ok
test project_stats::snapshot::tests::shared_oid_retains_each_parser_and_attributes_reclassify_without_reread ... ok
test tool_run::projection::tests::brief_labels_derive_from_argv_and_cap_at_12_chars ... ok
test telemetry::store::tests::counter_deltas_aggregate_and_group ... ok
test telemetry::store::tests::gauge_instant_query_uses_latest_live_value_per_source ... ok
test bead::mutation::tests::proof_bounded::proof_history_links_stay_bounded ... ok
test tool_run::projection::tests::detail_stage_counts_join_items_by_stage_and_cap_locators ... ok
test tool_run::projection::tests::detail_returns_brief_stages_argv_logs_and_children ... ok
test tool_run::projection::tests::glance_and_briefs_flag_stop_requests ... ok
test tool_run::store::receipts_report::tests::missing_runs_table_reports_ledger_unavailable ... ok
test tool_run::projection::tests::projections_never_emit_private_argv ... ok
test provider_usage::tests::refresh::usage_refresh_future_disable_expiry_preserves_marker_and_recovers_cadence ... ok
test project_stats::snapshot::tests::blob_cache_prunes_facts_from_superseded_content_versions ... ok
test bead::mutation::tests::proof_bounded::proof_history_plus_one_and_snooze_stay_bounded ... ok
test tool_run::store::demand_tests::replay_with_invalid_grant_reports_drops_without_rewriting ... ok
test tool_run::store::tests::golden_observe_and_reap_fixtures_pin_the_wire_shape ... ok
test tool_run::projection::tests::glance_reports_stage_progress_from_started_only_rows ... ok
test tool_run::projection::tests::projections_work_on_a_pre_index_store ... ok
test tool_run::store::demand_tests::diagnostics_append_unique_and_cap ... ok
test tool_run::store::demand_tests::settled_runs_accept_demand_and_unknown_runs_are_not_found ... ok
test tool_run::store::tests::begin_commits_created_and_running_together ... ok
test tool_run::projection::tests::glance_typical_matches_summarize ... ok
test tool_run::store::demand_tests::malformed_stored_demand_reads_as_absent_with_a_diagnostic ... ok
test tool_run::store::tests::handoff::golden_handoff_fixtures_pin_the_wire_shape ... ok
test provider_priority::tests::lock_wait_is_bounded ... ok
test tool_run::projection::tests::glance_last_activity_prefers_newer_samples_or_stages ... ok
test tool_run::projection::tests::node_summaries_match_agents_owners_and_since ... ok
test tool_run::projection::tests::projections_tolerate_missing_triage_tables ... ok
test tool_run::store::demand_tests::legacy_store_gains_the_column_on_write_and_reads_without_it ... ok
test tool_run::store::tests::busy_failure_is_bounded ... ok
test tool_run::projection::tests::glance_lists_unsettled_newest_first ... ok
test tool_run::store::demand_tests::grants_dedup_cap_and_invalid_drops ... ok
test project_stats::snapshot::tests::sloc_cache_reuses_parser_inputs_across_renames_and_role_changes ... ok
test tool_run::store::tests::handoff::starter_requires_handoff_and_valid_fields ... ok
test tool_run::store::tests::corrupt_store_is_quarantined_on_write_and_recreated ... ok
test tool_run::projection::tests::glance_carries_join_fact_through_join_and_release ... ok
test tool_run::store::demand_tests::merge_combines_context_usage_and_grants_across_writes ... ok
test tool_run::projection::tests::briefs_filter_and_paginate ... ok
test tool_run::projection::tests::node_summaries_page_and_group_by_tool ... ok
test tool_run::store::receipts_report::tests::incomplete_fingerprint_is_uncomparable ... ok
test tool_run::store::tests::compat::new_shape_store_stays_loadable_by_old_query ... ok
test tool_run::store::tests::queries_do_not_create_a_missing_store ... ok
test tool_run::store::receipts_report::tests::report_is_read_only ... ok
test tool_run::store::tests::receipt::digest_unchanged_when_only_receipt_differs ... ok
test tool_run::store::tests::compat::old_queries_load_store_with_triage_rows ... ok
test tool_run::store::tests::concurrent_begins_do_not_livelock ... ok
test tool_run::projection::tests::brief_detail_pruned_marks_settled_runs_without_stages ... ok
test telemetry::store::tests::retention_folds_through_both_rollup_tiers_before_deletion ... ok
test tool_run::store::receipts_report::tests::missing_receipt_table_stays_empty_without_diagnostic ... ok
test tool_run::projection::tests::detail_triage_items_order_witnesses_and_truncate ... ok
test tool_run::store::tests::event_replay_is_idempotent_and_conflicts_are_integrity_errors ... ok
test tool_run::store::stats_tests::unmigrated_store_without_demand_column_still_loads ... ok
test tool_run::store::tests::handoff::handoff_begin_stores_launcher_with_null_wrapper ... ok
test tool_run::store::tests::handoff::handoff_begin_rejects_invalid_combinations ... ok
test tool_run::store::tests::handoff::duplicate_run_id_returns_duplicate_run ... ok
test tool_run::store::tests::handoff::queries_never_expose_the_envelope ... ok
test tool_run::store::tests::receipt::policy_normalization_matrix ... ok
test tool_run::store::tests::handoff::handoff_begin_with_starter_persists_and_shows ... ok
test tool_run::store::tests::finish_stores_canonical_fingerprints_and_mutated_input ... ok
test tool_run::store::tests::handoff::claim_succeeds_and_replays ... ok
test tool_run::store::tests::handoff::join_rejects_bad_ids_before_a_store_write ... ok
test tool_run::store::stats_tests::malformed_sample_payload_is_skipped_with_a_diagnostic ... ok
test tool_run::store::tests::private_argv_is_not_serialized_on_queries ... ok
test tool_run::store::tests::compat::old_retention_deletes_cascade_triage_rows ... ok
test bead::mutation::tests::snooze_plus_one::reopening_and_launch_claiming_a_snoozed_task_drop_the_record ... ok
test tool_run::store::tests::newer_schema_is_refused_without_modification ... ok
test tool_run::store::receipts_report::tests::window_bounds_exclude_old_runs ... ok
test tool_run::store::tests::incomplete_fingerprints_do_not_guess_mutated_input ... ok
test tool_run::store::tests::handoff::join_agent_rules ... ok
test tool_run::store::tests::compat::retention_reports_and_deletes_triage_and_stage_output ... ok
test tool_run::store::tests::invalid_transition_is_an_error ... ok
test tool_run::store::receipts_report::tests::missing_git_history_is_uncomparable ... ok
test tool_run::store::tests::handoff::claim_with_pending_stop_settles_stopped ... ok
test tool_run::store::receipts_report::tests::dirty_tree_committed_counts_as_opportunity ... ok
test telemetry::store::tests::exact_label_cleanup_previews_and_deletes_every_tier ... ok
test tool_run::store::receipts_report::tests::identical_repeats_group_together ... ok
test tool_run::store::tests::handoff::join_first_write_replay_and_elsewhere ... ok
test tool_run::store::tests::retention_previews_quarantined_store_without_live_store ... ok
test tool_run::store::tests::handoff::finish_cause_table_and_diagnostics_persist ... ok
test tool_run::store::tests::observe_then_lost_reports_an_authorized_reap_candidate ... ok
test tool_run::store::tests::observe_then_finish_repeats_child_facts_idempotently ... ok
test tool_run::store::tests::handoff::claim_refusals_are_typed ... ok
test tool_run::store::tests::reconcile_marks_dead_wrappers_lost_without_inventing_duration ... ok
test tool_run::store::tests::reconcile_owner::created_owner_terminal_otherwise_settles_launch_failed ... ok
test tool_run::store::tests::reconcile_owner::created_owner_terminal_stop_settles_signaled ... ok
test tool_run::store::tests::reconcile_owner::created_owner_missing_launcher_dead_settles_launch_failed ... ok
test tool_run::store::tests::reconcile_owner::created_unknown_is_noop_with_diagnostic ... ok
test tool_run::store::tests::handoff::created_transitions_require_causes_and_no_codes ... ok
test tool_run::store::tests::reconcile_owner::created_owner_active_or_launcher_alive_is_noop ... ok
test tool_run::store::tests::triage::unused_imports_are_used ... ok
test tool_run::projection::tests::glance_reference_run_needs_same_digest_and_complete_stages ... ok
test tool_run::store::tests::reconcile_owner::handoff_never_reaps_and_settled_list_is_correct ... ok
test tool_run::store::tests::summary_never_substitutes_zero_for_missing_typical ... ok
test tool_run::store::tests::reconcile_without_an_observation_authorizes_no_reap ... ok
test tool_run::store::stats_tests::report_over_begin_finish_and_record_demand ... ok
test tool_run::store::tests::reconcile_owner::running_unknown_owner_is_noop ... ok
test tool_run::store::tests::retention_selects_quarantined_store_older_than_log_horizon ... ok
test tool_run::store::tests::triage_stage::stage_and_settle_reject_unknown_fields ... ok
test tool_run::projection::tests::detail_expected_stages_come_from_the_reference_run ... ok
test tool_run::store::tests::reconcile_owner::settled_reconcile_is_noop_without_new_event ... ok
test tool_run::store::tests::repeated_observation_replays_and_settled_or_missing_runs_reject ... ok
test tool_run::store::tests::version_rejection_and_unknown_evidence_slots ... ok
test tool_run::triage::tests::classification_is_permutation_stable ... ok
test tool_run::triage::tests::classify_and_verdict_fixture_round_trips ... ok
test tool_run::store::tests::reconcile_owner::running_worker_alive_or_owner_active_is_noop ... ok
test tool_run::triage::tests::cross_machine_evidence_never_witnesses ... ok
test tool_run::triage::tests::collisions_and_collapse ... ok
test tool_run::store::tests::receipt::eligible_pass_writes_one_active_row_and_retry_is_stable ... ok
test tool_run::triage::tests::generic_and_environment_are_always_unknown ... ok
test tool_run::store::tests::triage::validation_errors ... ok
test tool_run::triage::tests::cross_workspace_equality ... ok
test tool_run::triage::tests::knobs_tighten_known ... ok
test tool_run::triage::tests::ledger_adhoc_and_arg_mismatch_never_witness ... ok
test tool_run::triage::tests::ledger_baseline_is_flaky ... ok
test tool_run::triage::tests::ledger_bead_match_never_known ... ok
test tool_run::triage::tests::ledger_cleared_witness_is_not_known ... ok
test tool_run::triage::tests::ledger_cross_project_never_witnesses ... ok
test tool_run::triage::tests::ledger_known_witness_at_ancestor ... ok
test tool_run::triage::tests::ledger_same_fingerprint_pytest_flip_is_flaky ... ok
test tool_run::triage::tests::ledger_same_fingerprint_symvision_flip_is_not_flaky ... ok
test tool_run::triage::tests::ledger_touched_without_witness_is_new ... ok
test tool_run::triage::tests::ledger_untouched_without_evidence_is_unknown ... ok
test tool_run::triage::tests::owner_match_closed_within_lookback_is_possibly_fixed ... ok
test tool_run::triage::tests::owner_match_generic_filename_stoplist ... ok
test tool_run::triage::tests::owner_match_sase_191_3_probe_yields_no_owners ... ok
test tool_run::triage::tests::owner_match_location_and_title_cases ... ok
test tool_run::triage::tests::owner_matching_at_most_two_open_first ... ok
test tool_run::triage::tests::repeat_only_for_same_fingerprint_and_signatures ... ok
test tool_run::triage::tests::verdict_table_boundaries ... ok
test tool_run::triage::tests::verdict_terminal_causes_and_legacy_mapping ... ok
test tool_run::triage::tests::triage_fixture_round_trips ... ok
test vcs_log::aggregate::tests::aggregated_row_serializes_flat ... ok
test vcs_log::aggregate::tests::empty_input_returns_empty ... ok
test vcs_log::aggregate::tests::equal_timestamp_tie_break_is_repo_then_full_id ... ok
test vcs_log::aggregate::tests::interleaves_repos_by_timestamp_desc ... ok
test vcs_log::aggregate::tests::limit_zero_returns_empty ... ok
test vcs_log::aggregate::tests::preserves_commit_presence ... ok
test vcs_log::aggregate::tests::truncates_to_limit ... ok
test tool_run::triage::tests::display_bounding_and_redaction ... ok
test vcs_log::classify::tests::ahead_wins_when_sets_overlap ... ok
test vcs_log::classify::tests::classifies_synced_ahead_and_behind ... ok
test vcs_log::commit_type::tests::auto_type_alias_deduplicates_to_automatic ... ok
test vcs_log::commit_type::tests::automatic_commit_includes_concrete_terminal_type ... ok
test vcs_log::commit_type::tests::commit_wrapper_uses_subject_body_and_parent_count ... ok
test vcs_log::commit_type::tests::ignores_non_terminal_tag_shaped_text ... ok
test vcs_log::commit_type::tests::includes_merge_and_patch_labels_after_concrete_type ... ok
test vcs_log::commit_type::tests::legacy_stitch_inference_still_uses_stitch_provenance ... ok
test vcs_log::commit_type::tests::legacy_patch_key_and_empty_patch_values_are_handled ... ok
test vcs_log::commit_type::tests::manual_commit_has_only_manual_type ... ok
test vcs_log::commit_type::tests::stitch_type_deduplicates_provenance_and_concrete_type ... ok
test vcs_log::merge_summary::tests::merge_prefix_without_known_shape_returns_none ... ok
test vcs_log::merge_summary::tests::parses_branch_summary ... ok
test vcs_log::merge_summary::tests::parses_branch_summary_with_target ... ok
test vcs_log::merge_summary::tests::parses_github_pull_request_summary ... ok
test vcs_log::merge_summary::tests::parses_remote_branch_summary ... ok
test vcs_log::merge_summary::tests::parses_remote_branch_summary_with_target ... ok
test tool_run::triage::tests::version_refusal_and_status_precedence ... ok
test vcs_log::merge_summary::tests::partial_pull_request_shape_returns_none ... ok
test vcs_log::merge_summary::tests::pull_request_empty_body_has_no_headline ... ok
test vcs_log::merge_summary::tests::unrecognized_subject_returns_none ... ok
test vcs_log::origin::tests::classifies_plain_commit_as_manual ... ok
test vcs_log::origin::tests::ignores_tag_shaped_body_text ... ok
test vcs_log::origin::tests::legacy_agent_bead_or_plan_classifies_as_stitch ... ok
test vcs_log::origin::tests::legacy_type_spelling_classifies_as_stitch ... ok
test vcs_log::origin::tests::non_stitch_type_classifies_as_auto ... ok
test vcs_log::origin::tests::type_stitch_classifies_as_stitch ... ok
test vcs_log::parsers::tests::body_containing_unit_separator_stays_in_body ... ok
test vcs_log::parsers::tests::empty_stream_returns_empty ... ok
test vcs_log::parsers::tests::commit_with_stitch_type_gets_stitch_origin ... ok
test vcs_log::parsers::tests::git_appends_newline_between_records_is_stripped ... ok
test vcs_log::parsers::tests::legacy_seven_field_commit_has_no_parents ... ok
test vcs_log::parsers::tests::multiline_body_is_preserved_verbatim ... ok
test vcs_log::parsers::tests::multiple_commits_preserve_order ... ok
test vcs_log::parsers::tests::octopus_merge_parses_all_parent_ids ... ok
test vcs_log::parsers::tests::record_with_too_few_fields_is_dropped ... ok
test vcs_log::parsers::tests::record_with_unparseable_timestamp_is_dropped ... ok
test vcs_log::parsers::tests::root_commit_empty_parent_field_has_no_parents ... ok
test vcs_log::parsers::tests::single_commit_parses_all_fields ... ok
test vcs_log::parsers::tests::trailing_record_separator_yields_no_blank_commit ... ok
test wait_epic_follow::tests::attributed_epics_join_the_union ... ok
test wait_epic_follow::tests::clan_with_several_members_unions ... ok
test wait_epic_follow::tests::deadlock_guard_skips_own_epic_with_prefix ... ok
test wait_epic_follow::tests::dismissed_member_with_fresh_launch_still_blocks ... ok
test wait_epic_follow::tests::dismissed_reservation_blocks ... ok
test wait_epic_follow::tests::cycle_hook_blocks ... ok
test wait_epic_follow::tests::empty_members_are_none ... ok
test wait_epic_follow::tests::ended_launch_blocks_with_hint ... ok
test wait_epic_follow::tests::exact_own_bead_is_skipped ... ok
test wait_epic_follow::tests::launching_when_in_flight ... ok
test wait_epic_follow::tests::launching_overdue_after_grace ... ok
test wait_epic_follow::tests::launching_within_settle_window ... ok
test wait_epic_follow::tests::legacy_fallback_ignores_workers ... ok
test wait_epic_follow::tests::legacy_planner_follows ... ok
test wait_epic_follow::tests::live_sibling_launch_keeps_dismissed_target_launching ... ok
test wait_epic_follow::tests::recorded_epics_follow_with_contributors ... ok
test wait_epic_follow::tests::since_preserved_on_same_state ... ok
test wait_epic_follow::tests::since_resets_on_transition ... ok
test wait_epic_follow::tests::skipped_launch_blocks_with_hint ... ok
test wait_epic_follow::tests::unresolved_agent_stays_agent ... ok
test wire::tests::delta_wire_uses_long_form ... ok
test wire::tests::empty_lists_serialize_as_arrays_not_null ... ok
test wire::tests::legacy_cl_or_pr_key_deserializes_as_pr_url ... ok
test wire::tests::legacy_wire_field_order_matches_python ... ok
test wire::tests::legacy_changespec_wire_deserializes_canonical_patch_shape ... ok
test wire::tests::none_fields_serialize_as_json_null ... ok
test wire::tests::parse_error_wire_shape ... ok
test wire::tests::patch_wire_deserializes_legacy_changespec_shape ... ok
test wire::tests::patch_wire_serializes_canonical_stitch_keys ... ok
test wire::tests::source_span_round_trips ... ok
test workspace_lease::tests::authorize_rejects_primary_and_reserved_numbers ... ok
test wire::tests::populated_patch_round_trips ... ok
test workspace_lease::tests::empty_operation_uses_the_step_name_alone ... ok
test workspace_lease::tests::failure_message_names_step_and_forbids_primary_fallback ... ok
test workspace_lease::tests::normalize_maps_legacy_primary_only ... ok
test workspace_lease::tests::pool_bounds_match_unified_claim_range ... ok
test workspace_lease::tests::primary_error_names_legacy_spelling ... ok
test workspace_lease::tests::validate_policy_requires_kind_identity_and_leasable_workspace ... ok
test tool_run::store::tests::receipt::expiry_boundary_keeps_row ... ok
test tool_run::store::tests::triage::label_first_writer_wins ... ok
test tool_run::store::tests::receipt::eligible_no_new_failures_stores_refs ... ok
test tool_run::store::tests::receipt::fingerprint_drift_and_definition_change ... ok
test tool_run::store::tests::reconcile_reports_candidates_only_for_observed_runs ... ok
test tool_run::store::tests::triage::finish_keeps_recorded_fingerprint_before ... ok
test provider_disable::tests::lock_wait_is_bounded ... ok
test tool_run::triage::tests::golden_extractor_fixtures ... ok
test tool_run::store::tests::triage::idempotent_replay_changes_nothing ... ok
test provider_disable::tests::try_set_rejects_invalid_inputs_and_times_out_on_lock ... ok
test tool_run::store::tests::handoff::continuation_mode_round_trips_through_claim ... ok
test tool_run::store::tests::handoff::stop_first_wins_and_settled_writes_nothing ... ok
test tool_run::store::tests::receipt::store_stats_counts_and_missing_table_is_zero ... ok
test tool_run::store::tests::every_terminal_state_round_trips ... ok
test tool_run::store::tests::triage::record_then_show_round_trip ... ok
test tool_run::store::tests::handoff::release_join_matrix ... ok
test tool_run::store::tests::triage::refusals_for_missing_and_adhoc_runs ... ok
test tool_run::store::tests::receipt::corrupt_proof_is_not_covered_and_tombstones_on_retention ... ok
test tool_run::store::tests::receipt::lookup_refusals_for_incomplete_and_policy_version ... ok
test tool_run::store::tests::receipt::unexpired_receipt_survives_source_run_pruning ... ok
test tool_run::store::tests::retention_protects_unsettled_runs ... ok
test tool_run::store::tests::receipt::retention_deletes_expired_and_counts_detail_rows ... ok
test tool_run::store::tests::reconcile_owner::foreground_lost_records_wrapper_lost_and_reap_only_unowned ... ok
test tool_run::store::tests::triage::observe_persists_fingerprint_before ... ok
test tool_run::store::tests::triage::show_on_missing_store_and_old_store ... ok
test bead::mutation::tests::proof_bounded::proof_history_notes_family_stays_bounded ... ok
test tool_run::store::tests::reconcile_owner::running_timeout_and_stop_settle_signaled ... ok
test tool_run::store::tests::triage::record_creates_missing_triage_tables ... ok
test tool_run::store::tests::reconcile_owner::running_recovers_owner_success_and_error ... ok
test tool_run::store::tests::receipt::earlier_run_does_not_supersede_newer ... ok
test tool_run::store::tests::unknown_liveness_is_not_proof_of_death ... ok
test tool_run::store::tests::handoff::join_refuses_without_starter_stop_or_settlement ... ok
test tool_run::projection::tests::brief_verdict_buckets_follow_state_cause_and_triage ... ok
test tool_run::store::tests::compat::old_store_without_triage_tables_show_empty_and_record_creates ... ok
test tool_run::store::tests::triage_stage::show_supports_owner_lookup ... ok
test tool_run::store::tests::compat::old_shape_store_is_readable_and_migrates_on_write ... ok
test tool_run::store::tests::retention_aggregate_target_deletes_oldest_settled_logs_first ... ok
test tool_run::store::tests::triage_stage::stage_is_idempotent_and_first_writer_wins ... ok
test tool_run::store::tests::reconcile_owner::running_supervisor_loss_or_missing_settles_owner_lost ... ok
test tool_run::store::tests::triage_stage::stage_settle_show_round_trip_with_verdict ... ok
test tool_run::store::tests::triage_stage::known_witness_across_runs_in_store ... ok
test tool_run::store::tests::receipt::no_new_failures_matrix ... ok
test tool_run::store::tests::triage_stage::failures_aggregation_filters_and_isolation ... ok
test store_lock::tests::waiter_acquires_after_more_than_the_old_two_second_bound ... ok
test tool_run::store::tests::triage_stage::failures_affected_runs_off_by_default ... ok
test tool_run::store::tests::triage_stage::control_and_infra_produce_no_labels ... ok
test tool_run::store::tests::receipt::later_non_success_invalidates_and_recovery_succeeds ... ok
test tool_run::store::tests::triage_stage::failures_affected_runs_bounded_newest_first ... ok
test tool_run::store::tests::receipt::old_reader_opens_store_with_receipts_and_lookup_is_no_receipt ... ok
test tool_run::store::tests::receipt::no_mint_matrix_writes_zero_rows ... ok
test telemetry::store::tests::concurrent_writers_preserve_every_delta ... ok
test tool_run::store::tests::receipt::ineligible_fingerprint_and_settlement_cases ... ok
test tool_run::store::receipts_report::tests::git_budget_exhaustion_stays_uncomparable ... ok
test tool_run::store::stats_tests::report_includes_stages_backtest_and_pressure ... ok
test tool_run::projection::tests::brief_page_of_50_runs_stays_under_64k_with_fingerprints ... ok
test bead::mutation::tests::snooze_plus_one::task_plus_one_open_and_active_statuses_preserve_existing_contract ... ok
test tool_run::store::receipts_report::tests::scan_window_is_bounded_to_newest_500 ... ok
test tool_run::store::receipts_report::tests::uncomparable_output_is_bounded ... ok
test tool_run::projection::tests::glance_caps_at_200_runs_with_truncated ... ok
test bead::mutation::tests::replay_goldens::replay_golden_bytes_are_pinned ... ok
test bead::mutation::tests::replay_goldens::cached_golden_bytes_match_replay has been running for over 60 seconds
test bead::mutation::tests::replay_goldens::cached_golden_bytes_match_replay ... ok

test result: ok. 5356 passed; 0 failed; 4 ignored; 0 measured; 0 filtered out; finished in 142.20s

     Running tests/agent_scan_parity.rs (/home/bryan/.cache/sase/tmp/cargo-targets/gh_sase-org__sase-ws14-261024_085653/build/debug/deps/agent_scan_parity-7501f5f38c38959b)

running 45 tests
test missing_root_returns_empty_snapshot ... ok
test explicit_agent_clan_preserves_sequential_agent_session_fields ... ok
test launch_xprompts_preserves_swarm_kind ... ok
test imported_source_owner_survives_live_scan ... ok
test launch_xprompts_project_to_deduplicated_deterministic_records ... ok
test absent_and_invalid_xprompts_are_soft_scan_errors ... ok
test scalar_agent_meta_timestamps_are_normalized_to_lists ... ok
test scanner_keeps_parent_epic_and_authored_plan_references_separate ... ok
test scanner_accepts_mixed_legacy_and_day_sharded_ace_run_dirs ... ok
test exact_dir_scan_returns_only_requested_valid_unique_dirs ... ok
test exact_dir_scan_honors_project_and_workflow_filters ... ok
test bounded_not_before_applies_to_completed_rows_only ... ok
test disable_prompt_step_markers ... ok
test failed_record_carries_error_and_traceback ... ok
test workflow_root_record_has_state_and_steps ... ok
test only_workflow_dirs_filters_records ... ok
test running_record_carries_wait_completed_at ... ok
test running_record_prefers_canonical_agent_meta_tribe ... ok
test snapshot_serializes_to_json ... ok
test running_record_carries_bounded_json_output_variables ... ok
test artifact_index_metadata_helpers_round_trip ... ok
test artifact_index_status_counts_artifact_and_dismissed_rows ... ok
test done_record_parses_done_marker ... ok
test home_running_record_has_running_marker ... ok
test disable_raw_prompt_snippet ... ok
test bounded_newest_first_limits_completed_without_hiding_incomplete ... ok
test pending_question_marker_is_surfaced_when_present ... ok
test options_round_trip_through_snapshot ... ok
test records_are_sorted_deterministically ... ok
test pending_question_marker_is_absent_when_file_missing ... ok
test max_prompt_snippet_bytes_truncates ... ok
test malformed_agent_meta_is_skipped ... ok
test mentor_dir_is_walked ... ok
test retried_records_link_via_lineage_fields ... ok
test repeat_stopped_record_parses_repeat_stop_fields ... ok
test running_record_carries_agent_meta ... ok
test selective_marker_options_skip_payloads_but_keep_done_presence ... ok
test stats_count_decode_errors ... ok
test scan_returns_one_record_per_artifact_dir ... ok
test waiting_marker_decode_error_does_not_crash ... ok
test waiting_marker_carries_runner_slot_fields ... ok
test agent_session_parallel_survives_live_scan_and_indexed_reads ... ok
test workflow_state_hidden_is_parsed_and_indexed ... ok
test running_record_carries_linked_repos_through_scan_and_index ... ok
test plan_committed_survives_live_scan_and_indexed_reads ... ok

test result: ok. 45 passed; 0 failed; 0 ignored; 0 measured; 0 filtered out; finished in 0.23s

     Running tests/artifact_ref_commit_budget.rs (/home/bryan/.cache/sase/tmp/cargo-targets/gh_sase-org__sase-ws14-261024_085653/build/debug/deps/artifact_ref_commit_budget-a680c57b1248ec87)

running 1 test
test commit_inventory_budget_override_controls_whether_rows_survive ... ok

test result: ok. 1 passed; 0 failed; 0 ignored; 0 measured; 0 filtered out; finished in 0.28s

     Running tests/bead_event_parity.rs (/home/bryan/.cache/sase/tmp/cargo-targets/gh_sase-org__sase-ws14-261024_085653/build/debug/deps/bead_event_parity-3bf0f17f356c19c9)

running 35 tests
test close_event_stamps_an_issue_updated_to_closed_without_a_timestamp ... ok
test dependency_remove_payload_rejects_a_source_mismatch ... ok
test dependency_add_remove_add_replays_to_present ... ok
test byte_identical_concurrent_note_append_merges_once ... ok
test cross_stream_dependencies_resolve_after_all_creates ... ok
test dependency_remove_replay_tolerates_a_target_removed_first ... ok
test concurrent_note_appends_merge_without_losing_text ... ok
test event_validation_rejects_operation_payload_mismatch ... ok
test concurrent_close_projection_is_independent_of_branch_order ... ok
test dependency_remove_replay_is_tolerant_and_projection_round_trips ... ok
test every_transition_out_of_closed_starts_a_new_close_interval ... ok
test legacy_empty_timestamps_still_import_to_valid_events ... ok
test merge_event_stream_accepts_interleaved_additions_and_preserves_ids ... ok
test merge_event_stream_accepts_pure_reorder_branch ... ok
test merge_event_stream_keeps_exact_duplicate_append_once ... ok
test jsonl_import_to_events_reduces_to_byte_compatible_projection ... ok
test merge_event_stream_rejects_deleted_or_rewritten_base_events ... ok
test event_import_preserves_legacy_defaults_and_corrupt_jsonl_tolerance ... ok
test merge_event_stream_orders_non_base_union_deterministically ... ok
test merge_event_stream_keeps_non_monotonic_upstream_order ... ok
test note_appended_composes_after_a_legacy_note_snapshot ... ok
test event_import_mints_reproducible_content_hashed_ids ... ok
test reduce_applies_merged_stream_events_in_recorded_order ... ok
test note_appended_matches_legacy_note_rendering_and_composes ... ok
test merge_event_stream_supports_sequential_rebase_replay ... ok
test reducer_handles_current_mutation_operation_variants ... ok
test merge_event_stream_union_is_associative_and_idempotent ... ok
test reducer_removes_plan_children_and_dependency_edges_on_cascade_remove ... ok
test same_timestamp_dependency_add_replays_before_remove_across_streams ... ok
test redundant_close_keeps_the_first_close_projection ... ok
test merge_event_stream_unions_concurrent_appends_deterministically ... ok
test task_plus_one_replay_honors_observation_window_freshness ... ok
test serialized_event_store_fixture_matches_import_and_reduces ... ok
test reduce_survives_many_merged_streams_with_non_monotonic_timestamps ... ok
test write_event_store_leaves_an_unrelated_streams_bytes_unchanged_across_a_mutation ... ok

test result: ok. 35 passed; 0 failed; 0 ignored; 0 measured; 0 filtered out; finished in 0.04s

     Running tests/bead_read_model_mutation_proof.rs (/home/bryan/.cache/sase/tmp/cargo-targets/gh_sase-org__sase-ws14-261024_085653/build/debug/deps/bead_read_model_mutation_proof-bcb9fb708df7f18f)

running 2 tests
test bench_corpus_sampled_mutations ... ok
test cache_matches_replay_after_every_family_mutation ... ok

test result: ok. 2 passed; 0 failed; 0 ignored; 0 measured; 0 filtered out; finished in 9.03s

     Running tests/bead_read_model_parity.rs (/home/bryan/.cache/sase/tmp/cargo-targets/gh_sase-org__sase-ws14-261024_085653/build/debug/deps/bead_read_model_parity-8c8d0a7fb88ea87a)

running 6 tests
test bench_corpus_read_model_timings ... ok
test bench_corpus_sampled_parity ... ok
test cache_matches_replay_on_seeded_store ... ok
test concurrent_readers_see_consistent_snapshots ... ok
test cache_matches_replay_after_mutation_sequence has been running for over 60 seconds
test cache_matches_replay_with_adversarial_history has been running for over 60 seconds
test cache_matches_replay_with_adversarial_history ... ok
test cache_matches_replay_after_mutation_sequence ... ok

test result: ok. 6 passed; 0 failed; 0 ignored; 0 measured; 0 filtered out; finished in 177.21s

     Running tests/bead_read_parity.rs (/home/bryan/.cache/sase/tmp/cargo-targets/gh_sase-org__sase-ws14-261024_085653/build/debug/deps/bead_read_parity-3a2633f5de87ba85)

running 16 tests
test doctor_notes_explicitly_unavailable_plan_roots ... ok
test doctor_still_warns_when_a_legacy_store_lacks_issues_jsonl ... ok
test doctor_reports_orphan_nested_plan_records ... ok
test event_manifest_repair_refuses_invalid_canonical_streams ... ok
test doctor_reports_invalid_event_store_without_legacy_fallback ... ok
test issue_detail_preserves_unresolved_relationship_slots ... ok
test issue_detail_legacy_snapshot_keeps_import_compatible_fallback ... ok
test doctor_groups_plan_reference_diagnostics_without_changing_compatibility ... ok
test event_manifest_repair_refuses_unsupported_event_schema ... ok
test doctor_reports_projection_fields_and_redundant_close_census ... ok
test doctor_reports_orphans_in_stale_legacy_projection ... ok
test event_store_wins_over_stale_legacy_projection ... ok
test event_store_supports_read_queries_without_legacy_projection ... ok
test read_queries_match_python_contract_ordering ... ok
test event_manifest_repair_recounts_missing_or_stale_metadata_idempotently ... ok
test issue_detail_link_neighborhood_preserves_event_provenance ... ok

test result: ok. 16 passed; 0 failed; 0 ignored; 0 measured; 0 filtered out; finished in 0.14s

     Running tests/bead_storage_parity.rs (/home/bryan/.cache/sase/tmp/cargo-targets/gh_sase-org__sase-ws14-261024_085653/build/debug/deps/bead_storage_parity-45d10340f2fa5ea4)

running 8 tests
test corrupt_and_empty_fixtures_match_python_tolerance ... ok
test current_schema_fixture_loads_hierarchy_dependencies_and_metadata ... ok
test import_missing_file_returns_empty_outcome ... ok
test load_config_fixture_matches_python_shape ... ok
test import_from_file_uses_same_parser ... ok
test task_and_ready_values_round_trip_with_python_wire_spelling ... ok
test legacy_jsonl_fixtures_get_python_defaults ... ok
test export_current_fixture_is_byte_compatible ... ok

test result: ok. 8 passed; 0 failed; 0 ignored; 0 measured; 0 filtered out; finished in 0.00s

     Running tests/bead_touch_index_parity.rs (/home/bryan/.cache/sase/tmp/cargo-targets/gh_sase-org__sase-ws14-261024_085653/build/debug/deps/bead_touch_index_parity-ac2e7b3dbc3be23b)

running 2 tests
test fixture_store_reduces_to_the_pinned_snapshot ... ok
test per_actor_queries_are_exact_subsets_of_the_snapshot ... ok

test result: ok. 2 passed; 0 failed; 0 ignored; 0 measured; 0 filtered out; finished in 0.01s

     Running tests/command_line_perf.rs (/home/bryan/.cache/sase/tmp/cargo-targets/gh_sase-org__sase-ws14-261024_085653/build/debug/deps/command_line_perf-dbef23271881ac0d)

running 1 test
test command_line_perf_budgets ... ok

test result: ok. 1 passed; 0 failed; 0 ignored; 0 measured; 0 filtered out; finished in 0.04s

     Running tests/command_line_resolver.rs (/home/bryan/.cache/sase/tmp/cargo-targets/gh_sase-org__sase-ws14-261024_085653/build/debug/deps/command_line_resolver-131ed24c7ebd39e8)

running 28 tests
test confirms_flag_flow ... ok
test mini_extra_argument_beyond_fixed_nargs ... ok
test mini_alias_and_required_option ... ok
test mini_stacked_shorts_and_attached_value ... ok
test complete_dynamic_ordering_and_quoting ... ok
test prog_stripped_from_argv ... ok
test missing_required_and_variadic_ids ... ok
test unknown_subcommand_marks_rest_unknown ... ok
test status_choices_and_invalid_choice ... ok
test invariant_no_node_has_both_positionals_and_subcommands ... ok
test typing_in_progress_drops_prefix_diagnostic ... ok
test invariant_no_option_string_looks_like_negative_number ... ok
test mutex_suppresses_remove_but_keeps_help ... ok
test remainder_roles_and_argv ... ok
test equals_value_slot_adjusts_replace_start ... ok
test complete_partial_has_no_trailing_space_and_limit ... ok
test bare_group_uses_default_child ... ok
test unterminated_quote_reports_prefix ... ok
test signature_active_and_usage ... ok
test non_repeatable_flag_suppressed_elsewhere ... ok
test command_help_shapes ... ok
test unique_abbreviation_has_no_unknown_option ... ok
test schema_version_is_one ... ok
test bead_cl_is_subcommand_with_close_first ... ok
test run_policy_predicates ... ok
test invariant_no_greedy_positional_is_followed ... ok
test complete_dedupe_ors_selected ... ok
test bead_close_reason_value_slot ... ok

test result: ok. 28 passed; 0 failed; 0 ignored; 0 measured; 0 filtered out; finished in 0.07s

     Running tests/config_parity.rs (/home/bryan/.cache/sase/tmp/cargo-targets/gh_sase-org__sase-ws14-261024_085653/build/debug/deps/config_parity-891edc33483df50e)

running 36 tests
test axe_composition_diagnoses_unknown_layer_kind_and_ignores_its_section ... ok
test axe_composition_overlays_wait_runners_with_exact_provenance ... ok
test axe_composition_remaps_required_diagnostics_to_authored_public_paths ... ok
test axe_composition_merges_disjoint_same_layer_aliases_and_rejects_conflicts ... ok
test axe_composition_accepts_public_routine_job_aliases_with_source_provenance ... ok
test axe_description_requirements_validate_only_the_merged_config ... ok
test axe_composition_reports_attributed_legacy_and_identity_diagnostics ... ok
test axe_composition_retains_legacy_defaults_and_exact_key_provenance ... ok
test axe_inventory_generated_jobs_inherit_base_origin ... ok
test axe_inventory_marks_public_declarations_with_legacy_override ... ok
test axe_inventory_reports_job_newly_added_under_builtin_routine ... ok
test deep_merge_lists_replace_vs_concatenate ... ok
test axe_inventory_reports_overlay_and_local_declarations_as_user ... ok
test axe_inventory_resolves_first_declaration_across_legacy_and_public_spellings ... ok
test field_model_flattens_nested_and_classifies ... ok
test axe_inventory_reports_first_declaration_after_later_override ... ok
test inventory_diagnoses_glossary_outside_local_layer ... ok
test plan_edit_exact_key_path_preserves_dotted_mapping_keys ... ok
test axe_mutation_promotes_target_legacy_list_without_dropping_entries ... ok
test axe_mutation_writes_new_entries_to_canonical_paths ... ok
test axe_inventory_assigns_origin_to_every_entry ... ok
test plan_edit_rejects_missing_empty_and_contradictory_paths ... ok
test merge_layers_matches_python_deep_merge_golden ... ok
test plan_edit_unknown_target_errors ... ok
test plan_edit_promotes_list_form_jobs_with_exact_dotted_identities ... ok
test plan_edit_promotes_list_form_jobs_for_generic_public_edits ... ok
test plan_edit_set_builds_write_plan_and_preview ... ok
test axe_inventory_reports_user_declaration ... ok
test plan_edit_unset_removes_key_and_warns_on_readonly_target ... ok
test axe_inventory_reports_plugin_declaration_overridden_by_user ... ok
test inventory_reports_effective_value_and_provenance ... ok
test axe_entry_mutation_propagates_description_shape_to_diagnostics ... ok
test axe_inventory_marks_generated_instances_as_base_owned ... ok
test axe_entry_mutation_propagates_required_descriptions_to_preview ... ok
test axe_sparse_mutation_keeps_inherited_fields_and_matches_candidate_composition ... ok
test validate_detects_violations ... ok

test result: ok. 36 passed; 0 failed; 0 ignored; 0 measured; 0 filtered out; finished in 0.01s

     Running tests/continuation_contract.rs (/home/bryan/.cache/sase/tmp/cargo-targets/gh_sase-org__sase-ws14-261024_085653/build/debug/deps/continuation_contract-de9892e465025ba0)

running 1 test
test serial_replay_fixture_preserves_exact_parent_order ... ok

test result: ok. 1 passed; 0 failed; 0 ignored; 0 measured; 0 filtered out; finished in 0.00s

     Running tests/git_query_parity.rs (/home/bryan/.cache/sase/tmp/cargo-targets/gh_sase-org__sase-ws14-261024_085653/build/debug/deps/git_query_parity-a496c0e6228c9087)

running 33 tests
test derive_workspace_name_falls_back_to_root_path_when_remote_blank ... ok
test derive_workspace_name_falls_back_to_root_path_when_remote_none ... ok
test derive_workspace_name_https_remote_without_dot_git_suffix ... ok
test derive_workspace_name_https_remote_with_dot_git_suffix ... ok
test derive_workspace_name_path_like_remote ... ok
test derive_workspace_name_remote_dot_git_only_returns_none ... ok
test derive_workspace_name_remote_takes_priority_over_root ... ok
test derive_workspace_name_returns_none_when_both_inputs_empty ... ok
test derive_workspace_name_ssh_remote_with_dot_git_suffix ... ok
test git_name_status_entry_wire_round_trips_through_json ... ok
test git_name_status_entry_wire_serializes_to_python_shape ... ok
test git_query_wire_schema_version_is_one ... ok
test parse_branch_name_detached_head_returns_none ... ok
test parse_branch_name_empty_stdout_returns_none ... ok
test parse_branch_name_simple_value ... ok
test parse_branch_name_strips_surrounding_whitespace ... ok
test parse_branch_name_whitespace_only_returns_none ... ok
test parse_conflicted_files_empty_stdout_returns_empty_list ... ok
test parse_conflicted_files_only_blank_lines_returns_empty ... ok
test parse_conflicted_files_preserves_path_order ... ok
test parse_conflicted_files_strips_blank_lines ... ok
test parse_local_changes_clean_tree_returns_none ... ok
test parse_local_changes_dirty_tree_returns_stripped_text ... ok
test parse_local_changes_whitespace_only_returns_none ... ok
test parse_name_status_copy_with_score_carries_paired_paths ... ok
test parse_name_status_empty_stream_returns_empty_list ... ok
test parse_name_status_mixed_simple_and_rename_in_one_stream ... ok
test parse_name_status_rename_with_score_carries_paired_paths ... ok
test parse_name_status_simple_status_letters ... ok
test parse_name_status_skips_empty_status_tokens ... ok
test parse_name_status_trailing_nul_is_ignored ... ok
test parse_name_status_truncated_rename_falls_back_to_single_path ... ok
test parse_name_status_truncated_status_only_drops_entry ... ok

test result: ok. 33 passed; 0 failed; 0 ignored; 0 measured; 0 filtered out; finished in 0.00s

     Running tests/golden_corpus_parity.rs (/home/bryan/.cache/sase/tmp/cargo-targets/gh_sase-org__sase-ws14-261024_085653/build/debug/deps/golden_corpus_parity-cdfdf217f4c7e980)

running 3 tests
test archive_corpus_matches_python_golden_after_end_line_normalization ... ok
test rust_real_end_line_is_strictly_greater_than_python_placeholder ... ok
test project_corpus_matches_python_golden_after_end_line_normalization ... ok

test result: ok. 3 passed; 0 failed; 0 ignored; 0 measured; 0 filtered out; finished in 0.04s

     Running tests/hermetic_test_env.rs (/home/bryan/.cache/sase/tmp/cargo-targets/gh_sase-org__sase-ws14-261024_085653/build/debug/deps/hermetic_test_env-5579b1f3251db612)

running 1 test
test hermetic_test_env_is_in_force ... ok

test result: ok. 1 passed; 0 failed; 0 ignored; 0 measured; 0 filtered out; finished in 0.01s

     Running tests/notification_store_parity/main.rs (/home/bryan/.cache/sase/tmp/cargo-targets/gh_sase-org__sase-ws14-261024_085653/build/debug/deps/notification_store_parity-dec7bab0313c3c31)

running 83 tests
test mute_snooze_expiry::notification_activity_cursor_uses_resurface_time_and_id_tiebreaker ... ok
test plus_one_upsert::notification_plus_one_fields_default_and_skip_on_legacy_rows ... ok
test agent_dismissal::notification_dismiss_agent_completions_no_op_when_already_dismissed ... ok
test plus_one_upsert::notification_plus_one_appends_by_id_and_preserves_cursor ... ok
test agent_dismissal::notification_dismiss_agent_completions_matching_agents_is_completion_only ... ok
test agent_dismissal::notification_dismiss_agent_completions_matching_agents_matches_exact_settlement_rows ... ok
test agent_dismissal::notification_dismiss_agent_completions_matches_user_agent_jump_and_error ... ok
test agent_dismissal::notification_dismiss_matching_agents_matches_question_child_identity ... ok
test plus_one_upsert::notification_upsert_rejects_dedup_key_without_plus_one_note ... ok
test store_io::notification_json_shape_uses_expected_wire_keys ... ok
test store_io::notification_loads_legacy_defaults_and_skips_bad_rows ... ok
test store_io::notification_missing_file_returns_empty_snapshot ... ok
test store_io::notification_phase1_contract_fixture_loads_with_expected_counts ... ok
test agent_dismissal::notification_dismiss_agent_completions_matching_agents_skips_unmatched_settlement_rows ... ok
test store_io::notification_append_counts_returns_metadata_without_rows ... ok
test ack_index::notification_store_rejects_corrupt_generation_file ... ok
test plus_one_upsert::notification_upsert_supersede_no_match_is_silent ... ok
test reconcile_upsert::reconcile_never_marks_a_user_dismissal_reversible ... ok
test plus_one_upsert::notification_plus_one_no_match_and_invalid_requests ... ok
test store_io::notification_append_and_rewrite_round_trip_jsonl ... ok
test plus_one_upsert::notification_upsert_without_dedup_key_matches_append_bytes ... ok
test plus_one_upsert::notification_plus_one_by_key_picks_newest_including_dismissed ... ok
test store_io::notification_icon_round_trips_through_append_load_and_rewrite ... ok
test store_io::notification_append_counts_produces_byte_identical_jsonl ... ok
test plus_one_upsert::notification_plus_one_round_trip_and_legacy_jsonl_omits_empty_fields ... ok
test plus_one_upsert::notification_upsert_does_not_supersede_when_plus_oning ... ok
test agent_dismissal::notification_dismiss_matching_agents_covers_custom_gates ... ok
test mute_snooze_expiry::notification_expire_snoozes_handles_aware_and_naive_timestamps ... ok
test ack_index::notification_unread_index_lists_live_completion_and_settlement_rows ... ok
test mute_snooze_expiry::notification_snooze_validation_is_atomic_and_skips_ineligible_targets ... ok
test mute_snooze_expiry::notification_bulk_unmute_cancels_snoozes_and_reports_counts ... ok
test agent_dismissal::notification_dismiss_matching_agents_covers_notification_action_shapes ... ok
test mute_snooze_expiry::notification_bulk_mute_deduplicates_ids_and_reports_counts ... ok
test mute_snooze_expiry::notification_current_read_recovers_legacy_state_and_preserves_cancellations ... ok
test agent_dismissal::notification_dismiss_matching_agents_covers_user_agent_view_error_report ... ok
test mute_snooze_expiry::notification_bulk_snooze_uses_one_deadline_and_reports_counts ... ok
test agent_dismissal::notification_dismiss_agent_completions_leaves_settlement_rows_alone ... ok
test ack_index::notification_ack_dismisses_exact_rows_and_bumps_once ... ok
test store_io::notification_rewrite_counts_returns_metadata_without_rows ... ok
test reconcile_upsert::reconcile_skips_the_file_write_when_nothing_changed ... ok
test state_updates::notification_counts_match_python_priority_rules ... ok
test ack_index::notification_ack_and_index_generations_are_monotonic_across_threads ... ok
test reconcile_upsert::empty_raw_suffix_matches_like_a_missing_key_for_matching_agents ... ok
test reconcile_upsert::reconcile_appends_unknown_rows_and_skips_empty_ids ... ok
test reconcile_upsert::reconcile_resurfaces_marker_dismissed_rows ... ok
test state_updates::notification_state_update_counts_skips_returned_snapshot ... ok
test store_io::notification_rewrite_reaps_only_targeted_stale_temp_siblings ... ok
test reconcile_upsert::reconcile_auto_dismisses_with_the_marker ... ok
test mute_snooze_expiry::notification_snooze_normalizes_offsets_and_projects_earliest_deadline ... ok
test reconcile_upsert::empty_raw_suffix_matches_like_a_missing_key ... ok
test plus_one_upsert::notification_upsert_supersedes_matching_rows_only_on_create ... ok
test plus_one_upsert::notification_wait_checks_plus_one_cap_is_32_with_exact_drops ... ok
test reconcile_upsert::reconcile_without_a_marker_key_never_changes_dismissals ... ok
test agent_dismissal::notification_dismiss_matching_agents_matches_question_root_identity ... ok
test ack_index::notification_store_writes_bump_generation_and_noops_do_not ... ok
test plus_one_upsert::notification_upsert_creates_then_plus_ones_by_dedup_key ... ok
test plus_one_upsert::notification_plus_one_note_is_capped_at_max_chars ... ok
test plus_one_upsert::notification_upsert_matches_dismissed_and_snoozed_rows ... ok
test plus_one_upsert::notification_plus_one_caps_entries_and_counts_drops ... ok
test store_io::notification_tags_round_trip_through_append_load_and_rewrite ... ok
test store_io::notification_rewrite_all_preserves_unseen_rows ... ok
test store_io::notification_rewrite_counts_preserves_unseen_rows ... ok
test mute_snooze_expiry::notification_mute_and_snooze_follow_python_semantics ... ok
test mute_snooze_expiry::notification_dismissal_cancels_snooze_without_resurfacing ... ok
test state_updates::notification_state_updates_mutate_only_intended_rows ... ok
test state_updates::notification_mark_tab_read_uses_general_tab_for_untagged_rows ... ok
test reconcile_upsert::reconcile_refresh_files_replaces_files_without_moving_cursors ... ok
test reconcile_upsert::reconcile_refresh_copies_only_owned_fields ... ok
test store_io::notification_rewrite_counts_produces_byte_identical_jsonl ... ok
test state_updates::notification_mark_tab_read_marks_only_unread_target_tab ... ok
test store_io::notification_rewrite_preserves_unseen_rows ... ok
test state_updates::notification_undismiss_restores_dismissed_rows ... ok
test state_updates::notification_batch_dismiss_and_rewrite_all_update_the_store ... ok
test plus_one_upsert::notification_wait_checks_upsert_caps_at_32_while_others_keep_500 ... ok
test reconcile_upsert::reconcile_preserves_concurrent_dismissals_of_stale_rows ... ok
test plus_one_upsert::notification_compaction_trims_legacy_wait_checks_rows_preserving_newest ... ok
test mute_snooze_expiry::notification_snapshot_compacts_old_dismissed_rows_to_archive ... ok
test mute_snooze_expiry::notification_rewrite_compacts_when_store_crosses_retention_threshold ... ok
test mute_snooze_expiry::notification_three_day_retention_boundary_and_activity_fallback ... ok
test concurrency::notification_concurrent_append_and_expiry_converge_on_one_transition ... ok
test concurrency::notification_append_plus_upsert_concurrency_preserves_valid_rows ... ok
test concurrency::notification_append_plus_rewrite_counts_concurrency_preserves_valid_rows ... ok
test concurrency::notification_append_plus_rewrite_concurrency_preserves_valid_rows ... ok

test result: ok. 83 passed; 0 failed; 0 ignored; 0 measured; 0 filtered out; finished in 1.76s

     Running tests/plan_validate_parity.rs (/home/bryan/.cache/sase/tmp/cargo-targets/gh_sase-org__sase-ws14-261024_085653/build/debug/deps/plan_validate_parity-62fbdd90dad102a9)

running 2 tests
test plan_validate_matches_python_facade_fixture ... ok
test plan_validate_decisions_wire_shape_is_additive ... ok

test result: ok. 2 passed; 0 failed; 0 ignored; 0 measured; 0 filtered out; finished in 0.00s

     Running tests/prompt_stash_archive.rs (/home/bryan/.cache/sase/tmp/cargo-targets/gh_sase-org__sase-ws14-261024_085653/build/debug/deps/prompt_stash_archive-221717161c0e7c58)

running 13 tests
test archive_path_derives_from_the_stash_path ... ok
test missing_archive_reads_as_empty ... ok
test archive_append_failure_leaves_the_stash_untouched ... ok
test trash_limit_zero_still_archives_evictions ... ok
test pop_archives_every_removed_row_as_popped ... ok
test no_archive_file_is_created_without_a_permanent_removal ... ok
test trash_limit_eviction_archives_as_evicted ... ok
test purge_archives_every_purged_row_with_its_deletion_time ... ok
test reconcile_eviction_archives_as_evicted ... ok
test archive_reader_tolerates_malformed_lines_and_limits_newest_first ... ok
test recovery_restores_the_newest_archived_version ... ok
test rewrite_archives_only_text_frontmatter_or_cursor_replacements ... ok
test recovery_round_trips_and_skips_active_trashed_and_unknown_ids ... ok

test result: ok. 13 passed; 0 failed; 0 ignored; 0 measured; 0 filtered out; finished in 0.09s

     Running tests/prompt_stash_store_parity.rs (/home/bryan/.cache/sase/tmp/cargo-targets/gh_sase-org__sase-ws14-261024_085653/build/debug/deps/prompt_stash_store_parity-e01ba9d7db320b1b)

running 12 tests
test prompt_stash_cursor_serializes_under_nested_key ... ok
test prompt_stash_json_shape_uses_expected_wire_keys ... ok
test prompt_stash_missing_file_returns_empty_snapshot ... ok
test prompt_stash_legacy_row_defaults_cursor_to_none ... ok
test prompt_stash_skips_blank_and_malformed_rows ... ok
test prompt_stash_pop_unknown_ids_is_a_no_op ... ok
test prompt_stash_append_and_read_round_trip ... ok
test prompt_stash_rewrite_merges_and_preserves_unseen_rows ... ok
test prompt_stash_pop_removes_only_requested_ids ... ok
test prompt_stash_set_pinned_sets_and_clears_matching_ids ... ok
test prompt_stash_cursor_survives_append_read_pop_pin_rewrite ... ok
test prompt_stash_append_plus_pop_concurrency_preserves_valid_rows ... ok

test result: ok. 12 passed; 0 failed; 0 ignored; 0 measured; 0 filtered out; finished in 1.30s

     Running tests/prompt_stash_trash_lifecycle.rs (/home/bryan/.cache/sase/tmp/cargo-targets/gh_sase-org__sase-ws14-261024_085653/build/debug/deps/prompt_stash_trash_lifecycle-bf67b55a81b42243)

running 19 tests
test lifecycle_missing_file_returns_empty_versioned_snapshot ... ok
test empty_trashed_at_is_rejected ... ok
test backup_failure_fails_closed_and_leaves_the_file_unchanged ... ok
test crashed_tmp_files_never_replace_the_live_store ... ok
test stale_rewrite_and_append_are_rejected_without_touching_the_file ... ok
test unknown_ids_and_repeated_transitions_are_no_ops ... ok
test first_tagged_write_takes_a_verified_backup_once ... ok
test trash_limit_zero_disables_recovery ... ok
test trash_limit_one_keeps_only_the_newest_row ... ok
test trash_restore_round_trip_preserves_the_complete_entry ... ok
test trash_orders_newest_deleted_first ... ok
test purge_deletes_only_the_requested_trash_rows ... ok
test equal_timestamps_evict_deterministically ... ok
test trash_enforces_a_lowered_limit_in_the_same_transaction ... ok
test reconcile_enforces_a_lowered_limit_and_reports_evictions ... ok
test legacy_writer_hazard_is_real_and_new_writers_avoid_it ... ok
test legacy_mutators_preserve_trash ... ok
test opaque_lines_survive_every_mutation_verbatim ... ok
test concurrent_append_trash_restore_keeps_a_valid_disjoint_store ... ok

test result: ok. 19 passed; 0 failed; 0 ignored; 0 measured; 0 filtered out; finished in 2.55s

     Running tests/python_wire_parity.rs (/home/bryan/.cache/sase/tmp/cargo-targets/gh_sase-org__sase-ws14-261024_085653/build/debug/deps/python_wire_parity-02f4dae1fb7f8d7a)

running 13 tests
test agent_meta_clan_field_order_matches_python_wire ... ok
test agent_meta_parent_epic_plan_reference_round_trips ... ok
test bead_task_and_ready_enum_values_match_python_wire_values ... ok
test agent_meta_parallel_membership_matches_python_wire_defaulting ... ok
test cleanup_target_parallel_membership_matches_python_wire_defaulting ... ok
test agent_meta_auto_restart_is_omitted_when_absent ... ok
test agent_meta_finalizer_status_field_order_matches_python_wire ... ok
test legacy_task_snapshot_deserializes_and_reserializes_as_proc_shape ... ok
test agent_meta_created_epics_field_order_matches_python_wire ... ok
test agent_meta_wait_priority_matches_python_wire_defaulting ... ok
test proc_snapshot_json_uses_canonical_proc_keys ... ok
test python_fixture_deserializes_into_rust_type ... ok
test rust_json_equals_python_fixture ... ok

test result: ok. 13 passed; 0 failed; 0 ignored; 0 measured; 0 filtered out; finished in 0.00s

     Running tests/query_evaluator_parity.rs (/home/bryan/.cache/sase/tmp/cargo-targets/gh_sase-org__sase-ws14-261024_085653/build/debug/deps/query_evaluator_parity-31d4fd20c38c60ee)

running 17 tests
test ancestor_walk_avoids_cycles ... ok
test project_query_falls_back_to_directory_key_without_valid_metadata ... ok
test configured_project_name_replaces_directory_key_in_all_query_paths ... ok
test persistent_corpus_matches_golden_matrix_samples ... ok
test persistent_corpus_keeps_ancestor_memo_query_specific ... ok
test substring_semantics_not_regex ... ok
test persistent_corpus_reuses_derived_data_across_repeated_evaluations ... ok
test batch_evaluation_is_idempotent ... ok
test evaluation_matrix_escapes_are_literal ... ok
test batch_and_oneshot_agree ... ok
test evaluation_matrix_property_shorthands ... ok
test evaluation_matrix_boolean_ops ... ok
test evaluation_matrix_quoted_strings ... ok
test evaluation_matrix_status_shorthands ... ok
test evaluation_matrix_property_filters ... ok
test evaluation_matrix_error_running_shorthands ... ok
test explicit_patch_profile_matches_compatibility_golden_matrix ... ok

test result: ok. 17 passed; 0 failed; 0 ignored; 0 measured; 0 filtered out; finished in 0.07s

     Running tests/retryability_parity.rs (/home/bryan/.cache/sase/tmp/cargo-targets/gh_sase-org__sase-ws14-261024_085653/build/debug/deps/retryability_parity-7c96a1bbf56e6040)

running 3 tests
test retryability_wire_schema_version_is_one ... ok
test parity_cases_cover_transient_delayed_and_permanent_verdicts ... ok
test retryability_verdict_serializes_to_python_shape ... ok

test result: ok. 3 passed; 0 failed; 0 ignored; 0 measured; 0 filtered out; finished in 0.00s

     Running tests/vcs_log_parity.rs (/home/bryan/.cache/sase/tmp/cargo-targets/gh_sase-org__sase-ws14-261024_085653/build/debug/deps/vcs_log_parity-9f79980eff6e43d7)

running 27 tests
test aggregate_empty_returns_empty ... ok
test aggregate_interleaves_by_timestamp_desc ... ok
test aggregate_truncates_to_limit ... ok
test aggregate_tie_break_repo_then_full_id ... ok
test aggregated_commit_wire_serializes_flat ... ok
test aggregated_commit_wire_round_trips_through_json ... ok
test classify_commit_origin_distinguishes_auto_and_legacy_stitch ... ok
test classify_commit_origin_uses_terminal_type_footer ... ok
test classify_commit_presence_marks_synced_local_and_remote ... ok
test classify_commit_types_adds_provenance_concrete_merge_and_patch_labels ... ok
test classify_commit_types_for_commit_uses_parent_ids_for_merge_detection ... ok
test classify_commit_types_supports_legacy_spellings_and_unknown_values ... ok
test classify_commit_types_uses_terminal_footer_and_deduplicates_stitch ... ok
test parse_drops_record_with_bad_timestamp ... ok
test parse_drops_record_with_too_few_fields ... ok
test parse_empty_stream_returns_empty_list ... ok
test parse_legacy_single_commit_defaults_parent_ids ... ok
test parse_multiline_body_preserved ... ok
test parse_octopus_commit_parent_ids ... ok
test parse_root_commit_empty_parent_field ... ok
test parse_single_commit_all_fields ... ok
test parse_stitch_type_footer_sets_stitch_origin ... ok
test parse_strips_newline_git_inserts_between_records ... ok
test parse_trailing_record_separator_yields_no_blank ... ok
test vcs_commit_wire_defaults_presence_to_unknown ... ok
test vcs_log_wire_schema_version_is_four ... ok
test vcs_commit_wire_serializes_to_python_shape ... ok

test result: ok. 27 passed; 0 failed; 0 ignored; 0 measured; 0 filtered out; finished in 0.00s

     Running unittests src/lib.rs (/home/bryan/.cache/sase/tmp/cargo-targets/gh_sase-org__sase-ws14-261024_085653/build/debug/deps/sase_core_rs-1b83b99e626872b2)

running 350 tests
test agent_auto_restart::tests::episode_and_in_flight_bindings ... ok
test autonomy::tests::autonomy_wire_schema_version_binding ... ok
test agent_custody::tests::agent_archive_capability_bindings_are_exported_and_preserve_shapes ... ok
test agent_auto_restart::tests::ledger_binding_rejects_illegal_transitions ... ok
test agent_auto_restart::tests::classify_binding_relaunches_incident ... ok
test agent_custody::tests::status_bucket_binding_round_trips_canonical_text ... ok
test agent_identity::tests::agent_session_parent_binding_is_exported ... ok
test axe::tests::axe_status_binding_returns_exact_plain_python_shape ... ok
test agent_scan::tests::agent_model_summary_binding_round_trips_python_dict ... ok
test agent_auto_restart::tests::ledger_binding_stamps_optional_at ... ok
test agent_launch::tests::standalone_named_proc_validator_has_no_legacy_binding_name ... ok
test axe::tests::chop_clan_contracts_round_trip_through_python_bindings ... ok
test axe::tests::axe_status_binding_maps_schema_structural_and_unknown_errors_to_value_error ... ok
test axe::tests::chop_overrun_binding_maps_schema_and_structural_errors_to_value_error ... ok
test agent_custody::tests::agent_publication_batch_binding_returns_plain_dict ... ok
test agent_holds::tests::agent_hold_deadlock_reaches_walks_every_wait_branch ... ok
test agent_custody::tests::plan_agent_ownership_batch_binding_rejects_schema_mismatch ... ok
test agent_custody::tests::force_reuse_stop_barrier_binding_round_trips_json_shape ... ok
test agent_holds::tests::agent_hold_bindings_accept_legacy_spellings_and_serialize_canonical ... ok
test bead_decisions::tests::finalizer_bindings_round_trip_json_shapes ... ok
test bead_decisions::tests::task_type_spec_bindings_round_trip_validation_digest_and_snapshot ... ok
test artifact_refs::tests::files::artifact_context_query_binding_returns_projected_rows_and_handshake ... ok
test axe::tests::axe_status_public_projection_binding_preserves_user_values ... ok
test axe::tests::chop_overrun_binding_returns_exact_plain_python_shape ... ok
test bead_decisions::tests::gate_decision_bindings_round_trip_json_shapes ... ok
test bead_decisions::tests::bead_action_bindings_round_trip_json_shapes ... ok
test bead_decisions::tests::remaining_commit_work_binding_selects_and_rejects ... ok
test autonomy::tests::autonomy_summary_and_sentence_bindings ... ok
test axe::tests::chop_subprocess_diagnostic_binding_returns_plain_dict ... ok
test agent_scan::tests::reconcile_dismissed_members_binding_is_canonical_only ... ok
test agent_auto_restart::tests::auto_restart_bindings_are_registered ... ok
test agent_custody::tests::plan_agent_cleanup_binding_rejects_schema_mismatch ... ok
test bead_decisions::tests::gate_followup_binding_maps_schema_and_structural_errors_to_value_error ... ok
test bead_decisions::tests::gate_lifecycle_bindings_round_trip_json_shapes ... ok
test beads::tests::bead_drop_flag_type_migration_bindings_are_exported ... ok
test beads::tests::bead_doctor_binding_keeps_contexts_optional_and_marks_unavailable ... ok
test artifact_refs::tests::refs::prompt_artifact_bindings_round_trip_manifest_shapes ... ok
test beads::fingerprint::fingerprint_tests::store_fingerprint_json_bridge_matches_core_wire ... ok
test artifact_refs::tests::refs::artifact_ref_bindings_round_trip_json_shapes ... ok
test agent_scan::tests::agent_alias_history_binding_round_trips_python_dict ... ok
test agent_custody::tests::plan_agent_cleanup_binding_round_trips_json_shape ... ok
test axe::tests::required_axe_descriptions_round_trip_through_python_binding ... ok
test bead_decisions::tests::node_view_binding_round_trips_a_planned_run ... ok
test agent_custody::tests::plan_agent_ownership_batch_binding_round_trips_json_shape ... ok
test beads::tests::bead_create_binding_round_trips_task_type_and_fields ... ok
test axe::tests::axe_description_split_round_trips_through_python_binding ... ok
test beads::board::board_tests::board_snapshot_binding_round_trips ... ok
test beads::tests::bead_merge_event_streams_binding_preserves_replay_stable_union ... ok
test beads::fingerprint::fingerprint_tests::store_fingerprint_binding_round_trips ... ok
test autonomy::tests::autonomy_resolve_selection_rejects_bad_spellings ... ok
test bead_decisions::tests::gate_followup_binding_round_trips_incident_disposition ... ok
test artifact_refs::tests::files::artifact_file_query_binding_returns_full_rows_and_handshake ... ok
test beads::seal_watch::seal_watch_tests::seal_watch_bindings_round_trip ... ok
test beads::tests::bead_size_check_relax_bindings_are_exported_and_forward_core_policy ... ok
test agent_holds::tests::agent_hold_bindings_map_validation_and_lock_errors ... ok
test beads::tests::bead_set_link_projections_binding_rejects_invalid_request_dicts ... ok
test beads::artifact_refs::artifact_refs_tests::referenced_artifact_ids_binding_round_trips ... ok
test artifact_refs::tests::refs::artifact_ref_document_source_target_rejects_out_of_inventory_source_dir ... ok
test beads::tests::bead_merge_event_streams_binding_exposes_typed_relocations ... ok
test clan_waves::tests::project_clan_waves_binding_round_trips_request_and_result ... ok
test agent_custody::tests::agent_archive_corpus_bindings_round_trip_missing_index ... ok
test autonomy::tests::autonomy_decision_log_bindings_round_trip ... ok
test config::tests::disk_cleanup_outcome_binding_preserves_partial_effects ... ok
test beads::tests::bead_set_link_projections_binding_surfaces_core_validation ... ok
test beads::tests::bead_attachment_bindings_round_trip ... ok
test config::tests::macro_layer_normalize_binding_round_trips_python_dicts ... ok
test autonomy::tests::autonomy_effective_record_binding_round_trip_and_registration ... ok
test agent_holds::tests::agent_hold_capture_summary_and_prune_bindings ... ok
test config::tests::service_config_compose_binding_round_trips_python_dicts ... ok
test config::tests::config_routine_job_projection_round_trips_through_python_bindings ... ok
test config::tests::service_state_bindings_round_trip_python_dicts ... ok
test beads::tests::bead_plus_one_binding_exports_structured_atomic_result ... ok
test beads::tests::bead_target_routing_binding_round_trips ... ok
test beads::read_model::read_model_tests::read_model_bindings_round_trip ... ok
test beads::tests::bead_search_binding_accepts_regex_keyword ... ok
test artifact_refs::tests::refs::artifact_ref_document_source_target_round_trips_stale_and_source_dir ... ok
test continuation::tests::continuation_contract_bindings_round_trip_json_shapes ... ok
test config::tests::service_restart_decide_binding_round_trips_python_dicts ... ok
test editor_completion::tests::jinja::jinja_scope_variables_and_catalog_round_trip ... ok
test editor_completion::tests::jinja::jinja_bindings_are_registered_on_the_module ... ok
test config::tests::service_proc_request_mutations_round_trip_python_dicts ... ok
test editor_completion::tests::snippets::apply_snippet_session_event_binding_rejects_malformed_input ... ok
test config::tests::service_status_build_round_trips_pending_proc_requests ... ok
test config::tests::service_status_bindings_round_trip_python_dicts ... ok
test artifact_refs::tests::refs::artifact_ref_filter_path_payloads_binding_returns_batch_shape ... ok
test editor_completion::tests::snippets::argument_double_colon_to_parentheses_binding_returns_plain_edit_or_none ... ok
test agent_tab::tests::agent_tab_bindings_round_trip ... ok
test editor_completion::tests::snippets::argument_list_continuation_binding_returns_plain_edit_or_none ... ok
test continuation::tests::seal_binding_round_trips_stage_source_and_prior_refusals ... ok
test editor_completion::tests::snippets::filter_model_alias_shortcut_entries_binding_rejects_malformed_rows ... ok
test beads::tests::bead_create_binding_round_trips_creation_reason ... ok
test editor_completion::tests::jinja::jinja_completion_round_trip_inside_and_outside_tags ... ok
test editor_completion::tests::snippets::filter_model_completion_entries_binding_returns_plain_dict_shape ... ok
test editor_completion::tests::snippets::macro_argument_spans_binding_returns_open_structural_spans ... ok
test editor_completion::tests::snippets::macro_bindings_are_canonical_and_legacy_names_are_absent ... ok
test editor_completion::tests::snippets::model_alias_shortcut_bindings_return_plain_dict_shapes ... ok
test editor_completion::tests::snippets::filter_model_alias_shortcut_entries_binding_restricts_to_alias_kinds ... ok
test editor_completion::tests::snippets::filter_model_completion_entries_binding_rejects_malformed_rows ... ok
test config::tests::disk_inventory_binding_classifies_overlaps ... ok
test agent_custody::tests::dismissed_bundle_index_bindings_are_exported_and_round_trip ... ok
test editor_completion::tests::snippets::model_alias_shortcut_binding_rejects_malformed_position ... ok
test axe::tests::chop_agent_runners_contracts_round_trip_through_python_bindings ... ok
test editor_completion::tests::surfaces::indexed_at_reference_binding_stays_below_eight_ms_for_5000_rows ... ignored, the 8 ms performance gate is calibrated for release builds
test editor_completion::tests::snippets::catalog_options_accept_only_macro_keys ... ok
test artifact_refs::tests::refs::artifact_ref_payload_inventory_binding_returns_plain_json_shape ... ok
test editor_completion::tests::snippets::apply_snippet_session_event_binding_drives_nesting_through_dicts ... ok
test editor_completion::tests::surfaces::at_reference_bindings_return_plain_json_shapes ... ok
test editor_completion::tests::snippets::model_shortcut_binding_rejects_malformed_inputs ... ok
test beads::tests::bead_list_query_statuses_and_closed_bindings_round_trip ... ok
test editor_completion::tests::snippets::model_shortcut_bindings_return_plain_dict_list_and_none_shapes ... ok
test editor_completion::tests::snippets::load_editor_snippet_catalog_binding_returns_plain_dict_shape ... ok
test editor_content::tests::alternation_scan_binding_is_registered_and_uses_char_offsets ... ok
test beads::tests::bead_snooze_bindings_round_trip_the_whole_lifecycle ... ok
test beads::tests::bead_set_link_projections_binding_is_registered_and_projects_batch ... ok
test editor_completion::tests::snippets::model_shortcut_edit_binding_reports_segment_replacement_edits ... ok
test editor_content::tests::source_language_bindings_round_trip_wire_payloads ... ok
test editor_completion::tests::surfaces::directive_contract_and_completion_bindings_return_plain_json_shapes ... ok
test fleet::tests::catalog_query_terminal_flag_defaults_to_presentation ... ok
test artifact_refs::tests::files::artifact_consumption_binding_returns_summary_and_handshake ... ok
test editor_completion::tests::snippets::validate_snippet_trigger_binding_returns_plain_dict_shape ... ok
test fleet::tests::fleet_followed_batch_agent_session_promotions_round_trip_json_shapes ... ok
test editor_content::tests::text_tail_binding_returns_plain_dict_and_counts_unicode_chars ... ok
test beads::tests::bead_work_plan_binding_exposes_additive_bead_id_fields ... ok
test beads::tests::bead_update_many_binding_applies_batch_and_reports_unchanged ... ok
test editor_content::tests::inline_code_binding_returns_plain_byte_offset_tuples ... ok
test editor_completion::tests::snippets::compose_snippet_catalog_binding_exposes_missing_and_cycle_graph ... ok
test editor_completion::tests::snippets::xprompt_spacer_to_parentheses_binding_round_trips_utf16 ... ok
test beads::tests::bead_close_binding_stamps_the_supplied_author_on_the_close_event ... ok
test fleet::tests::gateway_and_bootstrap_bindings_are_registered ... ok
test editor_completion::tests::snippets::compose_snippet_catalog_binding_returns_plain_dict_shape ... ok
test instruction_manifest::tests::instruction_manifest_bindings_are_registered ... ok
test goals::tests::goal_bindings_are_registered ... ok
test instruction_manifest::tests::normalize_binding_rejects_bad_actor ... ok
test macro_input_types::tests::catalog_binding_round_trips_contract_rows ... ok
test instruction_manifest::tests::normalize_binding_fills_null_common_digest ... ok
test instruction_manifest::tests::normalize_instruction_manifest_binding_round_trips ... ok
test macro_input_types::tests::pyyaml_binding_matches_the_contract_vector ... ok
test editor_content::tests::memory_macro_bindings_expose_the_shared_contract ... ok
test editor_completion::tests::surfaces::placeholder_bindings_return_plain_json_shapes ... ok
test macro_input_types::tests::validate_and_check_bindings_round_trip ... ok
test macro_input_types::tests::classify_binding_round_trips_accept_and_reject ... ok
test instruction_manifest::tests::normalize_instruction_manifest_binding_round_trips_v2 ... ok
test beads::tests::bead_manifest_repair_binding_round_trips_structured_outcome ... ok
test beads::tests::bead_search_binding_round_trips_json_shape ... ok
test config::tests::feature_flag_state_binding_rejects_invalid_keys_and_corrupt_files ... ok
test json_bridge::tests::direct_serializer_matches_json_bridge_for_json_shape ... ok
test macro_input_types::tests::macro_input_type_bindings_are_registered ... ok
test beads::tests::bead_touch_index_bindings_round_trip_the_complete_snapshot ... ok
test note_attachment::tests::audience_and_object_bindings_round_trip ... ok
test memory_history::tests::memory_history_bindings_are_registered ... ok
test agent_identity::tests::relationship_bindings_validate_and_rewrite_plain_dicts ... ok
test note_attachment::tests::policy_bindings_round_trip ... ok
test migration::tests::migration_bindings_expose_contract_helpers ... ok
test note_attachment::tests::scan_compose_source_cycle_round_trips ... ok
test note_attachment::tests::uniquify_bumps_on_digest_conflict ... ok
test note_attachment::tests::classify_png_bytes_wins_over_txt_extension ... ok
test agent_holds::tests::agent_hold_rebind_and_launch_hold_bindings_round_trip ... ok
test editor_completion::tests::snippets::argument_colon_to_parentheses_binding_returns_plain_edit_or_none ... ok
test config::tests::managed_tmp_reap_binding_round_trips_dead_launch_wire ... ok
test notifications::tests::notification_delivery_binding_rejects_malformed_rules ... ok
test agent_identity::tests::managed_origin_decision_binding_returns_wire_dict ... ok
test agent_holds::tests::agent_hold_bindings_round_trip_and_predicate ... ok
test note_attachment::tests::note_attachment_bindings_are_registered ... ok
test agent_scan::tests::agent_output_variable_history_binding_round_trips_python_dict ... ok
test beads::tests::bead_claim_for_agent_launch_attaches_or_refuses_closed_beads ... ok
test macro_input_types::tests::load_registry_binding_round_trips_entries_and_diagnostics ... ok
test agent_custody::tests::agent_artifact_run_retention_binding_refuses_apply_without_protection ... ok
test autonomy::tests::autonomy_bindings_round_trip ... ok
test plans::decisions::tests::quote_match_binding_is_registered_and_round_trips ... ok
test fleet_attention::tests::fleet_attention_inventory_bindings_validate_envelopes ... ok
test notifications::tests::notification_reconcile_binding_rejects_malformed_requests ... ok
test artifact_links::tests::artifact_link_eligibility_bindings_round_trip_json_shapes ... ok
test editor_completion::tests::snippets::apply_snippet_session_event_binding_substitutes_variables_from_a_dict ... ok
test plans::decisions::tests::decision_bindings_are_registered_and_round_trip ... ok
test plans::decisions::tests::quote_match_binding_rejects_malformed_records ... ok
test plans::decisions::tests::decision_bindings_reject_invalid_input_shapes ... ok
test procs::tests::command_line_proc_binding_exposes_tag_and_limit ... ok
test json_bridge::tests::direct_serializer_matches_json_bridge_for_agent_scan_snapshot ... ok
test fleet::tests::fleet_issue_bootstrap_binding_delegates_to_store_without_persisting_secret ... ok
test procs::tests::proc_wire_schema_version_binding_reports_current_version ... ok
test agent_identity::tests::machine_hood_bindings_qualify_strip_and_classify ... ok
test agent_identity::tests::agent_identity_bindings_are_exported_and_preserve_shapes ... ok
test autonomy::tests::autonomy_mutate_and_inherit_bindings ... ok
test notifications::tests::notification_store_binding_rejects_bad_update_shape ... ok
test plans::tests::plan_search_binding_accepts_explicit_document_corpora ... ok
test project_onboarding::tests::classify_binding_rejects_bad_schema ... ok
test editor_completion::tests::choices::choice_and_label_bindings_round_trip ... ok
test mobile_pairing::tests::mobile_pairing_issue_binding_schema_error_is_secret_free ... ok
test plans::tests::sdd_artifact_link_bindings_match_core_contract ... ok
test plans::decisions::tests::sheet_summary_and_block_bindings_round_trip ... ok
test artifact_links::tests::artifact_link_index_bindings_round_trip ... ok
test plans::decisions::tests::sheet_bindings_reject_invalid_input_shapes ... ok
test project_onboarding::tests::project_onboarding_bindings_are_registered ... ok
test project_stats::tests::project_stats_query_rejects_an_invalid_request ... ok
test project_stats::tests::project_stats_query_is_registered ... ok
test project_onboarding::tests::classify_binding_round_trips_sidecar_hide ... ok
test goals::tests::goal_card_view_binding_reduces_state ... ok
test project_tag::tests::project_tag_bindings_are_registered ... ok
test beads::tests::bead_remove_many_binding_is_exported_and_removes_multiple_roots ... ok
test project_onboarding::tests::form_binding_round_trips_template_excludes ... ok
test project_onboarding::tests::plan_binding_rejects_bad_schema ... ok
test plans::tests::plan_reference_bindings_round_trip_json_shapes ... ok
test project_tag::tests::project_tag_trigger_binding_uses_char_offsets ... ok
test agent_launch::tests::hold_directive_bindings_collect_format_and_expand ... ok
test project_tag::tests::project_tag_apply_selection_binding_replaces_target_position ... ok
test agent_scan::tests::gate_turn_lookup_binding_serves_turn_records_without_legacy_name ... ok
test beads::tests::bead_update_binding_preserves_resolution_presence_semantics ... ok
test beads::tests::bead_note_edit_and_remove_bindings_round_trip ... ok
test config::tests::machine_setup_bindings_round_trip_json_shapes ... ok
test notifications::tests::notification_store_binding_round_trips_json_shape ... ok
test notifications::tests::notification_delivery_binding_resolves_a_batch_in_one_call ... ok
test project_stats::tests::project_stats_query_serializes_null_counts_for_unavailable_sources ... ok
test prompt_prediction::tests::prompt_prediction_model_predicts_and_ranks ... ok
test macro_input_types::tests::resolve_binding_round_trips_success_and_error ... ok
test project_tag::tests::project_tag_apply_selection_binding_returns_char_cursor ... ok
test prompt_prediction::tests::prompt_prediction_classes_are_registered ... ok
test provider_policy::tests::epic_land_model_binding_rejects_invalid_counts_and_thresholds ... ok
test migration::tests::migration_bounded_lock_binding_returns_releasable_handle ... ok
test provider_policy::tests::effort_override_binding_rejects_invalid_values ... ok
test project_tag::tests::project_tag_expand_binding_rewrites_and_reports ... ok
test project_tag::tests::project_tag_targets_with_state_fields_round_trip ... ok
test notifications::tests::notification_store_append_and_rewrite_counts_bindings_omit_rows ... ok
test provider_policy::tests::epic_land_model_binding_selects_explicit_then_threshold ... ok
test agent_launch::tests::prompt_proc_origin_returns_canonical_and_legacy_is_absent ... ok
test agent_scan::tests::agent_activity_stats_binding_round_trips_python_dict ... ok
test provider_policy::tests::provider_disable_try_set_bindings_report_first_writer ... ok
test notifications::tests::notification_store_counts_binding_omits_rows_and_persists ... ok
test procs::tests::reserve_proc_uses_proc_name_spelling ... ok
test agent_launch::tests::auto_directive_bindings_classify_and_describe_vocabulary ... ok
test provider_policy::tests::provider_pool_eligibility_bindings_cover_soft_vs_backup ... ok
test notifications::tests::pending_action_bindings_round_trip_transport_records ... ok
test prompt_prediction::tests::prompt_looks_generated_binding_matches_core_classifier ... ok
test prompt_prediction::tests::prompt_prediction_corpus_compiles_and_reports_stats ... ok
test provider_policy::tests::provider_usage_bindings_project_remaining_and_reject_invalid ... ok
test provider_policy::tests::provider_usage_project_indicator_binding_honors_floors ... ok
test agent_scan::tests::scan_agent_artifacts_binding_preserves_canonical_and_legacy_capacity ... ok
test procs::tests::proc_runtime_retention_binding_requires_trustworthy_store_snapshot ... ok
test provider_policy::tests::provider_disable_binding_rejects_invalid_values ... ok
test query::tests::bench_compile_corpus_with_profile_over_agent_scale_corpus ... ignored, manual perf check, not part of the default test run
test provider_policy::tests::provider_disable_bindings_round_trip_and_replace ... ok
test provider_policy::tests::provider_usage_normalize_agy_usage_round_trips_and_separates_errors ... ok
test editor_content::tests::alternation_scan_binding_converts_non_ascii_to_char_offsets ... ok
test prose_diff::tests::compare_prose_binding_round_trips ... ok
test project_onboarding::tests::plan_binding_round_trips_fresh_add ... ok
test provider_policy::tests::size_model_route_binding_rejects_invalid_sizes ... ok
test prose_diff::tests::compare_prose_binding_detects_promotion ... ok
test provider_policy::tests::provider_priority_binding_context_and_policy_round_trip ... ok
test prose_diff::tests::prose_diff_bindings_are_registered ... ok
test provider_policy::tests::provider_priority_binding_rejects_invalid_values ... ok
test notifications::tests::notification_store_current_snapshot_binding_reconciles_snoozes ... ok
test artifact_links::tests::artifact_link_index_binding_includes_conversion_cost ... ok
test project_stats::tests::project_stats_query_round_trips_code_only ... ok
test provider_policy::tests::runner_limit_override_bindings_round_trip_and_replace ... ok
test plans::decisions::tests::seven_binding_decision_integration ... ok
test query::tests::profile_binding_round_trips_compiled_profile_dict ... ok
test query::tests::query_compile_errors_are_python_value_errors ... ok
test query::tests::query_row_from_py_row_matches_json_wire_conversion_for_mixed_value_types ... ok
test project_onboarding::tests::plan_binding_round_trips_management_recovery_facts ... ok
test provider_policy::tests::size_model_route_binding_maps_public_aliases ... ok
test provider_policy::tests::provider_usage_normalize_muse_usage_round_trips_and_separates_errors ... ok
test sudo::tests::python_hosted_sudo_runner_launcher_rejects_unusable_executable ... ok
test provider_policy::tests::runner_limit_override_binding_rejects_invalid_values ... ok
test provider_policy::tests::provider_usage_normalize_grok_billing_round_trips_and_rejects_nonfinite ... ok
test sudo::tests::python_hosted_sudo_runner_launcher_uses_isolated_module_execution ... ok
test project_stats::tests::project_stats_query_round_trips_a_nontrivial_repo ... ok
test fleet::tests::fleet_contract_bindings_round_trip_nested_dicts ... ok
test project_tag::tests::project_tag_scan_binding_returns_char_offsets ... ok
test telemetry::tests::perf_logs_query_binding_round_trips_python_dict ... ok
test memory_history::tests::memory_history_review_state_and_mark_round_trip ... ok
test provider_policy::tests::provider_priority_bindings_round_trip_conflict_and_clear ... ok
test provider_policy::tests::provider_usage_observation_binding_clamps_retry_after ... ok
test query::tests::parse_patch_project_bytes_binding_emits_canonical_shape_and_query_accepts_it ... ok
test command_line::tests::command_line_grammar_binding_round_trips ... ok
test vcs::tests::classify_commit_origin_binding_returns_origin_string ... ok
test vcs::tests::classify_commit_types_binding_returns_label_list ... ok
test release_steward::tests::release_steward_binding_round_trips_releasable ... ok
test goals::tests::goal_render_bindings_round_trip ... ok
test vcs::tests::commit_footer_bindings_convert_linked_payloads ... ok
test vcs::tests::commit_subject_bindings_round_trip_wire_payload ... ok
test telemetry::tests::tool_run_receipts_report_round_trip_and_rejects_bad_schema ... ok
test project_stats::tests::project_stats_query_round_trips_combined_and_records ... ok
test agent_scan::tests::agent_stats_binding_round_trips_python_dict ... ok
test query::tests::query_handles_evaluate_multiple_queries_against_one_corpus ... ok
test vcs::tests::git_lock_bindings_round_trip_classify_and_decide ... ok
test stranded_work::tests::stranded_work_binding_round_trip ... ok
test vcs::tests::parse_merge_summary_binding_returns_dict_or_none ... ok
test vcs::tests::pending_commit_checkpoint_bindings_round_trip_json_shapes ... ok
test vcs::tests::git_object_sharing_binding_preserves_existing_reuse ... ok
test prompt_prediction::tests::prompt_prediction_model_rejects_unknown_role ... ok
test artifact_refs::tests::files::artifact_file_lifecycle_bindings_round_trip_plain_python_shapes ... ok
test release_steward::tests::release_steward_binding_maps_unreadable_to_watcher_broken ... ok
test query::tests::query_handle_bindings_reject_wrong_handle_types ... ok
test vcs::tests::sidecar_publication_binding_returns_plain_dict ... ok
test provider_policy::tests::provider_usage_hot_and_reservation_listing_bindings ... ok
test project_stats::tests::project_stats_query_code_unavailable_and_zero ... ok
test project_tag::tests::project_tag_resolve_binding_round_trips ... ok
test plans::tests::sdd_plan_header_block_bindings_match_core_contract ... ok
test vcs::tests::session_manifest_binding_classifies_current_legacy_and_slim ... ok
test query::tests::profile_binding_rejects_invalid_profile_and_mismatch ... ok
test memory_history::tests::memory_history_sync_and_subjects_round_trip ... ok
test provider_policy::tests::effort_override_bindings_round_trip_and_resolve ... ok
test config::tests::launch_scratch_liveness_binding_round_trips_wire ... ok
test prompt_prediction::tests::prompt_prediction_replay_reports_aggregates_only ... ok
test query::tests::profile_binding_evaluates_generic_rows ... ok
test vcs::tests::vcs_log_binding_exposes_schema_and_parent_ids ... ok
test wait_epic_follow::tests::wait_epic_follow_binding_round_trip ... ok
test vcs::tests::session_manifest_repair_binding_round_trips_policy_and_counts ... ok
test query::tests::legacy_query_handles_still_use_patch_profile ... ok
test release_steward::tests::release_steward_binding_rejects_invalid_request ... ok
test query::tests::compile_corpus_with_profile_rejects_object_shaped_field_value_directly ... ok
test procs::tests::begin_proc_settlement_round_trips_optional_outcome ... ok
test config::tests::feature_flag_state_bindings_are_exported_and_round_trip ... ok
test vcs::tests::publication_recovery_bindings_select_and_complete ... ok
test artifact_links::tests::artifact_link_index_binding_preserves_tolerant_read_model_coercions ... ok
test stranded_work::tests::stranded_work_binding_registered_by_name ... ok
test artifact_refs::tests::contracts::artifact_ref_contract_bindings_round_trip_json_shapes ... ok
test agent_scan::tests::clan_record_bindings_round_trip_python_dicts ... ok
test telemetry::tests::tool_run_duration_bindings_round_trip_python_dicts ... ok
test goals::tests::goal_ledger_append_reports_stale_basis ... ok
test notifications::tests::notification_reconcile_binding_applies_field_scoped_write ... ok
test notifications::tests::notification_plus_one_and_upsert_bindings_round_trip ... ok
test provider_policy::tests::provider_usage_load_with_floors_binding ... ok
test vcs::tests::replay_recovery_bindings_classify_and_admit ... ok
test sudo::tests::sudo_fit_ledger_binding_trims_oversize_tails ... ok
test notifications::tests::notification_ack_and_index_bindings_round_trip ... ok
test provider_policy::tests::provider_usage_store_bindings_record_load_context_and_reserve ... ok
test query::tests::query_handles_evaluate_one_query_against_multiple_corpora ... ok
test provider_policy::tests::provider_usage_record_attempt_binding_covers_adaptive_fields ... ok
test editor_content::tests::prompt_stash_archive_bindings_round_trip_pop_and_overwrite ... ok
test mobile_pairing::tests::mobile_pairing_issue_binding_returns_challenge ... ok
test query::tests::query_handles_match_legacy_one_shot_results ... ok
test goals::tests::goal_render_and_fast_path_bindings_round_trip ... ok
test agent_scan::tests::artifact_index_reader_bindings_round_trip ... ok
Usage:
  sase_sudo_runner --capabilities|-c
  sase_sudo_runner --manifest|-m PATH --expected-sha256|-e SHA256 [--detach-dir|-d DIR]

Reads one reviewed sudo manifest, verifies its canonical SHA-256, and emits either one JSON ledger on stdout or, with --detach-dir, one sudo_exec_started handshake after authentication succeeds.

Options:
  -c, --capabilities          Print the schema-version-1 capabilities document and exit
  -d, --detach-dir DIR       Authenticate, spawn the root executor, and print a started handshake
  -e, --expected-sha256 SHA   Require this lowercase canonical manifest SHA-256 digest
  -h, --help                  Show this help text
  -m, --manifest PATH         Read the reviewed sudo manifest JSON from PATH

Exit statuses:
  0  completed, command-level failure recorded, capabilities printed, or detached executor started
  10 authentication failed
  11 cancelled
  12 no controlling TTY
  13 invalid manifest, digest, handoff directory, or arguments
  14 runner failure

Platform support:
  Detached execution (--detach-dir and the detached_execution capability) requires Linux procfs and is unavailable on other platforms, where --capabilities reports an empty capability list and detach requests fail with an explicit unsupported-platform error. Synchronous manifest execution works everywhere.
test provider_policy::tests::provider_usage_adaptive_due_and_admit_bindings ... ok
test telemetry::demand_tests::tool_run_record_demand_binding_round_trips ... ok
test sudo::tests::sudo_bindings_validate_manifest_risk_ledger_and_help ... ok
test plans::tests::plan_validation_bindings_round_trip_json_shapes ... ok
test goals::tests::goal_ledger_bindings_round_trip ... ok
test procs::tests::proc_store_bindings_round_trip_python_dicts_and_legacy_aliases ... ok
test beads::tests::bead_mutation_bindings_preserve_changed_and_epic_preclaim ... ok
test editor_content::tests::prompt_stash_lifecycle_bindings_are_registered_and_round_trip ... ok
test telemetry::stats_tests::tool_run_stats_report_binding_round_trips ... ok
test telemetry::tests::tool_run_glance_join_fact_bindings_round_trip ... ok
test telemetry::tests::tool_run_glance_projection_bindings_round_trip ... ok
test telemetry::tests::tool_run_receipt_bindings_round_trip ... ok
test telemetry::tests::telemetry_bindings_round_trip_python_dicts ... ok
test agent_custody::tests::agent_archive_corpus_bindings_round_trip_v3_index ... ok
test telemetry::tests::tool_run_triage_bindings_round_trip ... ok
test telemetry::tests::tool_run_triage_classification_bindings_round_trip ... ok
test telemetry::tests::tool_run_bindings_round_trip_python_dicts ... ok

test result: ok. 348 passed; 0 failed; 2 ignored; 0 measured; 0 filtered out; finished in 1.94s

     Running unittests src/lib.rs (/home/bryan/.cache/sase/tmp/cargo-targets/gh_sase-org__sase-ws14-261024_085653/build/debug/deps/sase_gateway-c2c03ece79a8ce73)

running 243 tests
test cli::tests::parse_contract_out_short_flag ... ok
test cli::tests::parse_bind_short_flag ... ok
test cli::tests::parse_bind_long_flag ... ok
test cli::tests::parse_fleet_contract_out_short_flag ... ok
test cli::tests::parse_agent_bridge_command_short_flag ... ok
test cli::tests::parse_allow_non_loopback_short_flag ... ok
test cli::tests::parse_sase_home_short_flag ... ok
test cli::tests::parse_helper_bridge_command_short_flag ... ok
test cli::tests::parse_push_flags ... ok
test cli::tests::unknown_argument_is_rejected ... ok
test cli::tests::gateway_tracing_install_is_idempotent ... ok
test daemon::tests::daemon_host_identity_is_path_safe ... ok
test daemon::tests::daemon_mobile_bind_policy_is_skipped_when_mobile_http_disabled ... ok
test daemon::tests::daemon_default_paths_are_host_local_under_sase_home ... ok
test daemon::tests::daemon_run_root_override_drives_default_socket_path ... ok
test daemon::tests::daemon_socket_path_override_is_preserved ... ok
test federation_worker::imp::tests::cache::attention_inventory_read_operation_cache_key_is_namespaced_and_stable ... ok
test federation_worker::imp::tests::cache::attention_read_operation_cache_key_is_namespaced_and_stable ... ok
test federation_worker::imp::tests::remote::fleet_endpoint_join_accepts_api_bases ... ok
test federation_worker::imp::tests::remote::host_backoff_schedule_doubles_and_caps ... ok
test federation_worker::imp::tests::remote::read_backoff_triggers_only_on_retryable_errors ... ok
test federation_worker::imp::tests::operations::attention_inventory_read_returns_empty_hosts_when_unconfigured ... ok
test federation_worker::imp::tests::ipc::listener_creates_private_socket_and_rejects_symlink ... ok
test federation_worker::imp::tests::ipc::framed_ipc_rejects_oversized_request ... ok
test federation_worker::tests::cli_parses_socket_and_idle_options ... ok
test federation_worker::imp::tests::operations::attention_read_returns_empty_hosts_when_unconfigured ... ok
test federation_worker::imp::tests::remote::replace_config_fails_closed_for_missing_managed_ca_ref ... ok
test federation_worker::imp::tests::operations::mutate_rejects_unknown_alias_pin_mismatch_and_deadline ... ok
test fleet_attention::tests::reserve_rejects_installation_mismatch ... ok
test federation_worker::imp::tests::operations::resolve_attention_rejects_unknown_alias_pin_mismatch_and_deadline ... ok
test fleet_auth::tests::credential_lookup_checks_every_cached_record ... ok
2026-10-24T13:20:43.480184Z ERROR tower_http::trace::on_failure: response failed classification=Status code: 503 Service Unavailable latency=2 ms
test contract::tests::committed_fleet_contract_snapshot_is_current ... ok
test host_bridge::tests::launch_error_suffix_drops_secret_or_path_like_detail ... ok
test host_bridge::tests::launch_error_suffix_keeps_bounded_safe_bridge_detail ... ok
test push::tests::fcm_payload_contains_hint_only_data ... ok
test contract::tests::committed_contract_snapshot_is_current ... ok
test federation_worker::imp::tests::cache::cache_persists_and_ignores_newer_schema ... ok
test federation_worker::imp::tests::ipc::worker_answers_health_over_local_ipc ... ok
test fleet_attention::tests::settle_rejects_unsafe_message_and_host_label ... ok
test fleet_attention::tests::reserve_then_settle_round_trips_through_disk ... ok
test fleet_auth::tests::auth_store_files_use_private_modes ... ok
test federation_worker::imp::tests::remote::replace_config_reuses_unchanged_remote_hosts ... ok
test fleet_auth::tests::bootstrap_and_credential_secrets_are_hashed_at_rest ... ok
test routes::tests::agent_helper_bridges::events_without_token_returns_typed_unauthorized_error ... ok
test cli::tests::run_gateway_cli_writes_contract_outputs_without_serving ... ok
test fleet_auth::tests::authentication_cache_refreshes_after_durable_changes_only ... ok
test fleet_auth::tests::bootstrap_is_single_use_and_expiring ... ok
test routes::tests::agent_helper_bridges::command_helper_bridge_malformed_json_maps_to_unavailable ... ok
test routes::tests::agent_helper_bridges::helper_host_bridge_errors_map_to_stable_api_codes ... ok
test fleet_auth::tests::concurrent_store_instances_preserve_each_others_updates ... ok
test push::tests::fcm_provider_posts_expected_http_v1_shape ... ok
test routes::tests::agent_helper_bridges::agents_without_token_returns_typed_unauthorized_error ... ok
test routes::tests::agent_helper_bridges::events_with_token_returns_sse_response ... ok
2026-10-24T13:20:43.554462Z ERROR tower_http::trace::on_failure: response failed classification=Status code: 503 Service Unavailable latency=0 ms
test routes::tests::agent_helper_bridges::production_helper_bridge_returns_typed_unavailable_error ... ok
test routes::tests::agent_helper_bridges::command_helper_bridge_update_exit_codes_map_to_stable_errors ... ok
test routes::tests::agent_helper_bridges::command_helper_bridge_changespec_tags_returns_command_output ... ok
test routes::tests::fleet_attention::fleet_attention_inventory_returns_uncataloged_pending_requests ... ok
2026-10-24T13:20:43.556106Z ERROR tower_http::trace::on_failure: response failed classification=Status code: 503 Service Unavailable latency=3 ms
test routes::tests::agent_helper_bridges::command_helper_bridge_macro_catalog_returns_new_helper_fields ... ok
test routes::tests::agent_helper_bridges::command_helper_bridge_exit_failure_maps_to_unavailable ... ok
test routes::tests::agent_helper_bridges::command_helper_bridge_update_start_returns_command_output ... ok
test routes::tests::agent_helper_bridges::command_helper_bridge_not_found_maps_to_helper_not_found ... ok
test routes::tests::fleet_attention::fleet_attention_resolve_settles_unknown_request ... ok
test routes::tests::fleet_attention::fleet_attention_inventory_pages_pending_entries ... ok
2026-10-24T13:20:43.557919Z ERROR tower_http::trace::on_failure: response failed classification=Status code: 503 Service Unavailable latency=0 ms
test routes::tests::fleet_attention::fleet_attention_inventory_succeeds_on_busy_host ... ok
test routes::tests::agent_helper_bridges::production_agent_bridge_returns_typed_unavailable_error ... ok
test routes::tests::agent_helper_bridges::invalid_and_revoked_tokens_are_unauthorized ... ok
test routes::tests::agent_helper_bridges::helper_routes_without_token_return_typed_unauthorized_errors ... ok
test routes::tests::agent_helper_bridges::command_helper_bridge_update_status_returns_command_output ... ok
test routes::tests::agent_helper_bridges::fake_agent_bridge_routes_return_stable_success_shapes ... ok
test routes::tests::fleet_attention::fleet_attention_denies_missing_scope ... ok
test routes::tests::fleet_handlers::fleet_enrollment_rejects_replayed_and_expired_bootstrap_secrets ... ok
test routes::tests::agent_helper_bridges::fake_helper_bridge_routes_return_stable_success_shapes ... ok
test routes::tests::notification_handlers::action_artifacts_are_declared_as_attachments ... ok
test routes::tests::fleet_handlers::fleet_routes_enforce_declared_scopes ... ok
test routes::tests::notification_handlers::attachment_download_requires_gateway_auth ... ok
test routes::tests::notification_handlers::event_resume_after_restart_returns_resync_required ... ok
test routes::tests::notification_handlers::event_resume_outside_buffer_returns_resync_required ... ok
test routes::tests::notification_handlers::event_resume_replays_buffered_records_after_last_event_id ... ok
test routes::tests::notification_handlers::attachment_tokens_are_bound_to_device ... ok
test routes::tests::notification_handlers::expired_attachment_tokens_return_typed_error ... ok
test routes::tests::notification_handlers::gate_action_forwards_selected_option_submission ... ok
test routes::tests::notification_handlers::notification_detail_returns_notes_action_and_attachments ... ok
test routes::tests::notification_handlers::notification_detail_not_found_returns_typed_error ... ok
test routes::tests::notification_handlers::notification_state_mutation_without_token_returns_typed_unauthorized_error ... ok
test routes::tests::notification_handlers::notification_state_mutation_not_found_returns_typed_error ... ok
test routes::tests::notification_handlers::notification_dismiss_updates_store_and_emits_refresh_event ... ok
test routes::tests::notification_handlers::notification_mark_read_updates_store_and_audits ... ok
test routes::tests::notification_handlers::notification_detail_mints_short_lived_download_tokens ... ok
test routes::tests::notification_handlers::notifications_list_can_include_dismissed_and_silent_rows ... ok
test routes::tests::notification_handlers::notifications_without_token_returns_typed_unauthorized_error ... ok
test routes::tests::agent_helper_bridges::command_agent_bridge_routes_return_command_output ... ok
test routes::tests::notification_handlers::notifications_list_filters_and_orders_newest_first ... ok
test routes::tests::notification_handlers::notifications_list_expiry_publishes_activity_cursor_event ... ok
test routes::tests::notification_handlers::notifications_list_uses_host_action_state ... ok
test routes::tests::notification_handlers::notifications_list_uses_resurface_activity_cursor_and_id_tiebreaker ... ok
test routes::tests::notification_handlers::unknown_route_returns_typed_not_found_error ... ok
test routes::tests::notification_handlers::question_action_forwards_specialized_submission ... ok
test routes::tests::session_handlers::fleet_installation_pin_mismatch_returns_quarantine_response ... ok
test routes::tests::notification_handlers::unsafe_or_oversized_attachments_do_not_receive_tokens ... ok
test routes::tests::notification_handlers::symlink_pointing_outside_tmp_is_not_downloadable ... ok
test routes::tests::session_handlers::fleet_request_body_limit_rejects_large_enrollment_payloads ... ok
test routes::tests::session_handlers::health_route_returns_stable_record ... ok
test routes::tests::session_handlers::fleet_protocol_negotiation_rejects_incompatible_versions ... ok
test routes::tests::session_handlers::pair_finish_rejects_expired_code ... ok
test routes::tests::session_handlers::pair_start_http_route_is_gone ... ok
test routes::tests::session_handlers::pair_finish_persists_device_and_returns_token_once ... ok
test routes::tests::session_handlers::push_subscriptions_require_auth ... ok
test routes::tests::session_handlers::fleet_rotation_and_revocation_reject_stale_or_revoked_tokens ... ok
test routes::tests::session_handlers::session_returns_authenticated_device ... ok
test server::tests::default_bind_is_loopback ... ok
test routes::tests::session_handlers::session_without_token_returns_typed_unauthorized_error ... ok
test server::tests::explicit_non_loopback_opt_in_is_allowed ... ok
test routes::tests::session_handlers::push_subscription_validation_and_audit_do_not_leak_provider_token ... ok
test server::tests::non_loopback_bind_requires_explicit_opt_in ... ok
test routes::tests::session_handlers::fleet_enrollment_attempts_are_rate_limited ... ok
test routes::tests::fleet_handlers::fleet_launch_failure_settles_failed_without_raw_bridge_output ... ok
test routes::tests::session_handlers::push_subscription_duplicate_updates_existing_record ... ok
test storage::tests::token_pairing_persists_only_hash ... ok
test sudo_runner::tests::argv_record::absent_record_is_pending ... ok
test sudo_runner::tests::argv_record::begin_without_end_is_pending ... ok
test sudo_runner::tests::argv_record::complete_record_returns_arguments_in_order ... ok
test server::tests::listener_serves_health_over_http ... ok
test sudo_runner::tests::argv_record::empty_record_is_pending ... ok
test storage::tests::push_subscription_register_update_and_revoke_is_atomic ... ok
test routes::tests::session_handlers::test_push_provider_records_hint_attempts ... ok
test sudo_runner::tests::cli::capabilities_omit_detached_execution_when_identity_backend_is_absent ... ok
test sudo_runner::tests::argv_record::partial_argument_list_is_pending ... ok
test sudo_runner::tests::cli::capabilities_succeed_without_tty_manifest_or_sudo ... ok
test sudo_runner::tests::cli::help_succeeds_without_tty_or_sudo ... ok
test sudo_runner::tests::cli::linux_identity_backend_advertises_detached_execution ... ok
test sudo_runner::tests::cli::capabilities_reject_other_arguments ... ok
test sudo_runner::tests::cli::parse_rejects_launcher_override_arguments ... ok
test sudo_runner::tests::cli::parse_requires_one_manifest_and_digest ... ok
test sudo_runner::tests::cli::python_hosted_entry_rejects_non_absolute_interpreter ... ok
test routes::tests::session_handlers::push_subscription_register_list_and_revoke_round_trip ... ok
test sudo_runner::tests::cli::detach_rejects_before_auth_when_capability_absent ... ok
test sudo_runner::tests::argv_record::staged_producer_becomes_complete_through_readiness_helper ... ok
test server::tests::listener_smoke_exercises_pairing_auth_and_session ... ok
test sudo_runner::tests::dispatch::detached_auth_failure_keeps_ledger_shaped_output ... ok
test sudo_runner::tests::cli::native_launcher_places_internal_modes_directly_after_executable ... ok
test sudo_runner::tests::dispatch::cwd_removed_after_authentication_fails_before_dispatch_and_cleans_up ... ok
test sudo_runner::tests::dispatch::digest_mismatch_runs_nothing ... ok
test sudo_runner::tests::dispatch::detached_root_spawn_failure_keeps_ledger_shaped_output ... ok
test sudo_runner::tests::dispatch::command_literal_chdir_flag_after_boundary_is_allowed ... ok
test fleet_auth::tests::rotation_and_revocation_reject_old_or_revoked_tokens ... ok
test sudo_runner::tests::cli::python_hosted_launcher_preserves_isolated_module_prefix ... ok
test sudo_runner::tests::dispatch::apt_get_shaped_command_uses_requested_cwd_without_sudo_chdir_option ... ok
test sudo_runner::tests::dispatch::detached_success_emits_validated_handshake ... ok
test sudo_runner::tests::dispatch::tty_unavailable_emits_skipped_ledger_and_never_invokes_sudo ... ok
test sudo_runner::tests::dispatch::command_runs_in_distinct_cwd_with_spaces_and_parent_cwd_is_unchanged ... ok
test sudo_runner::tests::dispatch::nonexistent_cwd_fails_before_dispatch_and_cleans_up ... ok
test sudo_runner::tests::dispatch::initial_auth_failure_marks_all_entries_skipped ... ok
test sudo_runner::tests::worker::initgroups_base_group_accepts_current_platform_gid ... ok
test sudo_runner::tests::worker::initgroups_c_int_conversion_rejects_too_large_gid ... ok
test sudo_runner::tests::worker::internal_modes_reject_started_path_outside_handoff_dir ... ok
test sudo_runner::tests::dispatch::permission_denied_cwd_fails_before_dispatch_when_supported ... ok
test sudo_runner::tests::worker::internal_worker_rejects_ledger_symlink ... ok
test sudo_runner::tests::worker::internal_worker_rejects_mismatched_witness_without_executing ... ok
test sudo_runner::tests::worker::detached_timestamp_cleanup_failure_returns_started_handshake ... ok
test sudo_runner::tests::worker::internal_worker_reverifies_manifest_digest ... ok
test sudo_runner::tests::worker::internal_worker_records_run_as_resolution_failure ... ok
test sudo_runner::tests::dispatch::failed_command_stops_remaining_entries_by_default ... ok
test sudo_runner::tests::dispatch::resume_from_skips_prior_commands_and_probe_failure_uses_plain_sudo ... ok
test sudo_runner::tests::dispatch::successful_run_uses_expected_sudo_order_and_cleared_environment ... ok
test sudo_runner::tests::worker::internal_worker_writes_ledger_and_log_for_direct_command ... ok
test sudo_runner::tests::worker::internal_worker_keeps_bounded_ledger_tail_for_large_output ... ok
test sudo_runner::tests::worker::ledger_json_validates_against_manifest ... ok
test sudo_runner::tests::argv_record::incomplete_record_never_resolves_before_deadline ... ok
test sudo_runner::tests::worker::post_spawn_identity_failure_reaps_barred_worker ... ok
test wire::tests::error_wire_json_snapshot ... ok
test wire::tests::event_wire_json_snapshot ... ok
test sudo_runner::tests::worker::internal_worker_stop_file_cancels_running_command ... ok
test wire::tests::fleet_hello_keeps_capability_and_fleet_contract_versions_independent ... ok
test wire::tests::health_wire_json_snapshot ... ok
test wire::tests::mobile_agent_wire_json_snapshot ... ok
test wire::tests::mobile_macro_catalog_entry_deserializes_legacy_shape ... ok
test wire::tests::pairing_wire_json_snapshot ... ok
test wire::tests::mobile_helper_wire_json_snapshot ... ok
test wire::tests::push_hint_mapping_uses_safe_event_projection ... ok
test sudo_runner::tests::worker::output_policy_full_is_hard_bounded ... ok
test wire::tests::push_subscription_wire_json_snapshot ... ok
test wire::tests::session_wire_json_snapshot ... ok
test sudo_runner::tests::worker::post_spawn_publish_failure_reaps_barred_worker ... ok
test sudo_runner::tests::worker::output_policy_none_keeps_ledger_empty ... ok
test federation_worker::imp::tests::remote::worker_catalog_hosts_continues_only_requested_hosts ... ok
test sudo_runner::tests::worker::timeout_terminates_process_group_and_records_failed_entry ... ok
2026-10-24T13:20:43.834604Z  INFO sase_gateway::fleet_reads: fleet snapshot build finished scope="presentation" outcome="ok" duration_ms=279 served_rows=0 refresh_count=1 timed_out_waiters=0
test routes::tests::fleet_attention::fleet_attention_read_empty_request_touches_no_notification_store ... ok
2026-10-24T13:20:43.837262Z  INFO sase_gateway::fleet_reads: fleet snapshot build finished scope="presentation" outcome="ok" duration_ms=278 served_rows=0 refresh_count=1 timed_out_waiters=0
2026-10-24T13:20:43.838612Z  INFO sase_gateway::fleet_reads: fleet snapshot build finished scope="presentation" outcome="ok" duration_ms=281 served_rows=0 refresh_count=1 timed_out_waiters=0
test routes::tests::fleet_handlers::fleet_enrollment_and_hello_return_identity_and_capabilities ... ok
2026-10-24T13:20:43.862616Z  INFO sase_gateway::fleet_reads: fleet snapshot build finished scope="presentation" outcome="ok" duration_ms=243 served_rows=2 refresh_count=1 timed_out_waiters=0
2026-10-24T13:20:43.867333Z  INFO sase_gateway::fleet_reads: fleet snapshot build finished scope="presentation" outcome="ok" duration_ms=305 served_rows=0 refresh_count=1 timed_out_waiters=0
2026-10-24T13:20:43.889112Z  INFO sase_gateway::fleet_reads: fleet snapshot build finished scope="presentation" outcome="ok" duration_ms=270 served_rows=3 refresh_count=1 timed_out_waiters=0
test sudo_runner::tests::worker::internal_worker_does_not_execute_before_valid_witness ... ok
2026-10-24T13:20:43.945338Z  INFO sase_gateway::fleet_reads: fleet snapshot build finished scope="presentation" outcome="ok" duration_ms=77 served_rows=0 refresh_count=2 timed_out_waiters=0
2026-10-24T13:20:43.947270Z  INFO sase_gateway::fleet_reads: fleet snapshot build finished scope="presentation" outcome="ok" duration_ms=122 served_rows=1 refresh_count=1 timed_out_waiters=0
2026-10-24T13:20:43.948568Z  INFO sase_gateway::fleet_reads: fleet snapshot build finished scope="presentation" outcome="ok" duration_ms=121 served_rows=1 refresh_count=1 timed_out_waiters=0
2026-10-24T13:20:43.949130Z  INFO sase_gateway::fleet_reads: fleet snapshot build finished scope="presentation" outcome="ok" duration_ms=132 served_rows=1 refresh_count=1 timed_out_waiters=0
2026-10-24T13:20:43.949726Z  INFO sase_gateway::fleet_reads: fleet snapshot build finished scope="presentation" outcome="ok" duration_ms=119 served_rows=1 refresh_count=1 timed_out_waiters=0
2026-10-24T13:20:43.950314Z  INFO sase_gateway::fleet_reads: fleet snapshot build finished scope="presentation" outcome="ok" duration_ms=125 served_rows=1 refresh_count=1 timed_out_waiters=0
2026-10-24T13:20:43.951632Z  INFO sase_gateway::fleet_reads: fleet snapshot build finished scope="presentation" outcome="ok" duration_ms=120 served_rows=1 refresh_count=1 timed_out_waiters=0
test routes::tests::fleet_attention::fleet_attention_resolve_publishes_invalidation_events ... ok
test routes::tests::fleet_attention::fleet_attention_read_projects_correlated_gate_and_question ... ok
test routes::tests::fleet_attention::fleet_attention_resolve_maps_bridge_race_to_already_settled ... ok
2026-10-24T13:20:43.957063Z  INFO sase_gateway::fleet_reads: fleet snapshot build finished scope="presentation" outcome="ok" duration_ms=117 served_rows=1 refresh_count=1 timed_out_waiters=0
2026-10-24T13:20:43.957081Z  INFO sase_gateway::fleet_reads: fleet snapshot build finished scope="presentation" outcome="ok" duration_ms=120 served_rows=1 refresh_count=1 timed_out_waiters=0
2026-10-24T13:20:43.958389Z  INFO sase_gateway::fleet_reads: fleet snapshot build finished scope="presentation" outcome="ok" duration_ms=116 served_rows=1 refresh_count=1 timed_out_waiters=0
2026-10-24T13:20:43.958444Z  INFO sase_gateway::fleet_reads: fleet snapshot build finished scope="presentation" outcome="ok" duration_ms=117 served_rows=1 refresh_count=1 timed_out_waiters=0
test routes::tests::fleet_attention::fleet_attention_resolve_second_controller_gets_already_settled ... ok
2026-10-24T13:20:43.959579Z  INFO sase_gateway::fleet_reads: fleet snapshot build finished scope="presentation" outcome="ok" duration_ms=129 served_rows=1 refresh_count=1 timed_out_waiters=0
2026-10-24T13:20:43.959715Z  INFO sase_gateway::fleet_reads: fleet snapshot build finished scope="presentation" outcome="ok" duration_ms=111 served_rows=1 refresh_count=1 timed_out_waiters=0
2026-10-24T13:20:43.960578Z  INFO sase_gateway::fleet_reads: fleet snapshot build finished scope="presentation" outcome="ok" duration_ms=102 served_rows=1 refresh_count=1 timed_out_waiters=0
2026-10-24T13:20:43.960659Z  INFO sase_gateway::fleet_reads: fleet snapshot build finished scope="presentation" outcome="ok" duration_ms=102 served_rows=1 refresh_count=1 timed_out_waiters=0
test routes::tests::fleet_attention::fleet_attention_resolve_gate_settles_replays_and_conflicts ... ok
2026-10-24T13:20:43.961293Z  INFO sase_gateway::fleet_reads: fleet snapshot build finished scope="presentation" outcome="ok" duration_ms=98 served_rows=1 refresh_count=1 timed_out_waiters=0
test routes::tests::fleet_handlers::fleet_stop_retains_row_with_retry_and_fork ... ok
2026-10-24T13:20:43.962904Z  INFO sase_gateway::fleet_reads: fleet snapshot build finished scope="presentation" outcome="ok" duration_ms=112 served_rows=1 refresh_count=1 timed_out_waiters=0
2026-10-24T13:20:43.965079Z  INFO sase_gateway::fleet_reads: fleet snapshot build finished scope="presentation" outcome="ok" duration_ms=19 served_rows=0 refresh_count=3 timed_out_waiters=0
test routes::tests::fleet_attention::fleet_attention_resolve_refuses_stale_revision ... ok
test routes::tests::fleet_handlers::fleet_mutate_denies_missing_scope ... ok
test routes::tests::fleet_handlers::fleet_mutate_stop_settles_and_replays ... ok
test routes::tests::fleet_handlers::fleet_mutate_changed_payload_conflicts ... ok
test routes::tests::fleet_attention::fleet_attention_resolve_sudo_approve_is_deny_only_remote ... ok
2026-10-24T13:20:43.966609Z  INFO sase_gateway::fleet_reads: fleet snapshot build finished scope="presentation" outcome="ok" duration_ms=89 served_rows=1 refresh_count=1 timed_out_waiters=0
test routes::tests::fleet_handlers::fleet_launch_accepts_scoped_request_and_returns_receipt ... ok
2026-10-24T13:20:43.975262Z  INFO sase_gateway::fleet_reads: fleet snapshot build finished scope="presentation" outcome="ok" duration_ms=13 served_rows=1 refresh_count=2 timed_out_waiters=0
test routes::tests::fleet_handlers::fleet_mutate_same_key_returns_settled_after_terminal ... ok
test routes::tests::fleet_handlers::fleet_launch_recovers_pending_reservation_after_gateway_restart ... ok
2026-10-24T13:20:43.977546Z  INFO sase_gateway::fleet_reads: fleet snapshot build finished scope="presentation" outcome="ok" duration_ms=12 served_rows=1 refresh_count=2 timed_out_waiters=0
2026-10-24T13:20:43.993578Z  INFO sase_gateway::fleet_reads: fleet snapshot build finished scope="presentation" outcome="ok" duration_ms=25 served_rows=1 refresh_count=1 timed_out_waiters=0
2026-10-24T13:20:43.994092Z  INFO sase_gateway::fleet_reads: fleet snapshot build finished scope="presentation" outcome="ok" duration_ms=27 served_rows=1 refresh_count=2 timed_out_waiters=0
test routes::tests::fleet_handlers::fleet_launch_replays_delayed_launch_and_reconciles_visible_row ... ok
2026-10-24T13:20:44.005835Z  INFO sase_gateway::fleet_reads: fleet snapshot build finished scope="presentation" outcome="ok" duration_ms=11 served_rows=1 refresh_count=3 timed_out_waiters=0
test routes::tests::fleet_handlers::fleet_catalog_overlay_serves_fresh_launch_before_rebuild ... ok
2026-10-24T13:20:44.008435Z  INFO sase_gateway::fleet_reads: fleet snapshot build finished scope="presentation" outcome="ok" duration_ms=13 served_rows=1 refresh_count=1 timed_out_waiters=0
2026-10-24T13:20:44.012462Z  INFO sase_gateway::fleet_reads: fleet snapshot build finished scope="presentation" outcome="ok" duration_ms=74 served_rows=1 refresh_count=1 timed_out_waiters=0
test routes::tests::fleet_handlers::fleet_launch_omits_bridge_name_when_prompt_has_id ... ok
test fleet_reads::tests::reads::project_eligibility_is_bounded_and_path_free ... ok
2026-10-24T13:20:44.022607Z  INFO sase_gateway::fleet_reads: fleet snapshot build finished scope="presentation" outcome="ok" duration_ms=9 served_rows=1 refresh_count=1 timed_out_waiters=0
test routes::tests::fleet_handlers::fleet_mutate_refuses_stale_revision_and_superseded_instance ... ok
2026-10-24T13:20:44.031721Z  WARN sase_gateway::fleet_reads: fleet snapshot build finished scope="presentation" outcome="backend" duration_ms=39 served_rows=0 refresh_count=0 timed_out_waiters=0
2026-10-24T13:20:44.031810Z  WARN sase_gateway::fleet_reads: fleet snapshot back-off engaged scope="presentation" consecutive_failures=1 window_secs=14
2026-10-24T13:20:44.032103Z  WARN sase_gateway::fleet_reads: fleet snapshot build finished scope="presentation" outcome="backend" duration_ms=0 served_rows=0 refresh_count=0 timed_out_waiters=0
2026-10-24T13:20:44.032170Z  INFO sase_gateway::fleet_reads: fleet snapshot build finished scope="presentation" outcome="ok" duration_ms=9 served_rows=1 refresh_count=1 timed_out_waiters=0
test fleet_reads::tests::refresh::backoff_returns_remembered_error_on_cold_cache ... ok
2026-10-24T13:20:44.035513Z ERROR tower_http::trace::on_failure: response failed classification=Status code: 503 Service Unavailable latency=1 ms
test routes::tests::fleet_handlers::fleet_mutate_refuses_terminal_missing_capability_and_bridge_failure ... ok
2026-10-24T13:20:44.037055Z  INFO sase_gateway::fleet_reads: fleet snapshot build finished scope="presentation" outcome="ok" duration_ms=45 served_rows=1 refresh_count=1 timed_out_waiters=0
test fleet_reads::tests::reads::ordinary_multiline_prompt_stays_presentable_across_read_apis ... ok
2026-10-24T13:20:44.046412Z  INFO sase_gateway::fleet_reads: fleet snapshot build finished scope="presentation" outcome="ok" duration_ms=41 served_rows=0 refresh_count=1 timed_out_waiters=0
2026-10-24T13:20:44.080969Z  INFO sase_gateway::fleet_reads: fleet snapshot build finished scope="history" outcome="ok" duration_ms=189 served_rows=3 refresh_count=1 timed_out_waiters=0
test fleet_reads::tests::presentation::active_and_protected_members_remain_visible_without_root ... ok
2026-10-24T13:20:44.090346Z  INFO sase_gateway::fleet_reads: fleet snapshot build finished scope="presentation" outcome="ok" duration_ms=69 served_rows=1 refresh_count=1 timed_out_waiters=0
2026-10-24T13:20:44.091842Z  INFO sase_gateway::fleet_reads: fleet snapshot build finished scope="presentation" outcome="ok" duration_ms=71 served_rows=2 refresh_count=1 timed_out_waiters=0
test fleet_reads::tests::presentation::dead_active_leftovers_are_demoted_and_window_bounded ... ok
2026-10-24T13:20:44.092535Z  INFO sase_gateway::fleet_reads: fleet snapshot build finished scope="presentation" outcome="ok" duration_ms=72 served_rows=2 refresh_count=1 timed_out_waiters=0
2026-10-24T13:20:44.093402Z  INFO sase_gateway::fleet_reads: fleet snapshot build finished scope="presentation" outcome="ok" duration_ms=73 served_rows=2 refresh_count=1 timed_out_waiters=0
test fleet_reads::tests::snapshots::concurrent_snapshot_reads_are_coalesced ... ok
2026-10-24T13:20:44.094499Z  INFO sase_gateway::fleet_reads: fleet snapshot build finished scope="presentation" outcome="ok" duration_ms=76 served_rows=2 refresh_count=1 timed_out_waiters=0
test fleet_reads::tests::reads::summary_counts_are_independent_of_catalog_page_size ... ok
2026-10-24T13:20:44.096388Z  INFO sase_gateway::fleet_reads: fleet snapshot build finished scope="presentation" outcome="ok" duration_ms=76 served_rows=2 refresh_count=1 timed_out_waiters=0
2026-10-24T13:20:44.096388Z  INFO sase_gateway::fleet_reads: fleet snapshot build finished scope="presentation" outcome="ok" duration_ms=75 served_rows=2 refresh_count=1 timed_out_waiters=0
test fleet_reads::tests::reads::one_unprojectable_row_does_not_erase_the_presentable_set ... ok
test fleet_reads::tests::reads::detail_and_content_reads_use_opaque_handles ... ok
2026-10-24T13:20:44.099595Z  INFO sase_gateway::fleet_reads: fleet snapshot build finished scope="presentation" outcome="ok" duration_ms=79 served_rows=2 refresh_count=1 timed_out_waiters=0
2026-10-24T13:20:44.106392Z  INFO sase_gateway::fleet_reads: fleet snapshot build finished scope="presentation" outcome="ok" duration_ms=81 served_rows=2 refresh_count=1 timed_out_waiters=0
2026-10-24T13:20:44.106441Z  INFO sase_gateway::fleet_reads: fleet snapshot build finished scope="history" outcome="ok" duration_ms=59 served_rows=1 refresh_count=1 timed_out_waiters=0
2026-10-24T13:20:44.106701Z  INFO sase_gateway::fleet_reads: fleet snapshot build finished scope="presentation" outcome="ok" duration_ms=81 served_rows=2 refresh_count=1 timed_out_waiters=0
2026-10-24T13:20:44.107294Z  WARN sase_gateway::fleet_reads: fleet snapshot build finished scope="presentation" outcome="backend" duration_ms=0 served_rows=0 refresh_count=0 timed_out_waiters=0
2026-10-24T13:20:44.107413Z  WARN sase_gateway::fleet_reads: fleet snapshot back-off engaged scope="presentation" consecutive_failures=1 window_secs=14
2026-10-24T13:20:44.107464Z  WARN sase_gateway::fleet_reads: fleet snapshot build finished scope="presentation" outcome="backend" duration_ms=0 served_rows=0 refresh_count=0 timed_out_waiters=0
2026-10-24T13:20:44.107751Z  WARN sase_gateway::fleet_reads: fleet snapshot build finished scope="presentation" outcome="backend" duration_ms=0 served_rows=0 refresh_count=0 timed_out_waiters=0
2026-10-24T13:20:44.107881Z  INFO sase_gateway::fleet_reads: fleet snapshot build finished scope="presentation" outcome="ok" duration_ms=82 served_rows=2 refresh_count=1 timed_out_waiters=0
2026-10-24T13:20:44.108345Z  WARN sase_gateway::fleet_reads: fleet snapshot build finished scope="history" outcome="backend" duration_ms=0 served_rows=0 refresh_count=0 timed_out_waiters=0
test fleet_reads::tests::refresh::checkpoint_hook_runs_after_presentation_success_only ... 2026-10-24T13:20:44.108382Z  INFO sase_gateway::fleet_reads: fleet snapshot build finished scope="presentation" outcome="ok" duration_ms=28 served_rows=0 refresh_count=1 timed_out_waiters=0
ok
2026-10-24T13:20:44.108543Z  INFO sase_gateway::fleet_reads: fleet snapshot build finished scope="presentation" outcome="ok" duration_ms=83 served_rows=2 refresh_count=1 timed_out_waiters=0
2026-10-24T13:20:44.108910Z  INFO sase_gateway::fleet_reads: fleet snapshot build finished scope="presentation" outcome="ok" duration_ms=83 served_rows=2 refresh_count=1 timed_out_waiters=0
2026-10-24T13:20:44.109336Z  INFO sase_gateway::fleet_reads: fleet snapshot build finished scope="presentation" outcome="ok" duration_ms=84 served_rows=2 refresh_count=1 timed_out_waiters=0
2026-10-24T13:20:44.109352Z  INFO sase_gateway::fleet_reads: fleet snapshot build finished scope="presentation" outcome="ok" duration_ms=84 served_rows=1 refresh_count=1 timed_out_waiters=0
2026-10-24T13:20:44.109572Z  WARN sase_gateway::fleet_reads: fleet snapshot build finished scope="presentation" outcome="backend" duration_ms=0 served_rows=0 refresh_count=0 timed_out_waiters=0
2026-10-24T13:20:44.109808Z  INFO sase_gateway::fleet_reads: fleet snapshot build finished scope="presentation" outcome="ok" duration_ms=84 served_rows=2 refresh_count=1 timed_out_waiters=0
test fleet_reads::tests::snapshots::failed_history_rebuild_retains_stale_partial_prior_snapshot ... ok
2026-10-24T13:20:44.110998Z  INFO sase_gateway::fleet_reads: fleet snapshot build finished scope="presentation" outcome="ok" duration_ms=85 served_rows=3 refresh_count=1 timed_out_waiters=0
test fleet_reads::tests::snapshots::failed_rebuild_retains_stale_partial_prior_snapshot ... ok
test fleet_reads::tests::invalidation::fleet_events_publish_replay_and_resync_faults ... ok
test fleet_reads::tests::presentation::plan_turn_without_parent_timestamp_is_nested_not_a_root ... ok
test fleet_reads::tests::reads::batch_lookup_reads_followed_id_outside_first_page ... ok
2026-10-24T13:20:44.113419Z  INFO sase_gateway::fleet_reads: fleet snapshot build finished scope="presentation" outcome="ok" duration_ms=46 served_rows=3 refresh_count=1 timed_out_waiters=0
2026-10-24T13:20:44.116914Z  INFO sase_gateway::fleet_reads: fleet snapshot build finished scope="presentation" outcome="ok" duration_ms=91 served_rows=0 refresh_count=1 timed_out_waiters=0
test fleet_reads::tests::presentation::root_less_completed_plan_chain_agent_session_is_presented_through_its_plan_turn ... ok
2026-10-24T13:20:44.117910Z  INFO sase_gateway::fleet_reads: fleet snapshot build finished scope="presentation" outcome="ok" duration_ms=21 served_rows=2 refresh_count=2 timed_out_waiters=0
test fleet_reads::tests::snapshots::aged_cache_triggers_exactly_one_coalesced_rebuild ... ok
2026-10-24T13:20:44.119928Z  INFO sase_gateway::fleet_reads: fleet snapshot build finished scope="presentation" outcome="ok" duration_ms=28 served_rows=0 refresh_count=1 timed_out_waiters=0
test fleet_reads::tests::presentation::dead_orphan_of_dismissed_agent_session_is_excluded_from_catalog ... ok
2026-10-24T13:20:44.123790Z  INFO sase_gateway::fleet_reads: fleet snapshot build finished scope="presentation" outcome="ok" duration_ms=39 served_rows=2 refresh_count=1 timed_out_waiters=0
2026-10-24T13:20:44.150087Z  INFO sase_gateway::fleet_reads: fleet snapshot build finished scope="history" outcome="ok" duration_ms=54 served_rows=2 refresh_count=1 timed_out_waiters=0
test fleet_reads::tests::presentation::terminal_agent_session_root_represents_completed_members ... ok
2026-10-24T13:20:44.158727Z  INFO sase_gateway::fleet_reads: fleet snapshot build finished scope="history" outcome="ok" duration_ms=50 served_rows=0 refresh_count=1 timed_out_waiters=0
test fleet_reads::tests::presentation::dead_dismissed_workflow_run_is_excluded_from_catalog ... ok
2026-10-24T13:20:44.163653Z  INFO sase_gateway::fleet_reads: fleet snapshot build finished scope="history" outcome="ok" duration_ms=54 served_rows=2 refresh_count=1 timed_out_waiters=0
test fleet_reads::tests::presentation::history_rows_inherit_owner_presentation_facts_from_agent_session_root ... ok
2026-10-24T13:20:44.168217Z  INFO sase_gateway::fleet_reads: fleet snapshot build finished scope="presentation" outcome="ok" duration_ms=11 served_rows=3 refresh_count=2 timed_out_waiters=0
test fleet_reads::tests::snapshots::stale_snapshot_bound_cursor_returns_restart_page ... ok
2026-10-24T13:20:44.172735Z  INFO sase_gateway::fleet_reads: fleet snapshot build finished scope="history" outcome="ok" duration_ms=55 served_rows=7 refresh_count=1 timed_out_waiters=0
2026-10-24T13:20:44.176695Z  INFO sase_gateway::fleet_reads: fleet snapshot build finished scope="history" outcome="ok" duration_ms=51 served_rows=2 refresh_count=1 timed_out_waiters=0
test fleet_reads::tests::presentation::orphan_terminal_agent_session_members_are_hidden_from_presentation ... ok
test fleet_reads::tests::presentation::owner_served_set_matches_visible_identity_set ... ok
2026-10-24T13:20:44.208627Z  INFO sase_gateway::fleet_reads: fleet snapshot build finished scope="presentation" outcome="ok" duration_ms=6 served_rows=2 refresh_count=2 timed_out_waiters=0
2026-10-24T13:20:44.209353Z  INFO sase_gateway::fleet_reads: fleet snapshot build finished scope="presentation" outcome="ok" duration_ms=11 served_rows=4 refresh_count=1 timed_out_waiters=0
test fleet_reads::tests::refresh::failed_builds_back_off_and_reset_on_success ... ok
2026-10-24T13:20:44.267713Z  INFO sase_gateway::fleet_reads: fleet snapshot build finished scope="presentation" outcome="ok" duration_ms=14 served_rows=5 refresh_count=1 timed_out_waiters=0
test fleet_reads::tests::refresh::overlay_queries_once_per_snapshot_and_skips_under_contention ... ok
test federation_worker::imp::tests::remote::worker_bounds_deadline_and_preserves_fast_host_beside_hung_host ... ok
test federation_worker::imp::tests::remote::worker_trusts_pinned_ca_and_preserves_healthy_host_beside_faults ... ok
2026-10-24T13:20:44.381886Z  WARN sase_gateway::fleet_reads: fleet snapshot build finished scope="presentation" outcome="ok" duration_ms=361 served_rows=2 refresh_count=1 timed_out_waiters=20
test fleet_reads::tests::refresh::slow_build_stampede_starts_exactly_one_build ... ok
2026-10-24T13:20:44.479029Z  INFO sase_gateway::fleet_reads: fleet snapshot build finished scope="presentation" outcome="ok" duration_ms=461 served_rows=2 refresh_count=1 timed_out_waiters=0
2026-10-24T13:20:44.532045Z  WARN sase_gateway::fleet_reads: fleet snapshot build finished scope="presentation" outcome="ok" duration_ms=421 served_rows=2 refresh_count=2 timed_out_waiters=1
test fleet_reads::tests::refresh::late_build_result_fills_cache_for_later_reads ... ok
2026-10-24T13:20:44.608529Z  INFO sase_gateway::fleet_reads: fleet snapshot build finished scope="presentation" outcome="ok" duration_ms=452 served_rows=200 refresh_count=1 timed_out_waiters=0
2026-10-24T13:20:44.891962Z  INFO sase_gateway::fleet_reads: fleet snapshot build finished scope="presentation" outcome="ok" duration_ms=412 served_rows=2 refresh_count=2 timed_out_waiters=0
test fleet_reads::tests::refresh::forced_refresh_waits_then_builds_after_call ... ok
2026-10-24T13:20:45.288010Z  INFO sase_gateway::fleet_reads: fleet snapshot build finished scope="history" outcome="ok" duration_ms=565 served_rows=206 refresh_count=1 timed_out_waiters=0
test sudo_runner::tests::worker::internal_worker_streams_output_before_command_exit ... ok
test fleet_reads::tests::snapshots::explicit_history_pages_beyond_presentation_without_eager_cache ... ok
test sudo_runner::tests::worker::internal_worker_timeout_completes_when_descendant_holds_pipe ... ok
test federation_worker::imp::tests::remote::read_backoff_serves_cache_and_short_circuits_slow_host ... ok

test result: ok. 243 passed; 0 failed; 0 ignored; 0 measured; 0 filtered out; finished in 3.69s

     Running unittests src/federation_worker_main.rs (/home/bryan/.cache/sase/tmp/cargo-targets/gh_sase-org__sase-ws14-261024_085653/build/debug/deps/sase_federation_worker-f7de5e3f5997d7f4)

running 0 tests

test result: ok. 0 passed; 0 failed; 0 ignored; 0 measured; 0 filtered out; finished in 0.00s

     Running unittests src/main.rs (/home/bryan/.cache/sase/tmp/cargo-targets/gh_sase-org__sase-ws14-261024_085653/build/debug/deps/sase_gateway-32bb7c33fe771196)

running 0 tests

test result: ok. 0 passed; 0 failed; 0 ignored; 0 measured; 0 filtered out; finished in 0.00s

     Running unittests src/sudo_runner_main.rs (/home/bryan/.cache/sase/tmp/cargo-targets/gh_sase-org__sase-ws14-261024_085653/build/debug/deps/sase_sudo_runner-b27a0bb4977b2f3f)

running 0 tests

test result: ok. 0 passed; 0 failed; 0 ignored; 0 measured; 0 filtered out; finished in 0.00s

     Running unittests src/lib.rs (/home/bryan/.cache/sase/tmp/cargo-targets/gh_sase-org__sase-ws14-261024_085653/build/debug/deps/sase_macro_lsp-388d65d68a383e4b)

running 242 tests
test catalog_cache::tests::finalizer_catalog_cache_invalidate_all_drops_cached_rows ... ok
test catalog_cache::tests::finalizer_catalog_cache_refreshes_from_helper ... ok
test catalog_cache::tests::agent_catalog_cache_reports_helper_failure_without_cached_rows ... ok
test catalog_cache::tests::snippet_cache_refreshes_from_helper ... ok
test catalog_cache::tests::finalizer_catalog_cache_reports_helper_failure_without_cached_rows ... ok
test lsp_convert::tests::at_reference_kind_stage_items_filter_on_the_bare_typed_word ... ok
test lsp_convert::tests::at_reference_items_filter_on_the_typed_text_and_preview_the_match ... ok
test lsp_convert::tests::choice_items_use_enum_member_full_value_edits_and_metadata ... ok
test catalog_cache::tests::snippet_cache_returns_stale_entries_on_helper_failure ... ok
test catalog_cache::tests::finalizer_catalog_cache_returns_stale_rows_on_helper_failure ... ok
test lsp_convert::tests::choice_list_sets_incomplete_when_truncated ... ok
test lsp_convert::tests::coincident_additional_edits_merge_into_primary ... ok
test lsp_convert::tests::commit_documentation_omits_the_body_block_when_empty ... ok
test catalog_cache::tests::agent_catalog_cache_refreshes_from_helper ... ok
test catalog_cache::tests::vcs_repo_cache_refreshes_from_helper ... ok
test lsp_convert::tests::commit_documentation_truncates_a_long_body_to_a_bounded_line_count ... ok
test lsp_convert::tests::commit_payload_rows_render_as_references_with_body_in_documentation ... ok
test lsp_convert::tests::completion_item_uses_replacement_text_edit ... ok
test lsp_convert::tests::agent_completion_items_render_distinct_kinds_and_stable_sort_groups ... ok
test lsp_convert::tests::converts_editor_range_to_lsp_range ... ok
test catalog_cache::tests::vcs_repo_cache_returns_stale_response_on_helper_failure ... ok
test lsp_convert::tests::converts_sase_snippet_template_to_lsp_snippet_syntax ... ok
test lsp_convert::tests::finalizer_completion_emits_operation_aware_lsp_metadata ... ok
test lsp_convert::tests::model_alias_shortcut_item_carries_multi_edits_as_additional ... ok
test lsp_convert::tests::model_completion_items_render_provider_label_and_trailing_sort_group ... ok
test lsp_convert::tests::model_shortcut_item_carries_multi_edits_as_additional ... ok
test lsp_convert::tests::placeholder_tabstop_snippet_retriggers_completion ... ok
test lsp_convert::tests::single_edit_shortcut_items_have_no_additional_edits ... ok
test semantic_tokens::tests::legend_appends_argument_entries_without_reordering_existing_tokens ... ok
test server::jinja::tests::gitcommit_never_gets_jinja_scope ... ok
test server::jinja::tests::macro_directories_use_macro_scope ... ok
test server::jinja::tests::memory_notes_use_macro_scope ... ok
test server::jinja::tests::other_markdown_uses_prompt_scope ... ok
test server::jinja::tests::sase_language_ids_use_prompt_scope ... ok
test server::tests::argument_list_continuation::completion_offers_remaining_argument_at_continuation_caret ... ok
test server::tests::completion::identity_and_static_value_roles_use_the_shared_contract ... ok
test semantic_tokens::tests::unclosed_alternation_opener_carries_unknown_modifier ... ok
test semantic_tokens::tests::glossary_tokens_split_wrapped_segments_and_keep_artifacts ... ok
test semantic_tokens::tests::alternation_tokens_skip_literal_zones ... ok
test semantic_tokens::tests::alternation_branch_names_get_parameter_tokens ... ok
test semantic_tokens::tests::alternation_tokens_cover_mid_word_delimiters_and_separators ... ok
test semantic_tokens::tests::argument_tokens_skip_fenced_blocks ... ok
test semantic_tokens::tests::paren_alternation_keeps_macro_name_tokens ... ok
test semantic_tokens::tests::unknown_argument_keys_get_deprecated_modifier_when_catalog_is_warm ... ok
test semantic_tokens::tests::argument_values_preserve_pieces_around_nested_artifact_tokens ... ok
test semantic_tokens::tests::multiline_argument_values_split_on_lines_with_utf16_ranges ... ok
test semantic_tokens::tests::argument_tokens_cover_structure_and_literal_values ... ok
test semantic_tokens::tests::name_tokens_cover_xprompts_directives_aliases_and_literal_zones ... ok
test server::tests::documents::catalog_invalidation_tracks_xprompt_source_dirs ... ok
test server::tests::documents::document_eligibility_narrows_plain_markdown ... ok
test server::tests::catalog_loading::load_vcs_project_catalog_rejects_unknown_schema ... ok
test server::tests::catalog_loading::loads_v4_vcs_project_catalog_with_patch_entry_kind ... ok
test server::tests::catalog_loading::pre_v5_vcs_project_catalogs_default_palette_and_tags ... ok
test server::tests::catalog_loading::loads_v5_vcs_project_catalog_with_palette_and_tags ... ok
test server::tests::catalog_loading::loads_v1_vcs_project_catalog_with_project_defaults ... ok
test server::tests::catalog_loading::loads_v3_vcs_project_catalog_namespaces ... ok
test server::tests::jinja::filters_complete_after_pipe ... ok
test server::tests::completion::queue_completion_avoids_agent_targets ... ok
test server::tests::jinja::pipe_trigger_outside_tag_returns_none ... ok
test server::tests::jinja::repeat_makes_n_available ... ok
test server::tests::jinja::run_time_names_hidden_in_input_declaring_prompt ... ok
test server::tests::jinja::skill_frontmatter_offers_provider_vars ... ok
test server::tests::jinja::xprompt_path_offers_positional_args ... ok
test server::tests::jinja::statement_closers_lead_inside_for ... ok
test server::tests::catalog_loading::load_vcs_project_catalog_ignores_malformed_namespaces ... ok
test server::tests::jinja::members_complete_after_wait_dot ... ok
test server::tests::at_references::appends_known_kind_artifact_diagnostics_from_active_catalog ... ok
test server::tests::jinja::conditional_n_without_repeat_is_dimmed_with_hint ... ok
test server::tests::jinja::hover_shows_engine_markdown ... ok
test server::tests::choice_completion::frontmatter_type_field_replaces_the_current_value ... ok
test server::tests::at_references::semantic_tokens_mark_directive_owned_code_bodies ... ok
test server::tests::jinja::hover_resolves_filter ... ok
test server::tests::catalog_loading::loads_v4_vcs_project_catalog_with_entry_kind_and_no_legacy_kind ... ok
test server::tests::catalog_loading::artifact_catalog_loader_is_tolerant_and_schema_gated ... ok
test server::tests::macro_lsp::diagnostic_source_stays_legacy ... ok
test server::tests::choice_completion::frontmatter_completes_advertised_catalog_types ... ok
test server::tests::jinja::empty_in_tag_slot_claims_cursor_with_empty_menu ... ok
test server::tests::jinja::completion_item_carries_edits_sort_and_deprecation ... ok
test server::tests::choice_diagnostics::malformed_diagnostic_data_is_ignored_and_kinds_are_respected ... ok
test server::tests::completion::model_paren_completion_offers_alias_keys_and_values ... ok
test server::tests::jinja::fenced_code_has_no_jinja_menu ... ok
test server::tests::jinja::gitcommit_has_no_jinja_completion ... ok
test server::tests::choice_completion::bool_arguments_use_the_shared_choice_builder ... ok
test server::tests::macro_lsp::cache_isolates_true_from_false_policy ... ok
test server::tests::at_references::malformed_glossary_catalog_degrades_to_no_semantics ... ok
test server::tests::choice_completion::mid_value_completion_replaces_the_whole_current_value ... ok
test server::tests::completion::wait_keywords_survive_helper_failure_and_mixed_version_payloads ... ok
test server::tests::at_references::artifact_payload_inventory_cache_rebuilds_on_all_invalidation_paths ... ok
test server::tests::completion::directive_name_completion_documents_queue_capacity_budget ... ok
test server::tests::choice_completion::quoted_punctuation_inserts_the_encoded_value ... ok
test server::tests::macro_lsp::macro_document_paths_are_eligible_alongside_legacy ... ok
test server::tests::at_references::encodes_known_artifact_refs_and_skips_unknown_and_literal_tokens ... ok
test server::tests::macro_lsp::server_name_and_commands_preserved ... ok
test server::tests::completion::completes_xprompt_from_static_catalog ... ok
test server::tests::choice_diagnostics::hover_shows_choices_agent_and_large_table_truncation ... ok
test server::tests::choice_diagnostics::published_choice_diagnostic_data_drives_preferred_quick_fix ... ok
test server::tests::jinja::angle_bracket_inside_tag_stays_jinja ... ok
test server::tests::jinja::frontmatter_inputs_listed_first ... ok
test server::tests::macro_lsp::semantic_tokens_stable_across_policy ... ok
test server::tests::at_references::completes_grouped_at_references_from_the_client_root ... ok
test server::tests::completion::wait_unicode_mid_clause_uses_utf16_replacement_range ... ok
test server::tests::jinja::brace_trigger_outside_tag_returns_none ... ok
test server::tests::at_references::fuzzy_at_reference_payloads_survive_client_filtering ... ok
test server::tests::macro_lsp::macro_config_filenames_invalidate ... ok
test server::tests::macro_lsp::legacy_policy_is_unconditional ... ok
test server::tests::choice_completion::utf16_positions_replace_the_value_after_non_bmp ... ok
test server::tests::completion::final_completion_does_not_fetch_agent_catalog ... ok
test server::tests::completion::wait_bead_value_completion_uses_helper_rows ... ok
test server::tests::choice_completion::named_enum_completes_declared_choices_with_metadata ... ok
test server::tests::completion::final_completion_uses_catalog_and_dedicated_lsp_path ... ok
test server::tests::choice_completion::frontmatter_does_not_offer_types_in_the_markdown_body ... ok
test server::tests::model_completion::load_model_catalog_rejects_unknown_schema ... ok
test server::tests::completion::directive_keyword_completion_uses_the_active_fragment_range ... ok
test server::tests::completion::completes_directive_argument_values ... ok
test server::tests::completion::final_completion_returns_empty_on_helper_failure ... ok
test server::tests::macro_lsp::denied_policy_still_loads_retired_sources_through_rust ... ok
test server::tests::project_tags::semantic_tokens_emit_sigil_and_name_with_accent ... ok
test server::tests::project_tags::semantic_tokens_v4_catalog_has_no_tag_tokens ... ok
test server::tests::project_tags::semantic_tokens_mark_unknown_and_providerless_tags ... ok
test server::tests::project_tags::semantic_tokens_mark_disabled_state_tags ... ok
test server::tests::shortcuts::advertises_jinja_trigger_characters ... ok
test server::tests::shortcuts::advertises_full_semantic_tokens_with_standard_legend ... ok
test server::tests::model_completion::provider_scope_requires_provider_catalog_entry_for_old_catalogs ... ok
test server::tests::model_completion::completes_model_directive_values_from_catalog ... ok
test server::tests::choice_completion::colon_and_positional_forms_complete_enum_values ... ok
test server::tests::shortcuts::advertises_model_shortcut_trigger_character ... ok
test server::tests::model_completion::provider_scoped_model_directive_completion_returns_qualified_rows ... ok
test server::tests::macro_lsp::metadata_env_ignores_legacy_prefix ... ok
test server::tests::macro_lsp::false_policy_never_merges_unverified_helper_data ... ok
test server::tests::completion::directive_matrix_completes_every_advertised_name_and_alias ... ok
test server::tests::macro_lsp::macro_server_resolves_both_names ... ok
test server::tests::completion::wait_completion_uses_kind_aware_agent_catalog ... ok
test server::tests::model_completion::model_directive_completion_without_catalog_is_empty ... ok
test server::tests::completion::hold_completion_warms_agent_catalog_for_positional_targets ... ok
test server::tests::choice_completion::builtin_effort_argument_completes_seven_levels_in_order ... ok
test server::tests::model_completion::provider_scoped_model_directive_completion_uses_first_slash ... ok
test server::tests::model_completion::macro_argument_model_completion_matches_directive_list ... ok
test server::tests::completion::removed_identity_directives_do_not_complete ... ok
test server::tests::model_completion::leading_at_filters_model_completion_to_aliases ... ok
test server::tests::model_completion::enriched_model_catalog_renders_alias_detail_and_metadata ... ok
test server::tests::completion::host_catalog_is_not_fetched_for_static_value_roles ... ok
test server::tests::model_completion::model_directive_completion_filters_by_alias_hint ... ok
test server::tests::model_completion::stale_v1_alias_catalog_still_produces_items ... ok
test server::tests::project_tags::leading_project_recognizes_tags ... ok
test server::tests::completion::completes_identity_and_clan_from_the_public_editor_surface ... ok
test server::tests::shortcuts::advertises_slash_completion_trigger_character ... ok
test server::tests::shortcuts::model_alias_shortcut_missing_catalog_returns_empty_list ... ok
test server::tests::shortcuts::advertises_plus_completion_trigger_character ... ok
test server::tests::project_tags::initialize_advertises_project_tag_palette ... ok
test server::tests::shortcuts::model_alias_shortcut_offers_alias_rows_only_in_catalog_order ... ok
test server::tests::model_completion::model_at_suffix_still_completes_effort_vocabulary ... ok
test server::tests::project_tags::code_actions_rewrite_colon_refs_to_tags ... ok
test server::tests::model_completion::provider_scoped_model_directive_completion_matches_short_alias ... ok
test server::tests::shortcuts::advertises_placeholder_completion_trigger_character ... ok
test server::tests::shortcuts::advertises_vcs_ref_completion_trigger_characters ... ok
test server::tests::shortcuts::advertises_at_reference_completion_trigger_character ... ok
test server::tests::shortcuts::model_alias_shortcut_malformed_catalog_returns_empty_list ... ok
test server::tests::catalog_loading::completes_artifact_kinds_and_local_payloads_per_active_project ... ok
test server::tests::shortcuts::model_alias_shortcut_no_match_returns_empty_list_not_fallback ... ok
test server::tests::shortcuts::model_alias_shortcut_shows_expansion_detail_and_metadata_documentation ... ok
test server::tests::snippets::completes_placeholders_from_the_current_document ... ok
test server::tests::snippets::placeholder_completion_is_empty_without_another_span ... ok
test server::tests::snippets::bare_trigger_snippets_require_client_snippet_support ... ok
test server::tests::shortcuts::model_alias_shortcut_sets_filter_text_sort_text_and_preselect ... ok
test server::tests::snippets::placeholder_completion_appends_a_missing_closing_bracket ... ok
test server::tests::shortcuts::model_shortcut_adjacent_directives_remove_second_and_stay_disjoint ... ok
test server::tests::shortcuts::model_alias_shortcut_adjacent_directives_remove_second_and_stay_disjoint ... ok
test server::tests::shortcuts::model_shortcut_matches_short_hint_but_inserts_canonical_model ... ok
test server::tests::shortcuts::model_shortcut_offers_model_rows_only_in_catalog_order ... ok
test server::tests::snippets::placeholder_tabstop_snippet_item_retriggers_suggestions ... ok
test server::tests::project_tags::diagnostics_flag_ambiguous_tags_as_errors ... ok
test server::tests::project_tags::diagnostics_warn_on_disabled_tags_with_enable_hint ... ok
test server::tests::project_tags::hover_shows_state_and_workspace_dir ... ok
test server::tests::project_tags::code_actions_offer_tag_quickfixes ... ok
test server::tests::snippets::bare_trigger_snippet_completion_uses_snippet_items ... ok
test server::tests::project_tags::diagnostics_follow_anchored_tag_policy ... ok
test server::tests::shortcuts::model_shortcut_backspace_transitions_between_marker_kinds ... ok
test server::tests::shortcuts::model_shortcut_filters_and_replaces_provider_scoped_rows ... ok
test server::tests::shortcuts::model_alias_shortcut_text_edit_covers_every_trailing_whitespace_case ... ok
test server::tests::shortcuts::model_alias_shortcut_leaves_protected_equals_to_ordinary_completion ... ok
test server::tests::shortcuts::model_alias_shortcut_detects_later_line_and_after_leading_space ... ok
test server::tests::shortcuts::model_alias_shortcut_replaces_whole_token_from_mid_token_caret ... ok
test server::tests::shortcuts::model_alias_shortcut_filters_by_partial_case_insensitive_query ... ok
test server::tests::project_tags::hover_shows_resolved_tag_details ... ok
test server::tests::snippets::directive_snippet_for_alt_uses_brace_shorthand ... ok
test server::tests::snippets::identity_and_clan_editor_surfaces_use_current_metadata ... ok
test server::tests::shortcuts::model_shortcut_skips_unsafe_model_values_and_keeps_owned_empty_lists ... ok
test server::tests::surfaces::definition_uses_definition_path_outside_workspace_root ... ok
test server::tests::surfaces::definition_returns_none_for_pseudo_or_missing_sources ... ok
test server::tests::surfaces::typed_launch_diagnostics_and_code_actions_are_unconditional ... ok
test server::tests::snippets::snippet_project_variable_stays_literal_without_a_project ... ok
test server::tests::snippets::snippet_project_variable_resolves_from_a_leading_vcs_ref ... ok
test server::tests::project_tags::completion_docs_show_state_and_workspace_dir ... ok
test server::tests::vcs_completion::completes_vcs_ref_from_v3_catalog ... ok
test server::tests::vcs_completion::obsolete_and_unspaced_plus_forms_do_not_complete_vcs_projects ... ok
test server::tests::snippets::typed_launch_directive_recipes_are_unconditional ... ok
test server::tests::surfaces::exposes_hover_diagnostics_code_actions_and_definition ... ok
test server::tests::shortcuts::model_shortcut_empty_and_protected_contexts_do_not_fall_through ... ok
test server::tests::snippets::snippet_project_variable_falls_back_to_the_current_project ... ok
test server::tests::surfaces::detects_snippet_support_from_client_capabilities ... ok
test server::tests::spacer::eligible_completion_carries_command_while_zero_input_does_not ... ok
test server::tests::vcs_completion::vcs_project_completion_without_catalog_is_empty ... ok
test server::tests::spacer::accept_after_change_then_format_deletes_owned_spacer ... ok
test server::tests::snippets::xprompt_snippet_completions_use_single_row_skeletons ... ok
test server::tests::project_tags::completes_v5_project_rows_as_tags_in_catalog_order ... ok
test server::tests::surfaces::diagnostics_for_uri_text_honors_canonical_memory_file_uri ... ok
test server::tests::vcs_completion::bare_plus_at_bof_completes_vcs_project ... ok
test server::tests::snippets::snippet_project_variable_resolves_from_a_leading_tag ... ok
test server::tests::snippets::required_text_skeleton_keeps_double_colon_before_existing_text ... ok
test server::tests::snippets::snippet_clients_receive_identity_and_clan_forms ... ok
test server::tests::spacer::transition_completion_maps_ranges_with_spacer_deletion ... ok
test server::tests::spacer::accept_before_change_and_coalesced_opener ... ok
test server::tests::surfaces::definition_preserves_catalog_definition_range ... ok
test server::tests::spacer::stale_close_and_unrelated_changes_reject ... ok
test server::tests::spacer::autopair_unicode_suffix_and_before_opener_conventions ... ok
test catalog_cache::tests::snippet_cache_uses_rust_fallback_when_helper_unavailable ... ok
test server::tests::shortcuts::legacy_star_shortcuts_do_not_open_model_shortcut_completion ... ok
test server::tests::vcs_completion::space_delimited_plus_completes_vcs_project ... ok
test server::tests::vcs_completion::completes_vcs_repo_with_ranked_items_and_text_edit ... ok
test server::tests::vcs_completion::vcs_ref_completion_accepts_v2_catalog_without_namespaces ... ok
test server::tests::vcs_completion::vcs_ref_completion_ignores_malformed_namespaces ... ok
test server::tests::spacer::unicode_prefix_keeps_exact_deletion_range ... ok
test server::tests::snippets::xprompt_snippet_completion_returns_one_row_per_match ... ok
test server::tests::vcs_completion::vcs_ref_owner_slash_still_uses_repo_completion ... ok
test server::tests::vcs_completion::completes_vcs_project_with_primary_and_additional_edits ... ok
test server::tests::vcs_completion::vcs_ref_completion_filters_aliases_and_namespaces ... ok
test server::tests::vcs_completion::vcs_repo_completion_error_response_is_empty ... ok
test server::tests::vcs_completion::completes_vcs_project_replacing_existing_tag_at_eof ... ok
test server::tests::vcs_completion::vcs_project_completion_without_tags_falls_back_to_entries ... ok
test server::tests::surfaces::diagnostics_for_uri_text_accepts_markdown_local_xprompts ... ok
test server::tests::vcs_completion::automatic_and_manual_space_plus_completion_match ... ok
test server::tests::vcs_completion::completes_vcs_patch_with_pr_label_details ... ok
test server::tests::at_references::glossary_hover_and_definition_use_source_ranges ... ok
test server::tests::at_references::artifact_completion_discloses_the_display_cap ... ok
test catalog_cache::tests::wrapper_launch_with_plugin_metadata_uses_fast_rust_catalog ... ok
test catalog_cache::tests::direct_launch_keeps_rust_catalog_when_helper_unavailable ... ok
test server::tests::at_references::encodes_glossary_tokens_by_active_project_without_overlaps ... ok
test server::tests::project_tags::leading_tag_drives_glossary_context ... ok
test catalog_cache::tests::direct_launch_without_plugin_metadata_merges_helper_and_rust_catalogs ... ok
test server::tests::catalog_loading::completes_commit_payloads_from_a_real_git_checkout ... ok
test catalog_cache::tests::finalizer_catalog_cache_reports_helper_timeout ... ok
test catalog_cache::tests::vcs_repo_cache_reports_helper_timeout ... ok

test result: ok. 242 passed; 0 failed; 0 ignored; 0 measured; 0 filtered out; finished in 0.20s

     Running unittests src/main.rs (/home/bryan/.cache/sase/tmp/cargo-targets/gh_sase-org__sase-ws14-261024_085653/build/debug/deps/sase_macro_lsp-375ed2631c1dc605)

running 0 tests

test result: ok. 0 passed; 0 failed; 0 ignored; 0 measured; 0 filtered out; finished in 0.00s

     Running tests/jsonrpc_macro_lsp.rs (/home/bryan/.cache/sase/tmp/cargo-targets/gh_sase-org__sase-ws14-261024_085653/build/debug/deps/jsonrpc_macro_lsp-dbc563bed06ae5cf)

running 5 tests
test macros_config_recognized_for_invalidation ... ok
test semantic_tokens_legend_order_unchanged ... ok
test initialize_advertises_both_command_families_and_legacy_identity ... ok
test new_macro_binary_reports_macro_version ... ok
test diagnostics_keep_legacy_source_and_code_actions ... ok

test result: ok. 5 passed; 0 failed; 0 ignored; 0 measured; 0 filtered out; finished in 0.02s

     Running tests/jsonrpc_stdio.rs (/home/bryan/.cache/sase/tmp/cargo-targets/gh_sase-org__sase-ws14-261024_085653/build/debug/deps/jsonrpc_stdio-94aca1f87255eaf8)

running 11 tests
test read_message_round_trips_normal_jsonrpc_payload ... ok
test stdio_jsonrpc_unsupported_markdown_has_no_xprompt_behavior ... ok
test stdio_jsonrpc_invalid_auto_spelling_publishes_error ... ok
test stdio_jsonrpc_bare_snippet_completion ... ok
test stdio_jsonrpc_placeholder_completion_uses_open_document_text ... ok
test stdio_jsonrpc_frontmatter_diagnostics ... ok
test stdio_jsonrpc_initialize_and_completion ... ok
test stdio_jsonrpc_directive_value_roles ... ok
test stdio_jsonrpc_id_kwargs_diagnostics_completion_and_snippets ... ok
test stdio_jsonrpc_semantic_tokens_include_argument_structure ... ok
test read_message_times_out_on_stalled_input ... ok

test result: ok. 11 passed; 0 failed; 0 ignored; 0 measured; 0 filtered out; finished in 10.00s

     Running tests/jsonrpc_stdio_alternation.rs (/home/bryan/.cache/sase/tmp/cargo-targets/gh_sase-org__sase-ws14-261024_085653/build/debug/deps/jsonrpc_stdio_alternation-6337dd34133ff557)

running 1 test
test stdio_jsonrpc_alternation_tokens_and_unclosed_diagnostic ... ok

test result: ok. 1 passed; 0 failed; 0 ignored; 0 measured; 0 filtered out; finished in 0.05s

     Running tests/jsonrpc_stdio_choice_completion.rs (/home/bryan/.cache/sase/tmp/cargo-targets/gh_sase-org__sase-ws14-261024_085653/build/debug/deps/jsonrpc_stdio_choice_completion-7aa77125503ae81f)

running 1 test
test stdio_jsonrpc_choice_and_frontmatter_type_completion ... ok

test result: ok. 1 passed; 0 failed; 0 ignored; 0 measured; 0 filtered out; finished in 0.04s

     Running tests/jsonrpc_stdio_choice_diagnostics.rs (/home/bryan/.cache/sase/tmp/cargo-targets/gh_sase-org__sase-ws14-261024_085653/build/debug/deps/jsonrpc_stdio_choice_diagnostics-10c77d466454d800)

running 1 test
test stdio_jsonrpc_choice_diagnostic_quickfix_and_hover ... ok

test result: ok. 1 passed; 0 failed; 0 ignored; 0 measured; 0 filtered out; finished in 0.03s

     Running tests/jsonrpc_stdio_jinja.rs (/home/bryan/.cache/sase/tmp/cargo-targets/gh_sase-org__sase-ws14-261024_085653/build/debug/deps/jsonrpc_stdio_jinja-e997c7530619ed92)

running 1 test
test stdio_jsonrpc_jinja_completion_and_silent_brace_trigger ... ok

test result: ok. 1 passed; 0 failed; 0 ignored; 0 measured; 0 filtered out; finished in 0.05s

     Running tests/jsonrpc_stdio_model_alias_shortcut.rs (/home/bryan/.cache/sase/tmp/cargo-targets/gh_sase-org__sase-ws14-261024_085653/build/debug/deps/jsonrpc_stdio_model_alias_shortcut-84bcf3f2426f7cd5)

running 1 test
test stdio_jsonrpc_model_alias_shortcut_completion ... ok

test result: ok. 1 passed; 0 failed; 0 ignored; 0 measured; 0 filtered out; finished in 0.10s

     Running tests/jsonrpc_stdio_model_shortcut.rs (/home/bryan/.cache/sase/tmp/cargo-targets/gh_sase-org__sase-ws14-261024_085653/build/debug/deps/jsonrpc_stdio_model_shortcut-30facc0dcd4d010d)

running 1 test
test stdio_jsonrpc_model_shortcut_completion_transitions ... ok

test result: ok. 1 passed; 0 failed; 0 ignored; 0 measured; 0 filtered out; finished in 0.06s

     Running tests/jsonrpc_stdio_on_type_formatting.rs (/home/bryan/.cache/sase/tmp/cargo-targets/gh_sase-org__sase-ws14-261024_085653/build/debug/deps/jsonrpc_stdio_on_type_formatting-286405d18819d070)

running 3 tests
test stdio_jsonrpc_on_type_formatting_deletes_invocation_colon ... ok
test stdio_jsonrpc_on_type_formatting_continues_macro_argument_list ... ok
test stdio_jsonrpc_on_type_formatting_moves_double_colon_delimiter ... ok

test result: ok. 3 passed; 0 failed; 0 ignored; 0 measured; 0 filtered out; finished in 0.04s

     Running tests/jsonrpc_stdio_spacer_paren.rs (/home/bryan/.cache/sase/tmp/cargo-targets/gh_sase-org__sase-ws14-261024_085653/build/debug/deps/jsonrpc_stdio_spacer_paren-cc72f5d7fa64dd19)

running 1 test
test stdio_jsonrpc_spacer_paren_accept_format_and_complete ... ok

test result: ok. 1 passed; 0 failed; 0 ignored; 0 measured; 0 filtered out; finished in 0.05s

     Running unittests src/lib.rs (/home/bryan/.cache/sase/tmp/cargo-targets/gh_sase-org__sase-ws14-261024_085653/build/debug/deps/sase_workspace_hack-12b210af7fdda35a)

running 0 tests

test result: ok. 0 passed; 0 failed; 0 ignored; 0 measured; 0 filtered out; finished in 0.00s

   Doc-tests sase_core

running 0 tests

test result: ok. 0 passed; 0 failed; 0 ignored; 0 measured; 0 filtered out; finished in 0.00s

   Doc-tests sase_core_rs

running 0 tests

test result: ok. 0 passed; 0 failed; 0 ignored; 0 measured; 0 filtered out; finished in 0.00s

   Doc-tests sase_gateway

running 0 tests

test result: ok. 0 passed; 0 failed; 0 ignored; 0 measured; 0 filtered out; finished in 0.00s

   Doc-tests sase_macro_lsp

running 0 tests

test result: ok. 0 passed; 0 failed; 0 ignored; 0 measured; 0 filtered out; finished in 0.00s

   Doc-tests sase_workspace_hack

running 0 tests

test result: ok. 0 passed; 0 failed; 0 ignored; 0 measured; 0 filtered out; finished in 0.00s

...........................................................................................................
----------------------------------------------------------------------
Ran 107 tests in 0.366s

OK
succeeded  exit=0  duration=686342ms
Traceback (most recent call last):
  File "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/src/sase/core/rust.py", line 48, in require_rust_extension
    return importlib.import_module(RUST_EXTENSION_MODULE_NAME)
           ~~~~~~~~~~~~~~~~~~~~~~~^^^^^^^^^^^^^^^^^^^^^^^^^^^^
  File "/home/bryan/.local/share/uv/python/cpython-3.14.7-linux-x86_64-gnu/lib/python3.14/importlib/__init__.py", line 88, in import_module
    return _bootstrap._gcd_import(name[level:], package, level)
           ~~~~~~~~~~~~~~~~~~~~~~^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
  File "<frozen importlib._bootstrap>", line 1406, in _gcd_import
  File "<frozen importlib._bootstrap>", line 1371, in _find_and_load
  File "<frozen importlib._bootstrap>", line 1342, in _find_and_load_unlocked
  File "<frozen importlib._bootstrap>", line 938, in _load_unlocked
  File "<frozen importlib._bootstrap_external>", line 759, in exec_module
  File "<frozen importlib._bootstrap>", line 491, in _call_with_frames_removed
  File "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/sase/repos/linked/sase-core/crates/sase_core_py/python/sase_core_rs/__init__.py", line 1, in <module>
    from . import sase_core_rs
ImportError: cannot import name 'sase_core_rs' from partially initialized module 'sase_core_rs' (most likely due to a circular import) (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/sase/repos/linked/sase-core/crates/sase_core_py/python/sase_core_rs/__init__.py)

The above exception was the direct cause of the following exception:

Traceback (most recent call last):
  File "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/tools/refresh_linked_checkout", line 30, in <module>
    raise SystemExit(main())
                     ~~~~^^
  File "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/tools/refresh_linked_checkout", line 23, in main
    message = refresh_clean_linked_checkout(str(args.checkout))
  File "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/src/sase/_linked_repo_workspaces.py", line 230, in refresh_clean_linked_checkout
    status = classify_git_upstream(path)
  File "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/src/sase/version/_git.py", line 115, in classify_git_upstream
    git_root_text = run_git(source_root, "rev-parse", "--show-toplevel")
  File "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/src/sase/version/_git.py", line 282, in run_git
    completed, _outcome = run_with_git_lock_retry(
                          ~~~~~~~~~~~~~~~~~~~~~~~^
        attempt,
        ^^^^^^^^
    ...<3 lines>...
        result_adapter=_git_result_adapter,
        ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
    )
    ^
  File "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/src/sase/git_lock_retry/__init__.py", line 94, in run_with_git_lock_retry
    return impl(
        attempt,
    ...<14 lines>...
        **extra,
    )
  File "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/src/sase/git_lock_retry/_retry.py", line 76, in run_with_git_lock_retry
    retry_delays = configured_delays()
  File "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/src/sase/git_lock_retry/__init__.py", line 47, in git_lock_retry_delays
    return impl()
  File "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/src/sase/git_lock_retry/_policy.py", line 117, in git_lock_retry_delays
    installed = policy.git_lock_wire_schema_version()
  File "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/src/sase/core/git_lock_facade.py", line 22, in git_lock_wire_schema_version
    binding = require_rust_binding("git_lock_wire_schema_version")
  File "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/src/sase/core/rust.py", line 67, in require_rust_binding
    module = require_rust_extension()
  File "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/src/sase/core/rust.py", line 50, in require_rust_extension
    raise ImportError(
    ...<3 lines>...
    ) from exc
ImportError: sase_core_rs is not importable in this environment but is a hard runtime dependency of sase; run `just install-venv` in /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14.
# Capture the source identity after the checkout refresh above and before
# the build below. It is staged to a pending file and moved into place
# only after both the extension and the LSP install succeed (final step
# below), so an edit made during the build still reads as stale.
# Harden cargo crate downloads against transient crates.io flakiness.
# CI has hit `curl ... [16] Error in the HTTP2 framing layer` while
# maturin's `cargo metadata` fetches deps; disabling HTTP/2 multiplexing
# and raising the retry count makes the download resilient. Both are
# overridable from the environment.
🍹 Building a mixed python/rust project
🐍 Found CPython 3.14 at /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/.venv/bin/python
🔗 Found pyo3 bindings with abi3-py3.12 support
📡 Using build options features from pyproject.toml
   Compiling proc-macro2 v1.0.106
   Compiling unicode-ident v1.0.24
   Compiling quote v1.0.45
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
   Compiling stable_deref_trait v1.2.1
   Compiling crossbeam-deque v0.8.8
   Compiling futures-sink v0.3.32
   Compiling hashbrown v0.17.0
   Compiling equivalent v1.0.2
   Compiling iana-time-zone v0.1.65
   Compiling slab v0.4.12
   Compiling futures-io v0.3.32
   Compiling ucd-trie v0.1.7
   Compiling futures-task v0.3.32
   Compiling tower-service v0.3.3
   Compiling bitflags v2.11.1
   Compiling httparse v1.10.1
   Compiling writeable v0.6.3
   Compiling untrusted v0.9.0
   Compiling libm v0.2.16
   Compiling litemap v0.8.2
   Compiling same-file v1.0.6
   Compiling heck v0.5.0
   Compiling icu_properties_data v2.2.0
   Compiling typenum v1.20.0
   Compiling icu_normalizer_data v2.2.0
   Compiling utf8_iter v1.0.4
   Compiling fnv v1.0.7
   Compiling tower-layer v0.3.3
   Compiling deunicode v1.6.2
   Compiling parking_lot_core v0.9.12
   Compiling httpdate v1.0.3
   Compiling lazy_static v1.5.0
   Compiling rayon-core v1.13.0
   Compiling either v1.19.0
   Compiling rustls v0.21.12
   Compiling tracing-core v0.1.36
   Compiling thiserror v1.0.69
   Compiling sync_wrapper v1.0.2
   Compiling anstyle v1.0.14
   Compiling percent-encoding v2.3.2
   Compiling encoding_rs v0.8.35
   Compiling scopeguard v1.2.0
   Compiling ryu v1.0.23
   Compiling pkg-config v0.3.33
   Compiling clap_lex v1.1.1
   Compiling unicode-segmentation v1.13.3
   Compiling vcpkg v0.2.15
   Compiling aho-corasick v1.1.4
   Compiling bstr v1.13.1
   Compiling http v1.4.0
   Compiling indexmap v2.14.0
   Compiling winnow v1.0.4
   Compiling rustversion v1.0.22
   Compiling getrandom v0.4.2
   Compiling cc v1.2.61
   Compiling num-conv v0.2.1
   Compiling try-lock v0.2.5
   Compiling rustix v1.1.4
   Compiling num-traits v0.2.19
   Compiling powerfmt v0.2.0
   Compiling slug v0.1.6
   Compiling time-core v0.1.8
   Compiling thiserror v2.0.18
   Compiling walkdir v2.5.0
   Compiling mime v0.3.17
   Compiling phf_shared v0.11.3
   Compiling toml_writer v1.1.3+spec-1.1.0
   Compiling futures-channel v0.3.32
   Compiling home v0.5.12
   Compiling atomic-waker v1.1.2
   Compiling generic-array v0.14.7
   Compiling errno v0.3.14
   Compiling socket2 v0.6.3
   Compiling mio v1.2.0
   Compiling getrandom v0.2.17
   Compiling ahash v0.8.12
   Compiling http v0.2.12
   Compiling pyo3-build-config v0.22.6
   Compiling colored v2.2.0
   Compiling grep-matcher v0.1.9
   Compiling memmap2 v0.9.11
   Compiling socket2 v0.5.10
   Compiling itertools v0.11.0
   Compiling winnow v0.7.15
   Compiling humansize v2.1.3
   Compiling linux-raw-sys v0.12.1
   Compiling ppv-lite86 v0.2.21
   Compiling cpufeatures v0.2.17
   Compiling form_urlencoded v1.2.2
   Compiling crossbeam-channel v0.5.17
   Compiling term_size v0.3.2
   Compiling memoffset v0.9.1
   Compiling lock_api v0.4.14
   Compiling fallible-streaming-iterator v0.1.9
   Compiling base64 v0.21.7
   Compiling clap_builder v4.6.7
   Compiling want v0.3.1
   Compiling fallible-iterator v0.3.0
   Compiling toml_parser v1.1.5+spec-1.1.0
   Compiling tinyvec v1.13.3
   Compiling unsafe-libyaml v0.2.11
   Compiling regex-automata v0.4.14
   Compiling toml_datetime v0.7.5+spec-1.1.0
   Compiling serde_spanned v1.1.2
   Compiling http-body v1.0.1
   Compiling deranged v0.5.8
   Compiling psm v0.1.24
   Compiling stacker v0.1.25
   Compiling ring v0.17.14
   Compiling libsqlite3-sys v0.30.1
   Compiling encoding_rs_io v0.1.8
   Compiling phf v0.11.3
   Compiling base64 v0.22.1
   Compiling time-macros v0.2.27
   Compiling signal-hook-registry v1.4.8
   Compiling fastrand v2.4.1
   Compiling serde_path_to_error v0.1.20
   Compiling tracing-log v0.2.0
   Compiling etcetera v0.8.0
   Compiling sharded-slab v0.1.7
   Compiling fs2 v0.4.3
   Compiling thread_local v1.1.9
   Compiling sync_wrapper v0.1.2
   Compiling hex v0.4.3
   Compiling rand_core v0.6.4
   Compiling block-buffer v0.10.4
   Compiling crypto-common v0.1.7
   Compiling http-body v0.4.6
   Compiling unicode-casefold v0.2.0
   Compiling webpki-roots v0.25.4
   Compiling nu-ansi-term v0.50.3
   Compiling matchit v0.7.3
   Compiling chrono v0.4.44
   Compiling num-integer v0.1.46
   Compiling pyo3-ffi v0.22.6
   Compiling pyo3-macros-backend v0.22.6
   Compiling pyo3 v0.22.6
   Compiling rustls-pemfile v1.0.4
   Compiling ipnet v2.12.0
   Compiling unicode-width v0.2.2
   Compiling indoc v2.0.7
   Compiling unindent v0.2.4
   Compiling hashbrown v0.14.5
   Compiling parking_lot v0.12.5
   Compiling pem v3.0.6
   Compiling time v0.3.47
   Compiling grep-searcher v0.1.17
   Compiling unicode-normalization v0.1.25
   Compiling http-body-util v0.1.3
   Compiling toml v0.9.12+spec-1.1.0
   Compiling rand_chacha v0.3.1
   Compiling digest v0.10.7
   Compiling regex v1.12.3
   Compiling globset v0.4.19
   Compiling num-bigint v0.4.6
   Compiling pest v2.9.4
   Compiling rand v0.8.6
   Compiling rayon v1.12.0
   Compiling hashlink v0.9.1
   Compiling sha2 v0.10.9
   Compiling sha1 v0.10.7
   Compiling tempfile v3.27.0
   Compiling rustls-webpki v0.101.7
   Compiling sct v0.7.1
   Compiling parse-zoneinfo v0.3.1
   Compiling ignore v0.4.32
   Compiling syn v2.0.117
   Compiling syn v3.0.9
   Compiling phf_generator v0.11.3
   Compiling pest_meta v2.9.4
   Compiling matchers v0.2.0
   Compiling globwalk v0.9.1
   Compiling phf_codegen v0.11.3
   Compiling chrono-tz-build v0.3.0
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
   Compiling chrono-tz v0.9.0
   Compiling pest_generator v2.9.4
   Compiling clap_derive v4.6.7
   Compiling derive_arbitrary v1.5.0
   Compiling async-stream v0.3.6
   Compiling tokio v1.52.2
   Compiling futures-util v0.3.32
   Compiling tracing v0.1.44
   Compiling arbitrary v1.5.0
   Compiling clap v4.6.7
   Compiling zerofrom-derive v0.1.7
   Compiling yoke-derive v0.8.2
   Compiling zerofrom v0.1.7
   Compiling table_formatter v0.6.1
   Compiling pest_derive v2.9.4
   Compiling simple_asn1 v0.6.4
   Compiling clap-cargo v0.18.3
   Compiling tracing-subscriber v0.3.23
   Compiling tower-http v0.5.2
   Compiling json5 v0.4.1
   Compiling pyo3-macros v0.22.6
   Compiling serde_urlencoded v0.7.1
   Compiling yoke v0.8.2
   Compiling dashmap v6.1.0
   Compiling serde_yaml v0.9.34+deprecated
   Compiling jsonwebtoken v9.3.1
   Compiling axum-core v0.4.5
   Compiling tera v1.20.1
   Compiling sase_workspace_hack v0.1.0 (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/sase/repos/linked/sase-core/crates/sase_workspace_hack)
   Compiling zerovec v0.11.6
   Compiling zerotrie v0.2.4
   Compiling tokio-util v0.7.18
   Compiling tower v0.5.3
   Compiling hyper v1.9.0
   Compiling tokio-rustls v0.24.1
   Compiling tinystr v0.8.3
   Compiling potential_utf v0.1.5
   Compiling h2 v0.3.27
   Compiling icu_collections v2.2.0
   Compiling hyper-util v0.1.20
   Compiling icu_locale_core v2.2.0
   Compiling tokei v15.0.0
   Compiling axum v0.7.9
   Compiling icu_provider v2.2.0
   Compiling icu_properties v2.2.0
   Compiling icu_normalizer v2.2.0
   Compiling rusqlite v0.32.1
   Compiling hyper v0.14.32
   Compiling idna_adapter v1.2.2
   Compiling idna v1.1.0
   Compiling sase_core v0.42.3 (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/sase/repos/linked/sase-core/crates/sase_core)
   Compiling url v2.5.8
   Compiling hyper-rustls v0.24.2
   Compiling reqwest v0.11.27
   Compiling sase_gateway v0.42.3 (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/sase/repos/linked/sase-core/crates/sase_gateway)
   Compiling sase_core_py v0.42.3 (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/sase/repos/linked/sase-core/crates/sase_core_py)
    Finished `dev-update` profile [optimized] target(s) in 4m 35s
📦 Built wheel for abi3 Python ≥ 3.12 to /home/bryan/.cache/sase/tmp/agent-tmp/gh_sase-org__sase-ws14-261024_085653/.tmpf4npgX/sase_core_rs-0.42.3-cp312-abi3-linux_x86_64.whl
✏️ Setting installed package as editable
🛠 Installed sase-core-rs-0.42.3
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
   Compiling crossbeam-deque v0.8.8
   Compiling serde_json v1.0.149
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
   Compiling bytes v1.11.1
   Compiling futures-io v0.3.32
   Compiling lazy_static v1.5.0
   Compiling scopeguard v1.2.0
   Compiling futures-task v0.3.32
   Compiling deunicode v1.6.2
   Compiling slab v0.4.12
   Compiling vcpkg v0.2.15
   Compiling percent-encoding v2.3.2
   Compiling unicode-segmentation v1.13.3
   Compiling rayon-core v1.13.0
   Compiling either v1.19.0
   Compiling clap_lex v1.1.1
   Compiling thiserror v1.0.69
   Compiling heck v0.5.0
   Compiling pkg-config v0.3.33
   Compiling anstyle v1.0.14
   Compiling rustix v1.1.4
   Compiling tower-service v0.3.3
   Compiling winnow v1.0.4
   Compiling sync_wrapper v1.0.2
   Compiling aho-corasick v1.1.4
   Compiling bstr v1.13.1
   Compiling phf_shared v0.11.3
   Compiling getrandom v0.4.2
   Compiling tower-layer v0.3.3
   Compiling winnow v0.7.15
   Compiling encoding_rs v0.8.35
   Compiling httparse v1.10.1
   Compiling ahash v0.8.12
   Compiling generic-array v0.14.7
   Compiling grep-matcher v0.1.9
   Compiling cc v1.2.61
   Compiling walkdir v2.5.0
   Compiling linux-raw-sys v0.12.1
   Compiling num-traits v0.2.19
   Compiling home v0.5.12
   Compiling cpufeatures v0.2.17
   Compiling tracing-core v0.1.36
   Compiling toml_writer v1.1.3+spec-1.1.0
   Compiling bitflags v1.3.2
   Compiling fallible-iterator v0.3.0
   Compiling indexmap v2.14.0
   Compiling tinyvec v1.13.3
   Compiling ryu v1.0.23
   Compiling unsafe-libyaml v0.2.11
   Compiling fastrand v2.4.1
   Compiling fallible-streaming-iterator v0.1.9
   Compiling itertools v0.11.0
   Compiling lock_api v0.4.14
   Compiling thread_local v1.1.9
   Compiling serde_spanned v1.1.2
   Compiling toml_datetime v0.7.5+spec-1.1.0
   Compiling nu-ansi-term v0.50.3
   Compiling unicode-width v0.2.2
   Compiling hex v0.4.3
   Compiling unicode-casefold v0.2.0
   Compiling clap_builder v4.6.7
   Compiling crossbeam-channel v0.5.17
   Compiling slug v0.1.6
   Compiling colored v2.2.0
   Compiling sharded-slab v0.1.7
   Compiling futures-channel v0.3.32
   Compiling ppv-lite86 v0.2.21
   Compiling getrandom v0.2.17
   Compiling phf v0.11.3
   Compiling errno v0.3.14
   Compiling mio v1.2.0
   Compiling socket2 v0.6.3
   Compiling memmap2 v0.9.11
   Compiling toml_parser v1.1.5+spec-1.1.0
   Compiling humansize v2.1.3
   Compiling term_size v0.3.2
   Compiling fs2 v0.4.3
   Compiling regex-automata v0.4.14
   Compiling encoding_rs_io v0.1.8
   Compiling psm v0.1.24
   Compiling stacker v0.1.25
   Compiling libsqlite3-sys v0.30.1
   Compiling etcetera v0.8.0
   Compiling tracing-log v0.2.0
   Compiling unicode-normalization v0.1.25
   Compiling fluent-uri v0.1.4
   Compiling hashbrown v0.14.5
   Compiling rand_core v0.6.4
   Compiling toml v0.9.12+spec-1.1.0
   Compiling signal-hook-registry v1.4.8
   Compiling parking_lot v0.12.5
   Compiling block-buffer v0.10.4
   Compiling crypto-common v0.1.7
   Compiling grep-searcher v0.1.17
   Compiling regex v1.12.3
   Compiling globset v0.4.19
   Compiling matchers v0.2.0
   Compiling tempfile v3.27.0
   Compiling hashlink v0.9.1
   Compiling rand_chacha v0.3.1
   Compiling chrono v0.4.44
   Compiling digest v0.10.7
   Compiling ignore v0.4.32
   Compiling pest v2.9.4
   Compiling rayon v1.12.0
   Compiling rand v0.8.6
   Compiling parse-zoneinfo v0.3.1
   Compiling sha1 v0.10.7
   Compiling sha2 v0.10.9
   Compiling syn v2.0.117
   Compiling syn v3.0.9
   Compiling pest_meta v2.9.4
   Compiling phf_generator v0.11.3
   Compiling globwalk v0.9.1
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
   Compiling arbitrary v1.5.0
   Compiling tokio v1.52.2
   Compiling futures-util v0.3.32
   Compiling tracing v0.1.44
   Compiling pest_derive v2.9.4
   Compiling clap v4.6.7
   Compiling chrono-tz v0.9.0
   Compiling table_formatter v0.6.1
   Compiling clap-cargo v0.18.3
   Compiling tracing-subscriber v0.3.23
   Compiling futures v0.3.32
   Compiling tower v0.5.3
   Compiling tokio-util v0.7.18
   Compiling json5 v0.4.1
   Compiling dashmap v6.1.0
   Compiling lsp-types v0.97.0
   Compiling serde_yaml v0.9.34+deprecated
   Compiling tera v1.20.1
   Compiling sase_workspace_hack v0.1.0 (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/sase/repos/linked/sase-core/crates/sase_workspace_hack)
   Compiling tokei v15.0.0
   Compiling tower-lsp-server v0.21.1
   Compiling rusqlite v0.32.1
   Compiling sase_core v0.42.3 (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/sase/repos/linked/sase-core/crates/sase_core)
   Compiling sase_macro_lsp v0.42.3 (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/sase/repos/linked/sase-core/crates/sase_macro_lsp)
    Finished `dev-update` profile [optimized] target(s) in 3m 40s
[rust-dev-install] installed /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/.venv/bin/sase-macro-lsp

┌───────────────────────────────────────────────────────┐
│                RUNNING: just fix                      │
└───────────────────────────────────────────────────────┘

---------- Formatting Python with ruff... ----------
.venv-format/bin/ruff format src/ tests/
12604 files left unchanged

---------- Fixing Python with ruff... ----------
.venv-format/bin/ruff check --fix src/ tests/
All checks passed!

---------- Rendering generated docs... ----------
.venv-format/bin/python tools/render_docs --format-only

---------- Rendering sase-backed docs... ----------
.venv/bin/python tools/render_docs --sase-only
[render_keymap_macro_reference] ok

---------- Formatting Markdown with prettier... ----------
node_modules/.bin/prettier --write "**/*.md"
AGENTS.md 134ms (unchanged)
CLAUDE.md 108ms (unchanged)
CONTRIBUTING.md 14ms (unchanged)
demos/README.md 63ms (unchanged)
docs/_templates/concept.md 11ms (unchanged)
docs/_templates/how-to.md 8ms (unchanged)
docs/_templates/hub.md 8ms (unchanged)
docs/_templates/reference.md 7ms (unchanged)
docs/_templates/tutorial.md 9ms (unchanged)
docs/ace.md 76ms (unchanged)
docs/agent_sessions.md 7ms (unchanged)
docs/agents_sidecar.md 6ms (unchanged)
docs/axe.md 13ms (unchanged)
docs/beads.md 21ms (unchanged)
docs/blog/index.md 5ms (unchanged)
docs/blog/posts/axe-background-daemon.md 23ms (unchanged)
docs/blog/posts/beads-and-sdd.md 37ms (unchanged)
docs/blog/posts/changespecs-in-practice.md 29ms (unchanged)
docs/blog/posts/commit-workflows-plugins.md 56ms (unchanged)
docs/blog/posts/macros-in-depth.md 28ms (unchanged)
docs/blog/posts/prompt-widget-and-nvim.md 33ms (unchanged)
docs/blog/posts/structured-agentic-software-engineering.md 64ms (unchanged)
docs/blog/posts/telegram-mobile-agents.md 43ms (unchanged)
docs/blog/posts/whats-next-memory-mobile-web.md 24ms (unchanged)
docs/blog/posts/why-coding-agents-need-orchestration.md 120ms (unchanged)
docs/cli.md 8ms (unchanged)
docs/commit_workflows.md 9ms (unchanged)
docs/concepts/agents.md 7ms (unchanged)
docs/concepts/automation.md 6ms (unchanged)
docs/concepts/index.md 7ms (unchanged)
docs/concepts/landing.md 6ms (unchanged)
docs/concepts/memory.md 6ms (unchanged)
docs/concepts/prompts.md 7ms (unchanged)
docs/concepts/providers.md 6ms (unchanged)
docs/concepts/work-units.md 7ms (unchanged)
docs/configuration.md 82ms (unchanged)
docs/content_layout.md 4ms (unchanged)
docs/contribute/acknowledgements.md 19ms (unchanged)
docs/contribute/agents-sidecar-sync.md 25ms (unchanged)
docs/contribute/architecture.md 49ms (unchanged)
docs/contribute/artifacts-pane-contract.md 37ms (unchanged)
docs/contribute/artifacts-pane-visual-grammar.md 59ms (unchanged)
docs/contribute/commit-workflow-orchestrator.md 146ms (unchanged)
docs/contribute/development.md 189ms (unchanged)
docs/contribute/fakey.md 17ms (unchanged)
docs/contribute/index.md 7ms (unchanged)
docs/contribute/instruction-bundle-internals.md 26ms (unchanged)
docs/contribute/integration-apis.md 64ms (unchanged)
docs/contribute/llm-invocation.md 66ms (unchanged)
docs/contribute/mobile-gateway-api.md 42ms (unchanged)
docs/contribute/mobile-mvp-runbook.md 50ms (unchanged)
docs/contribute/monitor-completion.md 8ms (unchanged)
docs/contribute/perf-runbook.md 232ms (unchanged)
docs/contribute/plugin-api.md 63ms (unchanged)
docs/contribute/reader-testing.md 8ms (unchanged)
docs/contribute/release-safety.md 15ms (unchanged)
docs/contribute/release-train.md 25ms (unchanged)
docs/contribute/rust-backend.md 164ms (unchanged)
docs/contribute/sdd-storage.md 46ms (unchanged)
docs/contribute/telemetry.md 41ms (unchanged)
docs/contribute/tool-run-receipts.md 19ms (unchanged)
docs/contribute/tui-rendering.md 16ms (unchanged)
docs/contribute/vcs-provider-api.md 15ms (unchanged)
docs/contribute/workspace-provider.md 43ms (unchanged)
docs/contribute/writing-docs.md 25ms (unchanged)
docs/guides/add-existing-repository.md 6ms (unchanged)
docs/guides/choose-providers-models.md 8ms (unchanged)
docs/guides/configure-essentials.md 10ms (unchanged)
docs/guides/diagnose-with-doctor.md 6ms (unchanged)
docs/guides/find-and-replay-prompt.md 8ms (unchanged)
docs/guides/get-automated-code-review.md 10ms (unchanged)
docs/guides/hand-a-result-to-another-agent.md 7ms (unchanged)
docs/guides/index.md 9ms (unchanged)
docs/guides/plan-multi-agent-change.md 12ms (unchanged)
docs/guides/recover-interrupted-agent.md 8ms (unchanged)
docs/guides/reuse-prompt-with-macros.md 5ms (unchanged)
docs/guides/review-and-land-change.md 6ms (unchanged)
docs/guides/run-agents-in-parallel.md 6ms (unchanged)
docs/guides/schedule-recurring-work.md 9ms (unchanged)
docs/guides/setup-completion-editor.md 7ms (unchanged)
docs/guides/unstick-queued-agent.md 8ms (unchanged)
docs/images/blog/one_prompt_provider_clis.prompt.md 7ms (unchanged)
docs/images/blog/prompt_burrito.prompt.md 6ms (unchanged)
docs/images/blog/window_farm_vs_control_tower.prompt.md 8ms (unchanged)
docs/images/commit-workflow-infographic.critique.md 24ms (unchanged)
docs/images/commit-workflow-infographic.prompt.md 12ms (unchanged)
docs/images/infographic-style-brief.md 17ms (unchanged)
docs/images/macro-resolution-infographic.critique.md 12ms (unchanged)
docs/images/macro-resolution-infographic.prompt.md 18ms (unchanged)
docs/images/rust-backend-boundary-infographic.critique.md 42ms (unchanged)
docs/images/rust-backend-boundary-infographic.prompt.md 9ms (unchanged)
docs/images/sase_overview.critique.md 11ms (unchanged)
docs/images/sase_overview.prompt.md 10ms (unchanged)
docs/images/sase_tui_tabs_infographic.critique.md 49ms (unchanged)
docs/images/sase_tui_tabs_infographic.prompt.md 7ms (unchanged)
docs/images/sase-rust-core-integration.critique.md 39ms (unchanged)
docs/images/sase-rust-core-integration.prompt.md 5ms (unchanged)
docs/images/sase-telegram-integration.critique.md 31ms (unchanged)
docs/images/sase-telegram-integration.prompt.md 10ms (unchanged)
docs/images/workflow-execution-infographic.critique.md 43ms (unchanged)
docs/images/workflow-execution-infographic.prompt.md 10ms (unchanged)
docs/images/zorg-zettel-vision-infographic.critique.md 39ms (unchanged)
docs/index.md 5ms (unchanged)
docs/init.md 5ms (unchanged)
docs/instruction_bundles.md 6ms (unchanged)
docs/llms.md 35ms (unchanged)
docs/macros.md 19ms (unchanged)
docs/mobile_gateway.md 4ms (unchanged)
docs/monitors.md 7ms (unchanged)
docs/notifications.md 10ms (unchanged)
docs/plugins.md 7ms (unchanged)
docs/reference/agent-attachments.md 87ms (unchanged)
docs/reference/agent-auto-restart.md 28ms (unchanged)
docs/reference/agent-revive-log.md 11ms (unchanged)
docs/reference/agents/agent-clans.md 37ms (unchanged)
docs/reference/agents/agent-holds.md 7ms (unchanged)
docs/reference/agents/agent-launches.md 14ms (unchanged)
docs/reference/agents/agent-sessions.md 44ms (unchanged)
docs/reference/agents/agent-tribes.md 34ms (unchanged)
docs/reference/agents/hood-sync.md 64ms (unchanged)
docs/reference/agents/index.md 6ms (unchanged)
docs/reference/agents/initialization.md 49ms (unchanged)
docs/reference/agents/machine-initialization.md 10ms (unchanged)
docs/reference/agents/memory-initialization.md 38ms (unchanged)
docs/reference/agents/output-variables.md 20ms (unchanged)
docs/reference/agents/service-host.md 39ms (unchanged)
docs/reference/agents/workspaces.md 57ms (unchanged)
docs/reference/artifact-links.md 38ms (unchanged)
docs/reference/artifact-references.md 49ms (unchanged)
docs/reference/automation/index.md 5ms (unchanged)
docs/reference/automation/mentors.md 31ms (unchanged)
docs/reference/automation/monitor-operations.md 34ms (unchanged)
docs/reference/automation/monitors.md 79ms (unchanged)
docs/reference/automation/notification-cli.md 35ms (unchanged)
docs/reference/automation/notification-gates.md 78ms (unchanged)
docs/reference/automation/notification-storage.md 7ms (unchanged)
docs/reference/automation/notification-tags.md 17ms (unchanged)
docs/reference/automation/notification-types.md 66ms (unchanged)
docs/reference/automation/notifications.md 84ms (unchanged)
docs/reference/automation/scheduler-configuration.md 13ms (unchanged)
docs/reference/automation/scheduler-default-routines.md 64ms (unchanged)
docs/reference/automation/scheduler-description-grammar.md 14ms (unchanged)
docs/reference/automation/scheduler-housekeeping.md 46ms (unchanged)
docs/reference/automation/scheduler-jobs.md 92ms (unchanged)
docs/reference/automation/scheduler.md 41ms (unchanged)
docs/reference/automation/sudo.md 46ms (unchanged)
docs/reference/automation/tools.md 88ms (unchanged)
docs/reference/cli-notes.md 16ms (unchanged)
docs/reference/config/ace-behavior.md 38ms (unchanged)
docs/reference/config/ace-keymap-configuration.md 9ms (unchanged)
docs/reference/config/ace-prompts.md 50ms (unchanged)
docs/reference/config/agents-and-runners.md 43ms (unchanged)
docs/reference/config/agents.md 23ms (unchanged)
docs/reference/config/artifacts.md 14ms (unchanged)
docs/reference/config/automation-behavior.md 29ms (unchanged)
docs/reference/config/automation.md 33ms (unchanged)
docs/reference/config/core-behavior.md 34ms (unchanged)
docs/reference/config/core.md 8ms (unchanged)
docs/reference/config/display-and-reading.md 8ms (unchanged)
docs/reference/config/feature-flags.md 23ms (unchanged)
docs/reference/config/files-and-merging.md 16ms (unchanged)
docs/reference/config/finalizers.md 20ms (unchanged)
docs/reference/config/index.md 36ms (unchanged)
docs/reference/config/integrations-behavior.md 10ms (unchanged)
docs/reference/config/integrations.md 17ms (unchanged)
docs/reference/config/llm-provider-behavior.md 44ms (unchanged)
docs/reference/config/llm-provider.md 58ms (unchanged)
docs/reference/config/memory.md 7ms (unchanged)
docs/reference/config/monitor-behavior.md 5ms (unchanged)
docs/reference/config/needs-description.md 195ms (unchanged)
docs/reference/config/prompts-and-tools.md 39ms (unchanged)
docs/reference/config/prompts.md 34ms (unchanged)
docs/reference/config/repositories-behavior.md 43ms (unchanged)
docs/reference/config/repositories.md 110ms (unchanged)
docs/reference/config/runtime-and-storage.md 37ms (unchanged)
docs/reference/config/runtime.md 37ms (unchanged)
docs/reference/config/scheduler-behavior.md 32ms (unchanged)
docs/reference/config/scheduler.md 341ms (unchanged)
docs/reference/config/tui.md 284ms (unchanged)
docs/reference/config/workspace-behavior.md 6ms (unchanged)
docs/reference/content-layout.md 6ms (unchanged)
docs/reference/design-decisions.md 71ms (unchanged)
docs/reference/diagnostics.md 31ms (unchanged)
docs/reference/disk-cleanup.md 6ms (unchanged)
docs/reference/environment-variables.md 31ms (unchanged)
docs/reference/glossary.md 85ms (unchanged)
docs/reference/index.md 9ms (unchanged)
docs/reference/integrations/completion.md 41ms (unchanged)
docs/reference/integrations/editor.md 66ms (unchanged)
docs/reference/integrations/index.md 4ms (unchanged)
docs/reference/integrations/mobile-gateway.md 27ms (unchanged)
docs/reference/integrations/plugins-commands.md 16ms (unchanged)
docs/reference/integrations/plugins-update.md 41ms (unchanged)
docs/reference/integrations/plugins.md 30ms (unchanged)
docs/reference/integrations/remote-dispatch.md 39ms (unchanged)
docs/reference/memory/history.md 37ms (unchanged)
docs/reference/memory/index.md 3ms (unchanged)
docs/reference/memory/instruction-bundles.md 15ms (unchanged)
docs/reference/memory/memory.md 53ms (unchanged)
docs/reference/prompt-history.md 44ms (unchanged)
docs/reference/providers/agent-clis.md 73ms (unchanged)
docs/reference/providers/agy.md 13ms (unchanged)
docs/reference/providers/claude.md 25ms (unchanged)
docs/reference/providers/codex.md 21ms (unchanged)
docs/reference/providers/configuration.md 8ms (unchanged)
docs/reference/providers/grok.md 25ms (unchanged)
docs/reference/providers/index.md 5ms (unchanged)
docs/reference/providers/models.md 78ms (unchanged)
docs/reference/providers/muse.md 36ms (unchanged)
docs/reference/providers/opencode.md 6ms (unchanged)
docs/reference/providers/plugins.md 11ms (unchanged)
docs/reference/providers/qwen.md 7ms (unchanged)
docs/reference/providers/retry-and-fallback.md 29ms (unchanged)
docs/reference/providers/routing.md 45ms (unchanged)
docs/reference/providers/usage.md 37ms (unchanged)
docs/reference/query-language.md 38ms (unchanged)
docs/reference/runner-slots.md 45ms (unchanged)
docs/reference/upgrading/agents-sidecar.md 6ms (unchanged)
docs/reference/upgrading/automation.md 19ms (unchanged)
docs/reference/upgrading/configuration.md 12ms (unchanged)
docs/reference/upgrading/content-layout.md 11ms (unchanged)
docs/reference/upgrading/index.md 4ms (unchanged)
docs/reference/upgrading/local-state.md 20ms (unchanged)
docs/reference/upgrading/macros.md 17ms (unchanged)
docs/reference/upgrading/providers.md 10ms (unchanged)
docs/reference/upgrading/tui.md 16ms (unchanged)
docs/reference/upgrading/work-units.md 5ms (unchanged)
docs/reference/upgrading/workspaces.md 5ms (unchanged)
docs/reference/vcs/commit-workflows.md 27ms (unchanged)
docs/reference/vcs/index.md 4ms (unchanged)
docs/reference/vcs/providers.md 112ms (unchanged)
docs/reference/work-units/bead-artifacts.md 6ms (unchanged)
docs/reference/work-units/bead-attachments.md 49ms (unchanged)
docs/reference/work-units/bead-cli-inspection.md 58ms (unchanged)
docs/reference/work-units/bead-cli-query.md 49ms (unchanged)
docs/reference/work-units/bead-cli-records.md 54ms (unchanged)
docs/reference/work-units/bead-cli.md 51ms (unchanged)
docs/reference/work-units/bead-lifecycles.md 42ms (unchanged)
docs/reference/work-units/bead-mirroring.md 9ms (unchanged)
docs/reference/work-units/bead-pages.md 12ms (unchanged)
docs/reference/work-units/bead-storage.md 43ms (unchanged)
docs/reference/work-units/bead-triage.md 87ms (unchanged)
docs/reference/work-units/bead-tui.md 14ms (unchanged)
docs/reference/work-units/bead-work.md 57ms (unchanged)
docs/reference/work-units/beads.md 45ms (unchanged)
docs/reference/work-units/cli-workflows.md 31ms (unchanged)
docs/reference/work-units/goals.md 12ms (unchanged)
docs/reference/work-units/index.md 6ms (unchanged)
docs/reference/work-units/patches.md 36ms (unchanged)
docs/reference/work-units/plan-cli.md 28ms (unchanged)
docs/reference/work-units/plan-execution.md 8ms (unchanged)
docs/reference/work-units/plan-format.md 62ms (unchanged)
docs/reference/work-units/plans.md 74ms (unchanged)
docs/reference/work-units/project-spec.md 58ms (unchanged)
docs/reference/workflows.md 106ms (unchanged)
docs/rust_backend.md 9ms (unchanged)
docs/sdd.md 5ms (unchanged)
docs/start/first-change.md 5ms (unchanged)
docs/start/first-run.md 6ms (unchanged)
docs/start/index.md 5ms (unchanged)
docs/start/install.md 5ms (unchanged)
docs/tool.md 9ms (unchanged)
docs/vcs.md 22ms (unchanged)
docs/workspace.md 7ms (unchanged)
INSTALL.md 38ms (unchanged)
README.md 22ms (unchanged)
sase/memory/ace.md 6ms (unchanged)
sase/memory/cli_rules.md 5ms (unchanged)
sase/memory/decisions.md 23ms (unchanged)
sase/memory/decisions/adapters-normalize-harnesses.md 4ms (unchanged)
sase/memory/decisions/agents-sync-publish-only.md 8ms (unchanged)
sase/memory/decisions/check-full-is-explicit.md 6ms (unchanged)
sase/memory/decisions/ci-two-speed-split.md 6ms (unchanged)
sase/memory/decisions/corpus-before-mechanism.md 5ms (unchanged)
sase/memory/decisions/explicit-handoff-fails-closed.md 5ms (unchanged)
sase/memory/decisions/gates-never-block.md 6ms (unchanged)
sase/memory/decisions/global-install-is-human-only.md 5ms (unchanged)
sase/memory/decisions/goal-ledger.md 6ms (unchanged)
sase/memory/decisions/goals-host-binds.md 6ms (unchanged)
sase/memory/decisions/guarded-recipes.md 7ms (unchanged)
sase/memory/decisions/helpers-return-roots-declare.md 7ms (unchanged)
sase/memory/decisions/hold-pull-fail-open.md 7ms (unchanged)
sase/memory/decisions/host-owned-completion.md 5ms (unchanged)
sase/memory/decisions/instructions-per-invocation.md 11ms (unchanged)
sase/memory/decisions/machine-link-writes-off-primary.md 5ms (unchanged)
sase/memory/decisions/memory-links-are-authored.md 5ms (unchanged)
sase/memory/decisions/memory-webs.md 5ms (unchanged)
sase/memory/decisions/plugin-commands.md 5ms (unchanged)
sase/memory/decisions/project-labels-never-keys.md 5ms (unchanged)
sase/memory/decisions/readable-agents-md.md 6ms (unchanged)
sase/memory/decisions/receipts-prove-before-they-skip.md 5ms (unchanged)
sase/memory/decisions/record-before-admit.md 8ms (unchanged)
sase/memory/decisions/rust-core-required.md 4ms (unchanged)
sase/memory/decisions/single-turn-agents.md 4ms (unchanged)
sase/memory/decisions/size-alias-effort-ladder.md 6ms (unchanged)
sase/memory/decisions/triage-annotates-does-not-change-exit-codes.md 4ms (unchanged)
sase/memory/decisions/two-speed-verification.md 5ms (unchanged)
sase/memory/decisions/v1-import-retired.md 6ms (unchanged)
sase/memory/decisions/webs-render-in-their-own-section.md 6ms (unchanged)
sase/memory/demos.md 3ms (unchanged)
sase/memory/dispatch.md 8ms (unchanged)
sase/memory/docs_writing.md 4ms (unchanged)
sase/memory/generated_skills.md 9ms (unchanged)
sase/memory/glossary.md 6ms (unchanged)
sase/memory/glossary/agent-clan.md 3ms (unchanged)
sase/memory/glossary/agent-data-card-block.md 2ms (unchanged)
sase/memory/glossary/agent-data-card.md 3ms (unchanged)
sase/memory/glossary/agent-data-deck.md 3ms (unchanged)
sase/memory/glossary/agent-hood.md 2ms (unchanged)
sase/memory/glossary/agent-instruction-file.md 2ms (unchanged)
sase/memory/glossary/agent-neighbor.md 1ms (unchanged)
sase/memory/glossary/agent-node.md 1ms (unchanged)
sase/memory/glossary/agent-relation-jump-target.md 4ms (unchanged)
sase/memory/glossary/agent-tab.md 2ms (unchanged)
sase/memory/glossary/agent-tribe.md 2ms (unchanged)
sase/memory/glossary/agent-turn.md 1ms (unchanged)
sase/memory/glossary/artifact-markdown-file.md 3ms (unchanged)
sase/memory/glossary/artifact-reference.md 2ms (unchanged)
sase/memory/glossary/artifact.md 2ms (unchanged)
sase/memory/glossary/chop.md 2ms (unchanged)
sase/memory/glossary/clan-wave.md 2ms (unchanged)
sase/memory/glossary/core-memory.md 1ms (unchanged)
sase/memory/glossary/current-project.md 2ms (unchanged)
sase/memory/glossary/deck-panel.md 3ms (unchanged)
sase/memory/glossary/failure-signature.md 1ms (unchanged)
sase/memory/glossary/feature-flag.md 1ms (unchanged)
sase/memory/glossary/flag-bead.md 2ms (unchanged)
sase/memory/glossary/gate-turn.md 3ms (unchanged)
sase/memory/glossary/goal.md 3ms (unchanged)
sase/memory/glossary/instruction-bundle.md 2ms (unchanged)
sase/memory/glossary/instruction-manifest.md 2ms (unchanged)
sase/memory/glossary/llm-calls.md 2ms (unchanged)
sase/memory/glossary/lumberjack.md 1ms (unchanged)
sase/memory/glossary/machine-tab.md 2ms (unchanged)
sase/memory/glossary/macro-invocation.md 2ms (unchanged)
sase/memory/glossary/macro-memory.md 1ms (unchanged)
sase/memory/glossary/macro-part.md 1ms (unchanged)
sase/memory/glossary/macro-swarm.md 1ms (unchanged)
sase/memory/glossary/macro-workflow.md 1ms (unchanged)
sase/memory/glossary/macro.md 1ms (unchanged)
sase/memory/glossary/memory-strand.md 1ms (unchanged)
sase/memory/glossary/memory-web.md 2ms (unchanged)
sase/memory/glossary/named-proc.md 2ms (unchanged)
sase/memory/glossary/nav-item.md 2ms (unchanged)
sase/memory/glossary/nav-section.md 3ms (unchanged)
sase/memory/glossary/node-panel.md 2ms (unchanged)
sase/memory/glossary/oneshot-service-proc.md 2ms (unchanged)
sase/memory/glossary/patch.md 2ms (unchanged)
sase/memory/glossary/proc.md 2ms (unchanged)
sase/memory/glossary/project-tag.md 2ms (unchanged)
sase/memory/glossary/prompt-stash.md 3ms (unchanged)
sase/memory/glossary/raw-prompt.md 2ms (unchanged)
sase/memory/glossary/receipt.md 2ms (unchanged)
sase/memory/glossary/reference-memory.md 1ms (unchanged)
sase/memory/glossary/required-plugin.md 2ms (unchanged)
sase/memory/glossary/sase-agent-session.md 3ms (unchanged)
sase/memory/glossary/sase-agent.md 2ms (unchanged)
sase/memory/glossary/sase-gate.md 4ms (unchanged)
sase/memory/glossary/sase-monitor.md 3ms (unchanged)
sase/memory/glossary/sase-node.md 3ms (unchanged)
sase/memory/glossary/sase-project.md 3ms (unchanged)
sase/memory/glossary/sase-repo.md 2ms (unchanged)
sase/memory/glossary/sase-scheduler.md 2ms (unchanged)
sase/memory/glossary/sase-service.md 2ms (unchanged)
sase/memory/glossary/sase-turn.md 2ms (unchanged)
sase/memory/glossary/sase-workspace.md 2ms (unchanged)
sase/memory/glossary/service-proc.md 3ms (unchanged)
sase/memory/glossary/stash-trash.md 2ms (unchanged)
sase/memory/glossary/stitch.md 2ms (unchanged)
sase/memory/glossary/strand-keyword.md 2ms (unchanged)
sase/memory/glossary/task-type.md 2ms (unchanged)
sase/memory/glossary/tool-catalog.md 1ms (unchanged)
sase/memory/glossary/tool-run.md 3ms (unchanged)
sase/memory/glossary/triage-verdict.md 1ms (unchanged)
sase/memory/glossary/usage-window.md 2ms (unchanged)
sase/memory/gotchas.md 2ms (unchanged)
sase/memory/lint_and_test.md 17ms (unchanged)
sase/memory/macros.md 22ms (unchanged)
sase/memory/README.md 28ms (unchanged)
sase/memory/rust_core_backend_boundary.md 3ms (unchanged)
sase/memory/sase_artifacts.md 9ms (unchanged)
sase/memory/sase_beads.md 23ms (unchanged)
sase/memory/sase_flags.md 10ms (unchanged)
sase/memory/sase_sizes.md 6ms (unchanged)
sase/memory/sase.md 12ms (unchanged)
sase/memory/symvision.md 12ms (unchanged)
sase/memory/task_types.md 5ms (unchanged)
sase/memory/task_types/bug.md 7ms (unchanged)
sase/memory/task_types/ci.md 7ms (unchanged)
sase/memory/task_types/feature.md 7ms (unchanged)
sase/memory/task_types/flake.md 7ms (unchanged)
sase/memory/task_types/memory.md 7ms (unchanged)
sase/memory/tools.md 5ms (unchanged)
sase/memory/tui_perf.md 20ms (unchanged)
sase/memory/tui_screenshot.md 13ms (unchanged)
sase/memory/tui.md 2ms (unchanged)
sdd/history/instruction_inventory.md 11ms (unchanged)
smoke/pypi/README.md 6ms (unchanged)
src/sase/ace/tui/fonts/README.md 6ms (unchanged)
src/sase/amd/templates/AGENTS.minimal.template.md 1ms (unchanged)
src/sase/amd/templates/AGENTS.template.md 2ms (unchanged)
src/sase/llm_provider/templates/claude_helper_instructions.md 3ms (unchanged)
src/sase/macros/coder.md 2ms (unchanged)
src/sase/macros/fix_hook.md 4ms (unchanged)
src/sase/macros/skills/sase_agents_status.md 11ms (unchanged)
src/sase/macros/skills/sase_chats.md 15ms (unchanged)
src/sase/macros/skills/sase_final.md 28ms (unchanged)
src/sase/macros/skills/sase_gate.md 43ms (unchanged)
src/sase/macros/skills/sase_git_commit.md 20ms (unchanged)
src/sase/macros/skills/sase_handoff.md 10ms (unchanged)
src/sase/macros/skills/sase_memory_read.md 10ms (unchanged)
src/sase/macros/skills/sase_memory_write.md 15ms (unchanged)
src/sase/macros/skills/sase_monitor.md 33ms (unchanged)
src/sase/macros/skills/sase_new_task.md 16ms (unchanged)
src/sase/macros/skills/sase_notify.md 10ms (unchanged)
src/sase/macros/skills/sase_patches.md 17ms (unchanged)
src/sase/macros/skills/sase_plan.md 10ms (unchanged)
src/sase/macros/skills/sase_project.md 10ms (unchanged)
src/sase/macros/skills/sase_questions.md 8ms (unchanged)
src/sase/macros/skills/sase_repo.md 7ms (unchanged)
src/sase/macros/skills/sase_run.md 25ms (unchanged)
src/sase/macros/skills/sase_sudo.md 10ms (unchanged)
src/sase/macros/skills/sase_var.md 12ms (unchanged)
src/sase/macros/skills/SKILL.frame.template.md 1ms (unchanged)
src/sase/macros/split_file.md 3ms (unchanged)
src/sase/macros/summarize.md 2ms (unchanged)
src/sase/macros/t.md 2ms (unchanged)
src/sase/macros/tribe.md 2ms (unchanged)
src/sase/memory/assets/memory-directory-map.prompt.md 12ms (unchanged)
src/sase/sdd/assets/agents-directory-map.png.prompt.md 7ms (unchanged)
src/sase/sdd/assets/beads-directory-map.png.prompt.md 6ms (unchanged)
src/sase/sdd/assets/plans-directory-map.png.prompt.md 7ms (unchanged)
src/sase/sdd/assets/research-directory-map.png.prompt.md 5ms (unchanged)
tests/ace/tui/artifacts_contract/fixtures/notes/hello__a.md 2ms (unchanged)
tests/ace/tui/artifacts_contract/fixtures/notes/hello.md 2ms (unchanged)
tests/ace/tui/repro/README.md 4ms (unchanged)
tests/fixtures/agy/README.md 2ms (unchanged)
tests/fixtures/codex_stream/README.md 2ms (unchanged)
tests/fixtures/macro_named_input_types.md 3ms (unchanged)
tests/fixtures/qwen_stream/README.md 2ms (unchanged)
tests/perf/README.md 23ms (unchanged)
tests/plan_chain_golden/README.md 4ms (unchanged)

---------- Fixing keep-sorted blocks in YAML files... ----------
git ls-files -z '*.yml' '*.yaml' | xargs -0 -r sh -c 'for path do [ ! -e "$path" ] || printf "%s\0" "$path"; done' sh | xargs -0 -r .venv-format/bin/keep-sorted
.venv-format/bin/python tools/check_docs --fix
init memory: home memory refresh deferred until land (agent run); rerun `sase memory init` outside an agent after landing — home target: /home/bryan/.local/share/chezmoi/home/sase/memory/sase.md
init memory: initialized memory
  project memory target: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/sase/memory/sase.md
  global config source: /home/bryan/.local/share/chezmoi/home/dot_config/sase/sase.yml
Standard: tales approve + archive; epics launch; questions wait.
  plan: ✓ tale approved + archived · standard · gates.plan
  epic_plan: ✓ epic approved + launched · standard · gates.epic
  question: ✋ question waits for you · standard · gates.question
Covers host checkpoints only · the agent's shell is not restricted
Tale: tales approve + archive; epic plans wait; questions wait.
  plan: ✓ tale approved + archived · tale · gates.plan
  epic_plan: ✋ epic plan waits for you · tale · gates.epic
  question: ✋ question waits for you · tale · gates.question
Covers host checkpoints only · the agent's shell is not restricted
Epic: tale plans wait; epics launch; questions wait.
  plan: ✋ tale plan waits for you · epic · gates.plan
  epic_plan: ✓ epic approved + launched · epic · gates.epic
  question: ✋ question waits for you · epic · gates.question
Covers host checkpoints only · the agent's shell is not restricted
Autonomy profiles
  manual · tales ✋ · epics ✋ · questions ✋
  standard (default) · tales ✓ · epics ✓ · questions ✋
  tale · tales ✓ · epics ✋ · questions ✋
  epic · tales ✋ · epics ✓ · questions ✋
Roles
  epic_phase → standard (config) · set autonomy.roles.epic_phase
  epic_land → standard (config) · set autonomy.roles.epic_land
Covers host checkpoints only · the agent's shell is not restricted
sase tool run f828e8358ca62f99b9d51921556a45f2
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
[core-floor-probe] blocked_unpublished: sase-core-rs==0.42.3 is missing 1 capability(s), and at least one has no containing sase-core release tag yet.
[core-floor-probe] autonomy_effective_record: no introducing commit found in sase-core.
{"cache_hit": true, "capabilities": [{"commit": null, "name": "autonomy_effective_record", "release": null, "subject": null}], "declared_floor": "0.42.3", "exit_code": 4, "message": "sase-core-rs==0.42.3 is missing 1 capability(s), and at least one has no containing sase-core release tag yet.", "status": "blocked_unpublished"}
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
test selection escalated to the full suite (rules: core-identity-changed, src-data-asset); 5343 test files in scope
coverage contexts: not consulted — the run escalates to the full suite, so ground truth had nothing to add
escalating to the governed full test lane (rules: core-identity-changed, src-data-asset)
============================= test session starts ==============================
platform linux -- Python 3.14.7, pytest-9.1.1, pluggy-1.6.0
rootdir: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14
configfile: pyproject.toml
testpaths: tests
plugins: cov-7.1.0, mock-3.16.0, inline-snapshot-0.36.0, asyncio-1.4.0, hypothesis-6.168.5, xdist-3.8.0
asyncio: mode=Mode.AUTO, debug=False, asyncio_default_fixture_loop_scope=None, asyncio_default_test_loop_scope=function
created: 14/14 workers
14 workers [57297 items]

........................................................................ [  0%]
........................................................................ [  0%]
........................................................................ [  0%]
.............................s.......................................... [  0%]
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
..............s......................................................... [  7%]
........................................................................ [  7%]
........................................................................ [  7%]
........................................................................ [  7%]
........................................................................ [  7%]
........................................................................ [  8%]
........................................................................ [  8%]
........................................................................ [  8%]
........................................................................ [  8%]
........................................................................ [  8%]
...............s........................................................ [  8%]
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
....................................s................................... [ 12%]
........................................................................ [ 12%]
........................................................................ [ 13%]
........................................................................ [ 13%]
........................................................................ [ 13%]
........................................................................ [ 13%]
........................................................................ [ 13%]
...........................................s............................ [ 13%]
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
...................................F.................................... [ 35%]
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
.................s...................................................... [ 41%]
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
........................................................................ [ 48%]
........................................................................ [ 48%]
.................................................................s...... [ 48%]
...................................................................s.s.. [ 48%]
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
........................................................................ [ 50%]
........................................................................ [ 51%]
........................................................................ [ 51%]
........................................................s............... [ 51%]
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
..............................ssss...................................... [ 63%]
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
...........................................s............................ [ 73%]
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
...F.................................................................... [ 80%]
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
..........s............................................................. [ 84%]
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
...................................F.................................... [ 88%]
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
.........................................................                [100%]

═══════════════════════════════ inline-snapshot ════════════════════════════════
INFO: inline-snapshot was disabled because you used xdist. This means that tests
with snapshots will continue to run, but snapshot(x) will only return x and 
inline-snapshot will not be able to fix snapshots or generate reports.


=================================== FAILURES ===================================
__ test_interruption_kills_process_group_with_pipe_holding_descendant[False] ___
[gw8] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/.venv/bin/python

tmp_path = PosixPath('/var/tmp/sase-d00a07ab/pytest-of-bryan/pytest-0/popen-gw8/test_interruption_kills_proces0')
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7fefd96e27b0>
external_drain_alarm = False

    @pytest.mark.skipif(os.name != "posix", reason="process group cleanup requires POSIX")
    @pytest.mark.parametrize("external_drain_alarm", [False, True])
    def test_interruption_kills_process_group_with_pipe_holding_descendant(
        tmp_path: Path,
        monkeypatch: pytest.MonkeyPatch,
        external_drain_alarm: bool,
    ) -> None:
        command, pid_file = _descendant_pipe_command(tmp_path)
        monkeypatch.setenv("SASE_SDD_GIT_NETWORK_TRANSFER_CEILING", "5")
        monkeypatch.setattr("sase.sdd._git_runner.sdd_git_command", lambda _args: command)
    
        def run_transfer() -> None:
            run_sdd_git(
                ["fetch", "origin"],
                cwd=tmp_path,
                op="test.fetch_with_descendant",
                timeout=0.05 if not external_drain_alarm else 5.0,
                check=True,
                capture_output=True,
                text=True,
            )
    
        try:
            started = time.monotonic()
            if external_drain_alarm:
                with pytest.raises(PublicationDrainTimedOut):
                    with publication_drain._bounded_publication_drain(0.5):
                        run_transfer()
            else:
                with pytest.raises(SddGitCommandTimeout):
                    run_transfer()
>           descendant_pid = int(pid_file.read_text())
                                 ^^^^^^^^^^^^^^^^^^^^

tests/sdd_store/test_sdd_git_streaming.py:190: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
../../../../../../share/uv/python/cpython-3.14.7-linux-x86_64-gnu/lib/python3.14/pathlib/__init__.py:787: in read_text
    with self.open(mode='r', encoding=encoding, errors=errors, newline=newline) as f:
         ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

self = PosixPath('/var/tmp/sase-d00a07ab/pytest-of-bryan/pytest-0/popen-gw8/test_interruption_kills_proces0/descendant.pid')
mode = 'r', buffering = -1, encoding = 'locale', errors = None, newline = None

    def open(self, mode='r', buffering=-1, encoding=None,
             errors=None, newline=None):
        """
        Open the file pointed to by this path and return a file object, as
        the built-in open() function does.
        """
        if "b" not in mode:
            encoding = io.text_encoding(encoding)
>       return io.open(self, mode, buffering, encoding, errors, newline)
               ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
E       FileNotFoundError: [Errno 2] No such file or directory: '/var/tmp/sase-d00a07ab/pytest-of-bryan/pytest-0/popen-gw8/test_interruption_kills_proces0/descendant.pid'

../../../../../../share/uv/python/cpython-3.14.7-linux-x86_64-gnu/lib/python3.14/pathlib/__init__.py:771: FileNotFoundError
_____________________ test_empty_adapter_capabilities_ask ______________________
[gw10] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/.venv/bin/python

tmp_path = PosixPath('/var/tmp/sase-d00a07ab/pytest-of-bryan/pytest-0/popen-gw10/test_empty_adapter_capabilitie0')
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7fdd7bcd7e70>

    def test_empty_adapter_capabilities_ask(tmp_path: Path, monkeypatch) -> None:
        """A question adapter with no capabilities always asks."""
        from dataclasses import replace as _replace
    
        from sase.notification_gates.registry import adapter_for_kind
        from sase.notification_gates.service_evaluation import _evaluate_gate_request
        from sase.user_question_actions import user_question_gate_spec
    
        harness.isolated_gate_dirs(monkeypatch, tmp_path)
        _, _, parent_dir = harness.launch_meta("%auto\nDo the work", tmp_path)
        monkeypatch.setenv("SASE_ARTIFACTS_DIR", str(parent_dir))
        spec_dict = user_question_gate_spec(
            [dict(q) for q in harness.QUESTIONS],
            session_id="empty-cap",
            producer={"agent": "contract-agent"},
            auto=True,
        )
        from sase.notification_gates.models import GateSpec
    
        spec = GateSpec.from_mapping(spec_dict)
        adapter = adapter_for_kind("question")
        adapter = _replace(adapter, auto_capabilities=frozenset())
        _, decision, _ = _evaluate_gate_request(spec, adapter, request_id="empty-cap")
        assert decision["outcome"] == "ask"
>       assert decision["rule"] == "not_capable"
E       AssertionError: assert 'gates.question' == 'not_capable'
E         
E         - not_capable
E         + gates.question

tests/autonomy_contract/test_landing_gaps_gates.py:83: AssertionError
________________ test_tui_app_import_stays_under_startup_budget ________________
[gw0] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/.venv/bin/python

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
E       AssertionError: TUI app import loads 3536 modules against the 3527 cap; attribute the growth with `tools/tui_import_closure --diff $(git merge-base HEAD origin/master)` and defer the new edges
E       assert 3536 < 3527

tests/ace/tui/test_app_import_budget.py:96: AssertionError
=============================== warnings summary ===============================
.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:885: 14 warnings
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:885: PytestAssertRewriteWarning: Module already imported so cannot be rewritten; tests.ace.tui.command_line._completion_sources_shared
    self.import_plugin(import_spec)

.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:885: 14 warnings
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:885: PytestAssertRewriteWarning: Module already imported so cannot be rewritten; tests.ace.tui._bench_tui_jk_helpers
    self.import_plugin(import_spec)

.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:885: 14 warnings
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:885: PytestAssertRewriteWarning: Module already imported so cannot be rewritten; tests.monitor._no_new_receipt
    self.import_plugin(import_spec)

.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:885: 14 warnings
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:885: PytestAssertRewriteWarning: Module already imported so cannot be rewritten; tests._axe_lumberjack_fixtures
    self.import_plugin(import_spec)

tests/test_macro_processor_workflow_execute.py::test_execute_workflow_flatten_preserves_caller_named_args
tests/test_macro_processor_workflow_execute.py::test_execute_workflow_flatten_explicit_named_args_override_caller
tests/test_macro_processor_workflow_execute.py::test_execute_workflow_flatten_preserves_wrapper_model_override
tests/test_macro_processor_workflow_execute.py::test_execute_workflow_passes_inherited_vcs_tag_without_context_leak
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/src/sase/macro/workflow_runner.py:474: UserWarning: Standalone workflow '#split' is deprecated; use '#!split' instead.
    flattened = _flatten_anonymous_workflow(workflow, project=project)

tests/test_macro_processor_workflow_flatten.py::test_flatten_anonymous_workflow_returns_workflow_for_pure_multistep
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/tests/test_macro_processor_workflow_flatten.py:114: UserWarning: Standalone workflow '#split' is deprecated; use '#!split' instead.
    result = _flatten_anonymous_workflow(workflow)

tests/test_macro_processor_workflow_flatten.py::test_flatten_anonymous_workflow_slow_path_with_macro_and_workflow
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/src/sase/macro/workflow_runner.py:297: UserWarning: Standalone workflow '#batch_split' is deprecated; use '#!batch_split' instead.
    standalone = _find_standalone_workflow_ref(prompt_text, prompts)

tests/test_macro_processor_workflow_flatten.py::test_flatten_anonymous_workflow_slow_path_with_args
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/src/sase/macro/workflow_runner.py:297: UserWarning: Standalone workflow '#deploy' is deprecated; use '#!deploy' instead.
    standalone = _find_standalone_workflow_ref(prompt_text, prompts)

tests/test_macro_processor_workflow_flatten.py::test_flatten_anonymous_workflow_preserves_wrapper_model_directive
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/tests/test_macro_processor_workflow_flatten.py:421: UserWarning: Standalone workflow '#split' is deprecated; use '#!split' instead.
    result = _flatten_anonymous_workflow(workflow)

tests/ace/tui/test_agent_archive_controller_lookup.py::test_coalesced_idle_does_not_publish_false_missing_for_queued_open
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/.venv/lib/python3.14/site-packages/_pytest/nodes.py:336: RuntimeWarning: coroutine '_run_archive_request' was never awaited
    return (x[1] for x in self.iter_markers_with_node(name=name))
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/ace/tui/test_agent_archive_detail_ownership.py::test_inbox_debounced_update_repaints_after_archive_round_trip
  /home/bryan/.local/share/uv/python/cpython-3.14.7-linux-x86_64-gnu/lib/python3.14/typing.py:1725: RuntimeWarning: coroutine '_run_archive_request' was never awaited
    return ((p, type(p)) for p in parameters)
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/ace/tui/test_launchable_mru.py::test_launch_marks_pending_synchronously
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/src/sase/ace/tui/actions/agent_workflow/_launch_submit_helpers.py:132: RuntimeWarning: coroutine 'schedule_submit_time_vcs_replay.<locals>.record_off_thread' was never awaited
    task = spawn_pump_free_task(
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/sdd/test_artifact_link_event_acceptance_process_death.py::test_real_killed_publisher_process_leaves_no_corrupt_object_and_recovers
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/tests/sdd/test_artifact_link_event_acceptance_process_death.py:57: DeprecationWarning: This process (pid=313278) is multi-threaded, use of fork() may lead to deadlocks in the child.
    child = os.fork()

tests/test_procs_supervisor.py::test_starter_exit_does_not_kill_a_released_proc
  <frozen os>:898: DeprecationWarning: This process (pid=313288) is multi-threaded, use of fork() may lead to deadlocks in the child.

tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorContinuation::test_prepends_nudge_on_retry
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorContinuation::test_prepends_nudge_on_retry changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorContinuation::test_does_not_double_prepend_on_repeated_retries
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorContinuation::test_does_not_double_prepend_on_repeated_retries changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorContinuation::test_prepends_nudge_on_zero_wait_retry
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorContinuation::test_prepends_nudge_on_zero_wait_retry changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorNoNudge::test_no_nudge_leaves_prompt_untouched
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorNoNudge::test_no_nudge_leaves_prompt_untouched changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorCodexDefaults::test_codex_transient_default_retries_with_preserved_workspace
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorCodexDefaults::test_codex_transient_default_retries_with_preserved_workspace changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorPostPhaseTransition::test_retry_fires_for_coder_after_plan_approval
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorPostPhaseTransition::test_retry_fires_for_coder_after_plan_approval changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry_usage_limits.py::TestHandleWorkflowErrorUsageLimitPrecedence::test_transient_429_not_a_usage_limit_match_still_retries
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_exec_retry_usage_limits.py::TestHandleWorkflowErrorUsageLimitPrecedence::test_transient_429_not_a_usage_limit_match_still_retries changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry_usage_limits.py::TestHandleWorkflowErrorUsageLimitPrecedence::test_fallback_allowed_to_different_non_disabled_provider
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_exec_retry_usage_limits.py::TestHandleWorkflowErrorUsageLimitPrecedence::test_fallback_allowed_to_different_non_disabled_provider changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry_usage_limits.py::TestHandleWorkflowErrorUsageLimitPrecedence::test_fallback_allowed_when_fallback_provider_carries_soft_disable
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_exec_retry_usage_limits.py::TestHandleWorkflowErrorUsageLimitPrecedence::test_fallback_allowed_when_fallback_provider_carries_soft_disable changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry_usage_limits.py::TestHandleWorkflowErrorUsageLimitPrecedence::test_known_codex_attempt_does_not_scan_quoted_claude_limit_prose
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_exec_retry_usage_limits.py::TestHandleWorkflowErrorUsageLimitPrecedence::test_known_codex_attempt_does_not_scan_quoted_claude_limit_prose changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry_workspace.py::TestHandleWorkflowErrorPreserveWorkspace::test_preserve_workspace_skips_prepare_on_retry
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_exec_retry_workspace.py::TestHandleWorkflowErrorPreserveWorkspace::test_preserve_workspace_skips_prepare_on_retry changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry_workspace.py::TestHandleWorkflowErrorPreserveWorkspace::test_preserve_workspace_skips_prepare_on_fallback
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_exec_retry_workspace.py::TestHandleWorkflowErrorPreserveWorkspace::test_preserve_workspace_skips_prepare_on_fallback changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry_workspace.py::TestHandleWorkflowErrorPreserveWorkspace::test_default_preserve_workspace_false_still_calls_prepare
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_exec_retry_workspace.py::TestHandleWorkflowErrorPreserveWorkspace::test_default_preserve_workspace_false_still_calls_prepare changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_failed_fork_admission.py::TestFailedForkParentAdmission::test_runner_admits_and_claims_real_workspace_for_failed_fork_parent
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_failed_fork_admission.py::TestFailedForkParentAdmission::test_runner_admits_and_claims_real_workspace_for_failed_fork_parent changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_runner_slot_only_deferred_wait_gates_then_claims_workspace[wait_info0-0-None]
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_runner_slot_only_deferred_wait_gates_then_claims_workspace[wait_info0-0-None] changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_runner_slot_only_deferred_wait_gates_then_claims_workspace[wait_info1-None-20]
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_runner_slot_only_deferred_wait_gates_then_claims_workspace[wait_info1-None-20] changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_deferred_wait_gates_before_claim_and_prepares_claimed_workspace[None]
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_deferred_wait_gates_before_claim_and_prepares_claimed_workspace[None] changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_deferred_wait_gates_before_claim_and_prepares_claimed_workspace[hostile ambient value]
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_deferred_wait_gates_before_claim_and_prepares_claimed_workspace[hostile ambient value] changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_incomplete_clan_fork_expands_after_wait_before_slot_and_claim
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_incomplete_clan_fork_expands_after_wait_before_slot_and_claim changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_combined_wait_runs_dependencies_then_gate_then_claim
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_combined_wait_runs_dependencies_then_gate_then_claim changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_home_mode_deferred_wait_keeps_directory_workspace
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_home_mode_deferred_wait_keeps_directory_workspace changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_outcomes.py::TestDeferredWorkspaceOutcomes::test_repeat_stop_exits_before_workspace_claim_and_run_loop
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_outcomes.py::TestDeferredWorkspaceOutcomes::test_repeat_stop_exits_before_workspace_claim_and_run_loop changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_outcomes.py::TestDeferredWorkspaceOutcomes::test_deferred_workspace_without_extracted_wait_still_claims_real_workspace
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_outcomes.py::TestDeferredWorkspaceOutcomes::test_deferred_workspace_without_extracted_wait_still_claims_real_workspace changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_outcomes.py::TestDeferredWorkspaceOutcomes::test_bead_claim_failure_writes_error_and_skips_model_execution
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_outcomes.py::TestDeferredWorkspaceOutcomes::test_bead_claim_failure_writes_error_and_skips_model_execution changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_outcomes.py::TestDeferredWorkspaceOutcomes::test_bead_environment_mismatch_writes_error_and_skips_model_execution
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_outcomes.py::TestDeferredWorkspaceOutcomes::test_bead_environment_mismatch_writes_error_and_skips_model_execution changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_outcomes.py::TestDeferredWorkspaceOutcomes::test_launch_without_bead_never_invokes_claim_helper
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_outcomes.py::TestDeferredWorkspaceOutcomes::test_launch_without_bead_never_invokes_claim_helper changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_no_retry_when_config_is_none
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_no_retry_when_config_is_none changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_non_retryable_error_raises_immediately
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_non_retryable_error_raises_immediately changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_retry_on_retryable_error
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_retry_on_retryable_error changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_retry_state_written_during_wait
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_retry_state_written_during_wait changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_retry_state_deleted_on_completion
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_retry_state_deleted_on_completion changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_fallback_model_tried_after_max_retries
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_fallback_model_tried_after_max_retries changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_was_killed_during_wait_aborts_retry
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_was_killed_during_wait_aborts_retry changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_done_json_includes_retry_metadata
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_done_json_includes_retry_metadata changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_no_retry_metadata_when_no_retries
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_no_retry_metadata_when_no_retries changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_cross_provider_retry_uses_fallback_config
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_cross_provider_retry_uses_fallback_config changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_agent_is_admitted_before_workspace_preparation
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_agent_is_admitted_before_workspace_preparation changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_admitted_root_is_counted_when_workspace_preparation_fails
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_admitted_root_is_counted_when_workspace_preparation_fails changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_no_wait_runner_records_run_started_at_before_execution
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_no_wait_runner_records_run_started_at_before_execution changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_runner_persists_sdd_base_sha_before_execution
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_runner_persists_sdd_base_sha_before_execution changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_runner_populates_multi_agent_prompt_file_from_env
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_runner_populates_multi_agent_prompt_file_from_env changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_error_after_slot_admission_records_run_started_at
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_error_after_slot_admission_records_run_started_at changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_linked_repo_prep_failure_stops_before_execution
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_linked_repo_prep_failure_stops_before_execution changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_killed_while_waiting_does_not_record_run_started_at
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_killed_while_waiting_does_not_record_run_started_at changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_runner_passes_recorded_run_started_at_to_runtime_formatter
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_runner_passes_recorded_run_started_at_to_runtime_formatter changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_system_exit_from_execution_writes_failure_marker_and_notifies
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_system_exit_from_execution_writes_failure_marker_and_notifies changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_home_mode_running_marker_cleanup_updates_artifact_index
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_home_mode_running_marker_cleanup_updates_artifact_index changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14' to '<deleted>'; restored it.
    next(it)

tests/test_axe_runner_workspace_reclone.py::TestRecreateEndToEnd::test_forced_verify_failure_recreates_then_launch_prep_succeeds
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_runner_workspace_reclone.py::TestRecreateEndToEnd::test_forced_verify_failure_recreates_then_launch_prep_succeeds changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14' to '<deleted>'; restored it.
    next(it)

tests/ace/tui/command_line/test_completion_fixes.py::test_cursor_move_during_a_fetch_drops_the_result
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/src/sase/legacy_xprompt_syntax.py:94: RuntimeWarning: coroutine '_record_history_async.<locals>._record' was never awaited
    result = binding(
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/test_notification_modal_tab_order.py::test_on_mount_highlights_first_visible_row_when_initial_is_hidden
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/src/sase/ace/tui/modals/notification_modal_snooze_status.py:136: RuntimeWarning: coroutine 'Timer._run_timer' was never awaited
    self._snooze_status_timer = None
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/ace/tui/command_line/test_panel_shell_pilot.py::test_grammar_ready_refreshes_open_empty_panel_without_a_keystroke
  /home/bryan/.local/share/uv/python/cpython-3.14.7-linux-x86_64-gnu/lib/python3.14/copy.py:228: RuntimeWarning: coroutine '_recheck_grammar_key' was never awaited
    def _reconstruct(x, memo, func, args,
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/ace/tui/command_line/test_panel_shell_pilot.py::test_real_input_history_filters_prefix_and_resets_new_walk
  /home/bryan/.local/share/uv/python/cpython-3.14.7-linux-x86_64-gnu/lib/python3.14/copy.py:233: RuntimeWarning: coroutine '_record_history_async.<locals>._record' was never awaited
    args = (deepcopy(arg, memo) for arg in args)
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/ace/tui/command_line/test_panel_shell_submit.py::test_tail_polling_never_touches_message_pump
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/tests/ace/tui/command_line/test_panel_shell_submit.py:175: DeprecationWarning: 'asyncio.iscoroutinefunction' is deprecated and slated for removal in Python 3.16; use inspect.iscoroutinefunction() instead
    assert asyncio.iscoroutinefunction(CommandLineTranscript._tail_loop)

tests/ace/tui/command_line/test_run_policies.py::test_foreground_submit_runs_in_terminal_and_records
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/.venv/lib/python3.14/site-packages/textual/cache.py:226: RuntimeWarning: coroutine 'CommandLineScreenSubmissionMixin._record_local_history.<locals>._record' was never awaited
    def __init__(self, maxsize: int) -> None:
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/ace/tui/command_line/test_transcript_blocks_actions.py::test_v_opens_pager_for_selected_block
  /home/bryan/.local/share/uv/python/cpython-3.14.7-linux-x86_64-gnu/lib/python3.14/copy.py:110: RuntimeWarning: coroutine 'CommandLineScreenSubmissionMixin._submit_worker' was never awaited
    def deepcopy(x, memo=None, _nil=[]):
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/ace/tui/command_line/test_transcript_blocks_actions.py::test_p_opens_procs_with_focus_target
  /home/bryan/.local/share/uv/python/cpython-3.14.7-linux-x86_64-gnu/lib/python3.14/json/decoder.py:361: RuntimeWarning: coroutine 'CommandLineScreen._load_tail_worker' was never awaited
    obj, end = self.scan_once(s, idx)
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/test_run_agent_runner_clan_summary_refresh.py::test_successful_post_preparation_summary_survives_later_metadata_write
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_run_agent_runner_clan_summary_refresh.py::test_successful_post_preparation_summary_survives_later_metadata_write changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14' to '<deleted>'; restored it.
    next(it)

tests/test_run_agent_runner_clan_summary_refresh.py::test_unsuccessful_post_preparation_summary_keeps_earlier_success
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_run_agent_runner_clan_summary_refresh.py::test_unsuccessful_post_preparation_summary_keeps_earlier_success changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14' to '<deleted>'; restored it.
    next(it)

tests/ace/tui/command_line/test_transcript_scroll.py::test_panel_opens_anchored_at_bottom
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/src/sase/main/parser_gettext.py:54: RuntimeWarning: coroutine 'CommandLineScreenSubmissionMixin._submit_worker' was never awaited
    tuple(os.environ.get(key) for key in _GETTEXT_ENV_KEYS)
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/history/test_continuation_replay_hydration_retry.py::test_retry_then_fork_replay_end_to_end
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/history/test_continuation_replay_hydration_retry.py::test_retry_then_fork_replay_end_to_end changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14' to '<deleted>'; restored it.
    next(it)

tests/ace/tui/test_agent_archive_column_actions_interaction.py::test_J_and_K_switch_pulse_and_list_focus_without_moving_the_inbox
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/tests/ace/tui/_agent_archive_column_helpers.py:78: RuntimeWarning: coroutine 'AgentMetadataPagerMixin._open_agent_metadata_pager' was never awaited
    by_container.setdefault(row["container_key"], []).append(row)
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/ace/tui/test_agent_archive_column_actions_interaction.py::test_cursor_survives_a_rebuild_and_falls_to_a_neighbor_when_row_vanishes
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/tests/ace/tui/_agent_archive_column_helpers.py:78: RuntimeWarning: coroutine 'open_archive_chooser.<locals>._hydrate_and_present' was never awaited
    by_container.setdefault(row["container_key"], []).append(row)
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/axe/test_run_agent_exec_attempts_integration.py::test_retry_branch_snapshots_failed_attempt
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/axe/test_run_agent_exec_attempts_integration.py::test_retry_branch_snapshots_failed_attempt changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14' to '<deleted>'; restored it.
    next(it)

tests/axe/test_run_agent_exec_attempts_integration.py::test_retry_branch_releases_attempt_continuation_pointers
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/axe/test_run_agent_exec_attempts_integration.py::test_retry_branch_releases_attempt_continuation_pointers changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14' to '<deleted>'; restored it.
    next(it)

tests/axe/test_run_agent_exec_attempts_integration.py::test_fallback_branch_releases_attempt_continuation_pointers
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/axe/test_run_agent_exec_attempts_integration.py::test_fallback_branch_releases_attempt_continuation_pointers changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14' to '<deleted>'; restored it.
    next(it)

tests/axe/test_run_agent_exec_attempts_integration.py::test_fallback_branch_snapshots_with_primary_model_marker
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/axe/test_run_agent_exec_attempts_integration.py::test_fallback_branch_snapshots_with_primary_model_marker changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14' to '<deleted>'; restored it.
    next(it)

tests/completion/test_zsh_smoke.py: 18 warnings
  /home/bryan/.local/share/uv/python/cpython-3.14.7-linux-x86_64-gnu/lib/python3.14/pty.py:66: DeprecationWarning: This process (pid=313285) is multi-threaded, use of forkpty() may lead to deadlocks in the child.
    pid, fd = os.forkpty()

tests/ace/tui/test_dismissed_index_startup_sync.py::test_start_post_mount_background_loads_schedules_dismissed_sync_once
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/src/sase/ace/tui/actions/_launchable_mru.py:304: RuntimeWarning: coroutine 'Timer._run_timer' was never awaited
    log.debug("Launchable MRU tick not armed", exc_info=True)
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

-- Docs: https://docs.pytest.org/en/stable/how-to/capture-warnings.html
============================= slowest 20 durations =============================
64.47s call     tests/fakey/test_monitor_capacity_e2e.py::test_weight_two_land_agent_session_retains_one_claim_through_real_dispatch_and_delayed_child_bootstrap
62.28s call     tests/test_contract_manifest.py::test_contract_manifest_matches_marker_selection
53.22s call     tests/test_check_feature_flags_tool_run.py::test_main_static_on_repo_exits_zero
53.20s call     tests/test_check_feature_flags_tool_run.py::test_static_main_ignores_exploding_bd_command
47.47s call     tests/history/test_continuation_replay_hydration_basic.py::test_hundred_handoff_from_final_monitor_result_grows_linearly
30.27s call     tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_lowercase_picks_this_panel_capital_picks_other
29.33s call     tests/test_agent_artifact_directory_operation_audit.py::test_artifact_directory_operation_sites_are_reviewed
27.42s call     tests/pager/test_rendered_link_contract.py::test_kitchen_follow_copy_edit_and_media_for_each_supported_action
21.32s call     tests/test_project_display_presentation_audit.py::test_project_display_name_fallback_lives_only_in_chokepoint
20.44s call     tests/test_project_display_presentation_audit.py::test_display_fallback_exemptions_name_existing_sites_and_rationales
20.25s call     tests/test_bead/test_sync_remote_worker.py::test_managed_sync_worker_converges_sidecar_store_mutations
18.07s call     tests/ace/tui/test_deleted_proc_queue_imports.py::test_tests_do_not_import_deleted_proc_queue_module
15.93s call     tests/test_bare_git_init.py::TestInitBareGitProject::test_git_runner_removes_persistent_index_lock_after_retries
15.43s call     tests/tool/test_inline_escalation.py::test_slow_command_escalates_and_wait_returns_exit
15.40s call     tests/test_sdd_commit.py::test_commit_sdd_files_removes_persistent_index_lock_after_retry_exhausted
14.83s call     tests/ace/tui/test_artifacts_scaffold.py::test_number_keys_jump_artifacts_without_entering_from_other_tabs
13.85s call     tests/test_launcher_origin.py::test_every_launcher_call_passes_origin_explicitly
13.82s call     tests/ace/tui/test_agents_filter_bar_session.py::test_circumflex_history_replaces_the_live_edit_while_the_bar_is_open
12.39s call     tests/test_markdown_print_width.py::test_no_function_parameter_defaults_to_the_width
12.36s call     tests/workspace_provider/test_primary_writable_store_import_boundary.py::test_writable_store_resolution_importers_match_the_audited_allowlist
=========================== short test summary info ============================
FAILED tests/sdd_store/test_sdd_git_streaming.py::test_interruption_kills_process_group_with_pipe_holding_descendant[False]
FAILED tests/autonomy_contract/test_landing_gaps_gates.py::test_empty_adapter_capabilities_ask
FAILED tests/ace/tui/test_app_import_budget.py::test_tui_app_import_stays_under_startup_budget
==== 3 failed, 57278 passed, 17 skipped, 154 warnings in 786.18s (0:13:06) =====
error: recipe `test-scoped` failed on line 598 with exit code 1
error: recipe `check` failed on line 864 with exit code 1
failed  exit=1  duration=1133707ms
unattrib  7.4s
triage test (scoped): 2 KNOWN 1 NEW stopped
NEW test (scoped): FAILED tests/autonomy_contract/test_landing_gaps_gates.py::test_empty_adapter_capabilities_ask — recorded evidence; no owner
KNOWN test (scoped): FAILED tests/sdd_store/test_sdd_git_streaming.py::test_interruption_kills_process_group_with_pipe_holding_descendant[False] — witness 7c593d9817d9b64ace4c93325b5b44b2; no owner
KNOWN test (scoped): FAILED tests/ace/tui/test_app_import_budget.py::test_tui_app_import_stays_under_startup_budget — witness 0565caed0d1ee997557a16ec01dc1ecb; no owner
verdict: new_failures — 1 NEW, 2 KNOWN; exit 1
failed  exit=1  duration=2542061ms

