# Chat History - ace-run (sase-1s7.5--mon-1)

- **TIMESTAMP:** 2026-11-11 00:04:56 EST
- **MODEL:** grok/grok-4.6
- **AGENT:** sase-1s7.5--mon-1

## Prompt

sase monitor start --command 'sh /tmp/sase-1s7.5-watch.sh' --reason 'Wait for leak-report stitch, then Telemetry attempt 3, Master Gate, and Full CI 42942621559 for sase-1s7.5'

## Response

sase: running unwrapped (no profile (monitor.tool_wrap is verify))
origin/master=1a5bb8097b4c4252c788e6af0038c73f1d00c6f2
tip=1a5bb8097b4c4252c788e6af0038c73f1d00c6f2
master_gate=42949405363
https://github.com/sase-org/sase/actions/runs/42949481249
dispatched telemetry.yml after stitch
telemetry=42949481249
Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* master Master Gate · 42949405363
Triggered via push less than a minute ago

JOBS
✓ docs in 37s (ID 130289902144)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Install just
  ✓ Set up Python
  ✓ Build and validate docs
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ core-wheel in 24s (ID 130289902419)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Resolve pinned Rust core revision
  ✓ Restore cached core wheel
  - Check out Rust core
  - Run astral-sh/setup-uv@v4
  - Set up Rust
  - Cache Rust build
  - Build abi3 Rust core wheel
  - Build macro LSP
  - Record wheel provenance
  - Save core wheel cache
  ✓ Upload Rust core artifacts
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* lint (ID 130290054199)
  ✓ Set up job
  * Run actions/checkout@v4
  * Install dependencies
  * Check pinned core bindings
  * Bootstrap SDD sidecars
  * Initialize SASE home
  * Run actions/setup-go@v5
  * Cache Go binaries
  * Install Go tools (keep-sorted)
  * Cache Prettier dependencies
  * Check Python formatting
  * Check Markdown formatting
  * Check generated model docs
  * Check shipped model policy
  * Lint
  * SASE validation
  * Validate committed plans
  * Build and verify package
  * Post Run actions/checkout@v4
* test (1) (ID 130290054356)
  ✓ Set up job
  * Run actions/checkout@v4
  * Install dependencies
  * Run sharded fast suite
  * Post Run actions/checkout@v4
* test (8) (ID 130290054400)
  ✓ Set up job
  * Run actions/checkout@v4
  * Install dependencies
  * Run sharded fast suite
  * Post Run actions/checkout@v4
* test (4) (ID 130290054402)
  ✓ Set up job
  * Run actions/checkout@v4
  * Install dependencies
  * Run sharded fast suite
  * Post Run actions/checkout@v4
* test (5) (ID 130290054406)
  ✓ Set up job
  * Run actions/checkout@v4
  * Install dependencies
  * Run sharded fast suite
  * Post Run actions/checkout@v4
* test (2) (ID 130290054436)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (6) (ID 130290054462)
  ✓ Set up job
  * Run actions/checkout@v4
  * Install dependencies
  * Run sharded fast suite
  * Post Run actions/checkout@v4
* test (3) (ID 130290054480)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  * Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (7) (ID 130290054675)
  ✓ Set up job
  * Run actions/checkout@v4
  * Install dependencies
  * Run sharded fast suite
  * Post Run actions/checkout@v4

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
docs: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0jNnzagAAAACIAUfqgn7wRZJeKu+MlzNMQ0gxQUEyMDMwODE0MDUyAEVkZ2U=
docs: .github#7

! Failed to restore: Cache service responded with 400
docs: .github#26

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
docs: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache/restore@v4, actions/checkout@v4, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
core-wheel: .github#2

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
core-wheel: .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* master Master Gate · 42949405363
Triggered via push about 2 minutes ago

JOBS
✓ docs in 37s (ID 130289902144)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Install just
  ✓ Set up Python
  ✓ Build and validate docs
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ core-wheel in 24s (ID 130289902419)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Resolve pinned Rust core revision
  ✓ Restore cached core wheel
  - Check out Rust core
  - Run astral-sh/setup-uv@v4
  - Set up Rust
  - Cache Rust build
  - Build abi3 Rust core wheel
  - Build macro LSP
  - Record wheel provenance
  - Save core wheel cache
  ✓ Upload Rust core artifacts
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* lint (ID 130290054199)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Check pinned core bindings
  ✓ Bootstrap SDD sidecars
  ✓ Initialize SASE home
  ✓ Run actions/setup-go@v5
  ✓ Cache Go binaries
  - Install Go tools (keep-sorted)
  ✓ Cache Prettier dependencies
  ✓ Check Python formatting
  ✓ Check Markdown formatting
  ✓ Check generated model docs
  ✓ Check shipped model policy
  * Lint
  * SASE validation
  * Validate committed plans
  * Build and verify package
  * Post Cache Prettier dependencies
  * Post Cache Go binaries
  * Post Run actions/setup-go@v5
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (1) (ID 130290054356)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (8) (ID 130290054400)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (4) (ID 130290054402)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (5) (ID 130290054406)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (2) (ID 130290054436)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (6) (ID 130290054462)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (3) (ID 130290054480)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (7) (ID 130290054675)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
docs: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0jNnzagAAAACIAUfqgn7wRZJeKu+MlzNMQ0gxQUEyMDMwODE0MDUyAEVkZ2U=
docs: .github#7

! Failed to restore: Cache service responded with 400
docs: .github#26

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
docs: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache/restore@v4, actions/checkout@v4, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
core-wheel: .github#2

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
core-wheel: .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* master Master Gate · 42949405363
Triggered via push about 4 minutes ago

JOBS
✓ docs in 37s (ID 130289902144)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Install just
  ✓ Set up Python
  ✓ Build and validate docs
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ core-wheel in 24s (ID 130289902419)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Resolve pinned Rust core revision
  ✓ Restore cached core wheel
  - Check out Rust core
  - Run astral-sh/setup-uv@v4
  - Set up Rust
  - Cache Rust build
  - Build abi3 Rust core wheel
  - Build macro LSP
  - Record wheel provenance
  - Save core wheel cache
  ✓ Upload Rust core artifacts
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ lint in 4m15s (ID 130290054199)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Check pinned core bindings
  ✓ Bootstrap SDD sidecars
  ✓ Initialize SASE home
  ✓ Run actions/setup-go@v5
  ✓ Cache Go binaries
  - Install Go tools (keep-sorted)
  ✓ Cache Prettier dependencies
  ✓ Check Python formatting
  ✓ Check Markdown formatting
  ✓ Check generated model docs
  ✓ Check shipped model policy
  ✓ Lint
  ✓ SASE validation
  ✓ Validate committed plans
  ✓ Build and verify package
  ✓ Post Cache Prettier dependencies
  ✓ Post Cache Go binaries
  ✓ Post Run actions/setup-go@v5
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* test (1) (ID 130290054356)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (8) (ID 130290054400)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (4) (ID 130290054402)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (5) (ID 130290054406)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (2) (ID 130290054436)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (6) (ID 130290054462)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (3) (ID 130290054480)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (7) (ID 130290054675)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
docs: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0jNnzagAAAACIAUfqgn7wRZJeKu+MlzNMQ0gxQUEyMDMwODE0MDUyAEVkZ2U=
docs: .github#7

! Failed to restore: Cache service responded with 400
docs: .github#26

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
docs: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache/restore@v4, actions/checkout@v4, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
core-wheel: .github#2

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
core-wheel: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache@v4, actions/checkout@v4, actions/download-artifact@v4, actions/setup-go@v5, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
lint: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0gNrzagAAAADjSZJHlcfySKlfS9unohRVQ0gxQUEyMDMwODEzMDI1AEVkZ2U=
lint: .github#9

! Failed to restore: Cache service responded with 400
lint: .github#54

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
lint: .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* master Master Gate · 42949405363
Triggered via push about 6 minutes ago

JOBS
✓ docs in 37s (ID 130289902144)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Install just
  ✓ Set up Python
  ✓ Build and validate docs
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ core-wheel in 24s (ID 130289902419)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Resolve pinned Rust core revision
  ✓ Restore cached core wheel
  - Check out Rust core
  - Run astral-sh/setup-uv@v4
  - Set up Rust
  - Cache Rust build
  - Build abi3 Rust core wheel
  - Build macro LSP
  - Record wheel provenance
  - Save core wheel cache
  ✓ Upload Rust core artifacts
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ lint in 4m15s (ID 130290054199)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Check pinned core bindings
  ✓ Bootstrap SDD sidecars
  ✓ Initialize SASE home
  ✓ Run actions/setup-go@v5
  ✓ Cache Go binaries
  - Install Go tools (keep-sorted)
  ✓ Cache Prettier dependencies
  ✓ Check Python formatting
  ✓ Check Markdown formatting
  ✓ Check generated model docs
  ✓ Check shipped model policy
  ✓ Lint
  ✓ SASE validation
  ✓ Validate committed plans
  ✓ Build and verify package
  ✓ Post Cache Prettier dependencies
  ✓ Post Cache Go binaries
  ✓ Post Run actions/setup-go@v5
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* test (1) (ID 130290054356)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (8) (ID 130290054400)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (4) (ID 130290054402)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (5) (ID 130290054406)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (2) (ID 130290054436)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (6) (ID 130290054462)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (3) (ID 130290054480)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (7) (ID 130290054675)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
docs: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0jNnzagAAAACIAUfqgn7wRZJeKu+MlzNMQ0gxQUEyMDMwODE0MDUyAEVkZ2U=
docs: .github#7

! Failed to restore: Cache service responded with 400
docs: .github#26

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
docs: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache/restore@v4, actions/checkout@v4, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
core-wheel: .github#2

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
core-wheel: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache@v4, actions/checkout@v4, actions/download-artifact@v4, actions/setup-go@v5, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
lint: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0gNrzagAAAADjSZJHlcfySKlfS9unohRVQ0gxQUEyMDMwODEzMDI1AEVkZ2U=
lint: .github#9

! Failed to restore: Cache service responded with 400
lint: .github#54

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
lint: .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* master Master Gate · 42949405363
Triggered via push about 8 minutes ago

JOBS
✓ docs in 37s (ID 130289902144)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Install just
  ✓ Set up Python
  ✓ Build and validate docs
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ core-wheel in 24s (ID 130289902419)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Resolve pinned Rust core revision
  ✓ Restore cached core wheel
  - Check out Rust core
  - Run astral-sh/setup-uv@v4
  - Set up Rust
  - Cache Rust build
  - Build abi3 Rust core wheel
  - Build macro LSP
  - Record wheel provenance
  - Save core wheel cache
  ✓ Upload Rust core artifacts
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ lint in 4m15s (ID 130290054199)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Check pinned core bindings
  ✓ Bootstrap SDD sidecars
  ✓ Initialize SASE home
  ✓ Run actions/setup-go@v5
  ✓ Cache Go binaries
  - Install Go tools (keep-sorted)
  ✓ Cache Prettier dependencies
  ✓ Check Python formatting
  ✓ Check Markdown formatting
  ✓ Check generated model docs
  ✓ Check shipped model policy
  ✓ Lint
  ✓ SASE validation
  ✓ Validate committed plans
  ✓ Build and verify package
  ✓ Post Cache Prettier dependencies
  ✓ Post Cache Go binaries
  ✓ Post Run actions/setup-go@v5
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* test (1) (ID 130290054356)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (8) (ID 130290054400)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (4) (ID 130290054402)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (5) (ID 130290054406)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (2) (ID 130290054436)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (6) (ID 130290054462)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (3) (ID 130290054480)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (7) (ID 130290054675)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
docs: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0jNnzagAAAACIAUfqgn7wRZJeKu+MlzNMQ0gxQUEyMDMwODE0MDUyAEVkZ2U=
docs: .github#7

! Failed to restore: Cache service responded with 400
docs: .github#26

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
docs: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache/restore@v4, actions/checkout@v4, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
core-wheel: .github#2

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
core-wheel: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache@v4, actions/checkout@v4, actions/download-artifact@v4, actions/setup-go@v5, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
lint: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0gNrzagAAAADjSZJHlcfySKlfS9unohRVQ0gxQUEyMDMwODEzMDI1AEVkZ2U=
lint: .github#9

! Failed to restore: Cache service responded with 400
lint: .github#54

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
lint: .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* master Master Gate · 42949405363
Triggered via push about 11 minutes ago

JOBS
✓ docs in 37s (ID 130289902144)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Install just
  ✓ Set up Python
  ✓ Build and validate docs
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ core-wheel in 24s (ID 130289902419)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Resolve pinned Rust core revision
  ✓ Restore cached core wheel
  - Check out Rust core
  - Run astral-sh/setup-uv@v4
  - Set up Rust
  - Cache Rust build
  - Build abi3 Rust core wheel
  - Build macro LSP
  - Record wheel provenance
  - Save core wheel cache
  ✓ Upload Rust core artifacts
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ lint in 4m15s (ID 130290054199)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Check pinned core bindings
  ✓ Bootstrap SDD sidecars
  ✓ Initialize SASE home
  ✓ Run actions/setup-go@v5
  ✓ Cache Go binaries
  - Install Go tools (keep-sorted)
  ✓ Cache Prettier dependencies
  ✓ Check Python formatting
  ✓ Check Markdown formatting
  ✓ Check generated model docs
  ✓ Check shipped model policy
  ✓ Lint
  ✓ SASE validation
  ✓ Validate committed plans
  ✓ Build and verify package
  ✓ Post Cache Prettier dependencies
  ✓ Post Cache Go binaries
  ✓ Post Run actions/setup-go@v5
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ test (1) in 9m17s (ID 130290054356)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* test (8) (ID 130290054400)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (4) (ID 130290054402)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (5) (ID 130290054406)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
✓ test (2) in 9m7s (ID 130290054436)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* test (6) (ID 130290054462)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (3) (ID 130290054480)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (7) (ID 130290054675)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
docs: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0jNnzagAAAACIAUfqgn7wRZJeKu+MlzNMQ0gxQUEyMDMwODE0MDUyAEVkZ2U=
docs: .github#7

! Failed to restore: Cache service responded with 400
docs: .github#26

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
docs: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache/restore@v4, actions/checkout@v4, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
core-wheel: .github#2

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
core-wheel: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache@v4, actions/checkout@v4, actions/download-artifact@v4, actions/setup-go@v5, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
lint: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0gNrzagAAAADjSZJHlcfySKlfS9unohRVQ0gxQUEyMDMwODEzMDI1AEVkZ2U=
lint: .github#9

! Failed to restore: Cache service responded with 400
lint: .github#54

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
lint: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
test (1): .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0rtvzagAAAADRLyi0gj0BTpHbnj3FYzQdUEhYMzFFREdFMDUwOQBFZGdl
test (1): .github#9

! Failed to restore: Cache service responded with 400
test (1): .github#54

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
test (1): .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
test (2): .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0pdvzagAAAAB/CupxBgOHTrr4C1FsncKsQ0gxQUEyMDMwODE0MDIzAEVkZ2U=
test (2): .github#9

! Failed to restore: Cache service responded with 400
test (2): .github#54

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
test (2): .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* master Master Gate · 42949405363
Triggered via push about 13 minutes ago

JOBS
✓ docs in 37s (ID 130289902144)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Install just
  ✓ Set up Python
  ✓ Build and validate docs
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ core-wheel in 24s (ID 130289902419)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Resolve pinned Rust core revision
  ✓ Restore cached core wheel
  - Check out Rust core
  - Run astral-sh/setup-uv@v4
  - Set up Rust
  - Cache Rust build
  - Build abi3 Rust core wheel
  - Build macro LSP
  - Record wheel provenance
  - Save core wheel cache
  ✓ Upload Rust core artifacts
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ lint in 4m15s (ID 130290054199)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Check pinned core bindings
  ✓ Bootstrap SDD sidecars
  ✓ Initialize SASE home
  ✓ Run actions/setup-go@v5
  ✓ Cache Go binaries
  - Install Go tools (keep-sorted)
  ✓ Cache Prettier dependencies
  ✓ Check Python formatting
  ✓ Check Markdown formatting
  ✓ Check generated model docs
  ✓ Check shipped model policy
  ✓ Lint
  ✓ SASE validation
  ✓ Validate committed plans
  ✓ Build and verify package
  ✓ Post Cache Prettier dependencies
  ✓ Post Cache Go binaries
  ✓ Post Run actions/setup-go@v5
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ test (1) in 9m17s (ID 130290054356)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ test (8) in 12m28s (ID 130290054400)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ test (4) in 11m38s (ID 130290054402)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ test (5) in 10m55s (ID 130290054406)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ test (2) in 9m7s (ID 130290054436)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ test (6) in 12m29s (ID 130290054462)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ test (3) in 10m46s (ID 130290054480)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ test (7) in 12m20s (ID 130290054675)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
docs: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0jNnzagAAAACIAUfqgn7wRZJeKu+MlzNMQ0gxQUEyMDMwODE0MDUyAEVkZ2U=
docs: .github#7

! Failed to restore: Cache service responded with 400
docs: .github#26

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
docs: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache/restore@v4, actions/checkout@v4, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
core-wheel: .github#2

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
core-wheel: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache@v4, actions/checkout@v4, actions/download-artifact@v4, actions/setup-go@v5, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
lint: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0gNrzagAAAADjSZJHlcfySKlfS9unohRVQ0gxQUEyMDMwODEzMDI1AEVkZ2U=
lint: .github#9

! Failed to restore: Cache service responded with 400
lint: .github#54

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
lint: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
test (1): .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0rtvzagAAAADRLyi0gj0BTpHbnj3FYzQdUEhYMzFFREdFMDUwOQBFZGdl
test (1): .github#9

! Failed to restore: Cache service responded with 400
test (1): .github#54

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
test (1): .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
test (2): .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0pdvzagAAAAB/CupxBgOHTrr4C1FsncKsQ0gxQUEyMDMwODE0MDIzAEVkZ2U=
test (2): .github#9

! Failed to restore: Cache service responded with 400
test (2): .github#54

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
test (2): .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
test (6): .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0b9zzagAAAAC/EMxsnaYhSILqDYZ23kCUUEhMMzBFREdFMDEwNgBFZGdl
test (6): .github#9

! Failed to restore: Cache service responded with 400
test (6): .github#54

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
test (6): .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
test (3): .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0CdzzagAAAADBIf8TA4b3Q53AcIg0YByEUEhMMzBFREdFMDIyMQBFZGdl
test (3): .github#9

! Failed to restore: Cache service responded with 400
test (3): .github#54

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
test (3): .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
test (7): .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0ZtzzagAAAABTWAmbze4sQLoCh3xe7u8+UEhMMzBFREdFMDQwOABFZGdl
test (7): .github#9

! Failed to restore: Cache service responded with 400
test (7): .github#54

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
test (7): .github#1

✓ master Master Gate · 42949405363
Triggered via push about 15 minutes ago

JOBS
✓ docs in 37s (ID 130289902144)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Install just
  ✓ Set up Python
  ✓ Build and validate docs
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ core-wheel in 24s (ID 130289902419)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Resolve pinned Rust core revision
  ✓ Restore cached core wheel
  - Check out Rust core
  - Run astral-sh/setup-uv@v4
  - Set up Rust
  - Cache Rust build
  - Build abi3 Rust core wheel
  - Build macro LSP
  - Record wheel provenance
  - Save core wheel cache
  ✓ Upload Rust core artifacts
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ lint in 4m15s (ID 130290054199)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Check pinned core bindings
  ✓ Bootstrap SDD sidecars
  ✓ Initialize SASE home
  ✓ Run actions/setup-go@v5
  ✓ Cache Go binaries
  - Install Go tools (keep-sorted)
  ✓ Cache Prettier dependencies
  ✓ Check Python formatting
  ✓ Check Markdown formatting
  ✓ Check generated model docs
  ✓ Check shipped model policy
  ✓ Lint
  ✓ SASE validation
  ✓ Validate committed plans
  ✓ Build and verify package
  ✓ Post Cache Prettier dependencies
  ✓ Post Cache Go binaries
  ✓ Post Run actions/setup-go@v5
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ test (1) in 9m17s (ID 130290054356)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ test (8) in 12m28s (ID 130290054400)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ test (4) in 11m38s (ID 130290054402)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ test (5) in 10m55s (ID 130290054406)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ test (2) in 9m7s (ID 130290054436)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ test (6) in 12m29s (ID 130290054462)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ test (3) in 10m46s (ID 130290054480)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ test (7) in 12m20s (ID 130290054675)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
docs: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0jNnzagAAAACIAUfqgn7wRZJeKu+MlzNMQ0gxQUEyMDMwODE0MDUyAEVkZ2U=
docs: .github#7

! Failed to restore: Cache service responded with 400
docs: .github#26

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
docs: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache/restore@v4, actions/checkout@v4, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
core-wheel: .github#2

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
core-wheel: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache@v4, actions/checkout@v4, actions/download-artifact@v4, actions/setup-go@v5, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
lint: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0gNrzagAAAADjSZJHlcfySKlfS9unohRVQ0gxQUEyMDMwODEzMDI1AEVkZ2U=
lint: .github#9

! Failed to restore: Cache service responded with 400
lint: .github#54

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
lint: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
test (1): .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0rtvzagAAAADRLyi0gj0BTpHbnj3FYzQdUEhYMzFFREdFMDUwOQBFZGdl
test (1): .github#9

! Failed to restore: Cache service responded with 400
test (1): .github#54

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
test (1): .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
test (2): .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0pdvzagAAAAB/CupxBgOHTrr4C1FsncKsQ0gxQUEyMDMwODE0MDIzAEVkZ2U=
test (2): .github#9

! Failed to restore: Cache service responded with 400
test (2): .github#54

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
test (2): .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
test (6): .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0b9zzagAAAAC/EMxsnaYhSILqDYZ23kCUUEhMMzBFREdFMDEwNgBFZGdl
test (6): .github#9

! Failed to restore: Cache service responded with 400
test (6): .github#54

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
test (6): .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
test (3): .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0CdzzagAAAADBIf8TA4b3Q53AcIg0YByEUEhMMzBFREdFMDIyMQBFZGdl
test (3): .github#9

! Failed to restore: Cache service responded with 400
test (3): .github#54

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
test (3): .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
test (7): .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0ZtzzagAAAABTWAmbze4sQLoCh3xe7u8+UEhMMzBFREdFMDQwOABFZGdl
test (7): .github#9

! Failed to restore: Cache service responded with 400
test (7): .github#54

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
test (7): .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* master Full CI · 42942621559
Triggered via schedule about 1 hour ago

JOBS
✓ full / prepare in 20s (ID 130267805007)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Validate qualification inputs
  - Download the sealed candidate manifest
  - Bind published identity from the sealed manifest
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
- full / docs-build (ID 130267806591)
- full / release-core-floor-smoke (ID 130267806613)
✓ full / build-core / build-core in 10m46s (ID 130267944892)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Resolve core mode
  ✓ Resolve pinned Rust core revision
  ✓ Check out Rust core
  - Check out published Rust core tag
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up Rust
  ✓ Cache Rust build
  ✓ Build abi3 Rust core wheel
  - Download the sealed candidate manifest
  - Fetch and verify the published core wheel
  ✓ Build macro LSP
  ✓ Record wheel provenance
  - Record published tag provenance
  ✓ Upload Rust core artifacts
  ✓ Post Cache Rust build
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Check out Rust core
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ full / perf-floors in 8m57s (ID 130272098957)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Health check (Rust extension loadable)
  ✓ Run slow tests
  ✓ Run Phase 7E regression floor
  ✓ Upload Phase 7E floor-check report
  ✓ Run launch regression floor
  ✓ Upload launch floor-check report
  ✓ Run view-hints regression floor
  ✓ Upload view-hints floor-check report
  ✓ Run agents disk-load operation-count floor
  ✓ Upload agents disk-load floor-check report
  ✓ Run plugins catalog-scale regression floor
  ✓ Upload plugins catalog-scale floor-check report
  ✓ Run bead performance smoke
  ✓ Upload bead performance smoke
  ✓ Run bead scaled-corpus benchmark (record-only 4x)
  ✓ Upload bead scaled-corpus benchmark
  ✓ Run bead history-independence gate (1x+4x)
  ✓ Upload bead history-independence gate report
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ full / visual-test in 29m4s (ID 130272098967)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  ✓ Check TUI screenshots
  ✓ Locate visual report
  - Build visual report
  - Upload visual report
  - Publish visual report
  ✓ Publish unstable recapture summary
  ✓ Upload first-attempt diffs
  - Upload visual artifacts
  ✓ Post Install visual dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ full / lint in 6m1s (ID 130272098968)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  - Run astral-sh/setup-uv@v4
  - Set up preflight Python
  - Download Rust core artifacts for bindings preflight
  - Preflight core bindings
  ✓ Install dependencies
  ✓ Check pinned core bindings
  ✓ Bootstrap SDD sidecars
  ✓ Initialize SASE home
  ✓ Run actions/setup-go@v5
  ✓ Cache Go binaries
  - Install Go tools (keep-sorted)
  ✓ Cache Prettier dependencies
  ✓ Check Python formatting
  ✓ Check Markdown formatting
  ✓ Check generated model docs
  ✓ Check shipped model policy
  ✓ Lint
  ✓ SASE validation
  ✓ Validate committed plans
  ✓ Build and verify package
  ✓ Record installed core version
  ✓ Write qualification evidence
  ✓ Upload qualification evidence
  ✓ Post Cache Prettier dependencies
  ✓ Post Cache Go binaries
  ✓ Post Run actions/setup-go@v5
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ full / tutorial-tests in 47s (ID 130272098977)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run tutorial tests
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ full / ace-page-group-isolation in 1m38s (ID 130272099121)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  ✓ Run ACE shared-page isolation lane
  ✓ Post Install visual dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ full / test (3.14) in 54m47s (ID 130272099129)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  - Run tests (coverage leg)
  ✓ Run tests
  ✓ Build shard timings table
  ✓ Upload shard timings
  - Upload coverage
  ✓ Record installed core version
  ✓ Write qualification evidence
  ✓ Upload qualification evidence
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* full / test (3.12) (ID 130272099179)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run tests (coverage leg)
  * Run tests
  * Build shard timings table
  * Upload shard timings
  * Upload coverage
  * Record installed core version
  * Write qualification evidence
  * Upload qualification evidence
  * Post Install dependencies
  * Post Run actions/checkout@v4
