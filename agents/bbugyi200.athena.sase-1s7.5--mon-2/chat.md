# Chat History - ace-run (sase-1s7.5--mon-2)

- **TIMESTAMP:** 2026-11-11 02:21:57 EST
- **MODEL:** grok/grok-4.6
- **AGENT:** sase-1s7.5--mon-2

## Prompt

sase monitor start --command 'sh /tmp/sase-1s7.5-watch.sh' --reason 'Wait for drain-fix stitch, then Telemetry attempt 4, Full CI, Master Gate, and observe-only steward for sase-1s7.5'

## Response

sase: running unwrapped (no profile (monitor.tool_wrap is verify))
origin/master=b0f947b91df1ea054d6f52818af92895e5e4880e
tip=b0f947b91df1ea054d6f52818af92895e5e4880e
master_gate=42966095347
https://github.com/sase-org/sase/actions/runs/42966178009
dispatched telemetry.yml after stitch
https://github.com/sase-org/sase/actions/runs/42966182715
dispatched full.yml after stitch
https://github.com/sase-org/sase/actions/runs/42966187669
dispatched observe-only release-steward.yml
telemetry=42966178009
full_ci=42966182715
Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* master Master Gate · 42966095347
Triggered via push less than a minute ago

JOBS
✓ core-wheel in 26s (ID 130343580025)
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
* docs (ID 130343580271)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Install just
  ✓ Set up Python
  ✓ Build and validate docs
  * Post Run astral-sh/setup-uv@v4
  * Post Run actions/checkout@v4
* lint (ID 130343740988)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Check pinned core bindings
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
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (5) (ID 130343741078)
  ✓ Set up job
  * Run actions/checkout@v4
  * Install dependencies
  * Run sharded fast suite
  * Post Run actions/checkout@v4
* test (3) (ID 130343741119)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (1) (ID 130343741139)
  ✓ Set up job
  * Run actions/checkout@v4
  * Install dependencies
  * Run sharded fast suite
  * Post Run actions/checkout@v4
* test (6) (ID 130343741140)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  * Install dependencies
  * Run sharded fast suite
  * Post Run actions/checkout@v4
* test (2) (ID 130343741143)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  * Install dependencies
  * Run sharded fast suite
  * Post Run actions/checkout@v4
* test (8) (ID 130343741163)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  * Install dependencies
  * Run sharded fast suite
  * Post Run actions/checkout@v4
* test (4) (ID 130343741176)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (7) (ID 130343741268)
  ✓ Set up job
  * Run actions/checkout@v4
  * Install dependencies
  * Run sharded fast suite
  * Post Run actions/checkout@v4

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache/restore@v4, actions/checkout@v4, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
core-wheel: .github#2

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
core-wheel: .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* master Master Gate · 42966095347
Triggered via push about 2 minutes ago

JOBS
✓ core-wheel in 26s (ID 130343580025)
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
✓ docs in 48s (ID 130343580271)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Install just
  ✓ Set up Python
  ✓ Build and validate docs
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* lint (ID 130343740988)
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
* test (5) (ID 130343741078)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (3) (ID 130343741119)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (1) (ID 130343741139)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (6) (ID 130343741140)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (2) (ID 130343741143)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (8) (ID 130343741163)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (4) (ID 130343741176)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (7) (ID 130343741268)
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

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
docs: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0b/3zagAAAADcV9cHsLYFTrFz6OYZcJy0UEhYMzFFREdFMDUxMwBFZGdl
docs: .github#7

! Failed to restore: Cache service responded with 400
docs: .github#26

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
docs: .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* master Master Gate · 42966095347
Triggered via push about 4 minutes ago

JOBS
✓ core-wheel in 26s (ID 130343580025)
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
✓ docs in 48s (ID 130343580271)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Install just
  ✓ Set up Python
  ✓ Build and validate docs
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* lint (ID 130343740988)
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
* test (5) (ID 130343741078)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (3) (ID 130343741119)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (1) (ID 130343741139)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (6) (ID 130343741140)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (2) (ID 130343741143)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (8) (ID 130343741163)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (4) (ID 130343741176)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (7) (ID 130343741268)
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

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
docs: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0b/3zagAAAADcV9cHsLYFTrFz6OYZcJy0UEhYMzFFREdFMDUxMwBFZGdl
docs: .github#7

! Failed to restore: Cache service responded with 400
docs: .github#26

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
docs: .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* master Master Gate · 42966095347
Triggered via push about 7 minutes ago

JOBS
✓ core-wheel in 26s (ID 130343580025)
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
✓ docs in 48s (ID 130343580271)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Install just
  ✓ Set up Python
  ✓ Build and validate docs
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ lint in 4m56s (ID 130343740988)
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
* test (5) (ID 130343741078)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (3) (ID 130343741119)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (1) (ID 130343741139)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (6) (ID 130343741140)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (2) (ID 130343741143)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (8) (ID 130343741163)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (4) (ID 130343741176)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (7) (ID 130343741268)
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

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
docs: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0b/3zagAAAADcV9cHsLYFTrFz6OYZcJy0UEhYMzFFREdFMDUxMwBFZGdl
docs: .github#7

! Failed to restore: Cache service responded with 400
docs: .github#26

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
docs: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache@v4, actions/checkout@v4, actions/download-artifact@v4, actions/setup-go@v5, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
lint: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0gv7zagAAAADMkzNRUjVOSrUhI6JSOUS+UEhMMzBFREdFMDExNgBFZGdl
lint: .github#9

! Failed to restore: Cache service responded with 400
lint: .github#54

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
lint: .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* master Master Gate · 42966095347
Triggered via push about 9 minutes ago

JOBS
✓ core-wheel in 26s (ID 130343580025)
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
✓ docs in 48s (ID 130343580271)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Install just
  ✓ Set up Python
  ✓ Build and validate docs
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ lint in 4m56s (ID 130343740988)
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
* test (5) (ID 130343741078)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (3) (ID 130343741119)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (1) (ID 130343741139)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (6) (ID 130343741140)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (2) (ID 130343741143)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
✓ test (8) in 8m10s (ID 130343741163)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* test (4) (ID 130343741176)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (7) (ID 130343741268)
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

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
docs: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0b/3zagAAAADcV9cHsLYFTrFz6OYZcJy0UEhYMzFFREdFMDUxMwBFZGdl
docs: .github#7

! Failed to restore: Cache service responded with 400
docs: .github#26

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
docs: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache@v4, actions/checkout@v4, actions/download-artifact@v4, actions/setup-go@v5, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
lint: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0gv7zagAAAADMkzNRUjVOSrUhI6JSOUS+UEhMMzBFREdFMDExNgBFZGdl
lint: .github#9

! Failed to restore: Cache service responded with 400
lint: .github#54

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
lint: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
test (8): .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0Rv/zagAAAAACEu8+K/RrRpi5d5mUPMYFUEhYMzFFREdFMDUwNwBFZGdl
test (8): .github#9

! Failed to restore: Cache service responded with 400
test (8): .github#54

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
test (8): .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* master Master Gate · 42966095347
Triggered via push about 11 minutes ago

JOBS
✓ core-wheel in 26s (ID 130343580025)
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
✓ docs in 48s (ID 130343580271)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Install just
  ✓ Set up Python
  ✓ Build and validate docs
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ lint in 4m56s (ID 130343740988)
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
✓ test (5) in 9m46s (ID 130343741078)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* test (3) (ID 130343741119)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (1) (ID 130343741139)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (6) (ID 130343741140)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
✓ test (2) in 9m34s (ID 130343741143)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ test (8) in 8m10s (ID 130343741163)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* test (4) (ID 130343741176)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (7) (ID 130343741268)
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

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
docs: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0b/3zagAAAADcV9cHsLYFTrFz6OYZcJy0UEhYMzFFREdFMDUxMwBFZGdl
docs: .github#7

! Failed to restore: Cache service responded with 400
docs: .github#26

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
docs: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache@v4, actions/checkout@v4, actions/download-artifact@v4, actions/setup-go@v5, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
lint: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0gv7zagAAAADMkzNRUjVOSrUhI6JSOUS+UEhMMzBFREdFMDExNgBFZGdl
lint: .github#9

! Failed to restore: Cache service responded with 400
lint: .github#54

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
lint: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
test (8): .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0Rv/zagAAAAACEu8+K/RrRpi5d5mUPMYFUEhYMzFFREdFMDUwNwBFZGdl
test (8): .github#9

! Failed to restore: Cache service responded with 400
test (8): .github#54

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
test (8): .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* master Master Gate · 42966095347
Triggered via push about 13 minutes ago

JOBS
✓ core-wheel in 26s (ID 130343580025)
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
✓ docs in 48s (ID 130343580271)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Install just
  ✓ Set up Python
  ✓ Build and validate docs
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ lint in 4m56s (ID 130343740988)
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
✓ test (5) in 9m46s (ID 130343741078)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ test (3) in 12m1s (ID 130343741119)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ test (1) in 12m29s (ID 130343741139)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ test (6) in 12m3s (ID 130343741140)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ test (2) in 9m34s (ID 130343741143)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ test (8) in 8m10s (ID 130343741163)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ test (4) in 11m27s (ID 130343741176)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* test (7) (ID 130343741268)
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

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
docs: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0b/3zagAAAADcV9cHsLYFTrFz6OYZcJy0UEhYMzFFREdFMDUxMwBFZGdl
docs: .github#7

! Failed to restore: Cache service responded with 400
docs: .github#26

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
docs: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache@v4, actions/checkout@v4, actions/download-artifact@v4, actions/setup-go@v5, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
lint: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0gv7zagAAAADMkzNRUjVOSrUhI6JSOUS+UEhMMzBFREdFMDExNgBFZGdl
lint: .github#9

! Failed to restore: Cache service responded with 400
lint: .github#54

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
lint: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
test (8): .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0Rv/zagAAAAACEu8+K/RrRpi5d5mUPMYFUEhYMzFFREdFMDUwNwBFZGdl
test (8): .github#9

! Failed to restore: Cache service responded with 400
test (8): .github#54

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
test (8): .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
test (4): .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0CwD0agAAAADE3wk+Pbm8Q5dOuwhS1g9EUEhMMzBFREdFMDQxNwBFZGdl
test (4): .github#9

! Failed to restore: Cache service responded with 400
test (4): .github#54

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
test (4): .github#1

✓ master Master Gate · 42966095347
Triggered via push about 15 minutes ago

JOBS
✓ core-wheel in 26s (ID 130343580025)
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
✓ docs in 48s (ID 130343580271)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Install just
  ✓ Set up Python
  ✓ Build and validate docs
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ lint in 4m56s (ID 130343740988)
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
✓ test (5) in 9m46s (ID 130343741078)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ test (3) in 12m1s (ID 130343741119)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ test (1) in 12m29s (ID 130343741139)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ test (6) in 12m3s (ID 130343741140)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ test (2) in 9m34s (ID 130343741143)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ test (8) in 8m10s (ID 130343741163)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ test (4) in 11m27s (ID 130343741176)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ test (7) in 12m53s (ID 130343741268)
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

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
docs: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0b/3zagAAAADcV9cHsLYFTrFz6OYZcJy0UEhYMzFFREdFMDUxMwBFZGdl
docs: .github#7

! Failed to restore: Cache service responded with 400
docs: .github#26

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
docs: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache@v4, actions/checkout@v4, actions/download-artifact@v4, actions/setup-go@v5, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
lint: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0gv7zagAAAADMkzNRUjVOSrUhI6JSOUS+UEhMMzBFREdFMDExNgBFZGdl
lint: .github#9

! Failed to restore: Cache service responded with 400
lint: .github#54

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
lint: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
test (8): .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0Rv/zagAAAAACEu8+K/RrRpi5d5mUPMYFUEhYMzFFREdFMDUwNwBFZGdl
test (8): .github#9

! Failed to restore: Cache service responded with 400
test (8): .github#54

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
test (8): .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
test (4): .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0CwD0agAAAADE3wk+Pbm8Q5dOuwhS1g9EUEhMMzBFREdFMDQxNwBFZGdl
test (4): .github#9

! Failed to restore: Cache service responded with 400
test (4): .github#54

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
test (4): .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
test (7): .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0YAD0agAAAABp+U5vtvsqSLHyWKan5AdnTEFYMzExMDAwMTA5MDIzAEVkZ2U=
test (7): .github#9

! Failed to restore: Cache service responded with 400
test (7): .github#54

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
test (7): .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* master Full CI · 42966182715
Triggered via workflow_dispatch about 14 minutes ago

JOBS
✓ full / prepare in 20s (ID 130343865852)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Validate qualification inputs
  - Download the sealed candidate manifest
  - Bind published identity from the sealed manifest
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
- full / release-core-floor-smoke (ID 130343867306)
- full / docs-build (ID 130343867307)
* full / build-core / build-core (ID 130344002788)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Resolve core mode
  ✓ Resolve pinned Rust core revision
  ✓ Check out Rust core
  - Check out published Rust core tag
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up Rust
  ✓ Cache Rust build
  * Build abi3 Rust core wheel
  * Download the sealed candidate manifest
  * Fetch and verify the published core wheel
  * Build macro LSP
  * Record wheel provenance
  * Record published tag provenance
  * Upload Rust core artifacts
  * Post Cache Rust build
  * Post Run astral-sh/setup-uv@v4
  * Post Check out Rust core
  * Post Run actions/checkout@v4

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / prepare: .github#6

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / prepare: .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* master Full CI · 42966182715
Triggered via workflow_dispatch about 16 minutes ago

JOBS
✓ full / prepare in 20s (ID 130343865852)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Validate qualification inputs
  - Download the sealed candidate manifest
  - Bind published identity from the sealed manifest
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
- full / release-core-floor-smoke (ID 130343867306)
- full / docs-build (ID 130343867307)
✓ full / build-core / build-core in 15m34s (ID 130344002788)
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
* full / tutorial-tests (ID 130349372470)
  ✓ Set up job
  * Run actions/checkout@v4
  * Install dependencies
  * Run tutorial tests
  * Post Run actions/checkout@v4
* full / lint (ID 130349372477)
  ✓ Set up job
  * Run actions/checkout@v4
  * Run astral-sh/setup-uv@v4
  * Set up preflight Python
  * Download Rust core artifacts for bindings preflight
  * Preflight core bindings
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
  * Record installed core version
  * Write qualification evidence
  * Upload qualification evidence
  * Post Run actions/checkout@v4
* full / ace-page-group-isolation (ID 130349372511)
  ✓ Set up job
  * Run actions/checkout@v4
  * Install visual dependencies
  * Run ACE shared-page isolation lane
  * Post Run actions/checkout@v4
* full / test (3.14) (ID 130349372581)
  ✓ Set up job
  * Run actions/checkout@v4
  * Install dependencies
  * Run tests (coverage leg)
  * Run tests
  * Build shard timings table
  * Upload shard timings
  * Upload coverage
  * Record installed core version
  * Write qualification evidence
  * Upload qualification evidence
  * Post Run actions/checkout@v4
* full / test (3.12) (ID 130349372611)
  ✓ Set up job
  * Run actions/checkout@v4
  * Install dependencies
  * Run tests (coverage leg)
  * Run tests
  * Build shard timings table
  * Upload shard timings
  * Upload coverage
  * Record installed core version
  * Write qualification evidence
  * Upload qualification evidence
  * Post Run actions/checkout@v4
* full / perf-floors (ID 130349372613)
  ✓ Set up job
  * Run actions/checkout@v4
  * Install dependencies
  * Health check (Rust extension loadable)
  * Run slow tests
  * Run Phase 7E regression floor
  * Upload Phase 7E floor-check report
  * Run launch regression floor
  * Upload launch floor-check report
  * Run view-hints regression floor
  * Upload view-hints floor-check report
  * Run agents disk-load operation-count floor
  * Upload agents disk-load floor-check report
  * Run plugins catalog-scale regression floor
  * Upload plugins catalog-scale floor-check report
  * Run bead performance smoke
  * Upload bead performance smoke
  * Run bead scaled-corpus benchmark (record-only 4x)
  * Upload bead scaled-corpus benchmark
  * Run bead history-independence gate (1x+4x)
  * Upload bead history-independence gate report
  * Post Run actions/checkout@v4
* full / visual-test (ID 130349372627)
  ✓ Set up job
  * Run actions/checkout@v4
  * Install visual dependencies
  * Check TUI screenshots
  * Locate visual report
  * Build visual report
  * Upload visual report
  * Publish visual report
  * Publish unstable recapture summary
  * Upload first-attempt diffs
  * Upload visual artifacts
  * Post Run actions/checkout@v4
* full / test (3.13) (ID 130349372634)
  ✓ Set up job
  * Run actions/checkout@v4
  * Install dependencies
  * Run tests (coverage leg)
  * Run tests
  * Build shard timings table
  * Upload shard timings
  * Upload coverage
  * Record installed core version
  * Write qualification evidence
  * Upload qualification evidence
  * Post Run actions/checkout@v4

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / prepare: .github#6

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / prepare: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / build-core / build-core: .github#4

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0LQH0agAAAACAAn0JAmZMSbGa7VFO+5j/TEFYRURHRTE2MTMARWRnZQ==
full / build-core / build-core: .github#7

! Failed to restore: Cache service responded with 400
full / build-core / build-core: .github#25

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / build-core / build-core: .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* master Full CI · 42966182715
Triggered via workflow_dispatch about 18 minutes ago

JOBS
✓ full / prepare in 20s (ID 130343865852)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Validate qualification inputs
  - Download the sealed candidate manifest
  - Bind published identity from the sealed manifest
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
- full / release-core-floor-smoke (ID 130343867306)
- full / docs-build (ID 130343867307)
✓ full / build-core / build-core in 15m34s (ID 130344002788)
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
✓ full / tutorial-tests in 58s (ID 130349372470)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run tutorial tests
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* full / lint (ID 130349372477)
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
  * Lint
  * SASE validation
  * Validate committed plans
  * Build and verify package
  * Record installed core version
  * Write qualification evidence
  * Upload qualification evidence
  * Post Cache Prettier dependencies
  * Post Cache Go binaries
  * Post Run actions/setup-go@v5
  * Post Install dependencies
  * Post Run actions/checkout@v4
✓ full / ace-page-group-isolation in 1m26s (ID 130349372511)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  ✓ Run ACE shared-page isolation lane
  ✓ Post Install visual dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* full / test (3.14) (ID 130349372581)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  - Run tests (coverage leg)
  * Run tests
  * Build shard timings table
  * Upload shard timings
  * Upload coverage
  * Record installed core version
  * Write qualification evidence
  * Upload qualification evidence
  * Post Install dependencies
  * Post Run actions/checkout@v4
