#gh:gh_sase-org__sase Can you help me fix the `just symvision` command (see the command output below for context)? #plan 
```
┌───────────────────────────────────────────────────────┐
│                RUNNING: just symvision                │
└───────────────────────────────────────────────────────┘
  File "/home/bryan/projects/github/sase-org/sase/tools/validate_sase_core_rs", line 327
    return False
IndentationError: unexpected indent
[setup] Rebuilding stale or missing sase_core_rs from ../sase-core before Python dependency resolution.
# Harden cargo crate downloads against transient crates.io flakiness.
# CI has hit `curl ... [16] Error in the HTTP2 framing layer` while
# maturin's `cargo metadata` fetches deps; disabling HTTP/2 multiplexing
# and raising the retry count makes the download resilient. Both are
# overridable from the environment.
🍹 Building a mixed python/rust project
🔗 Found pyo3 bindings with abi3 support
🐍 Found CPython 3.14 at /home/bryan/projects/github/sase-org/sase/.venv/bin/python
📡 Using build options features from pyproject.toml
    Finished `release` profile [optimized] target(s) in 0.08s
📦 Built wheel for abi3 Python ≥ 3.12 to /tmp/.tmpHYdvJz/sase_core_rs-0.31.12-cp312-abi3-linux_x86_64.whl
✏️ Setting installed package as editable
🛠 Installed sase-core-rs-0.31.12
# Keep the LSP server in lockstep with the extension: both are built
# from the same sase-core checkout, and the ACE/LSP parity tests
# compare their directive contracts.
    Finished `release` profile [optimized] target(s) in 0.09s
[rust-lsp-install] installed /home/bryan/projects/github/sase-org/sase/.venv/bin/sase-xprompt-lsp
  File "/home/bryan/projects/github/sase-org/sase/tools/validate_sase_core_rs", line 327
    return False
IndentationError: unexpected indent
error: recipe `_setup` failed on line 121 with exit code 1
error: recipe `symvision` failed on line 784 with exit code 1
```