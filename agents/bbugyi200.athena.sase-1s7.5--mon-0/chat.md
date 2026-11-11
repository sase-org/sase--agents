# Chat History - ace-run (sase-1s7.5--mon-0)

- **TIMESTAMP:** 2026-11-10 21:36:18 EST
- **MODEL:** grok/grok-4.6
- **AGENT:** sase-1s7.5--mon-0

## Prompt

sase monitor start --command 'sh /tmp/sase-1s7.5-watch.sh' --reason 'Wait for matcher-fix Master Gate, observe-only steward, and Telemetry 42933587314 for sase-1s7.5'

## Response

sase: running unwrapped (no profile (monitor.tool_wrap is verify))
origin/master=39cdbd548aa4f46e23083058d52c8f66cb59e53d
tip=39cdbd548aa4f46e23083058d52c8f66cb59e53d
master_gate=42935424350
https://github.com/sase-org/sase/actions/runs/42935514100
dispatched observe-only steward
steward=42935514100
Refreshing run status every 60 seconds. Press Ctrl+C to quit.

* master Master Gate · 42935424350
Triggered via push less than a minute ago

JOBS
* docs (ID 130244199620)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Install just
  ✓ Set up Python
  ✓ Build and validate docs
  ✓ Post Run astral-sh/setup-uv@v4
  * Post Run actions/checkout@v4
✓ core-wheel in 27s (ID 130244199950)
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
* lint (ID 130244408175)
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
* test (2) (ID 130244408293)
  ✓ Set up job
  * Run actions/checkout@v4
  * Install dependencies
  * Run sharded fast suite
  * Post Run actions/checkout@v4
* test (5) (ID 130244408300)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  * Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (6) (ID 130244408306)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  * Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (3) (ID 130244408310)
  ✓ Set up job
  * Run actions/checkout@v4
  * Install dependencies
  * Run sharded fast suite
  * Post Run actions/checkout@v4
* test (4) (ID 130244408329)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  * Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (7) (ID 130244408334)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  * Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (8) (ID 130244408335)
  ✓ Set up job
  * Run actions/checkout@v4
  * Install dependencies
  * Run sharded fast suite
  * Post Run actions/checkout@v4
* test (1) (ID 130244408378)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  * Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache/restore@v4, actions/checkout@v4, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
core-wheel: .github#2

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
core-wheel: .github#1

Refreshing run status every 60 seconds. Press Ctrl+C to quit.

* master Master Gate · 42935424350
Triggered via push about 1 minute ago

JOBS
✓ docs in 45s (ID 130244199620)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Install just
  ✓ Set up Python
  ✓ Build and validate docs
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ core-wheel in 27s (ID 130244199950)
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
* lint (ID 130244408175)
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
  * Check shipped model policy
  * Lint
  * SASE validation
  * Validate committed plans
  * Build and verify package
  * Post Cache Prettier dependencies
  * Post Cache Go binaries
  * Post Run actions/setup-go@v5
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (2) (ID 130244408293)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (5) (ID 130244408300)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (6) (ID 130244408306)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (3) (ID 130244408310)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (4) (ID 130244408329)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (7) (ID 130244408334)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (8) (ID 130244408335)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (1) (ID 130244408378)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache/restore@v4, actions/checkout@v4, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
core-wheel: .github#2

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
core-wheel: .github#1

Refreshing run status every 60 seconds. Press Ctrl+C to quit.

* master Master Gate · 42935424350
Triggered via push about 2 minutes ago

JOBS
✓ docs in 45s (ID 130244199620)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Install just
  ✓ Set up Python
  ✓ Build and validate docs
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ core-wheel in 27s (ID 130244199950)
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
* lint (ID 130244408175)
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
* test (2) (ID 130244408293)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (5) (ID 130244408300)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (6) (ID 130244408306)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (3) (ID 130244408310)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (4) (ID 130244408329)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (7) (ID 130244408334)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (8) (ID 130244408335)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (1) (ID 130244408378)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache/restore@v4, actions/checkout@v4, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
core-wheel: .github#2

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
core-wheel: .github#1

Refreshing run status every 60 seconds. Press Ctrl+C to quit.

* master Master Gate · 42935424350
Triggered via push about 3 minutes ago

JOBS
✓ docs in 45s (ID 130244199620)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Install just
  ✓ Set up Python
  ✓ Build and validate docs
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ core-wheel in 27s (ID 130244199950)
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
* lint (ID 130244408175)
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
* test (2) (ID 130244408293)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (5) (ID 130244408300)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (6) (ID 130244408306)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (3) (ID 130244408310)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (4) (ID 130244408329)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (7) (ID 130244408334)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (8) (ID 130244408335)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (1) (ID 130244408378)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache/restore@v4, actions/checkout@v4, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
core-wheel: .github#2

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
core-wheel: .github#1

Refreshing run status every 60 seconds. Press Ctrl+C to quit.

* master Master Gate · 42935424350
Triggered via push about 4 minutes ago

JOBS
✓ docs in 45s (ID 130244199620)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Install just
  ✓ Set up Python
  ✓ Build and validate docs
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ core-wheel in 27s (ID 130244199950)
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
* lint (ID 130244408175)
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
  * SASE validation
  * Validate committed plans
  * Build and verify package
  * Post Cache Prettier dependencies
  * Post Cache Go binaries
  * Post Run actions/setup-go@v5
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (2) (ID 130244408293)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (5) (ID 130244408300)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (6) (ID 130244408306)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (3) (ID 130244408310)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (4) (ID 130244408329)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (7) (ID 130244408334)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (8) (ID 130244408335)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (1) (ID 130244408378)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache/restore@v4, actions/checkout@v4, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
core-wheel: .github#2

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
core-wheel: .github#1

Refreshing run status every 60 seconds. Press Ctrl+C to quit.

* master Master Gate · 42935424350
Triggered via push about 6 minutes ago

JOBS
✓ docs in 45s (ID 130244199620)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Install just
  ✓ Set up Python
  ✓ Build and validate docs
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ core-wheel in 27s (ID 130244199950)
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
✓ lint in 5m17s (ID 130244408175)
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
* test (2) (ID 130244408293)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (5) (ID 130244408300)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (6) (ID 130244408306)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (3) (ID 130244408310)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (4) (ID 130244408329)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (7) (ID 130244408334)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (8) (ID 130244408335)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (1) (ID 130244408378)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache/restore@v4, actions/checkout@v4, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
core-wheel: .github#2

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
core-wheel: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache@v4, actions/checkout@v4, actions/download-artifact@v4, actions/setup-go@v5, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
lint: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0+L7zagAAAADRRyVECTwBQpAYQZhN8uFHQ0gxQUEyMDMwODEzMDM2AEVkZ2U=
lint: .github#9

! Failed to restore: Cache service responded with 400
lint: .github#54

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
lint: .github#1

Refreshing run status every 60 seconds. Press Ctrl+C to quit.

* master Master Gate · 42935424350
Triggered via push about 7 minutes ago

JOBS
✓ docs in 45s (ID 130244199620)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Install just
  ✓ Set up Python
  ✓ Build and validate docs
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ core-wheel in 27s (ID 130244199950)
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
✓ lint in 5m17s (ID 130244408175)
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
* test (2) (ID 130244408293)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (5) (ID 130244408300)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (6) (ID 130244408306)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (3) (ID 130244408310)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (4) (ID 130244408329)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (7) (ID 130244408334)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (8) (ID 130244408335)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (1) (ID 130244408378)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache/restore@v4, actions/checkout@v4, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
core-wheel: .github#2

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
core-wheel: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache@v4, actions/checkout@v4, actions/download-artifact@v4, actions/setup-go@v5, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
lint: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0+L7zagAAAADRRyVECTwBQpAYQZhN8uFHQ0gxQUEyMDMwODEzMDM2AEVkZ2U=
lint: .github#9

