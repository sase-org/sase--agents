# Chat History - ace-run (sase-1s7.3--mon)

- **TIMESTAMP:** 2026-11-10 15:24:45 EST
- **MODEL:** grok/grok-4.6
- **AGENT:** sase-1s7.3--mon

## Prompt

sase monitor start --command 'gh run watch 42673707335 -R sase-org/sase-core --interval 120 || true' --reason 'Watch sase-core master CI rerun 42673707335 attempt 2 after infrastructure miss so sase-1s7.3 can clear core_ci_red'

## Response

sase: running unwrapped (no profile (monitor.tool_wrap is verify))
Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* master CI · 42673707335
Triggered via push about 2 minutes ago

JOBS
✓ release workflow scripts in 10s (ID 130082108744)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v10.3.0
  ✓ unit tests for release helper scripts
  ✓ Post Run astral-sh/setup-uv@v10.3.0
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* cargo fmt + clippy + test (macos-latest) (ID 130082109061)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Read pinned toolchain
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  ✓ cargo fmt --all -- --check
  ✓ unified dependency features
  * cargo clippy --workspace --all-targets -- -D warnings
  * cargo test --workspace
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
* maturin build + import smoke (ID 130082109165)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Cache pip / maturin
  * Build abi3 wheel
  * Run wheel smoke in fresh venv
  * twine check
  * Post Cache pip / maturin
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
* cargo fmt + clippy + test (ubuntu-latest) (ID 130082109297)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Read pinned toolchain
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  ✓ cargo fmt --all -- --check
  ✓ unified dependency features
  * cargo clippy --workspace --all-targets -- -D warnings
  * cargo test --workspace
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
release workflow scripts: .github#2

- reran run 40346929251: every red job never got a runner (1 starved)
release workflow scripts: .github#24

- reran run 40346929251: every red job never got a runner (1 starved)
release workflow scripts: .github#22

- reran run 40346929251: every red job never got a runner (1 starved)
release workflow scripts: .github#21

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
release workflow scripts: .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* master CI · 42673707335
Triggered via push about 4 minutes ago

JOBS
✓ release workflow scripts in 10s (ID 130082108744)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v10.3.0
  ✓ unit tests for release helper scripts
  ✓ Post Run astral-sh/setup-uv@v10.3.0
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* cargo fmt + clippy + test (macos-latest) (ID 130082109061)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Read pinned toolchain
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  ✓ cargo fmt --all -- --check
  ✓ unified dependency features
  * cargo clippy --workspace --all-targets -- -D warnings
  * cargo test --workspace
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
* maturin build + import smoke (ID 130082109165)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Cache pip / maturin
  * Build abi3 wheel
  * Run wheel smoke in fresh venv
  * twine check
  * Post Cache pip / maturin
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
* cargo fmt + clippy + test (ubuntu-latest) (ID 130082109297)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Read pinned toolchain
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  ✓ cargo fmt --all -- --check
  ✓ unified dependency features
  ✓ cargo clippy --workspace --all-targets -- -D warnings
  * cargo test --workspace
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
release workflow scripts: .github#2

- reran run 40346929251: every red job never got a runner (1 starved)
release workflow scripts: .github#24

- reran run 40346929251: every red job never got a runner (1 starved)
release workflow scripts: .github#22

- reran run 40346929251: every red job never got a runner (1 starved)
release workflow scripts: .github#21

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
release workflow scripts: .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* master CI · 42673707335
Triggered via push about 6 minutes ago

JOBS
✓ release workflow scripts in 10s (ID 130082108744)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v10.3.0
  ✓ unit tests for release helper scripts
  ✓ Post Run astral-sh/setup-uv@v10.3.0
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* cargo fmt + clippy + test (macos-latest) (ID 130082109061)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Read pinned toolchain
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  ✓ cargo fmt --all -- --check
  ✓ unified dependency features
  * cargo clippy --workspace --all-targets -- -D warnings
  * cargo test --workspace
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
* maturin build + import smoke (ID 130082109165)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Cache pip / maturin
  * Build abi3 wheel
  * Run wheel smoke in fresh venv
  * twine check
  * Post Cache pip / maturin
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
* cargo fmt + clippy + test (ubuntu-latest) (ID 130082109297)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Read pinned toolchain
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  ✓ cargo fmt --all -- --check
  ✓ unified dependency features
  ✓ cargo clippy --workspace --all-targets -- -D warnings
  * cargo test --workspace
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
release workflow scripts: .github#2