✓ full / test (3.13) in 49m12s (ID 130272099254)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  - Run tests (coverage leg)
  ✓ Run tests
  - Build shard timings table
  - Upload shard timings
  - Upload coverage
  ✓ Record installed core version
  ✓ Write qualification evidence
  ✓ Upload qualification evidence
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / prepare: .github#6

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / prepare: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / build-core / build-core: .github#4

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0J87zagAAAABthIK09aOAQYcgffFQ6MzhUEhYMzFFREdFMDYwNwBFZGdl
full / build-core / build-core: .github#7

! Failed to restore: Cache service responded with 400
full / build-core / build-core: .github#25

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / build-core / build-core: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / perf-floors: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0RNDzagAAAACfzCX56wkqQ6jV9SYuxRFgQ0gxQUEyMDMwODEzMDI1AEVkZ2U=
full / perf-floors: .github#9

! Failed to restore: Cache service responded with 400
full / perf-floors: .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / perf-floors: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / visual-test: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0+tTzagAAAABc4gQFoMSBSrtQjz00UkYjU0xDMzFFREdFMDgwNwBFZGdl
full / visual-test: .github#9

! Failed to restore: Cache service responded with 400
full / visual-test: .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / visual-test: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache@v4, actions/checkout@v4, actions/download-artifact@v4, actions/setup-go@v5, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / lint: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0lM/zagAAAAB3yQS/CMfFSJiRrt73gm5UUEhMMzBFREdFMDExNwBFZGdl
full / lint: .github#9

! Failed to restore: Cache service responded with 400
full / lint: .github#46

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / lint: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / tutorial-tests: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0Ws7zagAAAAAO39hx6gJHS7Q8Dow5F+0zQ0gxQUEyMDMwODEzMDMxAEVkZ2U=
full / tutorial-tests: .github#9

! Failed to restore: Cache service responded with 400
full / tutorial-tests: .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / tutorial-tests: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / ace-page-group-isolation: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0jM7zagAAAADMyRcszfEMQJA/QgihOY4oU1RCRURHRTAyMTQARWRnZQ==
full / ace-page-group-isolation: .github#9

! Failed to restore: Cache service responded with 400
full / ace-page-group-isolation: .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / ace-page-group-isolation: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / test (3.14): .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0AdvzagAAAACYlWXYox4pQp3F1ZNvSrsGQ08xRURHRTE0MTIARWRnZQ==
full / test (3.14): .github#9

! Failed to restore: Cache service responded with 400
full / test (3.14): .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / test (3.14): .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / test (3.13): .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0stnzagAAAAC/2v8ls11RTbuuPQLnkuvuU1RCRURHRTA2MTAARWRnZQ==
full / test (3.13): .github#9

! Failed to restore: Cache service responded with 400
full / test (3.13): .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / test (3.13): .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* master Full CI · 42942621559
Triggered via schedule about 1 hour ago

JOBS
✓ full / prepare in 20s (ID 130267805007)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Validate qualification inputs
  - Download the sealed candidate manifest
  - Bind published identity from the sealed manifest
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
- full / docs-build (ID 130267806591)
- full / release-core-floor-smoke (ID 130267806613)
✓ full / build-core / build-core in 10m46s (ID 130267944892)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Resolve core mode
  ✓ Resolve pinned Rust core revision
  ✓ Check out Rust core
  - Check out published Rust core tag
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up Rust
  ✓ Cache Rust build
  ✓ Build abi3 Rust core wheel
  - Download the sealed candidate manifest
  - Fetch and verify the published core wheel
  ✓ Build macro LSP
  ✓ Record wheel provenance
  - Record published tag provenance
  ✓ Upload Rust core artifacts
  ✓ Post Cache Rust build
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Check out Rust core
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ full / perf-floors in 8m57s (ID 130272098957)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Health check (Rust extension loadable)
  ✓ Run slow tests
  ✓ Run Phase 7E regression floor
  ✓ Upload Phase 7E floor-check report
  ✓ Run launch regression floor
  ✓ Upload launch floor-check report
  ✓ Run view-hints regression floor
  ✓ Upload view-hints floor-check report
  ✓ Run agents disk-load operation-count floor
  ✓ Upload agents disk-load floor-check report
  ✓ Run plugins catalog-scale regression floor
  ✓ Upload plugins catalog-scale floor-check report
  ✓ Run bead performance smoke
  ✓ Upload bead performance smoke
  ✓ Run bead scaled-corpus benchmark (record-only 4x)
  ✓ Upload bead scaled-corpus benchmark
  ✓ Run bead history-independence gate (1x+4x)
  ✓ Upload bead history-independence gate report
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ full / visual-test in 29m4s (ID 130272098967)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  ✓ Check TUI screenshots
  ✓ Locate visual report
  - Build visual report
  - Upload visual report
  - Publish visual report
  ✓ Publish unstable recapture summary
  ✓ Upload first-attempt diffs
  - Upload visual artifacts
  ✓ Post Install visual dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ full / lint in 6m1s (ID 130272098968)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  - Run astral-sh/setup-uv@v4
  - Set up preflight Python
  - Download Rust core artifacts for bindings preflight
  - Preflight core bindings
  ✓ Install dependencies
  ✓ Check pinned core bindings
  ✓ Bootstrap SDD sidecars
  ✓ Initialize SASE home
  ✓ Run actions/setup-go@v5
  ✓ Cache Go binaries
  - Install Go tools (keep-sorted)
  ✓ Cache Prettier dependencies
  ✓ Check Python formatting
  ✓ Check Markdown formatting
  ✓ Check generated model docs
  ✓ Check shipped model policy
  ✓ Lint
  ✓ SASE validation
  ✓ Validate committed plans
  ✓ Build and verify package
  ✓ Record installed core version
  ✓ Write qualification evidence
  ✓ Upload qualification evidence
  ✓ Post Cache Prettier dependencies
  ✓ Post Cache Go binaries
  ✓ Post Run actions/setup-go@v5
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ full / tutorial-tests in 47s (ID 130272098977)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run tutorial tests
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ full / ace-page-group-isolation in 1m38s (ID 130272099121)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  ✓ Run ACE shared-page isolation lane
  ✓ Post Install visual dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ full / test (3.14) in 54m47s (ID 130272099129)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  - Run tests (coverage leg)
  ✓ Run tests
  ✓ Build shard timings table
  ✓ Upload shard timings
  - Upload coverage
  ✓ Record installed core version
  ✓ Write qualification evidence
  ✓ Upload qualification evidence
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* full / test (3.12) (ID 130272099179)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run tests (coverage leg)
  * Run tests
  * Build shard timings table
  * Upload shard timings
  * Upload coverage
  * Record installed core version
  * Write qualification evidence
  * Upload qualification evidence
  * Post Install dependencies
  * Post Run actions/checkout@v4
✓ full / test (3.13) in 49m12s (ID 130272099254)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  - Run tests (coverage leg)
  ✓ Run tests
  - Build shard timings table
  - Upload shard timings
  - Upload coverage
  ✓ Record installed core version
  ✓ Write qualification evidence
  ✓ Upload qualification evidence
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / prepare: .github#6

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / prepare: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / build-core / build-core: .github#4

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0J87zagAAAABthIK09aOAQYcgffFQ6MzhUEhYMzFFREdFMDYwNwBFZGdl
full / build-core / build-core: .github#7

! Failed to restore: Cache service responded with 400
full / build-core / build-core: .github#25

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / build-core / build-core: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / perf-floors: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0RNDzagAAAACfzCX56wkqQ6jV9SYuxRFgQ0gxQUEyMDMwODEzMDI1AEVkZ2U=
full / perf-floors: .github#9

! Failed to restore: Cache service responded with 400
full / perf-floors: .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / perf-floors: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / visual-test: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0+tTzagAAAABc4gQFoMSBSrtQjz00UkYjU0xDMzFFREdFMDgwNwBFZGdl
full / visual-test: .github#9

! Failed to restore: Cache service responded with 400
full / visual-test: .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / visual-test: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache@v4, actions/checkout@v4, actions/download-artifact@v4, actions/setup-go@v5, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / lint: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0lM/zagAAAAB3yQS/CMfFSJiRrt73gm5UUEhMMzBFREdFMDExNwBFZGdl
full / lint: .github#9

! Failed to restore: Cache service responded with 400
full / lint: .github#46

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / lint: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / tutorial-tests: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0Ws7zagAAAAAO39hx6gJHS7Q8Dow5F+0zQ0gxQUEyMDMwODEzMDMxAEVkZ2U=
full / tutorial-tests: .github#9

! Failed to restore: Cache service responded with 400
full / tutorial-tests: .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / tutorial-tests: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / ace-page-group-isolation: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0jM7zagAAAADMyRcszfEMQJA/QgihOY4oU1RCRURHRTAyMTQARWRnZQ==
full / ace-page-group-isolation: .github#9

! Failed to restore: Cache service responded with 400
full / ace-page-group-isolation: .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / ace-page-group-isolation: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / test (3.14): .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0AdvzagAAAACYlWXYox4pQp3F1ZNvSrsGQ08xRURHRTE0MTIARWRnZQ==
full / test (3.14): .github#9

! Failed to restore: Cache service responded with 400
full / test (3.14): .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / test (3.14): .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / test (3.13): .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0stnzagAAAAC/2v8ls11RTbuuPQLnkuvuU1RCRURHRTA2MTAARWRnZQ==
full / test (3.13): .github#9

! Failed to restore: Cache service responded with 400
full / test (3.13): .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / test (3.13): .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* master Full CI · 42942621559
Triggered via schedule about 1 hour ago

JOBS
✓ full / prepare in 20s (ID 130267805007)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Validate qualification inputs
  - Download the sealed candidate manifest
  - Bind published identity from the sealed manifest
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
- full / docs-build (ID 130267806591)
- full / release-core-floor-smoke (ID 130267806613)
✓ full / build-core / build-core in 10m46s (ID 130267944892)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Resolve core mode
  ✓ Resolve pinned Rust core revision
  ✓ Check out Rust core
  - Check out published Rust core tag
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up Rust
  ✓ Cache Rust build
  ✓ Build abi3 Rust core wheel
  - Download the sealed candidate manifest
  - Fetch and verify the published core wheel
  ✓ Build macro LSP
  ✓ Record wheel provenance
  - Record published tag provenance
  ✓ Upload Rust core artifacts
  ✓ Post Cache Rust build
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Check out Rust core
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ full / perf-floors in 8m57s (ID 130272098957)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Health check (Rust extension loadable)
  ✓ Run slow tests
  ✓ Run Phase 7E regression floor
  ✓ Upload Phase 7E floor-check report
  ✓ Run launch regression floor
  ✓ Upload launch floor-check report
  ✓ Run view-hints regression floor
  ✓ Upload view-hints floor-check report
  ✓ Run agents disk-load operation-count floor
  ✓ Upload agents disk-load floor-check report
  ✓ Run plugins catalog-scale regression floor
  ✓ Upload plugins catalog-scale floor-check report
  ✓ Run bead performance smoke
  ✓ Upload bead performance smoke
  ✓ Run bead scaled-corpus benchmark (record-only 4x)
  ✓ Upload bead scaled-corpus benchmark
  ✓ Run bead history-independence gate (1x+4x)
  ✓ Upload bead history-independence gate report
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ full / visual-test in 29m4s (ID 130272098967)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  ✓ Check TUI screenshots
  ✓ Locate visual report
  - Build visual report
  - Upload visual report
  - Publish visual report
  ✓ Publish unstable recapture summary
  ✓ Upload first-attempt diffs
  - Upload visual artifacts
  ✓ Post Install visual dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ full / lint in 6m1s (ID 130272098968)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  - Run astral-sh/setup-uv@v4
  - Set up preflight Python
  - Download Rust core artifacts for bindings preflight
  - Preflight core bindings
  ✓ Install dependencies
  ✓ Check pinned core bindings
  ✓ Bootstrap SDD sidecars
  ✓ Initialize SASE home
  ✓ Run actions/setup-go@v5
  ✓ Cache Go binaries
  - Install Go tools (keep-sorted)
  ✓ Cache Prettier dependencies
  ✓ Check Python formatting
  ✓ Check Markdown formatting
  ✓ Check generated model docs
  ✓ Check shipped model policy
  ✓ Lint
  ✓ SASE validation
  ✓ Validate committed plans
  ✓ Build and verify package
  ✓ Record installed core version
  ✓ Write qualification evidence
  ✓ Upload qualification evidence
  ✓ Post Cache Prettier dependencies
  ✓ Post Cache Go binaries
  ✓ Post Run actions/setup-go@v5
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ full / tutorial-tests in 47s (ID 130272098977)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run tutorial tests
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ full / ace-page-group-isolation in 1m38s (ID 130272099121)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  ✓ Run ACE shared-page isolation lane
  ✓ Post Install visual dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ full / test (3.14) in 54m47s (ID 130272099129)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  - Run tests (coverage leg)
  ✓ Run tests
  ✓ Build shard timings table
  ✓ Upload shard timings
  - Upload coverage
  ✓ Record installed core version
  ✓ Write qualification evidence
  ✓ Upload qualification evidence
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* full / test (3.12) (ID 130272099179)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run tests (coverage leg)
  * Run tests
  * Build shard timings table
  * Upload shard timings
  * Upload coverage
  * Record installed core version
  * Write qualification evidence
  * Upload qualification evidence
  * Post Install dependencies
  * Post Run actions/checkout@v4
✓ full / test (3.13) in 49m12s (ID 130272099254)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  - Run tests (coverage leg)
  ✓ Run tests
  - Build shard timings table
  - Upload shard timings
  - Upload coverage
  ✓ Record installed core version
  ✓ Write qualification evidence
  ✓ Upload qualification evidence
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / prepare: .github#6

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / prepare: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / build-core / build-core: .github#4

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0J87zagAAAABthIK09aOAQYcgffFQ6MzhUEhYMzFFREdFMDYwNwBFZGdl
full / build-core / build-core: .github#7

! Failed to restore: Cache service responded with 400
full / build-core / build-core: .github#25

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / build-core / build-core: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / perf-floors: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0RNDzagAAAACfzCX56wkqQ6jV9SYuxRFgQ0gxQUEyMDMwODEzMDI1AEVkZ2U=
full / perf-floors: .github#9

! Failed to restore: Cache service responded with 400
full / perf-floors: .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / perf-floors: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / visual-test: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0+tTzagAAAABc4gQFoMSBSrtQjz00UkYjU0xDMzFFREdFMDgwNwBFZGdl
full / visual-test: .github#9

! Failed to restore: Cache service responded with 400
full / visual-test: .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / visual-test: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache@v4, actions/checkout@v4, actions/download-artifact@v4, actions/setup-go@v5, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / lint: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0lM/zagAAAAB3yQS/CMfFSJiRrt73gm5UUEhMMzBFREdFMDExNwBFZGdl
full / lint: .github#9

! Failed to restore: Cache service responded with 400
full / lint: .github#46

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / lint: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / tutorial-tests: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0Ws7zagAAAAAO39hx6gJHS7Q8Dow5F+0zQ0gxQUEyMDMwODEzMDMxAEVkZ2U=
full / tutorial-tests: .github#9

! Failed to restore: Cache service responded with 400
full / tutorial-tests: .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / tutorial-tests: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / ace-page-group-isolation: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0jM7zagAAAADMyRcszfEMQJA/QgihOY4oU1RCRURHRTAyMTQARWRnZQ==
full / ace-page-group-isolation: .github#9

! Failed to restore: Cache service responded with 400
full / ace-page-group-isolation: .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / ace-page-group-isolation: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / test (3.14): .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0AdvzagAAAACYlWXYox4pQp3F1ZNvSrsGQ08xRURHRTE0MTIARWRnZQ==
full / test (3.14): .github#9

! Failed to restore: Cache service responded with 400
full / test (3.14): .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / test (3.14): .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / test (3.13): .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0stnzagAAAAC/2v8ls11RTbuuPQLnkuvuU1RCRURHRTA2MTAARWRnZQ==
full / test (3.13): .github#9

! Failed to restore: Cache service responded with 400
full / test (3.13): .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / test (3.13): .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* master Full CI · 42942621559
Triggered via schedule about 1 hour ago

JOBS
✓ full / prepare in 20s (ID 130267805007)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Validate qualification inputs
  - Download the sealed candidate manifest
  - Bind published identity from the sealed manifest
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
- full / docs-build (ID 130267806591)
- full / release-core-floor-smoke (ID 130267806613)
✓ full / build-core / build-core in 10m46s (ID 130267944892)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Resolve core mode
  ✓ Resolve pinned Rust core revision
  ✓ Check out Rust core
  - Check out published Rust core tag
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up Rust
  ✓ Cache Rust build
  ✓ Build abi3 Rust core wheel
  - Download the sealed candidate manifest
  - Fetch and verify the published core wheel
  ✓ Build macro LSP
  ✓ Record wheel provenance
  - Record published tag provenance
  ✓ Upload Rust core artifacts
  ✓ Post Cache Rust build
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Check out Rust core
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ full / perf-floors in 8m57s (ID 130272098957)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Health check (Rust extension loadable)
  ✓ Run slow tests
  ✓ Run Phase 7E regression floor
  ✓ Upload Phase 7E floor-check report
  ✓ Run launch regression floor
  ✓ Upload launch floor-check report
  ✓ Run view-hints regression floor
  ✓ Upload view-hints floor-check report
  ✓ Run agents disk-load operation-count floor
  ✓ Upload agents disk-load floor-check report
  ✓ Run plugins catalog-scale regression floor
  ✓ Upload plugins catalog-scale floor-check report
  ✓ Run bead performance smoke
  ✓ Upload bead performance smoke
  ✓ Run bead scaled-corpus benchmark (record-only 4x)
  ✓ Upload bead scaled-corpus benchmark
  ✓ Run bead history-independence gate (1x+4x)
  ✓ Upload bead history-independence gate report
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ full / visual-test in 29m4s (ID 130272098967)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  ✓ Check TUI screenshots
  ✓ Locate visual report
  - Build visual report
  - Upload visual report
  - Publish visual report
  ✓ Publish unstable recapture summary
  ✓ Upload first-attempt diffs
  - Upload visual artifacts
  ✓ Post Install visual dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ full / lint in 6m1s (ID 130272098968)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  - Run astral-sh/setup-uv@v4
  - Set up preflight Python
  - Download Rust core artifacts for bindings preflight
  - Preflight core bindings
  ✓ Install dependencies
  ✓ Check pinned core bindings
  ✓ Bootstrap SDD sidecars
  ✓ Initialize SASE home
  ✓ Run actions/setup-go@v5
  ✓ Cache Go binaries
  - Install Go tools (keep-sorted)
  ✓ Cache Prettier dependencies
  ✓ Check Python formatting
  ✓ Check Markdown formatting
  ✓ Check generated model docs
  ✓ Check shipped model policy
  ✓ Lint
  ✓ SASE validation
  ✓ Validate committed plans
  ✓ Build and verify package
  ✓ Record installed core version
  ✓ Write qualification evidence
  ✓ Upload qualification evidence
  ✓ Post Cache Prettier dependencies
  ✓ Post Cache Go binaries
  ✓ Post Run actions/setup-go@v5
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ full / tutorial-tests in 47s (ID 130272098977)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run tutorial tests
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ full / ace-page-group-isolation in 1m38s (ID 130272099121)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  ✓ Run ACE shared-page isolation lane
  ✓ Post Install visual dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ full / test (3.14) in 54m47s (ID 130272099129)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  - Run tests (coverage leg)
  ✓ Run tests
  ✓ Build shard timings table
  ✓ Upload shard timings
  - Upload coverage
  ✓ Record installed core version
  ✓ Write qualification evidence
  ✓ Upload qualification evidence
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* full / test (3.12) (ID 130272099179)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run tests (coverage leg)
  * Run tests
  * Build shard timings table
  * Upload shard timings
  * Upload coverage
  * Record installed core version
  * Write qualification evidence
  * Upload qualification evidence
  * Post Install dependencies
  * Post Run actions/checkout@v4
✓ full / test (3.13) in 49m12s (ID 130272099254)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  - Run tests (coverage leg)
  ✓ Run tests
  - Build shard timings table
  - Upload shard timings
  - Upload coverage
  ✓ Record installed core version
  ✓ Write qualification evidence
  ✓ Upload qualification evidence
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / prepare: .github#6

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / prepare: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / build-core / build-core: .github#4

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0J87zagAAAABthIK09aOAQYcgffFQ6MzhUEhYMzFFREdFMDYwNwBFZGdl
full / build-core / build-core: .github#7

! Failed to restore: Cache service responded with 400
full / build-core / build-core: .github#25

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / build-core / build-core: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / perf-floors: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0RNDzagAAAACfzCX56wkqQ6jV9SYuxRFgQ0gxQUEyMDMwODEzMDI1AEVkZ2U=
full / perf-floors: .github#9

! Failed to restore: Cache service responded with 400
full / perf-floors: .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / perf-floors: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / visual-test: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0+tTzagAAAABc4gQFoMSBSrtQjz00UkYjU0xDMzFFREdFMDgwNwBFZGdl
full / visual-test: .github#9

! Failed to restore: Cache service responded with 400
full / visual-test: .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / visual-test: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache@v4, actions/checkout@v4, actions/download-artifact@v4, actions/setup-go@v5, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / lint: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0lM/zagAAAAB3yQS/CMfFSJiRrt73gm5UUEhMMzBFREdFMDExNwBFZGdl
full / lint: .github#9

! Failed to restore: Cache service responded with 400
full / lint: .github#46

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / lint: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / tutorial-tests: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0Ws7zagAAAAAO39hx6gJHS7Q8Dow5F+0zQ0gxQUEyMDMwODEzMDMxAEVkZ2U=
full / tutorial-tests: .github#9

! Failed to restore: Cache service responded with 400
full / tutorial-tests: .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / tutorial-tests: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / ace-page-group-isolation: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0jM7zagAAAADMyRcszfEMQJA/QgihOY4oU1RCRURHRTAyMTQARWRnZQ==
full / ace-page-group-isolation: .github#9

! Failed to restore: Cache service responded with 400
full / ace-page-group-isolation: .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / ace-page-group-isolation: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / test (3.14): .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0AdvzagAAAACYlWXYox4pQp3F1ZNvSrsGQ08xRURHRTE0MTIARWRnZQ==
full / test (3.14): .github#9

! Failed to restore: Cache service responded with 400
full / test (3.14): .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / test (3.14): .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / test (3.13): .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0stnzagAAAAC/2v8ls11RTbuuPQLnkuvuU1RCRURHRTA2MTAARWRnZQ==
full / test (3.13): .github#9

! Failed to restore: Cache service responded with 400
full / test (3.13): .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / test (3.13): .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* master Full CI · 42942621559
Triggered via schedule about 1 hour ago

JOBS
✓ full / prepare in 20s (ID 130267805007)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Validate qualification inputs
  - Download the sealed candidate manifest
  - Bind published identity from the sealed manifest
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
- full / docs-build (ID 130267806591)
- full / release-core-floor-smoke (ID 130267806613)
✓ full / build-core / build-core in 10m46s (ID 130267944892)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Resolve core mode
  ✓ Resolve pinned Rust core revision
  ✓ Check out Rust core
  - Check out published Rust core tag
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up Rust
  ✓ Cache Rust build
  ✓ Build abi3 Rust core wheel
  - Download the sealed candidate manifest
  - Fetch and verify the published core wheel
  ✓ Build macro LSP
  ✓ Record wheel provenance
  - Record published tag provenance
  ✓ Upload Rust core artifacts
  ✓ Post Cache Rust build
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Check out Rust core
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ full / perf-floors in 8m57s (ID 130272098957)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Health check (Rust extension loadable)
  ✓ Run slow tests
  ✓ Run Phase 7E regression floor
  ✓ Upload Phase 7E floor-check report
  ✓ Run launch regression floor
  ✓ Upload launch floor-check report
  ✓ Run view-hints regression floor
  ✓ Upload view-hints floor-check report
  ✓ Run agents disk-load operation-count floor
  ✓ Upload agents disk-load floor-check report
  ✓ Run plugins catalog-scale regression floor
  ✓ Upload plugins catalog-scale floor-check report
  ✓ Run bead performance smoke
  ✓ Upload bead performance smoke
  ✓ Run bead scaled-corpus benchmark (record-only 4x)
  ✓ Upload bead scaled-corpus benchmark
  ✓ Run bead history-independence gate (1x+4x)
  ✓ Upload bead history-independence gate report
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ full / visual-test in 29m4s (ID 130272098967)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  ✓ Check TUI screenshots
  ✓ Locate visual report
  - Build visual report
  - Upload visual report
  - Publish visual report
  ✓ Publish unstable recapture summary
  ✓ Upload first-attempt diffs
  - Upload visual artifacts
  ✓ Post Install visual dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ full / lint in 6m1s (ID 130272098968)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  - Run astral-sh/setup-uv@v4
  - Set up preflight Python
  - Download Rust core artifacts for bindings preflight
  - Preflight core bindings
  ✓ Install dependencies
  ✓ Check pinned core bindings
  ✓ Bootstrap SDD sidecars
  ✓ Initialize SASE home
  ✓ Run actions/setup-go@v5
  ✓ Cache Go binaries
  - Install Go tools (keep-sorted)
  ✓ Cache Prettier dependencies
  ✓ Check Python formatting
  ✓ Check Markdown formatting
  ✓ Check generated model docs
  ✓ Check shipped model policy
  ✓ Lint
  ✓ SASE validation
  ✓ Validate committed plans
  ✓ Build and verify package
  ✓ Record installed core version
  ✓ Write qualification evidence
  ✓ Upload qualification evidence
  ✓ Post Cache Prettier dependencies
  ✓ Post Cache Go binaries
  ✓ Post Run actions/setup-go@v5
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ full / tutorial-tests in 47s (ID 130272098977)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run tutorial tests
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ full / ace-page-group-isolation in 1m38s (ID 130272099121)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  ✓ Run ACE shared-page isolation lane
  ✓ Post Install visual dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ full / test (3.14) in 54m47s (ID 130272099129)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  - Run tests (coverage leg)
  ✓ Run tests
  ✓ Build shard timings table
  ✓ Upload shard timings
  - Upload coverage
  ✓ Record installed core version
  ✓ Write qualification evidence
  ✓ Upload qualification evidence
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* full / test (3.12) (ID 130272099179)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run tests (coverage leg)
  * Run tests
  * Build shard timings table
  * Upload shard timings
  * Upload coverage
  * Record installed core version
  * Write qualification evidence
  * Upload qualification evidence
  * Post Install dependencies
  * Post Run actions/checkout@v4