! Failed to restore: Cache service responded with 400
lint: .github#54

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
lint: .github#1

Refreshing run status every 60 seconds. Press Ctrl+C to quit.

* master Master Gate · 42935424350
Triggered via push about 8 minutes ago

JOBS
✓ docs in 45s (ID 130244199620)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Install just
  ✓ Set up Python
  ✓ Build and validate docs
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ core-wheel in 27s (ID 130244199950)
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
✓ lint in 5m17s (ID 130244408175)
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
* test (2) (ID 130244408293)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (5) (ID 130244408300)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (6) (ID 130244408306)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (3) (ID 130244408310)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (4) (ID 130244408329)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (7) (ID 130244408334)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (8) (ID 130244408335)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (1) (ID 130244408378)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache/restore@v4, actions/checkout@v4, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
core-wheel: .github#2

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
core-wheel: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache@v4, actions/checkout@v4, actions/download-artifact@v4, actions/setup-go@v5, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
lint: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0+L7zagAAAADRRyVECTwBQpAYQZhN8uFHQ0gxQUEyMDMwODEzMDM2AEVkZ2U=
lint: .github#9

! Failed to restore: Cache service responded with 400
lint: .github#54

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
lint: .github#1

Refreshing run status every 60 seconds. Press Ctrl+C to quit.

* master Master Gate · 42935424350
Triggered via push about 9 minutes ago

JOBS
✓ docs in 45s (ID 130244199620)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Install just
  ✓ Set up Python
  ✓ Build and validate docs
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ core-wheel in 27s (ID 130244199950)
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
✓ lint in 5m17s (ID 130244408175)
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
✓ test (2) in 8m3s (ID 130244408293)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* test (5) (ID 130244408300)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (6) (ID 130244408306)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (3) (ID 130244408310)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (4) (ID 130244408329)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (7) (ID 130244408334)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (8) (ID 130244408335)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (1) (ID 130244408378)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache/restore@v4, actions/checkout@v4, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
core-wheel: .github#2

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
core-wheel: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache@v4, actions/checkout@v4, actions/download-artifact@v4, actions/setup-go@v5, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
lint: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0+L7zagAAAADRRyVECTwBQpAYQZhN8uFHQ0gxQUEyMDMwODEzMDM2AEVkZ2U=
lint: .github#9

! Failed to restore: Cache service responded with 400
lint: .github#54

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
lint: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
test (2): .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0n7/zagAAAADwPRZBgjOiRq3IYBJJvk2CQ0gxQUEyMDMwODEzMDQwAEVkZ2U=
test (2): .github#9

! Failed to restore: Cache service responded with 400
test (2): .github#54

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
test (2): .github#1

Refreshing run status every 60 seconds. Press Ctrl+C to quit.

* master Master Gate · 42935424350
Triggered via push about 10 minutes ago

JOBS
✓ docs in 45s (ID 130244199620)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Install just
  ✓ Set up Python
  ✓ Build and validate docs
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ core-wheel in 27s (ID 130244199950)
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
✓ lint in 5m17s (ID 130244408175)
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
✓ test (2) in 8m3s (ID 130244408293)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ test (5) in 9m22s (ID 130244408300)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* test (6) (ID 130244408306)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (3) (ID 130244408310)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (4) (ID 130244408329)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (7) (ID 130244408334)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (8) (ID 130244408335)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
✓ test (1) in 9m17s (ID 130244408378)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache/restore@v4, actions/checkout@v4, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
core-wheel: .github#2

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
core-wheel: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache@v4, actions/checkout@v4, actions/download-artifact@v4, actions/setup-go@v5, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
lint: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0+L7zagAAAADRRyVECTwBQpAYQZhN8uFHQ0gxQUEyMDMwODEzMDM2AEVkZ2U=
lint: .github#9

! Failed to restore: Cache service responded with 400
lint: .github#54

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
lint: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
test (2): .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0n7/zagAAAADwPRZBgjOiRq3IYBJJvk2CQ0gxQUEyMDMwODEzMDQwAEVkZ2U=
test (2): .github#9

! Failed to restore: Cache service responded with 400
test (2): .github#54

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
test (2): .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
test (5): .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>07r/zagAAAAD+KbMhd0UASrXWOB1jH5WlUEhYMzFFREdFMDUxMwBFZGdl
test (5): .github#9

! Failed to restore: Cache service responded with 400
test (5): .github#54

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
test (5): .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
test (1): .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>06b/zagAAAACfMw25kovGR7hwn+8b4/3EQ0gxQUEyMDMwODE0MDQwAEVkZ2U=
test (1): .github#9

! Failed to restore: Cache service responded with 400
test (1): .github#54

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
test (1): .github#1

Refreshing run status every 60 seconds. Press Ctrl+C to quit.

* master Master Gate · 42935424350
Triggered via push about 11 minutes ago

JOBS
✓ docs in 45s (ID 130244199620)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Install just
  ✓ Set up Python
  ✓ Build and validate docs
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ core-wheel in 27s (ID 130244199950)
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
✓ lint in 5m17s (ID 130244408175)
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
✓ test (2) in 8m3s (ID 130244408293)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ test (5) in 9m22s (ID 130244408300)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ test (6) in 9m43s (ID 130244408306)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* test (3) (ID 130244408310)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (4) (ID 130244408329)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (7) (ID 130244408334)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
✓ test (8) in 10m36s (ID 130244408335)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ test (1) in 9m17s (ID 130244408378)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache/restore@v4, actions/checkout@v4, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
core-wheel: .github#2

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
core-wheel: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache@v4, actions/checkout@v4, actions/download-artifact@v4, actions/setup-go@v5, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
lint: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0+L7zagAAAADRRyVECTwBQpAYQZhN8uFHQ0gxQUEyMDMwODEzMDM2AEVkZ2U=
lint: .github#9

! Failed to restore: Cache service responded with 400
lint: .github#54

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
lint: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
test (2): .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0n7/zagAAAADwPRZBgjOiRq3IYBJJvk2CQ0gxQUEyMDMwODEzMDQwAEVkZ2U=
test (2): .github#9

! Failed to restore: Cache service responded with 400
test (2): .github#54

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
test (2): .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
test (5): .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>07r/zagAAAAD+KbMhd0UASrXWOB1jH5WlUEhYMzFFREdFMDUxMwBFZGdl
test (5): .github#9

! Failed to restore: Cache service responded with 400
test (5): .github#54

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
test (5): .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
test (6): .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0A8DzagAAAACO1+SdN+gjT45Fgz6KdzHjQ0gxQUEyMDMwODE0MDMxAEVkZ2U=
test (6): .github#9

! Failed to restore: Cache service responded with 400
test (6): .github#54

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
test (6): .github#1

Refreshing run status every 60 seconds. Press Ctrl+C to quit.

* master Master Gate · 42935424350
Triggered via push about 12 minutes ago

