# Chat History - ace-run (sase-1t0.1--mon)

- **TIMESTAMP:** 2026-11-15 12:59:56 EST
- **MODEL:** codex/gpt-6-luna
- **AGENT:** sase-1t0.1--mon

## Prompt

sase monitor start --command 'just install-venv' --reason 'Install the workspace venv with the changed local sase-core binding for retention verification'

## Response

sase: running unwrapped (no profile (monitor.tool_wrap is verify))
[install-venv] Installing local sase_core_rs from /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/sase/repos/linked/sase-core for local dev.
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
🐍 Found CPython 3.14 at /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/.venv/bin/python
🔗 Found pyo3 bindings with abi3-py3.12 support
📡 Using build options features from pyproject.toml
   Compiling proc-macro2 v1.0.106
   Compiling quote v1.0.45
   Compiling unicode-ident v1.0.24
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
   Compiling bytes v1.11.1
   Compiling regex-syntax v0.8.10
   Compiling log v0.4.29
   Compiling serde v1.0.228
   Compiling siphasher v1.0.4
   Compiling zmij v1.0.21
   Compiling version_check v0.9.5
   Compiling futures-core v0.3.32
   Compiling crossbeam-epoch v0.9.21
   Compiling smallvec v1.15.1
   Compiling serde_json v1.0.149
   Compiling crossbeam-deque v0.8.8
   Compiling stable_deref_trait v1.2.1
   Compiling futures-sink v0.3.32
   Compiling target-lexicon v0.12.16
   Compiling equivalent v1.0.2
   Compiling hashbrown v0.17.0
   Compiling slab v0.4.12
   Compiling ucd-trie v0.1.7
   Compiling tower-service v0.3.3
   Compiling futures-task v0.3.32
   Compiling iana-time-zone v0.1.65
   Compiling futures-io v0.3.32
   Compiling bitflags v2.11.1
   Compiling litemap v0.8.2
   Compiling writeable v0.6.3
   Compiling httparse v1.10.1
   Compiling untrusted v0.9.0
   Compiling heck v0.5.0
   Compiling same-file v1.0.6
   Compiling libm v0.2.16
   Compiling icu_normalizer_data v2.2.0
   Compiling typenum v1.20.0
   Compiling utf8_iter v1.0.4
   Compiling icu_properties_data v2.2.0
   Compiling deunicode v1.6.2
   Compiling fnv v1.0.7
   Compiling httpdate v1.0.3
   Compiling lazy_static v1.5.0
   Compiling tower-layer v0.3.3