✓ full / test (3.13) in 49m12s (ID 130272099254)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  - Run tests (coverage leg)
  ✓ Run tests
  - Build shard timings table
  - Upload shard timings
  - Upload coverage
  ✓ Record installed core version
  ✓ Write qualification evidence
  ✓ Upload qualification evidence
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / prepare: .github#6

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / prepare: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / build-core / build-core: .github#4

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0J87zagAAAABthIK09aOAQYcgffFQ6MzhUEhYMzFFREdFMDYwNwBFZGdl
full / build-core / build-core: .github#7

! Failed to restore: Cache service responded with 400
full / build-core / build-core: .github#25

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / build-core / build-core: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / perf-floors: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0RNDzagAAAACfzCX56wkqQ6jV9SYuxRFgQ0gxQUEyMDMwODEzMDI1AEVkZ2U=
full / perf-floors: .github#9

! Failed to restore: Cache service responded with 400
full / perf-floors: .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / perf-floors: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / visual-test: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0+tTzagAAAABc4gQFoMSBSrtQjz00UkYjU0xDMzFFREdFMDgwNwBFZGdl
full / visual-test: .github#9

! Failed to restore: Cache service responded with 400
full / visual-test: .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / visual-test: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache@v4, actions/checkout@v4, actions/download-artifact@v4, actions/setup-go@v5, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / lint: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0lM/zagAAAAB3yQS/CMfFSJiRrt73gm5UUEhMMzBFREdFMDExNwBFZGdl
full / lint: .github#9

! Failed to restore: Cache service responded with 400
full / lint: .github#46

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / lint: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / tutorial-tests: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0Ws7zagAAAAAO39hx6gJHS7Q8Dow5F+0zQ0gxQUEyMDMwODEzMDMxAEVkZ2U=
full / tutorial-tests: .github#9

! Failed to restore: Cache service responded with 400
full / tutorial-tests: .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / tutorial-tests: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / ace-page-group-isolation: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0jM7zagAAAADMyRcszfEMQJA/QgihOY4oU1RCRURHRTAyMTQARWRnZQ==
full / ace-page-group-isolation: .github#9

! Failed to restore: Cache service responded with 400
full / ace-page-group-isolation: .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / ace-page-group-isolation: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / test (3.14): .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0AdvzagAAAACYlWXYox4pQp3F1ZNvSrsGQ08xRURHRTE0MTIARWRnZQ==
full / test (3.14): .github#9

! Failed to restore: Cache service responded with 400
full / test (3.14): .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / test (3.14): .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / test (3.13): .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0stnzagAAAAC/2v8ls11RTbuuPQLnkuvuU1RCRURHRTA2MTAARWRnZQ==
full / test (3.13): .github#9

! Failed to restore: Cache service responded with 400
full / test (3.13): .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / test (3.13): .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* master Full CI · 42942621559
Triggered via schedule about 1 hour ago

JOBS
✓ full / prepare in 20s (ID 130267805007)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Validate qualification inputs
  - Download the sealed candidate manifest
  - Bind published identity from the sealed manifest
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
- full / docs-build (ID 130267806591)
- full / release-core-floor-smoke (ID 130267806613)
✓ full / build-core / build-core in 10m46s (ID 130267944892)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Resolve core mode
  ✓ Resolve pinned Rust core revision
  ✓ Check out Rust core
  - Check out published Rust core tag
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up Rust
  ✓ Cache Rust build
  ✓ Build abi3 Rust core wheel
  - Download the sealed candidate manifest
  - Fetch and verify the published core wheel
  ✓ Build macro LSP
  ✓ Record wheel provenance
  - Record published tag provenance
  ✓ Upload Rust core artifacts
  ✓ Post Cache Rust build
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Check out Rust core
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ full / perf-floors in 8m57s (ID 130272098957)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Health check (Rust extension loadable)
  ✓ Run slow tests
  ✓ Run Phase 7E regression floor
  ✓ Upload Phase 7E floor-check report
  ✓ Run launch regression floor
  ✓ Upload launch floor-check report
  ✓ Run view-hints regression floor
  ✓ Upload view-hints floor-check report
  ✓ Run agents disk-load operation-count floor
  ✓ Upload agents disk-load floor-check report
  ✓ Run plugins catalog-scale regression floor
  ✓ Upload plugins catalog-scale floor-check report
  ✓ Run bead performance smoke
  ✓ Upload bead performance smoke
  ✓ Run bead scaled-corpus benchmark (record-only 4x)
  ✓ Upload bead scaled-corpus benchmark
  ✓ Run bead history-independence gate (1x+4x)
  ✓ Upload bead history-independence gate report
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ full / visual-test in 29m4s (ID 130272098967)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  ✓ Check TUI screenshots
  ✓ Locate visual report
  - Build visual report
  - Upload visual report
  - Publish visual report
  ✓ Publish unstable recapture summary
  ✓ Upload first-attempt diffs
  - Upload visual artifacts
  ✓ Post Install visual dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ full / lint in 6m1s (ID 130272098968)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  - Run astral-sh/setup-uv@v4
  - Set up preflight Python
  - Download Rust core artifacts for bindings preflight
  - Preflight core bindings
  ✓ Install dependencies
  ✓ Check pinned core bindings
  ✓ Bootstrap SDD sidecars
  ✓ Initialize SASE home
  ✓ Run actions/setup-go@v5
  ✓ Cache Go binaries
  - Install Go tools (keep-sorted)
  ✓ Cache Prettier dependencies
  ✓ Check Python formatting
  ✓ Check Markdown formatting
  ✓ Check generated model docs
  ✓ Check shipped model policy
  ✓ Lint
  ✓ SASE validation
  ✓ Validate committed plans
  ✓ Build and verify package
  ✓ Record installed core version
  ✓ Write qualification evidence
  ✓ Upload qualification evidence
  ✓ Post Cache Prettier dependencies
  ✓ Post Cache Go binaries
  ✓ Post Run actions/setup-go@v5
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ full / tutorial-tests in 47s (ID 130272098977)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run tutorial tests
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ full / ace-page-group-isolation in 1m38s (ID 130272099121)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  ✓ Run ACE shared-page isolation lane
  ✓ Post Install visual dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ full / test (3.14) in 54m47s (ID 130272099129)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  - Run tests (coverage leg)
  ✓ Run tests
  ✓ Build shard timings table
  ✓ Upload shard timings
  - Upload coverage
  ✓ Record installed core version
  ✓ Write qualification evidence
  ✓ Upload qualification evidence
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* full / test (3.12) (ID 130272099179)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run tests (coverage leg)
  * Run tests
  * Build shard timings table
  * Upload shard timings
  * Upload coverage
  * Record installed core version
  * Write qualification evidence
  * Upload qualification evidence
  * Post Install dependencies
  * Post Run actions/checkout@v4
✓ full / test (3.13) in 49m12s (ID 130272099254)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  - Run tests (coverage leg)
  ✓ Run tests
  - Build shard timings table
  - Upload shard timings
  - Upload coverage
  ✓ Record installed core version
  ✓ Write qualification evidence
  ✓ Upload qualification evidence
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / prepare: .github#6

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / prepare: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / build-core / build-core: .github#4

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0J87zagAAAABthIK09aOAQYcgffFQ6MzhUEhYMzFFREdFMDYwNwBFZGdl
full / build-core / build-core: .github#7

! Failed to restore: Cache service responded with 400
full / build-core / build-core: .github#25

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / build-core / build-core: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / perf-floors: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0RNDzagAAAACfzCX56wkqQ6jV9SYuxRFgQ0gxQUEyMDMwODEzMDI1AEVkZ2U=
full / perf-floors: .github#9

! Failed to restore: Cache service responded with 400
full / perf-floors: .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / perf-floors: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / visual-test: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0+tTzagAAAABc4gQFoMSBSrtQjz00UkYjU0xDMzFFREdFMDgwNwBFZGdl
full / visual-test: .github#9

! Failed to restore: Cache service responded with 400
full / visual-test: .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / visual-test: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache@v4, actions/checkout@v4, actions/download-artifact@v4, actions/setup-go@v5, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / lint: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0lM/zagAAAAB3yQS/CMfFSJiRrt73gm5UUEhMMzBFREdFMDExNwBFZGdl
full / lint: .github#9

! Failed to restore: Cache service responded with 400
full / lint: .github#46

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / lint: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / tutorial-tests: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0Ws7zagAAAAAO39hx6gJHS7Q8Dow5F+0zQ0gxQUEyMDMwODEzMDMxAEVkZ2U=
full / tutorial-tests: .github#9

! Failed to restore: Cache service responded with 400
full / tutorial-tests: .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / tutorial-tests: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / ace-page-group-isolation: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0jM7zagAAAADMyRcszfEMQJA/QgihOY4oU1RCRURHRTAyMTQARWRnZQ==
full / ace-page-group-isolation: .github#9

! Failed to restore: Cache service responded with 400
full / ace-page-group-isolation: .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / ace-page-group-isolation: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / test (3.14): .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0AdvzagAAAACYlWXYox4pQp3F1ZNvSrsGQ08xRURHRTE0MTIARWRnZQ==
full / test (3.14): .github#9

! Failed to restore: Cache service responded with 400
full / test (3.14): .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / test (3.14): .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / test (3.13): .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0stnzagAAAAC/2v8ls11RTbuuPQLnkuvuU1RCRURHRTA2MTAARWRnZQ==
full / test (3.13): .github#9

! Failed to restore: Cache service responded with 400
full / test (3.13): .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / test (3.13): .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* master Full CI · 42942621559
Triggered via schedule about 1 hour ago

JOBS
✓ full / prepare in 20s (ID 130267805007)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Validate qualification inputs
  - Download the sealed candidate manifest
  - Bind published identity from the sealed manifest
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
- full / docs-build (ID 130267806591)
- full / release-core-floor-smoke (ID 130267806613)
✓ full / build-core / build-core in 10m46s (ID 130267944892)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Resolve core mode
  ✓ Resolve pinned Rust core revision
  ✓ Check out Rust core
  - Check out published Rust core tag
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up Rust
  ✓ Cache Rust build
  ✓ Build abi3 Rust core wheel
  - Download the sealed candidate manifest
  - Fetch and verify the published core wheel
  ✓ Build macro LSP
  ✓ Record wheel provenance
  - Record published tag provenance
  ✓ Upload Rust core artifacts
  ✓ Post Cache Rust build
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Check out Rust core
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ full / perf-floors in 8m57s (ID 130272098957)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Health check (Rust extension loadable)
  ✓ Run slow tests
  ✓ Run Phase 7E regression floor
  ✓ Upload Phase 7E floor-check report
  ✓ Run launch regression floor
  ✓ Upload launch floor-check report
  ✓ Run view-hints regression floor
  ✓ Upload view-hints floor-check report
  ✓ Run agents disk-load operation-count floor
  ✓ Upload agents disk-load floor-check report
  ✓ Run plugins catalog-scale regression floor
  ✓ Upload plugins catalog-scale floor-check report
  ✓ Run bead performance smoke
  ✓ Upload bead performance smoke
  ✓ Run bead scaled-corpus benchmark (record-only 4x)
  ✓ Upload bead scaled-corpus benchmark
  ✓ Run bead history-independence gate (1x+4x)
  ✓ Upload bead history-independence gate report
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ full / visual-test in 29m4s (ID 130272098967)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  ✓ Check TUI screenshots
  ✓ Locate visual report
  - Build visual report
  - Upload visual report
  - Publish visual report
  ✓ Publish unstable recapture summary
  ✓ Upload first-attempt diffs
  - Upload visual artifacts
  ✓ Post Install visual dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ full / lint in 6m1s (ID 130272098968)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  - Run astral-sh/setup-uv@v4
  - Set up preflight Python
  - Download Rust core artifacts for bindings preflight
  - Preflight core bindings
  ✓ Install dependencies
  ✓ Check pinned core bindings
  ✓ Bootstrap SDD sidecars
  ✓ Initialize SASE home
  ✓ Run actions/setup-go@v5
  ✓ Cache Go binaries
  - Install Go tools (keep-sorted)
  ✓ Cache Prettier dependencies
  ✓ Check Python formatting
  ✓ Check Markdown formatting
  ✓ Check generated model docs
  ✓ Check shipped model policy
  ✓ Lint
  ✓ SASE validation
  ✓ Validate committed plans
  ✓ Build and verify package
  ✓ Record installed core version
  ✓ Write qualification evidence
  ✓ Upload qualification evidence
  ✓ Post Cache Prettier dependencies
  ✓ Post Cache Go binaries
  ✓ Post Run actions/setup-go@v5
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ full / tutorial-tests in 47s (ID 130272098977)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run tutorial tests
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ full / ace-page-group-isolation in 1m38s (ID 130272099121)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  ✓ Run ACE shared-page isolation lane
  ✓ Post Install visual dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ full / test (3.14) in 54m47s (ID 130272099129)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  - Run tests (coverage leg)
  ✓ Run tests
  ✓ Build shard timings table
  ✓ Upload shard timings
  - Upload coverage
  ✓ Record installed core version
  ✓ Write qualification evidence
  ✓ Upload qualification evidence
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* full / test (3.12) (ID 130272099179)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run tests (coverage leg)
  * Run tests
  * Build shard timings table
  * Upload shard timings
  * Upload coverage
  * Record installed core version
  * Write qualification evidence
  * Upload qualification evidence
  * Post Install dependencies
  * Post Run actions/checkout@v4
✓ full / test (3.13) in 49m12s (ID 130272099254)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  - Run tests (coverage leg)
  ✓ Run tests
  - Build shard timings table
  - Upload shard timings
  - Upload coverage
  ✓ Record installed core version
  ✓ Write qualification evidence
  ✓ Upload qualification evidence
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / prepare: .github#6

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / prepare: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / build-core / build-core: .github#4

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0J87zagAAAABthIK09aOAQYcgffFQ6MzhUEhYMzFFREdFMDYwNwBFZGdl
full / build-core / build-core: .github#7

! Failed to restore: Cache service responded with 400
full / build-core / build-core: .github#25

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / build-core / build-core: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / perf-floors: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0RNDzagAAAACfzCX56wkqQ6jV9SYuxRFgQ0gxQUEyMDMwODEzMDI1AEVkZ2U=
full / perf-floors: .github#9

! Failed to restore: Cache service responded with 400
full / perf-floors: .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / perf-floors: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / visual-test: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0+tTzagAAAABc4gQFoMSBSrtQjz00UkYjU0xDMzFFREdFMDgwNwBFZGdl
full / visual-test: .github#9

! Failed to restore: Cache service responded with 400
full / visual-test: .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / visual-test: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache@v4, actions/checkout@v4, actions/download-artifact@v4, actions/setup-go@v5, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / lint: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0lM/zagAAAAB3yQS/CMfFSJiRrt73gm5UUEhMMzBFREdFMDExNwBFZGdl
full / lint: .github#9

! Failed to restore: Cache service responded with 400
full / lint: .github#46

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / lint: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / tutorial-tests: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0Ws7zagAAAAAO39hx6gJHS7Q8Dow5F+0zQ0gxQUEyMDMwODEzMDMxAEVkZ2U=
full / tutorial-tests: .github#9

! Failed to restore: Cache service responded with 400
full / tutorial-tests: .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / tutorial-tests: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / ace-page-group-isolation: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0jM7zagAAAADMyRcszfEMQJA/QgihOY4oU1RCRURHRTAyMTQARWRnZQ==
full / ace-page-group-isolation: .github#9

! Failed to restore: Cache service responded with 400
full / ace-page-group-isolation: .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / ace-page-group-isolation: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / test (3.14): .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0AdvzagAAAACYlWXYox4pQp3F1ZNvSrsGQ08xRURHRTE0MTIARWRnZQ==
full / test (3.14): .github#9

! Failed to restore: Cache service responded with 400
full / test (3.14): .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / test (3.14): .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / test (3.13): .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0stnzagAAAAC/2v8ls11RTbuuPQLnkuvuU1RCRURHRTA2MTAARWRnZQ==
full / test (3.13): .github#9

! Failed to restore: Cache service responded with 400
full / test (3.13): .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / test (3.13): .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* master Full CI · 42942621559
Triggered via schedule about 1 hour ago

JOBS
✓ full / prepare in 20s (ID 130267805007)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Validate qualification inputs
  - Download the sealed candidate manifest
  - Bind published identity from the sealed manifest
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
- full / docs-build (ID 130267806591)
- full / release-core-floor-smoke (ID 130267806613)
✓ full / build-core / build-core in 10m46s (ID 130267944892)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Resolve core mode
  ✓ Resolve pinned Rust core revision
  ✓ Check out Rust core
  - Check out published Rust core tag
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up Rust
  ✓ Cache Rust build
  ✓ Build abi3 Rust core wheel
  - Download the sealed candidate manifest
  - Fetch and verify the published core wheel
  ✓ Build macro LSP
  ✓ Record wheel provenance
  - Record published tag provenance
  ✓ Upload Rust core artifacts
  ✓ Post Cache Rust build
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Check out Rust core
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ full / perf-floors in 8m57s (ID 130272098957)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Health check (Rust extension loadable)
  ✓ Run slow tests
  ✓ Run Phase 7E regression floor
  ✓ Upload Phase 7E floor-check report
  ✓ Run launch regression floor
  ✓ Upload launch floor-check report
  ✓ Run view-hints regression floor
  ✓ Upload view-hints floor-check report
  ✓ Run agents disk-load operation-count floor
  ✓ Upload agents disk-load floor-check report
  ✓ Run plugins catalog-scale regression floor
  ✓ Upload plugins catalog-scale floor-check report
  ✓ Run bead performance smoke
  ✓ Upload bead performance smoke
  ✓ Run bead scaled-corpus benchmark (record-only 4x)
  ✓ Upload bead scaled-corpus benchmark
  ✓ Run bead history-independence gate (1x+4x)
  ✓ Upload bead history-independence gate report
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ full / visual-test in 29m4s (ID 130272098967)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  ✓ Check TUI screenshots
  ✓ Locate visual report
  - Build visual report
  - Upload visual report
  - Publish visual report
  ✓ Publish unstable recapture summary
  ✓ Upload first-attempt diffs
  - Upload visual artifacts
  ✓ Post Install visual dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ full / lint in 6m1s (ID 130272098968)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  - Run astral-sh/setup-uv@v4
  - Set up preflight Python
  - Download Rust core artifacts for bindings preflight
  - Preflight core bindings
  ✓ Install dependencies
  ✓ Check pinned core bindings
  ✓ Bootstrap SDD sidecars
  ✓ Initialize SASE home
  ✓ Run actions/setup-go@v5
  ✓ Cache Go binaries
  - Install Go tools (keep-sorted)
  ✓ Cache Prettier dependencies
  ✓ Check Python formatting
  ✓ Check Markdown formatting
  ✓ Check generated model docs
  ✓ Check shipped model policy
  ✓ Lint
  ✓ SASE validation
  ✓ Validate committed plans
  ✓ Build and verify package
  ✓ Record installed core version
  ✓ Write qualification evidence
  ✓ Upload qualification evidence
  ✓ Post Cache Prettier dependencies
  ✓ Post Cache Go binaries
  ✓ Post Run actions/setup-go@v5
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ full / tutorial-tests in 47s (ID 130272098977)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run tutorial tests
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ full / ace-page-group-isolation in 1m38s (ID 130272099121)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  ✓ Run ACE shared-page isolation lane
  ✓ Post Install visual dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ full / test (3.14) in 54m47s (ID 130272099129)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  - Run tests (coverage leg)
  ✓ Run tests
  ✓ Build shard timings table
  ✓ Upload shard timings
  - Upload coverage
  ✓ Record installed core version
  ✓ Write qualification evidence
  ✓ Upload qualification evidence
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* full / test (3.12) (ID 130272099179)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run tests (coverage leg)
  * Run tests
  * Build shard timings table
  * Upload shard timings
  * Upload coverage
  * Record installed core version
  * Write qualification evidence
  * Upload qualification evidence
  * Post Install dependencies
  * Post Run actions/checkout@v4
✓ full / test (3.13) in 49m12s (ID 130272099254)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  - Run tests (coverage leg)
  ✓ Run tests
  - Build shard timings table
  - Upload shard timings
  - Upload coverage
  ✓ Record installed core version
  ✓ Write qualification evidence
  ✓ Upload qualification evidence
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / prepare: .github#6

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / prepare: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / build-core / build-core: .github#4

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0J87zagAAAABthIK09aOAQYcgffFQ6MzhUEhYMzFFREdFMDYwNwBFZGdl
full / build-core / build-core: .github#7

! Failed to restore: Cache service responded with 400
full / build-core / build-core: .github#25

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / build-core / build-core: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / perf-floors: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0RNDzagAAAACfzCX56wkqQ6jV9SYuxRFgQ0gxQUEyMDMwODEzMDI1AEVkZ2U=
full / perf-floors: .github#9

! Failed to restore: Cache service responded with 400
full / perf-floors: .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / perf-floors: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / visual-test: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0+tTzagAAAABc4gQFoMSBSrtQjz00UkYjU0xDMzFFREdFMDgwNwBFZGdl
full / visual-test: .github#9

! Failed to restore: Cache service responded with 400
full / visual-test: .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / visual-test: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache@v4, actions/checkout@v4, actions/download-artifact@v4, actions/setup-go@v5, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / lint: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0lM/zagAAAAB3yQS/CMfFSJiRrt73gm5UUEhMMzBFREdFMDExNwBFZGdl
full / lint: .github#9

! Failed to restore: Cache service responded with 400
full / lint: .github#46

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / lint: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / tutorial-tests: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0Ws7zagAAAAAO39hx6gJHS7Q8Dow5F+0zQ0gxQUEyMDMwODEzMDMxAEVkZ2U=
full / tutorial-tests: .github#9

! Failed to restore: Cache service responded with 400
full / tutorial-tests: .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / tutorial-tests: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / ace-page-group-isolation: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0jM7zagAAAADMyRcszfEMQJA/QgihOY4oU1RCRURHRTAyMTQARWRnZQ==
full / ace-page-group-isolation: .github#9

! Failed to restore: Cache service responded with 400
full / ace-page-group-isolation: .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / ace-page-group-isolation: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / test (3.14): .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0AdvzagAAAACYlWXYox4pQp3F1ZNvSrsGQ08xRURHRTE0MTIARWRnZQ==
full / test (3.14): .github#9

! Failed to restore: Cache service responded with 400
full / test (3.14): .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / test (3.14): .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / test (3.13): .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0stnzagAAAAC/2v8ls11RTbuuPQLnkuvuU1RCRURHRTA2MTAARWRnZQ==
full / test (3.13): .github#9

! Failed to restore: Cache service responded with 400
full / test (3.13): .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / test (3.13): .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* master Full CI · 42942621559
Triggered via schedule about 1 hour ago

