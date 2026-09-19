# Chat History - ace-run (sase-11l.11.5.1--mon-0)

- **TIMESTAMP:** 2026-09-19 05:47:52 EDT
- **MODEL:** grok/grok-4.6
- **AGENT:** sase-11l.11.5.1--mon-0

## Prompt

sase monitor start --command '/tmp/sase-11l.11.5.1-verify.sh' --reason 'Rebuild sase-core-rs at re-ratcheted pin 44b82c3e392b and verify hold-deadlock tests plus just check for sase-11l.11.5.1'

## Response

=== pin file ===
44b82c3e392bb4642fbb909a2d656b8e94d2cadd
=== remote head vs pin ===
sase-core-revision.txt already matches sase-core HEAD 44b82c3e392bb4642fbb909a2d656b8e94d2cadd
PIN=44b82c3e392bb4642fbb909a2d656b8e94d2cadd
=== ancestry ok ===
=== install ===
[install] Installing local sase_core_rs from /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/sase/repos/linked/sase-core for local dev.
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
   Compiling unicode-ident v1.0.24
   Compiling quote v1.0.45
   Compiling libc v0.2.186
   Compiling cfg-if v1.0.4
   Compiling itoa v1.0.18
   Compiling pin-project-lite v0.2.17
   Compiling bytes v1.11.1
   Compiling find-msvc-tools v0.1.9
   Compiling once_cell v1.21.4
   Compiling shlex v1.3.0
   Compiling futures-core v0.3.32
   Compiling stable_deref_trait v1.2.1
   Compiling target-lexicon v0.12.16
   Compiling version_check v0.9.5
   Compiling autocfg v1.5.0
   Compiling serde_core v1.0.228
   Compiling log v0.4.29
   Compiling hashbrown v0.17.0
   Compiling equivalent v1.0.2
   Compiling zerocopy v0.8.48
   Compiling smallvec v1.15.1
   Compiling httparse v1.10.1
   Compiling serde v1.0.228
   Compiling memchr v2.8.0
   Compiling litemap v0.8.2
   Compiling tower-service v0.3.3
   Compiling futures-task v0.3.32
   Compiling slab v0.4.12
   Compiling untrusted v0.9.0
   Compiling writeable v0.6.3
   Compiling zmij v1.0.21
   Compiling utf8_iter v1.0.4
   Compiling icu_normalizer_data v2.2.0
   Compiling icu_properties_data v2.2.0
   Compiling serde_json v1.0.149
   Compiling httpdate v1.0.3
   Compiling fnv v1.0.7
   Compiling typenum v1.20.0
   Compiling rustls v0.21.12
   Compiling bitflags v2.11.1
   Compiling vcpkg v0.2.15
   Compiling ryu v1.0.23
   Compiling pkg-config v0.3.33
   Compiling futures-sink v0.3.32
   Compiling percent-encoding v2.3.2
   Compiling rustix v1.1.4
   Compiling thiserror v2.0.18
   Compiling rustversion v1.0.22
   Compiling tower-layer v0.3.3
   Compiling powerfmt v0.2.0
   Compiling try-lock v0.2.5
   Compiling getrandom v0.4.2
   Compiling time-core v0.1.8
   Compiling num-conv v0.2.1
   Compiling linux-raw-sys v0.12.1
   Compiling mime v0.3.17
   Compiling thiserror v1.0.69
   Compiling sync_wrapper v1.0.2
   Compiling regex-syntax v0.8.10
   Compiling atomic-waker v1.1.2
    Building [                           ] 0/242: writeable, pin-project-lite…    Building [                           ] 1/242: writeable, pin-project-lite…    Building [                           ] 2/242: writeable, pin-project-lite…    Building [                           ] 3/242: writeable, pin-project-lite…    Building [                           ] 4/242: writeable, pin-project-lite…   Compiling heck v0.5.0
    Building [                           ] 5/242: writeable, pin-project-lite…    Building [                           ] 6/242: writeable, pin-project-lite…    Building [                           ] 7/242: writeable, pin-project-lite…    Building [                           ] 8/242: writeable, pin-project-lite…    Building [>                          ] 9/242: writeable, pin-project-lite…   Compiling base64 v0.21.7
    Building [>                         ] 10/242: writeable, pin-project-lite…    Building [>                         ] 11/242: writeable, pin-project-lite…    Building [>                         ] 12/242: writeable, pin-project-lite…    Building [>                         ] 13/242: writeable, pin-project-lite…    Building [>                         ] 14/242: writeable, pin-project-lite…   Compiling fastrand v2.4.1
    Building [>                         ] 15/242: writeable, pin-project-lite…    Building [>                         ] 16/242: writeable, pin-project-lite…    Building [>                         ] 17/242: writeable, pin-project-lite…    Building [>                         ] 18/242: writeable, pin-project-lite…   Compiling cpufeatures v0.2.17
    Building [=>                        ] 19/242: writeable, pin-project-lite…    Building [=>                        ] 20/242: writeable, pin-project-lite…    Building [=>                        ] 21/242: writeable, pin-project-lite…   Compiling fallible-iterator v0.3.0
    Building [=>                        ] 22/242: writeable, pin-project-lite…    Building [=>                        ] 23/242: writeable, pin-project-lite…    Building [=>                        ] 24/242: writeable, pin-project-lite…    Building [=>                        ] 25/242: writeable, pin-project-lite…    Building [=>                        ] 26/242: writeable, pin-project-lite…    Building [=>                        ] 27/242: writeable, pin-project-lite…    Building [==>                       ] 28/242: writeable, pin-project-lite…    Building [==>                       ] 29/242: writeable, pin-project-lite…    Building [==>                       ] 30/242: writeable, pin-project-lite…   Compiling base64 v0.22.1
    Building [==>                       ] 31/242: writeable, pin-project-lite…   Compiling cc v1.2.61
    Building [==>                       ] 32/242: writeable, pin-project-lite…   Compiling unsafe-libyaml v0.2.11
    Building [==>                       ] 33/242: writeable, pin-project-lite…   Compiling http v1.4.0
    Building [==>                       ] 34/242: writeable, linux-raw-sys, t…   Compiling fallible-streaming-iterator v0.1.9
    Building [==>                       ] 35/242: writeable, linux-raw-sys, t…   Compiling iana-time-zone v0.1.65
    Building [==>                       ] 36/242: writeable, linux-raw-sys, t…   Compiling want v0.3.1
    Building [==>                       ] 37/242: writeable, linux-raw-sys, z…   Compiling encoding_rs v0.8.35
    Building [===>                      ] 38/242: writeable, linux-raw-sys, z…   Compiling generic-array v0.14.7
    Building [===>                      ] 39/242: writeable, linux-raw-sys, z…   Compiling futures-channel v0.3.32
    Building [===>                      ] 40/242: writeable, linux-raw-sys, f…   Compiling ahash v0.8.12
    Building [===>                      ] 41/242: writeable, linux-raw-sys, f…   Compiling webpki-roots v0.25.4
    Building [===>                      ] 42/242: writeable, linux-raw-sys, f…   Compiling ipnet v2.12.0
    Building [===>                      ] 43/242: writeable, linux-raw-sys, f…   Compiling hex v0.4.3
    Building [===>                      ] 44/242: writeable, linux-raw-sys, f…   Compiling tracing-core v0.1.36
    Building [===>                      ] 45/242: writeable, linux-raw-sys, f…   Compiling sync_wrapper v0.1.2
   Compiling num-traits v0.2.19
    Building [====>                     ] 47/242: writeable, linux-raw-sys, f…   Compiling memoffset v0.9.1
    Building [====>                     ] 48/242: writeable, linux-raw-sys, f…   Compiling matchit v0.7.3
    Building [====>                     ] 49/242: writeable, linux-raw-sys, f…    Building [====>                     ] 50/242: writeable, linux-raw-sys, f…   Compiling indexmap v2.14.0
    Building [====>                     ] 51/242: writeable, linux-raw-sys, f…   Compiling unicode-width v0.2.2
    Building [====>                     ] 52/242: writeable, linux-raw-sys, u…   Compiling indoc v2.0.7
    Building [====>                     ] 53/242: writeable, linux-raw-sys, u…   Compiling unindent v0.2.4
    Building [====>                     ] 54/242: writeable, unindent, linux-…    Building [====>                     ] 55/242: writeable, unindent, linux-…   Compiling http v0.2.12
    Building [=====>                    ] 56/242: writeable, unindent, linux-…    Building [=====>                    ] 57/242: writeable, unindent, linux-…   Compiling form_urlencoded v1.2.2
    Building [=====>                    ] 58/242: writeable, unindent, linux-…    Building [=====>                    ] 59/242: writeable, unindent, linux-…    Building [=====>                    ] 60/242: writeable, unindent, linux-…    Building [=====>                    ] 61/242: writeable, unindent, linux-…    Building [=====>                    ] 62/242: writeable, unindent, linux-…    Building [=====>                    ] 63/242: writeable, unindent, linux-…    Building [=====>                    ] 64/242: writeable, unindent, unicod…    Building [=====>                    ] 65/242: writeable, unindent, unicod…    Building [======>                   ] 66/242: writeable, unindent, unicod…    Building [======>                   ] 67/242: writeable, unindent, unicod…   Compiling deranged v0.5.8
    Building [======>                   ] 68/242: writeable, unindent, unicod…    Building [======>                   ] 69/242: writeable, unindent, unicod…    Building [======>                   ] 70/242: writeable, unindent, unicod…    Building [======>                   ] 71/242: writeable, unindent, unicod…    Building [======>                   ] 72/242: writeable, unindent, unicod…    Building [======>                   ] 73/242: writeable, unindent, unicod…   Compiling futures-util v0.3.32
    Building [=======>                  ] 75/242: writeable, unindent, unicod…    Building [=======>                  ] 76/242: writeable, unindent, unicod…   Compiling rustls-pemfile v1.0.4
    Building [=======>                  ] 77/242: writeable, unindent, unicod…    Building [=======>                  ] 78/242: writeable, unindent, unicod…    Building [=======>                  ] 79/242: writeable, unindent, unicod…    Building [=======>                  ] 80/242: writeable, unindent, unicod…    Building [=======>                  ] 81/242: writeable, unindent, unicod…    Building [=======>                  ] 82/242: unindent, unicode-width, fu…    Building [=======>                  ] 83/242: unindent, unicode-width, fu…    Building [========>                 ] 84/242: unindent, unicode-width, fu…    Building [========>                 ] 85/242: unindent, unicode-width, fu…   Compiling time-macros v0.2.27
    Building [========>                 ] 86/242: unindent, unicode-width, fu…    Building [========>                 ] 87/242: unindent, unicode-width, fu…    Building [========>                 ] 88/242: unindent, unicode-width, fu…    Building [========>                 ] 89/242: unindent, unicode-width, fu…   Compiling pyo3-build-config v0.22.6
    Building [========>                 ] 90/242: unindent, unicode-width, fu…   Compiling aho-corasick v1.1.4
    Building [========>                 ] 91/242: unindent, unicode-width, fu…   Compiling serde_path_to_error v0.1.20
    Building [========>                 ] 92/242: unindent, unicode-width, fu…    Building [========>                 ] 93/242: unindent, unicode-width, fu…    Building [=========>                ] 94/242: unindent, unicode-width, fu…    Building [=========>                ] 95/242: unindent, unicode-width, fu…    Building [=========>                ] 96/242: unindent, unicode-width, fu…    Building [=========>                ] 97/242: unindent, unicode-width, fu…    Building [=========>                ] 98/242: unindent, unicode-width, fu…    Building [=========>                ] 99/242: unindent, unicode-width, fu…    Building [=========>               ] 100/242: unindent, unicode-width, fu…    Building [=========>               ] 101/242: unindent, unicode-width, fu…    Building [=========>               ] 102/242: unindent, unicode-width, fu…    Building [=========>               ] 103/242: unindent, unicode-width, fu…    Building [=========>               ] 104/242: unindent, unicode-width, fu…    Building [=========>               ] 105/242: unindent, unicode-width, fu…   Compiling pem v3.0.6
    Building [==========>              ] 107/242: unindent, unicode-width, tr…    Building [==========>              ] 108/242: unindent, unicode-width, tr…   Compiling errno v0.3.14
   Compiling getrandom v0.2.17
   Compiling socket2 v0.6.3
   Compiling mio v1.2.0
   Compiling socket2 v0.5.10
   Compiling fs2 v0.4.3
    Building [==========>              ] 108/242: unindent, unicode-width, so…    Building [==========>              ] 109/242: unindent, unicode-width, so…   Compiling ring v0.17.14
   Compiling libsqlite3-sys v0.30.1
    Building [==========>              ] 110/242: unindent, ring(build.rs), u…   Compiling ppv-lite86 v0.2.21
    Building [==========>              ] 112/242: unindent, ring(build.rs), u…    Building [==========>              ] 113/242: unindent, ring(build.rs), u…    Building [==========>              ] 114/242: unindent, ring(build.rs), u…    Building [==========>              ] 115/242: unindent, ring(build.rs), u…    Building [==========>              ] 116/242: unindent, ring(build.rs), u…   Compiling tracing v0.1.44
   Compiling http-body v1.0.1
    Building [===========>             ] 118/242: unindent, ring(build.rs), u…    Building [===========>             ] 119/242: unindent, ring(build.rs), u…    Building [===========>             ] 120/242: unindent, ring(build.rs), u…    Building [===========>             ] 121/242: unindent, ring(build.rs), u…    Building [===========>             ] 122/242: unindent, unicode-width, pp…    Building [===========>             ] 123/242: unindent, ppv-lite86, socke…    Building [===========>             ] 124/242: ppv-lite86, socket2, future…    Building [===========>             ] 125/242: ppv-lite86, socket2, future…    Building [============>            ] 126/242: ppv-lite86, socket2, future…    Building [============>            ] 127/242: ppv-lite86, socket2, future…   Compiling http-body v0.4.6
    Building [============>            ] 127/242: ppv-lite86, socket2, http-b…    Building [============>            ] 129/242: ppv-lite86, socket2, http-b…   Compiling crypto-common v0.1.7
   Compiling block-buffer v0.10.4
    Building [============>            ] 130/242: ppv-lite86, socket2, http-b…   Compiling time v0.3.47
    Building [============>            ] 132/242: ppv-lite86, socket2, http-b…    Building [============>            ] 133/242: ppv-lite86, socket2, http-b…    Building [============>            ] 134/242: ppv-lite86, socket2, http-b…   Compiling signal-hook-registry v1.4.8
    Building [============>            ] 135/242: ppv-lite86, socket2, http-b…    Building [=============>           ] 136/242: ppv-lite86, socket2, http-b…   Compiling pyo3-macros-backend v0.22.6
   Compiling pyo3-ffi v0.22.6
   Compiling pyo3 v0.22.6
    Building [=============>           ] 137/242: ppv-lite86, socket2, http-b…   Compiling rand_core v0.6.4
    Building [=============>           ] 138/242: ppv-lite86, socket2, http-b…    Building [=============>           ] 139/242: ppv-lite86, socket2, http-b…    Building [=============>           ] 140/242: ppv-lite86, socket2, http-b…   Compiling tempfile v3.27.0
    Building [=============>           ] 141/242: ppv-lite86, socket2, http-b…    Building [=============>           ] 142/242: ppv-lite86, http-body, cryp…    Building [=============>           ] 143/242: ppv-lite86, http-body, cryp…    Building [=============>           ] 144/242: ppv-lite86, http-body, cryp…    Building [=============>           ] 145/242: ppv-lite86, http-body, cryp…    Building [==============>          ] 146/242: ppv-lite86, http-body, cryp…    Building [==============>          ] 147/242: ppv-lite86, http-body, cryp…    Building [==============>          ] 148/242: ppv-lite86, http-body, cryp…    Building [==============>          ] 149/242: ppv-lite86, http-body, cryp…    Building [==============>          ] 150/242: ppv-lite86, http-body, cryp…   Compiling hashbrown v0.14.5
    Building [==============>          ] 152/242: http-body, crypto-common, t…   Compiling http-body-util v0.1.3
    Building [==============>          ] 153/242: http-body, crypto-common, t…    Building [==============>          ] 154/242: http-body, crypto-common, t…    Building [===============>         ] 155/242: crypto-common, tempfile, ri…    Building [===============>         ] 156/242: crypto-common, tempfile, ri…   Compiling regex-automata v0.4.14
    Building [===============>         ] 157/242: crypto-common, tempfile, ri…    Building [===============>         ] 158/242: crypto-common, tempfile, ri…   Compiling num-integer v0.1.46
   Compiling chrono v0.4.44
    Building [===============>         ] 159/242: crypto-common, tempfile, ri…   Compiling digest v0.10.7
    Building [===============>         ] 160/242: tempfile, ring(build), pyo3…    Building [===============>         ] 161/242: tempfile, ring(build), pyo3…    Building [===============>         ] 162/242: tempfile, ring(build), pyo3…    Building [===============>         ] 163/242: tempfile, pyo3-ffi, regex-a…    Building [===============>         ] 164/242: tempfile, pyo3-ffi, regex-a…    Building [================>        ] 165/242: tempfile, pyo3-ffi, regex-a…   Compiling rand_chacha v0.3.1
    Building [================>        ] 165/242: rand_chacha, tempfile, pyo3…    Building [================>        ] 166/242: rand_chacha, pyo3-ffi, rege…    Building [================>        ] 167/242: rand_chacha, pyo3-ffi, rege…    Building [================>        ] 168/242: rand_chacha, regex-automata…   Compiling hashlink v0.9.1
    Building [================>        ] 169/242: rand_chacha, regex-automata…   Compiling num-bigint v0.4.6
    Building [================>        ] 170/242: rand_chacha, regex-automata…   Compiling tower-http v0.5.2
    Building [================>        ] 170/242: rand_chacha, tower-http, re…    Building [================>        ] 171/242: rand_chacha, tower-http, re…   Compiling sha2 v0.10.9
    Building [================>        ] 172/242: rand_chacha, tower-http, re…    Building [================>        ] 173/242: rand_chacha, tower-http, re…    Building [================>        ] 174/242: rand_chacha, tower-http, re…   Compiling rand v0.8.6
    Building [=================>       ] 175/242: tower-http, regex-automata,…   Compiling rustls-webpki v0.101.7
   Compiling sct v0.7.1
    Building [=================>       ] 175/242: tower-http, sct, regex-auto…    Building [=================>       ] 176/242: tower-http, sct, regex-auto…    Building [=================>       ] 177/242: tower-http, sct, regex-auto…   Compiling regex v1.12.3
    Building [=================>       ] 178/242: tower-http, sct, sha2, quot…   Compiling syn v2.0.117
    Building [=================>       ] 178/242: tower-http, sct, sha2, syn,…    Building [=================>       ] 179/242: tower-http, sct, sha2, syn,…    Building [=================>       ] 180/242: sct, sha2, syn, rand, regex…    Building [=================>       ] 181/242: sha2, syn, rand, regex, rus…    Building [=================>       ] 182/242: syn, rand, regex, rustls-we…    Building [=================>       ] 183/242: syn, regex, rustls-webpki, …    Building [==================>      ] 184/242: syn, rustls-webpki, libsqli…    Building [==================>      ] 184/242: rustls, syn, rustls-webpki,…    Building [==================>      ] 185/242: rustls, syn, libsqlite3-sys…    Building [==================>      ] 186/242: rustls, syn, libsqlite3-sys…   Compiling synstructure v0.13.2
    Building [==================>      ] 186/242: synstructure, pyo3-macros-b…   Compiling zerovec-derive v0.11.3
   Compiling displaydoc v0.2.5
   Compiling tokio-macros v2.7.0
   Compiling serde_derive v1.0.228
   Compiling thiserror-impl v2.0.18
   Compiling async-trait v0.1.89
   Compiling thiserror-impl v1.0.69
   Compiling async-stream-impl v0.3.6
    Building [==================>      ] 187/242: synstructure, pyo3-macros-b…   Compiling async-stream v0.3.6
    Building [==================>      ] 188/242: synstructure, pyo3-macros-b…    Building [==================>      ] 189/242: synstructure, pyo3-macros-b…   Compiling tokio v1.52.2
    Building [==================>      ] 190/242: synstructure, tokio, pyo3-m…   Compiling axum-core v0.4.5
    Building [==================>      ] 191/242: synstructure, tokio, pyo3-m…    Building [==================>      ] 192/242: synstructure, tokio, pyo3-m…    Building [==================>      ] 193/242: synstructure, tokio, pyo3-m…    Building [===================>     ] 194/242: synstructure, tokio, pyo3-m…   Compiling zerofrom-derive v0.1.7
   Compiling yoke-derive v0.8.2
    Building [===================>     ] 195/242: zerofrom-derive, tokio, pyo…    Building [===================>     ] 196/242: zerofrom-derive, tokio, pyo…   Compiling simple_asn1 v0.6.4
    Building [===================>     ] 197/242: zerofrom-derive, tokio, pyo…    Building [===================>     ] 198/242: zerofrom-derive, tokio, pyo…   Compiling zerofrom v0.1.7
    Building [===================>     ] 199/242: tokio, pyo3-macros-backend,…    Building [===================>     ] 200/242: tokio, pyo3-macros-backend,…    Building [===================>     ] 201/242: tokio, pyo3-macros-backend,…   Compiling pyo3-macros v0.22.6
    Building [===================>     ] 202/242: tokio, rustls, serde, simpl…    Building [===================>     ] 203/242: tokio, serde, simple_asn1, …   Compiling yoke v0.8.2
    Building [====================>    ] 204/242: tokio, serde, simple_asn1, …    Building [====================>    ] 205/242: tokio, serde, simple_asn1, …    Building [====================>    ] 206/242: tokio, serde, pyo3, axum-co…   Compiling serde_urlencoded v0.7.1
   Compiling serde_yaml v0.9.34+deprecated
   Compiling jsonwebtoken v9.3.1
    Building [====================>    ] 206/242: tokio, serde_yaml, serde, s…    Building [====================>    ] 207/242: tokio, serde_yaml, serde_ur…    Building [====================>    ] 208/242: tokio, serde_yaml, serde_ur…   Compiling zerovec v0.11.6
   Compiling zerotrie v0.2.4
    Building [====================>    ] 208/242: zerotrie, tokio, serde_yaml…    Building [====================>    ] 209/242: zerotrie, tokio, serde_yaml…    Building [====================>    ] 210/242: zerotrie, tokio, serde_yaml…    Building [====================>    ] 211/242: tokio, serde_yaml, zerovec,…   Compiling tinystr v0.8.3
   Compiling potential_utf v0.1.5
    Building [====================>    ] 211/242: tokio, potential_utf, serde…    Building [====================>    ] 212/242: tokio, potential_utf, serde…   Compiling icu_collections v2.2.0
    Building [=====================>   ] 213/242: tokio, serde_yaml, icu_coll…    Building [=====================>   ] 214/242: tokio, serde_yaml, icu_coll…    Building [=====================>   ] 215/242: tokio, icu_collections, tin…   Compiling icu_locale_core v2.2.0
    Building [=====================>   ] 215/242: icu_locale_core, tokio, icu…    Building [=====================>   ] 216/242: icu_locale_core, tokio, icu…   Compiling tokio-util v0.7.18
   Compiling hyper v1.9.0
   Compiling tokio-rustls v0.24.1
   Compiling tower v0.5.3
    Building [=====================>   ] 216/242: icu_locale_core, hyper, tok…    Building [=====================>   ] 217/242: icu_locale_core, hyper, tok…    Building [=====================>   ] 218/242: icu_locale_core, hyper, tok…    Building [=====================>   ] 219/242: icu_locale_core, hyper, tok…    Building [=====================>   ] 220/242: icu_locale_core, hyper, tok…    Building [=====================>   ] 221/242: icu_locale_core, hyper, tok…   Compiling h2 v0.3.27
    Building [=====================>   ] 221/242: icu_locale_core, hyper, h2,…    Building [=====================>   ] 222/242: icu_locale_core, hyper, h2,…   Compiling icu_provider v2.2.0
    Building [=====================>   ] 222/242: icu_provider, icu_locale_co…    Building [======================>  ] 223/242: icu_provider, hyper, h2, li…   Compiling hyper-util v0.1.20
    Building [======================>  ] 223/242: icu_provider, hyper, h2, hy…    Building [======================>  ] 224/242: icu_provider, h2, hyper-uti…   Compiling icu_normalizer v2.2.0
   Compiling icu_properties v2.2.0
    Building [======================>  ] 224/242: icu_provider, h2, icu_norma…    Building [======================>  ] 225/242: h2, icu_normalizer, icu_pro…    Building [======================>  ] 226/242: h2, libsqlite3-sys, icu_nor…   Compiling axum v0.7.9
    Building [======================>  ] 227/242: h2, libsqlite3-sys, icu_nor…   Compiling rusqlite v0.32.1
    Building [======================>  ] 227/242: h2, rusqlite, libsqlite3-sy…    Building [======================>  ] 228/242: h2, rusqlite, icu_normalize…    Building [======================>  ] 229/242: h2, rusqlite, axum, icu_pro…   Compiling idna_adapter v1.2.2
    Building [======================>  ] 229/242: h2, rusqlite, axum, idna_ad…    Building [======================>  ] 230/242: h2, rusqlite, axum, idna_ad…   Compiling idna v1.1.0
    Building [======================>  ] 231/242: h2, rusqlite, axum, idna       Compiling sase_core v0.34.62 (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/sase/repos/linked/sase-core/crates/sase_core)
    Building [======================>  ] 231/242: sase_core, h2, rusqlite, ax…    Building [======================>  ] 232/242: sase_core, h2, axum, idna      Compiling url v2.5.8
    Building [======================>  ] 232/242: url, sase_core, h2, axum, i…    Building [=======================> ] 233/242: url, sase_core, h2, axum       Compiling hyper v0.14.32
    Building [=======================> ] 233/242: url, sase_core, hyper, h2, …    Building [=======================> ] 234/242: url, sase_core, hyper, axum     Building [=======================> ] 235/242: sase_core, hyper, axum          Building [=======================> ] 236/242: sase_core, hyper               Compiling hyper-rustls v0.24.2
    Building [=======================> ] 236/242: sase_core, hyper-rustls, hy…    Building [=======================> ] 237/242: sase_core, hyper-rustls        Compiling reqwest v0.11.27
    Building [=======================> ] 237/242: sase_core, hyper-rustls, re…    Building [=======================> ] 238/242: sase_core, reqwest              Building [=======================> ] 239/242: sase_core                      Compiling sase_gateway v0.34.62 (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/sase/repos/linked/sase-core/crates/sase_gateway)
    Building [=======================> ] 239/242: sase_gateway, sase_core         Building [=======================> ] 240/242: sase_gateway                   Compiling sase_core_py v0.34.62 (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/sase/repos/linked/sase-core/crates/sase_core_py)
    Building [=======================> ] 241/242: sase_core_py                    Finished `release` profile [optimized] target(s) in 11m 04s