- reran run 40346929251: every red job never got a runner (1 starved)
release workflow scripts: .github#24

- reran run 40346929251: every red job never got a runner (1 starved)
release workflow scripts: .github#22

- reran run 40346929251: every red job never got a runner (1 starved)
release workflow scripts: .github#21

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
release workflow scripts: .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* master CI · 42673707335
Triggered via push about 8 minutes ago

JOBS
✓ release workflow scripts in 10s (ID 130082108744)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v10.3.0
  ✓ unit tests for release helper scripts
  ✓ Post Run astral-sh/setup-uv@v10.3.0
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* cargo fmt + clippy + test (macos-latest) (ID 130082109061)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Read pinned toolchain
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  ✓ cargo fmt --all -- --check
  ✓ unified dependency features
  * cargo clippy --workspace --all-targets -- -D warnings
  * cargo test --workspace
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
* maturin build + import smoke (ID 130082109165)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Cache pip / maturin
  * Build abi3 wheel
  * Run wheel smoke in fresh venv
  * twine check
  * Post Cache pip / maturin
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
* cargo fmt + clippy + test (ubuntu-latest) (ID 130082109297)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Read pinned toolchain
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  ✓ cargo fmt --all -- --check
  ✓ unified dependency features
  ✓ cargo clippy --workspace --all-targets -- -D warnings
  * cargo test --workspace
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
release workflow scripts: .github#2

- reran run 40346929251: every red job never got a runner (1 starved)
release workflow scripts: .github#24

- reran run 40346929251: every red job never got a runner (1 starved)
release workflow scripts: .github#22

- reran run 40346929251: every red job never got a runner (1 starved)
release workflow scripts: .github#21

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
release workflow scripts: .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* master CI · 42673707335
Triggered via push about 10 minutes ago

JOBS
✓ release workflow scripts in 10s (ID 130082108744)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v10.3.0
  ✓ unit tests for release helper scripts
  ✓ Post Run astral-sh/setup-uv@v10.3.0
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* cargo fmt + clippy + test (macos-latest) (ID 130082109061)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Read pinned toolchain
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  ✓ cargo fmt --all -- --check
  ✓ unified dependency features
  ✓ cargo clippy --workspace --all-targets -- -D warnings
  * cargo test --workspace
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
* maturin build + import smoke (ID 130082109165)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Cache pip / maturin
  * Build abi3 wheel
  * Run wheel smoke in fresh venv
  * twine check
  * Post Cache pip / maturin
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
✓ cargo fmt + clippy + test (ubuntu-latest) in 9m54s (ID 130082109297)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Read pinned toolchain
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  ✓ cargo fmt --all -- --check
  ✓ unified dependency features
  ✓ cargo clippy --workspace --all-targets -- -D warnings
  ✓ cargo test --workspace
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
release workflow scripts: .github#2

- reran run 40346929251: every red job never got a runner (1 starved)
release workflow scripts: .github#24

- reran run 40346929251: every red job never got a runner (1 starved)
release workflow scripts: .github#22

- reran run 40346929251: every red job never got a runner (1 starved)
release workflow scripts: .github#21

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
release workflow scripts: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/setup-python@v5. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
cargo fmt + clippy + test (ubuntu-latest): .github#2

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
cargo fmt + clippy + test (ubuntu-latest): .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* master CI · 42673707335
Triggered via push about 12 minutes ago