JOBS
✓ full / prepare in 20s (ID 130267805007)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Validate qualification inputs
  - Download the sealed candidate manifest
  - Bind published identity from the sealed manifest
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
- full / docs-build (ID 130267806591)
- full / release-core-floor-smoke (ID 130267806613)
✓ full / build-core / build-core in 10m46s (ID 130267944892)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Resolve core mode
  ✓ Resolve pinned Rust core revision
  ✓ Check out Rust core
  - Check out published Rust core tag
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up Rust
  ✓ Cache Rust build
  ✓ Build abi3 Rust core wheel
  - Download the sealed candidate manifest
  - Fetch and verify the published core wheel
  ✓ Build macro LSP
  ✓ Record wheel provenance
  - Record published tag provenance
  ✓ Upload Rust core artifacts
  ✓ Post Cache Rust build
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Check out Rust core
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ full / perf-floors in 8m57s (ID 130272098957)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Health check (Rust extension loadable)
  ✓ Run slow tests
  ✓ Run Phase 7E regression floor
  ✓ Upload Phase 7E floor-check report
  ✓ Run launch regression floor
  ✓ Upload launch floor-check report
  ✓ Run view-hints regression floor
  ✓ Upload view-hints floor-check report
  ✓ Run agents disk-load operation-count floor
  ✓ Upload agents disk-load floor-check report
  ✓ Run plugins catalog-scale regression floor
  ✓ Upload plugins catalog-scale floor-check report
  ✓ Run bead performance smoke
  ✓ Upload bead performance smoke
  ✓ Run bead scaled-corpus benchmark (record-only 4x)
  ✓ Upload bead scaled-corpus benchmark
  ✓ Run bead history-independence gate (1x+4x)
  ✓ Upload bead history-independence gate report
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ full / visual-test in 29m4s (ID 130272098967)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  ✓ Check TUI screenshots
  ✓ Locate visual report
  - Build visual report
  - Upload visual report
  - Publish visual report
  ✓ Publish unstable recapture summary
  ✓ Upload first-attempt diffs
  - Upload visual artifacts
  ✓ Post Install visual dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ full / lint in 6m1s (ID 130272098968)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  - Run astral-sh/setup-uv@v4
  - Set up preflight Python
  - Download Rust core artifacts for bindings preflight
  - Preflight core bindings
  ✓ Install dependencies
  ✓ Check pinned core bindings
  ✓ Bootstrap SDD sidecars
  ✓ Initialize SASE home
  ✓ Run actions/setup-go@v5
  ✓ Cache Go binaries
  - Install Go tools (keep-sorted)
  ✓ Cache Prettier dependencies
  ✓ Check Python formatting
  ✓ Check Markdown formatting
  ✓ Check generated model docs
  ✓ Check shipped model policy
  ✓ Lint
  ✓ SASE validation
  ✓ Validate committed plans
  ✓ Build and verify package
  ✓ Record installed core version
  ✓ Write qualification evidence
  ✓ Upload qualification evidence
  ✓ Post Cache Prettier dependencies
  ✓ Post Cache Go binaries
  ✓ Post Run actions/setup-go@v5
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ full / tutorial-tests in 47s (ID 130272098977)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run tutorial tests
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ full / ace-page-group-isolation in 1m38s (ID 130272099121)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  ✓ Run ACE shared-page isolation lane
  ✓ Post Install visual dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ full / test (3.14) in 54m47s (ID 130272099129)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  - Run tests (coverage leg)
  ✓ Run tests
  ✓ Build shard timings table
  ✓ Upload shard timings
  - Upload coverage
  ✓ Record installed core version
  ✓ Write qualification evidence
  ✓ Upload qualification evidence
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* full / test (3.12) (ID 130272099179)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run tests (coverage leg)
  * Run tests
  * Build shard timings table
  * Upload shard timings
  * Upload coverage
  * Record installed core version
  * Write qualification evidence
  * Upload qualification evidence
  * Post Install dependencies
  * Post Run actions/checkout@v4
✓ full / test (3.13) in 49m12s (ID 130272099254)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  - Run tests (coverage leg)
  ✓ Run tests
  - Build shard timings table
  - Upload shard timings
  - Upload coverage
  ✓ Record installed core version
  ✓ Write qualification evidence
  ✓ Upload qualification evidence
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / prepare: .github#6

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / prepare: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / build-core / build-core: .github#4

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0J87zagAAAABthIK09aOAQYcgffFQ6MzhUEhYMzFFREdFMDYwNwBFZGdl
full / build-core / build-core: .github#7

! Failed to restore: Cache service responded with 400
full / build-core / build-core: .github#25

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / build-core / build-core: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / perf-floors: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0RNDzagAAAACfzCX56wkqQ6jV9SYuxRFgQ0gxQUEyMDMwODEzMDI1AEVkZ2U=
full / perf-floors: .github#9

! Failed to restore: Cache service responded with 400
full / perf-floors: .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / perf-floors: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / visual-test: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0+tTzagAAAABc4gQFoMSBSrtQjz00UkYjU0xDMzFFREdFMDgwNwBFZGdl
full / visual-test: .github#9

! Failed to restore: Cache service responded with 400
full / visual-test: .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / visual-test: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache@v4, actions/checkout@v4, actions/download-artifact@v4, actions/setup-go@v5, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / lint: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0lM/zagAAAAB3yQS/CMfFSJiRrt73gm5UUEhMMzBFREdFMDExNwBFZGdl
full / lint: .github#9

! Failed to restore: Cache service responded with 400
full / lint: .github#46

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / lint: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / tutorial-tests: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0Ws7zagAAAAAO39hx6gJHS7Q8Dow5F+0zQ0gxQUEyMDMwODEzMDMxAEVkZ2U=
full / tutorial-tests: .github#9

! Failed to restore: Cache service responded with 400
full / tutorial-tests: .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / tutorial-tests: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / ace-page-group-isolation: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0jM7zagAAAADMyRcszfEMQJA/QgihOY4oU1RCRURHRTAyMTQARWRnZQ==
full / ace-page-group-isolation: .github#9

! Failed to restore: Cache service responded with 400
full / ace-page-group-isolation: .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / ace-page-group-isolation: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / test (3.14): .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0AdvzagAAAACYlWXYox4pQp3F1ZNvSrsGQ08xRURHRTE0MTIARWRnZQ==
full / test (3.14): .github#9

! Failed to restore: Cache service responded with 400
full / test (3.14): .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / test (3.14): .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / test (3.13): .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0stnzagAAAAC/2v8ls11RTbuuPQLnkuvuU1RCRURHRTA2MTAARWRnZQ==
full / test (3.13): .github#9

! Failed to restore: Cache service responded with 400
full / test (3.13): .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / test (3.13): .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* master Full CI · 42942621559
Triggered via schedule about 1 hour ago

JOBS
✓ full / prepare in 20s (ID 130267805007)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Validate qualification inputs
  - Download the sealed candidate manifest
  - Bind published identity from the sealed manifest
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
- full / docs-build (ID 130267806591)
- full / release-core-floor-smoke (ID 130267806613)
✓ full / build-core / build-core in 10m46s (ID 130267944892)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Resolve core mode
  ✓ Resolve pinned Rust core revision
  ✓ Check out Rust core
  - Check out published Rust core tag
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up Rust
  ✓ Cache Rust build
  ✓ Build abi3 Rust core wheel
  - Download the sealed candidate manifest
  - Fetch and verify the published core wheel
  ✓ Build macro LSP
  ✓ Record wheel provenance
  - Record published tag provenance
  ✓ Upload Rust core artifacts
  ✓ Post Cache Rust build
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Check out Rust core
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ full / perf-floors in 8m57s (ID 130272098957)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Health check (Rust extension loadable)
  ✓ Run slow tests
  ✓ Run Phase 7E regression floor
  ✓ Upload Phase 7E floor-check report
  ✓ Run launch regression floor
  ✓ Upload launch floor-check report
  ✓ Run view-hints regression floor
  ✓ Upload view-hints floor-check report
  ✓ Run agents disk-load operation-count floor
  ✓ Upload agents disk-load floor-check report
  ✓ Run plugins catalog-scale regression floor
  ✓ Upload plugins catalog-scale floor-check report
  ✓ Run bead performance smoke
  ✓ Upload bead performance smoke
  ✓ Run bead scaled-corpus benchmark (record-only 4x)
  ✓ Upload bead scaled-corpus benchmark
  ✓ Run bead history-independence gate (1x+4x)
  ✓ Upload bead history-independence gate report
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ full / visual-test in 29m4s (ID 130272098967)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  ✓ Check TUI screenshots
  ✓ Locate visual report
  - Build visual report
  - Upload visual report
  - Publish visual report
  ✓ Publish unstable recapture summary
  ✓ Upload first-attempt diffs
  - Upload visual artifacts
  ✓ Post Install visual dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ full / lint in 6m1s (ID 130272098968)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  - Run astral-sh/setup-uv@v4
  - Set up preflight Python
  - Download Rust core artifacts for bindings preflight
  - Preflight core bindings
  ✓ Install dependencies
  ✓ Check pinned core bindings
  ✓ Bootstrap SDD sidecars
  ✓ Initialize SASE home
  ✓ Run actions/setup-go@v5
  ✓ Cache Go binaries
  - Install Go tools (keep-sorted)
  ✓ Cache Prettier dependencies
  ✓ Check Python formatting
  ✓ Check Markdown formatting
  ✓ Check generated model docs
  ✓ Check shipped model policy
  ✓ Lint
  ✓ SASE validation
  ✓ Validate committed plans
  ✓ Build and verify package
  ✓ Record installed core version
  ✓ Write qualification evidence
  ✓ Upload qualification evidence
  ✓ Post Cache Prettier dependencies
  ✓ Post Cache Go binaries
  ✓ Post Run actions/setup-go@v5
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ full / tutorial-tests in 47s (ID 130272098977)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run tutorial tests
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ full / ace-page-group-isolation in 1m38s (ID 130272099121)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  ✓ Run ACE shared-page isolation lane
  ✓ Post Install visual dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ full / test (3.14) in 54m47s (ID 130272099129)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  - Run tests (coverage leg)
  ✓ Run tests
  ✓ Build shard timings table
  ✓ Upload shard timings
  - Upload coverage
  ✓ Record installed core version
  ✓ Write qualification evidence
  ✓ Upload qualification evidence
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* full / test (3.12) (ID 130272099179)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run tests (coverage leg)
  * Run tests
  * Build shard timings table
  * Upload shard timings
  * Upload coverage
  * Record installed core version
  * Write qualification evidence
  * Upload qualification evidence
  * Post Install dependencies
  * Post Run actions/checkout@v4
✓ full / test (3.13) in 49m12s (ID 130272099254)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  - Run tests (coverage leg)
  ✓ Run tests
  - Build shard timings table
  - Upload shard timings
  - Upload coverage
  ✓ Record installed core version
  ✓ Write qualification evidence
  ✓ Upload qualification evidence
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / prepare: .github#6

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / prepare: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / build-core / build-core: .github#4

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0J87zagAAAABthIK09aOAQYcgffFQ6MzhUEhYMzFFREdFMDYwNwBFZGdl
full / build-core / build-core: .github#7

! Failed to restore: Cache service responded with 400
full / build-core / build-core: .github#25

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / build-core / build-core: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / perf-floors: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0RNDzagAAAACfzCX56wkqQ6jV9SYuxRFgQ0gxQUEyMDMwODEzMDI1AEVkZ2U=
full / perf-floors: .github#9

! Failed to restore: Cache service responded with 400
full / perf-floors: .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / perf-floors: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / visual-test: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0+tTzagAAAABc4gQFoMSBSrtQjz00UkYjU0xDMzFFREdFMDgwNwBFZGdl
full / visual-test: .github#9

! Failed to restore: Cache service responded with 400
full / visual-test: .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / visual-test: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache@v4, actions/checkout@v4, actions/download-artifact@v4, actions/setup-go@v5, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / lint: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0lM/zagAAAAB3yQS/CMfFSJiRrt73gm5UUEhMMzBFREdFMDExNwBFZGdl
full / lint: .github#9

! Failed to restore: Cache service responded with 400
full / lint: .github#46

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / lint: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / tutorial-tests: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0Ws7zagAAAAAO39hx6gJHS7Q8Dow5F+0zQ0gxQUEyMDMwODEzMDMxAEVkZ2U=
full / tutorial-tests: .github#9

! Failed to restore: Cache service responded with 400
full / tutorial-tests: .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / tutorial-tests: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / ace-page-group-isolation: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0jM7zagAAAADMyRcszfEMQJA/QgihOY4oU1RCRURHRTAyMTQARWRnZQ==
full / ace-page-group-isolation: .github#9

! Failed to restore: Cache service responded with 400
full / ace-page-group-isolation: .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / ace-page-group-isolation: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / test (3.14): .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0AdvzagAAAACYlWXYox4pQp3F1ZNvSrsGQ08xRURHRTE0MTIARWRnZQ==
full / test (3.14): .github#9

! Failed to restore: Cache service responded with 400
full / test (3.14): .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / test (3.14): .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / test (3.13): .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0stnzagAAAAC/2v8ls11RTbuuPQLnkuvuU1RCRURHRTA2MTAARWRnZQ==
full / test (3.13): .github#9

! Failed to restore: Cache service responded with 400
full / test (3.13): .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / test (3.13): .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* master Full CI · 42942621559
Triggered via schedule about 1 hour ago

JOBS
✓ full / prepare in 20s (ID 130267805007)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Validate qualification inputs
  - Download the sealed candidate manifest
  - Bind published identity from the sealed manifest
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
- full / docs-build (ID 130267806591)
- full / release-core-floor-smoke (ID 130267806613)
✓ full / build-core / build-core in 10m46s (ID 130267944892)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Resolve core mode
  ✓ Resolve pinned Rust core revision
  ✓ Check out Rust core
  - Check out published Rust core tag
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up Rust
  ✓ Cache Rust build
  ✓ Build abi3 Rust core wheel
  - Download the sealed candidate manifest
  - Fetch and verify the published core wheel
  ✓ Build macro LSP
  ✓ Record wheel provenance
  - Record published tag provenance
  ✓ Upload Rust core artifacts
  ✓ Post Cache Rust build
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Check out Rust core
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ full / perf-floors in 8m57s (ID 130272098957)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Health check (Rust extension loadable)
  ✓ Run slow tests
  ✓ Run Phase 7E regression floor
  ✓ Upload Phase 7E floor-check report
  ✓ Run launch regression floor
  ✓ Upload launch floor-check report
  ✓ Run view-hints regression floor
  ✓ Upload view-hints floor-check report
  ✓ Run agents disk-load operation-count floor
  ✓ Upload agents disk-load floor-check report
  ✓ Run plugins catalog-scale regression floor
  ✓ Upload plugins catalog-scale floor-check report
  ✓ Run bead performance smoke
  ✓ Upload bead performance smoke
  ✓ Run bead scaled-corpus benchmark (record-only 4x)
  ✓ Upload bead scaled-corpus benchmark
  ✓ Run bead history-independence gate (1x+4x)
  ✓ Upload bead history-independence gate report
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ full / visual-test in 29m4s (ID 130272098967)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  ✓ Check TUI screenshots
  ✓ Locate visual report
  - Build visual report
  - Upload visual report
  - Publish visual report
  ✓ Publish unstable recapture summary
  ✓ Upload first-attempt diffs
  - Upload visual artifacts
  ✓ Post Install visual dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ full / lint in 6m1s (ID 130272098968)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  - Run astral-sh/setup-uv@v4
  - Set up preflight Python
  - Download Rust core artifacts for bindings preflight
  - Preflight core bindings
  ✓ Install dependencies
  ✓ Check pinned core bindings
  ✓ Bootstrap SDD sidecars
  ✓ Initialize SASE home
  ✓ Run actions/setup-go@v5
  ✓ Cache Go binaries
  - Install Go tools (keep-sorted)
  ✓ Cache Prettier dependencies
  ✓ Check Python formatting
  ✓ Check Markdown formatting
  ✓ Check generated model docs
  ✓ Check shipped model policy
  ✓ Lint
  ✓ SASE validation
  ✓ Validate committed plans
  ✓ Build and verify package
  ✓ Record installed core version
  ✓ Write qualification evidence
  ✓ Upload qualification evidence
  ✓ Post Cache Prettier dependencies
  ✓ Post Cache Go binaries
  ✓ Post Run actions/setup-go@v5
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ full / tutorial-tests in 47s (ID 130272098977)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run tutorial tests
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ full / ace-page-group-isolation in 1m38s (ID 130272099121)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  ✓ Run ACE shared-page isolation lane
  ✓ Post Install visual dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ full / test (3.14) in 54m47s (ID 130272099129)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  - Run tests (coverage leg)
  ✓ Run tests
  ✓ Build shard timings table
  ✓ Upload shard timings
  - Upload coverage
  ✓ Record installed core version
  ✓ Write qualification evidence
  ✓ Upload qualification evidence
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* full / test (3.12) (ID 130272099179)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run tests (coverage leg)
  * Run tests
  * Build shard timings table
  * Upload shard timings
  * Upload coverage
  * Record installed core version
  * Write qualification evidence
  * Upload qualification evidence
  * Post Install dependencies
  * Post Run actions/checkout@v4
✓ full / test (3.13) in 49m12s (ID 130272099254)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  - Run tests (coverage leg)
  ✓ Run tests
  - Build shard timings table
  - Upload shard timings
  - Upload coverage
  ✓ Record installed core version
  ✓ Write qualification evidence
  ✓ Upload qualification evidence
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / prepare: .github#6

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / prepare: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / build-core / build-core: .github#4

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0J87zagAAAABthIK09aOAQYcgffFQ6MzhUEhYMzFFREdFMDYwNwBFZGdl
full / build-core / build-core: .github#7

! Failed to restore: Cache service responded with 400
full / build-core / build-core: .github#25

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / build-core / build-core: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / perf-floors: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0RNDzagAAAACfzCX56wkqQ6jV9SYuxRFgQ0gxQUEyMDMwODEzMDI1AEVkZ2U=
full / perf-floors: .github#9

! Failed to restore: Cache service responded with 400
full / perf-floors: .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / perf-floors: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / visual-test: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0+tTzagAAAABc4gQFoMSBSrtQjz00UkYjU0xDMzFFREdFMDgwNwBFZGdl
full / visual-test: .github#9

! Failed to restore: Cache service responded with 400
full / visual-test: .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / visual-test: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache@v4, actions/checkout@v4, actions/download-artifact@v4, actions/setup-go@v5, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / lint: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0lM/zagAAAAB3yQS/CMfFSJiRrt73gm5UUEhMMzBFREdFMDExNwBFZGdl
full / lint: .github#9

! Failed to restore: Cache service responded with 400
full / lint: .github#46

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / lint: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / tutorial-tests: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0Ws7zagAAAAAO39hx6gJHS7Q8Dow5F+0zQ0gxQUEyMDMwODEzMDMxAEVkZ2U=
full / tutorial-tests: .github#9

! Failed to restore: Cache service responded with 400
full / tutorial-tests: .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / tutorial-tests: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / ace-page-group-isolation: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0jM7zagAAAADMyRcszfEMQJA/QgihOY4oU1RCRURHRTAyMTQARWRnZQ==
full / ace-page-group-isolation: .github#9

! Failed to restore: Cache service responded with 400
full / ace-page-group-isolation: .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / ace-page-group-isolation: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / test (3.14): .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0AdvzagAAAACYlWXYox4pQp3F1ZNvSrsGQ08xRURHRTE0MTIARWRnZQ==
full / test (3.14): .github#9

! Failed to restore: Cache service responded with 400
full / test (3.14): .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / test (3.14): .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / test (3.13): .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0stnzagAAAAC/2v8ls11RTbuuPQLnkuvuU1RCRURHRTA2MTAARWRnZQ==
full / test (3.13): .github#9

! Failed to restore: Cache service responded with 400
full / test (3.13): .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / test (3.13): .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* master Full CI · 42942621559
Triggered via schedule about 1 hour ago

JOBS
✓ full / prepare in 20s (ID 130267805007)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Validate qualification inputs
  - Download the sealed candidate manifest
  - Bind published identity from the sealed manifest
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
- full / docs-build (ID 130267806591)
- full / release-core-floor-smoke (ID 130267806613)
✓ full / build-core / build-core in 10m46s (ID 130267944892)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Resolve core mode
  ✓ Resolve pinned Rust core revision
  ✓ Check out Rust core
  - Check out published Rust core tag
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up Rust
  ✓ Cache Rust build
  ✓ Build abi3 Rust core wheel
  - Download the sealed candidate manifest
  - Fetch and verify the published core wheel
  ✓ Build macro LSP
  ✓ Record wheel provenance
  - Record published tag provenance
  ✓ Upload Rust core artifacts
  ✓ Post Cache Rust build
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Check out Rust core
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ full / perf-floors in 8m57s (ID 130272098957)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Health check (Rust extension loadable)
  ✓ Run slow tests
  ✓ Run Phase 7E regression floor
  ✓ Upload Phase 7E floor-check report
  ✓ Run launch regression floor
  ✓ Upload launch floor-check report
  ✓ Run view-hints regression floor
  ✓ Upload view-hints floor-check report
  ✓ Run agents disk-load operation-count floor
  ✓ Upload agents disk-load floor-check report
  ✓ Run plugins catalog-scale regression floor
  ✓ Upload plugins catalog-scale floor-check report
  ✓ Run bead performance smoke
  ✓ Upload bead performance smoke
  ✓ Run bead scaled-corpus benchmark (record-only 4x)
  ✓ Upload bead scaled-corpus benchmark
  ✓ Run bead history-independence gate (1x+4x)
  ✓ Upload bead history-independence gate report
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ full / visual-test in 29m4s (ID 130272098967)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  ✓ Check TUI screenshots
  ✓ Locate visual report
  - Build visual report
  - Upload visual report
  - Publish visual report
  ✓ Publish unstable recapture summary
  ✓ Upload first-attempt diffs
  - Upload visual artifacts
  ✓ Post Install visual dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ full / lint in 6m1s (ID 130272098968)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  - Run astral-sh/setup-uv@v4
  - Set up preflight Python
  - Download Rust core artifacts for bindings preflight
  - Preflight core bindings
  ✓ Install dependencies
  ✓ Check pinned core bindings
  ✓ Bootstrap SDD sidecars
  ✓ Initialize SASE home
  ✓ Run actions/setup-go@v5
  ✓ Cache Go binaries
  - Install Go tools (keep-sorted)
  ✓ Cache Prettier dependencies
  ✓ Check Python formatting
  ✓ Check Markdown formatting
  ✓ Check generated model docs
  ✓ Check shipped model policy
  ✓ Lint
  ✓ SASE validation
  ✓ Validate committed plans
  ✓ Build and verify package
  ✓ Record installed core version
  ✓ Write qualification evidence
  ✓ Upload qualification evidence
  ✓ Post Cache Prettier dependencies
  ✓ Post Cache Go binaries
  ✓ Post Run actions/setup-go@v5
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ full / tutorial-tests in 47s (ID 130272098977)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run tutorial tests
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ full / ace-page-group-isolation in 1m38s (ID 130272099121)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  ✓ Run ACE shared-page isolation lane
  ✓ Post Install visual dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ full / test (3.14) in 54m47s (ID 130272099129)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  - Run tests (coverage leg)
  ✓ Run tests
  ✓ Build shard timings table
  ✓ Upload shard timings
  - Upload coverage
  ✓ Record installed core version
  ✓ Write qualification evidence
  ✓ Upload qualification evidence
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* full / test (3.12) (ID 130272099179)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run tests (coverage leg)
  * Run tests
  * Build shard timings table
  * Upload shard timings
  * Upload coverage
  * Record installed core version
  * Write qualification evidence
  * Upload qualification evidence
  * Post Install dependencies
  * Post Run actions/checkout@v4
✓ full / test (3.13) in 49m12s (ID 130272099254)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  - Run tests (coverage leg)
  ✓ Run tests
  - Build shard timings table
  - Upload shard timings
  - Upload coverage
  ✓ Record installed core version
  ✓ Write qualification evidence
  ✓ Upload qualification evidence
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / prepare: .github#6

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / prepare: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / build-core / build-core: .github#4

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0J87zagAAAABthIK09aOAQYcgffFQ6MzhUEhYMzFFREdFMDYwNwBFZGdl
full / build-core / build-core: .github#7

! Failed to restore: Cache service responded with 400
full / build-core / build-core: .github#25

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / build-core / build-core: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / perf-floors: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0RNDzagAAAACfzCX56wkqQ6jV9SYuxRFgQ0gxQUEyMDMwODEzMDI1AEVkZ2U=
full / perf-floors: .github#9

! Failed to restore: Cache service responded with 400
full / perf-floors: .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / perf-floors: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / visual-test: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0+tTzagAAAABc4gQFoMSBSrtQjz00UkYjU0xDMzFFREdFMDgwNwBFZGdl
full / visual-test: .github#9

! Failed to restore: Cache service responded with 400
full / visual-test: .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / visual-test: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache@v4, actions/checkout@v4, actions/download-artifact@v4, actions/setup-go@v5, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / lint: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0lM/zagAAAAB3yQS/CMfFSJiRrt73gm5UUEhMMzBFREdFMDExNwBFZGdl
full / lint: .github#9

! Failed to restore: Cache service responded with 400
full / lint: .github#46

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / lint: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / tutorial-tests: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0Ws7zagAAAAAO39hx6gJHS7Q8Dow5F+0zQ0gxQUEyMDMwODEzMDMxAEVkZ2U=
full / tutorial-tests: .github#9

! Failed to restore: Cache service responded with 400
full / tutorial-tests: .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / tutorial-tests: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / ace-page-group-isolation: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0jM7zagAAAADMyRcszfEMQJA/QgihOY4oU1RCRURHRTAyMTQARWRnZQ==
full / ace-page-group-isolation: .github#9

! Failed to restore: Cache service responded with 400
full / ace-page-group-isolation: .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / ace-page-group-isolation: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / test (3.14): .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0AdvzagAAAACYlWXYox4pQp3F1ZNvSrsGQ08xRURHRTE0MTIARWRnZQ==
full / test (3.14): .github#9

! Failed to restore: Cache service responded with 400
full / test (3.14): .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / test (3.14): .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / test (3.13): .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0stnzagAAAAC/2v8ls11RTbuuPQLnkuvuU1RCRURHRTA2MTAARWRnZQ==
full / test (3.13): .github#9

! Failed to restore: Cache service responded with 400
full / test (3.13): .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / test (3.13): .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* master Full CI · 42942621559
Triggered via schedule about 1 hour ago