* full / test (3.12) (ID 130349372611)
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
* full / perf-floors (ID 130349372613)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Health check (Rust extension loadable)
  * Run slow tests
  * Run Phase 7E regression floor
  * Upload Phase 7E floor-check report
  * Run launch regression floor
  * Upload launch floor-check report
  * Run view-hints regression floor
  * Upload view-hints floor-check report
  * Run agents disk-load operation-count floor
  * Upload agents disk-load floor-check report
  * Run plugins catalog-scale regression floor
  * Upload plugins catalog-scale floor-check report
  * Run bead performance smoke
  * Upload bead performance smoke
  * Run bead scaled-corpus benchmark (record-only 4x)
  * Upload bead scaled-corpus benchmark
  * Run bead history-independence gate (1x+4x)
  * Upload bead history-independence gate report
  * Post Install dependencies
  * Post Run actions/checkout@v4
* full / visual-test (ID 130349372627)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  * Check TUI screenshots
  * Locate visual report
  * Build visual report
  * Upload visual report
  * Publish visual report
  * Publish unstable recapture summary
  * Upload first-attempt diffs
  * Upload visual artifacts
  * Post Install visual dependencies
  * Post Run actions/checkout@v4
* full / test (3.13) (ID 130349372634)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  - Run tests (coverage leg)
  * Run tests
  * Build shard timings table
  * Upload shard timings
  * Upload coverage
  * Record installed core version
  * Write qualification evidence
  * Upload qualification evidence
  * Post Install dependencies
  * Post Run actions/checkout@v4

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / prepare: .github#6

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / prepare: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / build-core / build-core: .github#4

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0LQH0agAAAACAAn0JAmZMSbGa7VFO+5j/TEFYRURHRTE2MTMARWRnZQ==
full / build-core / build-core: .github#7

! Failed to restore: Cache service responded with 400
full / build-core / build-core: .github#25

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / build-core / build-core: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / tutorial-tests: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0awH0agAAAABsNah2y6NwRrbhGzFSpF1PU0xDMzFFREdFMDEyMgBFZGdl
full / tutorial-tests: .github#9

! Failed to restore: Cache service responded with 400
full / tutorial-tests: .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / tutorial-tests: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / ace-page-group-isolation: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0hgH0agAAAAAZzH9Fqs5+S4bXRr4p6axUUEhMMzBFREdFMDEyMgBFZGdl
full / ace-page-group-isolation: .github#9

! Failed to restore: Cache service responded with 400
full / ace-page-group-isolation: .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / ace-page-group-isolation: .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* master Full CI · 42966182715
Triggered via workflow_dispatch about 20 minutes ago

JOBS
✓ full / prepare in 20s (ID 130343865852)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Validate qualification inputs
  - Download the sealed candidate manifest
  - Bind published identity from the sealed manifest
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
- full / release-core-floor-smoke (ID 130343867306)
- full / docs-build (ID 130343867307)
✓ full / build-core / build-core in 15m34s (ID 130344002788)
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
✓ full / tutorial-tests in 58s (ID 130349372470)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run tutorial tests
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* full / lint (ID 130349372477)
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
  * Lint
  * SASE validation
  * Validate committed plans
  * Build and verify package
  * Record installed core version
  * Write qualification evidence
  * Upload qualification evidence
  * Post Cache Prettier dependencies
  * Post Cache Go binaries
  * Post Run actions/setup-go@v5
  * Post Install dependencies
  * Post Run actions/checkout@v4
✓ full / ace-page-group-isolation in 1m26s (ID 130349372511)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  ✓ Run ACE shared-page isolation lane
  ✓ Post Install visual dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* full / test (3.14) (ID 130349372581)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  - Run tests (coverage leg)
  * Run tests
  * Build shard timings table
  * Upload shard timings
  * Upload coverage
  * Record installed core version
  * Write qualification evidence
  * Upload qualification evidence
  * Post Install dependencies
  * Post Run actions/checkout@v4
* full / test (3.12) (ID 130349372611)
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
* full / perf-floors (ID 130349372613)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Health check (Rust extension loadable)
  * Run slow tests
  * Run Phase 7E regression floor
  * Upload Phase 7E floor-check report
  * Run launch regression floor
  * Upload launch floor-check report
  * Run view-hints regression floor
  * Upload view-hints floor-check report
  * Run agents disk-load operation-count floor
  * Upload agents disk-load floor-check report
  * Run plugins catalog-scale regression floor
  * Upload plugins catalog-scale floor-check report
  * Run bead performance smoke
  * Upload bead performance smoke
  * Run bead scaled-corpus benchmark (record-only 4x)
  * Upload bead scaled-corpus benchmark
  * Run bead history-independence gate (1x+4x)
  * Upload bead history-independence gate report
  * Post Install dependencies
  * Post Run actions/checkout@v4
* full / visual-test (ID 130349372627)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  * Check TUI screenshots
  * Locate visual report
  * Build visual report
  * Upload visual report
  * Publish visual report
  * Publish unstable recapture summary
  * Upload first-attempt diffs
  * Upload visual artifacts
  * Post Install visual dependencies
  * Post Run actions/checkout@v4
* full / test (3.13) (ID 130349372634)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  - Run tests (coverage leg)
  * Run tests
  * Build shard timings table
  * Upload shard timings
  * Upload coverage
  * Record installed core version
  * Write qualification evidence
  * Upload qualification evidence
  * Post Install dependencies
  * Post Run actions/checkout@v4

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / prepare: .github#6

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / prepare: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / build-core / build-core: .github#4

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0LQH0agAAAACAAn0JAmZMSbGa7VFO+5j/TEFYRURHRTE2MTMARWRnZQ==
full / build-core / build-core: .github#7

! Failed to restore: Cache service responded with 400
full / build-core / build-core: .github#25

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / build-core / build-core: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / tutorial-tests: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0awH0agAAAABsNah2y6NwRrbhGzFSpF1PU0xDMzFFREdFMDEyMgBFZGdl
full / tutorial-tests: .github#9

! Failed to restore: Cache service responded with 400
full / tutorial-tests: .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / tutorial-tests: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / ace-page-group-isolation: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0hgH0agAAAAAZzH9Fqs5+S4bXRr4p6axUUEhMMzBFREdFMDEyMgBFZGdl
full / ace-page-group-isolation: .github#9

! Failed to restore: Cache service responded with 400
full / ace-page-group-isolation: .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / ace-page-group-isolation: .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* master Full CI · 42966182715
Triggered via workflow_dispatch about 22 minutes ago

JOBS
✓ full / prepare in 20s (ID 130343865852)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Validate qualification inputs
  - Download the sealed candidate manifest
  - Bind published identity from the sealed manifest
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
- full / release-core-floor-smoke (ID 130343867306)
- full / docs-build (ID 130343867307)
✓ full / build-core / build-core in 15m34s (ID 130344002788)
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
✓ full / tutorial-tests in 58s (ID 130349372470)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run tutorial tests
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ full / lint in 5m39s (ID 130349372477)
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
✓ full / ace-page-group-isolation in 1m26s (ID 130349372511)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  ✓ Run ACE shared-page isolation lane
  ✓ Post Install visual dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* full / test (3.14) (ID 130349372581)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  - Run tests (coverage leg)
  * Run tests
  * Build shard timings table
  * Upload shard timings
  * Upload coverage
  * Record installed core version
  * Write qualification evidence
  * Upload qualification evidence
  * Post Install dependencies
  * Post Run actions/checkout@v4
* full / test (3.12) (ID 130349372611)
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
* full / perf-floors (ID 130349372613)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Health check (Rust extension loadable)
  * Run slow tests
  * Run Phase 7E regression floor
  * Upload Phase 7E floor-check report
  * Run launch regression floor
  * Upload launch floor-check report
  * Run view-hints regression floor
  * Upload view-hints floor-check report
  * Run agents disk-load operation-count floor
  * Upload agents disk-load floor-check report
  * Run plugins catalog-scale regression floor
  * Upload plugins catalog-scale floor-check report
  * Run bead performance smoke
  * Upload bead performance smoke
  * Run bead scaled-corpus benchmark (record-only 4x)
  * Upload bead scaled-corpus benchmark
  * Run bead history-independence gate (1x+4x)
  * Upload bead history-independence gate report
  * Post Install dependencies
  * Post Run actions/checkout@v4
* full / visual-test (ID 130349372627)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  * Check TUI screenshots
  * Locate visual report
  * Build visual report
  * Upload visual report
  * Publish visual report
  * Publish unstable recapture summary
  * Upload first-attempt diffs
  * Upload visual artifacts
  * Post Install visual dependencies
  * Post Run actions/checkout@v4
* full / test (3.13) (ID 130349372634)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  - Run tests (coverage leg)
  * Run tests
  * Build shard timings table
  * Upload shard timings
  * Upload coverage
  * Record installed core version
  * Write qualification evidence
  * Upload qualification evidence
  * Post Install dependencies
  * Post Run actions/checkout@v4

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / prepare: .github#6

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / prepare: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / build-core / build-core: .github#4

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0LQH0agAAAACAAn0JAmZMSbGa7VFO+5j/TEFYRURHRTE2MTMARWRnZQ==
full / build-core / build-core: .github#7

! Failed to restore: Cache service responded with 400
full / build-core / build-core: .github#25

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / build-core / build-core: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / tutorial-tests: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0awH0agAAAABsNah2y6NwRrbhGzFSpF1PU0xDMzFFREdFMDEyMgBFZGdl
full / tutorial-tests: .github#9

! Failed to restore: Cache service responded with 400
full / tutorial-tests: .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / tutorial-tests: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / ace-page-group-isolation: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0hgH0agAAAAAZzH9Fqs5+S4bXRr4p6axUUEhMMzBFREdFMDEyMgBFZGdl
full / ace-page-group-isolation: .github#9

! Failed to restore: Cache service responded with 400
full / ace-page-group-isolation: .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / ace-page-group-isolation: .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* master Full CI · 42966182715
Triggered via workflow_dispatch about 24 minutes ago

JOBS
✓ full / prepare in 20s (ID 130343865852)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Validate qualification inputs
  - Download the sealed candidate manifest
  - Bind published identity from the sealed manifest
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
- full / release-core-floor-smoke (ID 130343867306)
- full / docs-build (ID 130343867307)
✓ full / build-core / build-core in 15m34s (ID 130344002788)
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
✓ full / tutorial-tests in 58s (ID 130349372470)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run tutorial tests
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ full / lint in 5m39s (ID 130349372477)
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
✓ full / ace-page-group-isolation in 1m26s (ID 130349372511)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  ✓ Run ACE shared-page isolation lane
  ✓ Post Install visual dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* full / test (3.14) (ID 130349372581)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  - Run tests (coverage leg)
  * Run tests
  * Build shard timings table
  * Upload shard timings
  * Upload coverage
  * Record installed core version
  * Write qualification evidence
  * Upload qualification evidence
  * Post Install dependencies
  * Post Run actions/checkout@v4
* full / test (3.12) (ID 130349372611)
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
✓ full / perf-floors in 8m17s (ID 130349372613)
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
* full / visual-test (ID 130349372627)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  * Check TUI screenshots
  * Locate visual report
  * Build visual report
  * Upload visual report
  * Publish visual report
  * Publish unstable recapture summary
  * Upload first-attempt diffs
  * Upload visual artifacts
  * Post Install visual dependencies
  * Post Run actions/checkout@v4
* full / test (3.13) (ID 130349372634)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  - Run tests (coverage leg)
  * Run tests
  * Build shard timings table
  * Upload shard timings
  * Upload coverage
  * Record installed core version
  * Write qualification evidence
  * Upload qualification evidence
  * Post Install dependencies
  * Post Run actions/checkout@v4

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / prepare: .github#6

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / prepare: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / build-core / build-core: .github#4

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0LQH0agAAAACAAn0JAmZMSbGa7VFO+5j/TEFYRURHRTE2MTMARWRnZQ==
full / build-core / build-core: .github#7

! Failed to restore: Cache service responded with 400
full / build-core / build-core: .github#25

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / build-core / build-core: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / tutorial-tests: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0awH0agAAAABsNah2y6NwRrbhGzFSpF1PU0xDMzFFREdFMDEyMgBFZGdl
full / tutorial-tests: .github#9

! Failed to restore: Cache service responded with 400
full / tutorial-tests: .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / tutorial-tests: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / ace-page-group-isolation: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0hgH0agAAAAAZzH9Fqs5+S4bXRr4p6axUUEhMMzBFREdFMDEyMgBFZGdl
full / ace-page-group-isolation: .github#9

! Failed to restore: Cache service responded with 400
full / ace-page-group-isolation: .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / ace-page-group-isolation: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / perf-floors: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0IQP0agAAAABqp4F+4oXTQ46Xsx4L3D4KQ0gxQUEyMDMwODE0MDYwAEVkZ2U=
full / perf-floors: .github#9

! Failed to restore: Cache service responded with 400
full / perf-floors: .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / perf-floors: .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* master Full CI · 42966182715
Triggered via workflow_dispatch about 26 minutes ago

JOBS
✓ full / prepare in 20s (ID 130343865852)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Validate qualification inputs
  - Download the sealed candidate manifest
  - Bind published identity from the sealed manifest
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
- full / release-core-floor-smoke (ID 130343867306)
- full / docs-build (ID 130343867307)
✓ full / build-core / build-core in 15m34s (ID 130344002788)
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
✓ full / tutorial-tests in 58s (ID 130349372470)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run tutorial tests
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ full / lint in 5m39s (ID 130349372477)
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
✓ full / ace-page-group-isolation in 1m26s (ID 130349372511)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  ✓ Run ACE shared-page isolation lane
  ✓ Post Install visual dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* full / test (3.14) (ID 130349372581)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  - Run tests (coverage leg)
  * Run tests
  * Build shard timings table
  * Upload shard timings
  * Upload coverage
  * Record installed core version
  * Write qualification evidence
  * Upload qualification evidence
  * Post Install dependencies
  * Post Run actions/checkout@v4
* full / test (3.12) (ID 130349372611)
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
✓ full / perf-floors in 8m17s (ID 130349372613)
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
* full / visual-test (ID 130349372627)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  * Check TUI screenshots
  * Locate visual report
  * Build visual report
  * Upload visual report
  * Publish visual report
  * Publish unstable recapture summary
  * Upload first-attempt diffs
  * Upload visual artifacts
  * Post Install visual dependencies
  * Post Run actions/checkout@v4
* full / test (3.13) (ID 130349372634)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  - Run tests (coverage leg)
  * Run tests
  * Build shard timings table
  * Upload shard timings
  * Upload coverage
  * Record installed core version
  * Write qualification evidence
  * Upload qualification evidence
  * Post Install dependencies
  * Post Run actions/checkout@v4

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / prepare: .github#6

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / prepare: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / build-core / build-core: .github#4

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0LQH0agAAAACAAn0JAmZMSbGa7VFO+5j/TEFYRURHRTE2MTMARWRnZQ==
full / build-core / build-core: .github#7

! Failed to restore: Cache service responded with 400
full / build-core / build-core: .github#25

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / build-core / build-core: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / tutorial-tests: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0awH0agAAAABsNah2y6NwRrbhGzFSpF1PU0xDMzFFREdFMDEyMgBFZGdl
full / tutorial-tests: .github#9

! Failed to restore: Cache service responded with 400
full / tutorial-tests: .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / tutorial-tests: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / ace-page-group-isolation: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0hgH0agAAAAAZzH9Fqs5+S4bXRr4p6axUUEhMMzBFREdFMDEyMgBFZGdl
full / ace-page-group-isolation: .github#9

! Failed to restore: Cache service responded with 400
full / ace-page-group-isolation: .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / ace-page-group-isolation: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / perf-floors: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0IQP0agAAAABqp4F+4oXTQ46Xsx4L3D4KQ0gxQUEyMDMwODE0MDYwAEVkZ2U=
full / perf-floors: .github#9

! Failed to restore: Cache service responded with 400
full / perf-floors: .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / perf-floors: .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* master Full CI · 42966182715
Triggered via workflow_dispatch about 28 minutes ago

JOBS
✓ full / prepare in 20s (ID 130343865852)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Validate qualification inputs
  - Download the sealed candidate manifest
  - Bind published identity from the sealed manifest
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
- full / release-core-floor-smoke (ID 130343867306)
- full / docs-build (ID 130343867307)
✓ full / build-core / build-core in 15m34s (ID 130344002788)
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
✓ full / tutorial-tests in 58s (ID 130349372470)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run tutorial tests
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ full / lint in 5m39s (ID 130349372477)
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
✓ full / ace-page-group-isolation in 1m26s (ID 130349372511)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  ✓ Run ACE shared-page isolation lane
  ✓ Post Install visual dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* full / test (3.14) (ID 130349372581)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  - Run tests (coverage leg)
  * Run tests
  * Build shard timings table
  * Upload shard timings
  * Upload coverage
  * Record installed core version
  * Write qualification evidence
  * Upload qualification evidence
  * Post Install dependencies
  * Post Run actions/checkout@v4
* full / test (3.12) (ID 130349372611)
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
✓ full / perf-floors in 8m17s (ID 130349372613)
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
* full / visual-test (ID 130349372627)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  * Check TUI screenshots
  * Locate visual report
  * Build visual report
  * Upload visual report
  * Publish visual report
  * Publish unstable recapture summary
  * Upload first-attempt diffs
  * Upload visual artifacts
  * Post Install visual dependencies
  * Post Run actions/checkout@v4
* full / test (3.13) (ID 130349372634)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  - Run tests (coverage leg)
  * Run tests
  * Build shard timings table
  * Upload shard timings
  * Upload coverage
  * Record installed core version
  * Write qualification evidence
  * Upload qualification evidence
  * Post Install dependencies
  * Post Run actions/checkout@v4

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / prepare: .github#6

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / prepare: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / build-core / build-core: .github#4

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0LQH0agAAAACAAn0JAmZMSbGa7VFO+5j/TEFYRURHRTE2MTMARWRnZQ==
full / build-core / build-core: .github#7

! Failed to restore: Cache service responded with 400
full / build-core / build-core: .github#25

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / build-core / build-core: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / tutorial-tests: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0awH0agAAAABsNah2y6NwRrbhGzFSpF1PU0xDMzFFREdFMDEyMgBFZGdl
full / tutorial-tests: .github#9