JOBS
✓ docs in 45s (ID 130244199620)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Install just
  ✓ Set up Python
  ✓ Build and validate docs
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ core-wheel in 27s (ID 130244199950)
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
✓ lint in 5m17s (ID 130244408175)
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
✓ test (2) in 8m3s (ID 130244408293)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ test (5) in 9m22s (ID 130244408300)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ test (6) in 9m43s (ID 130244408306)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* test (3) (ID 130244408310)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (4) (ID 130244408329)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (7) (ID 130244408334)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
✓ test (8) in 10m36s (ID 130244408335)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ test (1) in 9m17s (ID 130244408378)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache/restore@v4, actions/checkout@v4, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
core-wheel: .github#2

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
core-wheel: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache@v4, actions/checkout@v4, actions/download-artifact@v4, actions/setup-go@v5, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
lint: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0+L7zagAAAADRRyVECTwBQpAYQZhN8uFHQ0gxQUEyMDMwODEzMDM2AEVkZ2U=
lint: .github#9

! Failed to restore: Cache service responded with 400
lint: .github#54

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
lint: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
test (2): .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0n7/zagAAAADwPRZBgjOiRq3IYBJJvk2CQ0gxQUEyMDMwODEzMDQwAEVkZ2U=
test (2): .github#9

! Failed to restore: Cache service responded with 400
test (2): .github#54

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
test (2): .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
test (5): .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>07r/zagAAAAD+KbMhd0UASrXWOB1jH5WlUEhYMzFFREdFMDUxMwBFZGdl
test (5): .github#9

! Failed to restore: Cache service responded with 400
test (5): .github#54

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
test (5): .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
test (6): .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0A8DzagAAAACO1+SdN+gjT45Fgz6KdzHjQ0gxQUEyMDMwODE0MDMxAEVkZ2U=
test (6): .github#9

! Failed to restore: Cache service responded with 400
test (6): .github#54

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
test (6): .github#1

✓ master Master Gate · 42935424350
Triggered via push about 13 minutes ago

JOBS
✓ docs in 45s (ID 130244199620)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Install just
  ✓ Set up Python
  ✓ Build and validate docs
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ core-wheel in 27s (ID 130244199950)
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
✓ lint in 5m17s (ID 130244408175)
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
✓ test (2) in 8m3s (ID 130244408293)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ test (5) in 9m22s (ID 130244408300)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ test (6) in 9m43s (ID 130244408306)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ test (3) in 12m6s (ID 130244408310)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ test (4) in 12m0s (ID 130244408329)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ test (7) in 12m1s (ID 130244408334)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ test (8) in 10m36s (ID 130244408335)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ test (1) in 9m17s (ID 130244408378)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache/restore@v4, actions/checkout@v4, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
core-wheel: .github#2

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
core-wheel: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache@v4, actions/checkout@v4, actions/download-artifact@v4, actions/setup-go@v5, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
lint: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0+L7zagAAAADRRyVECTwBQpAYQZhN8uFHQ0gxQUEyMDMwODEzMDM2AEVkZ2U=
lint: .github#9

! Failed to restore: Cache service responded with 400
lint: .github#54

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
lint: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
test (2): .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0n7/zagAAAADwPRZBgjOiRq3IYBJJvk2CQ0gxQUEyMDMwODEzMDQwAEVkZ2U=
test (2): .github#9

! Failed to restore: Cache service responded with 400
test (2): .github#54

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
test (2): .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
test (5): .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>07r/zagAAAAD+KbMhd0UASrXWOB1jH5WlUEhYMzFFREdFMDUxMwBFZGdl
test (5): .github#9

! Failed to restore: Cache service responded with 400
test (5): .github#54

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
test (5): .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
test (6): .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0A8DzagAAAACO1+SdN+gjT45Fgz6KdzHjQ0gxQUEyMDMwODE0MDMxAEVkZ2U=
test (6): .github#9

! Failed to restore: Cache service responded with 400
test (6): .github#54

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
test (6): .github#1

Run Release steward (42935514100) has already completed with 'success'
Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* master CI Telemetry · 42933587314
Triggered via workflow_dispatch about 27 minutes ago

JOBS
✓ build-core / build-core in 11m19s (ID 130238055792)
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
* contention-test (ID 130242902322)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  * Run default-lane contention harness
  * Upload contention failure records
  * Post Install visual dependencies
  * Post Run actions/checkout@v4
* coverage-contexts (ID 130242902347)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Record per-test coverage contexts
  * Upload coverage contexts database
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test-cost (ID 130242902364)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run cost-attribution suite
  * Post Install dependencies
  * Post Run actions/checkout@v4

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
build-core / build-core: .github#4

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>027zzagAAAAAmH6abfnv9S4xiuquyWWzZQ0gxQUEyMDMwODE0MDI5AEVkZ2U=
build-core / build-core: .github#7

! Failed to restore: Cache service responded with 400
build-core / build-core: .github#25

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
build-core / build-core: .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* master CI Telemetry · 42933587314
Triggered via workflow_dispatch about 29 minutes ago

JOBS
✓ build-core / build-core in 11m19s (ID 130238055792)
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
* contention-test (ID 130242902322)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  * Run default-lane contention harness
  * Upload contention failure records
  * Post Install visual dependencies
  * Post Run actions/checkout@v4
* coverage-contexts (ID 130242902347)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Record per-test coverage contexts
  * Upload coverage contexts database
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test-cost (ID 130242902364)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run cost-attribution suite
  * Post Install dependencies
  * Post Run actions/checkout@v4

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
build-core / build-core: .github#4

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>027zzagAAAAAmH6abfnv9S4xiuquyWWzZQ0gxQUEyMDMwODE0MDI5AEVkZ2U=
build-core / build-core: .github#7

! Failed to restore: Cache service responded with 400
build-core / build-core: .github#25

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
build-core / build-core: .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* master CI Telemetry · 42933587314
Triggered via workflow_dispatch about 31 minutes ago

JOBS
✓ build-core / build-core in 11m19s (ID 130238055792)
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
* contention-test (ID 130242902322)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  * Run default-lane contention harness
  * Upload contention failure records
  * Post Install visual dependencies
  * Post Run actions/checkout@v4
* coverage-contexts (ID 130242902347)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Record per-test coverage contexts
  * Upload coverage contexts database
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test-cost (ID 130242902364)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run cost-attribution suite
  * Post Install dependencies
  * Post Run actions/checkout@v4

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
build-core / build-core: .github#4

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>027zzagAAAAAmH6abfnv9S4xiuquyWWzZQ0gxQUEyMDMwODE0MDI5AEVkZ2U=
build-core / build-core: .github#7

! Failed to restore: Cache service responded with 400
build-core / build-core: .github#25

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
build-core / build-core: .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* master CI Telemetry · 42933587314
Triggered via workflow_dispatch about 33 minutes ago

JOBS
✓ build-core / build-core in 11m19s (ID 130238055792)
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
* contention-test (ID 130242902322)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  * Run default-lane contention harness
  * Upload contention failure records
  * Post Install visual dependencies
  * Post Run actions/checkout@v4
* coverage-contexts (ID 130242902347)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Record per-test coverage contexts
  * Upload coverage contexts database
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test-cost (ID 130242902364)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run cost-attribution suite
  * Post Install dependencies
  * Post Run actions/checkout@v4

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
build-core / build-core: .github#4

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>027zzagAAAAAmH6abfnv9S4xiuquyWWzZQ0gxQUEyMDMwODE0MDI5AEVkZ2U=
build-core / build-core: .github#7

! Failed to restore: Cache service responded with 400
build-core / build-core: .github#25

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
build-core / build-core: .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* master CI Telemetry · 42933587314
Triggered via workflow_dispatch about 35 minutes ago

JOBS
✓ build-core / build-core in 11m19s (ID 130238055792)
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
* contention-test (ID 130242902322)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  * Run default-lane contention harness
  * Upload contention failure records
  * Post Install visual dependencies
  * Post Run actions/checkout@v4