JOBS
✓ full / prepare in 20s (ID 130267805007)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Validate qualification inputs
  - Download the sealed candidate manifest
  - Bind published identity from the sealed manifest
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
- full / docs-build (ID 130267806591)
- full / release-core-floor-smoke (ID 130267806613)
✓ full / build-core / build-core in 10m46s (ID 130267944892)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Resolve core mode
  ✓ Resolve pinned Rust core revision
  ✓ Check out Rust core
  - Check out published Rust core tag
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up Rust
  ✓ Cache Rust build
  ✓ Build abi3 Rust core wheel
  - Download the sealed candidate manifest
  - Fetch and verify the published core wheel
  ✓ Build macro LSP
  ✓ Record wheel provenance
  - Record published tag provenance
  ✓ Upload Rust core artifacts
  ✓ Post Cache Rust build
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Check out Rust core
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ full / perf-floors in 8m57s (ID 130272098957)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Health check (Rust extension loadable)
  ✓ Run slow tests
  ✓ Run Phase 7E regression floor
  ✓ Upload Phase 7E floor-check report
  ✓ Run launch regression floor
  ✓ Upload launch floor-check report
  ✓ Run view-hints regression floor
  ✓ Upload view-hints floor-check report
  ✓ Run agents disk-load operation-count floor
  ✓ Upload agents disk-load floor-check report
  ✓ Run plugins catalog-scale regression floor
  ✓ Upload plugins catalog-scale floor-check report
  ✓ Run bead performance smoke
  ✓ Upload bead performance smoke
  ✓ Run bead scaled-corpus benchmark (record-only 4x)
  ✓ Upload bead scaled-corpus benchmark
  ✓ Run bead history-independence gate (1x+4x)
  ✓ Upload bead history-independence gate report
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ full / visual-test in 29m4s (ID 130272098967)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  ✓ Check TUI screenshots
  ✓ Locate visual report
  - Build visual report
  - Upload visual report
  - Publish visual report
  ✓ Publish unstable recapture summary
  ✓ Upload first-attempt diffs
  - Upload visual artifacts
  ✓ Post Install visual dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ full / lint in 6m1s (ID 130272098968)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  - Run astral-sh/setup-uv@v4
  - Set up preflight Python
  - Download Rust core artifacts for bindings preflight
  - Preflight core bindings
  ✓ Install dependencies
  ✓ Check pinned core bindings
  ✓ Bootstrap SDD sidecars
  ✓ Initialize SASE home
  ✓ Run actions/setup-go@v5
  ✓ Cache Go binaries
  - Install Go tools (keep-sorted)
  ✓ Cache Prettier dependencies
  ✓ Check Python formatting
  ✓ Check Markdown formatting
  ✓ Check generated model docs
  ✓ Check shipped model policy
  ✓ Lint
  ✓ SASE validation
  ✓ Validate committed plans
  ✓ Build and verify package
  ✓ Record installed core version
  ✓ Write qualification evidence
  ✓ Upload qualification evidence
  ✓ Post Cache Prettier dependencies
  ✓ Post Cache Go binaries
  ✓ Post Run actions/setup-go@v5
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ full / tutorial-tests in 47s (ID 130272098977)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run tutorial tests
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ full / ace-page-group-isolation in 1m38s (ID 130272099121)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  ✓ Run ACE shared-page isolation lane
  ✓ Post Install visual dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ full / test (3.14) in 54m47s (ID 130272099129)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  - Run tests (coverage leg)
  ✓ Run tests
  ✓ Build shard timings table
  ✓ Upload shard timings
  - Upload coverage
  ✓ Record installed core version
  ✓ Write qualification evidence
  ✓ Upload qualification evidence
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* full / test (3.12) (ID 130272099179)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run tests (coverage leg)
  * Run tests
  * Build shard timings table
  * Upload shard timings
  * Upload coverage
  * Record installed core version
  * Write qualification evidence
  * Upload qualification evidence
  * Post Install dependencies
  * Post Run actions/checkout@v4
✓ full / test (3.13) in 49m12s (ID 130272099254)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  - Run tests (coverage leg)
  ✓ Run tests
  - Build shard timings table
  - Upload shard timings
  - Upload coverage
  ✓ Record installed core version
  ✓ Write qualification evidence
  ✓ Upload qualification evidence
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / prepare: .github#6

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / prepare: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / build-core / build-core: .github#4

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0J87zagAAAABthIK09aOAQYcgffFQ6MzhUEhYMzFFREdFMDYwNwBFZGdl
full / build-core / build-core: .github#7

! Failed to restore: Cache service responded with 400
full / build-core / build-core: .github#25

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / build-core / build-core: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / perf-floors: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0RNDzagAAAACfzCX56wkqQ6jV9SYuxRFgQ0gxQUEyMDMwODEzMDI1AEVkZ2U=
full / perf-floors: .github#9

! Failed to restore: Cache service responded with 400
full / perf-floors: .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / perf-floors: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / visual-test: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0+tTzagAAAABc4gQFoMSBSrtQjz00UkYjU0xDMzFFREdFMDgwNwBFZGdl
full / visual-test: .github#9

! Failed to restore: Cache service responded with 400
full / visual-test: .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / visual-test: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache@v4, actions/checkout@v4, actions/download-artifact@v4, actions/setup-go@v5, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / lint: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0lM/zagAAAAB3yQS/CMfFSJiRrt73gm5UUEhMMzBFREdFMDExNwBFZGdl
full / lint: .github#9

! Failed to restore: Cache service responded with 400
full / lint: .github#46

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / lint: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / tutorial-tests: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0Ws7zagAAAAAO39hx6gJHS7Q8Dow5F+0zQ0gxQUEyMDMwODEzMDMxAEVkZ2U=
full / tutorial-tests: .github#9

! Failed to restore: Cache service responded with 400
full / tutorial-tests: .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / tutorial-tests: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / ace-page-group-isolation: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0jM7zagAAAADMyRcszfEMQJA/QgihOY4oU1RCRURHRTAyMTQARWRnZQ==
full / ace-page-group-isolation: .github#9

! Failed to restore: Cache service responded with 400
full / ace-page-group-isolation: .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / ace-page-group-isolation: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / test (3.14): .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0AdvzagAAAACYlWXYox4pQp3F1ZNvSrsGQ08xRURHRTE0MTIARWRnZQ==
full / test (3.14): .github#9

! Failed to restore: Cache service responded with 400
full / test (3.14): .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / test (3.14): .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / test (3.13): .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0stnzagAAAAC/2v8ls11RTbuuPQLnkuvuU1RCRURHRTA2MTAARWRnZQ==
full / test (3.13): .github#9

! Failed to restore: Cache service responded with 400
full / test (3.13): .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / test (3.13): .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* master Full CI · 42942621559
Triggered via schedule about 1 hour ago

JOBS
✓ full / prepare in 20s (ID 130267805007)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Validate qualification inputs
  - Download the sealed candidate manifest
  - Bind published identity from the sealed manifest
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
- full / docs-build (ID 130267806591)
- full / release-core-floor-smoke (ID 130267806613)
✓ full / build-core / build-core in 10m46s (ID 130267944892)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Resolve core mode
  ✓ Resolve pinned Rust core revision
  ✓ Check out Rust core
  - Check out published Rust core tag
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up Rust
  ✓ Cache Rust build
  ✓ Build abi3 Rust core wheel
  - Download the sealed candidate manifest
  - Fetch and verify the published core wheel
  ✓ Build macro LSP
  ✓ Record wheel provenance
  - Record published tag provenance
  ✓ Upload Rust core artifacts
  ✓ Post Cache Rust build
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Check out Rust core
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ full / perf-floors in 8m57s (ID 130272098957)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Health check (Rust extension loadable)
  ✓ Run slow tests
  ✓ Run Phase 7E regression floor
  ✓ Upload Phase 7E floor-check report
  ✓ Run launch regression floor
  ✓ Upload launch floor-check report
  ✓ Run view-hints regression floor
  ✓ Upload view-hints floor-check report
  ✓ Run agents disk-load operation-count floor
  ✓ Upload agents disk-load floor-check report
  ✓ Run plugins catalog-scale regression floor
  ✓ Upload plugins catalog-scale floor-check report
  ✓ Run bead performance smoke
  ✓ Upload bead performance smoke
  ✓ Run bead scaled-corpus benchmark (record-only 4x)
  ✓ Upload bead scaled-corpus benchmark
  ✓ Run bead history-independence gate (1x+4x)
  ✓ Upload bead history-independence gate report
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ full / visual-test in 29m4s (ID 130272098967)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  ✓ Check TUI screenshots
  ✓ Locate visual report
  - Build visual report
  - Upload visual report
  - Publish visual report
  ✓ Publish unstable recapture summary
  ✓ Upload first-attempt diffs
  - Upload visual artifacts
  ✓ Post Install visual dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ full / lint in 6m1s (ID 130272098968)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  - Run astral-sh/setup-uv@v4
  - Set up preflight Python
  - Download Rust core artifacts for bindings preflight
  - Preflight core bindings
  ✓ Install dependencies
  ✓ Check pinned core bindings
  ✓ Bootstrap SDD sidecars
  ✓ Initialize SASE home
  ✓ Run actions/setup-go@v5
  ✓ Cache Go binaries
  - Install Go tools (keep-sorted)
  ✓ Cache Prettier dependencies
  ✓ Check Python formatting
  ✓ Check Markdown formatting
  ✓ Check generated model docs
  ✓ Check shipped model policy
  ✓ Lint
  ✓ SASE validation
  ✓ Validate committed plans
  ✓ Build and verify package
  ✓ Record installed core version
  ✓ Write qualification evidence
  ✓ Upload qualification evidence
  ✓ Post Cache Prettier dependencies
  ✓ Post Cache Go binaries
  ✓ Post Run actions/setup-go@v5
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ full / tutorial-tests in 47s (ID 130272098977)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run tutorial tests
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ full / ace-page-group-isolation in 1m38s (ID 130272099121)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  ✓ Run ACE shared-page isolation lane
  ✓ Post Install visual dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ full / test (3.14) in 54m47s (ID 130272099129)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  - Run tests (coverage leg)
  ✓ Run tests
  ✓ Build shard timings table
  ✓ Upload shard timings
  - Upload coverage
  ✓ Record installed core version
  ✓ Write qualification evidence
  ✓ Upload qualification evidence
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* full / test (3.12) (ID 130272099179)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run tests (coverage leg)
  * Run tests
  * Build shard timings table
  * Upload shard timings
  * Upload coverage
  * Record installed core version
  * Write qualification evidence
  * Upload qualification evidence
  * Post Install dependencies
  * Post Run actions/checkout@v4
✓ full / test (3.13) in 49m12s (ID 130272099254)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  - Run tests (coverage leg)
  ✓ Run tests
  - Build shard timings table
  - Upload shard timings
  - Upload coverage
  ✓ Record installed core version
  ✓ Write qualification evidence
  ✓ Upload qualification evidence
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / prepare: .github#6

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / prepare: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / build-core / build-core: .github#4

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0J87zagAAAABthIK09aOAQYcgffFQ6MzhUEhYMzFFREdFMDYwNwBFZGdl
full / build-core / build-core: .github#7

! Failed to restore: Cache service responded with 400
full / build-core / build-core: .github#25

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / build-core / build-core: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / perf-floors: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0RNDzagAAAACfzCX56wkqQ6jV9SYuxRFgQ0gxQUEyMDMwODEzMDI1AEVkZ2U=
full / perf-floors: .github#9

! Failed to restore: Cache service responded with 400
full / perf-floors: .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / perf-floors: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / visual-test: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0+tTzagAAAABc4gQFoMSBSrtQjz00UkYjU0xDMzFFREdFMDgwNwBFZGdl
full / visual-test: .github#9

! Failed to restore: Cache service responded with 400
full / visual-test: .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / visual-test: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache@v4, actions/checkout@v4, actions/download-artifact@v4, actions/setup-go@v5, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / lint: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0lM/zagAAAAB3yQS/CMfFSJiRrt73gm5UUEhMMzBFREdFMDExNwBFZGdl
full / lint: .github#9

! Failed to restore: Cache service responded with 400
full / lint: .github#46

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / lint: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / tutorial-tests: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0Ws7zagAAAAAO39hx6gJHS7Q8Dow5F+0zQ0gxQUEyMDMwODEzMDMxAEVkZ2U=
full / tutorial-tests: .github#9

! Failed to restore: Cache service responded with 400
full / tutorial-tests: .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / tutorial-tests: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / ace-page-group-isolation: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0jM7zagAAAADMyRcszfEMQJA/QgihOY4oU1RCRURHRTAyMTQARWRnZQ==
full / ace-page-group-isolation: .github#9

! Failed to restore: Cache service responded with 400
full / ace-page-group-isolation: .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / ace-page-group-isolation: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / test (3.14): .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0AdvzagAAAACYlWXYox4pQp3F1ZNvSrsGQ08xRURHRTE0MTIARWRnZQ==
full / test (3.14): .github#9

! Failed to restore: Cache service responded with 400
full / test (3.14): .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / test (3.14): .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / test (3.13): .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0stnzagAAAAC/2v8ls11RTbuuPQLnkuvuU1RCRURHRTA2MTAARWRnZQ==
full / test (3.13): .github#9

! Failed to restore: Cache service responded with 400
full / test (3.13): .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / test (3.13): .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* master Full CI · 42942621559
Triggered via schedule about 1 hour ago

JOBS
✓ full / prepare in 20s (ID 130267805007)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Validate qualification inputs
  - Download the sealed candidate manifest
  - Bind published identity from the sealed manifest
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
- full / docs-build (ID 130267806591)
- full / release-core-floor-smoke (ID 130267806613)
✓ full / build-core / build-core in 10m46s (ID 130267944892)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Resolve core mode
  ✓ Resolve pinned Rust core revision
  ✓ Check out Rust core
  - Check out published Rust core tag
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up Rust
  ✓ Cache Rust build
  ✓ Build abi3 Rust core wheel
  - Download the sealed candidate manifest
  - Fetch and verify the published core wheel
  ✓ Build macro LSP
  ✓ Record wheel provenance
  - Record published tag provenance
  ✓ Upload Rust core artifacts
  ✓ Post Cache Rust build
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Check out Rust core
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ full / perf-floors in 8m57s (ID 130272098957)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Health check (Rust extension loadable)
  ✓ Run slow tests
  ✓ Run Phase 7E regression floor
  ✓ Upload Phase 7E floor-check report
  ✓ Run launch regression floor
  ✓ Upload launch floor-check report
  ✓ Run view-hints regression floor
  ✓ Upload view-hints floor-check report
  ✓ Run agents disk-load operation-count floor
  ✓ Upload agents disk-load floor-check report
  ✓ Run plugins catalog-scale regression floor
  ✓ Upload plugins catalog-scale floor-check report
  ✓ Run bead performance smoke
  ✓ Upload bead performance smoke
  ✓ Run bead scaled-corpus benchmark (record-only 4x)
  ✓ Upload bead scaled-corpus benchmark
  ✓ Run bead history-independence gate (1x+4x)
  ✓ Upload bead history-independence gate report
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ full / visual-test in 29m4s (ID 130272098967)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  ✓ Check TUI screenshots
  ✓ Locate visual report
  - Build visual report
  - Upload visual report
  - Publish visual report
  ✓ Publish unstable recapture summary
  ✓ Upload first-attempt diffs
  - Upload visual artifacts
  ✓ Post Install visual dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ full / lint in 6m1s (ID 130272098968)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  - Run astral-sh/setup-uv@v4
  - Set up preflight Python
  - Download Rust core artifacts for bindings preflight
  - Preflight core bindings
  ✓ Install dependencies
  ✓ Check pinned core bindings
  ✓ Bootstrap SDD sidecars
  ✓ Initialize SASE home
  ✓ Run actions/setup-go@v5
  ✓ Cache Go binaries
  - Install Go tools (keep-sorted)
  ✓ Cache Prettier dependencies
  ✓ Check Python formatting
  ✓ Check Markdown formatting
  ✓ Check generated model docs
  ✓ Check shipped model policy
  ✓ Lint
  ✓ SASE validation
  ✓ Validate committed plans
  ✓ Build and verify package
  ✓ Record installed core version
  ✓ Write qualification evidence
  ✓ Upload qualification evidence
  ✓ Post Cache Prettier dependencies
  ✓ Post Cache Go binaries
  ✓ Post Run actions/setup-go@v5
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ full / tutorial-tests in 47s (ID 130272098977)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run tutorial tests
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ full / ace-page-group-isolation in 1m38s (ID 130272099121)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  ✓ Run ACE shared-page isolation lane
  ✓ Post Install visual dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ full / test (3.14) in 54m47s (ID 130272099129)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  - Run tests (coverage leg)
  ✓ Run tests
  ✓ Build shard timings table
  ✓ Upload shard timings
  - Upload coverage
  ✓ Record installed core version
  ✓ Write qualification evidence
  ✓ Upload qualification evidence
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* full / test (3.12) (ID 130272099179)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run tests (coverage leg)
  * Run tests
  * Build shard timings table
  * Upload shard timings
  * Upload coverage
  * Record installed core version
  * Write qualification evidence
  * Upload qualification evidence
  * Post Install dependencies
  * Post Run actions/checkout@v4
✓ full / test (3.13) in 49m12s (ID 130272099254)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  - Run tests (coverage leg)
  ✓ Run tests
  - Build shard timings table
  - Upload shard timings
  - Upload coverage
  ✓ Record installed core version
  ✓ Write qualification evidence
  ✓ Upload qualification evidence
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / prepare: .github#6

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / prepare: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / build-core / build-core: .github#4

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0J87zagAAAABthIK09aOAQYcgffFQ6MzhUEhYMzFFREdFMDYwNwBFZGdl
full / build-core / build-core: .github#7

! Failed to restore: Cache service responded with 400
full / build-core / build-core: .github#25

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / build-core / build-core: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / perf-floors: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0RNDzagAAAACfzCX56wkqQ6jV9SYuxRFgQ0gxQUEyMDMwODEzMDI1AEVkZ2U=
full / perf-floors: .github#9

! Failed to restore: Cache service responded with 400
full / perf-floors: .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / perf-floors: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / visual-test: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0+tTzagAAAABc4gQFoMSBSrtQjz00UkYjU0xDMzFFREdFMDgwNwBFZGdl
full / visual-test: .github#9

! Failed to restore: Cache service responded with 400
full / visual-test: .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / visual-test: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache@v4, actions/checkout@v4, actions/download-artifact@v4, actions/setup-go@v5, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / lint: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0lM/zagAAAAB3yQS/CMfFSJiRrt73gm5UUEhMMzBFREdFMDExNwBFZGdl
full / lint: .github#9

! Failed to restore: Cache service responded with 400
full / lint: .github#46

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / lint: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / tutorial-tests: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0Ws7zagAAAAAO39hx6gJHS7Q8Dow5F+0zQ0gxQUEyMDMwODEzMDMxAEVkZ2U=
full / tutorial-tests: .github#9

! Failed to restore: Cache service responded with 400
full / tutorial-tests: .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / tutorial-tests: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / ace-page-group-isolation: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0jM7zagAAAADMyRcszfEMQJA/QgihOY4oU1RCRURHRTAyMTQARWRnZQ==
full / ace-page-group-isolation: .github#9

! Failed to restore: Cache service responded with 400
full / ace-page-group-isolation: .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / ace-page-group-isolation: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / test (3.14): .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0AdvzagAAAACYlWXYox4pQp3F1ZNvSrsGQ08xRURHRTE0MTIARWRnZQ==
full / test (3.14): .github#9

! Failed to restore: Cache service responded with 400
full / test (3.14): .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / test (3.14): .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / test (3.13): .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0stnzagAAAAC/2v8ls11RTbuuPQLnkuvuU1RCRURHRTA2MTAARWRnZQ==
full / test (3.13): .github#9

! Failed to restore: Cache service responded with 400
full / test (3.13): .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / test (3.13): .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* master Full CI · 42942621559
Triggered via schedule about 1 hour ago

JOBS
✓ full / prepare in 20s (ID 130267805007)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Validate qualification inputs
  - Download the sealed candidate manifest
  - Bind published identity from the sealed manifest
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
- full / docs-build (ID 130267806591)
- full / release-core-floor-smoke (ID 130267806613)
✓ full / build-core / build-core in 10m46s (ID 130267944892)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Resolve core mode
  ✓ Resolve pinned Rust core revision
  ✓ Check out Rust core
  - Check out published Rust core tag
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up Rust
  ✓ Cache Rust build
  ✓ Build abi3 Rust core wheel
  - Download the sealed candidate manifest
  - Fetch and verify the published core wheel
  ✓ Build macro LSP
  ✓ Record wheel provenance
  - Record published tag provenance
  ✓ Upload Rust core artifacts
  ✓ Post Cache Rust build
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Check out Rust core
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ full / perf-floors in 8m57s (ID 130272098957)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Health check (Rust extension loadable)
  ✓ Run slow tests
  ✓ Run Phase 7E regression floor
  ✓ Upload Phase 7E floor-check report
  ✓ Run launch regression floor
  ✓ Upload launch floor-check report
  ✓ Run view-hints regression floor
  ✓ Upload view-hints floor-check report
  ✓ Run agents disk-load operation-count floor
  ✓ Upload agents disk-load floor-check report
  ✓ Run plugins catalog-scale regression floor
  ✓ Upload plugins catalog-scale floor-check report
  ✓ Run bead performance smoke
  ✓ Upload bead performance smoke
  ✓ Run bead scaled-corpus benchmark (record-only 4x)
  ✓ Upload bead scaled-corpus benchmark
  ✓ Run bead history-independence gate (1x+4x)
  ✓ Upload bead history-independence gate report
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ full / visual-test in 29m4s (ID 130272098967)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  ✓ Check TUI screenshots
  ✓ Locate visual report
  - Build visual report
  - Upload visual report
  - Publish visual report
  ✓ Publish unstable recapture summary
  ✓ Upload first-attempt diffs
  - Upload visual artifacts
  ✓ Post Install visual dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ full / lint in 6m1s (ID 130272098968)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  - Run astral-sh/setup-uv@v4
  - Set up preflight Python
  - Download Rust core artifacts for bindings preflight
  - Preflight core bindings
  ✓ Install dependencies
  ✓ Check pinned core bindings
  ✓ Bootstrap SDD sidecars
  ✓ Initialize SASE home
  ✓ Run actions/setup-go@v5
  ✓ Cache Go binaries
  - Install Go tools (keep-sorted)
  ✓ Cache Prettier dependencies
  ✓ Check Python formatting
  ✓ Check Markdown formatting
  ✓ Check generated model docs
  ✓ Check shipped model policy
  ✓ Lint
  ✓ SASE validation
  ✓ Validate committed plans
  ✓ Build and verify package
  ✓ Record installed core version
  ✓ Write qualification evidence
  ✓ Upload qualification evidence
  ✓ Post Cache Prettier dependencies
  ✓ Post Cache Go binaries
  ✓ Post Run actions/setup-go@v5
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ full / tutorial-tests in 47s (ID 130272098977)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run tutorial tests
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ full / ace-page-group-isolation in 1m38s (ID 130272099121)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  ✓ Run ACE shared-page isolation lane
  ✓ Post Install visual dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ full / test (3.14) in 54m47s (ID 130272099129)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  - Run tests (coverage leg)
  ✓ Run tests
  ✓ Build shard timings table
  ✓ Upload shard timings
  - Upload coverage
  ✓ Record installed core version
  ✓ Write qualification evidence
  ✓ Upload qualification evidence
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* full / test (3.12) (ID 130272099179)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run tests (coverage leg)
  * Run tests
  * Build shard timings table
  * Upload shard timings
  * Upload coverage
  * Record installed core version
  * Write qualification evidence
  * Upload qualification evidence
  * Post Install dependencies
  * Post Run actions/checkout@v4
✓ full / test (3.13) in 49m12s (ID 130272099254)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  - Run tests (coverage leg)
  ✓ Run tests
  - Build shard timings table
  - Upload shard timings
  - Upload coverage
  ✓ Record installed core version
  ✓ Write qualification evidence
  ✓ Upload qualification evidence
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / prepare: .github#6

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / prepare: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / build-core / build-core: .github#4

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0J87zagAAAABthIK09aOAQYcgffFQ6MzhUEhYMzFFREdFMDYwNwBFZGdl
full / build-core / build-core: .github#7

! Failed to restore: Cache service responded with 400
full / build-core / build-core: .github#25

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / build-core / build-core: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / perf-floors: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0RNDzagAAAACfzCX56wkqQ6jV9SYuxRFgQ0gxQUEyMDMwODEzMDI1AEVkZ2U=
full / perf-floors: .github#9

! Failed to restore: Cache service responded with 400
full / perf-floors: .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / perf-floors: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / visual-test: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0+tTzagAAAABc4gQFoMSBSrtQjz00UkYjU0xDMzFFREdFMDgwNwBFZGdl
full / visual-test: .github#9

! Failed to restore: Cache service responded with 400
full / visual-test: .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / visual-test: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache@v4, actions/checkout@v4, actions/download-artifact@v4, actions/setup-go@v5, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / lint: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0lM/zagAAAAB3yQS/CMfFSJiRrt73gm5UUEhMMzBFREdFMDExNwBFZGdl
full / lint: .github#9

! Failed to restore: Cache service responded with 400
full / lint: .github#46

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / lint: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / tutorial-tests: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0Ws7zagAAAAAO39hx6gJHS7Q8Dow5F+0zQ0gxQUEyMDMwODEzMDMxAEVkZ2U=
full / tutorial-tests: .github#9

! Failed to restore: Cache service responded with 400
full / tutorial-tests: .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / tutorial-tests: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / ace-page-group-isolation: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0jM7zagAAAADMyRcszfEMQJA/QgihOY4oU1RCRURHRTAyMTQARWRnZQ==
full / ace-page-group-isolation: .github#9