! Failed to restore: Cache service responded with 400
full / tutorial-tests: .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / tutorial-tests: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / ace-page-group-isolation: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0hgH0agAAAAAZzH9Fqs5+S4bXRr4p6axUUEhMMzBFREdFMDEyMgBFZGdl
full / ace-page-group-isolation: .github#9

! Failed to restore: Cache service responded with 400
full / ace-page-group-isolation: .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / ace-page-group-isolation: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / perf-floors: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0IQP0agAAAABqp4F+4oXTQ46Xsx4L3D4KQ0gxQUEyMDMwODE0MDYwAEVkZ2U=
full / perf-floors: .github#9

! Failed to restore: Cache service responded with 400
full / perf-floors: .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / perf-floors: .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* master Full CI · 42966182715
Triggered via workflow_dispatch about 30 minutes ago

JOBS
✓ full / prepare in 20s (ID 130343865852)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Validate qualification inputs
  - Download the sealed candidate manifest
  - Bind published identity from the sealed manifest
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
- full / release-core-floor-smoke (ID 130343867306)
- full / docs-build (ID 130343867307)
✓ full / build-core / build-core in 15m34s (ID 130344002788)
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
✓ full / tutorial-tests in 58s (ID 130349372470)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run tutorial tests
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ full / lint in 5m39s (ID 130349372477)
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
✓ full / ace-page-group-isolation in 1m26s (ID 130349372511)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  ✓ Run ACE shared-page isolation lane
  ✓ Post Install visual dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* full / test (3.14) (ID 130349372581)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  - Run tests (coverage leg)
  * Run tests
  * Build shard timings table
  * Upload shard timings
  * Upload coverage
  * Record installed core version
  * Write qualification evidence
  * Upload qualification evidence
  * Post Install dependencies
  * Post Run actions/checkout@v4
* full / test (3.12) (ID 130349372611)
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
✓ full / perf-floors in 8m17s (ID 130349372613)
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
* full / visual-test (ID 130349372627)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  * Check TUI screenshots
  * Locate visual report
  * Build visual report
  * Upload visual report
  * Publish visual report
  * Publish unstable recapture summary
  * Upload first-attempt diffs
  * Upload visual artifacts
  * Post Install visual dependencies
  * Post Run actions/checkout@v4
* full / test (3.13) (ID 130349372634)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  - Run tests (coverage leg)
  * Run tests
  * Build shard timings table
  * Upload shard timings
  * Upload coverage
  * Record installed core version
  * Write qualification evidence
  * Upload qualification evidence
  * Post Install dependencies
  * Post Run actions/checkout@v4

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / prepare: .github#6

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / prepare: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / build-core / build-core: .github#4

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0LQH0agAAAACAAn0JAmZMSbGa7VFO+5j/TEFYRURHRTE2MTMARWRnZQ==
full / build-core / build-core: .github#7

! Failed to restore: Cache service responded with 400
full / build-core / build-core: .github#25

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / build-core / build-core: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / tutorial-tests: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0awH0agAAAABsNah2y6NwRrbhGzFSpF1PU0xDMzFFREdFMDEyMgBFZGdl
full / tutorial-tests: .github#9

! Failed to restore: Cache service responded with 400
full / tutorial-tests: .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / tutorial-tests: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / ace-page-group-isolation: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0hgH0agAAAAAZzH9Fqs5+S4bXRr4p6axUUEhMMzBFREdFMDEyMgBFZGdl
full / ace-page-group-isolation: .github#9

! Failed to restore: Cache service responded with 400
full / ace-page-group-isolation: .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / ace-page-group-isolation: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / perf-floors: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0IQP0agAAAABqp4F+4oXTQ46Xsx4L3D4KQ0gxQUEyMDMwODE0MDYwAEVkZ2U=
full / perf-floors: .github#9

! Failed to restore: Cache service responded with 400
full / perf-floors: .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / perf-floors: .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* master Full CI · 42966182715
Triggered via workflow_dispatch about 32 minutes ago

JOBS
✓ full / prepare in 20s (ID 130343865852)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Validate qualification inputs
  - Download the sealed candidate manifest
  - Bind published identity from the sealed manifest
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
- full / release-core-floor-smoke (ID 130343867306)
- full / docs-build (ID 130343867307)
✓ full / build-core / build-core in 15m34s (ID 130344002788)
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
✓ full / tutorial-tests in 58s (ID 130349372470)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run tutorial tests
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ full / lint in 5m39s (ID 130349372477)
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
✓ full / ace-page-group-isolation in 1m26s (ID 130349372511)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  ✓ Run ACE shared-page isolation lane
  ✓ Post Install visual dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* full / test (3.14) (ID 130349372581)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  - Run tests (coverage leg)
  * Run tests
  * Build shard timings table
  * Upload shard timings
  * Upload coverage
  * Record installed core version
  * Write qualification evidence
  * Upload qualification evidence
  * Post Install dependencies
  * Post Run actions/checkout@v4
* full / test (3.12) (ID 130349372611)
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
✓ full / perf-floors in 8m17s (ID 130349372613)
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
* full / visual-test (ID 130349372627)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  * Check TUI screenshots
  * Locate visual report
  * Build visual report
  * Upload visual report
  * Publish visual report
  * Publish unstable recapture summary
  * Upload first-attempt diffs
  * Upload visual artifacts
  * Post Install visual dependencies
  * Post Run actions/checkout@v4
* full / test (3.13) (ID 130349372634)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  - Run tests (coverage leg)
  * Run tests
  * Build shard timings table
  * Upload shard timings
  * Upload coverage
  * Record installed core version
  * Write qualification evidence
  * Upload qualification evidence
  * Post Install dependencies
  * Post Run actions/checkout@v4

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / prepare: .github#6

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / prepare: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / build-core / build-core: .github#4

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0LQH0agAAAACAAn0JAmZMSbGa7VFO+5j/TEFYRURHRTE2MTMARWRnZQ==
full / build-core / build-core: .github#7

! Failed to restore: Cache service responded with 400
full / build-core / build-core: .github#25

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / build-core / build-core: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / tutorial-tests: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0awH0agAAAABsNah2y6NwRrbhGzFSpF1PU0xDMzFFREdFMDEyMgBFZGdl
full / tutorial-tests: .github#9

! Failed to restore: Cache service responded with 400
full / tutorial-tests: .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / tutorial-tests: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / ace-page-group-isolation: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0hgH0agAAAAAZzH9Fqs5+S4bXRr4p6axUUEhMMzBFREdFMDEyMgBFZGdl
full / ace-page-group-isolation: .github#9

! Failed to restore: Cache service responded with 400
full / ace-page-group-isolation: .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / ace-page-group-isolation: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / perf-floors: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0IQP0agAAAABqp4F+4oXTQ46Xsx4L3D4KQ0gxQUEyMDMwODE0MDYwAEVkZ2U=
full / perf-floors: .github#9

! Failed to restore: Cache service responded with 400
full / perf-floors: .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / perf-floors: .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* master Full CI · 42966182715
Triggered via workflow_dispatch about 34 minutes ago

JOBS
✓ full / prepare in 20s (ID 130343865852)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Validate qualification inputs
  - Download the sealed candidate manifest
  - Bind published identity from the sealed manifest
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
- full / release-core-floor-smoke (ID 130343867306)
- full / docs-build (ID 130343867307)
✓ full / build-core / build-core in 15m34s (ID 130344002788)
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
✓ full / tutorial-tests in 58s (ID 130349372470)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run tutorial tests
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ full / lint in 5m39s (ID 130349372477)
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
✓ full / ace-page-group-isolation in 1m26s (ID 130349372511)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  ✓ Run ACE shared-page isolation lane
  ✓ Post Install visual dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* full / test (3.14) (ID 130349372581)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  - Run tests (coverage leg)
  * Run tests
  * Build shard timings table
  * Upload shard timings
  * Upload coverage
  * Record installed core version
  * Write qualification evidence
  * Upload qualification evidence
  * Post Install dependencies
  * Post Run actions/checkout@v4
* full / test (3.12) (ID 130349372611)
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
✓ full / perf-floors in 8m17s (ID 130349372613)
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
* full / visual-test (ID 130349372627)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  * Check TUI screenshots
  * Locate visual report
  * Build visual report
  * Upload visual report
  * Publish visual report
  * Publish unstable recapture summary
  * Upload first-attempt diffs
  * Upload visual artifacts
  * Post Install visual dependencies
  * Post Run actions/checkout@v4
* full / test (3.13) (ID 130349372634)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  - Run tests (coverage leg)
  * Run tests
  * Build shard timings table
  * Upload shard timings
  * Upload coverage
  * Record installed core version
  * Write qualification evidence
  * Upload qualification evidence
  * Post Install dependencies
  * Post Run actions/checkout@v4

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / prepare: .github#6

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / prepare: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / build-core / build-core: .github#4

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0LQH0agAAAACAAn0JAmZMSbGa7VFO+5j/TEFYRURHRTE2MTMARWRnZQ==
full / build-core / build-core: .github#7

! Failed to restore: Cache service responded with 400
full / build-core / build-core: .github#25

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / build-core / build-core: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / tutorial-tests: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0awH0agAAAABsNah2y6NwRrbhGzFSpF1PU0xDMzFFREdFMDEyMgBFZGdl
full / tutorial-tests: .github#9

! Failed to restore: Cache service responded with 400
full / tutorial-tests: .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / tutorial-tests: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / ace-page-group-isolation: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0hgH0agAAAAAZzH9Fqs5+S4bXRr4p6axUUEhMMzBFREdFMDEyMgBFZGdl
full / ace-page-group-isolation: .github#9

! Failed to restore: Cache service responded with 400
full / ace-page-group-isolation: .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / ace-page-group-isolation: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / perf-floors: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0IQP0agAAAABqp4F+4oXTQ46Xsx4L3D4KQ0gxQUEyMDMwODE0MDYwAEVkZ2U=
full / perf-floors: .github#9

! Failed to restore: Cache service responded with 400
full / perf-floors: .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / perf-floors: .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* master Full CI · 42966182715
Triggered via workflow_dispatch about 36 minutes ago

JOBS
✓ full / prepare in 20s (ID 130343865852)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Validate qualification inputs
  - Download the sealed candidate manifest
  - Bind published identity from the sealed manifest
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
- full / release-core-floor-smoke (ID 130343867306)
- full / docs-build (ID 130343867307)
✓ full / build-core / build-core in 15m34s (ID 130344002788)
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
✓ full / tutorial-tests in 58s (ID 130349372470)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run tutorial tests
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ full / lint in 5m39s (ID 130349372477)
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
✓ full / ace-page-group-isolation in 1m26s (ID 130349372511)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  ✓ Run ACE shared-page isolation lane
  ✓ Post Install visual dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* full / test (3.14) (ID 130349372581)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  - Run tests (coverage leg)
  * Run tests
  * Build shard timings table
  * Upload shard timings
  * Upload coverage
  * Record installed core version
  * Write qualification evidence
  * Upload qualification evidence
  * Post Install dependencies
  * Post Run actions/checkout@v4
* full / test (3.12) (ID 130349372611)
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
✓ full / perf-floors in 8m17s (ID 130349372613)
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
* full / visual-test (ID 130349372627)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  * Check TUI screenshots
  * Locate visual report
  * Build visual report
  * Upload visual report
  * Publish visual report
  * Publish unstable recapture summary
  * Upload first-attempt diffs
  * Upload visual artifacts
  * Post Install visual dependencies
  * Post Run actions/checkout@v4
* full / test (3.13) (ID 130349372634)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  - Run tests (coverage leg)
  * Run tests
  * Build shard timings table
  * Upload shard timings
  * Upload coverage
  * Record installed core version
  * Write qualification evidence
  * Upload qualification evidence
  * Post Install dependencies
  * Post Run actions/checkout@v4

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / prepare: .github#6

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / prepare: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / build-core / build-core: .github#4

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0LQH0agAAAACAAn0JAmZMSbGa7VFO+5j/TEFYRURHRTE2MTMARWRnZQ==
full / build-core / build-core: .github#7

! Failed to restore: Cache service responded with 400
full / build-core / build-core: .github#25

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / build-core / build-core: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / tutorial-tests: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0awH0agAAAABsNah2y6NwRrbhGzFSpF1PU0xDMzFFREdFMDEyMgBFZGdl
full / tutorial-tests: .github#9

! Failed to restore: Cache service responded with 400
full / tutorial-tests: .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / tutorial-tests: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / ace-page-group-isolation: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0hgH0agAAAAAZzH9Fqs5+S4bXRr4p6axUUEhMMzBFREdFMDEyMgBFZGdl
full / ace-page-group-isolation: .github#9

! Failed to restore: Cache service responded with 400
full / ace-page-group-isolation: .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / ace-page-group-isolation: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / perf-floors: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0IQP0agAAAABqp4F+4oXTQ46Xsx4L3D4KQ0gxQUEyMDMwODE0MDYwAEVkZ2U=
full / perf-floors: .github#9

! Failed to restore: Cache service responded with 400
full / perf-floors: .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / perf-floors: .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* master Full CI · 42966182715
Triggered via workflow_dispatch about 38 minutes ago

JOBS
✓ full / prepare in 20s (ID 130343865852)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Validate qualification inputs
  - Download the sealed candidate manifest
  - Bind published identity from the sealed manifest
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
- full / release-core-floor-smoke (ID 130343867306)
- full / docs-build (ID 130343867307)
✓ full / build-core / build-core in 15m34s (ID 130344002788)
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
✓ full / tutorial-tests in 58s (ID 130349372470)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run tutorial tests
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ full / lint in 5m39s (ID 130349372477)
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
✓ full / ace-page-group-isolation in 1m26s (ID 130349372511)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  ✓ Run ACE shared-page isolation lane
  ✓ Post Install visual dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* full / test (3.14) (ID 130349372581)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  - Run tests (coverage leg)
  * Run tests
  * Build shard timings table
  * Upload shard timings
  * Upload coverage
  * Record installed core version
  * Write qualification evidence
  * Upload qualification evidence
  * Post Install dependencies
  * Post Run actions/checkout@v4
* full / test (3.12) (ID 130349372611)
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
✓ full / perf-floors in 8m17s (ID 130349372613)
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
* full / visual-test (ID 130349372627)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  * Check TUI screenshots
  * Locate visual report
  * Build visual report
  * Upload visual report
  * Publish visual report
  * Publish unstable recapture summary
  * Upload first-attempt diffs
  * Upload visual artifacts
  * Post Install visual dependencies
  * Post Run actions/checkout@v4
* full / test (3.13) (ID 130349372634)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  - Run tests (coverage leg)
  * Run tests
  * Build shard timings table
  * Upload shard timings
  * Upload coverage
  * Record installed core version
  * Write qualification evidence
  * Upload qualification evidence
  * Post Install dependencies
  * Post Run actions/checkout@v4

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / prepare: .github#6

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / prepare: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / build-core / build-core: .github#4

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0LQH0agAAAACAAn0JAmZMSbGa7VFO+5j/TEFYRURHRTE2MTMARWRnZQ==
full / build-core / build-core: .github#7

! Failed to restore: Cache service responded with 400
full / build-core / build-core: .github#25

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / build-core / build-core: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / tutorial-tests: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0awH0agAAAABsNah2y6NwRrbhGzFSpF1PU0xDMzFFREdFMDEyMgBFZGdl
full / tutorial-tests: .github#9

! Failed to restore: Cache service responded with 400
full / tutorial-tests: .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / tutorial-tests: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / ace-page-group-isolation: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0hgH0agAAAAAZzH9Fqs5+S4bXRr4p6axUUEhMMzBFREdFMDEyMgBFZGdl
full / ace-page-group-isolation: .github#9

! Failed to restore: Cache service responded with 400
full / ace-page-group-isolation: .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / ace-page-group-isolation: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / perf-floors: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0IQP0agAAAABqp4F+4oXTQ46Xsx4L3D4KQ0gxQUEyMDMwODE0MDYwAEVkZ2U=
full / perf-floors: .github#9

! Failed to restore: Cache service responded with 400
full / perf-floors: .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / perf-floors: .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* master Full CI · 42966182715
Triggered via workflow_dispatch about 40 minutes ago

JOBS
✓ full / prepare in 20s (ID 130343865852)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Validate qualification inputs
  - Download the sealed candidate manifest
  - Bind published identity from the sealed manifest
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
- full / release-core-floor-smoke (ID 130343867306)
- full / docs-build (ID 130343867307)
✓ full / build-core / build-core in 15m34s (ID 130344002788)
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
✓ full / tutorial-tests in 58s (ID 130349372470)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run tutorial tests
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ full / lint in 5m39s (ID 130349372477)
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
✓ full / ace-page-group-isolation in 1m26s (ID 130349372511)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  ✓ Run ACE shared-page isolation lane
  ✓ Post Install visual dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* full / test (3.14) (ID 130349372581)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  - Run tests (coverage leg)
  * Run tests
  * Build shard timings table
  * Upload shard timings
  * Upload coverage
  * Record installed core version
  * Write qualification evidence
  * Upload qualification evidence
  * Post Install dependencies
  * Post Run actions/checkout@v4
* full / test (3.12) (ID 130349372611)
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
✓ full / perf-floors in 8m17s (ID 130349372613)
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
* full / visual-test (ID 130349372627)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  X Check TUI screenshots
  ✓ Locate visual report
  ✓ Build visual report
  ✓ Upload visual report
  ✓ Publish visual report
  - Publish unstable recapture summary
  ✓ Upload first-attempt diffs
  * Upload visual artifacts
  * Post Install visual dependencies
  * Post Run actions/checkout@v4
* full / test (3.13) (ID 130349372634)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  - Run tests (coverage leg)
  * Run tests
  * Build shard timings table
  * Upload shard timings
  * Upload coverage
  * Record installed core version
  * Write qualification evidence
  * Upload qualification evidence
  * Post Install dependencies
  * Post Run actions/checkout@v4

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / prepare: .github#6

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / prepare: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / build-core / build-core: .github#4

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0LQH0agAAAACAAn0JAmZMSbGa7VFO+5j/TEFYRURHRTE2MTMARWRnZQ==
full / build-core / build-core: .github#7

! Failed to restore: Cache service responded with 400
full / build-core / build-core: .github#25

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / build-core / build-core: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / tutorial-tests: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0awH0agAAAABsNah2y6NwRrbhGzFSpF1PU0xDMzFFREdFMDEyMgBFZGdl
full / tutorial-tests: .github#9