sccache: warning: The server looks like it shut down unexpectedly, compiling locally instead
sccache: warning: The server looks like it shut down unexpectedly, compiling locally instead
sccache: warning: The server looks like it shut down unexpectedly, compiling locally instead
sccache: warning: The server looks like it shut down unexpectedly, compiling locally instead
sccache: warning: The server looks like it shut down unexpectedly, compiling locally instead
sccache: warning: The server looks like it shut down unexpectedly, compiling locally instead
sccache: warning: The server looks like it shut down unexpectedly, compiling locally instead
sccache: warning: The server looks like it shut down unexpectedly, compiling locally instead
sccache: warning: The server looks like it shut down unexpectedly, compiling locally instead
sccache: warning: The server looks like it shut down unexpectedly, compiling locally instead
sccache: warning: The server looks like it shut down unexpectedly, compiling locally instead
sccache: warning: The server looks like it shut down unexpectedly, compiling locally instead
sccache: warning: The server looks like it shut down unexpectedly, compiling locally instead
sccache: warning: The server looks like it shut down unexpectedly, compiling locally instead
sccache: warning: The server looks like it shut down unexpectedly, compiling locally instead
sccache: warning: The server looks like it shut down unexpectedly, compiling locally instead
sccache: warning: The server looks like it shut down unexpectedly, compiling locally instead
sccache: warning: The server looks like it shut down unexpectedly, compiling locally instead
sccache: warning: The server looks like it shut down unexpectedly, compiling locally instead
sccache: warning: The server looks like it shut down unexpectedly, compiling locally instead
sccache: warning: The server looks like it shut down unexpectedly, compiling locally instead
sccache: warning: The server looks like it shut down unexpectedly, compiling locally instead
sccache: warning: The server looks like it shut down unexpectedly, compiling locally instead
sccache: warning: The server looks like it shut down unexpectedly, compiling locally instead
sccache: warning: The server looks like it shut down unexpectedly, compiling locally instead
sccache: warning: The server looks like it shut down unexpectedly, compiling locally instead
sccache: warning: The server looks like it shut down unexpectedly, compiling locally instead
sccache: warning: The server looks like it shut down unexpectedly, compiling locally instead
sccache: warning: The server looks like it shut down unexpectedly, compiling locally instead
sccache: warning: The server looks like it shut down unexpectedly, compiling locally instead
sccache: warning: The server looks like it shut down unexpectedly, compiling locally instead
sccache: warning: The server looks like it shut down unexpectedly, compiling locally instead
sccache: warning: The server looks like it shut down unexpectedly, compiling locally instead
sccache: warning: The server looks like it shut down unexpectedly, compiling locally instead
sccache: warning: The server looks like it shut down unexpectedly, compiling locally instead
sccache: warning: The server looks like it shut down unexpectedly, compiling locally instead
sccache: warning: The server looks like it shut down unexpectedly, compiling locally instead
sccache: warning: The server looks like it shut down unexpectedly, compiling locally instead
sccache: warning: The server looks like it shut down unexpectedly, compiling locally instead
sccache: warning: The server looks like it shut down unexpectedly, compiling locally instead
sccache: warning: The server looks like it shut down unexpectedly, compiling locally instead
sccache: warning: The server looks like it shut down unexpectedly, compiling locally instead
sccache: warning: The server looks like it shut down unexpectedly, compiling locally instead
sccache: warning: The server looks like it shut down unexpectedly, compiling locally instead
sccache: warning: The server looks like it shut down unexpectedly, compiling locally instead
sccache: warning: The server looks like it shut down unexpectedly, compiling locally instead
sccache: warning: The server looks like it shut down unexpectedly, compiling locally instead
sccache: warning: The server looks like it shut down unexpectedly, compiling locally instead
sccache: warning: The server looks like it shut down unexpectedly, compiling locally instead
sccache: warning: The server looks like it shut down unexpectedly, compiling locally instead
sccache: error: failed to execute compile
sccache: caused by: Failed to send data to or receive data from server
sccache: caused by: Failed to read response header
sccache: caused by: failed to fill whole buffer
sccache: warning: The server looks like it shut down unexpectedly, compiling locally instead
error: could not compile `crossbeam-utils` (lib)

Caused by:
  process didn't exit successfully: `/home/bryan/bin/sase-rustc-wrapper /home/bryan/.rustup/toolchains/stable-x86_64-unknown-linux-gnu/bin/rustc --crate-name crossbeam_utils --edition=2021 /home/bryan/.cargo/registry/src/index.crates.io-1949cf8c6b5b557f/crossbeam-utils-0.8.21/src/lib.rs --error-format=json --json=diagnostic-rendered-ansi,artifacts,future-incompat,unused-externs-silent --crate-type lib --emit=dep-info,metadata,link -C opt-level=3 -C linker-plugin-lto -C codegen-units=1 --cfg 'feature="default"' --cfg 'feature="std"' --check-cfg 'cfg(docsrs,test)' --check-cfg 'cfg(feature, values("default", "loom", "nightly", "std"))' -C metadata=e9dde37a070c6c69 -C extra-filename=-177fc169687a71d4 --out-dir /home/bryan/.cache/sase/tmp/cargo-targets/gh_sase-org__sase-ws16-261115_123045/build/release/build/crossbeam-utils/177fc169687a71d4/out -C strip=debuginfo --cap-lints allow --force-warn=unused_crate_dependencies --check-cfg 'cfg(crossbeam_no_atomic,crossbeam_sanitize_thread)'` (exit status: 2)
warning: build failed, waiting for other jobs to finish...
sccache: error: failed to execute compile
sccache: caused by: Failed to send data to or receive data from server
sccache: caused by: Failed to read response header
sccache: caused by: failed to fill whole buffer
error: could not compile `serde_core` (lib)