! Failed to restore: Cache service responded with 400
full / ace-page-group-isolation: .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / ace-page-group-isolation: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / test (3.14): .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0AdvzagAAAACYlWXYox4pQp3F1ZNvSrsGQ08xRURHRTE0MTIARWRnZQ==
full / test (3.14): .github#9

! Failed to restore: Cache service responded with 400
full / test (3.14): .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / test (3.14): .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / test (3.13): .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0stnzagAAAAC/2v8ls11RTbuuPQLnkuvuU1RCRURHRTA2MTAARWRnZQ==
full / test (3.13): .github#9

! Failed to restore: Cache service responded with 400
full / test (3.13): .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / test (3.13): .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* master Full CI · 42942621559
Triggered via schedule about 1 hour ago

JOBS
✓ full / prepare in 20s (ID 130267805007)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Validate qualification inputs
  - Download the sealed candidate manifest
  - Bind published identity from the sealed manifest
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
- full / docs-build (ID 130267806591)
- full / release-core-floor-smoke (ID 130267806613)
✓ full / build-core / build-core in 10m46s (ID 130267944892)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Resolve core mode
  ✓ Resolve pinned Rust core revision
  ✓ Check out Rust core
  - Check out published Rust core tag
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up Rust
  ✓ Cache Rust build
  ✓ Build abi3 Rust core wheel
  - Download the sealed candidate manifest
  - Fetch and verify the published core wheel
  ✓ Build macro LSP
  ✓ Record wheel provenance
  - Record published tag provenance
  ✓ Upload Rust core artifacts
  ✓ Post Cache Rust build
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Check out Rust core
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ full / perf-floors in 8m57s (ID 130272098957)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Health check (Rust extension loadable)
  ✓ Run slow tests
  ✓ Run Phase 7E regression floor
  ✓ Upload Phase 7E floor-check report
  ✓ Run launch regression floor
  ✓ Upload launch floor-check report
  ✓ Run view-hints regression floor
  ✓ Upload view-hints floor-check report
  ✓ Run agents disk-load operation-count floor
  ✓ Upload agents disk-load floor-check report
  ✓ Run plugins catalog-scale regression floor
  ✓ Upload plugins catalog-scale floor-check report
  ✓ Run bead performance smoke
  ✓ Upload bead performance smoke
  ✓ Run bead scaled-corpus benchmark (record-only 4x)
  ✓ Upload bead scaled-corpus benchmark
  ✓ Run bead history-independence gate (1x+4x)
  ✓ Upload bead history-independence gate report
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ full / visual-test in 29m4s (ID 130272098967)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  ✓ Check TUI screenshots
  ✓ Locate visual report
  - Build visual report
  - Upload visual report
  - Publish visual report
  ✓ Publish unstable recapture summary
  ✓ Upload first-attempt diffs
  - Upload visual artifacts
  ✓ Post Install visual dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ full / lint in 6m1s (ID 130272098968)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  - Run astral-sh/setup-uv@v4
  - Set up preflight Python
  - Download Rust core artifacts for bindings preflight
  - Preflight core bindings
  ✓ Install dependencies
  ✓ Check pinned core bindings
  ✓ Bootstrap SDD sidecars
  ✓ Initialize SASE home
  ✓ Run actions/setup-go@v5
  ✓ Cache Go binaries
  - Install Go tools (keep-sorted)
  ✓ Cache Prettier dependencies
  ✓ Check Python formatting
  ✓ Check Markdown formatting
  ✓ Check generated model docs
  ✓ Check shipped model policy
  ✓ Lint
  ✓ SASE validation
  ✓ Validate committed plans
  ✓ Build and verify package
  ✓ Record installed core version
  ✓ Write qualification evidence
  ✓ Upload qualification evidence
  ✓ Post Cache Prettier dependencies
  ✓ Post Cache Go binaries
  ✓ Post Run actions/setup-go@v5
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ full / tutorial-tests in 47s (ID 130272098977)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run tutorial tests
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ full / ace-page-group-isolation in 1m38s (ID 130272099121)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  ✓ Run ACE shared-page isolation lane
  ✓ Post Install visual dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ full / test (3.14) in 54m47s (ID 130272099129)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  - Run tests (coverage leg)
  ✓ Run tests
  ✓ Build shard timings table
  ✓ Upload shard timings
  - Upload coverage
  ✓ Record installed core version
  ✓ Write qualification evidence
  ✓ Upload qualification evidence
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* full / test (3.12) (ID 130272099179)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run tests (coverage leg)
  * Run tests
  * Build shard timings table
  * Upload shard timings
  * Upload coverage
  * Record installed core version
  * Write qualification evidence
  * Upload qualification evidence
  * Post Install dependencies
  * Post Run actions/checkout@v4
✓ full / test (3.13) in 49m12s (ID 130272099254)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  - Run tests (coverage leg)
  ✓ Run tests
  - Build shard timings table
  - Upload shard timings
  - Upload coverage
  ✓ Record installed core version
  ✓ Write qualification evidence
  ✓ Upload qualification evidence
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / prepare: .github#6

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / prepare: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / build-core / build-core: .github#4

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0J87zagAAAABthIK09aOAQYcgffFQ6MzhUEhYMzFFREdFMDYwNwBFZGdl
full / build-core / build-core: .github#7

! Failed to restore: Cache service responded with 400
full / build-core / build-core: .github#25

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / build-core / build-core: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / perf-floors: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0RNDzagAAAACfzCX56wkqQ6jV9SYuxRFgQ0gxQUEyMDMwODEzMDI1AEVkZ2U=
full / perf-floors: .github#9

! Failed to restore: Cache service responded with 400
full / perf-floors: .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / perf-floors: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / visual-test: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0+tTzagAAAABc4gQFoMSBSrtQjz00UkYjU0xDMzFFREdFMDgwNwBFZGdl
full / visual-test: .github#9

! Failed to restore: Cache service responded with 400
full / visual-test: .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / visual-test: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache@v4, actions/checkout@v4, actions/download-artifact@v4, actions/setup-go@v5, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / lint: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0lM/zagAAAAB3yQS/CMfFSJiRrt73gm5UUEhMMzBFREdFMDExNwBFZGdl
full / lint: .github#9

! Failed to restore: Cache service responded with 400
full / lint: .github#46

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / lint: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / tutorial-tests: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0Ws7zagAAAAAO39hx6gJHS7Q8Dow5F+0zQ0gxQUEyMDMwODEzMDMxAEVkZ2U=
full / tutorial-tests: .github#9

! Failed to restore: Cache service responded with 400
full / tutorial-tests: .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / tutorial-tests: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / ace-page-group-isolation: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0jM7zagAAAADMyRcszfEMQJA/QgihOY4oU1RCRURHRTAyMTQARWRnZQ==
full / ace-page-group-isolation: .github#9

! Failed to restore: Cache service responded with 400
full / ace-page-group-isolation: .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / ace-page-group-isolation: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / test (3.14): .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0AdvzagAAAACYlWXYox4pQp3F1ZNvSrsGQ08xRURHRTE0MTIARWRnZQ==
full / test (3.14): .github#9

! Failed to restore: Cache service responded with 400
full / test (3.14): .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / test (3.14): .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / test (3.13): .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0stnzagAAAAC/2v8ls11RTbuuPQLnkuvuU1RCRURHRTA2MTAARWRnZQ==
full / test (3.13): .github#9

! Failed to restore: Cache service responded with 400
full / test (3.13): .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / test (3.13): .github#1

✓ master Full CI · 42942621559
Triggered via schedule about 1 hour ago

JOBS
✓ full / prepare in 20s (ID 130267805007)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Validate qualification inputs
  - Download the sealed candidate manifest
  - Bind published identity from the sealed manifest
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
- full / docs-build (ID 130267806591)
- full / release-core-floor-smoke (ID 130267806613)
✓ full / build-core / build-core in 10m46s (ID 130267944892)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Resolve core mode
  ✓ Resolve pinned Rust core revision
  ✓ Check out Rust core
  - Check out published Rust core tag
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up Rust
  ✓ Cache Rust build
  ✓ Build abi3 Rust core wheel
  - Download the sealed candidate manifest
  - Fetch and verify the published core wheel
  ✓ Build macro LSP
  ✓ Record wheel provenance
  - Record published tag provenance
  ✓ Upload Rust core artifacts
  ✓ Post Cache Rust build
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Check out Rust core
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ full / perf-floors in 8m57s (ID 130272098957)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Health check (Rust extension loadable)
  ✓ Run slow tests
  ✓ Run Phase 7E regression floor
  ✓ Upload Phase 7E floor-check report
  ✓ Run launch regression floor
  ✓ Upload launch floor-check report
  ✓ Run view-hints regression floor
  ✓ Upload view-hints floor-check report
  ✓ Run agents disk-load operation-count floor
  ✓ Upload agents disk-load floor-check report
  ✓ Run plugins catalog-scale regression floor
  ✓ Upload plugins catalog-scale floor-check report
  ✓ Run bead performance smoke
  ✓ Upload bead performance smoke
  ✓ Run bead scaled-corpus benchmark (record-only 4x)
  ✓ Upload bead scaled-corpus benchmark
  ✓ Run bead history-independence gate (1x+4x)
  ✓ Upload bead history-independence gate report
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ full / visual-test in 29m4s (ID 130272098967)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  ✓ Check TUI screenshots
  ✓ Locate visual report
  - Build visual report
  - Upload visual report
  - Publish visual report
  ✓ Publish unstable recapture summary
  ✓ Upload first-attempt diffs
  - Upload visual artifacts
  ✓ Post Install visual dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ full / lint in 6m1s (ID 130272098968)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  - Run astral-sh/setup-uv@v4
  - Set up preflight Python
  - Download Rust core artifacts for bindings preflight
  - Preflight core bindings
  ✓ Install dependencies
  ✓ Check pinned core bindings
  ✓ Bootstrap SDD sidecars
  ✓ Initialize SASE home
  ✓ Run actions/setup-go@v5
  ✓ Cache Go binaries
  - Install Go tools (keep-sorted)
  ✓ Cache Prettier dependencies
  ✓ Check Python formatting
  ✓ Check Markdown formatting
  ✓ Check generated model docs
  ✓ Check shipped model policy
  ✓ Lint
  ✓ SASE validation
  ✓ Validate committed plans
  ✓ Build and verify package
  ✓ Record installed core version
  ✓ Write qualification evidence
  ✓ Upload qualification evidence
  ✓ Post Cache Prettier dependencies
  ✓ Post Cache Go binaries
  ✓ Post Run actions/setup-go@v5
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ full / tutorial-tests in 47s (ID 130272098977)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run tutorial tests
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ full / ace-page-group-isolation in 1m38s (ID 130272099121)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  ✓ Run ACE shared-page isolation lane
  ✓ Post Install visual dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ full / test (3.14) in 54m47s (ID 130272099129)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  - Run tests (coverage leg)
  ✓ Run tests
  ✓ Build shard timings table
  ✓ Upload shard timings
  - Upload coverage
  ✓ Record installed core version
  ✓ Write qualification evidence
  ✓ Upload qualification evidence
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ full / test (3.12) in 1h35m35s (ID 130272099179)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run tests (coverage leg)
  - Run tests
  - Build shard timings table
  - Upload shard timings
  ✓ Upload coverage
  ✓ Record installed core version
  ✓ Write qualification evidence
  ✓ Upload qualification evidence
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ full / test (3.13) in 49m12s (ID 130272099254)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  - Run tests (coverage leg)
  ✓ Run tests
  - Build shard timings table
  - Upload shard timings
  - Upload coverage
  ✓ Record installed core version
  ✓ Write qualification evidence
  ✓ Upload qualification evidence
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / prepare: .github#6

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / prepare: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / build-core / build-core: .github#4

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0J87zagAAAABthIK09aOAQYcgffFQ6MzhUEhYMzFFREdFMDYwNwBFZGdl
full / build-core / build-core: .github#7

! Failed to restore: Cache service responded with 400
full / build-core / build-core: .github#25

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / build-core / build-core: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / perf-floors: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0RNDzagAAAACfzCX56wkqQ6jV9SYuxRFgQ0gxQUEyMDMwODEzMDI1AEVkZ2U=
full / perf-floors: .github#9

! Failed to restore: Cache service responded with 400
full / perf-floors: .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / perf-floors: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / visual-test: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0+tTzagAAAABc4gQFoMSBSrtQjz00UkYjU0xDMzFFREdFMDgwNwBFZGdl
full / visual-test: .github#9

! Failed to restore: Cache service responded with 400
full / visual-test: .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / visual-test: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache@v4, actions/checkout@v4, actions/download-artifact@v4, actions/setup-go@v5, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / lint: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0lM/zagAAAAB3yQS/CMfFSJiRrt73gm5UUEhMMzBFREdFMDExNwBFZGdl
full / lint: .github#9

! Failed to restore: Cache service responded with 400
full / lint: .github#46

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / lint: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / tutorial-tests: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0Ws7zagAAAAAO39hx6gJHS7Q8Dow5F+0zQ0gxQUEyMDMwODEzMDMxAEVkZ2U=
full / tutorial-tests: .github#9

! Failed to restore: Cache service responded with 400
full / tutorial-tests: .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / tutorial-tests: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / ace-page-group-isolation: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0jM7zagAAAADMyRcszfEMQJA/QgihOY4oU1RCRURHRTAyMTQARWRnZQ==
full / ace-page-group-isolation: .github#9

! Failed to restore: Cache service responded with 400
full / ace-page-group-isolation: .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / ace-page-group-isolation: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / test (3.14): .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0AdvzagAAAACYlWXYox4pQp3F1ZNvSrsGQ08xRURHRTE0MTIARWRnZQ==
full / test (3.14): .github#9

! Failed to restore: Cache service responded with 400
full / test (3.14): .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / test (3.14): .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4, codecov/codecov-action@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / test (3.12): .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0kOTzagAAAABwNrzvDssnSocTfuX9ucUwTEFYRURHRTIwMDYARWRnZQ==
full / test (3.12): .github#9

! Failed to restore: Cache service responded with 400
full / test (3.12): .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / test (3.12): .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* master CI Telemetry · 42949481249
Triggered via workflow_dispatch about 48 minutes ago

JOBS
✓ build-core / build-core in 13m23s (ID 130290157276)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Resolve core mode
  ✓ Resolve pinned Rust core revision
  ✓ Check out Rust core
  - Check out published Rust core tag
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up Rust
  ✓ Cache Rust build
  ✓ Build abi3 Rust core wheel
  - Download the sealed candidate manifest
  - Fetch and verify the published core wheel
  ✓ Build macro LSP
  ✓ Record wheel provenance
  - Record published tag provenance
  ✓ Upload Rust core artifacts
  ✓ Post Cache Rust build
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Check out Rust core
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* test-cost (ID 130295013692)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run cost-attribution suite
  * Upload global leak report
  * Post Install dependencies
  * Post Run actions/checkout@v4
* contention-test (ID 130295013705)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  * Run default-lane contention harness
  * Upload contention failure records
  * Post Install visual dependencies
  * Post Run actions/checkout@v4
* coverage-contexts (ID 130295013754)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Record per-test coverage contexts
  * Upload coverage contexts database
  * Post Install dependencies
  * Post Run actions/checkout@v4

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
build-core / build-core: .github#4

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0ttzzagAAAAAqVB+e59loT7lKWXqkntCzU0xDMzFFREdFMDcxMwBFZGdl
build-core / build-core: .github#7

! Failed to restore: Cache service responded with 400
build-core / build-core: .github#25

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
build-core / build-core: .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* master CI Telemetry · 42949481249
Triggered via workflow_dispatch about 50 minutes ago

JOBS
✓ build-core / build-core in 13m23s (ID 130290157276)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Resolve core mode
  ✓ Resolve pinned Rust core revision
  ✓ Check out Rust core
  - Check out published Rust core tag
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up Rust
  ✓ Cache Rust build
  ✓ Build abi3 Rust core wheel
  - Download the sealed candidate manifest
  - Fetch and verify the published core wheel
  ✓ Build macro LSP
  ✓ Record wheel provenance
  - Record published tag provenance
  ✓ Upload Rust core artifacts
  ✓ Post Cache Rust build
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Check out Rust core
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* test-cost (ID 130295013692)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run cost-attribution suite
  * Upload global leak report
  * Post Install dependencies
  * Post Run actions/checkout@v4
* contention-test (ID 130295013705)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  * Run default-lane contention harness
  * Upload contention failure records
  * Post Install visual dependencies
  * Post Run actions/checkout@v4
* coverage-contexts (ID 130295013754)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Record per-test coverage contexts
  * Upload coverage contexts database
  * Post Install dependencies
  * Post Run actions/checkout@v4

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
build-core / build-core: .github#4

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0ttzzagAAAAAqVB+e59loT7lKWXqkntCzU0xDMzFFREdFMDcxMwBFZGdl
build-core / build-core: .github#7

! Failed to restore: Cache service responded with 400
build-core / build-core: .github#25

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
build-core / build-core: .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* master CI Telemetry · 42949481249
Triggered via workflow_dispatch about 52 minutes ago

JOBS
✓ build-core / build-core in 13m23s (ID 130290157276)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Resolve core mode
  ✓ Resolve pinned Rust core revision
  ✓ Check out Rust core
  - Check out published Rust core tag
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up Rust
  ✓ Cache Rust build
  ✓ Build abi3 Rust core wheel
  - Download the sealed candidate manifest
  - Fetch and verify the published core wheel
  ✓ Build macro LSP
  ✓ Record wheel provenance
  - Record published tag provenance
  ✓ Upload Rust core artifacts
  ✓ Post Cache Rust build
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Check out Rust core
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* test-cost (ID 130295013692)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run cost-attribution suite
  * Upload global leak report
  * Post Install dependencies
  * Post Run actions/checkout@v4
* contention-test (ID 130295013705)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  * Run default-lane contention harness
  * Upload contention failure records
  * Post Install visual dependencies
  * Post Run actions/checkout@v4
* coverage-contexts (ID 130295013754)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Record per-test coverage contexts
  * Upload coverage contexts database
  * Post Install dependencies
  * Post Run actions/checkout@v4

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
build-core / build-core: .github#4

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0ttzzagAAAAAqVB+e59loT7lKWXqkntCzU0xDMzFFREdFMDcxMwBFZGdl
build-core / build-core: .github#7

! Failed to restore: Cache service responded with 400
build-core / build-core: .github#25

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
build-core / build-core: .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* master CI Telemetry · 42949481249
Triggered via workflow_dispatch about 54 minutes ago

JOBS
✓ build-core / build-core in 13m23s (ID 130290157276)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Resolve core mode
  ✓ Resolve pinned Rust core revision
  ✓ Check out Rust core
  - Check out published Rust core tag
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up Rust
  ✓ Cache Rust build
  ✓ Build abi3 Rust core wheel
  - Download the sealed candidate manifest
  - Fetch and verify the published core wheel
  ✓ Build macro LSP
  ✓ Record wheel provenance
  - Record published tag provenance
  ✓ Upload Rust core artifacts
  ✓ Post Cache Rust build
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Check out Rust core
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* test-cost (ID 130295013692)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run cost-attribution suite
  * Upload global leak report
  * Post Install dependencies
  * Post Run actions/checkout@v4
* contention-test (ID 130295013705)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  * Run default-lane contention harness
  * Upload contention failure records
  * Post Install visual dependencies
  * Post Run actions/checkout@v4
* coverage-contexts (ID 130295013754)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Record per-test coverage contexts
  * Upload coverage contexts database
  * Post Install dependencies
  * Post Run actions/checkout@v4

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
build-core / build-core: .github#4

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0ttzzagAAAAAqVB+e59loT7lKWXqkntCzU0xDMzFFREdFMDcxMwBFZGdl
build-core / build-core: .github#7

! Failed to restore: Cache service responded with 400
build-core / build-core: .github#25

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
build-core / build-core: .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* master CI Telemetry · 42949481249
Triggered via workflow_dispatch about 56 minutes ago

JOBS
✓ build-core / build-core in 13m23s (ID 130290157276)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Resolve core mode
  ✓ Resolve pinned Rust core revision
  ✓ Check out Rust core
  - Check out published Rust core tag
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up Rust
  ✓ Cache Rust build
  ✓ Build abi3 Rust core wheel
  - Download the sealed candidate manifest
  - Fetch and verify the published core wheel
  ✓ Build macro LSP
  ✓ Record wheel provenance
  - Record published tag provenance
  ✓ Upload Rust core artifacts
  ✓ Post Cache Rust build
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Check out Rust core
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* test-cost (ID 130295013692)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run cost-attribution suite
  * Upload global leak report
  * Post Install dependencies
  * Post Run actions/checkout@v4
* contention-test (ID 130295013705)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  * Run default-lane contention harness
  * Upload contention failure records
  * Post Install visual dependencies
  * Post Run actions/checkout@v4
* coverage-contexts (ID 130295013754)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Record per-test coverage contexts
  * Upload coverage contexts database
  * Post Install dependencies
  * Post Run actions/checkout@v4

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
build-core / build-core: .github#4

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0ttzzagAAAAAqVB+e59loT7lKWXqkntCzU0xDMzFFREdFMDcxMwBFZGdl
build-core / build-core: .github#7

! Failed to restore: Cache service responded with 400
build-core / build-core: .github#25

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
build-core / build-core: .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* master CI Telemetry · 42949481249
Triggered via workflow_dispatch about 58 minutes ago

JOBS
✓ build-core / build-core in 13m23s (ID 130290157276)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Resolve core mode
  ✓ Resolve pinned Rust core revision
  ✓ Check out Rust core
  - Check out published Rust core tag
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up Rust
  ✓ Cache Rust build
  ✓ Build abi3 Rust core wheel
  - Download the sealed candidate manifest
  - Fetch and verify the published core wheel
  ✓ Build macro LSP
  ✓ Record wheel provenance
  - Record published tag provenance
  ✓ Upload Rust core artifacts
  ✓ Post Cache Rust build
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Check out Rust core
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* test-cost (ID 130295013692)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run cost-attribution suite
  * Upload global leak report
  * Post Install dependencies
  * Post Run actions/checkout@v4
* contention-test (ID 130295013705)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  * Run default-lane contention harness
  * Upload contention failure records
  * Post Install visual dependencies
  * Post Run actions/checkout@v4
* coverage-contexts (ID 130295013754)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Record per-test coverage contexts
  * Upload coverage contexts database
  * Post Install dependencies
  * Post Run actions/checkout@v4

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
build-core / build-core: .github#4

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0ttzzagAAAAAqVB+e59loT7lKWXqkntCzU0xDMzFFREdFMDcxMwBFZGdl
build-core / build-core: .github#7

! Failed to restore: Cache service responded with 400
build-core / build-core: .github#25

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
build-core / build-core: .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* master CI Telemetry · 42949481249
Triggered via workflow_dispatch about 1 hour ago

JOBS
✓ build-core / build-core in 13m23s (ID 130290157276)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Resolve core mode
  ✓ Resolve pinned Rust core revision
  ✓ Check out Rust core
  - Check out published Rust core tag
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up Rust
  ✓ Cache Rust build
  ✓ Build abi3 Rust core wheel
  - Download the sealed candidate manifest
  - Fetch and verify the published core wheel
  ✓ Build macro LSP
  ✓ Record wheel provenance
  - Record published tag provenance
  ✓ Upload Rust core artifacts
  ✓ Post Cache Rust build
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Check out Rust core
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* test-cost (ID 130295013692)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run cost-attribution suite
  * Upload global leak report
  * Post Install dependencies
  * Post Run actions/checkout@v4
* contention-test (ID 130295013705)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  * Run default-lane contention harness
  * Upload contention failure records
  * Post Install visual dependencies
  * Post Run actions/checkout@v4
* coverage-contexts (ID 130295013754)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Record per-test coverage contexts
  * Upload coverage contexts database
  * Post Install dependencies
  * Post Run actions/checkout@v4

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
build-core / build-core: .github#4

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0ttzzagAAAAAqVB+e59loT7lKWXqkntCzU0xDMzFFREdFMDcxMwBFZGdl
build-core / build-core: .github#7

! Failed to restore: Cache service responded with 400
build-core / build-core: .github#25

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
build-core / build-core: .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* master CI Telemetry · 42949481249
Triggered via workflow_dispatch about 1 hour ago

JOBS
✓ build-core / build-core in 13m23s (ID 130290157276)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Resolve core mode
  ✓ Resolve pinned Rust core revision
  ✓ Check out Rust core
  - Check out published Rust core tag
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up Rust
  ✓ Cache Rust build
  ✓ Build abi3 Rust core wheel
  - Download the sealed candidate manifest
  - Fetch and verify the published core wheel
  ✓ Build macro LSP
  ✓ Record wheel provenance
  - Record published tag provenance
  ✓ Upload Rust core artifacts
  ✓ Post Cache Rust build
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Check out Rust core
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* test-cost (ID 130295013692)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run cost-attribution suite
  * Upload global leak report
  * Post Install dependencies
  * Post Run actions/checkout@v4
* contention-test (ID 130295013705)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  * Run default-lane contention harness
  * Upload contention failure records
  * Post Install visual dependencies
  * Post Run actions/checkout@v4
* coverage-contexts (ID 130295013754)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Record per-test coverage contexts
  * Upload coverage contexts database
  * Post Install dependencies
  * Post Run actions/checkout@v4

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
build-core / build-core: .github#4

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0ttzzagAAAAAqVB+e59loT7lKWXqkntCzU0xDMzFFREdFMDcxMwBFZGdl
build-core / build-core: .github#7