! Failed to restore: Cache service responded with 400
full / tutorial-tests: .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / tutorial-tests: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / ace-page-group-isolation: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0hgH0agAAAAAZzH9Fqs5+S4bXRr4p6axUUEhMMzBFREdFMDEyMgBFZGdl
full / ace-page-group-isolation: .github#9

! Failed to restore: Cache service responded with 400
full / ace-page-group-isolation: .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / ace-page-group-isolation: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / perf-floors: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0IQP0agAAAABqp4F+4oXTQ46Xsx4L3D4KQ0gxQUEyMDMwODE0MDYwAEVkZ2U=
full / perf-floors: .github#9

! Failed to restore: Cache service responded with 400
full / perf-floors: .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / perf-floors: .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* master Full CI · 42966182715
Triggered via workflow_dispatch about 42 minutes ago

JOBS
✓ full / prepare in 20s (ID 130343865852)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Validate qualification inputs
  - Download the sealed candidate manifest
  - Bind published identity from the sealed manifest
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
- full / release-core-floor-smoke (ID 130343867306)
- full / docs-build (ID 130343867307)
✓ full / build-core / build-core in 15m34s (ID 130344002788)
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
✓ full / tutorial-tests in 58s (ID 130349372470)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run tutorial tests
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ full / lint in 5m39s (ID 130349372477)
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
✓ full / ace-page-group-isolation in 1m26s (ID 130349372511)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  ✓ Run ACE shared-page isolation lane
  ✓ Post Install visual dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* full / test (3.14) (ID 130349372581)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  - Run tests (coverage leg)
  * Run tests
  * Build shard timings table
  * Upload shard timings
  * Upload coverage
  * Record installed core version
  * Write qualification evidence
  * Upload qualification evidence
  * Post Install dependencies
  * Post Run actions/checkout@v4
* full / test (3.12) (ID 130349372611)
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
✓ full / perf-floors in 8m17s (ID 130349372613)
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
X full / visual-test in 24m46s (ID 130349372627)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  X Check TUI screenshots
  ✓ Locate visual report
  ✓ Build visual report
  ✓ Upload visual report
  ✓ Publish visual report
  - Publish unstable recapture summary
  ✓ Upload first-attempt diffs
  ✓ Upload visual artifacts
  ✓ Post Install visual dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* full / test (3.13) (ID 130349372634)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  - Run tests (coverage leg)
  * Run tests
  * Build shard timings table
  * Upload shard timings
  * Upload coverage
  * Record installed core version
  * Write qualification evidence
  * Upload qualification evidence
  * Post Install dependencies
  * Post Run actions/checkout@v4

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / prepare: .github#6

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / prepare: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / build-core / build-core: .github#4

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0LQH0agAAAACAAn0JAmZMSbGa7VFO+5j/TEFYRURHRTE2MTMARWRnZQ==
full / build-core / build-core: .github#7

! Failed to restore: Cache service responded with 400
full / build-core / build-core: .github#25

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / build-core / build-core: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / tutorial-tests: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0awH0agAAAABsNah2y6NwRrbhGzFSpF1PU0xDMzFFREdFMDEyMgBFZGdl
full / tutorial-tests: .github#9

! Failed to restore: Cache service responded with 400
full / tutorial-tests: .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / tutorial-tests: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / ace-page-group-isolation: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0hgH0agAAAAAZzH9Fqs5+S4bXRr4p6axUUEhMMzBFREdFMDEyMgBFZGdl
full / ace-page-group-isolation: .github#9

! Failed to restore: Cache service responded with 400
full / ace-page-group-isolation: .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / ace-page-group-isolation: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / perf-floors: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0IQP0agAAAABqp4F+4oXTQ46Xsx4L3D4KQ0gxQUEyMDMwODE0MDYwAEVkZ2U=
full / perf-floors: .github#9

! Failed to restore: Cache service responded with 400
full / perf-floors: .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / perf-floors: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / visual-test: .github#2

X agents_final_rows_60x40: updated | changed pixels 8667/769500 (1.126316%) | expected=tests/ace/tui/visual/snapshots/png/agents_final_rows_60x40.png
full / visual-test: tests/ace/tui/visual/test_ace_png_snapshots_agents_final_rows.py#86

X Process completed with exit code 1.
full / visual-test: .github#382

! Failed to restore: Cache service responded with 400
full / visual-test: .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / visual-test: .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* master Full CI · 42966182715
Triggered via workflow_dispatch about 44 minutes ago

JOBS
✓ full / prepare in 20s (ID 130343865852)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Validate qualification inputs
  - Download the sealed candidate manifest
  - Bind published identity from the sealed manifest
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
- full / release-core-floor-smoke (ID 130343867306)
- full / docs-build (ID 130343867307)
✓ full / build-core / build-core in 15m34s (ID 130344002788)
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
✓ full / tutorial-tests in 58s (ID 130349372470)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run tutorial tests
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ full / lint in 5m39s (ID 130349372477)
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
✓ full / ace-page-group-isolation in 1m26s (ID 130349372511)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  ✓ Run ACE shared-page isolation lane
  ✓ Post Install visual dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* full / test (3.14) (ID 130349372581)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  - Run tests (coverage leg)
  * Run tests
  * Build shard timings table
  * Upload shard timings
  * Upload coverage
  * Record installed core version
  * Write qualification evidence
  * Upload qualification evidence
  * Post Install dependencies
  * Post Run actions/checkout@v4
* full / test (3.12) (ID 130349372611)
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
✓ full / perf-floors in 8m17s (ID 130349372613)
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
X full / visual-test in 24m46s (ID 130349372627)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  X Check TUI screenshots
  ✓ Locate visual report
  ✓ Build visual report
  ✓ Upload visual report
  ✓ Publish visual report
  - Publish unstable recapture summary
  ✓ Upload first-attempt diffs
  ✓ Upload visual artifacts
  ✓ Post Install visual dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* full / test (3.13) (ID 130349372634)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  - Run tests (coverage leg)
  * Run tests
  * Build shard timings table
  * Upload shard timings
  * Upload coverage
  * Record installed core version
  * Write qualification evidence
  * Upload qualification evidence
  * Post Install dependencies
  * Post Run actions/checkout@v4

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / prepare: .github#6

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / prepare: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / build-core / build-core: .github#4

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0LQH0agAAAACAAn0JAmZMSbGa7VFO+5j/TEFYRURHRTE2MTMARWRnZQ==
full / build-core / build-core: .github#7

! Failed to restore: Cache service responded with 400
full / build-core / build-core: .github#25

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / build-core / build-core: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / tutorial-tests: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0awH0agAAAABsNah2y6NwRrbhGzFSpF1PU0xDMzFFREdFMDEyMgBFZGdl
full / tutorial-tests: .github#9

! Failed to restore: Cache service responded with 400
full / tutorial-tests: .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / tutorial-tests: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / ace-page-group-isolation: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0hgH0agAAAAAZzH9Fqs5+S4bXRr4p6axUUEhMMzBFREdFMDEyMgBFZGdl
full / ace-page-group-isolation: .github#9

! Failed to restore: Cache service responded with 400
full / ace-page-group-isolation: .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / ace-page-group-isolation: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / perf-floors: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0IQP0agAAAABqp4F+4oXTQ46Xsx4L3D4KQ0gxQUEyMDMwODE0MDYwAEVkZ2U=
full / perf-floors: .github#9

! Failed to restore: Cache service responded with 400
full / perf-floors: .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / perf-floors: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / visual-test: .github#2

X agents_final_rows_60x40: updated | changed pixels 8667/769500 (1.126316%) | expected=tests/ace/tui/visual/snapshots/png/agents_final_rows_60x40.png
full / visual-test: tests/ace/tui/visual/test_ace_png_snapshots_agents_final_rows.py#86

X Process completed with exit code 1.
full / visual-test: .github#382

! Failed to restore: Cache service responded with 400
full / visual-test: .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / visual-test: .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* master Full CI · 42966182715
Triggered via workflow_dispatch about 46 minutes ago

JOBS
✓ full / prepare in 20s (ID 130343865852)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Validate qualification inputs
  - Download the sealed candidate manifest
  - Bind published identity from the sealed manifest
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
- full / release-core-floor-smoke (ID 130343867306)
- full / docs-build (ID 130343867307)
✓ full / build-core / build-core in 15m34s (ID 130344002788)
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
✓ full / tutorial-tests in 58s (ID 130349372470)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run tutorial tests
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ full / lint in 5m39s (ID 130349372477)
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
✓ full / ace-page-group-isolation in 1m26s (ID 130349372511)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  ✓ Run ACE shared-page isolation lane
  ✓ Post Install visual dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* full / test (3.14) (ID 130349372581)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  - Run tests (coverage leg)
  * Run tests
  * Build shard timings table
  * Upload shard timings
  * Upload coverage
  * Record installed core version
  * Write qualification evidence
  * Upload qualification evidence
  * Post Install dependencies
  * Post Run actions/checkout@v4
* full / test (3.12) (ID 130349372611)
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
✓ full / perf-floors in 8m17s (ID 130349372613)
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
X full / visual-test in 24m46s (ID 130349372627)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  X Check TUI screenshots
  ✓ Locate visual report
  ✓ Build visual report
  ✓ Upload visual report
  ✓ Publish visual report
  - Publish unstable recapture summary
  ✓ Upload first-attempt diffs
  ✓ Upload visual artifacts
  ✓ Post Install visual dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* full / test (3.13) (ID 130349372634)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  - Run tests (coverage leg)
  * Run tests
  * Build shard timings table
  * Upload shard timings
  * Upload coverage
  * Record installed core version
  * Write qualification evidence
  * Upload qualification evidence
  * Post Install dependencies
  * Post Run actions/checkout@v4

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / prepare: .github#6

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / prepare: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / build-core / build-core: .github#4

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0LQH0agAAAACAAn0JAmZMSbGa7VFO+5j/TEFYRURHRTE2MTMARWRnZQ==
full / build-core / build-core: .github#7

! Failed to restore: Cache service responded with 400
full / build-core / build-core: .github#25

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / build-core / build-core: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / tutorial-tests: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0awH0agAAAABsNah2y6NwRrbhGzFSpF1PU0xDMzFFREdFMDEyMgBFZGdl
full / tutorial-tests: .github#9

! Failed to restore: Cache service responded with 400
full / tutorial-tests: .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / tutorial-tests: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / ace-page-group-isolation: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0hgH0agAAAAAZzH9Fqs5+S4bXRr4p6axUUEhMMzBFREdFMDEyMgBFZGdl
full / ace-page-group-isolation: .github#9

! Failed to restore: Cache service responded with 400
full / ace-page-group-isolation: .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / ace-page-group-isolation: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / perf-floors: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0IQP0agAAAABqp4F+4oXTQ46Xsx4L3D4KQ0gxQUEyMDMwODE0MDYwAEVkZ2U=
full / perf-floors: .github#9

! Failed to restore: Cache service responded with 400
full / perf-floors: .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / perf-floors: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / visual-test: .github#2

X agents_final_rows_60x40: updated | changed pixels 8667/769500 (1.126316%) | expected=tests/ace/tui/visual/snapshots/png/agents_final_rows_60x40.png
full / visual-test: tests/ace/tui/visual/test_ace_png_snapshots_agents_final_rows.py#86

X Process completed with exit code 1.
full / visual-test: .github#382

! Failed to restore: Cache service responded with 400
full / visual-test: .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / visual-test: .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* master Full CI · 42966182715
Triggered via workflow_dispatch about 48 minutes ago

JOBS
✓ full / prepare in 20s (ID 130343865852)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Validate qualification inputs
  - Download the sealed candidate manifest
  - Bind published identity from the sealed manifest
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
- full / release-core-floor-smoke (ID 130343867306)
- full / docs-build (ID 130343867307)
✓ full / build-core / build-core in 15m34s (ID 130344002788)
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
✓ full / tutorial-tests in 58s (ID 130349372470)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run tutorial tests
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ full / lint in 5m39s (ID 130349372477)
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
✓ full / ace-page-group-isolation in 1m26s (ID 130349372511)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  ✓ Run ACE shared-page isolation lane
  ✓ Post Install visual dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* full / test (3.14) (ID 130349372581)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  - Run tests (coverage leg)
  * Run tests
  * Build shard timings table
  * Upload shard timings
  * Upload coverage
  * Record installed core version
  * Write qualification evidence
  * Upload qualification evidence
  * Post Install dependencies
  * Post Run actions/checkout@v4
* full / test (3.12) (ID 130349372611)
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
✓ full / perf-floors in 8m17s (ID 130349372613)
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
X full / visual-test in 24m46s (ID 130349372627)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  X Check TUI screenshots
  ✓ Locate visual report
  ✓ Build visual report
  ✓ Upload visual report
  ✓ Publish visual report
  - Publish unstable recapture summary
  ✓ Upload first-attempt diffs
  ✓ Upload visual artifacts
  ✓ Post Install visual dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* full / test (3.13) (ID 130349372634)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  - Run tests (coverage leg)
  * Run tests
  * Build shard timings table
  * Upload shard timings
  * Upload coverage
  * Record installed core version
  * Write qualification evidence
  * Upload qualification evidence
  * Post Install dependencies
  * Post Run actions/checkout@v4

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / prepare: .github#6

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / prepare: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / build-core / build-core: .github#4

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0LQH0agAAAACAAn0JAmZMSbGa7VFO+5j/TEFYRURHRTE2MTMARWRnZQ==
full / build-core / build-core: .github#7

! Failed to restore: Cache service responded with 400
full / build-core / build-core: .github#25

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / build-core / build-core: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / tutorial-tests: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0awH0agAAAABsNah2y6NwRrbhGzFSpF1PU0xDMzFFREdFMDEyMgBFZGdl
full / tutorial-tests: .github#9

! Failed to restore: Cache service responded with 400
full / tutorial-tests: .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / tutorial-tests: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / ace-page-group-isolation: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0hgH0agAAAAAZzH9Fqs5+S4bXRr4p6axUUEhMMzBFREdFMDEyMgBFZGdl
full / ace-page-group-isolation: .github#9

! Failed to restore: Cache service responded with 400
full / ace-page-group-isolation: .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / ace-page-group-isolation: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / perf-floors: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0IQP0agAAAABqp4F+4oXTQ46Xsx4L3D4KQ0gxQUEyMDMwODE0MDYwAEVkZ2U=
full / perf-floors: .github#9

! Failed to restore: Cache service responded with 400
full / perf-floors: .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / perf-floors: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / visual-test: .github#2

X agents_final_rows_60x40: updated | changed pixels 8667/769500 (1.126316%) | expected=tests/ace/tui/visual/snapshots/png/agents_final_rows_60x40.png
full / visual-test: tests/ace/tui/visual/test_ace_png_snapshots_agents_final_rows.py#86

X Process completed with exit code 1.
full / visual-test: .github#382

! Failed to restore: Cache service responded with 400
full / visual-test: .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / visual-test: .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* master Full CI · 42966182715
Triggered via workflow_dispatch about 50 minutes ago

JOBS
✓ full / prepare in 20s (ID 130343865852)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Validate qualification inputs
  - Download the sealed candidate manifest
  - Bind published identity from the sealed manifest
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
- full / release-core-floor-smoke (ID 130343867306)
- full / docs-build (ID 130343867307)
✓ full / build-core / build-core in 15m34s (ID 130344002788)
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
✓ full / tutorial-tests in 58s (ID 130349372470)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run tutorial tests
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ full / lint in 5m39s (ID 130349372477)
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
✓ full / ace-page-group-isolation in 1m26s (ID 130349372511)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  ✓ Run ACE shared-page isolation lane
  ✓ Post Install visual dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* full / test (3.14) (ID 130349372581)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  - Run tests (coverage leg)
  * Run tests
  * Build shard timings table
  * Upload shard timings
  * Upload coverage
  * Record installed core version
  * Write qualification evidence
  * Upload qualification evidence
  * Post Install dependencies
  * Post Run actions/checkout@v4
* full / test (3.12) (ID 130349372611)
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
✓ full / perf-floors in 8m17s (ID 130349372613)
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
X full / visual-test in 24m46s (ID 130349372627)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  X Check TUI screenshots
  ✓ Locate visual report
  ✓ Build visual report
  ✓ Upload visual report
  ✓ Publish visual report
  - Publish unstable recapture summary
  ✓ Upload first-attempt diffs
  ✓ Upload visual artifacts
  ✓ Post Install visual dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* full / test (3.13) (ID 130349372634)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  - Run tests (coverage leg)
  * Run tests
  * Build shard timings table
  * Upload shard timings
  * Upload coverage
  * Record installed core version
  * Write qualification evidence
  * Upload qualification evidence
  * Post Install dependencies
  * Post Run actions/checkout@v4

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / prepare: .github#6

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / prepare: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / build-core / build-core: .github#4

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0LQH0agAAAACAAn0JAmZMSbGa7VFO+5j/TEFYRURHRTE2MTMARWRnZQ==
full / build-core / build-core: .github#7

! Failed to restore: Cache service responded with 400
full / build-core / build-core: .github#25

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / build-core / build-core: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / tutorial-tests: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0awH0agAAAABsNah2y6NwRrbhGzFSpF1PU0xDMzFFREdFMDEyMgBFZGdl
full / tutorial-tests: .github#9

! Failed to restore: Cache service responded with 400
full / tutorial-tests: .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / tutorial-tests: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / ace-page-group-isolation: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0hgH0agAAAAAZzH9Fqs5+S4bXRr4p6axUUEhMMzBFREdFMDEyMgBFZGdl
full / ace-page-group-isolation: .github#9

! Failed to restore: Cache service responded with 400
full / ace-page-group-isolation: .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / ace-page-group-isolation: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / perf-floors: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0IQP0agAAAABqp4F+4oXTQ46Xsx4L3D4KQ0gxQUEyMDMwODE0MDYwAEVkZ2U=
full / perf-floors: .github#9

! Failed to restore: Cache service responded with 400
full / perf-floors: .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / perf-floors: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / visual-test: .github#2

X agents_final_rows_60x40: updated | changed pixels 8667/769500 (1.126316%) | expected=tests/ace/tui/visual/snapshots/png/agents_final_rows_60x40.png
full / visual-test: tests/ace/tui/visual/test_ace_png_snapshots_agents_final_rows.py#86

X Process completed with exit code 1.
full / visual-test: .github#382

! Failed to restore: Cache service responded with 400
full / visual-test: .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / visual-test: .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* master Full CI · 42966182715
Triggered via workflow_dispatch about 52 minutes ago