* coverage-contexts (ID 130242902347)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Record per-test coverage contexts
  * Upload coverage contexts database
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test-cost (ID 130242902364)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run cost-attribution suite
  * Post Install dependencies
  * Post Run actions/checkout@v4

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
build-core / build-core: .github#4

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>027zzagAAAAAmH6abfnv9S4xiuquyWWzZQ0gxQUEyMDMwODE0MDI5AEVkZ2U=
build-core / build-core: .github#7

! Failed to restore: Cache service responded with 400
build-core / build-core: .github#25

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
build-core / build-core: .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* master CI Telemetry · 42933587314
Triggered via workflow_dispatch about 37 minutes ago

JOBS
✓ build-core / build-core in 11m19s (ID 130238055792)
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
* contention-test (ID 130242902322)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  * Run default-lane contention harness
  * Upload contention failure records
  * Post Install visual dependencies
  * Post Run actions/checkout@v4
* coverage-contexts (ID 130242902347)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Record per-test coverage contexts
  * Upload coverage contexts database
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test-cost (ID 130242902364)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run cost-attribution suite
  * Post Install dependencies
  * Post Run actions/checkout@v4

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
build-core / build-core: .github#4

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>027zzagAAAAAmH6abfnv9S4xiuquyWWzZQ0gxQUEyMDMwODE0MDI5AEVkZ2U=
build-core / build-core: .github#7

! Failed to restore: Cache service responded with 400
build-core / build-core: .github#25

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
build-core / build-core: .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* master CI Telemetry · 42933587314
Triggered via workflow_dispatch about 40 minutes ago

JOBS
✓ build-core / build-core in 11m19s (ID 130238055792)
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
* contention-test (ID 130242902322)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  * Run default-lane contention harness
  * Upload contention failure records
  * Post Install visual dependencies
  * Post Run actions/checkout@v4
* coverage-contexts (ID 130242902347)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Record per-test coverage contexts
  * Upload coverage contexts database
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test-cost (ID 130242902364)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run cost-attribution suite
  * Post Install dependencies
  * Post Run actions/checkout@v4

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
build-core / build-core: .github#4

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>027zzagAAAAAmH6abfnv9S4xiuquyWWzZQ0gxQUEyMDMwODE0MDI5AEVkZ2U=
build-core / build-core: .github#7

! Failed to restore: Cache service responded with 400
build-core / build-core: .github#25

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
build-core / build-core: .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* master CI Telemetry · 42933587314
Triggered via workflow_dispatch about 42 minutes ago

JOBS
✓ build-core / build-core in 11m19s (ID 130238055792)
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
* contention-test (ID 130242902322)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  * Run default-lane contention harness
  * Upload contention failure records
  * Post Install visual dependencies
  * Post Run actions/checkout@v4
* coverage-contexts (ID 130242902347)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Record per-test coverage contexts
  * Upload coverage contexts database
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test-cost (ID 130242902364)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run cost-attribution suite
  * Post Install dependencies
  * Post Run actions/checkout@v4

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
build-core / build-core: .github#4

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>027zzagAAAAAmH6abfnv9S4xiuquyWWzZQ0gxQUEyMDMwODE0MDI5AEVkZ2U=
build-core / build-core: .github#7

! Failed to restore: Cache service responded with 400
build-core / build-core: .github#25

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
build-core / build-core: .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* master CI Telemetry · 42933587314
Triggered via workflow_dispatch about 44 minutes ago

JOBS
✓ build-core / build-core in 11m19s (ID 130238055792)
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
* contention-test (ID 130242902322)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  * Run default-lane contention harness
  * Upload contention failure records
  * Post Install visual dependencies
  * Post Run actions/checkout@v4
* coverage-contexts (ID 130242902347)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Record per-test coverage contexts
  * Upload coverage contexts database
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test-cost (ID 130242902364)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run cost-attribution suite
  * Post Install dependencies
  * Post Run actions/checkout@v4

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
build-core / build-core: .github#4

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>027zzagAAAAAmH6abfnv9S4xiuquyWWzZQ0gxQUEyMDMwODE0MDI5AEVkZ2U=
build-core / build-core: .github#7

! Failed to restore: Cache service responded with 400
build-core / build-core: .github#25

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
build-core / build-core: .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* master CI Telemetry · 42933587314
Triggered via workflow_dispatch about 46 minutes ago

JOBS
✓ build-core / build-core in 11m19s (ID 130238055792)
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
* contention-test (ID 130242902322)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  * Run default-lane contention harness
  * Upload contention failure records
  * Post Install visual dependencies
  * Post Run actions/checkout@v4
* coverage-contexts (ID 130242902347)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Record per-test coverage contexts
  * Upload coverage contexts database
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test-cost (ID 130242902364)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run cost-attribution suite
  * Post Install dependencies
  * Post Run actions/checkout@v4

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
build-core / build-core: .github#4

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>027zzagAAAAAmH6abfnv9S4xiuquyWWzZQ0gxQUEyMDMwODE0MDI5AEVkZ2U=
build-core / build-core: .github#7

! Failed to restore: Cache service responded with 400
build-core / build-core: .github#25

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
build-core / build-core: .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* master CI Telemetry · 42933587314
Triggered via workflow_dispatch about 48 minutes ago

JOBS
✓ build-core / build-core in 11m19s (ID 130238055792)
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
* contention-test (ID 130242902322)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  * Run default-lane contention harness
  * Upload contention failure records
  * Post Install visual dependencies
  * Post Run actions/checkout@v4
* coverage-contexts (ID 130242902347)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Record per-test coverage contexts
  * Upload coverage contexts database
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test-cost (ID 130242902364)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run cost-attribution suite
  * Post Install dependencies
  * Post Run actions/checkout@v4

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
build-core / build-core: .github#4

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>027zzagAAAAAmH6abfnv9S4xiuquyWWzZQ0gxQUEyMDMwODE0MDI5AEVkZ2U=
build-core / build-core: .github#7

! Failed to restore: Cache service responded with 400
build-core / build-core: .github#25

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
build-core / build-core: .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* master CI Telemetry · 42933587314
Triggered via workflow_dispatch about 50 minutes ago

JOBS
✓ build-core / build-core in 11m19s (ID 130238055792)
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
* contention-test (ID 130242902322)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  * Run default-lane contention harness
  * Upload contention failure records
  * Post Install visual dependencies
  * Post Run actions/checkout@v4
* coverage-contexts (ID 130242902347)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Record per-test coverage contexts
  * Upload coverage contexts database
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test-cost (ID 130242902364)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run cost-attribution suite
  * Post Install dependencies
  * Post Run actions/checkout@v4

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
build-core / build-core: .github#4

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>027zzagAAAAAmH6abfnv9S4xiuquyWWzZQ0gxQUEyMDMwODE0MDI5AEVkZ2U=
build-core / build-core: .github#7

! Failed to restore: Cache service responded with 400
build-core / build-core: .github#25

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
build-core / build-core: .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* master CI Telemetry · 42933587314
Triggered via workflow_dispatch about 52 minutes ago

JOBS
✓ build-core / build-core in 11m19s (ID 130238055792)
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
* contention-test (ID 130242902322)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  * Run default-lane contention harness
  * Upload contention failure records
  * Post Install visual dependencies
  * Post Run actions/checkout@v4
* coverage-contexts (ID 130242902347)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Record per-test coverage contexts
  * Upload coverage contexts database
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test-cost (ID 130242902364)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run cost-attribution suite
  * Post Install dependencies
  * Post Run actions/checkout@v4

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
build-core / build-core: .github#4

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>027zzagAAAAAmH6abfnv9S4xiuquyWWzZQ0gxQUEyMDMwODE0MDI5AEVkZ2U=
build-core / build-core: .github#7