JOBS
✓ release workflow scripts in 10s (ID 130082108744)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v10.3.0
  ✓ unit tests for release helper scripts
  ✓ Post Run astral-sh/setup-uv@v10.3.0
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* cargo fmt + clippy + test (macos-latest) (ID 130082109061)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Read pinned toolchain
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  ✓ cargo fmt --all -- --check
  ✓ unified dependency features
  ✓ cargo clippy --workspace --all-targets -- -D warnings
  * cargo test --workspace
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
* maturin build + import smoke (ID 130082109165)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Cache pip / maturin
  * Build abi3 wheel
  * Run wheel smoke in fresh venv
  * twine check
  * Post Cache pip / maturin
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
✓ cargo fmt + clippy + test (ubuntu-latest) in 9m54s (ID 130082109297)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Read pinned toolchain
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  ✓ cargo fmt --all -- --check
  ✓ unified dependency features
  ✓ cargo clippy --workspace --all-targets -- -D warnings
  ✓ cargo test --workspace
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
release workflow scripts: .github#2

- reran run 40346929251: every red job never got a runner (1 starved)
release workflow scripts: .github#24

- reran run 40346929251: every red job never got a runner (1 starved)
release workflow scripts: .github#22

- reran run 40346929251: every red job never got a runner (1 starved)
release workflow scripts: .github#21

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
release workflow scripts: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/setup-python@v5. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
cargo fmt + clippy + test (ubuntu-latest): .github#2

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
cargo fmt + clippy + test (ubuntu-latest): .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* master CI · 42673707335
Triggered via push about 14 minutes ago

JOBS
✓ release workflow scripts in 10s (ID 130082108744)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v10.3.0
  ✓ unit tests for release helper scripts
  ✓ Post Run astral-sh/setup-uv@v10.3.0
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* cargo fmt + clippy + test (macos-latest) (ID 130082109061)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Read pinned toolchain
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  ✓ cargo fmt --all -- --check
  ✓ unified dependency features
  ✓ cargo clippy --workspace --all-targets -- -D warnings
  * cargo test --workspace
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
✓ maturin build + import smoke in 12m30s (ID 130082109165)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Cache pip / maturin
  ✓ Build abi3 wheel
  ✓ Run wheel smoke in fresh venv
  ✓ twine check
  ✓ Post Cache pip / maturin
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ cargo fmt + clippy + test (ubuntu-latest) in 9m54s (ID 130082109297)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Read pinned toolchain
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  ✓ cargo fmt --all -- --check
  ✓ unified dependency features
  ✓ cargo clippy --workspace --all-targets -- -D warnings
  ✓ cargo test --workspace
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
release workflow scripts: .github#2

- reran run 40346929251: every red job never got a runner (1 starved)
release workflow scripts: .github#24

- reran run 40346929251: every red job never got a runner (1 starved)
release workflow scripts: .github#22

- reran run 40346929251: every red job never got a runner (1 starved)
release workflow scripts: .github#21

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
release workflow scripts: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/setup-python@v5. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
cargo fmt + clippy + test (ubuntu-latest): .github#2

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
cargo fmt + clippy + test (ubuntu-latest): .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* master CI · 42673707335
Triggered via push about 16 minutes ago

JOBS
✓ release workflow scripts in 10s (ID 130082108744)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v10.3.0
  ✓ unit tests for release helper scripts
  ✓ Post Run astral-sh/setup-uv@v10.3.0
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* cargo fmt + clippy + test (macos-latest) (ID 130082109061)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Read pinned toolchain
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  ✓ cargo fmt --all -- --check
  ✓ unified dependency features
  ✓ cargo clippy --workspace --all-targets -- -D warnings
  * cargo test --workspace
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
✓ maturin build + import smoke in 12m30s (ID 130082109165)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Cache pip / maturin
  ✓ Build abi3 wheel
  ✓ Run wheel smoke in fresh venv
  ✓ twine check
  ✓ Post Cache pip / maturin
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ cargo fmt + clippy + test (ubuntu-latest) in 9m54s (ID 130082109297)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Read pinned toolchain
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  ✓ cargo fmt --all -- --check
  ✓ unified dependency features
  ✓ cargo clippy --workspace --all-targets -- -D warnings
  ✓ cargo test --workspace
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
release workflow scripts: .github#2