JOBS
✓ full / prepare in 20s (ID 130343865852)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Validate qualification inputs
  - Download the sealed candidate manifest
  - Bind published identity from the sealed manifest
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
- full / release-core-floor-smoke (ID 130343867306)
- full / docs-build (ID 130343867307)
✓ full / build-core / build-core in 15m34s (ID 130344002788)
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
✓ full / tutorial-tests in 58s (ID 130349372470)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run tutorial tests
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ full / lint in 5m39s (ID 130349372477)
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
✓ full / ace-page-group-isolation in 1m26s (ID 130349372511)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  ✓ Run ACE shared-page isolation lane
  ✓ Post Install visual dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* full / test (3.14) (ID 130349372581)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  - Run tests (coverage leg)
  * Run tests
  * Build shard timings table
  * Upload shard timings
  * Upload coverage
  * Record installed core version
  * Write qualification evidence
  * Upload qualification evidence
  * Post Install dependencies
  * Post Run actions/checkout@v4
* full / test (3.12) (ID 130349372611)
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
✓ full / perf-floors in 8m17s (ID 130349372613)
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
X full / visual-test in 24m46s (ID 130349372627)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  X Check TUI screenshots
  ✓ Locate visual report
  ✓ Build visual report
  ✓ Upload visual report
  ✓ Publish visual report
  - Publish unstable recapture summary
  ✓ Upload first-attempt diffs
  ✓ Upload visual artifacts
  ✓ Post Install visual dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* full / test (3.13) (ID 130349372634)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  - Run tests (coverage leg)
  * Run tests
  * Build shard timings table
  * Upload shard timings
  * Upload coverage
  * Record installed core version
  * Write qualification evidence
  * Upload qualification evidence
  * Post Install dependencies
  * Post Run actions/checkout@v4

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / prepare: .github#6

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / prepare: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / build-core / build-core: .github#4

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0LQH0agAAAACAAn0JAmZMSbGa7VFO+5j/TEFYRURHRTE2MTMARWRnZQ==
full / build-core / build-core: .github#7

! Failed to restore: Cache service responded with 400
full / build-core / build-core: .github#25

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / build-core / build-core: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / tutorial-tests: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0awH0agAAAABsNah2y6NwRrbhGzFSpF1PU0xDMzFFREdFMDEyMgBFZGdl
full / tutorial-tests: .github#9

! Failed to restore: Cache service responded with 400
full / tutorial-tests: .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / tutorial-tests: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / ace-page-group-isolation: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0hgH0agAAAAAZzH9Fqs5+S4bXRr4p6axUUEhMMzBFREdFMDEyMgBFZGdl
full / ace-page-group-isolation: .github#9

! Failed to restore: Cache service responded with 400
full / ace-page-group-isolation: .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / ace-page-group-isolation: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / perf-floors: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0IQP0agAAAABqp4F+4oXTQ46Xsx4L3D4KQ0gxQUEyMDMwODE0MDYwAEVkZ2U=
full / perf-floors: .github#9

! Failed to restore: Cache service responded with 400
full / perf-floors: .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / perf-floors: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / visual-test: .github#2

X agents_final_rows_60x40: updated | changed pixels 8667/769500 (1.126316%) | expected=tests/ace/tui/visual/snapshots/png/agents_final_rows_60x40.png
full / visual-test: tests/ace/tui/visual/test_ace_png_snapshots_agents_final_rows.py#86

X Process completed with exit code 1.
full / visual-test: .github#382

! Failed to restore: Cache service responded with 400
full / visual-test: .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / visual-test: .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* master Full CI · 42966182715
Triggered via workflow_dispatch about 54 minutes ago

JOBS
✓ full / prepare in 20s (ID 130343865852)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Validate qualification inputs
  - Download the sealed candidate manifest
  - Bind published identity from the sealed manifest
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
- full / release-core-floor-smoke (ID 130343867306)
- full / docs-build (ID 130343867307)
✓ full / build-core / build-core in 15m34s (ID 130344002788)
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
✓ full / tutorial-tests in 58s (ID 130349372470)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run tutorial tests
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ full / lint in 5m39s (ID 130349372477)
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
✓ full / ace-page-group-isolation in 1m26s (ID 130349372511)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  ✓ Run ACE shared-page isolation lane
  ✓ Post Install visual dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* full / test (3.14) (ID 130349372581)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  - Run tests (coverage leg)
  * Run tests
  * Build shard timings table
  * Upload shard timings
  * Upload coverage
  * Record installed core version
  * Write qualification evidence
  * Upload qualification evidence
  * Post Install dependencies
  * Post Run actions/checkout@v4
* full / test (3.12) (ID 130349372611)
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
✓ full / perf-floors in 8m17s (ID 130349372613)
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
X full / visual-test in 24m46s (ID 130349372627)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  X Check TUI screenshots
  ✓ Locate visual report
  ✓ Build visual report
  ✓ Upload visual report
  ✓ Publish visual report
  - Publish unstable recapture summary
  ✓ Upload first-attempt diffs
  ✓ Upload visual artifacts
  ✓ Post Install visual dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* full / test (3.13) (ID 130349372634)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  - Run tests (coverage leg)
  * Run tests
  * Build shard timings table
  * Upload shard timings
  * Upload coverage
  * Record installed core version
  * Write qualification evidence
  * Upload qualification evidence
  * Post Install dependencies
  * Post Run actions/checkout@v4

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / prepare: .github#6

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / prepare: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / build-core / build-core: .github#4

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0LQH0agAAAACAAn0JAmZMSbGa7VFO+5j/TEFYRURHRTE2MTMARWRnZQ==
full / build-core / build-core: .github#7

! Failed to restore: Cache service responded with 400
full / build-core / build-core: .github#25

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / build-core / build-core: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / tutorial-tests: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0awH0agAAAABsNah2y6NwRrbhGzFSpF1PU0xDMzFFREdFMDEyMgBFZGdl
full / tutorial-tests: .github#9

! Failed to restore: Cache service responded with 400
full / tutorial-tests: .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / tutorial-tests: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / ace-page-group-isolation: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0hgH0agAAAAAZzH9Fqs5+S4bXRr4p6axUUEhMMzBFREdFMDEyMgBFZGdl
full / ace-page-group-isolation: .github#9

! Failed to restore: Cache service responded with 400
full / ace-page-group-isolation: .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / ace-page-group-isolation: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / perf-floors: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0IQP0agAAAABqp4F+4oXTQ46Xsx4L3D4KQ0gxQUEyMDMwODE0MDYwAEVkZ2U=
full / perf-floors: .github#9

! Failed to restore: Cache service responded with 400
full / perf-floors: .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / perf-floors: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / visual-test: .github#2

X agents_final_rows_60x40: updated | changed pixels 8667/769500 (1.126316%) | expected=tests/ace/tui/visual/snapshots/png/agents_final_rows_60x40.png
full / visual-test: tests/ace/tui/visual/test_ace_png_snapshots_agents_final_rows.py#86

X Process completed with exit code 1.
full / visual-test: .github#382

! Failed to restore: Cache service responded with 400
full / visual-test: .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / visual-test: .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* master Full CI · 42966182715
Triggered via workflow_dispatch about 56 minutes ago

JOBS
✓ full / prepare in 20s (ID 130343865852)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Validate qualification inputs
  - Download the sealed candidate manifest
  - Bind published identity from the sealed manifest
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
- full / release-core-floor-smoke (ID 130343867306)
- full / docs-build (ID 130343867307)
✓ full / build-core / build-core in 15m34s (ID 130344002788)
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
✓ full / tutorial-tests in 58s (ID 130349372470)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run tutorial tests
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ full / lint in 5m39s (ID 130349372477)
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
✓ full / ace-page-group-isolation in 1m26s (ID 130349372511)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  ✓ Run ACE shared-page isolation lane
  ✓ Post Install visual dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* full / test (3.14) (ID 130349372581)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  - Run tests (coverage leg)
  * Run tests
  * Build shard timings table
  * Upload shard timings
  * Upload coverage
  * Record installed core version
  * Write qualification evidence
  * Upload qualification evidence
  * Post Install dependencies
  * Post Run actions/checkout@v4
* full / test (3.12) (ID 130349372611)
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
✓ full / perf-floors in 8m17s (ID 130349372613)
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
X full / visual-test in 24m46s (ID 130349372627)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  X Check TUI screenshots
  ✓ Locate visual report
  ✓ Build visual report
  ✓ Upload visual report
  ✓ Publish visual report
  - Publish unstable recapture summary
  ✓ Upload first-attempt diffs
  ✓ Upload visual artifacts
  ✓ Post Install visual dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* full / test (3.13) (ID 130349372634)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  - Run tests (coverage leg)
  * Run tests
  * Build shard timings table
  * Upload shard timings
  * Upload coverage
  * Record installed core version
  * Write qualification evidence
  * Upload qualification evidence
  * Post Install dependencies
  * Post Run actions/checkout@v4

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / prepare: .github#6

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / prepare: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / build-core / build-core: .github#4

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0LQH0agAAAACAAn0JAmZMSbGa7VFO+5j/TEFYRURHRTE2MTMARWRnZQ==
full / build-core / build-core: .github#7

! Failed to restore: Cache service responded with 400
full / build-core / build-core: .github#25

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / build-core / build-core: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / tutorial-tests: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0awH0agAAAABsNah2y6NwRrbhGzFSpF1PU0xDMzFFREdFMDEyMgBFZGdl
full / tutorial-tests: .github#9

! Failed to restore: Cache service responded with 400
full / tutorial-tests: .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / tutorial-tests: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / ace-page-group-isolation: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0hgH0agAAAAAZzH9Fqs5+S4bXRr4p6axUUEhMMzBFREdFMDEyMgBFZGdl
full / ace-page-group-isolation: .github#9

! Failed to restore: Cache service responded with 400
full / ace-page-group-isolation: .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / ace-page-group-isolation: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / perf-floors: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0IQP0agAAAABqp4F+4oXTQ46Xsx4L3D4KQ0gxQUEyMDMwODE0MDYwAEVkZ2U=
full / perf-floors: .github#9

! Failed to restore: Cache service responded with 400
full / perf-floors: .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / perf-floors: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / visual-test: .github#2

X agents_final_rows_60x40: updated | changed pixels 8667/769500 (1.126316%) | expected=tests/ace/tui/visual/snapshots/png/agents_final_rows_60x40.png
full / visual-test: tests/ace/tui/visual/test_ace_png_snapshots_agents_final_rows.py#86

X Process completed with exit code 1.
full / visual-test: .github#382

! Failed to restore: Cache service responded with 400
full / visual-test: .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / visual-test: .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* master Full CI · 42966182715
Triggered via workflow_dispatch about 58 minutes ago

JOBS
✓ full / prepare in 20s (ID 130343865852)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Validate qualification inputs
  - Download the sealed candidate manifest
  - Bind published identity from the sealed manifest
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
- full / release-core-floor-smoke (ID 130343867306)
- full / docs-build (ID 130343867307)
✓ full / build-core / build-core in 15m34s (ID 130344002788)
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
✓ full / tutorial-tests in 58s (ID 130349372470)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run tutorial tests
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ full / lint in 5m39s (ID 130349372477)
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
✓ full / ace-page-group-isolation in 1m26s (ID 130349372511)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  ✓ Run ACE shared-page isolation lane
  ✓ Post Install visual dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* full / test (3.14) (ID 130349372581)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  - Run tests (coverage leg)
  * Run tests
  * Build shard timings table
  * Upload shard timings
  * Upload coverage
  * Record installed core version
  * Write qualification evidence
  * Upload qualification evidence
  * Post Install dependencies
  * Post Run actions/checkout@v4
* full / test (3.12) (ID 130349372611)
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
✓ full / perf-floors in 8m17s (ID 130349372613)
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
X full / visual-test in 24m46s (ID 130349372627)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  X Check TUI screenshots
  ✓ Locate visual report
  ✓ Build visual report
  ✓ Upload visual report
  ✓ Publish visual report
  - Publish unstable recapture summary
  ✓ Upload first-attempt diffs
  ✓ Upload visual artifacts
  ✓ Post Install visual dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* full / test (3.13) (ID 130349372634)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  - Run tests (coverage leg)
  * Run tests
  * Build shard timings table
  * Upload shard timings
  * Upload coverage
  * Record installed core version
  * Write qualification evidence
  * Upload qualification evidence
  * Post Install dependencies
  * Post Run actions/checkout@v4

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / prepare: .github#6

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / prepare: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / build-core / build-core: .github#4

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0LQH0agAAAACAAn0JAmZMSbGa7VFO+5j/TEFYRURHRTE2MTMARWRnZQ==
full / build-core / build-core: .github#7

! Failed to restore: Cache service responded with 400
full / build-core / build-core: .github#25

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / build-core / build-core: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / tutorial-tests: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0awH0agAAAABsNah2y6NwRrbhGzFSpF1PU0xDMzFFREdFMDEyMgBFZGdl
full / tutorial-tests: .github#9

! Failed to restore: Cache service responded with 400
full / tutorial-tests: .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / tutorial-tests: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / ace-page-group-isolation: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0hgH0agAAAAAZzH9Fqs5+S4bXRr4p6axUUEhMMzBFREdFMDEyMgBFZGdl
full / ace-page-group-isolation: .github#9

! Failed to restore: Cache service responded with 400
full / ace-page-group-isolation: .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / ace-page-group-isolation: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / perf-floors: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0IQP0agAAAABqp4F+4oXTQ46Xsx4L3D4KQ0gxQUEyMDMwODE0MDYwAEVkZ2U=
full / perf-floors: .github#9

! Failed to restore: Cache service responded with 400
full / perf-floors: .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / perf-floors: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / visual-test: .github#2

X agents_final_rows_60x40: updated | changed pixels 8667/769500 (1.126316%) | expected=tests/ace/tui/visual/snapshots/png/agents_final_rows_60x40.png
full / visual-test: tests/ace/tui/visual/test_ace_png_snapshots_agents_final_rows.py#86

X Process completed with exit code 1.
full / visual-test: .github#382

! Failed to restore: Cache service responded with 400
full / visual-test: .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / visual-test: .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* master Full CI · 42966182715
Triggered via workflow_dispatch about 1 hour ago

JOBS
✓ full / prepare in 20s (ID 130343865852)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Validate qualification inputs
  - Download the sealed candidate manifest
  - Bind published identity from the sealed manifest
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
- full / release-core-floor-smoke (ID 130343867306)
- full / docs-build (ID 130343867307)
✓ full / build-core / build-core in 15m34s (ID 130344002788)
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
✓ full / tutorial-tests in 58s (ID 130349372470)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run tutorial tests
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ full / lint in 5m39s (ID 130349372477)
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
✓ full / ace-page-group-isolation in 1m26s (ID 130349372511)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  ✓ Run ACE shared-page isolation lane
  ✓ Post Install visual dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* full / test (3.14) (ID 130349372581)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  - Run tests (coverage leg)
  * Run tests
  * Build shard timings table
  * Upload shard timings
  * Upload coverage
  * Record installed core version
  * Write qualification evidence
  * Upload qualification evidence
  * Post Install dependencies
  * Post Run actions/checkout@v4
* full / test (3.12) (ID 130349372611)
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
✓ full / perf-floors in 8m17s (ID 130349372613)
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
X full / visual-test in 24m46s (ID 130349372627)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  X Check TUI screenshots
  ✓ Locate visual report
  ✓ Build visual report
  ✓ Upload visual report
  ✓ Publish visual report
  - Publish unstable recapture summary
  ✓ Upload first-attempt diffs
  ✓ Upload visual artifacts
  ✓ Post Install visual dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ full / test (3.13) in 43m8s (ID 130349372634)
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

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0LQH0agAAAACAAn0JAmZMSbGa7VFO+5j/TEFYRURHRTE2MTMARWRnZQ==
full / build-core / build-core: .github#7

! Failed to restore: Cache service responded with 400
full / build-core / build-core: .github#25

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / build-core / build-core: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / tutorial-tests: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0awH0agAAAABsNah2y6NwRrbhGzFSpF1PU0xDMzFFREdFMDEyMgBFZGdl
full / tutorial-tests: .github#9

! Failed to restore: Cache service responded with 400
full / tutorial-tests: .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / tutorial-tests: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / ace-page-group-isolation: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0hgH0agAAAAAZzH9Fqs5+S4bXRr4p6axUUEhMMzBFREdFMDEyMgBFZGdl
full / ace-page-group-isolation: .github#9

! Failed to restore: Cache service responded with 400
full / ace-page-group-isolation: .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / ace-page-group-isolation: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / perf-floors: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0IQP0agAAAABqp4F+4oXTQ46Xsx4L3D4KQ0gxQUEyMDMwODE0MDYwAEVkZ2U=
full / perf-floors: .github#9

! Failed to restore: Cache service responded with 400
full / perf-floors: .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / perf-floors: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / visual-test: .github#2

X agents_final_rows_60x40: updated | changed pixels 8667/769500 (1.126316%) | expected=tests/ace/tui/visual/snapshots/png/agents_final_rows_60x40.png
full / visual-test: tests/ace/tui/visual/test_ace_png_snapshots_agents_final_rows.py#86

X Process completed with exit code 1.
full / visual-test: .github#382

! Failed to restore: Cache service responded with 400
full / visual-test: .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / visual-test: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / test (3.13): .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0TAv0agAAAADJ9qFN/KUsQLbsAdvT8e6uQ0gxQUEyMDMwODE0MDYyAEVkZ2U=
full / test (3.13): .github#9

! Failed to restore: Cache service responded with 400
full / test (3.13): .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / test (3.13): .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* master Full CI · 42966182715
Triggered via workflow_dispatch about 1 hour ago

JOBS
✓ full / prepare in 20s (ID 130343865852)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Validate qualification inputs
  - Download the sealed candidate manifest
  - Bind published identity from the sealed manifest
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
- full / release-core-floor-smoke (ID 130343867306)
- full / docs-build (ID 130343867307)
✓ full / build-core / build-core in 15m34s (ID 130344002788)
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
✓ full / tutorial-tests in 58s (ID 130349372470)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run tutorial tests
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ full / lint in 5m39s (ID 130349372477)
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
✓ full / ace-page-group-isolation in 1m26s (ID 130349372511)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  ✓ Run ACE shared-page isolation lane
  ✓ Post Install visual dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* full / test (3.14) (ID 130349372581)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  - Run tests (coverage leg)
  * Run tests
  * Build shard timings table
  * Upload shard timings
  * Upload coverage
  * Record installed core version
  * Write qualification evidence
  * Upload qualification evidence
  * Post Install dependencies
  * Post Run actions/checkout@v4