! Failed to restore: Cache service responded with 400
build-core / build-core: .github#25

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
build-core / build-core: .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* master CI Telemetry · 42933587314
Triggered via workflow_dispatch about 54 minutes ago

JOBS
✓ build-core / build-core in 11m19s (ID 130238055792)
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
* contention-test (ID 130242902322)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  * Run default-lane contention harness
  * Upload contention failure records
  * Post Install visual dependencies
  * Post Run actions/checkout@v4
* coverage-contexts (ID 130242902347)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Record per-test coverage contexts
  * Upload coverage contexts database
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test-cost (ID 130242902364)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run cost-attribution suite
  * Post Install dependencies
  * Post Run actions/checkout@v4

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
build-core / build-core: .github#4

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>027zzagAAAAAmH6abfnv9S4xiuquyWWzZQ0gxQUEyMDMwODE0MDI5AEVkZ2U=
build-core / build-core: .github#7

! Failed to restore: Cache service responded with 400
build-core / build-core: .github#25

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
build-core / build-core: .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* master CI Telemetry · 42933587314
Triggered via workflow_dispatch about 56 minutes ago

JOBS
✓ build-core / build-core in 11m19s (ID 130238055792)
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
* contention-test (ID 130242902322)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  * Run default-lane contention harness
  * Upload contention failure records
  * Post Install visual dependencies
  * Post Run actions/checkout@v4
* coverage-contexts (ID 130242902347)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Record per-test coverage contexts
  * Upload coverage contexts database
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test-cost (ID 130242902364)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run cost-attribution suite
  * Post Install dependencies
  * Post Run actions/checkout@v4

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
build-core / build-core: .github#4

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>027zzagAAAAAmH6abfnv9S4xiuquyWWzZQ0gxQUEyMDMwODE0MDI5AEVkZ2U=
build-core / build-core: .github#7

! Failed to restore: Cache service responded with 400
build-core / build-core: .github#25

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
build-core / build-core: .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* master CI Telemetry · 42933587314
Triggered via workflow_dispatch about 58 minutes ago

JOBS
✓ build-core / build-core in 11m19s (ID 130238055792)
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
* contention-test (ID 130242902322)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  * Run default-lane contention harness
  * Upload contention failure records
  * Post Install visual dependencies
  * Post Run actions/checkout@v4
* coverage-contexts (ID 130242902347)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Record per-test coverage contexts
  * Upload coverage contexts database
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test-cost (ID 130242902364)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run cost-attribution suite
  * Post Install dependencies
  * Post Run actions/checkout@v4

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
build-core / build-core: .github#4

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>027zzagAAAAAmH6abfnv9S4xiuquyWWzZQ0gxQUEyMDMwODE0MDI5AEVkZ2U=
build-core / build-core: .github#7

! Failed to restore: Cache service responded with 400
build-core / build-core: .github#25

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
build-core / build-core: .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* master CI Telemetry · 42933587314
Triggered via workflow_dispatch about 1 hour ago

JOBS
✓ build-core / build-core in 11m19s (ID 130238055792)
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
* contention-test (ID 130242902322)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  * Run default-lane contention harness
  * Upload contention failure records
  * Post Install visual dependencies
  * Post Run actions/checkout@v4
* coverage-contexts (ID 130242902347)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Record per-test coverage contexts
  * Upload coverage contexts database
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test-cost (ID 130242902364)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run cost-attribution suite
  * Post Install dependencies
  * Post Run actions/checkout@v4

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
build-core / build-core: .github#4

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>027zzagAAAAAmH6abfnv9S4xiuquyWWzZQ0gxQUEyMDMwODE0MDI5AEVkZ2U=
build-core / build-core: .github#7

! Failed to restore: Cache service responded with 400
build-core / build-core: .github#25

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
build-core / build-core: .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* master CI Telemetry · 42933587314
Triggered via workflow_dispatch about 1 hour ago

JOBS
✓ build-core / build-core in 11m19s (ID 130238055792)
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
* contention-test (ID 130242902322)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  * Run default-lane contention harness
  * Upload contention failure records
  * Post Install visual dependencies
  * Post Run actions/checkout@v4
* coverage-contexts (ID 130242902347)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Record per-test coverage contexts
  * Upload coverage contexts database
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test-cost (ID 130242902364)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run cost-attribution suite
  * Post Install dependencies
  * Post Run actions/checkout@v4

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
build-core / build-core: .github#4

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>027zzagAAAAAmH6abfnv9S4xiuquyWWzZQ0gxQUEyMDMwODE0MDI5AEVkZ2U=
build-core / build-core: .github#7

! Failed to restore: Cache service responded with 400
build-core / build-core: .github#25

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
build-core / build-core: .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* master CI Telemetry · 42933587314
Triggered via workflow_dispatch about 1 hour ago

JOBS
✓ build-core / build-core in 11m19s (ID 130238055792)
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
* contention-test (ID 130242902322)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  * Run default-lane contention harness
  * Upload contention failure records
  * Post Install visual dependencies
  * Post Run actions/checkout@v4
* coverage-contexts (ID 130242902347)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Record per-test coverage contexts
  * Upload coverage contexts database
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test-cost (ID 130242902364)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run cost-attribution suite
  * Post Install dependencies
  * Post Run actions/checkout@v4

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
build-core / build-core: .github#4

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>027zzagAAAAAmH6abfnv9S4xiuquyWWzZQ0gxQUEyMDMwODE0MDI5AEVkZ2U=
build-core / build-core: .github#7

! Failed to restore: Cache service responded with 400
build-core / build-core: .github#25

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
build-core / build-core: .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* master CI Telemetry · 42933587314
Triggered via workflow_dispatch about 1 hour ago

JOBS
✓ build-core / build-core in 11m19s (ID 130238055792)
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
* contention-test (ID 130242902322)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  * Run default-lane contention harness
  * Upload contention failure records
  * Post Install visual dependencies
  * Post Run actions/checkout@v4
* coverage-contexts (ID 130242902347)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Record per-test coverage contexts
  * Upload coverage contexts database
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test-cost (ID 130242902364)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run cost-attribution suite
  * Post Install dependencies
  * Post Run actions/checkout@v4

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
build-core / build-core: .github#4

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>027zzagAAAAAmH6abfnv9S4xiuquyWWzZQ0gxQUEyMDMwODE0MDI5AEVkZ2U=
build-core / build-core: .github#7

! Failed to restore: Cache service responded with 400
build-core / build-core: .github#25

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
build-core / build-core: .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* master CI Telemetry · 42933587314
Triggered via workflow_dispatch about 1 hour ago

JOBS
✓ build-core / build-core in 11m19s (ID 130238055792)
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
* contention-test (ID 130242902322)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  * Run default-lane contention harness
  * Upload contention failure records
  * Post Install visual dependencies
  * Post Run actions/checkout@v4
* coverage-contexts (ID 130242902347)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Record per-test coverage contexts
  * Upload coverage contexts database
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test-cost (ID 130242902364)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run cost-attribution suite
  * Post Install dependencies
  * Post Run actions/checkout@v4

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
build-core / build-core: .github#4

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>027zzagAAAAAmH6abfnv9S4xiuquyWWzZQ0gxQUEyMDMwODE0MDI5AEVkZ2U=
build-core / build-core: .github#7

! Failed to restore: Cache service responded with 400
build-core / build-core: .github#25

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
build-core / build-core: .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* master CI Telemetry · 42933587314
Triggered via workflow_dispatch about 1 hour ago

