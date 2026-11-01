# Chat History - ace-run (sase-1qk.3--mon-4)

- **TIMESTAMP:** 2026-11-01 17:27:00 EST
- **MODEL:** grok/grok-4.6
- **AGENT:** sase-1qk.3--mon-4

## Prompt

sase monitor start --command 'just check' --reason 'Verify before host completion'

## Response

sase tool run 5efb3750a00a88e8a831c04fad817ce4
[setup] fast-forwarded /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/sase/repos/linked/sase-core to origin/master
[validate_sase_core_rs_version] sase-core checkout is ahead of sase's compatibility window: source version 0.43.3 from /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/sase/repos/linked/sase-core/Cargo.toml does not satisfy `sase`'s `sase-core-rs==0.43.2` dependency in pyproject.toml. No action is needed: editable installs build from the checkout regardless, and `tools/ratchet_core_pin` moves the published pin on the release branch at release time.
[core-source] linked sase-core source changed since the extension was built; flagging an extension rebuild.
[setup] Note: the sase-core checkout is ahead of the published sase-core-rs pin in pyproject.toml; dev installs build from /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/sase/repos/linked/sase-core regardless. This is normal — the release-branch reconciler ratchets the published pin at release time, so no action is needed here.
[setup] Rebuilding sase_core_rs: linked sase-core source changed since the extension was built.
[validate_sase_core_rs_version] sase-core checkout is ahead of sase's compatibility window: source version 0.43.3 from /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/sase/repos/linked/sase-core/Cargo.toml does not satisfy `sase`'s `sase-core-rs==0.43.2` dependency in pyproject.toml. No action is needed: editable installs build from the checkout regardless, and `tools/ratchet_core_pin` moves the published pin on the release branch at release time.
[rust-install] Note: the sase-core checkout is ahead of the published sase-core-rs pin in pyproject.toml; dev builds from /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/sase/repos/linked/sase-core ignore it. This is normal — the release-branch reconciler ratchets the published pin at release time, so no action is needed here.
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
🐍 Found CPython 3.14 at /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/bin/python
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
   Compiling crossbeam-epoch v0.9.21
   Compiling smallvec v1.15.1
   Compiling serde_json v1.0.149
   Compiling target-lexicon v0.12.16
   Compiling stable_deref_trait v1.2.1
   Compiling futures-sink v0.3.32
   Compiling crossbeam-deque v0.8.8
   Compiling hashbrown v0.17.0
   Compiling equivalent v1.0.2
   Compiling tower-service v0.3.3
   Compiling ucd-trie v0.1.7
   Compiling iana-time-zone v0.1.65
   Compiling slab v0.4.12
   Compiling futures-io v0.3.32
   Compiling futures-task v0.3.32
   Compiling bitflags v2.11.1
   Compiling httparse v1.10.1
   Compiling writeable v0.6.3
   Compiling untrusted v0.9.0
   Compiling libm v0.2.16
   Compiling same-file v1.0.6
   Compiling litemap v0.8.2
   Compiling heck v0.5.0
   Compiling typenum v1.20.0
   Compiling icu_normalizer_data v2.2.0
   Compiling utf8_iter v1.0.4
   Compiling icu_properties_data v2.2.0
   Compiling fnv v1.0.7
   Compiling deunicode v1.6.2
   Compiling parking_lot_core v0.9.12
   Compiling httpdate v1.0.3
   Compiling lazy_static v1.5.0
    Building [                           ] 0/398: proc-macro2(build.rs), bitf…    Building [                           ] 1/398: proc-macro2(build.rs), bitf…    Building [                           ] 2/398: bitflags, crossbeam-epoch(b…    Building [                           ] 3/398: bitflags, crossbeam-epoch(b…    Building [                           ] 4/398: bitflags, crossbeam-epoch(b…    Building [                           ] 5/398: bitflags, crossbeam-epoch(b…    Building [                           ] 6/398: bitflags, crossbeam-epoch(b…    Building [                           ] 7/398: bitflags, crossbeam-epoch(b…    Building [                           ] 8/398: bitflags, crossbeam-epoch(b…    Building [                          ] 10/398: bitflags, crossbeam-epoch(b…    Building [                          ] 11/398: bitflags, crossbeam-epoch(b…    Building [                          ] 13/398: bitflags, crossbeam-epoch(b…    Building [>                         ] 16/398: bitflags, crossbeam-epoch(b…    Building [>                         ] 18/398: bitflags, crossbeam-epoch(b…    Building [>                         ] 19/398: bitflags, crossbeam-epoch(b…    Building [>                         ] 20/398: bitflags, crossbeam-epoch(b…    Building [>                         ] 21/398: bitflags, crossbeam-epoch(b…    Building [>                         ] 22/398: bitflags, crossbeam-epoch(b…    Building [>                         ] 24/398: bitflags, crossbeam-epoch(b…    Building [>                         ] 25/398: bitflags, serde_json(build)…    Building [>                         ] 26/398: bitflags, serde_json(build)…    Building [>                         ] 27/398: bitflags, serde_json(build)…    Building [>                         ] 29/398: bitflags, crossbeam-epoch(b…    Building [>                         ] 30/398: bitflags, crossbeam-epoch(b…   Compiling tower-layer v0.3.3
    Building [=>                        ] 31/398: bitflags, crossbeam-epoch(b…    Building [=>                        ] 32/398: bitflags, crossbeam-epoch(b…    Building [=>                        ] 33/398: bitflags, shlex, tower-laye…    Building [=>                        ] 34/398: bitflags, shlex, tower-laye…    Building [=>                        ] 35/398: bitflags, shlex, tower-laye…    Building [=>                        ] 36/398: bitflags, shlex, tower-laye…    Building [=>                        ] 37/398: bitflags, shlex, tower-laye…    Building [=>                        ] 38/398: bitflags, shlex, tower-laye…    Building [=>                        ] 39/398: bitflags, shlex, tower-laye…    Building [=>                        ] 40/398: bitflags, shlex, tower-laye…    Building [=>                        ] 41/398: bitflags, shlex, tower-laye…    Building [=>                        ] 42/398: bitflags, tower-layer, zero…   Compiling anstyle v1.0.14
    Building [=>                        ] 43/398: bitflags, tower-layer, zero…   Compiling cc v1.2.61
    Building [=>                        ] 44/398: bitflags, tower-layer, zero…   Compiling percent-encoding v2.3.2
    Building [=>                        ] 45/398: bitflags, tower-layer, zero…   Compiling vcpkg v0.2.15
    Building [==>                       ] 46/398: bitflags, tower-layer, zero…    Building [==>                       ] 47/398: bitflags, tower-layer, zero…   Compiling scopeguard v1.2.0
    Building [==>                       ] 48/398: bitflags, tower-layer, zero…   Compiling num-traits v0.2.19
    Building [==>                       ] 49/398: bitflags, tower-layer, zero…   Compiling sync_wrapper v1.0.2
    Building [==>                       ] 50/398: bitflags, sync_wrapper, tow…    Building [==>                       ] 51/398: bitflags, sync_wrapper, tow…   Compiling ryu v1.0.23
    Building [==>                       ] 52/398: bitflags, sync_wrapper, tow…   Compiling clap_lex v1.1.1
    Building [==>                       ] 53/398: bitflags, sync_wrapper, tow…    Building [==>                       ] 54/398: bitflags, sync_wrapper, tow…   Compiling generic-array v0.14.7
    Building [==>                       ] 56/398: bitflags, sync_wrapper, tow…   Compiling ahash v0.8.12
    Building [==>                       ] 57/398: bitflags, sync_wrapper, tow…   Compiling unicode-segmentation v1.13.3
    Building [==>                       ] 58/398: bitflags, sync_wrapper, tow…    Building [==>                       ] 59/398: bitflags, sync_wrapper, tow…    Building [==>                       ] 60/398: bitflags, sync_wrapper, tow…    Building [==>                       ] 61/398: bitflags, sync_wrapper, tow…   Compiling rustls v0.21.12
    Building [===>                      ] 62/398: bitflags, sync_wrapper, tow…   Compiling thiserror v1.0.69
    Building [===>                      ] 63/398: bitflags, sync_wrapper, tow…   Compiling rayon-core v1.13.0
    Building [===>                      ] 64/398: bitflags, sync_wrapper, tow…   Compiling either v1.19.0
    Building [===>                      ] 65/398: bitflags, sync_wrapper, tow…   Compiling pkg-config v0.3.33
    Building [===>                      ] 66/398: bitflags, sync_wrapper, tow…   Compiling phf_shared v0.11.3
    Building [===>                      ] 67/398: bitflags, sync_wrapper, tow…    Building [===>                      ] 68/398: bitflags, sync_wrapper, tow…   Compiling num-conv v0.2.1
    Building [===>                      ] 69/398: bitflags, num-conv, sync_wr…    Building [===>                      ] 70/398: bitflags, num-conv, sync_wr…    Building [===>                      ] 71/398: bitflags, num-conv, sync_wr…    Building [===>                      ] 72/398: bitflags, num-conv, sync_wr…   Compiling try-lock v0.2.5
    Building [===>                      ] 73/398: bitflags, num-conv, sync_wr…   Compiling rustix v1.1.4
    Building [===>                      ] 74/398: bitflags, num-conv, sync_wr…   Compiling futures-channel v0.3.32
    Building [===>                      ] 75/398: bitflags, num-conv, sync_wr…   Compiling walkdir v2.5.0
    Building [===>                      ] 76/398: bitflags, num-conv, sync_wr…   Compiling http v1.4.0
    Building [====>                     ] 77/398: bitflags, num-conv, sync_wr…   Compiling http v0.2.12
   Compiling powerfmt v0.2.0
   Compiling time-core v0.1.8
   Compiling thiserror v2.0.18
   Compiling winnow v1.0.4
   Compiling rustversion v1.0.22
    Building [====>                     ] 84/398: num-conv, sync_wrapper, tow…   Compiling aho-corasick v1.1.4
    Building [====>                     ] 85/398: num-conv, sync_wrapper, tow…   Compiling bstr v1.13.1
    Building [====>                     ] 87/398: num-conv, sync_wrapper, fut…   Compiling getrandom v0.4.2
    Building [====>                     ] 88/398: getrandom(build.rs), num-co…    Building [====>                     ] 89/398: getrandom(build.rs), num-co…    Building [====>                     ] 90/398: getrandom(build.rs), num-co…   Compiling tracing-core v0.1.36
   Compiling grep-matcher v0.1.9
    Building [=====>                    ] 92/398: getrandom(build.rs), num-co…    Building [=====>                    ] 93/398: getrandom(build.rs), num-co…    Building [=====>                    ] 94/398: getrandom(build.rs), num-co…    Building [=====>                    ] 95/398: getrandom(build.rs), num-co…   Compiling colored v2.2.0
    Building [=====>                    ] 96/398: getrandom(build.rs), num-co…    Building [=====>                    ] 97/398: num-conv, sync_wrapper, thi…   Compiling atomic-waker v1.1.2
    Building [=====>                    ] 98/398: num-conv, sync_wrapper, thi…    Building [=====>                    ] 99/398: num-conv, sync_wrapper, thi…    Building [=====>                   ] 100/398: num-conv, sync_wrapper, thi…   Compiling winnow v0.7.15
    Building [=====>                   ] 101/398: num-conv, sync_wrapper, thi…   Compiling linux-raw-sys v0.12.1
    Building [=====>                   ] 102/398: num-conv, sync_wrapper, thi…    Building [=====>                   ] 103/398: num-conv, sync_wrapper, thi…   Compiling indexmap v2.14.0
    Building [=====>                   ] 104/398: num-conv, sync_wrapper, thi…    Building [=====>                   ] 105/398: num-conv, sync_wrapper, thi…   Compiling cpufeatures v0.2.17
    Building [=====>                   ] 106/398: num-conv, sync_wrapper, thi…   Compiling pyo3-build-config v0.22.6
    Building [=====>                   ] 107/398: num-conv, sync_wrapper, thi…   Compiling mime v0.3.17
    Building [=====>                   ] 108/398: num-conv, sync_wrapper, thi…   Compiling toml_writer v1.1.3+spec-1.1.0
    Building [=====>                   ] 109/398: num-conv, sync_wrapper, thi…   Compiling slug v0.1.6
    Building [=====>                   ] 110/398: num-conv, sync_wrapper, thi…   Compiling encoding_rs v0.8.35
    Building [=====>                   ] 111/398: num-conv, sync_wrapper, thi…    Building [======>                  ] 112/398: num-conv, sync_wrapper, thi…    Building [======>                  ] 113/398: num-conv, crossbeam-epoch, …    Building [======>                  ] 114/398: num-conv, crossbeam-epoch, …    Building [======>                  ] 115/398: num-conv, crossbeam-epoch, …   Compiling home v0.5.12
    Building [======>                  ] 116/398: num-conv, crossbeam-epoch, …   Compiling crossbeam-channel v0.5.17
    Building [======>                  ] 117/398: num-conv, crossbeam-epoch, …    Building [======>                  ] 118/398: num-conv, crossbeam-epoch, …   Compiling getrandom v0.2.17
    Building [======>                  ] 119/398: num-conv, crossbeam-epoch, …   Compiling errno v0.3.14
    Building [======>                  ] 120/398: num-conv, crossbeam-epoch, …   Compiling mio v1.2.0
    Building [======>                  ] 121/398: num-conv, crossbeam-epoch, …    Building [======>                  ] 122/398: num-conv, crossbeam-epoch, …   Compiling socket2 v0.6.3
    Building [======>                  ] 123/398: num-conv, crossbeam-epoch, …   Compiling psm v0.1.24
    Building [======>                  ] 124/398: num-conv, crossbeam-epoch, …   Compiling stacker v0.1.25
    Building [======>                  ] 125/398: num-conv, crossbeam-epoch, …   Compiling ring v0.17.14
    Building [======>                  ] 126/398: num-conv, crossbeam-epoch, …   Compiling humansize v2.1.3
    Building [======>                  ] 127/398: num-conv, crossbeam-epoch, …   Compiling lock_api v0.4.14
    Building [=======>                 ] 128/398: num-conv, crossbeam-epoch, …   Compiling socket2 v0.5.10
    Building [=======>                 ] 130/398: num-conv, crossbeam-epoch, …   Compiling deranged v0.5.8
    Building [=======>                 ] 131/398: num-conv, crossbeam-epoch, …    Building [=======>                 ] 132/398: psm(build), num-conv, cross…    Building [=======>                 ] 133/398: psm(build), num-conv, cross…   Compiling memmap2 v0.9.11
    Building [=======>                 ] 134/398: psm(build), num-conv, cross…    Building [=======>                 ] 135/398: psm(build), num-conv, cross…    Building [=======>                 ] 136/398: num-conv, crossbeam-epoch, …   Compiling term_size v0.3.2
    Building [=======>                 ] 137/398: num-conv, crossbeam-epoch, …   Compiling itertools v0.11.0
    Building [=======>                 ] 138/398: num-conv, crossbeam-epoch, …   Compiling memoffset v0.9.1
    Building [=======>                 ] 139/398: num-conv, crossbeam-epoch, …   Compiling libsqlite3-sys v0.30.1
    Building [=======>                 ] 140/398: num-conv, crossbeam-epoch, …    Building [=======>                 ] 141/398: num-conv, crossbeam-epoch, …   Compiling toml_datetime v0.7.5+spec-1.1.0
    Building [=======>                 ] 142/398: num-conv, crossbeam-epoch, …   Compiling serde_spanned v1.1.2
    Building [=======>                 ] 143/398: crossbeam-epoch, thiserror(…   Compiling phf v0.11.3
    Building [========>                ] 144/398: crossbeam-epoch, thiserror(…   Compiling form_urlencoded v1.2.2
    Building [========>                ] 145/398: crossbeam-epoch, thiserror(…    Building [========>                ] 146/398: crossbeam-epoch, thiserror(…   Compiling want v0.3.1
    Building [========>                ] 147/398: crossbeam-epoch, thiserror(…   Compiling time-macros v0.2.27
    Building [========>                ] 148/398: crossbeam-epoch, thiserror(…   Compiling base64 v0.21.7
    Building [========>                ] 149/398: crossbeam-epoch, thiserror(…   Compiling fallible-streaming-iterator v0.1.9
    Building [========>                ] 150/398: crossbeam-epoch, thiserror(…   Compiling chrono v0.4.44
    Building [========>                ] 151/398: crossbeam-epoch, thiserror(…   Compiling tinyvec v1.13.3
    Building [========>                ] 152/398: crossbeam-epoch, thiserror(…   Compiling num-integer v0.1.46
    Building [========>                ] 153/398: crossbeam-epoch, thiserror(…   Compiling unsafe-libyaml v0.2.11
    Building [========>                ] 155/398: crossbeam-epoch, thiserror(…   Compiling clap_builder v4.6.7
    Building [========>                ] 156/398: crossbeam-epoch, thiserror(…   Compiling toml_parser v1.1.5+spec-1.1.0
   Compiling base64 v0.22.1
    Building [========>                ] 158/398: crossbeam-epoch, toml_parse…   Compiling fastrand v2.4.1
    Building [========>                ] 159/398: crossbeam-epoch, toml_parse…    Building [=========>               ] 160/398: crossbeam-epoch, toml_parse…    Building [=========>               ] 161/398: crossbeam-epoch, toml_parse…   Compiling ppv-lite86 v0.2.21
    Building [=========>               ] 162/398: crossbeam-epoch, toml_parse…    Building [=========>               ] 163/398: crossbeam-epoch, toml_parse…   Compiling fallible-iterator v0.3.0
   Compiling tracing-log v0.2.0
    Building [=========>               ] 165/398: crossbeam-epoch, toml_parse…    Building [=========>               ] 166/398: crossbeam-epoch, toml_parse…   Compiling serde_path_to_error v0.1.20
    Building [=========>               ] 167/398: crossbeam-epoch, toml_parse…   Compiling fs2 v0.4.3
    Building [=========>               ] 168/398: crossbeam-epoch, toml_parse…    Building [=========>               ] 169/398: crossbeam-epoch, toml_parse…   Compiling http-body v1.0.1
    Building [=========>               ] 170/398: crossbeam-epoch, toml_parse…    Building [=========>               ] 171/398: crossbeam-epoch, toml_parse…   Compiling thread_local v1.1.9
    Building [=========>               ] 172/398: crossbeam-epoch, toml_parse…   Compiling sharded-slab v0.1.7
    Building [=========>               ] 173/398: crossbeam-epoch, toml_parse…   Compiling etcetera v0.8.0
    Building [=========>               ] 174/398: crossbeam-epoch, toml_parse…   Compiling unicode-casefold v0.2.0
    Building [=========>               ] 175/398: crossbeam-epoch, toml_parse…   Compiling block-buffer v0.10.4
    Building [==========>              ] 176/398: block-buffer, crossbeam-epo…   Compiling crypto-common v0.1.7
    Building [==========>              ] 177/398: block-buffer, crossbeam-epo…    Building [==========>              ] 178/398: block-buffer, crossbeam-epo…   Compiling regex-automata v0.4.14
    Building [==========>              ] 179/398: block-buffer, crossbeam-epo…   Compiling http-body v0.4.6
    Building [==========>              ] 180/398: block-buffer, crossbeam-epo…   Compiling webpki-roots v0.25.4
    Building [==========>              ] 181/398: block-buffer, crossbeam-epo…    Building [==========>              ] 182/398: block-buffer, crossbeam-epo…   Compiling signal-hook-registry v1.4.8
    Building [==========>              ] 183/398: block-buffer, crossbeam-epo…   Compiling rand_core v0.6.4
    Building [==========>              ] 184/398: block-buffer, crossbeam-epo…   Compiling ipnet v2.12.0
    Building [==========>              ] 185/398: block-buffer, crossbeam-epo…    Building [==========>              ] 186/398: block-buffer, crossbeam-epo…   Compiling sync_wrapper v0.1.2
    Building [==========>              ] 188/398: block-buffer, crossbeam-epo…    Building [==========>              ] 189/398: block-buffer, toml_parser, …    Building [==========>              ] 190/398: block-buffer, toml_parser, …   Compiling nu-ansi-term v0.50.3
    Building [==========>              ] 191/398: block-buffer, toml_parser, …    Building [===========>             ] 192/398: block-buffer, toml_parser, …   Compiling hex v0.4.3
    Building [===========>             ] 193/398: block-buffer, toml_parser, …   Compiling pyo3-macros-backend v0.22.6
    Building [===========>             ] 194/398: block-buffer, toml_parser, …   Compiling pyo3-ffi v0.22.6
    Building [===========>             ] 195/398: pyo3-ffi(build.rs), block-b…   Compiling pyo3 v0.22.6
    Building [===========>             ] 196/398: pyo3-ffi(build.rs), block-b…   Compiling semver v1.0.28
    Building [===========>             ] 197/398: pyo3-ffi(build.rs), block-b…   Compiling matchit v0.7.3
    Building [===========>             ] 198/398: pyo3-ffi(build.rs), block-b…   Compiling unicode-width v0.2.2
    Building [===========>             ] 199/398: pyo3-ffi(build.rs), block-b…   Compiling indoc v2.0.7
    Building [===========>             ] 200/398: pyo3-ffi(build.rs), block-b…   Compiling parking_lot v0.12.5
    Building [===========>             ] 201/398: pyo3-ffi(build.rs), block-b…   Compiling unindent v0.2.4
    Building [===========>             ] 202/398: pyo3-ffi(build.rs), block-b…   Compiling encoding_rs_io v0.1.8
   Compiling unicode-normalization v0.1.25
    Building [===========>             ] 204/398: pyo3-ffi(build.rs), block-b…    Building [===========>             ] 205/398: pyo3-ffi(build.rs), block-b…   Compiling rustls-pemfile v1.0.4
    Building [===========>             ] 206/398: pyo3-ffi(build.rs), block-b…    Building [============>            ] 207/398: pyo3-ffi(build.rs), block-b…    Building [============>            ] 208/398: pyo3-ffi(build.rs), block-b…    Building [============>            ] 209/398: pyo3-ffi(build.rs), block-b…   Compiling time v0.3.47
    Building [============>            ] 210/398: pyo3-ffi(build.rs), block-b…    Building [============>            ] 211/398: pyo3-ffi(build.rs), block-b…    Building [============>            ] 212/398: pyo3-ffi(build.rs), block-b…   Compiling num-bigint v0.4.6
    Building [============>            ] 213/398: pyo3-ffi(build.rs), block-b…    Building [============>            ] 214/398: pyo3-ffi(build.rs), block-b…    Building [============>            ] 215/398: pyo3-ffi(build.rs), block-b…    Building [============>            ] 216/398: pyo3-ffi(build.rs), block-b…   Compiling hashbrown v0.14.5
    Building [============>            ] 217/398: pyo3-ffi(build.rs), block-b…    Building [============>            ] 218/398: pyo3-ffi(build.rs), block-b…    Building [============>            ] 219/398: pyo3-ffi(build.rs), block-b…    Building [============>            ] 220/398: pyo3-ffi(build.rs), block-b…    Building [============>            ] 221/398: pyo3-ffi(build.rs), block-b…   Compiling toml v0.9.12+spec-1.1.0
    Building [============>            ] 222/398: pyo3-ffi(build.rs), block-b…    Building [=============>           ] 223/398: pyo3-ffi(build.rs), block-b…    Building [=============>           ] 224/398: pyo3-ffi(build.rs), block-b…   Compiling pem v3.0.6
    Building [=============>           ] 226/398: pyo3-ffi(build.rs), block-b…    Building [=============>           ] 227/398: pyo3-ffi(build.rs), block-b…    Building [=============>           ] 228/398: pyo3-ffi(build.rs), block-b…    Building [=============>           ] 229/398: pyo3-ffi(build.rs), block-b…    Building [=============>           ] 230/398: pyo3-ffi(build.rs), block-b…   Compiling http-body-util v0.1.3
    Building [=============>           ] 231/398: pyo3-ffi(build.rs), block-b…    Building [=============>           ] 232/398: pyo3-ffi(build.rs), block-b…    Building [=============>           ] 233/398: block-buffer, parking_lot, …    Building [=============>           ] 234/398: block-buffer, parking_lot, …    Building [=============>           ] 235/398: block-buffer, parking_lot, …    Building [=============>           ] 236/398: block-buffer, parking_lot, …    Building [=============>           ] 237/398: block-buffer, parking_lot, …    Building [=============>           ] 238/398: block-buffer, parking_lot, …    Building [==============>          ] 239/398: block-buffer, parking_lot, …    Building [==============>          ] 240/398: block-buffer, rustls(build)…    Building [==============>          ] 241/398: block-buffer, parking_lot, …    Building [==============>          ] 242/398: parking_lot, rustix, libsql…    Building [==============>          ] 243/398: parking_lot, rustix, libsql…    Building [==============>          ] 244/398: parking_lot, rustix, libsql…    Building [==============>          ] 245/398: parking_lot, rustix, libsql…    Building [==============>          ] 246/398: parking_lot, rustix, libsql…    Building [==============>          ] 247/398: parking_lot, rustix, libsql…    Building [==============>          ] 248/398: parking_lot, rustix, libsql…   Compiling digest v0.10.7
    Building [==============>          ] 249/398: parking_lot, rustix, libsql…   Compiling rand_chacha v0.3.1
    Building [==============>          ] 250/398: parking_lot, rustix, libsql…    Building [==============>          ] 251/398: parking_lot, rustix, libsql…    Building [==============>          ] 252/398: parking_lot, rustix, libsql…    Building [==============>          ] 253/398: parking_lot, rustix, libsql…    Building [==============>          ] 254/398: parking_lot, rustix, libsql…    Building [===============>         ] 255/398: parking_lot, rustix, libsql…    Building [===============>         ] 256/398: parking_lot, rustix, libsql…    Building [===============>         ] 257/398: parking_lot, rustix, libsql…    Building [===============>         ] 258/398: parking_lot, rustix, libsql…    Building [===============>         ] 259/398: parking_lot, rustix, libsql…    Building [===============>         ] 260/398: parking_lot, rustix, libsql…    Building [===============>         ] 261/398: parking_lot, rustix, libsql…    Building [===============>         ] 262/398: parking_lot, rustix, libsql…    Building [===============>         ] 263/398: rustix, libsqlite3-sys(buil…    Building [===============>         ] 264/398: rustix, libsqlite3-sys(buil…   Compiling grep-searcher v0.1.17
    Building [===============>         ] 264/398: rustix, grep-searcher, libs…    Building [===============>         ] 265/398: rustix, grep-searcher, libs…    Building [===============>         ] 266/398: rustix, grep-searcher, libs…   Compiling pest v2.9.4
    Building [===============>         ] 267/398: rustix, grep-searcher, libs…    Building [===============>         ] 268/398: rustix, grep-searcher, libs…    Building [===============>         ] 270/398: rustix, grep-searcher, libs…   Compiling sha1 v0.10.7
   Compiling sha2 v0.10.9
    Building [================>        ] 271/398: rustix, grep-searcher, libs…    Building [================>        ] 272/398: rustix, grep-searcher, libs…    Building [================>        ] 273/398: rustix, grep-searcher, libs…    Building [================>        ] 274/398: rustix, grep-searcher, libs…   Compiling hashlink v0.9.1
    Building [================>        ] 275/398: rustix, grep-searcher, libs…    Building [================>        ] 276/398: rustix, grep-searcher, libs…   Compiling rand v0.8.6
    Building [================>        ] 277/398: rustix, grep-searcher, libs…    Building [================>        ] 278/398: rustix, grep-searcher, libs…    Building [================>        ] 279/398: rustix, grep-searcher, libs…   Compiling tempfile v3.27.0
    Building [================>        ] 280/398: grep-searcher, libsqlite3-s…   Compiling syn v2.0.117
   Compiling syn v3.0.9
    Building [================>        ] 281/398: grep-searcher, libsqlite3-s…   Compiling rayon v1.12.0
    Building [================>        ] 282/398: grep-searcher, libsqlite3-s…    Building [================>        ] 283/398: grep-searcher, libsqlite3-s…   Compiling regex v1.12.3
   Compiling globset v0.4.19
    Building [================>        ] 285/398: libsqlite3-sys(build), rand…    Building [================>        ] 286/398: libsqlite3-sys(build), rand…    Building [=================>       ] 287/398: libsqlite3-sys(build), rand…    Building [=================>       ] 288/398: libsqlite3-sys(build), rand…    Building [=================>       ] 289/398: libsqlite3-sys(build), rand…   Compiling phf_generator v0.11.3
    Building [=================>       ] 289/398: phf_generator, libsqlite3-s…    Building [=================>       ] 290/398: phf_generator, libsqlite3-s…    Building [=================>       ] 291/398: phf_generator, libsqlite3-s…   Compiling pest_meta v2.9.4
    Building [=================>       ] 292/398: phf_generator, libsqlite3-s…   Compiling ignore v0.4.32
    Building [=================>       ] 293/398: phf_generator, libsqlite3-s…   Compiling parse-zoneinfo v0.3.1
    Building [=================>       ] 294/398: phf_generator, libsqlite3-s…    Building [=================>       ] 295/398: phf_generator, libsqlite3-s…    Building [=================>       ] 296/398: phf_generator, libsqlite3-s…   Compiling phf_codegen v0.11.3
    Building [=================>       ] 297/398: libsqlite3-sys(build), ring…   Compiling rustls-webpki v0.101.7
   Compiling sct v0.7.1
    Building [=================>       ] 297/398: sct, libsqlite3-sys(build),…    Building [=================>       ] 298/398: sct, libsqlite3-sys(build),…    Building [=================>       ] 299/398: sct, libsqlite3-sys(build),…   Compiling chrono-tz-build v0.3.0
    Building [=================>       ] 300/398: sct, libsqlite3-sys(build),…    Building [=================>       ] 301/398: libsqlite3-sys(build), rust…   Compiling globwalk v0.9.1
    Building [=================>       ] 302/398: libsqlite3-sys(build), rust…    Building [==================>      ] 303/398: libsqlite3-sys(build), rust…   Compiling chrono-tz v0.9.0
    Building [==================>      ] 304/398: libsqlite3-sys(build), rust…    Building [==================>      ] 305/398: libsqlite3-sys(build), rust…    Building [==================>      ] 306/398: libsqlite3-sys(build), rust…    Building [==================>      ] 307/398: libsqlite3-sys(build), rust…    Building [==================>      ] 308/398: libsqlite3-sys(build), rust…    Building [==================>      ] 309/398: libsqlite3-sys(build), rust…    Building [==================>      ] 310/398: libsqlite3-sys(build), rust…   Compiling pest_generator v2.9.4
   Compiling clap_derive v4.6.7
   Compiling derive_arbitrary v1.5.0
    Building [==================>      ] 311/398: libsqlite3-sys(build), rust…   Compiling arbitrary v1.5.0
    Building [==================>      ] 312/398: libsqlite3-sys(build), rust…   Compiling synstructure v0.13.2
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
    Building [==================>      ] 313/398: displaydoc, libsqlite3-sys(…   Compiling pest_derive v2.9.4
    Building [==================>      ] 314/398: displaydoc, pest_derive, li…   Compiling async-stream v0.3.6
    Building [==================>      ] 315/398: displaydoc, pest_derive, li…    Building [==================>      ] 316/398: pest_derive, libsqlite3-sys…   Compiling tokio v1.52.2
    Building [==================>      ] 317/398: pest_derive, libsqlite3-sys…    Building [==================>      ] 318/398: pest_derive, libsqlite3-sys…   Compiling clap v4.6.7
    Building [===================>     ] 319/398: pest_derive, libsqlite3-sys…    Building [===================>     ] 320/398: libsqlite3-sys(build), rust…   Compiling futures-util v0.3.32
    Building [===================>     ] 321/398: libsqlite3-sys(build), rust…    Building [===================>     ] 322/398: libsqlite3-sys(build), rust…   Compiling tracing v0.1.44
    Building [===================>     ] 323/398: libsqlite3-sys(build), rust…    Building [===================>     ] 324/398: libsqlite3-sys(build), rust…    Building [===================>     ] 325/398: libsqlite3-sys(build), rust…    Building [===================>     ] 326/398: libsqlite3-sys(build), rust…   Compiling zerofrom-derive v0.1.7
   Compiling yoke-derive v0.8.2
    Building [===================>     ] 327/398: libsqlite3-sys(build), rust…   Compiling clap-cargo v0.18.3
    Building [===================>     ] 328/398: libsqlite3-sys(build), rust…   Compiling table_formatter v0.6.1
    Building [===================>     ] 329/398: libsqlite3-sys(build), rust…    Building [===================>     ] 330/398: libsqlite3-sys(build), rust…   Compiling simple_asn1 v0.6.4
    Building [===================>     ] 331/398: libsqlite3-sys(build), rust…   Compiling zerofrom v0.1.7
    Building [===================>     ] 332/398: zerofrom, libsqlite3-sys(bu…    Building [===================>     ] 333/398: zerofrom, libsqlite3-sys(bu…   Compiling tower-http v0.5.2
    Building [===================>     ] 334/398: zerofrom, libsqlite3-sys(bu…    Building [====================>    ] 335/398: zerofrom, libsqlite3-sys(bu…   Compiling yoke v0.8.2
    Building [====================>    ] 336/398: libsqlite3-sys(build), rust…    Building [====================>    ] 337/398: libsqlite3-sys(build), rust…    Building [====================>    ] 338/398: libsqlite3-sys(build), rust…   Compiling matchers v0.2.0
    Building [====================>    ] 338/398: regex, libsqlite3-sys(build…    Building [====================>    ] 339/398: regex, libsqlite3-sys(build…   Compiling zerovec v0.11.6
   Compiling zerotrie v0.2.4
   Compiling tracing-subscriber v0.3.23
    Building [====================>    ] 340/398: regex, libsqlite3-sys(build…    Building [====================>    ] 341/398: regex, libsqlite3-sys(build…    Building [====================>    ] 342/398: regex, libsqlite3-sys(build…    Building [====================>    ] 343/398: regex, libsqlite3-sys(build…    Building [====================>    ] 344/398: regex, libsqlite3-sys(build…   Compiling json5 v0.4.1
   Compiling tera v1.20.1
   Compiling sase_workspace_hack v0.1.0 (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/sase/repos/linked/sase-core/crates/sase_workspace_hack)
    Building [====================>    ] 345/398: regex, libsqlite3-sys(build…   Compiling pyo3-macros v0.22.6
    Building [====================>    ] 346/398: regex, libsqlite3-sys(build…    Building [====================>    ] 347/398: regex, libsqlite3-sys(build…    Building [====================>    ] 348/398: regex, libsqlite3-sys(build…    Building [====================>    ] 349/398: regex, libsqlite3-sys(build…    Building [====================>    ] 350/398: regex, libsqlite3-sys(build…   Compiling dashmap v6.1.0
   Compiling serde_urlencoded v0.7.1
   Compiling serde_yaml v0.9.34+deprecated
   Compiling jsonwebtoken v9.3.1
    Building [=====================>   ] 351/398: regex, libsqlite3-sys(build…    Building [=====================>   ] 352/398: libsqlite3-sys(build), rust…    Building [=====================>   ] 353/398: libsqlite3-sys(build), rust…    Building [=====================>   ] 354/398: libsqlite3-sys(build), rust…    Building [=====================>   ] 355/398: libsqlite3-sys(build), rust…   Compiling tinystr v0.8.3
   Compiling potential_utf v0.1.5
    Building [=====================>   ] 356/398: libsqlite3-sys(build), rust…   Compiling axum-core v0.4.5
    Building [=====================>   ] 357/398: libsqlite3-sys(build), rust…   Compiling icu_collections v2.2.0
    Building [=====================>   ] 357/398: icu_collections, libsqlite3…    Building [=====================>   ] 358/398: icu_collections, libsqlite3…    Building [=====================>   ] 359/398: icu_collections, libsqlite3…    Building [=====================>   ] 360/398: icu_collections, libsqlite3…    Building [=====================>   ] 361/398: icu_collections, libsqlite3…   Compiling icu_locale_core v2.2.0
    Building [=====================>   ] 362/398: icu_collections, libsqlite3…    Building [=====================>   ] 363/398: libsqlite3-sys(build), tera…   Compiling tokei v15.0.0
    Building [=====================>   ] 364/398: libsqlite3-sys(build), axum…    Building [=====================>   ] 365/398: libsqlite3-sys(build), axum…    Building [=====================>   ] 366/398: libsqlite3-sys(build), axum…    Building [======================>  ] 367/398: libsqlite3-sys(build), axum…    Building [======================>  ] 368/398: libsqlite3-sys(build), axum…    Building [======================>  ] 369/398: libsqlite3-sys(build), axum…    Building [======================>  ] 370/398: libsqlite3-sys(build), pyo3…   Compiling icu_provider v2.2.0
    Building [======================>  ] 370/398: libsqlite3-sys(build), icu_…    Building [======================>  ] 371/398: libsqlite3-sys(build), icu_…    Building [======================>  ] 372/398: libsqlite3-sys(build), icu_…    Building [======================>  ] 372/398: libsqlite3-sys(build), toke…    Building [======================>  ] 373/398: libsqlite3-sys(build), toke…   Compiling icu_properties v2.2.0
   Compiling icu_normalizer v2.2.0
    Building [======================>  ] 373/398: libsqlite3-sys(build), icu_…    Building [======================>  ] 374/398: libsqlite3-sys(build), icu_…   Compiling tokio-util v0.7.18
   Compiling tower v0.5.3
   Compiling tokio-rustls v0.24.1
   Compiling hyper v1.9.0
    Building [======================>  ] 375/398: libsqlite3-sys(build), icu_…    Building [======================>  ] 376/398: libsqlite3-sys(build), icu_…    Building [======================>  ] 377/398: libsqlite3-sys(build), icu_…    Building [======================>  ] 378/398: libsqlite3-sys(build), icu_…   Compiling h2 v0.3.27
    Building [======================>  ] 379/398: libsqlite3-sys(build), icu_…   Compiling idna_adapter v1.2.2
    Building [======================>  ] 380/398: libsqlite3-sys(build), h2, …    Building [======================>  ] 381/398: libsqlite3-sys(build), h2, …   Compiling idna v1.1.0
    Building [======================>  ] 382/398: libsqlite3-sys(build), h2, …   Compiling hyper-util v0.1.20
    Building [=======================> ] 383/398: libsqlite3-sys(build), h2, …   Compiling axum v0.7.9
    Building [=======================> ] 384/398: libsqlite3-sys(build), h2, …   Compiling url v2.5.8
    Building [=======================> ] 385/398: libsqlite3-sys(build), h2, …    Building [=======================> ] 386/398: libsqlite3-sys(build), h2, …    Building [=======================> ] 387/398: libsqlite3-sys(build), h2, …   Compiling hyper v0.14.32
    Building [=======================> ] 387/398: hyper, libsqlite3-sys(build…    Building [=======================> ] 388/398: hyper, libsqlite3-sys(build…    Building [=======================> ] 389/398: hyper, libsqlite3-sys(build)   Compiling hyper-rustls v0.24.2
    Building [=======================> ] 389/398: hyper, libsqlite3-sys(build…    Building [=======================> ] 390/398: libsqlite3-sys(build), hype…   Compiling reqwest v0.11.27
    Building [=======================> ] 390/398: libsqlite3-sys(build), reqw…    Building [=======================> ] 391/398: libsqlite3-sys(build), reqw…    Building [=======================> ] 392/398: libsqlite3-sys(build)           Building [=======================> ] 393/398: libsqlite3-sys                 Compiling rusqlite v0.32.1
    Building [=======================> ] 393/398: rusqlite, libsqlite3-sys        Building [=======================> ] 394/398: rusqlite                       Compiling sase_core v0.43.3 (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/sase/repos/linked/sase-core/crates/sase_core)
    Building [=======================> ] 394/398: sase_core, rusqlite             Building [=======================> ] 395/398: sase_core                      Compiling sase_gateway v0.43.3 (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/sase/repos/linked/sase-core/crates/sase_gateway)
    Building [=======================> ] 395/398: sase_gateway, sase_core         Building [=======================> ] 396/398: sase_gateway                   Compiling sase_core_py v0.43.3 (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/sase/repos/linked/sase-core/crates/sase_core_py)
    Building [=======================> ] 397/398: sase_core_py                    Finished `release` profile [optimized] target(s) in 15m 38s
📦 Built wheel for abi3 Python ≥ 3.12 to /home/bryan/.sase/cache/sase-core-artifacts/.build-5bkp_92j/sase_core_rs-0.43.3-cp312-abi3-manylinux_2_39_x86_64.whl
[rust-install] Installing cached sase_core_rs wheel from /home/bryan/.sase/cache/sase-core-artifacts/f3b00ef18fc7115081978f5197edb703ba54be1b162aee508693a259884bb143/sase_core_rs-0.43.3-cp312-abi3-manylinux_2_39_x86_64.whl.
Resolved 1 package in 1ms
Prepared 1 package in 152ms
Uninstalled 1 package in 1ms
Installed 1 package in 3ms
 - sase-core-rs==0.43.3 (from file:///home/bryan/.sase/cache/sase-core-artifacts/6402df24aafcfe1ce9432b86dd22d018f92af90f677ef5410f1fe1d018a25ce2/sase_core_rs-0.43.3-cp312-abi3-manylinux_2_39_x86_64.whl)
 + sase-core-rs==0.43.3 (from file:///home/bryan/.sase/cache/sase-core-artifacts/f3b00ef18fc7115081978f5197edb703ba54be1b162aee508693a259884bb143/sase_core_rs-0.43.3-cp312-abi3-manylinux_2_39_x86_64.whl)
# Keep the LSP server in lockstep with the extension: both are built
# from the same sase-core checkout, and the ACE/LSP parity tests
# compare their directive contracts.
[sase-core-wheel-cache] miss: no exact cached wheel
[sase-core-wheel-cache] Waiting for the shared build lock for 9e55f153ca43 (up to 900s).
[rust-lsp-install] Installing cached LSP binary from /home/bryan/.sase/cache/sase-core-artifacts/9e55f153ca434f6b5591992426468711b797b362182daf6dd65935911b79f3cf/sase-macro-lsp.
[rust-lsp-install] installed /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/bin/sase-macro-lsp
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
[core-floor-probe] blocked_unpublished: sase-core-rs==0.43.2 is missing 16 capability(s), and at least one has no containing sase-core release tag yet.
[core-floor-probe] decide_workspace_retention: first appears in sase-core 80338d6 (feat(workspace_retention): classify stranded handoff claim settlement); no release tag contains it yet.
[core-floor-probe] effective_wait_target: first appears in sase-core d7b00dd (feat(wait_target): add parse, effective-target, and NamedEnum vocabulary); release v0.43.3 contains it.
[core-floor-probe] evaluate_recovery_decision: first appears in sase-core 73ec04a (feat(staged-recovery): add Rust-owned recovery contracts and replay decisions); no release tag contains it yet.
[core-floor-probe] parse_wait_target: first appears in sase-core d7b00dd (feat(wait_target): add parse, effective-target, and NamedEnum vocabulary); release v0.43.3 contains it.
[core-floor-probe] plan_checked_release_workspace_claim_from_content: first appears in sase-core 80338d6 (feat(workspace_retention): classify stranded handoff claim settlement); no release tag contains it yet.
[core-floor-probe] plan_pin_workspace_claim_from_content: first appears in sase-core 80338d6 (feat(workspace_retention): classify stranded handoff claim settlement); no release tag contains it yet.
[core-floor-probe] recovery_adoption_lock_filename: first appears in sase-core 73ec04a (feat(staged-recovery): add Rust-owned recovery contracts and replay decisions); no release tag contains it yet.
[core-floor-probe] recovery_context_wire_schema_version: first appears in sase-core 73ec04a (feat(staged-recovery): add Rust-owned recovery contracts and replay decisions); no release tag contains it yet.
[core-floor-probe] resolve_agent_run_state_observations: first appears in sase-core dc5383f (feat(agent-run-state): classify raw evidence and bound hood discovery); no release tag contains it yet.
[core-floor-probe] select_agent_run_state_discovery_window: first appears in sase-core dc5383f (feat(agent-run-state): classify raw evidence and bound hood discovery); no release tag contains it yet.
[core-floor-probe] select_agent_run_state_hoods: first appears in sase-core dc5383f (feat(agent-run-state): classify raw evidence and bound hood discovery); no release tag contains it yet.
[core-floor-probe] select_current_wait_turn: first appears in sase-core d7b00dd (feat(wait_target): add parse, effective-target, and NamedEnum vocabulary); release v0.43.3 contains it.
[core-floor-probe] staged_handoff_receipt_transition_allowed: first appears in sase-core 73ec04a (feat(staged-recovery): add Rust-owned recovery contracts and replay decisions); no release tag contains it yet.
[core-floor-probe] staged_reconcile_page: first appears in sase-core 16a3ed0 (feat(staged-handoff): add bounded discovery and automatic recovery policy); no release tag contains it yet.
[core-floor-probe] validate_recovery_context: first appears in sase-core 73ec04a (feat(staged-recovery): add Rust-owned recovery contracts and replay decisions); no release tag contains it yet.
[core-floor-probe] workspace_retention_wire_schema_version: first appears in sase-core 80338d6 (feat(workspace_retention): classify stranded handoff claim settlement); no release tag contains it yet.
{"cache_hit": true, "capabilities": [{"commit": "80338d6", "name": "decide_workspace_retention", "release": null, "subject": "feat(workspace_retention): classify stranded handoff claim settlement"}, {"commit": "d7b00dd", "name": "effective_wait_target", "release": "v0.43.3", "subject": "feat(wait_target): add parse, effective-target, and NamedEnum vocabulary"}, {"commit": "73ec04a", "name": "evaluate_recovery_decision", "release": null, "subject": "feat(staged-recovery): add Rust-owned recovery contracts and replay decisions"}, {"commit": "d7b00dd", "name": "parse_wait_target", "release": "v0.43.3", "subject": "feat(wait_target): add parse, effective-target, and NamedEnum vocabulary"}, {"commit": "80338d6", "name": "plan_checked_release_workspace_claim_from_content", "release": null, "subject": "feat(workspace_retention): classify stranded handoff claim settlement"}, {"commit": "80338d6", "name": "plan_pin_workspace_claim_from_content", "release": null, "subject": "feat(workspace_retention): classify stranded handoff claim settlement"}, {"commit": "73ec04a", "name": "recovery_adoption_lock_filename", "release": null, "subject": "feat(staged-recovery): add Rust-owned recovery contracts and replay decisions"}, {"commit": "73ec04a", "name": "recovery_context_wire_schema_version", "release": null, "subject": "feat(staged-recovery): add Rust-owned recovery contracts and replay decisions"}, {"commit": "dc5383f", "name": "resolve_agent_run_state_observations", "release": null, "subject": "feat(agent-run-state): classify raw evidence and bound hood discovery"}, {"commit": "dc5383f", "name": "select_agent_run_state_discovery_window", "release": null, "subject": "feat(agent-run-state): classify raw evidence and bound hood discovery"}, {"commit": "dc5383f", "name": "select_agent_run_state_hoods", "release": null, "subject": "feat(agent-run-state): classify raw evidence and bound hood discovery"}, {"commit": "d7b00dd", "name": "select_current_wait_turn", "release": "v0.43.3", "subject": "feat(wait_target): add parse, effective-target, and NamedEnum vocabulary"}, {"commit": "73ec04a", "name": "staged_handoff_receipt_transition_allowed", "release": null, "subject": "feat(staged-recovery): add Rust-owned recovery contracts and replay decisions"}, {"commit": "16a3ed0", "name": "staged_reconcile_page", "release": null, "subject": "feat(staged-handoff): add bounded discovery and automatic recovery policy"}, {"commit": "73ec04a", "name": "validate_recovery_context", "release": null, "subject": "feat(staged-recovery): add Rust-owned recovery contracts and replay decisions"}, {"commit": "80338d6", "name": "workspace_retention_wire_schema_version", "release": null, "subject": "feat(workspace_retention): classify stranded handoff claim settlement"}], "declared_floor": "0.43.2", "exit_code": 4, "message": "sase-core-rs==0.43.2 is missing 16 capability(s), and at least one has no containing sase-core release tag yet.", "status": "blocked_unpublished"}
✓ committed plans
[check] Skipping docs build; no docs inputs changed.
✗ test (scoped)
[validate_sase_core_rs_version] sase-core checkout is ahead of sase's compatibility window: source version 0.43.3 from /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/sase/repos/linked/sase-core/Cargo.toml does not satisfy `sase`'s `sase-core-rs==0.43.2` dependency in pyproject.toml. No action is needed: editable installs build from the checkout regardless, and `tools/ratchet_core_pin` moves the published pin on the release branch at release time.
[setup] Note: the sase-core checkout is ahead of the published sase-core-rs pin in pyproject.toml; dev installs build from /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/sase/repos/linked/sase-core regardless. This is normal — the release-branch reconciler ratchets the published pin at release time, so no action is needed here.
.venv/bin/python tools/setup_required_plugins
[setup] Installing required plugin sase-github>=0.2.5.
[setup] Installing required plugin sase-research-artifacts>=0.2.0.

┌───────────────────────────────────────────────────────┐
│                RUNNING: just test-scoped              │
└───────────────────────────────────────────────────────┘

---------- Running diff-scoped pytest selection... ----------
test selection escalated to the full suite (rules: core-identity-changed); 5560 test files in scope
coverage contexts: not consulted — the run escalates to the full suite, so ground truth had nothing to add
escalating to the governed full test lane (rules: core-identity-changed)
/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/pytest_asyncio/plugin.py:300: PytestDeprecationWarning: The configuration option "asyncio_default_fixture_loop_scope" is unset.
The event loop scope for asynchronous fixtures will default to the "fixture" caching scope. Future versions of pytest-asyncio will default the loop scope for asynchronous fixtures to "function" scope. Set the default fixture loop scope explicitly in order to avoid unexpected behavior in the future. Valid fixture loop scopes are: "function", "class", "module", "package", "session"

  warnings.warn(PytestDeprecationWarning(_DEFAULT_FIXTURE_LOOP_SCOPE_UNSET))
/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/pytest_asyncio/plugin.py:300: PytestDeprecationWarning: The configuration option "asyncio_default_fixture_loop_scope" is unset.
The event loop scope for asynchronous fixtures will default to the "fixture" caching scope. Future versions of pytest-asyncio will default the loop scope for asynchronous fixtures to "function" scope. Set the default fixture loop scope explicitly in order to avoid unexpected behavior in the future. Valid fixture loop scopes are: "function", "class", "module", "package", "session"

  warnings.warn(PytestDeprecationWarning(_DEFAULT_FIXTURE_LOOP_SCOPE_UNSET))
/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/pytest_asyncio/plugin.py:300: PytestDeprecationWarning: The configuration option "asyncio_default_fixture_loop_scope" is unset.
The event loop scope for asynchronous fixtures will default to the "fixture" caching scope. Future versions of pytest-asyncio will default the loop scope for asynchronous fixtures to "function" scope. Set the default fixture loop scope explicitly in order to avoid unexpected behavior in the future. Valid fixture loop scopes are: "function", "class", "module", "package", "session"

  warnings.warn(PytestDeprecationWarning(_DEFAULT_FIXTURE_LOOP_SCOPE_UNSET))
/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/pytest_asyncio/plugin.py:300: PytestDeprecationWarning: The configuration option "asyncio_default_fixture_loop_scope" is unset.
The event loop scope for asynchronous fixtures will default to the "fixture" caching scope. Future versions of pytest-asyncio will default the loop scope for asynchronous fixtures to "function" scope. Set the default fixture loop scope explicitly in order to avoid unexpected behavior in the future. Valid fixture loop scopes are: "function", "class", "module", "package", "session"

  warnings.warn(PytestDeprecationWarning(_DEFAULT_FIXTURE_LOOP_SCOPE_UNSET))
/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/pytest_asyncio/plugin.py:300: PytestDeprecationWarning: The configuration option "asyncio_default_fixture_loop_scope" is unset.
The event loop scope for asynchronous fixtures will default to the "fixture" caching scope. Future versions of pytest-asyncio will default the loop scope for asynchronous fixtures to "function" scope. Set the default fixture loop scope explicitly in order to avoid unexpected behavior in the future. Valid fixture loop scopes are: "function", "class", "module", "package", "session"

  warnings.warn(PytestDeprecationWarning(_DEFAULT_FIXTURE_LOOP_SCOPE_UNSET))
/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/pytest_asyncio/plugin.py:300: PytestDeprecationWarning: The configuration option "asyncio_default_fixture_loop_scope" is unset.
The event loop scope for asynchronous fixtures will default to the "fixture" caching scope. Future versions of pytest-asyncio will default the loop scope for asynchronous fixtures to "function" scope. Set the default fixture loop scope explicitly in order to avoid unexpected behavior in the future. Valid fixture loop scopes are: "function", "class", "module", "package", "session"

  warnings.warn(PytestDeprecationWarning(_DEFAULT_FIXTURE_LOOP_SCOPE_UNSET))
/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/pytest_asyncio/plugin.py:300: PytestDeprecationWarning: The configuration option "asyncio_default_fixture_loop_scope" is unset.
The event loop scope for asynchronous fixtures will default to the "fixture" caching scope. Future versions of pytest-asyncio will default the loop scope for asynchronous fixtures to "function" scope. Set the default fixture loop scope explicitly in order to avoid unexpected behavior in the future. Valid fixture loop scopes are: "function", "class", "module", "package", "session"

  warnings.warn(PytestDeprecationWarning(_DEFAULT_FIXTURE_LOOP_SCOPE_UNSET))
/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/pytest_asyncio/plugin.py:300: PytestDeprecationWarning: The configuration option "asyncio_default_fixture_loop_scope" is unset.
The event loop scope for asynchronous fixtures will default to the "fixture" caching scope. Future versions of pytest-asyncio will default the loop scope for asynchronous fixtures to "function" scope. Set the default fixture loop scope explicitly in order to avoid unexpected behavior in the future. Valid fixture loop scopes are: "function", "class", "module", "package", "session"

  warnings.warn(PytestDeprecationWarning(_DEFAULT_FIXTURE_LOOP_SCOPE_UNSET))
/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/pytest_asyncio/plugin.py:300: PytestDeprecationWarning: The configuration option "asyncio_default_fixture_loop_scope" is unset.
The event loop scope for asynchronous fixtures will default to the "fixture" caching scope. Future versions of pytest-asyncio will default the loop scope for asynchronous fixtures to "function" scope. Set the default fixture loop scope explicitly in order to avoid unexpected behavior in the future. Valid fixture loop scopes are: "function", "class", "module", "package", "session"

  warnings.warn(PytestDeprecationWarning(_DEFAULT_FIXTURE_LOOP_SCOPE_UNSET))
/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/pytest_asyncio/plugin.py:300: PytestDeprecationWarning: The configuration option "asyncio_default_fixture_loop_scope" is unset.
The event loop scope for asynchronous fixtures will default to the "fixture" caching scope. Future versions of pytest-asyncio will default the loop scope for asynchronous fixtures to "function" scope. Set the default fixture loop scope explicitly in order to avoid unexpected behavior in the future. Valid fixture loop scopes are: "function", "class", "module", "package", "session"

  warnings.warn(PytestDeprecationWarning(_DEFAULT_FIXTURE_LOOP_SCOPE_UNSET))
/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/pytest_asyncio/plugin.py:300: PytestDeprecationWarning: The configuration option "asyncio_default_fixture_loop_scope" is unset.
The event loop scope for asynchronous fixtures will default to the "fixture" caching scope. Future versions of pytest-asyncio will default the loop scope for asynchronous fixtures to "function" scope. Set the default fixture loop scope explicitly in order to avoid unexpected behavior in the future. Valid fixture loop scopes are: "function", "class", "module", "package", "session"

  warnings.warn(PytestDeprecationWarning(_DEFAULT_FIXTURE_LOOP_SCOPE_UNSET))
/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/pytest_asyncio/plugin.py:300: PytestDeprecationWarning: The configuration option "asyncio_default_fixture_loop_scope" is unset.
The event loop scope for asynchronous fixtures will default to the "fixture" caching scope. Future versions of pytest-asyncio will default the loop scope for asynchronous fixtures to "function" scope. Set the default fixture loop scope explicitly in order to avoid unexpected behavior in the future. Valid fixture loop scopes are: "function", "class", "module", "package", "session"

  warnings.warn(PytestDeprecationWarning(_DEFAULT_FIXTURE_LOOP_SCOPE_UNSET))
/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/pytest_asyncio/plugin.py:300: PytestDeprecationWarning: The configuration option "asyncio_default_fixture_loop_scope" is unset.
The event loop scope for asynchronous fixtures will default to the "fixture" caching scope. Future versions of pytest-asyncio will default the loop scope for asynchronous fixtures to "function" scope. Set the default fixture loop scope explicitly in order to avoid unexpected behavior in the future. Valid fixture loop scopes are: "function", "class", "module", "package", "session"

  warnings.warn(PytestDeprecationWarning(_DEFAULT_FIXTURE_LOOP_SCOPE_UNSET))
/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/pytest_asyncio/plugin.py:300: PytestDeprecationWarning: The configuration option "asyncio_default_fixture_loop_scope" is unset.
The event loop scope for asynchronous fixtures will default to the "fixture" caching scope. Future versions of pytest-asyncio will default the loop scope for asynchronous fixtures to "function" scope. Set the default fixture loop scope explicitly in order to avoid unexpected behavior in the future. Valid fixture loop scopes are: "function", "class", "module", "package", "session"

  warnings.warn(PytestDeprecationWarning(_DEFAULT_FIXTURE_LOOP_SCOPE_UNSET))
/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/pytest_asyncio/plugin.py:300: PytestDeprecationWarning: The configuration option "asyncio_default_fixture_loop_scope" is unset.
The event loop scope for asynchronous fixtures will default to the "fixture" caching scope. Future versions of pytest-asyncio will default the loop scope for asynchronous fixtures to "function" scope. Set the default fixture loop scope explicitly in order to avoid unexpected behavior in the future. Valid fixture loop scopes are: "function", "class", "module", "package", "session"

  warnings.warn(PytestDeprecationWarning(_DEFAULT_FIXTURE_LOOP_SCOPE_UNSET))
============================= test session starts ==============================
platform linux -- Python 3.14.7, pytest-9.2.0, pluggy-1.7.0
rootdir: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19
configfile: pyproject.toml
testpaths: tests
plugins: mock-3.17.0, cov-7.1.0, hypothesis-6.170.14, inline-snapshot-0.36.1, asyncio-1.4.1, platformdirs-4.14.0, xdist-3.8.0
asyncio: mode=Mode.AUTO, debug=False, asyncio_default_fixture_loop_scope=None, asyncio_default_test_loop_scope=function
created: 14/14 workers
14 workers [59676 items]

........................................................................ [  0%]
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
........................................................................ [  2%]
........................................................................ [  2%]
........................................................................ [  2%]
........................................s............................... [  2%]
.....................................F.................................. [  3%]
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
........................s............................................... [  4%]
........................................................................ [  4%]
........................................................................ [  4%]
........................................................................ [  4%]
........................................................................ [  4%]
..................................................................s..... [  4%]
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
..........................s............................................. [  8%]
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
.................................................................s...... [ 10%]
........................................................................ [ 10%]
.......................s................................................ [ 10%]
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
........................................................................ [ 17%]
........................................................................ [ 18%]
....................s................................................... [ 18%]
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
........................s............................................... [ 34%]
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
........................................................................ [ 41%]
........................................................................ [ 42%]
........................................................................ [ 42%]
........................................................................ [ 42%]
........................................................................ [ 42%]
........................................................................ [ 42%]
........................................................................ [ 42%]
........................................................................ [ 42%]
................................................F....................... [ 42%]
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
.......................................................s................ [ 47%]
........................................................................ [ 47%]
........................................................................ [ 47%]
............................................ss.......................... [ 47%]
........................................................................ [ 47%]
........................................................................ [ 47%]
........................................................................ [ 47%]
..............................................................s......... [ 48%]
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
..F..................................................................... [ 69%]
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
......................ssss.............................................. [ 75%]
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
........................................................s............... [ 82%]
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
............................................................             [100%]/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/_pytest/unraisableexception.py:63: PytestUnraisableExceptionWarning: Exception ignored while calling GC callback <function gc_cumulative_time.<locals>.gc_callback at 0x7f6b4c429380>: None

Traceback (most recent call last):
  File "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/hypothesis/internal/conjecture/junkdrawer.py", line 497, in gc_callback
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
__________ test_reduce_stranded_work_round_trips_through_real_binding __________
[gw13] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/bin/python

    def test_reduce_stranded_work_round_trips_through_real_binding() -> None:
        facade._REDUCE_BINDING = None
        try:
            report = facade.reduce_stranded_work(
                {
                    "schema_version": 1,
                    "now": 200.0,
                    "settle_grace_seconds": 120.0,
                    "beads": [
                        {
                            "id": "sase-1.2",
                            "kind": "phase",
                            "status": "in_progress",
                            "candidate": True,
                            "assignee": "sase-1.2",
                            "parent_id": "sase-1",
                            "closed_at": None,
                            "records_available": True,
                            "members": [
                                {
                                    "name": "sase-1.2",
                                    "artifact_dir": "/tmp/sase-1.2",
                                    "turn_kind": "agent",
                                    "lifecycle": "done",
                                    "process_live": False,
                                    "remote": False,
                                    "finalizing": False,
                                    "pending_handoff": None,
                                    "handoff_inflight": False,
                                    "recovery_in_flight": False,
                                    "turn_state": None,
                                    "followup_pending": False,
                                    "followup_outcome": None,
                                    "followup_agent": None,
                                    "declared_bead_action": "keep",
                                    "started_at": 1.0,
                                    "ended_at": 2.0,
                                }
                            ],
                        }
                    ],
                }
            )
        except (RuntimeError, AttributeError) as exc:
            pytest.skip(f"stranded_work_reduce binding unavailable: {exc}")
>       assert report.schema_version == 1
E       AssertionError: assert 2 == 1
E        +  where 2 = StrandedWorkReport(schema_version=2, verdicts=(StrandedWorkVerdict(bead_id='sase-1.2', kind='phase', state='stranded',..._action='keep', since=2.0, parent_id='sase-1', blocked_by=(), blocks=()),), stranded_ids=('sase-1.2',), blocked_ids=()).schema_version

tests/test_stranded_work_facade.py:125: AssertionError
____ test_transport_adapter_preserves_handled_state_and_original_lifecycle _____
[gw11] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/bin/python

tmp_path = PosixPath('/var/tmp/sase-ad89b80b/pytest-of-bryan/pytest-4/popen-gw11/test_transport_adapter_preserv0')

    def test_transport_adapter_preserves_handled_state_and_original_lifecycle(
        tmp_path: Path,
    ) -> None:
        store_path = tmp_path / "actions.json"
        with (
            patch.object(pending_actions, "PENDING_ACTIONS_PATH", store_path),
            patch.object(
                pending_actions, "LEGACY_TELEGRAM_PENDING_ACTIONS_PATH", tmp_path / "legacy"
            ),
        ):
            notification = _notification(
                "abcd1234-full", "PlanApproval", {"response_dir": "x"}
            )
            pending_actions.register_notification(notification, now=10.0)
            pending_actions.upsert_transport_action(
                "abcd1234",
                {
                    "notification_id": notification.id,
                    "action": notification.action,
                    "chat_id": "chat",
                    "message_id": 42,
                    "extension": {"keep": True},
                },
                transport="telegram",
                now=20.0,
            )
            pending_actions.mark_already_handled(notification.id, source="test", now=30.0)
            pending_actions.register_notification(notification, now=100.0)
            entry = pending_actions.read_pending_action_store()["actions"]["abcd1234"]
            assert entry["state"] == "already_handled"
            assert entry["handled_source"] == "test"
            assert entry["created_at_unix"] == 10.0
            assert (
                entry["stale_deadline_unix"]
                == 10.0 + pending_actions.STALE_THRESHOLD_SECONDS
            )
            record = pending_actions.get_transport_action("abcd1234", transport="telegram")
            assert record is not None
            assert record["extension"] == {"keep": True}
            assert record["action_data"] == notification.action_data
            assert record["notification_id"] == notification.id
            assert pending_actions.remove_transport_action("abcd1234", transport="telegram")
            assert not pending_actions.remove_transport_action(
                "abcd1234", transport="telegram"
            )
            assert (
>               pending_actions.read_pending_action_store()["actions"]["abcd1234"]["state"]
                ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
                == "already_handled"
            )
E           KeyError: 'abcd1234'

tests/test_pending_actions.py:424: KeyError
_________________ test_total_timeout_settles_signaled_timeout __________________
[gw13] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/bin/python

tmp_path = PosixPath('/var/tmp/sase-ad89b80b/pytest-of-bryan/pytest-4/popen-gw13/test_total_timeout_settles_sig0')

    def test_total_timeout_settles_signaled_timeout(tmp_path: Path) -> None:
        """Row 5: a real supervisor's total timeout is a timeout, not a bare signal."""
    
        run_id, proc_id = _submit_worker(tmp_path, ("--", "sleep", "30"), timeout_seconds=1)
        proc = wait_for_proc(proc_id, timeout=60)
        assert _result_reason(proc) == "total-timeout"
>       run = _settled_run(run_id)
              ^^^^^^^^^^^^^^^^^^^^

/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/tests/tool/test_settlement_retention.py:213: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

run_id = 'bc3d0e2f0acd272fa4accc1ef6f9cb05', timeout = 60.0

    def _settled_run(run_id: str, *, timeout: float = 60.0) -> dict[str, Any]:
        deadline = time.monotonic() + timeout
        while time.monotonic() < deadline:
            run = get_run(run_id)
            if run["state"] not in ("created", "running"):
                return run
            time.sleep(0.2)  # sase-test-wait: poll worker or hook settlement
>       pytest.fail(f"run {run_id} did not settle")
E       Failed: run bc3d0e2f0acd272fa4accc1ef6f9cb05 did not settle

/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/tests/tool/test_settlement_retention.py:204: Failed
=============================== warnings summary ===============================
.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:915: 14 warnings
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:915: PytestAssertRewriteWarning: Module already imported so cannot be rewritten; tests.ace.tui.command_line._completion_sources_shared
    self.import_plugin(import_spec, consider_entry_points=True)

.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:915: 14 warnings
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:915: PytestAssertRewriteWarning: Module already imported so cannot be rewritten; tests.ace.tui._bench_tui_jk_helpers
    self.import_plugin(import_spec, consider_entry_points=True)

.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:915: 14 warnings
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:915: PytestAssertRewriteWarning: Module already imported so cannot be rewritten; tests.monitor._no_new_receipt
    self.import_plugin(import_spec, consider_entry_points=True)

.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:915: 14 warnings
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:915: PytestAssertRewriteWarning: Module already imported so cannot be rewritten; tests._axe_lumberjack_fixtures
    self.import_plugin(import_spec, consider_entry_points=True)

tests/ace/tui/test_agent_archive_controller_lookup.py::test_coalesced_idle_does_not_publish_false_missing_for_queued_open
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/_pytest/python.py:305: RuntimeWarning: coroutine '_run_archive_request' was never awaited
    @property
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/ace/tui/test_agent_archive_detail_ownership.py::test_inbox_debounced_update_repaints_after_archive_round_trip
  /home/bryan/.local/share/uv/python/cpython-3.14.7-linux-x86_64-gnu/lib/python3.14/typing.py:1725: RuntimeWarning: coroutine '_run_archive_request' was never awaited
    return ((p, type(p)) for p in parameters)
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/test_macro_processor_workflow_execute.py::test_execute_workflow_flatten_preserves_caller_named_args
tests/test_macro_processor_workflow_execute.py::test_execute_workflow_flatten_explicit_named_args_override_caller
tests/test_macro_processor_workflow_execute.py::test_execute_workflow_flatten_preserves_wrapper_model_override
tests/test_macro_processor_workflow_execute.py::test_execute_workflow_passes_inherited_vcs_tag_without_context_leak
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/src/sase/macro/workflow_runner.py:477: UserWarning: Standalone workflow '#split' is deprecated; use '#!split' instead.
    flattened = _flatten_anonymous_workflow(workflow, project=project)

tests/test_macro_processor_workflow_flatten.py::test_flatten_anonymous_workflow_returns_workflow_for_pure_multistep
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/tests/test_macro_processor_workflow_flatten.py:114: UserWarning: Standalone workflow '#split' is deprecated; use '#!split' instead.
    result = _flatten_anonymous_workflow(workflow)

tests/test_macro_processor_workflow_flatten.py::test_flatten_anonymous_workflow_slow_path_with_macro_and_workflow
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/src/sase/macro/workflow_runner.py:298: UserWarning: Standalone workflow '#batch_split' is deprecated; use '#!batch_split' instead.
    standalone = _find_standalone_workflow_ref(prompt_text, prompts)

tests/test_macro_processor_workflow_flatten.py::test_flatten_anonymous_workflow_slow_path_with_args
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/src/sase/macro/workflow_runner.py:298: UserWarning: Standalone workflow '#deploy' is deprecated; use '#!deploy' instead.
    standalone = _find_standalone_workflow_ref(prompt_text, prompts)

tests/test_macro_processor_workflow_flatten.py::test_flatten_anonymous_workflow_preserves_wrapper_model_directive
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/tests/test_macro_processor_workflow_flatten.py:421: UserWarning: Standalone workflow '#split' is deprecated; use '#!split' instead.
    result = _flatten_anonymous_workflow(workflow)

tests/ace/tui/test_launchable_mru.py::test_launch_marks_pending_synchronously
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/src/sase/ace/tui/actions/agent_workflow/_launch_submit_helpers.py:132: RuntimeWarning: coroutine 'schedule_submit_time_vcs_replay.<locals>.record_off_thread' was never awaited
    task = spawn_pump_free_task(
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/test_procs_supervisor.py::test_starter_exit_does_not_kill_a_released_proc
  <frozen os>:898: DeprecationWarning: This process (pid=4080313) is multi-threaded, use of fork() may lead to deadlocks in the child.

tests/sdd/test_artifact_link_event_acceptance_process_death.py::test_real_killed_publisher_process_leaves_no_corrupt_object_and_recovers
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/tests/sdd/test_artifact_link_event_acceptance_process_death.py:57: DeprecationWarning: This process (pid=4080209) is multi-threaded, use of fork() may lead to deadlocks in the child.
    child = os.fork()

tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorContinuation::test_prepends_nudge_on_retry
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1083: RuntimeWarning: tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorContinuation::test_prepends_nudge_on_retry changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorContinuation::test_does_not_double_prepend_on_repeated_retries
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1083: RuntimeWarning: tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorContinuation::test_does_not_double_prepend_on_repeated_retries changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19' to '<deleted>'; restored it.
    next(it)

tests/ace/tui/command_line/test_completion_fixes.py::test_cursor_move_during_a_fetch_drops_the_result
tests/ace/tui/command_line/test_panel_shell_pilot.py::test_real_input_history_filters_prefix_and_resets_new_walk
  /home/bryan/.local/share/uv/python/cpython-3.14.7-linux-x86_64-gnu/lib/python3.14/copy.py:201: RuntimeWarning: coroutine '_record_history_async.<locals>._record' was never awaited
    for key, value in x.items():
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorContinuation::test_prepends_nudge_on_zero_wait_retry
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1083: RuntimeWarning: tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorContinuation::test_prepends_nudge_on_zero_wait_retry changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorNoNudge::test_no_nudge_leaves_prompt_untouched
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1083: RuntimeWarning: tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorNoNudge::test_no_nudge_leaves_prompt_untouched changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorCodexDefaults::test_codex_transient_default_retries_with_preserved_workspace
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1083: RuntimeWarning: tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorCodexDefaults::test_codex_transient_default_retries_with_preserved_workspace changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorPostPhaseTransition::test_retry_fires_for_coder_after_plan_approval
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1083: RuntimeWarning: tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorPostPhaseTransition::test_retry_fires_for_coder_after_plan_approval changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry_usage_limits.py::TestHandleWorkflowErrorUsageLimitPrecedence::test_transient_429_not_a_usage_limit_match_still_retries
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1083: RuntimeWarning: tests/test_axe_run_agent_exec_retry_usage_limits.py::TestHandleWorkflowErrorUsageLimitPrecedence::test_transient_429_not_a_usage_limit_match_still_retries changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry_usage_limits.py::TestHandleWorkflowErrorUsageLimitPrecedence::test_fallback_allowed_to_different_non_disabled_provider
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1083: RuntimeWarning: tests/test_axe_run_agent_exec_retry_usage_limits.py::TestHandleWorkflowErrorUsageLimitPrecedence::test_fallback_allowed_to_different_non_disabled_provider changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry_usage_limits.py::TestHandleWorkflowErrorUsageLimitPrecedence::test_fallback_allowed_when_fallback_provider_carries_soft_disable
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1083: RuntimeWarning: tests/test_axe_run_agent_exec_retry_usage_limits.py::TestHandleWorkflowErrorUsageLimitPrecedence::test_fallback_allowed_when_fallback_provider_carries_soft_disable changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry_usage_limits.py::TestHandleWorkflowErrorUsageLimitPrecedence::test_known_codex_attempt_does_not_scan_quoted_claude_limit_prose
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1083: RuntimeWarning: tests/test_axe_run_agent_exec_retry_usage_limits.py::TestHandleWorkflowErrorUsageLimitPrecedence::test_known_codex_attempt_does_not_scan_quoted_claude_limit_prose changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry_workspace.py::TestHandleWorkflowErrorPreserveWorkspace::test_preserve_workspace_skips_prepare_on_retry
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1083: RuntimeWarning: tests/test_axe_run_agent_exec_retry_workspace.py::TestHandleWorkflowErrorPreserveWorkspace::test_preserve_workspace_skips_prepare_on_retry changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry_workspace.py::TestHandleWorkflowErrorPreserveWorkspace::test_preserve_workspace_skips_prepare_on_fallback
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1083: RuntimeWarning: tests/test_axe_run_agent_exec_retry_workspace.py::TestHandleWorkflowErrorPreserveWorkspace::test_preserve_workspace_skips_prepare_on_fallback changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry_workspace.py::TestHandleWorkflowErrorPreserveWorkspace::test_default_preserve_workspace_false_still_calls_prepare
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1083: RuntimeWarning: tests/test_axe_run_agent_exec_retry_workspace.py::TestHandleWorkflowErrorPreserveWorkspace::test_default_preserve_workspace_false_still_calls_prepare changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_failed_fork_admission.py::TestFailedForkParentAdmission::test_runner_admits_and_claims_real_workspace_for_failed_fork_parent
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1083: RuntimeWarning: tests/test_axe_run_agent_failed_fork_admission.py::TestFailedForkParentAdmission::test_runner_admits_and_claims_real_workspace_for_failed_fork_parent changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_runner_slot_only_deferred_wait_gates_then_claims_workspace[wait_info0-0-None]
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1083: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_runner_slot_only_deferred_wait_gates_then_claims_workspace[wait_info0-0-None] changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_runner_slot_only_deferred_wait_gates_then_claims_workspace[wait_info1-None-20]
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1083: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_runner_slot_only_deferred_wait_gates_then_claims_workspace[wait_info1-None-20] changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_deferred_wait_gates_before_claim_and_prepares_claimed_workspace[None]
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1083: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_deferred_wait_gates_before_claim_and_prepares_claimed_workspace[None] changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_deferred_wait_gates_before_claim_and_prepares_claimed_workspace[hostile ambient value]
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1083: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_deferred_wait_gates_before_claim_and_prepares_claimed_workspace[hostile ambient value] changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_incomplete_clan_fork_expands_after_wait_before_slot_and_claim
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1083: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_incomplete_clan_fork_expands_after_wait_before_slot_and_claim changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_combined_wait_runs_dependencies_then_gate_then_claim
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1083: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_combined_wait_runs_dependencies_then_gate_then_claim changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_home_mode_deferred_wait_keeps_directory_workspace
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1083: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_home_mode_deferred_wait_keeps_directory_workspace changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_outcomes.py::TestDeferredWorkspaceOutcomes::test_repeat_stop_exits_before_workspace_claim_and_run_loop
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1083: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_outcomes.py::TestDeferredWorkspaceOutcomes::test_repeat_stop_exits_before_workspace_claim_and_run_loop changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_outcomes.py::TestDeferredWorkspaceOutcomes::test_deferred_workspace_without_extracted_wait_still_claims_real_workspace
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1083: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_outcomes.py::TestDeferredWorkspaceOutcomes::test_deferred_workspace_without_extracted_wait_still_claims_real_workspace changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_outcomes.py::TestDeferredWorkspaceOutcomes::test_bead_claim_failure_writes_error_and_skips_model_execution
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1083: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_outcomes.py::TestDeferredWorkspaceOutcomes::test_bead_claim_failure_writes_error_and_skips_model_execution changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_outcomes.py::TestDeferredWorkspaceOutcomes::test_bead_environment_mismatch_writes_error_and_skips_model_execution
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1083: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_outcomes.py::TestDeferredWorkspaceOutcomes::test_bead_environment_mismatch_writes_error_and_skips_model_execution changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_outcomes.py::TestDeferredWorkspaceOutcomes::test_launch_without_bead_never_invokes_claim_helper
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1083: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_outcomes.py::TestDeferredWorkspaceOutcomes::test_launch_without_bead_never_invokes_claim_helper changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_no_retry_when_config_is_none
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1083: RuntimeWarning: tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_no_retry_when_config_is_none changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_non_retryable_error_raises_immediately
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1083: RuntimeWarning: tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_non_retryable_error_raises_immediately changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_retry_on_retryable_error
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1083: RuntimeWarning: tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_retry_on_retryable_error changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_retry_state_written_during_wait
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1083: RuntimeWarning: tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_retry_state_written_during_wait changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_retry_state_deleted_on_completion
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1083: RuntimeWarning: tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_retry_state_deleted_on_completion changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_fallback_model_tried_after_max_retries
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1083: RuntimeWarning: tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_fallback_model_tried_after_max_retries changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_was_killed_during_wait_aborts_retry
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1083: RuntimeWarning: tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_was_killed_during_wait_aborts_retry changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_done_json_includes_retry_metadata
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1083: RuntimeWarning: tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_done_json_includes_retry_metadata changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_no_retry_metadata_when_no_retries
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1083: RuntimeWarning: tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_no_retry_metadata_when_no_retries changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_cross_provider_retry_uses_fallback_config
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1083: RuntimeWarning: tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_cross_provider_retry_uses_fallback_config changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_agent_is_admitted_before_workspace_preparation
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1083: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_agent_is_admitted_before_workspace_preparation changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_admitted_root_is_counted_when_workspace_preparation_fails
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1083: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_admitted_root_is_counted_when_workspace_preparation_fails changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_no_wait_runner_records_run_started_at_before_execution
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1083: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_no_wait_runner_records_run_started_at_before_execution changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_runner_persists_sdd_base_sha_before_execution
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1083: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_runner_persists_sdd_base_sha_before_execution changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_runner_populates_multi_agent_prompt_file_from_env
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1083: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_runner_populates_multi_agent_prompt_file_from_env changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_error_after_slot_admission_records_run_started_at
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1083: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_error_after_slot_admission_records_run_started_at changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_linked_repo_prep_failure_stops_before_execution
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1083: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_linked_repo_prep_failure_stops_before_execution changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_killed_while_waiting_does_not_record_run_started_at
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1083: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_killed_while_waiting_does_not_record_run_started_at changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_runner_passes_recorded_run_started_at_to_runtime_formatter
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1083: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_runner_passes_recorded_run_started_at_to_runtime_formatter changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_system_exit_from_execution_writes_failure_marker_and_notifies
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1083: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_system_exit_from_execution_writes_failure_marker_and_notifies changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_home_mode_running_marker_cleanup_updates_artifact_index
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1083: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_home_mode_running_marker_cleanup_updates_artifact_index changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19' to '<deleted>'; restored it.
    next(it)

tests/test_axe_runner_workspace_reclone.py::TestRecreateEndToEnd::test_forced_verify_failure_recreates_then_launch_prep_succeeds
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1083: RuntimeWarning: tests/test_axe_runner_workspace_reclone.py::TestRecreateEndToEnd::test_forced_verify_failure_recreates_then_launch_prep_succeeds changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19' to '<deleted>'; restored it.
    next(it)

tests/test_notification_modal_tab_order.py::test_on_mount_highlights_first_visible_row_when_initial_is_hidden
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/src/sase/ace/tui/modals/notification_modal_snooze_status.py:136: RuntimeWarning: coroutine 'Timer._run_timer' was never awaited
    self._snooze_status_timer = None
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/ace/tui/command_line/test_panel_shell_pilot.py::test_grammar_ready_refreshes_open_empty_panel_without_a_keystroke
  /home/bryan/.local/share/uv/python/cpython-3.14.7-linux-x86_64-gnu/lib/python3.14/copy.py:201: RuntimeWarning: coroutine '_recheck_grammar_key' was never awaited
    for key, value in x.items():
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/ace/tui/command_line/test_panel_shell_submit.py::test_tail_polling_never_touches_message_pump
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/tests/ace/tui/command_line/test_panel_shell_submit.py:175: DeprecationWarning: 'asyncio.iscoroutinefunction' is deprecated and slated for removal in Python 3.16; use inspect.iscoroutinefunction() instead
    assert asyncio.iscoroutinefunction(CommandLineTranscript._tail_loop)

tests/footprint/test_tui.py::test_bump_resets_cached_state_after_fork
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/tests/footprint/test_tui.py:110: DeprecationWarning: This process (pid=4080206) is multi-threaded, use of fork() may lead to deadlocks in the child.
    child = os.fork()

tests/ace/tui/command_line/test_run_policies.py::test_foreground_submit_runs_in_terminal_and_records
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/textual/cache.py:226: RuntimeWarning: coroutine 'CommandLineScreenSubmissionMixin._record_local_history.<locals>._record' was never awaited
    def __init__(self, maxsize: int) -> None:
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/ace/tui/command_line/test_transcript_blocks_actions.py::test_v_opens_pager_for_selected_block
  /home/bryan/.local/share/uv/python/cpython-3.14.7-linux-x86_64-gnu/lib/python3.14/copy.py:189: RuntimeWarning: coroutine 'CommandLineScreenSubmissionMixin._submit_worker' was never awaited
    for k, j in zip(x, y):
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/ace/tui/command_line/test_transcript_blocks_actions.py::test_p_opens_procs_with_focus_target
  /home/bryan/.local/share/uv/python/cpython-3.14.7-linux-x86_64-gnu/lib/python3.14/json/decoder.py:361: RuntimeWarning: coroutine 'CommandLineScreen._load_tail_worker' was never awaited
    obj, end = self.scan_once(s, idx)
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/ace/tui/command_line/test_transcript_scroll.py::test_panel_opens_anchored_at_bottom
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/src/sase/main/parser_gettext.py:54: RuntimeWarning: coroutine 'CommandLineScreenSubmissionMixin._submit_worker' was never awaited
    tuple(os.environ.get(key) for key in _GETTEXT_ENV_KEYS)
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/test_run_agent_runner_clan_summary_refresh.py::test_successful_post_preparation_summary_survives_later_metadata_write
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1083: RuntimeWarning: tests/test_run_agent_runner_clan_summary_refresh.py::test_successful_post_preparation_summary_survives_later_metadata_write changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19' to '<deleted>'; restored it.
    next(it)

tests/test_run_agent_runner_clan_summary_refresh.py::test_unsuccessful_post_preparation_summary_keeps_earlier_success
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1083: RuntimeWarning: tests/test_run_agent_runner_clan_summary_refresh.py::test_unsuccessful_post_preparation_summary_keeps_earlier_success changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19' to '<deleted>'; restored it.
    next(it)

tests/agents_sync/test_publication_job.py::test_sigkilled_publisher_leaves_request_active_and_releases_locks
  /home/bryan/.local/share/uv/python/cpython-3.14.7-linux-x86_64-gnu/lib/python3.14/multiprocessing/popen_fork.py:76: DeprecationWarning: This process (pid=4080132) is multi-threaded, use of fork() may lead to deadlocks in the child.
    self.pid = os.fork()

tests/test_staged_reconcile_crashes.py::test_gate_publication_survives_process_death_before_outer_receipt
tests/test_staged_reconcile_crashes.py::test_monitor_submit_survives_process_death_and_scheduler_reuses_proc
  /home/bryan/.local/share/uv/python/cpython-3.14.7-linux-x86_64-gnu/lib/python3.14/multiprocessing/popen_fork.py:76: DeprecationWarning: This process (pid=4080313) is multi-threaded, use of fork() may lead to deadlocks in the child.
    self.pid = os.fork()

tests/history/test_continuation_replay_hydration_retry.py::test_retry_then_fork_replay_end_to_end
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1083: RuntimeWarning: tests/history/test_continuation_replay_hydration_retry.py::test_retry_then_fork_replay_end_to_end changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19' to '<deleted>'; restored it.
    next(it)

tests/ace/tui/test_agent_archive_column_actions_interaction.py::test_J_and_K_switch_pulse_and_list_focus_without_moving_the_inbox
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/tests/ace/tui/_agent_archive_column_helpers.py:78: RuntimeWarning: coroutine 'AgentMetadataPagerMixin._open_agent_metadata_pager' was never awaited
    by_container.setdefault(row["container_key"], []).append(row)
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/ace/tui/test_agent_archive_column_actions_interaction.py::test_cursor_survives_a_rebuild_and_falls_to_a_neighbor_when_row_vanishes
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/tests/ace/tui/_agent_archive_column_helpers.py:78: RuntimeWarning: coroutine 'open_archive_chooser.<locals>._hydrate_and_present' was never awaited
    by_container.setdefault(row["container_key"], []).append(row)
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/completion/test_zsh_smoke.py: 18 warnings
  /home/bryan/.local/share/uv/python/cpython-3.14.7-linux-x86_64-gnu/lib/python3.14/pty.py:66: DeprecationWarning: This process (pid=4080209) is multi-threaded, use of forkpty() may lead to deadlocks in the child.
    pid, fd = os.forkpty()

tests/ace/tui/test_dismissed_index_startup_sync.py::test_start_post_mount_background_loads_schedules_dismissed_sync_once
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/src/sase/ace/tui/actions/_launchable_mru.py:304: RuntimeWarning: coroutine 'Timer._run_timer' was never awaited
    log.debug("Launchable MRU tick not armed", exc_info=True)
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/axe/test_run_agent_exec_attempts_integration.py::test_retry_branch_snapshots_failed_attempt
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1083: RuntimeWarning: tests/axe/test_run_agent_exec_attempts_integration.py::test_retry_branch_snapshots_failed_attempt changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19' to '<deleted>'; restored it.
    next(it)

tests/axe/test_run_agent_exec_attempts_integration.py::test_retry_branch_releases_attempt_continuation_pointers
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1083: RuntimeWarning: tests/axe/test_run_agent_exec_attempts_integration.py::test_retry_branch_releases_attempt_continuation_pointers changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19' to '<deleted>'; restored it.
    next(it)

tests/axe/test_run_agent_exec_attempts_integration.py::test_fallback_branch_releases_attempt_continuation_pointers
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1083: RuntimeWarning: tests/axe/test_run_agent_exec_attempts_integration.py::test_fallback_branch_releases_attempt_continuation_pointers changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19' to '<deleted>'; restored it.
    next(it)

tests/axe/test_run_agent_exec_attempts_integration.py::test_fallback_branch_snapshots_with_primary_model_marker
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1083: RuntimeWarning: tests/axe/test_run_agent_exec_attempts_integration.py::test_fallback_branch_snapshots_with_primary_model_marker changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19' to '<deleted>'; restored it.
    next(it)

-- Docs: https://docs.pytest.org/en/stable/how-to/capture-warnings.html
============================= system temp leakage ==============================
The test suite left new entries in a watched temp directory:
  /var/tmp/sase-ad89b80b (24 new):
    - sase-join-artifacts-0n_8yoim
    - sase-join-artifacts-0v7db_3s
    - sase-join-artifacts-1e8bwczl
    - sase-join-artifacts-1eyqh3i_
    - sase-join-artifacts-1i25axdg
    - sase-join-artifacts-5cujlavy
    - sase-join-artifacts-8fcpm6pf
    - sase-join-artifacts-_fey29qx
    - sase-join-artifacts-auquitz2
    - sase-join-artifacts-c_p23ahp
    - sase-join-artifacts-d52um19j
    - sase-join-artifacts-djjatg6y
    - sase-join-artifacts-dn4urjpt
    - sase-join-artifacts-dw1aao3f
    - sase-join-artifacts-irnw3m5f
    - sase-join-artifacts-l_tp2fa9
    - sase-join-artifacts-lskjxu2g
    - sase-join-artifacts-m0gsdsv5
    - sase-join-artifacts-mg__ky3b
    - sase-join-artifacts-nyqk5mff
    ... and 4 more
Route temporary files through pytest's tmp_path/tmp_path_factory, or pass an explicit dir= so sase's sibling files are collected with them. Entries under the managed SASE temp root mean something bypassed get_sase_managed_tmpdir(), which sandboxes itself under pytest.
Set SASE_TMP_LEAK_GUARD_DISABLED=1 to bypass this guard while debugging.
============================= slowest 20 durations =============================
134.99s call     tests/tool/test_nested_stage_recording.py::test_child_pytest_of_a_stageless_run_records_no_stage_rows
85.17s call     tests/test_check_feature_flags_tool_run.py::test_main_static_on_repo_exits_zero
75.18s call     tests/history/test_continuation_replay_hydration_basic.py::test_hundred_handoff_from_final_monitor_result_grows_linearly
74.99s call     tests/test_contract_manifest.py::test_contract_manifest_matches_marker_selection
66.53s call     tests/workspace_provider/test_primary_writable_store_import_boundary.py::test_writable_store_resolution_importers_match_the_audited_allowlist
64.89s call     tests/test_launch_request_staging.py::test_typed_plan_and_continuation_survive_adoption
63.46s call     tests/tool/test_settlement_retention.py::test_total_timeout_settles_signaled_timeout
55.35s call     tests/test_check_feature_flags_tool_run.py::test_static_main_ignores_exploding_bd_command
53.96s call     tests/ace/tui/test_plugins_browser_pane_sase_update_dev.py::test_updates_pane_sase_update_dev_confirm_closes_admin_center
40.12s call     tests/test_agent_artifact_directory_operation_audit.py::test_artifact_directory_operation_sites_are_reviewed
31.77s call     tests/test_hypothesis_property.py::TestParseSuffixPrefix::test_no_prefix_passthrough
30.60s call     tests/pager/test_app_navigation.py::test_question_mark_opens_and_closes_the_help_screen
27.47s call     tests/pager/test_rendered_link_contract.py::test_kitchen_follow_copy_edit_and_media_for_each_supported_action
27.35s call     tests/ace/tui/test_deleted_proc_queue_imports.py::test_tests_do_not_import_deleted_proc_queue_module
25.67s call     tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_lowercase_picks_this_panel_capital_picks_other
24.09s call     tests/test_bead/test_sync_remote_worker.py::test_managed_sync_worker_converges_sidecar_store_mutations
23.35s call     tests/feature_flags/test_host_config_safety.py::test_config_seed_tests_do_not_snapshot_config_dir_at_module_scope
20.82s call     tests/test_project_display_presentation_audit.py::test_display_fallback_exemptions_name_existing_sites_and_rationales
20.30s call     tests/test_project_display_presentation_audit.py::test_project_display_name_fallback_lives_only_in_chokepoint
19.15s call     tests/test_gemini_active_surface_guard.py::test_no_gemini_cli_provider_surface_in_active_tree
=========================== short test summary info ============================
FAILED tests/test_stranded_work_facade.py::test_reduce_stranded_work_round_trips_through_real_binding - AssertionError: assert 2 == 1
 +  where 2 = StrandedWorkReport(schema_version=2, verdicts=(StrandedWorkVerdict(bead_id='sase-1.2', kind='phase', state='stranded',..._action='keep', since=2.0, parent_id='sase-1', blocked_by=(), blocks=()),), stranded_ids=('sase-1.2',), blocked_ids=()).schema_version
FAILED tests/test_pending_actions.py::test_transport_adapter_preserves_handled_state_and_original_lifecycle - KeyError: 'abcd1234'
FAILED tests/tool/test_settlement_retention.py::test_total_timeout_settles_signaled_timeout - Failed: run bc3d0e2f0acd272fa4accc1ef6f9cb05 did not settle
==== 3 failed, 59656 passed, 18 skipped, 158 warnings in 1027.31s (0:17:07) ====
error: recipe `test-scoped` failed on line 651 with exit code 1
error: recipe `check` failed on line 917 with exit code 1
failed  exit=1  duration=2492489ms
unattrib  19m 19s
triage test (scoped): 2 KNOWN 1 NEW stopped
NEW test (scoped): FAILED tests/tool/test_settlement_retention.py::test_total_timeout_settles_signaled_timeout - Failed: run <hex> did not settle — recorded evidence; no owner
KNOWN test (scoped): FAILED tests/test_pending_actions.py::test_transport_adapter_preserves_handled_state_and_original_lifecycle - KeyError: 'abcd1234' — witness 4062c1f3bb6b5a9d84097982381aef9f; no owner
KNOWN test (scoped): FAILED tests/test_stranded_work_facade.py::test_reduce_stranded_work_round_trips_through_real_binding - AssertionError: assert 2 == 1 — witness 4062c1f3bb6b5a9d84097982381aef9f; no owner
verdict: new_failures — 1 NEW, 2 KNOWN; exit 1