* full / test (3.12) (ID 130349372611)
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
✓ full / perf-floors in 8m17s (ID 130349372613)
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
X full / visual-test in 24m46s (ID 130349372627)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  X Check TUI screenshots
  ✓ Locate visual report
  ✓ Build visual report
  ✓ Upload visual report
  ✓ Publish visual report
  - Publish unstable recapture summary
  ✓ Upload first-attempt diffs
  ✓ Upload visual artifacts
  ✓ Post Install visual dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ full / test (3.13) in 43m8s (ID 130349372634)
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

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0LQH0agAAAACAAn0JAmZMSbGa7VFO+5j/TEFYRURHRTE2MTMARWRnZQ==
full / build-core / build-core: .github#7

! Failed to restore: Cache service responded with 400
full / build-core / build-core: .github#25

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / build-core / build-core: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / tutorial-tests: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0awH0agAAAABsNah2y6NwRrbhGzFSpF1PU0xDMzFFREdFMDEyMgBFZGdl
full / tutorial-tests: .github#9

! Failed to restore: Cache service responded with 400
full / tutorial-tests: .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / tutorial-tests: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / ace-page-group-isolation: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0hgH0agAAAAAZzH9Fqs5+S4bXRr4p6axUUEhMMzBFREdFMDEyMgBFZGdl
full / ace-page-group-isolation: .github#9

! Failed to restore: Cache service responded with 400
full / ace-page-group-isolation: .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / ace-page-group-isolation: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / perf-floors: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0IQP0agAAAABqp4F+4oXTQ46Xsx4L3D4KQ0gxQUEyMDMwODE0MDYwAEVkZ2U=
full / perf-floors: .github#9

! Failed to restore: Cache service responded with 400
full / perf-floors: .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / perf-floors: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / visual-test: .github#2

X agents_final_rows_60x40: updated | changed pixels 8667/769500 (1.126316%) | expected=tests/ace/tui/visual/snapshots/png/agents_final_rows_60x40.png
full / visual-test: tests/ace/tui/visual/test_ace_png_snapshots_agents_final_rows.py#86

X Process completed with exit code 1.
full / visual-test: .github#382

! Failed to restore: Cache service responded with 400
full / visual-test: .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / visual-test: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / test (3.13): .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0TAv0agAAAADJ9qFN/KUsQLbsAdvT8e6uQ0gxQUEyMDMwODE0MDYyAEVkZ2U=
full / test (3.13): .github#9

! Failed to restore: Cache service responded with 400
full / test (3.13): .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / test (3.13): .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* master Full CI · 42966182715
Triggered via workflow_dispatch about 1 hour ago

JOBS
✓ full / prepare in 20s (ID 130343865852)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Validate qualification inputs
  - Download the sealed candidate manifest
  - Bind published identity from the sealed manifest
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
- full / release-core-floor-smoke (ID 130343867306)
- full / docs-build (ID 130343867307)
✓ full / build-core / build-core in 15m34s (ID 130344002788)
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
✓ full / tutorial-tests in 58s (ID 130349372470)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run tutorial tests
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ full / lint in 5m39s (ID 130349372477)
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
✓ full / ace-page-group-isolation in 1m26s (ID 130349372511)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  ✓ Run ACE shared-page isolation lane
  ✓ Post Install visual dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* full / test (3.14) (ID 130349372581)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  - Run tests (coverage leg)
  * Run tests
  * Build shard timings table
  * Upload shard timings
  * Upload coverage
  * Record installed core version
  * Write qualification evidence
  * Upload qualification evidence
  * Post Install dependencies
  * Post Run actions/checkout@v4
* full / test (3.12) (ID 130349372611)
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
✓ full / perf-floors in 8m17s (ID 130349372613)
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
X full / visual-test in 24m46s (ID 130349372627)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  X Check TUI screenshots
  ✓ Locate visual report
  ✓ Build visual report
  ✓ Upload visual report
  ✓ Publish visual report
  - Publish unstable recapture summary
  ✓ Upload first-attempt diffs
  ✓ Upload visual artifacts
  ✓ Post Install visual dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ full / test (3.13) in 43m8s (ID 130349372634)
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

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0LQH0agAAAACAAn0JAmZMSbGa7VFO+5j/TEFYRURHRTE2MTMARWRnZQ==
full / build-core / build-core: .github#7

! Failed to restore: Cache service responded with 400
full / build-core / build-core: .github#25

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / build-core / build-core: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / tutorial-tests: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0awH0agAAAABsNah2y6NwRrbhGzFSpF1PU0xDMzFFREdFMDEyMgBFZGdl
full / tutorial-tests: .github#9

! Failed to restore: Cache service responded with 400
full / tutorial-tests: .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / tutorial-tests: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / ace-page-group-isolation: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0hgH0agAAAAAZzH9Fqs5+S4bXRr4p6axUUEhMMzBFREdFMDEyMgBFZGdl
full / ace-page-group-isolation: .github#9

! Failed to restore: Cache service responded with 400
full / ace-page-group-isolation: .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / ace-page-group-isolation: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / perf-floors: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0IQP0agAAAABqp4F+4oXTQ46Xsx4L3D4KQ0gxQUEyMDMwODE0MDYwAEVkZ2U=
full / perf-floors: .github#9

! Failed to restore: Cache service responded with 400
full / perf-floors: .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / perf-floors: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / visual-test: .github#2

X agents_final_rows_60x40: updated | changed pixels 8667/769500 (1.126316%) | expected=tests/ace/tui/visual/snapshots/png/agents_final_rows_60x40.png
full / visual-test: tests/ace/tui/visual/test_ace_png_snapshots_agents_final_rows.py#86

X Process completed with exit code 1.
full / visual-test: .github#382

! Failed to restore: Cache service responded with 400
full / visual-test: .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / visual-test: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / test (3.13): .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0TAv0agAAAADJ9qFN/KUsQLbsAdvT8e6uQ0gxQUEyMDMwODE0MDYyAEVkZ2U=
full / test (3.13): .github#9

! Failed to restore: Cache service responded with 400
full / test (3.13): .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / test (3.13): .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* master Full CI · 42966182715
Triggered via workflow_dispatch about 1 hour ago

JOBS
✓ full / prepare in 20s (ID 130343865852)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Validate qualification inputs
  - Download the sealed candidate manifest
  - Bind published identity from the sealed manifest
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
- full / release-core-floor-smoke (ID 130343867306)
- full / docs-build (ID 130343867307)
✓ full / build-core / build-core in 15m34s (ID 130344002788)
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
✓ full / tutorial-tests in 58s (ID 130349372470)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run tutorial tests
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ full / lint in 5m39s (ID 130349372477)
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
✓ full / ace-page-group-isolation in 1m26s (ID 130349372511)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  ✓ Run ACE shared-page isolation lane
  ✓ Post Install visual dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* full / test (3.14) (ID 130349372581)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  - Run tests (coverage leg)
  * Run tests
  * Build shard timings table
  * Upload shard timings
  * Upload coverage
  * Record installed core version
  * Write qualification evidence
  * Upload qualification evidence
  * Post Install dependencies
  * Post Run actions/checkout@v4
* full / test (3.12) (ID 130349372611)
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
✓ full / perf-floors in 8m17s (ID 130349372613)
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
X full / visual-test in 24m46s (ID 130349372627)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  X Check TUI screenshots
  ✓ Locate visual report
  ✓ Build visual report
  ✓ Upload visual report
  ✓ Publish visual report
  - Publish unstable recapture summary
  ✓ Upload first-attempt diffs
  ✓ Upload visual artifacts
  ✓ Post Install visual dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ full / test (3.13) in 43m8s (ID 130349372634)
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

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0LQH0agAAAACAAn0JAmZMSbGa7VFO+5j/TEFYRURHRTE2MTMARWRnZQ==
full / build-core / build-core: .github#7

! Failed to restore: Cache service responded with 400
full / build-core / build-core: .github#25

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / build-core / build-core: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / tutorial-tests: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0awH0agAAAABsNah2y6NwRrbhGzFSpF1PU0xDMzFFREdFMDEyMgBFZGdl
full / tutorial-tests: .github#9

! Failed to restore: Cache service responded with 400
full / tutorial-tests: .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / tutorial-tests: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / ace-page-group-isolation: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0hgH0agAAAAAZzH9Fqs5+S4bXRr4p6axUUEhMMzBFREdFMDEyMgBFZGdl
full / ace-page-group-isolation: .github#9

! Failed to restore: Cache service responded with 400
full / ace-page-group-isolation: .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / ace-page-group-isolation: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / perf-floors: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0IQP0agAAAABqp4F+4oXTQ46Xsx4L3D4KQ0gxQUEyMDMwODE0MDYwAEVkZ2U=
full / perf-floors: .github#9

! Failed to restore: Cache service responded with 400
full / perf-floors: .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / perf-floors: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / visual-test: .github#2

X agents_final_rows_60x40: updated | changed pixels 8667/769500 (1.126316%) | expected=tests/ace/tui/visual/snapshots/png/agents_final_rows_60x40.png
full / visual-test: tests/ace/tui/visual/test_ace_png_snapshots_agents_final_rows.py#86

X Process completed with exit code 1.
full / visual-test: .github#382

! Failed to restore: Cache service responded with 400
full / visual-test: .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / visual-test: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / test (3.13): .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0TAv0agAAAADJ9qFN/KUsQLbsAdvT8e6uQ0gxQUEyMDMwODE0MDYyAEVkZ2U=
full / test (3.13): .github#9

! Failed to restore: Cache service responded with 400
full / test (3.13): .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / test (3.13): .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* master Full CI · 42966182715
Triggered via workflow_dispatch about 1 hour ago

JOBS
✓ full / prepare in 20s (ID 130343865852)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Validate qualification inputs
  - Download the sealed candidate manifest
  - Bind published identity from the sealed manifest
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
- full / release-core-floor-smoke (ID 130343867306)
- full / docs-build (ID 130343867307)
✓ full / build-core / build-core in 15m34s (ID 130344002788)
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
✓ full / tutorial-tests in 58s (ID 130349372470)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run tutorial tests
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ full / lint in 5m39s (ID 130349372477)
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
✓ full / ace-page-group-isolation in 1m26s (ID 130349372511)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  ✓ Run ACE shared-page isolation lane
  ✓ Post Install visual dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* full / test (3.14) (ID 130349372581)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  - Run tests (coverage leg)
  * Run tests
  * Build shard timings table
  * Upload shard timings
  * Upload coverage
  * Record installed core version
  * Write qualification evidence
  * Upload qualification evidence
  * Post Install dependencies
  * Post Run actions/checkout@v4
* full / test (3.12) (ID 130349372611)
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
✓ full / perf-floors in 8m17s (ID 130349372613)
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
X full / visual-test in 24m46s (ID 130349372627)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  X Check TUI screenshots
  ✓ Locate visual report
  ✓ Build visual report
  ✓ Upload visual report
  ✓ Publish visual report
  - Publish unstable recapture summary
  ✓ Upload first-attempt diffs
  ✓ Upload visual artifacts
  ✓ Post Install visual dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ full / test (3.13) in 43m8s (ID 130349372634)
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

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0LQH0agAAAACAAn0JAmZMSbGa7VFO+5j/TEFYRURHRTE2MTMARWRnZQ==
full / build-core / build-core: .github#7

! Failed to restore: Cache service responded with 400
full / build-core / build-core: .github#25

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / build-core / build-core: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / tutorial-tests: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0awH0agAAAABsNah2y6NwRrbhGzFSpF1PU0xDMzFFREdFMDEyMgBFZGdl
full / tutorial-tests: .github#9

! Failed to restore: Cache service responded with 400
full / tutorial-tests: .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / tutorial-tests: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / ace-page-group-isolation: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0hgH0agAAAAAZzH9Fqs5+S4bXRr4p6axUUEhMMzBFREdFMDEyMgBFZGdl
full / ace-page-group-isolation: .github#9

! Failed to restore: Cache service responded with 400
full / ace-page-group-isolation: .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / ace-page-group-isolation: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / perf-floors: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0IQP0agAAAABqp4F+4oXTQ46Xsx4L3D4KQ0gxQUEyMDMwODE0MDYwAEVkZ2U=
full / perf-floors: .github#9

! Failed to restore: Cache service responded with 400
full / perf-floors: .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / perf-floors: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / visual-test: .github#2

X agents_final_rows_60x40: updated | changed pixels 8667/769500 (1.126316%) | expected=tests/ace/tui/visual/snapshots/png/agents_final_rows_60x40.png
full / visual-test: tests/ace/tui/visual/test_ace_png_snapshots_agents_final_rows.py#86

X Process completed with exit code 1.
full / visual-test: .github#382

! Failed to restore: Cache service responded with 400
full / visual-test: .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / visual-test: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / test (3.13): .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0TAv0agAAAADJ9qFN/KUsQLbsAdvT8e6uQ0gxQUEyMDMwODE0MDYyAEVkZ2U=
full / test (3.13): .github#9

! Failed to restore: Cache service responded with 400
full / test (3.13): .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / test (3.13): .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* master Full CI · 42966182715
Triggered via workflow_dispatch about 1 hour ago

JOBS
✓ full / prepare in 20s (ID 130343865852)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Validate qualification inputs
  - Download the sealed candidate manifest
  - Bind published identity from the sealed manifest
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
- full / release-core-floor-smoke (ID 130343867306)
- full / docs-build (ID 130343867307)
✓ full / build-core / build-core in 15m34s (ID 130344002788)
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
✓ full / tutorial-tests in 58s (ID 130349372470)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run tutorial tests
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ full / lint in 5m39s (ID 130349372477)
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
✓ full / ace-page-group-isolation in 1m26s (ID 130349372511)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  ✓ Run ACE shared-page isolation lane
  ✓ Post Install visual dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* full / test (3.14) (ID 130349372581)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  - Run tests (coverage leg)
  * Run tests
  * Build shard timings table
  * Upload shard timings
  * Upload coverage
  * Record installed core version
  * Write qualification evidence
  * Upload qualification evidence
  * Post Install dependencies
  * Post Run actions/checkout@v4
* full / test (3.12) (ID 130349372611)
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
✓ full / perf-floors in 8m17s (ID 130349372613)
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
X full / visual-test in 24m46s (ID 130349372627)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  X Check TUI screenshots
  ✓ Locate visual report
  ✓ Build visual report
  ✓ Upload visual report
  ✓ Publish visual report
  - Publish unstable recapture summary
  ✓ Upload first-attempt diffs
  ✓ Upload visual artifacts
  ✓ Post Install visual dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ full / test (3.13) in 43m8s (ID 130349372634)
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

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0LQH0agAAAACAAn0JAmZMSbGa7VFO+5j/TEFYRURHRTE2MTMARWRnZQ==
full / build-core / build-core: .github#7

! Failed to restore: Cache service responded with 400
full / build-core / build-core: .github#25

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / build-core / build-core: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / tutorial-tests: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0awH0agAAAABsNah2y6NwRrbhGzFSpF1PU0xDMzFFREdFMDEyMgBFZGdl
full / tutorial-tests: .github#9

! Failed to restore: Cache service responded with 400
full / tutorial-tests: .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / tutorial-tests: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / ace-page-group-isolation: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0hgH0agAAAAAZzH9Fqs5+S4bXRr4p6axUUEhMMzBFREdFMDEyMgBFZGdl
full / ace-page-group-isolation: .github#9

! Failed to restore: Cache service responded with 400
full / ace-page-group-isolation: .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / ace-page-group-isolation: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / perf-floors: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0IQP0agAAAABqp4F+4oXTQ46Xsx4L3D4KQ0gxQUEyMDMwODE0MDYwAEVkZ2U=
full / perf-floors: .github#9

! Failed to restore: Cache service responded with 400
full / perf-floors: .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / perf-floors: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / visual-test: .github#2

X agents_final_rows_60x40: updated | changed pixels 8667/769500 (1.126316%) | expected=tests/ace/tui/visual/snapshots/png/agents_final_rows_60x40.png
full / visual-test: tests/ace/tui/visual/test_ace_png_snapshots_agents_final_rows.py#86

X Process completed with exit code 1.
full / visual-test: .github#382

! Failed to restore: Cache service responded with 400
full / visual-test: .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / visual-test: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / test (3.13): .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0TAv0agAAAADJ9qFN/KUsQLbsAdvT8e6uQ0gxQUEyMDMwODE0MDYyAEVkZ2U=
full / test (3.13): .github#9

! Failed to restore: Cache service responded with 400
full / test (3.13): .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / test (3.13): .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* master Full CI · 42966182715
Triggered via workflow_dispatch about 1 hour ago

JOBS
✓ full / prepare in 20s (ID 130343865852)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Validate qualification inputs
  - Download the sealed candidate manifest
  - Bind published identity from the sealed manifest
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
- full / release-core-floor-smoke (ID 130343867306)
- full / docs-build (ID 130343867307)
✓ full / build-core / build-core in 15m34s (ID 130344002788)
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
✓ full / tutorial-tests in 58s (ID 130349372470)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run tutorial tests
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ full / lint in 5m39s (ID 130349372477)
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
✓ full / ace-page-group-isolation in 1m26s (ID 130349372511)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  ✓ Run ACE shared-page isolation lane
  ✓ Post Install visual dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* full / test (3.14) (ID 130349372581)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  - Run tests (coverage leg)
  * Run tests
  * Build shard timings table
  * Upload shard timings
  * Upload coverage
  * Record installed core version
  * Write qualification evidence
  * Upload qualification evidence
  * Post Install dependencies
  * Post Run actions/checkout@v4
* full / test (3.12) (ID 130349372611)
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
✓ full / perf-floors in 8m17s (ID 130349372613)
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
X full / visual-test in 24m46s (ID 130349372627)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  X Check TUI screenshots
  ✓ Locate visual report
  ✓ Build visual report
  ✓ Upload visual report
  ✓ Publish visual report
  - Publish unstable recapture summary
  ✓ Upload first-attempt diffs
  ✓ Upload visual artifacts
  ✓ Post Install visual dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ full / test (3.13) in 43m8s (ID 130349372634)
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

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0LQH0agAAAACAAn0JAmZMSbGa7VFO+5j/TEFYRURHRTE2MTMARWRnZQ==
full / build-core / build-core: .github#7