JOBS
✓ build-core / build-core in 11m19s (ID 130238055792)
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
* contention-test (ID 130242902322)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  * Run default-lane contention harness
  * Upload contention failure records
  * Post Install visual dependencies
  * Post Run actions/checkout@v4
* coverage-contexts (ID 130242902347)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Record per-test coverage contexts
  * Upload coverage contexts database
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test-cost (ID 130242902364)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run cost-attribution suite
  * Post Install dependencies
  * Post Run actions/checkout@v4

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
build-core / build-core: .github#4

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>027zzagAAAAAmH6abfnv9S4xiuquyWWzZQ0gxQUEyMDMwODE0MDI5AEVkZ2U=
build-core / build-core: .github#7

! Failed to restore: Cache service responded with 400
build-core / build-core: .github#25

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
build-core / build-core: .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* master CI Telemetry · 42933587314
Triggered via workflow_dispatch about 1 hour ago

JOBS
✓ build-core / build-core in 11m19s (ID 130238055792)
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
* contention-test (ID 130242902322)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  * Run default-lane contention harness
  * Upload contention failure records
  * Post Install visual dependencies
  * Post Run actions/checkout@v4
* coverage-contexts (ID 130242902347)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Record per-test coverage contexts
  * Upload coverage contexts database
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test-cost (ID 130242902364)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run cost-attribution suite
  * Post Install dependencies
  * Post Run actions/checkout@v4

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
build-core / build-core: .github#4

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>027zzagAAAAAmH6abfnv9S4xiuquyWWzZQ0gxQUEyMDMwODE0MDI5AEVkZ2U=
build-core / build-core: .github#7

! Failed to restore: Cache service responded with 400
build-core / build-core: .github#25

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
build-core / build-core: .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* master CI Telemetry · 42933587314
Triggered via workflow_dispatch about 1 hour ago

JOBS
✓ build-core / build-core in 11m19s (ID 130238055792)
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
* contention-test (ID 130242902322)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  * Run default-lane contention harness
  * Upload contention failure records
  * Post Install visual dependencies
  * Post Run actions/checkout@v4
* coverage-contexts (ID 130242902347)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Record per-test coverage contexts
  * Upload coverage contexts database
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test-cost (ID 130242902364)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run cost-attribution suite
  * Post Install dependencies
  * Post Run actions/checkout@v4

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
build-core / build-core: .github#4

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>027zzagAAAAAmH6abfnv9S4xiuquyWWzZQ0gxQUEyMDMwODE0MDI5AEVkZ2U=
build-core / build-core: .github#7

! Failed to restore: Cache service responded with 400
build-core / build-core: .github#25

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
build-core / build-core: .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* master CI Telemetry · 42933587314
Triggered via workflow_dispatch about 1 hour ago

JOBS
✓ build-core / build-core in 11m19s (ID 130238055792)
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
* contention-test (ID 130242902322)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  * Run default-lane contention harness
  * Upload contention failure records
  * Post Install visual dependencies
  * Post Run actions/checkout@v4
* coverage-contexts (ID 130242902347)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Record per-test coverage contexts
  * Upload coverage contexts database
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test-cost (ID 130242902364)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run cost-attribution suite
  * Post Install dependencies
  * Post Run actions/checkout@v4

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
build-core / build-core: .github#4

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>027zzagAAAAAmH6abfnv9S4xiuquyWWzZQ0gxQUEyMDMwODE0MDI5AEVkZ2U=
build-core / build-core: .github#7

! Failed to restore: Cache service responded with 400
build-core / build-core: .github#25

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
build-core / build-core: .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* master CI Telemetry · 42933587314
Triggered via workflow_dispatch about 1 hour ago

JOBS
✓ build-core / build-core in 11m19s (ID 130238055792)
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
* contention-test (ID 130242902322)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  * Run default-lane contention harness
  * Upload contention failure records
  * Post Install visual dependencies
  * Post Run actions/checkout@v4
* coverage-contexts (ID 130242902347)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Record per-test coverage contexts
  * Upload coverage contexts database
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test-cost (ID 130242902364)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run cost-attribution suite
  * Post Install dependencies
  * Post Run actions/checkout@v4

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
build-core / build-core: .github#4

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>027zzagAAAAAmH6abfnv9S4xiuquyWWzZQ0gxQUEyMDMwODE0MDI5AEVkZ2U=
build-core / build-core: .github#7

! Failed to restore: Cache service responded with 400
build-core / build-core: .github#25

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
build-core / build-core: .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* master CI Telemetry · 42933587314
Triggered via workflow_dispatch about 1 hour ago

JOBS
✓ build-core / build-core in 11m19s (ID 130238055792)
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
* contention-test (ID 130242902322)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  * Run default-lane contention harness
  * Upload contention failure records
  * Post Install visual dependencies
  * Post Run actions/checkout@v4
* coverage-contexts (ID 130242902347)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Record per-test coverage contexts
  * Upload coverage contexts database
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test-cost (ID 130242902364)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run cost-attribution suite
  * Post Install dependencies
  * Post Run actions/checkout@v4

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
build-core / build-core: .github#4

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>027zzagAAAAAmH6abfnv9S4xiuquyWWzZQ0gxQUEyMDMwODE0MDI5AEVkZ2U=
build-core / build-core: .github#7

! Failed to restore: Cache service responded with 400
build-core / build-core: .github#25

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
build-core / build-core: .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* master CI Telemetry · 42933587314
Triggered via workflow_dispatch about 1 hour ago

JOBS
✓ build-core / build-core in 11m19s (ID 130238055792)
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
* contention-test (ID 130242902322)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  * Run default-lane contention harness
  * Upload contention failure records
  * Post Install visual dependencies
  * Post Run actions/checkout@v4
* coverage-contexts (ID 130242902347)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Record per-test coverage contexts
  * Upload coverage contexts database
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test-cost (ID 130242902364)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run cost-attribution suite
  * Post Install dependencies
  * Post Run actions/checkout@v4

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
build-core / build-core: .github#4

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>027zzagAAAAAmH6abfnv9S4xiuquyWWzZQ0gxQUEyMDMwODE0MDI5AEVkZ2U=
build-core / build-core: .github#7

! Failed to restore: Cache service responded with 400
build-core / build-core: .github#25

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
build-core / build-core: .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* master CI Telemetry · 42933587314
Triggered via workflow_dispatch about 1 hour ago

JOBS
✓ build-core / build-core in 11m19s (ID 130238055792)
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
* contention-test (ID 130242902322)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  * Run default-lane contention harness
  * Upload contention failure records
  * Post Install visual dependencies
  * Post Run actions/checkout@v4
* coverage-contexts (ID 130242902347)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Record per-test coverage contexts
  * Upload coverage contexts database
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test-cost (ID 130242902364)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run cost-attribution suite
  * Post Install dependencies
  * Post Run actions/checkout@v4

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
build-core / build-core: .github#4

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>027zzagAAAAAmH6abfnv9S4xiuquyWWzZQ0gxQUEyMDMwODE0MDI5AEVkZ2U=
build-core / build-core: .github#7

! Failed to restore: Cache service responded with 400
build-core / build-core: .github#25

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
build-core / build-core: .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* master CI Telemetry · 42933587314
Triggered via workflow_dispatch about 1 hour ago

JOBS
✓ build-core / build-core in 11m19s (ID 130238055792)
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
* contention-test (ID 130242902322)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  * Run default-lane contention harness
  * Upload contention failure records
  * Post Install visual dependencies
  * Post Run actions/checkout@v4