Caused by:
  process didn't exit successfully: `/home/bryan/bin/sase-rustc-wrapper /home/bryan/.rustup/toolchains/stable-x86_64-unknown-linux-gnu/bin/rustc --crate-name serde_core --edition=2021 /home/bryan/.cargo/registry/src/index.crates.io-1949cf8c6b5b557f/serde_core-1.0.228/src/lib.rs --error-format=json --json=diagnostic-rendered-ansi,artifacts,future-incompat,unused-externs-silent --crate-type lib --emit=dep-info,metadata,link -C embed-bitcode=no -C debug-assertions=off --cfg 'feature="alloc"' --cfg 'feature="rc"' --cfg 'feature="result"' --cfg 'feature="std"' --check-cfg 'cfg(docsrs,test)' --check-cfg 'cfg(feature, values("alloc", "default", "rc", "result", "std", "unstable"))' -C metadata=01bc79776aabd735 -C extra-filename=-f0b5d462e5fe2aa2 --out-dir /home/bryan/.cache/sase/tmp/cargo-targets/gh_sase-org__sase-ws16-261115_123045/build/release/build/serde_core/f0b5d462e5fe2aa2/out -C strip=debuginfo --cap-lints allow --force-warn=unused_crate_dependencies --check-cfg 'cfg(if_docsrs_then_no_serde_core)' --check-cfg 'cfg(no_core_cstr)' --check-cfg 'cfg(no_core_error)' --check-cfg 'cfg(no_core_net)' --check-cfg 'cfg(no_core_num_saturating)' --check-cfg 'cfg(no_diagnostic_namespace)' --check-cfg 'cfg(no_serde_derive)' --check-cfg 'cfg(no_std_atomic)' --check-cfg 'cfg(no_std_atomic64)' --check-cfg 'cfg(no_target_has_atomic)'` (exit status: 2)
sccache: error: failed to execute compile
sccache: error: failed to execute compile
sccache: caused by: Failed to send data to or receive data from server
sccache: caused by: Failed to read response header
sccache: caused by: failed to fill whole buffer
error: failed to run custom build command for `libc v0.2.186`

Caused by:
  process didn't exit successfully: `/home/bryan/.cache/sase/tmp/cargo-targets/gh_sase-org__sase-ws16-261115_123045/build/release/build/libc/4f863fbb5c88aad9/out/build_script_build` (exit status: 101)
  --- stdout
  cargo:rerun-if-changed=build.rs

  --- stderr

  thread 'main' (2164685) panicked at /home/bryan/.cargo/registry/src/index.crates.io-1949cf8c6b5b557f/libc-0.2.186/build.rs:219:5:
  failed to run rustc: sccache: error: failed to execute compile
  sccache: caused by: Failed to send data to or receive data from server
  sccache: caused by: Failed to read response header
  sccache: caused by: failed to fill whole buffer

  note: run with `RUST_BACKTRACE=1` environment variable to display a backtrace
sccache: caused by: Failed to send data to or receive data from server
sccache: caused by: Failed to read response header
sccache: caused by: failed to fill whole buffer
error: could not compile `httparse` (build script)

Caused by:
  process didn't exit successfully: `/home/bryan/bin/sase-rustc-wrapper /home/bryan/.rustup/toolchains/stable-x86_64-unknown-linux-gnu/bin/rustc --crate-name build_script_build --edition=2018 /home/bryan/.cargo/registry/src/index.crates.io-1949cf8c6b5b557f/httparse-1.10.1/build.rs --error-format=json --json=diagnostic-rendered-ansi,artifacts,future-incompat,unused-externs-silent --crate-type bin --emit=dep-info,link -C embed-bitcode=no -C debug-assertions=off --cfg 'feature="default"' --cfg 'feature="std"' --check-cfg 'cfg(docsrs,test)' --check-cfg 'cfg(feature, values("default", "std"))' -C metadata=d528bd19f1858b8a --out-dir /home/bryan/.cache/sase/tmp/cargo-targets/gh_sase-org__sase-ws16-261115_123045/build/release/build/httparse/62c4f6dee775b265/out -C strip=debuginfo --cap-lints allow --force-warn=unused_crate_dependencies` (exit status: 2)
error: failed to run custom build command for `libc v0.2.186`