! Failed to restore: Cache service responded with 400
full / build-core / build-core: .github#25

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / build-core / build-core: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / tutorial-tests: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0awH0agAAAABsNah2y6NwRrbhGzFSpF1PU0xDMzFFREdFMDEyMgBFZGdl
full / tutorial-tests: .github#9

! Failed to restore: Cache service responded with 400
full / tutorial-tests: .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / tutorial-tests: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / ace-page-group-isolation: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0hgH0agAAAAAZzH9Fqs5+S4bXRr4p6axUUEhMMzBFREdFMDEyMgBFZGdl
full / ace-page-group-isolation: .github#9

! Failed to restore: Cache service responded with 400
full / ace-page-group-isolation: .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / ace-page-group-isolation: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / perf-floors: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0IQP0agAAAABqp4F+4oXTQ46Xsx4L3D4KQ0gxQUEyMDMwODE0MDYwAEVkZ2U=
full / perf-floors: .github#9

! Failed to restore: Cache service responded with 400
full / perf-floors: .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / perf-floors: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / visual-test: .github#2

X agents_final_rows_60x40: updated | changed pixels 8667/769500 (1.126316%) | expected=tests/ace/tui/visual/snapshots/png/agents_final_rows_60x40.png
full / visual-test: tests/ace/tui/visual/test_ace_png_snapshots_agents_final_rows.py#86

X Process completed with exit code 1.
full / visual-test: .github#382

! Failed to restore: Cache service responded with 400
full / visual-test: .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / visual-test: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / test (3.13): .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0TAv0agAAAADJ9qFN/KUsQLbsAdvT8e6uQ0gxQUEyMDMwODE0MDYyAEVkZ2U=
full / test (3.13): .github#9

! Failed to restore: Cache service responded with 400
full / test (3.13): .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / test (3.13): .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* master Full CI · 42966182715
Triggered via workflow_dispatch about 1 hour ago

JOBS
✓ full / prepare in 20s (ID 130343865852)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Validate qualification inputs
  - Download the sealed candidate manifest
  - Bind published identity from the sealed manifest
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
- full / release-core-floor-smoke (ID 130343867306)
- full / docs-build (ID 130343867307)
✓ full / build-core / build-core in 15m34s (ID 130344002788)
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
✓ full / tutorial-tests in 58s (ID 130349372470)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run tutorial tests
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ full / lint in 5m39s (ID 130349372477)
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
✓ full / ace-page-group-isolation in 1m26s (ID 130349372511)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  ✓ Run ACE shared-page isolation lane
  ✓ Post Install visual dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* full / test (3.14) (ID 130349372581)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  - Run tests (coverage leg)
  * Run tests
  * Build shard timings table
  * Upload shard timings
  * Upload coverage
  * Record installed core version
  * Write qualification evidence
  * Upload qualification evidence
  * Post Install dependencies
  * Post Run actions/checkout@v4
* full / test (3.12) (ID 130349372611)
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
✓ full / perf-floors in 8m17s (ID 130349372613)
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
X full / visual-test in 24m46s (ID 130349372627)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  X Check TUI screenshots
  ✓ Locate visual report
  ✓ Build visual report
  ✓ Upload visual report
  ✓ Publish visual report
  - Publish unstable recapture summary
  ✓ Upload first-attempt diffs
  ✓ Upload visual artifacts
  ✓ Post Install visual dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ full / test (3.13) in 43m8s (ID 130349372634)
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

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0LQH0agAAAACAAn0JAmZMSbGa7VFO+5j/TEFYRURHRTE2MTMARWRnZQ==
full / build-core / build-core: .github#7

! Failed to restore: Cache service responded with 400
full / build-core / build-core: .github#25

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / build-core / build-core: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / tutorial-tests: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0awH0agAAAABsNah2y6NwRrbhGzFSpF1PU0xDMzFFREdFMDEyMgBFZGdl
full / tutorial-tests: .github#9

! Failed to restore: Cache service responded with 400
full / tutorial-tests: .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / tutorial-tests: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / ace-page-group-isolation: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0hgH0agAAAAAZzH9Fqs5+S4bXRr4p6axUUEhMMzBFREdFMDEyMgBFZGdl
full / ace-page-group-isolation: .github#9

! Failed to restore: Cache service responded with 400
full / ace-page-group-isolation: .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / ace-page-group-isolation: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / perf-floors: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0IQP0agAAAABqp4F+4oXTQ46Xsx4L3D4KQ0gxQUEyMDMwODE0MDYwAEVkZ2U=
full / perf-floors: .github#9

! Failed to restore: Cache service responded with 400
full / perf-floors: .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / perf-floors: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / visual-test: .github#2

X agents_final_rows_60x40: updated | changed pixels 8667/769500 (1.126316%) | expected=tests/ace/tui/visual/snapshots/png/agents_final_rows_60x40.png
full / visual-test: tests/ace/tui/visual/test_ace_png_snapshots_agents_final_rows.py#86

X Process completed with exit code 1.
full / visual-test: .github#382

! Failed to restore: Cache service responded with 400
full / visual-test: .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / visual-test: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / test (3.13): .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0TAv0agAAAADJ9qFN/KUsQLbsAdvT8e6uQ0gxQUEyMDMwODE0MDYyAEVkZ2U=
full / test (3.13): .github#9

! Failed to restore: Cache service responded with 400
full / test (3.13): .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / test (3.13): .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* master Full CI · 42966182715
Triggered via workflow_dispatch about 1 hour ago

JOBS
✓ full / prepare in 20s (ID 130343865852)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Validate qualification inputs
  - Download the sealed candidate manifest
  - Bind published identity from the sealed manifest
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
- full / release-core-floor-smoke (ID 130343867306)
- full / docs-build (ID 130343867307)
✓ full / build-core / build-core in 15m34s (ID 130344002788)
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
✓ full / tutorial-tests in 58s (ID 130349372470)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run tutorial tests
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ full / lint in 5m39s (ID 130349372477)
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
✓ full / ace-page-group-isolation in 1m26s (ID 130349372511)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  ✓ Run ACE shared-page isolation lane
  ✓ Post Install visual dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* full / test (3.14) (ID 130349372581)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  - Run tests (coverage leg)
  * Run tests
  * Build shard timings table
  * Upload shard timings
  * Upload coverage
  * Record installed core version
  * Write qualification evidence
  * Upload qualification evidence
  * Post Install dependencies
  * Post Run actions/checkout@v4
* full / test (3.12) (ID 130349372611)
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
✓ full / perf-floors in 8m17s (ID 130349372613)
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
X full / visual-test in 24m46s (ID 130349372627)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  X Check TUI screenshots
  ✓ Locate visual report
  ✓ Build visual report
  ✓ Upload visual report
  ✓ Publish visual report
  - Publish unstable recapture summary
  ✓ Upload first-attempt diffs
  ✓ Upload visual artifacts
  ✓ Post Install visual dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ full / test (3.13) in 43m8s (ID 130349372634)
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

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0LQH0agAAAACAAn0JAmZMSbGa7VFO+5j/TEFYRURHRTE2MTMARWRnZQ==
full / build-core / build-core: .github#7

! Failed to restore: Cache service responded with 400
full / build-core / build-core: .github#25

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / build-core / build-core: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / tutorial-tests: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0awH0agAAAABsNah2y6NwRrbhGzFSpF1PU0xDMzFFREdFMDEyMgBFZGdl
full / tutorial-tests: .github#9

! Failed to restore: Cache service responded with 400
full / tutorial-tests: .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / tutorial-tests: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / ace-page-group-isolation: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0hgH0agAAAAAZzH9Fqs5+S4bXRr4p6axUUEhMMzBFREdFMDEyMgBFZGdl
full / ace-page-group-isolation: .github#9

! Failed to restore: Cache service responded with 400
full / ace-page-group-isolation: .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / ace-page-group-isolation: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / perf-floors: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0IQP0agAAAABqp4F+4oXTQ46Xsx4L3D4KQ0gxQUEyMDMwODE0MDYwAEVkZ2U=
full / perf-floors: .github#9

! Failed to restore: Cache service responded with 400
full / perf-floors: .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / perf-floors: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / visual-test: .github#2

X agents_final_rows_60x40: updated | changed pixels 8667/769500 (1.126316%) | expected=tests/ace/tui/visual/snapshots/png/agents_final_rows_60x40.png
full / visual-test: tests/ace/tui/visual/test_ace_png_snapshots_agents_final_rows.py#86

X Process completed with exit code 1.
full / visual-test: .github#382

! Failed to restore: Cache service responded with 400
full / visual-test: .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / visual-test: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / test (3.13): .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0TAv0agAAAADJ9qFN/KUsQLbsAdvT8e6uQ0gxQUEyMDMwODE0MDYyAEVkZ2U=
full / test (3.13): .github#9

! Failed to restore: Cache service responded with 400
full / test (3.13): .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / test (3.13): .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* master Full CI · 42966182715
Triggered via workflow_dispatch about 1 hour ago

JOBS
✓ full / prepare in 20s (ID 130343865852)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Validate qualification inputs
  - Download the sealed candidate manifest
  - Bind published identity from the sealed manifest
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
- full / release-core-floor-smoke (ID 130343867306)
- full / docs-build (ID 130343867307)
✓ full / build-core / build-core in 15m34s (ID 130344002788)
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
✓ full / tutorial-tests in 58s (ID 130349372470)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run tutorial tests
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ full / lint in 5m39s (ID 130349372477)
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
✓ full / ace-page-group-isolation in 1m26s (ID 130349372511)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  ✓ Run ACE shared-page isolation lane
  ✓ Post Install visual dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* full / test (3.14) (ID 130349372581)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  - Run tests (coverage leg)
  * Run tests
  * Build shard timings table
  * Upload shard timings
  * Upload coverage
  * Record installed core version
  * Write qualification evidence
  * Upload qualification evidence
  * Post Install dependencies
  * Post Run actions/checkout@v4
* full / test (3.12) (ID 130349372611)
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
✓ full / perf-floors in 8m17s (ID 130349372613)
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
X full / visual-test in 24m46s (ID 130349372627)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  X Check TUI screenshots
  ✓ Locate visual report
  ✓ Build visual report
  ✓ Upload visual report
  ✓ Publish visual report
  - Publish unstable recapture summary
  ✓ Upload first-attempt diffs
  ✓ Upload visual artifacts
  ✓ Post Install visual dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ full / test (3.13) in 43m8s (ID 130349372634)
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

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0LQH0agAAAACAAn0JAmZMSbGa7VFO+5j/TEFYRURHRTE2MTMARWRnZQ==
full / build-core / build-core: .github#7

! Failed to restore: Cache service responded with 400
full / build-core / build-core: .github#25

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / build-core / build-core: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / tutorial-tests: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0awH0agAAAABsNah2y6NwRrbhGzFSpF1PU0xDMzFFREdFMDEyMgBFZGdl
full / tutorial-tests: .github#9

! Failed to restore: Cache service responded with 400
full / tutorial-tests: .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / tutorial-tests: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / ace-page-group-isolation: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0hgH0agAAAAAZzH9Fqs5+S4bXRr4p6axUUEhMMzBFREdFMDEyMgBFZGdl
full / ace-page-group-isolation: .github#9

! Failed to restore: Cache service responded with 400
full / ace-page-group-isolation: .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / ace-page-group-isolation: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / perf-floors: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0IQP0agAAAABqp4F+4oXTQ46Xsx4L3D4KQ0gxQUEyMDMwODE0MDYwAEVkZ2U=
full / perf-floors: .github#9

! Failed to restore: Cache service responded with 400
full / perf-floors: .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / perf-floors: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / visual-test: .github#2

X agents_final_rows_60x40: updated | changed pixels 8667/769500 (1.126316%) | expected=tests/ace/tui/visual/snapshots/png/agents_final_rows_60x40.png
full / visual-test: tests/ace/tui/visual/test_ace_png_snapshots_agents_final_rows.py#86

X Process completed with exit code 1.
full / visual-test: .github#382

! Failed to restore: Cache service responded with 400
full / visual-test: .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / visual-test: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / test (3.13): .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0TAv0agAAAADJ9qFN/KUsQLbsAdvT8e6uQ0gxQUEyMDMwODE0MDYyAEVkZ2U=
full / test (3.13): .github#9

! Failed to restore: Cache service responded with 400
full / test (3.13): .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / test (3.13): .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* master Full CI · 42966182715
Triggered via workflow_dispatch about 1 hour ago

JOBS
✓ full / prepare in 20s (ID 130343865852)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Validate qualification inputs
  - Download the sealed candidate manifest
  - Bind published identity from the sealed manifest
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
- full / release-core-floor-smoke (ID 130343867306)
- full / docs-build (ID 130343867307)
✓ full / build-core / build-core in 15m34s (ID 130344002788)
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
✓ full / tutorial-tests in 58s (ID 130349372470)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run tutorial tests
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ full / lint in 5m39s (ID 130349372477)
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
✓ full / ace-page-group-isolation in 1m26s (ID 130349372511)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  ✓ Run ACE shared-page isolation lane
  ✓ Post Install visual dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* full / test (3.14) (ID 130349372581)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  - Run tests (coverage leg)
  * Run tests
  * Build shard timings table
  * Upload shard timings
  * Upload coverage
  * Record installed core version
  * Write qualification evidence
  * Upload qualification evidence
  * Post Install dependencies
  * Post Run actions/checkout@v4
✓ full / test (3.12) in 1h3m47s (ID 130349372611)
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
✓ full / perf-floors in 8m17s (ID 130349372613)
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
X full / visual-test in 24m46s (ID 130349372627)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  X Check TUI screenshots
  ✓ Locate visual report
  ✓ Build visual report
  ✓ Upload visual report
  ✓ Publish visual report
  - Publish unstable recapture summary
  ✓ Upload first-attempt diffs
  ✓ Upload visual artifacts
  ✓ Post Install visual dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ full / test (3.13) in 43m8s (ID 130349372634)
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

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0LQH0agAAAACAAn0JAmZMSbGa7VFO+5j/TEFYRURHRTE2MTMARWRnZQ==
full / build-core / build-core: .github#7

! Failed to restore: Cache service responded with 400
full / build-core / build-core: .github#25

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / build-core / build-core: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / tutorial-tests: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0awH0agAAAABsNah2y6NwRrbhGzFSpF1PU0xDMzFFREdFMDEyMgBFZGdl
full / tutorial-tests: .github#9

! Failed to restore: Cache service responded with 400
full / tutorial-tests: .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / tutorial-tests: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / ace-page-group-isolation: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0hgH0agAAAAAZzH9Fqs5+S4bXRr4p6axUUEhMMzBFREdFMDEyMgBFZGdl
full / ace-page-group-isolation: .github#9

! Failed to restore: Cache service responded with 400
full / ace-page-group-isolation: .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / ace-page-group-isolation: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / perf-floors: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0IQP0agAAAABqp4F+4oXTQ46Xsx4L3D4KQ0gxQUEyMDMwODE0MDYwAEVkZ2U=
full / perf-floors: .github#9

! Failed to restore: Cache service responded with 400
full / perf-floors: .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / perf-floors: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / visual-test: .github#2

X agents_final_rows_60x40: updated | changed pixels 8667/769500 (1.126316%) | expected=tests/ace/tui/visual/snapshots/png/agents_final_rows_60x40.png
full / visual-test: tests/ace/tui/visual/test_ace_png_snapshots_agents_final_rows.py#86

X Process completed with exit code 1.
full / visual-test: .github#382

! Failed to restore: Cache service responded with 400
full / visual-test: .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / visual-test: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / test (3.13): .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0TAv0agAAAADJ9qFN/KUsQLbsAdvT8e6uQ0gxQUEyMDMwODE0MDYyAEVkZ2U=
full / test (3.13): .github#9

! Failed to restore: Cache service responded with 400
full / test (3.13): .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / test (3.13): .github#1

X master Full CI · 42966182715
Triggered via workflow_dispatch about 1 hour ago

JOBS
✓ full / prepare in 20s (ID 130343865852)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Validate qualification inputs
  - Download the sealed candidate manifest
  - Bind published identity from the sealed manifest
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
- full / release-core-floor-smoke (ID 130343867306)
- full / docs-build (ID 130343867307)
✓ full / build-core / build-core in 15m34s (ID 130344002788)
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
✓ full / tutorial-tests in 58s (ID 130349372470)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run tutorial tests
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ full / lint in 5m39s (ID 130349372477)
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
✓ full / ace-page-group-isolation in 1m26s (ID 130349372511)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  ✓ Run ACE shared-page isolation lane
  ✓ Post Install visual dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ full / test (3.14) in 1h6m6s (ID 130349372581)
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
✓ full / test (3.12) in 1h3m47s (ID 130349372611)
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
✓ full / perf-floors in 8m17s (ID 130349372613)
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
X full / visual-test in 24m46s (ID 130349372627)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  X Check TUI screenshots
  ✓ Locate visual report
  ✓ Build visual report
  ✓ Upload visual report
  ✓ Publish visual report
  - Publish unstable recapture summary
  ✓ Upload first-attempt diffs
  ✓ Upload visual artifacts
  ✓ Post Install visual dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ full / test (3.13) in 43m8s (ID 130349372634)
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

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0LQH0agAAAACAAn0JAmZMSbGa7VFO+5j/TEFYRURHRTE2MTMARWRnZQ==
full / build-core / build-core: .github#7

! Failed to restore: Cache service responded with 400
full / build-core / build-core: .github#25

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / build-core / build-core: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / tutorial-tests: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0awH0agAAAABsNah2y6NwRrbhGzFSpF1PU0xDMzFFREdFMDEyMgBFZGdl
full / tutorial-tests: .github#9

! Failed to restore: Cache service responded with 400
full / tutorial-tests: .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / tutorial-tests: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / ace-page-group-isolation: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0hgH0agAAAAAZzH9Fqs5+S4bXRr4p6axUUEhMMzBFREdFMDEyMgBFZGdl
full / ace-page-group-isolation: .github#9

! Failed to restore: Cache service responded with 400
full / ace-page-group-isolation: .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / ace-page-group-isolation: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / perf-floors: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0IQP0agAAAABqp4F+4oXTQ46Xsx4L3D4KQ0gxQUEyMDMwODE0MDYwAEVkZ2U=
full / perf-floors: .github#9

! Failed to restore: Cache service responded with 400
full / perf-floors: .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / perf-floors: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / visual-test: .github#2