* coverage-contexts (ID 130242902347)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Record per-test coverage contexts
  * Upload coverage contexts database
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test-cost (ID 130242902364)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run cost-attribution suite
  * Post Install dependencies
  * Post Run actions/checkout@v4

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
build-core / build-core: .github#4

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>027zzagAAAAAmH6abfnv9S4xiuquyWWzZQ0gxQUEyMDMwODE0MDI5AEVkZ2U=
build-core / build-core: .github#7

! Failed to restore: Cache service responded with 400
build-core / build-core: .github#25

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
build-core / build-core: .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* master CI Telemetry · 42933587314
Triggered via workflow_dispatch about 1 hour ago

JOBS
✓ build-core / build-core in 11m19s (ID 130238055792)
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
* contention-test (ID 130242902322)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  * Run default-lane contention harness
  * Upload contention failure records
  * Post Install visual dependencies
  * Post Run actions/checkout@v4
* coverage-contexts (ID 130242902347)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Record per-test coverage contexts
  * Upload coverage contexts database
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test-cost (ID 130242902364)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run cost-attribution suite
  * Post Install dependencies
  * Post Run actions/checkout@v4

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
build-core / build-core: .github#4

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>027zzagAAAAAmH6abfnv9S4xiuquyWWzZQ0gxQUEyMDMwODE0MDI5AEVkZ2U=
build-core / build-core: .github#7

! Failed to restore: Cache service responded with 400
build-core / build-core: .github#25

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
build-core / build-core: .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* master CI Telemetry · 42933587314
Triggered via workflow_dispatch about 1 hour ago

JOBS
✓ build-core / build-core in 11m19s (ID 130238055792)
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
* contention-test (ID 130242902322)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  * Run default-lane contention harness
  * Upload contention failure records
  * Post Install visual dependencies
  * Post Run actions/checkout@v4
* coverage-contexts (ID 130242902347)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Record per-test coverage contexts
  * Upload coverage contexts database
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test-cost (ID 130242902364)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run cost-attribution suite
  * Post Install dependencies
  * Post Run actions/checkout@v4

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
build-core / build-core: .github#4

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>027zzagAAAAAmH6abfnv9S4xiuquyWWzZQ0gxQUEyMDMwODE0MDI5AEVkZ2U=
build-core / build-core: .github#7

! Failed to restore: Cache service responded with 400
build-core / build-core: .github#25

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
build-core / build-core: .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* master CI Telemetry · 42933587314
Triggered via workflow_dispatch about 1 hour ago

JOBS
✓ build-core / build-core in 11m19s (ID 130238055792)
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
* contention-test (ID 130242902322)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  * Run default-lane contention harness
  * Upload contention failure records
  * Post Install visual dependencies
  * Post Run actions/checkout@v4
* coverage-contexts (ID 130242902347)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Record per-test coverage contexts
  * Upload coverage contexts database
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test-cost (ID 130242902364)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run cost-attribution suite
  * Post Install dependencies
  * Post Run actions/checkout@v4

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
build-core / build-core: .github#4

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>027zzagAAAAAmH6abfnv9S4xiuquyWWzZQ0gxQUEyMDMwODE0MDI5AEVkZ2U=
build-core / build-core: .github#7

! Failed to restore: Cache service responded with 400
build-core / build-core: .github#25

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
build-core / build-core: .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* master CI Telemetry · 42933587314
Triggered via workflow_dispatch about 1 hour ago

JOBS
✓ build-core / build-core in 11m19s (ID 130238055792)
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
* contention-test (ID 130242902322)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  * Run default-lane contention harness
  * Upload contention failure records
  * Post Install visual dependencies
  * Post Run actions/checkout@v4
* coverage-contexts (ID 130242902347)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Record per-test coverage contexts
  * Upload coverage contexts database
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test-cost (ID 130242902364)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run cost-attribution suite
  * Post Install dependencies
  * Post Run actions/checkout@v4

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
build-core / build-core: .github#4

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>027zzagAAAAAmH6abfnv9S4xiuquyWWzZQ0gxQUEyMDMwODE0MDI5AEVkZ2U=
build-core / build-core: .github#7

! Failed to restore: Cache service responded with 400
build-core / build-core: .github#25

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
build-core / build-core: .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* master CI Telemetry · 42933587314
Triggered via workflow_dispatch about 1 hour ago

JOBS
✓ build-core / build-core in 11m19s (ID 130238055792)
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
* contention-test (ID 130242902322)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  * Run default-lane contention harness
  * Upload contention failure records
  * Post Install visual dependencies
  * Post Run actions/checkout@v4
* coverage-contexts (ID 130242902347)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Record per-test coverage contexts
  * Upload coverage contexts database
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test-cost (ID 130242902364)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run cost-attribution suite
  * Post Install dependencies
  * Post Run actions/checkout@v4

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
build-core / build-core: .github#4

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>027zzagAAAAAmH6abfnv9S4xiuquyWWzZQ0gxQUEyMDMwODE0MDI5AEVkZ2U=
build-core / build-core: .github#7

! Failed to restore: Cache service responded with 400
build-core / build-core: .github#25

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
build-core / build-core: .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* master CI Telemetry · 42933587314
Triggered via workflow_dispatch about 1 hour ago

JOBS
✓ build-core / build-core in 11m19s (ID 130238055792)
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
* contention-test (ID 130242902322)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  * Run default-lane contention harness
  * Upload contention failure records
  * Post Install visual dependencies
  * Post Run actions/checkout@v4
* coverage-contexts (ID 130242902347)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Record per-test coverage contexts
  * Upload coverage contexts database
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test-cost (ID 130242902364)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run cost-attribution suite
  * Post Install dependencies
  * Post Run actions/checkout@v4

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
build-core / build-core: .github#4

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>027zzagAAAAAmH6abfnv9S4xiuquyWWzZQ0gxQUEyMDMwODE0MDI5AEVkZ2U=
build-core / build-core: .github#7

! Failed to restore: Cache service responded with 400
build-core / build-core: .github#25

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
build-core / build-core: .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* master CI Telemetry · 42933587314
Triggered via workflow_dispatch about 1 hour ago

JOBS
✓ build-core / build-core in 11m19s (ID 130238055792)
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
* contention-test (ID 130242902322)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  * Run default-lane contention harness
  * Upload contention failure records
  * Post Install visual dependencies
  * Post Run actions/checkout@v4
✓ coverage-contexts in 1h28m36s (ID 130242902347)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Record per-test coverage contexts
  ✓ Upload coverage contexts database
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* test-cost (ID 130242902364)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run cost-attribution suite
  * Post Install dependencies
  * Post Run actions/checkout@v4

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
build-core / build-core: .github#4

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>027zzagAAAAAmH6abfnv9S4xiuquyWWzZQ0gxQUEyMDMwODE0MDI5AEVkZ2U=
build-core / build-core: .github#7

! Failed to restore: Cache service responded with 400
build-core / build-core: .github#25

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
build-core / build-core: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
coverage-contexts: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0odHzagAAAADbfusL0Z36RYEjeSgw2QHwU1RCRURHRTA2MTIARWRnZQ==
coverage-contexts: .github#9

! No files were found with the provided path: .coverage. No artifacts will be uploaded.
coverage-contexts: .github#16

! Failed to restore: Cache service responded with 400
coverage-contexts: .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
coverage-contexts: .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* master CI Telemetry · 42933587314
Triggered via workflow_dispatch about 1 hour ago