- reran run 40346929251: every red job never got a runner (1 starved)
release workflow scripts: .github#24

- reran run 40346929251: every red job never got a runner (1 starved)
release workflow scripts: .github#22

- reran run 40346929251: every red job never got a runner (1 starved)
release workflow scripts: .github#21

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
release workflow scripts: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/setup-python@v5. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
cargo fmt + clippy + test (ubuntu-latest): .github#2

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
cargo fmt + clippy + test (ubuntu-latest): .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* master CI · 42673707335
Triggered via push about 18 minutes ago

JOBS
✓ release workflow scripts in 10s (ID 130082108744)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v10.3.0
  ✓ unit tests for release helper scripts
  ✓ Post Run astral-sh/setup-uv@v10.3.0
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* cargo fmt + clippy + test (macos-latest) (ID 130082109061)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Read pinned toolchain
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  ✓ cargo fmt --all -- --check
  ✓ unified dependency features
  ✓ cargo clippy --workspace --all-targets -- -D warnings
  * cargo test --workspace
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
✓ maturin build + import smoke in 12m30s (ID 130082109165)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Cache pip / maturin
  ✓ Build abi3 wheel
  ✓ Run wheel smoke in fresh venv
  ✓ twine check
  ✓ Post Cache pip / maturin
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ cargo fmt + clippy + test (ubuntu-latest) in 9m54s (ID 130082109297)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Read pinned toolchain
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  ✓ cargo fmt --all -- --check
  ✓ unified dependency features
  ✓ cargo clippy --workspace --all-targets -- -D warnings
  ✓ cargo test --workspace
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
release workflow scripts: .github#2

- reran run 40346929251: every red job never got a runner (1 starved)
release workflow scripts: .github#24

- reran run 40346929251: every red job never got a runner (1 starved)
release workflow scripts: .github#22

- reran run 40346929251: every red job never got a runner (1 starved)
release workflow scripts: .github#21

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
release workflow scripts: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/setup-python@v5. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
cargo fmt + clippy + test (ubuntu-latest): .github#2

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
cargo fmt + clippy + test (ubuntu-latest): .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* master CI · 42673707335
Triggered via push about 20 minutes ago

JOBS
✓ release workflow scripts in 10s (ID 130082108744)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v10.3.0
  ✓ unit tests for release helper scripts
  ✓ Post Run astral-sh/setup-uv@v10.3.0
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* cargo fmt + clippy + test (macos-latest) (ID 130082109061)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Read pinned toolchain
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  ✓ cargo fmt --all -- --check
  ✓ unified dependency features
  ✓ cargo clippy --workspace --all-targets -- -D warnings
  * cargo test --workspace
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
✓ maturin build + import smoke in 12m30s (ID 130082109165)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Cache pip / maturin
  ✓ Build abi3 wheel
  ✓ Run wheel smoke in fresh venv
  ✓ twine check
  ✓ Post Cache pip / maturin
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ cargo fmt + clippy + test (ubuntu-latest) in 9m54s (ID 130082109297)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Read pinned toolchain
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  ✓ cargo fmt --all -- --check
  ✓ unified dependency features
  ✓ cargo clippy --workspace --all-targets -- -D warnings
  ✓ cargo test --workspace
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
release workflow scripts: .github#2

- reran run 40346929251: every red job never got a runner (1 starved)
release workflow scripts: .github#24

- reran run 40346929251: every red job never got a runner (1 starved)
release workflow scripts: .github#22

- reran run 40346929251: every red job never got a runner (1 starved)
release workflow scripts: .github#21

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
release workflow scripts: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/setup-python@v5. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
cargo fmt + clippy + test (ubuntu-latest): .github#2

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
cargo fmt + clippy + test (ubuntu-latest): .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* master CI · 42673707335
Triggered via push about 22 minutes ago