X agents_final_rows_60x40: updated | changed pixels 8667/769500 (1.126316%) | expected=tests/ace/tui/visual/snapshots/png/agents_final_rows_60x40.png
full / visual-test: tests/ace/tui/visual/test_ace_png_snapshots_agents_final_rows.py#86

X Process completed with exit code 1.
full / visual-test: .github#382

! Failed to restore: Cache service responded with 400
full / visual-test: .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / visual-test: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / test (3.13): .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0TAv0agAAAADJ9qFN/KUsQLbsAdvT8e6uQ0gxQUEyMDMwODE0MDYyAEVkZ2U=
full / test (3.13): .github#9

! Failed to restore: Cache service responded with 400
full / test (3.13): .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / test (3.13): .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* master CI Telemetry · 42966178009
Triggered via workflow_dispatch about 1 hour ago

JOBS
✓ build-core / build-core in 12m52s (ID 130343836973)
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
* contention-test (ID 130348282095)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  * Run default-lane contention harness
  * Upload contention failure records
  * Post Install visual dependencies
  * Post Run actions/checkout@v4
* coverage-contexts (ID 130348282153)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Record per-test coverage contexts
  * Upload coverage contexts database
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test-cost (ID 130348282178)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run cost-attribution suite
  * Upload global leak report
  * Post Install dependencies
  * Post Run actions/checkout@v4

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
build-core / build-core: .github#4

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0cAD0agAAAAA2LsPqUGJhSaMNaFixwAo0UEhMMzBFREdFMDQxNgBFZGdl
build-core / build-core: .github#7

! Failed to restore: Cache service responded with 400
build-core / build-core: .github#25

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
build-core / build-core: .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* master CI Telemetry · 42966178009
Triggered via workflow_dispatch about 1 hour ago

JOBS
✓ build-core / build-core in 12m52s (ID 130343836973)
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
* contention-test (ID 130348282095)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  * Run default-lane contention harness
  * Upload contention failure records
  * Post Install visual dependencies
  * Post Run actions/checkout@v4
* coverage-contexts (ID 130348282153)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Record per-test coverage contexts
  * Upload coverage contexts database
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test-cost (ID 130348282178)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run cost-attribution suite
  * Upload global leak report
  * Post Install dependencies
  * Post Run actions/checkout@v4

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
build-core / build-core: .github#4

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0cAD0agAAAAA2LsPqUGJhSaMNaFixwAo0UEhMMzBFREdFMDQxNgBFZGdl
build-core / build-core: .github#7

! Failed to restore: Cache service responded with 400
build-core / build-core: .github#25

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
build-core / build-core: .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* master CI Telemetry · 42966178009
Triggered via workflow_dispatch about 1 hour ago

JOBS
✓ build-core / build-core in 12m52s (ID 130343836973)
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
* contention-test (ID 130348282095)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  * Run default-lane contention harness
  * Upload contention failure records
  * Post Install visual dependencies
  * Post Run actions/checkout@v4
* coverage-contexts (ID 130348282153)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Record per-test coverage contexts
  * Upload coverage contexts database
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test-cost (ID 130348282178)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run cost-attribution suite
  * Upload global leak report
  * Post Install dependencies
  * Post Run actions/checkout@v4

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
build-core / build-core: .github#4

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0cAD0agAAAAA2LsPqUGJhSaMNaFixwAo0UEhMMzBFREdFMDQxNgBFZGdl
build-core / build-core: .github#7

! Failed to restore: Cache service responded with 400
build-core / build-core: .github#25

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
build-core / build-core: .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* master CI Telemetry · 42966178009
Triggered via workflow_dispatch about 1 hour ago

JOBS
✓ build-core / build-core in 12m52s (ID 130343836973)
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
* contention-test (ID 130348282095)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  * Run default-lane contention harness
  * Upload contention failure records
  * Post Install visual dependencies
  * Post Run actions/checkout@v4
* coverage-contexts (ID 130348282153)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Record per-test coverage contexts
  * Upload coverage contexts database
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test-cost (ID 130348282178)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run cost-attribution suite
  * Upload global leak report
  * Post Install dependencies
  * Post Run actions/checkout@v4

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
build-core / build-core: .github#4

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0cAD0agAAAAA2LsPqUGJhSaMNaFixwAo0UEhMMzBFREdFMDQxNgBFZGdl
build-core / build-core: .github#7

! Failed to restore: Cache service responded with 400
build-core / build-core: .github#25

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
build-core / build-core: .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* master CI Telemetry · 42966178009
Triggered via workflow_dispatch about 1 hour ago

JOBS
✓ build-core / build-core in 12m52s (ID 130343836973)
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
* contention-test (ID 130348282095)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  * Run default-lane contention harness
  * Upload contention failure records
  * Post Install visual dependencies
  * Post Run actions/checkout@v4
* coverage-contexts (ID 130348282153)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Record per-test coverage contexts
  * Upload coverage contexts database
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test-cost (ID 130348282178)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run cost-attribution suite
  * Upload global leak report
  * Post Install dependencies
  * Post Run actions/checkout@v4

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
build-core / build-core: .github#4

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0cAD0agAAAAA2LsPqUGJhSaMNaFixwAo0UEhMMzBFREdFMDQxNgBFZGdl
build-core / build-core: .github#7

! Failed to restore: Cache service responded with 400
build-core / build-core: .github#25

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
build-core / build-core: .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* master CI Telemetry · 42966178009
Triggered via workflow_dispatch about 1 hour ago

JOBS
✓ build-core / build-core in 12m52s (ID 130343836973)
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
* contention-test (ID 130348282095)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  * Run default-lane contention harness
  * Upload contention failure records
  * Post Install visual dependencies
  * Post Run actions/checkout@v4
✓ coverage-contexts in 1h20m12s (ID 130348282153)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Record per-test coverage contexts
  ✓ Upload coverage contexts database
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* test-cost (ID 130348282178)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run cost-attribution suite
  * Upload global leak report
  * Post Install dependencies
  * Post Run actions/checkout@v4

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
build-core / build-core: .github#4

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0cAD0agAAAAA2LsPqUGJhSaMNaFixwAo0UEhMMzBFREdFMDQxNgBFZGdl
build-core / build-core: .github#7

! Failed to restore: Cache service responded with 400
build-core / build-core: .github#25

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
build-core / build-core: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
coverage-contexts: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0PxP0agAAAACEGsb744yrR750Bw4bmJkTUEhMMzBFREdFMDIwOABFZGdl
coverage-contexts: .github#9

! No files were found with the provided path: .coverage. No artifacts will be uploaded.
coverage-contexts: .github#16

! Failed to restore: Cache service responded with 400
coverage-contexts: .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
coverage-contexts: .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* master CI Telemetry · 42966178009
Triggered via workflow_dispatch about 1 hour ago

JOBS
✓ build-core / build-core in 12m52s (ID 130343836973)
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
* contention-test (ID 130348282095)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  * Run default-lane contention harness
  * Upload contention failure records
  * Post Install visual dependencies
  * Post Run actions/checkout@v4
✓ coverage-contexts in 1h20m12s (ID 130348282153)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Record per-test coverage contexts
  ✓ Upload coverage contexts database
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* test-cost (ID 130348282178)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run cost-attribution suite
  * Upload global leak report
  * Post Install dependencies
  * Post Run actions/checkout@v4

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
build-core / build-core: .github#4

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0cAD0agAAAAA2LsPqUGJhSaMNaFixwAo0UEhMMzBFREdFMDQxNgBFZGdl
build-core / build-core: .github#7

! Failed to restore: Cache service responded with 400
build-core / build-core: .github#25

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
build-core / build-core: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
coverage-contexts: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0PxP0agAAAACEGsb744yrR750Bw4bmJkTUEhMMzBFREdFMDIwOABFZGdl
coverage-contexts: .github#9

! No files were found with the provided path: .coverage. No artifacts will be uploaded.
coverage-contexts: .github#16

! Failed to restore: Cache service responded with 400
coverage-contexts: .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
coverage-contexts: .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* master CI Telemetry · 42966178009
Triggered via workflow_dispatch about 1 hour ago

JOBS
✓ build-core / build-core in 12m52s (ID 130343836973)
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
* contention-test (ID 130348282095)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  * Run default-lane contention harness
  * Upload contention failure records
  * Post Install visual dependencies
  * Post Run actions/checkout@v4
✓ coverage-contexts in 1h20m12s (ID 130348282153)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Record per-test coverage contexts
  ✓ Upload coverage contexts database
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* test-cost (ID 130348282178)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run cost-attribution suite
  * Upload global leak report
  * Post Install dependencies
  * Post Run actions/checkout@v4

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
build-core / build-core: .github#4

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0cAD0agAAAAA2LsPqUGJhSaMNaFixwAo0UEhMMzBFREdFMDQxNgBFZGdl
build-core / build-core: .github#7

! Failed to restore: Cache service responded with 400
build-core / build-core: .github#25

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
build-core / build-core: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
coverage-contexts: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0PxP0agAAAACEGsb744yrR750Bw4bmJkTUEhMMzBFREdFMDIwOABFZGdl
coverage-contexts: .github#9

! No files were found with the provided path: .coverage. No artifacts will be uploaded.
coverage-contexts: .github#16

! Failed to restore: Cache service responded with 400
coverage-contexts: .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
coverage-contexts: .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* master CI Telemetry · 42966178009
Triggered via workflow_dispatch about 1 hour ago

JOBS
✓ build-core / build-core in 12m52s (ID 130343836973)
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
* contention-test (ID 130348282095)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  * Run default-lane contention harness
  * Upload contention failure records
  * Post Install visual dependencies
  * Post Run actions/checkout@v4
✓ coverage-contexts in 1h20m12s (ID 130348282153)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Record per-test coverage contexts
  ✓ Upload coverage contexts database
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* test-cost (ID 130348282178)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run cost-attribution suite
  * Upload global leak report
  * Post Install dependencies
  * Post Run actions/checkout@v4

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
build-core / build-core: .github#4

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0cAD0agAAAAA2LsPqUGJhSaMNaFixwAo0UEhMMzBFREdFMDQxNgBFZGdl
build-core / build-core: .github#7

! Failed to restore: Cache service responded with 400
build-core / build-core: .github#25

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
build-core / build-core: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
coverage-contexts: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0PxP0agAAAACEGsb744yrR750Bw4bmJkTUEhMMzBFREdFMDIwOABFZGdl
coverage-contexts: .github#9

! No files were found with the provided path: .coverage. No artifacts will be uploaded.
coverage-contexts: .github#16

! Failed to restore: Cache service responded with 400
coverage-contexts: .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
coverage-contexts: .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* master CI Telemetry · 42966178009
Triggered via workflow_dispatch about 1 hour ago

JOBS
✓ build-core / build-core in 12m52s (ID 130343836973)
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
* contention-test (ID 130348282095)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  * Run default-lane contention harness
  * Upload contention failure records
  * Post Install visual dependencies
  * Post Run actions/checkout@v4
✓ coverage-contexts in 1h20m12s (ID 130348282153)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Record per-test coverage contexts
  ✓ Upload coverage contexts database
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* test-cost (ID 130348282178)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run cost-attribution suite
  * Upload global leak report
  * Post Install dependencies
  * Post Run actions/checkout@v4

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
build-core / build-core: .github#4

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0cAD0agAAAAA2LsPqUGJhSaMNaFixwAo0UEhMMzBFREdFMDQxNgBFZGdl
build-core / build-core: .github#7

! Failed to restore: Cache service responded with 400
build-core / build-core: .github#25

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
build-core / build-core: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
coverage-contexts: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0PxP0agAAAACEGsb744yrR750Bw4bmJkTUEhMMzBFREdFMDIwOABFZGdl
coverage-contexts: .github#9

! No files were found with the provided path: .coverage. No artifacts will be uploaded.
coverage-contexts: .github#16

! Failed to restore: Cache service responded with 400
coverage-contexts: .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
coverage-contexts: .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* master CI Telemetry · 42966178009
Triggered via workflow_dispatch about 1 hour ago

JOBS
✓ build-core / build-core in 12m52s (ID 130343836973)
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
X contention-test in 1h30m17s (ID 130348282095)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  X Run default-lane contention harness
  ✓ Upload contention failure records
  ✓ Post Install visual dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ coverage-contexts in 1h20m12s (ID 130348282153)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Record per-test coverage contexts
  ✓ Upload coverage contexts database
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* test-cost (ID 130348282178)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run cost-attribution suite
  * Upload global leak report
  * Post Install dependencies
  * Post Run actions/checkout@v4

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
build-core / build-core: .github#4

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0cAD0agAAAAA2LsPqUGJhSaMNaFixwAo0UEhMMzBFREdFMDQxNgBFZGdl
build-core / build-core: .github#7

! Failed to restore: Cache service responded with 400
build-core / build-core: .github#25

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
build-core / build-core: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
coverage-contexts: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0PxP0agAAAACEGsb744yrR750Bw4bmJkTUEhMMzBFREdFMDIwOABFZGdl
coverage-contexts: .github#9

! No files were found with the provided path: .coverage. No artifacts will be uploaded.
coverage-contexts: .github#16

! Failed to restore: Cache service responded with 400
coverage-contexts: .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
coverage-contexts: .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* master CI Telemetry · 42966178009
Triggered via workflow_dispatch about 1 hour ago

JOBS
✓ build-core / build-core in 12m52s (ID 130343836973)
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
X contention-test in 1h30m17s (ID 130348282095)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  X Run default-lane contention harness
  ✓ Upload contention failure records
  ✓ Post Install visual dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ coverage-contexts in 1h20m12s (ID 130348282153)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Record per-test coverage contexts
  ✓ Upload coverage contexts database
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* test-cost (ID 130348282178)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run cost-attribution suite
  * Upload global leak report
  * Post Install dependencies
  * Post Run actions/checkout@v4

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
build-core / build-core: .github#4

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0cAD0agAAAAA2LsPqUGJhSaMNaFixwAo0UEhMMzBFREdFMDQxNgBFZGdl
build-core / build-core: .github#7

! Failed to restore: Cache service responded with 400
build-core / build-core: .github#25

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
build-core / build-core: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
coverage-contexts: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0PxP0agAAAACEGsb744yrR750Bw4bmJkTUEhMMzBFREdFMDIwOABFZGdl
coverage-contexts: .github#9

! No files were found with the provided path: .coverage. No artifacts will be uploaded.
coverage-contexts: .github#16

! Failed to restore: Cache service responded with 400
coverage-contexts: .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
coverage-contexts: .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* master CI Telemetry · 42966178009
Triggered via workflow_dispatch about 1 hour ago

JOBS
✓ build-core / build-core in 12m52s (ID 130343836973)
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
X contention-test in 1h30m17s (ID 130348282095)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  X Run default-lane contention harness
  ✓ Upload contention failure records
  ✓ Post Install visual dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ coverage-contexts in 1h20m12s (ID 130348282153)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Record per-test coverage contexts
  ✓ Upload coverage contexts database
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* test-cost (ID 130348282178)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run cost-attribution suite
  * Upload global leak report
  * Post Install dependencies
  * Post Run actions/checkout@v4

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
build-core / build-core: .github#4

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0cAD0agAAAAA2LsPqUGJhSaMNaFixwAo0UEhMMzBFREdFMDQxNgBFZGdl
build-core / build-core: .github#7

! Failed to restore: Cache service responded with 400
build-core / build-core: .github#25

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
build-core / build-core: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
coverage-contexts: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0PxP0agAAAACEGsb744yrR750Bw4bmJkTUEhMMzBFREdFMDIwOABFZGdl
coverage-contexts: .github#9

! No files were found with the provided path: .coverage. No artifacts will be uploaded.
coverage-contexts: .github#16

! Failed to restore: Cache service responded with 400
coverage-contexts: .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
coverage-contexts: .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* master CI Telemetry · 42966178009
Triggered via workflow_dispatch about 1 hour ago

JOBS
✓ build-core / build-core in 12m52s (ID 130343836973)
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
X contention-test in 1h30m17s (ID 130348282095)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  X Run default-lane contention harness
  ✓ Upload contention failure records
  ✓ Post Install visual dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ coverage-contexts in 1h20m12s (ID 130348282153)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Record per-test coverage contexts
  ✓ Upload coverage contexts database
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* test-cost (ID 130348282178)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run cost-attribution suite
  * Upload global leak report
  * Post Install dependencies
  * Post Run actions/checkout@v4

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
build-core / build-core: .github#4

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0cAD0agAAAAA2LsPqUGJhSaMNaFixwAo0UEhMMzBFREdFMDQxNgBFZGdl
build-core / build-core: .github#7

! Failed to restore: Cache service responded with 400
build-core / build-core: .github#25

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
build-core / build-core: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
coverage-contexts: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0PxP0agAAAACEGsb744yrR750Bw4bmJkTUEhMMzBFREdFMDIwOABFZGdl
coverage-contexts: .github#9

! No files were found with the provided path: .coverage. No artifacts will be uploaded.
coverage-contexts: .github#16

! Failed to restore: Cache service responded with 400
coverage-contexts: .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
coverage-contexts: .github#1

X master CI Telemetry · 42966178009
Triggered via workflow_dispatch about 1 hour ago

JOBS
✓ build-core / build-core in 12m52s (ID 130343836973)
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
X contention-test in 1h30m17s (ID 130348282095)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  X Run default-lane contention harness
  ✓ Upload contention failure records
  ✓ Post Install visual dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ coverage-contexts in 1h20m12s (ID 130348282153)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Record per-test coverage contexts
  ✓ Upload coverage contexts database
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
X test-cost in 1h38m16s (ID 130348282178)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  X Run cost-attribution suite
  ✓ Upload global leak report
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
build-core / build-core: .github#4

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0cAD0agAAAAA2LsPqUGJhSaMNaFixwAo0UEhMMzBFREdFMDQxNgBFZGdl
build-core / build-core: .github#7

! Failed to restore: Cache service responded with 400
build-core / build-core: .github#25

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
build-core / build-core: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
coverage-contexts: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0PxP0agAAAACEGsb744yrR750Bw4bmJkTUEhMMzBFREdFMDIwOABFZGdl
coverage-contexts: .github#9

! No files were found with the provided path: .coverage. No artifacts will be uploaded.
coverage-contexts: .github#16

! Failed to restore: Cache service responded with 400
coverage-contexts: .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
coverage-contexts: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
test-cost: .github#2

X Process completed with exit code 1.
test-cost: .github#1541

! Failed to restore: Cache service responded with 400
test-cost: .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
test-cost: .github#1