JOBS
✓ build-core / build-core in 11m19s (ID 130238055792)
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
X contention-test in 1h30m17s (ID 130242902322)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  X Run default-lane contention harness
  ✓ Upload contention failure records
  ✓ Post Install visual dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ coverage-contexts in 1h28m36s (ID 130242902347)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Record per-test coverage contexts
  ✓ Upload coverage contexts database
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* test-cost (ID 130242902364)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run cost-attribution suite
  * Post Install dependencies
  * Post Run actions/checkout@v4

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
build-core / build-core: .github#4

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>027zzagAAAAAmH6abfnv9S4xiuquyWWzZQ0gxQUEyMDMwODE0MDI5AEVkZ2U=
build-core / build-core: .github#7

! Failed to restore: Cache service responded with 400
build-core / build-core: .github#25

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
build-core / build-core: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
coverage-contexts: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0odHzagAAAADbfusL0Z36RYEjeSgw2QHwU1RCRURHRTA2MTIARWRnZQ==
coverage-contexts: .github#9

! No files were found with the provided path: .coverage. No artifacts will be uploaded.
coverage-contexts: .github#16

! Failed to restore: Cache service responded with 400
coverage-contexts: .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
coverage-contexts: .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* master CI Telemetry · 42933587314
Triggered via workflow_dispatch about 1 hour ago

JOBS
✓ build-core / build-core in 11m19s (ID 130238055792)
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
X contention-test in 1h30m17s (ID 130242902322)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  X Run default-lane contention harness
  ✓ Upload contention failure records
  ✓ Post Install visual dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ coverage-contexts in 1h28m36s (ID 130242902347)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Record per-test coverage contexts
  ✓ Upload coverage contexts database
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* test-cost (ID 130242902364)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run cost-attribution suite
  * Post Install dependencies
  * Post Run actions/checkout@v4

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
build-core / build-core: .github#4

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>027zzagAAAAAmH6abfnv9S4xiuquyWWzZQ0gxQUEyMDMwODE0MDI5AEVkZ2U=
build-core / build-core: .github#7

! Failed to restore: Cache service responded with 400
build-core / build-core: .github#25

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
build-core / build-core: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
coverage-contexts: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0odHzagAAAADbfusL0Z36RYEjeSgw2QHwU1RCRURHRTA2MTIARWRnZQ==
coverage-contexts: .github#9

! No files were found with the provided path: .coverage. No artifacts will be uploaded.
coverage-contexts: .github#16

! Failed to restore: Cache service responded with 400
coverage-contexts: .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
coverage-contexts: .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* master CI Telemetry · 42933587314
Triggered via workflow_dispatch about 1 hour ago

JOBS
✓ build-core / build-core in 11m19s (ID 130238055792)
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
X contention-test in 1h30m17s (ID 130242902322)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  X Run default-lane contention harness
  ✓ Upload contention failure records
  ✓ Post Install visual dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ coverage-contexts in 1h28m36s (ID 130242902347)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Record per-test coverage contexts
  ✓ Upload coverage contexts database
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* test-cost (ID 130242902364)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run cost-attribution suite
  * Post Install dependencies
  * Post Run actions/checkout@v4

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
build-core / build-core: .github#4

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>027zzagAAAAAmH6abfnv9S4xiuquyWWzZQ0gxQUEyMDMwODE0MDI5AEVkZ2U=
build-core / build-core: .github#7

! Failed to restore: Cache service responded with 400
build-core / build-core: .github#25

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
build-core / build-core: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
coverage-contexts: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0odHzagAAAADbfusL0Z36RYEjeSgw2QHwU1RCRURHRTA2MTIARWRnZQ==
coverage-contexts: .github#9

! No files were found with the provided path: .coverage. No artifacts will be uploaded.
coverage-contexts: .github#16

! Failed to restore: Cache service responded with 400
coverage-contexts: .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
coverage-contexts: .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* master CI Telemetry · 42933587314
Triggered via workflow_dispatch about 1 hour ago

JOBS
✓ build-core / build-core in 11m19s (ID 130238055792)
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
X contention-test in 1h30m17s (ID 130242902322)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  X Run default-lane contention harness
  ✓ Upload contention failure records
  ✓ Post Install visual dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ coverage-contexts in 1h28m36s (ID 130242902347)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Record per-test coverage contexts
  ✓ Upload coverage contexts database
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* test-cost (ID 130242902364)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run cost-attribution suite
  * Post Install dependencies
  * Post Run actions/checkout@v4

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
build-core / build-core: .github#4

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>027zzagAAAAAmH6abfnv9S4xiuquyWWzZQ0gxQUEyMDMwODE0MDI5AEVkZ2U=
build-core / build-core: .github#7

! Failed to restore: Cache service responded with 400
build-core / build-core: .github#25

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
build-core / build-core: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
coverage-contexts: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0odHzagAAAADbfusL0Z36RYEjeSgw2QHwU1RCRURHRTA2MTIARWRnZQ==
coverage-contexts: .github#9

! No files were found with the provided path: .coverage. No artifacts will be uploaded.
coverage-contexts: .github#16

! Failed to restore: Cache service responded with 400
coverage-contexts: .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
coverage-contexts: .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* master CI Telemetry · 42933587314
Triggered via workflow_dispatch about 1 hour ago

JOBS
✓ build-core / build-core in 11m19s (ID 130238055792)
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
X contention-test in 1h30m17s (ID 130242902322)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  X Run default-lane contention harness
  ✓ Upload contention failure records
  ✓ Post Install visual dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ coverage-contexts in 1h28m36s (ID 130242902347)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Record per-test coverage contexts
  ✓ Upload coverage contexts database
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* test-cost (ID 130242902364)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run cost-attribution suite
  * Post Install dependencies
  * Post Run actions/checkout@v4

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
build-core / build-core: .github#4

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>027zzagAAAAAmH6abfnv9S4xiuquyWWzZQ0gxQUEyMDMwODE0MDI5AEVkZ2U=
build-core / build-core: .github#7

! Failed to restore: Cache service responded with 400
build-core / build-core: .github#25

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
build-core / build-core: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
coverage-contexts: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0odHzagAAAADbfusL0Z36RYEjeSgw2QHwU1RCRURHRTA2MTIARWRnZQ==
coverage-contexts: .github#9

! No files were found with the provided path: .coverage. No artifacts will be uploaded.
coverage-contexts: .github#16

! Failed to restore: Cache service responded with 400
coverage-contexts: .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
coverage-contexts: .github#1

X master CI Telemetry · 42933587314
Triggered via workflow_dispatch about 1 hour ago

JOBS
✓ build-core / build-core in 11m19s (ID 130238055792)
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
X contention-test in 1h30m17s (ID 130242902322)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  X Run default-lane contention harness
  ✓ Upload contention failure records
  ✓ Post Install visual dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ coverage-contexts in 1h28m36s (ID 130242902347)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Record per-test coverage contexts
  ✓ Upload coverage contexts database
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
X test-cost in 1h41m7s (ID 130242902364)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  X Run cost-attribution suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
build-core / build-core: .github#4

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>027zzagAAAAAmH6abfnv9S4xiuquyWWzZQ0gxQUEyMDMwODE0MDI5AEVkZ2U=
build-core / build-core: .github#7

! Failed to restore: Cache service responded with 400
build-core / build-core: .github#25

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
build-core / build-core: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
coverage-contexts: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0odHzagAAAADbfusL0Z36RYEjeSgw2QHwU1RCRURHRTA2MTIARWRnZQ==
coverage-contexts: .github#9

! No files were found with the provided path: .coverage. No artifacts will be uploaded.
coverage-contexts: .github#16

! Failed to restore: Cache service responded with 400
coverage-contexts: .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
coverage-contexts: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
test-cost: .github#2

X Process completed with exit code 1.
test-cost: .github#1284

! Failed to restore: Cache service responded with 400
test-cost: .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
test-cost: .github#1