JOBS
✓ release workflow scripts in 10s (ID 130082108744)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v10.3.0
  ✓ unit tests for release helper scripts
  ✓ Post Run astral-sh/setup-uv@v10.3.0
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* cargo fmt + clippy + test (macos-latest) (ID 130082109061)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Read pinned toolchain
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  ✓ cargo fmt --all -- --check
  ✓ unified dependency features
  ✓ cargo clippy --workspace --all-targets -- -D warnings
  * cargo test --workspace
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
✓ maturin build + import smoke in 12m30s (ID 130082109165)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Cache pip / maturin
  ✓ Build abi3 wheel
  ✓ Run wheel smoke in fresh venv
  ✓ twine check
  ✓ Post Cache pip / maturin
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ cargo fmt + clippy + test (ubuntu-latest) in 9m54s (ID 130082109297)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Read pinned toolchain
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  ✓ cargo fmt --all -- --check
  ✓ unified dependency features
  ✓ cargo clippy --workspace --all-targets -- -D warnings
  ✓ cargo test --workspace
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
release workflow scripts: .github#2

- reran run 40346929251: every red job never got a runner (1 starved)
release workflow scripts: .github#24

- reran run 40346929251: every red job never got a runner (1 starved)
release workflow scripts: .github#22

- reran run 40346929251: every red job never got a runner (1 starved)
release workflow scripts: .github#21

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
release workflow scripts: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/setup-python@v5. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
cargo fmt + clippy + test (ubuntu-latest): .github#2

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
cargo fmt + clippy + test (ubuntu-latest): .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* master CI · 42673707335
Triggered via push about 24 minutes ago

JOBS
✓ release workflow scripts in 10s (ID 130082108744)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v10.3.0
  ✓ unit tests for release helper scripts
  ✓ Post Run astral-sh/setup-uv@v10.3.0
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* cargo fmt + clippy + test (macos-latest) (ID 130082109061)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Read pinned toolchain
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  ✓ cargo fmt --all -- --check
  ✓ unified dependency features
  ✓ cargo clippy --workspace --all-targets -- -D warnings
  * cargo test --workspace
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
✓ maturin build + import smoke in 12m30s (ID 130082109165)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Cache pip / maturin
  ✓ Build abi3 wheel
  ✓ Run wheel smoke in fresh venv
  ✓ twine check
  ✓ Post Cache pip / maturin
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ cargo fmt + clippy + test (ubuntu-latest) in 9m54s (ID 130082109297)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Read pinned toolchain
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  ✓ cargo fmt --all -- --check
  ✓ unified dependency features
  ✓ cargo clippy --workspace --all-targets -- -D warnings
  ✓ cargo test --workspace
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
release workflow scripts: .github#2

- reran run 40346929251: every red job never got a runner (1 starved)
release workflow scripts: .github#24

- reran run 40346929251: every red job never got a runner (1 starved)
release workflow scripts: .github#22

- reran run 40346929251: every red job never got a runner (1 starved)
release workflow scripts: .github#21

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
release workflow scripts: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/setup-python@v5. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
cargo fmt + clippy + test (ubuntu-latest): .github#2

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
cargo fmt + clippy + test (ubuntu-latest): .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* master CI · 42673707335
Triggered via push about 26 minutes ago

JOBS
✓ release workflow scripts in 10s (ID 130082108744)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v10.3.0
  ✓ unit tests for release helper scripts
  ✓ Post Run astral-sh/setup-uv@v10.3.0
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* cargo fmt + clippy + test (macos-latest) (ID 130082109061)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Read pinned toolchain
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  ✓ cargo fmt --all -- --check
  ✓ unified dependency features
  ✓ cargo clippy --workspace --all-targets -- -D warnings
  * cargo test --workspace
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
✓ maturin build + import smoke in 12m30s (ID 130082109165)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Cache pip / maturin
  ✓ Build abi3 wheel
  ✓ Run wheel smoke in fresh venv
  ✓ twine check
  ✓ Post Cache pip / maturin
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ cargo fmt + clippy + test (ubuntu-latest) in 9m54s (ID 130082109297)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Read pinned toolchain
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  ✓ cargo fmt --all -- --check
  ✓ unified dependency features
  ✓ cargo clippy --workspace --all-targets -- -D warnings
  ✓ cargo test --workspace
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
release workflow scripts: .github#2