Caused by:
  process didn't exit successfully: `/home/bryan/.cache/sase/tmp/cargo-targets/gh_sase-org__sase-ws16-261115_123045/build/release/build/libc/4f863fbb5c88aad9/out/build_script_build` (exit status: 101)
  --- stdout
  cargo:rerun-if-changed=build.rs

  --- stderr

  thread 'main' (2164634) panicked at /home/bryan/.cargo/registry/src/index.crates.io-1949cf8c6b5b557f/libc-0.2.186/build.rs:219:5:
  failed to run rustc: sccache: error: failed to execute compile
  sccache: caused by: Failed to send data to or receive data from server
  sccache: caused by: Failed to read response header
  sccache: caused by: failed to fill whole buffer

  note: run with `RUST_BACKTRACE=1` environment variable to display a backtrace
sccache: error: failed to execute compile
sccache: caused by: Failed to send data to or receive data from server
sccache: caused by: Failed to read response header
sccache: caused by: failed to fill whole buffer
error: could not compile `icu_normalizer_data` (build script)

Caused by:
  process didn't exit successfully: `/home/bryan/bin/sase-rustc-wrapper /home/bryan/.rustup/toolchains/stable-x86_64-unknown-linux-gnu/bin/rustc --crate-name build_script_build --edition=2021 /home/bryan/.cargo/registry/src/index.crates.io-1949cf8c6b5b557f/icu_normalizer_data-2.2.0/build.rs --error-format=json --json=diagnostic-rendered-ansi,artifacts,future-incompat,unused-externs-silent --crate-type bin --emit=dep-info,link -C embed-bitcode=no -C debug-assertions=off --check-cfg 'cfg(docsrs,test)' --check-cfg 'cfg(feature, values())' -C metadata=da36c1823ac93575 --out-dir /home/bryan/.cache/sase/tmp/cargo-targets/gh_sase-org__sase-ws16-261115_123045/build/release/build/icu_normalizer_data/0ae91869c97c9d68/out -C strip=debuginfo --cap-lints allow --force-warn=unused_crate_dependencies` (exit status: 2)
sccache: error: failed to execute compile
sccache: caused by: Failed to send data to or receive data from server
sccache: caused by: Failed to read response header
sccache: caused by: failed to fill whole buffer
error: could not compile `crossbeam-deque` (build script)

Caused by:
  process didn't exit successfully: `/home/bryan/bin/sase-rustc-wrapper /home/bryan/.rustup/toolchains/stable-x86_64-unknown-linux-gnu/bin/rustc --crate-name build_script_build --edition=2021 /home/bryan/.cargo/registry/src/index.crates.io-1949cf8c6b5b557f/crossbeam-deque-0.8.8/build.rs --error-format=json --json=diagnostic-rendered-ansi,artifacts,future-incompat,unused-externs-silent --crate-type bin --emit=dep-info,link -C embed-bitcode=no -C debug-assertions=off --cfg 'feature="default"' --cfg 'feature="std"' --check-cfg 'cfg(docsrs,test)' --check-cfg 'cfg(feature, values("default", "std"))' -C metadata=bf2fab00607801d8 --out-dir /home/bryan/.cache/sase/tmp/cargo-targets/gh_sase-org__sase-ws16-261115_123045/build/release/build/crossbeam-deque/84b25d122bfa837d/out -C strip=debuginfo --cap-lints allow --force-warn=unused_crate_dependencies` (exit status: 2)
sccache: error: failed to execute compile
sccache: error: failed to execute compile
error: could not compile `crossbeam-epoch` (build script)

Caused by:
  process didn't exit successfully: `/home/bryan/bin/sase-rustc-wrapper /home/bryan/.rustup/toolchains/stable-x86_64-unknown-linux-gnu/bin/rustc --crate-name build_script_build --edition=2021 /home/bryan/.cargo/registry/src/index.crates.io-1949cf8c6b5b557f/crossbeam-epoch-0.9.21/build.rs --error-format=json --json=diagnostic-rendered-ansi,artifacts,future-incompat,unused-externs-silent --crate-type bin --emit=dep-info,link -C embed-bitcode=no -C debug-assertions=off --cfg 'feature="alloc"' --cfg 'feature="std"' --check-cfg 'cfg(docsrs,test)' --check-cfg 'cfg(feature, values("alloc", "default", "loom", "loom-crate", "nightly", "std"))' -C metadata=c27c9d09d8ed9b51 --out-dir /home/bryan/.cache/sase/tmp/cargo-targets/gh_sase-org__sase-ws16-261115_123045/build/release/build/crossbeam-epoch/f1e581ac4356af63/out -C strip=debuginfo --cap-lints allow --force-warn=unused_crate_dependencies` (exit status: 2)
