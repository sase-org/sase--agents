# Chat History - ace-run (sase-pv.1--mon)

- **TIMESTAMP:** 2026-08-18 11:47:26 EDT
- **MODEL:** grok/grok-4.6
- **AGENT:** sase-pv.1--mon

## Prompt

sase monitor start --command 'just install && (cd sase/repos/linked/sase-core && just check) && just check-full' --reason 'Verify sase-pv.1 reserved-slug change in sase-core and this repo'

## Response

[install] Building sase_core_rs from /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/sase/repos/linked/sase-core for local dev.
[validate_sase_core_rs_version] sase-core checkout is ahead of sase's compatibility window: source version 0.28.0 from /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/sase/repos/linked/sase-core/Cargo.toml does not satisfy `sase`'s `sase-core-rs>=0.27.18,<0.28.0` dependency in pyproject.toml. No action is needed: editable installs build from the checkout regardless, and `tools/ratchet_core_window` moves the published window on the release branch at release time.
[rust-install] Note: the sase-core checkout is ahead of the published sase-core-rs window in pyproject.toml; dev builds from /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/sase/repos/linked/sase-core ignore it. This is normal — the release-branch reconciler ratchets the published window at release time, so no action is needed here.
# Harden cargo crate downloads against transient crates.io flakiness.
# CI has hit `curl ... [16] Error in the HTTP2 framing layer` while
# maturin's `cargo metadata` fetches deps; disabling HTTP/2 multiplexing
# and raising the retry count makes the download resilient. Both are
# overridable from the environment.
🍹 Building a mixed python/rust project
🐍 Found CPython 3.14 at /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/bin/python
🔗 Found pyo3 bindings with abi3-py3.12 support
📡 Using build options features from pyproject.toml
   Compiling target-lexicon v0.12.16
   Compiling version_check v0.9.5
   Compiling proc-macro2 v1.0.106
   Compiling unicode-ident v1.0.24
   Compiling quote v1.0.45
   Compiling once_cell v1.21.4
   Compiling cfg-if v1.0.4
   Compiling autocfg v1.5.0
   Compiling libc v0.2.186
   Compiling zerocopy v0.8.48
   Compiling serde_core v1.0.228
   Compiling typenum v1.20.0
   Compiling find-msvc-tools v0.1.9
   Compiling shlex v1.3.0
   Compiling memchr v2.8.0
   Compiling pkg-config v0.3.33
   Compiling vcpkg v0.2.15
   Compiling bitflags v2.11.1
   Compiling getrandom v0.4.2
   Compiling rustix v1.1.4
   Compiling hashbrown v0.17.0
   Compiling serde v1.0.228
   Compiling equivalent v1.0.2
   Compiling zmij v1.0.21
   Compiling serde_json v1.0.149
   Compiling regex-syntax v0.8.10
   Compiling itoa v1.0.18
   Compiling thiserror v1.0.69
   Compiling heck v0.5.0
   Compiling linux-raw-sys v0.12.1
   Compiling fastrand v2.4.1
   Compiling cpufeatures v0.2.17
   Compiling unsafe-libyaml v0.2.11
   Compiling fallible-streaming-iterator v0.1.9
   Compiling fallible-iterator v0.3.0
   Compiling smallvec v1.15.1
   Compiling ryu v1.0.23
   Compiling unindent v0.2.4
   Compiling hex v0.4.3
   Compiling unicode-width v0.2.2
   Compiling indoc v2.0.7
    Building [                           ] 0/115: linux-raw-sys, bitflags, se…    Building [                           ] 1/115: linux-raw-sys, bitflags, se…    Building [                           ] 2/115: linux-raw-sys, bitflags, se…   Compiling cc v1.2.61
    Building [                           ] 3/115: linux-raw-sys, bitflags, se…    Building [                           ] 4/115: linux-raw-sys, bitflags, se…    Building [>                          ] 5/115: linux-raw-sys, bitflags, se…    Building [=>                         ] 9/115: linux-raw-sys, bitflags, se…   Compiling generic-array v0.14.7
   Compiling ahash v0.8.12
    Building [=>                        ] 12/115: linux-raw-sys, bitflags, se…    Building [=>                        ] 13/115: linux-raw-sys, bitflags, se…    Building [==>                       ] 15/115: linux-raw-sys, bitflags, se…    Building [==>                       ] 16/115: linux-raw-sys, bitflags, se…    Building [==>                       ] 17/115: linux-raw-sys, bitflags, se…   Compiling num-traits v0.2.19
    Building [===>                      ] 18/115: linux-raw-sys, bitflags, se…   Compiling memoffset v0.9.1
    Building [===>                      ] 19/115: linux-raw-sys, bitflags, se…    Building [===>                      ] 20/115: linux-raw-sys, bitflags, se…    Building [===>                      ] 21/115: linux-raw-sys, bitflags, se…    Building [====>                     ] 23/115: linux-raw-sys, serde(build.…    Building [====>                     ] 24/115: linux-raw-sys, serde(build.…    Building [====>                     ] 25/115: linux-raw-sys, fallible-str…    Building [====>                     ] 26/115: linux-raw-sys, fallible-str…    Building [=====>                    ] 27/115: linux-raw-sys, fallible-str…    Building [=====>                    ] 28/115: linux-raw-sys, fallible-str…    Building [=====>                    ] 29/115: linux-raw-sys, generic-arra…    Building [=====>                    ] 30/115: linux-raw-sys, generic-arra…    Building [======>                   ] 31/115: linux-raw-sys, generic-arra…    Building [======>                   ] 32/115: linux-raw-sys, generic-arra…    Building [======>                   ] 33/115: linux-raw-sys, zerocopy, me…    Building [======>                   ] 34/115: linux-raw-sys, zerocopy, me…    Building [=======>                  ] 37/115: linux-raw-sys, zerocopy, me…    Building [=======>                  ] 38/115: linux-raw-sys, zerocopy, me…    Building [========>                 ] 40/115: linux-raw-sys, zerocopy, me…    Building [========>                 ] 43/115: linux-raw-sys, zerocopy, fa…    Building [=========>                ] 45/115: linux-raw-sys, zerocopy, fa…    Building [=========>                ] 46/115: linux-raw-sys, zerocopy, cc…    Building [=========>                ] 47/115: linux-raw-sys, zerocopy, cc…    Building [=========>                ] 48/115: linux-raw-sys, zerocopy, cc…    Building [==========>               ] 49/115: linux-raw-sys, zerocopy, cc…    Building [==========>               ] 50/115: linux-raw-sys, zerocopy, cc…    Building [==========>               ] 51/115: linux-raw-sys, zerocopy, cc…    Building [==========>               ] 52/115: linux-raw-sys, zerocopy, cc…    Building [==========>               ] 53/115: linux-raw-sys, zerocopy, cc…    Building [===========>              ] 54/115: linux-raw-sys, zerocopy, cc…    Building [===========>              ] 55/115: linux-raw-sys, zerocopy, cc…    Building [===========>              ] 56/115: linux-raw-sys, zerocopy, cc…    Building [===========>              ] 57/115: linux-raw-sys, zerocopy, cc…    Building [===========>              ] 57/115: linux-raw-sys, zerocopy, ru…    Building [============>             ] 58/115: zerocopy, rustix, cc, proc-…    Building [============>             ] 59/115: zerocopy, rustix, cc, proc-…   Compiling aho-corasick v1.1.4
   Compiling pyo3-build-config v0.22.6
    Building [============>             ] 60/115: zerocopy, rustix, cc, proc-…   Compiling indexmap v2.14.0
    Building [============>             ] 61/115: zerocopy, rustix, cc, proc-…    Building [=============>            ] 62/115: zerocopy, rustix, cc, quote…   Compiling syn v2.0.117
    Building [=============>            ] 63/115: zerocopy, rustix, cc, quote…    Building [=============>            ] 64/115: zerocopy, rustix, cc, pyo3-…    Building [=============>            ] 65/115: zerocopy, rustix, cc, pyo3-…   Compiling libsqlite3-sys v0.30.1
    Building [=============>            ] 66/115: zerocopy, rustix, pyo3-buil…    Building [==============>           ] 67/115: zerocopy, rustix, libc, pyo…   Compiling chrono v0.4.44
    Building [==============>           ] 68/115: zerocopy, rustix, pyo3-buil…    Building [==============>           ] 69/115: zerocopy, rustix, pyo3-buil…   Compiling fs2 v0.4.3
    Building [==============>           ] 69/115: fs2, zerocopy, rustix, pyo3…    Building [==============>           ] 70/115: fs2, zerocopy, rustix, pyo3…    Building [===============>          ] 71/115: zerocopy, rustix, pyo3-buil…    Building [===============>          ] 72/115: zerocopy, rustix, pyo3-buil…    Building [===============>          ] 73/115: zerocopy, rustix, pyo3-buil…   Compiling crypto-common v0.1.7
   Compiling block-buffer v0.10.4
    Building [===============>          ] 74/115: zerocopy, rustix, pyo3-buil…   Compiling digest v0.10.7
    Building [===============>          ] 75/115: zerocopy, rustix, pyo3-buil…    Building [================>         ] 76/115: zerocopy, rustix, pyo3-buil…    Building [================>         ] 77/115: zerocopy, rustix, pyo3-buil…   Compiling sha2 v0.10.9
    Building [================>         ] 78/115: zerocopy, rustix, pyo3-buil…   Compiling pyo3-macros-backend v0.22.6
   Compiling pyo3-ffi v0.22.6
   Compiling pyo3 v0.22.6
    Building [================>         ] 79/115: zerocopy, rustix, sha2, pyo…    Building [=================>        ] 80/115: zerocopy, rustix, sha2, pyo…    Building [=================>        ] 81/115: zerocopy, rustix, sha2, pyo…    Building [=================>        ] 82/115: zerocopy, rustix, sha2, pyo…    Building [=================>        ] 83/115: zerocopy, rustix, sha2, pyo…    Building [=================>        ] 84/115: zerocopy, rustix, sha2, reg…    Building [==================>       ] 85/115: zerocopy, rustix, pyo3(buil…    Building [==================>       ] 86/115: zerocopy, rustix, sha2, reg…   Compiling regex-automata v0.4.14
    Building [==================>       ] 86/115: regex-automata, zerocopy, r…   Compiling tempfile v3.27.0
    Building [==================>       ] 87/115: regex-automata, zerocopy, r…    Building [==================>       ] 88/115: regex-automata, zerocopy, r…    Building [===================>      ] 89/115: regex-automata, zerocopy, r…    Building [===================>      ] 90/115: regex-automata, zerocopy, s…    Building [===================>      ] 91/115: regex-automata, zerocopy, s…    Building [===================>      ] 92/115: regex-automata, zerocopy, s…    Building [====================>     ] 93/115: regex-automata, zerocopy, s…   Compiling serde_derive v1.0.228
   Compiling thiserror-impl v1.0.69
    Building [====================>     ] 94/115: regex-automata, zerocopy, s…   Compiling hashbrown v0.14.5
    Building [====================>     ] 95/115: regex-automata, zerocopy, s…    Building [====================>     ] 96/115: regex-automata, serde_json,…    Building [====================>     ] 97/115: regex-automata, regex-synta…    Building [=====================>    ] 98/115: regex-automata, serde_deriv…   Compiling regex v1.12.3
    Building [=====================>    ] 99/115: regex-automata, thiserror, …    Building [====================>    ] 100/115: regex-automata, serde_deriv…   Compiling hashlink v0.9.1
    Building [====================>    ] 101/115: regex-automata, serde_deriv…    Building [=====================>   ] 102/115: regex-automata, serde_deriv…    Building [=====================>   ] 103/115: regex-automata, serde_deriv…    Building [=====================>   ] 104/115: regex-automata, pyo3-macros…   Compiling pyo3-macros v0.22.6
    Building [=====================>   ] 105/115: pyo3-macros, regex-automata…    Building [======================>  ] 106/115: regex-automata, pyo3, libsq…   Compiling serde_yaml v0.9.34+deprecated
    Building [======================>  ] 107/115: regex-automata, pyo3, libsq…    Building [======================>  ] 108/115: pyo3, libsqlite3-sys(build)…    Building [======================>  ] 109/115: pyo3, libsqlite3-sys(build)     Building [======================>  ] 110/115: libsqlite3-sys(build)           Building [=======================> ] 111/115: libsqlite3-sys                 Compiling rusqlite v0.32.1
    Building [=======================> ] 111/115: libsqlite3-sys, rusqlite        Building [=======================> ] 112/115: rusqlite                       Compiling sase_core v0.28.0 (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/sase/repos/linked/sase-core/crates/sase_core)
    Building [=======================> ] 112/115: sase_core, rusqlite             Building [=======================> ] 113/115: sase_core                      Compiling sase_core_py v0.28.0 (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/sase/repos/linked/sase-core/crates/sase_core_py)
    Building [=======================> ] 114/115: sase_core_py                    Finished `release` profile [optimized] target(s) in 4m 37s
📦 Built wheel for abi3 Python ≥ 3.12 to /tmp/.tmpm4lgL8/sase_core_rs-0.28.0-cp312-abi3-linux_x86_64.whl
✏️ Setting installed package as editable
🛠 Installed sase-core-rs-0.28.0
uv pip install --python .venv/bin/python --no-sources $(just _core-overrides-arg) -e ".[dev]"
Resolved 98 packages in 304ms
   Building sase @ file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19
      Built sase @ file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19
Prepared 1 package in 708ms
Uninstalled 1 package in 10ms
Installed 1 package in 3ms
 ~ sase==0.16.0 (from file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19)
.venv/bin/python tools/setup_required_plugins
[setup] Installing required plugin sase-github>=0.2.5.
[setup] Installing required plugin sase-research-artifacts.
./scripts/check.sh all
    Checking cfg-if v1.0.4
    Checking itoa v1.0.18
    Checking once_cell v1.21.4
    Checking memchr v2.8.0
    Checking smallvec v1.15.1
   Compiling serde_core v1.0.228
    Checking equivalent v1.0.2
    Checking hashbrown v0.17.0
   Compiling serde_json v1.0.149
    Checking typenum v1.20.0
    Checking bitflags v2.11.1
    Checking regex-syntax v0.8.10
    Checking ryu v1.0.23
    Checking pin-project-lite v0.2.17
    Checking linux-raw-sys v0.12.1
    Checking fallible-iterator v0.3.0
    Checking iana-time-zone v0.1.65
    Checking fastrand v2.4.1
    Checking cpufeatures v0.2.17
    Checking fallible-streaming-iterator v0.1.9
    Checking unsafe-libyaml v0.2.11
    Checking bytes v1.11.1
    Checking hex v0.4.3
    Checking unicode-width v0.2.2
    Checking futures-core v0.3.32
    Checking log v0.4.29
    Checking futures-sink v0.3.32
    Checking futures-io v0.3.32
    Checking futures-task v0.3.32
    Checking slab v0.4.12
   Compiling httparse v1.10.1
    Checking tower-service v0.3.3
    Checking stable_deref_trait v1.2.1
   Compiling target-lexicon v0.12.16
    Checking tower-layer v0.3.3
    Checking sync_wrapper v1.0.2
    Checking writeable v0.6.3
    Checking litemap v0.8.2
    Checking untrusted v0.9.0
   Compiling icu_normalizer_data v2.2.0
    Checking utf8_iter v1.0.4
   Compiling icu_properties_data v2.2.0
    Checking httpdate v1.0.3
    Checking fnv v1.0.7
    Checking percent-encoding v2.3.2
   Compiling parking_lot_core v0.9.12
   Compiling crossbeam-utils v0.8.21
   Compiling num-traits v0.2.19
   Compiling rustls v0.21.12
   Compiling num-conv v0.2.1
    Checking powerfmt v0.2.0
    Checking libc v0.2.186
    Checking zerocopy v0.8.48
    Checking zmij v1.0.21
   Compiling ring v0.17.14
    Checking bitflags v1.3.2
    Checking scopeguard v1.2.0
   Compiling rustversion v1.0.22
   Compiling thiserror v2.0.18
   Compiling syn v2.0.117
    Checking try-lock v0.2.5
   Compiling time-core v0.1.8
    Checking lazy_static v1.5.0
    Checking atomic-waker v1.1.2
    Checking mime v0.3.17
    Checking libsqlite3-sys v0.30.1
    Checking tracing-core v0.1.36
    Checking futures-channel v0.3.32
    Checking lock_api v0.4.14
    Checking fluent-uri v0.1.4
    Checking thread_local v1.1.9
    Checking nu-ansi-term v0.50.3
    Checking base64 v0.21.7
    Checking base64 v0.22.1
    Checking encoding_rs v0.8.35
   Compiling memoffset v0.9.1
    Checking sync_wrapper v0.1.2
    Checking ipnet v2.12.0
    Checking matchit v0.7.3
    Checking webpki-roots v0.25.4
   Compiling heck v0.5.0
    Checking unindent v0.2.4
   Compiling indoc v2.0.7
    Checking aho-corasick v1.1.4
    Checking form_urlencoded v1.2.2
    Checking want v0.3.1
    Checking deranged v0.5.8
    Checking sharded-slab v0.1.7
    Checking indexmap v2.14.0
    Checking rustix v1.1.4
   Compiling time-macros v0.2.27
    Building [=======>                  ] 94/292: num-traits(build), icu_prop…    Building [=======>                 ] 101/292: icu_properties_data(build),…    Building [========>                ] 110/292: libsqlite3-sys, deranged, z…    Building [========>                ] 114/292: deranged, zerocopy, memoffs…    Checking rustls-pemfile v1.0.4
    Building [=========>               ] 118/292: deranged, zerocopy, memoffs…    Building [=========>               ] 119/292: deranged, zerocopy, memoffs…    Building [=========>               ] 120/292: deranged, zerocopy, memoffs…    Building [=========>               ] 121/292: deranged, zerocopy, memoffs…    Building [=========>               ] 122/292: deranged, zerocopy, memoffs…    Building [=========>               ] 123/292: deranged, zerocopy, memoffs…    Building [=========>               ] 124/292: deranged, zerocopy, aho-cor…    Checking pem v3.0.6
    Building [=========>               ] 125/292: deranged, zerocopy, aho-cor…    Checking tracing-log v0.2.0
    Building [=========>               ] 126/292: deranged, zerocopy, tracing…    Checking generic-array v0.14.7
    Building [=========>               ] 127/292: deranged, zerocopy, tracing…    Building [==========>              ] 129/292: deranged, zerocopy, tracing…    Building [==========>              ] 130/292: deranged, zerocopy, tracing…    Checking http v1.4.0
    Checking http v0.2.12
    Building [==========>              ] 131/292: deranged, zerocopy, tracing…    Building [==========>              ] 132/292: deranged, zerocopy, tracing…    Building [==========>              ] 133/292: deranged, zerocopy, tracing…    Building [==========>              ] 134/292: deranged, zerocopy, aho-cor…    Building [==========>              ] 135/292: deranged, zerocopy, aho-cor…   Compiling pyo3-build-config v0.22.6
    Building [==========>              ] 137/292: deranged, zerocopy, aho-cor…    Building [==========>              ] 138/292: deranged, zerocopy, aho-cor…    Building [==========>              ] 139/292: deranged, zerocopy, aho-cor…    Building [==========>              ] 140/292: deranged, zerocopy, aho-cor…    Checking getrandom v0.4.2
    Checking fs2 v0.4.3
    Checking errno v0.3.14
    Checking mio v1.2.0
    Checking socket2 v0.6.3
    Checking getrandom v0.2.17
    Checking socket2 v0.5.10
    Building [===========>             ] 141/292: deranged, zerocopy, socket2…    Building [===========>             ] 142/292: deranged, zerocopy, socket2…    Checking chrono v0.4.44
    Checking num-integer v0.1.46
    Building [===========>             ] 143/292: num-integer, deranged, zero…    Checking signal-hook-registry v1.4.8
    Building [===========>             ] 145/292: num-integer, deranged, zero…    Checking block-buffer v0.10.4
    Checking crypto-common v0.1.7
    Building [===========>             ] 146/292: num-integer, deranged, zero…    Checking rand_core v0.6.4
    Building [===========>             ] 147/292: num-integer, deranged, zero…    Building [===========>             ] 148/292: num-integer, deranged, zero…    Building [===========>             ] 149/292: num-integer, deranged, zero…    Building [===========>             ] 150/292: num-integer, deranged, zero…    Checking digest v0.10.7
    Building [===========>             ] 151/292: num-integer, deranged, zero…    Building [============>            ] 152/292: num-integer, deranged, zero…    Building [============>            ] 153/292: num-integer, deranged, zero…    Building [============>            ] 154/292: num-integer, deranged, zero…    Checking http-body v0.4.6
    Building [============>            ] 155/292: num-integer, deranged, zero…    Building [============>            ] 156/292: num-integer, deranged, zero…    Checking num-bigint v0.4.6
    Building [============>            ] 157/292: deranged, zerocopy, ring(bu…    Building [============>            ] 158/292: deranged, zerocopy, ring(bu…    Building [============>            ] 159/292: deranged, zerocopy, ring(bu…    Building [============>            ] 160/292: deranged, zerocopy, ring(bu…    Building [============>            ] 161/292: deranged, zerocopy, ring(bu…    Building [============>            ] 162/292: deranged, zerocopy, ring(bu…    Checking sha2 v0.10.9
    Building [============>            ] 163/292: deranged, zerocopy, sha2, r…    Checking http-body v1.0.1
    Building [=============>           ] 164/292: deranged, zerocopy, sha2, r…    Building [=============>           ] 165/292: deranged, zerocopy, sha2, r…    Checking http-body-util v0.1.3
    Building [=============>           ] 166/292: deranged, zerocopy, sha2, r…    Checking regex-automata v0.4.14
    Building [=============>           ] 167/292: deranged, zerocopy, sha2, r…    Checking time v0.3.47
    Building [=============>           ] 168/292: zerocopy, sha2, ring(build)…    Building [=============>           ] 169/292: zerocopy, ring(build), time…    Building [=============>           ] 170/292: zerocopy, ring(build), time…    Building [=============>           ] 171/292: zerocopy, ring(build), time…    Checking tempfile v3.27.0
    Building [=============>           ] 172/292: zerocopy, ring(build), time…    Building [=============>           ] 173/292: zerocopy, ring(build), time…    Building [=============>           ] 174/292: zerocopy, ring(build), time…   Compiling pyo3-macros-backend v0.22.6
   Compiling pyo3-ffi v0.22.6
   Compiling pyo3 v0.22.6
    Building [=============>           ] 175/292: zerocopy, ring(build), time…    Building [==============>          ] 176/292: zerocopy, ring(build), time…    Checking serde_path_to_error v0.1.20
    Building [==============>          ] 177/292: zerocopy, ring(build), time…    Building [==============>          ] 178/292: zerocopy, ring(build), time…    Building [==============>          ] 179/292: zerocopy, ring(build), time…    Building [==============>          ] 180/292: zerocopy, ring(build), time…    Building [==============>          ] 181/292: zerocopy, ring(build), time…    Building [==============>          ] 182/292: zerocopy, pyo3(build), ring…    Building [==============>          ] 183/292: zerocopy, ring(build), time…    Building [==============>          ] 184/292: zerocopy, ring(build), time…    Building [==============>          ] 185/292: zerocopy, ring(build), time…    Building [==============>          ] 186/292: zerocopy, ring(build), serd…    Building [===============>         ] 187/292: zerocopy, ring(build), rege…    Building [===============>         ] 188/292: zerocopy, regex-automata, s…    Building [===============>         ] 189/292: zerocopy, regex-automata, s…    Checking regex v1.12.3
    Checking matchers v0.2.0
    Building [===============>         ] 190/292: zerocopy, syn, matchers, ri…   Compiling synstructure v0.13.2
    Building [===============>         ] 191/292: zerocopy, syn, ring, regex,…    Checking ahash v0.8.12
    Checking ppv-lite86 v0.2.21
    Building [===============>         ] 192/292: ahash, syn, ring, regex, pp…    Checking hashbrown v0.14.5
    Building [===============>         ] 193/292: syn, hashbrown, ring, regex…    Building [===============>         ] 194/292: syn, hashbrown, ring, ppv-l…    Checking rand_chacha v0.3.1
    Building [===============>         ] 195/292: syn, hashbrown, ring, pyo3-…    Building [===============>         ] 196/292: syn, hashbrown, ring, pyo3-…   Compiling serde_derive v1.0.228
   Compiling thiserror-impl v1.0.69
   Compiling tokio-macros v2.7.0
   Compiling tracing-attributes v0.1.31
   Compiling zerofrom-derive v0.1.7
   Compiling futures-macro v0.3.32
   Compiling yoke-derive v0.8.2
   Compiling zerovec-derive v0.11.3
   Compiling displaydoc v0.2.5
   Compiling serde_repr v0.1.20
   Compiling thiserror-impl v2.0.18
   Compiling async-trait v0.1.89
   Compiling async-stream-impl v0.3.6
    Checking rand v0.8.6
    Building [===============>         ] 198/292: async-trait, serde_repr, ra…    Checking hashlink v0.9.1
    Checking dashmap v6.1.0
    Building [================>        ] 199/292: hashlink, async-trait, serd…    Checking rustls-webpki v0.101.7
    Checking sct v0.7.1
    Building [================>        ] 200/292: hashlink, async-trait, serd…    Building [================>        ] 201/292: hashlink, async-trait, serd…    Checking rusqlite v0.32.1
    Building [================>        ] 202/292: async-trait, serde_repr, ru…    Building [================>        ] 203/292: async-trait, rustls-webpki,…    Building [================>        ] 204/292: async-trait, rustls-webpki,…    Checking async-stream v0.3.6
    Building [================>        ] 205/292: async-trait, rustls-webpki,…    Checking tokio v1.52.2
    Building [================>        ] 206/292: async-trait, rustls-webpki,…    Building [================>        ] 207/292: async-trait, rustls-webpki,…    Building [================>        ] 208/292: async-trait, rustls-webpki,…    Checking futures-util v0.3.32
    Building [================>        ] 209/292: async-trait, futures-util, …    Building [================>        ] 210/292: futures-util, rustls-webpki…    Building [=================>       ] 211/292: futures-util, rustls, rand,…    Building [=================>       ] 212/292: futures-util, rustls, thise…    Building [=================>       ] 213/292: futures-util, rustls, thise…    Checking zerofrom v0.1.7
    Building [=================>       ] 214/292: futures-util, rustls, thise…    Checking thiserror v1.0.69
    Building [=================>       ] 215/292: futures-util, rustls, thise…    Checking yoke v0.8.2
    Building [=================>       ] 216/292: futures-util, rustls, thise…    Building [=================>       ] 217/292: futures-util, rustls, serde…    Checking tracing v0.1.44
    Building [=================>       ] 218/292: tracing, futures-util, rust…    Building [=================>       ] 219/292: tracing, futures-util, rust…    Building [=================>       ] 220/292: tracing, futures-util, rust…    Checking simple_asn1 v0.6.4
    Building [=================>       ] 221/292: tracing, futures-util, rust…    Checking zerovec v0.11.6
    Checking zerotrie v0.2.4
    Building [==================>      ] 222/292: tracing, futures-util, rust…    Checking tracing-subscriber v0.3.23
    Checking tower-http v0.5.2
    Building [==================>      ] 223/292: futures-util, tracing-subsc…    Building [==================>      ] 224/292: futures-util, tracing-subsc…    Building [==================>      ] 225/292: futures-util, tracing-subsc…    Building [==================>      ] 226/292: futures-util, tracing-subsc…    Checking tinystr v0.8.3
    Checking potential_utf v0.1.5
    Building [==================>      ] 227/292: potential_utf, futures-util…    Building [==================>      ] 228/292: potential_utf, futures-util…    Checking icu_collections v2.2.0
    Building [==================>      ] 229/292: futures-util, tracing-subsc…    Checking icu_locale_core v2.2.0
    Building [==================>      ] 230/292: futures-util, tracing-subsc…    Building [==================>      ] 231/292: futures-util, icu_locale_co…    Building [==================>      ] 232/292: futures-util, icu_locale_co…   Compiling pyo3-macros v0.22.6
    Building [==================>      ] 233/292: pyo3-macros, futures-util, …    Checking serde v1.0.228
    Building [===================>     ] 234/292: pyo3-macros, futures-util, …    Building [===================>     ] 235/292: pyo3-macros, futures-util, …    Checking icu_provider v2.2.0
    Building [===================>     ] 236/292: pyo3-macros, futures-util, …    Building [===================>     ] 237/292: futures-util, pyo3, serde, …    Checking icu_properties v2.2.0
    Checking icu_normalizer v2.2.0
    Building [===================>     ] 238/292: futures-util, pyo3, icu_pro…    Checking serde_yaml v0.9.34+deprecated
    Checking lsp-types v0.97.0
    Checking serde_urlencoded v0.7.1
    Checking jsonwebtoken v9.3.1
    Building [===================>     ] 239/292: serde_urlencoded, futures-u…    Building [===================>     ] 240/292: futures-util, pyo3, jsonweb…    Building [===================>     ] 241/292: futures-util, pyo3, jsonweb…    Checking futures v0.3.32
    Checking axum-core v0.4.5
    Building [===================>     ] 242/292: futures, pyo3, jsonwebtoken…    Building [===================>     ] 243/292: pyo3, jsonwebtoken, icu_pro…    Building [===================>     ] 244/292: pyo3, icu_properties, axum-…    Checking sase_core v0.28.0 (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/sase/repos/linked/sase-core/crates/sase_core)
    Building [===================>     ] 245/292: pyo3, sase_core(test), icu_…    Checking idna_adapter v1.2.2
    Building [====================>    ] 246/292: pyo3, sase_core(test), axum…    Checking idna v1.1.0
    Building [====================>    ] 247/292: pyo3, sase_core(test), idna…    Checking url v2.5.8
    Building [====================>    ] 248/292: pyo3, url, sase_core(test),…    Building [====================>    ] 249/292: url, sase_core(test), axum-…    Building [====================>    ] 250/292: sase_core(test), axum-core,…    Checking tokio-util v0.7.18
    Checking tower v0.5.3
    Checking hyper v1.9.0
    Checking tokio-rustls v0.24.1
    Building [====================>    ] 251/292: tokio-rustls, sase_core(tes…    Building [====================>    ] 252/292: sase_core(test), tower, axu…    Building [====================>    ] 253/292: sase_core(test), tower, lsp…    Building [====================>    ] 254/292: sase_core(test), lsp-types,…    Checking h2 v0.3.27
    Building [====================>    ] 255/292: h2, sase_core(test), lsp-ty…    Checking hyper-util v0.1.20
    Building [====================>    ] 256/292: h2, sase_core(test), lsp-ty…    Checking axum v0.7.9
    Building [=====================>   ] 257/292: h2, axum, sase_core(test), …    Checking hyper v0.14.32
    Building [=====================>   ] 258/292: axum, sase_core(test), hype…    Building [=====================>   ] 259/292: sase_core(test), hyper, lsp…    Checking tower-lsp-server v0.21.1
    Building [=====================>   ] 260/292: tower-lsp-server, sase_core…    Checking hyper-rustls v0.24.2
    Building [=====================>   ] 261/292: tower-lsp-server, hyper-rus…    Checking reqwest v0.11.27
    Building [=====================>   ] 262/292: tower-lsp-server, sase_core…    Building [=====================>   ] 263/292: tower-lsp-server, sase_core…    Building [=====================>   ] 264/292: sase_core(test), sase_core      Checking sase_xprompt_lsp v0.28.0 (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/sase/repos/linked/sase-core/crates/sase_xprompt_lsp)
    Checking sase_gateway v0.28.0 (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/sase/repos/linked/sase-core/crates/sase_gateway)
    Checking sase_core_py v0.28.0 (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/sase/repos/linked/sase-core/crates/sase_core_py)
    Building [=====================>   ] 265/292: golden_corpus_parity(test),…    Building [=====================>   ] 266/292: golden_corpus_parity(test),…    Building [=====================>   ] 267/292: golden_corpus_parity(test),…    Building [=====================>   ] 268/292: golden_corpus_parity(test),…    Building [======================>  ] 269/292: golden_corpus_parity(test),…    Building [======================>  ] 270/292: notification_store_parity(t…    Building [======================>  ] 271/292: notification_store_parity(t…    Building [======================>  ] 272/292: notification_store_parity(t…    Building [======================>  ] 273/292: notification_store_parity(t…    Building [======================>  ] 274/292: notification_store_parity(t…    Building [======================>  ] 275/292: notification_store_parity(t…    Building [======================>  ] 276/292: notification_store_parity(t…    Building [======================>  ] 277/292: notification_store_parity(t…    Building [======================>  ] 278/292: sase_gateway(test), sase_ga…    Building [======================>  ] 279/292: sase_gateway(test), sase_ga…    Building [======================>  ] 280/292: sase_gateway(test), sase_ga…    Building [=======================> ] 281/292: sase_gateway(test), jsonrpc…    Building [=======================> ] 282/292: sase_gateway(test), jsonrpc…    Building [=======================> ] 283/292: sase_gateway(test), jsonrpc…    Building [=======================> ] 284/292: sase_gateway(test), sase_ga…    Building [=======================> ] 285/292: sase_gateway(test), sase_ga…    Building [=======================> ] 286/292: sase_gateway(test), sase_co…    Building [=======================> ] 287/292: sase_gateway(test), sase_co…    Building [=======================> ] 288/292: sase_gateway(test), sase_co…    Building [=======================> ] 289/292: sase_core_rs(test), sase_co…    Building [=======================> ] 290/292: sase_core_rs(test), sase_co…    Building [=======================> ] 291/292: sase_core(test)                 Finished `dev` profile [unoptimized + debuginfo] target(s) in 52.14s
   Compiling once_cell v1.21.4
   Compiling memchr v2.8.0
   Compiling smallvec v1.15.1
   Compiling iana-time-zone v0.1.65
   Compiling pin-project-lite v0.2.17
   Compiling bytes v1.11.1
   Compiling futures-core v0.3.32
   Compiling log v0.4.29
   Compiling futures-sink v0.3.32
   Compiling slab v0.4.12
   Compiling futures-task v0.3.32
   Compiling futures-io v0.3.32
   Compiling tower-service v0.3.3
   Compiling stable_deref_trait v1.2.1
   Compiling tower-layer v0.3.3
   Compiling sync_wrapper v1.0.2
   Compiling untrusted v0.9.0
   Compiling writeable v0.6.3
   Compiling litemap v0.8.2
   Compiling utf8_iter v1.0.4
   Compiling fnv v1.0.7
   Compiling httpdate v1.0.3
   Compiling scopeguard v1.2.0
   Compiling percent-encoding v2.3.2
   Compiling bitflags v1.3.2
   Compiling time-core v0.1.8
   Compiling try-lock v0.2.5
   Compiling num-conv v0.2.1
   Compiling powerfmt v0.2.0
   Compiling lazy_static v1.5.0
   Compiling thread_local v1.1.9
   Compiling nu-ansi-term v0.50.3
   Compiling atomic-waker v1.1.2
   Compiling mime v0.3.17
   Compiling base64 v0.22.1
   Compiling base64 v0.21.7
   Compiling encoding_rs v0.8.35
   Compiling webpki-roots v0.25.4
   Compiling matchit v0.7.3
   Compiling serde_core v1.0.228
   Compiling futures-channel v0.3.32
   Compiling tracing-core v0.1.36
   Compiling httparse v1.10.1
   Compiling icu_normalizer_data v2.2.0
   Compiling icu_properties_data v2.2.0
   Compiling lock_api v0.4.14
   Compiling crossbeam-utils v0.8.21
   Compiling fluent-uri v0.1.4
   Compiling want v0.3.1
   Compiling ipnet v2.12.0
   Compiling sync_wrapper v0.1.2
   Compiling unindent v0.2.4
   Compiling num-traits v0.2.19
   Compiling ahash v0.8.12
   Compiling errno v0.3.14
   Compiling socket2 v0.6.3
   Compiling mio v1.2.0
   Compiling getrandom v0.2.17
   Compiling parking_lot_core v0.9.12
   Compiling form_urlencoded v1.2.2
   Compiling sharded-slab v0.1.7
   Compiling time-macros v0.2.27
   Compiling socket2 v0.5.10
   Compiling deranged v0.5.8
   Compiling ppv-lite86 v0.2.21
   Compiling memoffset v0.9.1
   Compiling tempfile v3.27.0
   Compiling thiserror v1.0.69
   Compiling pyo3-build-config v0.22.6
   Compiling thiserror v2.0.18
   Compiling async-stream v0.3.6
   Compiling zerofrom v0.1.7
    Building [===========>             ] 146/292: sharded-slab, want, ahash, …   Compiling signal-hook-registry v1.4.8
   Compiling pem v3.0.6
    Building [===========>             ] 148/292: sharded-slab, ahash, time-m…   Compiling hashbrown v0.14.5
   Compiling rustls-pemfile v1.0.4
    Building [===========>             ] 150/292: sharded-slab, ahash, time-m…    Building [===========>             ] 151/292: sharded-slab, ahash, time-m…    Building [============>            ] 152/292: sharded-slab, ahash, time-m…    Building [============>            ] 153/292: sharded-slab, ahash, time-m…    Building [============>            ] 154/292: sharded-slab, ahash, time-m…    Building [============>            ] 155/292: sharded-slab, ahash, time-m…    Building [============>            ] 156/292: sharded-slab, time-macros, …   Compiling ring v0.17.14
   Compiling rand_core v0.6.4
    Building [============>            ] 157/292: sharded-slab, time-macros, …   Compiling yoke v0.8.2
   Compiling aho-corasick v1.1.4
   Compiling futures-util v0.3.32
    Building [============>            ] 158/292: sharded-slab, time-macros, …    Building [============>            ] 160/292: sharded-slab, time-macros, …    Building [============>            ] 161/292: sharded-slab, time-macros, …    Building [============>            ] 162/292: sharded-slab, time-macros, …    Building [============>            ] 163/292: sharded-slab, time-macros, …    Building [=============>           ] 164/292: sharded-slab, time-macros, …   Compiling http v1.4.0
   Compiling http v0.2.12
    Building [=============>           ] 165/292: sharded-slab, time-macros, …    Building [=============>           ] 166/292: sharded-slab, time-macros, …   Compiling tracing v0.1.44
   Compiling tracing-log v0.2.0
    Building [=============>           ] 167/292: sharded-slab, time-macros, …   Compiling tokio v1.52.2
    Building [=============>           ] 168/292: sharded-slab, time-macros, …   Compiling zerovec v0.11.6
   Compiling zerotrie v0.2.4
    Building [=============>           ] 169/292: sharded-slab, time-macros, …    Building [=============>           ] 171/292: sharded-slab, time-macros, …    Building [=============>           ] 172/292: sharded-slab, time-macros, …    Building [=============>           ] 173/292: sharded-slab, time-macros, …   Compiling rand_chacha v0.3.1
    Building [=============>           ] 174/292: sharded-slab, time-macros, …    Building [=============>           ] 175/292: sharded-slab, time-macros, …    Building [==============>          ] 176/292: sharded-slab, time-macros, …    Building [==============>          ] 177/292: sharded-slab, time-macros, …    Building [==============>          ] 178/292: sharded-slab, time-macros, …    Building [==============>          ] 179/292: sharded-slab, time-macros, …    Building [==============>          ] 180/292: sharded-slab, time-macros, …    Building [==============>          ] 181/292: sharded-slab, time-macros, …    Building [==============>          ] 182/292: sharded-slab, time-macros, …    Building [==============>          ] 183/292: sharded-slab, time-macros, …    Building [==============>          ] 184/292: sharded-slab, time-macros, …    Building [==============>          ] 185/292: time-macros, pyo3-build-con…   Compiling rand v0.8.6
   Compiling chrono v0.4.44
   Compiling num-integer v0.1.46
    Building [==============>          ] 185/292: num-integer, time-macros, p…    Building [==============>          ] 186/292: num-integer, time-macros, p…   Compiling pyo3-ffi v0.22.6
   Compiling pyo3-macros-backend v0.22.6
   Compiling pyo3 v0.22.6
    Building [===============>         ] 187/292: num-integer, time-macros, r…    Building [===============>         ] 188/292: num-integer, time-macros, r…   Compiling hashlink v0.9.1
   Compiling dashmap v6.1.0
    Building [===============>         ] 188/292: num-integer, time-macros, h…    Building [===============>         ] 189/292: num-integer, time-macros, h…    Building [===============>         ] 190/292: num-integer, hashlink, rand…    Building [===============>         ] 191/292: num-integer, hashlink, http…    Building [===============>         ] 192/292: num-integer, hashlink, http…    Building [===============>         ] 193/292: num-integer, hashlink, http…    Building [===============>         ] 194/292: num-integer, pyo3-macros-ba…   Compiling num-bigint v0.4.6
   Compiling tinystr v0.8.3
   Compiling potential_utf v0.1.5
    Building [===============>         ] 195/292: num-integer, pyo3-macros-ba…    Building [===============>         ] 196/292: num-integer, pyo3-macros-ba…   Compiling http-body v0.4.6
    Building [===============>         ] 196/292: num-integer, http-body, pyo…    Building [===============>         ] 197/292: num-integer, http-body, pyo…    Building [===============>         ] 198/292: http-body, pyo3-macros-back…    Building [================>        ] 199/292: http-body, pyo3-macros-back…   Compiling icu_collections v2.2.0
   Compiling http-body v1.0.1
    Building [================>        ] 200/292: http-body, pyo3-macros-back…   Compiling icu_locale_core v2.2.0
   Compiling rusqlite v0.32.1
    Building [================>        ] 201/292: http-body, pyo3-macros-back…   Compiling http-body-util v0.1.3
    Building [================>        ] 202/292: http-body, pyo3-macros-back…    Building [================>        ] 203/292: http-body, pyo3-macros-back…    Building [================>        ] 204/292: pyo3-macros-backend, rusqli…    Building [================>        ] 205/292: pyo3-macros-backend, rusqli…    Building [================>        ] 206/292: pyo3-macros-backend, rusqli…    Building [================>        ] 207/292: pyo3-macros-backend, rusqli…    Building [================>        ] 208/292: pyo3-macros-backend, rusqli…   Compiling regex-automata v0.4.14
   Compiling tower-http v0.5.2
    Building [================>        ] 209/292: pyo3-macros-backend, rusqli…    Building [================>        ] 210/292: pyo3-macros-backend, rusqli…   Compiling time v0.3.47
    Building [=================>       ] 211/292: pyo3-macros-backend, rusqli…    Building [=================>       ] 212/292: pyo3-macros-backend, rusqli…    Building [=================>       ] 213/292: pyo3-macros-backend, rusqli…   Compiling rustls-webpki v0.101.7
   Compiling sct v0.7.1
    Building [=================>       ] 214/292: pyo3-macros-backend, rusqli…    Building [=================>       ] 215/292: pyo3-macros-backend, rusqli…   Compiling icu_provider v2.2.0
    Building [=================>       ] 216/292: pyo3-macros-backend, rusqli…   Compiling rustls v0.21.12
    Building [=================>       ] 217/292: pyo3-macros-backend, rusqli…    Building [=================>       ] 218/292: pyo3-macros-backend, rusqli…   Compiling icu_normalizer v2.2.0
   Compiling icu_properties v2.2.0
    Building [=================>       ] 218/292: icu_normalizer, pyo3-macros…    Building [=================>       ] 219/292: icu_normalizer, pyo3-macros…    Building [=================>       ] 220/292: icu_normalizer, pyo3-macros…    Building [=================>       ] 221/292: icu_normalizer, pyo3-macros…   Compiling serde v1.0.228
   Compiling serde_json v1.0.149
   Compiling serde_path_to_error v0.1.20
    Building [==================>      ] 222/292: icu_normalizer, pyo3-macros…    Building [==================>      ] 223/292: icu_normalizer, pyo3-macros…    Building [==================>      ] 224/292: icu_normalizer, pyo3-macros…    Building [==================>      ] 225/292: icu_normalizer, pyo3-macros…    Building [==================>      ] 226/292: pyo3-macros-backend, serde_…   Compiling serde_yaml v0.9.34+deprecated
   Compiling serde_urlencoded v0.7.1
    Building [==================>      ] 227/292: pyo3-macros-backend, serde_…   Compiling simple_asn1 v0.6.4
    Building [==================>      ] 227/292: pyo3-macros-backend, simple…   Compiling futures v0.3.32
   Compiling axum-core v0.4.5
    Building [==================>      ] 228/292: pyo3-macros-backend, simple…    Building [==================>      ] 229/292: pyo3-macros-backend, simple…    Building [==================>      ] 230/292: pyo3-macros-backend, simple…    Building [==================>      ] 231/292: pyo3-macros-backend, simple…   Compiling idna_adapter v1.2.2
    Building [==================>      ] 231/292: pyo3-macros-backend, idna_a…   Compiling lsp-types v0.97.0
   Compiling jsonwebtoken v9.3.1
   Compiling idna v1.1.0
    Building [==================>      ] 232/292: pyo3-macros-backend, idna_a…    Building [==================>      ] 233/292: pyo3-macros-backend, serde_…    Building [===================>     ] 234/292: pyo3-macros-backend, serde_…    Building [===================>     ] 235/292: pyo3-macros-backend, idna, …   Compiling url v2.5.8
   Compiling pyo3-macros v0.22.6
    Building [===================>     ] 236/292: idna, pyo3-macros, rustls, …    Building [===================>     ] 237/292: pyo3-macros, rustls, axum-c…    Building [===================>     ] 238/292: rustls, axum-core, serde_ya…    Building [===================>     ] 239/292: rustls, axum-core, serde_ya…   Compiling regex v1.12.3
   Compiling matchers v0.2.0
    Building [===================>     ] 239/292: regex, matchers, rustls, ax…    Building [===================>     ] 240/292: regex, matchers, rustls, ax…    Building [===================>     ] 241/292: regex, matchers, rustls, ax…   Compiling tracing-subscriber v0.3.23
    Building [===================>     ] 241/292: regex, matchers, tracing-su…    Building [===================>     ] 242/292: regex, tracing-subscriber, …   Compiling sase_core v0.28.0 (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/sase/repos/linked/sase-core/crates/sase_core)
    Building [===================>     ] 243/292: tracing-subscriber, rustls,…   Compiling tokio-util v0.7.18
   Compiling tower v0.5.3
   Compiling tokio-rustls v0.24.1
   Compiling hyper v1.9.0
    Building [===================>     ] 243/292: tower, hyper, tracing-subsc…    Building [===================>     ] 244/292: tower, hyper, tracing-subsc…    Building [===================>     ] 245/292: tower, hyper, tracing-subsc…    Building [====================>    ] 246/292: tower, hyper, tracing-subsc…    Building [====================>    ] 247/292: hyper, tracing-subscriber, …   Compiling h2 v0.3.27
    Building [====================>    ] 248/292: hyper, tracing-subscriber, …   Compiling hyper-util v0.1.20
    Building [====================>    ] 248/292: hyper, hyper-util, tracing-…    Building [====================>    ] 249/292: hyper, hyper-util, tracing-…   Compiling axum v0.7.9
    Building [====================>    ] 249/292: axum, hyper, hyper-util, tr…    Building [====================>    ] 250/292: axum, hyper-util, tracing-s…    Building [====================>    ] 251/292: axum, tracing-subscriber, p…    Building [====================>    ] 252/292: axum, tracing-subscriber, p…    Building [====================>    ] 253/292: axum, pyo3, lsp-types, sase…    Building [====================>    ] 254/292: axum, lsp-types, sase_core(…   Compiling hyper v0.14.32
    Building [====================>    ] 254/292: axum, lsp-types, hyper, sas…    Building [====================>    ] 255/292: axum, lsp-types, hyper, sas…    Building [====================>    ] 256/292: lsp-types, hyper, sase_core…   Compiling hyper-rustls v0.24.2
    Building [====================>    ] 256/292: hyper-rustls, lsp-types, hy…   Compiling reqwest v0.11.27
    Building [====================>    ] 256/292: reqwest, hyper-rustls, lsp-…    Building [=====================>   ] 257/292: reqwest, lsp-types, hyper, …    Building [=====================>   ] 258/292: reqwest, lsp-types, sase_co…   Compiling tower-lsp-server v0.21.1
    Building [=====================>   ] 258/292: reqwest, tower-lsp-server, …    Building [=====================>   ] 259/292: reqwest, tower-lsp-server, …    Building [=====================>   ] 260/292: reqwest, sase_core(test), s…    Building [=====================>   ] 261/292: sase_core(test), sase_core     Compiling sase_xprompt_lsp v0.28.0 (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/sase/repos/linked/sase-core/crates/sase_xprompt_lsp)
   Compiling sase_gateway v0.28.0 (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/sase/repos/linked/sase-core/crates/sase_gateway)
    Building [=====================>   ] 261/292: sase_xprompt_lsp, sase_gate…    Building [=====================>   ] 262/292: sase_gateway, sase_core(tes…    Building [=====================>   ] 263/292: sase_core(test), sase_core     Compiling sase_core_py v0.28.0 (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/sase/repos/linked/sase-core/crates/sase_core_py)
    Building [=====================>   ] 267/292: config_parity(test), agent_…    Building [=====================>   ] 268/292: config_parity(test), agent_…    Building [======================>  ] 269/292: config_parity(test), agent_…    Building [======================>  ] 270/292: config_parity(test), agent_…    Building [======================>  ] 271/292: config_parity(test), agent_…    Building [======================>  ] 272/292: config_parity(test), agent_…    Building [======================>  ] 273/292: config_parity(test), agent_…    Building [======================>  ] 274/292: config_parity(test), agent_…    Building [======================>  ] 275/292: config_parity(test), agent_…    Building [======================>  ] 276/292: config_parity(test), agent_…    Building [======================>  ] 277/292: config_parity(test), agent_…    Building [======================>  ] 278/292: config_parity(test), agent_…    Building [======================>  ] 279/292: config_parity(test), agent_…    Building [======================>  ] 280/292: config_parity(test), agent_…    Building [=======================> ] 281/292: config_parity(test), agent_…    Building [=======================> ] 282/292: config_parity(test), jsonrp…    Building [=======================> ] 283/292: config_parity(test), jsonrp…    Building [=======================> ] 284/292: jsonrpc_stdio(test), sase-x…    Building [=======================> ] 285/292: jsonrpc_stdio(test), sase_c…    Building [=======================> ] 286/292: sase_core_rs(test), sase_xp…    Building [=======================> ] 287/292: sase_xprompt_lsp(test), sas…    Building [=======================> ] 288/292: sase_core(test), sase_gatew…    Building [=======================> ] 289/292: sase_core(test), sase_core_…    Building [=======================> ] 291/292: sase_core(test)                 Finished `test` profile [unoptimized + debuginfo] target(s) in 1m 12s
     Running unittests src/lib.rs (target/debug/deps/sase_core-908276d0af21f757)

running 1700 tests
test agent_clan_tribe::tests::absent_declarations_resolve_to_none ... ok
test agent_clan_tribe::tests::absent_summaries_resolve_to_none ... ok
test agent_clan_tribe::tests::latest_explicit_declaration_wins_and_omissions_do_not_clear ... ok
test agent_clan_tribe::tests::latest_explicit_summary_wins_and_omissions_do_not_clear ... ok
test agent_clan_tribe::tests::repeated_declarations_and_generations_are_scoped ... ok
test agent_clan_tribe::tests::stable_identity_breaks_equal_timestamp_summary_ties ... ok
test agent_clan_tribe::tests::repeated_summaries_and_generations_are_scoped ... ok
test agent_clan_tribe::tests::stable_identity_breaks_equal_timestamp_ties ... ok
test agent_cleanup::execution::tests::bundle_filename_and_shard_match_dismissed_layout ... ok
test agent_cleanup::execution::tests::delete_agent_artifact_markers_removes_loader_files_only ... ok
test agent_cleanup::execution::tests::release_workspace_text_removes_empty_running_field ... ok
test agent_cleanup::execution::tests::release_workspace_text_removes_matching_claim_and_cleans_field ... ok
test agent_cleanup::execution::tests::mark_running_hook_mentor_and_comment_suffixes_as_killed ... ok
test agent_cleanup::execution::tests::save_dismissed_bundle_json_writes_sharded_pretty_json ... ok
test agent_cleanup::execution::tests::save_dismissed_bundle_json_replaces_existing_bundle ... ok
test agent_cleanup::planner::tests::broad_scopes_keep_child_rows_cascade_only ... ok
test agent_cleanup::planner::tests::clan_scope_keeps_active_parallel_family_root_from_dismissal ... ok
test agent_cleanup::planner::tests::completed_workflow_parent_gets_timestamp_and_workflow_releases ... ok
test agent_cleanup::planner::tests::clan_scope_without_generation_selects_all_generations ... ok
test agent_cleanup::planner::tests::clan_scope_filters_generation_and_partitions_with_workflow_cascade ... ok
test agent_cleanup::planner::tests::all_panels_kill_and_dismiss_partitions_targets ... ok
test agent_cleanup::planner::tests::direct_child_side_effects_include_child_not_siblings ... ok
test agent_cleanup::planner::tests::direct_workflow_child_does_not_release_parent_workspace_claim ... ok
test agent_cleanup::planner::tests::dismiss_side_effects_allow_duplicate_historical_names ... ok
test agent_cleanup::planner::tests::dismissable_statuses_include_stopped ... ok
test agent_cleanup::planner::tests::dismiss_side_effects_preserve_names ... ok
test agent_cleanup::planner::tests::dismissable_statuses_include_tale_done ... ok
test agent_cleanup::planner::tests::dismissing_parallel_root_cascades_only_after_members_finish ... ok
test agent_cleanup::planner::tests::explicit_child_only_completed_target_becomes_dismiss_item ... ok
test agent_cleanup::planner::tests::explicit_child_only_running_target_becomes_kill_item ... ok
test agent_cleanup::planner::tests::explicit_identities_select_only_marked_targets ... ok
test agent_cleanup::planner::tests::focused_panel_selects_matching_tribe_and_dismisses_completed ... ok
test agent_cleanup::planner::tests::killing_one_parallel_member_leaves_root_and_siblings_untouched ... ok
test agent_cleanup::planner::tests::no_op_plan_reports_none_severity ... ok
test agent_cleanup::planner::tests::parallel_family_root_kill_cascades_to_live_members_only ... ok
test agent_cleanup::planner::tests::stopped_row_is_dismissed_not_killed_or_failed ... ok
test agent_cleanup::planner::tests::tribe_scope_uses_parent_tribe_for_workflow_children_but_skips_child_directly ... ok
test agent_cleanup::planner::tests::unknown_kill_kind_is_skipped ... ok
test agent_cleanup::planner::tests::workflow_parent_cascade_deduplicates_child_inputs ... ok
test agent_family::tests::absent_parent_reports_absent ... ok
test agent_family::tests::dismissed_parent_reports_dismissed ... ok
test agent_family::tests::duplicate_newest_timestamp_reports_ambiguous ... ok
test agent_family::tests::newest_terminal_visible_parent_wins ... ok
test agent_family::tests::non_terminal_parent_reports_running ... ok
test agent_archive::tests::mark_agent_archive_bundles_revived_updates_bundle_and_index ... ok
test agent_group_archive::tests::missing_group_name_loads_as_none ... ok
test agent_group_archive::tests::corrupt_and_missing_group_files_are_tolerated ... ok
test agent_group_archive::tests::load_group_keeps_refs_when_bundle_files_are_missing ... ok
test agent_group_archive::tests::delete_group_removes_only_requested_metadata_record ... ok
test agent_group_archive::tests::missing_ref_prompt_preview_loads_as_none ... ok
test agent_group_archive::tests::mark_group_revived_preserves_metadata ... ok
test agent_identity::identity::tests::explicit_owner_prevents_mismatched_strip ... ok
test agent_identity::identity::tests::family_hood_ancestors_and_membership_are_canonical ... ok
test agent_identity::identity::tests::globalization_normalizes_archive_and_round_trips ... ok
test agent_group_archive::tests::recent_groups_tolerate_corrupt_files_and_mark_revived ... ok
test agent_identity::identity::tests::hood_membership_never_raises_for_historical_candidates ... ok
test agent_group_archive::tests::recent_groups_replace_same_group_id ... ok
test agent_identity::identity::tests::legacy_globalization_verifies_machine_hood ... ok
test agent_group_archive::tests::whitespace_group_name_normalizes_to_none ... ok
test agent_identity::identity::tests::legacy_v1_group_ownership_evidence_matrix ... ok
test agent_identity::identity::tests::historical_family_classification_is_total_and_canonical ... ok
test agent_identity::identity::tests::legacy_v1_group_ownership_rejects_impossible_evidence ... ok
test agent_identity::identity::tests::link_targets_distinguish_family_and_solo ... ok
test agent_identity::identity::tests::localization_covers_all_owner_cases ... ok
test agent_identity::identity::tests::ownership_classification_never_parses_names ... ok
test agent_identity::identity::tests::unsafe_names_and_empty_remainders_fail ... ok
test agent_identity::identity::tests::username_and_owner_validation_matrix ... ok
test agent_identity::relationships::tests::historical_family_names_validate_in_relationship_batches ... ok
test agent_group_archive::tests::save_list_and_load_preserve_group_name ... ok
test agent_identity::relationships::tests::rejects_bad_container_members_and_names ... ok
test agent_identity::relationships::tests::rejects_duplicate_runs_names_and_containers ... ok
test agent_identity::relationships::tests::complete_mapping_rewrites_all_run_id_fields_in_input_order ... ok
test agent_identity::relationships::tests::serde_contract_rejects_machine_local_and_unknown_state ... ok
test agent_identity::relationships::tests::mapping_must_be_complete_unique_and_exact ... ok
test agent_launch::tests::fanout_plan_round_trips_slots ... ok
test agent_identity::relationships::tests::valid_mixed_batch_returns_canonical_summary ... ok
test agent_launch::tests::allocate_and_claim_picks_first_available_workspace ... ok
test agent_identity::relationships::tests::rejects_self_duplicate_and_cyclic_edges ... ok
test agent_identity::relationships::tests::required_optional_and_cross_owner_targets_are_enforced ... ok
test agent_launch::tests::claim_workspace_rejects_duplicate_nonzero_but_allows_zero ... ok
test agent_launch::tests::launch_request_round_trips_json_shape ... ok
test agent_launch::tests::render_alternative_prompt_empty_branch_does_not_invent_space ... ok
test agent_launch::tests::prepared_wire_preserves_null_claim_request ... ok
test agent_launch::tests::prepare_agent_launch_deferred_and_home_claim_shapes ... ok
test agent_launch::tests::timestamp_batch_rejects_invalid_format ... ok
test agent_launch::tests::prepare_agent_launch_writes_prompt_and_shapes_process_data ... ok
test agent_launch::tests::timestamp_batch_allocates_unique_visible_timestamps ... ok
test agent_launch::tests::timestamp_batch_starts_after_previous_allocation ... ok
test agent_name_template::tests::derives_namespace_template_shapes ... ok
test agent_launch::tests::transfer_workspace_claim_matches_pid_and_preserves_claim_name ... ok
test agent_name_template::tests::compares_by_auto_sequence_order ... ok
test agent_launch::tests::workspace_claims_parse_valid_rows_and_ignore_malformed ... ok
test agent_name_template::tests::generates_shortlex_tokens ... ok
test agent_archive::tests::query_agent_archive_returns_paged_summary_rows ... ok
test agent_name_template::tests::parses_exactly_one_marker ... ok
test agent_name_template::tests::matches_template_tokens ... ok
test agent_name_template::tests::parses_keyed_markers ... ok
test agent_name_template::tests::renders_template_shapes ... ok
test agent_name_template::tests::scanner_ignores_invalid_braced_and_jinja_forms ... ok
test agent_name_template::tests::rejects_invalid_or_multiple_markers ... ok
test agent_name_template::tests::scans_markers_with_round_trip_byte_spans ... ok
test agent_name_template::tests::render_and_match_are_exact_inverses ... ok
test agent_runtime::tests::approved_plan_followup_starts_a_new_active_segment ... ok
test agent_runtime::tests::answered_question_gap_between_segments_is_excluded ... ok
test agent_runtime::tests::empty_input_has_zero_inactive_runtime ... ok
test agent_runtime::tests::gaps_and_sequential_members_are_summed ... ok
test agent_runtime::tests::earliest_valid_stop_or_finish_is_shared_runtime_end ... ok
test agent_runtime::tests::malformed_terminal_and_reversed_segments_are_rejected ... ok
test agent_runtime::tests::malformed_timestamps_do_not_contribute ... ok
test agent_runtime::tests::open_intervals_end_at_now_and_mark_runtime_active ... ok
test agent_runtime::tests::pending_question_window_extends_to_now_and_does_not_tick ... ok
test agent_runtime::tests::plan_feedback_window_is_excised ... ok
test agent_runtime::tests::slot_yield_needs_a_resolved_question_answer_time ... ok
test agent_runtime::tests::overlapping_members_are_measured_once ... ok
test agent_runtime::tests::synthesized_terminal_never_supplies_the_runtime_end ... ok
test agent_runtime::tests::wait_policies_distinguish_plan_review_from_slot_yields ... ok
test agent_runtime::tests::unresolved_plan_caps_a_live_member_and_does_not_tick ... ok
test agent_scan::index::tests::abandoned_terminalization_prefers_stopped_at_then_directory_mtime ... ok
test agent_group_archive::tests::recent_groups_are_capped_and_list_newest_first ... ok
test agent_launch::tests::fanout_planner_deprecated_time_directive_is_not_special ... ok
test agent_launch::tests::fanout_planner_time_waits_defer_workspace ... ok
test agent_launch::tests::fanout_planner_t_xprompt_defer_workspace ... ok
test agent_group_archive::tests::save_and_list_pages_saved_groups_newest_first ... ok
test agent_identity::relationships::tests::rejects_schema_unsafe_oversized_and_owner_mismatch ... ok
test agent_launch::tests::fanout_planner_extracts_repeat_slots ... ok
test agent_launch::tests::fanout_planner_does_not_support_removed_name_spellings ... ok
test agent_launch::tests::fanout_planner_brace_single_branch_has_implicit_empty_variant ... ok
test agent_launch::tests::launch_inline_scanner_preserves_argument_parser_precedence ... ok
test agent_launch::tests::fanout_planner_rejects_repeated_top_level_model_directives ... ok
test agent_launch::tests::fanout_planner_empty_branch_removes_space_before_punctuation ... ok
test agent_launch::tests::fanout_planner_brace_composes_cartesian_with_paren_alt ... ok
test agent_launch::tests::fanout_planner_brace_branch_text_keeps_commas ... ok
test agent_launch::tests::fanout_planner_correlates_shared_named_alt_keys ... ok
test agent_launch::tests::fanout_planner_empty_branch_collapses_multiple_spaces ... ok
test agent_launch::tests::fanout_planner_rejects_repeated_models_with_brace_alternatives ... ok
test agent_launch::tests::fanout_planner_empty_branch_removes_leading_space ... ok
test agent_launch::tests::fanout_planner_correlated_group_mixes_named_and_unnamed_ids ... ok
test agent_launch::tests::fanout_planner_cartesian_products_independent_correlated_groups ... ok
test agent_launch::tests::fanout_planner_brace_named_text_blocks ... ok
test agent_launch::tests::fanout_planner_single_shared_key_collapses_to_one_slot ... ok
test agent_launch::tests::fanout_planner_brace_nested_pipes_do_not_split ... ok
test agent_launch::tests::fanout_planner_brace_model_branches_match_paren_parity ... ok
test agent_launch::tests::fanout_planner_preserves_named_alt_ids_and_values_only ... ok
test agent_launch::tests::fanout_planner_empty_branch_preserves_newlines_and_indentation ... ok
test agent_launch::tests::fanout_planner_model_alt_ids_preserve_named_model_branches ... ok
test agent_launch::tests::fanout_planner_empty_branch_removes_trailing_space ... ok
test agent_launch::tests::extract_first_model_value_strips_known_effort_suffix ... ok
test agent_launch::tests::fanout_planner_empty_branch_collapses_between_words ... ok
test agent_launch::tests::fanout_planner_preserves_repeat_bead_association ... ok
test agent_launch::tests::fanout_planner_model_value_fanout_after_directive_colon ... ok
test agent_launch::tests::fanout_planner_single_top_level_model_is_single_launch ... ok
test agent_launch::tests::fanout_planner_value_fanouts_compose_cartesian ... ok
test agent_launch::tests::fanout_planner_allocates_unnamed_alt_ids_after_named_ids ... ok
test agent_launch::tests::fanout_planner_ignores_alternative_inside_adjacent_inline_code ... ok
test agent_launch::tests::fanout_planner_brace_model_branches_report_model_slots ... ok
test agent_launch::tests::fanout_planner_brace_value_fanout_after_directive_colon ... ok
test agent_launch::tests::fanout_planner_brace_named_and_numeric_branch_ids ... ok
test agent_launch::tests::fanout_planner_ignores_models_inside_adjacent_inline_code ... ok
test agent_launch::tests::fanout_planner_strips_branch_effort_for_slot_naming ... ok
test agent_launch::tests::fanout_planner_rejects_paren_multi_model_directive ... ok
test agent_launch::tests::fanout_planner_unclosed_brace_reports_missing_close ... ok
test agent_launch::tests::fanout_planner_rejects_repeated_top_level_models_with_alternatives ... ok
test agent_launch::tests::fanout_planner_rejects_same_value_repeated_model_directives ... ok
test agent_launch::tests::fanout_planner_unvalued_model_markers_do_not_count_as_repeated ... ok
test agent_scan::index::tests::index_query_wire_round_trips_active_limit ... ok
test agent_launch::tests::fanout_planner_brace_value_fanout_after_effort_e_alias ... ok
test agent_launch::tests::fanout_planner_brace_shorthand_splits_pipe_branches ... ok
test agent_launch::tests::fanout_planner_empty_branch_preserves_following_directive_separator ... ok
test agent_launch::tests::fanout_planner_correlates_transitive_alt_keys ... ok
test agent_launch::tests::fanout_planner_splits_multi_prompt_outside_fences ... ok
test agent_launch::tests::fanout_planner_splits_model_branches_and_alternatives ... ok
test agent_launch::tests::fanout_planner_preserves_repeat_and_id_inside_literal_zones ... ok
test agent_launch::tests::fanout_planner_ignores_wait_forms_inside_adjacent_inline_code ... ok
test agent_launch::tests::fanout_planner_composes_cartesian_alt_ids ... ok
test agent_scan::index::tests::replace_unusable_index_file_renames_sidecars ... ok
test agent_scan::index::tests::prompt_snippet_truncation_stays_on_utf8_char_boundary ... ok
test agent_scan::layout::tests::canonical_ace_run_path_is_day_sharded ... ok
test agent_scan::layout::tests::non_ace_run_path_stays_flat ... ok
test agent_scan::layout::tests::parse_accepts_legacy_and_sharded_paths ... ok
test agent_scan::layout::tests::parse_rejects_malformed_shard_paths ... ok
test agent_scan::selector::tests::parser_accepts_nested_and_escaped_paths ... ok
test agent_scan::selector::tests::parser_rejects_invalid_selectors ... ok
test agent_scan::selector::tests::parser_splits_dotted_names_from_the_right ... ok
test agent_scan::wire::tests::agent_meta_wire_round_trips_alias_trail_and_origin ... ok
test agent_scan::wire::tests::agent_meta_wire_round_trips_every_monitor_field ... ok
test agent_scan::wire::tests::agent_meta_wire_without_monitor_fields_still_parses ... ok
test agent_scan::wire::tests::done_marker_wire_round_trips_every_monitor_field ... ok
test agent_scan::wire::tests::done_marker_wire_without_monitor_fields_still_parses ... ok
test agent_scan::wire::tests::prompt_step_marker_wire_defaults_absent_alias_trail ... ok
test agent_scan::wire::tests::prompt_step_marker_wire_round_trips_alias_trail_and_origin ... ok
test agent_scan::index::tests::alias_history_rejects_empty_aliases ... ok
test agent_scan::index::tests::alias_history_status_counts_projection_rows ... ok
test agent_scan::index::tests::alias_history_falls_back_to_legacy_first_hop ... ok
test agent_stats::activity::tests::rejects_invalid_range_before_opening_index ... ok
test agent_stats::activity::tests::skips_malformed_bundles_and_ignores_legacy_question_store ... ok
test agent_stats::activity::tests::maps_both_response_shapes_and_pending_plan_bundles ... ok
test agent_scan::index::tests::active_query_excludes_dismissed_identity_after_rebuild ... ok
test agent_scan::layout::tests::resolve_legacy_path_to_shard_when_present ... ok
test agent_scan::layout::tests::collect_prefers_sharded_duplicate_timestamp ... ok
test agent_scan::scanner::tests::scanner_round_trips_alias_trail_and_origin ... ok
test agent_scan::scanner::tests::scanner_defaults_absent_alias_trail_and_origin ... ok
test agent_stats::run::tests::rejects_invalid_ranges_and_bucket_explosions ... ok
test agent_stats::activity::tests::aggregates_logs_and_project_scoped_gate_bundles ... ok
test agent_scan::index::tests::query_keeps_corrupt_existing_index_strict ... ok
test agent_scan::index::tests::alias_history_revalidate_refreshes_candidate_rows ... ok
test agent_scan::index::tests::alias_history_filters_hidden_and_project_keys ... ok
test agent_scan::index::tests::alias_history_prompt_snippets_strip_collapse_and_truncate ... ok
test agent_scan::index::tests::alias_history_preserves_request_order_and_empty_groups ... ok
test agent_scan::index::tests::anonymous_appears_as_agent_workflow_is_not_hidden ... ok
test agent_scan::index::tests::alias_history_truncates_newest_first_and_reports_counts ... ok
test agent_scan::index::tests::bounded_artifact_index_delete_skips_locked_database ... ok
test agent_stats::run::tests::runtime_percentiles_interpolate_sorted_durations ... ok
test agent_scan::index::tests::alias_history_projection_replaces_and_deletes_rows ... ok
test agent_stats::runner::tests::host_liveness_requires_current_matching_claim_identity ... ok
test agent_stats::runner::tests::open_intervals_require_liveness_and_missing_starts_are_not_invalid ... ok
test agent_stats::runner::tests::simultaneous_boundaries_do_not_create_phantom_occupancy ... ok
test agent_stats::runner::tests::trend_is_strictly_bounded_and_keeps_partial_final_slice ... ok
test agent_stats::wire::tests::older_commit_stats_without_committing_runs_default ... ok
test agent_stats::wire::tests::older_run_stats_payload_without_runners_deserializes ... ok
test agent_stats::wire::tests::older_run_stats_payload_without_xprompts_deserializes ... ok
test agent_stats::wire::tests::older_run_stats_request_uses_xprompt_defaults ... ok
test agent_stats::wire::tests::older_xprompt_row_without_truncation_counts_defaults ... ok
test artifact_consumption::tests::reader_is_tolerant_of_bad_rows_and_an_absent_file ... ok
test agent_stats::run::tests::missing_archive_spec_is_not_malformed ... ok
test artifact_consumption::tests::restricted_summary_omits_unselected_and_never_consumed_refs ... ok
test artifact_consumption::tests::summary_distinguishes_events_from_distinct_agents ... ok
test artifact_file::economics::tests::aggregates_mixed_rows_truncation_redundancy_and_projections ... ok
test artifact_file::economics::tests::single_day_window_has_finite_rates_and_schema_is_checked ... ok
test artifact_file::retention::tests::invalid_now_and_schema_are_rejected ... ok
test artifact_file::retention::tests::each_additional_predicate_filters_generation_candidates ... ok
test artifact_file::retention::tests::protects_explicit_and_referenced_and_separates_byte_free_rows ... ok
test artifact_file::retention::tests::predicates_compose_clamp_generation_floor_and_limit_deterministically ... ok
test artifact_file::retention::tests::retention_now_uses_its_embedded_offset_calendar_date ... ok
test artifact_file::tests::absent_index_is_empty_and_invalid_since_is_an_error ... ok
test artifact_file::retention::tests::zero_keep_without_other_predicates_disables_selection ... ok
test artifact_file::tests::embedded_offset_controls_calendar_date_but_sorting_uses_instant ... ok
test artifact_file::tests::parser_accepts_supported_range_and_skips_bad_rows ... ok
test artifact_file::tests::query_sorts_newest_first_missing_last_and_applies_limit ... ok
test artifact_file::tests::query_applies_every_filter_individually_and_combined ... ok
test artifact_file::tests::since_uses_plan_search_forms_and_excludes_missing_dates ... ok
test artifact_file::tests::unused_filter_runs_before_limit_and_tolerates_missing_ledgers ... ok
test artifact_file::trash::tests::byte_free_collision_and_unreadable_listing_are_deterministic ... ok
test artifact_file::trash::tests::refuses_symlink_escape_and_unsafe_entry_id ... ok
test artifact_file::trash::tests::byte_backed_store_list_restore_and_purge_round_trip ... ok
test agent_stats::run::tests::aggregates_swarm_xprompt_kind_through_stats_wire ... ok
test agent_stats::activity::tests::counts_gate_even_when_index_row_is_hidden_abandoned ... ok
test agent_scan::index::tests::wait_completed_records_are_indexed_as_running ... ok
test agent_stats::run::tests::aggregates_ranked_xprompt_usage_and_focused_breakdowns ... ok
test artifact_file::vcs::tests::rejects_cache_path_escape_inputs ... ok
test artifact_object_store::tests::object_paths_reject_non_full_lowercase_sha256 ... ok
test artifact_object_store::tests::object_relpath_uses_digest_shard ... ok
test agent_scan::index::tests::active_limit_prioritizes_waiting_rows_over_newer_stale_rows ... ok
test artifact_ref::entry::tests::rejects_empty_stable_id_and_bad_kind ... ok
test artifact_ref::entry::tests::rejects_malformed_revision_digest_and_property_keys ... ok
test artifact_ref::entry::tests::valid_entry_passes ... ok
test artifact_ref::expansion::tests::double_braces_escape_to_literal_braces ... ok
test artifact_ref::expansion::tests::substituted_values_are_never_rescanned ... ok
test artifact_ref::expansion::tests::missing_value_is_a_render_error ... ok
test artifact_ref::expansion::tests::unknown_placeholder_and_unbalanced_braces_are_rejected ... ok
test artifact_ref::expansion::tests::validate_returns_placeholders_in_first_seen_order_without_duplicates ... ok
test artifact_ref::file_roots::tests::absolute_and_home_paths_resolve_to_one_logical_path ... ok
test artifact_ref::file_roots::tests::directories_and_size_overages_are_denied ... ok
test artifact_ref::file_roots::tests::file_path_payload_still_round_trips_as_a_file_path_payload ... ok
test artifact_ref::file_roots::tests::missing_inside_root_is_missing_and_traversal_escape_is_filtered ... ok
test artifact_ref::file_roots::tests::overlapping_roots_are_ambiguous_and_glob_miss_is_filtered ... ok
test artifact_ref::file_roots::tests::relative_paths_and_zero_roots_are_rejected_without_guessing ... ok
test artifact_ref::filter::tests::batch_filter_reports_allowed_and_filtered_in_input_order ... ok
test artifact_ref::filter::tests::explicit_empty_filter_allows_nothing ... ok
test artifact_ref::file_roots::tests::symlink_escape_fifo_and_unreadable_files_are_denied ... ok
test artifact_ref::filter::tests::globstar_matches_root_and_nested_paths_case_sensitively ... ok
test artifact_ref::filter::tests::malformed_patterns_and_unsafe_payloads_error ... ok
test artifact_ref::filter::tests::negative_only_allows_everything_except_vetoes ... ok
test artifact_ref::filter::tests::positives_or_together_and_negations_veto ... ok
test artifact_ref::kinds::tests::canonical_parse_rewrites_commit_and_plans_but_nothing_else ... ok
test artifact_ref::kinds::tests::catalog_lists_reserved_kinds_offered_in_completion ... ok
test artifact_ref::kinds::tests::catalog_marks_aliases_and_historical_kinds_absent_from_completion ... ok
test artifact_ref::kinds::tests::commit_canonicalizes_to_stitch_without_a_diagnostic ... ok
test artifact_file::vcs::tests::replaces_wrong_cache_content_after_verifying_git_blob ... ok
test artifact_ref::kinds::tests::plans_canonicalizes_to_plan_with_a_diagnostic ... ok
test artifact_ref::kinds::tests::default_parse_is_byte_identical_for_every_historical_kind ... ok
test artifact_ref::kinds::tests::unregistered_labels_canonicalize_to_themselves ... ok
test artifact_ref::list::tests::batch_resolve_loads_the_artifact_index_once ... ok
test artifact_ref::list::tests::normalize_deduplicates_in_first_occurrence_order ... ok
test artifact_ref::list::tests::parse_rejects_malformed_sigiled_and_empty_entries_with_position ... ok
test artifact_ref::list::tests::parse_and_normalize_every_kind_and_fragment ... ok
test artifact_ref::provider_spec::tests::accepts_two_cell_emoji_icon ... ok
test artifact_ref::provider_spec::tests::rejects_bad_expansion_format ... ok
test artifact_ref::provider_spec::tests::rejects_bad_inventory_globs_and_publication_values ... ok
test artifact_ref::provider_spec::tests::digest_changes_when_icon_changes ... ok
test artifact_ref::provider_spec::tests::rejects_missing_or_malformed_icon ... ok
test artifact_ref::provider_spec::tests::rejects_reserved_kind_and_bad_identifiers ... ok
test artifact_ref::list::tests::malformed_entry_does_not_abort_valid_neighbors ... ok
test artifact_ref::provider_spec::tests::rejects_property_type_enum_and_source_issues ... ok
test artifact_ref::provider_spec::tests::rejects_undeclared_detail_and_identity_properties ... ok
test artifact_file::vcs::tests::materializes_direct_blob_then_uses_verified_cache ... ok
test artifact_ref::provider_spec::tests::rejects_unsupported_schema_version ... ok
test artifact_ref::ref_files::tests::fold_deduplicates_versions_and_unions_provenance ... ok
test artifact_ref::provider_spec::tests::valid_spec_passes_and_digest_is_stable ... ok
test artifact_ref::ref_files::tests::validation_rejects_bad_identity_fields ... ok
test artifact_ref::ref_files::tests::row_round_trips_and_parse_skips_bad_and_future_lines ... ok
test artifact_ref::scanner::tests::fragment_splits_after_the_closing_quote ... ok
test artifact_ref::scanner::tests::quote_artifact_ref_argument_round_trips_through_the_scanner ... ok
test artifact_ref::scanner::tests::quoted_argument_with_spaces_parses_and_round_trips ... ok
test artifact_ref::scanner::tests::quoted_argument_supports_escaped_quote_and_backslash ... ok
test artifact_ref::scanner::tests::quoted_trailing_punctuation_is_not_trimmed ... ok
test artifact_ref::scanner::tests::unterminated_quote_at_true_eof_ends_at_end_of_text ... ok
test artifact_ref::scanner::tests::unterminated_quote_ends_at_the_current_line_never_at_eof ... ok
test artifact_ref::tests::agent_resolution_globalizes_and_preserves_historical_names ... ok
test artifact_ref::tests::canonicalization_recognizes_only_canonical_entity_pages ... ok
test artifact_ref::tests::commit_resolution_still_considers_sidecar_repositories ... ok
test artifact_ref::tests::bead_resolution_covers_pages_projects_and_ambiguity ... ok
test artifact_ref::tests::canonicalization_uses_order_and_artifact_index ... ok
test artifact_ref::tests::context_schema_version_is_required_for_context_operations ... ok
test artifact_ref::tests::file_path_payloads_accept_fragments_and_stitch_shorthand_bounds ... ok
test artifact_ref::tests::every_kind_and_fragment_round_trips ... ok
test artifact_ref::tests::document_path_globs_filter_resolution_and_canonicalization ... ok
test artifact_ref::tests::filtered_drift_candidates_are_not_reported ... ok
test artifact_ref::tests::filtered_root_cannot_be_bypassed_by_later_duplicate_roots ... ok
test artifact_ref::tests::indexed_vcs_backed_file_resolution_is_pure_and_reports_provenance ... ok
test artifact_ref::tests::indexed_file_resolution_accepts_supported_envelope_range ... ok
test artifact_ref::tests::namespace_resolution_is_canonical_and_local ... ok
test artifact_ref::tests::parsed_references_carry_the_current_wire_schema ... ok
test artifact_ref::tests::scanner_enforces_left_context_but_scans_fences ... ok
test artifact_ref::tests::scanner_reports_utf8_byte_spans_and_malformed_candidates ... ok
test artifact_ref::tests::validate_artifact_ref_context_accepts_the_supported_range ... ok
test artifact_ref::uses::tests::manifest_parse_tolerates_unknown_fields ... ok
test artifact_ref::uses::tests::manifest_round_trip_skips_bad_and_future_lines ... ok
test artifact_ref::uses::tests::valid_record_passes ... ok
test artifact_ref::tests::path_resolution_covers_order_drift_ambiguity_and_missing ... ok
test artifact_ref::tests::parse_rejects_invalid_shapes_and_illegal_fragments ... ok
test axe_chop::tests::agent_clan_guard_short_circuits_trigger_errors ... ok
test axe_chop::tests::agent_clan_guard_matches_only_explicit_active_case_sensitive_clans ... ok
test axe_chop::tests::agent_runners_guard_counts_only_active_runner_slot_holders ... ok
test axe_chop::tests::axe_descriptions_split_into_normalized_summary_and_body ... ok
test artifact_ref::uses::tests::rejects_empty_required_fields_and_bad_kind ... ok
test axe_chop::tests::checkpoint_success_policy_commits_only_after_success ... ok
test axe_chop::tests::chop_report_rejects_control_characters_and_overlong_text ... ok
test axe_chop::tests::chop_report_rejects_ragged_rows_disallowed_glyphs_and_invalid_gauges ... ok
test axe_chop::tests::chop_report_rejects_unknown_block_kinds_and_tones ... ok
test axe_chop::tests::chop_result_without_report_remains_valid_and_serializes_null ... ok
test axe_chop::tests::chop_report_round_trips_every_block_kind ... ok
test axe_chop::tests::chop_report_rejects_excess_blocks_and_rows ... ok
test axe_chop::tests::chop_report_rejects_oversize_documents ... ok
test axe_chop::tests::clan_scoped_proposals_round_trip_without_changing_legacy_proposals ... ok
test axe_chop::tests::compound_durations_are_strict_and_positive ... ok
test axe_chop::tests::derived_agent_names_include_sanitized_bounded_run_token ... ok
test axe_chop::tests::derived_agent_names_include_target_and_order ... ok
test axe_chop::tests::derived_agent_names_keep_length_and_trailing_separator_guards ... ok
test axe_chop::tests::derived_agent_names_reject_empty_sanitized_run_token ... ok
test axe_chop::tests::earlier_guard_wins_over_agent_runners ... ok
test axe_chop::tests::git_trigger_returns_checkpoint_observation ... ok
test axe_chop::tests::guards_short_circuit_triggers ... ok
test axe_chop::tests::legacy_changespec_guard_provider_deserializes_as_patch ... ok
test axe_chop::tests::once_per_release_removes_exact_keys_and_is_idempotent ... ok
test axe_chop::tests::once_per_release_validates_engine_and_document_schemas ... ok
test axe_chop::tests::once_per_store_rejects_duplicates_and_evicts_oldest ... ok
test agent_scan::index::tests::recent_completed_rows_remain_visible_when_not_dismissed ... ok
test artifact_file::vcs::tests::searches_bounded_remote_history_when_recorded_sha_is_gone ... ok
test axe_chop::tests::strict_axe_validation_accepts_keyed_and_tagged_agent_clan_guards ... ok
test axe_chop::tests::strict_axe_validation_accepts_keyed_and_tagged_agent_runners_guards ... ok
test axe_chop::tests::strict_axe_validation_accepts_missing_descriptions_by_default ... ok
test axe_chop::tests::strict_axe_validation_accepts_new_shape ... ok
test artifact_file::vcs::tests::reports_missing_for_unknown_content_or_a_zero_history_bound ... ok
test axe_chop::tests::strict_axe_validation_accepts_nonnegative_or_missing_wait_runners ... ok
test axe_chop::tests::result_validation_accepts_proposals_and_rejects_workflows ... ok
test axe_chop::tests::strict_axe_validation_emits_only_the_first_description_shape_error ... ok
test axe_chop::tests::strict_axe_validation_counts_description_limits_in_characters ... ok
test axe_chop::tests::strict_axe_validation_gates_description_shape_and_accepts_single_lines ... ok
test axe_chop::tests::strict_axe_validation_rejects_blank_descriptions ... ok
test axe_chop::tests::strict_axe_validation_rejects_invalid_agent_clan_guards_fail_closed ... ok
test axe_chop::tests::clan_summaries_agree_per_raw_clan_before_launch ... ok
test axe_chop::tests::strict_axe_validation_rejects_invalid_wait_runners ... ok
test axe_chop::tests::strict_axe_validation_rejects_invalid_agent_runners_guards_fail_closed ... ok
test axe_chop::tests::strict_axe_validation_rejects_non_positive_log_temp_max_age ... ok
test axe_chop::tests::strict_axe_validation_reports_each_description_shape_error_precisely ... ok
test axe_chop::tests::strict_axe_validation_reports_migrations_duplicates_and_provenance ... ok
test axe_chop::tests::strict_axe_validation_requires_lumberjack_and_chop_descriptions_when_enabled ... ok
test axe_chop::tests::result_validation_rejects_forward_wait_and_unknown_fields ... ok
test axe_chop::tests::target_expansion_filters_projects_and_separates_overrides ... ok
test axe_overrun::tests::action_succeeded_with_script_duration_is_sampled_on_that_value ... ok
test axe_overrun::tests::action_succeeded_without_script_duration_is_ignored ... ok
test axe_chop::tests::target_expansion_uses_stable_hash_without_identity_field ... ok
test axe_overrun::tests::exact_equality_counts_as_over ... ok
test axe_overrun::tests::empty_history_is_none_with_null_ratios ... ok
test axe_overrun::tests::fast_skipped_newest_run_in_front_of_over_success_is_still_over ... ok
test axe_overrun::tests::live_running_run_past_interval_is_over_from_elapsed_time ... ok
test axe_overrun::tests::negative_duration_is_dropped_not_fatal ... ok
test axe_overrun::tests::newest_sampled_run_over_is_over ... ok
test axe_overrun::tests::non_positive_interval_is_an_error ... ok
test axe_overrun::tests::older_overrun_is_locatable_by_run_idx_after_a_healthy_newest_run ... ok
test axe_overrun::tests::only_an_older_run_over_is_intermittent ... ok
test axe_overrun::tests::only_ten_percent_ratio_is_not_over_and_not_intermittent ... ok
test agent_scan::index::tests::explicit_workflow_state_hidden_is_still_filtered ... ok
test axe_overrun::tests::serde_rejects_unknown_fields_and_invalid_enum_values ... ok
test axe_overrun::tests::serialization_pins_public_field_order_and_round_trips ... ok
test axe_overrun::tests::structural_validation_returns_path_specific_errors ... ok
test axe_overrun::tests::unknown_status_string_is_dropped_not_fatal ... ok
test axe_overrun::tests::unparsable_started_at_is_dropped_for_every_otherwise_sampleable_status ... ok
test axe_overrun::tests::unparsable_started_at_is_dropped_not_fatal ... ok
test axe_status::tests::desired_stopped_with_live_orchestrator_is_degraded ... ok
test axe_status::tests::historical_error_count_does_not_degrade_a_fresh_worker ... ok
test axe_status::tests::collection_error_is_a_normal_error_snapshot_with_exit_two ... ok
test axe_status::tests::lifecycle_matrix_preserves_intent_separately_from_health ... ok
test axe_status::tests::live_lumberjack_without_coherent_orchestrator_is_degraded ... ok
test axe_status::tests::live_orphan_is_retained_and_dead_unconfigured_row_is_filtered ... ok
test axe_status::tests::lumberjack_state_precedence_and_heartbeat_boundaries_are_pinned ... ok
test axe_status::tests::orchestrator_live_pid_without_lock_has_exact_evidence ... ok
test axe_status::tests::orchestrator_conflicting_live_identities_are_sorted_and_exact ... ok
test axe_status::tests::orchestrator_lock_without_live_pid_has_exact_evidence ... ok
test axe_status::tests::normalization_is_independent_of_input_order_and_duplicates ... ok
test axe_status::tests::serde_rejects_unknown_fields_and_invalid_enum_values ... ok
test axe_status::tests::structural_validation_returns_path_specific_errors ... ok
test axe_status::tests::serialization_pins_public_field_order_nulls_lists_and_enum_values ... ok
test bead::cli::tests::close_parser_accepts_force_with_reason_and_resolution ... ok
test bead::cli::tests::colored_type_cell_keeps_alignment_padding_outside_ansi_span ... ok
test bead::cli::tests::claimed_status_is_in_default_list_with_claim_details_and_color ... ok
test agent_scan::index::tests::cached_query_returns_rebuilt_records_without_revalidation ... ok
test bead::cli::tests::close_fast_path_accepts_note_and_updates_once ... ok
test bead::cli::tests::create_rejects_bare_task_constructor_without_size ... ok
test bead::cli::tests::create_plan_under_in_tree_plans_root_stores_canonical_reference ... ok
test bead::cli::tests::close_summary_preserves_requested_ids_and_real_prior_status ... ok
test bead::cli::tests::create_plan_path_is_relative_to_store_workspace_from_nested_cwd ... ok
test artifact_file::vcs::tests::tries_later_checkouts_when_the_first_lacks_the_object ... ok
test bead::cli::tests::design_plan_roots_resolves_the_beads_sidecar_to_its_plans_sibling ... ok
test bead::cli::tests::design_storage_root_resolves_the_beads_sidecar_to_the_workspace ... ok
test bead::cli::tests::parse_create_type_accepts_flag_form_and_rejects_arity ... ok
test bead::cli::tests::create_plan_under_sidecar_plans_root_stores_canonical_reference ... ok
test bead::cli::tests::list_compact_colors_shared_type_status_and_id_vocabulary ... ok
test bead::cli::tests::ready_empty_state_explains_epic_preassignment ... ok
test bead::cli::tests::list_compact_renders_aligned_glyph_only_type_column ... ok
test bead::cli::tests::create_and_remove_are_handled_with_mutation_summaries ... ok
test bead::cli::tests::create_round_trips_a_flag_bead ... ok
test bead::cli::tests::search_applies_filters_and_limit ... ok
test bead::cli::tests::search_compact_color_always_highlights_matches ... ok
test bead::cli::tests::ready_lists_only_unblocked_ready_tasks_with_ready_glyph ... ok
test bead::cli::tests::search_compact_orders_matches_newest_first ... ok
test bead::cli::tests::remove_missing_later_id_is_an_atomic_fast_path_error ... ok
test bead::cli::tests::search_compact_renders_aligned_glyph_only_type_column ... ok
test bead::cli::tests::search_compact_renders_name_and_description ... ok
test bead::cli::tests::search_no_match_is_successful ... ok
test bead::cli::tests::search_regex_flag_is_fast_path_only_as_bare_flag ... ok
test bead::cli::tests::search_json_renders_stable_uncolored_envelope ... ok
test bead::cli::tests::search_full_reuses_show_rendering_for_single_result ... ok
test bead::cli::tests::remove_handles_multiple_ids_with_unique_output_and_requested_summary ... ok
test bead::cli::tests::search_design_matches_canonical_plan_reference ... ok
test bead::cli::tests::search_regex_invalid_pattern_is_usage_error_across_formats ... ok
test bead::cli::tests::dependency_remove_is_handled_with_a_batch_mutation_summary ... ok
test bead::cli::tests::show_keeps_one_line_when_a_legacy_path_resolves_to_itself ... ok
test axe_chop::tests::clan_summary_validation_is_field_specific_and_text_block_safe ... ok
test bead::cli::tests::show_marks_a_reference_resolved_through_month_drift ... ok
test bead::cli::tests::create_show_and_ref_verbs_honor_the_reference_contract ... ok
test bead::cli::tests::search_regex_zero_width_only_pattern_matches_without_empty_highlights ... ok
test bead::cli::tests::search_whitespace_query_is_usage_error ... ok
test bead::cli::tests::show_renders_reference_above_its_resolved_path ... ok
test bead::cli::tests::show_reports_a_malformed_reference ... ok
test bead::cli::tests::update_fast_path_defers_size_flag_to_python ... ok
test bead::cli::tests::show_reports_an_ambiguous_reference_instead_of_guessing ... ok
test bead::cli::tests::show_resolves_a_legacy_path_against_the_working_directory ... ok
test bead::cli::tests::show_says_plainly_when_a_reference_resolves_nowhere ... ok
test bead::config::tests::load_current_shape ... ok
test bead::config::tests::missing_file_returns_supplied_default ... ok
test bead::cli::tests::stats_prints_ready_and_task_rows ... ok
test bead::config::tests::save_matches_python_pretty_json_shape ... ok
test bead::events::tests::issue_update_event_fields_resolution_round_trips_all_three_encodings ... ok
test bead::events::tests::concurrently_minted_bead_id_relocates_instead_of_wedging_the_store ... ok
test bead::events::tests::concurrently_minted_child_id_renumbers_to_a_free_sibling ... ok
test bead::events::tests::note_append_validation_and_rendering_are_owned_by_the_event ... ok
test bead::events::tests::merging_without_a_relocation_id_still_reports_the_duplicate ... ok
test bead::events::tests::reduction_collapses_duplicate_external_refs_regardless_of_stream_order ... ok
test bead::events::tests::reduction_collapse_prefers_earlier_created_at_over_id_order ... ok
test bead::events::tests::reduction_collapse_does_not_disturb_unrelated_issues ... ok
test bead::cli::tests::update_fast_path_reports_changed_and_unchanged_rows_in_one_commit ... ok
test bead::events::tests::reduction_keeps_flag_rows_out_of_external_ref_collapse ... ok
test bead::events::tests::redundant_close_is_an_exact_no_op ... ok
test bead::events::tests::issue_update_event_fields_round_trip_every_field ... ok
test bead::events::tests::three_way_merge_preserves_independent_plus_ones_and_deduplicates_reporter ... ok
test bead::events::tests::refs_import_as_individual_events_and_replay_idempotently ... ok
test bead::history::tests::lost_notes_are_stable_by_issue_id_and_support_one_issue ... ok
test bead::history::tests::lost_notes_ignores_append_only_revision_chains ... ok
test bead::events::tests::relocated_events_are_reminted_onto_their_new_stream ... ok
test bead::history::tests::external_ref_set_and_clear_are_recorded_in_history ... ok
test bead::events::tests::relocation_picks_the_same_loser_whichever_side_git_calls_ours ... ok
test bead::history::tests::lost_notes_reports_overwritten_nonempty_revisions ... ok
test bead::history::tests::close_reopen_close_status_timeline_is_complete ... ok
test bead::history::tests::merged_order_keeps_appended_predated_event_after_earlier_stream_event ... ok
test bead::history::tests::removal_ends_the_timeline ... ok
test bead::jsonl::tests::atomic_temp_paths_are_unique_per_process ... ok
test bead::history::tests::phase_history_is_read_from_parent_stream ... ok
test bead::history::tests::notes_history_preserves_each_revision_pair ... ok
test bead::history::tests::unknown_issue_is_an_error ... ok
test bead::jsonl::tests::atomic_if_changed_skips_identical_bytes ... ok
test bead::history::tests::single_update_and_noop_report_only_real_changes ... ok
test bead::jsonl::tests::corrupt_lines_are_skipped ... ok
test bead::jsonl::tests::import_defaults_missing_model_to_empty ... ok
test bead::jsonl::tests::import_defaults_missing_plan_tiers_from_phase_children ... ok
test bead::jsonl::tests::export_sorts_by_id_and_uses_compact_json ... ok
test bead::jsonl::tests::import_rejects_model_control_characters ... ok
test bead::jsonl::tests::refs_round_trip_and_empty_refs_do_not_change_jsonl_shape ... ok
test bead::jsonl::tests::import_rejects_duplicate_external_refs ... ok
test bead::cli::tests::search_regex_matches_patterns_and_highlights_ranges ... ok
test bead::cli::tests::search_regex_json_marks_regex_mode ... ok
test bead::jsonl::tests::import_preserves_model ... ok
test agent_scan::index::tests::query_self_heals_done_creation_before_completed_filter ... ok
test bead::jsonl::tests::unknown_event_operation_names_the_upgrade_remedy ... ok
test bead::jsonl::tests::write_event_store_changed_writes_selected_streams_and_reloads ... ok
test bead::mutation::tests::batch_close_preflights_every_request_before_writing ... ok
test bead::mutation::tests::absent_resolution_does_not_conflict_with_recorded_canceled_close ... ok
test bead::mutation::tests::agent_claim_mutations_reject_missing_and_blank_requests ... ok
test bead::mutation::tests::a_store_bricked_by_a_close_over_a_snooze_loads_again ... ok
test bead::mutation::tests::an_invalid_derived_state_leaves_the_event_streams_untouched ... ok
test bead::mutation::tests::append_issue_note_appends_attributed_entries_and_event ... ok
test agent_scan::index::tests::only_monitors_filters_to_monitor_family_role ... ok
test bead::mutation::tests::claim_for_agent_launch_rejects_missing_closed_and_blank_requests ... ok
test axe_chop::tests::clan_scoped_proposals_validate_member_and_directive_shapes ... ok
test bead::mutation::tests::a_pre_close_history_projection_recovers_its_reason_on_the_next_load ... ok
test bead::mutation::tests::append_issue_note_defaults_blank_author_to_store_owner ... ok
test bead::mutation::tests::cancel_task_snooze_returns_the_bead_to_ready ... ok
test bead::mutation::tests::append_issue_note_rejects_blank_entry_without_writing ... ok
test agent_scan::index::tests::cached_query_does_not_refresh_stale_marker_rows ... ok
test bead::mutation::tests::claim_for_agent_launch_claims_open_and_reassigns_in_progress_issue ... ok
test bead::mutation::tests::claim_for_agent_wait_claims_open_and_is_idempotent_for_same_agent ... ok
test bead::mutation::tests::close_with_note_rejects_blank_entry_without_writing ... ok
test bead::mutation::tests::close_skips_already_closed_issues_without_new_events ... ok
test bead::mutation::tests::close_records_explicit_resolution_and_reopen_update_clears_it ... ok
test bead::mutation::tests::closing_a_snoozed_task_drops_the_record_and_the_store_reloads ... ok
test bead::mutation::tests::create_rejects_model_control_characters ... ok
test bead::mutation::tests::conflicting_reason_aborts_before_writing ... ok
test bead::mutation::tests::close_with_note_appends_to_every_requested_issue_before_close ... ok
test bead::mutation::tests::create_requires_size_only_for_new_tasks ... ok
test bead::mutation::tests::closing_child_epic_closes_completed_parent_phase ... ok
test agent_scan::index::tests::terminal_workflow_state_rows_are_recent_completed_rows ... ok
test bead::mutation::tests::create_requires_task_type_only_for_new_tasks ... ok
test bead::mutation::tests::deferral_length_label_buckets_and_rounds_half_away_from_zero ... ok
test bead::mutation::tests::create_and_update_model ... ok
test bead::mutation::tests::conflicting_resolution_aborts_mixed_batch_before_writing ... ok
test bead::mutation::tests::claim_for_agent_wait_declines_other_claims_and_terminal_states_without_writes ... ok
test bead::mutation::tests::create_uses_explicit_creator_for_issue_and_reference_events ... ok
test bead::mutation::tests::create_top_level_uses_current_store_max_and_persists_counter ... ok
test agent_scan::index::tests::rebuild_indexes_scanner_equivalent_records ... ok
test bead::mutation::tests::create_rejects_duplicate_external_ref_without_writing ... ok
test bead::mutation::tests::create_add_and_remove_references_use_individual_events_and_noop_cleanly ... ok
test bead::mutation::tests::flag_create_rejects_the_four_new_validation_errors ... ok
test bead::mutation::tests::forced_close_requires_reason_and_non_done_resolution ... ok
test bead::mutation::tests::init_store_writes_a_root_level_store_for_a_dot_dirname ... ok
test bead::mutation::tests::explicitly_closing_parent_and_child_emits_one_explicit_parent_event ... ok
test agent_stats::run::tests::runner_fixed_and_all_time_empty_ranges_have_distinct_contracts ... ok
test bead::mutation::tests::forced_close_plan_sweeps_open_children_before_parent ... ok
test bead::mutation::tests::every_reopen_cause_archives_the_close_reason_it_used_to_destroy ... ok
test bead::mutation::tests::flag_external_ref_does_not_reserve_external_issue_identity ... ok
test bead::mutation::tests::concurrent_task_plus_ones_preserve_reporters_and_deduplicate_retries ... ok
test bead::mutation::tests::forced_close_plan_sweeps_through_nested_child_epics ... ok
test bead::mutation::tests::event_backed_child_id_reuse_after_remove_matches_jsonl_semantics ... ok
test bead::mutation::tests::mutable_appends_mint_stable_content_hashed_event_ids ... ok
test bead::mutation::tests::flag_bead_create_update_and_close_round_trip ... ok
test bead::mutation::tests::legacy_jsonl_migration_first_save_writes_every_imported_stream ... ok
test bead::mutation::tests::mark_ready_rejects_phase_and_idempotent_plan ... ok
test agent_scan::index::tests::query_self_heals_running_to_done_transition ... ok
test bead::mutation::tests::create_resolves_creator_from_phase_parent_then_store_owner ... ok
test bead::mutation::tests::phase_with_blank_parent_creator_falls_back_to_store_owner ... ok
test bead::mutation::tests::concurrent_launch_claims_preserve_sibling_events_and_projection ... ok
test bead::mutation::tests::mutations_create_canonical_events_and_regenerate_projection ... ok
test agent_stats::run::tests::committing_agents_counts_distinct_names_not_runs ... ok
test bead::mutation::tests::external_ref_create_update_clear_and_batch_conflicts_are_atomic ... ok
test bead::mutation::tests::open_sibling_delegated_work_keeps_parent_phase_open ... ok
test bead::mutation::tests::one_mutation_touches_only_the_mutated_stream_file ... ok
test bead::mutation::tests::phase_size_round_trips_through_create_update_events_and_projection ... ok
test bead::mutation::tests::nested_delegation_closes_only_phase_parents ... ok
test bead::mutation::tests::plus_one_below_the_target_leaves_a_snoozed_bead_snoozed ... ok
test bead::mutation::tests::reference_mutations_reject_malformed_entries_without_writing ... ok
test bead::mutation::tests::plus_one_at_the_target_wakes_a_snoozed_bead_with_a_preset_note ... ok
test bead::mutation::tests::open_issue_no_longer_leaves_stale_close_metadata_in_the_projection ... ok
test bead::mutation::tests::projection_writers_are_byte_stable_for_the_same_store_state ... ok
test bead::mutation::tests::preclaim_epic_work_plan_validation_is_all_or_nothing ... ok
test bead::mutation::tests::plus_one_never_wakes_a_snoozed_bead_that_set_no_target ... ok
test bead::mutation::tests::preclaim_epic_work_plan_updates_once_and_returns_rollback ... ok
test bead::mutation::tests::re_snoozing_replaces_the_record_and_appends_a_second_event ... ok
test bead::mutation::tests::re_snoozing_appends_a_second_note_naming_the_replaced_wake_time ... ok
test bead::mutation::tests::remove_issues_rejects_an_empty_request ... ok
test bead::mutation::tests::plus_one_close_record_joins_its_evidence_entry_exactly ... ok
test agent_scan::index::tests::query_self_heals_appended_feedback_submitted_at ... ok
test bead::mutation::tests::release_agent_claim_is_owner_guarded_and_round_trips_to_open ... ok
test bead::mutation::tests::remove_issues_deduplicates_duplicate_requests_and_events ... ok
test bead::mutation::tests::remove_dependencies_rejects_an_unknown_source_without_writing ... ok
test bead::mutation::tests::removing_child_epic_does_not_close_parent_phase ... ok
test bead::mutation::tests::release_agent_claim_declines_in_progress_and_closed_without_writes ... ok
test bead::mutation::tests::remove_dependencies_batches_and_deduplicates_targets ... ok
test bead::mutation::tests::remove_issues_missing_later_id_leaves_store_unchanged ... ok
test bead::mutation::tests::remove_dependencies_records_the_full_removed_edge ... ok
test bead::mutation::tests::remove_dependencies_validates_the_whole_batch_before_writing ... ok
test bead::mutation::tests::remove_issues_removes_independent_roots_in_argument_order ... ok
test agent_scan::index::tests::terminalize_stale_active_rows_skips_workspace_claim ... ok
test bead::mutation::tests::remove_issues_deduplicates_overlapping_roots_in_both_orders ... ok
test bead::mutation::tests::snooze_task_rejects_non_task_beads ... ok
test bead::mutation::tests::repeat_close_is_write_free_and_classified_as_already_closed ... ok
test bead::mutation::tests::reopening_grandchild_reopens_closed_ancestors_and_clears_resolution ... ok
test bead::mutation::tests::remove_plan_cascades_through_nested_child_epics ... ok
test bead::mutation::tests::task_type_create_rejects_cross_field_and_slug_errors ... ok
test bead::mutation::tests::snooze_task_with_no_reason_or_target_still_names_the_wake_conditions ... ok
test bead::mutation::tests::snooze_task_records_wake_conditions_and_replays_from_events ... ok
test bead::mutation::tests::repeat_close_with_note_writes_only_the_note ... ok
test bead::mutation::tests::task_plus_one_creator_and_repeat_are_byte_identical_noops ... ok
test bead::mutation::tests::snooze_task_rejects_bad_targets_times_and_statuses ... ok
test bead::mutation::tests::unforced_close_with_open_descendant_fails_without_writing ... ok
test bead::mutation::tests::mutation_and_reducer_agree_on_every_reopen_path ... ok
test bead::mutation::tests::sase_mk_blast_radius_regression_preserves_unrelated_stream_bytes ... ok
test bead::mutation::tests::task_plus_one_is_atomic_normalized_and_promotes_closed_task ... ok
test bead::mutation::tests::task_type_round_trips_through_create_events_and_projection ... ok
test bead::mutation::tests::task_plus_one_fresh_observation_window_reopens_closed_task_and_clears_assignee ... ok
test bead::mutation::tests::update_issues_invalid_field_value_leaves_every_target_unmodified ... ok
test bead::mutation::tests::reopening_a_bead_that_was_never_closed_archives_nothing ... ok
test agent_scan::index::tests::query_skips_rescan_when_signatures_match ... ok
test bead::mutation::tests::update_issues_collapses_duplicate_ids_to_one_update ... ok
test bead::mutation::tests::task_plus_one_stale_observation_window_records_without_reopening_closed_task ... ok
test bead::mutation::tests::task_create_and_ready_updates_round_trip_through_events ... ok
test bead::mutation::tests::update_issues_reopens_shared_ancestor_only_once ... ok
test agent_scan::index::tests::query_self_heals_waiting_deletion_to_running ... ok
test bead::mutation::tests::reopening_and_launch_claiming_a_snoozed_task_drop_the_record ... ok
test bead::mutation::tests::update_issues_applies_same_fields_to_every_target_in_one_pass ... ok
test bead::read::tests::claimed_dependency_is_an_active_blocker ... ok
test bead::read::tests::claimed_status_filter_is_parsed_and_counted ... ok
test bead::read::tests::ready_query_returns_only_unblocked_ready_tasks ... ok
test bead::read::tests::doctor_ignores_transient_mutation_holder_metadata ... ok
test bead::read::tests::resolve_issue_id_accepts_full_ids_and_unique_suffixes ... ok
test bead::read::tests::doctor_marks_unavailable_reference_context_as_skipped ... ok
test bead::read::tests::resolve_issue_id_reports_unknown_and_ambiguous_suffixes ... ok
test bead::mutation::tests::update_issues_unknown_id_leaves_store_untouched ... ok
test bead::read::tests::stats_derive_plus_one_total_from_structured_evidence ... ok
test bead::mutation::tests::update_issues_status_closed_rejects_out_of_batch_descendant ... ok
test bead::mutation::tests::update_status_closed_rejects_open_descendants ... ok
test bead::mutation::tests::update_issues_closes_parent_and_child_regardless_of_argument_order ... ok
test bead::read::tests::reference_diagnostics_groups_unknown_missing_and_ambiguous_entries ... ok
test bead::mutation::tests::update_issues_mixed_batch_reports_changed_and_unchanged ... ok
test bead::mutation::tests::update_refuses_the_snoozed_status_shortcut ... ok
test bead::mutation::tests::update_out_of_closed_reopens_closed_ancestor ... ok
test bead::mutation::tests::repeated_close_episodes_append_oldest_first_with_their_causes ... ok
test bead::schema::tests::metadata_migration_adds_only_missing_columns ... ok
test bead::mutation::tests::update_with_matching_fields_is_a_quiet_no_op ... ok
test bead::schema::tests::migration_detection_matches_python_helpers ... ok
test bead::search::tests::closed_issues_match_by_default ... ok
test bead::search::tests::field_names_constant_matches_all_collectable_fields ... ok
test bead::search::tests::filters_status_type_and_tier_together ... ok
test bead::search::tests::invalid_regex_is_a_validation_error ... ok
test bead::search::tests::issues_without_close_history_do_not_match_an_archived_reason ... ok
test bead::search::tests::literal_match_truth_uses_plain_case_folded_containment ... ok
test bead::schema::tests::schema_contains_current_constraints ... ok
test bead::search::tests::limit_keeps_newest_matches ... ok
test bead::search::tests::literal_search_treats_regex_metacharacters_literally ... ok
test bead::search::tests::matches_an_archived_close_reason ... ok
test bead::search::tests::matches_an_archived_resolution ... ok
test bead::search::tests::matches_case_insensitive_unicode_substrings ... ok
test bead::search::tests::no_match_returns_empty_results ... ok
test bead::search::tests::matches_every_searchable_field ... ok
test bead::mutation::tests::updating_a_snoozed_bead_off_snoozed_drops_the_record ... ok
test bead::search::tests::public_search_loads_store_and_returns_wire_matches ... ok
test agent_scan::index::tests::rebuild_replaces_corrupt_existing_index ... ok
test bead::search::tests::rejects_empty_or_whitespace_query ... ok
test bead::search::tests::regex_search_allows_inline_case_sensitivity ... ok
test bead::search::tests::zero_limit_is_unlimited ... ok
test bead::search::tests::returns_newest_matches_before_older_matches ... ok
test bead::wire::tests::bug_id_requires_changespec_name ... ok
test bead::wire::tests::claimed_status_round_trips_through_serde ... ok
test bead::wire::tests::close_history_omits_absent_reason_and_resolution ... ok
test bead::wire::tests::close_history_is_allowed_on_every_issue_type ... ok
test bead::wire::tests::close_history_validation_rejects_blank_fields ... ok
test bead::wire::tests::empty_optional_strings_normalize_to_none ... ok
test bead::wire::tests::close_history_round_trips_and_stays_absent_when_empty ... ok
test bead::mutation::tests::task_plus_one_open_and_active_statuses_preserve_existing_contract ... ok
test bead::search::tests::zero_width_regex_matches_fields ... ok
test bead::wire::tests::empty_phase_size_normalizes_to_none_and_invalid_values_fail ... ok
test bead::wire::tests::empty_task_type_normalizes_to_none ... ok
test bead::wire::tests::flag_issues_cannot_have_parent_or_tier ... ok
test bead::wire::tests::external_ref_round_trips_when_non_empty ... ok
test bead::wire::tests::flag_issues_must_carry_flag_metadata ... ok
test bead::wire::tests::flag_issues_still_cannot_be_ready_or_snoozed_or_carry_plus_ones ... ok
test bead::wire::tests::flag_key_is_absent_when_the_bead_is_not_a_flag ... ok
test bead::wire::tests::flag_metadata_requires_flag_type ... ok
test bead::wire::tests::model_rejects_control_characters ... ok
test bead::wire::tests::legacy_defaults_match_python_jsonl_loader ... ok
test bead::wire::tests::flag_type_round_trips_with_its_record ... ok
test bead::wire::tests::flag_record_validates_key_date_and_release ... ok
test bead::search::tests::regex_search_matches_patterns_case_insensitively_by_default ... ok
test bead::wire::tests::phase_size_round_trips_all_enum_values_and_rejects_plan_usage ... ok
test bead::search::tests::zero_width_regex_matches_truth_but_not_highlight_ranges ... ok
test bead::wire::tests::phase_rejects_plan_only_fields ... ok
test bead::wire::tests::phase_requires_parent ... ok
test bead::wire::tests::ready_status_requires_task_type ... ok
test agent_scan::index::tests::schema_v19_upgrade_refreshes_record_json_for_model_aliases ... ok
test bead::wire::tests::snooze_key_is_absent_when_the_bead_is_not_snoozed ... ok
test bead::wire::tests::snooze_metadata_requires_snoozed_status ... ok
test bead::wire::tests::snooze_record_validates_its_own_fields ... ok
test bead::wire::tests::resolution_round_trips_and_requires_closed_status ... ok
test bead::wire::tests::snoozed_status_round_trips_with_its_record ... ok
test bead::wire::tests::snoozed_status_requires_a_task_and_a_record ... ok
test bead::wire::tests::task_plus_one_evidence_validates_structure_and_reporter_uniqueness ... ok
test bead::wire::tests::task_type_and_field_keys_must_be_bounded_snake_case ... ok
test bead::wire::tests::task_type_fields_require_task_type ... ok
test bead::wire::tests::task_type_is_rejected_on_non_task_issues ... ok
test bead::wire::tests::task_validation_allows_size_and_ready_but_rejects_plan_fields ... ok
test bead::wire::tests::task_type_round_trips_and_stays_absent_when_empty ... ok
test bead::work::tests::child_epics_are_excluded_from_parent_waves ... ok
test bead::work::tests::claimed_phase_is_still_scheduled ... ok
test bead::work::tests::delegated_only_plan_has_no_waves ... ok
test bead::work::tests::closed_in_epic_blocker_is_only_a_bead_wait ... ok
test bead::work::tests::closed_or_removed_child_plan_does_not_exclude_phase ... ok
test bead::work::tests::detects_cycles ... ok
test bead::work::tests::delegated_phase_is_excluded_but_remains_a_bead_blocker ... ok
test bead::work::tests::missing_out_of_epic_blocker_is_satisfied_with_warning ... ok
test bead::work::tests::parent_does_not_change_epic_launch_tag ... ok
test agent_scan::index::tests::terminalize_stale_active_rows_skips_fresh_missing_marker_race ... ok
test bead::work::tests::land_waits_on_every_launched_phase_in_wave_order ... ok
test bead::work::tests::epic_work_plan_copies_phase_and_land_models ... ok
test bead::work::tests::plans_diamond_dag_in_waves ... ok
test bead::work::tests::rejects_open_out_of_epic_blocker ... ok
test bead::work::tests::standalone_epic_uses_epic_launch_tag ... ok
test bead::work::tests::total_phase_count_includes_closed_phases ... ok
test commit_footer::tests::new_links_allocate_numeric_ids_without_body_or_footer_collisions ... ok
test commit_footer::tests::adding_tags_preserves_link_and_definition_below_complete_tag_block ... ok
test commit_footer::tests::parses_linked_values_and_reference_destinations ... ok
test commit_footer::tests::parses_plain_prefixed_and_legacy_tags_with_later_duplicates ... ok
test commit_footer::tests::repeated_updates_are_idempotent_and_preserve_trailing_shape ... ok
test commit_sha::tests::equivalent_sha_matrix ... ok
test commit_footer::tests::shared_targets_reuse_one_definition_deterministically ... ok
test commit_sha::tests::rejects_ambiguous_or_invalid_shas ... ok
test commit_footer::tests::replacing_or_removing_linked_tags_cleans_only_owned_definitions ... ok
test commit_subject::tests::exempts_git_generated_and_rebase_subjects ... ok
test commit_footer::tests::ordinary_reference_definitions_and_mid_message_tags_remain_body ... ok
test commit_subject::tests::exposes_stable_ordered_defaults ... ok
test commit_subject::tests::honors_custom_allowed_types ... ok
test commit_subject::tests::parses_plain_scoped_breaking_and_spaced_subjects ... ok
test commit_subject::tests::reads_only_the_trimmed_first_line ... ok
test commit_subject::tests::rejects_empty_descriptions_and_subjects ... ok
test commit_subject::tests::rejects_missing_or_malformed_type_separator ... ok
test commit_subject::tests::reports_uppercase_before_unknown_type ... ok
test content_layout::tests::collision_policy_is_exclusive_for_config_and_first_wins_for_xprompts ... ok
test content_layout::tests::memory_references_are_always_the_flat_namespaced_filename ... ok
test content_layout::tests::memory_rules_reject_reserved_names_bad_stems_and_bad_tiers ... ok
test content_layout::tests::memory_sources_are_project_before_home_with_exclusive_read_policy ... ok
test content_layout::tests::memory_tier_parses_only_the_two_supported_note_types ... ok
test content_layout::tests::missing_project_root_still_returns_complete_home_contract ... ok
test content_layout::tests::project_and_home_paths_keep_runtime_and_generated_content_separate ... ok
test content_layout::tests::ref_directories_are_canonical ... ok
test content_layout::tests::skill_placement_issues_name_the_move_in_both_directions ... ok
test content_layout::tests::skill_directories_are_canonical_in_every_scope ... ok
test content_layout::tests::skill_reference_names_split_provider_name_from_xprompt_reference ... ok
test content_layout::tests::skill_sources_are_ordered_first_wins_with_no_legacy_paths ... ok
test content_layout::tests::xprompt_priority_covers_canonical_legacy_config_plugin_and_package ... ok
test editor::at_reference::tests::bare_menu_groups_builtins_then_sorted_kinds_and_visible_paths ... ok
test editor::at_reference::tests::detects_path_shaped_kind_queries ... ok
test editor::at_reference::tests::dotfile_visibility_tracks_the_trailing_partial ... ok
test editor::at_reference::tests::fuzzy_kind_matches_do_not_gate_file_rows ... ok
test editor::at_reference::tests::detects_kind_and_payload_at_every_cursor_position ... ok
test editor::at_reference::tests::gated_menu_without_matching_paths_does_not_offer_an_empty_reveal ... ok
test editor::at_reference::tests::fuzzy_kind_menu_keeps_builtin_ties_and_reports_runs ... ok
test editor::at_reference::tests::kind_and_file_groups_filter_independently ... ok
test editor::at_reference::tests::malformed_scope_degrades_to_an_unscoped_row ... ok
test editor::at_reference::tests::path_menu_fuzzy_matches_only_the_trailing_partial ... ok
test editor::at_reference::tests::indexed_payload_menu_matches_the_wire_inventory_path ... ok
test editor::at_reference::tests::payload_menu_includes_title_only_matches ... ok
test editor::at_reference::tests::payload_menu_preserves_empty_query_provider_order ... ok
test editor::at_reference::tests::payload_wire_defaults_new_metadata_when_deserializing_old_rows ... ok
test editor::at_reference::tests::payload_menu_is_path_first_and_ranks_both_match_fields ... ok
test editor::at_reference::tests::payload_rank_breaks_quality_ties_but_unranked_rows_keep_text_order ... ok
test editor::at_reference::tests::rejects_prose_invalid_characters_and_literal_zones ... ok
test editor::at_reference::tests::qualified_match_highlights_each_field_and_drops_straddling_runs ... ok
test editor::at_reference::tests::scoped_payload_matches_repo_and_title_as_one_qualified_target ... ok
test editor::at_reference::tests::shared_extension_requires_an_all_prefix_leading_group ... ok
test editor::at_reference::tests::shared_extension_uses_only_the_leading_non_empty_group ... ok
test editor::at_reference::tests::payload_caps_report_matches_and_caller_truncation ... ok
test editor::at_reference::tests::caps_each_group_but_records_pre_cap_counts ... ok
test editor::completion::tests::agent_candidates_are_kind_aware_ordered_and_compatible ... ok
test editor::completion::tests::agent_candidates_carry_documentation_only_when_present ... ok
test editor::completion::tests::agent_and_indexed_file_payloads_match_mid_name_fragments ... ok
test editor::completion::tests::artifact_kind_candidates_list_builtins_in_documented_order ... ok
test editor::completion::tests::artifact_replacement_ranges_are_utf16_safe_and_at_paths_stay_references ... ok
test editor::completion::tests::builds_argument_name_completions ... ok
test editor::completion::tests::builds_catalog_completions_with_marker_filters ... ok
test editor::completion::tests::builds_snippet_completions_by_case_insensitive_prefix ... ok
test editor::completion::tests::builds_bead_payload_candidates_from_published_pages ... ok
test editor::completion::tests::builds_agent_payload_candidates_from_published_pages ... ok
test editor::completion::tests::builds_chat_and_indexed_file_payloads_but_not_remote_kinds ... ok
test editor::completion::tests::builds_dynamic_kind_and_payload_candidates ... ok
test editor::completion::tests::commit_age_labels_match_prompt_bar_thresholds ... ok
test editor::completion::tests::classifies_artifact_kind_and_payload_at_every_cursor_position ... ok
test agent_scan::index::tests::query_self_heals_hidden_to_visible_before_visible_filter ... ok
test editor::completion::tests::closed_placeholder_does_not_steal_following_context ... ok
test editor::completion::tests::classifies_vcs_project_trigger ... ok
test editor::completion::tests::classifies_primary_completion_modes ... ok
test editor::completion::tests::classifies_vcs_repo_then_vcs_ref_before_xprompt_argument_hints ... ok
test editor::completion::tests::classifies_vcs_repo_then_vcs_ref_then_xprompt_args ... ok
test bead::mutation::tests::bead_mutation_lock_contention_times_out ... ok
test editor::completion::tests::bof_trigger_merges_into_single_primary_edit ... ok
test editor::completion::tests::commit_log_failures_report_the_underlying_os_error ... ok
test editor::completion::tests::commit_inventory_reports_the_merged_row_cap ... ok
test editor::completion::tests::commit_merge_ties_break_by_repository_then_sha ... ok
test editor::completion::tests::commit_timeout_override_accepts_only_positive_finite_seconds ... ok
test editor::completion::tests::agent_prefix_query_survives_a_corpus_of_fuzzy_matches ... ok
test editor::completion::tests::commit_timeout_reads_the_documented_environment_override ... ok
test editor::completion::tests::detects_vcs_ref_colon_spans ... ok
test editor::completion::tests::detects_narrow_argument_contexts ... ok
test editor::completion::tests::detects_vcs_ref_paren_hitl ... ok
test agent_scan::index::tests::terminalize_stale_active_rows_revalidates_new_running_marker ... ok
test editor::completion::tests::detects_vcs_repo_colon_spans ... ok
test editor::completion::tests::detects_vcs_repo_paren_hitl_and_nested_namespaces ... ok
test bead::schema::tests::plus_one_evidence_migration_defaults_legacy_rows_to_empty_json ... ok
test editor::completion::tests::effort_and_auto_directive_arguments_classify_with_candidates ... ok
test editor::completion::tests::directive_keyword_completion_targets_only_the_post_comma_fragment ... ok
test editor::completion::tests::memory_completes_only_through_the_memory_namespace ... ok
test editor::completion::tests::model_at_suffix_completes_effort_vocabulary ... ok
test editor::completion::tests::directive_keyword_completion_stays_out_of_positional_and_value_positions ... ok
test editor::completion::tests::payload_inventory_applies_document_root_path_globs ... ok
test editor::completion::tests::placeholder_context_precedes_other_explicit_completion_modes ... ok
test editor::completion::tests::repeatable_agent_context_replaces_earlier_element_and_filters_selected ... ok
test editor::completion::tests::repeatable_positionals_keep_the_tail_input_and_active_element_range ... ok
test editor::completion::tests::snippet_context_does_not_steal_higher_priority_tokens ... ok
test editor::completion::tests::commit_log_distinguishes_every_unusable_repository_outcome ... ok
test editor::completion::tests::vcs_prepend_offset_skips_horizontal_whitespace_only ... ok
test agent_scan::index::tests::recent_completed_limit_does_not_bound_active_rows ... ok
test editor::completion::tests::trailing_trigger_emits_primary_plus_additional_edit ... ok
test editor::completion::tests::vcs_project_candidates_accept_legacy_changespec_kind ... ok
test editor::completion::tests::commit_inventory_is_empty_for_sidecar_only_context ... ok
test bead::schema::tests::external_ref_migration_adds_nullable_partial_unique_index ... ok
test agent_stats::run::tests::runner_eligibility_honors_family_workflow_visibility_and_project ... ok
test editor::completion::tests::vcs_project_candidates_filter_preserves_catalog_order ... ok
test editor::completion::tests::vcs_ref_accept_preserves_visible_space_before_document_final_newline ... ok
test editor::completion::tests::vcs_ref_builder_filters_by_query_and_alias ... ok
test editor::completion::tests::payload_enumeration_is_bounded_and_deduplicated ... ok
test editor::completion::tests::vcs_ref_builder_groups_rows_and_replaces_root_ref ... ok
test editor::completion::tests::vcs_ref_trigger_negatives ... ok
test editor::completion::tests::vcs_ref_golden_vectors ... ok
test editor::completion::tests::vcs_repo_builder_replaces_only_the_ref_value ... ok
test editor::completion::tests::vcs_repo_golden_vectors ... ok
test editor::completion::tests::vcs_project_candidates_filter_for_bare_plus_query ... ok
test editor::completion::tests::vcs_repo_trigger_negatives ... ok
test editor::completion::tests::wait_candidates_merge_keywords_and_exclude_selected_values ... ok
test editor::definition::tests::navigates_from_a_memory_reference_to_the_memory_note ... ok
test editor::completion::tests::wait_context_narrows_to_active_clause_and_tracks_selected_values ... ok
test editor::completion::tests::vcs_project_candidates_include_patch_context ... ok
test editor::definition::tests::resolves_inline_and_standalone_xprompt_definitions ... ok
test editor::definition::tests::resolves_namespaced_shorthand_and_slash_skill_definitions ... ok
test editor::definition::tests::returns_none_for_missing_entries_or_source_targets ... ok
test editor::definition::tests::validates_local_file_definition_paths_conservatively ... ok
test editor::completion::tests::vcs_project_candidates_match_aliases ... ok
test editor::definition::tests::preserves_catalog_definition_range ... ok
test agent_scan::index::tests::tier1_active_query_is_bounded_to_newest_incomplete_rows ... ok
test editor::completion::tests::payload_inventory_reaches_past_the_editor_display_cap ... ok
test editor::diagnostics::tests::artifact_diagnostics_report_malformed_and_unresolved_known_kinds ... ok
test agent_scan::index::tests::migration_recomputes_hidden_for_v1_indexes ... ok
test editor::diagnostics::tests::artifact_diagnostics_report_unresolved_bead_pages ... ok
test editor::diagnostics::tests::artifact_diagnostics_shape_check_commit_and_bug_without_resolution ... ok
test editor::diagnostics::tests::artifact_diagnostics_resolve_document_chat_and_file_locally ... ok
test editor::diagnostics::tests::artifact_diagnostics_skip_literal_ranges_and_unknown_kinds ... ok
test bead::schema::tests::resolution_migration_preserves_legacy_rows_without_backfill ... ok
test editor::completion::tests::commit_inventory_preserves_subject_and_multiline_body ... ok
test bead::schema::tests::task_type_migration_adds_columns_index_and_check ... ok
test editor::completion::tests::vcs_project_edits_never_overlap ... ok
test agent_scan::index::tests::hidden_inclusive_full_history_can_inspect_dismissed_rows ... ok
test editor::diagnostics::tests::accepts_valid_input_aliases_and_defaults ... ok
test editor::diagnostics::tests::recognizes_current_directives_but_rejects_removed_spellings ... ok
test editor::diagnostics::tests::reports_flow_style_input_default_on_offending_scalar ... ok
test editor::diagnostics::tests::accepts_known_frontmatter_input_type_aliases ... ok
test editor::diagnostics::tests::incomplete_forms_do_not_emit_required_arg_noise ... ok
test editor::diagnostics::tests::reports_flow_style_frontmatter_input_type_diagnostic ... ok
test editor::diagnostics::tests::keywords_do_not_restore_dynamic_memory_matching ... ok
test editor::diagnostics::tests::reports_frontmatter_yaml_and_shape_diagnostics ... ok
test editor::diagnostics::tests::accepts_current_document_local_xprompts_and_validates_args ... ok
test editor::diagnostics::tests::reports_initial_diagnostics ... ok
test editor::diagnostics::tests::repeatable_tail_accepts_and_validates_every_element ... ok
test editor::diagnostics::tests::accepts_valid_argument_forms_and_bool_spellings ... ok
test editor::diagnostics::tests::accepts_frontmatter_local_xprompts ... ok
test editor::diagnostics::tests::accepts_input_descriptions_and_reports_invalid_shapes ... ok
test editor::diagnostics::tests::reports_invalid_input_defaults ... ok
test editor::directive::tests::alt_metadata_advertises_brace_shorthand ... ok
test editor::diagnostics::tests::reports_input_shape_name_duplicate_identifier_and_unknown_fields ... ok
test editor::directive::tests::auto_metadata_describes_gate_owned_resolution_and_offers_compatibility_suggestions ... ok
test editor::directive::tests::directive_completion_t_prefix_is_empty ... ok
test editor::diagnostics::tests::reports_unknown_top_level_and_invalid_name ... ok
test editor::diagnostics::tests::reports_invalid_snippet_tags_keywords_and_skill_metadata ... ok
test editor::directive::tests::effort_argument_candidates_are_the_canonical_vocabulary ... ok
test editor::diagnostics::tests::reports_longform_frontmatter_input_type_diagnostic ... ok
test editor::diagnostics::tests::reports_shortform_frontmatter_input_type_diagnostic ... ok
test editor::diagnostics::tests::reports_xprompt_argument_contract_diagnostics ... ok
test editor::diagnostics::tests::slash_skills_resolve_by_provider_name_not_xprompt_reference ... ok
test editor::directive::tests::clan_metadata_matches_the_editor_contract ... ok
test editor::directive::tests::removed_auto_approve_aliases_do_not_resolve_or_complete ... ok
test editor::directive::tests::id_metadata_and_completion_match_the_editor_contract ... ok
test editor::directive::tests::effort_is_a_recognized_directive_with_e_alias ... ok
test editor::directive::tests::removed_identity_directives_do_not_resolve_or_complete ... ok
test editor::directive::tests::resolves_documented_aliases ... ok
test editor::directive::tests::wait_argument_candidates_use_runtime_keywords ... ok
test editor::frontmatter::tests::field_schema_is_ordered_documented_and_parity_scoped ... ok
test editor::frontmatter::tests::hover_documents_log_skill_use_field ... ok
test editor::file::tests::preserves_at_prefix_and_marks_symlinked_directories ... ok
test editor::frontmatter::tests::input_type_schema_matches_parser_spellings ... ok
test editor::file::tests::orders_directories_first_and_filters_dotfiles ... ok
test editor::frontmatter::tests::validate_accepts_bare_body_without_delimiters ... ok
test editor::frontmatter::tests::validate_accepts_known_good_block ... ok
test editor::frontmatter::tests::validate_accepts_log_skill_use_boolean ... ok
test editor::frontmatter::tests::validate_accepts_enum_choices_shortform_and_longform ... ok
test editor::frontmatter::tests::validate_field_handles_block_values ... ok
test editor::frontmatter::tests::validate_checks_enum_default_membership ... ok
test editor::frontmatter::tests::validate_flags_choices_on_non_enum_type ... ok
test editor::frontmatter::tests::validate_flags_duplicate_choice_values ... ok
test editor::frontmatter::tests::validate_flags_enum_without_choices ... ok
test editor::frontmatter::tests::validate_field_isolates_a_single_property ... ok
test editor::frontmatter::tests::validate_flags_known_bad_input_type ... ok
test editor::frontmatter::tests::validate_flags_non_boolean_log_skill_use ... ok
test editor::fuzzy::tests::classifies_all_match_tiers ... ok
test editor::fuzzy::tests::reports_character_ranges_for_non_ascii_text ... ok
test editor::fuzzy::tests::basename_retry_beats_a_cross_directory_alignment ... ok
test editor::frontmatter::tests::validates_repeatable_input_metadata_and_final_position ... ok
test editor::fuzzy::tests::comparator_is_deterministic_under_shuffled_input ... ok
test editor::fuzzy::tests::empty_query_matches_and_missing_subsequence_does_not ... ok
test editor::fuzzy::tests::tightens_site_to_the_contiguous_segment ... ok
test editor::hover::tests::builds_frontmatter_field_hover ... ok
test editor::hover::tests::builds_xprompt_and_argument_hover ... ok
test editor::hover::tests::directive_argument_hover_uses_current_identity_and_clan_metadata ... ok
test editor::hover::tests::frontmatter_hover_ignores_body_and_non_field_positions ... ok
test editor::fuzzy::tests::rewards_separator_and_camel_case_boundaries ... ok
test editor::hover::tests::hovers_a_skill_through_both_of_its_names ... ok
test editor::hover::tests::hovers_an_xprompt_memory_with_its_kind_and_tier ... ok
test editor::placeholder::tests::an_empty_common_slice_leaves_document_only_output_unchanged ... ok
test editor::placeholder::tests::appends_common_candidates_after_prompt_candidates_in_caller_order ... ok
test editor::placeholder::tests::builds_deduplicated_document_order_candidates ... ok
test editor::placeholder::tests::candidates_serialize_with_a_lowercase_source_tag ... ok
test editor::placeholder::tests::completion_edits_leave_the_cursor_after_a_closing_bracket ... ok
test editor::placeholder::tests::completion_list_details_reflect_the_candidate_source ... ok
test editor::placeholder::tests::dedups_common_candidates_against_the_prompt_and_each_other ... ok
test editor::placeholder::tests::detects_context_with_and_without_a_closing_bracket ... ok
test agent_stats::run::tests::runner_occupancy_handles_overlap_carry_in_waits_and_boundaries ... ok
test editor::placeholder::tests::completion_candidates_rank_literal_spans_after_live_spans ... ok
test editor::placeholder::tests::excludes_the_span_under_the_cursor ... ok
test agent_scan::index::tests::query_self_heals_newly_added_run_started_at ... ok
test editor::placeholder::tests::rejects_context_after_an_intervening_closing_bracket ... ok
test editor::placeholder::tests::filters_prefix_case_insensitively_and_handles_utf16_ranges ... ok
test editor::placeholder::tests::extracts_strict_single_line_spans_including_code ... ok
test editor::placeholder::tests::live_candidate_dedups_literal_and_common_occurrences_at_live_position ... ok
test editor::placeholder::tests::filters_common_candidates_with_the_same_prefix_rule ... ok
test editor::token::tests::extracts_mid_token_ranges ... ok
test agent_scan::index::tests::schema_v21_upgrade_backfills_model_alias_projection ... ok
test editor::placeholder::tests::summarizes_exact_raw_fields_with_bounded_context ... ok
test editor::completion::tests::commit_inventory_enforces_the_per_repository_scan_limit ... ok
test editor::placeholder::tests::substitutes_only_mapped_raw_spans_without_rescanning_values ... ok
test editor::token::tests::detects_vcs_project_trigger_tokens ... ok
test editor::token::tests::maps_lsp_utf16_positions_defensively ... ok
test editor::token::tests::extracts_expected_tokens ... ok
test editor::token::tests::recognizes_canonical_and_legacy_memory_markdown_source_paths ... ok
test editor::placeholder::tests::slugs_unicode_names_and_resolves_collisions_in_input_order ... ok
test editor::xprompt_args::tests::preserves_commas_and_equals_inside_quotes_and_text_blocks ... ok
test editor::xprompt_args::tests::parses_parenthesized_named_and_positional_args ... ok
test editor::token::tests::vcs_project_trigger_requires_bof_or_literal_space ... ok
test effort::tests::leaves_unknown_or_internal_at_intact ... ok
test effort::tests::resolves_effective_effort_precedence_and_source ... ok
test effort::tests::splits_trailing_known_effort ... ok
test effort::tests::validates_canonical_vocabulary ... ok
test editor::xprompt_args::tests::marks_open_forms_without_parsing_required_args ... ok
test editor::xprompt_args::tests::parses_colon_plus_hitl_and_namespaced_forms ... ok
test editor::token::tests::recognizes_prompt_widget_snippet_trigger_tokens ... ok
test editor::xprompt_args::tests::preserves_empty_elements_for_contract_validation ... ok
test effort_override::tests::clear_is_idempotent ... ok
test effort::tests::invalid_candidates_are_skipped ... ok
test effort_override::tests::invalid_inputs_are_rejected ... ok
test external_pr::classify::tests::blank_marker_is_ambiguous ... ok
test external_pr::classify::tests::maps_statuses_and_archive_destination ... ok
test external_pr::classify::tests::owned_url_skips_and_preserves_origin ... ok
test external_pr::classify::tests::refresh_fires_for_closed_unmerged_pr ... ok
test effort_override::tests::exact_and_no_expiry_records_obey_boundary_expiry ... ok
test effort_override::tests::malformed_stale_and_missing_field_state_self_cleans ... ok
test external_pr::classify::tests::sase_owned_patch_never_refreshes_despite_status_drift ... ok
test external_pr::classify::tests::refresh_fires_when_open_external_patch_status_drifts ... ok
test external_pr::classify::tests::unchanged_external_patch_skips ... ok
test external_pr::classify::tests::refresh_fires_for_merged_pr_and_moves_to_archive ... ok
test external_pr::url::tests::canonicalizes_github_url_variants ... ok
test external_pr::classify::tests::unknown_origin_patch_never_refreshes_despite_status_drift ... ok
test external_pr::url::tests::canonicalizes_gitlab_merge_request_urls ... ok
test external_pr::url::tests::rejects_unparseable_urls ... ok
test git_query::parsers::tests::branch_name_empty_stdout_returns_none ... ok
test effort_override::tests::every_canonical_level_round_trips_and_replaces ... ok
test git_query::parsers::tests::branch_name_whitespace_only_returns_none ... ok
test git_query::parsers::tests::branch_name_simple_value ... ok
test external_pr::classify::tests::unmarked_pr_adopts_external_with_slug ... ok
test external_pr::classify::tests::marker_orphan_adopts_marker_name ... ok
test git_query::parsers::tests::conflicted_files_empty_stdout_returns_empty ... ok
test external_pr::classify::tests::marker_repairs_reserved_stub ... ok
test git_query::parsers::tests::conflicted_files_only_blank_lines_returns_empty ... ok
test git_query::parsers::tests::branch_name_detached_head_returns_none ... ok
test git_query::parsers::tests::branch_name_strips_surrounding_whitespace ... ok
test git_query::parsers::tests::local_changes_whitespace_only_returns_none ... ok
test git_query::parsers::tests::conflicted_files_preserves_path_order ... ok
test git_query::parsers::tests::name_status_empty_stream_returns_empty ... ok
test git_query::parsers::tests::name_status_mixed_simple_and_rename_in_one_stream ... ok
test git_query::parsers::tests::local_changes_clean_tree_returns_none ... ok
test git_query::parsers::tests::name_status_rename_with_score_carries_paired_paths ... ok
test git_query::parsers::tests::local_changes_dirty_tree_returns_stripped_text ... ok
test git_query::parsers::tests::name_status_simple_status_letters ... ok
test git_query::parsers::tests::name_status_skips_empty_status_tokens ... ok
test git_query::parsers::tests::name_status_trailing_nul_is_ignored ... ok
test git_query::parsers::tests::name_status_copy_with_score_carries_paired_paths ... ok
test git_query::parsers::tests::name_status_truncated_rename_falls_back_to_single_path ... ok
test git_query::parsers::tests::name_status_truncated_status_only_drops_entry ... ok
test git_query::parsers::tests::conflicted_files_strips_blank_lines ... ok
test git_query::parsers::tests::workspace_name_https_remote_with_dot_git ... ok
test git_query::parsers::tests::workspace_name_https_remote_without_dot_git ... ok
test git_query::parsers::tests::workspace_name_falls_back_to_root_when_remote_blank ... ok
test git_query::parsers::tests::workspace_name_path_like_remote ... ok
test git_query::parsers::tests::workspace_name_remote_dot_git_only_returns_none ... ok
test git_query::parsers::tests::workspace_name_remote_takes_priority_over_root ... ok
test git_query::parsers::tests::workspace_name_returns_none_when_both_inputs_empty ... ok
test git_query::parsers::tests::workspace_name_falls_back_to_root_when_remote_none ... ok
test git_query::parsers::tests::workspace_name_ssh_remote_with_dot_git ... ok
test glossary::tests::builds_effective_aliases_with_derived_plurals ... ok
test glossary::tests::builds_effective_aliases_with_term_first ... ok
test glossary::tests::filters_display_aliases_to_non_derivable_configured_aliases ... ok
test glossary::tests::skips_derived_plural_claimed_by_authored_alias_without_diagnostic ... ok
test glossary::tests::pluralizes_phrases_with_conservative_ascii_rules ... ok
test glossary::tests::validation_diagnostics_stay_authored_for_alias_edge_cases ... ok
test host_bridge::tests::static_helper_bridge_returns_snippet_catalog_response ... ok
test host_bridge::tests::snippet_catalog_wire_accepts_minimal_entry_json ... ok
test agent_stats::run::tests::runner_question_wait_uses_matching_gate_response_time ... ok
test agent_scan::index::tests::bounded_query_retains_dismissed_clan_declaration_as_context ... ok
test glossary::tests::literal_zone_filter_skips_candidates_but_keeps_prose_match ... ok
test host_bridge::tests::static_helper_bridge_returns_vcs_repo_catalog_response ... ok
test agent_stats::run::tests::aggregates_window_outcomes_metadata_and_runtime ... ok
test host_bridge::tests::static_helper_bridge_returns_structured_catalog_response ... ok
test glossary::tests::scans_wrapped_phrase_with_trimmed_segments ... ok
test agent_scan::index::tests::query_self_heals_pending_question_creation_and_deletion ... ok
test machine_hood::tests::machine_hood_of_classifies_known_machines ... ok
test host_bridge::tests::xprompt_catalog_entry_wire_accepts_old_and_new_definition_path_json ... ok
test machine_hood::tests::machine_hood_of_returns_none_for_unknown_or_partial ... ok
test machine_hood::tests::qualify_and_strip_round_trip ... ok
test machine_hood::tests::qualify_does_not_confuse_prefix_of_another_machine ... ok
test machine_hood::tests::qualify_is_idempotent ... ok
test machine_hood::tests::qualify_prepends_when_missing ... ok
test glossary::tests::lookup_on_continuation_word_returns_wrapped_span ... ok
test machine_hood::tests::qualify_preserves_family_names ... ok
test agent_scan::index::tests::indexed_clan_context_honors_latest_declarations_and_generations ... ok
test machine_hood::tests::strip_never_produces_empty_remainder ... ok
test machine_hood::tests::strip_is_idempotent ... ok
test machine_hood::tests::validate_rejects_empty_uppercase_digits_and_dots ... ok
test machine_hood::tests::strip_removes_leading_hood ... ok
test machine_hood::tests::strip_leaves_unqualified_and_foreign_names ... ok
test machine_hood::tests::validate_accepts_lowercase_and_underscores ... ok
test markdown_link_refs::tests::allocate_reserves_a_dangling_numeric_use_with_no_definition ... ok
test markdown_link_refs::tests::append_definitions_in_numeric_order_and_skips_matching_ones ... ok
test markdown_link_refs::tests::scan_collects_definitions_first_wins_and_uses_all_three_forms ... ok
test markdown_link_refs::tests::scan_ignores_footnotes_inline_links_definitions_and_literal_zones ... ok
test markdown_link_refs::tests::allocate_reuses_matching_destination_before_picking_a_new_number ... ok
test markdown_link_refs::tests::allocate_fills_gaps_between_existing_definitions ... ok
test host_bridge::tests::command_helper_bridge_invokes_editor_snippet_catalog ... ok
test editor::completion::tests::vcs_project_golden_vectors ... ok
test markdown_link_refs::tests::scan_skips_duplicate_bracket_pairs_used_as_link_text ... ok
test markdown_link_refs::tests::append_is_idempotent_and_preserves_trailing_newline_shape ... ok
test model_route::tests::empty_or_blank_explicit_model_falls_through_to_config ... ok
test model_route::tests::maps_every_phase_size_to_the_public_alias ... ok
test model_route::tests::selects_explicit_epic_land_model_over_threshold ... ok
test model_route::tests::rejects_invalid_and_retired_size_names ... ok
test model_route::tests::rejects_invalid_counts_thresholds_and_targets ... ok
test model_route::tests::uses_big_target_at_and_above_threshold ... ok
test model_route::tests::zero_phase_count_is_valid_and_selects_the_normal_target ... ok
test model_route::tests::wire_json_uses_config_field_source_names ... ok
test notifications::mobile::tests::gate_action_string_mapping_is_complete ... ok
test notifications::mobile::tests::action_result_contract_snapshot_is_stable ... ok
test notifications::mobile::tests::gate_action_request_option_inputs_round_trips ... ok
test glossary::tests::wrapped_phrase_accepts_crlf_without_segment_carriage_returns ... ok
test host_bridge::tests::command_helper_bridge_invokes_editor_vcs_repo_catalog ... ok
test notifications::mobile::tests::priority_and_error_classifiers_are_disjoint ... ok
test notifications::mobile::tests::planner_errors_are_deterministic ... ok
test notifications::mobile::tests::prefix_resolution_makes_collisions_explicit ... ok
test notifications::mobile::tests::gate_envelope_version_acceptance_is_bounded ... ok
test notifications::mobile::tests::question_planner_supports_index_label_id_and_custom_answers ... ok
test notifications::mobile::tests::custom_gate_notification_contract_snapshot_is_stable ... ok
test notifications::mobile::tests::epic_notification_contract_snapshot_is_stable ... ok
test glossary::tests::three_word_term_wraps_across_three_lines ... ok
test notifications::mobile::tests::launch_approval_detail_exposes_preview_identity ... ok
test notifications::pending_actions::tests::custom_gate_without_bundle_path_has_missing_target_state ... ok
test notifications::mobile::tests::every_non_question_gate_projects_the_same_branch_wire ... ok
test notifications::mobile::tests::mobile_notification_contract_snapshot_is_stable ... ok
test notifications::mobile::tests::schema_version_3_envelope_with_declared_inputs_yields_branches ... ok
test notifications::pending_actions::tests::pending_state_detects_stale_and_external_plan_response ... ok
test notifications::pending_actions::tests::epic_approval_without_response_dir_has_missing_target_state ... ok
test editor::completion::tests::commit_inventory_skips_unusable_checkouts_and_bug_stays_empty ... ok
test notifications::pending_actions::tests::custom_gate_uses_only_neutral_terminal_files ... ok
test notifications::pending_actions::tests::epic_approval_is_typed_and_resolves_through_pending_store ... ok
test notifications::pending_actions::tests::launch_approval_is_a_pending_action_kind ... ok
test notifications::tabs::tests::a_panel_and_tag_collision_sorts_as_a_panel_either_way ... ok
test notifications::tabs::tests::a_non_panel_row_does_not_donate_a_panel_icon ... ok
test notifications::tabs::tests::a_resurfaced_row_donates_its_icon_over_a_newer_sent_row ... ok
test notifications::tabs::tests::a_row_donates_its_icon_only_to_its_declared_panel_tab ... ok
test notifications::tabs::tests::an_absent_color_stays_absent_on_the_wire ... ok
test notifications::pending_actions::tests::pending_store_merges_legacy_telegram_shape ... ok
test notifications::pending_actions::tests::cleanup_stale_pending_actions_removes_only_expired_entries ... ok
test notifications::tabs::tests::an_absent_icon_stays_absent_on_the_wire ... ok
test notifications::tabs::tests::a_snoozed_row_leaves_its_panel_tab ... ok
test notifications::tabs::tests::counts_and_tabs_agree_and_skip_read_or_silent_rows ... ok
test notifications::tabs::tests::a_resurfaced_row_donates_its_color_over_a_newer_sent_row ... ok
test notifications::tabs::tests::a_tab_wears_the_newest_declared_color_and_ignores_junk ... ok
test notifications::tabs::tests::declared_panel_outranks_hitl_errors_and_tags ... ok
test notifications::pending_actions::tests::pending_store_registers_and_resolves_prefixes ... ok
test glossary::tests::single_line_match_has_one_span_equal_segment ... ok
test notifications::tabs::tests::oldest_activity_and_next_wake_are_minimums ... ok
test notifications::tabs::tests::hitl_then_errors_then_first_tag_then_general ... ok
test notifications::tabs::tests::reserved_and_malformed_panels_fall_through ... ok
test notifications::tabs::tests::a_tab_wears_the_newest_declared_icon_and_ignores_junk ... ok
test notifications::tabs::tests::snoozed_precedes_muted_for_a_muted_row_with_a_wake_time ... ok
test notifications::tabs::tests::labels_title_case_tag_words ... ok
test parser::tests::description_preserves_internal_blank_lines_then_trims ... ok
test notifications::tabs::tests::tab_order_matches_the_panel ... ok
test notifications::tabs::tests::a_two_tag_row_lands_in_exactly_one_tab ... ok
test parser::tests::indented_blank_run_in_description_does_not_end_spec ... ok
test parser::tests::empty_input_yields_no_specs ... ok
test parser::tests::invalid_utf8_returns_parse_error_wire ... ok
test parser::tests::legacy_changespec_header_detection_requires_whitespace_then_word ... ok
test parser::tests::legacy_changespec_header_separates_specs_without_blank_lines ... ok
test parser::tests::empty_value_lines_become_none_or_empty_per_python_rules ... ok
test parser::tests::drops_incomplete_specs_missing_name_or_status ... ok
test parser::tests::multi_line_description_strips_two_space_continuation ... ok
test parser::tests::new_name_inside_a_spec_starts_a_new_spec ... ok
test parser::tests::parent_cl_pr_bug_scalars_round_trip ... ok
test parser::tests::missing_or_invalid_project_name_metadata_stays_absent ... ok
test parser::tests::patch_header_detection_accepts_canonical_and_legacy_headers ... ok
test glossary::tests::lookup_uses_utf16_editor_positions ... ok
test parser::tests::missing_refs_section_defaults_to_empty ... ok
test parser::tests::pr_origin_scalars_round_trip_and_absence_defaults_unknown ... ok
test parser::tests::project_basename_strips_extension_and_archive_suffix ... ok
test parser::tests::project_name_metadata_is_stamped_on_every_patch ... ok
test glossary::tests::scans_derived_plural_for_term_without_configured_aliases ... ok
test parser::tests::refs_parse_at_end_of_spec ... ok
test parser::tests::parses_direct_name_spec_without_header ... ok
test parser::tests::span_excludes_trailing_blank_separator ... ok
test parser::tests::two_blank_lines_separate_specs ... ok
test parser::tests::rust_end_line_is_real_not_placeholder ... ok
test parser::tests::parses_headered_spec_with_inline_description ... ok
test plan::artifact_link::tests::artifacts_is_compatible_with_either_counterpart_section ... ok
test perf_logs::aggregate::tests::absent_and_empty_sources_are_covered_without_failure ... ok
test perf_logs::aggregate::tests::byte_cap_truncates_tail_without_counting_leading_fragment ... ok
test perf_logs::aggregate::tests::percentile_edges_use_nearest_rank_rounding ... ok
test perf_logs::aggregate::tests::record_cap_marks_source_truncated ... ok
test plan::artifact_link::tests::bead_section_supports_linked_unlinked_and_prettier_wrapped_labels ... ok
test plan::artifact_link::tests::discontiguous_header_groups_before_body_content_are_invalid ... ok
test perf_logs::aggregate::tests::malformed_timestamp_and_partial_trailing_lines_are_reported ... ok
test plan::artifact_link::tests::escapes_labels_and_trailing_text ... ok
test plan::artifact_link::tests::bead_upsert_keeps_bead_frontmatter ... ok
test plan::artifact_link::tests::artifacts_is_list_shaped_and_orders_between_agents_and_commits ... ok
test perf_logs::aggregate::tests::aggregates_mixed_timestamp_formats_and_window ... ok
test plan::artifact_link::tests::back_compat_single_legacy_and_mixed_cases ... ok
test plan::artifact_link::tests::fenced_header_example_is_not_a_live_document_header ... ok
test plan::artifact_link::tests::empty_list_section_is_omitted ... ok
test glossary::tests::wrapped_phrase_does_not_cross_block_boundaries ... ok
test plan::artifact_link::tests::extra_leading_blank_line_is_recognized_as_noncanonical_layout ... ok
test plan::artifact_link::tests::known_header_labels_after_body_content_are_ordinary_bullets ... ok
test plan::artifact_link::tests::ordinary_bold_and_nested_body_bullets_are_not_header_sections ... ok
test plan::artifact_link::tests::list_cap_is_visible_and_round_trips_logically ... ok
test plan::artifact_link::tests::plan_and_prompt_sections_accept_absolute_cross_repo_targets ... ok
test plan::artifact_link::tests::legacy_upsert_preserves_frontmatter_body_and_other_sections ... ok
test plan::artifact_link::tests::title_before_header_means_the_bullet_is_body_content ... ok
test plan::artifact_link::tests::rejects_malformed_duplicate_unknown_and_unterminated_documents ... ok
test plan::artifact_link::tests::multi_section_round_trip_uses_fixed_order ... ok
test plan::artifact_link::tests::parent_upsert_removes_only_legacy_top_level_parent ... ok
test plan::artifact_link::tests::parses_prettier_wrapped_commit_and_preserves_unchanged_bytes ... ok
test plan::artifact_link::tests::remove_section_keeps_the_rest_and_canonical_layout ... ok
test parser::tests::refs_parse_in_canonical_position_and_preserve_raw_invalid_text ... ok
test plan::read::tests::derives_title_from_h1_then_humanized_name ... ok
test plan::read::tests::discovers_local_flat_and_sharded_layout ... ok
test plan::read::tests::discovers_every_repo_kind_with_labels_and_relpaths ... ok
test plan::read::tests::accepts_rfc3339_and_date_only_create_time ... ok
test plan::read::tests::explicit_empty_corpora_disable_the_legacy_repo_scan ... ok
test plan::read::tests::explicit_document_corpora_include_one_bundle_level_shallow_first ... ok
test plan::read::tests::empty_kind_filter_selects_no_repo_plans ... ok
test plan::read::tests::explicit_document_corpora_replace_legacy_scan_and_keep_own_relpaths ... ok
test plan::read::tests::missing_roots_yield_no_plans_without_error ... ok
test plan::read::tests::explicit_document_corpora_skip_prompt_specs_dotdirs_and_deeper_files ... ok
test plan::read::tests::falls_back_to_mtime_when_create_time_absent ... ok
test plan::read::tests::canonical_plans_are_tier_classified_with_tale_fallback ... ok
test plan::read::tests::ignores_non_markdown_files ... ok
test plan::read::tests::explicit_plans_corpus_honors_tier_and_other_labels_ignore_it ... ok
test plan::read::tests::kind_filter_does_not_constrain_local_plans ... ok
test plan::read::tests::filters_repo_corpus_by_kind ... ok
test plan::read::tests::prompt_directory_projects_plan_bullet_label ... ok
test plan::refs::tests::alias_prefix_reparses_as_canonical ... ok
test plan::read::tests::parses_frontmatter_fields_and_normalizes_created_at ... ok
test plan::read::tests::projects_canonical_prompt_link_label_without_polluting_plan_content ... ok
test plan::read::tests::sorts_files_within_a_shard ... ok
test plan::refs::tests::canonicalize_uses_first_matching_root ... ok
test glossary::tests::wrapped_longer_match_wins_over_shorter_at_same_start ... ok
test plan::read::tests::repo_plans_precede_local_plans ... ok
test plan::read::tests::tolerates_malformed_and_absent_frontmatter ... ok
test plan::refs::tests::every_legacy_form_resolves_to_the_same_file ... ok
test plan::refs::tests::missing_keeps_ordered_best_candidates ... ok
test plan::read::tests::mixed_transition_projects_label_only_when_paths_agree ... ok
test plan::refs::tests::typed_reference_round_trips ... ok
test plan::refs::tests::exact_resolution_uses_first_root ... ok
test plan::refs::tests::unregistered_schemes_and_paths_remain_legacy ... ok
test plan::refs::tests::multiple_month_drift_matches_are_ambiguous ... ok
test plan::refs::tests::unique_month_drift_resolves ... ok
test plan::refs::tests::typed_reference_rejects_unsafe_payloads_and_unknown_kinds ... ok
test plan::search::tests::applies_limit_after_ranking ... ok
test plan::refs::tests::validation_messages_remain_stable_after_helper_extraction ... ok
test plan::search::tests::counterpart_label_remains_searchable_as_frontmatter_metadata ... ok
test plan::search::tests::blank_query_is_treated_as_browse ... ok
test plan::search::tests::browse_mode_returns_all_plans_sorted_by_recency ... ok
test plan::search::tests::date_range_filters_inclusively_on_day_bounds ... ok
test plan::search::tests::excludes_plans_without_dates_when_date_filter_active ... ok
test plan::search::tests::field_names_constant_matches_searchable_fields ... ok
test plan::search::tests::explicit_sort_modes_override_defaults ... ok
test plan::search::tests::filters_status_source_and_date_together ... ok
test plan::search::tests::matches_case_insensitive_unicode_substrings ... ok
test plan::search::tests::matches_every_searchable_field ... ok
test plan::search::tests::no_match_returns_empty_results ... ok
test plan::search::tests::parses_relative_and_partial_date_bounds ... ok
test plan::read::tests::tier_frontmatter_classifies_canonical_plans_and_filters_post_parse ... ok
test plan::search::tests::ranks_title_above_frontmatter_above_body ... ok
test plan::search::tests::recency_breaks_relevance_ties ... ok
test plan::search::tests::rejects_invalid_date_bound ... ok
test plan::search::tests::public_search_filters_across_explicit_corpus_labels ... ok
test plan::search::tests::relative_months_clamp_to_month_length ... ok
test plan::search::tests::rejects_unknown_sort_mode ... ok
test plan::search::tests::repo_outranks_local_on_equal_relevance ... ok
test plan::search::tests::public_search_kind_filter_narrows_repo_only ... ok
test plan::search::tests::public_search_reads_ranks_and_prioritizes_repo ... ok
test plan::search::tests::source_filter_scopes_results ... ok
test plan::search::tests::status_filter_is_case_insensitive ... ok
test plan::search::tests::status_value_is_reported_as_status_not_frontmatter ... ok
test plan::validate::tests::common_field_rules_report_together_with_locations ... ok
test plan::search::tests::zero_limit_is_unlimited ... ok
test plan::validate::tests::a_malformed_header_block_does_not_hide_frontmatter_diagnostics ... ok
test plan::validate::tests::epic_missing_collection_and_phase_scalar_rules_report ... ok
test plan::validate::tests::epic_top_level_rules_all_report ... ok
test glossary::tests::scan_skips_fenced_and_inline_code_literals ... ok
test plan::validate::tests::missing_phase_description_warns_without_changing_the_plan ... ok
test plan::validate::tests::a_well_formed_or_absent_header_block_raises_nothing ... ok
test plan::validate::tests::legacy_changespec_frontmatter_key_validates_as_patch ... ok
test plan::validate::tests::missing_wrong_type_and_invalid_tier_are_distinct ... ok
test plan::validate::tests::both_tiers_require_a_non_empty_string_title ... ok
test plan::validate::tests::schema_is_ordered_and_contains_exact_phase_guidance ... ok
test plan::validate::tests::phase_optional_fields_validate_types_and_model_syntax ... ok
test plan::validate::tests::phase_shape_keys_and_required_fields_report ... ok
test plan::validate::tests::unsupported_caller_tier_is_a_usage_error ... ok
test plan::validate::tests::phase_ids_and_dependency_graph_rules_report_in_one_pass ... ok
test plan::validate::tests::structural_diagnostics_cover_each_rule ... ok
test plan::validate::tests::tale_epic_fields_are_inert_warnings ... ok
test plan::validate::tests::other_header_block_defects_are_located_errors ... ok
test plan::validate::tests::trailing_text_in_a_link_section_is_a_located_error ... ok
test plan::validate::tests::valid_epic_returns_all_normalized_fields ... ok
test plan::validate::tests::parent_bead_is_optional_epic_only_and_type_checked ... ok
test plan::validate::tests::valid_tale_returns_normalized_plan_and_accepts_system_fields ... ok
test procs::store::tests::legacy_commandless_tui_rows_remain_readable ... ok
test plan::validate::tests::managed_plan_proposer_is_optional_normalized_and_type_checked ... ok
test agent_stats::run::tests::runner_query_requires_matching_live_workspace_claim ... ok
test procs::store::tests::detached_kind_round_trips_and_unknown_kinds_are_rejected ... ok
test agent_scan::index::tests::late_xprompts_file_refreshes_cached_record ... ok
test plan::validate::tests::managed_plan_links_are_optional_on_both_tiers_and_type_checked ... ok
test plan::validate::tests::phase_size_is_strict_for_authoring_and_legacy_safe_for_launch ... ok
test bead::schema::tests::fresh_schema_accepts_claimed_status ... ok
test plan::validate::tests::tale_size_is_required_strict_and_normalized ... ok
test procs::store::tests::append_and_read_round_trip_is_newest_first_and_normalizes_tags ... ok
test glossary::tests::scans_case_insensitively_with_longest_non_overlapping_matches ... ok
test project_spec::tests::archive_detection_accepts_canonical_and_legacy_extensions ... ok
test project_spec::tests::lifecycle_read_accepts_canonical_disabled_state ... ok
test project_spec::tests::lifecycle_read_accepts_canonical_sibling_state ... ok
test project_spec::tests::lifecycle_read_defaults_missing_state_to_enabled ... ok
test project_spec::tests::lifecycle_read_warns_and_defaults_invalid_state ... ok
test project_spec::tests::lifecycle_read_normalizes_legacy_enabled_and_disabled_states ... ok
test project_spec::tests::lifecycle_read_warns_on_duplicate_state ... ok
test procs::store::tests::legacy_task_id_rows_are_accepted_and_rewritten_with_proc_id ... ok
test project_spec::tests::lifecycle_update_accepts_sibling_target_state ... ok
test project_spec::tests::lifecycle_project_records_include_aliases_and_collision_warnings ... ok
test project_spec::tests::lifecycle_update_inserts_before_first_name ... ok
test project_spec::tests::lifecycle_update_normalizes_legacy_target_states ... ok
test project_spec::tests::lifecycle_update_inserts_before_running_and_preserves_crlf ... ok
test project_spec::tests::lifecycle_project_records_classify_true_projects_and_vcs_kind ... ok
test project_spec::tests::lifecycle_update_replaces_existing_state_line ... ok
test project_spec::tests::project_aliases_read_defaults_missing_aliases_to_empty ... ok
test project_spec::tests::lifecycle_update_rejects_invalid_target_state ... ok
test project_spec::tests::project_aliases_update_rejects_invalid_or_duplicate_aliases ... ok
test project_spec::tests::project_aliases_read_sorts_dedupes_and_warns ... ok
test project_spec::tests::project_aliases_update_inserts_before_first_name ... ok
test procs::store::tests::reserve_replays_identical_shell_request_and_rejects_conflicts ... ok
test project_spec::tests::project_aliases_update_removes_existing_aliases ... ok
test project_spec::tests::project_name_read_warns_on_invalid_and_duplicate_names ... ok
test procs::store::tests::unknown_fields_are_tolerated_and_malformed_rows_are_dropped_on_rewrite ... ok
test project_spec::tests::project_aliases_update_replaces_existing_aliases_sorted ... ok
test project_spec::tests::project_aliases_update_inserts_before_running_and_preserves_crlf ... ok
test project_spec::tests::project_name_update_inserts_replaces_and_removes_name ... ok
test project_spec::tests::project_name_update_preserves_crlf_and_rejects_invalid_name ... ok
test project_spec::tests::project_name_read_accepts_missing_and_present_name ... ok
test project_spec::tests::project_spec_basename_accepts_active_and_archive_extensions ... ok
test procs::store::tests::updating_an_existing_row_to_the_detached_kind_validates ... ok
test project_spec::tests::project_spec_filenames_are_canonical_sase ... ok
test procs::store::tests::terminal_transition_guards_and_repeat_writes_preserve_final_fields ... ok
test project_spec::tests::lifecycle_project_records_filter_and_sort_projects ... ok
test project_spec::tests::project_spec_path_conversions_emit_canonical_extension ... ok
test prompt_artifact::tests::manifest_parse_tolerates_unknown_fields ... ok
test prompt_artifact::tests::manifest_round_trip_skips_bad_and_future_lines ... ok
test prompt_artifact::tests::pool_names_cover_paths_unicode_extensions_and_length ... ok
test prompt_artifact::tests::rewrite_does_not_allocate_for_absent_tokens ... ok
test prompt_artifact::tests::rewrite_reserves_existing_definitions_and_numeric_uses ... ok
test prompt_artifact::tests::rewrite_is_idempotent_and_reports_only_linked_records ... ok
test prompt_artifact::tests::rewrite_reuses_matching_existing_definition ... ok
test prompt_artifact::tests::rewrite_uses_expanded_reference_when_authored_token_is_absent ... ok
test prompt_artifact::tests::rewrite_shares_labels_for_one_destination ... ok
test prompt_artifact::tests::sanitized_collisions_are_disambiguated ... ok
test prompt_artifact::tests::selection_keeps_newest_rows_in_first_reference_order ... ok
test prompt_literals::tests::ignores_unmatched_and_multiline_runs ... ok
test procs::store::tests::retention_reports_only_store_owned_logs_for_deletion ... ok
test prompt_literals::tests::keeps_crlf_lines_independent ... ok
test procs::store::tests::running_rows_survive_retention ... ok
test prompt_artifact::tests::rewrite_skips_literal_zones_and_existing_markdown_links ... ok
test prompt_literals::tests::recognizes_punctuation_and_word_adjacent_spans ... ok
test prompt_literals::tests::merges_overlapping_and_adjacent_masks_once ... ok
test prompt_literals::tests::matches_equal_runs_while_allowing_shorter_nested_runs ... ok
test prompt_literals::tests::reports_utf8_byte_offsets ... ok
test procs::store::tests::proc_shell_lifecycle_requires_settlement_and_single_supervisor_finish ... ok
test provider_disable::tests::canonical_active_file_is_not_rewritten ... ok
test provider_disable::tests::invalid_inputs_are_rejected ... ok
test procs::store::tests::retention_keeps_newest_terminal_rows_at_and_beyond_limit ... ok
test provider_disable::tests::malformed_envelope_deletes_state ... ok
test provider_disable::tests::clear_one_and_missing_clear_are_idempotent ... ok
test provider_disable::tests::exact_boundary_expiry_and_until_cleared_persistence ... ok
test query::searchable::tests::project_dir_name_basic ... ok
test query::searchable::tests::artifact_references_are_searchable ... ok
test query::profile::tests::from_wire_rejects_digest_mismatch ... ok
test provider_disable::tests::malformed_and_expired_entries_are_pruned_independently ... ok
test provider_disable::tests::try_set_returns_existing_record_without_mutating_it ... ok
test provider_disable::tests::try_set_replaces_an_expired_record ... ok
test query::profile::tests::from_wire_rejects_unknown_predicate ... ok
test provider_disable::tests::replacing_one_provider_preserves_siblings ... ok
test query::tests::canonical_escape_string_value ... ok
test query::tests::canonical_not_around_and_gets_parens ... ok
test query::tests::canonical_implicit_and ... ok
test query::tests::canonical_error_suffix_running_markers ... ok
test query::tests::canonical_any_special_implicit_and ... ok
test query::tests::canonical_and_inside_or_gets_parens ... ok
test query::tests::boolean_precedence_works_on_generic_rows ... ok
test query::tests::canonical_or_inside_and_gets_parens ... ok
test query::tests::canonical_not_string ... ok
test query::tests::ast_round_trips_through_json ... ok
test query::tests::canonical_or ... ok
test query::tests::canonical_case_sensitive_string ... ok
test query::tests::canonical_status_property ... ok
test query::tests::digest_mismatch_is_rejected_before_evaluation ... ok
test query::tests::canonical_simple_string ... ok
test query::tests::canonical_property_filter_shorthands ... ok
test query::tests::flat_negation_and_comma_rules ... ok
test query::tests::flat_canonical_groups_fields_then_predicates_then_text ... ok
test query::tests::flat_profile_parses_closed_host_predicates_without_boolean_syntax ... ok
test query::tests::flat_predicates_evaluate_absent_facts_as_false ... ok
test query::tests::invalid_profile_is_structured_error ... ok
test query::profile::tests::patch_profile_digest_matches_python_compiler ... ok
test query::tests::parse_any_special_expands_to_or ... ok
test query::tests::parse_bare_word ... ok
test query::tests::flat_validates_enum_bool_and_int_literals ... ok
test query::tests::flat_repeated_values_are_any_match_and_exclusions_negate ... ok
test query::tests::parse_double_not_collapses_to_two_nots ... ok
test query::tests::flat_tokenizer_rejects_boolean_syntax ... ok
test query::tests::parse_case_sensitive_string ... ok
test query::tests::generic_corpus_reuses_indexes_across_evaluations ... ok
test query::tests::parse_error_missing_operand ... ok
test query::tests::generic_rows_honor_searchable_fields_and_predicates ... ok
test query::tests::parse_error_empty_query ... ok
test query::tests::parse_error_suffix_and_string ... ok
test query::tests::parse_implicit_and_with_parens ... ok
test query::tests::parse_error_unmatched_paren ... ok
test query::tests::parse_not_running_agent_shorthand ... ok
test query::tests::parse_not_tightest ... ok
test query::tests::parse_implicit_and ... ok
test query::tests::parse_not_running_process_shorthand ... ok
test query::tests::parse_or_loosest ... ok
test query::tests::parse_property_match ... ok
test query::tests::parser_error_wire_kind_is_parser ... ok
test query::tests::parse_standalone_exclamation_is_error_suffix ... ok
test query::tests::patch_wrappers_match_explicit_patch_profile ... ok
test query::tests::token_round_trips_through_json ... ok
test query::tests::tokenize_any_special_only_standalone ... ok
test query::tests::tokenize_at_not_standalone_is_error ... ok
test query::tests::tokenize_bare_word_with_numbers ... ok
test query::tests::tokenize_case_sensitive_string ... ok
test query::tests::tokenize_dollar_not_standalone_is_error ... ok
test query::tests::tokenize_double_exclamation_not_standalone_is_two_nots ... ok
test query::tests::tokenize_double_exclamation_standalone_is_not_error_suffix ... ok
test query::tests::tokenize_invalid_escape ... ok
test query::tests::tokenize_invalid_property_key ... ok
test query::tests::tokenize_not_at_with_space ... ok
test query::tests::tokenize_not_dollar_with_space ... ok
test query::tests::tokenize_not_keyword_with_error_suffix ... ok
test query::tests::tokenize_origin_property ... ok
test query::tests::tokenize_paren_and_keywords ... ok
test query::tests::tokenize_property_quoted_value ... ok
test query::tests::tokenize_quoted_with_escapes ... ok
test query::tests::tokenize_standalone_at_and_bang ... ok
test query::tests::tokenize_property_shorthands ... ok
test query::tests::tokenize_status_shorthand_invalid ... ok
test query::tests::tokenize_status_shorthand_uppercase ... ok
test query::tests::tokenize_rejects_disabled_predicate_and_any_special ... ok
test query::tests::tokenize_status_shorthands ... ok
test query::tests::tokenize_triple_specials ... ok
test query::tests::tokenize_unterminated_string ... ok
test query::tests::tokenize_rejects_undeclared_property_and_keeps_span ... ok
test query::tests::tokenizer_error_wire_kind_is_tokenizer ... ok
test referenced_by::tests::duplicate_block_collapses_to_one ... ok
test referenced_by::tests::stray_end_marker_with_no_start_is_left_alone ... ok
test referenced_by::tests::strip_leaves_a_document_with_no_block_untouched ... ok
test referenced_by::tests::render_sorts_rows_and_numbers_links_through_the_shared_allocator ... ok
test referenced_by::tests::render_parse_round_trips ... ok
test query::tests::tokenize_uses_profile_fields_and_sigils ... ok
test referenced_by::tests::render_caps_at_fifty_rows_and_reports_omitted ... ok
test referenced_by::tests::unterminated_start_marker_extends_to_eof ... ok
test referenced_by::tests::upsert_with_empty_table_removes_the_block ... ok
test referenced_by::tests::upsert_places_block_at_bottom_and_is_idempotent ... ok
test provider_disable::tests::concurrent_entries_are_returned_in_provider_order ... ok
test runner_limit_override::tests::invalid_inputs_are_rejected ... ok
test agent_scan::index::tests::upsert_and_delete_one_artifact_row ... ok
test runner_limit_override::tests::exact_and_no_expiry_records_obey_boundary_expiry ... ok
test runner_limit_override::tests::persisted_json_is_complete_and_clear_is_idempotent ... ok
test sections::tests::comments_basic_and_with_error_suffix ... ok
test runner_limit_override::tests::malformed_stale_and_invalid_state_self_cleans ... ok
test sections::tests::commits_drawers_attach_to_current_entry ... ok
test runner_limit_override::tests::positive_limits_round_trip_and_replace ... ok
test sections::tests::commits_proposal_letter_carries_through ... ok
test sections::tests::commits_body_lines_use_six_space_indent_and_dot_for_blank ... ok
test sections::tests::hooks_running_agent_suffix_split_from_summary ... ok
test referenced_by::tests::strip_normalizes_trailing_whitespace_for_stable_digests ... ok
test sections::tests::commits_line_starts_new_entry_and_strips_trailing_suffix ... ok
test sections::tests::hooks_new_command_flushes_previous_hook ... ok
test sections::tests::commits_running_agent_and_rejected_proposal_suffixes ... ok
test snippet_session::session_tests::apply_edit_deletes_offsets_falling_before_the_first_stop ... ok
test sections::tests::stitches_line_uses_same_entry_parser ... ok
test snippet_session::session_tests::advance_and_retreat_on_an_inactive_session_are_no_ops ... ok
test snippet_session::session_tests::apply_edit_normalizes_unordered_edit_bounds ... ok
test snippet_session::session_tests::apply_edit_on_an_inactive_session_is_a_no_op ... ok
test sections::tests::hooks_command_then_status_line ... ok
test agent_scan::index::tests::query_self_heals_appended_plan_submitted_at ... ok
test snippet_session::session_tests::apply_session_event_advance_retreat_apply_edit_and_clear_round_trip ... ok
test snippet_session::session_tests::apply_edit_remaps_stops_before_at_inside_and_after_the_edit ... ok
test snippet_session::session_tests::apply_session_event_drives_the_reported_bug_scenario_end_to_end ... ok
test snippet_session::session_tests::apply_session_event_expand_reports_the_new_cursor_offset ... ok
test snippet_session::session_tests::apply_session_event_plan_is_stateless_and_echoes_state_unchanged ... ok
test snippet_session::session_tests::clear_ends_an_active_session ... ok
test snippet_session::session_tests::deleting_a_whole_nested_expansion_drops_it_without_corrupting_the_enclosing_session ... ok
test snippet_session::session_tests::depth_cap_drops_outermost_session_on_overflow ... ok
test snippet_session::session_tests::expand_outside_active_span_resets_instead_of_nesting ... ok
test snippet_session::session_tests::event_kind_tags_match_the_documented_snake_case_names ... ok
test snippet_session::session_tests::event_result_serializes_with_the_documented_field_order ... ok
test snippet_session::session_tests::expanding_a_no_stop_plan_outside_any_session_clears_state ... ok
test snippet_session::session_tests::nesting_a_plan_with_no_stops_leaves_the_enclosing_session_untouched ... ok
test snippet_session::session_tests::nesting_at_a_stop_resumes_outer_session_after_inner_exhausts ... ok
test snippet_session::session_tests::retreat_at_start_and_advance_past_end_report_no_target ... ok
test snippet_session::session_tests::two_levels_of_nesting_resume_enclosing_sessions_in_order ... ok
test snippet_session::session_tests::state_serializes_with_the_documented_field_order ... ok
test snippet_session::tests::continuation_line_indentation_can_be_disabled ... ok
test agent_stats::run::tests::runner_query_filters_stale_and_never_started_records ... ok
test snippet_session::tests::continuation_lines_are_indented_and_offsets_shift ... ok
test snippet_session::tests::escaped_dollars_are_literal_and_not_tabstops ... ok
test snippet_session::tests::missing_zero_appends_implicit_final_stop ... ok
test sections::tests::deltas_requires_exactly_two_leading_spaces ... ok
test snippet_session::tests::multi_digit_tabstops_sort_by_number ... ok
test sections::tests::deltas_glyph_to_change_type_mapping ... ok
test snippet_session::tests::templates_without_markers_have_no_stops ... ok
test snippet_session::tests::offsets_are_character_offsets_not_byte_offsets ... ok
test snippet_session::tests::repeated_tabstop_numbers_only_create_one_stop ... ok
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
test sections::tests::mentors_legacy_profiles_without_counts_split_on_whitespace ... ok
test parser::tests::save_pending_entries_flushes_at_field_boundary ... ok
test sections::tests::mentors_draft_marker_is_stripped ... ok
test sections::tests::mentors_running_status_without_timestamp_parses_as_none ... ok
test parser::tests::legacy_commits_section_still_parses_as_stitches ... ok
test parser::tests::parse_patch_project_bytes_emits_canonical_patch_wire ... ok
test agent_scan::index::tests::related_artifact_dirs_follow_retry_and_parent_lineage ... ok
test status::name::tests::has_suffix_recognises_single_and_double_underscore ... ok
test bead::schema::tests::issue_type_migration_preserves_and_accepts_claimed_status ... ok
test sections::tests::mentors_entry_with_count_then_status ... ok
test sections::tests::mentors_entry_ref_suffix_marks_type_entry_ref ... ok
test bead::schema::tests::fresh_schema_enforces_task_and_ready_constraints ... ok
test bead::schema::tests::refs_migration_preserves_existing_rows_and_defaults_empty ... ok
test bead::schema::tests::fresh_schema_enforces_task_type_check_and_accepts_task_rows ... ok
test status::constants::tests::unmodified_status_passes_through ... ok
test status::planner::tests::archive_action_none_within_archive_class ... ok
test status::constants::tests::legacy_ready_to_mail_suffix_stripped ... ok
test status::constants::tests::terminal_statuses_have_no_outgoing_transitions ... ok
test status::planner::tests::archive_action_from_archive_under_no_validate ... ok
test status::planner::tests::invalid_transition_validate_false_allows ... ok
test status::planner::tests::archive_action_to_archive_on_submitted ... ok
test status::constants::tests::valid_transitions_allow_known_pairs ... ok
test status::planner::tests::parent_constraint_skipped_for_reverted_branch ... ok
test status::planner::tests::parent_wip_blocks_child_to_mailed ... ok
test status::constants::tests::workspace_suffix_stripped_from_status ... ok
test status::planner::tests::invalid_transition_validate_true_rejects ... ok
test status::planner::tests::archive_action_none_within_main_class ... ok
test status::constants::tests::workspace_suffix_does_not_block_validation ... ok
test status::planner::tests::ready_to_draft_blocked_by_invalid_children ... ok
test status::planner::tests::ready_to_draft_appends_suffix_and_sets_mentor ... ok
test status::planner::tests::parent_ready_does_not_block_mailed ... ok
test status::planner::tests::legacy_ready_to_mail_suffix_stripped_for_validation ... ok
test status::planner::tests::archived_terminal_no_further_transitions ... ok
test status::constants::tests::unknown_statuses_rejected ... ok
test status::planner::tests::invalid_transition_error_format_matches_python ... ok
test status::planner::tests::reverted_terminal_no_further_transitions ... ok
test status::planner::tests::draft_to_ready_no_suffix_clears_mentors_only ... ok
test status::planner::tests::schema_version_mismatch_returns_error ... ok
test status::planner::tests::submitted_terminal_no_further_transitions ... ok
test status::planner::tests::unknown_status_rejected_under_validation ... ok
test status::planner::tests::wip_to_draft_no_suffix_no_mentor ... ok
test status::wire::tests::json_shape_keeps_optional_fields_as_null ... ok
test status::wire::tests::plan_round_trips_through_json ... ok
test status::wire::tests::request_round_trips_through_json ... ok
test status::planner::tests::wip_to_ready_blocked_by_sibling_unreverted_children ... ok
test status::planner::tests::ready_to_draft_picks_lowest_free_suffix ... ok
test status::wire::tests::schema_mismatch_returns_error ... ok
test status::planner::tests::workspace_suffix_normalised_for_validation ... ok
test store_lock::tests::timeout_parser_accepts_positive_floats_and_rejects_bad_values ... ok
test suffix::tests::legacy_tilde_colon_is_plain ... ok
test suffix::tests::long_prefixes_take_priority_over_short ... ok
test suffix::tests::none_input_returns_none_pair ... ok
test suffix::tests::standalone_markers_have_empty_value ... ok
test suffix::tests::unknown_prefix_returns_value_unchanged ... ok
test suffix::tests::entry_ref_recognizes_digit_optional_letter ... ok
test suffix::tests::metahook_promotes_error_to_metahook_complete ... ok
test task_type::snapshot::tests::parse_rejects_invalid_json ... ok
test task_type::spec::tests::field_types_are_the_scalar_subset_of_property_types ... ok
test task_type::spec::tests::rejects_missing_label_summary_and_when_to_use_caps ... ok
test task_type::spec::tests::digest_is_stable_across_omitted_and_explicit_defaults ... ok
test task_type::spec::tests::rejects_unsupported_schema_version ... ok
test status::planner::tests::draft_to_ready_with_suffix_strips_and_clears_mentors ... ok
test bead::mutation::tests::concurrent_update_and_claim_preserve_both_events_and_projection ... ok
test task_type::spec::tests::rejects_unknown_default_size ... ok
test task_type::render::tests::missing_placeholder_value_is_an_error ... ok
test task_type::render::tests::does_not_rescan_substituted_values ... ok
test task_type::render::tests::renders_placeholders_verbatim ... ok
test task_type::render::tests::empty_without_template ... ok
test task_type::spec::tests::rejects_empty_or_unknown_roles ... ok
test status::planner::tests::wip_to_ready_with_suffix_strips ... ok
test task_type::spec::tests::rejects_malformed_glyph_and_accent ... ok
test task_type::spec::tests::accepts_single_cell_glyph_and_hex_accent ... ok
test agent_stats::run::tests::user_hidden_skipped_counts_only_runner_eligible_rows ... ok
test task_type::spec::tests::accepts_flag_as_a_claimable_task_type_slug ... ok
test bead::schema::tests::fresh_schema_accepts_bookend_phase_sizes ... ok
test task_type::spec::tests::rejects_empty_enum_values_and_invalid_regex ... ok
test task_type::spec::tests::rejects_duplicate_and_bad_field_names ... ok
test task_type::spec::tests::rejects_reserved_and_malformed_slugs ... ok
test task_type::spec::tests::rejects_template_placeholders_that_are_undeclared_or_data_only ... ok
test task_type::spec::tests::reserved_slugs_are_the_three_issue_types_and_four_filter_sentinels ... ok
test task_type::spec::tests::rejects_unsupported_field_types_outside_scalar_subset ... ok
test task_type::values::tests::invalid_spec_is_a_hard_error ... ok
test task_type::spec::tests::accepts_spec_with_no_body_template ... ok
test vcs_log::aggregate::tests::limit_zero_returns_empty ... ok
test vcs_log::aggregate::tests::preserves_commit_presence ... ok
test vcs_log::aggregate::tests::empty_input_returns_empty ... ok
test vcs_log::aggregate::tests::aggregated_row_serializes_flat ... ok
test vcs_log::aggregate::tests::equal_timestamp_tie_break_is_repo_then_full_id ... ok
test vcs_log::aggregate::tests::interleaves_repos_by_timestamp_desc ... ok
test vcs_log::aggregate::tests::truncates_to_limit ... ok
test task_type::values::tests::rejects_padded_or_non_decimal_integers_and_short_dates ... ok
test vcs_log::classify::tests::ahead_wins_when_sets_overlap ... ok
test vcs_log::classify::tests::classifies_synced_ahead_and_behind ... ok
test vcs_log::merge_summary::tests::parses_branch_summary_with_target ... ok
test vcs_log::merge_summary::tests::merge_prefix_without_known_shape_returns_none ... ok
test vcs_log::merge_summary::tests::parses_github_pull_request_summary ... ok
test vcs_log::merge_summary::tests::parses_branch_summary ... ok
test vcs_log::merge_summary::tests::parses_remote_branch_summary ... ok
test parser::tests::full_section_parity_emits_structured_entries ... ok
test vcs_log::merge_summary::tests::parses_remote_branch_summary_with_target ... ok
test vcs_log::merge_summary::tests::partial_pull_request_shape_returns_none ... ok
test sections::tests::timestamps_hybrid_bracketed_yymmdd_parses ... ok
test vcs_log::merge_summary::tests::unrecognized_subject_returns_none ... ok
test sections::tests::timestamps_legacy_bracketed_format_still_parses ... ok
test sections::tests::timestamps_new_format_parses ... ok
test task_type::snapshot::tests::rejects_digest_mismatch_and_duplicate_slugs ... ok
test task_type::spec::tests::valid_spec_passes_and_digest_is_stable ... ok
test task_type::values::tests::empty_required_string_is_missing ... ok
test task_type::spec::tests::rejects_validator_keys_on_the_wrong_field_type ... ok
test vcs_log::merge_summary::tests::pull_request_empty_body_has_no_headline ... ok
test vcs_log::origin::tests::classifies_plain_commit_as_manual ... ok
test vcs_log::origin::tests::ignores_tag_shaped_body_text ... ok
test vcs_log::origin::tests::type_stitch_classifies_as_stitch ... ok
test task_type::values::tests::reports_missing_unknown_and_invalid_together ... ok
test vcs_log::origin::tests::legacy_agent_bead_or_plan_classifies_as_stitch ... ok
test vcs_log::origin::tests::legacy_type_spelling_classifies_as_stitch ... ok
test vcs_log::parsers::tests::body_containing_unit_separator_stays_in_body ... ok
test vcs_log::parsers::tests::commit_with_stitch_type_gets_stitch_origin ... ok
test vcs_log::origin::tests::non_stitch_type_classifies_as_auto ... ok
test vcs_log::parsers::tests::empty_stream_returns_empty ... ok
test provider_disable::tests::first_writer_wins_under_contention_without_extending_or_losing_siblings ... ok
test task_type::values::tests::reports_string_max_length_and_allows_optional_fields_to_be_absent ... ok
test vcs_log::parsers::tests::octopus_merge_parses_all_parent_ids ... ok
test vcs_log::parsers::tests::legacy_seven_field_commit_has_no_parents ... ok
test vcs_log::parsers::tests::record_with_unparseable_timestamp_is_dropped ... ok
test vcs_log::parsers::tests::record_with_too_few_fields_is_dropped ... ok
test vcs_log::parsers::tests::git_appends_newline_between_records_is_stripped ... ok
test vcs_log::parsers::tests::multiline_body_is_preserved_verbatim ... ok
test vcs_log::parsers::tests::root_commit_empty_parent_field_has_no_parents ... ok
test task_type::values::tests::valid_values_return_no_errors ... ok
test vcs_log::parsers::tests::trailing_record_separator_yields_no_blank_commit ... ok
test wire::tests::empty_lists_serialize_as_arrays_not_null ... ok
test vcs_log::parsers::tests::single_commit_parses_all_fields ... ok
test wire::tests::legacy_cl_or_pr_key_deserializes_as_pr_url ... ok
test vcs_log::parsers::tests::multiple_commits_preserve_order ... ok
test wire::tests::legacy_changespec_wire_deserializes_canonical_patch_shape ... ok
test wire::tests::legacy_wire_field_order_matches_python ... ok
test wire::tests::none_fields_serialize_as_json_null ... ok
test wire::tests::delta_wire_uses_long_form ... ok
test workspace_lease::tests::authorize_rejects_primary_and_reserved_numbers ... ok
test workspace_lease::tests::empty_operation_uses_the_step_name_alone ... ok
test wire::tests::parse_error_wire_shape ... ok
test workspace_lease::tests::failure_message_names_step_and_forbids_primary_fallback ... ok
test workspace_lease::tests::normalize_maps_legacy_primary_only ... ok
test workspace_lease::tests::pool_bounds_match_unified_claim_range ... ok
test wire::tests::populated_patch_round_trips ... ok
test task_type::snapshot::tests::round_trips_and_sorts_by_slug ... ok
test xprompt_catalog::tests::catalog_payloads_without_memory_fields_still_deserialize ... ok
test wire::tests::patch_wire_deserializes_legacy_changespec_shape ... ok
test agent_stats::run::tests::runner_recovers_synthesized_hidden_lanes_without_trusting_the_stamp ... ok
test wire::tests::patch_wire_serializes_canonical_stitch_keys ... ok
test workspace_lease::tests::primary_error_names_legacy_spelling ... ok
test workspace_lease::tests::validate_policy_requires_kind_identity_and_leasable_workspace ... ok
test xprompt_catalog::tests::composes_unicode_aliases_and_handles_unchanged_leading_scalars ... ok
test wire::tests::source_span_round_trips ... ok
test xprompt_catalog::tests::composes_capitalized_aliases_and_preserves_remaining_case ... ok
test xprompt_catalog::tests::aliases_use_composed_templates_and_references_can_target_aliases ... ok
test xprompt_catalog::tests::explicit_capitalized_trigger_wins_alias_collision ... ok
test xprompt_catalog::tests::known_projects_use_display_names_aliases_and_gp_fallback ... ok
test xprompt_catalog::tests::invalid_memory_notes_become_diagnostics_instead_of_silent_gaps ... ok
test xprompt_catalog::tests::packaged_skill_frame_template_is_not_a_skill_source ... ok
test xprompt_catalog::tests::home_skills_use_the_skill_namespace_and_project_qualified_form ... ok
test xprompt_catalog::tests::computes_known_project_local_config_definition_range ... ok
test xprompt_catalog::tests::packaged_skills_load_from_nested_xprompts_skills_only ... ok
test task_type::values::tests::validates_enum_integer_and_date ... ok
test xprompt_catalog::tests::explicit_project_selection_picks_that_projects_memory_only ... ok
test xprompt_catalog::tests::memory_notes_load_as_namespaced_no_argument_xprompt_memories ... ok
test xprompt_catalog::tests::ordinary_definitions_cannot_claim_the_reserved_memory_namespace ... ok
test xprompt_catalog::tests::config_workflows_are_ignored_but_file_backed_project_workflows_load ... ok
test xprompt_catalog::tests::canonical_project_sources_win_with_legacy_read_compatibility ... ok
test xprompt_catalog::tests::project_config_collision_reports_split_state ... ok
test agent_stats::run::tests::runner_peak_can_exceed_ten_and_long_trend_stays_bounded ... ok
test xprompt_catalog::tests::project_memory_shadows_home_memory_of_the_same_stem ... ok
test xprompt_catalog::tests::loads_plugin_file_and_config_catalog_sources ... ok
test xprompt_catalog::tests::project_catalog_uses_canonical_namespace_and_filter_refs ... ok
test xprompt_catalog::tests::pseudo_sources_do_not_get_definition_paths ... ok
test xprompt_catalog::tests::yaml_child_key_range_finds_immediate_quoted_children ... ok
test xprompt_catalog::tests::split_canonical_and_legacy_memory_state_is_a_collision_error ... ok
test agent_scan::selector::tests::multiple_selectors_preserve_order_and_dedup ... ok
test xprompt_catalog::tests::rejects_misplaced_skill_definitions_in_both_directions ... ok
test xprompt_catalog::tests::snippet_reference_golden_vectors ... ok
test xprompt_catalog::tests::parity_fixture_covers_supported_catalog_sources ... ok
test agent_stats::run::tests::attributes_project_and_patch_work_with_filters_and_statuses ... ok
test agent_scan::selector::tests::exact_key_wildcard_uses_newest_artifact_only ... ok
test agent_stats::run::tests::runner_diagnostics_separate_malformed_rows_and_invalid_intervals ... ok
test xprompt_catalog::tests::converts_native_xprompt_snippet_templates ... ok
test xprompt_catalog::tests::loads_native_snippet_catalog_with_user_overrides ... ok
test xprompt_catalog::tests::parses_markdown_frontmatter_local_xprompts_without_global_entry ... ok
test xprompt_catalog::tests::native_snippet_catalog_resolves_references_after_user_merge ... ok
test agent_scan::index::tests::schema_v18_upgrade_adds_xprompts_signature_column ... ok
test agent_scan::index::tests::output_variable_history_filters_groups_and_truncates ... ok
test editor::completion::tests::commit_inventory_merges_repositories_by_recency_and_assigns_rank ... ok
test procs::store::tests::concurrent_writers_do_not_lose_rows ... ok
test telemetry::store::tests::wal_initialization_lock_wait_is_bounded ... ok
test agent_scan::selector::tests::hood_and_global_selectors_collapse_repeated_runs ... ok
test agent_scan::selector::tests::unscoped_key_wildcard_and_unnamed_rows ... ok
test xprompt_catalog::tests::loads_markdown_and_workflow_with_canonical_insertions ... ok
test xprompt_catalog::tests::filters_step_inputs_and_formats_defaults ... ok
test bead::schema::tests::snoozed_status_migration_admits_snoozed_tasks_and_keeps_close_history ... ok
test xprompt_catalog::tests::memory_entries_render_as_memory_with_a_navigable_definition ... ok
test bead::schema::tests::relax_migration_preserves_claimed_rows_and_related_data ... ok
test telemetry::store::tests::histogram_quantile_interpolates_cumulative_buckets ... ok
test bead::schema::tests::task_ready_migration_preserves_rows_and_dependencies ... ok
test telemetry::store::tests::corrupt_store_is_quarantined_and_recreated ... ok
test xprompt_catalog::tests::projects_repeatable_agent_input_metadata ... ok
test editor::completion::tests::payload_inventory_discloses_the_scan_bound ... ok
test agent_scan::index::tests::terminalize_stale_active_rows_hides_abandoned_record ... ok
test telemetry::store::tests::counter_deltas_aggregate_and_group ... ok
test telemetry::store::tests::gauge_instant_query_uses_latest_live_value_per_source ... ok
test agent_scan::selector::tests::unscoped_and_exact_selectors_use_newest_artifact ... ok
test bead::schema::tests::flag_type_migration_admits_flag_rows_and_keeps_snooze ... ok
test agent_scan::index::tests::terminalize_repairs_visible_abandoned_rows ... ok
test agent_scan::index::tests::output_variable_projection_backfills_replaces_and_deletes_rows ... ok
test agent_scan::selector::tests::hidden_project_limit_and_ambiguity ... ok
test agent_scan::selector::tests::nested_paths_and_failures_are_precise ... ok
test telemetry::store::tests::retention_folds_through_both_rollup_tiers_before_deletion ... ok
test store_lock::tests::timeout_names_holder_and_does_not_materially_overshoot_deadline ... ok
test editor::completion::tests::commit_inventory_keeps_non_sidecar_repository_kinds ... ok
test telemetry::store::tests::exact_label_cleanup_previews_and_deletes_every_tier ... ok
test xprompt_catalog::tests::parses_xprompt_workflow_and_input_descriptions ... ok
test procs::store::tests::held_exclusive_lock_bounds_reader_and_writer_waits ... ok
test prompt_stash::store::tests::held_exclusive_lock_bounds_reader_and_writer_waits ... ok
test telemetry::store::tests::concurrent_writers_preserve_every_delta ... ok
test editor::completion::tests::commit_inventory_skips_sidecars_before_reporting_the_row_cap ... ok
test effort_override::tests::lock_wait_is_bounded ... ok
test editor::completion::tests::commit_log_reports_an_expired_budget_instead_of_empty_output ... ok
test provider_disable::tests::try_set_rejects_invalid_inputs_and_times_out_on_lock ... ok
test provider_disable::tests::lock_wait_is_bounded ... ok
test runner_limit_override::tests::lock_wait_is_bounded ... ok
test agent_scan::index::tests::stale_dismissed_suffixes_do_not_consume_active_limit ... ok
test store_lock::tests::waiter_acquires_after_more_than_the_old_two_second_bound ... ok

test result: ok. 1700 passed; 0 failed; 0 ignored; 0 measured; 0 filtered out; finished in 2.94s

     Running tests/agent_scan_parity.rs (target/debug/deps/agent_scan_parity-5d8a095921773469)

running 44 tests
test missing_root_returns_empty_snapshot ... ok
test explicit_agent_clan_preserves_sequential_family_fields ... ok
test absent_and_invalid_xprompts_are_soft_scan_errors ... ok
test launch_xprompts_preserves_swarm_kind ... ok
test launch_xprompts_project_to_deduplicated_deterministic_records ... ok
test scalar_agent_meta_timestamps_are_normalized_to_lists ... ok
test exact_dir_scan_returns_only_requested_valid_unique_dirs ... ok
test scanner_keeps_parent_epic_and_authored_plan_references_separate ... ok
test scanner_accepts_mixed_legacy_and_day_sharded_ace_run_dirs ... ok
test bounded_not_before_applies_to_completed_rows_only ... ok
test bounded_newest_first_limits_completed_without_hiding_incomplete ... ok
test exact_dir_scan_honors_project_and_workflow_filters ... ok
test malformed_agent_meta_is_skipped ... ok
test failed_record_carries_error_and_traceback ... ok
test max_prompt_snippet_bytes_truncates ... ok
test mentor_dir_is_walked ... ok
test options_round_trip_through_snapshot ... ok
test home_running_record_has_running_marker ... ok
test retried_records_link_via_lineage_fields ... ok
test repeat_stopped_record_parses_repeat_stop_fields ... ok
test pending_question_marker_is_absent_when_file_missing ... ok
test only_workflow_dirs_filters_records ... ok
test records_are_sorted_deterministically ... ok
test disable_prompt_step_markers ... ok
test disable_raw_prompt_snippet ... ok
test workflow_root_record_has_state_and_steps ... ok
test pending_question_marker_is_surfaced_when_present ... ok
test selective_marker_options_skip_payloads_but_keep_done_presence ... ok
test waiting_marker_decode_error_does_not_crash ... ok
test running_record_carries_agent_meta ... ok
test running_record_prefers_canonical_agent_meta_tribe ... ok
test stats_count_decode_errors ... ok
test scan_returns_one_record_per_artifact_dir ... ok
test running_record_carries_wait_completed_at ... ok
test done_record_parses_done_marker ... ok
test waiting_marker_carries_runner_slot_fields ... ok
test snapshot_serializes_to_json ... ok
test artifact_index_metadata_helpers_round_trip ... ok
test running_record_carries_bounded_json_output_variables ... ok
test artifact_index_status_counts_artifact_and_dismissed_rows ... ok
test plan_committed_survives_live_scan_and_indexed_reads ... ok
test running_record_carries_linked_repos_through_scan_and_index ... ok
test agent_family_parallel_survives_live_scan_and_indexed_reads ... ok
test workflow_state_hidden_is_parsed_and_indexed ... ok

test result: ok. 44 passed; 0 failed; 0 ignored; 0 measured; 0 filtered out; finished in 0.04s

     Running tests/artifact_ref_commit_budget.rs (target/debug/deps/artifact_ref_commit_budget-935899c6abf67b7e)

running 1 test
test commit_inventory_budget_override_controls_whether_rows_survive ... ok

test result: ok. 1 passed; 0 failed; 0 ignored; 0 measured; 0 filtered out; finished in 0.27s

     Running tests/bead_event_parity.rs (target/debug/deps/bead_event_parity-04840916c4602056)

running 35 tests
test close_event_stamps_an_issue_updated_to_closed_without_a_timestamp ... ok
test cross_stream_dependencies_resolve_after_all_creates ... ok
test dependency_remove_payload_rejects_a_source_mismatch ... ok
test dependency_add_remove_add_replays_to_present ... ok
test byte_identical_concurrent_note_append_merges_once ... ok
test dependency_remove_replay_tolerates_a_target_removed_first ... ok
test concurrent_note_appends_merge_without_losing_text ... ok
test concurrent_close_projection_is_independent_of_branch_order ... ok
test event_validation_rejects_operation_payload_mismatch ... ok
test dependency_remove_replay_is_tolerant_and_projection_round_trips ... ok
test every_transition_out_of_closed_starts_a_new_close_interval ... ok
test flag_validation_errors_reject_import ... ok
test flag_bead_create_update_and_close_reduce ... ok
test legacy_empty_timestamps_still_import_to_valid_events ... ok
test merge_event_stream_keeps_exact_duplicate_append_once ... ok
test merge_event_stream_rejects_deleted_or_rewritten_base_events ... ok
test merge_event_stream_accepts_interleaved_additions_and_preserves_ids ... ok
test merge_event_stream_orders_non_base_union_deterministically ... ok
test note_appended_composes_after_a_legacy_note_snapshot ... ok
test jsonl_import_to_events_reduces_to_byte_compatible_projection ... ok
test event_import_preserves_legacy_defaults_and_corrupt_jsonl_tolerance ... ok
test merge_event_stream_supports_sequential_rebase_replay ... ok
test note_appended_matches_legacy_note_rendering_and_composes ... ok
test merge_event_stream_union_is_associative_and_idempotent ... ok
test reduce_applies_merged_stream_events_in_recorded_order ... ok
test reducer_handles_current_mutation_operation_variants ... ok
test reducer_removes_plan_children_and_dependency_edges_on_cascade_remove ... ok
test redundant_close_keeps_the_first_close_projection ... ok
test same_timestamp_dependency_add_replays_before_remove_across_streams ... ok
test merge_event_stream_unions_concurrent_appends_deterministically ... ok
test event_import_mints_reproducible_content_hashed_ids ... ok
test task_plus_one_replay_honors_observation_window_freshness ... ok
test serialized_event_store_fixture_matches_import_and_reduces ... ok
test reduce_survives_many_merged_streams_with_non_monotonic_timestamps ... ok
test write_event_store_leaves_an_unrelated_streams_bytes_unchanged_across_a_mutation ... ok

test result: ok. 35 passed; 0 failed; 0 ignored; 0 measured; 0 filtered out; finished in 0.00s

     Running tests/bead_read_parity.rs (target/debug/deps/bead_read_parity-20039adf650ec0d0)

running 13 tests
test doctor_notes_explicitly_unavailable_plan_roots ... ok
test doctor_reports_orphan_nested_plan_records ... ok
test event_manifest_repair_refuses_invalid_canonical_streams ... ok
test doctor_reports_invalid_event_store_without_legacy_fallback ... ok
test issue_detail_preserves_unresolved_relationship_slots ... ok
test event_manifest_repair_refuses_unsupported_event_schema ... ok
test event_manifest_repair_recounts_missing_or_stale_metadata_idempotently ... ok
test doctor_reports_orphans_in_stale_legacy_projection ... ok
test doctor_reports_projection_fields_and_redundant_close_census ... ok
test event_store_wins_over_stale_legacy_projection ... ok
test event_store_supports_read_queries_without_legacy_projection ... ok
test doctor_groups_plan_reference_diagnostics_without_changing_compatibility ... ok
test read_queries_match_python_contract_ordering ... ok

test result: ok. 13 passed; 0 failed; 0 ignored; 0 measured; 0 filtered out; finished in 0.01s

     Running tests/bead_storage_parity.rs (target/debug/deps/bead_storage_parity-61c903642c384684)

running 8 tests
test corrupt_and_empty_fixtures_match_python_tolerance ... ok
test load_config_fixture_matches_python_shape ... ok
test current_schema_fixture_loads_hierarchy_dependencies_and_metadata ... ok
test import_missing_file_returns_empty_outcome ... ok
test export_current_fixture_is_byte_compatible ... ok
test legacy_jsonl_fixtures_get_python_defaults ... ok
test import_from_file_uses_same_parser ... ok
test task_and_ready_values_round_trip_with_python_wire_spelling ... ok

test result: ok. 8 passed; 0 failed; 0 ignored; 0 measured; 0 filtered out; finished in 0.00s

     Running tests/config_parity.rs (target/debug/deps/config_parity-a608e38ed9fa4e0c)

running 20 tests
test deep_merge_lists_replace_vs_concatenate ... ok
test axe_composition_overlays_wait_runners_with_exact_provenance ... ok
test axe_description_requirements_validate_only_the_merged_config ... ok
test axe_composition_reports_attributed_legacy_and_identity_diagnostics ... ok
test axe_composition_retains_legacy_defaults_and_exact_key_provenance ... ok
test field_model_flattens_nested_and_classifies ... ok
test inventory_diagnoses_glossary_outside_local_layer ... ok
test plan_edit_rejects_missing_empty_and_contradictory_paths ... ok
test plan_edit_exact_key_path_preserves_dotted_mapping_keys ... ok
test axe_mutation_promotes_target_legacy_list_without_dropping_entries ... ok
test plan_edit_unknown_target_errors ... ok
test plan_edit_set_builds_write_plan_and_preview ... ok
test merge_layers_matches_python_deep_merge_golden ... ok
test plan_edit_unset_removes_key_and_warns_on_readonly_target ... ok
test axe_entry_mutation_propagates_description_shape_to_diagnostics ... ok
test axe_entry_mutation_propagates_required_descriptions_to_preview ... ok
test axe_sparse_mutation_keeps_inherited_fields_and_matches_candidate_composition ... ok
test axe_inventory_marks_generated_instances_as_base_owned ... ok
test inventory_reports_effective_value_and_provenance ... ok
test validate_detects_violations ... ok

test result: ok. 20 passed; 0 failed; 0 ignored; 0 measured; 0 filtered out; finished in 0.00s

     Running tests/git_query_parity.rs (target/debug/deps/git_query_parity-bc24508a1816ee97)

running 33 tests
test derive_workspace_name_falls_back_to_root_path_when_remote_blank ... ok
test derive_workspace_name_falls_back_to_root_path_when_remote_none ... ok
test derive_workspace_name_https_remote_with_dot_git_suffix ... ok
test derive_workspace_name_https_remote_without_dot_git_suffix ... ok
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

     Running tests/golden_corpus_parity.rs (target/debug/deps/golden_corpus_parity-70f8384cf4ce1ee2)

running 3 tests
test archive_corpus_matches_python_golden_after_end_line_normalization ... ok
test rust_real_end_line_is_strictly_greater_than_python_placeholder ... ok
test project_corpus_matches_python_golden_after_end_line_normalization ... ok

test result: ok. 3 passed; 0 failed; 0 ignored; 0 measured; 0 filtered out; finished in 0.04s

     Running tests/notification_store_parity.rs (target/debug/deps/notification_store_parity-ca9a402c99e60ac8)

running 42 tests
test notification_activity_cursor_uses_resurface_time_and_id_tiebreaker ... ok
test notification_append_counts_returns_metadata_without_rows ... ok
test notification_append_and_rewrite_round_trip_jsonl ... ok
test notification_append_counts_produces_byte_identical_jsonl ... ok
test notification_bulk_snooze_uses_one_deadline_and_reports_counts ... ok
test notification_bulk_mute_deduplicates_ids_and_reports_counts ... ok
test notification_json_shape_uses_expected_wire_keys ... ok
test notification_counts_match_python_priority_rules ... ok
test notification_dismiss_agent_completions_no_op_when_already_dismissed ... ok
test notification_dismiss_matching_agents_covers_custom_gates ... ok
test notification_dismiss_matching_agents_matches_question_child_identity ... ok
test notification_missing_file_returns_empty_snapshot ... ok
test notification_loads_legacy_defaults_and_skips_bad_rows ... ok
test notification_dismiss_matching_agents_covers_user_agent_view_error_report ... ok
test notification_dismiss_agent_completions_matching_agents_is_completion_only ... ok
test notification_icon_round_trips_through_append_load_and_rewrite ... ok
test notification_bulk_unmute_cancels_snoozes_and_reports_counts ... ok
test notification_expire_snoozes_handles_aware_and_naive_timestamps ... ok
test notification_batch_dismiss_and_rewrite_all_update_the_store ... ok
test notification_rewrite_counts_returns_metadata_without_rows ... ok
test notification_mark_tab_read_uses_general_tab_for_untagged_rows ... ok
test notification_current_read_recovers_legacy_state_and_preserves_cancellations ... ok
test notification_rewrite_counts_preserves_unseen_rows ... ok
test notification_dismiss_matching_agents_covers_notification_action_shapes ... ok
test notification_mute_and_snooze_follow_python_semantics ... ok
test notification_phase1_contract_fixture_loads_with_expected_counts ... ok
test notification_dismiss_agent_completions_matches_user_agent_jump_and_error ... ok
test notification_rewrite_all_preserves_unseen_rows ... ok
test notification_rewrite_reaps_only_targeted_stale_temp_siblings ... ok
test notification_dismissal_cancels_snooze_without_resurfacing ... ok
test notification_rewrite_counts_produces_byte_identical_jsonl ... ok
test notification_state_update_counts_skips_returned_snapshot ... ok
test notification_tags_round_trip_through_append_load_and_rewrite ... ok
test notification_mark_tab_read_marks_only_unread_target_tab ... ok
test notification_dismiss_matching_agents_matches_question_root_identity ... ok
test notification_rewrite_preserves_unseen_rows ... ok
test notification_snooze_validation_is_atomic_and_skips_ineligible_targets ... ok
test notification_snooze_normalizes_offsets_and_projects_earliest_deadline ... ok
test notification_state_updates_mutate_only_intended_rows ... ok
test notification_concurrent_append_and_expiry_converge_on_one_transition ... ok
test notification_append_plus_rewrite_counts_concurrency_preserves_valid_rows ... ok
test notification_append_plus_rewrite_concurrency_preserves_valid_rows ... ok

test result: ok. 42 passed; 0 failed; 0 ignored; 0 measured; 0 filtered out; finished in 0.36s

     Running tests/plan_validate_parity.rs (target/debug/deps/plan_validate_parity-544aa60f0341d182)

running 1 test
test plan_validate_matches_python_facade_fixture ... ok

test result: ok. 1 passed; 0 failed; 0 ignored; 0 measured; 0 filtered out; finished in 0.00s

     Running tests/prompt_stash_store_parity.rs (target/debug/deps/prompt_stash_store_parity-19abcd560030503a)

running 9 tests
test prompt_stash_json_shape_uses_expected_wire_keys ... ok
test prompt_stash_missing_file_returns_empty_snapshot ... ok
test prompt_stash_append_and_read_round_trip ... ok
test prompt_stash_pop_unknown_ids_is_a_no_op ... ok
test prompt_stash_skips_blank_and_malformed_rows ... ok
test prompt_stash_pop_removes_only_requested_ids ... ok
test prompt_stash_rewrite_merges_and_preserves_unseen_rows ... ok
test prompt_stash_set_pinned_sets_and_clears_matching_ids ... ok
test prompt_stash_append_plus_pop_concurrency_preserves_valid_rows ... ok

test result: ok. 9 passed; 0 failed; 0 ignored; 0 measured; 0 filtered out; finished in 0.17s

     Running tests/python_wire_parity.rs (target/debug/deps/python_wire_parity-5a439ad6c93ef8bd)

running 11 tests
test agent_meta_clan_field_order_matches_python_wire ... ok
test bead_flag_enum_and_record_match_python_wire_values ... ok
test agent_meta_wait_priority_matches_python_wire_defaulting ... ok
test bead_task_and_ready_enum_values_match_python_wire_values ... ok
test agent_meta_parent_epic_plan_reference_round_trips ... ok
test cleanup_target_parallel_membership_matches_python_wire_defaulting ... ok
test agent_meta_parallel_membership_matches_python_wire_defaulting ... ok
test python_fixture_deserializes_into_rust_type ... ok
test proc_snapshot_json_uses_canonical_proc_keys ... ok
test legacy_task_snapshot_deserializes_and_reserializes_as_proc_shape ... ok
test rust_json_equals_python_fixture ... ok

test result: ok. 11 passed; 0 failed; 0 ignored; 0 measured; 0 filtered out; finished in 0.00s

     Running tests/query_evaluator_parity.rs (target/debug/deps/query_evaluator_parity-ccbd78623f1e113f)

running 17 tests
test ancestor_walk_avoids_cycles ... ok
test project_query_falls_back_to_directory_key_without_valid_metadata ... ok
test configured_project_name_replaces_directory_key_in_all_query_paths ... ok
test persistent_corpus_matches_golden_matrix_samples ... ok
test batch_evaluation_is_idempotent ... ok
test substring_semantics_not_regex ... ok
test persistent_corpus_reuses_derived_data_across_repeated_evaluations ... ok
test persistent_corpus_keeps_ancestor_memo_query_specific ... ok
test evaluation_matrix_escapes_are_literal ... ok
test batch_and_oneshot_agree ... ok
test evaluation_matrix_boolean_ops ... ok
test evaluation_matrix_quoted_strings ... ok
test evaluation_matrix_property_shorthands ... ok
test evaluation_matrix_status_shorthands ... ok
test evaluation_matrix_error_running_shorthands ... ok
test evaluation_matrix_property_filters ... ok
test explicit_patch_profile_matches_compatibility_golden_matrix ... ok

test result: ok. 17 passed; 0 failed; 0 ignored; 0 measured; 0 filtered out; finished in 0.08s

     Running tests/vcs_log_parity.rs (target/debug/deps/vcs_log_parity-66599f1d6923e042)

running 23 tests
test aggregate_empty_returns_empty ... ok
test aggregate_interleaves_by_timestamp_desc ... ok
test aggregate_tie_break_repo_then_full_id ... ok
test aggregate_truncates_to_limit ... ok
test aggregated_commit_wire_round_trips_through_json ... ok
test classify_commit_origin_distinguishes_auto_and_legacy_stitch ... ok
test classify_commit_origin_uses_terminal_type_footer ... ok
test aggregated_commit_wire_serializes_flat ... ok
test classify_commit_presence_marks_synced_local_and_remote ... ok
test parse_drops_record_with_bad_timestamp ... ok
test parse_drops_record_with_too_few_fields ... ok
test parse_empty_stream_returns_empty_list ... ok
test parse_legacy_single_commit_defaults_parent_ids ... ok
test parse_octopus_commit_parent_ids ... ok
test parse_multiline_body_preserved ... ok
test parse_root_commit_empty_parent_field ... ok
test parse_single_commit_all_fields ... ok
test parse_strips_newline_git_inserts_between_records ... ok
test parse_stitch_type_footer_sets_stitch_origin ... ok
test parse_trailing_record_separator_yields_no_blank ... ok
test vcs_commit_wire_defaults_presence_to_unknown ... ok
test vcs_log_wire_schema_version_is_four ... ok
test vcs_commit_wire_serializes_to_python_shape ... ok

test result: ok. 23 passed; 0 failed; 0 ignored; 0 measured; 0 filtered out; finished in 0.00s

     Running unittests src/lib.rs (target/debug/deps/sase_core_rs-ec156f17b502f0d4)

running 87 tests
test tests::indexed_at_reference_binding_stays_below_eight_ms_for_5000_rows ... ignored, the 8 ms performance gate is calibrated for release builds
test tests::classify_commit_origin_binding_returns_origin_string ... ok
test tests::apply_snippet_session_event_binding_drives_nesting_through_dicts ... ok
test tests::profile_binding_round_trips_compiled_profile_dict ... ok
test tests::chop_clan_contracts_round_trip_through_python_bindings ... ok
test tests::prompt_artifact_bindings_round_trip_manifest_shapes ... ok
test tests::bead_flag_bindings_round_trip_create_update_and_close ... ok
test tests::bead_plus_one_binding_exports_structured_atomic_result ... ok
test tests::agent_alias_history_binding_round_trips_python_dict ... ok
test tests::axe_description_split_round_trips_through_python_binding ... ok
test tests::profile_binding_rejects_invalid_profile_and_mismatch ... ok
test tests::provider_disable_binding_rejects_invalid_values ... ok
test tests::artifact_ref_payload_inventory_binding_returns_plain_json_shape ... ok
test tests::query_compile_errors_are_python_value_errors ... ok
test tests::provider_disable_try_set_bindings_report_first_writer ... ok
test tests::agent_output_variable_history_binding_round_trips_python_dict ... ok
test tests::axe_status_binding_returns_exact_plain_python_shape ... ok
test tests::bead_size_check_relax_bindings_are_exported_and_forward_core_policy ... ok
test tests::at_reference_bindings_return_plain_json_shapes ... ok
test tests::relationship_bindings_validate_and_rewrite_plain_dicts ... ok
test tests::sdd_artifact_link_bindings_match_core_contract ... ok
test tests::sdd_plan_header_block_bindings_match_core_contract ... ok
test tests::bead_doctor_binding_keeps_contexts_optional_and_marks_unavailable ... ok
test tests::required_axe_descriptions_round_trip_through_python_binding ... ok
test tests::runner_limit_override_binding_rejects_invalid_values ... ok
test tests::runner_limit_override_bindings_round_trip_and_replace ... ok
test tests::query_handles_evaluate_multiple_queries_against_one_corpus ... ok
test tests::task_type_spec_bindings_round_trip_validation_digest_and_snapshot ... ok
test tests::vcs_log_binding_exposes_schema_and_parent_ids ... ok
test tests::size_model_route_binding_maps_public_aliases ... ok
test tests::epic_land_model_binding_rejects_invalid_counts_and_thresholds ... ok
test tests::commit_subject_bindings_round_trip_wire_payload ... ok
test tests::notification_store_binding_rejects_bad_update_shape ... ok
test tests::size_model_route_binding_rejects_invalid_sizes ... ok
test tests::bead_update_many_binding_applies_batch_and_reports_unchanged ... ok
test tests::chop_overrun_binding_returns_exact_plain_python_shape ... ok
test tests::artifact_ref_filter_path_payloads_binding_returns_batch_shape ... ok
test tests::apply_snippet_session_event_binding_rejects_malformed_input ... ok
test tests::bead_merge_event_streams_binding_preserves_replay_stable_union ... ok
test tests::provider_disable_bindings_round_trip_and_replace ... ok
test tests::perf_logs_query_binding_round_trips_python_dict ... ok
test tests::agent_identity_bindings_are_exported_and_preserve_shapes ... ok
test tests::notification_store_append_and_rewrite_counts_bindings_omit_rows ... ok
test tests::profile_binding_evaluates_generic_rows ... ok
test tests::bead_manifest_repair_binding_round_trips_structured_outcome ... ok
test tests::memory_xprompt_bindings_expose_the_shared_contract ... ok
test tests::bead_snooze_bindings_round_trip_the_whole_lifecycle ... ok
test tests::notification_store_binding_round_trips_json_shape ... ok
test tests::artifact_file_query_binding_returns_full_rows_and_handshake ... ok
test tests::artifact_consumption_binding_returns_summary_and_handshake ... ok
test tests::compose_snippet_catalog_binding_returns_plain_dict_shape ... ok
test tests::notification_store_current_snapshot_binding_reconciles_snoozes ... ok
test tests::bead_mutation_bindings_preserve_changed_and_epic_preclaim ... ok
test tests::machine_hood_bindings_qualify_strip_and_classify ... ok
test tests::agent_stats_binding_round_trips_python_dict ... ok
test tests::legacy_query_handles_still_use_patch_profile ... ok
test tests::chop_agent_runners_contracts_round_trip_through_python_bindings ... ok
test tests::plan_reference_bindings_round_trip_json_shapes ... ok
test tests::parse_patch_project_bytes_binding_emits_canonical_shape_and_query_accepts_it ... ok
test tests::bead_search_binding_round_trips_json_shape ... ok
test tests::placeholder_bindings_return_plain_json_shapes ... ok
test tests::plan_agent_cleanup_binding_round_trips_json_shape ... ok
test tests::effort_override_binding_rejects_invalid_values ... ok
test tests::parse_merge_summary_binding_returns_dict_or_none ... ok
test tests::artifact_ref_contract_bindings_round_trip_json_shapes ... ok
test tests::axe_status_binding_maps_schema_structural_and_unknown_errors_to_value_error ... ok
test tests::bead_work_plan_binding_exposes_additive_bead_id_fields ... ok
test tests::bead_search_binding_accepts_regex_keyword ... ok
test tests::bead_remove_many_binding_is_exported_and_removes_multiple_roots ... ok
test tests::plan_agent_cleanup_binding_rejects_schema_mismatch ... ok
test tests::commit_footer_bindings_convert_linked_payloads ... ok
test tests::artifact_ref_bindings_round_trip_json_shapes ... ok
test tests::bead_create_binding_round_trips_task_type_and_fields ... ok
test tests::chop_overrun_binding_maps_schema_and_structural_errors_to_value_error ... ok
test tests::effort_override_bindings_round_trip_and_resolve ... ok
test tests::epic_land_model_binding_selects_explicit_then_threshold ... ok
test tests::notification_store_counts_binding_omits_rows_and_persists ... ok
test tests::proc_store_bindings_round_trip_python_dicts_and_legacy_aliases ... ok
test tests::inline_code_binding_returns_plain_byte_offset_tuples ... ok
test tests::plan_search_binding_accepts_explicit_document_corpora ... ok
test tests::query_handles_evaluate_one_query_against_multiple_corpora ... ok
test tests::query_handles_match_legacy_one_shot_results ... ok
test tests::agent_activity_stats_binding_round_trips_python_dict ... ok
test tests::query_handle_bindings_reject_wrong_handle_types ... ok
test tests::artifact_file_lifecycle_bindings_round_trip_plain_python_shapes ... ok
test tests::telemetry_bindings_round_trip_python_dicts ... ok
test tests::plan_validation_bindings_round_trip_json_shapes ... ok

test result: ok. 86 passed; 0 failed; 1 ignored; 0 measured; 0 filtered out; finished in 0.23s

     Running unittests src/lib.rs (target/debug/deps/sase_gateway-fdf46efa768907b7)

running 79 tests
test daemon::tests::daemon_host_identity_is_path_safe ... ok
test daemon::tests::daemon_mobile_bind_policy_is_skipped_when_mobile_http_disabled ... ok
test daemon::tests::daemon_default_paths_are_host_local_under_sase_home ... ok
test daemon::tests::daemon_run_root_override_drives_default_socket_path ... ok
test daemon::tests::daemon_socket_path_override_is_preserved ... ok
test push::tests::fcm_payload_contains_hint_only_data ... ok
test routes::tests::helper_host_bridge_errors_map_to_stable_api_codes ... ok
test server::tests::default_bind_is_loopback ... ok
test server::tests::explicit_non_loopback_opt_in_is_allowed ... ok
test server::tests::non_loopback_bind_requires_explicit_opt_in ... ok
test wire::tests::event_wire_json_snapshot ... ok
test wire::tests::error_wire_json_snapshot ... ok
test wire::tests::health_wire_json_snapshot ... ok
test wire::tests::mobile_xprompt_catalog_entry_deserializes_legacy_shape ... ok
test wire::tests::mobile_agent_wire_json_snapshot ... ok
test wire::tests::pairing_wire_json_snapshot ... ok
test wire::tests::push_hint_mapping_uses_safe_event_projection ... ok
test wire::tests::push_subscription_wire_json_snapshot ... ok
test wire::tests::session_wire_json_snapshot ... ok
test wire::tests::mobile_helper_wire_json_snapshot ... ok
test contract::tests::committed_contract_snapshot_is_current ... ok
test routes::tests::agents_without_token_returns_typed_unauthorized_error ... ok
test storage::tests::push_subscription_register_update_and_revoke_is_atomic ... ok
test routes::tests::command_helper_bridge_changespec_tags_returns_command_output ... ok
test routes::tests::event_resume_replays_buffered_records_after_last_event_id ... ok
test routes::tests::events_without_token_returns_typed_unauthorized_error ... ok
test routes::tests::session_without_token_returns_typed_unauthorized_error ... ok
test routes::tests::health_route_returns_stable_record ... ok
test routes::tests::unknown_route_returns_typed_not_found_error ... ok
test storage::tests::token_pairing_persists_only_hash ... ok
test routes::tests::notification_state_mutation_without_token_returns_typed_unauthorized_error ... ok
test routes::tests::push_subscriptions_require_auth ... ok
test routes::tests::action_artifacts_are_declared_as_attachments ... ok
test routes::tests::pair_start_returns_short_lived_code_without_token ... ok
test routes::tests::unsafe_or_oversized_attachments_do_not_receive_tokens ... ok
test server::tests::listener_serves_health_over_http ... ok
test routes::tests::expired_attachment_tokens_return_typed_error ... ok
test routes::tests::command_helper_bridge_not_found_maps_to_helper_not_found ... ok
test routes::tests::invalid_and_revoked_tokens_are_unauthorized ... ok
test routes::tests::events_with_token_returns_sse_response ... ok
test routes::tests::command_helper_bridge_update_start_returns_command_output ... ok
test routes::tests::command_helper_bridge_malformed_json_maps_to_unavailable ... ok
test routes::tests::notification_detail_not_found_returns_typed_error ... ok
test routes::tests::command_helper_bridge_exit_failure_maps_to_unavailable ... ok
test routes::tests::command_helper_bridge_update_status_returns_command_output ... ok
test routes::tests::notifications_list_uses_host_action_state ... ok
test routes::tests::notification_mark_read_updates_store_and_audits ... ok
test routes::tests::notifications_list_filters_and_orders_newest_first ... ok
test routes::tests::question_action_forwards_specialized_submission ... ok
test routes::tests::pair_finish_rejects_expired_code ... ok
test push::tests::fcm_provider_posts_expected_http_v1_shape ... ok
test routes::tests::event_resume_after_restart_returns_resync_required ... ok
test routes::tests::notification_detail_returns_notes_action_and_attachments ... ok
test routes::tests::production_agent_bridge_returns_typed_unavailable_error ... ok
test routes::tests::test_push_provider_records_hint_attempts ... ok
test routes::tests::notifications_list_expiry_publishes_activity_cursor_event ... ok
test routes::tests::helper_routes_without_token_return_typed_unauthorized_errors ... ok
test routes::tests::attachment_download_requires_gateway_auth ... ok
test routes::tests::notifications_without_token_returns_typed_unauthorized_error ... ok
test routes::tests::command_helper_bridge_xprompt_catalog_returns_new_helper_fields ... ok
test server::tests::listener_smoke_exercises_pairing_auth_and_session ... ok
test routes::tests::notifications_list_can_include_dismissed_and_silent_rows ... ok
test routes::tests::push_subscription_duplicate_updates_existing_record ... ok
test routes::tests::command_helper_bridge_update_exit_codes_map_to_stable_errors ... ok
test routes::tests::notification_dismiss_updates_store_and_emits_refresh_event ... ok
test routes::tests::notifications_list_uses_resurface_activity_cursor_and_id_tiebreaker ... ok
test routes::tests::attachment_tokens_are_bound_to_device ... ok
test routes::tests::event_resume_outside_buffer_returns_resync_required ... ok
test routes::tests::fake_agent_bridge_routes_return_stable_success_shapes ... ok
test routes::tests::gate_action_forwards_selected_option_submission ... ok
test routes::tests::notification_detail_mints_short_lived_download_tokens ... ok
test routes::tests::pair_finish_persists_device_and_returns_token_once ... ok
test routes::tests::session_returns_authenticated_device ... ok
test routes::tests::notification_state_mutation_not_found_returns_typed_error ... ok
test routes::tests::push_subscription_validation_and_audit_do_not_leak_provider_token ... ok
test routes::tests::production_helper_bridge_returns_typed_unavailable_error ... ok
test routes::tests::push_subscription_register_list_and_revoke_round_trip ... ok
test routes::tests::fake_helper_bridge_routes_return_stable_success_shapes ... ok
test routes::tests::command_agent_bridge_routes_return_command_output ... ok

test result: ok. 79 passed; 0 failed; 0 ignored; 0 measured; 0 filtered out; finished in 0.11s

     Running unittests src/main.rs (target/debug/deps/sase_gateway-e631b0e85fe443a5)

running 8 tests
test tests::parse_agent_bridge_command_short_flag ... ok
test tests::parse_bind_short_flag ... ok
test tests::parse_allow_non_loopback_short_flag ... ok
test tests::parse_bind_long_flag ... ok
test tests::parse_contract_out_short_flag ... ok
test tests::parse_helper_bridge_command_short_flag ... ok
test tests::parse_push_flags ... ok
test tests::parse_sase_home_short_flag ... ok

test result: ok. 8 passed; 0 failed; 0 ignored; 0 measured; 0 filtered out; finished in 0.00s

     Running unittests src/lib.rs (target/debug/deps/sase_xprompt_lsp-b881f1a61a665981)

running 98 tests
test lsp_convert::tests::agent_completion_items_render_distinct_kinds_and_stable_sort_groups ... ok
test lsp_convert::tests::at_reference_kind_stage_items_filter_on_the_bare_typed_word ... ok
test lsp_convert::tests::at_reference_items_filter_on_the_typed_text_and_preview_the_match ... ok
test catalog_cache::tests::snippet_cache_refreshes_from_helper ... ok
test catalog_cache::tests::vcs_repo_cache_refreshes_from_helper ... ok
test catalog_cache::tests::vcs_repo_cache_returns_stale_response_on_helper_failure ... ok
test catalog_cache::tests::snippet_cache_returns_stale_entries_on_helper_failure ... ok
test lsp_convert::tests::commit_documentation_omits_the_body_block_when_empty ... ok
test lsp_convert::tests::completion_item_uses_replacement_text_edit ... ok
test lsp_convert::tests::converts_editor_range_to_lsp_range ... ok
test lsp_convert::tests::commit_documentation_truncates_a_long_body_to_a_bounded_line_count ... ok
test lsp_convert::tests::model_completion_items_render_provider_label_and_trailing_sort_group ... ok
test lsp_convert::tests::converts_sase_snippet_template_to_lsp_snippet_syntax ... ok
test lsp_convert::tests::commit_payload_rows_render_as_references_with_body_in_documentation ... ok
test lsp_convert::tests::placeholder_tabstop_snippet_retriggers_completion ... ok
test server::tests::artifact_catalog_loader_is_tolerant_and_schema_gated ... ok
test server::tests::catalog_invalidation_tracks_xprompt_source_dirs ... ok
test server::tests::advertises_vcs_ref_completion_trigger_characters ... ok
test server::tests::advertises_placeholder_completion_trigger_character ... ok
test server::tests::advertises_full_semantic_tokens_with_standard_legend ... ok
test server::tests::advertises_at_reference_completion_trigger_character ... ok
test server::tests::advertises_slash_completion_trigger_character ... ok
test server::tests::advertises_plus_completion_trigger_character ... ok
test server::tests::detects_snippet_support_from_client_capabilities ... ok
test server::tests::directive_snippet_for_alt_uses_brace_shorthand ... ok
test server::tests::document_eligibility_narrows_plain_markdown ... ok
test server::tests::completes_placeholders_from_the_current_document ... ok
test server::tests::completes_identity_and_clan_from_the_public_editor_surface ... ok
test semantic_tokens::tests::glossary_tokens_split_wrapped_segments_and_keep_artifacts ... ok
test server::tests::loads_v3_vcs_project_catalog_namespaces ... ok
test server::tests::placeholder_tabstop_snippet_item_retriggers_suggestions ... ok
test server::tests::identity_and_clan_editor_surfaces_use_current_metadata ... ok
test server::tests::wait_completion_uses_kind_aware_agent_catalog ... ok
test server::tests::xprompt_snippet_completion_returns_one_row_per_match ... ok
test server::tests::xprompt_snippet_completions_use_single_row_skeletons ... ok
test server::tests::load_model_catalog_rejects_unknown_schema ... ok
test server::tests::placeholder_completion_is_empty_without_another_span ... ok
test server::tests::placeholder_completion_appends_a_missing_closing_bracket ... ok
test server::tests::completes_model_directive_values_from_catalog ... ok
test server::tests::model_directive_completion_without_catalog_is_empty ... ok
test server::tests::completes_vcs_repo_with_ranked_items_and_text_edit ... ok
test server::tests::diagnostics_for_uri_text_honors_canonical_memory_file_uri ... ok
test server::tests::vcs_ref_completion_accepts_v2_catalog_without_namespaces ... ok
test server::tests::fuzzy_at_reference_payloads_survive_client_filtering ... ok
test server::tests::exposes_hover_diagnostics_code_actions_and_definition ... ok
test server::tests::vcs_ref_completion_filters_aliases_and_namespaces ... ok
test server::tests::bare_trigger_snippet_completion_uses_snippet_items ... ok
test server::tests::vcs_ref_completion_ignores_malformed_namespaces ... ok
test server::tests::completes_xprompt_from_static_catalog ... ok
test server::tests::loads_v1_vcs_project_catalog_with_project_defaults ... ok
test server::tests::loads_v4_vcs_project_catalog_with_patch_entry_kind ... ok
test server::tests::completes_grouped_at_references_from_the_client_root ... ok
test server::tests::load_vcs_project_catalog_ignores_malformed_namespaces ... ok
test server::tests::load_vcs_project_catalog_rejects_unknown_schema ... ok
test server::tests::completes_vcs_ref_from_v3_catalog ... ok
test server::tests::stale_v1_alias_catalog_still_produces_items ... ok
test server::tests::definition_uses_definition_path_outside_workspace_root ... ok
test server::tests::bare_trigger_snippets_require_client_snippet_support ... ok
test server::tests::model_directive_completion_filters_by_alias_hint ... ok
test server::tests::enriched_model_catalog_renders_alias_detail_and_metadata ... ok
test server::tests::obsolete_and_unspaced_plus_forms_do_not_complete_vcs_projects ... ok
test server::tests::completes_artifact_kinds_and_local_payloads_per_active_project ... ok
test server::tests::artifact_completion_discloses_the_display_cap ... ok
test server::tests::encodes_known_artifact_refs_and_skips_unknown_and_literal_tokens ... ok
test server::tests::artifact_payload_inventory_cache_rebuilds_on_all_invalidation_paths ... ok
test server::tests::model_at_suffix_still_completes_effort_vocabulary ... ok
test server::tests::definition_returns_none_for_pseudo_or_missing_sources ... ok
test server::tests::provider_scoped_model_directive_completion_matches_short_alias ... ok
test server::tests::completes_directive_argument_values ... ok
test server::tests::vcs_ref_owner_slash_still_uses_repo_completion ... ok
test server::tests::directive_keyword_completion_uses_the_active_fragment_range ... ok
test server::tests::provider_scoped_model_directive_completion_returns_qualified_rows ... ok
test server::tests::diagnostics_for_uri_text_accepts_markdown_local_xprompts ... ok
test server::tests::completes_vcs_patch_with_pr_label_details ... ok
test server::tests::completes_vcs_project_replacing_existing_tag_at_eof ... ok
test server::tests::malformed_glossary_catalog_degrades_to_no_semantics ... ok
test catalog_cache::tests::snippet_cache_uses_rust_fallback_when_helper_unavailable ... ok
test server::tests::completes_vcs_project_with_primary_and_additional_edits ... ok
test server::tests::appends_known_kind_artifact_diagnostics_from_active_catalog ... ok
test server::tests::required_text_skeleton_keeps_double_colon_before_existing_text ... ok
test server::tests::removed_identity_directives_do_not_complete ... ok
test server::tests::leading_at_filters_model_completion_to_aliases ... ok
test server::tests::vcs_repo_completion_error_response_is_empty ... ok
test server::tests::provider_scope_requires_provider_catalog_entry_for_old_catalogs ... ok
test server::tests::space_delimited_plus_completes_vcs_project ... ok
test server::tests::vcs_project_completion_without_catalog_is_empty ... ok
test server::tests::definition_preserves_catalog_definition_range ... ok
test server::tests::provider_scoped_model_directive_completion_uses_first_slash ... ok
test server::tests::snippet_clients_receive_identity_and_clan_forms ... ok
test server::tests::bare_plus_at_bof_completes_vcs_project ... ok
test server::tests::encodes_glossary_tokens_by_active_project_without_overlaps ... ok
test server::tests::completes_commit_payloads_from_a_real_git_checkout ... ok
test server::tests::automatic_and_manual_space_plus_completion_match ... ok
test server::tests::glossary_hover_and_definition_use_source_ranges ... ok
test catalog_cache::tests::direct_launch_without_plugin_metadata_merges_helper_and_rust_catalogs ... ok
test catalog_cache::tests::wrapper_launch_with_plugin_metadata_uses_fast_rust_catalog ... ok
test catalog_cache::tests::direct_launch_keeps_rust_catalog_when_helper_unavailable ... ok
test catalog_cache::tests::vcs_repo_cache_reports_helper_timeout ... ok

test result: ok. 98 passed; 0 failed; 0 ignored; 0 measured; 0 filtered out; finished in 0.20s

     Running unittests src/main.rs (target/debug/deps/sase_xprompt_lsp-6be5469ae5c3ea67)

running 0 tests

test result: ok. 0 passed; 0 failed; 0 ignored; 0 measured; 0 filtered out; finished in 0.00s

     Running tests/jsonrpc_stdio.rs (target/debug/deps/jsonrpc_stdio-7cbf1c24b522da38)

running 6 tests
test stdio_jsonrpc_unsupported_markdown_has_no_xprompt_behavior ... ok
test stdio_jsonrpc_placeholder_completion_uses_open_document_text ... ok
test stdio_jsonrpc_frontmatter_diagnostics ... ok
test stdio_jsonrpc_bare_snippet_completion ... ok
test stdio_jsonrpc_initialize_and_completion ... ok
test stdio_jsonrpc_id_kwargs_diagnostics_completion_and_snippets ... ok

test result: ok. 6 passed; 0 failed; 0 ignored; 0 measured; 0 filtered out; finished in 0.02s

   Doc-tests sase_core

running 0 tests

test result: ok. 0 passed; 0 failed; 0 ignored; 0 measured; 0 filtered out; finished in 0.00s

   Doc-tests sase_core_rs

running 0 tests

test result: ok. 0 passed; 0 failed; 0 ignored; 0 measured; 0 filtered out; finished in 0.00s

   Doc-tests sase_gateway

running 0 tests

test result: ok. 0 passed; 0 failed; 0 ignored; 0 measured; 0 filtered out; finished in 0.00s

   Doc-tests sase_xprompt_lsp

running 0 tests

test result: ok. 0 passed; 0 failed; 0 ignored; 0 measured; 0 filtered out; finished in 0.00s

[validate_sase_core_rs_version] sase-core checkout is ahead of sase's compatibility window: source version 0.28.0 from /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/sase/repos/linked/sase-core/Cargo.toml does not satisfy `sase`'s `sase-core-rs>=0.27.18,<0.28.0` dependency in pyproject.toml. No action is needed: editable installs build from the checkout regardless, and `tools/ratchet_core_window` moves the published window on the release branch at release time.
[setup] Note: the sase-core checkout is ahead of the published sase-core-rs window in pyproject.toml; dev installs build from /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/sase/repos/linked/sase-core regardless. This is normal — the release-branch reconciler ratchets the published window at release time, so no action is needed here.
.venv/bin/python tools/setup_required_plugins
[setup] Installing required plugin sase-github>=0.2.5.
[setup] Installing required plugin sase-research-artifacts.
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
✗ lint (symvision)
[validate_sase_core_rs_version] sase-core checkout is ahead of sase's compatibility window: source version 0.28.0 from /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/sase/repos/linked/sase-core/Cargo.toml does not satisfy `sase`'s `sase-core-rs>=0.27.18,<0.28.0` dependency in pyproject.toml. No action is needed: editable installs build from the checkout regardless, and `tools/ratchet_core_window` moves the published window on the release branch at release time.
[setup] Note: the sase-core checkout is ahead of the published sase-core-rs window in pyproject.toml; dev installs build from /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/sase/repos/linked/sase-core regardless. This is normal — the release-branch reconciler ratchets the published window at release time, so no action is needed here.
.venv/bin/python tools/setup_required_plugins
[setup] Installing required plugin sase-github>=0.2.5.
[setup] Installing required plugin sase-research-artifacts.
SASE_SYMVISION_BEAD_STATUS_ONLY=1 BD_COMMAND=tools/sase_bead .venv/bin/symvision src/sase --exclude-decorator gate_command_entrypoint --exclude-decorator builtin_chop --epic-symbol "sase-n4.5(ProviderDisableWriteOutcome)" --epic-symbol "sase-n4(UsageLimitSettings)" --epic-symbol "sase-n4(find_matching_pattern)" --epic-symbol "sase-n4(get_usage_limit_config)" --epic-symbol "sase-n4(is_usage_limit_error)" --epic-symbol "sase-n4(normalize_for_match)" --epic-symbol "sase-n4(parse_reset_hint)" --epic-symbol "sase-pq.5(TaskTypeGateDisplay)" --epic-symbol "sase-pq.5(parse_task_type_gate_display)" --epic-symbol "sase-pq.5(resolve_task_type_gate_display)" --epic-symbol "sase-pq.5(task_type_gate_chip)" --epic-symbol "sase-pq.5(task_type_gate_display_payload)" --epic-symbol "sase-pq.5(task_type_gate_markdown_fact)" --epic-symbol "sase-pq.5(task_type_gate_note)" 
Error: --epic-symbol 'sase-pq.5(TaskTypeGateDisplay)': bead 'sase-pq.5' is closed. Remove this stale --epic-symbol entry and clean up the symbol.
Error: --epic-symbol 'sase-pq.5(parse_task_type_gate_display)': bead 'sase-pq.5' is closed. Remove this stale --epic-symbol entry and clean up the symbol.
Error: --epic-symbol 'sase-pq.5(resolve_task_type_gate_display)': bead 'sase-pq.5' is closed. Remove this stale --epic-symbol entry and clean up the symbol.
Error: --epic-symbol 'sase-pq.5(task_type_gate_chip)': bead 'sase-pq.5' is closed. Remove this stale --epic-symbol entry and clean up the symbol.
Error: --epic-symbol 'sase-pq.5(task_type_gate_display_payload)': bead 'sase-pq.5' is closed. Remove this stale --epic-symbol entry and clean up the symbol.
Error: --epic-symbol 'sase-pq.5(task_type_gate_markdown_fact)': bead 'sase-pq.5' is closed. Remove this stale --epic-symbol entry and clean up the symbol.
Error: --epic-symbol 'sase-pq.5(task_type_gate_note)': bead 'sase-pq.5' is closed. Remove this stale --epic-symbol entry and clean up the symbol.
error: recipe `_lint-symvision` failed on line 349 with exit code 1
error: recipe `check-full` failed on line 658 with exit code 1