! Failed to restore: Cache service responded with 400
build-core / build-core: .github#25

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
build-core / build-core: .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* master CI Telemetry · 42949481249
Triggered via workflow_dispatch about 1 hour ago

JOBS
✓ build-core / build-core in 13m23s (ID 130290157276)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Resolve core mode
  ✓ Resolve pinned Rust core revision
  ✓ Check out Rust core
  - Check out published Rust core tag
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up Rust
  ✓ Cache Rust build
  ✓ Build abi3 Rust core wheel
  - Download the sealed candidate manifest
  - Fetch and verify the published core wheel
  ✓ Build macro LSP
  ✓ Record wheel provenance
  - Record published tag provenance
  ✓ Upload Rust core artifacts
  ✓ Post Cache Rust build
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Check out Rust core
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* test-cost (ID 130295013692)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run cost-attribution suite
  * Upload global leak report
  * Post Install dependencies
  * Post Run actions/checkout@v4
* contention-test (ID 130295013705)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  * Run default-lane contention harness
  * Upload contention failure records
  * Post Install visual dependencies
  * Post Run actions/checkout@v4
* coverage-contexts (ID 130295013754)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Record per-test coverage contexts
  * Upload coverage contexts database
  * Post Install dependencies
  * Post Run actions/checkout@v4

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
build-core / build-core: .github#4

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0ttzzagAAAAAqVB+e59loT7lKWXqkntCzU0xDMzFFREdFMDcxMwBFZGdl
build-core / build-core: .github#7

! Failed to restore: Cache service responded with 400
build-core / build-core: .github#25

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
build-core / build-core: .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* master CI Telemetry · 42949481249
Triggered via workflow_dispatch about 1 hour ago

JOBS
✓ build-core / build-core in 13m23s (ID 130290157276)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Resolve core mode
  ✓ Resolve pinned Rust core revision
  ✓ Check out Rust core
  - Check out published Rust core tag
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up Rust
  ✓ Cache Rust build
  ✓ Build abi3 Rust core wheel
  - Download the sealed candidate manifest
  - Fetch and verify the published core wheel
  ✓ Build macro LSP
  ✓ Record wheel provenance
  - Record published tag provenance
  ✓ Upload Rust core artifacts
  ✓ Post Cache Rust build
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Check out Rust core
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* test-cost (ID 130295013692)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run cost-attribution suite
  * Upload global leak report
  * Post Install dependencies
  * Post Run actions/checkout@v4
* contention-test (ID 130295013705)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  * Run default-lane contention harness
  * Upload contention failure records
  * Post Install visual dependencies
  * Post Run actions/checkout@v4
* coverage-contexts (ID 130295013754)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Record per-test coverage contexts
  * Upload coverage contexts database
  * Post Install dependencies
  * Post Run actions/checkout@v4

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
build-core / build-core: .github#4

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0ttzzagAAAAAqVB+e59loT7lKWXqkntCzU0xDMzFFREdFMDcxMwBFZGdl
build-core / build-core: .github#7

! Failed to restore: Cache service responded with 400
build-core / build-core: .github#25

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
build-core / build-core: .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* master CI Telemetry · 42949481249
Triggered via workflow_dispatch about 1 hour ago

JOBS
✓ build-core / build-core in 13m23s (ID 130290157276)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Resolve core mode
  ✓ Resolve pinned Rust core revision
  ✓ Check out Rust core
  - Check out published Rust core tag
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up Rust
  ✓ Cache Rust build
  ✓ Build abi3 Rust core wheel
  - Download the sealed candidate manifest
  - Fetch and verify the published core wheel
  ✓ Build macro LSP
  ✓ Record wheel provenance
  - Record published tag provenance
  ✓ Upload Rust core artifacts
  ✓ Post Cache Rust build
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Check out Rust core
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* test-cost (ID 130295013692)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run cost-attribution suite
  * Upload global leak report
  * Post Install dependencies
  * Post Run actions/checkout@v4
* contention-test (ID 130295013705)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  * Run default-lane contention harness
  * Upload contention failure records
  * Post Install visual dependencies
  * Post Run actions/checkout@v4
* coverage-contexts (ID 130295013754)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Record per-test coverage contexts
  * Upload coverage contexts database
  * Post Install dependencies
  * Post Run actions/checkout@v4

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
build-core / build-core: .github#4

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0ttzzagAAAAAqVB+e59loT7lKWXqkntCzU0xDMzFFREdFMDcxMwBFZGdl
build-core / build-core: .github#7

! Failed to restore: Cache service responded with 400
build-core / build-core: .github#25

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
build-core / build-core: .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* master CI Telemetry · 42949481249
Triggered via workflow_dispatch about 1 hour ago

JOBS
✓ build-core / build-core in 13m23s (ID 130290157276)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Resolve core mode
  ✓ Resolve pinned Rust core revision
  ✓ Check out Rust core
  - Check out published Rust core tag
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up Rust
  ✓ Cache Rust build
  ✓ Build abi3 Rust core wheel
  - Download the sealed candidate manifest
  - Fetch and verify the published core wheel
  ✓ Build macro LSP
  ✓ Record wheel provenance
  - Record published tag provenance
  ✓ Upload Rust core artifacts
  ✓ Post Cache Rust build
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Check out Rust core
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* test-cost (ID 130295013692)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run cost-attribution suite
  * Upload global leak report
  * Post Install dependencies
  * Post Run actions/checkout@v4
* contention-test (ID 130295013705)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  * Run default-lane contention harness
  * Upload contention failure records
  * Post Install visual dependencies
  * Post Run actions/checkout@v4
* coverage-contexts (ID 130295013754)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Record per-test coverage contexts
  * Upload coverage contexts database
  * Post Install dependencies
  * Post Run actions/checkout@v4

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
build-core / build-core: .github#4

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0ttzzagAAAAAqVB+e59loT7lKWXqkntCzU0xDMzFFREdFMDcxMwBFZGdl
build-core / build-core: .github#7

! Failed to restore: Cache service responded with 400
build-core / build-core: .github#25

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
build-core / build-core: .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* master CI Telemetry · 42949481249
Triggered via workflow_dispatch about 1 hour ago

JOBS
✓ build-core / build-core in 13m23s (ID 130290157276)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Resolve core mode
  ✓ Resolve pinned Rust core revision
  ✓ Check out Rust core
  - Check out published Rust core tag
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up Rust
  ✓ Cache Rust build
  ✓ Build abi3 Rust core wheel
  - Download the sealed candidate manifest
  - Fetch and verify the published core wheel
  ✓ Build macro LSP
  ✓ Record wheel provenance
  - Record published tag provenance
  ✓ Upload Rust core artifacts
  ✓ Post Cache Rust build
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Check out Rust core
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* test-cost (ID 130295013692)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run cost-attribution suite
  * Upload global leak report
  * Post Install dependencies
  * Post Run actions/checkout@v4
* contention-test (ID 130295013705)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  * Run default-lane contention harness
  * Upload contention failure records
  * Post Install visual dependencies
  * Post Run actions/checkout@v4
* coverage-contexts (ID 130295013754)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Record per-test coverage contexts
  * Upload coverage contexts database
  * Post Install dependencies
  * Post Run actions/checkout@v4

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
build-core / build-core: .github#4

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0ttzzagAAAAAqVB+e59loT7lKWXqkntCzU0xDMzFFREdFMDcxMwBFZGdl
build-core / build-core: .github#7

! Failed to restore: Cache service responded with 400
build-core / build-core: .github#25

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
build-core / build-core: .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* master CI Telemetry · 42949481249
Triggered via workflow_dispatch about 1 hour ago

JOBS
✓ build-core / build-core in 13m23s (ID 130290157276)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Resolve core mode
  ✓ Resolve pinned Rust core revision
  ✓ Check out Rust core
  - Check out published Rust core tag
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up Rust
  ✓ Cache Rust build
  ✓ Build abi3 Rust core wheel
  - Download the sealed candidate manifest
  - Fetch and verify the published core wheel
  ✓ Build macro LSP
  ✓ Record wheel provenance
  - Record published tag provenance
  ✓ Upload Rust core artifacts
  ✓ Post Cache Rust build
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Check out Rust core
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* test-cost (ID 130295013692)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run cost-attribution suite
  * Upload global leak report
  * Post Install dependencies
  * Post Run actions/checkout@v4
* contention-test (ID 130295013705)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  * Run default-lane contention harness
  * Upload contention failure records
  * Post Install visual dependencies
  * Post Run actions/checkout@v4
* coverage-contexts (ID 130295013754)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Record per-test coverage contexts
  * Upload coverage contexts database
  * Post Install dependencies
  * Post Run actions/checkout@v4

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
build-core / build-core: .github#4

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0ttzzagAAAAAqVB+e59loT7lKWXqkntCzU0xDMzFFREdFMDcxMwBFZGdl
build-core / build-core: .github#7

! Failed to restore: Cache service responded with 400
build-core / build-core: .github#25

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
build-core / build-core: .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* master CI Telemetry · 42949481249
Triggered via workflow_dispatch about 1 hour ago

JOBS
✓ build-core / build-core in 13m23s (ID 130290157276)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Resolve core mode
  ✓ Resolve pinned Rust core revision
  ✓ Check out Rust core
  - Check out published Rust core tag
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up Rust
  ✓ Cache Rust build
  ✓ Build abi3 Rust core wheel
  - Download the sealed candidate manifest
  - Fetch and verify the published core wheel
  ✓ Build macro LSP
  ✓ Record wheel provenance
  - Record published tag provenance
  ✓ Upload Rust core artifacts
  ✓ Post Cache Rust build
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Check out Rust core
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* test-cost (ID 130295013692)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run cost-attribution suite
  * Upload global leak report
  * Post Install dependencies
  * Post Run actions/checkout@v4
* contention-test (ID 130295013705)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  * Run default-lane contention harness
  * Upload contention failure records
  * Post Install visual dependencies
  * Post Run actions/checkout@v4
* coverage-contexts (ID 130295013754)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Record per-test coverage contexts
  * Upload coverage contexts database
  * Post Install dependencies
  * Post Run actions/checkout@v4

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
build-core / build-core: .github#4

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0ttzzagAAAAAqVB+e59loT7lKWXqkntCzU0xDMzFFREdFMDcxMwBFZGdl
build-core / build-core: .github#7

! Failed to restore: Cache service responded with 400
build-core / build-core: .github#25

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
build-core / build-core: .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* master CI Telemetry · 42949481249
Triggered via workflow_dispatch about 1 hour ago

JOBS
✓ build-core / build-core in 13m23s (ID 130290157276)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Resolve core mode
  ✓ Resolve pinned Rust core revision
  ✓ Check out Rust core
  - Check out published Rust core tag
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up Rust
  ✓ Cache Rust build
  ✓ Build abi3 Rust core wheel
  - Download the sealed candidate manifest
  - Fetch and verify the published core wheel
  ✓ Build macro LSP
  ✓ Record wheel provenance
  - Record published tag provenance
  ✓ Upload Rust core artifacts
  ✓ Post Cache Rust build
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Check out Rust core
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* test-cost (ID 130295013692)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run cost-attribution suite
  * Upload global leak report
  * Post Install dependencies
  * Post Run actions/checkout@v4
* contention-test (ID 130295013705)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  * Run default-lane contention harness
  * Upload contention failure records
  * Post Install visual dependencies
  * Post Run actions/checkout@v4
* coverage-contexts (ID 130295013754)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Record per-test coverage contexts
  * Upload coverage contexts database
  * Post Install dependencies
  * Post Run actions/checkout@v4

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
build-core / build-core: .github#4

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0ttzzagAAAAAqVB+e59loT7lKWXqkntCzU0xDMzFFREdFMDcxMwBFZGdl
build-core / build-core: .github#7

! Failed to restore: Cache service responded with 400
build-core / build-core: .github#25

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
build-core / build-core: .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* master CI Telemetry · 42949481249
Triggered via workflow_dispatch about 1 hour ago

JOBS
✓ build-core / build-core in 13m23s (ID 130290157276)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Resolve core mode
  ✓ Resolve pinned Rust core revision
  ✓ Check out Rust core
  - Check out published Rust core tag
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up Rust
  ✓ Cache Rust build
  ✓ Build abi3 Rust core wheel
  - Download the sealed candidate manifest
  - Fetch and verify the published core wheel
  ✓ Build macro LSP
  ✓ Record wheel provenance
  - Record published tag provenance
  ✓ Upload Rust core artifacts
  ✓ Post Cache Rust build
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Check out Rust core
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* test-cost (ID 130295013692)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run cost-attribution suite
  * Upload global leak report
  * Post Install dependencies
  * Post Run actions/checkout@v4
* contention-test (ID 130295013705)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  * Run default-lane contention harness
  * Upload contention failure records
  * Post Install visual dependencies
  * Post Run actions/checkout@v4
* coverage-contexts (ID 130295013754)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Record per-test coverage contexts
  * Upload coverage contexts database
  * Post Install dependencies
  * Post Run actions/checkout@v4

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
build-core / build-core: .github#4

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0ttzzagAAAAAqVB+e59loT7lKWXqkntCzU0xDMzFFREdFMDcxMwBFZGdl
build-core / build-core: .github#7

! Failed to restore: Cache service responded with 400
build-core / build-core: .github#25

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
build-core / build-core: .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* master CI Telemetry · 42949481249
Triggered via workflow_dispatch about 1 hour ago

JOBS
✓ build-core / build-core in 13m23s (ID 130290157276)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Resolve core mode
  ✓ Resolve pinned Rust core revision
  ✓ Check out Rust core
  - Check out published Rust core tag
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up Rust
  ✓ Cache Rust build
  ✓ Build abi3 Rust core wheel
  - Download the sealed candidate manifest
  - Fetch and verify the published core wheel
  ✓ Build macro LSP
  ✓ Record wheel provenance
  - Record published tag provenance
  ✓ Upload Rust core artifacts
  ✓ Post Cache Rust build
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Check out Rust core
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* test-cost (ID 130295013692)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run cost-attribution suite
  * Upload global leak report
  * Post Install dependencies
  * Post Run actions/checkout@v4
* contention-test (ID 130295013705)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  * Run default-lane contention harness
  * Upload contention failure records
  * Post Install visual dependencies
  * Post Run actions/checkout@v4
* coverage-contexts (ID 130295013754)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Record per-test coverage contexts
  * Upload coverage contexts database
  * Post Install dependencies
  * Post Run actions/checkout@v4

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
build-core / build-core: .github#4

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0ttzzagAAAAAqVB+e59loT7lKWXqkntCzU0xDMzFFREdFMDcxMwBFZGdl
build-core / build-core: .github#7

! Failed to restore: Cache service responded with 400
build-core / build-core: .github#25

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
build-core / build-core: .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* master CI Telemetry · 42949481249
Triggered via workflow_dispatch about 1 hour ago

JOBS
✓ build-core / build-core in 13m23s (ID 130290157276)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Resolve core mode
  ✓ Resolve pinned Rust core revision
  ✓ Check out Rust core
  - Check out published Rust core tag
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up Rust
  ✓ Cache Rust build
  ✓ Build abi3 Rust core wheel
  - Download the sealed candidate manifest
  - Fetch and verify the published core wheel
  ✓ Build macro LSP
  ✓ Record wheel provenance
  - Record published tag provenance
  ✓ Upload Rust core artifacts
  ✓ Post Cache Rust build
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Check out Rust core
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* test-cost (ID 130295013692)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run cost-attribution suite
  * Upload global leak report
  * Post Install dependencies
  * Post Run actions/checkout@v4
* contention-test (ID 130295013705)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  * Run default-lane contention harness
  * Upload contention failure records
  * Post Install visual dependencies
  * Post Run actions/checkout@v4
* coverage-contexts (ID 130295013754)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Record per-test coverage contexts
  * Upload coverage contexts database
  * Post Install dependencies
  * Post Run actions/checkout@v4

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
build-core / build-core: .github#4

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0ttzzagAAAAAqVB+e59loT7lKWXqkntCzU0xDMzFFREdFMDcxMwBFZGdl
build-core / build-core: .github#7

! Failed to restore: Cache service responded with 400
build-core / build-core: .github#25

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
build-core / build-core: .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* master CI Telemetry · 42949481249
Triggered via workflow_dispatch about 1 hour ago

JOBS
✓ build-core / build-core in 13m23s (ID 130290157276)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Resolve core mode
  ✓ Resolve pinned Rust core revision
  ✓ Check out Rust core
  - Check out published Rust core tag
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up Rust
  ✓ Cache Rust build
  ✓ Build abi3 Rust core wheel
  - Download the sealed candidate manifest
  - Fetch and verify the published core wheel
  ✓ Build macro LSP
  ✓ Record wheel provenance
  - Record published tag provenance
  ✓ Upload Rust core artifacts
  ✓ Post Cache Rust build
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Check out Rust core
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* test-cost (ID 130295013692)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run cost-attribution suite
  * Upload global leak report
  * Post Install dependencies
  * Post Run actions/checkout@v4
* contention-test (ID 130295013705)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  * Run default-lane contention harness
  * Upload contention failure records
  * Post Install visual dependencies
  * Post Run actions/checkout@v4
* coverage-contexts (ID 130295013754)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Record per-test coverage contexts
  * Upload coverage contexts database
  * Post Install dependencies
  * Post Run actions/checkout@v4

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
build-core / build-core: .github#4

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0ttzzagAAAAAqVB+e59loT7lKWXqkntCzU0xDMzFFREdFMDcxMwBFZGdl
build-core / build-core: .github#7

! Failed to restore: Cache service responded with 400
build-core / build-core: .github#25

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
build-core / build-core: .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* master CI Telemetry · 42949481249
Triggered via workflow_dispatch about 1 hour ago

JOBS
✓ build-core / build-core in 13m23s (ID 130290157276)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Resolve core mode
  ✓ Resolve pinned Rust core revision
  ✓ Check out Rust core
  - Check out published Rust core tag
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up Rust
  ✓ Cache Rust build
  ✓ Build abi3 Rust core wheel
  - Download the sealed candidate manifest
  - Fetch and verify the published core wheel
  ✓ Build macro LSP
  ✓ Record wheel provenance
  - Record published tag provenance
  ✓ Upload Rust core artifacts
  ✓ Post Cache Rust build
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Check out Rust core
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* test-cost (ID 130295013692)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run cost-attribution suite
  * Upload global leak report
  * Post Install dependencies
  * Post Run actions/checkout@v4
* contention-test (ID 130295013705)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  * Run default-lane contention harness
  * Upload contention failure records
  * Post Install visual dependencies
  * Post Run actions/checkout@v4
* coverage-contexts (ID 130295013754)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Record per-test coverage contexts
  * Upload coverage contexts database
  * Post Install dependencies
  * Post Run actions/checkout@v4

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
build-core / build-core: .github#4

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0ttzzagAAAAAqVB+e59loT7lKWXqkntCzU0xDMzFFREdFMDcxMwBFZGdl
build-core / build-core: .github#7

! Failed to restore: Cache service responded with 400
build-core / build-core: .github#25

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
build-core / build-core: .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* master CI Telemetry · 42949481249
Triggered via workflow_dispatch about 1 hour ago

JOBS
✓ build-core / build-core in 13m23s (ID 130290157276)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Resolve core mode
  ✓ Resolve pinned Rust core revision
  ✓ Check out Rust core
  - Check out published Rust core tag
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up Rust
  ✓ Cache Rust build
  ✓ Build abi3 Rust core wheel
  - Download the sealed candidate manifest
  - Fetch and verify the published core wheel
  ✓ Build macro LSP
  ✓ Record wheel provenance
  - Record published tag provenance
  ✓ Upload Rust core artifacts
  ✓ Post Cache Rust build
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Check out Rust core
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* test-cost (ID 130295013692)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run cost-attribution suite
  * Upload global leak report
  * Post Install dependencies
  * Post Run actions/checkout@v4
* contention-test (ID 130295013705)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  * Run default-lane contention harness
  * Upload contention failure records
  * Post Install visual dependencies
  * Post Run actions/checkout@v4
* coverage-contexts (ID 130295013754)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Record per-test coverage contexts
  * Upload coverage contexts database
  * Post Install dependencies
  * Post Run actions/checkout@v4

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
build-core / build-core: .github#4

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0ttzzagAAAAAqVB+e59loT7lKWXqkntCzU0xDMzFFREdFMDcxMwBFZGdl
build-core / build-core: .github#7

! Failed to restore: Cache service responded with 400
build-core / build-core: .github#25

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
build-core / build-core: .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* master CI Telemetry · 42949481249
Triggered via workflow_dispatch about 1 hour ago

JOBS
✓ build-core / build-core in 13m23s (ID 130290157276)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Resolve core mode
  ✓ Resolve pinned Rust core revision
  ✓ Check out Rust core
  - Check out published Rust core tag
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up Rust
  ✓ Cache Rust build
  ✓ Build abi3 Rust core wheel
  - Download the sealed candidate manifest
  - Fetch and verify the published core wheel
  ✓ Build macro LSP
  ✓ Record wheel provenance
  - Record published tag provenance
  ✓ Upload Rust core artifacts
  ✓ Post Cache Rust build
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Check out Rust core
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* test-cost (ID 130295013692)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run cost-attribution suite
  * Upload global leak report
  * Post Install dependencies
  * Post Run actions/checkout@v4
* contention-test (ID 130295013705)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  * Run default-lane contention harness
  * Upload contention failure records
  * Post Install visual dependencies
  * Post Run actions/checkout@v4
* coverage-contexts (ID 130295013754)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Record per-test coverage contexts
  * Upload coverage contexts database
  * Post Install dependencies
  * Post Run actions/checkout@v4

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
build-core / build-core: .github#4

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0ttzzagAAAAAqVB+e59loT7lKWXqkntCzU0xDMzFFREdFMDcxMwBFZGdl
build-core / build-core: .github#7

! Failed to restore: Cache service responded with 400
build-core / build-core: .github#25

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
build-core / build-core: .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* master CI Telemetry · 42949481249
Triggered via workflow_dispatch about 1 hour ago

JOBS
✓ build-core / build-core in 13m23s (ID 130290157276)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Resolve core mode
  ✓ Resolve pinned Rust core revision
  ✓ Check out Rust core
  - Check out published Rust core tag
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up Rust
  ✓ Cache Rust build
  ✓ Build abi3 Rust core wheel
  - Download the sealed candidate manifest
  - Fetch and verify the published core wheel
  ✓ Build macro LSP
  ✓ Record wheel provenance
  - Record published tag provenance
  ✓ Upload Rust core artifacts
  ✓ Post Cache Rust build
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Check out Rust core
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* test-cost (ID 130295013692)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run cost-attribution suite
  * Upload global leak report
  * Post Install dependencies
  * Post Run actions/checkout@v4
* contention-test (ID 130295013705)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  * Run default-lane contention harness
  * Upload contention failure records
  * Post Install visual dependencies
  * Post Run actions/checkout@v4
* coverage-contexts (ID 130295013754)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Record per-test coverage contexts
  * Upload coverage contexts database
  * Post Install dependencies
  * Post Run actions/checkout@v4

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
build-core / build-core: .github#4

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0ttzzagAAAAAqVB+e59loT7lKWXqkntCzU0xDMzFFREdFMDcxMwBFZGdl
build-core / build-core: .github#7

! Failed to restore: Cache service responded with 400
build-core / build-core: .github#25

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
build-core / build-core: .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* master CI Telemetry · 42949481249
Triggered via workflow_dispatch about 1 hour ago

JOBS
✓ build-core / build-core in 13m23s (ID 130290157276)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Resolve core mode
  ✓ Resolve pinned Rust core revision
  ✓ Check out Rust core
  - Check out published Rust core tag
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up Rust
  ✓ Cache Rust build
  ✓ Build abi3 Rust core wheel
  - Download the sealed candidate manifest
  - Fetch and verify the published core wheel
  ✓ Build macro LSP
  ✓ Record wheel provenance
  - Record published tag provenance
  ✓ Upload Rust core artifacts
  ✓ Post Cache Rust build
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Check out Rust core
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* test-cost (ID 130295013692)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run cost-attribution suite
  * Upload global leak report
  * Post Install dependencies
  * Post Run actions/checkout@v4
* contention-test (ID 130295013705)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  * Run default-lane contention harness
  * Upload contention failure records
  * Post Install visual dependencies
  * Post Run actions/checkout@v4
* coverage-contexts (ID 130295013754)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Record per-test coverage contexts
  * Upload coverage contexts database
  * Post Install dependencies
  * Post Run actions/checkout@v4

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
build-core / build-core: .github#4

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0ttzzagAAAAAqVB+e59loT7lKWXqkntCzU0xDMzFFREdFMDcxMwBFZGdl
build-core / build-core: .github#7

! Failed to restore: Cache service responded with 400
build-core / build-core: .github#25

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
build-core / build-core: .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* master CI Telemetry · 42949481249
Triggered via workflow_dispatch about 1 hour ago

JOBS
✓ build-core / build-core in 13m23s (ID 130290157276)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Resolve core mode
  ✓ Resolve pinned Rust core revision
  ✓ Check out Rust core
  - Check out published Rust core tag
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up Rust
  ✓ Cache Rust build
  ✓ Build abi3 Rust core wheel
  - Download the sealed candidate manifest
  - Fetch and verify the published core wheel
  ✓ Build macro LSP
  ✓ Record wheel provenance
  - Record published tag provenance
  ✓ Upload Rust core artifacts
  ✓ Post Cache Rust build
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Check out Rust core
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* test-cost (ID 130295013692)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run cost-attribution suite
  * Upload global leak report
  * Post Install dependencies
  * Post Run actions/checkout@v4
* contention-test (ID 130295013705)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  * Run default-lane contention harness
  * Upload contention failure records
  * Post Install visual dependencies
  * Post Run actions/checkout@v4