- reran run 40346929251: every red job never got a runner (1 starved)
release workflow scripts: .github#24

- reran run 40346929251: every red job never got a runner (1 starved)
release workflow scripts: .github#22

- reran run 40346929251: every red job never got a runner (1 starved)
release workflow scripts: .github#21

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
release workflow scripts: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/setup-python@v5. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
cargo fmt + clippy + test (ubuntu-latest): .github#2

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
cargo fmt + clippy + test (ubuntu-latest): .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* master CI · 42673707335
Triggered via push about 28 minutes ago

JOBS
✓ release workflow scripts in 10s (ID 130082108744)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v10.3.0
  ✓ unit tests for release helper scripts
  ✓ Post Run astral-sh/setup-uv@v10.3.0
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* cargo fmt + clippy + test (macos-latest) (ID 130082109061)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Read pinned toolchain
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  ✓ cargo fmt --all -- --check
  ✓ unified dependency features
  ✓ cargo clippy --workspace --all-targets -- -D warnings
  * cargo test --workspace
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
✓ maturin build + import smoke in 12m30s (ID 130082109165)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Cache pip / maturin
  ✓ Build abi3 wheel
  ✓ Run wheel smoke in fresh venv
  ✓ twine check
  ✓ Post Cache pip / maturin
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ cargo fmt + clippy + test (ubuntu-latest) in 9m54s (ID 130082109297)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Read pinned toolchain
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  ✓ cargo fmt --all -- --check
  ✓ unified dependency features
  ✓ cargo clippy --workspace --all-targets -- -D warnings
  ✓ cargo test --workspace
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
release workflow scripts: .github#2

- reran run 40346929251: every red job never got a runner (1 starved)
release workflow scripts: .github#24

- reran run 40346929251: every red job never got a runner (1 starved)
release workflow scripts: .github#22

- reran run 40346929251: every red job never got a runner (1 starved)
release workflow scripts: .github#21

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
release workflow scripts: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/setup-python@v5. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
cargo fmt + clippy + test (ubuntu-latest): .github#2

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
cargo fmt + clippy + test (ubuntu-latest): .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* master CI · 42673707335
Triggered via push about 30 minutes ago

JOBS
✓ release workflow scripts in 10s (ID 130082108744)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v10.3.0
  ✓ unit tests for release helper scripts
  ✓ Post Run astral-sh/setup-uv@v10.3.0
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* cargo fmt + clippy + test (macos-latest) (ID 130082109061)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Read pinned toolchain
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  ✓ cargo fmt --all -- --check
  ✓ unified dependency features
  ✓ cargo clippy --workspace --all-targets -- -D warnings
  * cargo test --workspace
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
✓ maturin build + import smoke in 12m30s (ID 130082109165)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Cache pip / maturin
  ✓ Build abi3 wheel
  ✓ Run wheel smoke in fresh venv
  ✓ twine check
  ✓ Post Cache pip / maturin
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ cargo fmt + clippy + test (ubuntu-latest) in 9m54s (ID 130082109297)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Read pinned toolchain
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  ✓ cargo fmt --all -- --check
  ✓ unified dependency features
  ✓ cargo clippy --workspace --all-targets -- -D warnings
  ✓ cargo test --workspace
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
release workflow scripts: .github#2

- reran run 40346929251: every red job never got a runner (1 starved)
release workflow scripts: .github#24

- reran run 40346929251: every red job never got a runner (1 starved)
release workflow scripts: .github#22

- reran run 40346929251: every red job never got a runner (1 starved)
release workflow scripts: .github#21

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
release workflow scripts: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/setup-python@v5. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
cargo fmt + clippy + test (ubuntu-latest): .github#2

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
cargo fmt + clippy + test (ubuntu-latest): .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* master CI · 42673707335
Triggered via push about 32 minutes ago

