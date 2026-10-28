# Chat History - ace-run (sase-1p1.12--mon-1)

- **TIMESTAMP:** 2026-10-28 04:03:14 EDT
- **MODEL:** grok/grok-4.6
- **AGENT:** sase-1p1.12--mon-1

## Prompt

sase monitor start --command 'just check' --reason 'Verify Footprint export/import before host completion'

## Response

sase tool run 2f2e7efbed313b3f144f84012045418e
[validate_sase_core_rs_version] sase-core checkout is ahead of sase's compatibility window: source version 0.43.0 from /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/sase/repos/linked/sase-core/Cargo.toml does not satisfy `sase`'s `sase-core-rs==0.42.7` dependency in pyproject.toml. No action is needed: editable installs build from the checkout regardless, and `tools/ratchet_core_pin` moves the published pin on the release branch at release time.
[core-source] linked sase-core source changed since the extension was built; flagging an extension rebuild.
[setup] Note: the sase-core checkout is ahead of the published sase-core-rs pin in pyproject.toml; dev installs build from /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/sase/repos/linked/sase-core regardless. This is normal — the release-branch reconciler ratchets the published pin at release time, so no action is needed here.
[setup] Rebuilding sase_core_rs: linked sase-core source changed since the extension was built.
[validate_sase_core_rs_version] sase-core checkout is ahead of sase's compatibility window: source version 0.43.0 from /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/sase/repos/linked/sase-core/Cargo.toml does not satisfy `sase`'s `sase-core-rs==0.42.7` dependency in pyproject.toml. No action is needed: editable installs build from the checkout regardless, and `tools/ratchet_core_pin` moves the published pin on the release branch at release time.
[rust-install] Note: the sase-core checkout is ahead of the published sase-core-rs pin in pyproject.toml; dev builds from /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/sase/repos/linked/sase-core ignore it. This is normal — the release-branch reconciler ratchets the published pin at release time, so no action is needed here.
# Harden cargo crate downloads against transient crates.io flakiness.
# CI has hit `curl ... [16] Error in the HTTP2 framing layer` while
# maturin's `cargo metadata` fetches deps; disabling HTTP/2 multiplexing
# and raising the retry count makes the download resilient. Both are
# overridable from the environment.
# Capture the source identity after the checkout refresh above and before
# the build below. It is written to the venv only after a successful
# install (wheel-cache hit or `maturin develop` alike), so an edit made
# during the build still reads as stale on the next check.
[sase-core-wheel-cache] miss: sase-core checkout is dirty
[sase-core-wheel-cache] miss: sase-core checkout is dirty
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
   Compiling stable_deref_trait v1.2.1
   Compiling futures-sink v0.3.32
   Compiling crossbeam-deque v0.8.8
   Compiling target-lexicon v0.12.16
   Compiling hashbrown v0.17.0
   Compiling equivalent v1.0.2
   Compiling futures-io v0.3.32
   Compiling futures-task v0.3.32
   Compiling tower-service v0.3.3
   Compiling ucd-trie v0.1.7
   Compiling iana-time-zone v0.1.65
   Compiling slab v0.4.12
   Compiling bitflags v2.11.1
   Compiling untrusted v0.9.0
   Compiling libm v0.2.16
   Compiling same-file v1.0.6
   Compiling litemap v0.8.2
   Compiling heck v0.5.0
   Compiling httparse v1.10.1
   Compiling writeable v0.6.3
   Compiling icu_normalizer_data v2.2.0
   Compiling utf8_iter v1.0.4
   Compiling icu_properties_data v2.2.0
   Compiling typenum v1.20.0
   Compiling lazy_static v1.5.0
   Compiling tower-layer v0.3.3
   Compiling fnv v1.0.7
   Compiling deunicode v1.6.2
   Compiling parking_lot_core v0.9.12
    Building [                           ] 0/398: proc-macro2(build.rs), itoa…    Building [                           ] 2/398: proc-macro2(build.rs), itoa…    Building [                          ] 10/398: itoa, serde_core(build), fi…    Building [                          ] 13/398: itoa, serde_core(build), fi…    Building [                          ] 14/398: itoa, find-msvc-tools, lite…    Building [>                         ] 17/398: itoa, find-msvc-tools, lite…    Building [>                         ] 18/398: itoa, find-msvc-tools, lite…    Building [>                         ] 20/398: itoa, find-msvc-tools, lite…    Building [>                         ] 21/398: itoa, find-msvc-tools, lite…    Building [>                         ] 22/398: itoa, find-msvc-tools, lite…    Building [>                         ] 23/398: itoa, find-msvc-tools, lite…    Building [>                         ] 24/398: itoa, find-msvc-tools, lite…    Building [>                         ] 25/398: itoa, zmij(build), find-msv…    Building [>                         ] 26/398: itoa, find-msvc-tools, lite…    Building [>                         ] 27/398: itoa, find-msvc-tools, lite…    Building [>                         ] 28/398: itoa, find-msvc-tools, lite…    Building [>                         ] 29/398: itoa, find-msvc-tools, lite…   Compiling httpdate v1.0.3
    Building [>                         ] 30/398: itoa, find-msvc-tools, lite…    Building [=>                        ] 31/398: itoa, find-msvc-tools, lite…    Building [=>                        ] 32/398: itoa, find-msvc-tools, lite…   Compiling encoding_rs v0.8.35
    Building [=>                        ] 33/398: itoa, find-msvc-tools, lite…    Building [=>                        ] 34/398: itoa, find-msvc-tools, lite…    Building [=>                        ] 35/398: itoa, find-msvc-tools, lite…   Compiling ryu v1.0.23
    Building [=>                        ] 36/398: itoa, find-msvc-tools, lite…   Compiling clap_lex v1.1.1
    Building [=>                        ] 37/398: itoa, find-msvc-tools, lite…    Building [=>                        ] 38/398: itoa, find-msvc-tools, lite…    Building [=>                        ] 39/398: itoa, find-msvc-tools, lite…   Compiling unicode-segmentation v1.13.3
    Building [=>                        ] 41/398: itoa, find-msvc-tools, lite…    Building [=>                        ] 42/398: itoa, find-msvc-tools, lite…    Building [=>                        ] 43/398: itoa, find-msvc-tools, lite…   Compiling tracing-core v0.1.36
    Building [=>                        ] 44/398: itoa, find-msvc-tools, lite…   Compiling cc v1.2.61
    Building [=>                        ] 45/398: itoa, find-msvc-tools, lite…    Building [==>                       ] 46/398: itoa, find-msvc-tools, lite…    Building [==>                       ] 47/398: itoa, find-msvc-tools, lite…    Building [==>                       ] 48/398: itoa, litemap, zerocopy, it…    Building [==>                       ] 49/398: itoa, litemap, zerocopy, cl…   Compiling rustls v0.21.12
    Building [==>                       ] 50/398: itoa, rustls(build.rs), lit…   Compiling num-traits v0.2.19
    Building [==>                       ] 51/398: itoa, rustls(build.rs), lit…   Compiling thiserror v1.0.69
    Building [==>                       ] 52/398: itoa, litemap, zerocopy, cl…    Building [==>                       ] 53/398: itoa, litemap, zerocopy, cl…   Compiling aho-corasick v1.1.4
    Building [==>                       ] 54/398: itoa, litemap, zerocopy, cl…    Building [==>                       ] 55/398: itoa, litemap, zerocopy, cl…   Compiling bstr v1.13.1
    Building [==>                       ] 56/398: itoa, litemap, zerocopy, bs…    Building [==>                       ] 57/398: itoa, litemap, zerocopy, bs…    Building [==>                       ] 58/398: itoa, litemap, zerocopy, bs…   Compiling http v1.4.0
    Building [==>                       ] 59/398: itoa, litemap, zerocopy, bs…   Compiling http v0.2.12
    Building [==>                       ] 60/398: litemap, zerocopy, bstr, cl…    Building [==>                       ] 61/398: litemap, zerocopy, bstr, cl…    Building [===>                      ] 62/398: litemap, zerocopy, bstr, cl…   Compiling rayon-core v1.13.0
    Building [===>                      ] 63/398: litemap, zerocopy, bstr, cl…   Compiling either v1.19.0
    Building [===>                      ] 64/398: litemap, zerocopy, bstr, cl…   Compiling walkdir v2.5.0
    Building [===>                      ] 65/398: litemap, zerocopy, bstr, cl…   Compiling pkg-config v0.3.33
    Building [===>                      ] 66/398: litemap, zerocopy, bstr, cl…   Compiling anstyle v1.0.14
   Compiling percent-encoding v2.3.2
   Compiling vcpkg v0.2.15
    Building [===>                      ] 70/398: vcpkg, litemap, zerocopy, b…   Compiling phf_shared v0.11.3
    Building [===>                      ] 71/398: vcpkg, litemap, zerocopy, b…   Compiling scopeguard v1.2.0
    Building [===>                      ] 72/398: vcpkg, litemap, zerocopy, b…   Compiling sync_wrapper v1.0.2
    Building [===>                      ] 74/398: vcpkg, litemap, zerocopy, b…    Building [===>                      ] 76/398: vcpkg, litemap, rayon-core(…   Compiling powerfmt v0.2.0
    Building [====>                     ] 77/398: vcpkg, litemap, zerocopy, b…   Compiling time-core v0.1.8
    Building [====>                     ] 78/398: vcpkg, zerocopy, bstr, clap…   Compiling thiserror v2.0.18
    Building [====>                     ] 79/398: vcpkg, zerocopy, bstr, clap…   Compiling winnow v1.0.4
    Building [====>                     ] 80/398: vcpkg, zerocopy, bstr, clap…   Compiling rustversion v1.0.22
    Building [====>                     ] 81/398: vcpkg, zerocopy, bstr, clap…   Compiling getrandom v0.4.2
    Building [====>                     ] 82/398: vcpkg, zerocopy, bstr, clap…   Compiling slug v0.1.6
    Building [====>                     ] 83/398: vcpkg, zerocopy, bstr, clap…   Compiling futures-channel v0.3.32
    Building [====>                     ] 84/398: vcpkg, zerocopy, bstr, clap…    Building [====>                     ] 85/398: vcpkg, zerocopy, bstr, clap…   Compiling num-conv v0.2.1
    Building [====>                     ] 86/398: vcpkg, zerocopy, bstr, clap…    Building [====>                     ] 87/398: vcpkg, zerocopy, bstr, clap…   Compiling try-lock v0.2.5
    Building [====>                     ] 88/398: try-lock, vcpkg, zerocopy, …   Compiling rustix v1.1.4
    Building [====>                     ] 89/398: try-lock, vcpkg, zerocopy, …   Compiling colored v2.2.0
    Building [====>                     ] 90/398: try-lock, vcpkg, zerocopy, …    Building [====>                     ] 91/398: try-lock, vcpkg, zerocopy, …   Compiling grep-matcher v0.1.9
    Building [=====>                    ] 92/398: try-lock, vcpkg, zerocopy, …   Compiling winnow v0.7.15
    Building [=====>                    ] 93/398: try-lock, vcpkg, zerocopy, …    Building [=====>                    ] 94/398: try-lock, vcpkg, thiserror(…   Compiling linux-raw-sys v0.12.1
    Building [=====>                    ] 96/398: try-lock, vcpkg, thiserror(…   Compiling indexmap v2.14.0
    Building [=====>                    ] 97/398: try-lock, vcpkg, thiserror(…    Building [=====>                    ] 98/398: try-lock, vcpkg, thiserror(…   Compiling cpufeatures v0.2.17
    Building [=====>                    ] 99/398: try-lock, vcpkg, thiserror(…   Compiling mime v0.3.17
    Building [=====>                   ] 100/398: try-lock, vcpkg, thiserror(…    Building [=====>                   ] 101/398: try-lock, vcpkg, thiserror(…    Building [=====>                   ] 102/398: try-lock, vcpkg, thiserror(…   Compiling pyo3-build-config v0.22.6
    Building [=====>                   ] 103/398: try-lock, vcpkg, thiserror(…   Compiling toml_writer v1.1.3+spec-1.1.0
    Building [=====>                   ] 104/398: try-lock, vcpkg, thiserror(…   Compiling home v0.5.12
    Building [=====>                   ] 105/398: try-lock, vcpkg, thiserror(…   Compiling atomic-waker v1.1.2
    Building [=====>                   ] 106/398: try-lock, vcpkg, thiserror(…   Compiling itertools v0.11.0
    Building [=====>                   ] 107/398: try-lock, vcpkg, thiserror(…    Building [=====>                   ] 108/398: try-lock, vcpkg, thiserror(…   Compiling ahash v0.8.12
    Building [=====>                   ] 109/398: try-lock, vcpkg, thiserror(…   Compiling generic-array v0.14.7
    Building [=====>                   ] 110/398: try-lock, vcpkg, thiserror(…    Building [=====>                   ] 111/398: try-lock, vcpkg, thiserror(…    Building [======>                  ] 112/398: try-lock, vcpkg, thiserror(…    Building [======>                  ] 113/398: try-lock, vcpkg, ahash(buil…    Building [======>                  ] 114/398: try-lock, vcpkg, thiserror(…    Building [======>                  ] 115/398: try-lock, vcpkg, thiserror(…   Compiling crossbeam-channel v0.5.17
   Compiling memoffset v0.9.1
    Building [======>                  ] 117/398: try-lock, vcpkg, thiserror(…    Building [======>                  ] 118/398: try-lock, vcpkg, thiserror(…   Compiling base64 v0.21.7
    Building [======>                  ] 119/398: try-lock, vcpkg, thiserror(…    Building [======>                  ] 120/398: try-lock, vcpkg, thiserror(…   Compiling clap_builder v4.6.7
    Building [======>                  ] 121/398: try-lock, vcpkg, thiserror(…    Building [======>                  ] 122/398: try-lock, vcpkg, thiserror(…   Compiling deranged v0.5.8
    Building [======>                  ] 123/398: try-lock, vcpkg, thiserror(…   Compiling fallible-streaming-iterator v0.1.9
    Building [======>                  ] 124/398: try-lock, vcpkg, thiserror(…    Building [======>                  ] 125/398: try-lock, vcpkg, thiserror(…   Compiling tinyvec v1.13.3
    Building [======>                  ] 126/398: try-lock, vcpkg, thiserror(…   Compiling unsafe-libyaml v0.2.11
    Building [======>                  ] 127/398: try-lock, vcpkg, thiserror(…   Compiling base64 v0.22.1
    Building [=======>                 ] 128/398: try-lock, vcpkg, thiserror(…   Compiling humansize v2.1.3
    Building [=======>                 ] 129/398: try-lock, vcpkg, thiserror(…   Compiling errno v0.3.14
    Building [=======>                 ] 130/398: try-lock, vcpkg, thiserror(…   Compiling socket2 v0.6.3
    Building [=======>                 ] 131/398: try-lock, vcpkg, thiserror(…   Compiling phf v0.11.3
    Building [=======>                 ] 132/398: try-lock, phf, vcpkg, thise…   Compiling psm v0.1.24
    Building [=======>                 ] 133/398: try-lock, phf, vcpkg, thise…   Compiling mio v1.2.0
    Building [=======>                 ] 134/398: try-lock, phf, thiserror(bu…   Compiling getrandom v0.2.17
    Building [=======>                 ] 135/398: phf, thiserror(build), base…   Compiling stacker v0.1.25
    Building [=======>                 ] 136/398: phf, thiserror(build), base…    Building [=======>                 ] 137/398: phf, thiserror(build), base…   Compiling ring v0.17.14
    Building [=======>                 ] 138/398: phf, thiserror(build), ring…    Building [=======>                 ] 139/398: phf, thiserror(build), ring…    Building [=======>                 ] 140/398: phf, thiserror(build), ring…    Building [=======>                 ] 141/398: phf, thiserror(build), ring…   Compiling form_urlencoded v1.2.2
    Building [=======>                 ] 142/398: phf, thiserror(build), ring…   Compiling libsqlite3-sys v0.30.1
    Building [=======>                 ] 143/398: phf, thiserror(build), ring…   Compiling lock_api v0.4.14
    Building [========>                ] 144/398: phf, thiserror(build), ring…   Compiling want v0.3.1
    Building [========>                ] 145/398: phf, thiserror(build), ring…   Compiling memmap2 v0.9.11
    Building [========>                ] 146/398: phf, thiserror(build), ring…    Building [========>                ] 147/398: phf, thiserror(build), base…    Building [========>                ] 148/398: phf, thiserror(build), base…   Compiling socket2 v0.5.10
    Building [========>                ] 149/398: phf, thiserror(build), base…    Building [========>                ] 150/398: phf, thiserror(build), base…   Compiling regex-automata v0.4.14
    Building [========>                ] 151/398: phf, thiserror(build), base…   Compiling term_size v0.3.2
    Building [========>                ] 152/398: phf, thiserror(build), base…    Building [========>                ] 153/398: phf, thiserror(build), base…    Building [========>                ] 154/398: phf, base64, zerocopy, mime…   Compiling fastrand v2.4.1
    Building [========>                ] 155/398: phf, base64, zerocopy, mime…   Compiling toml_parser v1.1.5+spec-1.1.0
    Building [========>                ] 156/398: phf, base64, zerocopy, mime…   Compiling fallible-iterator v0.3.0
    Building [========>                ] 157/398: phf, fallible-iterator, bas…   Compiling num-integer v0.1.46
    Building [========>                ] 158/398: phf, fallible-iterator, bas…    Building [========>                ] 159/398: phf, fallible-iterator, bas…   Compiling http-body v1.0.1
    Building [=========>               ] 160/398: phf, fallible-iterator, bas…   Compiling encoding_rs_io v0.1.8
    Building [=========>               ] 161/398: phf, fallible-iterator, bas…   Compiling serde_spanned v1.1.2
    Building [=========>               ] 162/398: phf, fallible-iterator, bas…   Compiling chrono v0.4.44
    Building [=========>               ] 163/398: phf, fallible-iterator, bas…    Building [=========>               ] 164/398: phf, fallible-iterator, bas…   Compiling toml_datetime v0.7.5+spec-1.1.0
    Building [=========>               ] 165/398: phf, fallible-iterator, bas…   Compiling time-macros v0.2.27
    Building [=========>               ] 166/398: phf, fallible-iterator, bas…    Building [=========>               ] 167/398: phf, fallible-iterator, bas…   Compiling serde_path_to_error v0.1.20
    Building [=========>               ] 168/398: phf, fallible-iterator, bas…   Compiling etcetera v0.8.0
    Building [=========>               ] 169/398: phf, fallible-iterator, bas…    Building [=========>               ] 170/398: phf, fallible-iterator, bas…   Compiling fs2 v0.4.3
    Building [=========>               ] 171/398: phf, fallible-iterator, bas…   Compiling tracing-log v0.2.0
   Compiling sharded-slab v0.1.7
    Building [=========>               ] 173/398: phf, fallible-iterator, bas…   Compiling http-body v0.4.6
    Building [=========>               ] 174/398: phf, fallible-iterator, bas…   Compiling thread_local v1.1.9
    Building [=========>               ] 175/398: phf, fallible-iterator, bas…    Building [==========>              ] 176/398: phf, chrono, fallible-itera…   Compiling nu-ansi-term v0.50.3
    Building [==========>              ] 177/398: phf, chrono, fallible-itera…   Compiling hex v0.4.3
    Building [==========>              ] 179/398: phf, chrono, fallible-itera…   Compiling semver v1.0.28
    Building [==========>              ] 180/398: phf, chrono, fallible-itera…   Compiling matchit v0.7.3
    Building [==========>              ] 181/398: phf, chrono, fallible-itera…   Compiling unicode-width v0.2.2
    Building [==========>              ] 182/398: phf, chrono, fallible-itera…    Building [==========>              ] 183/398: phf, chrono, fallible-itera…   Compiling ipnet v2.12.0
    Building [==========>              ] 184/398: phf, chrono, fallible-itera…   Compiling unicode-casefold v0.2.0
    Building [==========>              ] 185/398: phf, chrono, fallible-itera…   Compiling sync_wrapper v0.1.2
    Building [==========>              ] 186/398: phf, chrono, fallible-itera…   Compiling webpki-roots v0.25.4
    Building [==========>              ] 187/398: phf, chrono, fallible-itera…    Building [==========>              ] 188/398: phf, chrono, fallible-itera…   Compiling pem v3.0.6
    Building [==========>              ] 189/398: phf, chrono, fallible-itera…   Compiling signal-hook-registry v1.4.8
    Building [==========>              ] 190/398: phf, chrono, fallible-itera…   Compiling pyo3-ffi v0.22.6
    Building [==========>              ] 191/398: phf, chrono, fallible-itera…    Building [===========>             ] 192/398: phf, chrono, fallible-itera…   Compiling pyo3-macros-backend v0.22.6
    Building [===========>             ] 193/398: phf, chrono, fallible-itera…   Compiling unicode-normalization v0.1.25
    Building [===========>             ] 194/398: phf, chrono, fallible-itera…    Building [===========>             ] 195/398: pyo3-ffi(build), phf, chron…   Compiling rustls-pemfile v1.0.4
    Building [===========>             ] 196/398: phf, chrono, fallible-itera…   Compiling pyo3 v0.22.6
    Building [===========>             ] 197/398: phf, chrono, fallible-itera…   Compiling block-buffer v0.10.4
    Building [===========>             ] 198/398: phf, chrono, fallible-itera…   Compiling crypto-common v0.1.7
    Building [===========>             ] 199/398: chrono, fallible-iterator, …    Building [===========>             ] 200/398: chrono, fallible-iterator, …   Compiling indoc v2.0.7
    Building [===========>             ] 201/398: chrono, fallible-iterator, …    Building [===========>             ] 202/398: chrono, fallible-iterator, …    Building [===========>             ] 203/398: chrono, fallible-iterator, …   Compiling unindent v0.2.4
    Building [===========>             ] 204/398: chrono, fallible-iterator, …    Building [===========>             ] 205/398: chrono, fallible-iterator, …    Building [===========>             ] 206/398: chrono, fallible-iterator, …    Building [============>            ] 207/398: chrono, fallible-iterator, …    Building [============>            ] 208/398: chrono, fallible-iterator, …    Building [============>            ] 209/398: chrono, fallible-iterator, …    Building [============>            ] 210/398: chrono, fallible-iterator, …    Building [============>            ] 211/398: chrono, fallible-iterator, …    Building [============>            ] 212/398: chrono, fallible-iterator, …    Building [============>            ] 213/398: chrono, fallible-iterator, …   Compiling num-bigint v0.4.6
    Building [============>            ] 214/398: chrono, fallible-iterator, …    Building [============>            ] 215/398: chrono, fallible-iterator, …    Building [============>            ] 216/398: chrono, fallible-iterator, …   Compiling rand_core v0.6.4
    Building [============>            ] 217/398: chrono, fallible-iterator, …    Building [============>            ] 218/398: chrono, fallible-iterator, …   Compiling ppv-lite86 v0.2.21
   Compiling grep-searcher v0.1.17
    Building [============>            ] 220/398: chrono, fallible-iterator, …    Building [============>            ] 221/398: chrono, fallible-iterator, …   Compiling http-body-util v0.1.3
    Building [============>            ] 222/398: chrono, fallible-iterator, …    Building [=============>           ] 223/398: chrono, fallible-iterator, …   Compiling parking_lot v0.12.5
    Building [=============>           ] 224/398: chrono, fallible-iterator, …    Building [=============>           ] 225/398: chrono, fallible-iterator, …    Building [=============>           ] 226/398: chrono, fallible-iterator, …    Building [=============>           ] 227/398: chrono, fallible-iterator, …    Building [=============>           ] 228/398: chrono, fallible-iterator, …    Building [=============>           ] 230/398: chrono, fallible-iterator, …    Building [=============>           ] 231/398: chrono, fallible-iterator, …    Building [=============>           ] 232/398: chrono, unicode-width, chro…    Building [=============>           ] 233/398: chrono, unicode-width, chro…    Building [=============>           ] 234/398: chrono, unicode-width, chro…    Building [=============>           ] 235/398: chrono, unicode-width, chro…    Building [=============>           ] 236/398: chrono, unicode-width, chro…    Building [=============>           ] 237/398: chrono, unicode-width, chro…    Building [=============>           ] 238/398: chrono, unicode-width, chro…    Building [==============>          ] 239/398: chrono, unicode-width, chro…    Building [==============>          ] 240/398: chrono, unicode-width, chro…   Compiling toml v0.9.12+spec-1.1.0
    Building [==============>          ] 241/398: chrono, unicode-width, chro…    Building [==============>          ] 242/398: chrono, unicode-width, chro…    Building [==============>          ] 243/398: chrono, unicode-width, chro…    Building [==============>          ] 244/398: chrono, unicode-width, chro…    Building [==============>          ] 245/398: chrono, unicode-width, chro…    Building [==============>          ] 246/398: chrono, unicode-width, chro…    Building [==============>          ] 247/398: chrono, unicode-width, chro…    Building [==============>          ] 248/398: chrono, chrono, rand_core, …    Building [==============>          ] 249/398: chrono, chrono, rand_core, …    Building [==============>          ] 251/398: chrono, chrono, rand_core, …   Compiling digest v0.10.7
    Building [==============>          ] 252/398: chrono, chrono, rand_core, …    Building [==============>          ] 253/398: chrono, rand_core, rand_cor…    Building [==============>          ] 254/398: chrono, rand_core, rand_cor…    Building [===============>         ] 255/398: chrono, rand_core, unicode-…    Building [===============>         ] 256/398: chrono, rand_core, unicode-…    Building [===============>         ] 257/398: chrono, rand_core, pyo3-ffi…    Building [===============>         ] 258/398: chrono, rand_core, pyo3-ffi…    Building [===============>         ] 259/398: chrono, rand_core, pyo3-ffi…   Compiling pest v2.9.4
   Compiling time v0.3.47
    Building [===============>         ] 259/398: chrono, rand_core, time, py…    Building [===============>         ] 260/398: chrono, rand_core, time, py…    Building [===============>         ] 261/398: chrono, rand_core, time, py…   Compiling rand_chacha v0.3.1
    Building [===============>         ] 261/398: chrono, rand_chacha, rand_c…    Building [===============>         ] 263/398: chrono, rand_chacha, time, …    Building [===============>         ] 264/398: chrono, rand_chacha, time, …    Building [===============>         ] 265/398: chrono, rand_chacha, time, …    Building [===============>         ] 267/398: chrono, rand_chacha, time, …    Building [===============>         ] 268/398: chrono, rand_chacha, time, …   Compiling regex v1.12.3
   Compiling globset v0.4.19
   Compiling tempfile v3.27.0
    Building [===============>         ] 269/398: chrono, rand_chacha, time, …    Building [===============>         ] 270/398: chrono, rand_chacha, time, …    Building [================>        ] 271/398: chrono, rand_chacha, time, …   Compiling sha1 v0.10.7
   Compiling sha2 v0.10.9
    Building [================>        ] 271/398: chrono, rand_chacha, sha2, …    Building [================>        ] 272/398: chrono, rand_chacha, sha2, …    Building [================>        ] 273/398: chrono, rand_chacha, sha2, …   Compiling rayon v1.12.0
    Building [================>        ] 274/398: chrono, rand_chacha, sha2, …    Building [================>        ] 275/398: rand_chacha, sha2, time, sh…   Compiling rand v0.8.6
   Compiling syn v2.0.117
   Compiling syn v3.0.9
    Building [================>        ] 275/398: rand_chacha, sha2, syn, tim…    Building [================>        ] 277/398: sha2, syn, time, sha1, num-…   Compiling parse-zoneinfo v0.3.1
    Building [================>        ] 278/398: sha2, syn, time, sha1, num-…    Building [================>        ] 279/398: sha2, syn, time, sha1, num-…   Compiling ignore v0.4.32
    Building [================>        ] 281/398: sha2, syn, time, num-bigint…    Building [================>        ] 282/398: sha2, syn, time, num-bigint…   Compiling hashbrown v0.14.5
    Building [================>        ] 283/398: sha2, syn, time, num-bigint…    Building [================>        ] 284/398: sha2, syn, time, num-bigint…    Building [================>        ] 285/398: sha2, syn, rustls(build), t…    Building [================>        ] 286/398: sha2, syn, time, num-bigint…    Building [=================>       ] 287/398: syn, time, num-bigint, syn,…    Building [=================>       ] 288/398: syn, time, syn, ring, pest,…    Building [=================>       ] 289/398: syn, time, syn, ring, pest,…   Compiling pest_meta v2.9.4
    Building [=================>       ] 289/398: pest_meta, syn, time, syn, …    Building [=================>       ] 290/398: pest_meta, syn, time, syn, …   Compiling phf_generator v0.11.3
    Building [=================>       ] 291/398: pest_meta, syn, time, syn, …    Building [=================>       ] 292/398: pest_meta, syn, time, syn, …   Compiling globwalk v0.9.1
    Building [=================>       ] 293/398: pest_meta, syn, time, syn, …    Building [=================>       ] 294/398: pest_meta, syn, time, syn, …   Compiling phf_codegen v0.11.3
    Building [=================>       ] 295/398: pest_meta, syn, time, syn, …   Compiling hashlink v0.9.1
    Building [=================>       ] 295/398: pest_meta, syn, time, hashl…    Building [=================>       ] 296/398: pest_meta, syn, time, hashl…    Building [=================>       ] 297/398: pest_meta, syn, time, hashl…   Compiling chrono-tz-build v0.3.0
    Building [=================>       ] 297/398: pest_meta, chrono-tz-build,…    Building [=================>       ] 298/398: pest_meta, chrono-tz-build,…    Building [=================>       ] 299/398: pest_meta, chrono-tz-build,…    Building [=================>       ] 300/398: pest_meta, chrono-tz-build,…    Building [=================>       ] 301/398: chrono-tz-build, syn, syn, …   Compiling chrono-tz v0.9.0
    Building [=================>       ] 302/398: syn, syn, ring, libsqlite3-…    Building [==================>      ] 303/398: syn, syn, ring, libsqlite3-…    Building [==================>      ] 304/398: syn, syn, ring, libsqlite3-…    Building [==================>      ] 305/398: syn, syn, ring, libsqlite3-…    Building [==================>      ] 306/398: syn, syn, ring, chrono-tz, …    Building [==================>      ] 307/398: syn, chrono-tz, syn, ring, …   Compiling rustls-webpki v0.101.7
   Compiling sct v0.7.1
    Building [==================>      ] 307/398: rustls-webpki, syn, chrono-…    Building [==================>      ] 308/398: rustls-webpki, syn, chrono-…   Compiling pest_generator v2.9.4
   Compiling clap_derive v4.6.7
   Compiling derive_arbitrary v1.5.0
    Building [==================>      ] 309/398: rustls-webpki, chrono-tz, s…    Building [==================>      ] 310/398: rustls-webpki, chrono-tz, s…   Compiling synstructure v0.13.2
    Building [==================>      ] 310/398: rustls-webpki, pyo3-macros-…   Compiling serde_derive v1.0.228
   Compiling tokio-macros v2.7.0
   Compiling zerovec-derive v0.11.3
   Compiling tracing-attributes v0.1.31
   Compiling displaydoc v0.2.5
   Compiling futures-macro v0.3.32
   Compiling thiserror-impl v1.0.69
   Compiling thiserror-impl v2.0.18
   Compiling async-trait v0.1.89
   Compiling async-stream-impl v0.3.6
    Building [==================>      ] 311/398: thiserror-impl, rustls-webp…   Compiling arbitrary v1.5.0
    Building [==================>      ] 312/398: thiserror-impl, rustls-webp…   Compiling async-stream v0.3.6
    Building [==================>      ] 313/398: thiserror-impl, rustls-webp…   Compiling pest_derive v2.9.4
    Building [==================>      ] 314/398: thiserror-impl, pest_derive…   Compiling tokio v1.52.2
    Building [==================>      ] 315/398: thiserror-impl, pest_derive…    Building [==================>      ] 316/398: thiserror-impl, pest_derive…   Compiling futures-util v0.3.32
    Building [==================>      ] 317/398: thiserror-impl, pest_derive…    Building [==================>      ] 318/398: thiserror-impl, pest_derive…    Building [===================>     ] 319/398: thiserror-impl, pyo3-macros…    Building [===================>     ] 320/398: thiserror-impl, pyo3-macros…    Building [===================>     ] 321/398: thiserror-impl, pyo3-macros…   Compiling zerofrom-derive v0.1.7
   Compiling yoke-derive v0.8.2
    Building [===================>     ] 322/398: thiserror-impl, pyo3-macros…   Compiling tracing v0.1.44
    Building [===================>     ] 323/398: thiserror-impl, tracing, py…    Building [===================>     ] 324/398: thiserror-impl, tracing, py…   Compiling clap v4.6.7
    Building [===================>     ] 325/398: thiserror-impl, tracing, py…    Building [===================>     ] 326/398: thiserror-impl, tracing, py…    Building [===================>     ] 327/398: tracing, pyo3-macros-backen…   Compiling clap-cargo v0.18.3
    Building [===================>     ] 328/398: tracing, pyo3-macros-backen…   Compiling zerofrom v0.1.7
    Building [===================>     ] 329/398: tracing, pyo3-macros-backen…    Building [===================>     ] 330/398: tracing, pyo3-macros-backen…   Compiling table_formatter v0.6.1
    Building [===================>     ] 331/398: tracing, pyo3-macros-backen…   Compiling simple_asn1 v0.6.4
    Building [===================>     ] 331/398: simple_asn1, tracing, pyo3-…    Building [===================>     ] 332/398: simple_asn1, tracing, pyo3-…   Compiling tower-http v0.5.2
    Building [===================>     ] 333/398: simple_asn1, pyo3-macros-ba…   Compiling yoke v0.8.2
    Building [===================>     ] 334/398: simple_asn1, pyo3-macros-ba…    Building [====================>    ] 335/398: simple_asn1, pyo3-macros-ba…    Building [====================>    ] 336/398: simple_asn1, pyo3-macros-ba…    Building [====================>    ] 337/398: simple_asn1, pyo3-macros-ba…    Building [====================>    ] 338/398: simple_asn1, pyo3-macros-ba…   Compiling zerovec v0.11.6
   Compiling zerotrie v0.2.4
    Building [====================>    ] 338/398: simple_asn1, zerotrie, pyo3…    Building [====================>    ] 339/398: simple_asn1, zerotrie, pyo3…    Building [====================>    ] 340/398: simple_asn1, zerotrie, pyo3…    Building [====================>    ] 341/398: simple_asn1, zerotrie, pyo3…   Compiling matchers v0.2.0
    Building [====================>    ] 342/398: simple_asn1, zerotrie, pyo3…    Building [====================>    ] 343/398: zerotrie, pyo3-macros-backe…   Compiling json5 v0.4.1
   Compiling tera v1.20.1
   Compiling sase_workspace_hack v0.1.0 (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/sase/repos/linked/sase-core/crates/sase_workspace_hack)
    Building [====================>    ] 344/398: zerotrie, sase_workspace_ha…   Compiling tracing-subscriber v0.3.23
    Building [====================>    ] 345/398: zerotrie, sase_workspace_ha…    Building [====================>    ] 346/398: zerotrie, sase_workspace_ha…    Building [====================>    ] 347/398: sase_workspace_hack(build.r…   Compiling serde_urlencoded v0.7.1
   Compiling dashmap v6.1.0
   Compiling serde_yaml v0.9.34+deprecated
   Compiling jsonwebtoken v9.3.1
    Building [====================>    ] 348/398: sase_workspace_hack(build.r…    Building [====================>    ] 349/398: pyo3-macros-backend, sase_w…    Building [====================>    ] 350/398: pyo3-macros-backend, zerove…   Compiling pyo3-macros v0.22.6
    Building [=====================>   ] 351/398: zerovec, tera, jsonwebtoken…    Building [=====================>   ] 352/398: zerovec, tera, jsonwebtoken…   Compiling tinystr v0.8.3
   Compiling potential_utf v0.1.5
    Building [=====================>   ] 354/398: tera, jsonwebtoken, json5, …    Building [=====================>   ] 355/398: tera, jsonwebtoken, json5, …    Building [=====================>   ] 356/398: tera, jsonwebtoken, libsqli…    Building [=====================>   ] 357/398: tera, jsonwebtoken, libsqli…   Compiling icu_collections v2.2.0
    Building [=====================>   ] 357/398: tera, jsonwebtoken, icu_col…    Building [=====================>   ] 358/398: tera, jsonwebtoken, icu_col…   Compiling icu_locale_core v2.2.0
    Building [=====================>   ] 358/398: icu_locale_core, tera, json…    Building [=====================>   ] 359/398: icu_locale_core, tera, json…    Building [=====================>   ] 359/398: ignore, icu_locale_core, te…    Building [=====================>   ] 360/398: ignore, icu_locale_core, te…   Compiling axum-core v0.4.5
    Building [=====================>   ] 361/398: ignore, icu_locale_core, te…    Building [=====================>   ] 362/398: ignore, icu_locale_core, te…    Building [=====================>   ] 363/398: ignore, icu_locale_core, te…    Building [=====================>   ] 364/398: ignore, icu_locale_core, te…   Compiling tokei v15.0.0
    Building [=====================>   ] 365/398: ignore, icu_locale_core, li…   Compiling icu_provider v2.2.0
    Building [=====================>   ] 366/398: ignore, libsqlite3-sys(buil…    Building [======================>  ] 367/398: ignore, tokei(build), libsq…    Building [======================>  ] 368/398: ignore, libsqlite3-sys(buil…    Building [======================>  ] 369/398: ignore, libsqlite3-sys(buil…   Compiling icu_properties v2.2.0
   Compiling icu_normalizer v2.2.0
    Building [======================>  ] 369/398: ignore, icu_normalizer, icu…    Building [======================>  ] 370/398: ignore, icu_normalizer, icu…    Building [======================>  ] 371/398: ignore, icu_normalizer, icu…    Building [======================>  ] 372/398: ignore, icu_normalizer, icu…    Building [======================>  ] 373/398: ignore, icu_normalizer, icu…    Building [======================>  ] 374/398: icu_normalizer, icu_propert…    Building [======================>  ] 375/398: icu_properties, libsqlite3-…   Compiling idna_adapter v1.2.2
    Building [======================>  ] 376/398: libsqlite3-sys(build), idna…   Compiling tokio-util v0.7.18
   Compiling tower v0.5.3
   Compiling tokio-rustls v0.24.1
   Compiling hyper v1.9.0
    Building [======================>  ] 376/398: hyper, tokio-rustls, tower,…    Building [======================>  ] 377/398: hyper, tokio-rustls, tower,…   Compiling idna v1.1.0
    Building [======================>  ] 378/398: hyper, tokio-rustls, tower,…    Building [======================>  ] 379/398: hyper, tower, libsqlite3-sy…    Building [======================>  ] 380/398: hyper, libsqlite3-sys(build…   Compiling h2 v0.3.27
    Building [======================>  ] 381/398: hyper, libsqlite3-sys(build…    Building [======================>  ] 382/398: hyper, libsqlite3-sys(build…   Compiling url v2.5.8
    Building [=======================> ] 383/398: hyper, libsqlite3-sys(build…   Compiling hyper-util v0.1.20
    Building [=======================> ] 383/398: hyper, hyper-util, libsqlit…    Building [=======================> ] 384/398: hyper-util, libsqlite3-sys(…   Compiling axum v0.7.9
    Building [=======================> ] 384/398: axum, hyper-util, libsqlite…    Building [=======================> ] 385/398: axum, libsqlite3-sys(build)…    Building [=======================> ] 386/398: axum, libsqlite3-sys(build)…    Building [=======================> ] 387/398: axum, libsqlite3-sys(build)…   Compiling hyper v0.14.32
    Building [=======================> ] 387/398: hyper, axum, libsqlite3-sys…    Building [=======================> ] 388/398: hyper, axum, libsqlite3-sys…    Building [=======================> ] 389/398: hyper, libsqlite3-sys(build)   Compiling hyper-rustls v0.24.2
    Building [=======================> ] 389/398: hyper, libsqlite3-sys(build…    Building [=======================> ] 390/398: libsqlite3-sys(build), hype…   Compiling reqwest v0.11.27
    Building [=======================> ] 390/398: libsqlite3-sys(build), reqw…    Building [=======================> ] 391/398: libsqlite3-sys(build), reqw…    Building [=======================> ] 392/398: libsqlite3-sys(build)           Building [=======================> ] 393/398: libsqlite3-sys                 Compiling rusqlite v0.32.1
    Building [=======================> ] 393/398: rusqlite, libsqlite3-sys        Building [=======================> ] 394/398: rusqlite                       Compiling sase_core v0.43.0 (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/sase/repos/linked/sase-core/crates/sase_core)
    Building [=======================> ] 394/398: sase_core, rusqlite             Building [=======================> ] 395/398: sase_core                      Compiling sase_gateway v0.43.0 (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/sase/repos/linked/sase-core/crates/sase_gateway)
    Building [=======================> ] 395/398: sase_gateway, sase_core         Building [=======================> ] 396/398: sase_gateway                   Compiling sase_core_py v0.43.0 (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/sase/repos/linked/sase-core/crates/sase_core_py)
    Building [=======================> ] 397/398: sase_core_py                    Finished `release` profile [optimized] target(s) in 15m 28s
📦 Built wheel for abi3 Python ≥ 3.12 to /home/bryan/.cache/sase/tmp/agent-tmp/gh_sase-org__sase-ws14-261028_025120/.tmp4Xau8D/sase_core_rs-0.43.0-cp312-abi3-linux_x86_64.whl
✏️ Setting installed package as editable
🛠 Installed sase-core-rs-0.43.0
[sase-core-wheel-cache] miss: sase-core checkout is dirty
# Keep the LSP server in lockstep with the extension: both are built
# from the same sase-core checkout, and the ACE/LSP parity tests
# compare their directive contracts.
[sase-core-wheel-cache] miss: sase-core checkout is dirty
[sase-core-wheel-cache] miss: sase-core checkout is dirty
   Compiling sase_core v0.43.0 (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/sase/repos/linked/sase-core/crates/sase_core)
    Building [=======================> ] 285/288: sase_core                      Compiling sase_macro_lsp v0.43.0 (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/sase/repos/linked/sase-core/crates/sase_macro_lsp)
    Building [=======================> ] 285/288: sase_macro_lsp, sase_core       Building [=======================> ] 286/288: sase_macro_lsp                  Building [=======================> ] 287/288: sase-macro-lsp(bin)             Finished `dev-update` profile [optimized] target(s) in 2m 35s
[rust-lsp-install] installed /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/.venv/bin/sase-macro-lsp
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
✗ lint (symvision)
[validate_sase_core_rs_version] sase-core checkout is ahead of sase's compatibility window: source version 0.43.0 from /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/sase/repos/linked/sase-core/Cargo.toml does not satisfy `sase`'s `sase-core-rs==0.42.7` dependency in pyproject.toml. No action is needed: editable installs build from the checkout regardless, and `tools/ratchet_core_pin` moves the published pin on the release branch at release time.
[setup] Note: the sase-core checkout is ahead of the published sase-core-rs pin in pyproject.toml; dev installs build from /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/sase/repos/linked/sase-core regardless. This is normal — the release-branch reconciler ratchets the published pin at release time, so no action is needed here.
.venv/bin/python tools/setup_required_plugins
[setup] Installing required plugin sase-github>=0.2.5.
[setup] Installing required plugin sase-research-artifacts>=0.2.0.
SASE_SYMVISION_BEAD_STATUS_ONLY=1 BD_COMMAND=tools/sase_bead .venv/bin/symvision src/sase --exclude-decorator gate_command_entrypoint --exclude-decorator builtin_chop --epic-symbol 'sase-1p1(footprint_wire_schema_version)' --epic-symbol 'sase-1p1(footprint_upsert_derived)' --epic-symbol 'sase-1p1(footprint_validate_overlay)' 
Error: Private functions/classes should not be imported. Make these public if they need to be imported by non-test files!:
  _RecoveryAssessment in src/sase/finalizers/_failed_close_recovery_assess.py
error: recipe `_lint-symvision` failed on line 491 with exit code 1
✓ lint (docs contract)
✓ SASE validation
[core-floor-probe] blocked_unpublished: sase-core-rs==0.42.7 is missing 33 capability(s), and at least one has no containing sase-core release tag yet.
[core-floor-probe] agent_publication_protection_wire_schema_version: first appears in sase-core 416db28 (feat(core): add publication protection policy); release v0.43.0 contains it.
[core-floor-probe] artifact_link_collision_partition: first appears in sase-core 6613c9b (feat(artifact-link): add collision partition and quarantine contracts); no release tag contains it yet.
[core-floor-probe] artifact_link_collision_wire_schema_version: first appears in sase-core 6613c9b (feat(artifact-link): add collision partition and quarantine contracts); no release tag contains it yet.
[core-floor-probe] artifact_link_quarantine_record_canonical_json: first appears in sase-core 6613c9b (feat(artifact-link): add collision partition and quarantine contracts); no release tag contains it yet.
[core-floor-probe] artifact_link_quarantine_record_path: first appears in sase-core 6613c9b (feat(artifact-link): add collision partition and quarantine contracts); no release tag contains it yet.
[core-floor-probe] artifact_link_quarantine_record_validate: first appears in sase-core 6613c9b (feat(artifact-link): add collision partition and quarantine contracts); no release tag contains it yet.
[core-floor-probe] artifact_link_quarantine_wire_schema_version: first appears in sase-core 6613c9b (feat(artifact-link): add collision partition and quarantine contracts); no release tag contains it yet.
[core-floor-probe] assess_repository_landing_proof: first appears in sase-core 800caef (fix(beads): recover every eligible failed-run close in one mutation); release v0.43.0 contains it.
[core-floor-probe] bead_recover_failed_closes: first appears in sase-core 4f17b72 (feat(beads): recover failed-run closes atomically); release v0.43.0 contains it.
[core-floor-probe] classify_sidecar_publication_push_result: first appears in sase-core 416db28 (feat(core): add publication protection policy); release v0.43.0 contains it.
[core-floor-probe] footprint_card: first appears in sase-core 83b010d (feat(footprint): add lens engine, evidence states, and review decisions); no release tag contains it yet.
[core-floor-probe] footprint_catalog_status: first appears in sase-core 2d0b62e (feat(footprint): add ledger, spool fold, catalog ingest, and status); no release tag contains it yet.
[core-floor-probe] footprint_clear: first appears in sase-core 2d0b62e (feat(footprint): add ledger, spool fold, catalog ingest, and status); no release tag contains it yet.
[core-floor-probe] footprint_decide: first appears in sase-core 83b010d (feat(footprint): add lens engine, evidence states, and review decisions); no release tag contains it yet.
[core-floor-probe] footprint_export: no introducing commit found in sase-core.
[core-floor-probe] footprint_fold: first appears in sase-core 2d0b62e (feat(footprint): add ledger, spool fold, catalog ingest, and status); no release tag contains it yet.
[core-floor-probe] footprint_import: no introducing commit found in sase-core.
[core-floor-probe] footprint_ingest_catalog: first appears in sase-core 2d0b62e (feat(footprint): add ledger, spool fold, catalog ingest, and status); no release tag contains it yet.
[core-floor-probe] footprint_prune: first appears in sase-core 2d0b62e (feat(footprint): add ledger, spool fold, catalog ingest, and status); no release tag contains it yet.
[core-floor-probe] footprint_report: first appears in sase-core 83b010d (feat(footprint): add lens engine, evidence states, and review decisions); no release tag contains it yet.
[core-floor-probe] footprint_status: first appears in sase-core 2d0b62e (feat(footprint): add ledger, spool fold, catalog ingest, and status); no release tag contains it yet.
[core-floor-probe] footprint_upsert_derived: first appears in sase-core 2d0b62e (feat(footprint): add ledger, spool fold, catalog ingest, and status); no release tag contains it yet.
[core-floor-probe] footprint_validate_overlay: first appears in sase-core 2d0b62e (feat(footprint): add ledger, spool fold, catalog ingest, and status); no release tag contains it yet.
[core-floor-probe] footprint_wire_schema_version: first appears in sase-core 2d0b62e (feat(footprint): add ledger, spool fold, catalog ingest, and status); no release tag contains it yet.
[core-floor-probe] publication_protection_ledger_empty: first appears in sase-core 416db28 (feat(core): add publication protection policy); release v0.43.0 contains it.
[core-floor-probe] publication_protection_ledger_validate: first appears in sase-core 416db28 (feat(core): add publication protection policy); release v0.43.0 contains it.
[core-floor-probe] publication_protection_lookup: first appears in sase-core 416db28 (feat(core): add publication protection policy); release v0.43.0 contains it.
[core-floor-probe] publication_protection_record_from_rejection: first appears in sase-core 416db28 (feat(core): add publication protection policy); release v0.43.0 contains it.
[core-floor-probe] publication_protection_record_from_scan: first appears in sase-core 416db28 (feat(core): add publication protection policy); release v0.43.0 contains it.
[core-floor-probe] publication_protection_resolve_verified_clean: first appears in sase-core 416db28 (feat(core): add publication protection policy); release v0.43.0 contains it.
[core-floor-probe] publication_protection_retry_allowed: first appears in sase-core 416db28 (feat(core): add publication protection policy); release v0.43.0 contains it.
[core-floor-probe] publication_protection_upsert: first appears in sase-core 416db28 (feat(core): add publication protection policy); release v0.43.0 contains it.
[core-floor-probe] publication_scan_disposition: first appears in sase-core 416db28 (feat(core): add publication protection policy); release v0.43.0 contains it.
{"cache_hit": false, "capabilities": [{"commit": "416db28", "name": "agent_publication_protection_wire_schema_version", "release": "v0.43.0", "subject": "feat(core): add publication protection policy"}, {"commit": "6613c9b", "name": "artifact_link_collision_partition", "release": null, "subject": "feat(artifact-link): add collision partition and quarantine contracts"}, {"commit": "6613c9b", "name": "artifact_link_collision_wire_schema_version", "release": null, "subject": "feat(artifact-link): add collision partition and quarantine contracts"}, {"commit": "6613c9b", "name": "artifact_link_quarantine_record_canonical_json", "release": null, "subject": "feat(artifact-link): add collision partition and quarantine contracts"}, {"commit": "6613c9b", "name": "artifact_link_quarantine_record_path", "release": null, "subject": "feat(artifact-link): add collision partition and quarantine contracts"}, {"commit": "6613c9b", "name": "artifact_link_quarantine_record_validate", "release": null, "subject": "feat(artifact-link): add collision partition and quarantine contracts"}, {"commit": "6613c9b", "name": "artifact_link_quarantine_wire_schema_version", "release": null, "subject": "feat(artifact-link): add collision partition and quarantine contracts"}, {"commit": "800caef", "name": "assess_repository_landing_proof", "release": "v0.43.0", "subject": "fix(beads): recover every eligible failed-run close in one mutation"}, {"commit": "4f17b72", "name": "bead_recover_failed_closes", "release": "v0.43.0", "subject": "feat(beads): recover failed-run closes atomically"}, {"commit": "416db28", "name": "classify_sidecar_publication_push_result", "release": "v0.43.0", "subject": "feat(core): add publication protection policy"}, {"commit": "83b010d", "name": "footprint_card", "release": null, "subject": "feat(footprint): add lens engine, evidence states, and review decisions"}, {"commit": "2d0b62e", "name": "footprint_catalog_status", "release": null, "subject": "feat(footprint): add ledger, spool fold, catalog ingest, and status"}, {"commit": "2d0b62e", "name": "footprint_clear", "release": null, "subject": "feat(footprint): add ledger, spool fold, catalog ingest, and status"}, {"commit": "83b010d", "name": "footprint_decide", "release": null, "subject": "feat(footprint): add lens engine, evidence states, and review decisions"}, {"commit": null, "name": "footprint_export", "release": null, "subject": null}, {"commit": "2d0b62e", "name": "footprint_fold", "release": null, "subject": "feat(footprint): add ledger, spool fold, catalog ingest, and status"}, {"commit": null, "name": "footprint_import", "release": null, "subject": null}, {"commit": "2d0b62e", "name": "footprint_ingest_catalog", "release": null, "subject": "feat(footprint): add ledger, spool fold, catalog ingest, and status"}, {"commit": "2d0b62e", "name": "footprint_prune", "release": null, "subject": "feat(footprint): add ledger, spool fold, catalog ingest, and status"}, {"commit": "83b010d", "name": "footprint_report", "release": null, "subject": "feat(footprint): add lens engine, evidence states, and review decisions"}, {"commit": "2d0b62e", "name": "footprint_status", "release": null, "subject": "feat(footprint): add ledger, spool fold, catalog ingest, and status"}, {"commit": "2d0b62e", "name": "footprint_upsert_derived", "release": null, "subject": "feat(footprint): add ledger, spool fold, catalog ingest, and status"}, {"commit": "2d0b62e", "name": "footprint_validate_overlay", "release": null, "subject": "feat(footprint): add ledger, spool fold, catalog ingest, and status"}, {"commit": "2d0b62e", "name": "footprint_wire_schema_version", "release": null, "subject": "feat(footprint): add ledger, spool fold, catalog ingest, and status"}, {"commit": "416db28", "name": "publication_protection_ledger_empty", "release": "v0.43.0", "subject": "feat(core): add publication protection policy"}, {"commit": "416db28", "name": "publication_protection_ledger_validate", "release": "v0.43.0", "subject": "feat(core): add publication protection policy"}, {"commit": "416db28", "name": "publication_protection_lookup", "release": "v0.43.0", "subject": "feat(core): add publication protection policy"}, {"commit": "416db28", "name": "publication_protection_record_from_rejection", "release": "v0.43.0", "subject": "feat(core): add publication protection policy"}, {"commit": "416db28", "name": "publication_protection_record_from_scan", "release": "v0.43.0", "subject": "feat(core): add publication protection policy"}, {"commit": "416db28", "name": "publication_protection_resolve_verified_clean", "release": "v0.43.0", "subject": "feat(core): add publication protection policy"}, {"commit": "416db28", "name": "publication_protection_retry_allowed", "release": "v0.43.0", "subject": "feat(core): add publication protection policy"}, {"commit": "416db28", "name": "publication_protection_upsert", "release": "v0.43.0", "subject": "feat(core): add publication protection policy"}, {"commit": "416db28", "name": "publication_scan_disposition", "release": "v0.43.0", "subject": "feat(core): add publication protection policy"}], "declared_floor": "0.42.7", "exit_code": 4, "message": "sase-core-rs==0.42.7 is missing 33 capability(s), and at least one has no containing sase-core release tag yet.", "status": "blocked_unpublished"}
✓ committed plans
✓ docs (build + links)
✗ test (scoped)
[validate_sase_core_rs_version] sase-core checkout is ahead of sase's compatibility window: source version 0.43.0 from /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/sase/repos/linked/sase-core/Cargo.toml does not satisfy `sase`'s `sase-core-rs==0.42.7` dependency in pyproject.toml. No action is needed: editable installs build from the checkout regardless, and `tools/ratchet_core_pin` moves the published pin on the release branch at release time.
[setup] Note: the sase-core checkout is ahead of the published sase-core-rs pin in pyproject.toml; dev installs build from /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/sase/repos/linked/sase-core regardless. This is normal — the release-branch reconciler ratchets the published pin at release time, so no action is needed here.
.venv/bin/python tools/setup_required_plugins
[setup] Installing required plugin sase-github>=0.2.5.
[setup] Installing required plugin sase-research-artifacts>=0.2.0.

┌───────────────────────────────────────────────────────┐
│                RUNNING: just test-scoped              │
└───────────────────────────────────────────────────────┘

---------- Running diff-scoped pytest selection... ----------
test selection escalated to the full suite (rules: core-identity-changed); 5435 test files in scope
coverage contexts: not consulted — the run escalates to the full suite, so ground truth had nothing to add
escalating to the governed full test lane (rules: core-identity-changed)
============================= test session starts ==============================
platform linux -- Python 3.14.7, pytest-9.1.1, pluggy-1.6.0
rootdir: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14
configfile: pyproject.toml
testpaths: tests
plugins: cov-7.1.0, mock-3.16.0, inline-snapshot-0.36.0, asyncio-1.4.0, hypothesis-6.168.5, xdist-3.8.0, platformdirs-4.13.5
asyncio: mode=Mode.AUTO, debug=False, asyncio_default_fixture_loop_scope=None, asyncio_default_test_loop_scope=function
created: 14/14 workers
14 workers [58478 items]

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
........................................................................ [  2%]
....................................................................s... [  3%]
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
...........................s............................................ [  5%]
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
...............................s........................................ [  7%]
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
.............................................................s.......... [  8%]
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
.......................s................................................ [ 13%]
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
..........................................s............................. [ 15%]
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
...................s.................................................... [ 32%]
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
....................................F.................F................. [ 34%]
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
.............................F.......................................... [ 38%]
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
................................................F....................... [ 40%]
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
........................................................................ [ 42%]
........................................s............................... [ 43%]
........................................................................ [ 43%]
........................................................................ [ 43%]
..............................................s.s....................... [ 43%]
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
................F...F................................................... [ 48%]
........................................................................ [ 48%]
........................................................................ [ 48%]
........................................................................ [ 49%]
........................................................................ [ 49%]
........................................................................ [ 49%]
...............................................................s........ [ 49%]
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
........ssss............................................................ [ 61%]
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
....................s................................................... [ 67%]
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
........................................F............................... [ 70%]
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
.......................................................F................ [ 87%]
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
........................................................................ [ 98%]
........................................................................ [ 99%]
........................................................................ [ 99%]
........................................................................ [ 99%]
........................................................................ [ 99%]
........................................................................ [ 99%]
........................................................................ [ 99%]
........................................................................ [ 99%]
........................................................................ [ 99%]
..............                                                           [100%]

═══════════════════════════════ inline-snapshot ════════════════════════════════
INFO: CI run was detected because environment variable "CI" was defined. 
inline-snapshot runs with --inline-snapshot=disable by default in CI. This means
that tests with snapshots will continue to run, but snapshot(x) will only return
x and inline-snapshot will not be able to fix snapshots or generate reports. You
can change this by using --inline-snapshot=report for example.


=================================== FAILURES ===================================
__________ test_prepare_workspace_holds_agents_lock_across_the_clean ___________
[gw9] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/.venv/bin/python

monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7fbbc80897f0>

    def test_prepare_workspace_holds_agents_lock_across_the_clean(
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        """The lock covers the clean and checkout, and is released afterwards."""
    
        repo = _shared_agents_clone()
        monkeypatch.setenv("SASE_AGENTS_SYNC_LOCK_TIMEOUT", "0")
        provider = _successful_provider()
        observed: list[bool] = []
    
        def _clean(workspace_dir: str, diff_name: str) -> tuple[bool, None]:
            assert workspace_dir and diff_name
            observed.append(_lock_is_free(_lock_path(repo)))
            return (True, None)
    
        with (
            patch("sase.workflows.commit_utils.run_sase_hg_clean", _clean),
            patch(
                "sase.axe.runner_workspace_prepare.get_vcs_provider", return_value=provider
            ),
        ):
>           assert prepare_workspace(str(repo), "agents", VCS_DEFAULT_REVISION) is None
                   ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

tests/test_axe_runner_workspace_agents_lock.py:121: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
src/sase/axe/runner_workspace_prepare.py:115: in prepare_workspace
    _prepare_workspace_locked(
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

workspace_dir = '/var/tmp/sase-d00a07ab/pytest-of-bryan/pytest-22/popen-gw9/home1987/.sase/projects/gh_sase-org__sase/repos/agents'
cl_name = 'agents', update_target = '__vcs_default__', backup_suffix = 'ace'
project_basename = '', self_heal = False, workspace_num = 1

    def _prepare_workspace_locked(
        workspace_dir: str,
        cl_name: str,
        update_target: str,
        backup_suffix: str,
        project_basename: str,
        *,
        self_heal: bool = False,
        workspace_num: int = 1,
    ) -> None:
        """Run the clean/checkout/sync pass that :func:`prepare_workspace` guards.
    
        Raises:
            WorkspacePreparationError: If any step fails, carrying the underlying
                failure text in ``reason``.
        """
    
        from sase.workflows.commit_utils import run_sase_hg_clean
    
        # An index.lock left behind by a crashed or SIGTERM-killed git process
        # blocks every subsequent operation in this clone ("Another git process
        # seems to be running..."), which would fail the clean/checkout below. This
        # runs against a workspace we have exclusively claimed, so a lock old enough
        # to predate the claim is abandoned; clear it as git itself instructs.
        clear_stale_git_index_lock(workspace_dir)
    
        if not protect_unpushed_sidecar_commits(workspace_dir, workspace_num=workspace_num):
            raise WorkspacePreparationError(
                "sidecar repos hold unpublished commits that could not be published "
                "before workspace cleanup (see diagnostics above)",
                step="sidecar-protection",
                workspace_dir=workspace_dir,
            )
    
        # The provider is resolved up front only for self-heal inspection; the
        # default path keeps today's order (clean before provider resolution) so
        # early clean failures keep their existing precedence.
        provider: VCSProvider | None = None
        inspection: CheckoutInspection | None = None
        if self_heal:
            # Self-heal inspection. Providers without the heal operations raise
            # NotImplementedError and preparation keeps today's behavior below.
            provider = get_vcs_provider(workspace_dir)
            try:
                inspection = provider.inspect_checkout(workspace_dir)
            except NotImplementedError:
                inspection = None
        healing = inspection is not None
        rescued: RescueRecord | None = None
        if inspection is not None and provider is not None:
            rescued = rescue_heal_state(workspace_dir, workspace_num, inspection)
            if inspection.operations:
                require_verified_snapshot(
                    workspace_dir,
                    workspace_num,
                    label="abort",
                    reason=(
                        "self-heal: preserving before aborting "
                        f"{', '.join(inspection.operations)}"
                    ),
                    step="heal",
                )
                try:
                    abort_ok, abort_err = provider.abort_in_progress_operations(
                        workspace_dir
                    )
                except NotImplementedError:
                    abort_ok, abort_err = True, None
                if not abort_ok:
                    reason = (
                        "could not abort in-progress git operations: "
                        f"{abort_err or 'unknown error'}"
                    )
                    print(reason, file=sys.stderr)
                    raise WorkspacePreparationError(
                        reason,
                        step="heal",
                        workspace_dir=workspace_dir,
                        reclone_eligible=True,
                    )
                for label in inspection.operations:
                    print(f"Aborted stale {label} in {workspace_dir}")
    
        # Clean workspace (saves any existing changes to a diff file).
        # run_sase_hg_clean captures a verified snapshot before its stash, so
        # normal launches and direct callers obtain durable preservation before
        # the first source-mutating cleanup. A preservation failure must not
        # fall through to the destructive reset/clean fallback below.
        print("Cleaning workspace...")
>       success, error = run_sase_hg_clean(
            workspace_dir, f"{cl_name}-{backup_suffix}", workspace_num=workspace_num
        )
E       TypeError: test_prepare_workspace_holds_agents_lock_across_the_clean.<locals>._clean() got an unexpected keyword argument 'workspace_num'. Did you mean 'workspace_dir'?

src/sase/axe/runner_workspace_prepare.py:215: TypeError
----------------------------- Captured stdout call -----------------------------
Cleaning workspace...
____ test_prepare_workspace_leaves_workspace_scoped_agents_clone_unguarded _____
[gw9] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/.venv/bin/python

tmp_path = PosixPath('/var/tmp/sase-d00a07ab/pytest-of-bryan/pytest-22/popen-gw9/test_prepare_workspace_leaves_0')
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7fbbca6fd940>

    def test_prepare_workspace_leaves_workspace_scoped_agents_clone_unguarded(
        tmp_path: Path,
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        """Only the machine-shared clone is coordinated, not a workspace sidecar."""
    
        repo = _git_init(tmp_path / "sase_3" / "sase" / "repos" / "agents")
        monkeypatch.setenv("SASE_AGENTS_SYNC_LOCK_TIMEOUT", "0")
        observed: list[bool] = []
    
        def _clean(workspace_dir: str, diff_name: str) -> tuple[bool, None]:
            assert workspace_dir and diff_name
            observed.append(_lock_is_free(_lock_path(repo)))
            return (True, None)
    
        with (
            patch("sase.workflows.commit_utils.run_sase_hg_clean", _clean),
            patch(
                "sase.axe.runner_workspace_prepare.get_vcs_provider",
                return_value=_successful_provider(),
            ),
        ):
>           assert prepare_workspace(str(repo), "agents", VCS_DEFAULT_REVISION) is None
                   ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

tests/test_axe_runner_workspace_agents_lock.py:150: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
src/sase/axe/runner_workspace_prepare.py:115: in prepare_workspace
    _prepare_workspace_locked(
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

workspace_dir = '/var/tmp/sase-d00a07ab/pytest-of-bryan/pytest-22/popen-gw9/test_prepare_workspace_leaves_0/sase_3/sase/repos/agents'
cl_name = 'agents', update_target = '__vcs_default__', backup_suffix = 'ace'
project_basename = '', self_heal = False, workspace_num = 1

    def _prepare_workspace_locked(
        workspace_dir: str,
        cl_name: str,
        update_target: str,
        backup_suffix: str,
        project_basename: str,
        *,
        self_heal: bool = False,
        workspace_num: int = 1,
    ) -> None:
        """Run the clean/checkout/sync pass that :func:`prepare_workspace` guards.
    
        Raises:
            WorkspacePreparationError: If any step fails, carrying the underlying
                failure text in ``reason``.
        """
    
        from sase.workflows.commit_utils import run_sase_hg_clean
    
        # An index.lock left behind by a crashed or SIGTERM-killed git process
        # blocks every subsequent operation in this clone ("Another git process
        # seems to be running..."), which would fail the clean/checkout below. This
        # runs against a workspace we have exclusively claimed, so a lock old enough
        # to predate the claim is abandoned; clear it as git itself instructs.
        clear_stale_git_index_lock(workspace_dir)
    
        if not protect_unpushed_sidecar_commits(workspace_dir, workspace_num=workspace_num):
            raise WorkspacePreparationError(
                "sidecar repos hold unpublished commits that could not be published "
                "before workspace cleanup (see diagnostics above)",
                step="sidecar-protection",
                workspace_dir=workspace_dir,
            )
    
        # The provider is resolved up front only for self-heal inspection; the
        # default path keeps today's order (clean before provider resolution) so
        # early clean failures keep their existing precedence.
        provider: VCSProvider | None = None
        inspection: CheckoutInspection | None = None
        if self_heal:
            # Self-heal inspection. Providers without the heal operations raise
            # NotImplementedError and preparation keeps today's behavior below.
            provider = get_vcs_provider(workspace_dir)
            try:
                inspection = provider.inspect_checkout(workspace_dir)
            except NotImplementedError:
                inspection = None
        healing = inspection is not None
        rescued: RescueRecord | None = None
        if inspection is not None and provider is not None:
            rescued = rescue_heal_state(workspace_dir, workspace_num, inspection)
            if inspection.operations:
                require_verified_snapshot(
                    workspace_dir,
                    workspace_num,
                    label="abort",
                    reason=(
                        "self-heal: preserving before aborting "
                        f"{', '.join(inspection.operations)}"
                    ),
                    step="heal",
                )
                try:
                    abort_ok, abort_err = provider.abort_in_progress_operations(
                        workspace_dir
                    )
                except NotImplementedError:
                    abort_ok, abort_err = True, None
                if not abort_ok:
                    reason = (
                        "could not abort in-progress git operations: "
                        f"{abort_err or 'unknown error'}"
                    )
                    print(reason, file=sys.stderr)
                    raise WorkspacePreparationError(
                        reason,
                        step="heal",
                        workspace_dir=workspace_dir,
                        reclone_eligible=True,
                    )
                for label in inspection.operations:
                    print(f"Aborted stale {label} in {workspace_dir}")
    
        # Clean workspace (saves any existing changes to a diff file).
        # run_sase_hg_clean captures a verified snapshot before its stash, so
        # normal launches and direct callers obtain durable preservation before
        # the first source-mutating cleanup. A preservation failure must not
        # fall through to the destructive reset/clean fallback below.
        print("Cleaning workspace...")
>       success, error = run_sase_hg_clean(
            workspace_dir, f"{cl_name}-{backup_suffix}", workspace_num=workspace_num
        )
E       TypeError: test_prepare_workspace_leaves_workspace_scoped_agents_clone_unguarded.<locals>._clean() got an unexpected keyword argument 'workspace_num'. Did you mean 'workspace_dir'?

src/sase/axe/runner_workspace_prepare.py:215: TypeError
----------------------------- Captured stdout call -----------------------------
Cleaning workspace...
_ test_prepare_workspace_rescues_unpushed_bead_commits_before_sidecar_reset[plans-embedded] _
[gw7] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/.venv/bin/python

tmp_path = PosixPath('/var/tmp/sase-d00a07ab/pytest-of-bryan/pytest-22/popen-gw7/test_prepare_workspace_rescues0')
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7f0003f9c0c0>
beads_dirname = 'beads'

    @pytest.mark.parametrize(
        "beads_dirname",
        ["beads", BEADS_DIRNAME_ROOT],
        ids=["plans-embedded", "repo-root"],
    )
    def test_prepare_workspace_rescues_unpushed_bead_commits_before_sidecar_reset(
        tmp_path: Path,
        monkeypatch: pytest.MonkeyPatch,
        beads_dirname: str,
    ) -> None:
        _remote, local, upstream_writer, phase_ids = _seed_claim_soak_remote(
            tmp_path,
            phase_count=2,
            beads_dirname=beads_dirname,
        )
        local_phase, upstream_phase = phase_ids
        local_beads = local / beads_dirname
        upstream_beads = upstream_writer / beads_dirname
        with BeadProject(local, beads_dirname=beads_dirname) as project:
            _issue, changed = project.claim_for_agent_wait(local_phase, "local-agent")
        assert changed
        assert commit_bead_claim(local_beads, local_phase, "local-agent")
        local_commit = _git(local, "rev-parse", "HEAD").stdout.strip()
    
        with BeadProject(upstream_writer, beads_dirname=beads_dirname) as project:
            _issue, changed = project.claim_for_agent_wait(
                upstream_phase,
                "upstream-agent",
            )
        assert changed
        assert commit_bead_claim(
            upstream_beads,
            upstream_phase,
            "upstream-agent",
        )
        _git(upstream_writer, "push")
        _git(local, "fetch", "origin")
        assert unpushed_bead_commit_count(local, local_beads) == 1
    
        sync_log = tmp_path / "failed-sync.log"
        sync_attempts: list[Path] = []
    
        def fail_publish(beads_dir: Path, **kwargs: object) -> SimpleNamespace:
            sync_attempts.append(beads_dir)
            return SimpleNamespace(
                pushed=False,
                error="injected managed sync failure",
                log_path=sync_log,
            )
    
        class ResettingProvider:
            checkout_revisions: list[str]
    
            def __init__(self) -> None:
                self.checkout_revisions = []
    
            def get_default_parent_revision(self, cwd: str) -> str:
                return "origin/main"
    
            def checkout(self, revision: str, cwd: str) -> tuple[bool, str | None]:
                self.checkout_revisions.append(revision)
                _git(Path(cwd), "reset", "--hard", revision)
                return True, None
    
            def sync_workspace(self, cwd: str) -> tuple[bool, str | None]:
                return True, None
    
        provider = ResettingProvider()
        monkeypatch.setattr("sase.bead.sync.push_bead_work_launch", fail_publish)
        monkeypatch.setattr(
            "sase.workflows.commit_utils.run_sase_hg_clean",
            lambda *_args: (True, ""),
        )
        monkeypatch.setattr(
            "sase.axe.runner_workspace_prepare.get_vcs_provider",
            lambda _cwd: provider,
        )
    
        assert (
>           prepare_workspace(
                str(local),
                "sidecar",
                VCS_DEFAULT_REVISION,
            )
            is None
        )

tests/test_bead/test_sync_workspace_prepare_regressions.py:103: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
src/sase/axe/runner_workspace_prepare.py:115: in prepare_workspace
    _prepare_workspace_locked(
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

workspace_dir = '/var/tmp/sase-d00a07ab/pytest-of-bryan/pytest-22/popen-gw7/test_prepare_workspace_rescues0/claim-soak-local'
cl_name = 'sidecar', update_target = '__vcs_default__', backup_suffix = 'ace'
project_basename = '', self_heal = False, workspace_num = 1

    def _prepare_workspace_locked(
        workspace_dir: str,
        cl_name: str,
        update_target: str,
        backup_suffix: str,
        project_basename: str,
        *,
        self_heal: bool = False,
        workspace_num: int = 1,
    ) -> None:
        """Run the clean/checkout/sync pass that :func:`prepare_workspace` guards.
    
        Raises:
            WorkspacePreparationError: If any step fails, carrying the underlying
                failure text in ``reason``.
        """
    
        from sase.workflows.commit_utils import run_sase_hg_clean
    
        # An index.lock left behind by a crashed or SIGTERM-killed git process
        # blocks every subsequent operation in this clone ("Another git process
        # seems to be running..."), which would fail the clean/checkout below. This
        # runs against a workspace we have exclusively claimed, so a lock old enough
        # to predate the claim is abandoned; clear it as git itself instructs.
        clear_stale_git_index_lock(workspace_dir)
    
        if not protect_unpushed_sidecar_commits(workspace_dir, workspace_num=workspace_num):
            raise WorkspacePreparationError(
                "sidecar repos hold unpublished commits that could not be published "
                "before workspace cleanup (see diagnostics above)",
                step="sidecar-protection",
                workspace_dir=workspace_dir,
            )
    
        # The provider is resolved up front only for self-heal inspection; the
        # default path keeps today's order (clean before provider resolution) so
        # early clean failures keep their existing precedence.
        provider: VCSProvider | None = None
        inspection: CheckoutInspection | None = None
        if self_heal:
            # Self-heal inspection. Providers without the heal operations raise
            # NotImplementedError and preparation keeps today's behavior below.
            provider = get_vcs_provider(workspace_dir)
            try:
                inspection = provider.inspect_checkout(workspace_dir)
            except NotImplementedError:
                inspection = None
        healing = inspection is not None
        rescued: RescueRecord | None = None
        if inspection is not None and provider is not None:
            rescued = rescue_heal_state(workspace_dir, workspace_num, inspection)
            if inspection.operations:
                require_verified_snapshot(
                    workspace_dir,
                    workspace_num,
                    label="abort",
                    reason=(
                        "self-heal: preserving before aborting "
                        f"{', '.join(inspection.operations)}"
                    ),
                    step="heal",
                )
                try:
                    abort_ok, abort_err = provider.abort_in_progress_operations(
                        workspace_dir
                    )
                except NotImplementedError:
                    abort_ok, abort_err = True, None
                if not abort_ok:
                    reason = (
                        "could not abort in-progress git operations: "
                        f"{abort_err or 'unknown error'}"
                    )
                    print(reason, file=sys.stderr)
                    raise WorkspacePreparationError(
                        reason,
                        step="heal",
                        workspace_dir=workspace_dir,
                        reclone_eligible=True,
                    )
                for label in inspection.operations:
                    print(f"Aborted stale {label} in {workspace_dir}")
    
        # Clean workspace (saves any existing changes to a diff file).
        # run_sase_hg_clean captures a verified snapshot before its stash, so
        # normal launches and direct callers obtain durable preservation before
        # the first source-mutating cleanup. A preservation failure must not
        # fall through to the destructive reset/clean fallback below.
        print("Cleaning workspace...")
>       success, error = run_sase_hg_clean(
            workspace_dir, f"{cl_name}-{backup_suffix}", workspace_num=workspace_num
        )
E       TypeError: test_prepare_workspace_rescues_unpushed_bead_commits_before_sidecar_reset.<locals>.<lambda>() got an unexpected keyword argument 'workspace_num'

src/sase/axe/runner_workspace_prepare.py:215: TypeError
----------------------------- Captured stdout call -----------------------------
Found 1 unpushed local bead commit(s) in /var/tmp/sase-d00a07ab/pytest-of-bryan/pytest-22/popen-gw7/test_prepare_workspace_rescues0/claim-soak-local; publishing before workspace cleanup...
Cleaning workspace...
----------------------------- Captured stderr call -----------------------------
Warning: retained 1 unpublished local bead commit(s) at refs/sase/recovery/20261028T075321Z-main-603c3773e2 before workspace cleanup; injected managed sync failure (managed sync log: /var/tmp/sase-d00a07ab/pytest-of-bryan/pytest-22/popen-gw7/test_prepare_workspace_rescues0/failed-sync.log)
_ test_prepare_workspace_rescues_unpushed_bead_commits_before_sidecar_reset[repo-root] _
[gw7] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/.venv/bin/python

tmp_path = PosixPath('/var/tmp/sase-d00a07ab/pytest-of-bryan/pytest-22/popen-gw7/test_prepare_workspace_rescues1')
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7f0003e9d320>
beads_dirname = '.'

    @pytest.mark.parametrize(
        "beads_dirname",
        ["beads", BEADS_DIRNAME_ROOT],
        ids=["plans-embedded", "repo-root"],
    )
    def test_prepare_workspace_rescues_unpushed_bead_commits_before_sidecar_reset(
        tmp_path: Path,
        monkeypatch: pytest.MonkeyPatch,
        beads_dirname: str,
    ) -> None:
        _remote, local, upstream_writer, phase_ids = _seed_claim_soak_remote(
            tmp_path,
            phase_count=2,
            beads_dirname=beads_dirname,
        )
        local_phase, upstream_phase = phase_ids
        local_beads = local / beads_dirname
        upstream_beads = upstream_writer / beads_dirname
        with BeadProject(local, beads_dirname=beads_dirname) as project:
            _issue, changed = project.claim_for_agent_wait(local_phase, "local-agent")
        assert changed
        assert commit_bead_claim(local_beads, local_phase, "local-agent")
        local_commit = _git(local, "rev-parse", "HEAD").stdout.strip()
    
        with BeadProject(upstream_writer, beads_dirname=beads_dirname) as project:
            _issue, changed = project.claim_for_agent_wait(
                upstream_phase,
                "upstream-agent",
            )
        assert changed
        assert commit_bead_claim(
            upstream_beads,
            upstream_phase,
            "upstream-agent",
        )
        _git(upstream_writer, "push")
        _git(local, "fetch", "origin")
        assert unpushed_bead_commit_count(local, local_beads) == 1
    
        sync_log = tmp_path / "failed-sync.log"
        sync_attempts: list[Path] = []
    
        def fail_publish(beads_dir: Path, **kwargs: object) -> SimpleNamespace:
            sync_attempts.append(beads_dir)
            return SimpleNamespace(
                pushed=False,
                error="injected managed sync failure",
                log_path=sync_log,
            )
    
        class ResettingProvider:
            checkout_revisions: list[str]
    
            def __init__(self) -> None:
                self.checkout_revisions = []
    
            def get_default_parent_revision(self, cwd: str) -> str:
                return "origin/main"
    
            def checkout(self, revision: str, cwd: str) -> tuple[bool, str | None]:
                self.checkout_revisions.append(revision)
                _git(Path(cwd), "reset", "--hard", revision)
                return True, None
    
            def sync_workspace(self, cwd: str) -> tuple[bool, str | None]:
                return True, None
    
        provider = ResettingProvider()
        monkeypatch.setattr("sase.bead.sync.push_bead_work_launch", fail_publish)
        monkeypatch.setattr(
            "sase.workflows.commit_utils.run_sase_hg_clean",
            lambda *_args: (True, ""),
        )
        monkeypatch.setattr(
            "sase.axe.runner_workspace_prepare.get_vcs_provider",
            lambda _cwd: provider,
        )
    
        assert (
>           prepare_workspace(
                str(local),
                "sidecar",
                VCS_DEFAULT_REVISION,
            )
            is None
        )

tests/test_bead/test_sync_workspace_prepare_regressions.py:103: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
src/sase/axe/runner_workspace_prepare.py:115: in prepare_workspace
    _prepare_workspace_locked(
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

workspace_dir = '/var/tmp/sase-d00a07ab/pytest-of-bryan/pytest-22/popen-gw7/test_prepare_workspace_rescues1/claim-soak-local'
cl_name = 'sidecar', update_target = '__vcs_default__', backup_suffix = 'ace'
project_basename = '', self_heal = False, workspace_num = 1

    def _prepare_workspace_locked(
        workspace_dir: str,
        cl_name: str,
        update_target: str,
        backup_suffix: str,
        project_basename: str,
        *,
        self_heal: bool = False,
        workspace_num: int = 1,
    ) -> None:
        """Run the clean/checkout/sync pass that :func:`prepare_workspace` guards.
    
        Raises:
            WorkspacePreparationError: If any step fails, carrying the underlying
                failure text in ``reason``.
        """
    
        from sase.workflows.commit_utils import run_sase_hg_clean
    
        # An index.lock left behind by a crashed or SIGTERM-killed git process
        # blocks every subsequent operation in this clone ("Another git process
        # seems to be running..."), which would fail the clean/checkout below. This
        # runs against a workspace we have exclusively claimed, so a lock old enough
        # to predate the claim is abandoned; clear it as git itself instructs.
        clear_stale_git_index_lock(workspace_dir)
    
        if not protect_unpushed_sidecar_commits(workspace_dir, workspace_num=workspace_num):
            raise WorkspacePreparationError(
                "sidecar repos hold unpublished commits that could not be published "
                "before workspace cleanup (see diagnostics above)",
                step="sidecar-protection",
                workspace_dir=workspace_dir,
            )
    
        # The provider is resolved up front only for self-heal inspection; the
        # default path keeps today's order (clean before provider resolution) so
        # early clean failures keep their existing precedence.
        provider: VCSProvider | None = None
        inspection: CheckoutInspection | None = None
        if self_heal:
            # Self-heal inspection. Providers without the heal operations raise
            # NotImplementedError and preparation keeps today's behavior below.
            provider = get_vcs_provider(workspace_dir)
            try:
                inspection = provider.inspect_checkout(workspace_dir)
            except NotImplementedError:
                inspection = None
        healing = inspection is not None
        rescued: RescueRecord | None = None
        if inspection is not None and provider is not None:
            rescued = rescue_heal_state(workspace_dir, workspace_num, inspection)
            if inspection.operations:
                require_verified_snapshot(
                    workspace_dir,
                    workspace_num,
                    label="abort",
                    reason=(
                        "self-heal: preserving before aborting "
                        f"{', '.join(inspection.operations)}"
                    ),
                    step="heal",
                )
                try:
                    abort_ok, abort_err = provider.abort_in_progress_operations(
                        workspace_dir
                    )
                except NotImplementedError:
                    abort_ok, abort_err = True, None
                if not abort_ok:
                    reason = (
                        "could not abort in-progress git operations: "
                        f"{abort_err or 'unknown error'}"
                    )
                    print(reason, file=sys.stderr)
                    raise WorkspacePreparationError(
                        reason,
                        step="heal",
                        workspace_dir=workspace_dir,
                        reclone_eligible=True,
                    )
                for label in inspection.operations:
                    print(f"Aborted stale {label} in {workspace_dir}")
    
        # Clean workspace (saves any existing changes to a diff file).
        # run_sase_hg_clean captures a verified snapshot before its stash, so
        # normal launches and direct callers obtain durable preservation before
        # the first source-mutating cleanup. A preservation failure must not
        # fall through to the destructive reset/clean fallback below.
        print("Cleaning workspace...")
>       success, error = run_sase_hg_clean(
            workspace_dir, f"{cl_name}-{backup_suffix}", workspace_num=workspace_num
        )
E       TypeError: test_prepare_workspace_rescues_unpushed_bead_commits_before_sidecar_reset.<locals>.<lambda>() got an unexpected keyword argument 'workspace_num'

src/sase/axe/runner_workspace_prepare.py:215: TypeError
----------------------------- Captured stdout call -----------------------------
Found 1 unpushed local bead commit(s) in /var/tmp/sase-d00a07ab/pytest-of-bryan/pytest-22/popen-gw7/test_prepare_workspace_rescues1/claim-soak-local; publishing before workspace cleanup...
Cleaning workspace...
----------------------------- Captured stderr call -----------------------------
Warning: retained 1 unpublished local bead commit(s) at refs/sase/recovery/20261028T075329Z-main-23a5d24e97 before workspace cleanup; injected managed sync failure (managed sync log: /var/tmp/sase-d00a07ab/pytest-of-bryan/pytest-22/popen-gw7/test_prepare_workspace_rescues1/failed-sync.log)
__________ test_eviction_quarantines_unborn_head_sidecar_and_reclones __________
[gw7] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/.venv/bin/python

parent_root = '/var/tmp/sase-d00a07ab/pytest-of-bryan/pytest-22/popen-gw7/test_eviction_quarantines_unbo0/project_7'
workspace_dir = '/var/tmp/sase-d00a07ab/pytest-of-bryan/pytest-22/popen-gw7/test_eviction_quarantines_unbo0/project_7'
workspace_num = 7
reason = 'launch-time eviction: nested repository preservation', within = ()
already_proven = ()

    def preserve_nested_repositories(
        parent_root: str | Path,
        *,
        workspace_dir: str | Path,
        workspace_num: int,
        reason: str,
        within: Sequence[str | Path] = (),
        already_proven: Sequence[str | Path] = (),
    ) -> NestedPreservation:
        """Snapshot every nested git checkout that a removal is about to destroy.
    
        Returns locators for captured dirty trees. A nested checkout whose
        snapshot returns ``None`` is a proven no-work tree. Enumeration or
        capture failure raises :class:`NestedPreservationError` and must not be
        treated as permission to delete. Locators captured before a later
        failure are attached to the error.
        """
        parent = Path(parent_root).expanduser()
        proven = {Path(path).expanduser().resolve(strict=False) for path in already_proven}
        roots = discover_nested_git_repos(parent, within=within)
        locations: list[str] = []
        kept: list[Path] = []
        for root in roots:
            resolved = root.resolve(strict=False)
            if resolved in proven:
                continue
            kept.append(root)
            try:
>               record = snapshot_git_repo(
                    root,
                    workspace_dir=workspace_dir,
                    workspace_num=workspace_num,
                    label=_label_for(root, parent),
                    reason=reason,
                )

src/sase/workspace_provider/_snapshot_nested.py:61: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
src/sase/workspace_provider/_snapshot_capture.py:67: in snapshot_git_repo
    return _snapshot_git_repo(
src/sase/workspace_provider/_snapshot_capture.py:104: in _snapshot_git_repo
    state = read_source_state(repo_root)
            ^^^^^^^^^^^^^^^^^^^^^^^^^^^^
src/sase/workspace_provider/_snapshot_capture.py:155: in read_source_state
    head = git_output(repo_root, "rev-parse", "--verify", "HEAD")
           ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

cwd = PosixPath('/var/tmp/sase-d00a07ab/pytest-of-bryan/pytest-22/popen-gw7/test_eviction_quarantines_unbo0/project_7/sase/repos/plans')
env = None, args = ('rev-parse', '--verify', 'HEAD')

    def git_output(cwd: Path, *args: str, env: dict[str, str] | None = None) -> str:
        result = run_git_bytes(cwd, *args, env=env)
        if result.returncode != 0:
            detail = _err_text(result)
>           raise PreservationError(f"git {' '.join(args)} failed: {detail}")
E           sase.workspace_provider._snapshot_model.PreservationError: git rev-parse --verify HEAD failed: fatal: Needed a single revision

src/sase/workspace_provider/_snapshot_git.py:68: PreservationError

The above exception was the direct cause of the following exception:

workspace_dir = '/var/tmp/sase-d00a07ab/pytest-of-bryan/pytest-22/popen-gw7/test_eviction_quarantines_unbo0/project_7'
workspace_num = 7

    def prepare_launch_workspace_repos(
        workspace_dir: str,
        workspace_num: int,
    ) -> frozenset[str]:
        """Evict launch-scoped repos and strictly recreate required sidecars.
    
        The returned paths identify sidecars proven to have been freshly cloned by
        this launch, so later linked-repo setup can reuse them without another
        materialization or synchronization pass.
    
        Launch-time sidecar protection publishes once, rescues unpublishable
        state to the durable rescue store outside the workspace, and always
        proceeds with eviction: leftover state from an earlier run never fails a
        new launch.
        """
        from sase.axe.runner_workspace_errors import WorkspacePreparationError
        from sase.linked_repos import clear_workspace_repos
        from sase.workspace_provider.snapshot import (
            NestedPreservationError,
            PreservationError,
            format_preservation_locations,
            preserve_nested_repositories,
        )
    
        # Only numbered workspaces evict sidecars; the primary checkout's clones
        # survive ``clear_workspace_repos`` untouched.
        if workspace_num > 1:
            try:
>               nested = preserve_nested_repositories(
                    workspace_dir,
                    workspace_dir=workspace_dir,
                    workspace_num=workspace_num,
                    reason="launch-time eviction: nested repository preservation",
                )

src/sase/axe/runner_workspace_protection.py:231: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

parent_root = '/var/tmp/sase-d00a07ab/pytest-of-bryan/pytest-22/popen-gw7/test_eviction_quarantines_unbo0/project_7'
workspace_dir = '/var/tmp/sase-d00a07ab/pytest-of-bryan/pytest-22/popen-gw7/test_eviction_quarantines_unbo0/project_7'
workspace_num = 7
reason = 'launch-time eviction: nested repository preservation', within = ()
already_proven = ()

    def preserve_nested_repositories(
        parent_root: str | Path,
        *,
        workspace_dir: str | Path,
        workspace_num: int,
        reason: str,
        within: Sequence[str | Path] = (),
        already_proven: Sequence[str | Path] = (),
    ) -> NestedPreservation:
        """Snapshot every nested git checkout that a removal is about to destroy.
    
        Returns locators for captured dirty trees. A nested checkout whose
        snapshot returns ``None`` is a proven no-work tree. Enumeration or
        capture failure raises :class:`NestedPreservationError` and must not be
        treated as permission to delete. Locators captured before a later
        failure are attached to the error.
        """
        parent = Path(parent_root).expanduser()
        proven = {Path(path).expanduser().resolve(strict=False) for path in already_proven}
        roots = discover_nested_git_repos(parent, within=within)
        locations: list[str] = []
        kept: list[Path] = []
        for root in roots:
            resolved = root.resolve(strict=False)
            if resolved in proven:
                continue
            kept.append(root)
            try:
                record = snapshot_git_repo(
                    root,
                    workspace_dir=workspace_dir,
                    workspace_num=workspace_num,
                    label=_label_for(root, parent),
                    reason=reason,
                )
            except PreservationError as exc:
>               raise NestedPreservationError(
                    f"could not preserve nested repository {root}: {exc}",
                    locations=locations,
                ) from exc
E               sase.workspace_provider._snapshot_model.NestedPreservationError: could not preserve nested repository /var/tmp/sase-d00a07ab/pytest-of-bryan/pytest-22/popen-gw7/test_eviction_quarantines_unbo0/project_7/sase/repos/plans: git rev-parse --verify HEAD failed: fatal: Needed a single revision

src/sase/workspace_provider/_snapshot_nested.py:69: NestedPreservationError

The above exception was the direct cause of the following exception:

tmp_path = PosixPath('/var/tmp/sase-d00a07ab/pytest-of-bryan/pytest-22/popen-gw7/test_eviction_quarantines_unbo0')
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7effdf4764a0>

    def test_eviction_quarantines_unborn_head_sidecar_and_reclones(
        tmp_path: Path,
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        workspace, plans, _remote = _seed_workspace_sidecar_repo(tmp_path)
        _damage_sidecar_unborn_head(plans)
        home, notified = _redirect_state(tmp_path, monkeypatch)
        clones: list[tuple[str, int, bool]] = []
    
        def recreate_plans_sidecar(
            workspace_dir: str, workspace_num: int, *, strict: bool = False
        ) -> None:
            clones.append((workspace_dir, workspace_num, strict))
            fresh = Path(workspace_dir) / "sase" / "repos" / "plans"
            fresh.mkdir(parents=True)
            init_git_repo(fresh)
    
        monkeypatch.setattr(
            "sase.sdd.store.ensure_workspace_sdd_clone",
            recreate_plans_sidecar,
        )
    
>       cloned_sidecars = prepare_launch_workspace_repos(str(workspace), _WORKSPACE_NUM)
                          ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

tests/test_bead/test_workspace_sidecar_eviction_plans.py:60: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

workspace_dir = '/var/tmp/sase-d00a07ab/pytest-of-bryan/pytest-22/popen-gw7/test_eviction_quarantines_unbo0/project_7'
workspace_num = 7

    def prepare_launch_workspace_repos(
        workspace_dir: str,
        workspace_num: int,
    ) -> frozenset[str]:
        """Evict launch-scoped repos and strictly recreate required sidecars.
    
        The returned paths identify sidecars proven to have been freshly cloned by
        this launch, so later linked-repo setup can reuse them without another
        materialization or synchronization pass.
    
        Launch-time sidecar protection publishes once, rescues unpublishable
        state to the durable rescue store outside the workspace, and always
        proceeds with eviction: leftover state from an earlier run never fails a
        new launch.
        """
        from sase.axe.runner_workspace_errors import WorkspacePreparationError
        from sase.linked_repos import clear_workspace_repos
        from sase.workspace_provider.snapshot import (
            NestedPreservationError,
            PreservationError,
            format_preservation_locations,
            preserve_nested_repositories,
        )
    
        # Only numbered workspaces evict sidecars; the primary checkout's clones
        # survive ``clear_workspace_repos`` untouched.
        if workspace_num > 1:
            try:
                nested = preserve_nested_repositories(
                    workspace_dir,
                    workspace_dir=workspace_dir,
                    workspace_num=workspace_num,
                    reason="launch-time eviction: nested repository preservation",
                )
            except NestedPreservationError as exc:
                loc = format_preservation_locations(exc.locations)
>               raise WorkspacePreparationError(
                    "verified nested preservation failed before launch eviction: "
                    f"{exc}{loc}",
                    step="sidecar-protection",
                    workspace_dir=str(workspace_dir),
                    reclone_eligible=False,
                ) from exc
E               sase.axe.runner_workspace_errors.WorkspacePreparationError: Failed to prepare workspace /var/tmp/sase-d00a07ab/pytest-of-bryan/pytest-22/popen-gw7/test_eviction_quarantines_unbo0/project_7 during sidecar-protection: verified nested preservation failed before launch eviction: could not preserve nested repository /var/tmp/sase-d00a07ab/pytest-of-bryan/pytest-22/popen-gw7/test_eviction_quarantines_unbo0/project_7/sase/repos/plans: git rev-parse --verify HEAD failed: fatal: Needed a single revision

src/sase/axe/runner_workspace_protection.py:239: WorkspacePreparationError
_________ test_eviction_proceeds_when_damaged_sidecar_quarantine_fails _________
[gw7] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/.venv/bin/python

parent_root = '/var/tmp/sase-d00a07ab/pytest-of-bryan/pytest-22/popen-gw7/test_eviction_proceeds_when_da0/project_7'
workspace_dir = '/var/tmp/sase-d00a07ab/pytest-of-bryan/pytest-22/popen-gw7/test_eviction_proceeds_when_da0/project_7'
workspace_num = 7
reason = 'launch-time eviction: nested repository preservation', within = ()
already_proven = ()

    def preserve_nested_repositories(
        parent_root: str | Path,
        *,
        workspace_dir: str | Path,
        workspace_num: int,
        reason: str,
        within: Sequence[str | Path] = (),
        already_proven: Sequence[str | Path] = (),
    ) -> NestedPreservation:
        """Snapshot every nested git checkout that a removal is about to destroy.
    
        Returns locators for captured dirty trees. A nested checkout whose
        snapshot returns ``None`` is a proven no-work tree. Enumeration or
        capture failure raises :class:`NestedPreservationError` and must not be
        treated as permission to delete. Locators captured before a later
        failure are attached to the error.
        """
        parent = Path(parent_root).expanduser()
        proven = {Path(path).expanduser().resolve(strict=False) for path in already_proven}
        roots = discover_nested_git_repos(parent, within=within)
        locations: list[str] = []
        kept: list[Path] = []
        for root in roots:
            resolved = root.resolve(strict=False)
            if resolved in proven:
                continue
            kept.append(root)
            try:
>               record = snapshot_git_repo(
                    root,
                    workspace_dir=workspace_dir,
                    workspace_num=workspace_num,
                    label=_label_for(root, parent),
                    reason=reason,
                )

src/sase/workspace_provider/_snapshot_nested.py:61: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
src/sase/workspace_provider/_snapshot_capture.py:67: in snapshot_git_repo
    return _snapshot_git_repo(
src/sase/workspace_provider/_snapshot_capture.py:104: in _snapshot_git_repo
    state = read_source_state(repo_root)
            ^^^^^^^^^^^^^^^^^^^^^^^^^^^^
src/sase/workspace_provider/_snapshot_capture.py:155: in read_source_state
    head = git_output(repo_root, "rev-parse", "--verify", "HEAD")
           ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

cwd = PosixPath('/var/tmp/sase-d00a07ab/pytest-of-bryan/pytest-22/popen-gw7/test_eviction_proceeds_when_da0/project_7/sase/repos/plans')
env = None, args = ('rev-parse', '--verify', 'HEAD')

    def git_output(cwd: Path, *args: str, env: dict[str, str] | None = None) -> str:
        result = run_git_bytes(cwd, *args, env=env)
        if result.returncode != 0:
            detail = _err_text(result)
>           raise PreservationError(f"git {' '.join(args)} failed: {detail}")
E           sase.workspace_provider._snapshot_model.PreservationError: git rev-parse --verify HEAD failed: fatal: Needed a single revision

src/sase/workspace_provider/_snapshot_git.py:68: PreservationError

The above exception was the direct cause of the following exception:

workspace_dir = '/var/tmp/sase-d00a07ab/pytest-of-bryan/pytest-22/popen-gw7/test_eviction_proceeds_when_da0/project_7'
workspace_num = 7

    def prepare_launch_workspace_repos(
        workspace_dir: str,
        workspace_num: int,
    ) -> frozenset[str]:
        """Evict launch-scoped repos and strictly recreate required sidecars.
    
        The returned paths identify sidecars proven to have been freshly cloned by
        this launch, so later linked-repo setup can reuse them without another
        materialization or synchronization pass.
    
        Launch-time sidecar protection publishes once, rescues unpublishable
        state to the durable rescue store outside the workspace, and always
        proceeds with eviction: leftover state from an earlier run never fails a
        new launch.
        """
        from sase.axe.runner_workspace_errors import WorkspacePreparationError
        from sase.linked_repos import clear_workspace_repos
        from sase.workspace_provider.snapshot import (
            NestedPreservationError,
            PreservationError,
            format_preservation_locations,
            preserve_nested_repositories,
        )
    
        # Only numbered workspaces evict sidecars; the primary checkout's clones
        # survive ``clear_workspace_repos`` untouched.
        if workspace_num > 1:
            try:
>               nested = preserve_nested_repositories(
                    workspace_dir,
                    workspace_dir=workspace_dir,
                    workspace_num=workspace_num,
                    reason="launch-time eviction: nested repository preservation",
                )

src/sase/axe/runner_workspace_protection.py:231: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

parent_root = '/var/tmp/sase-d00a07ab/pytest-of-bryan/pytest-22/popen-gw7/test_eviction_proceeds_when_da0/project_7'
workspace_dir = '/var/tmp/sase-d00a07ab/pytest-of-bryan/pytest-22/popen-gw7/test_eviction_proceeds_when_da0/project_7'
workspace_num = 7
reason = 'launch-time eviction: nested repository preservation', within = ()
already_proven = ()

    def preserve_nested_repositories(
        parent_root: str | Path,
        *,
        workspace_dir: str | Path,
        workspace_num: int,
        reason: str,
        within: Sequence[str | Path] = (),
        already_proven: Sequence[str | Path] = (),
    ) -> NestedPreservation:
        """Snapshot every nested git checkout that a removal is about to destroy.
    
        Returns locators for captured dirty trees. A nested checkout whose
        snapshot returns ``None`` is a proven no-work tree. Enumeration or
        capture failure raises :class:`NestedPreservationError` and must not be
        treated as permission to delete. Locators captured before a later
        failure are attached to the error.
        """
        parent = Path(parent_root).expanduser()
        proven = {Path(path).expanduser().resolve(strict=False) for path in already_proven}
        roots = discover_nested_git_repos(parent, within=within)
        locations: list[str] = []
        kept: list[Path] = []
        for root in roots:
            resolved = root.resolve(strict=False)
            if resolved in proven:
                continue
            kept.append(root)
            try:
                record = snapshot_git_repo(
                    root,
                    workspace_dir=workspace_dir,
                    workspace_num=workspace_num,
                    label=_label_for(root, parent),
                    reason=reason,
                )
            except PreservationError as exc:
>               raise NestedPreservationError(
                    f"could not preserve nested repository {root}: {exc}",
                    locations=locations,
                ) from exc
E               sase.workspace_provider._snapshot_model.NestedPreservationError: could not preserve nested repository /var/tmp/sase-d00a07ab/pytest-of-bryan/pytest-22/popen-gw7/test_eviction_proceeds_when_da0/project_7/sase/repos/plans: git rev-parse --verify HEAD failed: fatal: Needed a single revision

src/sase/workspace_provider/_snapshot_nested.py:69: NestedPreservationError

The above exception was the direct cause of the following exception:

tmp_path = PosixPath('/var/tmp/sase-d00a07ab/pytest-of-bryan/pytest-22/popen-gw7/test_eviction_proceeds_when_da0')
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7effdf475ef0>
capsys = <_pytest.capture.CaptureFixture object at 0x7effdc37e8d0>

    def test_eviction_proceeds_when_damaged_sidecar_quarantine_fails(
        tmp_path: Path,
        monkeypatch: pytest.MonkeyPatch,
        capsys: pytest.CaptureFixture[str],
    ) -> None:
        workspace, plans, _remote = _seed_workspace_sidecar_repo(tmp_path)
        _damage_sidecar_unborn_head(plans)
        _home, notified = _redirect_state(tmp_path, monkeypatch)
        clones: list[tuple[str, int, bool]] = []
        monkeypatch.setattr(
            "sase.workspace_provider.rescue.quarantine_directory",
            lambda *_args, **_kwargs: None,
        )
        monkeypatch.setattr(
            "sase.sdd.store.ensure_workspace_sdd_clone",
            _record_clone(clones),
        )
    
>       prepare_launch_workspace_repos(str(workspace), _WORKSPACE_NUM)

tests/test_bead/test_workspace_sidecar_eviction_plans.py:98: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

workspace_dir = '/var/tmp/sase-d00a07ab/pytest-of-bryan/pytest-22/popen-gw7/test_eviction_proceeds_when_da0/project_7'
workspace_num = 7

    def prepare_launch_workspace_repos(
        workspace_dir: str,
        workspace_num: int,
    ) -> frozenset[str]:
        """Evict launch-scoped repos and strictly recreate required sidecars.
    
        The returned paths identify sidecars proven to have been freshly cloned by
        this launch, so later linked-repo setup can reuse them without another
        materialization or synchronization pass.
    
        Launch-time sidecar protection publishes once, rescues unpublishable
        state to the durable rescue store outside the workspace, and always
        proceeds with eviction: leftover state from an earlier run never fails a
        new launch.
        """
        from sase.axe.runner_workspace_errors import WorkspacePreparationError
        from sase.linked_repos import clear_workspace_repos
        from sase.workspace_provider.snapshot import (
            NestedPreservationError,
            PreservationError,
            format_preservation_locations,
            preserve_nested_repositories,
        )
    
        # Only numbered workspaces evict sidecars; the primary checkout's clones
        # survive ``clear_workspace_repos`` untouched.
        if workspace_num > 1:
            try:
                nested = preserve_nested_repositories(
                    workspace_dir,
                    workspace_dir=workspace_dir,
                    workspace_num=workspace_num,
                    reason="launch-time eviction: nested repository preservation",
                )
            except NestedPreservationError as exc:
                loc = format_preservation_locations(exc.locations)
>               raise WorkspacePreparationError(
                    "verified nested preservation failed before launch eviction: "
                    f"{exc}{loc}",
                    step="sidecar-protection",
                    workspace_dir=str(workspace_dir),
                    reclone_eligible=False,
                ) from exc
E               sase.axe.runner_workspace_errors.WorkspacePreparationError: Failed to prepare workspace /var/tmp/sase-d00a07ab/pytest-of-bryan/pytest-22/popen-gw7/test_eviction_proceeds_when_da0/project_7 during sidecar-protection: verified nested preservation failed before launch eviction: could not preserve nested repository /var/tmp/sase-d00a07ab/pytest-of-bryan/pytest-22/popen-gw7/test_eviction_proceeds_when_da0/project_7/sase/repos/plans: git rev-parse --verify HEAD failed: fatal: Needed a single revision

src/sase/axe/runner_workspace_protection.py:239: WorkspacePreparationError
_____________ test_artifact_directory_operation_sites_are_reviewed _____________
[gw8] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/.venv/bin/python

    def test_artifact_directory_operation_sites_are_reviewed() -> None:
>       assert set(_artifact_directory_operation_contexts()) == set(
            _REVIEWED_DIR_OPERATION_CONTEXTS
        )
E       AssertionError: assert {'src/sase/_l...migrate', ...} == {'src/sase/_l...migrate', ...}
E         
E         Extra items in the left set:
E         'src/sase/workspace_provider/_snapshot_restore.py:_clear_worktree'
E         'src/sase/workspace_provider/_snapshot_capture.py:_verify_pack'
E         'src/sase/workspace_provider/_snapshot_restore.py:_restore_operation_markers'
E         'src/sase/workspace_provider/_snapshot_capture.py:_discard_incomplete'
E         'src/sase/workspace_provider/_snapshot_capture.py:_cleanup_capture_temps'
E         
E         Full diff:
E           {
E               'src/sase/_linked_repo_workspaces.py:_remove_path',
E               'src/sase/_linked_repo_workspaces.py:clear_workspace_repos',
E               'src/sase/_linked_repo_workspaces.py:move_aside_for_background_delete',
E               'src/sase/ace/tui/bgcmd.py:dismiss_background_command',
E               'src/sase/agent/names/_wipe_execute.py:_remove_artifact_dirs',
E               'src/sase/agents/cli_artifacts_layout.py:_handle_migrate',
E               'src/sase/agents/cli_artifacts_layout.py:_handle_rollback',
E               'src/sase/agents_sync/_git_sync_ops_git.py:ensure_agents_clone',
E               'src/sase/agents_sync/purge_local_state.py:_apply_closure',
E               'src/sase/agents_sync/v2_io.py:_cleanup_transaction_dirs',
E               'src/sase/axe/run_agent_exec_attempts.py:_move_into_tmp',
E               'src/sase/axe/run_agent_exec_attempts.py:snapshot_attempt',
E               'src/sase/bead/attachments/lifecycle.py:quarantine_local_object',
E               'src/sase/bead/attachments/store.py:remove',
E               'src/sase/dev_update/prebuild_producer.py:_prune_completed_sets',
E               'src/sase/dev_update/prebuild_producer.py:produce_prebuild',
E               'src/sase/llm_provider/_codex_home.py:_try_delete_shadow_home',
E               'src/sase/llm_provider/_plan_utils.py:move_plan_to_sase',
E               'src/sase/main/project_handler_lifecycle.py:delete_project_locked',
E               'src/sase/main/repo_open_external.py:_remove_clone_staging_path',
E               'src/sase/main/workspace_handler_maintenance.py:remove_checkout',
E               'src/sase/main/workspace_handler_migration.py:handle_migrate',
E               'src/sase/migration_kit/atomic.py:_remove_path',
E               'src/sase/migration_kit/atomic.py:remove_path',
E               'src/sase/migration_kit/restore.py:_swap_into_place',
E               'src/sase/mode_switch/execute.py:_cleanup_failed_clone',
E               'src/sase/notification_gates/command_runner.py:_remove_untrusted_terminal',
E               'src/sase/notification_gates/service_creation.py:_start_gate_creation',
E               'src/sase/notification_gates/service_creation.py:create_gate',
E               'src/sase/procs/_migration.py:_perform_migration',
E               'src/sase/procs/_migration.py:_relocate_legacy_logs',
E               'src/sase/sdd/_bead_adoption.py:_copy_bead_state',
E               'src/sase/sdd/_bead_adoption.py:cleanup_plans_bead_state',
E               'src/sase/sdd/_store_adoption.py:cleanup_staging',
E               'src/sase/sdd/_store_clone_common.py:remove_partial_sdd_clone',
E               'src/sase/sdd/_store_clone_transaction.py:_remove_clone_stage_path',
E               'src/sase/sdd/_store_link.py:_replace_workspace_sdd_clone',
E               'src/sase/sudo/execution_handoff.py:cleanup_handoff',
E               'src/sase/workspace_provider/_rescue_git.py:_rescue_git_repo_body',
E               'src/sase/workspace_provider/_rescue_store.py:_quarantine_directory',
E               'src/sase/workspace_provider/_rescue_store.py:_reap_rescue_entries',
E         +     'src/sase/workspace_provider/_snapshot_capture.py:_cleanup_capture_temps',
E         +     'src/sase/workspace_provider/_snapshot_capture.py:_discard_incomplete',
E         +     'src/sase/workspace_provider/_snapshot_capture.py:_verify_pack',
E         +     'src/sase/workspace_provider/_snapshot_restore.py:_clear_worktree',
E         +     'src/sase/workspace_provider/_snapshot_restore.py:_restore_operation_markers',
E               'src/sase/workspace_provider/_utils_checkout.py:_remove_corrupt_checkout',
E               'src/sase/workspace_provider/_utils_git.py:abort_in_progress_git_operations',
E               'src/sase/workspace_provider/reset_replay.py:_clear_owned_paths',
E           }

tests/test_agent_artifact_directory_operation_audit.py:319: AssertionError
________________ test_tui_app_import_stays_under_startup_budget ________________
[gw1] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/.venv/bin/python

    def test_tui_app_import_stays_under_startup_budget() -> None:
        """Importing the app should not pull known heavy deferred profile edges."""
    
        last_elapsed = 0.0
        last_count = 0
        for _ in range(2):
>           payload = _measure_tui_app_import()
                      ^^^^^^^^^^^^^^^^^^^^^^^^^

tests/ace/tui/test_app_import_budget.py:124: 
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
E       AssertionError: TUI app import loads 3549 modules against the 3539 cap; attribute the growth with `tools/tui_import_closure --diff $(git merge-base HEAD origin/master)` and defer the new edges
E       assert 3549 < 3539

tests/ace/tui/test_app_import_budget.py:109: AssertionError
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
  /home/bryan/.local/share/uv/python/cpython-3.14.7-linux-x86_64-gnu/lib/python3.14/weakref.py:239: RuntimeWarning: coroutine '_run_archive_request' was never awaited
    other = dict(other)
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

tests/test_procs_supervisor.py::test_starter_exit_does_not_kill_a_released_proc
  <frozen os>:898: DeprecationWarning: This process (pid=3422139) is multi-threaded, use of fork() may lead to deadlocks in the child.

tests/sdd/test_artifact_link_event_acceptance_process_death.py::test_real_killed_publisher_process_leaves_no_corrupt_object_and_recovers
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/tests/sdd/test_artifact_link_event_acceptance_process_death.py:57: DeprecationWarning: This process (pid=3422067) is multi-threaded, use of fork() may lead to deadlocks in the child.
    child = os.fork()

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

tests/ace/tui/command_line/test_completion_fixes.py::test_cursor_move_during_a_fetch_drops_the_result
tests/ace/tui/command_line/test_panel_shell_pilot.py::test_real_input_history_filters_prefix_and_resets_new_walk
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/src/sase/legacy_xprompt_syntax.py:94: RuntimeWarning: coroutine '_record_history_async.<locals>._record' was never awaited
    result = binding(
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_home_mode_running_marker_cleanup_updates_artifact_index
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_home_mode_running_marker_cleanup_updates_artifact_index changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14' to '<deleted>'; restored it.
    next(it)

tests/test_axe_runner_workspace_reclone.py::TestRecreateEndToEnd::test_forced_verify_failure_recreates_then_launch_prep_succeeds
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_runner_workspace_reclone.py::TestRecreateEndToEnd::test_forced_verify_failure_recreates_then_launch_prep_succeeds changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14' to '<deleted>'; restored it.
    next(it)

tests/test_notification_modal_tab_order.py::test_on_mount_highlights_first_visible_row_when_initial_is_hidden
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/src/sase/ace/tui/modals/notification_modal_snooze_status.py:136: RuntimeWarning: coroutine 'Timer._run_timer' was never awaited
    self._snooze_status_timer = None
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/ace/tui/command_line/test_panel_shell_pilot.py::test_grammar_ready_refreshes_open_empty_panel_without_a_keystroke
  /home/bryan/.local/share/uv/python/cpython-3.14.7-linux-x86_64-gnu/lib/python3.14/copy.py:189: RuntimeWarning: coroutine '_recheck_grammar_key' was never awaited
    for k, j in zip(x, y):
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
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/src/sase/legacy_xprompt_syntax.py:94: RuntimeWarning: coroutine 'CommandLineScreenSubmissionMixin._submit_worker' was never awaited
    result = binding(
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

tests/history/test_continuation_replay_hydration_retry.py::test_retry_then_fork_replay_end_to_end
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/history/test_continuation_replay_hydration_retry.py::test_retry_then_fork_replay_end_to_end changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14' to '<deleted>'; restored it.
    next(it)

tests/test_run_agent_runner_clan_summary_refresh.py::test_unsuccessful_post_preparation_summary_keeps_earlier_success
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_run_agent_runner_clan_summary_refresh.py::test_unsuccessful_post_preparation_summary_keeps_earlier_success changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14' to '<deleted>'; restored it.
    next(it)

tests/ace/tui/command_line/test_transcript_blocks_keys.py::test_r_reruns_and_R_is_limited_to_declined_blocks
  /home/bryan/.local/share/uv/python/cpython-3.14.7-linux-x86_64-gnu/lib/python3.14/json/decoder.py:361: RuntimeWarning: coroutine 'CommandLineScreenSubmissionMixin._submit_worker' was never awaited
    obj, end = self.scan_once(s, idx)
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

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

tests/completion/test_zsh_smoke.py: 18 warnings
  /home/bryan/.local/share/uv/python/cpython-3.14.7-linux-x86_64-gnu/lib/python3.14/pty.py:66: DeprecationWarning: This process (pid=3422002) is multi-threaded, use of forkpty() may lead to deadlocks in the child.
    pid, fd = os.forkpty()

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

tests/ace/tui/test_dismissed_index_startup_sync.py::test_start_post_mount_background_loads_schedules_dismissed_sync_once
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/src/sase/ace/tui/actions/_launchable_mru.py:304: RuntimeWarning: coroutine 'Timer._run_timer' was never awaited
    log.debug("Launchable MRU tick not armed", exc_info=True)
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

-- Docs: https://docs.pytest.org/en/stable/how-to/capture-warnings.html
============================= slowest 20 durations =============================
66.13s call     tests/test_contract_manifest.py::test_contract_manifest_matches_marker_selection
61.00s call     tests/sdd/test_git_identity_fixture.py::test_sdd_git_identity_survives_empty_home_subprocess
57.74s call     tests/test_check_feature_flags_tool_run.py::test_static_main_ignores_exploding_bd_command
55.28s call     tests/test_check_feature_flags_tool_run.py::test_main_static_on_repo_exits_zero
44.05s call     tests/history/test_continuation_replay_hydration_basic.py::test_hundred_handoff_from_final_monitor_result_grows_linearly
30.92s call     tests/test_agent_artifact_directory_operation_audit.py::test_artifact_directory_operation_sites_are_reviewed
27.24s call     tests/pager/test_rendered_link_contract.py::test_kitchen_follow_copy_edit_and_media_for_each_supported_action
25.54s call     tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_lowercase_picks_this_panel_capital_picks_other
20.68s call     tests/test_bead/test_sync_remote_worker.py::test_managed_sync_worker_converges_sidecar_store_mutations
20.36s call     tests/ace/tui/test_deleted_proc_queue_imports.py::test_tests_do_not_import_deleted_proc_queue_module
19.88s call     tests/test_project_display_presentation_audit.py::test_display_fallback_exemptions_name_existing_sites_and_rationales
19.20s call     tests/test_project_display_presentation_audit.py::test_project_display_name_fallback_lives_only_in_chokepoint
15.41s call     tests/test_sdd_commit.py::test_commit_sdd_files_removes_persistent_index_lock_after_retry_exhausted
15.35s call     tests/test_bare_git_init.py::TestInitBareGitProject::test_git_runner_removes_persistent_index_lock_after_retries
14.97s call     tests/tool/test_inline_escalation.py::test_slow_command_escalates_and_wait_returns_exit
14.60s call     tests/workspace_provider/test_primary_writable_store_import_boundary.py::test_writable_store_resolution_importers_match_the_audited_allowlist
14.07s call     tests/test_markdown_print_width.py::test_no_function_parameter_defaults_to_the_width
13.96s call     tests/ace/tui/test_agents_filter_bar_session.py::test_circumflex_history_replaces_the_live_edit_while_the_bar_is_open
13.25s call     tests/instructions/test_invoke_boundary.py::test_only_boundary_calls_provider_invoke
12.92s call     tests/test_proc_submission_static_invariants.py::test_production_proc_writers_do_not_emit_legacy_kinds
=========================== short test summary info ============================
FAILED tests/test_axe_runner_workspace_agents_lock.py::test_prepare_workspace_holds_agents_lock_across_the_clean - TypeError: test_prepare_workspace_holds_agents_lock_across_the_clean.<locals>._clean() got an unexpected keyword argument 'workspace_num'. Did you mean 'workspace_dir'?
FAILED tests/test_axe_runner_workspace_agents_lock.py::test_prepare_workspace_leaves_workspace_scoped_agents_clone_unguarded - TypeError: test_prepare_workspace_leaves_workspace_scoped_agents_clone_unguarded.<locals>._clean() got an unexpected keyword argument 'workspace_num'. Did you mean 'workspace_dir'?
FAILED tests/test_bead/test_sync_workspace_prepare_regressions.py::test_prepare_workspace_rescues_unpushed_bead_commits_before_sidecar_reset[plans-embedded] - TypeError: test_prepare_workspace_rescues_unpushed_bead_commits_before_sidecar_reset.<locals>.<lambda>() got an unexpected keyword argument 'workspace_num'
FAILED tests/test_bead/test_sync_workspace_prepare_regressions.py::test_prepare_workspace_rescues_unpushed_bead_commits_before_sidecar_reset[repo-root] - TypeError: test_prepare_workspace_rescues_unpushed_bead_commits_before_sidecar_reset.<locals>.<lambda>() got an unexpected keyword argument 'workspace_num'
FAILED tests/test_bead/test_workspace_sidecar_eviction_plans.py::test_eviction_quarantines_unborn_head_sidecar_and_reclones - sase.axe.runner_workspace_errors.WorkspacePreparationError: Failed to prepare workspace /var/tmp/sase-d00a07ab/pytest-of-bryan/pytest-22/popen-gw7/test_eviction_quarantines_unbo0/project_7 during sidecar-protection: verified nested preservation failed before launch eviction: could not preserve nested repository /var/tmp/sase-d00a07ab/pytest-of-bryan/pytest-22/popen-gw7/test_eviction_quarantines_unbo0/project_7/sase/repos/plans: git rev-parse --verify HEAD failed: fatal: Needed a single revision
FAILED tests/test_bead/test_workspace_sidecar_eviction_plans.py::test_eviction_proceeds_when_damaged_sidecar_quarantine_fails - sase.axe.runner_workspace_errors.WorkspacePreparationError: Failed to prepare workspace /var/tmp/sase-d00a07ab/pytest-of-bryan/pytest-22/popen-gw7/test_eviction_proceeds_when_da0/project_7 during sidecar-protection: verified nested preservation failed before launch eviction: could not preserve nested repository /var/tmp/sase-d00a07ab/pytest-of-bryan/pytest-22/popen-gw7/test_eviction_proceeds_when_da0/project_7/sase/repos/plans: git rev-parse --verify HEAD failed: fatal: Needed a single revision
FAILED tests/test_agent_artifact_directory_operation_audit.py::test_artifact_directory_operation_sites_are_reviewed - AssertionError: assert {'src/sase/_l...migrate', ...} == {'src/sase/_l...migrate', ...}
  
  Extra items in the left set:
  'src/sase/workspace_provider/_snapshot_restore.py:_clear_worktree'
  'src/sase/workspace_provider/_snapshot_capture.py:_verify_pack'
  'src/sase/workspace_provider/_snapshot_restore.py:_restore_operation_markers'
  'src/sase/workspace_provider/_snapshot_capture.py:_discard_incomplete'
  'src/sase/workspace_provider/_snapshot_capture.py:_cleanup_capture_temps'
  
  Full diff:
    {
        'src/sase/_linked_repo_workspaces.py:_remove_path',
        'src/sase/_linked_repo_workspaces.py:clear_workspace_repos',
        'src/sase/_linked_repo_workspaces.py:move_aside_for_background_delete',
        'src/sase/ace/tui/bgcmd.py:dismiss_background_command',
        'src/sase/agent/names/_wipe_execute.py:_remove_artifact_dirs',
        'src/sase/agents/cli_artifacts_layout.py:_handle_migrate',
        'src/sase/agents/cli_artifacts_layout.py:_handle_rollback',
        'src/sase/agents_sync/_git_sync_ops_git.py:ensure_agents_clone',
        'src/sase/agents_sync/purge_local_state.py:_apply_closure',
        'src/sase/agents_sync/v2_io.py:_cleanup_transaction_dirs',
        'src/sase/axe/run_agent_exec_attempts.py:_move_into_tmp',
        'src/sase/axe/run_agent_exec_attempts.py:snapshot_attempt',
        'src/sase/bead/attachments/lifecycle.py:quarantine_local_object',
        'src/sase/bead/attachments/store.py:remove',
        'src/sase/dev_update/prebuild_producer.py:_prune_completed_sets',
        'src/sase/dev_update/prebuild_producer.py:produce_prebuild',
        'src/sase/llm_provider/_codex_home.py:_try_delete_shadow_home',
        'src/sase/llm_provider/_plan_utils.py:move_plan_to_sase',
        'src/sase/main/project_handler_lifecycle.py:delete_project_locked',
        'src/sase/main/repo_open_external.py:_remove_clone_staging_path',
        'src/sase/main/workspace_handler_maintenance.py:remove_checkout',
        'src/sase/main/workspace_handler_migration.py:handle_migrate',
        'src/sase/migration_kit/atomic.py:_remove_path',
        'src/sase/migration_kit/atomic.py:remove_path',
        'src/sase/migration_kit/restore.py:_swap_into_place',
        'src/sase/mode_switch/execute.py:_cleanup_failed_clone',
        'src/sase/notification_gates/command_runner.py:_remove_untrusted_terminal',
        'src/sase/notification_gates/service_creation.py:_start_gate_creation',
        'src/sase/notification_gates/service_creation.py:create_gate',
        'src/sase/procs/_migration.py:_perform_migration',
        'src/sase/procs/_migration.py:_relocate_legacy_logs',
        'src/sase/sdd/_bead_adoption.py:_copy_bead_state',
        'src/sase/sdd/_bead_adoption.py:cleanup_plans_bead_state',
        'src/sase/sdd/_store_adoption.py:cleanup_staging',
        'src/sase/sdd/_store_clone_common.py:remove_partial_sdd_clone',
        'src/sase/sdd/_store_clone_transaction.py:_remove_clone_stage_path',
        'src/sase/sdd/_store_link.py:_replace_workspace_sdd_clone',
        'src/sase/sudo/execution_handoff.py:cleanup_handoff',
        'src/sase/workspace_provider/_rescue_git.py:_rescue_git_repo_body',
        'src/sase/workspace_provider/_rescue_store.py:_quarantine_directory',
        'src/sase/workspace_provider/_rescue_store.py:_reap_rescue_entries',
  +     'src/sase/workspace_provider/_snapshot_capture.py:_cleanup_capture_temps',
  +     'src/sase/workspace_provider/_snapshot_capture.py:_discard_incomplete',
  +     'src/sase/workspace_provider/_snapshot_capture.py:_verify_pack',
  +     'src/sase/workspace_provider/_snapshot_restore.py:_clear_worktree',
  +     'src/sase/workspace_provider/_snapshot_restore.py:_restore_operation_markers',
        'src/sase/workspace_provider/_utils_checkout.py:_remove_corrupt_checkout',
        'src/sase/workspace_provider/_utils_git.py:abort_in_progress_git_operations',
        'src/sase/workspace_provider/reset_replay.py:_clear_owned_paths',
    }
FAILED tests/ace/tui/test_app_import_budget.py::test_tui_app_import_stays_under_startup_budget - AssertionError: TUI app import loads 3549 modules against the 3539 cap; attribute the growth with `tools/tui_import_closure --diff $(git merge-base HEAD origin/master)` and defer the new edges
assert 3549 < 3539
==== 8 failed, 58454 passed, 17 skipped, 154 warnings in 805.99s (0:13:25) =====
error: recipe `test-scoped` failed on line 629 with exit code 1
scoped: escalated to the full suite (rules: core-identity-changed); contexts baseline not consulted
✗ 2 stage(s) failed; continued past them (first exit 1)
error: recipe `check` failed on line 897 with exit code 1
failed  exit=1  duration=2283834ms
unattrib  18m 35s
triage lint (symvision): 1 KNOWN continued
triage test (scoped): 1 FLAKY 6 KNOWN continued
KNOWN lint (symvision): _RecoveryAssessment in src/sase/finalizers/_failed_close_recovery_assess.py — witness 1dc946d3c1a3ec6ed5f0c3cdbaf2e681; no owner
KNOWN test (scoped): FAILED tests/test_axe_runner_workspace_agents_lock.py::test_prepare_workspace_holds_agents_lock_across_the_clean - TypeError: test_prepare_workspace_holds_agents_lock_across_the_clean.<locals>._clean() got an unexpected keyword argument 'workspace_num'. Did you mean 'workspace_dir'? — witness 5ef4483d5a0cc2ef07e034182ed32cf9; no owner
KNOWN test (scoped): FAILED tests/test_axe_runner_workspace_agents_lock.py::test_prepare_workspace_leaves_workspace_scoped_agents_clone_unguarded - TypeError: test_prepare_workspace_leaves_workspace_scoped_agents_clone_unguarded.<locals>._clean() got an unexpected keyword argument 'workspace_num'. Did you mean 'workspace_dir'? — witness 1dc946d3c1a3ec6ed5f0c3cdbaf2e681; no owner
FLAKY test (scoped): FAILED tests/test_bead/test_workspace_sidecar_eviction_plans.py::test_eviction_proceeds_when_damaged_sidecar_quarantine_fails - sase.axe.runner_workspace_errors.WorkspacePreparationError: Failed to prepare workspace /var<tmp> during sidecar-protection: verified nested preservation failed before launch eviction: could not preserve nested repository /var<tmp> git rev-parse --verify HEAD failed: fatal: Needed a single revision — recorded evidence; no owner
verdict: no_new_failures — 7 KNOWN, 1 FLAKY; exit 1