📦 Built wheel for abi3 Python ≥ 3.12 to /home/bryan/.cache/sase/tmp/agent-tmp/gh_sase-org__sase-ws10-260919_050037/.tmpoVRXW9/sase_core_rs-0.34.62-cp312-abi3-linux_x86_64.whl
✏️ Setting installed package as editable
🛠 Installed sase-core-rs-0.34.62
🍹 Building a mixed python/rust project
🐍 Found CPython 3.14 at /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/bin/python
🔗 Found pyo3 bindings with abi3-py3.12 support
📡 Using build options features from pyproject.toml
    Finished `release` profile [optimized] target(s) in 0.13s
📦 Built wheel for abi3 Python ≥ 3.12 to /home/bryan/.sase/cache/sase-core-wheels/.build-zztcvo80/sase_core_rs-0.34.62-cp312-abi3-manylinux_2_39_x86_64.whl
/home/bryan/.sase/cache/sase-core-wheels/e0ccf59ecfdb24b9f7428934188729d1edff34e9d30f15b18cec3fedce805491/sase_core_rs-0.34.62-cp312-abi3-manylinux_2_39_x86_64.whl
# Keep the LSP server in lockstep with the extension: both are built
# from the same sase-core checkout, and the ACE/LSP parity tests
# compare their directive contracts.
   Compiling sase_core v0.34.62 (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/sase/repos/linked/sase-core/crates/sase_core)
    Building [=======================> ] 145/148: sase_core                      Compiling sase_xprompt_lsp v0.34.62 (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/sase/repos/linked/sase-core/crates/sase_xprompt_lsp)
    Building [=======================> ] 145/148: sase_xprompt_lsp, sase_core     Building [=======================> ] 146/148: sase_xprompt_lsp                Building [=======================> ] 147/148: sase-xprompt-lsp(bin)           Finished `dev-update` profile [optimized] target(s) in 1m 39s