sccache: caused by: Failed to send data to or receive data from server
sccache: caused by: Failed to read response header
sccache: caused by: Connection reset by peer (os error 104)
sccache: caused by: Failed to send data to or receive data from server
sccache: caused by: Failed to read response header
sccache: caused by: Connection reset by peer (os error 104)
error: could not compile `zmij` (lib)

Caused by:
  process didn't exit successfully: `/home/bryan/bin/sase-rustc-wrapper /home/bryan/.rustup/toolchains/stable-x86_64-unknown-linux-gnu/bin/rustc --crate-name zmij --edition=2021 /home/bryan/.cargo/registry/src/index.crates.io-1949cf8c6b5b557f/zmij-1.0.21/src/lib.rs --error-format=json --json=diagnostic-rendered-ansi,artifacts,future-incompat,unused-externs-silent --crate-type lib --emit=dep-info,metadata,link -C opt-level=3 -C linker-plugin-lto -C codegen-units=1 --check-cfg 'cfg(docsrs,test)' --check-cfg 'cfg(feature, values("no-panic"))' -C metadata=928c06c0fea7300f -C extra-filename=-ef6f5e92411273ab --out-dir /home/bryan/.cache/sase/tmp/cargo-targets/gh_sase-org__sase-ws16-261115_123045/build/release/build/zmij/ef6f5e92411273ab/out -C strip=debuginfo --cap-lints allow --force-warn=unused_crate_dependencies --check-cfg 'cfg(exhaustive)' --check-cfg 'cfg(zmij_no_select_unpredictable)'` (exit status: 2)
error: could not compile `target-lexicon` (lib)

Caused by:
  process didn't exit successfully: `/home/bryan/bin/sase-rustc-wrapper /home/bryan/.rustup/toolchains/stable-x86_64-unknown-linux-gnu/bin/rustc --crate-name target_lexicon --edition=2018 /home/bryan/.cargo/registry/src/index.crates.io-1949cf8c6b5b557f/target-lexicon-0.12.16/src/lib.rs --error-format=json --json=diagnostic-rendered-ansi,artifacts,future-incompat,unused-externs-silent --crate-type lib --emit=dep-info,metadata,link -C embed-bitcode=no -C debug-assertions=off --cfg 'feature="default"' --check-cfg 'cfg(docsrs,test)' --check-cfg 'cfg(feature, values("arch_zkasm", "default", "serde", "serde_support", "std"))' -C metadata=0b280f5b2bad4499 -C extra-filename=-5212da4cb1996759 --out-dir /home/bryan/.cache/sase/tmp/cargo-targets/gh_sase-org__sase-ws16-261115_123045/build/release/build/target-lexicon/5212da4cb1996759/out -C strip=debuginfo --cap-lints allow --force-warn=unused_crate_dependencies --cfg 'feature="rust_1_40"'` (exit status: 2)
sccache: error: failed to execute compile
sccache: error: failed to execute compile
sccache: caused by: Failed to send data to or receive data from server
sccache: caused by: Failed to send data to or receive data from server
sccache: caused by: Failed to read response header
sccache: caused by: Failed to read response header
sccache: caused by: failed to fill whole buffer
sccache: caused by: Connection reset by peer (os error 104)
error: could not compile `zmij` (lib)

Caused by:
  process didn't exit successfully: `/home/bryan/bin/sase-rustc-wrapper /home/bryan/.rustup/toolchains/stable-x86_64-unknown-linux-gnu/bin/rustc --crate-name zmij --edition=2021 /home/bryan/.cargo/registry/src/index.crates.io-1949cf8c6b5b557f/zmij-1.0.21/src/lib.rs --error-format=json --json=diagnostic-rendered-ansi,artifacts,future-incompat,unused-externs-silent --crate-type lib --emit=dep-info,metadata,link -C embed-bitcode=no -C debug-assertions=off --check-cfg 'cfg(docsrs,test)' --check-cfg 'cfg(feature, values("no-panic"))' -C metadata=f6cb8a53446f915c -C extra-filename=-02ca38c4d4f526f8 --out-dir /home/bryan/.cache/sase/tmp/cargo-targets/gh_sase-org__sase-ws16-261115_123045/build/release/build/zmij/02ca38c4d4f526f8/out -C strip=debuginfo --cap-lints allow --force-warn=unused_crate_dependencies --check-cfg 'cfg(exhaustive)' --check-cfg 'cfg(zmij_no_select_unpredictable)'` (exit status: 2)
