# Chat History - ace-run (sase-1ko.7--mon-1)

- **TIMESTAMP:** 2026-10-14 04:13:05 EDT
- **MODEL:** grok/grok-4.6
- **AGENT:** sase-1ko.7--mon-1

## Prompt

sase monitor start --command 'just check' --reason 'Verify Claude explicit delivery before host completion'

## Response

sase tool run 2657f4f156d66c0ec4c430f65f5b0294
[setup] fast-forwarded /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/sase/repos/linked/sase-core to origin/master
[validate_sase_core_rs_version] sase-core checkout is ahead of sase's compatibility window: source version 0.39.1 from /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/sase/repos/linked/sase-core/Cargo.toml does not satisfy `sase`'s `sase-core-rs>=0.35.0,<0.36.0` dependency in pyproject.toml. No action is needed: editable installs build from the checkout regardless, and `tools/ratchet_core_window` moves the published window on the release branch at release time.
[core-source] linked sase-core source changed since the extension was built; flagging an extension rebuild.
[setup] Note: the sase-core checkout is ahead of the published sase-core-rs window in pyproject.toml; dev installs build from /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/sase/repos/linked/sase-core regardless. This is normal — the release-branch reconciler ratchets the published window at release time, so no action is needed here.
[setup] Rebuilding sase_core_rs: linked sase-core source changed since the extension was built.
[validate_sase_core_rs_version] sase-core checkout is ahead of sase's compatibility window: source version 0.39.1 from /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/sase/repos/linked/sase-core/Cargo.toml does not satisfy `sase`'s `sase-core-rs>=0.35.0,<0.36.0` dependency in pyproject.toml. No action is needed: editable installs build from the checkout regardless, and `tools/ratchet_core_window` moves the published window on the release branch at release time.
[rust-install] Note: the sase-core checkout is ahead of the published sase-core-rs window in pyproject.toml; dev builds from /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/sase/repos/linked/sase-core ignore it. This is normal — the release-branch reconciler ratchets the published window at release time, so no action is needed here.
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
🐍 Found CPython 3.12 at /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/bin/python
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
   Compiling once_cell v1.21.4
   Compiling shlex v1.3.0
   Compiling find-msvc-tools v0.1.9
   Compiling futures-core v0.3.32
   Compiling memchr v2.8.0
   Compiling version_check v0.9.5
   Compiling log v0.4.29
    Building [                           ] 0/277: once_cell, version_check, b…   Compiling autocfg v1.5.0
    Building [                           ] 1/277: once_cell, version_check, b…   Compiling target-lexicon v0.12.16
    Building [                           ] 2/277: once_cell, target-lexicon(b…   Compiling stable_deref_trait v1.2.1
    Building [                           ] 3/277: once_cell, target-lexicon(b…   Compiling futures-sink v0.3.32
    Building [                           ] 4/277: once_cell, target-lexicon(b…   Compiling smallvec v1.15.1
    Building [                           ] 5/277: once_cell, target-lexicon(b…   Compiling serde_core v1.0.228
    Building [                           ] 6/277: once_cell, target-lexicon(b…   Compiling zerocopy v0.8.48
    Building [                           ] 7/277: zerocopy(build.rs), once_ce…   Compiling cc v1.2.61
    Building [                           ] 8/277: zerocopy(build.rs), once_ce…    Building [                           ] 9/277: zerocopy(build.rs), quote(b…   Compiling futures-channel v0.3.32
    Building [                          ] 10/277: zerocopy(build.rs), quote(b…   Compiling equivalent v1.0.2
    Building [>                         ] 11/277: zerocopy(build.rs), quote(b…   Compiling tracing-core v0.1.36
    Building [>                         ] 12/277: zerocopy(build.rs), futures…   Compiling hashbrown v0.17.0
    Building [>                         ] 13/277: zerocopy(build.rs), futures…   Compiling tower-service v0.3.3
    Building [>                         ] 14/277: zerocopy(build.rs), futures…    Building [>                         ] 15/277: zerocopy(build.rs), futures…    Building [>                         ] 16/277: zerocopy(build.rs), futures…   Compiling slab v0.4.12
    Building [>                         ] 17/277: zerocopy(build.rs), futures…    Building [>                         ] 18/277: zerocopy(build.rs), futures…   Compiling futures-task v0.3.32
    Building [>                         ] 19/277: zerocopy(build.rs), futures…   Compiling futures-io v0.3.32
    Building [>                         ] 20/277: zerocopy(build.rs), futures…    Building [>                         ] 21/277: zerocopy(build.rs), futures…    Building [=>                        ] 22/277: zerocopy(build.rs), futures…    Building [=>                        ] 23/277: zerocopy(build.rs), target-…   Compiling siphasher v1.0.4
    Building [=>                        ] 24/277: zerocopy(build.rs), target-…    Building [=>                        ] 25/277: zerocopy(build.rs), target-…    Building [=>                        ] 26/277: zerocopy(build.rs), target-…   Compiling generic-array v0.14.7
    Building [=>                        ] 27/277: zerocopy(build.rs), target-…   Compiling serde v1.0.228
    Building [=>                        ] 28/277: zerocopy(build.rs), target-…   Compiling litemap v0.8.2
    Building [=>                        ] 29/277: zerocopy(build.rs), target-…    Building [=>                        ] 30/277: zerocopy(build), target-lex…   Compiling regex-syntax v0.8.10
    Building [=>                        ] 31/277: zerocopy(build), target-lex…   Compiling num-traits v0.2.19
    Building [==>                       ] 32/277: zerocopy(build), target-lex…    Building [==>                       ] 33/277: target-lexicon, regex-synta…   Compiling zmij v1.0.21
    Building [==>                       ] 34/277: target-lexicon, regex-synta…    Building [==>                       ] 35/277: num-traits(build), target-l…   Compiling pyo3-build-config v0.22.6
   Compiling phf_shared v0.11.3
    Building [==>                       ] 37/277: num-traits(build), pyo3-bui…   Compiling writeable v0.6.3
    Building [==>                       ] 38/277: num-traits(build), pyo3-bui…   Compiling httparse v1.10.1
    Building [==>                       ] 39/277: num-traits(build), pyo3-bui…   Compiling untrusted v0.9.0
    Building [==>                       ] 40/277: num-traits(build), pyo3-bui…    Building [==>                       ] 41/277: pyo3-build-config(build.rs)…   Compiling rand_core v0.6.4
    Building [==>                       ] 42/277: pyo3-build-config(build.rs)…    Building [===>                      ] 43/277: pyo3-build-config(build.rs)…    Building [===>                      ] 44/277: pyo3-build-config(build.rs)…   Compiling http v1.4.0
    Building [===>                      ] 45/277: http, pyo3-build-config(bui…    Building [===>                      ] 46/277: http, pyo3-build-config(bui…   Compiling ahash v0.8.12
    Building [===>                      ] 47/277: http, pyo3-build-config(bui…   Compiling rand v0.8.6
    Building [===>                      ] 48/277: http, pyo3-build-config(bui…   Compiling utf8_iter v1.0.4
    Building [===>                      ] 49/277: http, pyo3-build-config(bui…   Compiling icu_normalizer_data v2.2.0
    Building [===>                      ] 50/277: http, pyo3-build-config(bui…    Building [===>                      ] 51/277: http, pyo3-build-config(bui…   Compiling indexmap v2.14.0
    Building [===>                      ] 52/277: indexmap, http, pyo3-build-…   Compiling typenum v1.20.0
    Building [===>                      ] 53/277: indexmap, http, pyo3-build-…   Compiling serde_json v1.0.149
    Building [====>                     ] 54/277: indexmap, http, pyo3-build-…    Building [====>                     ] 55/277: indexmap, http, pyo3-build-…   Compiling icu_properties_data v2.2.0
    Building [====>                     ] 56/277: indexmap, http, pyo3-build-…    Building [====>                     ] 57/277: indexmap, http, pyo3-build-…   Compiling errno v0.3.14
    Building [====>                     ] 58/277: indexmap, http, pyo3-build-…   Compiling socket2 v0.6.3
    Building [====>                     ] 59/277: indexmap, http, pyo3-build-…   Compiling mio v1.2.0
    Building [====>                     ] 60/277: indexmap, http, pyo3-build-…   Compiling syn v2.0.117
    Building [====>                     ] 61/277: indexmap, http, pyo3-build-…   Compiling getrandom v0.2.17
    Building [====>                     ] 62/277: indexmap, http, pyo3-build-…   Compiling phf_generator v0.11.3
    Building [====>                     ] 63/277: indexmap, http, pyo3-build-…   Compiling signal-hook-registry v1.4.8
    Building [=====>                    ] 64/277: indexmap, http, pyo3-build-…    Building [=====>                    ] 65/277: indexmap, http, pyo3-build-…    Building [=====>                    ] 66/277: indexmap, http, pyo3-build-…    Building [=====>                    ] 67/277: indexmap, http, pyo3-build-…    Building [=====>                    ] 68/277: indexmap, pyo3-build-config…    Building [=====>                    ] 69/277: indexmap, ahash(build), pyo…    Building [=====>                    ] 70/277: indexmap, ahash(build), pyo…   Compiling aho-corasick v1.1.4
    Building [=====>                    ] 71/277: indexmap, ahash(build), pyo…   Compiling fnv v1.0.7
    Building [=====>                    ] 72/277: indexmap, pyo3-build-config…    Building [=====>                    ] 73/277: indexmap, http, regex-synta…   Compiling httpdate v1.0.3
    Building [=====>                    ] 74/277: indexmap, httpdate, http, r…    Building [======>                   ] 75/277: indexmap, httpdate, http, r…   Compiling http-body v1.0.1
    Building [======>                   ] 76/277: indexmap, httpdate, http, h…   Compiling tower-layer v0.3.3
    Building [======>                   ] 77/277: indexmap, httpdate, http, h…   Compiling http v0.2.12
    Building [======>                   ] 78/277: indexmap, httpdate, http, h…    Building [======>                   ] 79/277: indexmap, httpdate, http, h…   Compiling phf_codegen v0.11.3
    Building [======>                   ] 80/277: indexmap, httpdate, http, r…    Building [======>                   ] 81/277: indexmap, http, regex-synta…   Compiling phf v0.11.3
    Building [======>                   ] 82/277: indexmap, http, regex-synta…   Compiling rustls v0.21.12
    Building [======>                   ] 83/277: indexmap, http, regex-synta…   Compiling vcpkg v0.2.15
    Building [======>                   ] 84/277: indexmap, http, regex-synta…    Building [======>                   ] 85/277: indexmap, generic-array, ht…   Compiling ryu v1.0.23
    Building [=======>                  ] 86/277: indexmap, generic-array, ht…   Compiling bitflags v2.11.1
    Building [=======>                  ] 87/277: indexmap, bitflags, generic…   Compiling pkg-config v0.3.33
    Building [=======>                  ] 88/277: indexmap, bitflags, generic…   Compiling regex-automata v0.4.14
    Building [=======>                  ] 89/277: indexmap, bitflags, generic…   Compiling sync_wrapper v1.0.2
    Building [=======>                  ] 90/277: indexmap, bitflags, generic…   Compiling percent-encoding v2.3.2
    Building [=======>                  ] 91/277: indexmap, bitflags, generic…   Compiling try-lock v0.2.5
    Building [=======>                  ] 92/277: bitflags, generic-array, pk…   Compiling ring v0.17.14
    Building [=======>                  ] 93/277: ring(build.rs), bitflags, g…   Compiling thiserror v2.0.18
    Building [=======>                  ] 94/277: ring(build.rs), generic-arr…   Compiling rustix v1.1.4
    Building [=======>                  ] 95/277: ring(build.rs), rustix(buil…   Compiling time-core v0.1.8
    Building [========>                 ] 96/277: ring(build.rs), rustix(buil…   Compiling form_urlencoded v1.2.2
    Building [========>                 ] 97/277: ring(build.rs), rustix(buil…   Compiling rustversion v1.0.22
    Building [========>                 ] 98/277: ring(build.rs), rustix(buil…   Compiling getrandom v0.4.2
    Building [========>                 ] 99/277: ring(build.rs), rustix(buil…   Compiling num-conv v0.2.1
    Building [========>                ] 100/277: ring(build.rs), rustix(buil…    Building [========>                ] 101/277: rustix(build.rs), generic-a…   Compiling powerfmt v0.2.0
    Building [========>                ] 102/277: rustix(build.rs), generic-a…   Compiling iana-time-zone v0.1.65
    Building [========>                ] 103/277: generic-array, num-conv, re…    Building [========>                ] 104/277: generic-array, num-conv, re…   Compiling block-buffer v0.10.4
    Building [========>                ] 105/277: num-conv, regex-syntax, ser…   Compiling crypto-common v0.1.7
    Building [========>                ] 106/277: num-conv, regex-syntax, ser…   Compiling time-macros v0.2.27
    Building [========>                ] 107/277: regex-syntax, serde_core, s…   Compiling libsqlite3-sys v0.30.1
    Building [========>                ] 108/277: regex-syntax, serde_core, s…   Compiling http-body v0.4.6
    Building [========>                ] 109/277: http-body, regex-syntax, se…   Compiling chrono v0.4.44
    Building [========>                ] 110/277: http-body, serde_core, siph…   Compiling digest v0.10.7
    Building [=========>               ] 111/277: http-body, serde_core, siph…    Building [=========>               ] 112/277: http-body, serde_core, siph…   Compiling deranged v0.5.8
    Building [=========>               ] 113/277: http-body, serde_core, ring…    Building [=========>               ] 114/277: http-body, serde_core, getr…    Building [=========>               ] 115/277: http-body, serde_core, rust…    Building [=========>               ] 116/277: http-body, serde_core, ring…    Building [=========>               ] 117/277: http-body, serde_core, ring…   Compiling pyo3-macros-backend v0.22.6
    Building [=========>               ] 118/277: http-body, serde_core, ring…    Building [=========>               ] 119/277: http-body, serde_core, ring…   Compiling pyo3-ffi v0.22.6
    Building [=========>               ] 120/277: http-body, serde_core, ring…   Compiling want v0.3.1
    Building [=========>               ] 121/277: http-body, serde_core, ring…   Compiling http-body-util v0.1.3
    Building [==========>              ] 122/277: http-body, http-body-util, …    Building [==========>              ] 123/277: http-body-util, serde_core,…   Compiling num-integer v0.1.46
    Building [==========>              ] 124/277: num-integer, http-body-util…   Compiling socket2 v0.5.10
    Building [==========>              ] 125/277: num-integer, http-body-util…   Compiling regex v1.12.3
    Building [==========>              ] 126/277: num-integer, http-body-util…    Building [==========>              ] 127/277: num-integer, serde_core, ri…    Building [==========>              ] 128/277: num-integer, serde_core, ri…    Building [==========>              ] 129/277: num-integer, ring(build), r…   Compiling atomic-waker v1.1.2
    Building [==========>              ] 130/277: ring(build), regex, syn, ze…    Building [==========>              ] 131/277: ring(build), regex, syn, ze…   Compiling cpufeatures v0.2.17
    Building [==========>              ] 132/277: ring(build), regex, syn, ze…   Compiling linux-raw-sys v0.12.1
    Building [===========>             ] 133/277: ring(build), regex, syn, li…   Compiling thiserror v1.0.69
    Building [===========>             ] 134/277: ring(build), regex, syn, li…   Compiling mime v0.3.17
    Building [===========>             ] 135/277: mime, ring(build), regex, s…   Compiling parse-zoneinfo v0.3.1
    Building [===========>             ] 136/277: parse-zoneinfo, mime, ring(…    Building [===========>             ] 137/277: parse-zoneinfo, mime, ring(…   Compiling time v0.3.47
    Building [===========>             ] 138/277: parse-zoneinfo, time, mime,…   Compiling num-bigint v0.4.6
    Building [===========>             ] 139/277: parse-zoneinfo, time, mime,…    Building [===========>             ] 140/277: parse-zoneinfo, time, mime,…    Building [===========>             ] 141/277: parse-zoneinfo, time, mime,…    Building [===========>             ] 142/277: parse-zoneinfo, time, mime,…    Building [===========>             ] 143/277: parse-zoneinfo, time, mime,…    Building [===========>             ] 144/277: parse-zoneinfo, time, mime,…   Compiling chrono-tz-build v0.3.0
    Building [============>            ] 145/277: parse-zoneinfo, time, mime,…    Building [============>            ] 146/277: parse-zoneinfo, time, ring(…   Compiling memoffset v0.9.1
    Building [============>            ] 147/277: parse-zoneinfo, time, ring(…   Compiling fallible-streaming-iterator v0.1.9
    Building [============>            ] 148/277: parse-zoneinfo, time, falli…   Compiling base64 v0.22.1
    Building [============>            ] 149/277: parse-zoneinfo, time, falli…   Compiling heck v0.5.0
    Building [============>            ] 150/277: heck, time, fallible-stream…   Compiling fallible-iterator v0.3.0
    Building [============>            ] 151/277: heck, time, ring(build), sy…   Compiling chrono-tz v0.9.0
    Building [============>            ] 152/277: heck, time, ring(build), ch…   Compiling tinyvec v1.13.3
    Building [============>            ] 153/277: time, ring(build), chrono-t…   Compiling lazy_static v1.5.0
    Building [============>            ] 154/277: time, ring(build), chrono-t…    Building [============>            ] 155/277: time, ring(build), syn, zer…   Compiling base64 v0.21.7
    Building [=============>           ] 156/277: time, ring(build), syn, zer…   Compiling unsafe-libyaml v0.2.11
    Building [=============>           ] 157/277: unsafe-libyaml, time, ring(…   Compiling synstructure v0.13.2
    Building [=============>           ] 158/277: unsafe-libyaml, time, ring(…   Compiling fastrand v2.4.1
    Building [=============>           ] 159/277: unsafe-libyaml, time, ring(…   Compiling unicode-normalization v0.1.25
    Building [=============>           ] 160/277: unsafe-libyaml, time, ring(…   Compiling rustls-pemfile v1.0.4
    Building [=============>           ] 161/277: unsafe-libyaml, rustls-pemf…    Building [=============>           ] 162/277: unsafe-libyaml, ahash, rust…   Compiling ppv-lite86 v0.2.21
    Building [=============>           ] 163/277: unsafe-libyaml, ahash, rust…   Compiling hashbrown v0.14.5
    Building [=============>           ] 164/277: unsafe-libyaml, ahash, ppv-…   Compiling pem v3.0.6
    Building [=============>           ] 165/277: unsafe-libyaml, ppv-lite86,…    Building [=============>           ] 166/277: unsafe-libyaml, chrono-tz, …   Compiling tempfile v3.27.0
    Building [==============>          ] 167/277: unsafe-libyaml, chrono-tz, …    Building [==============>          ] 168/277: unsafe-libyaml, chrono-tz, …   Compiling rand_chacha v0.3.1
    Building [==============>          ] 169/277: unsafe-libyaml, chrono-tz, …   Compiling sharded-slab v0.1.7
    Building [==============>          ] 170/277: unsafe-libyaml, chrono-tz, …    Building [==============>          ] 171/277: unsafe-libyaml, chrono-tz, …    Building [==============>          ] 172/277: unsafe-libyaml, chrono-tz, …   Compiling sha2 v0.10.9
    Building [==============>          ] 173/277: unsafe-libyaml, chrono-tz, …   Compiling sha1 v0.10.7
    Building [==============>          ] 174/277: unsafe-libyaml, chrono-tz, …   Compiling serde_path_to_error v0.1.20
    Building [==============>          ] 175/277: unsafe-libyaml, chrono-tz, …   Compiling pyo3 v0.22.6
    Building [==============>          ] 176/277: unsafe-libyaml, chrono-tz, …   Compiling fs2 v0.4.3
    Building [==============>          ] 177/277: unsafe-libyaml, chrono-tz, …   Compiling tracing-log v0.2.0
    Building [===============>         ] 178/277: unsafe-libyaml, chrono-tz, …   Compiling hashlink v0.9.1
    Building [===============>         ] 179/277: unsafe-libyaml, chrono-tz, …   Compiling encoding_rs v0.8.35
    Building [===============>         ] 180/277: unsafe-libyaml, chrono-tz, …   Compiling matchers v0.2.0
    Building [===============>         ] 181/277: unsafe-libyaml, chrono-tz, …    Building [===============>         ] 182/277: unsafe-libyaml, chrono-tz, …   Compiling thread_local v1.1.9
    Building [===============>         ] 183/277: unsafe-libyaml, chrono-tz, …   Compiling nu-ansi-term v0.50.3
    Building [===============>         ] 184/277: unsafe-libyaml, chrono-tz, …   Compiling unicode-width v0.2.2
    Building [===============>         ] 185/277: unsafe-libyaml, chrono-tz, …   Compiling sync_wrapper v0.1.2
    Building [===============>         ] 186/277: unsafe-libyaml, chrono-tz, …   Compiling unicode-casefold v0.2.0
    Building [===============>         ] 187/277: unsafe-libyaml, chrono-tz, …   Compiling webpki-roots v0.25.4
    Building [===============>         ] 188/277: unsafe-libyaml, chrono-tz, …   Compiling zerofrom-derive v0.1.7
    Building [================>        ] 189/277: unsafe-libyaml, chrono-tz, …   Compiling yoke-derive v0.8.2
    Building [================>        ] 190/277: chrono-tz, regex, unicode-w…   Compiling tokio-macros v2.7.0
    Building [================>        ] 191/277: chrono-tz, regex, unicode-w…   Compiling tracing-attributes v0.1.31
    Building [================>        ] 192/277: chrono-tz, regex, unicode-w…   Compiling zerovec-derive v0.11.3
    Building [================>        ] 193/277: chrono-tz, regex, unicode-w…   Compiling displaydoc v0.2.5
    Building [================>        ] 194/277: chrono-tz, regex, displaydo…   Compiling futures-macro v0.3.32
    Building [================>        ] 195/277: chrono-tz, regex, displaydo…   Compiling serde_derive v1.0.228
    Building [================>        ] 196/277: chrono-tz, regex, displaydo…   Compiling sase_workspace_hack v0.1.0 (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/sase/repos/linked/sase-core/crates/sase_workspace_hack)
    Building [================>        ] 197/277: chrono-tz, regex, displaydo…   Compiling thiserror-impl v2.0.18
    Building [================>        ] 198/277: chrono-tz, regex, displaydo…   Compiling thiserror-impl v1.0.69
    Building [=================>       ] 200/277: chrono-tz, yoke-derive, thi…   Compiling async-trait v0.1.89
    Building [=================>       ] 201/277: chrono-tz, yoke-derive, thi…   Compiling tokio v1.52.2
    Building [=================>       ] 202/277: chrono-tz, yoke-derive, thi…   Compiling futures-util v0.3.32
    Building [=================>       ] 203/277: chrono-tz, yoke-derive, thi…   Compiling async-stream-impl v0.3.6
    Building [=================>       ] 204/277: async-stream-impl, chrono-t…   Compiling hex v0.4.3
    Building [=================>       ] 205/277: async-stream-impl, chrono-t…   Compiling matchit v0.7.3
    Building [=================>       ] 206/277: async-stream-impl, chrono-t…   Compiling ipnet v2.12.0
    Building [=================>       ] 207/277: chrono-tz, matchit, thiserr…   Compiling zerofrom v0.1.7
    Building [=================>       ] 208/277: chrono-tz, zerofrom, matchi…   Compiling tracing v0.1.44
    Building [=================>       ] 209/277: chrono-tz, zerofrom, matchi…   Compiling yoke v0.8.2
    Building [=================>       ] 210/277: chrono-tz, yoke, matchit, t…   Compiling async-stream v0.3.6
    Building [==================>      ] 211/277: chrono-tz, yoke, thiserror-…   Compiling tower-http v0.5.2
    Building [==================>      ] 212/277: yoke, thiserror-impl, tokio…   Compiling tracing-subscriber v0.3.23
    Building [==================>      ] 213/277: yoke, thiserror-impl, tokio…   Compiling zerovec v0.11.6
    Building [==================>      ] 214/277: zerovec, thiserror-impl, to…   Compiling zerotrie v0.2.4
    Building [==================>      ] 215/277: zerovec, thiserror-impl, to…    Building [==================>      ] 216/277: zerovec, tokio, futures-uti…    Building [==================>      ] 217/277: zerovec, tokio, futures-uti…   Compiling simple_asn1 v0.6.4
    Building [==================>      ] 218/277: zerovec, tokio, futures-uti…    Building [==================>      ] 219/277: zerovec, tokio, futures-uti…    Building [==================>      ] 220/277: zerovec, memoffset, tokio, …    Building [==================>      ] 221/277: zerovec, memoffset, tokio, …   Compiling indoc v2.0.7
    Building [===================>     ] 222/277: zerovec, indoc, tokio, futu…   Compiling unindent v0.2.4
    Building [===================>     ] 223/277: zerovec, indoc, tokio, futu…    Building [===================>     ] 224/277: zerovec, indoc, tokio, futu…    Building [===================>     ] 225/277: zerovec, indoc, tokio, futu…    Building [===================>     ] 226/277: zerovec, indoc, tokio, futu…   Compiling tinystr v0.8.3
    Building [===================>     ] 227/277: tinystr, zerovec, tokio, fu…   Compiling potential_utf v0.1.5
    Building [===================>     ] 228/277: tinystr, tokio, futures-uti…   Compiling pyo3-macros v0.22.6
    Building [===================>     ] 229/277: tinystr, tokio, futures-uti…   Compiling icu_collections v2.2.0
    Building [===================>     ] 230/277: tinystr, tokio, futures-uti…   Compiling icu_locale_core v2.2.0
    Building [===================>     ] 231/277: tokio, futures-util, ring(b…    Building [===================>     ] 232/277: tokio, futures-util, ring(b…    Building [====================>    ] 233/277: tokio, futures-util, ring(b…    Building [====================>    ] 234/277: tokio, futures-util, ring(b…    Building [====================>    ] 235/277: tokio, futures-util, ring(b…    Building [====================>    ] 236/277: tokio, futures-util, ring(b…    Building [====================>    ] 237/277: tokio, futures-util, ring(b…   Compiling serde_urlencoded v0.7.1
   Compiling serde_yaml v0.9.34+deprecated
    Building [====================>    ] 237/277: serde_urlencoded, tokio, fu…    Building [====================>    ] 238/277: serde_urlencoded, tokio, fu…   Compiling icu_provider v2.2.0
    Building [====================>    ] 239/277: tokio, futures-util, ring(b…   Compiling icu_properties v2.2.0
   Compiling icu_normalizer v2.2.0
    Building [====================>    ] 239/277: icu_normalizer, tokio, futu…    Building [====================>    ] 240/277: icu_normalizer, tokio, futu…   Compiling axum-core v0.4.5
    Building [====================>    ] 240/277: axum-core, icu_normalizer, …    Building [====================>    ] 241/277: axum-core, icu_normalizer, …    Building [====================>    ] 242/277: axum-core, icu_normalizer, …    Building [====================>    ] 243/277: axum-core, tokio, ring(buil…    Building [=====================>   ] 244/277: axum-core, tokio, tracing-s…    Building [=====================>   ] 245/277: axum-core, tokio, tracing-s…   Compiling idna_adapter v1.2.2
   Compiling idna v1.1.0
    Building [=====================>   ] 246/277: axum-core, tokio, tracing-s…    Building [=====================>   ] 247/277: axum-core, tokio, tracing-s…   Compiling url v2.5.8
    Building [=====================>   ] 248/277: axum-core, tokio, tracing-s…   Compiling tokio-util v0.7.18
   Compiling tower v0.5.3
   Compiling hyper v1.9.0
    Building [=====================>   ] 248/277: hyper, axum-core, tokio, tr…    Building [=====================>   ] 249/277: hyper, axum-core, tokio, tr…    Building [=====================>   ] 250/277: hyper, axum-core, tokio, to…   Compiling sct v0.7.1
   Compiling rustls-webpki v0.101.7
   Compiling jsonwebtoken v9.3.1
    Building [=====================>   ] 251/277: hyper, axum-core, tokio, sc…    Building [=====================>   ] 252/277: hyper, axum-core, tokio, id…   Compiling h2 v0.3.27
    Building [=====================>   ] 252/277: hyper, axum-core, tokio, sa…    Building [=====================>   ] 253/277: hyper, axum-core, tokio, id…    Building [=====================>   ] 254/277: hyper, tokio, idna, libsqli…    Building [======================>  ] 255/277: hyper, tokio, libsqlite3-sy…    Building [======================>  ] 256/277: hyper, tokio, libsqlite3-sy…    Building [======================>  ] 256/277: hyper, rustls, tokio, libsq…    Building [======================>  ] 257/277: hyper, rustls, tokio, libsq…   Compiling hyper-util v0.1.20
   Compiling axum v0.7.9
    Building [======================>  ] 258/277: hyper, rustls, tokio, libsq…    Building [======================>  ] 259/277: hyper, rustls, tokio, libsq…    Building [======================>  ] 260/277: hyper, rustls, tokio, libsq…    Building [======================>  ] 261/277: hyper, rustls, tokio, libsq…    Building [======================>  ] 262/277: rustls, tokio, libsqlite3-s…    Building [======================>  ] 263/277: rustls, tokio, libsqlite3-s…   Compiling tokio-rustls v0.24.1
    Building [======================>  ] 264/277: rustls, tokio, libsqlite3-s…    Building [======================>  ] 265/277: rustls, libsqlite3-sys(buil…   Compiling hyper v0.14.32
    Building [======================>  ] 265/277: rustls, hyper, libsqlite3-s…    Building [=======================> ] 266/277: rustls, hyper, libsqlite3-s…    Building [=======================> ] 267/277: hyper, libsqlite3-sys(build…    Building [=======================> ] 268/277: hyper, libsqlite3-sys(build)   Compiling hyper-rustls v0.24.2
    Building [=======================> ] 268/277: hyper, libsqlite3-sys(build…   Compiling reqwest v0.11.27
    Building [=======================> ] 269/277: hyper, libsqlite3-sys(build…    Building [=======================> ] 270/277: libsqlite3-sys(build), reqw…    Building [=======================> ] 271/277: libsqlite3-sys(build)           Building [=======================> ] 272/277: libsqlite3-sys                 Compiling rusqlite v0.32.1
    Building [=======================> ] 272/277: rusqlite, libsqlite3-sys        Building [=======================> ] 273/277: rusqlite                       Compiling sase_core v0.39.1 (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/sase/repos/linked/sase-core/crates/sase_core)
    Building [=======================> ] 273/277: rusqlite, sase_core             Building [=======================> ] 274/277: sase_core                      Compiling sase_gateway v0.39.1 (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/sase/repos/linked/sase-core/crates/sase_gateway)
    Building [=======================> ] 274/277: sase_gateway, sase_core         Building [=======================> ] 275/277: sase_core                      Compiling sase_core_py v0.39.1 (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/sase/repos/linked/sase-core/crates/sase_core_py)
    Building [=======================> ] 276/277: sase_core_py                    Finished `release` profile [optimized] target(s) in 21m 29s
📦 Built wheel for abi3 Python ≥ 3.12 to /home/bryan/.sase/cache/sase-core-artifacts/.build-nzba70k9/sase_core_rs-0.39.1-cp312-abi3-manylinux_2_39_x86_64.whl
[rust-install] Installing cached sase_core_rs wheel from /home/bryan/.sase/cache/sase-core-artifacts/4dc3f0f71626bd45809e6bb627bba5d168d200621e89891bf52c5053648f5151/sase_core_rs-0.39.1-cp312-abi3-manylinux_2_39_x86_64.whl.
Resolved 1 package in 6ms
Prepared 1 package in 199ms
Uninstalled 1 package in 3ms
Installed 1 package in 4ms
 - sase-core-rs==0.39.1 (from file:///home/bryan/.sase/cache/sase-core-artifacts/21c28c0886f53da27bb50cc618d794d5a786ec3b517444999a8fbe90a7f61776/sase_core_rs-0.39.1-cp312-abi3-manylinux_2_39_x86_64.whl)
 + sase-core-rs==0.39.1 (from file:///home/bryan/.sase/cache/sase-core-artifacts/4dc3f0f71626bd45809e6bb627bba5d168d200621e89891bf52c5053648f5151/sase_core_rs-0.39.1-cp312-abi3-manylinux_2_39_x86_64.whl)
# Keep the LSP server in lockstep with the extension: both are built
# from the same sase-core checkout, and the ACE/LSP parity tests
# compare their directive contracts.
[sase-core-wheel-cache] miss: no exact cached wheel
   Compiling sase_core v0.39.1 (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/sase/repos/linked/sase-core/crates/sase_core)
    Building [=======================> ] 172/175: sase_core                      Compiling sase_macro_lsp v0.39.1 (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/sase/repos/linked/sase-core/crates/sase_macro_lsp)
    Building [=======================> ] 172/175: sase_core, sase_macro_lsp       Building [=======================> ] 173/175: sase_core                       Building [=======================> ] 174/175: sase-macro-lsp(bin)             Finished `dev-update` profile [optimized] target(s) in 3m 20s
[rust-lsp-install] Installing cached LSP binary from /home/bryan/.sase/cache/sase-core-artifacts/bb91d0bdde5a89d670368354b67c24b171107ffaf6058089cfc7735b7a9d49fd/sase-macro-lsp.
[rust-lsp-install] installed /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/bin/sase-macro-lsp
.venv/bin/python tools/setup_required_plugins
[setup] Installing required plugin sase-github>=0.2.5.
[setup] Installing required plugin sase-research-artifacts>=0.2.0.
✓ fmt (python)
✓ fmt (markdown)
✓ fmt (generated docs)
✓ model policy
✓ lint (keep-sorted)
✓ lint (ruff)
✓ lint (mypy)
✓ lint (feature flags)
✓ lint (pyscripts)
✓ lint (test waits)
✓ lint (changelog)
✓ lint (patch/stitch terminology)
✗ lint (symvision)
[validate_sase_core_rs_version] sase-core checkout is ahead of sase's compatibility window: source version 0.39.1 from /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/sase/repos/linked/sase-core/Cargo.toml does not satisfy `sase`'s `sase-core-rs>=0.35.0,<0.36.0` dependency in pyproject.toml. No action is needed: editable installs build from the checkout regardless, and `tools/ratchet_core_window` moves the published window on the release branch at release time.
[setup] Note: the sase-core checkout is ahead of the published sase-core-rs window in pyproject.toml; dev installs build from /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/sase/repos/linked/sase-core regardless. This is normal — the release-branch reconciler ratchets the published window at release time, so no action is needed here.
.venv/bin/python tools/setup_required_plugins
[setup] Installing required plugin sase-github>=0.2.5.
[setup] Installing required plugin sase-research-artifacts>=0.2.0.
SASE_SYMVISION_BEAD_STATUS_ONLY=1 BD_COMMAND=tools/sase_bead .venv/bin/symvision src/sase --exclude-decorator gate_command_entrypoint --exclude-decorator builtin_chop 
Unused public functions/classes. Make these private if they are used only within the file they are defined. If the functions/classes are completely unused, you should delete them:
  claude_helper_sources in src/sase/instructions/coverage_sources.py
  contains_contract in src/sase/instructions/fingerprints.py
  count_contract_sources in src/sase/instructions/fingerprints.py
  human_rules_blocks in src/sase/instructions/grok.py
  prompt_prefixes in src/sase/instructions/muse.py
  prompt_texts in src/sase/instructions/muse.py
  rules_texts in src/sase/instructions/muse.py
error: Recipe `_lint-symvision` failed on line 459 with exit code 1
✓ SASE validation
[core-floor-probe] blocked_unpublished: sase-core-rs==0.35.0 is missing 165 capability(s), and at least one has no containing sase-core release tag yet.
[core-floor-probe] PromptPredictionCorpus: first appears in sase-core 12e012d (feat(core-binding): add prompt_prediction binding module with tests); release v0.36.1 contains it.
[core-floor-probe] PromptPredictionModel: first appears in sase-core 12e012d (feat(core-binding): add prompt_prediction binding module with tests); release v0.36.1 contains it.
[core-floor-probe] ack_agent_completions: first appears in sase-core 28befcb (feat(notifications): store generations, ack API, and lean unread index); release v0.36.2 contains it.
[core-floor-probe] advance_auto_restart_ledger: first appears in sase-core d4ad8c9 (feat(agent): add agent auto-restart core modules and scan wire); release v0.38.0 contains it.
[core-floor-probe] agent_auto_restart_wire_schema_version: first appears in sase-core d4ad8c9 (feat(agent): add agent auto-restart core modules and scan wire); release v0.38.0 contains it.
[core-floor-probe] alternation_scan: first appears in sase-core 1e51ff3 (feat(alternation): shared scanner, binding, diagnostic, and LSP tokens); release v0.36.1 contains it.
[core-floor-probe] argument_list_continuation_edit: first appears in sase-core 2f16dc4 (feat(editor): continue existing macro argument lists); release v0.36.6 contains it.
[core-floor-probe] artifact_link_index_build: first appears in sase-core daad8f2 (feat(artifact_link): add immutable inverted index and PyO3 handle); no release tag contains it yet.
[core-floor-probe] artifact_link_index_chips: first appears in sase-core daad8f2 (feat(artifact_link): add immutable inverted index and PyO3 handle); no release tag contains it yet.
[core-floor-probe] artifact_link_index_project: first appears in sase-core daad8f2 (feat(artifact_link): add immutable inverted index and PyO3 handle); no release tag contains it yet.
[core-floor-probe] artifact_link_index_target: first appears in sase-core daad8f2 (feat(artifact_link): add immutable inverted index and PyO3 handle); no release tag contains it yet.
[core-floor-probe] artifact_link_index_wire_schema_version: first appears in sase-core daad8f2 (feat(artifact_link): add immutable inverted index and PyO3 handle); no release tag contains it yet.
[core-floor-probe] attachment_audience_decision: first appears in sase-core 7806f58 (feat(attachments): core attachment audience policy and scanner); release v0.36.1 contains it.
[core-floor-probe] attachment_canonical_extension: first appears in sase-core 7806f58 (feat(attachments): core attachment audience policy and scanner); release v0.36.1 contains it.
[core-floor-probe] attachment_object_digest_from_relpath: first appears in sase-core 7806f58 (feat(attachments): core attachment audience policy and scanner); release v0.36.1 contains it.
[core-floor-probe] attachment_placement: first appears in sase-core 43f744b (feat(note-attachment): add attachment wire, reducer, mutation APIs, and policy); release v0.36.1 contains it.
[core-floor-probe] attachment_public_object_relpath: first appears in sase-core 7806f58 (feat(attachments): core attachment audience policy and scanner); release v0.36.1 contains it.
[core-floor-probe] attachment_scan_file: first appears in sase-core 7806f58 (feat(attachments): core attachment audience policy and scanner); release v0.36.1 contains it.
[core-floor-probe] attachment_scanner_rules_version: first appears in sase-core 7806f58 (feat(attachments): core attachment audience policy and scanner); release v0.36.1 contains it.
[core-floor-probe] attachment_sensitive_path_reason: first appears in sase-core 43f744b (feat(note-attachment): add attachment wire, reducer, mutation APIs, and policy); release v0.36.1 contains it.
[core-floor-probe] attachment_should_auto_fetch: first appears in sase-core 43f744b (feat(note-attachment): add attachment wire, reducer, mutation APIs, and policy); release v0.36.1 contains it.
[core-floor-probe] auto_restart_lineage_root: first appears in sase-core d4ad8c9 (feat(agent): add agent auto-restart core modules and scan wire); release v0.38.0 contains it.
[core-floor-probe] auto_restart_recovery_is_in_flight: first appears in sase-core d4ad8c9 (feat(agent): add agent auto-restart core modules and scan wire); release v0.38.0 contains it.
[core-floor-probe] autonomy_append_decision: first appears in sase-core 51b66fd (feat(autonomy): core summary, sentences, mutation, and decision log); release v0.37.1 contains it.
[core-floor-probe] autonomy_decision_sentence: first appears in sase-core 51b66fd (feat(autonomy): core summary, sentences, mutation, and decision log); release v0.37.1 contains it.
[core-floor-probe] autonomy_evaluate: first appears in sase-core 01b0ad7 (feat(autonomy): add core record, compatibility profiles, and evaluate()); release v0.37.1 contains it.
[core-floor-probe] autonomy_inherit: first appears in sase-core 51b66fd (feat(autonomy): core summary, sentences, mutation, and decision log); release v0.37.1 contains it.
[core-floor-probe] autonomy_legacy_projection: first appears in sase-core 01b0ad7 (feat(autonomy): add core record, compatibility profiles, and evaluate()); release v0.37.1 contains it.
[core-floor-probe] autonomy_mutate: first appears in sase-core 51b66fd (feat(autonomy): core summary, sentences, mutation, and decision log); release v0.37.1 contains it.
[core-floor-probe] autonomy_profiles: first appears in sase-core 51b66fd (feat(autonomy): core summary, sentences, mutation, and decision log); release v0.37.1 contains it.
[core-floor-probe] autonomy_read_decisions: first appears in sase-core 51b66fd (feat(autonomy): core summary, sentences, mutation, and decision log); release v0.37.1 contains it.
[core-floor-probe] autonomy_record_from_legacy_meta: first appears in sase-core 01b0ad7 (feat(autonomy): add core record, compatibility profiles, and evaluate()); release v0.37.1 contains it.
[core-floor-probe] autonomy_resolve_selection: first appears in sase-core 01b0ad7 (feat(autonomy): add core record, compatibility profiles, and evaluate()); release v0.37.1 contains it.
[core-floor-probe] autonomy_summary: first appears in sase-core 51b66fd (feat(autonomy): core summary, sentences, mutation, and decision log); release v0.37.1 contains it.
[core-floor-probe] bead_probe_target_owner: first appears in sase-core bff4860 (feat(bead): one-replay core support for in-mutation resolution and target probing); release v0.37.1 contains it.
[core-floor-probe] build_agent_tab_catalog: first appears in sase-core c448ed6 (feat(agent-tab): core tab model with directive, typed units, and Python bindings); release v0.36.0 contains it.
[core-floor-probe] canonicalize_agent_tab_name: first appears in sase-core c448ed6 (feat(agent-tab): core tab model with directive, typed units, and Python bindings); release v0.36.0 contains it.
[core-floor-probe] check_input_value: first appears in sase-core 2838c7e (feat: add macro input-type catalog, resolver, and Python bindings); release v0.36.6 contains it.
[core-floor-probe] claim_auto_restart_ledger: first appears in sase-core d4ad8c9 (feat(agent): add agent auto-restart core modules and scan wire); release v0.38.0 contains it.
[core-floor-probe] classify_agent_failure: first appears in sase-core d4ad8c9 (feat(agent): add agent auto-restart core modules and scan wire); release v0.38.0 contains it.
[core-floor-probe] classify_attachment: first appears in sase-core 39324ac (feat(note-attachment): add core attachment grammar, names, and media classification); release v0.36.1 contains it.
[core-floor-probe] classify_auto_directive: first appears in sase-core e8606a5 (feat(auto): fail-closed %auto grammar classifier in sase-core); release v0.37.1 contains it.
[core-floor-probe] classify_deferred_prompt_obligation: first appears in sase-core 3d406d4 (feat(agent-publication-recovery): retry selection, page+SHA completion, and prompt status); release v0.36.5 contains it.
[core-floor-probe] classify_git_lock_failure: first appears in sase-core 47b28fb (feat(git-lock): add index-lock recovery policy domain); release v0.38.0 contains it.
[core-floor-probe] classify_git_lock_owner: first appears in sase-core 47b28fb (feat(git-lock): add index-lock recovery policy domain); release v0.38.0 contains it.
[core-floor-probe] classify_model_value: first appears in sase-core 16095fc (feat(macros): add builtin model and effort types with one routing classifier); release v0.36.6 contains it.
[core-floor-probe] classify_project_candidates: first appears in sase-core aaec3bf (feat(project-onboarding): classify candidates and evaluate creation forms); release v0.39.0 contains it.
[core-floor-probe] classify_session_manifest_files: first appears in sase-core d7f2dbf (feat(agent-session-manifest): canonical file-set derivation and classification); release v0.36.5 contains it.
[core-floor-probe] compare_prose: first appears in sase-core 3b27df5 (feat(prose-diff): add pure sase-core prose_diff module and Python binding); release v0.36.2 contains it.
[core-floor-probe] compile_agent_archive_corpus: first appears in sase-core bc40675 (feat(archive): bind corpus compile, summary, rows, lookup, and count); release v0.38.0 contains it.
[core-floor-probe] compose_note_attachment_text: first appears in sase-core 39324ac (feat(note-attachment): add core attachment grammar, names, and media classification); release v0.36.1 contains it.
[core-floor-probe] count_agent_archive_corpus: first appears in sase-core bc40675 (feat(archive): bind corpus compile, summary, rows, lookup, and count); release v0.38.0 contains it.
[core-floor-probe] decide_eager_git_lock_cleanup: first appears in sase-core 47b28fb (feat(git-lock): add index-lock recovery policy domain); release v0.38.0 contains it.
[core-floor-probe] decide_git_lock_recovery: first appears in sase-core 47b28fb (feat(git-lock): add index-lock recovery policy domain); release v0.38.0 contains it.
[core-floor-probe] decide_publication_request_completion: first appears in sase-core 3d406d4 (feat(agent-publication-recovery): retry selection, page+SHA completion, and prompt status); release v0.36.5 contains it.
[core-floor-probe] default_git_lock_retry_delays: first appears in sase-core 47b28fb (feat(git-lock): add index-lock recovery policy domain); release v0.38.0 contains it.
[core-floor-probe] delete_agent_artifact_alias: first appears in sase-core 6306bd2 (feat(agent-scan): add no-migrate index readers and alias bindings); no release tag contains it yet.
[core-floor-probe] delete_dismissed_bundle_summaries_for_suffixes: first appears in sase-core d30e133 (feat(agent-archive): move dismissed-bundle archive index into sase_core store); no release tag contains it yet.
[core-floor-probe] derive_auto_restart_episode: first appears in sase-core d4ad8c9 (feat(agent): add agent auto-restart core modules and scan wire); release v0.38.0 contains it.
[core-floor-probe] dismissed_bundle_index_progress: first appears in sase-core d30e133 (feat(agent-archive): move dismissed-bundle archive index into sase_core store); no release tag contains it yet.
[core-floor-probe] dismissed_bundle_index_signature: first appears in sase-core d30e133 (feat(agent-archive): move dismissed-bundle archive index into sase_core store); no release tag contains it yet.
[core-floor-probe] editor_snippet_catalog_wire_schema_version: first appears in sase-core a62699b (feat(macros)!: emit canonical macro wires and snippet catalog schema 2); release v0.37.0 contains it.
[core-floor-probe] evaluate_prompt_prediction_replay: first appears in sase-core 1ad57ea (feat(prompt-prediction): add per-point novel coverage and precision to sweep wire); release v0.36.1 contains it.
[core-floor-probe] evaluate_repo_creation_form: first appears in sase-core aaec3bf (feat(project-onboarding): classify candidates and evaluate creation forms); release v0.39.0 contains it.
[core-floor-probe] git_lock_wire_schema_version: first appears in sase-core 47b28fb (feat(git-lock): add index-lock recovery policy domain); release v0.38.0 contains it.
[core-floor-probe] goal_card_markdown: first appears in sase-core 33b0250 (feat(goals): make goal a first-class builtin artifact kind in sase-core (sase-1bu.6)); release v0.36.0 contains it.
[core-floor-probe] goal_card_view: first appears in sase-core 33b0250 (feat(goals): make goal a first-class builtin artifact kind in sase-core (sase-1bu.6)); release v0.36.0 contains it.
[core-floor-probe] goal_citation_line: first appears in sase-core 33b0250 (feat(goals): make goal a first-class builtin artifact kind in sase-core (sase-1bu.6)); release v0.36.0 contains it.
[core-floor-probe] goal_fast_path: first appears in sase-core d2d9ec7 (feat(goals): add goal ledger, fast path, and terminal renderer backend); release v0.36.0 contains it.
[core-floor-probe] goal_ledger_append: first appears in sase-core cbe70f6 (feat(goal): add goal ledger I/O in sase-core with Python bindings (sase-1bu.2)); release v0.36.0 contains it.
[core-floor-probe] goal_ledger_doctor: first appears in sase-core cbe70f6 (feat(goal): add goal ledger I/O in sase-core with Python bindings (sase-1bu.2)); release v0.36.0 contains it.
[core-floor-probe] goal_ledger_history: first appears in sase-core cbe70f6 (feat(goal): add goal ledger I/O in sase-core with Python bindings (sase-1bu.2)); release v0.36.0 contains it.
[core-floor-probe] goal_ledger_init: first appears in sase-core cbe70f6 (feat(goal): add goal ledger I/O in sase-core with Python bindings (sase-1bu.2)); release v0.36.0 contains it.
[core-floor-probe] goal_ledger_list: first appears in sase-core cbe70f6 (feat(goal): add goal ledger I/O in sase-core with Python bindings (sase-1bu.2)); release v0.36.0 contains it.
[core-floor-probe] goal_ledger_probe_list: first appears in sase-core cbe70f6 (feat(goal): add goal ledger I/O in sase-core with Python bindings (sase-1bu.2)); release v0.36.0 contains it.
[core-floor-probe] goal_ledger_show: first appears in sase-core cbe70f6 (feat(goal): add goal ledger I/O in sase-core with Python bindings (sase-1bu.2)); release v0.36.0 contains it.
[core-floor-probe] goal_ledger_store_schema_version: first appears in sase-core cbe70f6 (feat(goal): add goal ledger I/O in sase-core with Python bindings (sase-1bu.2)); release v0.36.0 contains it.
[core-floor-probe] goal_ledger_wire_schema_version: first appears in sase-core cbe70f6 (feat(goal): add goal ledger I/O in sase-core with Python bindings (sase-1bu.2)); release v0.36.0 contains it.
[core-floor-probe] goal_mint_id: first appears in sase-core cbe70f6 (feat(goal): add goal ledger I/O in sase-core with Python bindings (sase-1bu.2)); release v0.36.0 contains it.
[core-floor-probe] goal_projection_refresh: first appears in sase-core cbe70f6 (feat(goal): add goal ledger I/O in sase-core with Python bindings (sase-1bu.2)); release v0.36.0 contains it.
[core-floor-probe] goal_projection_status: first appears in sase-core cbe70f6 (feat(goal): add goal ledger I/O in sase-core with Python bindings (sase-1bu.2)); release v0.36.0 contains it.
[core-floor-probe] goal_render_card: first appears in sase-core d2d9ec7 (feat(goals): add goal ledger, fast path, and terminal renderer backend); release v0.36.0 contains it.
[core-floor-probe] goal_render_list: first appears in sase-core d2d9ec7 (feat(goals): add goal ledger, fast path, and terminal renderer backend); release v0.36.0 contains it.
[core-floor-probe] instruction_manifest_wire_schema_version: first appears in sase-core fa39036 (feat(instructions): instruction manifest v1 wire schema, binding, and golden fixture (sase-1h3.2)); release v0.37.1 contains it.
[core-floor-probe] jinja_catalog: first appears in sase-core 3adc01b (feat(editor-completion): add jinja completion bindings and tests); release v0.36.2 contains it.
[core-floor-probe] jinja_completion: first appears in sase-core 3adc01b (feat(editor-completion): add jinja completion bindings and tests); release v0.36.2 contains it.
[core-floor-probe] jinja_scope_variables: first appears in sase-core 3adc01b (feat(editor-completion): add jinja completion bindings and tests); release v0.36.2 contains it.
[core-floor-probe] launch_scratch_liveness_wire_schema_version: first appears in sase-core 297bc1e (feat(core): launch_scratch_liveness module with procfs probe bindings); release v0.36.0 contains it.
[core-floor-probe] list_agent_artifact_aliases: first appears in sase-core 6306bd2 (feat(agent-scan): add no-migrate index readers and alias bindings); no release tag contains it yet.
[core-floor-probe] load_agent_artifact_index_projection: first appears in sase-core 6306bd2 (feat(agent-scan): add no-migrate index readers and alias bindings); no release tag contains it yet.
[core-floor-probe] load_macro_input_type_registry: first appears in sase-core af5df61 (feat(core): load plugin input_type registries with resolution, catalog, and LSP wiring); release v0.37.0 contains it.
[core-floor-probe] lookup_agent_archive_corpus: first appears in sase-core bc40675 (feat(archive): bind corpus compile, summary, rows, lookup, and count); release v0.38.0 contains it.
[core-floor-probe] macro_argument_choice_candidates: first appears in sase-core 0d27dad (feat(macros): carry resolved choice metadata and shared candidates); release v0.36.6 contains it.
[core-floor-probe] macro_argument_spans: first appears in sase-core c4444ab (feat(core-expand): rename catalog and editor internals toward macros with pinned legacy output); release v0.36.3 contains it.
[core-floor-probe] macro_completion_spacer_to_parentheses_edit: first appears in sase-core 0279de6 (feat(macros): flip emitted wires to macro spellings, rename LSP crate); release v0.36.6 contains it.
[core-floor-probe] macro_input_type_catalog: first appears in sase-core 2838c7e (feat: add macro input-type catalog, resolver, and Python bindings); release v0.36.6 contains it.
[core-floor-probe] macro_input_type_label: first appears in sase-core 0d27dad (feat(macros): carry resolved choice metadata and shared candidates); release v0.36.6 contains it.
[core-floor-probe] macro_skill_definition_wire_schema_version: first appears in sase-core c4444ab (feat(core-expand): rename catalog and editor internals toward macros with pinned legacy output); release v0.36.3 contains it.
[core-floor-probe] managed_tmp_roots_list: first appears in sase-core 924884e (feat(managed-tmp-roots): add Rust-owned registry with Py bindings (sase-1bf.1)); release v0.36.0 contains it.
[core-floor-probe] managed_tmp_roots_register: first appears in sase-core 924884e (feat(managed-tmp-roots): add Rust-owned registry with Py bindings (sase-1bf.1)); release v0.36.0 contains it.
[core-floor-probe] managed_tmp_roots_wire_schema_version: first appears in sase-core 924884e (feat(managed-tmp-roots): add Rust-owned registry with Py bindings (sase-1bf.1)); release v0.36.0 contains it.
[core-floor-probe] match_git_lock_path: first appears in sase-core 47b28fb (feat(git-lock): add index-lock recovery policy domain); release v0.38.0 contains it.
[core-floor-probe] memory_history_compare: first appears in sase-core 11f29c3 (feat(memory-history): add cache-backed query layer with python bindings); release v0.36.2 contains it.
[core-floor-probe] memory_history_feed: first appears in sase-core 11f29c3 (feat(memory-history): add cache-backed query layer with python bindings); release v0.36.2 contains it.
[core-floor-probe] memory_history_mark_reviewed: first appears in sase-core c2a415e (feat(memory-history): add review state store with query and mark-reviewed); release v0.36.4 contains it.
[core-floor-probe] memory_history_resolve: first appears in sase-core 11f29c3 (feat(memory-history): add cache-backed query layer with python bindings); release v0.36.2 contains it.
[core-floor-probe] memory_history_review_state: first appears in sase-core c2a415e (feat(memory-history): add review state store with query and mark-reviewed); release v0.36.4 contains it.
[core-floor-probe] memory_history_subjects: first appears in sase-core 11f29c3 (feat(memory-history): add cache-backed query layer with python bindings); release v0.36.2 contains it.
[core-floor-probe] memory_history_sync: first appears in sase-core 11f29c3 (feat(memory-history): add cache-backed query layer with python bindings); release v0.36.2 contains it.
[core-floor-probe] memory_history_timeline: first appears in sase-core 11f29c3 (feat(memory-history): add cache-backed query layer with python bindings); release v0.36.2 contains it.
[core-floor-probe] memory_history_version: first appears in sase-core 11f29c3 (feat(memory-history): add cache-backed query layer with python bindings); release v0.36.2 contains it.
[core-floor-probe] memory_history_wire_schema_version: first appears in sase-core 11f29c3 (feat(memory-history): add cache-backed query layer with python bindings); release v0.36.2 contains it.
[core-floor-probe] normalize_instruction_manifest: first appears in sase-core fa39036 (feat(instructions): instruction manifest v1 wire schema, binding, and golden fixture (sase-1h3.2)); release v0.37.1 contains it.
[core-floor-probe] normalize_macro_config_layer: first appears in sase-core 4eb40d5 (feat(compat): shared Rust config normalization contract); release v0.36.4 contains it.
[core-floor-probe] observe_launch_scratch_liveness: first appears in sase-core 297bc1e (feat(core): launch_scratch_liveness module with procfs probe bindings); release v0.36.0 contains it.
[core-floor-probe] parse_git_lock_retry_delays: first appears in sase-core 47b28fb (feat(git-lock): add index-lock recovery policy domain); release v0.38.0 contains it.
[core-floor-probe] plan_decision_quote_match: first appears in sase-core df735e4 (feat(sase-core): add plan decision human quote matcher with PyO3 binding); release v0.37.1 contains it.
[core-floor-probe] plan_decision_sheet: first appears in sase-core 88d6385 (feat(plan): add decision sheet, summary, and prompt-block backend); release v0.37.1 contains it.
[core-floor-probe] plan_decision_summary: first appears in sase-core 88d6385 (feat(plan): add decision sheet, summary, and prompt-block backend); release v0.37.1 contains it.
[core-floor-probe] plan_decisions_digest: first appears in sase-core c089cf1 (feat(sase-core): add plan decisions resolver payload/digest/resolve with PyO3 bindings); release v0.37.1 contains it.
[core-floor-probe] plan_decisions_payload: first appears in sase-core c089cf1 (feat(sase-core): add plan decisions resolver payload/digest/resolve with PyO3 bindings); release v0.37.1 contains it.
[core-floor-probe] plan_decisions_prompt_block: first appears in sase-core 88d6385 (feat(plan): add decision sheet, summary, and prompt-block backend); release v0.37.1 contains it.
[core-floor-probe] plan_decisions_resolve: first appears in sase-core c089cf1 (feat(sase-core): add plan decisions resolver payload/digest/resolve with PyO3 bindings); release v0.37.1 contains it.
[core-floor-probe] plan_project_onboarding: first appears in sase-core 792255d (feat(project-onboarding): derive ordered onboarding plans from facts); release v0.39.0 contains it.
[core-floor-probe] project_finalizer_node_view: first appears in sase-core f52fa7c (feat(finalizer): implement core-run-view-model run_view module); release v0.35.1 contains it.
[core-floor-probe] project_onboarding_wire_schema_version: first appears in sase-core aaec3bf (feat(project-onboarding): classify candidates and evaluate creation forms); release v0.39.0 contains it.
[core-floor-probe] prompt_looks_generated: first appears in sase-core 0ad6e44 (feat(prompt-prediction): flag chop and job tribe origins as generated); release v0.36.2 contains it.
[core-floor-probe] prompt_prediction_wire_schema_version: first appears in sase-core 12e012d (feat(core-binding): add prompt_prediction binding module with tests); release v0.36.1 contains it.
[core-floor-probe] prompt_proc_origin: first appears in sase-core 92a4fc4 (feat(agent-launch): add native %proc dispatch helpers); release v0.31.5 contains it.
[core-floor-probe] query_dismissed_bundle_paths_by_suffixes: first appears in sase-core d30e133 (feat(agent-archive): move dismissed-bundle archive index into sase_core store); no release tag contains it yet.
[core-floor-probe] query_dismissed_bundle_summaries: first appears in sase-core d30e133 (feat(agent-archive): move dismissed-bundle archive index into sase_core store); no release tag contains it yet.
[core-floor-probe] query_dismissed_bundle_summary_identities: first appears in sase-core d30e133 (feat(agent-archive): move dismissed-bundle archive index into sase_core store); no release tag contains it yet.
[core-floor-probe] read_agent_artifact_index_schema_version: first appears in sase-core 6306bd2 (feat(agent-scan): add no-migrate index readers and alias bindings); no release tag contains it yet.
[core-floor-probe] read_prompt_stash_archive: first appears in sase-core df23cce (feat(prompt-stash): append-only archive for every permanent stash removal); release v0.36.1 contains it.
[core-floor-probe] read_unread_completion_index: first appears in sase-core 28befcb (feat(notifications): store generations, ack API, and lean unread index); release v0.36.2 contains it.
[core-floor-probe] rebuild_dismissed_bundle_index: first appears in sase-core d30e133 (feat(agent-archive): move dismissed-bundle archive index into sase_core store); no release tag contains it yet.
[core-floor-probe] reconcile_notification_rows: first appears in sase-core 413511f (feat(notifications): lock-held field-scoped reconcile write plus empty raw_suffix matcher parity); release v0.36.1 contains it.
[core-floor-probe] recover_prompt_stash_archive: first appears in sase-core df23cce (feat(prompt-stash): append-only archive for every permanent stash removal); release v0.36.1 contains it.
[core-floor-probe] resolve_input_type: first appears in sase-core 2838c7e (feat: add macro input-type catalog, resolver, and Python bindings); release v0.36.6 contains it.
[core-floor-probe] resolve_macro_skill_definition: first appears in sase-core c4444ab (feat(core-expand): rename catalog and editor internals toward macros with pinned legacy output); release v0.36.3 contains it.
[core-floor-probe] rows_agent_archive_corpus: first appears in sase-core bc40675 (feat(archive): bind corpus compile, summary, rows, lookup, and count); release v0.38.0 contains it.
[core-floor-probe] sanitize_attachment_name: first appears in sase-core 39324ac (feat(note-attachment): add core attachment grammar, names, and media classification); release v0.36.1 contains it.
[core-floor-probe] scan_note_attachment_refs: first appears in sase-core 39324ac (feat(note-attachment): add core attachment grammar, names, and media classification); release v0.36.1 contains it.
[core-floor-probe] select_publication_retries: first appears in sase-core 3d406d4 (feat(agent-publication-recovery): retry selection, page+SHA completion, and prompt status); release v0.36.5 contains it.
[core-floor-probe] set_dismissed_bundle_visibility_for_suffixes: first appears in sase-core d30e133 (feat(agent-archive): move dismissed-bundle archive index into sase_core store); no release tag contains it yet.
[core-floor-probe] status_bucket_for_status: first appears in sase-core 9f6ce0c (feat(agent-archive): add live status-bucket match with outcome derived from bucket); release v0.38.0 contains it.
[core-floor-probe] summarize_agent_archive_corpus: first appears in sase-core bc40675 (feat(archive): bind corpus compile, summary, rows, lookup, and count); release v0.38.0 contains it.
[core-floor-probe] summarize_agent_models: first appears in sase-core a95609e (feat(core): expose session agent model summaries); release v0.38.0 contains it.
[core-floor-probe] tool_run_briefs: first appears in sase-core 9368ddf (feat(tool-run): add live glance, briefs, and node-summary projections); release v0.36.0 contains it.
[core-floor-probe] tool_run_detail: first appears in sase-core 830e900 (feat(tool-run): add tool_run_detail projection with stage timeline and witness counts); release v0.36.0 contains it.
[core-floor-probe] tool_run_duration_calibration: first appears in sase-core 17b072b (feat(tool-run): add duration classes and inline-fit policy); release v0.36.1 contains it.
[core-floor-probe] tool_run_duration_fit: first appears in sase-core 17b072b (feat(tool-run): add duration classes and inline-fit policy); release v0.36.1 contains it.
[core-floor-probe] tool_run_join: first appears in sase-core cee9f49 (feat(tool-run): add detached starter scope, monitor join, and sync wait budget); release v0.36.1 contains it.
[core-floor-probe] tool_run_live_glance: first appears in sase-core 9368ddf (feat(tool-run): add live glance, briefs, and node-summary projections); release v0.36.0 contains it.
[core-floor-probe] tool_run_node_summaries: first appears in sase-core 9368ddf (feat(tool-run): add live glance, briefs, and node-summary projections); release v0.36.0 contains it.
[core-floor-probe] tool_run_record_demand: first appears in sase-core 7a9ffad (feat(tool-run): record per-run demand context, usage, and worker grants); release v0.36.2 contains it.
[core-floor-probe] tool_run_release_join: first appears in sase-core cee9f49 (feat(tool-run): add detached starter scope, monitor join, and sync wait budget); release v0.36.1 contains it.
[core-floor-probe] tool_run_stats_report: first appears in sase-core 6e23783 (feat(tool-run): implement core-stats report for sase-1dm.3); release v0.36.2 contains it.
[core-floor-probe] tool_run_sync_wait_budget: first appears in sase-core cee9f49 (feat(tool-run): add detached starter scope, monitor join, and sync wait budget); release v0.36.1 contains it.
[core-floor-probe] unique_attachment_name: first appears in sase-core 39324ac (feat(note-attachment): add core attachment grammar, names, and media classification); release v0.36.1 contains it.
[core-floor-probe] upsert_agent_artifact_alias: first appears in sase-core 6306bd2 (feat(agent-scan): add no-migrate index readers and alias bindings); no release tag contains it yet.
[core-floor-probe] upsert_dismissed_bundle_summary: first appears in sase-core d30e133 (feat(agent-archive): move dismissed-bundle archive index into sase_core store); no release tag contains it yet.
[core-floor-probe] validate_enum_choices: first appears in sase-core 2838c7e (feat: add macro input-type catalog, resolver, and Python bindings); release v0.36.6 contains it.
[core-floor-probe] validate_git_lock_retry_delays: first appears in sase-core 47b28fb (feat(git-lock): add index-lock recovery policy domain); release v0.38.0 contains it.
[core-floor-probe] wait_epic_follow_reduce: first appears in sase-core 4b4a052 (feat(wait): add pure wait_epic_follow reducer with Python binding (sase-1h7.4)); release v0.37.1 contains it.
{"cache_hit": true, "capabilities": [{"commit": "12e012d", "name": "PromptPredictionCorpus", "release": "v0.36.1", "subject": "feat(core-binding): add prompt_prediction binding module with tests"}, {"commit": "12e012d", "name": "PromptPredictionModel", "release": "v0.36.1", "subject": "feat(core-binding): add prompt_prediction binding module with tests"}, {"commit": "28befcb", "name": "ack_agent_completions", "release": "v0.36.2", "subject": "feat(notifications): store generations, ack API, and lean unread index"}, {"commit": "d4ad8c9", "name": "advance_auto_restart_ledger", "release": "v0.38.0", "subject": "feat(agent): add agent auto-restart core modules and scan wire"}, {"commit": "d4ad8c9", "name": "agent_auto_restart_wire_schema_version", "release": "v0.38.0", "subject": "feat(agent): add agent auto-restart core modules and scan wire"}, {"commit": "1e51ff3", "name": "alternation_scan", "release": "v0.36.1", "subject": "feat(alternation): shared scanner, binding, diagnostic, and LSP tokens"}, {"commit": "2f16dc4", "name": "argument_list_continuation_edit", "release": "v0.36.6", "subject": "feat(editor): continue existing macro argument lists"}, {"commit": "daad8f2", "name": "artifact_link_index_build", "release": null, "subject": "feat(artifact_link): add immutable inverted index and PyO3 handle"}, {"commit": "daad8f2", "name": "artifact_link_index_chips", "release": null, "subject": "feat(artifact_link): add immutable inverted index and PyO3 handle"}, {"commit": "daad8f2", "name": "artifact_link_index_project", "release": null, "subject": "feat(artifact_link): add immutable inverted index and PyO3 handle"}, {"commit": "daad8f2", "name": "artifact_link_index_target", "release": null, "subject": "feat(artifact_link): add immutable inverted index and PyO3 handle"}, {"commit": "daad8f2", "name": "artifact_link_index_wire_schema_version", "release": null, "subject": "feat(artifact_link): add immutable inverted index and PyO3 handle"}, {"commit": "7806f58", "name": "attachment_audience_decision", "release": "v0.36.1", "subject": "feat(attachments): core attachment audience policy and scanner"}, {"commit": "7806f58", "name": "attachment_canonical_extension", "release": "v0.36.1", "subject": "feat(attachments): core attachment audience policy and scanner"}, {"commit": "7806f58", "name": "attachment_object_digest_from_relpath", "release": "v0.36.1", "subject": "feat(attachments): core attachment audience policy and scanner"}, {"commit": "43f744b", "name": "attachment_placement", "release": "v0.36.1", "subject": "feat(note-attachment): add attachment wire, reducer, mutation APIs, and policy"}, {"commit": "7806f58", "name": "attachment_public_object_relpath", "release": "v0.36.1", "subject": "feat(attachments): core attachment audience policy and scanner"}, {"commit": "7806f58", "name": "attachment_scan_file", "release": "v0.36.1", "subject": "feat(attachments): core attachment audience policy and scanner"}, {"commit": "7806f58", "name": "attachment_scanner_rules_version", "release": "v0.36.1", "subject": "feat(attachments): core attachment audience policy and scanner"}, {"commit": "43f744b", "name": "attachment_sensitive_path_reason", "release": "v0.36.1", "subject": "feat(note-attachment): add attachment wire, reducer, mutation APIs, and policy"}, {"commit": "43f744b", "name": "attachment_should_auto_fetch", "release": "v0.36.1", "subject": "feat(note-attachment): add attachment wire, reducer, mutation APIs, and policy"}, {"commit": "d4ad8c9", "name": "auto_restart_lineage_root", "release": "v0.38.0", "subject": "feat(agent): add agent auto-restart core modules and scan wire"}, {"commit": "d4ad8c9", "name": "auto_restart_recovery_is_in_flight", "release": "v0.38.0", "subject": "feat(agent): add agent auto-restart core modules and scan wire"}, {"commit": "51b66fd", "name": "autonomy_append_decision", "release": "v0.37.1", "subject": "feat(autonomy): core summary, sentences, mutation, and decision log"}, {"commit": "51b66fd", "name": "autonomy_decision_sentence", "release": "v0.37.1", "subject": "feat(autonomy): core summary, sentences, mutation, and decision log"}, {"commit": "01b0ad7", "name": "autonomy_evaluate", "release": "v0.37.1", "subject": "feat(autonomy): add core record, compatibility profiles, and evaluate()"}, {"commit": "51b66fd", "name": "autonomy_inherit", "release": "v0.37.1", "subject": "feat(autonomy): core summary, sentences, mutation, and decision log"}, {"commit": "01b0ad7", "name": "autonomy_legacy_projection", "release": "v0.37.1", "subject": "feat(autonomy): add core record, compatibility profiles, and evaluate()"}, {"commit": "51b66fd", "name": "autonomy_mutate", "release": "v0.37.1", "subject": "feat(autonomy): core summary, sentences, mutation, and decision log"}, {"commit": "51b66fd", "name": "autonomy_profiles", "release": "v0.37.1", "subject": "feat(autonomy): core summary, sentences, mutation, and decision log"}, {"commit": "51b66fd", "name": "autonomy_read_decisions", "release": "v0.37.1", "subject": "feat(autonomy): core summary, sentences, mutation, and decision log"}, {"commit": "01b0ad7", "name": "autonomy_record_from_legacy_meta", "release": "v0.37.1", "subject": "feat(autonomy): add core record, compatibility profiles, and evaluate()"}, {"commit": "01b0ad7", "name": "autonomy_resolve_selection", "release": "v0.37.1", "subject": "feat(autonomy): add core record, compatibility profiles, and evaluate()"}, {"commit": "51b66fd", "name": "autonomy_summary", "release": "v0.37.1", "subject": "feat(autonomy): core summary, sentences, mutation, and decision log"}, {"commit": "bff4860", "name": "bead_probe_target_owner", "release": "v0.37.1", "subject": "feat(bead): one-replay core support for in-mutation resolution and target probing"}, {"commit": "c448ed6", "name": "build_agent_tab_catalog", "release": "v0.36.0", "subject": "feat(agent-tab): core tab model with directive, typed units, and Python bindings"}, {"commit": "c448ed6", "name": "canonicalize_agent_tab_name", "release": "v0.36.0", "subject": "feat(agent-tab): core tab model with directive, typed units, and Python bindings"}, {"commit": "2838c7e", "name": "check_input_value", "release": "v0.36.6", "subject": "feat: add macro input-type catalog, resolver, and Python bindings"}, {"commit": "d4ad8c9", "name": "claim_auto_restart_ledger", "release": "v0.38.0", "subject": "feat(agent): add agent auto-restart core modules and scan wire"}, {"commit": "d4ad8c9", "name": "classify_agent_failure", "release": "v0.38.0", "subject": "feat(agent): add agent auto-restart core modules and scan wire"}, {"commit": "39324ac", "name": "classify_attachment", "release": "v0.36.1", "subject": "feat(note-attachment): add core attachment grammar, names, and media classification"}, {"commit": "e8606a5", "name": "classify_auto_directive", "release": "v0.37.1", "subject": "feat(auto): fail-closed %auto grammar classifier in sase-core"}, {"commit": "3d406d4", "name": "classify_deferred_prompt_obligation", "release": "v0.36.5", "subject": "feat(agent-publication-recovery): retry selection, page+SHA completion, and prompt status"}, {"commit": "47b28fb", "name": "classify_git_lock_failure", "release": "v0.38.0", "subject": "feat(git-lock): add index-lock recovery policy domain"}, {"commit": "47b28fb", "name": "classify_git_lock_owner", "release": "v0.38.0", "subject": "feat(git-lock): add index-lock recovery policy domain"}, {"commit": "16095fc", "name": "classify_model_value", "release": "v0.36.6", "subject": "feat(macros): add builtin model and effort types with one routing classifier"}, {"commit": "aaec3bf", "name": "classify_project_candidates", "release": "v0.39.0", "subject": "feat(project-onboarding): classify candidates and evaluate creation forms"}, {"commit": "d7f2dbf", "name": "classify_session_manifest_files", "release": "v0.36.5", "subject": "feat(agent-session-manifest): canonical file-set derivation and classification"}, {"commit": "3b27df5", "name": "compare_prose", "release": "v0.36.2", "subject": "feat(prose-diff): add pure sase-core prose_diff module and Python binding"}, {"commit": "bc40675", "name": "compile_agent_archive_corpus", "release": "v0.38.0", "subject": "feat(archive): bind corpus compile, summary, rows, lookup, and count"}, {"commit": "39324ac", "name": "compose_note_attachment_text", "release": "v0.36.1", "subject": "feat(note-attachment): add core attachment grammar, names, and media classification"}, {"commit": "bc40675", "name": "count_agent_archive_corpus", "release": "v0.38.0", "subject": "feat(archive): bind corpus compile, summary, rows, lookup, and count"}, {"commit": "47b28fb", "name": "decide_eager_git_lock_cleanup", "release": "v0.38.0", "subject": "feat(git-lock): add index-lock recovery policy domain"}, {"commit": "47b28fb", "name": "decide_git_lock_recovery", "release": "v0.38.0", "subject": "feat(git-lock): add index-lock recovery policy domain"}, {"commit": "3d406d4", "name": "decide_publication_request_completion", "release": "v0.36.5", "subject": "feat(agent-publication-recovery): retry selection, page+SHA completion, and prompt status"}, {"commit": "47b28fb", "name": "default_git_lock_retry_delays", "release": "v0.38.0", "subject": "feat(git-lock): add index-lock recovery policy domain"}, {"commit": "6306bd2", "name": "delete_agent_artifact_alias", "release": null, "subject": "feat(agent-scan): add no-migrate index readers and alias bindings"}, {"commit": "d30e133", "name": "delete_dismissed_bundle_summaries_for_suffixes", "release": null, "subject": "feat(agent-archive): move dismissed-bundle archive index into sase_core store"}, {"commit": "d4ad8c9", "name": "derive_auto_restart_episode", "release": "v0.38.0", "subject": "feat(agent): add agent auto-restart core modules and scan wire"}, {"commit": "d30e133", "name": "dismissed_bundle_index_progress", "release": null, "subject": "feat(agent-archive): move dismissed-bundle archive index into sase_core store"}, {"commit": "d30e133", "name": "dismissed_bundle_index_signature", "release": null, "subject": "feat(agent-archive): move dismissed-bundle archive index into sase_core store"}, {"commit": "a62699b", "name": "editor_snippet_catalog_wire_schema_version", "release": "v0.37.0", "subject": "feat(macros)!: emit canonical macro wires and snippet catalog schema 2"}, {"commit": "1ad57ea", "name": "evaluate_prompt_prediction_replay", "release": "v0.36.1", "subject": "feat(prompt-prediction): add per-point novel coverage and precision to sweep wire"}, {"commit": "aaec3bf", "name": "evaluate_repo_creation_form", "release": "v0.39.0", "subject": "feat(project-onboarding): classify candidates and evaluate creation forms"}, {"commit": "47b28fb", "name": "git_lock_wire_schema_version", "release": "v0.38.0", "subject": "feat(git-lock): add index-lock recovery policy domain"}, {"commit": "33b0250", "name": "goal_card_markdown", "release": "v0.36.0", "subject": "feat(goals): make goal a first-class builtin artifact kind in sase-core (sase-1bu.6)"}, {"commit": "33b0250", "name": "goal_card_view", "release": "v0.36.0", "subject": "feat(goals): make goal a first-class builtin artifact kind in sase-core (sase-1bu.6)"}, {"commit": "33b0250", "name": "goal_citation_line", "release": "v0.36.0", "subject": "feat(goals): make goal a first-class builtin artifact kind in sase-core (sase-1bu.6)"}, {"commit": "d2d9ec7", "name": "goal_fast_path", "release": "v0.36.0", "subject": "feat(goals): add goal ledger, fast path, and terminal renderer backend"}, {"commit": "cbe70f6", "name": "goal_ledger_append", "release": "v0.36.0", "subject": "feat(goal): add goal ledger I/O in sase-core with Python bindings (sase-1bu.2)"}, {"commit": "cbe70f6", "name": "goal_ledger_doctor", "release": "v0.36.0", "subject": "feat(goal): add goal ledger I/O in sase-core with Python bindings (sase-1bu.2)"}, {"commit": "cbe70f6", "name": "goal_ledger_history", "release": "v0.36.0", "subject": "feat(goal): add goal ledger I/O in sase-core with Python bindings (sase-1bu.2)"}, {"commit": "cbe70f6", "name": "goal_ledger_init", "release": "v0.36.0", "subject": "feat(goal): add goal ledger I/O in sase-core with Python bindings (sase-1bu.2)"}, {"commit": "cbe70f6", "name": "goal_ledger_list", "release": "v0.36.0", "subject": "feat(goal): add goal ledger I/O in sase-core with Python bindings (sase-1bu.2)"}, {"commit": "cbe70f6", "name": "goal_ledger_probe_list", "release": "v0.36.0", "subject": "feat(goal): add goal ledger I/O in sase-core with Python bindings (sase-1bu.2)"}, {"commit": "cbe70f6", "name": "goal_ledger_show", "release": "v0.36.0", "subject": "feat(goal): add goal ledger I/O in sase-core with Python bindings (sase-1bu.2)"}, {"commit": "cbe70f6", "name": "goal_ledger_store_schema_version", "release": "v0.36.0", "subject": "feat(goal): add goal ledger I/O in sase-core with Python bindings (sase-1bu.2)"}, {"commit": "cbe70f6", "name": "goal_ledger_wire_schema_version", "release": "v0.36.0", "subject": "feat(goal): add goal ledger I/O in sase-core with Python bindings (sase-1bu.2)"}, {"commit": "cbe70f6", "name": "goal_mint_id", "release": "v0.36.0", "subject": "feat(goal): add goal ledger I/O in sase-core with Python bindings (sase-1bu.2)"}, {"commit": "cbe70f6", "name": "goal_projection_refresh", "release": "v0.36.0", "subject": "feat(goal): add goal ledger I/O in sase-core with Python bindings (sase-1bu.2)"}, {"commit": "cbe70f6", "name": "goal_projection_status", "release": "v0.36.0", "subject": "feat(goal): add goal ledger I/O in sase-core with Python bindings (sase-1bu.2)"}, {"commit": "d2d9ec7", "name": "goal_render_card", "release": "v0.36.0", "subject": "feat(goals): add goal ledger, fast path, and terminal renderer backend"}, {"commit": "d2d9ec7", "name": "goal_render_list", "release": "v0.36.0", "subject": "feat(goals): add goal ledger, fast path, and terminal renderer backend"}, {"commit": "fa39036", "name": "instruction_manifest_wire_schema_version", "release": "v0.37.1", "subject": "feat(instructions): instruction manifest v1 wire schema, binding, and golden fixture (sase-1h3.2)"}, {"commit": "3adc01b", "name": "jinja_catalog", "release": "v0.36.2", "subject": "feat(editor-completion): add jinja completion bindings and tests"}, {"commit": "3adc01b", "name": "jinja_completion", "release": "v0.36.2", "subject": "feat(editor-completion): add jinja completion bindings and tests"}, {"commit": "3adc01b", "name": "jinja_scope_variables", "release": "v0.36.2", "subject": "feat(editor-completion): add jinja completion bindings and tests"}, {"commit": "297bc1e", "name": "launch_scratch_liveness_wire_schema_version", "release": "v0.36.0", "subject": "feat(core): launch_scratch_liveness module with procfs probe bindings"}, {"commit": "6306bd2", "name": "list_agent_artifact_aliases", "release": null, "subject": "feat(agent-scan): add no-migrate index readers and alias bindings"}, {"commit": "6306bd2", "name": "load_agent_artifact_index_projection", "release": null, "subject": "feat(agent-scan): add no-migrate index readers and alias bindings"}, {"commit": "af5df61", "name": "load_macro_input_type_registry", "release": "v0.37.0", "subject": "feat(core): load plugin input_type registries with resolution, catalog, and LSP wiring"}, {"commit": "bc40675", "name": "lookup_agent_archive_corpus", "release": "v0.38.0", "subject": "feat(archive): bind corpus compile, summary, rows, lookup, and count"}, {"commit": "0d27dad", "name": "macro_argument_choice_candidates", "release": "v0.36.6", "subject": "feat(macros): carry resolved choice metadata and shared candidates"}, {"commit": "c4444ab", "name": "macro_argument_spans", "release": "v0.36.3", "subject": "feat(core-expand): rename catalog and editor internals toward macros with pinned legacy output"}, {"commit": "0279de6", "name": "macro_completion_spacer_to_parentheses_edit", "release": "v0.36.6", "subject": "feat(macros): flip emitted wires to macro spellings, rename LSP crate"}, {"commit": "2838c7e", "name": "macro_input_type_catalog", "release": "v0.36.6", "subject": "feat: add macro input-type catalog, resolver, and Python bindings"}, {"commit": "0d27dad", "name": "macro_input_type_label", "release": "v0.36.6", "subject": "feat(macros): carry resolved choice metadata and shared candidates"}, {"commit": "c4444ab", "name": "macro_skill_definition_wire_schema_version", "release": "v0.36.3", "subject": "feat(core-expand): rename catalog and editor internals toward macros with pinned legacy output"}, {"commit": "924884e", "name": "managed_tmp_roots_list", "release": "v0.36.0", "subject": "feat(managed-tmp-roots): add Rust-owned registry with Py bindings (sase-1bf.1)"}, {"commit": "924884e", "name": "managed_tmp_roots_register", "release": "v0.36.0", "subject": "feat(managed-tmp-roots): add Rust-owned registry with Py bindings (sase-1bf.1)"}, {"commit": "924884e", "name": "managed_tmp_roots_wire_schema_version", "release": "v0.36.0", "subject": "feat(managed-tmp-roots): add Rust-owned registry with Py bindings (sase-1bf.1)"}, {"commit": "47b28fb", "name": "match_git_lock_path", "release": "v0.38.0", "subject": "feat(git-lock): add index-lock recovery policy domain"}, {"commit": "11f29c3", "name": "memory_history_compare", "release": "v0.36.2", "subject": "feat(memory-history): add cache-backed query layer with python bindings"}, {"commit": "11f29c3", "name": "memory_history_feed", "release": "v0.36.2", "subject": "feat(memory-history): add cache-backed query layer with python bindings"}, {"commit": "c2a415e", "name": "memory_history_mark_reviewed", "release": "v0.36.4", "subject": "feat(memory-history): add review state store with query and mark-reviewed"}, {"commit": "11f29c3", "name": "memory_history_resolve", "release": "v0.36.2", "subject": "feat(memory-history): add cache-backed query layer with python bindings"}, {"commit": "c2a415e", "name": "memory_history_review_state", "release": "v0.36.4", "subject": "feat(memory-history): add review state store with query and mark-reviewed"}, {"commit": "11f29c3", "name": "memory_history_subjects", "release": "v0.36.2", "subject": "feat(memory-history): add cache-backed query layer with python bindings"}, {"commit": "11f29c3", "name": "memory_history_sync", "release": "v0.36.2", "subject": "feat(memory-history): add cache-backed query layer with python bindings"}, {"commit": "11f29c3", "name": "memory_history_timeline", "release": "v0.36.2", "subject": "feat(memory-history): add cache-backed query layer with python bindings"}, {"commit": "11f29c3", "name": "memory_history_version", "release": "v0.36.2", "subject": "feat(memory-history): add cache-backed query layer with python bindings"}, {"commit": "11f29c3", "name": "memory_history_wire_schema_version", "release": "v0.36.2", "subject": "feat(memory-history): add cache-backed query layer with python bindings"}, {"commit": "fa39036", "name": "normalize_instruction_manifest", "release": "v0.37.1", "subject": "feat(instructions): instruction manifest v1 wire schema, binding, and golden fixture (sase-1h3.2)"}, {"commit": "4eb40d5", "name": "normalize_macro_config_layer", "release": "v0.36.4", "subject": "feat(compat): shared Rust config normalization contract"}, {"commit": "297bc1e", "name": "observe_launch_scratch_liveness", "release": "v0.36.0", "subject": "feat(core): launch_scratch_liveness module with procfs probe bindings"}, {"commit": "47b28fb", "name": "parse_git_lock_retry_delays", "release": "v0.38.0", "subject": "feat(git-lock): add index-lock recovery policy domain"}, {"commit": "df735e4", "name": "plan_decision_quote_match", "release": "v0.37.1", "subject": "feat(sase-core): add plan decision human quote matcher with PyO3 binding"}, {"commit": "88d6385", "name": "plan_decision_sheet", "release": "v0.37.1", "subject": "feat(plan): add decision sheet, summary, and prompt-block backend"}, {"commit": "88d6385", "name": "plan_decision_summary", "release": "v0.37.1", "subject": "feat(plan): add decision sheet, summary, and prompt-block backend"}, {"commit": "c089cf1", "name": "plan_decisions_digest", "release": "v0.37.1", "subject": "feat(sase-core): add plan decisions resolver payload/digest/resolve with PyO3 bindings"}, {"commit": "c089cf1", "name": "plan_decisions_payload", "release": "v0.37.1", "subject": "feat(sase-core): add plan decisions resolver payload/digest/resolve with PyO3 bindings"}, {"commit": "88d6385", "name": "plan_decisions_prompt_block", "release": "v0.37.1", "subject": "feat(plan): add decision sheet, summary, and prompt-block backend"}, {"commit": "c089cf1", "name": "plan_decisions_resolve", "release": "v0.37.1", "subject": "feat(sase-core): add plan decisions resolver payload/digest/resolve with PyO3 bindings"}, {"commit": "792255d", "name": "plan_project_onboarding", "release": "v0.39.0", "subject": "feat(project-onboarding): derive ordered onboarding plans from facts"}, {"commit": "f52fa7c", "name": "project_finalizer_node_view", "release": "v0.35.1", "subject": "feat(finalizer): implement core-run-view-model run_view module"}, {"commit": "aaec3bf", "name": "project_onboarding_wire_schema_version", "release": "v0.39.0", "subject": "feat(project-onboarding): classify candidates and evaluate creation forms"}, {"commit": "0ad6e44", "name": "prompt_looks_generated", "release": "v0.36.2", "subject": "feat(prompt-prediction): flag chop and job tribe origins as generated"}, {"commit": "12e012d", "name": "prompt_prediction_wire_schema_version", "release": "v0.36.1", "subject": "feat(core-binding): add prompt_prediction binding module with tests"}, {"commit": "92a4fc4", "name": "prompt_proc_origin", "release": "v0.31.5", "subject": "feat(agent-launch): add native %proc dispatch helpers"}, {"commit": "d30e133", "name": "query_dismissed_bundle_paths_by_suffixes", "release": null, "subject": "feat(agent-archive): move dismissed-bundle archive index into sase_core store"}, {"commit": "d30e133", "name": "query_dismissed_bundle_summaries", "release": null, "subject": "feat(agent-archive): move dismissed-bundle archive index into sase_core store"}, {"commit": "d30e133", "name": "query_dismissed_bundle_summary_identities", "release": null, "subject": "feat(agent-archive): move dismissed-bundle archive index into sase_core store"}, {"commit": "6306bd2", "name": "read_agent_artifact_index_schema_version", "release": null, "subject": "feat(agent-scan): add no-migrate index readers and alias bindings"}, {"commit": "df23cce", "name": "read_prompt_stash_archive", "release": "v0.36.1", "subject": "feat(prompt-stash): append-only archive for every permanent stash removal"}, {"commit": "28befcb", "name": "read_unread_completion_index", "release": "v0.36.2", "subject": "feat(notifications): store generations, ack API, and lean unread index"}, {"commit": "d30e133", "name": "rebuild_dismissed_bundle_index", "release": null, "subject": "feat(agent-archive): move dismissed-bundle archive index into sase_core store"}, {"commit": "413511f", "name": "reconcile_notification_rows", "release": "v0.36.1", "subject": "feat(notifications): lock-held field-scoped reconcile write plus empty raw_suffix matcher parity"}, {"commit": "df23cce", "name": "recover_prompt_stash_archive", "release": "v0.36.1", "subject": "feat(prompt-stash): append-only archive for every permanent stash removal"}, {"commit": "2838c7e", "name": "resolve_input_type", "release": "v0.36.6", "subject": "feat: add macro input-type catalog, resolver, and Python bindings"}, {"commit": "c4444ab", "name": "resolve_macro_skill_definition", "release": "v0.36.3", "subject": "feat(core-expand): rename catalog and editor internals toward macros with pinned legacy output"}, {"commit": "bc40675", "name": "rows_agent_archive_corpus", "release": "v0.38.0", "subject": "feat(archive): bind corpus compile, summary, rows, lookup, and count"}, {"commit": "39324ac", "name": "sanitize_attachment_name", "release": "v0.36.1", "subject": "feat(note-attachment): add core attachment grammar, names, and media classification"}, {"commit": "39324ac", "name": "scan_note_attachment_refs", "release": "v0.36.1", "subject": "feat(note-attachment): add core attachment grammar, names, and media classification"}, {"commit": "3d406d4", "name": "select_publication_retries", "release": "v0.36.5", "subject": "feat(agent-publication-recovery): retry selection, page+SHA completion, and prompt status"}, {"commit": "d30e133", "name": "set_dismissed_bundle_visibility_for_suffixes", "release": null, "subject": "feat(agent-archive): move dismissed-bundle archive index into sase_core store"}, {"commit": "9f6ce0c", "name": "status_bucket_for_status", "release": "v0.38.0", "subject": "feat(agent-archive): add live status-bucket match with outcome derived from bucket"}, {"commit": "bc40675", "name": "summarize_agent_archive_corpus", "release": "v0.38.0", "subject": "feat(archive): bind corpus compile, summary, rows, lookup, and count"}, {"commit": "a95609e", "name": "summarize_agent_models", "release": "v0.38.0", "subject": "feat(core): expose session agent model summaries"}, {"commit": "9368ddf", "name": "tool_run_briefs", "release": "v0.36.0", "subject": "feat(tool-run): add live glance, briefs, and node-summary projections"}, {"commit": "830e900", "name": "tool_run_detail", "release": "v0.36.0", "subject": "feat(tool-run): add tool_run_detail projection with stage timeline and witness counts"}, {"commit": "17b072b", "name": "tool_run_duration_calibration", "release": "v0.36.1", "subject": "feat(tool-run): add duration classes and inline-fit policy"}, {"commit": "17b072b", "name": "tool_run_duration_fit", "release": "v0.36.1", "subject": "feat(tool-run): add duration classes and inline-fit policy"}, {"commit": "cee9f49", "name": "tool_run_join", "release": "v0.36.1", "subject": "feat(tool-run): add detached starter scope, monitor join, and sync wait budget"}, {"commit": "9368ddf", "name": "tool_run_live_glance", "release": "v0.36.0", "subject": "feat(tool-run): add live glance, briefs, and node-summary projections"}, {"commit": "9368ddf", "name": "tool_run_node_summaries", "release": "v0.36.0", "subject": "feat(tool-run): add live glance, briefs, and node-summary projections"}, {"commit": "7a9ffad", "name": "tool_run_record_demand", "release": "v0.36.2", "subject": "feat(tool-run): record per-run demand context, usage, and worker grants"}, {"commit": "cee9f49", "name": "tool_run_release_join", "release": "v0.36.1", "subject": "feat(tool-run): add detached starter scope, monitor join, and sync wait budget"}, {"commit": "6e23783", "name": "tool_run_stats_report", "release": "v0.36.2", "subject": "feat(tool-run): implement core-stats report for sase-1dm.3"}, {"commit": "cee9f49", "name": "tool_run_sync_wait_budget", "release": "v0.36.1", "subject": "feat(tool-run): add detached starter scope, monitor join, and sync wait budget"}, {"commit": "39324ac", "name": "unique_attachment_name", "release": "v0.36.1", "subject": "feat(note-attachment): add core attachment grammar, names, and media classification"}, {"commit": "6306bd2", "name": "upsert_agent_artifact_alias", "release": null, "subject": "feat(agent-scan): add no-migrate index readers and alias bindings"}, {"commit": "d30e133", "name": "upsert_dismissed_bundle_summary", "release": null, "subject": "feat(agent-archive): move dismissed-bundle archive index into sase_core store"}, {"commit": "2838c7e", "name": "validate_enum_choices", "release": "v0.36.6", "subject": "feat: add macro input-type catalog, resolver, and Python bindings"}, {"commit": "47b28fb", "name": "validate_git_lock_retry_delays", "release": "v0.38.0", "subject": "feat(git-lock): add index-lock recovery policy domain"}, {"commit": "4b4a052", "name": "wait_epic_follow_reduce", "release": "v0.37.1", "subject": "feat(wait): add pure wait_epic_follow reducer with Python binding (sase-1h7.4)"}], "declared_floor": "0.35.0", "exit_code": 4, "message": "sase-core-rs==0.35.0 is missing 165 capability(s), and at least one has no containing sase-core release tag yet.", "status": "blocked_unpublished"}
✓ committed plans
✗ test (scoped)
[validate_sase_core_rs_version] sase-core checkout is ahead of sase's compatibility window: source version 0.39.1 from /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/sase/repos/linked/sase-core/Cargo.toml does not satisfy `sase`'s `sase-core-rs>=0.35.0,<0.36.0` dependency in pyproject.toml. No action is needed: editable installs build from the checkout regardless, and `tools/ratchet_core_window` moves the published window on the release branch at release time.
[setup] Note: the sase-core checkout is ahead of the published sase-core-rs window in pyproject.toml; dev installs build from /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/sase/repos/linked/sase-core regardless. This is normal — the release-branch reconciler ratchets the published window at release time, so no action is needed here.
.venv/bin/python tools/setup_required_plugins
[setup] Installing required plugin sase-github>=0.2.5.
[setup] Installing required plugin sase-research-artifacts>=0.2.0.

┌───────────────────────────────────────────────────────┐
│                RUNNING: just test-scoped              │
└───────────────────────────────────────────────────────┘

---------- Running diff-scoped pytest selection... ----------
test selection escalated to the full suite (rules: core-identity-changed, justfile, src-data-asset); 5202 test files in scope
coverage contexts: not consulted — the run escalates to the full suite, so ground truth had nothing to add
escalating to the governed full test lane (rules: core-identity-changed, justfile, src-data-asset)
============================= test session starts ==============================
platform linux -- Python 3.12.3, pytest-9.1.1, pluggy-1.6.0
rootdir: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12
configfile: pyproject.toml
testpaths: tests
plugins: cov-7.1.0, xdist-3.8.0, mock-3.15.1, hypothesis-6.168.0, asyncio-1.4.0, platformdirs-4.12.4, inline-snapshot-0.35.4
asyncio: mode=Mode.AUTO, debug=False, asyncio_default_fixture_loop_scope=None, asyncio_default_test_loop_scope=function
created: 7/7 workers
7 workers [55738 items]

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
........................................................................ [  2%]
........................................................................ [  2%]
........................................................................ [  2%]
........................................................................ [  2%]
..............................................................s......... [  2%]
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
........................................................................ [  4%]
........................................................................ [  4%]
........................................................................ [  4%]
........................................................................ [  4%]
........................................................................ [  4%]
........................................................................ [  4%]
........................................................................ [  4%]
...........................................................s............ [  4%]
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
..........................................................s............. [ 11%]
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
........................s............................................... [ 13%]
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
........................................................................ [ 15%]
........................................................................ [ 15%]
........................................................................ [ 15%]
........................................................................ [ 15%]
...........................ss.s.ss...................................... [ 15%]
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
.....s.................................................................. [ 19%]
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
..........................................................s............. [ 25%]
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
.......s................................................................ [ 37%]
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
........................................................................ [ 47%]
........................................................................ [ 47%]
........................................................................ [ 47%]
........................................................................ [ 47%]
........................................................................ [ 47%]
........................................................................ [ 47%]
................................s....................................... [ 47%]
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
..........................s............................................. [ 56%]
........................................................................ [ 56%]
........................................................................ [ 56%]
........................................................................ [ 56%]
........................................................................ [ 56%]
.............................................................sssss...... [ 56%]
........................................................................ [ 57%]
........................................................................ [ 57%]
..............................................s......................... [ 57%]
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
..............................................................F......... [ 58%]
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
.....................................F..................F............... [ 61%]
........................................................................ [ 61%]
........................................................................ [ 61%]
........................................................................ [ 61%]
........................................................................ [ 61%]
........................................................................ [ 61%]
....................F.F.............................F..F...F.....F...... [ 62%]
........................................................................ [ 62%]
........................................................................ [ 62%]
........................................................................ [ 62%]
........................................................................ [ 62%]
........................................................................ [ 62%]
........................................................................ [ 62%]
........................................................................ [ 62%]
........................................................................ [ 63%]
..............................................F......................... [ 63%]
..........................................................F............. [ 63%]
........................................................................ [ 63%]
........................................................................ [ 63%]
.......................................s................................ [ 63%]
........................................................................ [ 63%]
........................................................................ [ 63%]
...........................F............................................ [ 64%]
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
.......................................F................................ [ 68%]
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
........................................................................ [ 74%]
..s.sss................................................................. [ 74%]
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
.............................................s.......................... [ 76%]
........................................................................ [ 77%]
...................................FF................................... [ 77%]
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
....s......ss........................................................... [ 79%]
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
........................................................................ [ 86%]
........................................................................ [ 86%]
........................................................................ [ 86%]
........................................................................ [ 86%]
........................................................................ [ 86%]
........................................................................ [ 86%]
........................................................................ [ 86%]
................F....................................................... [ 86%]
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
..................s..................................................... [ 88%]
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
............................................................F........... [ 95%]
........................................................................ [ 95%]
.........................F....F.........F..F.F.......................... [ 95%]
........................................................................ [ 95%]
........................................................................ [ 96%]
........................................................................ [ 96%]
........................................................................ [ 96%]
........................................................................ [ 96%]
........................................................................ [ 96%]
.......................................................F................ [ 96%]
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
..........                                                               [100%]/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/lib/python3.12/site-packages/_pytest/unraisableexception.py:67: PytestUnraisableExceptionWarning: Exception ignored in: <function gc_cumulative_time.<locals>.gc_callback at 0x7cc497a4f740>

Traceback (most recent call last):
  File "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/lib/python3.12/site-packages/hypothesis/internal/conjecture/junkdrawer.py", line 497, in gc_callback
    now = _perf_counter()
          ^^^^^^^^^^^^^^^
KeyboardInterrupt

Enable tracemalloc to get traceback where the object was allocated.
See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.
  warnings.warn(pytest.PytestUnraisableExceptionWarning(msg))


═══════════════════════════════ inline-snapshot ════════════════════════════════
INFO: CI run was detected because environment variable "CI" was defined. 
inline-snapshot runs with --inline-snapshot=disable by default in CI. This means
that tests with snapshots will continue to run, but snapshot(x) will only return
x and inline-snapshot will not be able to fix snapshots or generate reports. You
can change this by using --inline-snapshot=report for example.


=================================== FAILURES ===================================
_______________________ test_sigterm_leaves_run_running ________________________
[gw6] linux -- Python 3.12.3 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/bin/python

monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7cc4967526f0>
tmp_path = PosixPath('/var/tmp/sase-3573d744/pytest-of-bryan/pytest-2/popen-gw6/test_sigterm_leaves_run_runnin0')
capsys = <_pytest.capture.CaptureFixture object at 0x7cc495a8f0b0>

    def test_sigterm_leaves_run_running(
        monkeypatch: pytest.MonkeyPatch, tmp_path: Path, capsys: pytest.CaptureFixture[str]
    ) -> None:
        import signal as signal_module
    
        from sase.procs import read_procs, wait_for_proc
        from sase.tool.control import ToolStopCliRequest, handle_stop
    
        _clean_env(monkeypatch, tmp_path)
        _agent_env(monkeypatch, tmp_path)
        monkeypatch.setenv("SASE_PROVIDER_SYNC_SOFT_CEILING_SECONDS", "60")
        previous_term = signal_module.getsignal(signal_module.SIGTERM)
        previous_int = signal_module.getsignal(signal_module.SIGINT)
        previous_hup = signal_module.getsignal(signal_module.SIGHUP)
        stop_fired = threading.Event()
    
        def _kill_after_launch() -> None:
            deadline = time.monotonic() + 60
            while time.monotonic() < deadline and not stop_fired.is_set():
                try:
                    rows = _rows()
                except Exception:  # noqa: BLE001 - the main thread owns the store.
                    rows = []
                if any(row.get("launch_mode") == "handoff" for row in rows):
                    break
                time.sleep(0.2)  # sase-test-wait: follower reservation handshake
            time.sleep(2.0)  # sase-test-wait: follower is inside its bounded wait
            if stop_fired.is_set():
                return
            os.kill(os.getpid(), signal_module.SIGTERM)
    
        killer = threading.Thread(target=_kill_after_launch, daemon=True)
        try:
            killer.start()
            code = execute_tool_run(_request("--", "sh", "-c", "sleep 60"))
        finally:
            stop_fired.set()
            killer.join(timeout=10)
            assert signal_module.getsignal(signal_module.SIGTERM) is previous_term
            assert signal_module.getsignal(signal_module.SIGINT) is previous_int
            assert signal_module.getsignal(signal_module.SIGHUP) is previous_hup
>       assert code == 143
E       assert 124 == 143

/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/tests/tool/test_inline_escalation.py:231: AssertionError
----------------------------- Captured stderr call -----------------------------

Received SIGTERM - agent was killed
sase tool run 0002657691da490e77d2a3324176be3d
sase tool run: ad-hoc (run 0002657691da490e77d2a3324176be3d) is still running after 1m3s; it was not stopped.
This agent's soft ceiling is 1m (SASE_PROVIDER_SYNC_SOFT_CEILING_SECONDS=60).
Hand the same run to a monitor and end this turn (nothing reruns):
  sase monitor start -J 0002657691da490e77d2a3324176be3d -p verify -r 'finish ad-hoc (joined run)' -n '<what the follow-up should do with the result>'
Or wait again inline, bounded by the same ceiling:
  sase tool wait 0002657691da490e77d2a3324176be3d -T 200
Unless a monitor joins it, this run is stopped when this agent's turn ends.
_____________ test_repeat_hint_render_reuses_result_and_renderable _____________
[gw4] linux -- Python 3.12.3 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/bin/python

tmp_path = PosixPath('/var/tmp/sase-3573d744/pytest-of-bryan/pytest-2/popen-gw4/test_repeat_hint_render_reuses0')

    def test_repeat_hint_render_reuses_result_and_renderable(tmp_path: Path) -> None:
        workspace = tmp_path / "workspace"
        workspace.mkdir()
        agent = make_artifact_agent(
            tmp_path,
            status="DONE",
            workspace_dir=str(workspace),
        )
        Path(agent.response_path or "").write_text(
            "Open src/reused.py\n",
            encoding="utf-8",
        )
        panel = FakePromptPanel()
        cache_detail_header_summary(panel, agent, DetailHeaderSummary())
    
        first = panel.update_display_with_hints(agent)
        first_renderable = panel.captured[-1]
        second = panel.update_display_with_hints(agent)
    
        assert first is second
        assert panel.captured[-1] is first_renderable
        from rich.console import Group
        from sase.ace.tui.widgets.decks.card_part import CardPart
    
        assert isinstance(first_renderable, Group)
        assert any(isinstance(c, CardPart) for c in first_renderable.renderables)
>       assert first.file_hints == {
            1: str(workspace / "src/raw.py"),
            2: str(workspace / "src/reused.py"),
        }
E       AssertionError: assert {1: '/var/tmp...rc/reused.py'} == {1: '/var/tmp...rc/reused.py'}
E         
E         Omitting 1 identical items, use -vv to show
E         Differing items:
E         {2: '/var/tmp/sase-3573d744/pytest-of-bryan/pytest-2/popen-gw4/test_repeat_hint_render_reuses0/workspace/src/raw.py'} != {2: '/var/tmp/sase-3573d744/pytest-of-bryan/pytest-2/popen-gw4/test_repeat_hint_render_reuses0/workspace/src/reused.py'}
E         Left contains 1 more item:
E         {3: '/var/tmp/sase-3573d744/pytest-of-bryan/pytest-2/popen-gw4/test_repeat_hint_render_reuses0/workspace/src/reused.py'}
E         
E         Full diff:
E           {
E               1: '/var/tmp/sase-3573d744/pytest-of-bryan/pytest-2/popen-gw4/test_repeat_hint_render_reuses0/workspace/src/raw.py',
E         +     2: '/var/tmp/sase-3573d744/pytest-of-bryan/pytest-2/popen-gw4/test_repeat_hint_render_reuses0/workspace/src/raw.py',
E         -     2: '/var/tmp/sase-3573d744/pytest-of-bryan/pytest-2/popen-gw4/test_repeat_hint_render_reuses0/workspace/src/reused.py',
E         ?     ^
E         +     3: '/var/tmp/sase-3573d744/pytest-of-bryan/pytest-2/popen-gw4/test_repeat_hint_render_reuses0/workspace/src/reused.py',
E         ?     ^
E           }

tests/ace/tui/widgets/test_agent_display_hint_cache.py:49: AssertionError
__________ test_changed_reply_invalidates_hint_document_and_mappings ___________
[gw4] linux -- Python 3.12.3 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/bin/python

tmp_path = PosixPath('/var/tmp/sase-3573d744/pytest-of-bryan/pytest-2/popen-gw4/test_changed_reply_invalidates0')

    def test_changed_reply_invalidates_hint_document_and_mappings(tmp_path: Path) -> None:
        workspace = tmp_path / "workspace"
        workspace.mkdir()
        agent = make_artifact_agent(
            tmp_path,
            status="DONE",
            workspace_dir=str(workspace),
        )
        response_path = Path(agent.response_path or "")
        response_path.write_text("Open src/first.py\n", encoding="utf-8")
        panel = FakePromptPanel()
        cache_detail_header_summary(panel, agent, DetailHeaderSummary())
    
        first = panel.update_display_with_hints(agent)
        first_renderable = panel.captured[-1]
        response_path.write_text(
            "Open src/second-and-longer.py\n",
            encoding="utf-8",
        )
        second = panel.update_display_with_hints(agent)
    
        assert second is not first
        assert panel.captured[-1] is not first_renderable
        assert str(workspace / "src/first.py") not in second.file_hints.values()
        assert str(workspace / "src/second-and-longer.py") in second.file_hints.values()
>       assert "[2] src/second-and-longer.py" in plain_of(panel.captured[-1])
E       AssertionError: assert '[2] src/second-and-longer.py' in 'AGENT TURN\nName: unassigned\nPatch: test_cl\nTimestamps: START | 2024-01-01 14:23:45\n            DONE  | 2024-01-01...────────────────────\n\nAGENT PROMPT\nLaunch from [2] @src/raw.py\n\nAGENT CHAT\nOpen [3] src/second-and-longer.py\n\n'
E        +  where 'AGENT TURN\nName: unassigned\nPatch: test_cl\nTimestamps: START | 2024-01-01 14:23:45\n            DONE  | 2024-01-01...────────────────────\n\nAGENT PROMPT\nLaunch from [2] @src/raw.py\n\nAGENT CHAT\nOpen [3] src/second-and-longer.py\n\n' = plain_of(<rich.console.Group object at 0x7951abe3f200>)

tests/ace/tui/widgets/test_agent_display_hint_cache.py:111: AssertionError
________ TestAgentRawPromptRendering.test_done_agent_renders_raw_prompt ________
[gw4] linux -- Python 3.12.3 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/bin/python

self = <tests.ace.tui.widgets.test_agent_display_raw_prompt.TestAgentRawPromptRendering object at 0x7951e364ede0>
tmp_path = PosixPath('/var/tmp/sase-3573d744/pytest-of-bryan/pytest-2/popen-gw4/test_done_agent_renders_raw_pr0')

    def test_done_agent_renders_raw_prompt(self, tmp_path: Path) -> None:
        panel = FakePromptPanel()
        agent = make_artifact_agent(tmp_path, status="DONE")
    
        panel.update_display(agent)
    
        plain = plain_of(panel.captured[-1])
        assert "AGENT RAW PROMPT" in plain
        assert "Launch from @src/raw.py" in plain
        assert "AGENT PROMPT" in plain
        assert "AGENT CHAT" in plain
        rendered = panel.captured[-1]
        assert_rendered_section_is_compact(
            rendered,
            "AGENT RAW PROMPT",
            "Launch from @src/raw.py",
        )
>       assert_rendered_section_is_compact(
            rendered,
            "AGENT PROMPT",
            "Expanded prompt body",
        )

tests/ace/tui/widgets/test_agent_display_raw_prompt.py:44: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

renderable = <rich.console.Group object at 0x7951a9bb6a50>
heading = 'AGENT PROMPT', first_content_prefix = 'Expanded prompt body'
widths = (60, 120)

    def assert_rendered_section_is_compact(
        renderable: object,
        heading: str,
        first_content_prefix: str,
        *,
        widths: tuple[int, ...] = (60, 120),
    ) -> None:
        """Assert compact section spacing after Rich renders Group boundaries."""
        for width in widths:
            output = StringIO()
            console = Console(file=output, width=width, color_system=None)
            console.print(renderable, end="")
            lines = output.getvalue().splitlines()
            heading_index = lines.index(heading)
>           assert lines[heading_index + 1].startswith(first_content_prefix)
                   ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
E           AssertionError

tests/ace/tui/widgets/_agent_display_metadata_helpers.py:102: AssertionError
_ TestAgentRawPromptRendering.test_agent_prompt_and_chat_use_logical_project_name _
[gw4] linux -- Python 3.12.3 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/bin/python

self = <tests.ace.tui.widgets.test_agent_display_raw_prompt.TestAgentRawPromptRendering object at 0x7951e364e630>
tmp_path = PosixPath('/var/tmp/sase-3573d744/pytest-of-bryan/pytest-2/popen-gw4/test_agent_prompt_and_chat_use0')
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7951a9d70470>

    def test_agent_prompt_and_chat_use_logical_project_name(
        self,
        tmp_path: Path,
        monkeypatch,
    ) -> None:
        monkeypatch.setattr("sase.project_aliases._vcs_workflow_names", lambda: {"gh"})
        monkeypatch.setattr(
            pdn,
            "_project_display_name_map_cached",
            lambda *_args, **_kwargs: {"gh_acme__widgets": "widgets"},
        )
        panel = FakePromptPanel()
        agent = make_artifact_agent(tmp_path, status="DONE")
        Path(agent.artifacts_dir, "01_prompt.md").write_text(
            "Prompt says #gh:gh_acme__widgets inspect.\n",
            encoding="utf-8",
        )
        Path(agent.response_path).write_text(
            "Response echoes #gh:gh_acme__widgets now.\n",
            encoding="utf-8",
        )
    
        panel.update_display(agent)
    
        plain = plain_of(panel.captured[-1])
>       assert "Prompt says #gh:widgets inspect." in plain
E       AssertionError: assert 'Prompt says #gh:widgets inspect.' in 'AGENT TURN\nName: unassigned\nPatch: test_cl\nTimestamps: START | 2024-01-01 14:23:45\n            DONE  | 2024-01-01...─────────────────────────\n\nAGENT PROMPT\n\nLaunch from @src/raw.py\nAGENT CHAT\n\nResponse echoes #gh:widgets now.\n'

tests/ace/tui/widgets/test_agent_display_raw_prompt.py:92: AssertionError
_ TestAgentRawPromptHintMode.test_hint_mode_prompt_and_chat_use_logical_project_name _
[gw4] linux -- Python 3.12.3 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/bin/python

self = <tests.ace.tui.widgets.test_agent_display_raw_prompt_hints.TestAgentRawPromptHintMode object at 0x7951e36659a0>
tmp_path = PosixPath('/var/tmp/sase-3573d744/pytest-of-bryan/pytest-2/popen-gw4/test_hint_mode_prompt_and_chat0')
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7951abecaab0>

    def test_hint_mode_prompt_and_chat_use_logical_project_name(
        self,
        tmp_path: Path,
        monkeypatch,
    ) -> None:
        monkeypatch.setattr("sase.project_aliases._vcs_workflow_names", lambda: {"gh"})
        monkeypatch.setattr(
            pdn,
            "_project_display_name_map_cached",
            lambda *_args, **_kwargs: {"gh_acme__widgets": "widgets"},
        )
        panel = FakePromptPanel()
        agent = make_artifact_agent(
            tmp_path,
            status="DONE",
            raw_prompt="#gh:gh_acme__widgets raw",
        )
        Path(agent.artifacts_dir, "01_prompt.md").write_text(
            "#gh:gh_acme__widgets prompt\n",
            encoding="utf-8",
        )
        Path(agent.response_path).write_text(
            "#gh:gh_acme__widgets response\n",
            encoding="utf-8",
        )
    
        panel.update_display_with_hints(agent)
    
        plain = plain_of(panel.captured[-1])
        assert "#gh:widgets raw" in plain
>       assert "#gh:widgets prompt" in plain
E       AssertionError: assert '#gh:widgets prompt' in 'AGENT TURN\nName: unassigned\nPatch: test_cl\nTimestamps: START | 2024-01-01 14:23:45\n            DONE  | 2024-01-01...─────────────────────────────────────────────\n\nAGENT PROMPT\n#gh:widgets raw\n\nAGENT CHAT\n#gh:widgets response\n\n'

tests/ace/tui/widgets/test_agent_display_raw_prompt_hints.py:62: AssertionError
_ TestAgentRawPromptHintMode.test_hint_mode_renders_raw_prompt_for_terminal_agent _
[gw4] linux -- Python 3.12.3 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/bin/python

self = <tests.ace.tui.widgets.test_agent_display_raw_prompt_hints.TestAgentRawPromptHintMode object at 0x7951e3666c00>
tmp_path = PosixPath('/var/tmp/sase-3573d744/pytest-of-bryan/pytest-2/popen-gw4/test_hint_mode_renders_raw_pro0')

    def test_hint_mode_renders_raw_prompt_for_terminal_agent(
        self,
        tmp_path: Path,
    ) -> None:
        workspace_dir = tmp_path / "workspace"
        workspace_dir.mkdir()
        panel = FakePromptPanel()
        agent = make_artifact_agent(
            tmp_path,
            status="DONE",
            workspace_dir=str(workspace_dir),
        )
    
        result = panel.update_display_with_hints(agent)
    
        rendered = panel.captured[-1]
        plain = plain_of(rendered)
        assert "AGENT RAW PROMPT" in plain
        assert "[1] @src/raw.py" in plain
        assert result.file_hints[1] == str(workspace_dir / "src/raw.py")
        assert_logical_section_is_compact(
            rendered,
            "AGENT RAW PROMPT",
            "Launch from [1] @src/raw.py",
        )
>       assert_logical_section_is_compact(
            rendered,
            "AGENT PROMPT",
            "Expanded prompt body",
        )

tests/ace/tui/widgets/test_agent_display_raw_prompt_hints.py:121: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

renderable = <rich.console.Group object at 0x7951a9bb7e00>
heading = 'AGENT PROMPT', first_content_prefix = 'Expanded prompt body'

    def assert_logical_section_is_compact(
        renderable: Any,
        heading: str,
        first_content_prefix: str,
    ) -> None:
        """Assert that logical text has no spacer after a section heading."""
        plain = _logical_plain(renderable)
        lines = plain.splitlines()
        heading_index = lines.index(heading)
>       assert lines[heading_index + 1].startswith(first_content_prefix)
               ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
E       AssertionError

tests/ace/tui/widgets/_agent_display_metadata_helpers.py:84: AssertionError
_ TestAgentRawPromptHintMode.test_hint_mode_keeps_typed_artifact_refs_semantic _
[gw4] linux -- Python 3.12.3 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/bin/python

self = <tests.ace.tui.widgets.test_agent_display_raw_prompt_hints.TestAgentRawPromptHintMode object at 0x7951e3667e60>
tmp_path = PosixPath('/var/tmp/sase-3573d744/pytest-of-bryan/pytest-2/popen-gw4/test_hint_mode_keeps_typed_art0')

    def test_hint_mode_keeps_typed_artifact_refs_semantic(
        self,
        tmp_path: Path,
    ) -> None:
        workspace_dir = tmp_path / "workspace"
        workspace_dir.mkdir()
        panel = FakePromptPanel()
        agent = make_artifact_agent(
            tmp_path,
            status="DONE",
            workspace_dir=str(workspace_dir),
            raw_prompt="#work(@plans:202608/design.md#L12) and @src/raw.py",
        )
    
        result = panel.update_display_with_hints(agent)
    
        rendered = _header_text(panel.captured[-1])
        assert "#work(@plans:202608/design.md#L12) and [1] @src/raw.py" in (
            rendered.plain
        )
>       assert result.file_hints == {1: str(workspace_dir / "src/raw.py")}
E       AssertionError: assert {1: '/var/tmp...e/src/raw.py'} == {1: '/var/tmp...e/src/raw.py'}
E         
E         Omitting 1 identical items, use -vv to show
E         Left contains 2 more items:
E         {2: '/var/tmp/sase-3573d744/pytest-of-bryan/pytest-2/popen-gw4/test_hint_mode_keeps_typed_art0/workspace/202608/design.md',
E          3: '/var/tmp/sase-3573d744/pytest-of-bryan/pytest-2/popen-gw4/test_hint_mode_keeps_typed_art0/workspace/src/raw.py'}
E         
E         Full diff:
E           {
E               1: '/var/tmp/sase-3573d744/pytest-of-bryan/pytest-2/popen-gw4/test_hint_mode_keeps_typed_art0/workspace/src/raw.py',
E         +     2: '/var/tmp/sase-3573d744/pytest-of-bryan/pytest-2/popen-gw4/test_hint_mode_keeps_typed_art0/workspace/202608/design.md',
E         +     3: '/var/tmp/sase-3573d744/pytest-of-bryan/pytest-2/popen-gw4/test_hint_mode_keeps_typed_art0/workspace/src/raw.py',
E           }

tests/ace/tui/widgets/test_agent_display_raw_prompt_hints.py:186: AssertionError
_ TestAgentRawPromptHintMode.test_hint_mode_renders_timestamp_file_hints_before_body_hints _
[gw4] linux -- Python 3.12.3 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/bin/python

self = <tests.ace.tui.widgets.test_agent_display_raw_prompt_hints.TestAgentRawPromptHintMode object at 0x7951e367cb30>
tmp_path = PosixPath('/var/tmp/sase-3573d744/pytest-of-bryan/pytest-2/popen-gw4/test_hint_mode_renders_timesta0')

    def test_hint_mode_renders_timestamp_file_hints_before_body_hints(
        self,
        tmp_path: Path,
    ) -> None:
        workspace_dir = tmp_path / "workspace"
        workspace_dir.mkdir()
        panel = FakePromptPanel()
        agent = make_artifact_agent(
            tmp_path,
            status="DONE",
            workspace_dir=str(workspace_dir),
        )
        Path(agent.artifacts_dir, "01_prompt.md").write_text(
            "Expanded prompt mentions src/prompt.py\n",
            encoding="utf-8",
        )
        feedback_time = datetime(2024, 1, 1, 14, 25, 0)
        rejected_plan_path = (
            Path.home() / ".sase" / "plans" / "202605" / "wait_requires_success.md"
        )
        expected_hint_path = os.path.expanduser(
            "~/.sase/plans/202605/wait_requires_success.md"
        )
        agent.feedback_times = [feedback_time]
        agent.feedback_plan_paths = {feedback_time: str(rejected_plan_path)}
    
        result = panel.update_display_with_hints(agent)
    
        plain = plain_of(panel.captured[-1])
        assert "[1] ~/.sase/plans/202605/wait_requires_success.md" in plain
        assert "[2] @src/raw.py" in plain
>       assert "[3] src/prompt.py" in plain
E       AssertionError: assert '[3] src/prompt.py' in 'AGENT TURN\nName: unassigned\nPatch: test_cl\nTimestamps: START | 2024-01-01 14:23:45\n            FBACK | 2024-01-01...──────────────────────────────────\n\nAGENT PROMPT\nLaunch from [3] @src/raw.py\n\nAGENT CHAT\nFinal response body\n\n'

tests/ace/tui/widgets/test_agent_display_raw_prompt_hints.py:286: AssertionError
_______________ test_hint_mode_keeps_collapsed_header_unchanged ________________
[gw4] linux -- Python 3.12.3 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/bin/python

tmp_path = PosixPath('/var/tmp/sase-3573d744/pytest-of-bryan/pytest-2/popen-gw4/test_hint_mode_keeps_collapsed0')

    async def test_hint_mode_keeps_collapsed_header_unchanged(tmp_path: Any) -> None:
        from pathlib import Path
    
        from tests.ace.tui.widgets._agent_display_helpers import make_artifact_agent
    
        workspace = tmp_path / "workspace"
        (workspace / "src").mkdir(parents=True)
        (workspace / "src" / "example.py").write_text("", encoding="utf-8")
        (workspace / "src" / "body.py").write_text("", encoding="utf-8")
        agent = make_artifact_agent(
            tmp_path,
            status="DONE",
            raw_prompt="Read @src/example.py",
            workspace_dir=str(workspace),
        )
        Path(str(agent.response_path)).write_text("See src/body.py\n", encoding="utf-8")
        app = DetailApp()
        async with app.run_test(size=(80, 24)) as pilot:
            detail = app.query_one("#agent-detail-panel", AgentDetail)
            await show_agent_full(detail, agent, pilot)
            panel = header_panel(detail)
            assert not panel.is_expanded
            pre_text = header_text(panel)
            pre_rows = panel.rendered_row_count
            result = detail.update_display_with_hints(agent)
            await pilot.pause()
            assert not panel.is_expanded
            assert header_text(panel) == pre_text
            assert panel.rendered_row_count == pre_rows
            assert "[1]" not in header_text(panel)
>           assert str(workspace / "src/example.py") not in result.file_hints.values()
E           AssertionError: assert '/var/tmp/sase-3573d744/pytest-of-bryan/pytest-2/popen-gw4/test_hint_mode_keeps_collapsed0/workspace/src/example.py' not in dict_values(['/var/tmp/sase-3573d744/pytest-of-bryan/pytest-2/popen-gw4/test_hint_mode_keeps_collapsed0/workspace/src/...y', '/var/tmp/sase-3573d744/pytest-of-bryan/pytest-2/popen-gw4/test_hint_mode_keeps_collapsed0/workspace/src/body.py'])
E            +  where '/var/tmp/sase-3573d744/pytest-of-bryan/pytest-2/popen-gw4/test_hint_mode_keeps_collapsed0/workspace/src/example.py' = str((PosixPath('/var/tmp/sase-3573d744/pytest-of-bryan/pytest-2/popen-gw4/test_hint_mode_keeps_collapsed0/workspace') / 'src/example.py'))
E            +  and   dict_values(['/var/tmp/sase-3573d744/pytest-of-bryan/pytest-2/popen-gw4/test_hint_mode_keeps_collapsed0/workspace/src/...y', '/var/tmp/sase-3573d744/pytest-of-bryan/pytest-2/popen-gw4/test_hint_mode_keeps_collapsed0/workspace/src/body.py']) = <built-in method values of dict object at 0x7951a83893c0>()
E            +    where <built-in method values of dict object at 0x7951a83893c0> = {1: '/var/tmp/sase-3573d744/pytest-of-bryan/pytest-2/popen-gw4/test_hint_mode_keeps_collapsed0/workspace/src/example.py', 2: '/var/tmp/sase-3573d744/pytest-of-bryan/pytest-2/popen-gw4/test_hint_mode_keeps_collapsed0/workspace/src/body.py'}.values
E            +      where {1: '/var/tmp/sase-3573d744/pytest-of-bryan/pytest-2/popen-gw4/test_hint_mode_keeps_collapsed0/workspace/src/example.py', 2: '/var/tmp/sase-3573d744/pytest-of-bryan/pytest-2/popen-gw4/test_hint_mode_keeps_collapsed0/workspace/src/body.py'} = AgentHintRender(file_hints={1: '/var/tmp/sase-3573d744/pytest-of-bryan/pytest-2/popen-gw4/test_hint_mode_keeps_collaps... glossary_reports={}, memory_reports={}, artifact_read_refs={}, memory_version_pins={}, header_enrichment_pending=True).file_hints

tests/ace/tui/widgets/test_agent_header_panel_basic.py:203: AssertionError
_______ test_collapsed_preview_shows_quote_bar_and_body_omits_raw_prompt _______
[gw4] linux -- Python 3.12.3 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/bin/python

tmp_path = PosixPath('/var/tmp/sase-3573d744/pytest-of-bryan/pytest-2/popen-gw4/test_collapsed_preview_shows_q0')

    async def test_collapsed_preview_shows_quote_bar_and_body_omits_raw_prompt(
        tmp_path: Any,
    ) -> None:
        app = DetailApp()
        async with app.run_test(size=(80, 24)) as pilot:
            detail = app.query_one("#agent-detail-panel", AgentDetail)
            await show_agent_full(
                detail, artifact_agent(tmp_path, "a", LONG_RAW_PROMPT), pilot
            )
            panel = header_panel(detail)
            assert not panel.is_expanded
            _assert_card(panel)
            assert "rendering the AGENT RAW PROMPT" in header_text(panel)
            prompt = detail.query_one("#agent-prompt-panel", AgentPromptPanel)
            body = renderable_to_text(prompt.content) or ""
>           assert "AGENT RAW PROMPT" not in body
E           AssertionError: assert 'AGENT RAW PROMPT' not in 'AGENT PROMP...esponse body'
E             
E             'AGENT RAW PROMPT' is contained here:
E               ering the AGENT RAW PROMPT section in the sticky header above the agent data deck panel? Make 
E             ?           ++++++++++++++++
E               sure that we provide a good preview of the contents in this section.                                                    
E                                                                                                                                       
E               - first list item explains the quote bar                                                                                
E               - second list item explains the row budget                                                                              
E               ```                                                                                                                     
E               some fenced code block line                                                                                             
E               ```                                                                                                                     
E               A final hard-wrapped prose paragraph keeps going so the preview budget overflows and the border subtitle names the      
E               hidden line count.                                                                                                      
E               AGENT CHAT
E               Final response body

tests/ace/tui/widgets/test_agent_header_panel_preview.py:81: AssertionError
_________ test_bottom_pinned_body_stays_pinned_across_row_count_change _________
[gw4] linux -- Python 3.12.3 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/bin/python

tmp_path = PosixPath('/var/tmp/sase-3573d744/pytest-of-bryan/pytest-2/popen-gw4/test_bottom_pinned_body_stays_0')

    async def test_bottom_pinned_body_stays_pinned_across_row_count_change(
        tmp_path: Any,
    ) -> None:
        app = DetailApp()
        async with app.run_test(size=(80, 24)) as pilot:
            detail = app.query_one("#agent-detail-panel", AgentDetail)
            await show_agent_full(
                detail, artifact_agent(tmp_path, "a", _SHORT_RAW_PROMPT), pilot
            )
            panel = header_panel(detail)
            before = panel.rendered_row_count
            main_view = detail.deck_area.panel(0).main_view
            main_view.pin_to_bottom()
            assert bool(main_view.is_pinned_to_bottom) is True
            await show_agent_full(
                detail, artifact_agent(tmp_path, "b", LONG_RAW_PROMPT), pilot
            )
            assert panel.rendered_row_count != before
>           assert bool(main_view.is_pinned_to_bottom) is True
E           assert False is True
E            +  where False = bool(False)
E            +    where False = MainDeckView().is_pinned_to_bottom

tests/ace/tui/widgets/test_agent_header_panel_preview.py:402: AssertionError
___________ test_agent_macro_and_prompt_receive_roles_replies_do_not ___________
[gw4] linux -- Python 3.12.3 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/bin/python

tmp_path = PosixPath('/var/tmp/sase-3573d744/pytest-of-bryan/pytest-2/popen-gw4/test_agent_macro_and_prompt_re0')

    def test_agent_macro_and_prompt_receive_roles_replies_do_not(
        tmp_path: Path,
    ) -> None:
        panel = FakePromptPanel()
        source = "Ask Agent Clan to inspect sase-core; run `checks`"
        glossary = dynamic_catalog_for_term(tmp_path, "Agent Clan")
        repo = dynamic_catalog_for_identifier(tmp_path, "sase-core")
        install_panel_semantics(panel, glossary=glossary, repo=repo)
        agent = make_artifact_agent(
            tmp_path,
            status="DONE",
            raw_prompt="#git:sase %auto Ask Agent Clan to inspect sase-core",
        )
        Path(agent.artifacts_dir, "01_prompt.md").write_text(
            source + "\n", encoding="utf-8"
        )
        Path(agent.response_path).write_text(
            "Reply repeats Agent Clan and sase-core.\n",
            encoding="utf-8",
        )
    
        panel.update_display(agent)
        rendered = flatten_card_document(panel.captured[-1])
        header = _header_text(rendered)
        assert MACRO_TOKEN_STYLES["invocation"] in _styles_at(header, "#git")
        assert _has_role_underline(_styles_at(header, "Agent Clan"))
        assert _has_role_underline(_styles_at(header, "sase-core"))
    
        prompt_body = _prompt_body(rendered)
        assert _has_role_underline(_styles_at(prompt_body, "Agent Clan"))
>       inline = _styles_at(prompt_body, "`checks`", offset=1)
                 ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

tests/ace/tui/widgets/test_agent_prompt_semantic.py:198: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

text = <text '#git:sase %auto Ask Agent Clan to inspect sase-core' [Span(0, 51, Style(color=Color('#f8f8f2', ColorType.TRUECO...nderline=True))] Style(bgcolor=Color('#272822', ColorType.TRUECOLOR, triplet=ColorTriplet(red=39, green=40, blue=34)))>
needle = '`checks`', offset = 1

    def _styles_at(
        text: Text | AgentHeaderRenderable,
        needle: str,
        *,
        offset: int = 0,
    ) -> set[str]:
>       position = text.plain.index(needle) + offset
                   ^^^^^^^^^^^^^^^^^^^^^^^^
E       ValueError: substring not found

tests/ace/tui/widgets/test_agent_prompt_semantic.py:64: ValueError
________ test_hinted_raw_prompt_moves_to_identity_and_keeps_its_markers ________
[gw4] linux -- Python 3.12.3 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/bin/python

tmp_path = PosixPath('/var/tmp/sase-3573d744/pytest-of-bryan/pytest-2/popen-gw4/test_hinted_raw_prompt_moves_t0')

    def test_hinted_raw_prompt_moves_to_identity_and_keeps_its_markers(
        tmp_path: Path,
    ) -> None:
        workspace = tmp_path / "workspace"
        workspace.mkdir()
        panel = _DetachedPanel()
        agent = make_artifact_agent(
            tmp_path,
            status="DONE",
            workspace_dir=str(workspace),
            raw_prompt="Read @src/example.py",
        )
    
        result = panel.update_display_with_hints(agent)
    
        identity = find_identity_header(panel.captured[-1])
        assert identity is not None
        assert identity.raw_prompt is not None
        assert identity.raw_prompt.plain == "Read [1] @src/example.py"
>       assert result.file_hints == {1: str(workspace / "src/example.py")}
E       AssertionError: assert {1: '/var/tmp...c/example.py'} == {1: '/var/tmp...c/example.py'}
E         
E         Omitting 1 identical items, use -vv to show
E         Left contains 1 more item:
E         {2: '/var/tmp/sase-3573d744/pytest-of-bryan/pytest-2/popen-gw4/test_hinted_raw_prompt_moves_t0/workspace/src/example.py'}
E         
E         Full diff:
E           {
E               1: '/var/tmp/sase-3573d744/pytest-of-bryan/pytest-2/popen-gw4/test_hinted_raw_prompt_moves_t0/workspace/src/example.py',
E         +     2: '/var/tmp/sase-3573d744/pytest-of-bryan/pytest-2/popen-gw4/test_hinted_raw_prompt_moves_t0/workspace/src/example.py',
E           }

tests/ace/tui/widgets/test_identity_header_raw_prompt.py:127: AssertionError
_______________ test_collapsed_detached_raw_prompt_skips_markers _______________
[gw4] linux -- Python 3.12.3 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/bin/python

tmp_path = PosixPath('/var/tmp/sase-3573d744/pytest-of-bryan/pytest-2/popen-gw4/test_collapsed_detached_raw_pr0')

    def test_collapsed_detached_raw_prompt_skips_markers(tmp_path: Path) -> None:
        workspace = tmp_path / "workspace"
        (workspace / "src").mkdir(parents=True)
        (workspace / "src" / "example.py").write_text("", encoding="utf-8")
        (workspace / "src" / "body.py").write_text("", encoding="utf-8")
        panel = _CollapsedDetachedPanel()
        agent = make_artifact_agent(
            tmp_path,
            status="DONE",
            workspace_dir=str(workspace),
            raw_prompt="Read @src/example.py",
        )
        prompt_path = Path(str(agent.artifacts_dir)) / "01_prompt.md"
        prompt_path.write_text("See src/body.py\n", encoding="utf-8")
    
        result = panel.update_display_with_hints(agent)
    
        identity = find_identity_header(panel.captured[-1])
        assert identity is not None
        assert identity.raw_prompt is not None
        assert identity.raw_prompt.plain == "Read @src/example.py"
        assert "[1]" not in identity.raw_prompt.plain
>       assert str(workspace / "src/example.py") not in result.file_hints.values()
E       AssertionError: assert '/var/tmp/sase-3573d744/pytest-of-bryan/pytest-2/popen-gw4/test_collapsed_detached_raw_pr0/workspace/src/example.py' not in dict_values(['/var/tmp/sase-3573d744/pytest-of-bryan/pytest-2/popen-gw4/test_collapsed_detached_raw_pr0/workspace/src/example.py'])
E        +  where '/var/tmp/sase-3573d744/pytest-of-bryan/pytest-2/popen-gw4/test_collapsed_detached_raw_pr0/workspace/src/example.py' = str((PosixPath('/var/tmp/sase-3573d744/pytest-of-bryan/pytest-2/popen-gw4/test_collapsed_detached_raw_pr0/workspace') / 'src/example.py'))
E        +  and   dict_values(['/var/tmp/sase-3573d744/pytest-of-bryan/pytest-2/popen-gw4/test_collapsed_detached_raw_pr0/workspace/src/example.py']) = <built-in method values of dict object at 0x7951ce9a2c00>()
E        +    where <built-in method values of dict object at 0x7951ce9a2c00> = {1: '/var/tmp/sase-3573d744/pytest-of-bryan/pytest-2/popen-gw4/test_collapsed_detached_raw_pr0/workspace/src/example.py'}.values
E        +      where {1: '/var/tmp/sase-3573d744/pytest-of-bryan/pytest-2/popen-gw4/test_collapsed_detached_raw_pr0/workspace/src/example.py'} = AgentHintRender(file_hints={1: '/var/tmp/sase-3573d744/pytest-of-bryan/pytest-2/popen-gw4/test_collapsed_detached_raw_... glossary_reports={}, memory_reports={}, artifact_read_refs={}, memory_version_pins={}, header_enrichment_pending=True).file_hints

tests/ace/tui/widgets/test_identity_header_raw_prompt.py:153: AssertionError
_____ test_conformance_warns_for_duplicate_root_and_leaked_helper_markers ______
[gw2] linux -- Python 3.12.3 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/bin/python

tmp_path = PosixPath('/var/tmp/sase-3573d744/pytest-of-bryan/pytest-2/popen-gw2/test_conformance_warns_for_dup0')
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x77988b5c8d70>

    def test_conformance_warns_for_duplicate_root_and_leaked_helper_markers(
        tmp_path: Path, monkeypatch
    ) -> None:
        """The deep check names root duplicates, helper gaps, and root leaks."""
        from sase.doctor import checks_instructions
        from sase.instructions import coverage_records, coverage_sessions, run_index
>       from sase.instructions.manifests import _RunManifest
E       ImportError: cannot import name '_RunManifest' from 'sase.instructions.manifests' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/src/sase/instructions/manifests.py)

tests/instructions/test_scoreboard_conformance.py:227: ImportError
____________ test_member_loader_reuses_reply_and_prompt_precedence _____________
[gw6] linux -- Python 3.12.3 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/bin/python

tmp_path = PosixPath('/var/tmp/sase-3573d744/pytest-of-bryan/pytest-2/popen-gw6/test_member_loader_reuses_repl0')

    def test_member_loader_reuses_reply_and_prompt_precedence(tmp_path: Path) -> None:
        artifacts = tmp_path / "artifacts"
        artifacts.mkdir()
        (artifacts / "raw_prompt.md").write_text(
            "\n#research first segment\n",
            encoding="utf-8",
        )
        (artifacts / "01_prompt.md").write_text(
            "\nExpanded prompt body\n",
            encoding="utf-8",
        )
        response = artifacts / "response.md"
        response.write_text("\nFinal member conclusion\nsecond line\n", encoding="utf-8")
        member = _agent(
            "research.one",
            artifacts_dir=str(artifacts),
            response_path=str(response),
        )
    
        snapshot = _load_clan_disk_member_snapshot(
            member,
            ".one",
            frozenset({"replies", "prompts"}),
        )
    
        assert [(entry.kind, entry.preview) for entry in snapshot.replies] == [
            ("AGENT REPLY", "Final member conclusion")
        ]
>       assert [(entry.kind, entry.preview) for entry in snapshot.prompts] == [
            ("AGENT RAW PROMPT", "#research first segment"),
            ("AGENT PROMPT", "Expanded prompt body"),
        ]
E       AssertionError: assert [('AGENT RAW ...rst segment')] == [('AGENT RAW ...prompt body')]
E         
E         At index 1 diff: ('AGENT PROMPT', '#research first segment') != ('AGENT PROMPT', 'Expanded prompt body')
E         
E         Full diff:
E           [
E               (
E                   'AGENT RAW PROMPT',
E                   '#research first segment',
E               ),
E               (
E                   'AGENT PROMPT',
E         -         'Expanded prompt body',
E         +         '#research first segment',
E               ),
E           ]

tests/ace/tui/widgets/test_agent_clan_aggregation.py:164: AssertionError
_ test_agent_session_content_hints_are_full_at_both_levels_and_use_phase_workspace _
[gw6] linux -- Python 3.12.3 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/bin/python

tmp_path = PosixPath('/var/tmp/sase-3573d744/pytest-of-bryan/pytest-2/popen-gw6/test_agent_session_content_hin0')

    def test_agent_session_content_hints_are_full_at_both_levels_and_use_phase_workspace(
        tmp_path: Path,
    ) -> None:
        root, child = make_agent_session(tmp_path)
        root_workspace = tmp_path / "root-workspace"
        child_workspace = tmp_path / "child-workspace"
        root_workspace.mkdir()
        child_workspace.mkdir()
        root.workspace_dir = str(root_workspace)
        child.workspace_dir = str(child_workspace)
    
        root_dir = Path(root.artifacts_dir or "")
        child_dir = Path(child.artifacts_dir or "")
        (root_dir / "raw_prompt.md").write_text(
            "@docs/visible-macro.md\n"
            + "\n".join(f"macro filler {index}" for index in range(2, 15))
            + "\n@docs/hidden-macro.md\n",
            encoding="utf-8",
        )
        (root_dir / "01_prompt.md").write_text(
            "src/visible-prompt.py\n"
            + "\n".join(f"prompt filler {index}" for index in range(2, 15))
            + "\nsrc/hidden-prompt.py\n",
            encoding="utf-8",
        )
        (root_dir / "response.md").write_text(
            "root/hidden-reply.txt\nroot filler 2\nroot filler 3\n"
            "root filler 4\nroot filler 5\nroot/visible-reply.txt\n",
            encoding="utf-8",
        )
        (child_dir / "response.md").write_text(
            "child/hidden-reply.txt\nchild filler 2\nchild filler 3\n"
            "child filler 4\nchild filler 5\nchild/visible-reply.txt\n",
            encoding="utf-8",
        )
    
        expected_paths = {
            str(root_workspace / "docs/visible-macro.md"),
            str(root_workspace / "docs/hidden-macro.md"),
            str(root_workspace / "src/visible-prompt.py"),
            str(root_workspace / "src/hidden-prompt.py"),
            str(root_workspace / "root/hidden-reply.txt"),
            str(root_workspace / "root/visible-reply.txt"),
            str(child_workspace / "child/hidden-reply.txt"),
            str(child_workspace / "child/visible-reply.txt"),
        }
        rendered_paths: list[set[str]] = []
        for level in (FoldLevel.EXPANDED, FoldLevel.FULLY_EXPANDED):
            panel = FakePromptPanel()
            panel.app = SimpleNamespace(
                panel_fold_level=level,
                _panel_fold_overrides=SimpleNamespace(snapshot=lambda: {}),
            )
            cache_detail_header_summary(panel, root, DetailHeaderSummary())
    
            result = panel.update_display_with_hints(root)
            rendered_paths.append(set(result.file_hints.values()))
    
>       assert rendered_paths == [expected_paths, expected_paths]
E       AssertionError: assert [{'/var/tmp/s...e-reply.txt'}] == [{'/var/tmp/s...ly.txt', ...}]
E         
E         At index 0 diff: {'/var/tmp/sase-3573d744/pytest-of-bryan/pytest-2/popen-gw6/test_agent_session_content_hin0/root-workspace/docs/visible-macro.md', '/var/tmp/sase-3573d744/pytest-of-bryan/pytest-2/popen-gw6/test_agent_session_content_hin0/root-workspace/root/visible-reply.txt', '/var/tmp/sase-3573d744/pytest-of-bryan/pytest-2/popen-gw6/test_agent_session_content_hin0/root-workspace/root/hidden-reply.txt', '/var/tmp/sase-3573d744/pytest-of-bryan/pytest-2/popen-gw6/test_agent_session_content_hin0/child-workspace/child/hidden-reply.txt', '/var/tmp/sase-3573d744/pytest-of-bryan/pytest-2/popen-gw6/test_agent_session_content_hin0/root-workspace/docs/hidden-macro.md', '/var/tmp/sase-3573d744/pytest-of-bryan/pytest-2/popen-gw6/test_agent_session_content_hin0/child-workspace/child/visible-reply.txt'} != {'/var/tmp/sase-3573d744/pytest-of-bryan/pytest-2/popen-gw6/test_agent_session_content_hin0/root-workspace/docs/visible-macro.md', '/var/tmp/sase-3573d744/pytest-of-bryan/pytest-2/popen-gw6/test_agent_session_content_hin0/root-workspace/root/hidden-reply.txt', '/var/tmp/sase-3573d744/pytest-of-bryan/pytest-2/popen-gw6/test_agent_session_content_hin0/root-workspace/root/visible-reply.txt', '/var/tmp/sase-3573d744/pytest-of-bryan/pytest-2/popen-gw6/test_agent_session_content_hin0/root-workspace/src/hidden-prompt.py', '/var/tmp/sase-3573d744/pytest-of-bryan/pytest-2/popen-gw6/test_agent_session_content_hin0/root-workspace/src/visible-prompt.py', '/var/tmp/sase-3573d744/pytest-of-bryan/pytest-2/popen-gw6/test_agent_session_content_hin0/child-workspace/child/hidden-reply.txt', '/var/tmp/sase-3573d744/pytest-of-bryan/pytest-2/popen-gw6/test_agent_session_content_hin0/root-workspace/docs/hidden-macro.md', '/var/tmp/sase-3573d744/pytest-of-bryan/pytest-2/popen-gw6/test_agent_session_content_hin0/child-workspace/child/visible-reply.txt'}
E         
E         Full diff:
E           [
E               {
E                   '/var/tmp/sase-3573d744/pytest-of-bryan/pytest-2/popen-gw6/test_agent_session_content_hin0/child-workspace/child/hidden-reply.txt',
E                   '/var/tmp/sase-3573d744/pytest-of-bryan/pytest-2/popen-gw6/test_agent_session_content_hin0/child-workspace/child/visible-reply.txt',
E                   '/var/tmp/sase-3573d744/pytest-of-bryan/pytest-2/popen-gw6/test_agent_session_content_hin0/root-workspace/docs/hidden-macro.md',
E                   '/var/tmp/sase-3573d744/pytest-of-bryan/pytest-2/popen-gw6/test_agent_session_content_hin0/root-workspace/docs/visible-macro.md',
E                   '/var/tmp/sase-3573d744/pytest-of-bryan/pytest-2/popen-gw6/test_agent_session_content_hin0/root-workspace/root/hidden-reply.txt',
E                   '/var/tmp/sase-3573d744/pytest-of-bryan/pytest-2/popen-gw6/test_agent_session_content_hin0/root-workspace/root/visible-reply.txt',
E         -         '/var/tmp/sase-3573d744/pytest-of-bryan/pytest-2/popen-gw6/test_agent_session_content_hin0/root-workspace/src/hidden-prompt.py',
E         -         '/var/tmp/sase-3573d744/pytest-of-bryan/pytest-2/popen-gw6/test_agent_session_content_hin0/root-workspace/src/visible-prompt.py',
E               },
E               {
E                   '/var/tmp/sase-3573d744/pytest-of-bryan/pytest-2/popen-gw6/test_agent_session_content_hin0/child-workspace/child/hidden-reply.txt',
E                   '/var/tmp/sase-3573d744/pytest-of-bryan/pytest-2/popen-gw6/test_agent_session_content_hin0/child-workspace/child/visible-reply.txt',
E                   '/var/tmp/sase-3573d744/pytest-of-bryan/pytest-2/popen-gw6/test_agent_session_content_hin0/root-workspace/docs/hidden-macro.md',
E                   '/var/tmp/sase-3573d744/pytest-of-bryan/pytest-2/popen-gw6/test_agent_session_content_hin0/root-workspace/docs/visible-macro.md',
E                   '/var/tmp/sase-3573d744/pytest-of-bryan/pytest-2/popen-gw6/test_agent_session_content_hin0/root-workspace/root/hidden-reply.txt',
E                   '/var/tmp/sase-3573d744/pytest-of-bryan/pytest-2/popen-gw6/test_agent_session_content_hin0/root-workspace/root/visible-reply.txt',
E         -         '/var/tmp/sase-3573d744/pytest-of-bryan/pytest-2/popen-gw6/test_agent_session_content_hin0/root-workspace/src/hidden-prompt.py',
E         -         '/var/tmp/sase-3573d744/pytest-of-bryan/pytest-2/popen-gw6/test_agent_session_content_hin0/root-workspace/src/visible-prompt.py',
E               },
E           ]

tests/ace/tui/widgets/test_agent_display_agent_session_hints.py:168: AssertionError
_____________ test_session_collapsed_detached_macro_skips_markers ______________
[gw6] linux -- Python 3.12.3 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/bin/python

tmp_path = PosixPath('/var/tmp/sase-3573d744/pytest-of-bryan/pytest-2/popen-gw6/test_session_collapsed_detache0')

    def test_session_collapsed_detached_macro_skips_markers(tmp_path: Path) -> None:
        root, _child = make_agent_session(tmp_path)
        workspace = tmp_path / "workspace"
        (workspace / "src").mkdir(parents=True)
        (workspace / "src" / "example.py").write_text("", encoding="utf-8")
        (workspace / "src" / "body.py").write_text("", encoding="utf-8")
        root.workspace_dir = str(workspace)
        Path(str(root.artifacts_dir)).joinpath("raw_prompt.md").write_text(
            "Read @src/example.py\n", encoding="utf-8"
        )
        Path(str(root.artifacts_dir)).joinpath("01_prompt.md").write_text(
            "See src/body.py\n", encoding="utf-8"
        )
        panel = _CollapsedDetachedSessionPanel()
    
        result = panel.update_display_with_hints(root)
    
        identity = find_identity_header(panel.captured[-1])
        assert identity is not None
        assert identity.raw_prompt is not None
        assert "[1]" not in identity.raw_prompt.plain
        assert "Read @src/example.py" in identity.raw_prompt.plain
>       assert str(workspace / "src/example.py") not in result.file_hints.values()
E       AssertionError: assert '/var/tmp/sase-3573d744/pytest-of-bryan/pytest-2/popen-gw6/test_session_collapsed_detache0/workspace/src/example.py' not in dict_values(['/var/tmp/sase-3573d744/pytest-of-bryan/pytest-2/popen-gw6/test_session_collapsed_detache0/workspace/src/example.py'])
E        +  where '/var/tmp/sase-3573d744/pytest-of-bryan/pytest-2/popen-gw6/test_session_collapsed_detache0/workspace/src/example.py' = str((PosixPath('/var/tmp/sase-3573d744/pytest-of-bryan/pytest-2/popen-gw6/test_session_collapsed_detache0/workspace') / 'src/example.py'))
E        +  and   dict_values(['/var/tmp/sase-3573d744/pytest-of-bryan/pytest-2/popen-gw6/test_session_collapsed_detache0/workspace/src/example.py']) = <built-in method values of dict object at 0x7cc49ec6ea40>()
E        +    where <built-in method values of dict object at 0x7cc49ec6ea40> = {1: '/var/tmp/sase-3573d744/pytest-of-bryan/pytest-2/popen-gw6/test_session_collapsed_detache0/workspace/src/example.py'}.values
E        +      where {1: '/var/tmp/sase-3573d744/pytest-of-bryan/pytest-2/popen-gw6/test_session_collapsed_detache0/workspace/src/example.py'} = AgentHintRender(file_hints={1: '/var/tmp/sase-3573d744/pytest-of-bryan/pytest-2/popen-gw6/test_session_collapsed_detac... glossary_reports={}, memory_reports={}, artifact_read_refs={}, memory_version_pins={}, header_enrichment_pending=True).file_hints

tests/ace/tui/widgets/test_agent_display_agent_session_hints.py:290: AssertionError
_ test_agent_session_conversation_sections_are_always_full[FoldLevel.COLLAPSED-overrides0] _
[gw6] linux -- Python 3.12.3 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/bin/python

tmp_path = PosixPath('/var/tmp/sase-3573d744/pytest-of-bryan/pytest-2/popen-gw6/test_agent_session_conversatio0')
level = <FoldLevel.COLLAPSED: 'collapsed'>, overrides = {}

    @pytest.mark.parametrize(
        ("level", "overrides"),
        [
            (FoldLevel.COLLAPSED, {}),
            (FoldLevel.EXPANDED, {}),
            (FoldLevel.FULLY_EXPANDED, {}),
            (FoldLevel.EXHAUSTIVE, {}),
            (
                FoldLevel.EXPANDED,
                {
                    "agent-raw-prompt": FoldLevel.COLLAPSED,
                    "agent-prompt": FoldLevel.EXPANDED,
                    "agent-reply": FoldLevel.FULLY_EXPANDED,
                },
            ),
        ],
    )
    def test_agent_session_conversation_sections_are_always_full(
        tmp_path: Path,
        level: FoldLevel,
        overrides: dict[str, FoldLevel],
    ) -> None:
        renderable = _render_agent_session(
            tmp_path,
            level=level,
            overrides=overrides,
        )
        plain = plain_of(renderable)
    
        assert "AGENT RAW PROMPT\n" in plain
        assert "AGENT PROMPT\n" in plain
        assert "AGENT REPLY · 2\n" in plain
        assert "plan macro line 15" in plain
>       assert "plan prompt line 15" in plain
E       AssertionError: assert 'plan prompt line 15' in 'SESSION\nName: alpha\nPatch: session-test\nModels: claude/opus · claude/sonnet\nTurns: --plan · CLAUDE(opus)\n       ...\n\ncode reply line 1\ncode reply line 2\ncode reply line 3\ncode reply line 4\ncode reply line 5\ncode reply line 6\n'

tests/ace/tui/widgets/test_agent_display_agent_session_render.py:123: AssertionError
_ test_agent_session_conversation_sections_are_always_full[FoldLevel.FULLY_EXPANDED-overrides2] _
[gw6] linux -- Python 3.12.3 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/bin/python

tmp_path = PosixPath('/var/tmp/sase-3573d744/pytest-of-bryan/pytest-2/popen-gw6/test_agent_session_conversatio1')
level = <FoldLevel.FULLY_EXPANDED: 'fully_expanded'>, overrides = {}

    @pytest.mark.parametrize(
        ("level", "overrides"),
        [
            (FoldLevel.COLLAPSED, {}),
            (FoldLevel.EXPANDED, {}),
            (FoldLevel.FULLY_EXPANDED, {}),
            (FoldLevel.EXHAUSTIVE, {}),
            (
                FoldLevel.EXPANDED,
                {
                    "agent-raw-prompt": FoldLevel.COLLAPSED,
                    "agent-prompt": FoldLevel.EXPANDED,
                    "agent-reply": FoldLevel.FULLY_EXPANDED,
                },
            ),
        ],
    )
    def test_agent_session_conversation_sections_are_always_full(
        tmp_path: Path,
        level: FoldLevel,
        overrides: dict[str, FoldLevel],
    ) -> None:
        renderable = _render_agent_session(
            tmp_path,
            level=level,
            overrides=overrides,
        )
        plain = plain_of(renderable)
    
        assert "AGENT RAW PROMPT\n" in plain
        assert "AGENT PROMPT\n" in plain
        assert "AGENT REPLY · 2\n" in plain
        assert "plan macro line 15" in plain
>       assert "plan prompt line 15" in plain
E       AssertionError: assert 'plan prompt line 15' in 'SESSION\nName: alpha\nPatch: session-test\nModels: claude/opus · claude/sonnet\nTurns: --plan · CLAUDE(opus)\n       ...\n\ncode reply line 1\ncode reply line 2\ncode reply line 3\ncode reply line 4\ncode reply line 5\ncode reply line 6\n'

tests/ace/tui/widgets/test_agent_display_agent_session_render.py:123: AssertionError
_ test_agent_session_conversation_sections_are_always_full[FoldLevel.EXPANDED-overrides4] _
[gw6] linux -- Python 3.12.3 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/bin/python

tmp_path = PosixPath('/var/tmp/sase-3573d744/pytest-of-bryan/pytest-2/popen-gw6/test_agent_session_conversatio2')
level = <FoldLevel.EXPANDED: 'expanded'>
overrides = {'agent-raw-prompt': <FoldLevel.COLLAPSED: 'collapsed'>, 'agent-prompt': <FoldLevel.EXPANDED: 'expanded'>, 'agent-reply': <FoldLevel.FULLY_EXPANDED: 'fully_expanded'>}

    @pytest.mark.parametrize(
        ("level", "overrides"),
        [
            (FoldLevel.COLLAPSED, {}),
            (FoldLevel.EXPANDED, {}),
            (FoldLevel.FULLY_EXPANDED, {}),
            (FoldLevel.EXHAUSTIVE, {}),
            (
                FoldLevel.EXPANDED,
                {
                    "agent-raw-prompt": FoldLevel.COLLAPSED,
                    "agent-prompt": FoldLevel.EXPANDED,
                    "agent-reply": FoldLevel.FULLY_EXPANDED,
                },
            ),
        ],
    )
    def test_agent_session_conversation_sections_are_always_full(
        tmp_path: Path,
        level: FoldLevel,
        overrides: dict[str, FoldLevel],
    ) -> None:
        renderable = _render_agent_session(
            tmp_path,
            level=level,
            overrides=overrides,
        )
        plain = plain_of(renderable)
    
        assert "AGENT RAW PROMPT\n" in plain
        assert "AGENT PROMPT\n" in plain
        assert "AGENT REPLY · 2\n" in plain
        assert "plan macro line 15" in plain
>       assert "plan prompt line 15" in plain
E       AssertionError: assert 'plan prompt line 15' in 'SESSION\nName: alpha\nPatch: session-test\nModels: claude/opus · claude/sonnet\nTurns: --plan · CLAUDE(opus)\n       ...\n\ncode reply line 1\ncode reply line 2\ncode reply line 3\ncode reply line 4\ncode reply line 5\ncode reply line 6\n'

tests/ace/tui/widgets/test_agent_display_agent_session_render.py:123: AssertionError
________________ test_tui_app_import_stays_under_startup_budget ________________
[gw3] linux -- Python 3.12.3 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/bin/python

    def test_tui_app_import_stays_under_startup_budget() -> None:
        """Importing the app should not pull known heavy deferred profile edges."""
    
        last_elapsed = 0.0
        last_count = 0
        for _ in range(2):
            payload = _measure_tui_app_import()
            last_elapsed = float(payload["elapsed_seconds"])
            last_count = int(payload["module_count"])
            if last_elapsed < _MAX_ELAPSED_SECONDS:
                return
    
>       raise AssertionError(
            f"TUI app import stayed over the {_MAX_ELAPSED_SECONDS}s CPU budget "
            f"after 2 attempts (elapsed={last_elapsed!r}, module_count={last_count!r})"
        )
E       AssertionError: TUI app import stayed over the 5.0s CPU budget after 2 attempts (elapsed=5.249098084, module_count=3510)

tests/ace/tui/test_app_import_budget.py:103: AssertionError
=============================== warnings summary ===============================
.venv/lib/python3.12/site-packages/_pytest/config/__init__.py:885
.venv/lib/python3.12/site-packages/_pytest/config/__init__.py:885
.venv/lib/python3.12/site-packages/_pytest/config/__init__.py:885
.venv/lib/python3.12/site-packages/_pytest/config/__init__.py:885
.venv/lib/python3.12/site-packages/_pytest/config/__init__.py:885
.venv/lib/python3.12/site-packages/_pytest/config/__init__.py:885
.venv/lib/python3.12/site-packages/_pytest/config/__init__.py:885
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/lib/python3.12/site-packages/_pytest/config/__init__.py:885: PytestAssertRewriteWarning: Module already imported so cannot be rewritten; tests.ace.tui.command_line._completion_sources_shared
    self.import_plugin(import_spec)

.venv/lib/python3.12/site-packages/_pytest/config/__init__.py:885
.venv/lib/python3.12/site-packages/_pytest/config/__init__.py:885
.venv/lib/python3.12/site-packages/_pytest/config/__init__.py:885
.venv/lib/python3.12/site-packages/_pytest/config/__init__.py:885
.venv/lib/python3.12/site-packages/_pytest/config/__init__.py:885
.venv/lib/python3.12/site-packages/_pytest/config/__init__.py:885
.venv/lib/python3.12/site-packages/_pytest/config/__init__.py:885
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/lib/python3.12/site-packages/_pytest/config/__init__.py:885: PytestAssertRewriteWarning: Module already imported so cannot be rewritten; tests.ace.tui._bench_tui_jk_helpers
    self.import_plugin(import_spec)

.venv/lib/python3.12/site-packages/_pytest/config/__init__.py:885
.venv/lib/python3.12/site-packages/_pytest/config/__init__.py:885
.venv/lib/python3.12/site-packages/_pytest/config/__init__.py:885
.venv/lib/python3.12/site-packages/_pytest/config/__init__.py:885
.venv/lib/python3.12/site-packages/_pytest/config/__init__.py:885
.venv/lib/python3.12/site-packages/_pytest/config/__init__.py:885
.venv/lib/python3.12/site-packages/_pytest/config/__init__.py:885
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/lib/python3.12/site-packages/_pytest/config/__init__.py:885: PytestAssertRewriteWarning: Module already imported so cannot be rewritten; tests.monitor._no_new_receipt
    self.import_plugin(import_spec)

.venv/lib/python3.12/site-packages/_pytest/config/__init__.py:885
.venv/lib/python3.12/site-packages/_pytest/config/__init__.py:885
.venv/lib/python3.12/site-packages/_pytest/config/__init__.py:885
.venv/lib/python3.12/site-packages/_pytest/config/__init__.py:885
.venv/lib/python3.12/site-packages/_pytest/config/__init__.py:885
.venv/lib/python3.12/site-packages/_pytest/config/__init__.py:885
.venv/lib/python3.12/site-packages/_pytest/config/__init__.py:885
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/lib/python3.12/site-packages/_pytest/config/__init__.py:885: PytestAssertRewriteWarning: Module already imported so cannot be rewritten; tests._axe_lumberjack_fixtures
    self.import_plugin(import_spec)

tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorContinuation::test_prepends_nudge_on_retry
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/lib/python3.12/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorContinuation::test_prepends_nudge_on_retry changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorContinuation::test_does_not_double_prepend_on_repeated_retries
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/lib/python3.12/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorContinuation::test_does_not_double_prepend_on_repeated_retries changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorContinuation::test_prepends_nudge_on_zero_wait_retry
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/lib/python3.12/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorContinuation::test_prepends_nudge_on_zero_wait_retry changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorNoNudge::test_no_nudge_leaves_prompt_untouched
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/lib/python3.12/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorNoNudge::test_no_nudge_leaves_prompt_untouched changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorCodexDefaults::test_codex_transient_default_retries_with_preserved_workspace
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/lib/python3.12/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorCodexDefaults::test_codex_transient_default_retries_with_preserved_workspace changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorPostPhaseTransition::test_retry_fires_for_coder_after_plan_approval
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/lib/python3.12/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorPostPhaseTransition::test_retry_fires_for_coder_after_plan_approval changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry_usage_limits.py::TestHandleWorkflowErrorUsageLimitPrecedence::test_transient_429_not_a_usage_limit_match_still_retries
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/lib/python3.12/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_exec_retry_usage_limits.py::TestHandleWorkflowErrorUsageLimitPrecedence::test_transient_429_not_a_usage_limit_match_still_retries changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry_usage_limits.py::TestHandleWorkflowErrorUsageLimitPrecedence::test_fallback_allowed_to_different_non_disabled_provider
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/lib/python3.12/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_exec_retry_usage_limits.py::TestHandleWorkflowErrorUsageLimitPrecedence::test_fallback_allowed_to_different_non_disabled_provider changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry_usage_limits.py::TestHandleWorkflowErrorUsageLimitPrecedence::test_fallback_allowed_when_fallback_provider_carries_soft_disable
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/lib/python3.12/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_exec_retry_usage_limits.py::TestHandleWorkflowErrorUsageLimitPrecedence::test_fallback_allowed_when_fallback_provider_carries_soft_disable changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry_usage_limits.py::TestHandleWorkflowErrorUsageLimitPrecedence::test_known_codex_attempt_does_not_scan_quoted_claude_limit_prose
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/lib/python3.12/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_exec_retry_usage_limits.py::TestHandleWorkflowErrorUsageLimitPrecedence::test_known_codex_attempt_does_not_scan_quoted_claude_limit_prose changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12' to '<deleted>'; restored it.
    next(it)

tests/ace/tui/test_launchable_mru.py::test_launch_marks_pending_synchronously
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/src/sase/ace/tui/actions/agent_workflow/_launch_submit_helpers.py:132: RuntimeWarning: coroutine 'schedule_submit_time_vcs_replay.<locals>.record_off_thread' was never awaited
    task = spawn_pump_free_task(
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/test_axe_run_agent_exec_retry_workspace.py::TestHandleWorkflowErrorPreserveWorkspace::test_preserve_workspace_skips_prepare_on_retry
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/lib/python3.12/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_exec_retry_workspace.py::TestHandleWorkflowErrorPreserveWorkspace::test_preserve_workspace_skips_prepare_on_retry changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry_workspace.py::TestHandleWorkflowErrorPreserveWorkspace::test_preserve_workspace_skips_prepare_on_fallback
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/lib/python3.12/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_exec_retry_workspace.py::TestHandleWorkflowErrorPreserveWorkspace::test_preserve_workspace_skips_prepare_on_fallback changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry_workspace.py::TestHandleWorkflowErrorPreserveWorkspace::test_default_preserve_workspace_false_still_calls_prepare
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/lib/python3.12/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_exec_retry_workspace.py::TestHandleWorkflowErrorPreserveWorkspace::test_default_preserve_workspace_false_still_calls_prepare changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_failed_fork_admission.py::TestFailedForkParentAdmission::test_runner_admits_and_claims_real_workspace_for_failed_fork_parent
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/lib/python3.12/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_failed_fork_admission.py::TestFailedForkParentAdmission::test_runner_admits_and_claims_real_workspace_for_failed_fork_parent changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_runner_slot_only_deferred_wait_gates_then_claims_workspace[wait_info0-0-None]
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/lib/python3.12/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_runner_slot_only_deferred_wait_gates_then_claims_workspace[wait_info0-0-None] changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_runner_slot_only_deferred_wait_gates_then_claims_workspace[wait_info1-None-20]
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/lib/python3.12/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_runner_slot_only_deferred_wait_gates_then_claims_workspace[wait_info1-None-20] changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_deferred_wait_gates_before_claim_and_prepares_claimed_workspace
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/lib/python3.12/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_deferred_wait_gates_before_claim_and_prepares_claimed_workspace changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_incomplete_clan_fork_expands_after_wait_before_slot_and_claim
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/lib/python3.12/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_incomplete_clan_fork_expands_after_wait_before_slot_and_claim changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_combined_wait_runs_dependencies_then_gate_then_claim
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/lib/python3.12/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_combined_wait_runs_dependencies_then_gate_then_claim changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_home_mode_deferred_wait_keeps_directory_workspace
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/lib/python3.12/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_home_mode_deferred_wait_keeps_directory_workspace changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_outcomes.py::TestDeferredWorkspaceOutcomes::test_repeat_stop_exits_before_workspace_claim_and_run_loop
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/lib/python3.12/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_outcomes.py::TestDeferredWorkspaceOutcomes::test_repeat_stop_exits_before_workspace_claim_and_run_loop changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_outcomes.py::TestDeferredWorkspaceOutcomes::test_deferred_workspace_without_extracted_wait_still_claims_real_workspace
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/lib/python3.12/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_outcomes.py::TestDeferredWorkspaceOutcomes::test_deferred_workspace_without_extracted_wait_still_claims_real_workspace changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_outcomes.py::TestDeferredWorkspaceOutcomes::test_bead_claim_failure_writes_error_and_skips_model_execution
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/lib/python3.12/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_outcomes.py::TestDeferredWorkspaceOutcomes::test_bead_claim_failure_writes_error_and_skips_model_execution changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_outcomes.py::TestDeferredWorkspaceOutcomes::test_bead_environment_mismatch_writes_error_and_skips_model_execution
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/lib/python3.12/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_outcomes.py::TestDeferredWorkspaceOutcomes::test_bead_environment_mismatch_writes_error_and_skips_model_execution changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_outcomes.py::TestDeferredWorkspaceOutcomes::test_launch_without_bead_never_invokes_claim_helper
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/lib/python3.12/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_outcomes.py::TestDeferredWorkspaceOutcomes::test_launch_without_bead_never_invokes_claim_helper changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_no_retry_when_config_is_none
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/lib/python3.12/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_no_retry_when_config_is_none changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_non_retryable_error_raises_immediately
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/lib/python3.12/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_non_retryable_error_raises_immediately changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_retry_on_retryable_error
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/lib/python3.12/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_retry_on_retryable_error changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_retry_state_written_during_wait
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/lib/python3.12/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_retry_state_written_during_wait changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_retry_state_deleted_on_completion
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/lib/python3.12/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_retry_state_deleted_on_completion changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_fallback_model_tried_after_max_retries
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/lib/python3.12/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_fallback_model_tried_after_max_retries changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_was_killed_during_wait_aborts_retry
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/lib/python3.12/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_was_killed_during_wait_aborts_retry changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_done_json_includes_retry_metadata
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/lib/python3.12/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_done_json_includes_retry_metadata changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_no_retry_metadata_when_no_retries
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/lib/python3.12/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_no_retry_metadata_when_no_retries changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_cross_provider_retry_uses_fallback_config
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/lib/python3.12/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_cross_provider_retry_uses_fallback_config changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_agent_is_admitted_before_workspace_preparation
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/lib/python3.12/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_agent_is_admitted_before_workspace_preparation changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_admitted_root_is_counted_when_workspace_preparation_fails
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/lib/python3.12/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_admitted_root_is_counted_when_workspace_preparation_fails changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_no_wait_runner_records_run_started_at_before_execution
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/lib/python3.12/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_no_wait_runner_records_run_started_at_before_execution changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_runner_persists_sdd_base_sha_before_execution
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/lib/python3.12/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_runner_persists_sdd_base_sha_before_execution changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_runner_populates_multi_agent_prompt_file_from_env
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/lib/python3.12/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_runner_populates_multi_agent_prompt_file_from_env changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_error_after_slot_admission_records_run_started_at
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/lib/python3.12/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_error_after_slot_admission_records_run_started_at changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_linked_repo_prep_failure_stops_before_execution
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/lib/python3.12/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_linked_repo_prep_failure_stops_before_execution changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_killed_while_waiting_does_not_record_run_started_at
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/lib/python3.12/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_killed_while_waiting_does_not_record_run_started_at changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_runner_passes_recorded_run_started_at_to_runtime_formatter
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/lib/python3.12/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_runner_passes_recorded_run_started_at_to_runtime_formatter changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_system_exit_from_execution_writes_failure_marker_and_notifies
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/lib/python3.12/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_system_exit_from_execution_writes_failure_marker_and_notifies changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_home_mode_running_marker_cleanup_updates_artifact_index
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/lib/python3.12/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_home_mode_running_marker_cleanup_updates_artifact_index changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12' to '<deleted>'; restored it.
    next(it)

tests/test_axe_runner_workspace_reclone.py::TestRecreateEndToEnd::test_forced_verify_failure_recreates_then_launch_prep_succeeds
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/lib/python3.12/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_runner_workspace_reclone.py::TestRecreateEndToEnd::test_forced_verify_failure_recreates_then_launch_prep_succeeds changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12' to '<deleted>'; restored it.
    next(it)

tests/ace/tui/command_line/test_completion_fixes.py::test_line_change_during_a_fetch_drops_the_result
  /usr/lib/python3.12/copy.py:252: RuntimeWarning: coroutine '_record_history_async.<locals>._record' was never awaited
    args = (deepcopy(arg, memo) for arg in args)
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/test_procs_supervisor.py::test_starter_exit_does_not_kill_a_released_proc
  <frozen os>:859: DeprecationWarning: This process (pid=4143073) is multi-threaded, use of fork() may lead to deadlocks in the child.

tests/ace/tui/command_line/test_panel_shell_pilot.py::test_submit_failure_turns_block_red_and_restores_line
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/lib/python3.12/site-packages/textual/css/_style_properties.py:414: RuntimeWarning: coroutine '_recheck_grammar_key' was never awaited
    def __get__(
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/ace/tui/command_line/test_panel_shell_pilot.py::test_real_input_history_filters_prefix_and_resets_new_walk
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/src/sase/ace/tui/keymaps/key_validation.py:94: RuntimeWarning: coroutine '_record_history_async.<locals>._record' was never awaited
    return tuple(part.strip() for part in key.split(","))
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/ace/tui/command_line/test_run_policies.py::test_foreground_submit_runs_in_terminal_and_records
  /usr/lib/python3.12/pathlib.py:387: RuntimeWarning: coroutine 'CommandLineScreenSubmissionMixin._record_local_history.<locals>._record' was never awaited
    @classmethod
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/ace/tui/command_line/test_transcript_blocks_actions.py::test_v_opens_pager_for_selected_block
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/lib/python3.12/site-packages/textual/css/_styles_builder.py:260: RuntimeWarning: coroutine 'CommandLineScreenSubmissionMixin._submit_worker' was never awaited
    self.styles._rules[name.replace("-", "_")] = Scalar.parse(  # type: ignore
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/ace/tui/command_line/test_transcript_blocks_actions.py::test_p_opens_procs_with_focus_target
  /usr/lib/python3.12/pathlib.py:369: RuntimeWarning: coroutine 'CommandLineScreen._load_tail_worker' was never awaited
    path = os.fspath(arg)
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/ace/tui/command_line/test_transcript_blocks_keys.py::test_r_reruns_and_R_is_limited_to_declined_blocks
  /usr/lib/python3.12/json/decoder.py:353: RuntimeWarning: coroutine 'CommandLineScreenSubmissionMixin._submit_worker' was never awaited
    obj, end = self.scan_once(s, idx)
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/test_run_agent_runner_clan_summary_refresh.py::test_successful_post_preparation_summary_survives_later_metadata_write
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/lib/python3.12/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_run_agent_runner_clan_summary_refresh.py::test_successful_post_preparation_summary_survives_later_metadata_write changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12' to '<deleted>'; restored it.
    next(it)

tests/test_run_agent_runner_clan_summary_refresh.py::test_unsuccessful_post_preparation_summary_keeps_earlier_success
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/lib/python3.12/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_run_agent_runner_clan_summary_refresh.py::test_unsuccessful_post_preparation_summary_keeps_earlier_success changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12' to '<deleted>'; restored it.
    next(it)

tests/test_macro_processor_workflow_execute.py::test_execute_workflow_flatten_preserves_caller_named_args
tests/test_macro_processor_workflow_execute.py::test_execute_workflow_flatten_explicit_named_args_override_caller
tests/test_macro_processor_workflow_execute.py::test_execute_workflow_flatten_preserves_wrapper_model_override
tests/test_macro_processor_workflow_execute.py::test_execute_workflow_passes_inherited_vcs_tag_without_context_leak
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/src/sase/macro/workflow_runner.py:474: UserWarning: Standalone workflow '#split' is deprecated; use '#!split' instead.
    flattened = _flatten_anonymous_workflow(workflow, project=project)

tests/test_macro_processor_workflow_flatten.py::test_flatten_anonymous_workflow_returns_workflow_for_pure_multistep
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/tests/test_macro_processor_workflow_flatten.py:114: UserWarning: Standalone workflow '#split' is deprecated; use '#!split' instead.
    result = _flatten_anonymous_workflow(workflow)

tests/test_macro_processor_workflow_flatten.py::test_flatten_anonymous_workflow_slow_path_with_macro_and_workflow
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/src/sase/macro/workflow_runner.py:297: UserWarning: Standalone workflow '#batch_split' is deprecated; use '#!batch_split' instead.
    standalone = _find_standalone_workflow_ref(prompt_text, prompts)

tests/test_macro_processor_workflow_flatten.py::test_flatten_anonymous_workflow_slow_path_with_args
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/src/sase/macro/workflow_runner.py:297: UserWarning: Standalone workflow '#deploy' is deprecated; use '#!deploy' instead.
    standalone = _find_standalone_workflow_ref(prompt_text, prompts)

tests/test_macro_processor_workflow_flatten.py::test_flatten_anonymous_workflow_preserves_wrapper_model_directive
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/tests/test_macro_processor_workflow_flatten.py:421: UserWarning: Standalone workflow '#split' is deprecated; use '#!split' instead.
    result = _flatten_anonymous_workflow(workflow)

tests/test_notification_modal_tab_order.py::test_on_mount_highlights_first_visible_row_when_initial_is_hidden
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/src/sase/ace/tui/modals/notification_modal_snooze_status.py:136: RuntimeWarning: coroutine 'Timer._run_timer' was never awaited
    self._snooze_status_timer = None
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/axe/test_run_agent_exec_attempts_integration.py::test_retry_branch_snapshots_failed_attempt
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/lib/python3.12/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/axe/test_run_agent_exec_attempts_integration.py::test_retry_branch_snapshots_failed_attempt changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12' to '<deleted>'; restored it.
    next(it)

tests/axe/test_run_agent_exec_attempts_integration.py::test_retry_branch_releases_attempt_continuation_pointers
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/lib/python3.12/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/axe/test_run_agent_exec_attempts_integration.py::test_retry_branch_releases_attempt_continuation_pointers changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12' to '<deleted>'; restored it.
    next(it)

tests/axe/test_run_agent_exec_attempts_integration.py::test_fallback_branch_releases_attempt_continuation_pointers
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/lib/python3.12/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/axe/test_run_agent_exec_attempts_integration.py::test_fallback_branch_releases_attempt_continuation_pointers changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12' to '<deleted>'; restored it.
    next(it)

tests/axe/test_run_agent_exec_attempts_integration.py::test_fallback_branch_snapshots_with_primary_model_marker
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/lib/python3.12/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/axe/test_run_agent_exec_attempts_integration.py::test_fallback_branch_snapshots_with_primary_model_marker changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12' to '<deleted>'; restored it.
    next(it)

tests/completion/test_zsh_smoke.py: 18 warnings
  /usr/lib/python3.12/pty.py:95: DeprecationWarning: This process (pid=4143061) is multi-threaded, use of forkpty() may lead to deadlocks in the child.
    pid, fd = os.forkpty()

tests/sdd/test_artifact_link_event_acceptance_process_death.py::test_real_killed_publisher_process_leaves_no_corrupt_object_and_recovers
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/tests/sdd/test_artifact_link_event_acceptance_process_death.py:57: DeprecationWarning: This process (pid=4143070) is multi-threaded, use of fork() may lead to deadlocks in the child.
    child = os.fork()

tests/ace/tui/test_agent_archive_column_actions_interaction.py::test_enter_l_or_click_on_the_pulse_returns_to_the_parked_inbox
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/src/sase/ace/tui/models/agent_archive_list.py:144: RuntimeWarning: coroutine 'AgentMetadataPagerMixin._open_agent_metadata_pager' was never awaited
    if all(isinstance(part, str) and part for part in (user, machine, run_id)):
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/ace/tui/test_agent_archive_column_actions_interaction.py::test_cursor_survives_a_rebuild_and_falls_to_a_neighbor_when_row_vanishes
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/tests/ace/tui/_agent_archive_column_helpers.py:49: RuntimeWarning: coroutine 'open_archive_chooser.<locals>._hydrate_and_present' was never awaited
    "last_activity_at": f"{day}T{hour:02d}:00:00Z",
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/ace/tui/test_agent_archive_controller_generations.py::test_worker_publishes_display_snapshot_for_project_banners
  /usr/lib/python3.12/inspect.py:3045: RuntimeWarning: coroutine '_run_archive_request' was never awaited
    params = OrderedDict((param.name, param) for param in parameters)
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/ace/tui/test_agent_archive_controller_prewarm.py::test_early_open_paints_loading_and_queues_until_gate
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/src/sase/ace/tui/models/agent_archive_list.py:99: RuntimeWarning: coroutine '_run_archive_request' was never awaited
    return tuple(item.key for item in self.items if item.selectable)
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/history/test_continuation_replay_hydration_retry.py::test_retry_then_fork_replay_end_to_end
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/lib/python3.12/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/history/test_continuation_replay_hydration_retry.py::test_retry_then_fork_replay_end_to_end changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12' to '<deleted>'; restored it.
    next(it)

tests/ace/tui/test_dismissed_index_startup_sync.py::test_start_post_mount_background_loads_schedules_dismissed_sync_once
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/src/sase/ace/tui/actions/_launchable_mru.py:304: RuntimeWarning: coroutine 'Timer._run_timer' was never awaited
    log.debug("Launchable MRU tick not armed", exc_info=True)
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

-- Docs: https://docs.pytest.org/en/stable/how-to/capture-warnings.html
============================= slowest 20 durations =============================
111.56s call     tests/test_contract_manifest.py::test_contract_manifest_matches_marker_selection
78.56s call     tests/test_check_feature_flags_tool_run.py::test_main_static_on_repo_exits_zero
75.86s call     tests/test_agent_artifact_directory_operation_audit.py::test_artifact_directory_operation_sites_are_reviewed
71.70s call     tests/test_check_feature_flags_tool_run.py::test_static_main_ignores_exploding_bd_command
67.36s call     tests/tool/test_nested_stage_recording.py::test_child_pytest_of_a_stageless_run_records_no_stage_rows
66.65s call     tests/fakey/test_monitor_capacity_e2e.py::test_weight_two_land_agent_session_retains_one_claim_through_real_dispatch_and_delayed_child_bootstrap
62.98s call     tests/tool/test_inline_escalation.py::test_sigterm_leaves_run_running
53.05s call     tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_lowercase_picks_this_panel_capital_picks_other
47.88s call     tests/history/test_continuation_replay_hydration_basic.py::test_hundred_handoff_from_final_monitor_result_grows_linearly
42.62s call     tests/ace/tui/test_deleted_proc_queue_imports.py::test_tests_do_not_import_deleted_proc_queue_module
39.42s call     tests/test_project_display_presentation_audit.py::test_project_display_name_fallback_lives_only_in_chokepoint
38.98s call     tests/test_project_display_presentation_audit.py::test_display_fallback_exemptions_name_existing_sites_and_rationales
37.89s call     tests/sdd/test_git_identity_fixture.py::test_sdd_git_identity_survives_empty_home_subprocess
34.01s call     tests/workspace_provider/test_primary_writable_store_import_boundary.py::test_writable_store_resolution_importers_match_the_audited_allowlist
33.29s call     tests/pager/test_rendered_link_contract.py::test_kitchen_follow_copy_edit_and_media_for_each_supported_action
32.43s call     tests/test_markdown_print_width.py::test_no_function_parameter_defaults_to_the_width
31.85s call     tests/instructions/test_invoke_boundary.py::test_allowlist_entries_still_exist
31.74s call     tests/instructions/test_invoke_boundary.py::test_only_boundary_calls_provider_invoke
30.35s call     tests/ace/tui/test_artifacts_scaffold.py::test_number_keys_jump_artifacts_without_entering_from_other_tabs
29.77s call     tests/feature_flags/test_host_config_safety.py::test_config_seed_tests_do_not_snapshot_config_dir_at_module_scope
=========================== short test summary info ============================
FAILED tests/tool/test_inline_escalation.py::test_sigterm_leaves_run_running - assert 124 == 143
FAILED tests/ace/tui/widgets/test_agent_display_hint_cache.py::test_repeat_hint_render_reuses_result_and_renderable - AssertionError: assert {1: '/var/tmp...rc/reused.py'} == {1: '/var/tmp...rc/reused.py'}
  
  Omitting 1 identical items, use -vv to show
  Differing items:
  {2: '/var/tmp/sase-3573d744/pytest-of-bryan/pytest-2/popen-gw4/test_repeat_hint_render_reuses0/workspace/src/raw.py'} != {2: '/var/tmp/sase-3573d744/pytest-of-bryan/pytest-2/popen-gw4/test_repeat_hint_render_reuses0/workspace/src/reused.py'}
  Left contains 1 more item:
  {3: '/var/tmp/sase-3573d744/pytest-of-bryan/pytest-2/popen-gw4/test_repeat_hint_render_reuses0/workspace/src/reused.py'}
  
  Full diff:
    {
        1: '/var/tmp/sase-3573d744/pytest-of-bryan/pytest-2/popen-gw4/test_repeat_hint_render_reuses0/workspace/src/raw.py',
  +     2: '/var/tmp/sase-3573d744/pytest-of-bryan/pytest-2/popen-gw4/test_repeat_hint_render_reuses0/workspace/src/raw.py',
  -     2: '/var/tmp/sase-3573d744/pytest-of-bryan/pytest-2/popen-gw4/test_repeat_hint_render_reuses0/workspace/src/reused.py',
  ?     ^
  +     3: '/var/tmp/sase-3573d744/pytest-of-bryan/pytest-2/popen-gw4/test_repeat_hint_render_reuses0/workspace/src/reused.py',
  ?     ^
    }
FAILED tests/ace/tui/widgets/test_agent_display_hint_cache.py::test_changed_reply_invalidates_hint_document_and_mappings - AssertionError: assert '[2] src/second-and-longer.py' in 'AGENT TURN\nName: unassigned\nPatch: test_cl\nTimestamps: START | 2024-01-01 14:23:45\n            DONE  | 2024-01-01...────────────────────\n\nAGENT PROMPT\nLaunch from [2] @src/raw.py\n\nAGENT CHAT\nOpen [3] src/second-and-longer.py\n\n'
 +  where 'AGENT TURN\nName: unassigned\nPatch: test_cl\nTimestamps: START | 2024-01-01 14:23:45\n            DONE  | 2024-01-01...────────────────────\n\nAGENT PROMPT\nLaunch from [2] @src/raw.py\n\nAGENT CHAT\nOpen [3] src/second-and-longer.py\n\n' = plain_of(<rich.console.Group object at 0x7951abe3f200>)
FAILED tests/ace/tui/widgets/test_agent_display_raw_prompt.py::TestAgentRawPromptRendering::test_done_agent_renders_raw_prompt - AssertionError
FAILED tests/ace/tui/widgets/test_agent_display_raw_prompt.py::TestAgentRawPromptRendering::test_agent_prompt_and_chat_use_logical_project_name - AssertionError: assert 'Prompt says #gh:widgets inspect.' in 'AGENT TURN\nName: unassigned\nPatch: test_cl\nTimestamps: START | 2024-01-01 14:23:45\n            DONE  | 2024-01-01...─────────────────────────\n\nAGENT PROMPT\n\nLaunch from @src/raw.py\nAGENT CHAT\n\nResponse echoes #gh:widgets now.\n'
FAILED tests/ace/tui/widgets/test_agent_display_raw_prompt_hints.py::TestAgentRawPromptHintMode::test_hint_mode_prompt_and_chat_use_logical_project_name - AssertionError: assert '#gh:widgets prompt' in 'AGENT TURN\nName: unassigned\nPatch: test_cl\nTimestamps: START | 2024-01-01 14:23:45\n            DONE  | 2024-01-01...─────────────────────────────────────────────\n\nAGENT PROMPT\n#gh:widgets raw\n\nAGENT CHAT\n#gh:widgets response\n\n'
FAILED tests/ace/tui/widgets/test_agent_display_raw_prompt_hints.py::TestAgentRawPromptHintMode::test_hint_mode_renders_raw_prompt_for_terminal_agent - AssertionError
FAILED tests/ace/tui/widgets/test_agent_display_raw_prompt_hints.py::TestAgentRawPromptHintMode::test_hint_mode_keeps_typed_artifact_refs_semantic - AssertionError: assert {1: '/var/tmp...e/src/raw.py'} == {1: '/var/tmp...e/src/raw.py'}
  
  Omitting 1 identical items, use -vv to show
  Left contains 2 more items:
  {2: '/var/tmp/sase-3573d744/pytest-of-bryan/pytest-2/popen-gw4/test_hint_mode_keeps_typed_art0/workspace/202608/design.md',
   3: '/var/tmp/sase-3573d744/pytest-of-bryan/pytest-2/popen-gw4/test_hint_mode_keeps_typed_art0/workspace/src/raw.py'}
  
  Full diff:
    {
        1: '/var/tmp/sase-3573d744/pytest-of-bryan/pytest-2/popen-gw4/test_hint_mode_keeps_typed_art0/workspace/src/raw.py',
  +     2: '/var/tmp/sase-3573d744/pytest-of-bryan/pytest-2/popen-gw4/test_hint_mode_keeps_typed_art0/workspace/202608/design.md',
  +     3: '/var/tmp/sase-3573d744/pytest-of-bryan/pytest-2/popen-gw4/test_hint_mode_keeps_typed_art0/workspace/src/raw.py',
    }
FAILED tests/ace/tui/widgets/test_agent_display_raw_prompt_hints.py::TestAgentRawPromptHintMode::test_hint_mode_renders_timestamp_file_hints_before_body_hints - AssertionError: assert '[3] src/prompt.py' in 'AGENT TURN\nName: unassigned\nPatch: test_cl\nTimestamps: START | 2024-01-01 14:23:45\n            FBACK | 2024-01-01...──────────────────────────────────\n\nAGENT PROMPT\nLaunch from [3] @src/raw.py\n\nAGENT CHAT\nFinal response body\n\n'
FAILED tests/ace/tui/widgets/test_agent_header_panel_basic.py::test_hint_mode_keeps_collapsed_header_unchanged - AssertionError: assert '/var/tmp/sase-3573d744/pytest-of-bryan/pytest-2/popen-gw4/test_hint_mode_keeps_collapsed0/workspace/src/example.py' not in dict_values(['/var/tmp/sase-3573d744/pytest-of-bryan/pytest-2/popen-gw4/test_hint_mode_keeps_collapsed0/workspace/src/...y', '/var/tmp/sase-3573d744/pytest-of-bryan/pytest-2/popen-gw4/test_hint_mode_keeps_collapsed0/workspace/src/body.py'])
 +  where '/var/tmp/sase-3573d744/pytest-of-bryan/pytest-2/popen-gw4/test_hint_mode_keeps_collapsed0/workspace/src/example.py' = str((PosixPath('/var/tmp/sase-3573d744/pytest-of-bryan/pytest-2/popen-gw4/test_hint_mode_keeps_collapsed0/workspace') / 'src/example.py'))
 +  and   dict_values(['/var/tmp/sase-3573d744/pytest-of-bryan/pytest-2/popen-gw4/test_hint_mode_keeps_collapsed0/workspace/src/...y', '/var/tmp/sase-3573d744/pytest-of-bryan/pytest-2/popen-gw4/test_hint_mode_keeps_collapsed0/workspace/src/body.py']) = <built-in method values of dict object at 0x7951a83893c0>()
 +    where <built-in method values of dict object at 0x7951a83893c0> = {1: '/var/tmp/sase-3573d744/pytest-of-bryan/pytest-2/popen-gw4/test_hint_mode_keeps_collapsed0/workspace/src/example.py', 2: '/var/tmp/sase-3573d744/pytest-of-bryan/pytest-2/popen-gw4/test_hint_mode_keeps_collapsed0/workspace/src/body.py'}.values
 +      where {1: '/var/tmp/sase-3573d744/pytest-of-bryan/pytest-2/popen-gw4/test_hint_mode_keeps_collapsed0/workspace/src/example.py', 2: '/var/tmp/sase-3573d744/pytest-of-bryan/pytest-2/popen-gw4/test_hint_mode_keeps_collapsed0/workspace/src/body.py'} = AgentHintRender(file_hints={1: '/var/tmp/sase-3573d744/pytest-of-bryan/pytest-2/popen-gw4/test_hint_mode_keeps_collaps... glossary_reports={}, memory_reports={}, artifact_read_refs={}, memory_version_pins={}, header_enrichment_pending=True).file_hints
FAILED tests/ace/tui/widgets/test_agent_header_panel_preview.py::test_collapsed_preview_shows_quote_bar_and_body_omits_raw_prompt - AssertionError: assert 'AGENT RAW PROMPT' not in 'AGENT PROMP...esponse body'
  
  'AGENT RAW PROMPT' is contained here:
    ering the AGENT RAW PROMPT section in the sticky header above the agent data deck panel? Make 
  ?           ++++++++++++++++
    sure that we provide a good preview of the contents in this section.                                                    
                                                                                                                            
    - first list item explains the quote bar                                                                                
    - second list item explains the row budget                                                                              
    ```                                                                                                                     
    some fenced code block line                                                                                             
    ```                                                                                                                     
    A final hard-wrapped prose paragraph keeps going so the preview budget overflows and the border subtitle names the      
    hidden line count.                                                                                                      
    AGENT CHAT
    Final response body
FAILED tests/ace/tui/widgets/test_agent_header_panel_preview.py::test_bottom_pinned_body_stays_pinned_across_row_count_change - assert False is True
 +  where False = bool(False)
 +    where False = MainDeckView().is_pinned_to_bottom
FAILED tests/ace/tui/widgets/test_agent_prompt_semantic.py::test_agent_macro_and_prompt_receive_roles_replies_do_not - ValueError: substring not found
FAILED tests/ace/tui/widgets/test_identity_header_raw_prompt.py::test_hinted_raw_prompt_moves_to_identity_and_keeps_its_markers - AssertionError: assert {1: '/var/tmp...c/example.py'} == {1: '/var/tmp...c/example.py'}
  
  Omitting 1 identical items, use -vv to show
  Left contains 1 more item:
  {2: '/var/tmp/sase-3573d744/pytest-of-bryan/pytest-2/popen-gw4/test_hinted_raw_prompt_moves_t0/workspace/src/example.py'}
  
  Full diff:
    {
        1: '/var/tmp/sase-3573d744/pytest-of-bryan/pytest-2/popen-gw4/test_hinted_raw_prompt_moves_t0/workspace/src/example.py',
  +     2: '/var/tmp/sase-3573d744/pytest-of-bryan/pytest-2/popen-gw4/test_hinted_raw_prompt_moves_t0/workspace/src/example.py',
    }
FAILED tests/ace/tui/widgets/test_identity_header_raw_prompt.py::test_collapsed_detached_raw_prompt_skips_markers - AssertionError: assert '/var/tmp/sase-3573d744/pytest-of-bryan/pytest-2/popen-gw4/test_collapsed_detached_raw_pr0/workspace/src/example.py' not in dict_values(['/var/tmp/sase-3573d744/pytest-of-bryan/pytest-2/popen-gw4/test_collapsed_detached_raw_pr0/workspace/src/example.py'])
 +  where '/var/tmp/sase-3573d744/pytest-of-bryan/pytest-2/popen-gw4/test_collapsed_detached_raw_pr0/workspace/src/example.py' = str((PosixPath('/var/tmp/sase-3573d744/pytest-of-bryan/pytest-2/popen-gw4/test_collapsed_detached_raw_pr0/workspace') / 'src/example.py'))
 +  and   dict_values(['/var/tmp/sase-3573d744/pytest-of-bryan/pytest-2/popen-gw4/test_collapsed_detached_raw_pr0/workspace/src/example.py']) = <built-in method values of dict object at 0x7951ce9a2c00>()
 +    where <built-in method values of dict object at 0x7951ce9a2c00> = {1: '/var/tmp/sase-3573d744/pytest-of-bryan/pytest-2/popen-gw4/test_collapsed_detached_raw_pr0/workspace/src/example.py'}.values
 +      where {1: '/var/tmp/sase-3573d744/pytest-of-bryan/pytest-2/popen-gw4/test_collapsed_detached_raw_pr0/workspace/src/example.py'} = AgentHintRender(file_hints={1: '/var/tmp/sase-3573d744/pytest-of-bryan/pytest-2/popen-gw4/test_collapsed_detached_raw_... glossary_reports={}, memory_reports={}, artifact_read_refs={}, memory_version_pins={}, header_enrichment_pending=True).file_hints
FAILED tests/instructions/test_scoreboard_conformance.py::test_conformance_warns_for_duplicate_root_and_leaked_helper_markers - ImportError: cannot import name '_RunManifest' from 'sase.instructions.manifests' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/src/sase/instructions/manifests.py)
FAILED tests/ace/tui/widgets/test_agent_clan_aggregation.py::test_member_loader_reuses_reply_and_prompt_precedence - AssertionError: assert [('AGENT RAW ...rst segment')] == [('AGENT RAW ...prompt body')]
  
  At index 1 diff: ('AGENT PROMPT', '#research first segment') != ('AGENT PROMPT', 'Expanded prompt body')
  
  Full diff:
    [
        (
            'AGENT RAW PROMPT',
            '#research first segment',
        ),
        (
            'AGENT PROMPT',
  -         'Expanded prompt body',
  +         '#research first segment',
        ),
    ]
FAILED tests/ace/tui/widgets/test_agent_display_agent_session_hints.py::test_agent_session_content_hints_are_full_at_both_levels_and_use_phase_workspace - AssertionError: assert [{'/var/tmp/s...e-reply.txt'}] == [{'/var/tmp/s...ly.txt', ...}]
  
  At index 0 diff: {'/var/tmp/sase-3573d744/pytest-of-bryan/pytest-2/popen-gw6/test_agent_session_content_hin0/root-workspace/docs/visible-macro.md', '/var/tmp/sase-3573d744/pytest-of-bryan/pytest-2/popen-gw6/test_agent_session_content_hin0/root-workspace/root/visible-reply.txt', '/var/tmp/sase-3573d744/pytest-of-bryan/pytest-2/popen-gw6/test_agent_session_content_hin0/root-workspace/root/hidden-reply.txt', '/var/tmp/sase-3573d744/pytest-of-bryan/pytest-2/popen-gw6/test_agent_session_content_hin0/child-workspace/child/hidden-reply.txt', '/var/tmp/sase-3573d744/pytest-of-bryan/pytest-2/popen-gw6/test_agent_session_content_hin0/root-workspace/docs/hidden-macro.md', '/var/tmp/sase-3573d744/pytest-of-bryan/pytest-2/popen-gw6/test_agent_session_content_hin0/child-workspace/child/visible-reply.txt'} != {'/var/tmp/sase-3573d744/pytest-of-bryan/pytest-2/popen-gw6/test_agent_session_content_hin0/root-workspace/docs/visible-macro.md', '/var/tmp/sase-3573d744/pytest-of-bryan/pytest-2/popen-gw6/test_agent_session_content_hin0/root-workspace/root/hidden-reply.txt', '/var/tmp/sase-3573d744/pytest-of-bryan/pytest-2/popen-gw6/test_agent_session_content_hin0/root-workspace/root/visible-reply.txt', '/var/tmp/sase-3573d744/pytest-of-bryan/pytest-2/popen-gw6/test_agent_session_content_hin0/root-workspace/src/hidden-prompt.py', '/var/tmp/sase-3573d744/pytest-of-bryan/pytest-2/popen-gw6/test_agent_session_content_hin0/root-workspace/src/visible-prompt.py', '/var/tmp/sase-3573d744/pytest-of-bryan/pytest-2/popen-gw6/test_agent_session_content_hin0/child-workspace/child/hidden-reply.txt', '/var/tmp/sase-3573d744/pytest-of-bryan/pytest-2/popen-gw6/test_agent_session_content_hin0/root-workspace/docs/hidden-macro.md', '/var/tmp/sase-3573d744/pytest-of-bryan/pytest-2/popen-gw6/test_agent_session_content_hin0/child-workspace/child/visible-reply.txt'}
  
  Full diff:
    [
        {
            '/var/tmp/sase-3573d744/pytest-of-bryan/pytest-2/popen-gw6/test_agent_session_content_hin0/child-workspace/child/hidden-reply.txt',
            '/var/tmp/sase-3573d744/pytest-of-bryan/pytest-2/popen-gw6/test_agent_session_content_hin0/child-workspace/child/visible-reply.txt',
            '/var/tmp/sase-3573d744/pytest-of-bryan/pytest-2/popen-gw6/test_agent_session_content_hin0/root-workspace/docs/hidden-macro.md',
            '/var/tmp/sase-3573d744/pytest-of-bryan/pytest-2/popen-gw6/test_agent_session_content_hin0/root-workspace/docs/visible-macro.md',
            '/var/tmp/sase-3573d744/pytest-of-bryan/pytest-2/popen-gw6/test_agent_session_content_hin0/root-workspace/root/hidden-reply.txt',
            '/var/tmp/sase-3573d744/pytest-of-bryan/pytest-2/popen-gw6/test_agent_session_content_hin0/root-workspace/root/visible-reply.txt',
  -         '/var/tmp/sase-3573d744/pytest-of-bryan/pytest-2/popen-gw6/test_agent_session_content_hin0/root-workspace/src/hidden-prompt.py',
  -         '/var/tmp/sase-3573d744/pytest-of-bryan/pytest-2/popen-gw6/test_agent_session_content_hin0/root-workspace/src/visible-prompt.py',
        },
        {
            '/var/tmp/sase-3573d744/pytest-of-bryan/pytest-2/popen-gw6/test_agent_session_content_hin0/child-workspace/child/hidden-reply.txt',
            '/var/tmp/sase-3573d744/pytest-of-bryan/pytest-2/popen-gw6/test_agent_session_content_hin0/child-workspace/child/visible-reply.txt',
            '/var/tmp/sase-3573d744/pytest-of-bryan/pytest-2/popen-gw6/test_agent_session_content_hin0/root-workspace/docs/hidden-macro.md',
            '/var/tmp/sase-3573d744/pytest-of-bryan/pytest-2/popen-gw6/test_agent_session_content_hin0/root-workspace/docs/visible-macro.md',
            '/var/tmp/sase-3573d744/pytest-of-bryan/pytest-2/popen-gw6/test_agent_session_content_hin0/root-workspace/root/hidden-reply.txt',
            '/var/tmp/sase-3573d744/pytest-of-bryan/pytest-2/popen-gw6/test_agent_session_content_hin0/root-workspace/root/visible-reply.txt',
  -         '/var/tmp/sase-3573d744/pytest-of-bryan/pytest-2/popen-gw6/test_agent_session_content_hin0/root-workspace/src/hidden-prompt.py',
  -         '/var/tmp/sase-3573d744/pytest-of-bryan/pytest-2/popen-gw6/test_agent_session_content_hin0/root-workspace/src/visible-prompt.py',
        },
    ]
FAILED tests/ace/tui/widgets/test_agent_display_agent_session_hints.py::test_session_collapsed_detached_macro_skips_markers - AssertionError: assert '/var/tmp/sase-3573d744/pytest-of-bryan/pytest-2/popen-gw6/test_session_collapsed_detache0/workspace/src/example.py' not in dict_values(['/var/tmp/sase-3573d744/pytest-of-bryan/pytest-2/popen-gw6/test_session_collapsed_detache0/workspace/src/example.py'])
 +  where '/var/tmp/sase-3573d744/pytest-of-bryan/pytest-2/popen-gw6/test_session_collapsed_detache0/workspace/src/example.py' = str((PosixPath('/var/tmp/sase-3573d744/pytest-of-bryan/pytest-2/popen-gw6/test_session_collapsed_detache0/workspace') / 'src/example.py'))
 +  and   dict_values(['/var/tmp/sase-3573d744/pytest-of-bryan/pytest-2/popen-gw6/test_session_collapsed_detache0/workspace/src/example.py']) = <built-in method values of dict object at 0x7cc49ec6ea40>()
 +    where <built-in method values of dict object at 0x7cc49ec6ea40> = {1: '/var/tmp/sase-3573d744/pytest-of-bryan/pytest-2/popen-gw6/test_session_collapsed_detache0/workspace/src/example.py'}.values
 +      where {1: '/var/tmp/sase-3573d744/pytest-of-bryan/pytest-2/popen-gw6/test_session_collapsed_detache0/workspace/src/example.py'} = AgentHintRender(file_hints={1: '/var/tmp/sase-3573d744/pytest-of-bryan/pytest-2/popen-gw6/test_session_collapsed_detac... glossary_reports={}, memory_reports={}, artifact_read_refs={}, memory_version_pins={}, header_enrichment_pending=True).file_hints
FAILED tests/ace/tui/widgets/test_agent_display_agent_session_render.py::test_agent_session_conversation_sections_are_always_full[FoldLevel.COLLAPSED-overrides0] - AssertionError: assert 'plan prompt line 15' in 'SESSION\nName: alpha\nPatch: session-test\nModels: claude/opus · claude/sonnet\nTurns: --plan · CLAUDE(opus)\n       ...\n\ncode reply line 1\ncode reply line 2\ncode reply line 3\ncode reply line 4\ncode reply line 5\ncode reply line 6\n'
FAILED tests/ace/tui/widgets/test_agent_display_agent_session_render.py::test_agent_session_conversation_sections_are_always_full[FoldLevel.FULLY_EXPANDED-overrides2] - AssertionError: assert 'plan prompt line 15' in 'SESSION\nName: alpha\nPatch: session-test\nModels: claude/opus · claude/sonnet\nTurns: --plan · CLAUDE(opus)\n       ...\n\ncode reply line 1\ncode reply line 2\ncode reply line 3\ncode reply line 4\ncode reply line 5\ncode reply line 6\n'
FAILED tests/ace/tui/widgets/test_agent_display_agent_session_render.py::test_agent_session_conversation_sections_are_always_full[FoldLevel.EXPANDED-overrides4] - AssertionError: assert 'plan prompt line 15' in 'SESSION\nName: alpha\nPatch: session-test\nModels: claude/opus · claude/sonnet\nTurns: --plan · CLAUDE(opus)\n       ...\n\ncode reply line 1\ncode reply line 2\ncode reply line 3\ncode reply line 4\ncode reply line 5\ncode reply line 6\n'
FAILED tests/ace/tui/test_app_import_budget.py::test_tui_app_import_stays_under_startup_budget - AssertionError: TUI app import stayed over the 5.0s CPU budget after 2 attempts (elapsed=5.249098084, module_count=3510)
=== 23 failed, 55685 passed, 31 skipped, 124 warnings in 2492.51s (0:41:32) ====
error: Recipe `test-scoped` failed on line 573 with exit code 1
error: Recipe `check` failed on line 823 with exit code 1
failed  exit=1  duration=4550828ms
unattrib  27m 2s
triage lint (symvision): 7 KNOWN continued
triage test (scoped): 18 KNOWN 3 NEW stopped
NEW test (scoped): FAILED tests/instructions/test_scoreboard_conformance.py::test_conformance_warns_for_duplicate_root_and_leaked_helper_markers - ImportError: cannot import name '_RunManifest' from 'sase.instructions.manifests' (src/sase/instructions/manifests.py) — recorded evidence; no owner
NEW test (scoped): FAILED tests/ace/tui/widgets/test_agent_header_panel_preview.py::test_collapsed_preview_shows_quote_bar_and_body_omits_raw_prompt - AssertionError: assert 'AGENT RAW PROMPT' not in 'AGENT PROMP...esponse body' — recorded evidence; no owner
NEW test (scoped): FAILED tests/ace/tui/widgets/test_agent_display_raw_prompt.py::TestAgentRawPromptRendering::test_done_agent_renders_raw_prompt - AssertionError — recorded evidence; no owner
KNOWN lint (symvision): count_contract_sources in src/sase/instructions/fingerprints.py — witness 1082a81f9094da7271a4747532964c3c; no owner
KNOWN lint (symvision): human_rules_blocks in src/sase/instructions/grok.py — witness 1082a81f9094da7271a4747532964c3c; no owner
KNOWN lint (symvision): prompt_texts in src/sase/instructions/muse.py — witness 1082a81f9094da7271a4747532964c3c; no owner
verdict: new_failures — 3 NEW, 25 KNOWN; exit 1