* coverage-contexts (ID 130295013754)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Record per-test coverage contexts
  * Upload coverage contexts database
  * Post Install dependencies
  * Post Run actions/checkout@v4

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
build-core / build-core: .github#4

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0ttzzagAAAAAqVB+e59loT7lKWXqkntCzU0xDMzFFREdFMDcxMwBFZGdl
build-core / build-core: .github#7

! Failed to restore: Cache service responded with 400
build-core / build-core: .github#25

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
build-core / build-core: .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* master CI Telemetry · 42949481249
Triggered via workflow_dispatch about 1 hour ago

JOBS
✓ build-core / build-core in 13m23s (ID 130290157276)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Resolve core mode
  ✓ Resolve pinned Rust core revision
  ✓ Check out Rust core
  - Check out published Rust core tag
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up Rust
  ✓ Cache Rust build
  ✓ Build abi3 Rust core wheel
  - Download the sealed candidate manifest
  - Fetch and verify the published core wheel
  ✓ Build macro LSP
  ✓ Record wheel provenance
  - Record published tag provenance
  ✓ Upload Rust core artifacts
  ✓ Post Cache Rust build
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Check out Rust core
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* test-cost (ID 130295013692)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run cost-attribution suite
  * Upload global leak report
  * Post Install dependencies
  * Post Run actions/checkout@v4
* contention-test (ID 130295013705)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  * Run default-lane contention harness
  * Upload contention failure records
  * Post Install visual dependencies
  * Post Run actions/checkout@v4
* coverage-contexts (ID 130295013754)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Record per-test coverage contexts
  * Upload coverage contexts database
  * Post Install dependencies
  * Post Run actions/checkout@v4

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
build-core / build-core: .github#4

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0ttzzagAAAAAqVB+e59loT7lKWXqkntCzU0xDMzFFREdFMDcxMwBFZGdl
build-core / build-core: .github#7

! Failed to restore: Cache service responded with 400
build-core / build-core: .github#25

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
build-core / build-core: .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* master CI Telemetry · 42949481249
Triggered via workflow_dispatch about 1 hour ago

JOBS
✓ build-core / build-core in 13m23s (ID 130290157276)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Resolve core mode
  ✓ Resolve pinned Rust core revision
  ✓ Check out Rust core
  - Check out published Rust core tag
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up Rust
  ✓ Cache Rust build
  ✓ Build abi3 Rust core wheel
  - Download the sealed candidate manifest
  - Fetch and verify the published core wheel
  ✓ Build macro LSP
  ✓ Record wheel provenance
  - Record published tag provenance
  ✓ Upload Rust core artifacts
  ✓ Post Cache Rust build
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Check out Rust core
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* test-cost (ID 130295013692)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run cost-attribution suite
  * Upload global leak report
  * Post Install dependencies
  * Post Run actions/checkout@v4
* contention-test (ID 130295013705)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  * Run default-lane contention harness
  * Upload contention failure records
  * Post Install visual dependencies
  * Post Run actions/checkout@v4
* coverage-contexts (ID 130295013754)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Record per-test coverage contexts
  * Upload coverage contexts database
  * Post Install dependencies
  * Post Run actions/checkout@v4

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
build-core / build-core: .github#4

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0ttzzagAAAAAqVB+e59loT7lKWXqkntCzU0xDMzFFREdFMDcxMwBFZGdl
build-core / build-core: .github#7

! Failed to restore: Cache service responded with 400
build-core / build-core: .github#25

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
build-core / build-core: .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* master CI Telemetry · 42949481249
Triggered via workflow_dispatch about 1 hour ago

JOBS
✓ build-core / build-core in 13m23s (ID 130290157276)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Resolve core mode
  ✓ Resolve pinned Rust core revision
  ✓ Check out Rust core
  - Check out published Rust core tag
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up Rust
  ✓ Cache Rust build
  ✓ Build abi3 Rust core wheel
  - Download the sealed candidate manifest
  - Fetch and verify the published core wheel
  ✓ Build macro LSP
  ✓ Record wheel provenance
  - Record published tag provenance
  ✓ Upload Rust core artifacts
  ✓ Post Cache Rust build
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Check out Rust core
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* test-cost (ID 130295013692)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run cost-attribution suite
  * Upload global leak report
  * Post Install dependencies
  * Post Run actions/checkout@v4
X contention-test in 1h30m17s (ID 130295013705)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  X Run default-lane contention harness
  ✓ Upload contention failure records
  ✓ Post Install visual dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* coverage-contexts (ID 130295013754)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Record per-test coverage contexts
  * Upload coverage contexts database
  * Post Install dependencies
  * Post Run actions/checkout@v4

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
build-core / build-core: .github#4

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0ttzzagAAAAAqVB+e59loT7lKWXqkntCzU0xDMzFFREdFMDcxMwBFZGdl
build-core / build-core: .github#7

! Failed to restore: Cache service responded with 400
build-core / build-core: .github#25

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
build-core / build-core: .github#1

X The job has exceeded the maximum execution time of 1h30m0s
contention-test: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
contention-test: .github#35

X The operation was canceled.
contention-test: .github#1162

! Failed to restore: Cache service responded with 400
contention-test: .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
contention-test: .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* master CI Telemetry · 42949481249
Triggered via workflow_dispatch about 1 hour ago

JOBS
✓ build-core / build-core in 13m23s (ID 130290157276)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Resolve core mode
  ✓ Resolve pinned Rust core revision
  ✓ Check out Rust core
  - Check out published Rust core tag
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up Rust
  ✓ Cache Rust build
  ✓ Build abi3 Rust core wheel
  - Download the sealed candidate manifest
  - Fetch and verify the published core wheel
  ✓ Build macro LSP
  ✓ Record wheel provenance
  - Record published tag provenance
  ✓ Upload Rust core artifacts
  ✓ Post Cache Rust build
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Check out Rust core
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* test-cost (ID 130295013692)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run cost-attribution suite
  * Upload global leak report
  * Post Install dependencies
  * Post Run actions/checkout@v4
X contention-test in 1h30m17s (ID 130295013705)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  X Run default-lane contention harness
  ✓ Upload contention failure records
  ✓ Post Install visual dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* coverage-contexts (ID 130295013754)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Record per-test coverage contexts
  * Upload coverage contexts database
  * Post Install dependencies
  * Post Run actions/checkout@v4

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
build-core / build-core: .github#4

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0ttzzagAAAAAqVB+e59loT7lKWXqkntCzU0xDMzFFREdFMDcxMwBFZGdl
build-core / build-core: .github#7

! Failed to restore: Cache service responded with 400
build-core / build-core: .github#25

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
build-core / build-core: .github#1

X The job has exceeded the maximum execution time of 1h30m0s
contention-test: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
contention-test: .github#35

X The operation was canceled.
contention-test: .github#1162

! Failed to restore: Cache service responded with 400
contention-test: .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
contention-test: .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* master CI Telemetry · 42949481249
Triggered via workflow_dispatch about 1 hour ago

JOBS
✓ build-core / build-core in 13m23s (ID 130290157276)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Resolve core mode
  ✓ Resolve pinned Rust core revision
  ✓ Check out Rust core
  - Check out published Rust core tag
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up Rust
  ✓ Cache Rust build
  ✓ Build abi3 Rust core wheel
  - Download the sealed candidate manifest
  - Fetch and verify the published core wheel
  ✓ Build macro LSP
  ✓ Record wheel provenance
  - Record published tag provenance
  ✓ Upload Rust core artifacts
  ✓ Post Cache Rust build
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Check out Rust core
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* test-cost (ID 130295013692)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run cost-attribution suite
  * Upload global leak report
  * Post Install dependencies
  * Post Run actions/checkout@v4
X contention-test in 1h30m17s (ID 130295013705)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  X Run default-lane contention harness
  ✓ Upload contention failure records
  ✓ Post Install visual dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* coverage-contexts (ID 130295013754)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Record per-test coverage contexts
  * Upload coverage contexts database
  * Post Install dependencies
  * Post Run actions/checkout@v4

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
build-core / build-core: .github#4

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0ttzzagAAAAAqVB+e59loT7lKWXqkntCzU0xDMzFFREdFMDcxMwBFZGdl
build-core / build-core: .github#7

! Failed to restore: Cache service responded with 400
build-core / build-core: .github#25

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
build-core / build-core: .github#1

X The job has exceeded the maximum execution time of 1h30m0s
contention-test: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
contention-test: .github#35

X The operation was canceled.
contention-test: .github#1162

! Failed to restore: Cache service responded with 400
contention-test: .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
contention-test: .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* master CI Telemetry · 42949481249
Triggered via workflow_dispatch about 1 hour ago

JOBS
✓ build-core / build-core in 13m23s (ID 130290157276)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Resolve core mode
  ✓ Resolve pinned Rust core revision
  ✓ Check out Rust core
  - Check out published Rust core tag
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up Rust
  ✓ Cache Rust build
  ✓ Build abi3 Rust core wheel
  - Download the sealed candidate manifest
  - Fetch and verify the published core wheel
  ✓ Build macro LSP
  ✓ Record wheel provenance
  - Record published tag provenance
  ✓ Upload Rust core artifacts
  ✓ Post Cache Rust build
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Check out Rust core
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* test-cost (ID 130295013692)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run cost-attribution suite
  * Upload global leak report
  * Post Install dependencies
  * Post Run actions/checkout@v4
X contention-test in 1h30m17s (ID 130295013705)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  X Run default-lane contention harness
  ✓ Upload contention failure records
  ✓ Post Install visual dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
X coverage-contexts in 1h37m6s (ID 130295013754)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  X Record per-test coverage contexts
  ✓ Upload coverage contexts database
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
build-core / build-core: .github#4

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0ttzzagAAAAAqVB+e59loT7lKWXqkntCzU0xDMzFFREdFMDcxMwBFZGdl
build-core / build-core: .github#7

! Failed to restore: Cache service responded with 400
build-core / build-core: .github#25

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
build-core / build-core: .github#1

X The job has exceeded the maximum execution time of 1h30m0s
contention-test: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
contention-test: .github#35

X The operation was canceled.
contention-test: .github#1162

! Failed to restore: Cache service responded with 400
contention-test: .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
contention-test: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
coverage-contexts: .github#2

! No files were found with the provided path: .coverage. No artifacts will be uploaded.
coverage-contexts: .github#16

X Process completed with exit code 1.
coverage-contexts: .github#1389

! Failed to restore: Cache service responded with 400
coverage-contexts: .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
coverage-contexts: .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* master CI Telemetry · 42949481249
Triggered via workflow_dispatch about 1 hour ago

JOBS
✓ build-core / build-core in 13m23s (ID 130290157276)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Resolve core mode
  ✓ Resolve pinned Rust core revision
  ✓ Check out Rust core
  - Check out published Rust core tag
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up Rust
  ✓ Cache Rust build
  ✓ Build abi3 Rust core wheel
  - Download the sealed candidate manifest
  - Fetch and verify the published core wheel
  ✓ Build macro LSP
  ✓ Record wheel provenance
  - Record published tag provenance
  ✓ Upload Rust core artifacts
  ✓ Post Cache Rust build
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Check out Rust core
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* test-cost (ID 130295013692)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run cost-attribution suite
  * Upload global leak report
  * Post Install dependencies
  * Post Run actions/checkout@v4
X contention-test in 1h30m17s (ID 130295013705)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  X Run default-lane contention harness
  ✓ Upload contention failure records
  ✓ Post Install visual dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
X coverage-contexts in 1h37m6s (ID 130295013754)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  X Record per-test coverage contexts
  ✓ Upload coverage contexts database
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
build-core / build-core: .github#4

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0ttzzagAAAAAqVB+e59loT7lKWXqkntCzU0xDMzFFREdFMDcxMwBFZGdl
build-core / build-core: .github#7

! Failed to restore: Cache service responded with 400
build-core / build-core: .github#25

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
build-core / build-core: .github#1

X The job has exceeded the maximum execution time of 1h30m0s
contention-test: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
contention-test: .github#35

X The operation was canceled.
contention-test: .github#1162

! Failed to restore: Cache service responded with 400
contention-test: .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
contention-test: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
coverage-contexts: .github#2

! No files were found with the provided path: .coverage. No artifacts will be uploaded.
coverage-contexts: .github#16

X Process completed with exit code 1.
coverage-contexts: .github#1389

! Failed to restore: Cache service responded with 400
coverage-contexts: .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
coverage-contexts: .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* master CI Telemetry · 42949481249
Triggered via workflow_dispatch about 1 hour ago

JOBS
✓ build-core / build-core in 13m23s (ID 130290157276)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Resolve core mode
  ✓ Resolve pinned Rust core revision
  ✓ Check out Rust core
  - Check out published Rust core tag
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up Rust
  ✓ Cache Rust build
  ✓ Build abi3 Rust core wheel
  - Download the sealed candidate manifest
  - Fetch and verify the published core wheel
  ✓ Build macro LSP
  ✓ Record wheel provenance
  - Record published tag provenance
  ✓ Upload Rust core artifacts
  ✓ Post Cache Rust build
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Check out Rust core
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* test-cost (ID 130295013692)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run cost-attribution suite
  * Upload global leak report
  * Post Install dependencies
  * Post Run actions/checkout@v4
X contention-test in 1h30m17s (ID 130295013705)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  X Run default-lane contention harness
  ✓ Upload contention failure records
  ✓ Post Install visual dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
X coverage-contexts in 1h37m6s (ID 130295013754)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  X Record per-test coverage contexts
  ✓ Upload coverage contexts database
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
build-core / build-core: .github#4

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0ttzzagAAAAAqVB+e59loT7lKWXqkntCzU0xDMzFFREdFMDcxMwBFZGdl
build-core / build-core: .github#7

! Failed to restore: Cache service responded with 400
build-core / build-core: .github#25

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
build-core / build-core: .github#1

X The job has exceeded the maximum execution time of 1h30m0s
contention-test: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
contention-test: .github#35

X The operation was canceled.
contention-test: .github#1162

! Failed to restore: Cache service responded with 400
contention-test: .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
contention-test: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
coverage-contexts: .github#2

! No files were found with the provided path: .coverage. No artifacts will be uploaded.
coverage-contexts: .github#16

X Process completed with exit code 1.
coverage-contexts: .github#1389

! Failed to restore: Cache service responded with 400
coverage-contexts: .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
coverage-contexts: .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* master CI Telemetry · 42949481249
Triggered via workflow_dispatch about 1 hour ago

JOBS
✓ build-core / build-core in 13m23s (ID 130290157276)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Resolve core mode
  ✓ Resolve pinned Rust core revision
  ✓ Check out Rust core
  - Check out published Rust core tag
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up Rust
  ✓ Cache Rust build
  ✓ Build abi3 Rust core wheel
  - Download the sealed candidate manifest
  - Fetch and verify the published core wheel
  ✓ Build macro LSP
  ✓ Record wheel provenance
  - Record published tag provenance
  ✓ Upload Rust core artifacts
  ✓ Post Cache Rust build
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Check out Rust core
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* test-cost (ID 130295013692)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run cost-attribution suite
  * Upload global leak report
  * Post Install dependencies
  * Post Run actions/checkout@v4
X contention-test in 1h30m17s (ID 130295013705)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  X Run default-lane contention harness
  ✓ Upload contention failure records
  ✓ Post Install visual dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
X coverage-contexts in 1h37m6s (ID 130295013754)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  X Record per-test coverage contexts
  ✓ Upload coverage contexts database
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
build-core / build-core: .github#4

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0ttzzagAAAAAqVB+e59loT7lKWXqkntCzU0xDMzFFREdFMDcxMwBFZGdl
build-core / build-core: .github#7

! Failed to restore: Cache service responded with 400
build-core / build-core: .github#25

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
build-core / build-core: .github#1

X The job has exceeded the maximum execution time of 1h30m0s
contention-test: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
contention-test: .github#35

X The operation was canceled.
contention-test: .github#1162

! Failed to restore: Cache service responded with 400
contention-test: .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
contention-test: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
coverage-contexts: .github#2

! No files were found with the provided path: .coverage. No artifacts will be uploaded.
coverage-contexts: .github#16

X Process completed with exit code 1.
coverage-contexts: .github#1389

! Failed to restore: Cache service responded with 400
coverage-contexts: .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
coverage-contexts: .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* master CI Telemetry · 42949481249
Triggered via workflow_dispatch about 1 hour ago

JOBS
✓ build-core / build-core in 13m23s (ID 130290157276)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Resolve core mode
  ✓ Resolve pinned Rust core revision
  ✓ Check out Rust core
  - Check out published Rust core tag
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up Rust
  ✓ Cache Rust build
  ✓ Build abi3 Rust core wheel
  - Download the sealed candidate manifest
  - Fetch and verify the published core wheel
  ✓ Build macro LSP
  ✓ Record wheel provenance
  - Record published tag provenance
  ✓ Upload Rust core artifacts
  ✓ Post Cache Rust build
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Check out Rust core
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* test-cost (ID 130295013692)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run cost-attribution suite
  * Upload global leak report
  * Post Install dependencies
  * Post Run actions/checkout@v4
X contention-test in 1h30m17s (ID 130295013705)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  X Run default-lane contention harness
  ✓ Upload contention failure records
  ✓ Post Install visual dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
X coverage-contexts in 1h37m6s (ID 130295013754)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  X Record per-test coverage contexts
  ✓ Upload coverage contexts database
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
build-core / build-core: .github#4

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0ttzzagAAAAAqVB+e59loT7lKWXqkntCzU0xDMzFFREdFMDcxMwBFZGdl
build-core / build-core: .github#7

! Failed to restore: Cache service responded with 400
build-core / build-core: .github#25

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
build-core / build-core: .github#1

X The job has exceeded the maximum execution time of 1h30m0s
contention-test: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
contention-test: .github#35

X The operation was canceled.
contention-test: .github#1162

! Failed to restore: Cache service responded with 400
contention-test: .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
contention-test: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
coverage-contexts: .github#2

! No files were found with the provided path: .coverage. No artifacts will be uploaded.
coverage-contexts: .github#16

X Process completed with exit code 1.
coverage-contexts: .github#1389

! Failed to restore: Cache service responded with 400
coverage-contexts: .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
coverage-contexts: .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* master CI Telemetry · 42949481249
Triggered via workflow_dispatch about 2 hours ago

JOBS
✓ build-core / build-core in 13m23s (ID 130290157276)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Resolve core mode
  ✓ Resolve pinned Rust core revision
  ✓ Check out Rust core
  - Check out published Rust core tag
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up Rust
  ✓ Cache Rust build
  ✓ Build abi3 Rust core wheel
  - Download the sealed candidate manifest
  - Fetch and verify the published core wheel
  ✓ Build macro LSP
  ✓ Record wheel provenance
  - Record published tag provenance
  ✓ Upload Rust core artifacts
  ✓ Post Cache Rust build
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Check out Rust core
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* test-cost (ID 130295013692)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run cost-attribution suite
  * Upload global leak report
  * Post Install dependencies
  * Post Run actions/checkout@v4
X contention-test in 1h30m17s (ID 130295013705)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  X Run default-lane contention harness
  ✓ Upload contention failure records
  ✓ Post Install visual dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
X coverage-contexts in 1h37m6s (ID 130295013754)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  X Record per-test coverage contexts
  ✓ Upload coverage contexts database
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
build-core / build-core: .github#4

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0ttzzagAAAAAqVB+e59loT7lKWXqkntCzU0xDMzFFREdFMDcxMwBFZGdl
build-core / build-core: .github#7

! Failed to restore: Cache service responded with 400
build-core / build-core: .github#25

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
build-core / build-core: .github#1

X The job has exceeded the maximum execution time of 1h30m0s
contention-test: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
contention-test: .github#35

X The operation was canceled.
contention-test: .github#1162

! Failed to restore: Cache service responded with 400
contention-test: .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
contention-test: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
coverage-contexts: .github#2

! No files were found with the provided path: .coverage. No artifacts will be uploaded.
coverage-contexts: .github#16

X Process completed with exit code 1.
coverage-contexts: .github#1389

! Failed to restore: Cache service responded with 400
coverage-contexts: .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
coverage-contexts: .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* master CI Telemetry · 42949481249
Triggered via workflow_dispatch about 2 hours ago

JOBS
✓ build-core / build-core in 13m23s (ID 130290157276)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Resolve core mode
  ✓ Resolve pinned Rust core revision
  ✓ Check out Rust core
  - Check out published Rust core tag
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up Rust
  ✓ Cache Rust build
  ✓ Build abi3 Rust core wheel
  - Download the sealed candidate manifest
  - Fetch and verify the published core wheel
  ✓ Build macro LSP
  ✓ Record wheel provenance
  - Record published tag provenance
  ✓ Upload Rust core artifacts
  ✓ Post Cache Rust build
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Check out Rust core
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* test-cost (ID 130295013692)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run cost-attribution suite
  * Upload global leak report
  * Post Install dependencies
  * Post Run actions/checkout@v4
X contention-test in 1h30m17s (ID 130295013705)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  X Run default-lane contention harness
  ✓ Upload contention failure records
  ✓ Post Install visual dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
X coverage-contexts in 1h37m6s (ID 130295013754)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  X Record per-test coverage contexts
  ✓ Upload coverage contexts database
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
build-core / build-core: .github#4

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0ttzzagAAAAAqVB+e59loT7lKWXqkntCzU0xDMzFFREdFMDcxMwBFZGdl
build-core / build-core: .github#7

! Failed to restore: Cache service responded with 400
build-core / build-core: .github#25

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
build-core / build-core: .github#1

X The job has exceeded the maximum execution time of 1h30m0s
contention-test: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
contention-test: .github#35

X The operation was canceled.
contention-test: .github#1162

! Failed to restore: Cache service responded with 400
contention-test: .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
contention-test: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
coverage-contexts: .github#2

! No files were found with the provided path: .coverage. No artifacts will be uploaded.
coverage-contexts: .github#16

X Process completed with exit code 1.
coverage-contexts: .github#1389

! Failed to restore: Cache service responded with 400
coverage-contexts: .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
coverage-contexts: .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* master CI Telemetry · 42949481249
Triggered via workflow_dispatch about 2 hours ago

JOBS
✓ build-core / build-core in 13m23s (ID 130290157276)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Resolve core mode
  ✓ Resolve pinned Rust core revision
  ✓ Check out Rust core
  - Check out published Rust core tag
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up Rust
  ✓ Cache Rust build
  ✓ Build abi3 Rust core wheel
  - Download the sealed candidate manifest
  - Fetch and verify the published core wheel
  ✓ Build macro LSP
  ✓ Record wheel provenance
  - Record published tag provenance
  ✓ Upload Rust core artifacts
  ✓ Post Cache Rust build
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Check out Rust core
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* test-cost (ID 130295013692)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run cost-attribution suite
  * Upload global leak report
  * Post Install dependencies
  * Post Run actions/checkout@v4
X contention-test in 1h30m17s (ID 130295013705)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  X Run default-lane contention harness
  ✓ Upload contention failure records
  ✓ Post Install visual dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
X coverage-contexts in 1h37m6s (ID 130295013754)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  X Record per-test coverage contexts
  ✓ Upload coverage contexts database
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
build-core / build-core: .github#4

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0ttzzagAAAAAqVB+e59loT7lKWXqkntCzU0xDMzFFREdFMDcxMwBFZGdl
build-core / build-core: .github#7

! Failed to restore: Cache service responded with 400
build-core / build-core: .github#25

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
build-core / build-core: .github#1

X The job has exceeded the maximum execution time of 1h30m0s
contention-test: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
contention-test: .github#35

X The operation was canceled.
contention-test: .github#1162

! Failed to restore: Cache service responded with 400
contention-test: .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
contention-test: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
coverage-contexts: .github#2

! No files were found with the provided path: .coverage. No artifacts will be uploaded.
coverage-contexts: .github#16

X Process completed with exit code 1.
coverage-contexts: .github#1389

! Failed to restore: Cache service responded with 400
coverage-contexts: .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
coverage-contexts: .github#1

X master CI Telemetry · 42949481249
Triggered via workflow_dispatch about 2 hours ago

JOBS
✓ build-core / build-core in 13m23s (ID 130290157276)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Resolve core mode
  ✓ Resolve pinned Rust core revision
  ✓ Check out Rust core
  - Check out published Rust core tag
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up Rust
  ✓ Cache Rust build
  ✓ Build abi3 Rust core wheel
  - Download the sealed candidate manifest
  - Fetch and verify the published core wheel
  ✓ Build macro LSP
  ✓ Record wheel provenance
  - Record published tag provenance
  ✓ Upload Rust core artifacts
  ✓ Post Cache Rust build
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Check out Rust core
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
X test-cost in 1h52m46s (ID 130295013692)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  X Run cost-attribution suite
  ✓ Upload global leak report
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
X contention-test in 1h30m17s (ID 130295013705)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  X Run default-lane contention harness
  ✓ Upload contention failure records
  ✓ Post Install visual dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
X coverage-contexts in 1h37m6s (ID 130295013754)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  X Record per-test coverage contexts
  ✓ Upload coverage contexts database
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
build-core / build-core: .github#4

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0ttzzagAAAAAqVB+e59loT7lKWXqkntCzU0xDMzFFREdFMDcxMwBFZGdl
build-core / build-core: .github#7

! Failed to restore: Cache service responded with 400
build-core / build-core: .github#25

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
build-core / build-core: .github#1

X The job has exceeded the maximum execution time of 1h30m0s
contention-test: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
contention-test: .github#35

X The operation was canceled.
contention-test: .github#1162

! Failed to restore: Cache service responded with 400
contention-test: .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
contention-test: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
coverage-contexts: .github#2

! No files were found with the provided path: .coverage. No artifacts will be uploaded.
coverage-contexts: .github#16

X Process completed with exit code 1.
coverage-contexts: .github#1389

! Failed to restore: Cache service responded with 400
coverage-contexts: .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
coverage-contexts: .github#1