error: could not compile `zerocopy` (lib)

Caused by:
  process didn't exit successfully: `/home/bryan/bin/sase-rustc-wrapper /home/bryan/.rustup/toolchains/stable-x86_64-unknown-linux-gnu/bin/rustc --crate-name zerocopy --edition=2021 /home/bryan/.cargo/registry/src/index.crates.io-1949cf8c6b5b557f/zerocopy-0.8.48/src/lib.rs --error-format=json --json=diagnostic-rendered-ansi,artifacts,future-incompat,unused-externs-silent --crate-type lib --emit=dep-info,metadata,link -C opt-level=3 -C linker-plugin-lto -C codegen-units=1 --cfg 'feature="simd"' --check-cfg 'cfg(docsrs,test)' --check-cfg 'cfg(feature, values("__internal_use_only_features_that_work_on_stable", "alloc", "derive", "float-nightly", "simd", "simd-nightly", "std", "zerocopy-derive"))' -C metadata=fb537accfdcf2ec9 -C extra-filename=-a63b5e171ab88188 --out-dir /home/bryan/.cache/sase/tmp/cargo-targets/gh_sase-org__sase-ws16-261115_123045/build/release/build/zerocopy/a63b5e171ab88188/out -C strip=debuginfo --cap-lints allow --force-warn=unused_crate_dependencies --check-cfg 'cfg(no_zerocopy_simd_x86_avx12_1_89_0)' --check-cfg 'cfg(rust, values("1.89.0"))' --check-cfg 'cfg(no_zerocopy_core_error_1_81_0)' --check-cfg 'cfg(rust, values("1.81.0"))' --check-cfg 'cfg(no_zerocopy_diagnostic_on_unimplemented_1_78_0)' --check-cfg 'cfg(rust, values("1.78.0"))' --check-cfg 'cfg(no_zerocopy_generic_bounds_in_const_fn_1_61_0)' --check-cfg 'cfg(rust, values("1.61.0"))' --check-cfg 'cfg(no_zerocopy_target_has_atomics_1_60_0)' --check-cfg 'cfg(rust, values("1.60.0"))' --check-cfg 'cfg(no_zerocopy_aarch64_simd_1_59_0)' --check-cfg 'cfg(rust, values("1.59.0"))' --check-cfg 'cfg(no_zerocopy_aarch64_simd_be_1_87_0)' --check-cfg 'cfg(rust, values("1.87.0"))' --check-cfg 'cfg(no_zerocopy_panic_in_const_and_vec_try_reserve_1_57_0)' --check-cfg 'cfg(rust, values("1.57.0"))' --check-cfg 'cfg(doc_cfg)' --check-cfg 'cfg(kani)' --check-cfg 'cfg(__ZEROCOPY_INTERNAL_USE_ONLY_NIGHTLY_FEATURES_IN_TESTS)' --check-cfg 'cfg(__ZEROCOPY_INTERNAL_USE_ONLY_DEV_MODE)' --check-cfg 'cfg(coverage_nightly)' --check-cfg 'cfg(zerocopy_inline_always)'` (exit status: 2)
💥 maturin failed
  Caused by: Failed to build a native library through cargo
  Caused by: Cargo build finished with "exit status: 101": `env -u CARGO PYO3_BUILD_EXTENSION_MODULE="1" PYO3_ENVIRONMENT_SIGNATURE="cpython-3.14-64bit" PYO3_PYTHON="/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/.venv/bin/python" PYTHON_SYS_EXECUTABLE="/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/.venv/bin/python" "cargo" "rustc" "--profile" "release" "--features" "pyo3/extension-module" "--message-format" "json-render-diagnostics" "--manifest-path" "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/sase/repos/linked/sase-core/crates/sase_core_py/Cargo.toml" "--lib" "--crate-type" "cdylib" "--" "-C" "strip=symbols"`
error: recipe `rust-install` failed on line 1257 with exit code 1
error: recipe `_install-venv` failed on line 202 with exit code 1

