# Chat History - ace-run (0nd--mon-0)

- **TIMESTAMP:** 2026-09-18 22:02:51 EDT
- **MODEL:** grok/grok-4.6
- **AGENT:** 0nd--mon-0

## Prompt

sase monitor start --command 'just check' --reason 'Re-verify builtin model alias defaults after just check failures'

## Response

[setup] fast-forwarded /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/sase/repos/linked/sase-core to origin/master
[validate_sase_core_rs] installed sase-core-rs distribution version 0.34.58 disagrees with the /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/sase/repos/linked/sase-core/Cargo.toml checkout version 0.34.59; the checkout moved and the extension was not rebuilt. Run `just install`.
[setup] Rebuilding stale or missing sase_core_rs from /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/sase/repos/linked/sase-core before Python dependency resolution.
# Harden cargo crate downloads against transient crates.io flakiness.
# CI has hit `curl ... [16] Error in the HTTP2 framing layer` while
# maturin's `cargo metadata` fetches deps; disabling HTTP/2 multiplexing
# and raising the retry count makes the download resilient. Both are
# overridable from the environment.
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
   Compiling itoa v1.0.18
   Compiling pin-project-lite v0.2.17
   Compiling bytes v1.11.1
   Compiling shlex v1.3.0
   Compiling find-msvc-tools v0.1.9
   Compiling once_cell v1.21.4
   Compiling futures-core v0.3.32
   Compiling stable_deref_trait v1.2.1
   Compiling target-lexicon v0.12.16
   Compiling version_check v0.9.5
   Compiling autocfg v1.5.0
   Compiling log v0.4.29
   Compiling serde_core v1.0.228
   Compiling zerocopy v0.8.48
   Compiling hashbrown v0.17.0
   Compiling equivalent v1.0.2
   Compiling smallvec v1.15.1
   Compiling slab v0.4.12
   Compiling writeable v0.6.3
   Compiling memchr v2.8.0
   Compiling untrusted v0.9.0
   Compiling httparse v1.10.1
   Compiling futures-task v0.3.32
   Compiling litemap v0.8.2
   Compiling serde v1.0.228
   Compiling tower-service v0.3.3
   Compiling icu_normalizer_data v2.2.0
   Compiling zmij v1.0.21
   Compiling icu_properties_data v2.2.0
   Compiling utf8_iter v1.0.4
   Compiling typenum v1.20.0
   Compiling serde_json v1.0.149
   Compiling httpdate v1.0.3
   Compiling fnv v1.0.7
   Compiling pkg-config v0.3.33
   Compiling futures-sink v0.3.32
   Compiling vcpkg v0.2.15
   Compiling percent-encoding v2.3.2
   Compiling bitflags v2.11.1
   Compiling ryu v1.0.23
   Compiling rustls v0.21.12
   Compiling getrandom v0.4.2
   Compiling powerfmt v0.2.0
   Compiling rustix v1.1.4
   Compiling try-lock v0.2.5
   Compiling tower-layer v0.3.3
   Compiling rustversion v1.0.22
   Compiling num-conv v0.2.1
   Compiling thiserror v2.0.18
   Compiling time-core v0.1.8
   Compiling sync_wrapper v1.0.2
   Compiling thiserror v1.0.69
   Compiling regex-syntax v0.8.10
   Compiling atomic-waker v1.1.2
   Compiling mime v0.3.17
   Compiling linux-raw-sys v0.12.1
    Building [                           ] 0/242: try-lock, target-lexicon(bu…    Building [                           ] 1/242: try-lock, target-lexicon(bu…    Building [                           ] 2/242: try-lock, target-lexicon(bu…    Building [                           ] 3/242: try-lock, target-lexicon(bu…   Compiling fallible-iterator v0.3.0
    Building [                           ] 4/242: try-lock, fallible-iterator…    Building [                           ] 5/242: try-lock, fallible-iterator…    Building [                           ] 6/242: try-lock, fallible-iterator…    Building [                           ] 7/242: try-lock, fallible-iterator…    Building [                           ] 8/242: try-lock, fallible-iterator…    Building [>                          ] 9/242: try-lock, fallible-iterator…    Building [>                         ] 10/242: try-lock, fallible-iterator…    Building [>                         ] 11/242: try-lock, fallible-iterator…    Building [>                         ] 12/242: try-lock, fallible-iterator…    Building [>                         ] 13/242: try-lock, fallible-iterator…    Building [>                         ] 14/242: try-lock, fallible-iterator…    Building [>                         ] 15/242: try-lock, fallible-iterator…   Compiling fastrand v2.4.1
    Building [>                         ] 16/242: try-lock, fallible-iterator…    Building [>                         ] 17/242: try-lock, fallible-iterator…    Building [>                         ] 18/242: try-lock, fallible-iterator…    Building [=>                        ] 19/242: try-lock, fallible-iterator…   Compiling cpufeatures v0.2.17
    Building [=>                        ] 20/242: try-lock, fallible-iterator…   Compiling iana-time-zone v0.1.65
    Building [=>                        ] 21/242: try-lock, fallible-iterator…    Building [=>                        ] 22/242: try-lock, fallible-iterator…   Compiling base64 v0.22.1
    Building [=>                        ] 23/242: try-lock, fallible-iterator…    Building [=>                        ] 24/242: try-lock, fallible-iterator…    Building [=>                        ] 25/242: try-lock, fallible-iterator…    Building [=>                        ] 26/242: try-lock, fallible-iterator…    Building [=>                        ] 27/242: try-lock, fallible-iterator…    Building [==>                       ] 28/242: try-lock, fallible-iterator…    Building [==>                       ] 29/242: try-lock, fallible-iterator…    Building [==>                       ] 30/242: try-lock, fallible-iterator…    Building [==>                       ] 31/242: try-lock, fallible-iterator…   Compiling base64 v0.21.7
    Building [==>                       ] 32/242: try-lock, fallible-iterator…   Compiling fallible-streaming-iterator v0.1.9
    Building [==>                       ] 33/242: try-lock, fallible-iterator…   Compiling heck v0.5.0
    Building [==>                       ] 34/242: try-lock, fallible-iterator…   Compiling unsafe-libyaml v0.2.11
    Building [==>                       ] 35/242: try-lock, fallible-iterator…   Compiling futures-channel v0.3.32
    Building [==>                       ] 36/242: try-lock, fallible-iterator…   Compiling tracing-core v0.1.36
    Building [==>                       ] 37/242: try-lock, fallible-iterator…   Compiling hex v0.4.3
    Building [===>                      ] 38/242: try-lock, hex, fallible-ite…   Compiling encoding_rs v0.8.35
    Building [===>                      ] 39/242: try-lock, hex, fallible-ite…   Compiling sync_wrapper v0.1.2
    Building [===>                      ] 40/242: try-lock, hex, fallible-ite…   Compiling matchit v0.7.3
    Building [===>                      ] 41/242: try-lock, hex, fallible-ite…   Compiling num-traits v0.2.19
    Building [===>                      ] 42/242: try-lock, hex, fallible-ite…   Compiling memoffset v0.9.1
    Building [===>                      ] 43/242: try-lock, hex, fallible-ite…   Compiling http v1.4.0
    Building [===>                      ] 44/242: try-lock, hex, fallible-ite…   Compiling unicode-width v0.2.2
    Building [===>                      ] 45/242: try-lock, hex, fallible-ite…    Building [===>                      ] 46/242: try-lock, hex, fallible-ite…    Building [====>                     ] 47/242: try-lock, hex, fallible-ite…   Compiling webpki-roots v0.25.4
    Building [====>                     ] 48/242: try-lock, hex, fallible-ite…    Building [====>                     ] 49/242: try-lock, hex, fallible-ite…   Compiling generic-array v0.14.7
    Building [====>                     ] 50/242: try-lock, hex, fallible-ite…   Compiling ahash v0.8.12
    Building [====>                     ] 51/242: try-lock, hex, fallible-ite…    Building [====>                     ] 52/242: try-lock, hex, fallible-ite…   Compiling ipnet v2.12.0
    Building [====>                     ] 53/242: try-lock, hex, fallible-ite…   Compiling form_urlencoded v1.2.2
    Building [====>                     ] 54/242: try-lock, hex, fallible-ite…    Building [====>                     ] 55/242: try-lock, hex, fallible-ite…    Building [=====>                    ] 56/242: try-lock, hex, fallible-ite…   Compiling indoc v2.0.7
    Building [=====>                    ] 57/242: try-lock, hex, fallible-ite…   Compiling unindent v0.2.4
    Building [=====>                    ] 60/242: try-lock, hex, fallible-ite…    Building [=====>                    ] 61/242: try-lock, hex, fallible-ite…    Building [=====>                    ] 62/242: try-lock, hex, fallible-ite…    Building [=====>                    ] 63/242: try-lock, hex, fallible-ite…    Building [=====>                    ] 64/242: try-lock, hex, fallible-ite…    Building [=====>                    ] 65/242: try-lock, hex, fallible-ite…   Compiling indexmap v2.14.0
    Building [======>                   ] 66/242: try-lock, hex, fallible-ite…   Compiling cc v1.2.61
    Building [======>                   ] 67/242: try-lock, hex, fallible-ite…    Building [======>                   ] 68/242: try-lock, hex, fallible-ite…    Building [======>                   ] 69/242: try-lock, hex, fallible-ite…   Compiling deranged v0.5.8
    Building [======>                   ] 70/242: try-lock, hex, fallible-ite…    Building [======>                   ] 72/242: try-lock, hex, fallible-ite…   Compiling want v0.3.1
    Building [======>                   ] 73/242: hex, fallible-iterator, ser…    Building [======>                   ] 74/242: hex, fallible-iterator, ser…    Building [=======>                  ] 75/242: hex, fallible-iterator, ser…    Building [=======>                  ] 76/242: hex, fallible-iterator, ser…   Compiling time-macros v0.2.27
    Building [=======>                  ] 79/242: hex, fallible-iterator, ser…   Compiling aho-corasick v1.1.4
   Compiling http v0.2.12
    Building [=======>                  ] 80/242: hex, fallible-iterator, ser…    Building [=======>                  ] 81/242: hex, fallible-iterator, ser…    Building [=======>                  ] 82/242: hex, fallible-iterator, ser…    Building [=======>                  ] 83/242: hex, fallible-iterator, ser…    Building [========>                 ] 84/242: hex, fallible-iterator, ser…   Compiling futures-util v0.3.32
    Building [========>                 ] 85/242: hex, fallible-iterator, ser…    Building [========>                 ] 86/242: hex, fallible-iterator, ser…    Building [========>                 ] 87/242: hex, fallible-iterator, ser…    Building [========>                 ] 88/242: hex, fallible-iterator, ser…    Building [========>                 ] 89/242: hex, fallible-iterator, ser…   Compiling pem v3.0.6
    Building [========>                 ] 90/242: hex, fallible-iterator, ser…    Building [========>                 ] 91/242: hex, fallible-iterator, ser…   Compiling rustls-pemfile v1.0.4
    Building [========>                 ] 93/242: hex, fallible-iterator, ser…   Compiling serde_path_to_error v0.1.20
    Building [=========>                ] 94/242: hex, fallible-iterator, htt…    Building [=========>                ] 95/242: hex, fallible-iterator, htt…    Building [=========>                ] 96/242: hex, fallible-iterator, htt…   Compiling pyo3-build-config v0.22.6
    Building [=========>                ] 97/242: hex, fallible-iterator, htt…    Building [=========>                ] 98/242: hex, fallible-iterator, htt…    Building [=========>                ] 99/242: hex, fallible-iterator, htt…    Building [=========>               ] 100/242: hex, fallible-iterator, ind…    Building [=========>               ] 101/242: hex, indexmap, pem, serde_p…    Building [=========>               ] 102/242: hex, indexmap, pem, serde_p…    Building [=========>               ] 103/242: hex, indexmap, pem, serde_p…    Building [=========>               ] 105/242: hex, indexmap, pem, serde_p…    Building [=========>               ] 106/242: hex, indexmap, pem, serde_p…    Building [==========>              ] 107/242: hex, indexmap, pem, serde_p…    Building [==========>              ] 108/242: hex, indexmap, pem, serde_p…   Compiling tracing v0.1.44
    Building [==========>              ] 109/242: hex, indexmap, pem, serde_p…    Building [==========>              ] 110/242: indexmap, pem, serde_path_t…    Building [==========>              ] 111/242: indexmap, pem, serde_path_t…    Building [==========>              ] 112/242: indexmap, pem, serde_path_t…    Building [==========>              ] 113/242: indexmap, pem, serde_path_t…    Building [==========>              ] 114/242: indexmap, pem, serde_path_t…    Building [==========>              ] 115/242: indexmap, pem, serde_path_t…   Compiling num-integer v0.1.46
   Compiling chrono v0.4.44
    Building [==========>              ] 116/242: indexmap, pem, serde_path_t…    Building [===========>             ] 117/242: indexmap, pem, serde_path_t…    Building [===========>             ] 118/242: indexmap, pem, serde_path_t…    Building [===========>             ] 119/242: indexmap, pem, serde_path_t…    Building [===========>             ] 120/242: indexmap, pem, serde_path_t…    Building [===========>             ] 121/242: indexmap, pem, serde_path_t…    Building [===========>             ] 122/242: indexmap, pem, serde_path_t…    Building [===========>             ] 123/242: indexmap, pem, proc-macro2(…   Compiling http-body v0.4.6
    Building [===========>             ] 125/242: indexmap, proc-macro2(build…   Compiling http-body v1.0.1
   Compiling block-buffer v0.10.4
   Compiling crypto-common v0.1.7
    Building [============>            ] 127/242: indexmap, proc-macro2(build…   Compiling ring v0.17.14
   Compiling libsqlite3-sys v0.30.1
    Building [============>            ] 128/242: indexmap, proc-macro2(build…   Compiling time v0.3.47
    Building [============>            ] 129/242: indexmap, proc-macro2(build…    Building [============>            ] 130/242: proc-macro2(build), chrono,…    Building [============>            ] 131/242: proc-macro2(build), chrono,…    Building [============>            ] 132/242: ring(build), proc-macro2(bu…   Compiling errno v0.3.14
   Compiling getrandom v0.2.17
   Compiling mio v1.2.0
   Compiling socket2 v0.6.3
   Compiling socket2 v0.5.10
   Compiling fs2 v0.4.3
    Building [============>            ] 132/242: getrandom, ring(build), pro…    Building [============>            ] 133/242: getrandom, ring(build), pro…    Building [============>            ] 134/242: getrandom, ring(build), pro…   Compiling num-bigint v0.4.6
    Building [============>            ] 135/242: getrandom, ring(build), pro…    Building [=============>           ] 136/242: getrandom, ring(build), pro…   Compiling pyo3-macros-backend v0.22.6
   Compiling pyo3-ffi v0.22.6
   Compiling pyo3 v0.22.6
    Building [=============>           ] 137/242: getrandom, pyo3-macros-back…   Compiling ppv-lite86 v0.2.21
    Building [=============>           ] 138/242: getrandom, pyo3-macros-back…    Building [=============>           ] 139/242: getrandom, ring(build), pro…   Compiling regex-automata v0.4.14
    Building [=============>           ] 140/242: getrandom, proc-macro2, rin…    Building [=============>           ] 141/242: getrandom, proc-macro2, rin…    Building [=============>           ] 142/242: getrandom, proc-macro2, rin…    Building [=============>           ] 143/242: getrandom, proc-macro2, rin…    Building [=============>           ] 144/242: getrandom, proc-macro2, rin…    Building [=============>           ] 145/242: getrandom, proc-macro2, rin…    Building [==============>          ] 146/242: getrandom, proc-macro2, rin…   Compiling http-body-util v0.1.3
    Building [==============>          ] 147/242: getrandom, proc-macro2, rin…    Building [==============>          ] 148/242: getrandom, proc-macro2, rin…   Compiling digest v0.10.7
    Building [==============>          ] 149/242: getrandom, proc-macro2, rin…   Compiling rand_core v0.6.4
    Building [==============>          ] 149/242: rand_core, getrandom, proc-…    Building [==============>          ] 150/242: rand_core, proc-macro2, rin…    Building [==============>          ] 151/242: rand_core, proc-macro2, rin…    Building [==============>          ] 152/242: rand_core, proc-macro2, rin…    Building [==============>          ] 153/242: rand_core, proc-macro2, rin…   Compiling signal-hook-registry v1.4.8
   Compiling hashbrown v0.14.5
    Building [==============>          ] 154/242: rand_core, proc-macro2, rin…    Building [===============>         ] 155/242: rand_core, proc-macro2, rin…    Building [===============>         ] 156/242: rand_core, proc-macro2, rin…   Compiling tempfile v3.27.0
    Building [===============>         ] 157/242: rand_core, proc-macro2, rin…    Building [===============>         ] 158/242: rand_core, proc-macro2, rin…    Building [===============>         ] 159/242: rand_core, proc-macro2, rin…    Building [===============>         ] 160/242: rand_core, proc-macro2, rin…   Compiling sha2 v0.10.9
    Building [===============>         ] 162/242: proc-macro2, ring(build), r…    Building [===============>         ] 163/242: proc-macro2, ring(build), r…   Compiling tower-http v0.5.2
    Building [===============>         ] 164/242: proc-macro2, ring(build), r…    Building [================>        ] 165/242: proc-macro2, ring(build), r…    Building [================>        ] 165/242: proc-macro2, quote, ring(bu…    Building [================>        ] 166/242: quote, ring(build), regex-a…   Compiling rand_chacha v0.3.1
    Building [================>        ] 167/242: quote, ring(build), regex-a…    Building [================>        ] 168/242: quote, ring(build), regex-a…    Building [================>        ] 169/242: quote, ring(build), regex-a…    Building [================>        ] 170/242: quote, ring(build), regex-a…    Building [================>        ] 171/242: quote, ring(build), regex-a…    Building [================>        ] 172/242: quote, ring(build), regex-a…   Compiling hashlink v0.9.1
    Building [================>        ] 173/242: quote, ring(build), regex-a…    Building [================>        ] 174/242: quote, ring(build), regex-a…    Building [=================>       ] 175/242: quote, ring(build), regex-a…   Compiling rand v0.8.6
    Building [=================>       ] 175/242: quote, rand, ring(build), r…    Building [=================>       ] 176/242: quote, rand, ring(build), r…   Compiling syn v2.0.117
    Building [=================>       ] 177/242: rand, ring(build), regex-au…    Building [=================>       ] 178/242: rand, ring(build), regex-au…    Building [=================>       ] 179/242: ring(build), regex-automata…    Building [=================>       ] 180/242: regex-automata, syn, rustls…    Building [=================>       ] 181/242: regex-automata, syn, ring, …   Compiling regex v1.12.3
    Building [=================>       ] 182/242: syn, ring, libsqlite3-sys(b…   Compiling synstructure v0.13.2
    Building [=================>       ] 182/242: syn, synstructure, pyo3-mac…   Compiling zerovec-derive v0.11.3
   Compiling tokio-macros v2.7.0
   Compiling displaydoc v0.2.5
   Compiling serde_derive v1.0.228
   Compiling thiserror-impl v2.0.18
   Compiling thiserror-impl v1.0.69
   Compiling async-trait v0.1.89
   Compiling async-stream-impl v0.3.6
    Building [=================>       ] 183/242: thiserror-impl, thiserror-i…    Building [==================>      ] 184/242: thiserror-impl, thiserror-i…   Compiling tokio v1.52.2
    Building [==================>      ] 185/242: thiserror-impl, thiserror-i…   Compiling async-stream v0.3.6
    Building [==================>      ] 186/242: thiserror-impl, thiserror-i…    Building [==================>      ] 187/242: thiserror-impl, thiserror-i…   Compiling axum-core v0.4.5
    Building [==================>      ] 188/242: thiserror-impl, thiserror-i…    Building [==================>      ] 189/242: thiserror-impl, tokio, syns…    Building [==================>      ] 190/242: tokio, synstructure, pyo3-m…    Building [==================>      ] 191/242: tokio, synstructure, pyo3-m…   Compiling zerofrom-derive v0.1.7
   Compiling yoke-derive v0.8.2
    Building [==================>      ] 192/242: tokio, zerofrom-derive, yok…    Building [==================>      ] 193/242: tokio, zerofrom-derive, yok…    Building [===================>     ] 194/242: tokio, zerofrom-derive, yok…   Compiling simple_asn1 v0.6.4
    Building [===================>     ] 195/242: tokio, zerofrom-derive, yok…    Building [===================>     ] 196/242: serde, tokio, zerofrom-deri…    Building [===================>     ] 197/242: serde, tokio, zerofrom-deri…   Compiling zerofrom v0.1.7
    Building [===================>     ] 198/242: serde, tokio, zerofrom, pyo…   Compiling sct v0.7.1
   Compiling rustls-webpki v0.101.7
    Building [===================>     ] 198/242: serde, tokio, zerofrom, rus…    Building [===================>     ] 199/242: serde, tokio, zerofrom, rus…   Compiling yoke v0.8.2
    Building [===================>     ] 199/242: serde, tokio, yoke, zerofro…    Building [===================>     ] 200/242: serde, tokio, yoke, rustls-…    Building [===================>     ] 201/242: serde, tokio, yoke, rustls-…   Compiling serde_urlencoded v0.7.1
   Compiling serde_yaml v0.9.34+deprecated
   Compiling jsonwebtoken v9.3.1
    Building [===================>     ] 201/242: serde, tokio, jsonwebtoken,…    Building [===================>     ] 202/242: tokio, jsonwebtoken, yoke, …    Building [===================>     ] 203/242: tokio, jsonwebtoken, yoke, …   Compiling zerovec v0.11.6
   Compiling zerotrie v0.2.4
    Building [====================>    ] 204/242: tokio, jsonwebtoken, rustls…    Building [====================>    ] 205/242: tokio, jsonwebtoken, rustls…   Compiling pyo3-macros v0.22.6
    Building [====================>    ] 207/242: tokio, pyo3-macros, jsonweb…    Building [====================>    ] 207/242: tokio, rustls, pyo3-macros,…    Building [====================>    ] 208/242: tokio, rustls, pyo3-macros,…    Building [====================>    ] 209/242: tokio, rustls, jsonwebtoken…    Building [====================>    ] 210/242: tokio, rustls, jsonwebtoken…   Compiling tinystr v0.8.3
   Compiling potential_utf v0.1.5
    Building [====================>    ] 211/242: tokio, rustls, jsonwebtoken…    Building [====================>    ] 212/242: tokio, rustls, jsonwebtoken…   Compiling icu_collections v2.2.0
    Building [=====================>   ] 213/242: tokio, rustls, jsonwebtoken…    Building [=====================>   ] 214/242: tokio, rustls, icu_collecti…   Compiling icu_locale_core v2.2.0
    Building [=====================>   ] 214/242: tokio, rustls, icu_locale_c…    Building [=====================>   ] 215/242: tokio, rustls, icu_locale_c…    Building [=====================>   ] 216/242: tokio, rustls, icu_locale_c…   Compiling tokio-util v0.7.18
   Compiling hyper v1.9.0
   Compiling tower v0.5.3
    Building [=====================>   ] 217/242: rustls, icu_locale_core, to…    Building [=====================>   ] 218/242: rustls, icu_locale_core, to…    Building [=====================>   ] 219/242: rustls, icu_locale_core, to…   Compiling icu_provider v2.2.0
    Building [=====================>   ] 220/242: rustls, tokio-util, hyper, …   Compiling h2 v0.3.27
    Building [=====================>   ] 221/242: rustls, hyper, icu_provider…   Compiling tokio-rustls v0.24.1
    Building [=====================>   ] 221/242: rustls, tokio-rustls, hyper…    Building [=====================>   ] 222/242: tokio-rustls, hyper, icu_pr…   Compiling icu_normalizer v2.2.0
   Compiling icu_properties v2.2.0
    Building [=====================>   ] 222/242: icu_properties, tokio-rustl…    Building [======================>  ] 223/242: icu_properties, tokio-rustl…   Compiling hyper-util v0.1.20
    Building [======================>  ] 224/242: icu_properties, tokio-rustl…    Building [======================>  ] 225/242: icu_properties, icu_normali…   Compiling axum v0.7.9
    Building [======================>  ] 225/242: icu_properties, axum, icu_n…    Building [======================>  ] 227/242: icu_properties, axum, libsq…   Compiling idna_adapter v1.2.2
    Building [======================>  ] 227/242: icu_properties, idna_adapte…    Building [======================>  ] 228/242: idna_adapter, axum, libsqli…   Compiling idna v1.1.0
    Building [======================>  ] 228/242: idna_adapter, axum, idna, l…    Building [======================>  ] 229/242: axum, idna, libsqlite3-sys(…   Compiling url v2.5.8
    Building [======================>  ] 229/242: url, axum, idna, libsqlite3…    Building [======================>  ] 230/242: url, axum, libsqlite3-sys(b…   Compiling hyper v0.14.32
    Building [======================>  ] 230/242: hyper, url, axum, libsqlite…    Building [======================>  ] 231/242: hyper, url, axum, libsqlite…    Building [======================>  ] 232/242: hyper, url, libsqlite3-sys(…    Building [=======================> ] 233/242: hyper, libsqlite3-sys(build)   Compiling hyper-rustls v0.24.2
    Building [=======================> ] 233/242: hyper, hyper-rustls, libsql…    Building [=======================> ] 234/242: hyper-rustls, libsqlite3-sy…   Compiling reqwest v0.11.27
    Building [=======================> ] 234/242: reqwest, hyper-rustls, libs…    Building [=======================> ] 235/242: reqwest, libsqlite3-sys(bui…    Building [=======================> ] 236/242: libsqlite3-sys(build)           Building [=======================> ] 237/242: libsqlite3-sys                 Compiling rusqlite v0.32.1
    Building [=======================> ] 237/242: libsqlite3-sys, rusqlite        Building [=======================> ] 238/242: rusqlite                       Compiling sase_core v0.34.59 (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/sase/repos/linked/sase-core/crates/sase_core)
    Building [=======================> ] 238/242: sase_core, rusqlite             Building [=======================> ] 239/242: sase_core                      Compiling sase_gateway v0.34.59 (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/sase/repos/linked/sase-core/crates/sase_gateway)
    Building [=======================> ] 239/242: sase_core, sase_gateway         Building [=======================> ] 240/242: sase_gateway                   Compiling sase_core_py v0.34.59 (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/sase/repos/linked/sase-core/crates/sase_core_py)
    Building [=======================> ] 241/242: sase_core_py                    Finished `release` profile [optimized] target(s) in 10m 59s
📦 Built wheel for abi3 Python ≥ 3.12 to /home/bryan/.cache/sase/tmp/agent-tmp/gh_sase-org__sase-ws10-260918_210528/.tmpPryfZL/sase_core_rs-0.34.59-cp312-abi3-linux_x86_64.whl
✏️ Setting installed package as editable
🛠 Installed sase-core-rs-0.34.59
🍹 Building a mixed python/rust project
🐍 Found CPython 3.14 at /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/bin/python
🔗 Found pyo3 bindings with abi3-py3.12 support
📡 Using build options features from pyproject.toml
    Finished `release` profile [optimized] target(s) in 0.18s
📦 Built wheel for abi3 Python ≥ 3.12 to /home/bryan/.sase/cache/sase-core-wheels/.build-y5dkpxzg/sase_core_rs-0.34.59-cp312-abi3-manylinux_2_39_x86_64.whl
/home/bryan/.sase/cache/sase-core-wheels/632a931ff1968709d4dac0ffd4c2e955153bddd4156c833c082c4e1d4b53b9fa/sase_core_rs-0.34.59-cp312-abi3-manylinux_2_39_x86_64.whl
# Keep the LSP server in lockstep with the extension: both are built
# from the same sase-core checkout, and the ACE/LSP parity tests
# compare their directive contracts.
   Compiling sase_core v0.34.59 (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/sase/repos/linked/sase-core/crates/sase_core)
    Building [=======================> ] 145/148: sase_core                      Compiling sase_xprompt_lsp v0.34.59 (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/sase/repos/linked/sase-core/crates/sase_xprompt_lsp)
    Building [=======================> ] 145/148: sase_core, sase_xprompt_lsp     Building [=======================> ] 146/148: sase_xprompt_lsp                Building [=======================> ] 147/148: sase-xprompt-lsp(bin)           Finished `dev-update` profile [optimized] target(s) in 1m 32s
[rust-lsp-install] installed /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/bin/sase-xprompt-lsp
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
✓ lint (toobig)
✓ SASE validation
[core-floor-probe] stale_actionable: sase-core-rs==0.34.48 is missing 5 capability(s) that exist in a published sase-core release.
[core-floor-probe] bead_set_link_projections: first appears in sase-core d32591f (feat(bead): add atomic bulk link-projection mutation); release v0.34.53 contains it.
[core-floor-probe] select_remaining_commit_obligations: first appears in sase-core 8d5341a (feat(finalizer): select remaining declared repos after repair); release v0.34.53 contains it.
[core-floor-probe] sudo_authorize_settlement: first appears in sase-core 9e1ab3f (feat(sudo): add completion authorization core contracts); release v0.34.54 contains it.
[core-floor-probe] sudo_classify_attempt_liveness: first appears in sase-core 9e1ab3f (feat(sudo): add completion authorization core contracts); release v0.34.54 contains it.
[core-floor-probe] sudo_validate_handshake: first appears in sase-core b70e64d (feat(sudo): add detached runner execution); release v0.34.52 contains it.
{"cache_hit": true, "capabilities": [{"commit": "d32591f", "name": "bead_set_link_projections", "release": "v0.34.53", "subject": "feat(bead): add atomic bulk link-projection mutation"}, {"commit": "8d5341a", "name": "select_remaining_commit_obligations", "release": "v0.34.53", "subject": "feat(finalizer): select remaining declared repos after repair"}, {"commit": "9e1ab3f", "name": "sudo_authorize_settlement", "release": "v0.34.54", "subject": "feat(sudo): add completion authorization core contracts"}, {"commit": "9e1ab3f", "name": "sudo_classify_attempt_liveness", "release": "v0.34.54", "subject": "feat(sudo): add completion authorization core contracts"}, {"commit": "b70e64d", "name": "sudo_validate_handshake", "release": "v0.34.52", "subject": "feat(sudo): add detached runner execution"}], "declared_floor": "0.34.48", "exit_code": 3, "message": "sase-core-rs==0.34.48 is missing 5 capability(s) that exist in a published sase-core release.", "status": "stale_actionable"}
✓ committed plans
✗ test (scoped)
.venv/bin/python tools/setup_required_plugins
[setup] Installing required plugin sase-github>=0.2.5.
[setup] Installing required plugin sase-research-artifacts>=0.2.0.

┌───────────────────────────────────────────────────────┐
│                RUNNING: just test-scoped              │
└───────────────────────────────────────────────────────┘

---------- Running diff-scoped pytest selection... ----------
test selection escalated to the full suite (rules: core-identity-changed, src-data-asset); 4002 test files in scope
coverage contexts: not consulted — the run escalates to the full suite, so ground truth had nothing to add
escalating to the governed full test lane (rules: core-identity-changed, src-data-asset)
============================= test session starts ==============================
platform linux -- Python 3.14.7, pytest-9.0.2, pluggy-1.6.0
rootdir: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10
configfile: pyproject.toml
testpaths: tests
plugins: cov-7.0.0, asyncio-1.3.0, hypothesis-6.151.9, xdist-3.8.0, inline-snapshot-0.32.5, mock-3.15.1
asyncio: mode=Mode.AUTO, debug=False, asyncio_default_fixture_loop_scope=None, asyncio_default_test_loop_scope=function
created: 7/7 workers
7 workers [43269 items]

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
........................................................................ [ 26%]
........................................................................ [ 26%]
........................................................................ [ 26%]
........................................................................ [ 26%]
........................................................................ [ 26%]
........................................................................ [ 26%]
..................................................................F..... [ 27%]
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
.............................................ssss....................... [ 39%]
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
........................................................................ [ 42%]
........................................................................ [ 42%]
..................................................s..................... [ 42%]
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
........................................................................ [ 47%]
...........................................................s............ [ 47%]
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
........s............................................................... [ 52%]
........................................................................ [ 52%]
........................................................................ [ 52%]
........................................................................ [ 52%]
.............ss......................................................... [ 52%]
........................................................................ [ 52%]
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
..........s............................................................. [ 63%]
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
........................................................................ [ 66%]
........................................................................ [ 66%]
........................................................................ [ 66%]
........................................................................ [ 66%]
........................................................................ [ 66%]
........................................................................ [ 66%]
........................................................................ [ 67%]
........................................................................ [ 67%]
........................................................................ [ 67%]
...................................s.................................... [ 67%]
........................................................................ [ 67%]
........................................................................ [ 67%]
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
........................................................................ [ 76%]
........................................................................ [ 76%]
........................................................................ [ 76%]
.....s.................................................................. [ 76%]
........................................................................ [ 76%]
........................................................................ [ 76%]
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
........................................................................ [ 81%]
........................................................................ [ 81%]
........................................................................ [ 81%]
........................................................................ [ 81%]
.......................................................................s [ 81%]
........................................................................ [ 81%]
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
........................................................................ [ 98%]
........................................................................ [ 98%]
........................................................................ [ 98%]
........................................................................ [ 98%]
........................................................................ [ 98%]
........................................................................ [ 98%]
........................................................................ [ 99%]
..F..................................................................... [ 99%]
........................................................................ [ 99%]
........................................................................ [ 99%]
........................................................................ [ 99%]
........................................................................ [ 99%]
.....................................................................    [100%]/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/lib/python3.14/site-packages/_pytest/unraisableexception.py:67: PytestUnraisableExceptionWarning: Exception ignored while calling GC callback <function gc_cumulative_time.<locals>.gc_callback at 0x7f4ba1e79430>: None

Traceback (most recent call last):
  File "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/lib/python3.14/site-packages/hypothesis/internal/conjecture/junkdrawer.py", line 468, in gc_callback
    now = _perf_counter()
KeyboardInterrupt


  warnings.warn(pytest.PytestUnraisableExceptionWarning(msg))


═══════════════════════════════ inline-snapshot ════════════════════════════════
INFO: CI run was detected because environment variable "CI" was defined. 
inline-snapshot runs with --inline-snapshot=disable by default in CI. This means
that tests with snapshots will continue to run, but snapshot(x) will only return
x and inline-snapshot will not be able to fix snapshots or generate reports. You
can change this by using --inline-snapshot=report for example.


=================================== FAILURES ===================================
_ test_unsafe_axe_systemd_scope_matrix[0::/user.slice/user-1000.slice/user@1000.service/app.slice/tmux-spawn-example.scope\n-True-tmux-spawn-example.scope] _
[gw3] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/bin/python

monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7f58c039f310>
tmp_path = PosixPath('/var/tmp/sase-02a72d87/pytest-of-bryan/pytest-9/popen-gw3/test_unsafe_axe_systemd_scope_0')
cgroup = '0::/user.slice/user-1000.slice/user@1000.service/app.slice/tmux-spawn-example.scope\n'
has_systemd_run = True, expected_scope = 'tmux-spawn-example.scope'

    @pytest.mark.parametrize(
        ("cgroup", "has_systemd_run", "expected_scope"),
        [
            (
                "0::/user.slice/user-1000.slice/user@1000.service/"
                "app.slice/tmux-spawn-example.scope\n",
                True,
                "tmux-spawn-example.scope",
            ),
            (
                "0::/user.slice/user-1000.slice/user@1000.service/"
                "app.slice/sase-axe-123.scope\n",
                True,
                None,
            ),
            ("0::/user.slice/app.slice/sase-axe.scope\n", True, None),
            (
                "0::/user.slice/user-1000.slice/user@1000.service/"
                "app.slice/tmux-spawn-example.scope\n",
                False,
                None,
            ),
            ("5:cpu:/legacy/session.scope\n", True, None),
        ],
    )
    def test_unsafe_axe_systemd_scope_matrix(
        monkeypatch: pytest.MonkeyPatch,
        tmp_path: Path,
        cgroup: str,
        has_systemd_run: bool,
        expected_scope: str | None,
    ) -> None:
        proc_root = tmp_path / "proc"
        process_dir = proc_root / "123"
        process_dir.mkdir(parents=True)
        (process_dir / "cgroup").write_text(cgroup)
        monkeypatch.setattr("sase.axe.systemd_scope.sys.platform", "linux")
        monkeypatch.setattr(
            "sase.axe.systemd_scope.shutil.which",
            lambda _name: "/usr/bin/systemd-run" if has_systemd_run else None,
        )
    
>       assert unsafe_axe_systemd_scope(123, proc_root=proc_root) == expected_scope
E       AssertionError: assert None == 'tmux-spawn-example.scope'
E        +  where None = unsafe_axe_systemd_scope(123, proc_root=PosixPath('/var/tmp/sase-02a72d87/pytest-of-bryan/pytest-9/popen-gw3/test_unsafe_axe_systemd_scope_0/proc'))

tests/doctor/test_checks_axe.py:161: AssertionError
_________ test_confirmed_toggle_restarts_axe_and_suppresses_duplicates _________
[gw6] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/bin/python

monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7f25548a91d0>

    async def test_confirmed_toggle_restarts_axe_and_suppresses_duplicates(
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        started = threading.Event()
        release = threading.Event()
        mutations: list[tuple[str, bool]] = []
        restarts: list[bool] = []
        _install_load(
            monkeypatch,
            _payload((_view("artifact_links", enabled=False),)),
        )
    
        def slow_set(key: str, enabled: bool) -> None:
            mutations.append((key, enabled))
            started.set()
            release.wait(timeout=2)
    
        monkeypatch.setattr(
            "sase.ace.tui.modals.feature_flags_pane.set_saved_feature_flag",
            slow_set,
        )
        monkeypatch.setattr(
            "sase.ace.tui.update_restart.running_background_procs",
            lambda _app: [],
        )
        async with AcePage(initial_tab="agents") as page:
            page.app._restart_tui = (  # type: ignore[method-assign]
                lambda *, restart_axe: restarts.append(restart_axe)
            )
            _modal, pane = await _open_flags_pane(page)
            pane.action_toggle_flag()
            await page.expect_modal("ConfirmActionModal")
            await page.press("y")
            await page.wait_for(lambda _s: started.is_set())
>           assert pane._mutating is True
E           AssertionError: assert False is True
E            +  where False = FeatureFlagsPane(id='flags', classes='-embedded')._mutating

tests/ace/tui/test_feature_flags_pane.py:342: AssertionError
=============================== warnings summary ===============================
.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:852
.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:852
.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:852
.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:852
.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:852
.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:852
.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:852
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:852: PytestAssertRewriteWarning: Module already imported so cannot be rewritten; tests._axe_lumberjack_fixtures
    self.import_plugin(import_spec)

tests/test_run_agent_runner_clan_summary_refresh.py::test_successful_post_preparation_summary_survives_later_metadata_write
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_run_agent_runner_clan_summary_refresh.py::test_successful_post_preparation_summary_survives_later_metadata_write changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
    next(it)

tests/test_run_agent_runner_clan_summary_refresh.py::test_unsuccessful_post_preparation_summary_keeps_earlier_success
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_run_agent_runner_clan_summary_refresh.py::test_unsuccessful_post_preparation_summary_keeps_earlier_success changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
    next(it)

tests/axe/test_run_agent_exec_attempts_integration.py::test_retry_branch_snapshots_failed_attempt
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/axe/test_run_agent_exec_attempts_integration.py::test_retry_branch_snapshots_failed_attempt changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
    next(it)

tests/axe/test_run_agent_exec_attempts_integration.py::test_fallback_branch_snapshots_with_primary_model_marker
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/axe/test_run_agent_exec_attempts_integration.py::test_fallback_branch_snapshots_with_primary_model_marker changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
    next(it)

tests/completion/test_zsh_smoke.py: 18 warnings
  /home/bryan/.local/share/uv/python/cpython-3.14.7-linux-x86_64-gnu/lib/python3.14/pty.py:66: DeprecationWarning: This process (pid=3034699) is multi-threaded, use of forkpty() may lead to deadlocks in the child.
    pid, fd = os.forkpty()

tests/test_xprompt_processor_workflow_execute.py::test_execute_workflow_flatten_preserves_caller_named_args
tests/test_xprompt_processor_workflow_execute.py::test_execute_workflow_flatten_explicit_named_args_override_caller
tests/test_xprompt_processor_workflow_execute.py::test_execute_workflow_flatten_preserves_wrapper_model_override
tests/test_xprompt_processor_workflow_execute.py::test_execute_workflow_passes_inherited_vcs_tag_without_context_leak
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/src/sase/xprompt/workflow_runner.py:474: UserWarning: Standalone workflow '#split' is deprecated; use '#!split' instead.
    flattened = _flatten_anonymous_workflow(workflow, project=project)

tests/test_xprompt_processor_workflow_flatten.py::test_flatten_anonymous_workflow_returns_workflow_for_pure_multistep
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/tests/test_xprompt_processor_workflow_flatten.py:114: UserWarning: Standalone workflow '#split' is deprecated; use '#!split' instead.
    result = _flatten_anonymous_workflow(workflow)

tests/test_xprompt_processor_workflow_flatten.py::test_flatten_anonymous_workflow_slow_path_with_xprompt_and_workflow
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/src/sase/xprompt/workflow_runner.py:297: UserWarning: Standalone workflow '#batch_split' is deprecated; use '#!batch_split' instead.
    standalone = _find_standalone_workflow_ref(prompt_text, prompts)

tests/test_xprompt_processor_workflow_flatten.py::test_flatten_anonymous_workflow_slow_path_with_args
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/src/sase/xprompt/workflow_runner.py:297: UserWarning: Standalone workflow '#deploy' is deprecated; use '#!deploy' instead.
    standalone = _find_standalone_workflow_ref(prompt_text, prompts)

tests/test_xprompt_processor_workflow_flatten.py::test_flatten_anonymous_workflow_preserves_wrapper_model_directive
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/tests/test_xprompt_processor_workflow_flatten.py:421: UserWarning: Standalone workflow '#split' is deprecated; use '#!split' instead.
    result = _flatten_anonymous_workflow(workflow)

tests/sdd/test_artifact_link_event_acceptance_process_death.py::test_real_killed_publisher_process_leaves_no_corrupt_object_and_recovers
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/tests/sdd/test_artifact_link_event_acceptance_process_death.py:57: DeprecationWarning: This process (pid=3034611) is multi-threaded, use of fork() may lead to deadlocks in the child.
    child = os.fork()

tests/test_notification_modal_tab_order.py::test_on_mount_highlights_first_visible_row_when_initial_is_hidden
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/src/sase/ace/tui/modals/notification_modal_snooze_status.py:136: RuntimeWarning: coroutine 'Timer._run_timer' was never awaited
    self._snooze_status_timer = None
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/test_procs_supervisor.py::test_starter_exit_does_not_kill_a_released_proc
  <frozen os>:898: DeprecationWarning: This process (pid=3034798) is multi-threaded, use of fork() may lead to deadlocks in the child.

tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorContinuation::test_prepends_nudge_on_retry
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorContinuation::test_prepends_nudge_on_retry changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorContinuation::test_does_not_double_prepend_on_repeated_retries
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorContinuation::test_does_not_double_prepend_on_repeated_retries changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorContinuation::test_prepends_nudge_on_zero_wait_retry
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorContinuation::test_prepends_nudge_on_zero_wait_retry changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorNoNudge::test_no_nudge_leaves_prompt_untouched
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorNoNudge::test_no_nudge_leaves_prompt_untouched changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorCodexDefaults::test_codex_transient_default_retries_with_preserved_workspace
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorCodexDefaults::test_codex_transient_default_retries_with_preserved_workspace changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorPostPhaseTransition::test_retry_fires_for_coder_after_plan_approval
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorPostPhaseTransition::test_retry_fires_for_coder_after_plan_approval changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry_usage_limits.py::TestHandleWorkflowErrorUsageLimitPrecedence::test_transient_429_not_a_usage_limit_match_still_retries
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_exec_retry_usage_limits.py::TestHandleWorkflowErrorUsageLimitPrecedence::test_transient_429_not_a_usage_limit_match_still_retries changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry_usage_limits.py::TestHandleWorkflowErrorUsageLimitPrecedence::test_fallback_allowed_to_different_non_disabled_provider
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_exec_retry_usage_limits.py::TestHandleWorkflowErrorUsageLimitPrecedence::test_fallback_allowed_to_different_non_disabled_provider changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry_usage_limits.py::TestHandleWorkflowErrorUsageLimitPrecedence::test_fallback_allowed_when_fallback_provider_carries_soft_disable
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_exec_retry_usage_limits.py::TestHandleWorkflowErrorUsageLimitPrecedence::test_fallback_allowed_when_fallback_provider_carries_soft_disable changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry_usage_limits.py::TestHandleWorkflowErrorUsageLimitPrecedence::test_known_codex_attempt_does_not_scan_quoted_claude_limit_prose
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_exec_retry_usage_limits.py::TestHandleWorkflowErrorUsageLimitPrecedence::test_known_codex_attempt_does_not_scan_quoted_claude_limit_prose changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry_workspace.py::TestHandleWorkflowErrorPreserveWorkspace::test_preserve_workspace_skips_prepare_on_retry
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_exec_retry_workspace.py::TestHandleWorkflowErrorPreserveWorkspace::test_preserve_workspace_skips_prepare_on_retry changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry_workspace.py::TestHandleWorkflowErrorPreserveWorkspace::test_preserve_workspace_skips_prepare_on_fallback
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_exec_retry_workspace.py::TestHandleWorkflowErrorPreserveWorkspace::test_preserve_workspace_skips_prepare_on_fallback changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry_workspace.py::TestHandleWorkflowErrorPreserveWorkspace::test_default_preserve_workspace_false_still_calls_prepare
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_exec_retry_workspace.py::TestHandleWorkflowErrorPreserveWorkspace::test_default_preserve_workspace_false_still_calls_prepare changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_failed_fork_admission.py::TestFailedForkParentAdmission::test_runner_admits_and_claims_real_workspace_for_failed_fork_parent
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_failed_fork_admission.py::TestFailedForkParentAdmission::test_runner_admits_and_claims_real_workspace_for_failed_fork_parent changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_runner_slot_only_deferred_wait_gates_then_claims_workspace[wait_info0-0-None]
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_runner_slot_only_deferred_wait_gates_then_claims_workspace[wait_info0-0-None] changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_runner_slot_only_deferred_wait_gates_then_claims_workspace[wait_info1-None-20]
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_runner_slot_only_deferred_wait_gates_then_claims_workspace[wait_info1-None-20] changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_deferred_wait_gates_before_claim_and_prepares_claimed_workspace
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_deferred_wait_gates_before_claim_and_prepares_claimed_workspace changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_incomplete_clan_fork_expands_after_wait_before_slot_and_claim
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_incomplete_clan_fork_expands_after_wait_before_slot_and_claim changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_combined_wait_runs_dependencies_then_gate_then_claim
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_combined_wait_runs_dependencies_then_gate_then_claim changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_home_mode_deferred_wait_keeps_directory_workspace
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_home_mode_deferred_wait_keeps_directory_workspace changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_outcomes.py::TestDeferredWorkspaceOutcomes::test_repeat_stop_exits_before_workspace_claim_and_run_loop
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_outcomes.py::TestDeferredWorkspaceOutcomes::test_repeat_stop_exits_before_workspace_claim_and_run_loop changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_outcomes.py::TestDeferredWorkspaceOutcomes::test_deferred_workspace_without_extracted_wait_still_claims_real_workspace
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_outcomes.py::TestDeferredWorkspaceOutcomes::test_deferred_workspace_without_extracted_wait_still_claims_real_workspace changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_outcomes.py::TestDeferredWorkspaceOutcomes::test_bead_claim_failure_writes_error_and_skips_model_execution
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_outcomes.py::TestDeferredWorkspaceOutcomes::test_bead_claim_failure_writes_error_and_skips_model_execution changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_outcomes.py::TestDeferredWorkspaceOutcomes::test_bead_environment_mismatch_writes_error_and_skips_model_execution
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_outcomes.py::TestDeferredWorkspaceOutcomes::test_bead_environment_mismatch_writes_error_and_skips_model_execution changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_outcomes.py::TestDeferredWorkspaceOutcomes::test_launch_without_bead_never_invokes_claim_helper
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_outcomes.py::TestDeferredWorkspaceOutcomes::test_launch_without_bead_never_invokes_claim_helper changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_no_retry_when_config_is_none
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_no_retry_when_config_is_none changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_non_retryable_error_raises_immediately
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_non_retryable_error_raises_immediately changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_retry_on_retryable_error
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_retry_on_retryable_error changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_retry_state_written_during_wait
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_retry_state_written_during_wait changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_retry_state_deleted_on_completion
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_retry_state_deleted_on_completion changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_fallback_model_tried_after_max_retries
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_fallback_model_tried_after_max_retries changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_was_killed_during_wait_aborts_retry
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_was_killed_during_wait_aborts_retry changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_done_json_includes_retry_metadata
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_done_json_includes_retry_metadata changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_no_retry_metadata_when_no_retries
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_no_retry_metadata_when_no_retries changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_cross_provider_retry_uses_fallback_config
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_cross_provider_retry_uses_fallback_config changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_agent_is_admitted_before_workspace_preparation
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_agent_is_admitted_before_workspace_preparation changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_admitted_root_is_counted_when_workspace_preparation_fails
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_admitted_root_is_counted_when_workspace_preparation_fails changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_no_wait_runner_records_run_started_at_before_execution
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_no_wait_runner_records_run_started_at_before_execution changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_runner_persists_sdd_base_sha_before_execution
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_runner_persists_sdd_base_sha_before_execution changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_runner_populates_multi_agent_prompt_file_from_env
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_runner_populates_multi_agent_prompt_file_from_env changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_error_after_slot_admission_records_run_started_at
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_error_after_slot_admission_records_run_started_at changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_linked_repo_prep_failure_stops_before_execution
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_linked_repo_prep_failure_stops_before_execution changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_killed_while_waiting_does_not_record_run_started_at
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_killed_while_waiting_does_not_record_run_started_at changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_runner_passes_recorded_run_started_at_to_runtime_formatter
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_runner_passes_recorded_run_started_at_to_runtime_formatter changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_system_exit_from_execution_writes_failure_marker_and_notifies
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_system_exit_from_execution_writes_failure_marker_and_notifies changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_home_mode_running_marker_cleanup_updates_artifact_index
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_home_mode_running_marker_cleanup_updates_artifact_index changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
    next(it)

-- Docs: https://docs.pytest.org/en/stable/how-to/capture-warnings.html
============================= slowest 20 durations =============================
105.71s call     tests/sdd/test_git_identity_fixture.py::test_sdd_git_identity_survives_empty_home_subprocess
90.04s call     tests/history/test_continuation_replay_hydration.py::test_hundred_handoff_from_final_monitor_result_grows_linearly
67.31s call     tests/fakey/test_monitor_capacity_e2e.py::test_weight_two_land_family_retains_one_claim_through_real_dispatch_and_delayed_child_bootstrap
64.16s call     tests/test_check_feature_flags_tool_run.py::test_static_main_ignores_exploding_bd_command
63.33s call     tests/test_contract_manifest.py::test_contract_manifest_matches_marker_selection
56.56s call     tests/test_check_feature_flags_tool_run.py::test_main_static_on_repo_exits_zero
29.57s call     tests/pager/test_rendered_link_contract.py::test_kitchen_follow_copy_edit_and_media_for_each_supported_action
22.64s call     tests/test_agent_artifact_directory_operation_audit.py::test_artifact_directory_operation_sites_are_reviewed
21.65s call     tests/fakey/test_pipe_e2e.py::test_two_link_chain_then_bound_leaves_the_agent_running
18.53s call     tests/gate_conformance/test_gate_shell_conformance.py::test_shell_gate_settles_identically_across_every_surface
17.83s call     tests/fakey/test_provider_drain_e2e.py::test_provider_drain_e2e_flag_on_relaunches_stranded_agent
17.81s call     tests/workspace_provider/test_primary_writable_store_import_boundary.py::test_writable_store_resolution_importers_match_the_audited_allowlist
17.41s call     tests/ace/tui/test_deleted_proc_queue_imports.py::test_tests_do_not_import_deleted_proc_queue_module
16.86s call     tests/ace/tui/test_plugins_browser_pane_sase_update.py::test_updates_pane_sase_update_noop_closes_without_restart
16.32s call     tests/test_commit_workflow_bead_lifecycle_e2e.py::test_stitch_create_requires_keep_then_closes_only_assigned_phase
14.00s call     tests/test_config_reader_probe.py::test_cross_test_config_reader_is_reported_as_poisoning
13.58s call     tests/ace/tui/test_agents_filter_bar_session.py::test_circumflex_history_replaces_the_live_edit_while_the_bar_is_open
13.33s call     tests/ace/tui/test_agents_panel_fold_mounted.py::test_mounted_clan_fold_chords_zoom_and_patch_isolation
13.29s call     tests/test_markdown_print_width.py::test_no_function_parameter_defaults_to_the_width
12.61s call     tests/ace/tui/test_artifacts_scaffold.py::test_number_keys_jump_artifacts_without_entering_from_other_tabs
=========================== short test summary info ============================
FAILED tests/doctor/test_checks_axe.py::test_unsafe_axe_systemd_scope_matrix[0::/user.slice/user-1000.slice/user@1000.service/app.slice/tmux-spawn-example.scope\n-True-tmux-spawn-example.scope] - AssertionError: assert None == 'tmux-spawn-example.scope'
 +  where None = unsafe_axe_systemd_scope(123, proc_root=PosixPath('/var/tmp/sase-02a72d87/pytest-of-bryan/pytest-9/popen-gw3/test_unsafe_axe_systemd_scope_0/proc'))
FAILED tests/ace/tui/test_feature_flags_pane.py::test_confirmed_toggle_restarts_axe_and_suppresses_duplicates - AssertionError: assert False is True
 +  where False = FeatureFlagsPane(id='flags', classes='-embedded')._mutating
==== 2 failed, 43254 passed, 14 skipped, 86 warnings in 1250.24s (0:20:50) =====
error: recipe `test-scoped` failed on line 475 with exit code 1
error: recipe `check` failed on line 701 with exit code 1