[rust-lsp-install] installed /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/bin/sase-xprompt-lsp
uv pip install --python .venv/bin/python --no-sources $(just _core-overrides-arg) -e ".[dev]"
Resolved 98 packages in 288ms
   Building sase @ file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10
      Built sase @ file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10
Prepared 1 package in 504ms
Uninstalled 1 package in 4ms
Installed 1 package in 10ms
 ~ sase==0.17.1 (from file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10)
.venv/bin/python tools/setup_required_plugins
[setup] Installing required plugin sase-github>=0.2.5.
[setup] Installing required plugin sase-research-artifacts>=0.2.0.
=== binding ===
file /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/sase/repos/linked/sase-core/crates/sase_core_py/python/sase_core_rs/__init__.py
version 0.34.62
binding <built-in function agent_hold_deadlock_reaches>
=== focused tests ===
[setup] fast-forwarded /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/sase/repos/linked/sase-core to origin/master
[validate_sase_core_rs] installed sase-core-rs distribution version 0.34.62 disagrees with the /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/sase/repos/linked/sase-core/Cargo.toml checkout version 0.34.63; the checkout moved and the extension was not rebuilt. Run `just install`.
[setup] Rebuilding stale or missing sase_core_rs from /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/sase/repos/linked/sase-core before Python dependency resolution.
# Harden cargo crate downloads against transient crates.io flakiness.
# CI has hit `curl ... [16] Error in the HTTP2 framing layer` while
# maturin's `cargo metadata` fetches deps; disabling HTTP/2 multiplexing
# and raising the retry count makes the download resilient. Both are
# overridable from the environment.
[rust-install] Installing cached sase_core_rs wheel from /home/bryan/.sase/cache/sase-core-wheels/c3c4a240bd4ab5cd9d2ad8170b002fd0bc3233e03bae4a72ea6767185db9e33a/sase_core_rs-0.34.63-cp312-abi3-manylinux_2_39_x86_64.whl.
Resolved 1 package in 1ms
Prepared 1 package in 107ms
Uninstalled 1 package in 0.52ms
Installed 1 package in 1ms
 - sase-core-rs==0.34.62 (from file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/sase/repos/linked/sase-core/crates/sase_core_py)
 + sase-core-rs==0.34.63 (from file:///home/bryan/.sase/cache/sase-core-wheels/c3c4a240bd4ab5cd9d2ad8170b002fd0bc3233e03bae4a72ea6767185db9e33a/sase_core_rs-0.34.63-cp312-abi3-manylinux_2_39_x86_64.whl)
# Keep the LSP server in lockstep with the extension: both are built
# from the same sase-core checkout, and the ACE/LSP parity tests
# compare their directive contracts.
   Compiling sase_core v0.34.63 (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/sase/repos/linked/sase-core/crates/sase_core)
    Building [=======================> ] 145/148: sase_core                      Compiling sase_xprompt_lsp v0.34.63 (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/sase/repos/linked/sase-core/crates/sase_xprompt_lsp)
    Building [=======================> ] 145/148: sase_xprompt_lsp, sase_core     Building [=======================> ] 146/148: sase_xprompt_lsp                Building [=======================> ] 147/148: sase-xprompt-lsp(bin)           Finished `dev-update` profile [optimized] target(s) in 1m 33s
[rust-lsp-install] installed /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/bin/sase-xprompt-lsp
.venv/bin/python tools/setup_required_plugins
[setup] Installing required plugin sase-github>=0.2.5.
[setup] Installing required plugin sase-research-artifacts>=0.2.0.

┌───────────────────────────────────────────────────────┐
│                RUNNING: just test                     │
└───────────────────────────────────────────────────────┘

---------- Running pytest (parallel, no coverage)... ----------
============================= test session starts ==============================
platform linux -- Python 3.14.7, pytest-9.0.2, pluggy-1.6.0
rootdir: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10
configfile: pyproject.toml
plugins: cov-7.0.0, asyncio-1.3.0, hypothesis-6.151.9, xdist-3.8.0, inline-snapshot-0.32.5, mock-3.15.1
asyncio: mode=Mode.AUTO, debug=False, asyncio_default_fixture_loop_scope=None, asyncio_default_test_loop_scope=function
created: 14/14 workers
14 workers [14 items]

..............                                                           [100%]

═══════════════════════════════ inline-snapshot ════════════════════════════════
INFO: CI run was detected because environment variable "CI" was defined. 
inline-snapshot runs with --inline-snapshot=disable by default in CI. This means
that tests with snapshots will continue to run, but snapshot(x) will only return
x and inline-snapshot will not be able to fix snapshots or generate reports. You
can change this by using --inline-snapshot=report for example.


============================= slowest 20 durations =============================
1.70s setup    tests/test_run_agent_wait_slot_hold_deadlock.py::test_hood_cutoff_ignores_members_launched_after_the_waiter
1.70s setup    tests/test_run_agent_wait_slot_hold_deadlock.py::test_settled_branch_is_not_a_mutual_block
1.69s setup    tests/test_run_agent_wait_slot_hold_deadlock.py::test_no_deadlock_for_non_agent_armer_kinds
1.68s setup    tests/test_run_agent_wait_slot_hold_deadlock.py::test_longer_cycle_with_repeated_vertices_still_reaches
1.45s setup    tests/test_run_agent_wait_slot_hold_deadlock.py::test_direct_deadlock_returns_the_armer_record
1.45s setup    tests/test_run_agent_wait_slot_hold_deadlock.py::test_transitive_deadlock_walks_the_armers_own_wait_set
1.32s setup    tests/test_run_agent_wait_slot_hold_deadlock.py::test_no_deadlock_when_hold_is_not_found
1.28s setup    tests/test_run_agent_wait_slot_hold_deadlock.py::test_cli_and_directive_holds_exercise_family_identity
1.23s setup    tests/test_run_agent_wait_slot_hold_deadlock.py::test_cycle_in_wait_chain_does_not_loop_forever
1.22s setup    tests/test_run_agent_wait_slot_hold_deadlock.py::test_hood_mediated_cycle_uses_wait_for_hoods
1.22s setup    tests/test_run_agent_wait_slot_hold_deadlock.py::test_no_deadlock_when_armer_is_running
1.21s setup    tests/test_run_agent_wait_slot_hold_deadlock.py::test_branched_cycle_visits_the_second_wait_branch
1.20s setup    tests/test_run_agent_wait_slot_hold_deadlock.py::test_family_wait_name_matches_role_suffixed_candidate
1.20s setup    tests/test_run_agent_wait_slot_hold_deadlock.py::test_no_deadlock_when_armer_is_not_waiting_on_the_candidate
0.09s call     tests/test_run_agent_wait_slot_hold_deadlock.py::test_cli_and_directive_holds_exercise_family_identity

(5 durations < 0.005s hidden.  Use -vv to show these durations.)
============================== 14 passed in 4.95s ==============================
sase-core pin ratchet 44b82c3e392b -> 39602c950f88 pending
HEAD moved after tests; re-ratcheting and rebuilding
sase-core pin ratchet 44b82c3e392b -> 39602c950f88 applied
PIN=39602c950f8882d71dab1e3b74c17d2751e8b1cf
=== ancestry ok ===
=== install ===
[install] Installing local sase_core_rs from /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/sase/repos/linked/sase-core for local dev.
# Harden cargo crate downloads against transient crates.io flakiness.
# CI has hit `curl ... [16] Error in the HTTP2 framing layer` while
# maturin's `cargo metadata` fetches deps; disabling HTTP/2 multiplexing
# and raising the retry count makes the download resilient. Both are
# overridable from the environment.
[rust-install] Installing cached sase_core_rs wheel from /home/bryan/.sase/cache/sase-core-wheels/c3c4a240bd4ab5cd9d2ad8170b002fd0bc3233e03bae4a72ea6767185db9e33a/sase_core_rs-0.34.63-cp312-abi3-manylinux_2_39_x86_64.whl.
Resolved 1 package in 1ms
Prepared 1 package in 0.35ms
Uninstalled 1 package in 0.69ms
Installed 1 package in 8ms
 ~ sase-core-rs==0.34.63 (from file:///home/bryan/.sase/cache/sase-core-wheels/c3c4a240bd4ab5cd9d2ad8170b002fd0bc3233e03bae4a72ea6767185db9e33a/sase_core_rs-0.34.63-cp312-abi3-manylinux_2_39_x86_64.whl)
# Keep the LSP server in lockstep with the extension: both are built
# from the same sase-core checkout, and the ACE/LSP parity tests
# compare their directive contracts.
    Finished `dev-update` profile [optimized] target(s) in 0.15s
[rust-lsp-install] installed /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/bin/sase-xprompt-lsp
uv pip install --python .venv/bin/python --no-sources $(just _core-overrides-arg) -e ".[dev]"
Resolved 98 packages in 11ms
   Building sase @ file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10
      Built sase @ file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10
Prepared 1 package in 447ms
Uninstalled 1 package in 2ms
Installed 1 package in 8ms
 ~ sase==0.17.1 (from file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10)
.venv/bin/python tools/setup_required_plugins
[setup] Installing required plugin sase-github>=0.2.5.
[setup] Installing required plugin sase-research-artifacts>=0.2.0.
=== binding ===
file /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/lib/python3.14/site-packages/sase_core_rs/__init__.py
version 0.34.63
binding <built-in function agent_hold_deadlock_reaches>
=== focused tests ===
.venv/bin/python tools/setup_required_plugins
[setup] Installing required plugin sase-github>=0.2.5.
[setup] Installing required plugin sase-research-artifacts>=0.2.0.

┌───────────────────────────────────────────────────────┐
│                RUNNING: just test                     │
└───────────────────────────────────────────────────────┘

---------- Running pytest (parallel, no coverage)... ----------
============================= test session starts ==============================
platform linux -- Python 3.14.7, pytest-9.0.2, pluggy-1.6.0
rootdir: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10
configfile: pyproject.toml
plugins: cov-7.0.0, asyncio-1.3.0, hypothesis-6.151.9, xdist-3.8.0, inline-snapshot-0.32.5, mock-3.15.1
asyncio: mode=Mode.AUTO, debug=False, asyncio_default_fixture_loop_scope=None, asyncio_default_test_loop_scope=function
created: 14/14 workers
14 workers [14 items]

..............                                                           [100%]

═══════════════════════════════ inline-snapshot ════════════════════════════════
INFO: CI run was detected because environment variable "CI" was defined. 
inline-snapshot runs with --inline-snapshot=disable by default in CI. This means
that tests with snapshots will continue to run, but snapshot(x) will only return
x and inline-snapshot will not be able to fix snapshots or generate reports. You
can change this by using --inline-snapshot=report for example.


============================= slowest 20 durations =============================
1.31s setup    tests/test_run_agent_wait_slot_hold_deadlock.py::test_hood_cutoff_ignores_members_launched_after_the_waiter
1.30s setup    tests/test_run_agent_wait_slot_hold_deadlock.py::test_direct_deadlock_returns_the_armer_record
1.22s setup    tests/test_run_agent_wait_slot_hold_deadlock.py::test_settled_branch_is_not_a_mutual_block
1.21s setup    tests/test_run_agent_wait_slot_hold_deadlock.py::test_no_deadlock_for_non_agent_armer_kinds
1.20s setup    tests/test_run_agent_wait_slot_hold_deadlock.py::test_cli_and_directive_holds_exercise_family_identity
1.20s setup    tests/test_run_agent_wait_slot_hold_deadlock.py::test_family_wait_name_matches_role_suffixed_candidate
1.19s setup    tests/test_run_agent_wait_slot_hold_deadlock.py::test_cycle_in_wait_chain_does_not_loop_forever
1.19s setup    tests/test_run_agent_wait_slot_hold_deadlock.py::test_transitive_deadlock_walks_the_armers_own_wait_set
1.18s setup    tests/test_run_agent_wait_slot_hold_deadlock.py::test_hood_mediated_cycle_uses_wait_for_hoods
1.18s setup    tests/test_run_agent_wait_slot_hold_deadlock.py::test_no_deadlock_when_armer_is_not_waiting_on_the_candidate
1.16s setup    tests/test_run_agent_wait_slot_hold_deadlock.py::test_no_deadlock_when_armer_is_running
1.16s setup    tests/test_run_agent_wait_slot_hold_deadlock.py::test_no_deadlock_when_hold_is_not_found
1.15s setup    tests/test_run_agent_wait_slot_hold_deadlock.py::test_branched_cycle_visits_the_second_wait_branch
1.14s setup    tests/test_run_agent_wait_slot_hold_deadlock.py::test_longer_cycle_with_repeated_vertices_still_reaches
0.09s call     tests/test_run_agent_wait_slot_hold_deadlock.py::test_cli_and_directive_holds_exercise_family_identity

(5 durations < 0.005s hidden.  Use -vv to show these durations.)
============================== 14 passed in 4.59s ==============================
sase-core-revision.txt already matches sase-core HEAD 39602c950f8882d71dab1e3b74c17d2751e8b1cf
=== ratchet --check ===
sase-core-revision.txt already matches sase-core HEAD 39602c950f8882d71dab1e3b74c17d2751e8b1cf
=== lockfile untouched ===
=== just check ===
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
[core-floor-probe] stale_actionable: sase-core-rs==0.34.48 is missing 7 capability(s) that exist in a published sase-core release.
[core-floor-probe] agent_hold_deadlock_reaches: first appears in sase-core 0a7301c (feat(hold): walk every wait branch for hold deadlock reachability); release v0.34.62 contains it.
[core-floor-probe] agent_hold_summarize_capture: first appears in sase-core 6fe31cb (feat(hold): persist capture summaries and return prune evidence); release v0.34.61 contains it.
[core-floor-probe] bead_set_link_projections: first appears in sase-core d32591f (feat(bead): add atomic bulk link-projection mutation); release v0.34.53 contains it.
[core-floor-probe] select_remaining_commit_obligations: first appears in sase-core 8d5341a (feat(finalizer): select remaining declared repos after repair); release v0.34.53 contains it.
[core-floor-probe] sudo_authorize_settlement: first appears in sase-core 9e1ab3f (feat(sudo): add completion authorization core contracts); release v0.34.54 contains it.
[core-floor-probe] sudo_classify_attempt_liveness: first appears in sase-core 9e1ab3f (feat(sudo): add completion authorization core contracts); release v0.34.54 contains it.
[core-floor-probe] sudo_validate_handshake: first appears in sase-core b70e64d (feat(sudo): add detached runner execution); release v0.34.52 contains it.
{"cache_hit": true, "capabilities": [{"commit": "0a7301c", "name": "agent_hold_deadlock_reaches", "release": "v0.34.62", "subject": "feat(hold): walk every wait branch for hold deadlock reachability"}, {"commit": "6fe31cb", "name": "agent_hold_summarize_capture", "release": "v0.34.61", "subject": "feat(hold): persist capture summaries and return prune evidence"}, {"commit": "d32591f", "name": "bead_set_link_projections", "release": "v0.34.53", "subject": "feat(bead): add atomic bulk link-projection mutation"}, {"commit": "8d5341a", "name": "select_remaining_commit_obligations", "release": "v0.34.53", "subject": "feat(finalizer): select remaining declared repos after repair"}, {"commit": "9e1ab3f", "name": "sudo_authorize_settlement", "release": "v0.34.54", "subject": "feat(sudo): add completion authorization core contracts"}, {"commit": "9e1ab3f", "name": "sudo_classify_attempt_liveness", "release": "v0.34.54", "subject": "feat(sudo): add completion authorization core contracts"}, {"commit": "b70e64d", "name": "sudo_validate_handshake", "release": "v0.34.52", "subject": "feat(sudo): add detached runner execution"}], "declared_floor": "0.34.48", "exit_code": 3, "message": "sase-core-rs==0.34.48 is missing 7 capability(s) that exist in a published sase-core release.", "status": "stale_actionable"}
✓ committed plans
✗ test (scoped)
.venv/bin/python tools/setup_required_plugins
[setup] Installing required plugin sase-github>=0.2.5.
[setup] Installing required plugin sase-research-artifacts>=0.2.0.

┌───────────────────────────────────────────────────────┐
│                RUNNING: just test-scoped              │
└───────────────────────────────────────────────────────┘

---------- Running diff-scoped pytest selection... ----------
test selection escalated to the full suite (rules: contract-set-only, core-identity-changed); 4006 test files in scope
coverage contexts: not consulted — the run escalates to the full suite, so ground truth had nothing to add
escalating to the governed full test lane (rules: contract-set-only, core-identity-changed)
============================= test session starts ==============================
platform linux -- Python 3.14.7, pytest-9.0.2, pluggy-1.6.0
rootdir: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10
configfile: pyproject.toml
testpaths: tests
plugins: cov-7.0.0, asyncio-1.3.0, hypothesis-6.151.9, xdist-3.8.0, inline-snapshot-0.32.5, mock-3.15.1
asyncio: mode=Mode.AUTO, debug=False, asyncio_default_fixture_loop_scope=None, asyncio_default_test_loop_scope=function
created: 6/6 workers
6 workers [43347 items]

........................................................................ [  0%]
........................................................................ [  0%]
........................................................................ [  0%]
.................................s...................................... [  0%]
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
........................s............................................... [  3%]
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
.s...................................................................... [  7%]
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
............................................................s........... [ 10%]
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
....................................................s................... [ 20%]
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
.............................................s.......................... [ 26%]
.....ss................................................................. [ 26%]
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
........................................................................ [ 39%]
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
........................................................................ [ 54%]
........................................................................ [ 54%]
........................................................................ [ 54%]
........................................................................ [ 54%]
........................................................................ [ 54%]
........................................................................ [ 54%]
........................................................................ [ 55%]
.........................................s.............................. [ 55%]
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
....................................................................ssss [ 63%]
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
........................................................................ [ 67%]
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
....................................................s................... [ 73%]
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
........................................................................ [ 76%]
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
........................................................................ [ 81%]
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
......................F................................................. [ 88%]
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
........................................................................ [ 97%]
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
...                                                                      [100%]/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/lib/python3.14/site-packages/_pytest/unraisableexception.py:67: PytestUnraisableExceptionWarning: Exception ignored while calling GC callback <function gc_cumulative_time.<locals>.gc_callback at 0x7f8f194d7a00>: None

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
_________ test_context_assembles_dynamic_document_role_and_namespaces __________
[gw1] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/bin/python

monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7f0e7043cc20>
tmp_path = PosixPath('/var/tmp/sase-02a72d87/pytest-of-bryan/pytest-12/popen-gw1/test_context_assembles_dynamic0')

    def test_context_assembles_dynamic_document_role_and_namespaces(
        monkeypatch: pytest.MonkeyPatch,
        tmp_path: Path,
    ) -> None:
        class _Store:
            def split_sidecar_roles(self) -> tuple[str, ...]:
                return ("plans", "designs", "beads")
    
            def kind_root(self, role: str) -> Path:
                if role == "designs":
                    return tmp_path / "missing-designs-clone"
                if role == "plans":
                    return tmp_path / "repo-plans"
                raise ValueError(role)
    
        repo = SimpleNamespace(name="sase", slug="sase-org/sase", kind="primary")
        inventory = SimpleNamespace(records=(repo,))
        project_record = SimpleNamespace(
            project_name="gh_sase-org__sase",
            display_name="sase",
            aliases=["core-ui"],
        )
        bead_store = ArtifactRefBeadStore("sase", "sase", tmp_path / "beads")
        agent_root = ArtifactRefAgentRoot("sase", tmp_path / "agents")
        agent_owner = ArtifactRefAgentOwner("alice", "athena")
        monkeypatch.setattr(artifact_ref_context, "resolve_sdd_store", lambda *_: _Store())
        monkeypatch.setattr(
            artifact_ref_context,
            "resolution_config",
            lambda *_: {
                "repos": {
                    "sidecar": {
                        "custom": {
                            "designs": {
                                "description": "Durable designs.",
                                "ref": {"filters": {"path_globs": ["docs/**/*.md"]}},
                            }
                        }
                    }
                }
            },
        )
        monkeypatch.setattr(
            artifact_ref_context,
            "collect_repo_inventory",
            lambda **_: inventory,
        )
        monkeypatch.setattr(
            artifact_ref_context,
            "list_project_records",
            lambda *_args, **_kwargs: [project_record],
        )
        monkeypatch.setattr(
            artifact_ref_context,
            "effective_project_name",
            lambda record: record.display_name,
        )
        monkeypatch.setattr(
            artifact_ref_context,
            "sase_subdir",
            lambda name: tmp_path / "state" / name,
        )
        monkeypatch.setattr(
            artifact_ref_context,
            "default_artifact_files_index_path",
            lambda: tmp_path / "artifact-index.jsonl",
        )
        monkeypatch.setattr(
            artifact_ref_context,
            "collect_entity_context",
            lambda store, project_ref, projects: (
                (bead_store,),
                (agent_root,),
                agent_owner,
            ),
        )
    
        context = artifact_refs.artifact_ref_context(tmp_path / "workspace", 7)
    
        assert [(entry.kind, entry.root) for entry in context.document_roots] == [
            ("plan", (tmp_path / "repo-plans").resolve()),
            ("plan", (tmp_path / "state" / "plans").resolve()),
            ("designs", (tmp_path / "missing-designs-clone").resolve()),
        ]
        assert [entry.path_globs for entry in context.document_roots] == [
            ("**/*.md",),
            ("**/*.md",),
            ("docs/**/*.md",),
        ]
>       assert context.known_kinds == (
            "stitch",
            "patch",
            "bead",
            "agent",
            "file",
            "job",
            "commit",
            "plans",
            "chat",
            "bug",
            "plan",
            "designs",
        )
E       AssertionError: assert ('stitch', 'p..., 'tool', ...) == ('stitch', 'p...', 'job', ...)
E         
E         At index 5 diff: 'tool' != 'job'
E         Left contains one more item: 'designs'
E         
E         Full diff:
E           (
E               'stitch',
E               'patch',
E               'bead',
E               'agent',
E               'file',
E         +     'tool',
E               'job',
E               'commit',
E               'plans',
E               'chat',
E               'bug',
E               'plan',
E               'designs',
E           )

tests/artifact_refs/test_context.py:158: AssertionError
------------------------------ Captured log call -------------------------------
WARNING  sase.sidecar_ref_config:sidecar_ref_config.py:89 sidecar ref config repos.sidecar.<bucket>.designs.ref.filters.path_globs: ref.filters.path_globs is deprecated; use ref.inventory.globs
=============================== warnings summary ===============================
.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:852
.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:852
.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:852
.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:852
.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:852
.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:852
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:852: PytestAssertRewriteWarning: Module already imported so cannot be rewritten; tests._axe_lumberjack_fixtures
    self.import_plugin(import_spec)

tests/test_procs_supervisor.py::test_starter_exit_does_not_kill_a_released_proc
  <frozen os>:898: DeprecationWarning: This process (pid=2849296) is multi-threaded, use of fork() may lead to deadlocks in the child.

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

tests/test_run_agent_runner_clan_summary_refresh.py::test_successful_post_preparation_summary_survives_later_metadata_write
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_run_agent_runner_clan_summary_refresh.py::test_successful_post_preparation_summary_survives_later_metadata_write changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_outcomes.py::TestDeferredWorkspaceOutcomes::test_bead_environment_mismatch_writes_error_and_skips_model_execution
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_outcomes.py::TestDeferredWorkspaceOutcomes::test_bead_environment_mismatch_writes_error_and_skips_model_execution changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
    next(it)

tests/test_run_agent_runner_clan_summary_refresh.py::test_unsuccessful_post_preparation_summary_keeps_earlier_success
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_run_agent_runner_clan_summary_refresh.py::test_unsuccessful_post_preparation_summary_keeps_earlier_success changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
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

tests/test_notification_modal_tab_order.py::test_on_mount_highlights_first_visible_row_when_initial_is_hidden
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/src/sase/ace/tui/modals/notification_modal_snooze_status.py:136: RuntimeWarning: coroutine 'Timer._run_timer' was never awaited
    self._snooze_status_timer = None
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/sdd/test_artifact_link_event_acceptance_process_death.py::test_real_killed_publisher_process_leaves_no_corrupt_object_and_recovers
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/tests/sdd/test_artifact_link_event_acceptance_process_death.py:57: DeprecationWarning: This process (pid=2849296) is multi-threaded, use of fork() may lead to deadlocks in the child.
    child = os.fork()

tests/axe/test_run_agent_exec_attempts_integration.py::test_retry_branch_snapshots_failed_attempt
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/axe/test_run_agent_exec_attempts_integration.py::test_retry_branch_snapshots_failed_attempt changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
    next(it)

tests/axe/test_run_agent_exec_attempts_integration.py::test_fallback_branch_snapshots_with_primary_model_marker
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/axe/test_run_agent_exec_attempts_integration.py::test_fallback_branch_snapshots_with_primary_model_marker changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
    next(it)

tests/completion/test_zsh_smoke.py: 18 warnings
  /home/bryan/.local/share/uv/python/cpython-3.14.7-linux-x86_64-gnu/lib/python3.14/pty.py:66: DeprecationWarning: This process (pid=2849239) is multi-threaded, use of forkpty() may lead to deadlocks in the child.
    pid, fd = os.forkpty()

-- Docs: https://docs.pytest.org/en/stable/how-to/capture-warnings.html
============================= slowest 20 durations =============================
71.28s call     tests/history/test_continuation_replay_hydration.py::test_hundred_handoff_from_final_monitor_result_grows_linearly
66.01s call     tests/fakey/test_monitor_capacity_e2e.py::test_weight_two_land_family_retains_one_claim_through_real_dispatch_and_delayed_child_bootstrap
53.22s call     tests/test_contract_manifest.py::test_contract_manifest_matches_marker_selection
53.10s call     tests/test_check_feature_flags_tool_run.py::test_static_main_ignores_exploding_bd_command
50.99s call     tests/test_check_feature_flags_tool_run.py::test_main_static_on_repo_exits_zero
26.52s call     tests/pager/test_rendered_link_contract.py::test_kitchen_follow_copy_edit_and_media_for_each_supported_action
23.07s call     tests/test_agent_artifact_directory_operation_audit.py::test_artifact_directory_operation_sites_are_reviewed
18.60s call     tests/ace/tui/test_plugins_browser_pane_sase_update.py::test_updates_pane_sase_update_loads_receipt_on_plan_worker
17.10s call     tests/ace/tui/test_plugins_browser_pane_sase_update.py::test_updates_pane_sase_update_noop_closes_without_restart
16.80s call     tests/ace/tui/test_plugins_browser_pane_marks.py::test_cli_mark_consumed_by_update_when_cli_rows_hidden
15.01s call     tests/test_commit_workflow_bead_lifecycle_e2e.py::test_stitch_create_requires_keep_then_closes_only_assigned_phase
12.65s call     tests/ace/tui/test_agents_filter_bar_session.py::test_circumflex_history_replaces_the_live_edit_while_the_bar_is_open
12.48s call     tests/ace/tui/test_artifacts_scaffold.py::test_number_keys_jump_artifacts_without_entering_from_other_tabs
11.02s call     tests/ace/tui/test_deleted_proc_queue_imports.py::test_tests_do_not_import_deleted_proc_queue_module
10.33s call     tests/ace/tui/test_agents_panel_fold_mounted.py::test_mounted_clan_fold_chords_zoom_and_patch_isolation
10.04s call     tests/feature_flags/test_host_config_safety.py::test_config_seed_tests_do_not_snapshot_config_dir_at_module_scope
9.93s call     tests/monitor/test_monitor_start_ack.py::test_start_monitor_kills_a_supervisor_that_never_writes_the_ack_marker
9.75s call     tests/test_visual_capture.py::test_pytester_xdist_project_merges_worker_local_records
9.59s call     tests/test_procs_service.py::test_settlement_recovers_every_injected_crash_checkpoint_repeatedly
9.42s call     tests/ace/tui/test_agent_metadata_search.py::test_inline_metadata_search_commit_repeat_q_and_passthrough
=========================== short test summary info ============================
FAILED tests/artifact_refs/test_context.py::test_context_assembles_dynamic_document_role_and_namespaces - AssertionError: assert ('stitch', 'p..., 'tool', ...) == ('stitch', 'p...', 'job', ...)
  
  At index 5 diff: 'tool' != 'job'
  Left contains one more item: 'designs'
  
  Full diff:
    (
        'stitch',
        'patch',
        'bead',
        'agent',
        'file',
  +     'tool',
        'job',
        'commit',
        'plans',
        'chat',
        'bug',
        'plan',
        'designs',
    )
==== 1 failed, 43332 passed, 15 skipped, 85 warnings in 1248.51s (0:20:48) =====
error: recipe `test-scoped` failed on line 473 with exit code 1
error: recipe `check` failed on line 699 with exit code 1