JOBS
✓ release workflow scripts in 10s (ID 130082108744)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v10.3.0
  ✓ unit tests for release helper scripts
  ✓ Post Run astral-sh/setup-uv@v10.3.0
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* cargo fmt + clippy + test (macos-latest) (ID 130082109061)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Read pinned toolchain
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  ✓ cargo fmt --all -- --check
  ✓ unified dependency features
  ✓ cargo clippy --workspace --all-targets -- -D warnings
  * cargo test --workspace
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
✓ maturin build + import smoke in 12m30s (ID 130082109165)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Cache pip / maturin
  ✓ Build abi3 wheel
  ✓ Run wheel smoke in fresh venv
  ✓ twine check
  ✓ Post Cache pip / maturin
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ cargo fmt + clippy + test (ubuntu-latest) in 9m54s (ID 130082109297)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Read pinned toolchain
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  ✓ cargo fmt --all -- --check
  ✓ unified dependency features
  ✓ cargo clippy --workspace --all-targets -- -D warnings
  ✓ cargo test --workspace
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
release workflow scripts: .github#2

- reran run 40346929251: every red job never got a runner (1 starved)
release workflow scripts: .github#24

- reran run 40346929251: every red job never got a runner (1 starved)
release workflow scripts: .github#22

- reran run 40346929251: every red job never got a runner (1 starved)
release workflow scripts: .github#21

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
release workflow scripts: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/setup-python@v5. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
cargo fmt + clippy + test (ubuntu-latest): .github#2

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
cargo fmt + clippy + test (ubuntu-latest): .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* master CI · 42673707335
Triggered via push about 34 minutes ago

JOBS
✓ release workflow scripts in 10s (ID 130082108744)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v10.3.0
  ✓ unit tests for release helper scripts
  ✓ Post Run astral-sh/setup-uv@v10.3.0
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* cargo fmt + clippy + test (macos-latest) (ID 130082109061)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Read pinned toolchain
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  ✓ cargo fmt --all -- --check
  ✓ unified dependency features
  ✓ cargo clippy --workspace --all-targets -- -D warnings
  * cargo test --workspace
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
✓ maturin build + import smoke in 12m30s (ID 130082109165)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Cache pip / maturin
  ✓ Build abi3 wheel
  ✓ Run wheel smoke in fresh venv
  ✓ twine check
  ✓ Post Cache pip / maturin
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ cargo fmt + clippy + test (ubuntu-latest) in 9m54s (ID 130082109297)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Read pinned toolchain
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  ✓ cargo fmt --all -- --check
  ✓ unified dependency features
  ✓ cargo clippy --workspace --all-targets -- -D warnings
  ✓ cargo test --workspace
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
release workflow scripts: .github#2

- reran run 40346929251: every red job never got a runner (1 starved)
release workflow scripts: .github#24

- reran run 40346929251: every red job never got a runner (1 starved)
release workflow scripts: .github#22

- reran run 40346929251: every red job never got a runner (1 starved)
release workflow scripts: .github#21

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
release workflow scripts: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/setup-python@v5. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
cargo fmt + clippy + test (ubuntu-latest): .github#2

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
cargo fmt + clippy + test (ubuntu-latest): .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* master CI · 42673707335
Triggered via push about 36 minutes ago

JOBS
✓ release workflow scripts in 10s (ID 130082108744)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v10.3.0
  ✓ unit tests for release helper scripts
  ✓ Post Run astral-sh/setup-uv@v10.3.0
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* cargo fmt + clippy + test (macos-latest) (ID 130082109061)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Read pinned toolchain
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  ✓ cargo fmt --all -- --check
  ✓ unified dependency features
  ✓ cargo clippy --workspace --all-targets -- -D warnings
  * cargo test --workspace
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
✓ maturin build + import smoke in 12m30s (ID 130082109165)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Cache pip / maturin
  ✓ Build abi3 wheel
  ✓ Run wheel smoke in fresh venv
  ✓ twine check
  ✓ Post Cache pip / maturin
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ cargo fmt + clippy + test (ubuntu-latest) in 9m54s (ID 130082109297)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Read pinned toolchain
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  ✓ cargo fmt --all -- --check
  ✓ unified dependency features
  ✓ cargo clippy --workspace --all-targets -- -D warnings
  ✓ cargo test --workspace
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
release workflow scripts: .github#2

- reran run 40346929251: every red job never got a runner (1 starved)
release workflow scripts: .github#24

- reran run 40346929251: every red job never got a runner (1 starved)
release workflow scripts: .github#22

- reran run 40346929251: every red job never got a runner (1 starved)
release workflow scripts: .github#21

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
release workflow scripts: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/setup-python@v5. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
cargo fmt + clippy + test (ubuntu-latest): .github#2

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
cargo fmt + clippy + test (ubuntu-latest): .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* master CI · 42673707335
Triggered via push about 38 minutes ago

JOBS
✓ release workflow scripts in 10s (ID 130082108744)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v10.3.0
  ✓ unit tests for release helper scripts
  ✓ Post Run astral-sh/setup-uv@v10.3.0
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* cargo fmt + clippy + test (macos-latest) (ID 130082109061)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Read pinned toolchain
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  ✓ cargo fmt --all -- --check
  ✓ unified dependency features
  ✓ cargo clippy --workspace --all-targets -- -D warnings
  ✓ cargo test --workspace
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
✓ maturin build + import smoke in 12m30s (ID 130082109165)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Cache pip / maturin
  ✓ Build abi3 wheel
  ✓ Run wheel smoke in fresh venv
  ✓ twine check
  ✓ Post Cache pip / maturin
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ cargo fmt + clippy + test (ubuntu-latest) in 9m54s (ID 130082109297)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Read pinned toolchain
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  ✓ cargo fmt --all -- --check
  ✓ unified dependency features
  ✓ cargo clippy --workspace --all-targets -- -D warnings
  ✓ cargo test --workspace
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
release workflow scripts: .github#2

- reran run 40346929251: every red job never got a runner (1 starved)
release workflow scripts: .github#24

- reran run 40346929251: every red job never got a runner (1 starved)
release workflow scripts: .github#22

- reran run 40346929251: every red job never got a runner (1 starved)
release workflow scripts: .github#21

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
release workflow scripts: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/setup-python@v5. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
cargo fmt + clippy + test (ubuntu-latest): .github#2

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
cargo fmt + clippy + test (ubuntu-latest): .github#1

✓ master CI · 42673707335
Triggered via push about 40 minutes ago

JOBS
✓ release workflow scripts in 10s (ID 130082108744)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v10.3.0
  ✓ unit tests for release helper scripts
  ✓ Post Run astral-sh/setup-uv@v10.3.0
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ cargo fmt + clippy + test (macos-latest) in 38m32s (ID 130082109061)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Read pinned toolchain
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  ✓ cargo fmt --all -- --check
  ✓ unified dependency features
  ✓ cargo clippy --workspace --all-targets -- -D warnings
  ✓ cargo test --workspace
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ maturin build + import smoke in 12m30s (ID 130082109165)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Cache pip / maturin
  ✓ Build abi3 wheel
  ✓ Run wheel smoke in fresh venv
  ✓ twine check
  ✓ Post Cache pip / maturin
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ cargo fmt + clippy + test (ubuntu-latest) in 9m54s (ID 130082109297)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Read pinned toolchain
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  ✓ cargo fmt --all -- --check
  ✓ unified dependency features
  ✓ cargo clippy --workspace --all-targets -- -D warnings
  ✓ cargo test --workspace
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
release workflow scripts: .github#2

- reran run 40346929251: every red job never got a runner (1 starved)
release workflow scripts: .github#24

- reran run 40346929251: every red job never got a runner (1 starved)
release workflow scripts: .github#22

- reran run 40346929251: every red job never got a runner (1 starved)
release workflow scripts: .github#21

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
release workflow scripts: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/setup-python@v5. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
cargo fmt + clippy + test (ubuntu-latest): .github#2

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
cargo fmt + clippy + test (ubuntu-latest): .github#1


