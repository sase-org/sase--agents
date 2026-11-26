# Chat History - ace-run (sase-1vb.6--mon)

- **TIMESTAMP:** 2026-11-26 10:26:25 EST
- **MODEL:** codex/gpt-6-luna
- **AGENT:** sase-1vb.6--mon

## Prompt

sase monitor start --command 'gh run watch 45846683375 --repo sase-org/sase --exit-status' --reason 'Wait for Master Gate on landed tip 1e017d0defae1100988816e246930db21ffdfc84 to finish'

## Response

sase: running unwrapped (no profile (monitor.tool_wrap is verify))
Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Master Gate · 45846683375
Triggered via push about 4 minutes ago

JOBS
✓ docs in 43s (ID 140002064615)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Install just
  ✓ Set up Python
  ✓ Build and validate docs
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ core-wheel in 27s (ID 140002065096)
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
* lint (ID 140002347998)
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
* test (8) (ID 140002348205)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (6) (ID 140002348206)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (7) (ID 140002348215)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (4) (ID 140002348218)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (5) (ID 140002348235)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (1) (ID 140002348268)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (3) (ID 140002348276)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (2) (ID 140002348307)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
docs: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0c0wIawAAAACOXf5NpvwsR4nFqoZbJwHEQ08xRURHRTE2MjAARWRnZQ==
docs: .github#7

! Failed to restore: Cache service responded with 400
docs: .github#26

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache/restore@v4, actions/checkout@v4, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
core-wheel: .github#2

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Master Gate · 45846683375
Triggered via push about 4 minutes ago

JOBS
✓ docs in 43s (ID 140002064615)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Install just
  ✓ Set up Python
  ✓ Build and validate docs
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ core-wheel in 27s (ID 140002065096)
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
* lint (ID 140002347998)
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
* test (8) (ID 140002348205)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (6) (ID 140002348206)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (7) (ID 140002348215)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (4) (ID 140002348218)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (5) (ID 140002348235)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (1) (ID 140002348268)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (3) (ID 140002348276)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (2) (ID 140002348307)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
docs: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0c0wIawAAAACOXf5NpvwsR4nFqoZbJwHEQ08xRURHRTE2MjAARWRnZQ==
docs: .github#7

! Failed to restore: Cache service responded with 400
docs: .github#26

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache/restore@v4, actions/checkout@v4, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
core-wheel: .github#2

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Master Gate · 45846683375
Triggered via push about 4 minutes ago

JOBS
✓ docs in 43s (ID 140002064615)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Install just
  ✓ Set up Python
  ✓ Build and validate docs
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ core-wheel in 27s (ID 140002065096)
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
* lint (ID 140002347998)
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
* test (8) (ID 140002348205)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (6) (ID 140002348206)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (7) (ID 140002348215)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (4) (ID 140002348218)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (5) (ID 140002348235)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (1) (ID 140002348268)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (3) (ID 140002348276)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (2) (ID 140002348307)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
docs: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0c0wIawAAAACOXf5NpvwsR4nFqoZbJwHEQ08xRURHRTE2MjAARWRnZQ==
docs: .github#7

! Failed to restore: Cache service responded with 400
docs: .github#26

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache/restore@v4, actions/checkout@v4, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
core-wheel: .github#2

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Master Gate · 45846683375
Triggered via push about 4 minutes ago

JOBS
✓ docs in 43s (ID 140002064615)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Install just
  ✓ Set up Python
  ✓ Build and validate docs
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ core-wheel in 27s (ID 140002065096)
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
* lint (ID 140002347998)
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
* test (8) (ID 140002348205)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (6) (ID 140002348206)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (7) (ID 140002348215)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (4) (ID 140002348218)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (5) (ID 140002348235)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (1) (ID 140002348268)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (3) (ID 140002348276)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (2) (ID 140002348307)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
docs: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0c0wIawAAAACOXf5NpvwsR4nFqoZbJwHEQ08xRURHRTE2MjAARWRnZQ==
docs: .github#7

! Failed to restore: Cache service responded with 400
docs: .github#26

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache/restore@v4, actions/checkout@v4, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
core-wheel: .github#2

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Master Gate · 45846683375
Triggered via push about 4 minutes ago

JOBS
✓ docs in 43s (ID 140002064615)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Install just
  ✓ Set up Python
  ✓ Build and validate docs
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ core-wheel in 27s (ID 140002065096)
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
* lint (ID 140002347998)
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
* test (8) (ID 140002348205)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (6) (ID 140002348206)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (7) (ID 140002348215)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (4) (ID 140002348218)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (5) (ID 140002348235)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (1) (ID 140002348268)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (3) (ID 140002348276)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (2) (ID 140002348307)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
docs: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0c0wIawAAAACOXf5NpvwsR4nFqoZbJwHEQ08xRURHRTE2MjAARWRnZQ==
docs: .github#7

! Failed to restore: Cache service responded with 400
docs: .github#26

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache/restore@v4, actions/checkout@v4, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
core-wheel: .github#2

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Master Gate · 45846683375
Triggered via push about 4 minutes ago

JOBS
✓ docs in 43s (ID 140002064615)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Install just
  ✓ Set up Python
  ✓ Build and validate docs
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ core-wheel in 27s (ID 140002065096)
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
* lint (ID 140002347998)
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
* test (8) (ID 140002348205)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (6) (ID 140002348206)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (7) (ID 140002348215)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (4) (ID 140002348218)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (5) (ID 140002348235)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (1) (ID 140002348268)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (3) (ID 140002348276)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (2) (ID 140002348307)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
docs: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0c0wIawAAAACOXf5NpvwsR4nFqoZbJwHEQ08xRURHRTE2MjAARWRnZQ==
docs: .github#7

! Failed to restore: Cache service responded with 400
docs: .github#26

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache/restore@v4, actions/checkout@v4, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
core-wheel: .github#2

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Master Gate · 45846683375
Triggered via push about 4 minutes ago

JOBS
✓ docs in 43s (ID 140002064615)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Install just
  ✓ Set up Python
  ✓ Build and validate docs
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ core-wheel in 27s (ID 140002065096)
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
* lint (ID 140002347998)
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
* test (8) (ID 140002348205)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (6) (ID 140002348206)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (7) (ID 140002348215)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (4) (ID 140002348218)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (5) (ID 140002348235)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (1) (ID 140002348268)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (3) (ID 140002348276)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (2) (ID 140002348307)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
docs: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0c0wIawAAAACOXf5NpvwsR4nFqoZbJwHEQ08xRURHRTE2MjAARWRnZQ==
docs: .github#7

! Failed to restore: Cache service responded with 400
docs: .github#26

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache/restore@v4, actions/checkout@v4, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
core-wheel: .github#2

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Master Gate · 45846683375
Triggered via push about 5 minutes ago

JOBS
✓ docs in 43s (ID 140002064615)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Install just
  ✓ Set up Python
  ✓ Build and validate docs
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ core-wheel in 27s (ID 140002065096)
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
* lint (ID 140002347998)
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
* test (8) (ID 140002348205)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (6) (ID 140002348206)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (7) (ID 140002348215)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (4) (ID 140002348218)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (5) (ID 140002348235)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (1) (ID 140002348268)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (3) (ID 140002348276)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (2) (ID 140002348307)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
docs: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0c0wIawAAAACOXf5NpvwsR4nFqoZbJwHEQ08xRURHRTE2MjAARWRnZQ==
docs: .github#7

! Failed to restore: Cache service responded with 400
docs: .github#26

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache/restore@v4, actions/checkout@v4, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
core-wheel: .github#2

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Master Gate · 45846683375
Triggered via push about 5 minutes ago

JOBS
✓ docs in 43s (ID 140002064615)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Install just
  ✓ Set up Python
  ✓ Build and validate docs
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ core-wheel in 27s (ID 140002065096)
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
* lint (ID 140002347998)
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
  * Validate committed plans
  * Build and verify package
  * Post Cache Prettier dependencies
  * Post Cache Go binaries
  * Post Run actions/setup-go@v5
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (8) (ID 140002348205)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (6) (ID 140002348206)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (7) (ID 140002348215)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (4) (ID 140002348218)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (5) (ID 140002348235)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (1) (ID 140002348268)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (3) (ID 140002348276)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (2) (ID 140002348307)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
docs: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0c0wIawAAAACOXf5NpvwsR4nFqoZbJwHEQ08xRURHRTE2MjAARWRnZQ==
docs: .github#7

! Failed to restore: Cache service responded with 400
docs: .github#26

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache/restore@v4, actions/checkout@v4, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
core-wheel: .github#2

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Master Gate · 45846683375
Triggered via push about 5 minutes ago

JOBS
✓ docs in 43s (ID 140002064615)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Install just
  ✓ Set up Python
  ✓ Build and validate docs
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ core-wheel in 27s (ID 140002065096)
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
* lint (ID 140002347998)
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
  * Build and verify package
  * Post Cache Prettier dependencies
  * Post Cache Go binaries
  * Post Run actions/setup-go@v5
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (8) (ID 140002348205)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (6) (ID 140002348206)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (7) (ID 140002348215)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (4) (ID 140002348218)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (5) (ID 140002348235)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (1) (ID 140002348268)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (3) (ID 140002348276)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (2) (ID 140002348307)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
docs: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0c0wIawAAAACOXf5NpvwsR4nFqoZbJwHEQ08xRURHRTE2MjAARWRnZQ==
docs: .github#7

! Failed to restore: Cache service responded with 400
docs: .github#26

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache/restore@v4, actions/checkout@v4, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
core-wheel: .github#2

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Master Gate · 45846683375
Triggered via push about 5 minutes ago

JOBS
✓ docs in 43s (ID 140002064615)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Install just
  ✓ Set up Python
  ✓ Build and validate docs
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ core-wheel in 27s (ID 140002065096)
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
* lint (ID 140002347998)
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
  * Build and verify package
  * Post Cache Prettier dependencies
  * Post Cache Go binaries
  * Post Run actions/setup-go@v5
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (8) (ID 140002348205)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (6) (ID 140002348206)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (7) (ID 140002348215)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (4) (ID 140002348218)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (5) (ID 140002348235)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (1) (ID 140002348268)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (3) (ID 140002348276)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (2) (ID 140002348307)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
docs: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0c0wIawAAAACOXf5NpvwsR4nFqoZbJwHEQ08xRURHRTE2MjAARWRnZQ==
docs: .github#7

! Failed to restore: Cache service responded with 400
docs: .github#26

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache/restore@v4, actions/checkout@v4, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
core-wheel: .github#2

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Master Gate · 45846683375
Triggered via push about 5 minutes ago

JOBS
✓ docs in 43s (ID 140002064615)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Install just
  ✓ Set up Python
  ✓ Build and validate docs
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ core-wheel in 27s (ID 140002065096)
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
* lint (ID 140002347998)
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
  * Build and verify package
  * Post Cache Prettier dependencies
  * Post Cache Go binaries
  * Post Run actions/setup-go@v5
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (8) (ID 140002348205)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (6) (ID 140002348206)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (7) (ID 140002348215)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (4) (ID 140002348218)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (5) (ID 140002348235)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (1) (ID 140002348268)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (3) (ID 140002348276)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (2) (ID 140002348307)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
docs: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0c0wIawAAAACOXf5NpvwsR4nFqoZbJwHEQ08xRURHRTE2MjAARWRnZQ==
docs: .github#7

! Failed to restore: Cache service responded with 400
docs: .github#26

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache/restore@v4, actions/checkout@v4, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
core-wheel: .github#2

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Master Gate · 45846683375
Triggered via push about 5 minutes ago

JOBS
✓ docs in 43s (ID 140002064615)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Install just
  ✓ Set up Python
  ✓ Build and validate docs
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ core-wheel in 27s (ID 140002065096)
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
✓ lint in 4m54s (ID 140002347998)
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
* test (8) (ID 140002348205)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (6) (ID 140002348206)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (7) (ID 140002348215)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (4) (ID 140002348218)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (5) (ID 140002348235)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (1) (ID 140002348268)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (3) (ID 140002348276)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (2) (ID 140002348307)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
docs: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0c0wIawAAAACOXf5NpvwsR4nFqoZbJwHEQ08xRURHRTE2MjAARWRnZQ==
docs: .github#7

! Failed to restore: Cache service responded with 400
docs: .github#26

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache/restore@v4, actions/checkout@v4, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
core-wheel: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache@v4, actions/checkout@v4, actions/download-artifact@v4, actions/setup-go@v5, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
lint: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0jE0IawAAAADNcL55q1IlRLnjbGxMCbSlUEhMMzBFREdFMDQxNwBFZGdl
lint: .github#9

! Failed to restore: Cache service responded with 400
lint: .github#54

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Master Gate · 45846683375
Triggered via push about 5 minutes ago

JOBS
✓ docs in 43s (ID 140002064615)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Install just
  ✓ Set up Python
  ✓ Build and validate docs
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ core-wheel in 27s (ID 140002065096)
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
✓ lint in 4m54s (ID 140002347998)
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
* test (8) (ID 140002348205)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (6) (ID 140002348206)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (7) (ID 140002348215)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (4) (ID 140002348218)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (5) (ID 140002348235)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (1) (ID 140002348268)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (3) (ID 140002348276)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (2) (ID 140002348307)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
docs: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0c0wIawAAAACOXf5NpvwsR4nFqoZbJwHEQ08xRURHRTE2MjAARWRnZQ==
docs: .github#7

! Failed to restore: Cache service responded with 400
docs: .github#26

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache/restore@v4, actions/checkout@v4, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
core-wheel: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache@v4, actions/checkout@v4, actions/download-artifact@v4, actions/setup-go@v5, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
lint: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0jE0IawAAAADNcL55q1IlRLnjbGxMCbSlUEhMMzBFREdFMDQxNwBFZGdl
lint: .github#9

! Failed to restore: Cache service responded with 400
lint: .github#54

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Master Gate · 45846683375
Triggered via push about 5 minutes ago

JOBS
✓ docs in 43s (ID 140002064615)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Install just
  ✓ Set up Python
  ✓ Build and validate docs
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ core-wheel in 27s (ID 140002065096)
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
✓ lint in 4m54s (ID 140002347998)
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
* test (8) (ID 140002348205)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (6) (ID 140002348206)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (7) (ID 140002348215)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (4) (ID 140002348218)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (5) (ID 140002348235)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (1) (ID 140002348268)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (3) (ID 140002348276)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (2) (ID 140002348307)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
docs: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0c0wIawAAAACOXf5NpvwsR4nFqoZbJwHEQ08xRURHRTE2MjAARWRnZQ==
docs: .github#7

! Failed to restore: Cache service responded with 400
docs: .github#26

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache/restore@v4, actions/checkout@v4, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
core-wheel: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache@v4, actions/checkout@v4, actions/download-artifact@v4, actions/setup-go@v5, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
lint: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0jE0IawAAAADNcL55q1IlRLnjbGxMCbSlUEhMMzBFREdFMDQxNwBFZGdl
lint: .github#9

! Failed to restore: Cache service responded with 400
lint: .github#54

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Master Gate · 45846683375
Triggered via push about 5 minutes ago

JOBS
✓ docs in 43s (ID 140002064615)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Install just
  ✓ Set up Python
  ✓ Build and validate docs
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ core-wheel in 27s (ID 140002065096)
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
✓ lint in 4m54s (ID 140002347998)
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
* test (8) (ID 140002348205)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (6) (ID 140002348206)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (7) (ID 140002348215)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (4) (ID 140002348218)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (5) (ID 140002348235)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (1) (ID 140002348268)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (3) (ID 140002348276)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (2) (ID 140002348307)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
docs: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0c0wIawAAAACOXf5NpvwsR4nFqoZbJwHEQ08xRURHRTE2MjAARWRnZQ==
docs: .github#7

! Failed to restore: Cache service responded with 400
docs: .github#26

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache/restore@v4, actions/checkout@v4, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
core-wheel: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache@v4, actions/checkout@v4, actions/download-artifact@v4, actions/setup-go@v5, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
lint: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0jE0IawAAAADNcL55q1IlRLnjbGxMCbSlUEhMMzBFREdFMDQxNwBFZGdl
lint: .github#9

! Failed to restore: Cache service responded with 400
lint: .github#54

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Master Gate · 45846683375
Triggered via push about 5 minutes ago

JOBS
✓ docs in 43s (ID 140002064615)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Install just
  ✓ Set up Python
  ✓ Build and validate docs
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ core-wheel in 27s (ID 140002065096)
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
✓ lint in 4m54s (ID 140002347998)
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
* test (8) (ID 140002348205)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (6) (ID 140002348206)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (7) (ID 140002348215)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (4) (ID 140002348218)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (5) (ID 140002348235)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (1) (ID 140002348268)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (3) (ID 140002348276)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (2) (ID 140002348307)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
docs: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0c0wIawAAAACOXf5NpvwsR4nFqoZbJwHEQ08xRURHRTE2MjAARWRnZQ==
docs: .github#7

! Failed to restore: Cache service responded with 400
docs: .github#26

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache/restore@v4, actions/checkout@v4, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
core-wheel: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache@v4, actions/checkout@v4, actions/download-artifact@v4, actions/setup-go@v5, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
lint: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0jE0IawAAAADNcL55q1IlRLnjbGxMCbSlUEhMMzBFREdFMDQxNwBFZGdl
lint: .github#9

! Failed to restore: Cache service responded with 400
lint: .github#54

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Master Gate · 45846683375
Triggered via push about 5 minutes ago

JOBS
✓ docs in 43s (ID 140002064615)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Install just
  ✓ Set up Python
  ✓ Build and validate docs
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ core-wheel in 27s (ID 140002065096)
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
✓ lint in 4m54s (ID 140002347998)
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
* test (8) (ID 140002348205)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (6) (ID 140002348206)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (7) (ID 140002348215)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (4) (ID 140002348218)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (5) (ID 140002348235)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (1) (ID 140002348268)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (3) (ID 140002348276)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (2) (ID 140002348307)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
docs: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0c0wIawAAAACOXf5NpvwsR4nFqoZbJwHEQ08xRURHRTE2MjAARWRnZQ==
docs: .github#7

! Failed to restore: Cache service responded with 400
docs: .github#26

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache/restore@v4, actions/checkout@v4, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
core-wheel: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache@v4, actions/checkout@v4, actions/download-artifact@v4, actions/setup-go@v5, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
lint: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0jE0IawAAAADNcL55q1IlRLnjbGxMCbSlUEhMMzBFREdFMDQxNwBFZGdl
lint: .github#9

! Failed to restore: Cache service responded with 400
lint: .github#54

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Master Gate · 45846683375
Triggered via push about 6 minutes ago

JOBS
✓ docs in 43s (ID 140002064615)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Install just
  ✓ Set up Python
  ✓ Build and validate docs
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ core-wheel in 27s (ID 140002065096)
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
✓ lint in 4m54s (ID 140002347998)
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
* test (8) (ID 140002348205)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (6) (ID 140002348206)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (7) (ID 140002348215)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (4) (ID 140002348218)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (5) (ID 140002348235)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (1) (ID 140002348268)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (3) (ID 140002348276)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (2) (ID 140002348307)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
docs: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0c0wIawAAAACOXf5NpvwsR4nFqoZbJwHEQ08xRURHRTE2MjAARWRnZQ==
docs: .github#7

! Failed to restore: Cache service responded with 400
docs: .github#26

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache/restore@v4, actions/checkout@v4, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
core-wheel: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache@v4, actions/checkout@v4, actions/download-artifact@v4, actions/setup-go@v5, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
lint: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0jE0IawAAAADNcL55q1IlRLnjbGxMCbSlUEhMMzBFREdFMDQxNwBFZGdl
lint: .github#9

! Failed to restore: Cache service responded with 400
lint: .github#54

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Master Gate · 45846683375
Triggered via push about 6 minutes ago

JOBS
✓ docs in 43s (ID 140002064615)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Install just
  ✓ Set up Python
  ✓ Build and validate docs
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ core-wheel in 27s (ID 140002065096)
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
✓ lint in 4m54s (ID 140002347998)
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
* test (8) (ID 140002348205)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (6) (ID 140002348206)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (7) (ID 140002348215)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (4) (ID 140002348218)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (5) (ID 140002348235)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (1) (ID 140002348268)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (3) (ID 140002348276)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (2) (ID 140002348307)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
docs: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0c0wIawAAAACOXf5NpvwsR4nFqoZbJwHEQ08xRURHRTE2MjAARWRnZQ==
docs: .github#7

! Failed to restore: Cache service responded with 400
docs: .github#26

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache/restore@v4, actions/checkout@v4, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
core-wheel: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache@v4, actions/checkout@v4, actions/download-artifact@v4, actions/setup-go@v5, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
lint: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0jE0IawAAAADNcL55q1IlRLnjbGxMCbSlUEhMMzBFREdFMDQxNwBFZGdl
lint: .github#9

! Failed to restore: Cache service responded with 400
lint: .github#54

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Master Gate · 45846683375
Triggered via push about 6 minutes ago

JOBS
✓ docs in 43s (ID 140002064615)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Install just
  ✓ Set up Python
  ✓ Build and validate docs
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ core-wheel in 27s (ID 140002065096)
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
✓ lint in 4m54s (ID 140002347998)
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
* test (8) (ID 140002348205)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (6) (ID 140002348206)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (7) (ID 140002348215)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (4) (ID 140002348218)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (5) (ID 140002348235)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (1) (ID 140002348268)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (3) (ID 140002348276)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (2) (ID 140002348307)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
docs: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0c0wIawAAAACOXf5NpvwsR4nFqoZbJwHEQ08xRURHRTE2MjAARWRnZQ==
docs: .github#7

! Failed to restore: Cache service responded with 400
docs: .github#26

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache/restore@v4, actions/checkout@v4, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
core-wheel: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache@v4, actions/checkout@v4, actions/download-artifact@v4, actions/setup-go@v5, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
lint: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0jE0IawAAAADNcL55q1IlRLnjbGxMCbSlUEhMMzBFREdFMDQxNwBFZGdl
lint: .github#9

! Failed to restore: Cache service responded with 400
lint: .github#54

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Master Gate · 45846683375
Triggered via push about 6 minutes ago

JOBS
✓ docs in 43s (ID 140002064615)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Install just
  ✓ Set up Python
  ✓ Build and validate docs
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ core-wheel in 27s (ID 140002065096)
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
✓ lint in 4m54s (ID 140002347998)
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
* test (8) (ID 140002348205)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (6) (ID 140002348206)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (7) (ID 140002348215)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (4) (ID 140002348218)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (5) (ID 140002348235)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (1) (ID 140002348268)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (3) (ID 140002348276)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (2) (ID 140002348307)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
docs: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0c0wIawAAAACOXf5NpvwsR4nFqoZbJwHEQ08xRURHRTE2MjAARWRnZQ==
docs: .github#7

! Failed to restore: Cache service responded with 400
docs: .github#26

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache/restore@v4, actions/checkout@v4, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
core-wheel: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache@v4, actions/checkout@v4, actions/download-artifact@v4, actions/setup-go@v5, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
lint: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0jE0IawAAAADNcL55q1IlRLnjbGxMCbSlUEhMMzBFREdFMDQxNwBFZGdl
lint: .github#9

! Failed to restore: Cache service responded with 400
lint: .github#54

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Master Gate · 45846683375
Triggered via push about 6 minutes ago

JOBS
✓ docs in 43s (ID 140002064615)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Install just
  ✓ Set up Python
  ✓ Build and validate docs
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ core-wheel in 27s (ID 140002065096)
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
✓ lint in 4m54s (ID 140002347998)
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
* test (8) (ID 140002348205)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (6) (ID 140002348206)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (7) (ID 140002348215)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (4) (ID 140002348218)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (5) (ID 140002348235)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (1) (ID 140002348268)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (3) (ID 140002348276)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (2) (ID 140002348307)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
docs: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0c0wIawAAAACOXf5NpvwsR4nFqoZbJwHEQ08xRURHRTE2MjAARWRnZQ==
docs: .github#7

! Failed to restore: Cache service responded with 400
docs: .github#26

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache/restore@v4, actions/checkout@v4, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
core-wheel: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache@v4, actions/checkout@v4, actions/download-artifact@v4, actions/setup-go@v5, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
lint: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0jE0IawAAAADNcL55q1IlRLnjbGxMCbSlUEhMMzBFREdFMDQxNwBFZGdl
lint: .github#9

! Failed to restore: Cache service responded with 400
lint: .github#54

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Master Gate · 45846683375
Triggered via push about 6 minutes ago

JOBS
✓ docs in 43s (ID 140002064615)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Install just
  ✓ Set up Python
  ✓ Build and validate docs
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ core-wheel in 27s (ID 140002065096)
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
✓ lint in 4m54s (ID 140002347998)
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
* test (8) (ID 140002348205)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (6) (ID 140002348206)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (7) (ID 140002348215)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (4) (ID 140002348218)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (5) (ID 140002348235)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (1) (ID 140002348268)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (3) (ID 140002348276)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (2) (ID 140002348307)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
docs: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0c0wIawAAAACOXf5NpvwsR4nFqoZbJwHEQ08xRURHRTE2MjAARWRnZQ==
docs: .github#7

! Failed to restore: Cache service responded with 400
docs: .github#26

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache/restore@v4, actions/checkout@v4, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
core-wheel: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache@v4, actions/checkout@v4, actions/download-artifact@v4, actions/setup-go@v5, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
lint: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0jE0IawAAAADNcL55q1IlRLnjbGxMCbSlUEhMMzBFREdFMDQxNwBFZGdl
lint: .github#9

! Failed to restore: Cache service responded with 400
lint: .github#54

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Master Gate · 45846683375
Triggered via push about 6 minutes ago

JOBS
✓ docs in 43s (ID 140002064615)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Install just
  ✓ Set up Python
  ✓ Build and validate docs
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ core-wheel in 27s (ID 140002065096)
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
✓ lint in 4m54s (ID 140002347998)
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
* test (8) (ID 140002348205)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (6) (ID 140002348206)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (7) (ID 140002348215)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (4) (ID 140002348218)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (5) (ID 140002348235)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (1) (ID 140002348268)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (3) (ID 140002348276)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (2) (ID 140002348307)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
docs: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0c0wIawAAAACOXf5NpvwsR4nFqoZbJwHEQ08xRURHRTE2MjAARWRnZQ==
docs: .github#7

! Failed to restore: Cache service responded with 400
docs: .github#26

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache/restore@v4, actions/checkout@v4, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
core-wheel: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache@v4, actions/checkout@v4, actions/download-artifact@v4, actions/setup-go@v5, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
lint: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0jE0IawAAAADNcL55q1IlRLnjbGxMCbSlUEhMMzBFREdFMDQxNwBFZGdl
lint: .github#9

! Failed to restore: Cache service responded with 400
lint: .github#54

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Master Gate · 45846683375
Triggered via push about 6 minutes ago

JOBS
✓ docs in 43s (ID 140002064615)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Install just
  ✓ Set up Python
  ✓ Build and validate docs
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ core-wheel in 27s (ID 140002065096)
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
✓ lint in 4m54s (ID 140002347998)
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
* test (8) (ID 140002348205)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (6) (ID 140002348206)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (7) (ID 140002348215)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (4) (ID 140002348218)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (5) (ID 140002348235)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (1) (ID 140002348268)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (3) (ID 140002348276)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (2) (ID 140002348307)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
docs: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0c0wIawAAAACOXf5NpvwsR4nFqoZbJwHEQ08xRURHRTE2MjAARWRnZQ==
docs: .github#7

! Failed to restore: Cache service responded with 400
docs: .github#26

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache/restore@v4, actions/checkout@v4, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
core-wheel: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache@v4, actions/checkout@v4, actions/download-artifact@v4, actions/setup-go@v5, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
lint: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0jE0IawAAAADNcL55q1IlRLnjbGxMCbSlUEhMMzBFREdFMDQxNwBFZGdl
lint: .github#9

! Failed to restore: Cache service responded with 400
lint: .github#54

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Master Gate · 45846683375
Triggered via push about 6 minutes ago

JOBS
✓ docs in 43s (ID 140002064615)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Install just
  ✓ Set up Python
  ✓ Build and validate docs
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ core-wheel in 27s (ID 140002065096)
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
✓ lint in 4m54s (ID 140002347998)
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
* test (8) (ID 140002348205)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (6) (ID 140002348206)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (7) (ID 140002348215)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (4) (ID 140002348218)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (5) (ID 140002348235)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (1) (ID 140002348268)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (3) (ID 140002348276)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (2) (ID 140002348307)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
docs: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0c0wIawAAAACOXf5NpvwsR4nFqoZbJwHEQ08xRURHRTE2MjAARWRnZQ==
docs: .github#7

! Failed to restore: Cache service responded with 400
docs: .github#26

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache/restore@v4, actions/checkout@v4, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
core-wheel: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache@v4, actions/checkout@v4, actions/download-artifact@v4, actions/setup-go@v5, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
lint: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0jE0IawAAAADNcL55q1IlRLnjbGxMCbSlUEhMMzBFREdFMDQxNwBFZGdl
lint: .github#9

! Failed to restore: Cache service responded with 400
lint: .github#54

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Master Gate · 45846683375
Triggered via push about 6 minutes ago

JOBS
✓ docs in 43s (ID 140002064615)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Install just
  ✓ Set up Python
  ✓ Build and validate docs
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ core-wheel in 27s (ID 140002065096)
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
✓ lint in 4m54s (ID 140002347998)
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
* test (8) (ID 140002348205)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (6) (ID 140002348206)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (7) (ID 140002348215)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (4) (ID 140002348218)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (5) (ID 140002348235)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (1) (ID 140002348268)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (3) (ID 140002348276)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (2) (ID 140002348307)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
docs: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0c0wIawAAAACOXf5NpvwsR4nFqoZbJwHEQ08xRURHRTE2MjAARWRnZQ==
docs: .github#7

! Failed to restore: Cache service responded with 400
docs: .github#26

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache/restore@v4, actions/checkout@v4, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
core-wheel: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache@v4, actions/checkout@v4, actions/download-artifact@v4, actions/setup-go@v5, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
lint: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0jE0IawAAAADNcL55q1IlRLnjbGxMCbSlUEhMMzBFREdFMDQxNwBFZGdl
lint: .github#9

! Failed to restore: Cache service responded with 400
lint: .github#54

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Master Gate · 45846683375
Triggered via push about 6 minutes ago

JOBS
✓ docs in 43s (ID 140002064615)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Install just
  ✓ Set up Python
  ✓ Build and validate docs
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ core-wheel in 27s (ID 140002065096)
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
✓ lint in 4m54s (ID 140002347998)
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
* test (8) (ID 140002348205)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (6) (ID 140002348206)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (7) (ID 140002348215)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (4) (ID 140002348218)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (5) (ID 140002348235)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (1) (ID 140002348268)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (3) (ID 140002348276)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (2) (ID 140002348307)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
docs: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0c0wIawAAAACOXf5NpvwsR4nFqoZbJwHEQ08xRURHRTE2MjAARWRnZQ==
docs: .github#7

! Failed to restore: Cache service responded with 400
docs: .github#26

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache/restore@v4, actions/checkout@v4, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
core-wheel: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache@v4, actions/checkout@v4, actions/download-artifact@v4, actions/setup-go@v5, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
lint: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0jE0IawAAAADNcL55q1IlRLnjbGxMCbSlUEhMMzBFREdFMDQxNwBFZGdl
lint: .github#9

! Failed to restore: Cache service responded with 400
lint: .github#54

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Master Gate · 45846683375
Triggered via push about 6 minutes ago

JOBS
✓ docs in 43s (ID 140002064615)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Install just
  ✓ Set up Python
  ✓ Build and validate docs
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ core-wheel in 27s (ID 140002065096)
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
✓ lint in 4m54s (ID 140002347998)
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
* test (8) (ID 140002348205)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (6) (ID 140002348206)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (7) (ID 140002348215)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (4) (ID 140002348218)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (5) (ID 140002348235)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (1) (ID 140002348268)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (3) (ID 140002348276)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (2) (ID 140002348307)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
docs: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0c0wIawAAAACOXf5NpvwsR4nFqoZbJwHEQ08xRURHRTE2MjAARWRnZQ==
docs: .github#7

! Failed to restore: Cache service responded with 400
docs: .github#26

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache/restore@v4, actions/checkout@v4, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
core-wheel: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache@v4, actions/checkout@v4, actions/download-artifact@v4, actions/setup-go@v5, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
lint: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0jE0IawAAAADNcL55q1IlRLnjbGxMCbSlUEhMMzBFREdFMDQxNwBFZGdl
lint: .github#9

! Failed to restore: Cache service responded with 400
lint: .github#54

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Master Gate · 45846683375
Triggered via push about 7 minutes ago

JOBS
✓ docs in 43s (ID 140002064615)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Install just
  ✓ Set up Python
  ✓ Build and validate docs
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ core-wheel in 27s (ID 140002065096)
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
✓ lint in 4m54s (ID 140002347998)
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
* test (8) (ID 140002348205)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (6) (ID 140002348206)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (7) (ID 140002348215)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (4) (ID 140002348218)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (5) (ID 140002348235)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (1) (ID 140002348268)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (3) (ID 140002348276)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (2) (ID 140002348307)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
docs: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0c0wIawAAAACOXf5NpvwsR4nFqoZbJwHEQ08xRURHRTE2MjAARWRnZQ==
docs: .github#7

! Failed to restore: Cache service responded with 400
docs: .github#26

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache/restore@v4, actions/checkout@v4, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
core-wheel: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache@v4, actions/checkout@v4, actions/download-artifact@v4, actions/setup-go@v5, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
lint: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0jE0IawAAAADNcL55q1IlRLnjbGxMCbSlUEhMMzBFREdFMDQxNwBFZGdl
lint: .github#9

! Failed to restore: Cache service responded with 400
lint: .github#54

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Master Gate · 45846683375
Triggered via push about 7 minutes ago

JOBS
✓ docs in 43s (ID 140002064615)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Install just
  ✓ Set up Python
  ✓ Build and validate docs
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ core-wheel in 27s (ID 140002065096)
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
✓ lint in 4m54s (ID 140002347998)
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
* test (8) (ID 140002348205)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (6) (ID 140002348206)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (7) (ID 140002348215)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (4) (ID 140002348218)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (5) (ID 140002348235)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (1) (ID 140002348268)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (3) (ID 140002348276)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (2) (ID 140002348307)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
docs: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0c0wIawAAAACOXf5NpvwsR4nFqoZbJwHEQ08xRURHRTE2MjAARWRnZQ==
docs: .github#7

! Failed to restore: Cache service responded with 400
docs: .github#26

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache/restore@v4, actions/checkout@v4, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
core-wheel: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache@v4, actions/checkout@v4, actions/download-artifact@v4, actions/setup-go@v5, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
lint: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0jE0IawAAAADNcL55q1IlRLnjbGxMCbSlUEhMMzBFREdFMDQxNwBFZGdl
lint: .github#9

! Failed to restore: Cache service responded with 400
lint: .github#54

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Master Gate · 45846683375
Triggered via push about 7 minutes ago

JOBS
✓ docs in 43s (ID 140002064615)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Install just
  ✓ Set up Python
  ✓ Build and validate docs
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ core-wheel in 27s (ID 140002065096)
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
✓ lint in 4m54s (ID 140002347998)
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
* test (8) (ID 140002348205)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (6) (ID 140002348206)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (7) (ID 140002348215)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (4) (ID 140002348218)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (5) (ID 140002348235)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (1) (ID 140002348268)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (3) (ID 140002348276)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (2) (ID 140002348307)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
docs: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0c0wIawAAAACOXf5NpvwsR4nFqoZbJwHEQ08xRURHRTE2MjAARWRnZQ==
docs: .github#7

! Failed to restore: Cache service responded with 400
docs: .github#26

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache/restore@v4, actions/checkout@v4, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
core-wheel: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache@v4, actions/checkout@v4, actions/download-artifact@v4, actions/setup-go@v5, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
lint: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0jE0IawAAAADNcL55q1IlRLnjbGxMCbSlUEhMMzBFREdFMDQxNwBFZGdl
lint: .github#9

! Failed to restore: Cache service responded with 400
lint: .github#54

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Master Gate · 45846683375
Triggered via push about 7 minutes ago

JOBS
✓ docs in 43s (ID 140002064615)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Install just
  ✓ Set up Python
  ✓ Build and validate docs
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ core-wheel in 27s (ID 140002065096)
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
✓ lint in 4m54s (ID 140002347998)
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
* test (8) (ID 140002348205)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (6) (ID 140002348206)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (7) (ID 140002348215)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (4) (ID 140002348218)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (5) (ID 140002348235)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (1) (ID 140002348268)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (3) (ID 140002348276)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (2) (ID 140002348307)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
docs: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0c0wIawAAAACOXf5NpvwsR4nFqoZbJwHEQ08xRURHRTE2MjAARWRnZQ==
docs: .github#7

! Failed to restore: Cache service responded with 400
docs: .github#26

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache/restore@v4, actions/checkout@v4, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
core-wheel: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache@v4, actions/checkout@v4, actions/download-artifact@v4, actions/setup-go@v5, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
lint: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0jE0IawAAAADNcL55q1IlRLnjbGxMCbSlUEhMMzBFREdFMDQxNwBFZGdl
lint: .github#9

! Failed to restore: Cache service responded with 400
lint: .github#54

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Master Gate · 45846683375
Triggered via push about 7 minutes ago

JOBS
✓ docs in 43s (ID 140002064615)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Install just
  ✓ Set up Python
  ✓ Build and validate docs
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ core-wheel in 27s (ID 140002065096)
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
✓ lint in 4m54s (ID 140002347998)
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
* test (8) (ID 140002348205)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (6) (ID 140002348206)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (7) (ID 140002348215)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (4) (ID 140002348218)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (5) (ID 140002348235)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (1) (ID 140002348268)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (3) (ID 140002348276)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (2) (ID 140002348307)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
docs: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0c0wIawAAAACOXf5NpvwsR4nFqoZbJwHEQ08xRURHRTE2MjAARWRnZQ==
docs: .github#7

! Failed to restore: Cache service responded with 400
docs: .github#26

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache/restore@v4, actions/checkout@v4, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
core-wheel: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache@v4, actions/checkout@v4, actions/download-artifact@v4, actions/setup-go@v5, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
lint: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0jE0IawAAAADNcL55q1IlRLnjbGxMCbSlUEhMMzBFREdFMDQxNwBFZGdl
lint: .github#9

! Failed to restore: Cache service responded with 400
lint: .github#54

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Master Gate · 45846683375
Triggered via push about 7 minutes ago

JOBS
✓ docs in 43s (ID 140002064615)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Install just
  ✓ Set up Python
  ✓ Build and validate docs
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ core-wheel in 27s (ID 140002065096)
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
✓ lint in 4m54s (ID 140002347998)
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
* test (8) (ID 140002348205)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (6) (ID 140002348206)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (7) (ID 140002348215)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (4) (ID 140002348218)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (5) (ID 140002348235)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (1) (ID 140002348268)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (3) (ID 140002348276)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (2) (ID 140002348307)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
docs: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0c0wIawAAAACOXf5NpvwsR4nFqoZbJwHEQ08xRURHRTE2MjAARWRnZQ==
docs: .github#7

! Failed to restore: Cache service responded with 400
docs: .github#26

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache/restore@v4, actions/checkout@v4, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
core-wheel: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache@v4, actions/checkout@v4, actions/download-artifact@v4, actions/setup-go@v5, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
lint: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0jE0IawAAAADNcL55q1IlRLnjbGxMCbSlUEhMMzBFREdFMDQxNwBFZGdl
lint: .github#9

! Failed to restore: Cache service responded with 400
lint: .github#54

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Master Gate · 45846683375
Triggered via push about 7 minutes ago

JOBS
✓ docs in 43s (ID 140002064615)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Install just
  ✓ Set up Python
  ✓ Build and validate docs
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ core-wheel in 27s (ID 140002065096)
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
✓ lint in 4m54s (ID 140002347998)
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
* test (8) (ID 140002348205)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (6) (ID 140002348206)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (7) (ID 140002348215)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (4) (ID 140002348218)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (5) (ID 140002348235)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (1) (ID 140002348268)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (3) (ID 140002348276)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (2) (ID 140002348307)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
docs: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0c0wIawAAAACOXf5NpvwsR4nFqoZbJwHEQ08xRURHRTE2MjAARWRnZQ==
docs: .github#7

! Failed to restore: Cache service responded with 400
docs: .github#26

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache/restore@v4, actions/checkout@v4, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
core-wheel: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache@v4, actions/checkout@v4, actions/download-artifact@v4, actions/setup-go@v5, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
lint: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0jE0IawAAAADNcL55q1IlRLnjbGxMCbSlUEhMMzBFREdFMDQxNwBFZGdl
lint: .github#9

! Failed to restore: Cache service responded with 400
lint: .github#54

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Master Gate · 45846683375
Triggered via push about 7 minutes ago

JOBS
✓ docs in 43s (ID 140002064615)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Install just
  ✓ Set up Python
  ✓ Build and validate docs
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ core-wheel in 27s (ID 140002065096)
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
✓ lint in 4m54s (ID 140002347998)
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
* test (8) (ID 140002348205)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (6) (ID 140002348206)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (7) (ID 140002348215)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (4) (ID 140002348218)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (5) (ID 140002348235)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (1) (ID 140002348268)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (3) (ID 140002348276)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (2) (ID 140002348307)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
docs: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0c0wIawAAAACOXf5NpvwsR4nFqoZbJwHEQ08xRURHRTE2MjAARWRnZQ==
docs: .github#7

! Failed to restore: Cache service responded with 400
docs: .github#26

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache/restore@v4, actions/checkout@v4, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
core-wheel: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache@v4, actions/checkout@v4, actions/download-artifact@v4, actions/setup-go@v5, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
lint: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0jE0IawAAAADNcL55q1IlRLnjbGxMCbSlUEhMMzBFREdFMDQxNwBFZGdl
lint: .github#9

! Failed to restore: Cache service responded with 400
lint: .github#54

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Master Gate · 45846683375
Triggered via push about 7 minutes ago

JOBS
✓ docs in 43s (ID 140002064615)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Install just
  ✓ Set up Python
  ✓ Build and validate docs
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ core-wheel in 27s (ID 140002065096)
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
✓ lint in 4m54s (ID 140002347998)
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
* test (8) (ID 140002348205)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (6) (ID 140002348206)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (7) (ID 140002348215)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (4) (ID 140002348218)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (5) (ID 140002348235)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (1) (ID 140002348268)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (3) (ID 140002348276)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (2) (ID 140002348307)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
docs: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0c0wIawAAAACOXf5NpvwsR4nFqoZbJwHEQ08xRURHRTE2MjAARWRnZQ==
docs: .github#7

! Failed to restore: Cache service responded with 400
docs: .github#26

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache/restore@v4, actions/checkout@v4, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
core-wheel: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache@v4, actions/checkout@v4, actions/download-artifact@v4, actions/setup-go@v5, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
lint: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0jE0IawAAAADNcL55q1IlRLnjbGxMCbSlUEhMMzBFREdFMDQxNwBFZGdl
lint: .github#9

! Failed to restore: Cache service responded with 400
lint: .github#54

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Master Gate · 45846683375
Triggered via push about 7 minutes ago

JOBS
✓ docs in 43s (ID 140002064615)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Install just
  ✓ Set up Python
  ✓ Build and validate docs
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ core-wheel in 27s (ID 140002065096)
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
✓ lint in 4m54s (ID 140002347998)
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
* test (8) (ID 140002348205)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (6) (ID 140002348206)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (7) (ID 140002348215)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (4) (ID 140002348218)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (5) (ID 140002348235)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (1) (ID 140002348268)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (3) (ID 140002348276)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (2) (ID 140002348307)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
docs: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0c0wIawAAAACOXf5NpvwsR4nFqoZbJwHEQ08xRURHRTE2MjAARWRnZQ==
docs: .github#7

! Failed to restore: Cache service responded with 400
docs: .github#26

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache/restore@v4, actions/checkout@v4, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
core-wheel: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache@v4, actions/checkout@v4, actions/download-artifact@v4, actions/setup-go@v5, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
lint: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0jE0IawAAAADNcL55q1IlRLnjbGxMCbSlUEhMMzBFREdFMDQxNwBFZGdl
lint: .github#9

! Failed to restore: Cache service responded with 400
lint: .github#54

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Master Gate · 45846683375
Triggered via push about 7 minutes ago

JOBS
✓ docs in 43s (ID 140002064615)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Install just
  ✓ Set up Python
  ✓ Build and validate docs
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ core-wheel in 27s (ID 140002065096)
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
✓ lint in 4m54s (ID 140002347998)
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
* test (8) (ID 140002348205)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (6) (ID 140002348206)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (7) (ID 140002348215)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (4) (ID 140002348218)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (5) (ID 140002348235)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (1) (ID 140002348268)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (3) (ID 140002348276)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (2) (ID 140002348307)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
docs: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0c0wIawAAAACOXf5NpvwsR4nFqoZbJwHEQ08xRURHRTE2MjAARWRnZQ==
docs: .github#7

! Failed to restore: Cache service responded with 400
docs: .github#26

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache/restore@v4, actions/checkout@v4, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
core-wheel: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache@v4, actions/checkout@v4, actions/download-artifact@v4, actions/setup-go@v5, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
lint: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0jE0IawAAAADNcL55q1IlRLnjbGxMCbSlUEhMMzBFREdFMDQxNwBFZGdl
lint: .github#9

! Failed to restore: Cache service responded with 400
lint: .github#54

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Master Gate · 45846683375
Triggered via push about 8 minutes ago

JOBS
✓ docs in 43s (ID 140002064615)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Install just
  ✓ Set up Python
  ✓ Build and validate docs
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ core-wheel in 27s (ID 140002065096)
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
✓ lint in 4m54s (ID 140002347998)
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
* test (8) (ID 140002348205)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (6) (ID 140002348206)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (7) (ID 140002348215)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (4) (ID 140002348218)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (5) (ID 140002348235)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (1) (ID 140002348268)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (3) (ID 140002348276)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (2) (ID 140002348307)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
docs: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0c0wIawAAAACOXf5NpvwsR4nFqoZbJwHEQ08xRURHRTE2MjAARWRnZQ==
docs: .github#7

! Failed to restore: Cache service responded with 400
docs: .github#26

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache/restore@v4, actions/checkout@v4, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
core-wheel: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache@v4, actions/checkout@v4, actions/download-artifact@v4, actions/setup-go@v5, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
lint: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0jE0IawAAAADNcL55q1IlRLnjbGxMCbSlUEhMMzBFREdFMDQxNwBFZGdl
lint: .github#9

! Failed to restore: Cache service responded with 400
lint: .github#54

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Master Gate · 45846683375
Triggered via push about 8 minutes ago

JOBS
✓ docs in 43s (ID 140002064615)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Install just
  ✓ Set up Python
  ✓ Build and validate docs
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ core-wheel in 27s (ID 140002065096)
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
✓ lint in 4m54s (ID 140002347998)
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
* test (8) (ID 140002348205)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (6) (ID 140002348206)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (7) (ID 140002348215)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (4) (ID 140002348218)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (5) (ID 140002348235)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (1) (ID 140002348268)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (3) (ID 140002348276)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (2) (ID 140002348307)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
docs: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0c0wIawAAAACOXf5NpvwsR4nFqoZbJwHEQ08xRURHRTE2MjAARWRnZQ==
docs: .github#7

! Failed to restore: Cache service responded with 400
docs: .github#26

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache/restore@v4, actions/checkout@v4, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
core-wheel: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache@v4, actions/checkout@v4, actions/download-artifact@v4, actions/setup-go@v5, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
lint: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0jE0IawAAAADNcL55q1IlRLnjbGxMCbSlUEhMMzBFREdFMDQxNwBFZGdl
lint: .github#9

! Failed to restore: Cache service responded with 400
lint: .github#54

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Master Gate · 45846683375
Triggered via push about 8 minutes ago

JOBS
✓ docs in 43s (ID 140002064615)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Install just
  ✓ Set up Python
  ✓ Build and validate docs
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ core-wheel in 27s (ID 140002065096)
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
✓ lint in 4m54s (ID 140002347998)
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
* test (8) (ID 140002348205)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (6) (ID 140002348206)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (7) (ID 140002348215)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (4) (ID 140002348218)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (5) (ID 140002348235)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (1) (ID 140002348268)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (3) (ID 140002348276)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (2) (ID 140002348307)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
docs: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0c0wIawAAAACOXf5NpvwsR4nFqoZbJwHEQ08xRURHRTE2MjAARWRnZQ==
docs: .github#7

! Failed to restore: Cache service responded with 400
docs: .github#26

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache/restore@v4, actions/checkout@v4, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
core-wheel: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache@v4, actions/checkout@v4, actions/download-artifact@v4, actions/setup-go@v5, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
lint: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0jE0IawAAAADNcL55q1IlRLnjbGxMCbSlUEhMMzBFREdFMDQxNwBFZGdl
lint: .github#9

! Failed to restore: Cache service responded with 400
lint: .github#54

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Master Gate · 45846683375
Triggered via push about 8 minutes ago

JOBS
✓ docs in 43s (ID 140002064615)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Install just
  ✓ Set up Python
  ✓ Build and validate docs
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ core-wheel in 27s (ID 140002065096)
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
✓ lint in 4m54s (ID 140002347998)
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
* test (8) (ID 140002348205)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (6) (ID 140002348206)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (7) (ID 140002348215)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (4) (ID 140002348218)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (5) (ID 140002348235)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (1) (ID 140002348268)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (3) (ID 140002348276)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (2) (ID 140002348307)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
docs: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0c0wIawAAAACOXf5NpvwsR4nFqoZbJwHEQ08xRURHRTE2MjAARWRnZQ==
docs: .github#7

! Failed to restore: Cache service responded with 400
docs: .github#26

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache/restore@v4, actions/checkout@v4, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
core-wheel: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache@v4, actions/checkout@v4, actions/download-artifact@v4, actions/setup-go@v5, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
lint: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0jE0IawAAAADNcL55q1IlRLnjbGxMCbSlUEhMMzBFREdFMDQxNwBFZGdl
lint: .github#9

! Failed to restore: Cache service responded with 400
lint: .github#54

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Master Gate · 45846683375
Triggered via push about 8 minutes ago

JOBS
✓ docs in 43s (ID 140002064615)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Install just
  ✓ Set up Python
  ✓ Build and validate docs
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ core-wheel in 27s (ID 140002065096)
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
✓ lint in 4m54s (ID 140002347998)
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
* test (8) (ID 140002348205)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (6) (ID 140002348206)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (7) (ID 140002348215)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (4) (ID 140002348218)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (5) (ID 140002348235)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (1) (ID 140002348268)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (3) (ID 140002348276)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (2) (ID 140002348307)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
docs: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0c0wIawAAAACOXf5NpvwsR4nFqoZbJwHEQ08xRURHRTE2MjAARWRnZQ==
docs: .github#7

! Failed to restore: Cache service responded with 400
docs: .github#26

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache/restore@v4, actions/checkout@v4, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
core-wheel: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache@v4, actions/checkout@v4, actions/download-artifact@v4, actions/setup-go@v5, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
lint: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0jE0IawAAAADNcL55q1IlRLnjbGxMCbSlUEhMMzBFREdFMDQxNwBFZGdl
lint: .github#9

! Failed to restore: Cache service responded with 400
lint: .github#54

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Master Gate · 45846683375
Triggered via push about 8 minutes ago

JOBS
✓ docs in 43s (ID 140002064615)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Install just
  ✓ Set up Python
  ✓ Build and validate docs
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ core-wheel in 27s (ID 140002065096)
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
✓ lint in 4m54s (ID 140002347998)
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
* test (8) (ID 140002348205)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (6) (ID 140002348206)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (7) (ID 140002348215)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (4) (ID 140002348218)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (5) (ID 140002348235)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (1) (ID 140002348268)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (3) (ID 140002348276)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (2) (ID 140002348307)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
docs: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0c0wIawAAAACOXf5NpvwsR4nFqoZbJwHEQ08xRURHRTE2MjAARWRnZQ==
docs: .github#7

! Failed to restore: Cache service responded with 400
docs: .github#26

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache/restore@v4, actions/checkout@v4, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
core-wheel: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache@v4, actions/checkout@v4, actions/download-artifact@v4, actions/setup-go@v5, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
lint: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0jE0IawAAAADNcL55q1IlRLnjbGxMCbSlUEhMMzBFREdFMDQxNwBFZGdl
lint: .github#9

! Failed to restore: Cache service responded with 400
lint: .github#54

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Master Gate · 45846683375
Triggered via push about 8 minutes ago

JOBS
✓ docs in 43s (ID 140002064615)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Install just
  ✓ Set up Python
  ✓ Build and validate docs
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ core-wheel in 27s (ID 140002065096)
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
✓ lint in 4m54s (ID 140002347998)
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
* test (8) (ID 140002348205)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (6) (ID 140002348206)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (7) (ID 140002348215)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (4) (ID 140002348218)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (5) (ID 140002348235)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (1) (ID 140002348268)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (3) (ID 140002348276)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (2) (ID 140002348307)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
docs: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0c0wIawAAAACOXf5NpvwsR4nFqoZbJwHEQ08xRURHRTE2MjAARWRnZQ==
docs: .github#7

! Failed to restore: Cache service responded with 400
docs: .github#26

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache/restore@v4, actions/checkout@v4, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
core-wheel: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache@v4, actions/checkout@v4, actions/download-artifact@v4, actions/setup-go@v5, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
lint: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0jE0IawAAAADNcL55q1IlRLnjbGxMCbSlUEhMMzBFREdFMDQxNwBFZGdl
lint: .github#9

! Failed to restore: Cache service responded with 400
lint: .github#54

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Master Gate · 45846683375
Triggered via push about 8 minutes ago

JOBS
✓ docs in 43s (ID 140002064615)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Install just
  ✓ Set up Python
  ✓ Build and validate docs
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ core-wheel in 27s (ID 140002065096)
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
✓ lint in 4m54s (ID 140002347998)
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
* test (8) (ID 140002348205)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (6) (ID 140002348206)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (7) (ID 140002348215)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (4) (ID 140002348218)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (5) (ID 140002348235)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (1) (ID 140002348268)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (3) (ID 140002348276)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (2) (ID 140002348307)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
docs: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0c0wIawAAAACOXf5NpvwsR4nFqoZbJwHEQ08xRURHRTE2MjAARWRnZQ==
docs: .github#7

! Failed to restore: Cache service responded with 400
docs: .github#26

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache/restore@v4, actions/checkout@v4, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
core-wheel: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache@v4, actions/checkout@v4, actions/download-artifact@v4, actions/setup-go@v5, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
lint: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0jE0IawAAAADNcL55q1IlRLnjbGxMCbSlUEhMMzBFREdFMDQxNwBFZGdl
lint: .github#9

! Failed to restore: Cache service responded with 400
lint: .github#54

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Master Gate · 45846683375
Triggered via push about 8 minutes ago

JOBS
✓ docs in 43s (ID 140002064615)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Install just
  ✓ Set up Python
  ✓ Build and validate docs
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ core-wheel in 27s (ID 140002065096)
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
✓ lint in 4m54s (ID 140002347998)
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
* test (8) (ID 140002348205)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (6) (ID 140002348206)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (7) (ID 140002348215)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (4) (ID 140002348218)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (5) (ID 140002348235)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (1) (ID 140002348268)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (3) (ID 140002348276)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (2) (ID 140002348307)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
docs: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0c0wIawAAAACOXf5NpvwsR4nFqoZbJwHEQ08xRURHRTE2MjAARWRnZQ==
docs: .github#7

! Failed to restore: Cache service responded with 400
docs: .github#26

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache/restore@v4, actions/checkout@v4, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
core-wheel: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache@v4, actions/checkout@v4, actions/download-artifact@v4, actions/setup-go@v5, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
lint: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0jE0IawAAAADNcL55q1IlRLnjbGxMCbSlUEhMMzBFREdFMDQxNwBFZGdl
lint: .github#9

! Failed to restore: Cache service responded with 400
lint: .github#54

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Master Gate · 45846683375
Triggered via push about 8 minutes ago

JOBS
✓ docs in 43s (ID 140002064615)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Install just
  ✓ Set up Python
  ✓ Build and validate docs
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ core-wheel in 27s (ID 140002065096)
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
✓ lint in 4m54s (ID 140002347998)
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
* test (8) (ID 140002348205)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (6) (ID 140002348206)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (7) (ID 140002348215)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (4) (ID 140002348218)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (5) (ID 140002348235)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (1) (ID 140002348268)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (3) (ID 140002348276)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (2) (ID 140002348307)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
docs: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0c0wIawAAAACOXf5NpvwsR4nFqoZbJwHEQ08xRURHRTE2MjAARWRnZQ==
docs: .github#7

! Failed to restore: Cache service responded with 400
docs: .github#26

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache/restore@v4, actions/checkout@v4, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
core-wheel: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache@v4, actions/checkout@v4, actions/download-artifact@v4, actions/setup-go@v5, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
lint: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0jE0IawAAAADNcL55q1IlRLnjbGxMCbSlUEhMMzBFREdFMDQxNwBFZGdl
lint: .github#9

! Failed to restore: Cache service responded with 400
lint: .github#54

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Master Gate · 45846683375
Triggered via push about 8 minutes ago

JOBS
✓ docs in 43s (ID 140002064615)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Install just
  ✓ Set up Python
  ✓ Build and validate docs
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ core-wheel in 27s (ID 140002065096)
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
✓ lint in 4m54s (ID 140002347998)
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
* test (8) (ID 140002348205)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (6) (ID 140002348206)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (7) (ID 140002348215)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (4) (ID 140002348218)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (5) (ID 140002348235)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (1) (ID 140002348268)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (3) (ID 140002348276)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (2) (ID 140002348307)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
docs: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0c0wIawAAAACOXf5NpvwsR4nFqoZbJwHEQ08xRURHRTE2MjAARWRnZQ==
docs: .github#7

! Failed to restore: Cache service responded with 400
docs: .github#26

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache/restore@v4, actions/checkout@v4, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
core-wheel: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache@v4, actions/checkout@v4, actions/download-artifact@v4, actions/setup-go@v5, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
lint: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0jE0IawAAAADNcL55q1IlRLnjbGxMCbSlUEhMMzBFREdFMDQxNwBFZGdl
lint: .github#9

! Failed to restore: Cache service responded with 400
lint: .github#54

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Master Gate · 45846683375
Triggered via push about 9 minutes ago

JOBS
✓ docs in 43s (ID 140002064615)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Install just
  ✓ Set up Python
  ✓ Build and validate docs
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ core-wheel in 27s (ID 140002065096)
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
✓ lint in 4m54s (ID 140002347998)
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
* test (8) (ID 140002348205)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (6) (ID 140002348206)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (7) (ID 140002348215)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (4) (ID 140002348218)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (5) (ID 140002348235)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (1) (ID 140002348268)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (3) (ID 140002348276)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (2) (ID 140002348307)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
docs: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0c0wIawAAAACOXf5NpvwsR4nFqoZbJwHEQ08xRURHRTE2MjAARWRnZQ==
docs: .github#7

! Failed to restore: Cache service responded with 400
docs: .github#26

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache/restore@v4, actions/checkout@v4, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
core-wheel: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache@v4, actions/checkout@v4, actions/download-artifact@v4, actions/setup-go@v5, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
lint: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0jE0IawAAAADNcL55q1IlRLnjbGxMCbSlUEhMMzBFREdFMDQxNwBFZGdl
lint: .github#9

! Failed to restore: Cache service responded with 400
lint: .github#54

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Master Gate · 45846683375
Triggered via push about 9 minutes ago

JOBS
✓ docs in 43s (ID 140002064615)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Install just
  ✓ Set up Python
  ✓ Build and validate docs
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ core-wheel in 27s (ID 140002065096)
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
✓ lint in 4m54s (ID 140002347998)
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
* test (8) (ID 140002348205)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (6) (ID 140002348206)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (7) (ID 140002348215)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (4) (ID 140002348218)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (5) (ID 140002348235)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (1) (ID 140002348268)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (3) (ID 140002348276)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (2) (ID 140002348307)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
docs: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0c0wIawAAAACOXf5NpvwsR4nFqoZbJwHEQ08xRURHRTE2MjAARWRnZQ==
docs: .github#7

! Failed to restore: Cache service responded with 400
docs: .github#26

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache/restore@v4, actions/checkout@v4, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
core-wheel: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache@v4, actions/checkout@v4, actions/download-artifact@v4, actions/setup-go@v5, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
lint: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0jE0IawAAAADNcL55q1IlRLnjbGxMCbSlUEhMMzBFREdFMDQxNwBFZGdl
lint: .github#9

! Failed to restore: Cache service responded with 400
lint: .github#54

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Master Gate · 45846683375
Triggered via push about 9 minutes ago

JOBS
✓ docs in 43s (ID 140002064615)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Install just
  ✓ Set up Python
  ✓ Build and validate docs
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ core-wheel in 27s (ID 140002065096)
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
✓ lint in 4m54s (ID 140002347998)
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
* test (8) (ID 140002348205)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (6) (ID 140002348206)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (7) (ID 140002348215)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (4) (ID 140002348218)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (5) (ID 140002348235)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (1) (ID 140002348268)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (3) (ID 140002348276)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (2) (ID 140002348307)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
docs: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0c0wIawAAAACOXf5NpvwsR4nFqoZbJwHEQ08xRURHRTE2MjAARWRnZQ==
docs: .github#7

! Failed to restore: Cache service responded with 400
docs: .github#26

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache/restore@v4, actions/checkout@v4, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
core-wheel: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache@v4, actions/checkout@v4, actions/download-artifact@v4, actions/setup-go@v5, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
lint: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0jE0IawAAAADNcL55q1IlRLnjbGxMCbSlUEhMMzBFREdFMDQxNwBFZGdl
lint: .github#9

! Failed to restore: Cache service responded with 400
lint: .github#54

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Master Gate · 45846683375
Triggered via push about 9 minutes ago

JOBS
✓ docs in 43s (ID 140002064615)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Install just
  ✓ Set up Python
  ✓ Build and validate docs
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ core-wheel in 27s (ID 140002065096)
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
✓ lint in 4m54s (ID 140002347998)
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
* test (8) (ID 140002348205)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (6) (ID 140002348206)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (7) (ID 140002348215)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (4) (ID 140002348218)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
✓ test (5) in 8m38s (ID 140002348235)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* test (1) (ID 140002348268)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (3) (ID 140002348276)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (2) (ID 140002348307)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
docs: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0c0wIawAAAACOXf5NpvwsR4nFqoZbJwHEQ08xRURHRTE2MjAARWRnZQ==
docs: .github#7

! Failed to restore: Cache service responded with 400
docs: .github#26

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache/restore@v4, actions/checkout@v4, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
core-wheel: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache@v4, actions/checkout@v4, actions/download-artifact@v4, actions/setup-go@v5, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
lint: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0jE0IawAAAADNcL55q1IlRLnjbGxMCbSlUEhMMzBFREdFMDQxNwBFZGdl
lint: .github#9

! Failed to restore: Cache service responded with 400
lint: .github#54

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
test (5): .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0bU4IawAAAAB+SZv8gyN5Q6bHYNkba7GRUEhYMzFFREdFMDUyMABFZGdl
test (5): .github#9

! Failed to restore: Cache service responded with 400
test (5): .github#54

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Master Gate · 45846683375
Triggered via push about 9 minutes ago

JOBS
✓ docs in 43s (ID 140002064615)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Install just
  ✓ Set up Python
  ✓ Build and validate docs
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ core-wheel in 27s (ID 140002065096)
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
✓ lint in 4m54s (ID 140002347998)
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
* test (8) (ID 140002348205)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (6) (ID 140002348206)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (7) (ID 140002348215)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (4) (ID 140002348218)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
✓ test (5) in 8m38s (ID 140002348235)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* test (1) (ID 140002348268)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (3) (ID 140002348276)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (2) (ID 140002348307)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
docs: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0c0wIawAAAACOXf5NpvwsR4nFqoZbJwHEQ08xRURHRTE2MjAARWRnZQ==
docs: .github#7

! Failed to restore: Cache service responded with 400
docs: .github#26

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache/restore@v4, actions/checkout@v4, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
core-wheel: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache@v4, actions/checkout@v4, actions/download-artifact@v4, actions/setup-go@v5, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
lint: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0jE0IawAAAADNcL55q1IlRLnjbGxMCbSlUEhMMzBFREdFMDQxNwBFZGdl
lint: .github#9

! Failed to restore: Cache service responded with 400
lint: .github#54

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
test (5): .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0bU4IawAAAAB+SZv8gyN5Q6bHYNkba7GRUEhYMzFFREdFMDUyMABFZGdl
test (5): .github#9

! Failed to restore: Cache service responded with 400
test (5): .github#54

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Master Gate · 45846683375
Triggered via push about 9 minutes ago

JOBS
✓ docs in 43s (ID 140002064615)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Install just
  ✓ Set up Python
  ✓ Build and validate docs
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ core-wheel in 27s (ID 140002065096)
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
✓ lint in 4m54s (ID 140002347998)
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
* test (8) (ID 140002348205)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (6) (ID 140002348206)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (7) (ID 140002348215)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (4) (ID 140002348218)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
✓ test (5) in 8m38s (ID 140002348235)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* test (1) (ID 140002348268)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (3) (ID 140002348276)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (2) (ID 140002348307)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
docs: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0c0wIawAAAACOXf5NpvwsR4nFqoZbJwHEQ08xRURHRTE2MjAARWRnZQ==
docs: .github#7

! Failed to restore: Cache service responded with 400
docs: .github#26

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache/restore@v4, actions/checkout@v4, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
core-wheel: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache@v4, actions/checkout@v4, actions/download-artifact@v4, actions/setup-go@v5, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
lint: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0jE0IawAAAADNcL55q1IlRLnjbGxMCbSlUEhMMzBFREdFMDQxNwBFZGdl
lint: .github#9

! Failed to restore: Cache service responded with 400
lint: .github#54

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
test (5): .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0bU4IawAAAAB+SZv8gyN5Q6bHYNkba7GRUEhYMzFFREdFMDUyMABFZGdl
test (5): .github#9

! Failed to restore: Cache service responded with 400
test (5): .github#54

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Master Gate · 45846683375
Triggered via push about 9 minutes ago

JOBS
✓ docs in 43s (ID 140002064615)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Install just
  ✓ Set up Python
  ✓ Build and validate docs
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ core-wheel in 27s (ID 140002065096)
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
✓ lint in 4m54s (ID 140002347998)
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
* test (8) (ID 140002348205)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (6) (ID 140002348206)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (7) (ID 140002348215)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (4) (ID 140002348218)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
✓ test (5) in 8m38s (ID 140002348235)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* test (1) (ID 140002348268)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (3) (ID 140002348276)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (2) (ID 140002348307)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
docs: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0c0wIawAAAACOXf5NpvwsR4nFqoZbJwHEQ08xRURHRTE2MjAARWRnZQ==
docs: .github#7

! Failed to restore: Cache service responded with 400
docs: .github#26

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache/restore@v4, actions/checkout@v4, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
core-wheel: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache@v4, actions/checkout@v4, actions/download-artifact@v4, actions/setup-go@v5, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
lint: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0jE0IawAAAADNcL55q1IlRLnjbGxMCbSlUEhMMzBFREdFMDQxNwBFZGdl
lint: .github#9

! Failed to restore: Cache service responded with 400
lint: .github#54

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
test (5): .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0bU4IawAAAAB+SZv8gyN5Q6bHYNkba7GRUEhYMzFFREdFMDUyMABFZGdl
test (5): .github#9

! Failed to restore: Cache service responded with 400
test (5): .github#54

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Master Gate · 45846683375
Triggered via push about 9 minutes ago

JOBS
✓ docs in 43s (ID 140002064615)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Install just
  ✓ Set up Python
  ✓ Build and validate docs
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ core-wheel in 27s (ID 140002065096)
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
✓ lint in 4m54s (ID 140002347998)
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
* test (8) (ID 140002348205)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (6) (ID 140002348206)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (7) (ID 140002348215)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (4) (ID 140002348218)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
✓ test (5) in 8m38s (ID 140002348235)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* test (1) (ID 140002348268)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (3) (ID 140002348276)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (2) (ID 140002348307)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
docs: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0c0wIawAAAACOXf5NpvwsR4nFqoZbJwHEQ08xRURHRTE2MjAARWRnZQ==
docs: .github#7

! Failed to restore: Cache service responded with 400
docs: .github#26

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache/restore@v4, actions/checkout@v4, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
core-wheel: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache@v4, actions/checkout@v4, actions/download-artifact@v4, actions/setup-go@v5, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
lint: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0jE0IawAAAADNcL55q1IlRLnjbGxMCbSlUEhMMzBFREdFMDQxNwBFZGdl
lint: .github#9

! Failed to restore: Cache service responded with 400
lint: .github#54

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
test (5): .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0bU4IawAAAAB+SZv8gyN5Q6bHYNkba7GRUEhYMzFFREdFMDUyMABFZGdl
test (5): .github#9

! Failed to restore: Cache service responded with 400
test (5): .github#54

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Master Gate · 45846683375
Triggered via push about 9 minutes ago

JOBS
✓ docs in 43s (ID 140002064615)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Install just
  ✓ Set up Python
  ✓ Build and validate docs
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ core-wheel in 27s (ID 140002065096)
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
✓ lint in 4m54s (ID 140002347998)
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
* test (8) (ID 140002348205)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (6) (ID 140002348206)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (7) (ID 140002348215)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (4) (ID 140002348218)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
✓ test (5) in 8m38s (ID 140002348235)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* test (1) (ID 140002348268)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (3) (ID 140002348276)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (2) (ID 140002348307)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
docs: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0c0wIawAAAACOXf5NpvwsR4nFqoZbJwHEQ08xRURHRTE2MjAARWRnZQ==
docs: .github#7

! Failed to restore: Cache service responded with 400
docs: .github#26

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache/restore@v4, actions/checkout@v4, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
core-wheel: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache@v4, actions/checkout@v4, actions/download-artifact@v4, actions/setup-go@v5, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
lint: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0jE0IawAAAADNcL55q1IlRLnjbGxMCbSlUEhMMzBFREdFMDQxNwBFZGdl
lint: .github#9

! Failed to restore: Cache service responded with 400
lint: .github#54

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
test (5): .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0bU4IawAAAAB+SZv8gyN5Q6bHYNkba7GRUEhYMzFFREdFMDUyMABFZGdl
test (5): .github#9

! Failed to restore: Cache service responded with 400
test (5): .github#54

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Master Gate · 45846683375
Triggered via push about 9 minutes ago

JOBS
✓ docs in 43s (ID 140002064615)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Install just
  ✓ Set up Python
  ✓ Build and validate docs
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ core-wheel in 27s (ID 140002065096)
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
✓ lint in 4m54s (ID 140002347998)
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
* test (8) (ID 140002348205)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (6) (ID 140002348206)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (7) (ID 140002348215)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (4) (ID 140002348218)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
✓ test (5) in 8m38s (ID 140002348235)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* test (1) (ID 140002348268)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (3) (ID 140002348276)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (2) (ID 140002348307)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
docs: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0c0wIawAAAACOXf5NpvwsR4nFqoZbJwHEQ08xRURHRTE2MjAARWRnZQ==
docs: .github#7

! Failed to restore: Cache service responded with 400
docs: .github#26

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache/restore@v4, actions/checkout@v4, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
core-wheel: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache@v4, actions/checkout@v4, actions/download-artifact@v4, actions/setup-go@v5, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
lint: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0jE0IawAAAADNcL55q1IlRLnjbGxMCbSlUEhMMzBFREdFMDQxNwBFZGdl
lint: .github#9

! Failed to restore: Cache service responded with 400
lint: .github#54

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
test (5): .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0bU4IawAAAAB+SZv8gyN5Q6bHYNkba7GRUEhYMzFFREdFMDUyMABFZGdl
test (5): .github#9

! Failed to restore: Cache service responded with 400
test (5): .github#54

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Master Gate · 45846683375
Triggered via push about 9 minutes ago

JOBS
✓ docs in 43s (ID 140002064615)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Install just
  ✓ Set up Python
  ✓ Build and validate docs
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ core-wheel in 27s (ID 140002065096)
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
✓ lint in 4m54s (ID 140002347998)
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
* test (8) (ID 140002348205)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (6) (ID 140002348206)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (7) (ID 140002348215)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (4) (ID 140002348218)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
✓ test (5) in 8m38s (ID 140002348235)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* test (1) (ID 140002348268)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (3) (ID 140002348276)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (2) (ID 140002348307)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
docs: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0c0wIawAAAACOXf5NpvwsR4nFqoZbJwHEQ08xRURHRTE2MjAARWRnZQ==
docs: .github#7

! Failed to restore: Cache service responded with 400
docs: .github#26

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache/restore@v4, actions/checkout@v4, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
core-wheel: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache@v4, actions/checkout@v4, actions/download-artifact@v4, actions/setup-go@v5, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
lint: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0jE0IawAAAADNcL55q1IlRLnjbGxMCbSlUEhMMzBFREdFMDQxNwBFZGdl
lint: .github#9

! Failed to restore: Cache service responded with 400
lint: .github#54

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
test (5): .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0bU4IawAAAAB+SZv8gyN5Q6bHYNkba7GRUEhYMzFFREdFMDUyMABFZGdl
test (5): .github#9

! Failed to restore: Cache service responded with 400
test (5): .github#54

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Master Gate · 45846683375
Triggered via push about 9 minutes ago

JOBS
✓ docs in 43s (ID 140002064615)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Install just
  ✓ Set up Python
  ✓ Build and validate docs
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ core-wheel in 27s (ID 140002065096)
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
✓ lint in 4m54s (ID 140002347998)
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
* test (8) (ID 140002348205)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (6) (ID 140002348206)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (7) (ID 140002348215)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (4) (ID 140002348218)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
✓ test (5) in 8m38s (ID 140002348235)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* test (1) (ID 140002348268)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (3) (ID 140002348276)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (2) (ID 140002348307)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
docs: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0c0wIawAAAACOXf5NpvwsR4nFqoZbJwHEQ08xRURHRTE2MjAARWRnZQ==
docs: .github#7

! Failed to restore: Cache service responded with 400
docs: .github#26

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache/restore@v4, actions/checkout@v4, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
core-wheel: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache@v4, actions/checkout@v4, actions/download-artifact@v4, actions/setup-go@v5, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
lint: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0jE0IawAAAADNcL55q1IlRLnjbGxMCbSlUEhMMzBFREdFMDQxNwBFZGdl
lint: .github#9

! Failed to restore: Cache service responded with 400
lint: .github#54

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
test (5): .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0bU4IawAAAAB+SZv8gyN5Q6bHYNkba7GRUEhYMzFFREdFMDUyMABFZGdl
test (5): .github#9

! Failed to restore: Cache service responded with 400
test (5): .github#54

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Master Gate · 45846683375
Triggered via push about 10 minutes ago

JOBS
✓ docs in 43s (ID 140002064615)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Install just
  ✓ Set up Python
  ✓ Build and validate docs
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ core-wheel in 27s (ID 140002065096)
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
✓ lint in 4m54s (ID 140002347998)
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
* test (8) (ID 140002348205)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (6) (ID 140002348206)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (7) (ID 140002348215)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (4) (ID 140002348218)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
✓ test (5) in 8m38s (ID 140002348235)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* test (1) (ID 140002348268)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (3) (ID 140002348276)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (2) (ID 140002348307)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
docs: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0c0wIawAAAACOXf5NpvwsR4nFqoZbJwHEQ08xRURHRTE2MjAARWRnZQ==
docs: .github#7

! Failed to restore: Cache service responded with 400
docs: .github#26

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache/restore@v4, actions/checkout@v4, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
core-wheel: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache@v4, actions/checkout@v4, actions/download-artifact@v4, actions/setup-go@v5, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
lint: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0jE0IawAAAADNcL55q1IlRLnjbGxMCbSlUEhMMzBFREdFMDQxNwBFZGdl
lint: .github#9

! Failed to restore: Cache service responded with 400
lint: .github#54

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
test (5): .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0bU4IawAAAAB+SZv8gyN5Q6bHYNkba7GRUEhYMzFFREdFMDUyMABFZGdl
test (5): .github#9

! Failed to restore: Cache service responded with 400
test (5): .github#54

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Master Gate · 45846683375
Triggered via push about 10 minutes ago

JOBS
✓ docs in 43s (ID 140002064615)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Install just
  ✓ Set up Python
  ✓ Build and validate docs
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ core-wheel in 27s (ID 140002065096)
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
✓ lint in 4m54s (ID 140002347998)
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
* test (8) (ID 140002348205)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (6) (ID 140002348206)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (7) (ID 140002348215)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (4) (ID 140002348218)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
✓ test (5) in 8m38s (ID 140002348235)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* test (1) (ID 140002348268)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (3) (ID 140002348276)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (2) (ID 140002348307)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
docs: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0c0wIawAAAACOXf5NpvwsR4nFqoZbJwHEQ08xRURHRTE2MjAARWRnZQ==
docs: .github#7

! Failed to restore: Cache service responded with 400
docs: .github#26

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache/restore@v4, actions/checkout@v4, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
core-wheel: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache@v4, actions/checkout@v4, actions/download-artifact@v4, actions/setup-go@v5, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
lint: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0jE0IawAAAADNcL55q1IlRLnjbGxMCbSlUEhMMzBFREdFMDQxNwBFZGdl
lint: .github#9

! Failed to restore: Cache service responded with 400
lint: .github#54

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
test (5): .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0bU4IawAAAAB+SZv8gyN5Q6bHYNkba7GRUEhYMzFFREdFMDUyMABFZGdl
test (5): .github#9

! Failed to restore: Cache service responded with 400
test (5): .github#54

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Master Gate · 45846683375
Triggered via push about 10 minutes ago

JOBS
✓ docs in 43s (ID 140002064615)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Install just
  ✓ Set up Python
  ✓ Build and validate docs
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ core-wheel in 27s (ID 140002065096)
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
✓ lint in 4m54s (ID 140002347998)
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
* test (8) (ID 140002348205)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (6) (ID 140002348206)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (7) (ID 140002348215)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (4) (ID 140002348218)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
✓ test (5) in 8m38s (ID 140002348235)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* test (1) (ID 140002348268)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (3) (ID 140002348276)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (2) (ID 140002348307)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
docs: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0c0wIawAAAACOXf5NpvwsR4nFqoZbJwHEQ08xRURHRTE2MjAARWRnZQ==
docs: .github#7

! Failed to restore: Cache service responded with 400
docs: .github#26

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache/restore@v4, actions/checkout@v4, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
core-wheel: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache@v4, actions/checkout@v4, actions/download-artifact@v4, actions/setup-go@v5, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
lint: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0jE0IawAAAADNcL55q1IlRLnjbGxMCbSlUEhMMzBFREdFMDQxNwBFZGdl
lint: .github#9

! Failed to restore: Cache service responded with 400
lint: .github#54

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
test (5): .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0bU4IawAAAAB+SZv8gyN5Q6bHYNkba7GRUEhYMzFFREdFMDUyMABFZGdl
test (5): .github#9

! Failed to restore: Cache service responded with 400
test (5): .github#54

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Master Gate · 45846683375
Triggered via push about 10 minutes ago

JOBS
✓ docs in 43s (ID 140002064615)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Install just
  ✓ Set up Python
  ✓ Build and validate docs
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ core-wheel in 27s (ID 140002065096)
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
✓ lint in 4m54s (ID 140002347998)
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
* test (8) (ID 140002348205)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (6) (ID 140002348206)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (7) (ID 140002348215)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (4) (ID 140002348218)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
✓ test (5) in 8m38s (ID 140002348235)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* test (1) (ID 140002348268)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (3) (ID 140002348276)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (2) (ID 140002348307)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
docs: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0c0wIawAAAACOXf5NpvwsR4nFqoZbJwHEQ08xRURHRTE2MjAARWRnZQ==
docs: .github#7

! Failed to restore: Cache service responded with 400
docs: .github#26

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache/restore@v4, actions/checkout@v4, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
core-wheel: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache@v4, actions/checkout@v4, actions/download-artifact@v4, actions/setup-go@v5, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
lint: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0jE0IawAAAADNcL55q1IlRLnjbGxMCbSlUEhMMzBFREdFMDQxNwBFZGdl
lint: .github#9

! Failed to restore: Cache service responded with 400
lint: .github#54

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
test (5): .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0bU4IawAAAAB+SZv8gyN5Q6bHYNkba7GRUEhYMzFFREdFMDUyMABFZGdl
test (5): .github#9

! Failed to restore: Cache service responded with 400
test (5): .github#54

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Master Gate · 45846683375
Triggered via push about 10 minutes ago

JOBS
✓ docs in 43s (ID 140002064615)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Install just
  ✓ Set up Python
  ✓ Build and validate docs
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ core-wheel in 27s (ID 140002065096)
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
✓ lint in 4m54s (ID 140002347998)
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
* test (8) (ID 140002348205)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (6) (ID 140002348206)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (7) (ID 140002348215)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (4) (ID 140002348218)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
✓ test (5) in 8m38s (ID 140002348235)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* test (1) (ID 140002348268)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (3) (ID 140002348276)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (2) (ID 140002348307)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
docs: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0c0wIawAAAACOXf5NpvwsR4nFqoZbJwHEQ08xRURHRTE2MjAARWRnZQ==
docs: .github#7

! Failed to restore: Cache service responded with 400
docs: .github#26

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache/restore@v4, actions/checkout@v4, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
core-wheel: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache@v4, actions/checkout@v4, actions/download-artifact@v4, actions/setup-go@v5, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
lint: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0jE0IawAAAADNcL55q1IlRLnjbGxMCbSlUEhMMzBFREdFMDQxNwBFZGdl
lint: .github#9

! Failed to restore: Cache service responded with 400
lint: .github#54

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
test (5): .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0bU4IawAAAAB+SZv8gyN5Q6bHYNkba7GRUEhYMzFFREdFMDUyMABFZGdl
test (5): .github#9

! Failed to restore: Cache service responded with 400
test (5): .github#54

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Master Gate · 45846683375
Triggered via push about 10 minutes ago

JOBS
✓ docs in 43s (ID 140002064615)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Install just
  ✓ Set up Python
  ✓ Build and validate docs
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ core-wheel in 27s (ID 140002065096)
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
✓ lint in 4m54s (ID 140002347998)
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
* test (8) (ID 140002348205)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (6) (ID 140002348206)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (7) (ID 140002348215)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (4) (ID 140002348218)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
✓ test (5) in 8m38s (ID 140002348235)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* test (1) (ID 140002348268)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (3) (ID 140002348276)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (2) (ID 140002348307)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
docs: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0c0wIawAAAACOXf5NpvwsR4nFqoZbJwHEQ08xRURHRTE2MjAARWRnZQ==
docs: .github#7

! Failed to restore: Cache service responded with 400
docs: .github#26

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache/restore@v4, actions/checkout@v4, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
core-wheel: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache@v4, actions/checkout@v4, actions/download-artifact@v4, actions/setup-go@v5, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
lint: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0jE0IawAAAADNcL55q1IlRLnjbGxMCbSlUEhMMzBFREdFMDQxNwBFZGdl
lint: .github#9

! Failed to restore: Cache service responded with 400
lint: .github#54

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
test (5): .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0bU4IawAAAAB+SZv8gyN5Q6bHYNkba7GRUEhYMzFFREdFMDUyMABFZGdl
test (5): .github#9

! Failed to restore: Cache service responded with 400
test (5): .github#54

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Master Gate · 45846683375
Triggered via push about 10 minutes ago

JOBS
✓ docs in 43s (ID 140002064615)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Install just
  ✓ Set up Python
  ✓ Build and validate docs
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ core-wheel in 27s (ID 140002065096)
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
✓ lint in 4m54s (ID 140002347998)
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
✓ test (8) in 9m56s (ID 140002348205)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* test (6) (ID 140002348206)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (7) (ID 140002348215)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (4) (ID 140002348218)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
✓ test (5) in 8m38s (ID 140002348235)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* test (1) (ID 140002348268)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (3) (ID 140002348276)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (2) (ID 140002348307)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
docs: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0c0wIawAAAACOXf5NpvwsR4nFqoZbJwHEQ08xRURHRTE2MjAARWRnZQ==
docs: .github#7

! Failed to restore: Cache service responded with 400
docs: .github#26

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache/restore@v4, actions/checkout@v4, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
core-wheel: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache@v4, actions/checkout@v4, actions/download-artifact@v4, actions/setup-go@v5, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
lint: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0jE0IawAAAADNcL55q1IlRLnjbGxMCbSlUEhMMzBFREdFMDQxNwBFZGdl
lint: .github#9

! Failed to restore: Cache service responded with 400
lint: .github#54

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
test (8): .github#3

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0uk4IawAAAAC6tD3vPdkIRqIg1LVTj8WTU1RCRURHRTAzMTAARWRnZQ==
test (8): .github#9

! Failed to restore: Cache service responded with 400
test (8): .github#54

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Master Gate · 45846683375
Triggered via push about 10 minutes ago

JOBS
✓ docs in 43s (ID 140002064615)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Install just
  ✓ Set up Python
  ✓ Build and validate docs
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ core-wheel in 27s (ID 140002065096)
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
✓ lint in 4m54s (ID 140002347998)
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
✓ test (8) in 9m56s (ID 140002348205)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* test (6) (ID 140002348206)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (7) (ID 140002348215)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (4) (ID 140002348218)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
✓ test (5) in 8m38s (ID 140002348235)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* test (1) (ID 140002348268)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (3) (ID 140002348276)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (2) (ID 140002348307)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
docs: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0c0wIawAAAACOXf5NpvwsR4nFqoZbJwHEQ08xRURHRTE2MjAARWRnZQ==
docs: .github#7

! Failed to restore: Cache service responded with 400
docs: .github#26

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache/restore@v4, actions/checkout@v4, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
core-wheel: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache@v4, actions/checkout@v4, actions/download-artifact@v4, actions/setup-go@v5, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
lint: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0jE0IawAAAADNcL55q1IlRLnjbGxMCbSlUEhMMzBFREdFMDQxNwBFZGdl
lint: .github#9

! Failed to restore: Cache service responded with 400
lint: .github#54

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
test (8): .github#3

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0uk4IawAAAAC6tD3vPdkIRqIg1LVTj8WTU1RCRURHRTAzMTAARWRnZQ==
test (8): .github#9

! Failed to restore: Cache service responded with 400
test (8): .github#54

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Master Gate · 45846683375
Triggered via push about 10 minutes ago

JOBS
✓ docs in 43s (ID 140002064615)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Install just
  ✓ Set up Python
  ✓ Build and validate docs
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ core-wheel in 27s (ID 140002065096)
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
✓ lint in 4m54s (ID 140002347998)
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
✓ test (8) in 9m56s (ID 140002348205)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* test (6) (ID 140002348206)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (7) (ID 140002348215)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (4) (ID 140002348218)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
✓ test (5) in 8m38s (ID 140002348235)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* test (1) (ID 140002348268)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (3) (ID 140002348276)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (2) (ID 140002348307)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
docs: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0c0wIawAAAACOXf5NpvwsR4nFqoZbJwHEQ08xRURHRTE2MjAARWRnZQ==
docs: .github#7

! Failed to restore: Cache service responded with 400
docs: .github#26

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache/restore@v4, actions/checkout@v4, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
core-wheel: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache@v4, actions/checkout@v4, actions/download-artifact@v4, actions/setup-go@v5, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
lint: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0jE0IawAAAADNcL55q1IlRLnjbGxMCbSlUEhMMzBFREdFMDQxNwBFZGdl
lint: .github#9

! Failed to restore: Cache service responded with 400
lint: .github#54

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
test (8): .github#3

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0uk4IawAAAAC6tD3vPdkIRqIg1LVTj8WTU1RCRURHRTAzMTAARWRnZQ==
test (8): .github#9

! Failed to restore: Cache service responded with 400
test (8): .github#54

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Master Gate · 45846683375
Triggered via push about 10 minutes ago

JOBS
✓ docs in 43s (ID 140002064615)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Install just
  ✓ Set up Python
  ✓ Build and validate docs
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ core-wheel in 27s (ID 140002065096)
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
✓ lint in 4m54s (ID 140002347998)
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
✓ test (8) in 9m56s (ID 140002348205)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* test (6) (ID 140002348206)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (7) (ID 140002348215)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (4) (ID 140002348218)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
✓ test (5) in 8m38s (ID 140002348235)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* test (1) (ID 140002348268)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (3) (ID 140002348276)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (2) (ID 140002348307)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
docs: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0c0wIawAAAACOXf5NpvwsR4nFqoZbJwHEQ08xRURHRTE2MjAARWRnZQ==
docs: .github#7

! Failed to restore: Cache service responded with 400
docs: .github#26

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache/restore@v4, actions/checkout@v4, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
core-wheel: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache@v4, actions/checkout@v4, actions/download-artifact@v4, actions/setup-go@v5, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
lint: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0jE0IawAAAADNcL55q1IlRLnjbGxMCbSlUEhMMzBFREdFMDQxNwBFZGdl
lint: .github#9

! Failed to restore: Cache service responded with 400
lint: .github#54

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
test (8): .github#3

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0uk4IawAAAAC6tD3vPdkIRqIg1LVTj8WTU1RCRURHRTAzMTAARWRnZQ==
test (8): .github#9

! Failed to restore: Cache service responded with 400
test (8): .github#54

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Master Gate · 45846683375
Triggered via push about 10 minutes ago

JOBS
✓ docs in 43s (ID 140002064615)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Install just
  ✓ Set up Python
  ✓ Build and validate docs
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ core-wheel in 27s (ID 140002065096)
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
✓ lint in 4m54s (ID 140002347998)
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
✓ test (8) in 9m56s (ID 140002348205)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* test (6) (ID 140002348206)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (7) (ID 140002348215)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (4) (ID 140002348218)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
✓ test (5) in 8m38s (ID 140002348235)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* test (1) (ID 140002348268)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (3) (ID 140002348276)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (2) (ID 140002348307)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
docs: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0c0wIawAAAACOXf5NpvwsR4nFqoZbJwHEQ08xRURHRTE2MjAARWRnZQ==
docs: .github#7

! Failed to restore: Cache service responded with 400
docs: .github#26

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache/restore@v4, actions/checkout@v4, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
core-wheel: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache@v4, actions/checkout@v4, actions/download-artifact@v4, actions/setup-go@v5, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
lint: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0jE0IawAAAADNcL55q1IlRLnjbGxMCbSlUEhMMzBFREdFMDQxNwBFZGdl
lint: .github#9

! Failed to restore: Cache service responded with 400
lint: .github#54

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
test (8): .github#3

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0uk4IawAAAAC6tD3vPdkIRqIg1LVTj8WTU1RCRURHRTAzMTAARWRnZQ==
test (8): .github#9

! Failed to restore: Cache service responded with 400
test (8): .github#54

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Master Gate · 45846683375
Triggered via push about 10 minutes ago

JOBS
✓ docs in 43s (ID 140002064615)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Install just
  ✓ Set up Python
  ✓ Build and validate docs
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ core-wheel in 27s (ID 140002065096)
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
✓ lint in 4m54s (ID 140002347998)
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
✓ test (8) in 9m56s (ID 140002348205)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* test (6) (ID 140002348206)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (7) (ID 140002348215)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (4) (ID 140002348218)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
✓ test (5) in 8m38s (ID 140002348235)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* test (1) (ID 140002348268)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (3) (ID 140002348276)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (2) (ID 140002348307)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
docs: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0c0wIawAAAACOXf5NpvwsR4nFqoZbJwHEQ08xRURHRTE2MjAARWRnZQ==
docs: .github#7

! Failed to restore: Cache service responded with 400
docs: .github#26

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache/restore@v4, actions/checkout@v4, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
core-wheel: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache@v4, actions/checkout@v4, actions/download-artifact@v4, actions/setup-go@v5, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
lint: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0jE0IawAAAADNcL55q1IlRLnjbGxMCbSlUEhMMzBFREdFMDQxNwBFZGdl
lint: .github#9

! Failed to restore: Cache service responded with 400
lint: .github#54

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
test (8): .github#3

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0uk4IawAAAAC6tD3vPdkIRqIg1LVTj8WTU1RCRURHRTAzMTAARWRnZQ==
test (8): .github#9

! Failed to restore: Cache service responded with 400
test (8): .github#54

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Master Gate · 45846683375
Triggered via push about 11 minutes ago

JOBS
✓ docs in 43s (ID 140002064615)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Install just
  ✓ Set up Python
  ✓ Build and validate docs
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ core-wheel in 27s (ID 140002065096)
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
✓ lint in 4m54s (ID 140002347998)
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
✓ test (8) in 9m56s (ID 140002348205)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* test (6) (ID 140002348206)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (7) (ID 140002348215)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (4) (ID 140002348218)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
✓ test (5) in 8m38s (ID 140002348235)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* test (1) (ID 140002348268)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (3) (ID 140002348276)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* test (2) (ID 140002348307)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
docs: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0c0wIawAAAACOXf5NpvwsR4nFqoZbJwHEQ08xRURHRTE2MjAARWRnZQ==
docs: .github#7

! Failed to restore: Cache service responded with 400
docs: .github#26

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache/restore@v4, actions/checkout@v4, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
core-wheel: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache@v4, actions/checkout@v4, actions/download-artifact@v4, actions/setup-go@v5, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
lint: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0jE0IawAAAADNcL55q1IlRLnjbGxMCbSlUEhMMzBFREdFMDQxNwBFZGdl
lint: .github#9

! Failed to restore: Cache service responded with 400
lint: .github#54

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
test (8): .github#3

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0uk4IawAAAAC6tD3vPdkIRqIg1LVTj8WTU1RCRURHRTAzMTAARWRnZQ==
test (8): .github#9

! Failed to restore: Cache service responded with 400
test (8): .github#54

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Master Gate · 45846683375
Triggered via push about 11 minutes ago

JOBS
✓ docs in 43s (ID 140002064615)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Install just
  ✓ Set up Python
  ✓ Build and validate docs
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ core-wheel in 27s (ID 140002065096)
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
✓ lint in 4m54s (ID 140002347998)
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
✓ test (8) in 9m56s (ID 140002348205)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* test (6) (ID 140002348206)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (7) (ID 140002348215)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (4) (ID 140002348218)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
✓ test (5) in 8m38s (ID 140002348235)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* test (1) (ID 140002348268)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
✓ test (3) in 10m27s (ID 140002348276)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* test (2) (ID 140002348307)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
docs: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0c0wIawAAAACOXf5NpvwsR4nFqoZbJwHEQ08xRURHRTE2MjAARWRnZQ==
docs: .github#7

! Failed to restore: Cache service responded with 400
docs: .github#26

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache/restore@v4, actions/checkout@v4, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
core-wheel: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache@v4, actions/checkout@v4, actions/download-artifact@v4, actions/setup-go@v5, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
lint: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0jE0IawAAAADNcL55q1IlRLnjbGxMCbSlUEhMMzBFREdFMDQxNwBFZGdl
lint: .github#9

! Failed to restore: Cache service responded with 400
lint: .github#54

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
test (8): .github#3

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0uk4IawAAAAC6tD3vPdkIRqIg1LVTj8WTU1RCRURHRTAzMTAARWRnZQ==
test (8): .github#9

! Failed to restore: Cache service responded with 400
test (8): .github#54

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
test (3): .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>02k4IawAAAACxtNaOOqIGRJm4BTK4l+njUEhMMzBFREdFMDQwNgBFZGdl
test (3): .github#9

! Failed to restore: Cache service responded with 400
test (3): .github#54

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Master Gate · 45846683375
Triggered via push about 11 minutes ago

JOBS
✓ docs in 43s (ID 140002064615)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Install just
  ✓ Set up Python
  ✓ Build and validate docs
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ core-wheel in 27s (ID 140002065096)
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
✓ lint in 4m54s (ID 140002347998)
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
✓ test (8) in 9m56s (ID 140002348205)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* test (6) (ID 140002348206)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (7) (ID 140002348215)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (4) (ID 140002348218)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
✓ test (5) in 8m38s (ID 140002348235)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* test (1) (ID 140002348268)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
✓ test (3) in 10m27s (ID 140002348276)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* test (2) (ID 140002348307)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
docs: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0c0wIawAAAACOXf5NpvwsR4nFqoZbJwHEQ08xRURHRTE2MjAARWRnZQ==
docs: .github#7

! Failed to restore: Cache service responded with 400
docs: .github#26

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache/restore@v4, actions/checkout@v4, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
core-wheel: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache@v4, actions/checkout@v4, actions/download-artifact@v4, actions/setup-go@v5, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
lint: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0jE0IawAAAADNcL55q1IlRLnjbGxMCbSlUEhMMzBFREdFMDQxNwBFZGdl
lint: .github#9

! Failed to restore: Cache service responded with 400
lint: .github#54

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
test (8): .github#3

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0uk4IawAAAAC6tD3vPdkIRqIg1LVTj8WTU1RCRURHRTAzMTAARWRnZQ==
test (8): .github#9

! Failed to restore: Cache service responded with 400
test (8): .github#54

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
test (3): .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>02k4IawAAAACxtNaOOqIGRJm4BTK4l+njUEhMMzBFREdFMDQwNgBFZGdl
test (3): .github#9

! Failed to restore: Cache service responded with 400
test (3): .github#54

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Master Gate · 45846683375
Triggered via push about 11 minutes ago

JOBS
✓ docs in 43s (ID 140002064615)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Install just
  ✓ Set up Python
  ✓ Build and validate docs
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ core-wheel in 27s (ID 140002065096)
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
✓ lint in 4m54s (ID 140002347998)
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
✓ test (8) in 9m56s (ID 140002348205)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* test (6) (ID 140002348206)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (7) (ID 140002348215)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (4) (ID 140002348218)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
✓ test (5) in 8m38s (ID 140002348235)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* test (1) (ID 140002348268)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
✓ test (3) in 10m27s (ID 140002348276)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* test (2) (ID 140002348307)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
docs: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0c0wIawAAAACOXf5NpvwsR4nFqoZbJwHEQ08xRURHRTE2MjAARWRnZQ==
docs: .github#7

! Failed to restore: Cache service responded with 400
docs: .github#26

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache/restore@v4, actions/checkout@v4, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
core-wheel: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache@v4, actions/checkout@v4, actions/download-artifact@v4, actions/setup-go@v5, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
lint: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0jE0IawAAAADNcL55q1IlRLnjbGxMCbSlUEhMMzBFREdFMDQxNwBFZGdl
lint: .github#9

! Failed to restore: Cache service responded with 400
lint: .github#54

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
test (8): .github#3

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0uk4IawAAAAC6tD3vPdkIRqIg1LVTj8WTU1RCRURHRTAzMTAARWRnZQ==
test (8): .github#9

! Failed to restore: Cache service responded with 400
test (8): .github#54

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
test (3): .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>02k4IawAAAACxtNaOOqIGRJm4BTK4l+njUEhMMzBFREdFMDQwNgBFZGdl
test (3): .github#9

! Failed to restore: Cache service responded with 400
test (3): .github#54

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Master Gate · 45846683375
Triggered via push about 11 minutes ago

JOBS
✓ docs in 43s (ID 140002064615)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Install just
  ✓ Set up Python
  ✓ Build and validate docs
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ core-wheel in 27s (ID 140002065096)
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
✓ lint in 4m54s (ID 140002347998)
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
✓ test (8) in 9m56s (ID 140002348205)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* test (6) (ID 140002348206)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (7) (ID 140002348215)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (4) (ID 140002348218)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
✓ test (5) in 8m38s (ID 140002348235)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* test (1) (ID 140002348268)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
✓ test (3) in 10m27s (ID 140002348276)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* test (2) (ID 140002348307)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
docs: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0c0wIawAAAACOXf5NpvwsR4nFqoZbJwHEQ08xRURHRTE2MjAARWRnZQ==
docs: .github#7

! Failed to restore: Cache service responded with 400
docs: .github#26

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache/restore@v4, actions/checkout@v4, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
core-wheel: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache@v4, actions/checkout@v4, actions/download-artifact@v4, actions/setup-go@v5, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
lint: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0jE0IawAAAADNcL55q1IlRLnjbGxMCbSlUEhMMzBFREdFMDQxNwBFZGdl
lint: .github#9

! Failed to restore: Cache service responded with 400
lint: .github#54

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
test (8): .github#3

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0uk4IawAAAAC6tD3vPdkIRqIg1LVTj8WTU1RCRURHRTAzMTAARWRnZQ==
test (8): .github#9

! Failed to restore: Cache service responded with 400
test (8): .github#54

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
test (3): .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>02k4IawAAAACxtNaOOqIGRJm4BTK4l+njUEhMMzBFREdFMDQwNgBFZGdl
test (3): .github#9

! Failed to restore: Cache service responded with 400
test (3): .github#54

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Master Gate · 45846683375
Triggered via push about 11 minutes ago

JOBS
✓ docs in 43s (ID 140002064615)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Install just
  ✓ Set up Python
  ✓ Build and validate docs
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ core-wheel in 27s (ID 140002065096)
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
✓ lint in 4m54s (ID 140002347998)
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
✓ test (8) in 9m56s (ID 140002348205)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* test (6) (ID 140002348206)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (7) (ID 140002348215)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (4) (ID 140002348218)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
✓ test (5) in 8m38s (ID 140002348235)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* test (1) (ID 140002348268)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
✓ test (3) in 10m27s (ID 140002348276)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* test (2) (ID 140002348307)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
docs: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0c0wIawAAAACOXf5NpvwsR4nFqoZbJwHEQ08xRURHRTE2MjAARWRnZQ==
docs: .github#7

! Failed to restore: Cache service responded with 400
docs: .github#26

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache/restore@v4, actions/checkout@v4, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
core-wheel: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache@v4, actions/checkout@v4, actions/download-artifact@v4, actions/setup-go@v5, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
lint: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0jE0IawAAAADNcL55q1IlRLnjbGxMCbSlUEhMMzBFREdFMDQxNwBFZGdl
lint: .github#9

! Failed to restore: Cache service responded with 400
lint: .github#54

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
test (8): .github#3

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0uk4IawAAAAC6tD3vPdkIRqIg1LVTj8WTU1RCRURHRTAzMTAARWRnZQ==
test (8): .github#9

! Failed to restore: Cache service responded with 400
test (8): .github#54

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
test (3): .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>02k4IawAAAACxtNaOOqIGRJm4BTK4l+njUEhMMzBFREdFMDQwNgBFZGdl
test (3): .github#9

! Failed to restore: Cache service responded with 400
test (3): .github#54

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Master Gate · 45846683375
Triggered via push about 11 minutes ago

JOBS
✓ docs in 43s (ID 140002064615)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Install just
  ✓ Set up Python
  ✓ Build and validate docs
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ core-wheel in 27s (ID 140002065096)
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
✓ lint in 4m54s (ID 140002347998)
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
✓ test (8) in 9m56s (ID 140002348205)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* test (6) (ID 140002348206)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (7) (ID 140002348215)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (4) (ID 140002348218)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
✓ test (5) in 8m38s (ID 140002348235)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* test (1) (ID 140002348268)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
✓ test (3) in 10m27s (ID 140002348276)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* test (2) (ID 140002348307)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
docs: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0c0wIawAAAACOXf5NpvwsR4nFqoZbJwHEQ08xRURHRTE2MjAARWRnZQ==
docs: .github#7

! Failed to restore: Cache service responded with 400
docs: .github#26

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache/restore@v4, actions/checkout@v4, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
core-wheel: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache@v4, actions/checkout@v4, actions/download-artifact@v4, actions/setup-go@v5, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
lint: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0jE0IawAAAADNcL55q1IlRLnjbGxMCbSlUEhMMzBFREdFMDQxNwBFZGdl
lint: .github#9

! Failed to restore: Cache service responded with 400
lint: .github#54

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
test (8): .github#3

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0uk4IawAAAAC6tD3vPdkIRqIg1LVTj8WTU1RCRURHRTAzMTAARWRnZQ==
test (8): .github#9

! Failed to restore: Cache service responded with 400
test (8): .github#54

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
test (3): .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>02k4IawAAAACxtNaOOqIGRJm4BTK4l+njUEhMMzBFREdFMDQwNgBFZGdl
test (3): .github#9

! Failed to restore: Cache service responded with 400
test (3): .github#54

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Master Gate · 45846683375
Triggered via push about 11 minutes ago

JOBS
✓ docs in 43s (ID 140002064615)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Install just
  ✓ Set up Python
  ✓ Build and validate docs
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ core-wheel in 27s (ID 140002065096)
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
✓ lint in 4m54s (ID 140002347998)
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
✓ test (8) in 9m56s (ID 140002348205)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* test (6) (ID 140002348206)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (7) (ID 140002348215)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (4) (ID 140002348218)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
✓ test (5) in 8m38s (ID 140002348235)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* test (1) (ID 140002348268)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
✓ test (3) in 10m27s (ID 140002348276)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* test (2) (ID 140002348307)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
docs: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0c0wIawAAAACOXf5NpvwsR4nFqoZbJwHEQ08xRURHRTE2MjAARWRnZQ==
docs: .github#7

! Failed to restore: Cache service responded with 400
docs: .github#26

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache/restore@v4, actions/checkout@v4, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
core-wheel: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache@v4, actions/checkout@v4, actions/download-artifact@v4, actions/setup-go@v5, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
lint: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0jE0IawAAAADNcL55q1IlRLnjbGxMCbSlUEhMMzBFREdFMDQxNwBFZGdl
lint: .github#9

! Failed to restore: Cache service responded with 400
lint: .github#54

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
test (8): .github#3

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0uk4IawAAAAC6tD3vPdkIRqIg1LVTj8WTU1RCRURHRTAzMTAARWRnZQ==
test (8): .github#9

! Failed to restore: Cache service responded with 400
test (8): .github#54

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
test (3): .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>02k4IawAAAACxtNaOOqIGRJm4BTK4l+njUEhMMzBFREdFMDQwNgBFZGdl
test (3): .github#9

! Failed to restore: Cache service responded with 400
test (3): .github#54

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Master Gate · 45846683375
Triggered via push about 11 minutes ago

JOBS
✓ docs in 43s (ID 140002064615)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Install just
  ✓ Set up Python
  ✓ Build and validate docs
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ core-wheel in 27s (ID 140002065096)
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
✓ lint in 4m54s (ID 140002347998)
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
✓ test (8) in 9m56s (ID 140002348205)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* test (6) (ID 140002348206)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (7) (ID 140002348215)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (4) (ID 140002348218)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
✓ test (5) in 8m38s (ID 140002348235)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* test (1) (ID 140002348268)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
✓ test (3) in 10m27s (ID 140002348276)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* test (2) (ID 140002348307)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
docs: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0c0wIawAAAACOXf5NpvwsR4nFqoZbJwHEQ08xRURHRTE2MjAARWRnZQ==
docs: .github#7

! Failed to restore: Cache service responded with 400
docs: .github#26

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache/restore@v4, actions/checkout@v4, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
core-wheel: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache@v4, actions/checkout@v4, actions/download-artifact@v4, actions/setup-go@v5, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
lint: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0jE0IawAAAADNcL55q1IlRLnjbGxMCbSlUEhMMzBFREdFMDQxNwBFZGdl
lint: .github#9

! Failed to restore: Cache service responded with 400
lint: .github#54

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
test (8): .github#3

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0uk4IawAAAAC6tD3vPdkIRqIg1LVTj8WTU1RCRURHRTAzMTAARWRnZQ==
test (8): .github#9

! Failed to restore: Cache service responded with 400
test (8): .github#54

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
test (3): .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>02k4IawAAAACxtNaOOqIGRJm4BTK4l+njUEhMMzBFREdFMDQwNgBFZGdl
test (3): .github#9

! Failed to restore: Cache service responded with 400
test (3): .github#54

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Master Gate · 45846683375
Triggered via push about 11 minutes ago

JOBS
✓ docs in 43s (ID 140002064615)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Install just
  ✓ Set up Python
  ✓ Build and validate docs
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ core-wheel in 27s (ID 140002065096)
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
✓ lint in 4m54s (ID 140002347998)
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
✓ test (8) in 9m56s (ID 140002348205)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* test (6) (ID 140002348206)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (7) (ID 140002348215)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (4) (ID 140002348218)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
✓ test (5) in 8m38s (ID 140002348235)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* test (1) (ID 140002348268)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
✓ test (3) in 10m27s (ID 140002348276)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* test (2) (ID 140002348307)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
docs: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0c0wIawAAAACOXf5NpvwsR4nFqoZbJwHEQ08xRURHRTE2MjAARWRnZQ==
docs: .github#7

! Failed to restore: Cache service responded with 400
docs: .github#26

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache/restore@v4, actions/checkout@v4, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
core-wheel: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache@v4, actions/checkout@v4, actions/download-artifact@v4, actions/setup-go@v5, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
lint: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0jE0IawAAAADNcL55q1IlRLnjbGxMCbSlUEhMMzBFREdFMDQxNwBFZGdl
lint: .github#9

! Failed to restore: Cache service responded with 400
lint: .github#54

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
test (8): .github#3

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0uk4IawAAAAC6tD3vPdkIRqIg1LVTj8WTU1RCRURHRTAzMTAARWRnZQ==
test (8): .github#9

! Failed to restore: Cache service responded with 400
test (8): .github#54

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
test (3): .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>02k4IawAAAACxtNaOOqIGRJm4BTK4l+njUEhMMzBFREdFMDQwNgBFZGdl
test (3): .github#9

! Failed to restore: Cache service responded with 400
test (3): .github#54

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Master Gate · 45846683375
Triggered via push about 11 minutes ago

JOBS
✓ docs in 43s (ID 140002064615)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Install just
  ✓ Set up Python
  ✓ Build and validate docs
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ core-wheel in 27s (ID 140002065096)
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
✓ lint in 4m54s (ID 140002347998)
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
✓ test (8) in 9m56s (ID 140002348205)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* test (6) (ID 140002348206)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (7) (ID 140002348215)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (4) (ID 140002348218)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
✓ test (5) in 8m38s (ID 140002348235)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* test (1) (ID 140002348268)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
✓ test (3) in 10m27s (ID 140002348276)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* test (2) (ID 140002348307)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
docs: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0c0wIawAAAACOXf5NpvwsR4nFqoZbJwHEQ08xRURHRTE2MjAARWRnZQ==
docs: .github#7

! Failed to restore: Cache service responded with 400
docs: .github#26

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache/restore@v4, actions/checkout@v4, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
core-wheel: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache@v4, actions/checkout@v4, actions/download-artifact@v4, actions/setup-go@v5, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
lint: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0jE0IawAAAADNcL55q1IlRLnjbGxMCbSlUEhMMzBFREdFMDQxNwBFZGdl
lint: .github#9

! Failed to restore: Cache service responded with 400
lint: .github#54

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
test (8): .github#3

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0uk4IawAAAAC6tD3vPdkIRqIg1LVTj8WTU1RCRURHRTAzMTAARWRnZQ==
test (8): .github#9

! Failed to restore: Cache service responded with 400
test (8): .github#54

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
test (3): .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>02k4IawAAAACxtNaOOqIGRJm4BTK4l+njUEhMMzBFREdFMDQwNgBFZGdl
test (3): .github#9

! Failed to restore: Cache service responded with 400
test (3): .github#54

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Master Gate · 45846683375
Triggered via push about 11 minutes ago

JOBS
✓ docs in 43s (ID 140002064615)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Install just
  ✓ Set up Python
  ✓ Build and validate docs
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ core-wheel in 27s (ID 140002065096)
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
✓ lint in 4m54s (ID 140002347998)
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
✓ test (8) in 9m56s (ID 140002348205)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* test (6) (ID 140002348206)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (7) (ID 140002348215)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (4) (ID 140002348218)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
✓ test (5) in 8m38s (ID 140002348235)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* test (1) (ID 140002348268)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
✓ test (3) in 10m27s (ID 140002348276)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* test (2) (ID 140002348307)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
docs: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0c0wIawAAAACOXf5NpvwsR4nFqoZbJwHEQ08xRURHRTE2MjAARWRnZQ==
docs: .github#7

! Failed to restore: Cache service responded with 400
docs: .github#26

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache/restore@v4, actions/checkout@v4, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
core-wheel: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache@v4, actions/checkout@v4, actions/download-artifact@v4, actions/setup-go@v5, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
lint: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0jE0IawAAAADNcL55q1IlRLnjbGxMCbSlUEhMMzBFREdFMDQxNwBFZGdl
lint: .github#9

! Failed to restore: Cache service responded with 400
lint: .github#54

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
test (8): .github#3

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0uk4IawAAAAC6tD3vPdkIRqIg1LVTj8WTU1RCRURHRTAzMTAARWRnZQ==
test (8): .github#9

! Failed to restore: Cache service responded with 400
test (8): .github#54

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
test (3): .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>02k4IawAAAACxtNaOOqIGRJm4BTK4l+njUEhMMzBFREdFMDQwNgBFZGdl
test (3): .github#9

! Failed to restore: Cache service responded with 400
test (3): .github#54

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Master Gate · 45846683375
Triggered via push about 11 minutes ago

JOBS
✓ docs in 43s (ID 140002064615)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Install just
  ✓ Set up Python
  ✓ Build and validate docs
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ core-wheel in 27s (ID 140002065096)
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
✓ lint in 4m54s (ID 140002347998)
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
✓ test (8) in 9m56s (ID 140002348205)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* test (6) (ID 140002348206)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (7) (ID 140002348215)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (4) (ID 140002348218)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
✓ test (5) in 8m38s (ID 140002348235)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* test (1) (ID 140002348268)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
✓ test (3) in 10m27s (ID 140002348276)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* test (2) (ID 140002348307)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
docs: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0c0wIawAAAACOXf5NpvwsR4nFqoZbJwHEQ08xRURHRTE2MjAARWRnZQ==
docs: .github#7

! Failed to restore: Cache service responded with 400
docs: .github#26

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache/restore@v4, actions/checkout@v4, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
core-wheel: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache@v4, actions/checkout@v4, actions/download-artifact@v4, actions/setup-go@v5, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
lint: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0jE0IawAAAADNcL55q1IlRLnjbGxMCbSlUEhMMzBFREdFMDQxNwBFZGdl
lint: .github#9

! Failed to restore: Cache service responded with 400
lint: .github#54

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
test (8): .github#3

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0uk4IawAAAAC6tD3vPdkIRqIg1LVTj8WTU1RCRURHRTAzMTAARWRnZQ==
test (8): .github#9

! Failed to restore: Cache service responded with 400
test (8): .github#54

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
test (3): .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>02k4IawAAAACxtNaOOqIGRJm4BTK4l+njUEhMMzBFREdFMDQwNgBFZGdl
test (3): .github#9

! Failed to restore: Cache service responded with 400
test (3): .github#54

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Master Gate · 45846683375
Triggered via push about 12 minutes ago

JOBS
✓ docs in 43s (ID 140002064615)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Install just
  ✓ Set up Python
  ✓ Build and validate docs
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ core-wheel in 27s (ID 140002065096)
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
✓ lint in 4m54s (ID 140002347998)
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
✓ test (8) in 9m56s (ID 140002348205)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* test (6) (ID 140002348206)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (7) (ID 140002348215)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (4) (ID 140002348218)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
✓ test (5) in 8m38s (ID 140002348235)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* test (1) (ID 140002348268)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
✓ test (3) in 10m27s (ID 140002348276)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* test (2) (ID 140002348307)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
docs: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0c0wIawAAAACOXf5NpvwsR4nFqoZbJwHEQ08xRURHRTE2MjAARWRnZQ==
docs: .github#7

! Failed to restore: Cache service responded with 400
docs: .github#26

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache/restore@v4, actions/checkout@v4, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
core-wheel: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache@v4, actions/checkout@v4, actions/download-artifact@v4, actions/setup-go@v5, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
lint: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0jE0IawAAAADNcL55q1IlRLnjbGxMCbSlUEhMMzBFREdFMDQxNwBFZGdl
lint: .github#9

! Failed to restore: Cache service responded with 400
lint: .github#54

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
test (8): .github#3

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0uk4IawAAAAC6tD3vPdkIRqIg1LVTj8WTU1RCRURHRTAzMTAARWRnZQ==
test (8): .github#9

! Failed to restore: Cache service responded with 400
test (8): .github#54

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
test (3): .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>02k4IawAAAACxtNaOOqIGRJm4BTK4l+njUEhMMzBFREdFMDQwNgBFZGdl
test (3): .github#9

! Failed to restore: Cache service responded with 400
test (3): .github#54

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Master Gate · 45846683375
Triggered via push about 12 minutes ago

JOBS
✓ docs in 43s (ID 140002064615)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Install just
  ✓ Set up Python
  ✓ Build and validate docs
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ core-wheel in 27s (ID 140002065096)
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
✓ lint in 4m54s (ID 140002347998)
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
✓ test (8) in 9m56s (ID 140002348205)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* test (6) (ID 140002348206)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (7) (ID 140002348215)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (4) (ID 140002348218)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
✓ test (5) in 8m38s (ID 140002348235)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* test (1) (ID 140002348268)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
✓ test (3) in 10m27s (ID 140002348276)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* test (2) (ID 140002348307)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
docs: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0c0wIawAAAACOXf5NpvwsR4nFqoZbJwHEQ08xRURHRTE2MjAARWRnZQ==
docs: .github#7

! Failed to restore: Cache service responded with 400
docs: .github#26

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache/restore@v4, actions/checkout@v4, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
core-wheel: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache@v4, actions/checkout@v4, actions/download-artifact@v4, actions/setup-go@v5, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
lint: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0jE0IawAAAADNcL55q1IlRLnjbGxMCbSlUEhMMzBFREdFMDQxNwBFZGdl
lint: .github#9

! Failed to restore: Cache service responded with 400
lint: .github#54

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
test (8): .github#3

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0uk4IawAAAAC6tD3vPdkIRqIg1LVTj8WTU1RCRURHRTAzMTAARWRnZQ==
test (8): .github#9

! Failed to restore: Cache service responded with 400
test (8): .github#54

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
test (3): .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>02k4IawAAAACxtNaOOqIGRJm4BTK4l+njUEhMMzBFREdFMDQwNgBFZGdl
test (3): .github#9

! Failed to restore: Cache service responded with 400
test (3): .github#54

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Master Gate · 45846683375
Triggered via push about 12 minutes ago

JOBS
✓ docs in 43s (ID 140002064615)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Install just
  ✓ Set up Python
  ✓ Build and validate docs
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ core-wheel in 27s (ID 140002065096)
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
✓ lint in 4m54s (ID 140002347998)
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
✓ test (8) in 9m56s (ID 140002348205)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* test (6) (ID 140002348206)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (7) (ID 140002348215)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (4) (ID 140002348218)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
✓ test (5) in 8m38s (ID 140002348235)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* test (1) (ID 140002348268)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
✓ test (3) in 10m27s (ID 140002348276)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* test (2) (ID 140002348307)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
docs: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0c0wIawAAAACOXf5NpvwsR4nFqoZbJwHEQ08xRURHRTE2MjAARWRnZQ==
docs: .github#7

! Failed to restore: Cache service responded with 400
docs: .github#26

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache/restore@v4, actions/checkout@v4, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
core-wheel: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache@v4, actions/checkout@v4, actions/download-artifact@v4, actions/setup-go@v5, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
lint: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0jE0IawAAAADNcL55q1IlRLnjbGxMCbSlUEhMMzBFREdFMDQxNwBFZGdl
lint: .github#9

! Failed to restore: Cache service responded with 400
lint: .github#54

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
test (8): .github#3

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0uk4IawAAAAC6tD3vPdkIRqIg1LVTj8WTU1RCRURHRTAzMTAARWRnZQ==
test (8): .github#9

! Failed to restore: Cache service responded with 400
test (8): .github#54

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
test (3): .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>02k4IawAAAACxtNaOOqIGRJm4BTK4l+njUEhMMzBFREdFMDQwNgBFZGdl
test (3): .github#9

! Failed to restore: Cache service responded with 400
test (3): .github#54

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Master Gate · 45846683375
Triggered via push about 12 minutes ago

JOBS
✓ docs in 43s (ID 140002064615)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Install just
  ✓ Set up Python
  ✓ Build and validate docs
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ core-wheel in 27s (ID 140002065096)
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
✓ lint in 4m54s (ID 140002347998)
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
✓ test (8) in 9m56s (ID 140002348205)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* test (6) (ID 140002348206)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (7) (ID 140002348215)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (4) (ID 140002348218)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
✓ test (5) in 8m38s (ID 140002348235)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* test (1) (ID 140002348268)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
✓ test (3) in 10m27s (ID 140002348276)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* test (2) (ID 140002348307)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
docs: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0c0wIawAAAACOXf5NpvwsR4nFqoZbJwHEQ08xRURHRTE2MjAARWRnZQ==
docs: .github#7

! Failed to restore: Cache service responded with 400
docs: .github#26

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache/restore@v4, actions/checkout@v4, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
core-wheel: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache@v4, actions/checkout@v4, actions/download-artifact@v4, actions/setup-go@v5, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
lint: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0jE0IawAAAADNcL55q1IlRLnjbGxMCbSlUEhMMzBFREdFMDQxNwBFZGdl
lint: .github#9

! Failed to restore: Cache service responded with 400
lint: .github#54

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
test (8): .github#3

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0uk4IawAAAAC6tD3vPdkIRqIg1LVTj8WTU1RCRURHRTAzMTAARWRnZQ==
test (8): .github#9

! Failed to restore: Cache service responded with 400
test (8): .github#54

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
test (3): .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>02k4IawAAAACxtNaOOqIGRJm4BTK4l+njUEhMMzBFREdFMDQwNgBFZGdl
test (3): .github#9

! Failed to restore: Cache service responded with 400
test (3): .github#54

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Master Gate · 45846683375
Triggered via push about 12 minutes ago

JOBS
✓ docs in 43s (ID 140002064615)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Install just
  ✓ Set up Python
  ✓ Build and validate docs
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ core-wheel in 27s (ID 140002065096)
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
✓ lint in 4m54s (ID 140002347998)
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
✓ test (8) in 9m56s (ID 140002348205)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* test (6) (ID 140002348206)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (7) (ID 140002348215)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
✓ test (4) in 11m46s (ID 140002348218)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ test (5) in 8m38s (ID 140002348235)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* test (1) (ID 140002348268)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
✓ test (3) in 10m27s (ID 140002348276)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* test (2) (ID 140002348307)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
docs: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0c0wIawAAAACOXf5NpvwsR4nFqoZbJwHEQ08xRURHRTE2MjAARWRnZQ==
docs: .github#7

! Failed to restore: Cache service responded with 400
docs: .github#26

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache/restore@v4, actions/checkout@v4, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
core-wheel: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache@v4, actions/checkout@v4, actions/download-artifact@v4, actions/setup-go@v5, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
lint: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0jE0IawAAAADNcL55q1IlRLnjbGxMCbSlUEhMMzBFREdFMDQxNwBFZGdl
lint: .github#9

! Failed to restore: Cache service responded with 400
lint: .github#54

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
test (8): .github#3

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0uk4IawAAAAC6tD3vPdkIRqIg1LVTj8WTU1RCRURHRTAzMTAARWRnZQ==
test (8): .github#9

! Failed to restore: Cache service responded with 400
test (8): .github#54

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
test (3): .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>02k4IawAAAACxtNaOOqIGRJm4BTK4l+njUEhMMzBFREdFMDQwNgBFZGdl
test (3): .github#9

! Failed to restore: Cache service responded with 400
test (3): .github#54

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Master Gate · 45846683375
Triggered via push about 12 minutes ago

JOBS
✓ docs in 43s (ID 140002064615)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Install just
  ✓ Set up Python
  ✓ Build and validate docs
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ core-wheel in 27s (ID 140002065096)
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
✓ lint in 4m54s (ID 140002347998)
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
✓ test (8) in 9m56s (ID 140002348205)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* test (6) (ID 140002348206)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (7) (ID 140002348215)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
✓ test (4) in 11m46s (ID 140002348218)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ test (5) in 8m38s (ID 140002348235)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* test (1) (ID 140002348268)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
✓ test (3) in 10m27s (ID 140002348276)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* test (2) (ID 140002348307)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
docs: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0c0wIawAAAACOXf5NpvwsR4nFqoZbJwHEQ08xRURHRTE2MjAARWRnZQ==
docs: .github#7

! Failed to restore: Cache service responded with 400
docs: .github#26

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache/restore@v4, actions/checkout@v4, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
core-wheel: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache@v4, actions/checkout@v4, actions/download-artifact@v4, actions/setup-go@v5, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
lint: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0jE0IawAAAADNcL55q1IlRLnjbGxMCbSlUEhMMzBFREdFMDQxNwBFZGdl
lint: .github#9

! Failed to restore: Cache service responded with 400
lint: .github#54

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
test (8): .github#3

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0uk4IawAAAAC6tD3vPdkIRqIg1LVTj8WTU1RCRURHRTAzMTAARWRnZQ==
test (8): .github#9

! Failed to restore: Cache service responded with 400
test (8): .github#54

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
test (3): .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>02k4IawAAAACxtNaOOqIGRJm4BTK4l+njUEhMMzBFREdFMDQwNgBFZGdl
test (3): .github#9

! Failed to restore: Cache service responded with 400
test (3): .github#54

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Master Gate · 45846683375
Triggered via push about 12 minutes ago

JOBS
✓ docs in 43s (ID 140002064615)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Install just
  ✓ Set up Python
  ✓ Build and validate docs
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ core-wheel in 27s (ID 140002065096)
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
✓ lint in 4m54s (ID 140002347998)
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
✓ test (8) in 9m56s (ID 140002348205)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* test (6) (ID 140002348206)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (7) (ID 140002348215)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
✓ test (4) in 11m46s (ID 140002348218)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ test (5) in 8m38s (ID 140002348235)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* test (1) (ID 140002348268)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
✓ test (3) in 10m27s (ID 140002348276)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* test (2) (ID 140002348307)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
docs: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0c0wIawAAAACOXf5NpvwsR4nFqoZbJwHEQ08xRURHRTE2MjAARWRnZQ==
docs: .github#7

! Failed to restore: Cache service responded with 400
docs: .github#26

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache/restore@v4, actions/checkout@v4, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
core-wheel: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache@v4, actions/checkout@v4, actions/download-artifact@v4, actions/setup-go@v5, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
lint: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0jE0IawAAAADNcL55q1IlRLnjbGxMCbSlUEhMMzBFREdFMDQxNwBFZGdl
lint: .github#9

! Failed to restore: Cache service responded with 400
lint: .github#54

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
test (8): .github#3

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0uk4IawAAAAC6tD3vPdkIRqIg1LVTj8WTU1RCRURHRTAzMTAARWRnZQ==
test (8): .github#9

! Failed to restore: Cache service responded with 400
test (8): .github#54

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
test (3): .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>02k4IawAAAACxtNaOOqIGRJm4BTK4l+njUEhMMzBFREdFMDQwNgBFZGdl
test (3): .github#9

! Failed to restore: Cache service responded with 400
test (3): .github#54

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Master Gate · 45846683375
Triggered via push about 12 minutes ago

JOBS
✓ docs in 43s (ID 140002064615)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Install just
  ✓ Set up Python
  ✓ Build and validate docs
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ core-wheel in 27s (ID 140002065096)
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
✓ lint in 4m54s (ID 140002347998)
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
✓ test (8) in 9m56s (ID 140002348205)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* test (6) (ID 140002348206)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (7) (ID 140002348215)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
✓ test (4) in 11m46s (ID 140002348218)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ test (5) in 8m38s (ID 140002348235)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* test (1) (ID 140002348268)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
✓ test (3) in 10m27s (ID 140002348276)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* test (2) (ID 140002348307)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
docs: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0c0wIawAAAACOXf5NpvwsR4nFqoZbJwHEQ08xRURHRTE2MjAARWRnZQ==
docs: .github#7

! Failed to restore: Cache service responded with 400
docs: .github#26

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache/restore@v4, actions/checkout@v4, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
core-wheel: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache@v4, actions/checkout@v4, actions/download-artifact@v4, actions/setup-go@v5, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
lint: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0jE0IawAAAADNcL55q1IlRLnjbGxMCbSlUEhMMzBFREdFMDQxNwBFZGdl
lint: .github#9

! Failed to restore: Cache service responded with 400
lint: .github#54

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
test (8): .github#3

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0uk4IawAAAAC6tD3vPdkIRqIg1LVTj8WTU1RCRURHRTAzMTAARWRnZQ==
test (8): .github#9

! Failed to restore: Cache service responded with 400
test (8): .github#54

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
test (3): .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>02k4IawAAAACxtNaOOqIGRJm4BTK4l+njUEhMMzBFREdFMDQwNgBFZGdl
test (3): .github#9

! Failed to restore: Cache service responded with 400
test (3): .github#54

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Master Gate · 45846683375
Triggered via push about 12 minutes ago

JOBS
✓ docs in 43s (ID 140002064615)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Install just
  ✓ Set up Python
  ✓ Build and validate docs
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ core-wheel in 27s (ID 140002065096)
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
✓ lint in 4m54s (ID 140002347998)
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
✓ test (8) in 9m56s (ID 140002348205)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* test (6) (ID 140002348206)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (7) (ID 140002348215)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
✓ test (4) in 11m46s (ID 140002348218)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ test (5) in 8m38s (ID 140002348235)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* test (1) (ID 140002348268)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
✓ test (3) in 10m27s (ID 140002348276)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* test (2) (ID 140002348307)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
docs: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0c0wIawAAAACOXf5NpvwsR4nFqoZbJwHEQ08xRURHRTE2MjAARWRnZQ==
docs: .github#7

! Failed to restore: Cache service responded with 400
docs: .github#26

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache/restore@v4, actions/checkout@v4, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
core-wheel: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache@v4, actions/checkout@v4, actions/download-artifact@v4, actions/setup-go@v5, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
lint: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0jE0IawAAAADNcL55q1IlRLnjbGxMCbSlUEhMMzBFREdFMDQxNwBFZGdl
lint: .github#9

! Failed to restore: Cache service responded with 400
lint: .github#54

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
test (8): .github#3

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0uk4IawAAAAC6tD3vPdkIRqIg1LVTj8WTU1RCRURHRTAzMTAARWRnZQ==
test (8): .github#9

! Failed to restore: Cache service responded with 400
test (8): .github#54

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
test (3): .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>02k4IawAAAACxtNaOOqIGRJm4BTK4l+njUEhMMzBFREdFMDQwNgBFZGdl
test (3): .github#9

! Failed to restore: Cache service responded with 400
test (3): .github#54

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Master Gate · 45846683375
Triggered via push about 12 minutes ago

JOBS
✓ docs in 43s (ID 140002064615)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Install just
  ✓ Set up Python
  ✓ Build and validate docs
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ core-wheel in 27s (ID 140002065096)
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
✓ lint in 4m54s (ID 140002347998)
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
✓ test (8) in 9m56s (ID 140002348205)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* test (6) (ID 140002348206)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (7) (ID 140002348215)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
✓ test (4) in 11m46s (ID 140002348218)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ test (5) in 8m38s (ID 140002348235)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ test (1) in 12m8s (ID 140002348268)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ test (3) in 10m27s (ID 140002348276)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* test (2) (ID 140002348307)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
docs: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0c0wIawAAAACOXf5NpvwsR4nFqoZbJwHEQ08xRURHRTE2MjAARWRnZQ==
docs: .github#7

! Failed to restore: Cache service responded with 400
docs: .github#26

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache/restore@v4, actions/checkout@v4, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
core-wheel: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache@v4, actions/checkout@v4, actions/download-artifact@v4, actions/setup-go@v5, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
lint: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0jE0IawAAAADNcL55q1IlRLnjbGxMCbSlUEhMMzBFREdFMDQxNwBFZGdl
lint: .github#9

! Failed to restore: Cache service responded with 400
lint: .github#54

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
test (8): .github#3

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0uk4IawAAAAC6tD3vPdkIRqIg1LVTj8WTU1RCRURHRTAzMTAARWRnZQ==
test (8): .github#9

! Failed to restore: Cache service responded with 400
test (8): .github#54

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
test (3): .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>02k4IawAAAACxtNaOOqIGRJm4BTK4l+njUEhMMzBFREdFMDQwNgBFZGdl
test (3): .github#9

! Failed to restore: Cache service responded with 400
test (3): .github#54

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Master Gate · 45846683375
Triggered via push about 12 minutes ago

JOBS
✓ docs in 43s (ID 140002064615)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Install just
  ✓ Set up Python
  ✓ Build and validate docs
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ core-wheel in 27s (ID 140002065096)
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
✓ lint in 4m54s (ID 140002347998)
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
✓ test (8) in 9m56s (ID 140002348205)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* test (6) (ID 140002348206)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (7) (ID 140002348215)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
✓ test (4) in 11m46s (ID 140002348218)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ test (5) in 8m38s (ID 140002348235)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ test (1) in 12m8s (ID 140002348268)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ test (3) in 10m27s (ID 140002348276)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* test (2) (ID 140002348307)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
docs: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0c0wIawAAAACOXf5NpvwsR4nFqoZbJwHEQ08xRURHRTE2MjAARWRnZQ==
docs: .github#7

! Failed to restore: Cache service responded with 400
docs: .github#26

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache/restore@v4, actions/checkout@v4, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
core-wheel: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache@v4, actions/checkout@v4, actions/download-artifact@v4, actions/setup-go@v5, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
lint: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0jE0IawAAAADNcL55q1IlRLnjbGxMCbSlUEhMMzBFREdFMDQxNwBFZGdl
lint: .github#9

! Failed to restore: Cache service responded with 400
lint: .github#54

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
test (8): .github#3

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0uk4IawAAAAC6tD3vPdkIRqIg1LVTj8WTU1RCRURHRTAzMTAARWRnZQ==
test (8): .github#9

! Failed to restore: Cache service responded with 400
test (8): .github#54

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
test (3): .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>02k4IawAAAACxtNaOOqIGRJm4BTK4l+njUEhMMzBFREdFMDQwNgBFZGdl
test (3): .github#9

! Failed to restore: Cache service responded with 400
test (3): .github#54

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Master Gate · 45846683375
Triggered via push about 12 minutes ago

JOBS
✓ docs in 43s (ID 140002064615)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Install just
  ✓ Set up Python
  ✓ Build and validate docs
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ core-wheel in 27s (ID 140002065096)
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
✓ lint in 4m54s (ID 140002347998)
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
✓ test (8) in 9m56s (ID 140002348205)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* test (6) (ID 140002348206)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (7) (ID 140002348215)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
✓ test (4) in 11m46s (ID 140002348218)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ test (5) in 8m38s (ID 140002348235)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ test (1) in 12m8s (ID 140002348268)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ test (3) in 10m27s (ID 140002348276)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* test (2) (ID 140002348307)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
docs: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0c0wIawAAAACOXf5NpvwsR4nFqoZbJwHEQ08xRURHRTE2MjAARWRnZQ==
docs: .github#7

! Failed to restore: Cache service responded with 400
docs: .github#26

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache/restore@v4, actions/checkout@v4, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
core-wheel: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache@v4, actions/checkout@v4, actions/download-artifact@v4, actions/setup-go@v5, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
lint: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0jE0IawAAAADNcL55q1IlRLnjbGxMCbSlUEhMMzBFREdFMDQxNwBFZGdl
lint: .github#9

! Failed to restore: Cache service responded with 400
lint: .github#54

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
test (8): .github#3

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0uk4IawAAAAC6tD3vPdkIRqIg1LVTj8WTU1RCRURHRTAzMTAARWRnZQ==
test (8): .github#9

! Failed to restore: Cache service responded with 400
test (8): .github#54

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
test (3): .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>02k4IawAAAACxtNaOOqIGRJm4BTK4l+njUEhMMzBFREdFMDQwNgBFZGdl
test (3): .github#9

! Failed to restore: Cache service responded with 400
test (3): .github#54

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Master Gate · 45846683375
Triggered via push about 12 minutes ago

JOBS
✓ docs in 43s (ID 140002064615)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Install just
  ✓ Set up Python
  ✓ Build and validate docs
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ core-wheel in 27s (ID 140002065096)
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
✓ lint in 4m54s (ID 140002347998)
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
✓ test (8) in 9m56s (ID 140002348205)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* test (6) (ID 140002348206)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (7) (ID 140002348215)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
✓ test (4) in 11m46s (ID 140002348218)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ test (5) in 8m38s (ID 140002348235)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ test (1) in 12m8s (ID 140002348268)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ test (3) in 10m27s (ID 140002348276)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* test (2) (ID 140002348307)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
docs: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0c0wIawAAAACOXf5NpvwsR4nFqoZbJwHEQ08xRURHRTE2MjAARWRnZQ==
docs: .github#7

! Failed to restore: Cache service responded with 400
docs: .github#26

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache/restore@v4, actions/checkout@v4, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
core-wheel: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache@v4, actions/checkout@v4, actions/download-artifact@v4, actions/setup-go@v5, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
lint: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0jE0IawAAAADNcL55q1IlRLnjbGxMCbSlUEhMMzBFREdFMDQxNwBFZGdl
lint: .github#9

! Failed to restore: Cache service responded with 400
lint: .github#54

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
test (8): .github#3

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0uk4IawAAAAC6tD3vPdkIRqIg1LVTj8WTU1RCRURHRTAzMTAARWRnZQ==
test (8): .github#9

! Failed to restore: Cache service responded with 400
test (8): .github#54

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
test (3): .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>02k4IawAAAACxtNaOOqIGRJm4BTK4l+njUEhMMzBFREdFMDQwNgBFZGdl
test (3): .github#9

! Failed to restore: Cache service responded with 400
test (3): .github#54

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Master Gate · 45846683375
Triggered via push about 13 minutes ago

JOBS
✓ docs in 43s (ID 140002064615)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Install just
  ✓ Set up Python
  ✓ Build and validate docs
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ core-wheel in 27s (ID 140002065096)
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
✓ lint in 4m54s (ID 140002347998)
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
✓ test (8) in 9m56s (ID 140002348205)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* test (6) (ID 140002348206)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (7) (ID 140002348215)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
✓ test (4) in 11m46s (ID 140002348218)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ test (5) in 8m38s (ID 140002348235)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ test (1) in 12m8s (ID 140002348268)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ test (3) in 10m27s (ID 140002348276)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* test (2) (ID 140002348307)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
docs: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0c0wIawAAAACOXf5NpvwsR4nFqoZbJwHEQ08xRURHRTE2MjAARWRnZQ==
docs: .github#7

! Failed to restore: Cache service responded with 400
docs: .github#26

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache/restore@v4, actions/checkout@v4, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
core-wheel: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache@v4, actions/checkout@v4, actions/download-artifact@v4, actions/setup-go@v5, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
lint: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0jE0IawAAAADNcL55q1IlRLnjbGxMCbSlUEhMMzBFREdFMDQxNwBFZGdl
lint: .github#9

! Failed to restore: Cache service responded with 400
lint: .github#54

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
test (8): .github#3

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0uk4IawAAAAC6tD3vPdkIRqIg1LVTj8WTU1RCRURHRTAzMTAARWRnZQ==
test (8): .github#9

! Failed to restore: Cache service responded with 400
test (8): .github#54

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
test (3): .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>02k4IawAAAACxtNaOOqIGRJm4BTK4l+njUEhMMzBFREdFMDQwNgBFZGdl
test (3): .github#9

! Failed to restore: Cache service responded with 400
test (3): .github#54

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Master Gate · 45846683375
Triggered via push about 13 minutes ago

JOBS
✓ docs in 43s (ID 140002064615)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Install just
  ✓ Set up Python
  ✓ Build and validate docs
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ core-wheel in 27s (ID 140002065096)
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
✓ lint in 4m54s (ID 140002347998)
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
✓ test (8) in 9m56s (ID 140002348205)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* test (6) (ID 140002348206)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (7) (ID 140002348215)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
✓ test (4) in 11m46s (ID 140002348218)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ test (5) in 8m38s (ID 140002348235)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ test (1) in 12m8s (ID 140002348268)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ test (3) in 10m27s (ID 140002348276)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* test (2) (ID 140002348307)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
docs: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0c0wIawAAAACOXf5NpvwsR4nFqoZbJwHEQ08xRURHRTE2MjAARWRnZQ==
docs: .github#7

! Failed to restore: Cache service responded with 400
docs: .github#26

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache/restore@v4, actions/checkout@v4, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
core-wheel: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache@v4, actions/checkout@v4, actions/download-artifact@v4, actions/setup-go@v5, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
lint: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0jE0IawAAAADNcL55q1IlRLnjbGxMCbSlUEhMMzBFREdFMDQxNwBFZGdl
lint: .github#9

! Failed to restore: Cache service responded with 400
lint: .github#54

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
test (8): .github#3

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0uk4IawAAAAC6tD3vPdkIRqIg1LVTj8WTU1RCRURHRTAzMTAARWRnZQ==
test (8): .github#9

! Failed to restore: Cache service responded with 400
test (8): .github#54

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
test (3): .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>02k4IawAAAACxtNaOOqIGRJm4BTK4l+njUEhMMzBFREdFMDQwNgBFZGdl
test (3): .github#9

! Failed to restore: Cache service responded with 400
test (3): .github#54

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Master Gate · 45846683375
Triggered via push about 13 minutes ago

JOBS
✓ docs in 43s (ID 140002064615)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Install just
  ✓ Set up Python
  ✓ Build and validate docs
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ core-wheel in 27s (ID 140002065096)
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
✓ lint in 4m54s (ID 140002347998)
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
✓ test (8) in 9m56s (ID 140002348205)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* test (6) (ID 140002348206)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (7) (ID 140002348215)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
✓ test (4) in 11m46s (ID 140002348218)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ test (5) in 8m38s (ID 140002348235)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ test (1) in 12m8s (ID 140002348268)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ test (3) in 10m27s (ID 140002348276)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* test (2) (ID 140002348307)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
docs: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0c0wIawAAAACOXf5NpvwsR4nFqoZbJwHEQ08xRURHRTE2MjAARWRnZQ==
docs: .github#7

! Failed to restore: Cache service responded with 400
docs: .github#26

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache/restore@v4, actions/checkout@v4, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
core-wheel: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache@v4, actions/checkout@v4, actions/download-artifact@v4, actions/setup-go@v5, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
lint: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0jE0IawAAAADNcL55q1IlRLnjbGxMCbSlUEhMMzBFREdFMDQxNwBFZGdl
lint: .github#9

! Failed to restore: Cache service responded with 400
lint: .github#54

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
test (8): .github#3

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0uk4IawAAAAC6tD3vPdkIRqIg1LVTj8WTU1RCRURHRTAzMTAARWRnZQ==
test (8): .github#9

! Failed to restore: Cache service responded with 400
test (8): .github#54

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
test (3): .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>02k4IawAAAACxtNaOOqIGRJm4BTK4l+njUEhMMzBFREdFMDQwNgBFZGdl
test (3): .github#9

! Failed to restore: Cache service responded with 400
test (3): .github#54

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Master Gate · 45846683375
Triggered via push about 13 minutes ago

JOBS
✓ docs in 43s (ID 140002064615)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Install just
  ✓ Set up Python
  ✓ Build and validate docs
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ core-wheel in 27s (ID 140002065096)
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
✓ lint in 4m54s (ID 140002347998)
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
✓ test (8) in 9m56s (ID 140002348205)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* test (6) (ID 140002348206)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (7) (ID 140002348215)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
✓ test (4) in 11m46s (ID 140002348218)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ test (5) in 8m38s (ID 140002348235)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ test (1) in 12m8s (ID 140002348268)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ test (3) in 10m27s (ID 140002348276)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* test (2) (ID 140002348307)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
docs: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0c0wIawAAAACOXf5NpvwsR4nFqoZbJwHEQ08xRURHRTE2MjAARWRnZQ==
docs: .github#7

! Failed to restore: Cache service responded with 400
docs: .github#26

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache/restore@v4, actions/checkout@v4, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
core-wheel: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache@v4, actions/checkout@v4, actions/download-artifact@v4, actions/setup-go@v5, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
lint: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0jE0IawAAAADNcL55q1IlRLnjbGxMCbSlUEhMMzBFREdFMDQxNwBFZGdl
lint: .github#9

! Failed to restore: Cache service responded with 400
lint: .github#54

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
test (8): .github#3

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0uk4IawAAAAC6tD3vPdkIRqIg1LVTj8WTU1RCRURHRTAzMTAARWRnZQ==
test (8): .github#9

! Failed to restore: Cache service responded with 400
test (8): .github#54

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
test (3): .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>02k4IawAAAACxtNaOOqIGRJm4BTK4l+njUEhMMzBFREdFMDQwNgBFZGdl
test (3): .github#9

! Failed to restore: Cache service responded with 400
test (3): .github#54

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Master Gate · 45846683375
Triggered via push about 13 minutes ago

JOBS
✓ docs in 43s (ID 140002064615)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Install just
  ✓ Set up Python
  ✓ Build and validate docs
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ core-wheel in 27s (ID 140002065096)
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
✓ lint in 4m54s (ID 140002347998)
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
✓ test (8) in 9m56s (ID 140002348205)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* test (6) (ID 140002348206)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (7) (ID 140002348215)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
✓ test (4) in 11m46s (ID 140002348218)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ test (5) in 8m38s (ID 140002348235)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ test (1) in 12m8s (ID 140002348268)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ test (3) in 10m27s (ID 140002348276)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* test (2) (ID 140002348307)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
docs: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0c0wIawAAAACOXf5NpvwsR4nFqoZbJwHEQ08xRURHRTE2MjAARWRnZQ==
docs: .github#7

! Failed to restore: Cache service responded with 400
docs: .github#26

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache/restore@v4, actions/checkout@v4, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
core-wheel: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache@v4, actions/checkout@v4, actions/download-artifact@v4, actions/setup-go@v5, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
lint: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0jE0IawAAAADNcL55q1IlRLnjbGxMCbSlUEhMMzBFREdFMDQxNwBFZGdl
lint: .github#9

! Failed to restore: Cache service responded with 400
lint: .github#54

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
test (8): .github#3

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0uk4IawAAAAC6tD3vPdkIRqIg1LVTj8WTU1RCRURHRTAzMTAARWRnZQ==
test (8): .github#9

! Failed to restore: Cache service responded with 400
test (8): .github#54

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
test (3): .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>02k4IawAAAACxtNaOOqIGRJm4BTK4l+njUEhMMzBFREdFMDQwNgBFZGdl
test (3): .github#9

! Failed to restore: Cache service responded with 400
test (3): .github#54

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Master Gate · 45846683375
Triggered via push about 13 minutes ago

JOBS
✓ docs in 43s (ID 140002064615)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Install just
  ✓ Set up Python
  ✓ Build and validate docs
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ core-wheel in 27s (ID 140002065096)
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
✓ lint in 4m54s (ID 140002347998)
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
✓ test (8) in 9m56s (ID 140002348205)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* test (6) (ID 140002348206)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (7) (ID 140002348215)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
✓ test (4) in 11m46s (ID 140002348218)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ test (5) in 8m38s (ID 140002348235)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ test (1) in 12m8s (ID 140002348268)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ test (3) in 10m27s (ID 140002348276)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* test (2) (ID 140002348307)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
docs: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0c0wIawAAAACOXf5NpvwsR4nFqoZbJwHEQ08xRURHRTE2MjAARWRnZQ==
docs: .github#7

! Failed to restore: Cache service responded with 400
docs: .github#26

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache/restore@v4, actions/checkout@v4, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
core-wheel: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache@v4, actions/checkout@v4, actions/download-artifact@v4, actions/setup-go@v5, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
lint: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0jE0IawAAAADNcL55q1IlRLnjbGxMCbSlUEhMMzBFREdFMDQxNwBFZGdl
lint: .github#9

! Failed to restore: Cache service responded with 400
lint: .github#54

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
test (8): .github#3

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0uk4IawAAAAC6tD3vPdkIRqIg1LVTj8WTU1RCRURHRTAzMTAARWRnZQ==
test (8): .github#9

! Failed to restore: Cache service responded with 400
test (8): .github#54

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
test (3): .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>02k4IawAAAACxtNaOOqIGRJm4BTK4l+njUEhMMzBFREdFMDQwNgBFZGdl
test (3): .github#9

! Failed to restore: Cache service responded with 400
test (3): .github#54

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Master Gate · 45846683375
Triggered via push about 13 minutes ago

JOBS
✓ docs in 43s (ID 140002064615)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Install just
  ✓ Set up Python
  ✓ Build and validate docs
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ core-wheel in 27s (ID 140002065096)
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
✓ lint in 4m54s (ID 140002347998)
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
✓ test (8) in 9m56s (ID 140002348205)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* test (6) (ID 140002348206)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (7) (ID 140002348215)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
✓ test (4) in 11m46s (ID 140002348218)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ test (5) in 8m38s (ID 140002348235)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ test (1) in 12m8s (ID 140002348268)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ test (3) in 10m27s (ID 140002348276)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* test (2) (ID 140002348307)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
docs: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0c0wIawAAAACOXf5NpvwsR4nFqoZbJwHEQ08xRURHRTE2MjAARWRnZQ==
docs: .github#7

! Failed to restore: Cache service responded with 400
docs: .github#26

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache/restore@v4, actions/checkout@v4, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
core-wheel: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache@v4, actions/checkout@v4, actions/download-artifact@v4, actions/setup-go@v5, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
lint: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0jE0IawAAAADNcL55q1IlRLnjbGxMCbSlUEhMMzBFREdFMDQxNwBFZGdl
lint: .github#9

! Failed to restore: Cache service responded with 400
lint: .github#54

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
test (8): .github#3

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0uk4IawAAAAC6tD3vPdkIRqIg1LVTj8WTU1RCRURHRTAzMTAARWRnZQ==
test (8): .github#9

! Failed to restore: Cache service responded with 400
test (8): .github#54

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
test (3): .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>02k4IawAAAACxtNaOOqIGRJm4BTK4l+njUEhMMzBFREdFMDQwNgBFZGdl
test (3): .github#9

! Failed to restore: Cache service responded with 400
test (3): .github#54

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Master Gate · 45846683375
Triggered via push about 13 minutes ago

JOBS
✓ docs in 43s (ID 140002064615)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Install just
  ✓ Set up Python
  ✓ Build and validate docs
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ core-wheel in 27s (ID 140002065096)
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
✓ lint in 4m54s (ID 140002347998)
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
✓ test (8) in 9m56s (ID 140002348205)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* test (6) (ID 140002348206)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (7) (ID 140002348215)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
✓ test (4) in 11m46s (ID 140002348218)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ test (5) in 8m38s (ID 140002348235)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ test (1) in 12m8s (ID 140002348268)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ test (3) in 10m27s (ID 140002348276)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* test (2) (ID 140002348307)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
docs: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0c0wIawAAAACOXf5NpvwsR4nFqoZbJwHEQ08xRURHRTE2MjAARWRnZQ==
docs: .github#7

! Failed to restore: Cache service responded with 400
docs: .github#26

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache/restore@v4, actions/checkout@v4, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
core-wheel: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache@v4, actions/checkout@v4, actions/download-artifact@v4, actions/setup-go@v5, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
lint: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0jE0IawAAAADNcL55q1IlRLnjbGxMCbSlUEhMMzBFREdFMDQxNwBFZGdl
lint: .github#9

! Failed to restore: Cache service responded with 400
lint: .github#54

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
test (8): .github#3

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0uk4IawAAAAC6tD3vPdkIRqIg1LVTj8WTU1RCRURHRTAzMTAARWRnZQ==
test (8): .github#9

! Failed to restore: Cache service responded with 400
test (8): .github#54

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
test (3): .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>02k4IawAAAACxtNaOOqIGRJm4BTK4l+njUEhMMzBFREdFMDQwNgBFZGdl
test (3): .github#9

! Failed to restore: Cache service responded with 400
test (3): .github#54

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Master Gate · 45846683375
Triggered via push about 13 minutes ago

JOBS
✓ docs in 43s (ID 140002064615)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Install just
  ✓ Set up Python
  ✓ Build and validate docs
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ core-wheel in 27s (ID 140002065096)
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
✓ lint in 4m54s (ID 140002347998)
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
✓ test (8) in 9m56s (ID 140002348205)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* test (6) (ID 140002348206)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (7) (ID 140002348215)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
✓ test (4) in 11m46s (ID 140002348218)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ test (5) in 8m38s (ID 140002348235)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ test (1) in 12m8s (ID 140002348268)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ test (3) in 10m27s (ID 140002348276)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* test (2) (ID 140002348307)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
docs: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0c0wIawAAAACOXf5NpvwsR4nFqoZbJwHEQ08xRURHRTE2MjAARWRnZQ==
docs: .github#7

! Failed to restore: Cache service responded with 400
docs: .github#26

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache/restore@v4, actions/checkout@v4, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
core-wheel: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache@v4, actions/checkout@v4, actions/download-artifact@v4, actions/setup-go@v5, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
lint: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0jE0IawAAAADNcL55q1IlRLnjbGxMCbSlUEhMMzBFREdFMDQxNwBFZGdl
lint: .github#9

! Failed to restore: Cache service responded with 400
lint: .github#54

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
test (8): .github#3

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0uk4IawAAAAC6tD3vPdkIRqIg1LVTj8WTU1RCRURHRTAzMTAARWRnZQ==
test (8): .github#9

! Failed to restore: Cache service responded with 400
test (8): .github#54

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
test (3): .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>02k4IawAAAACxtNaOOqIGRJm4BTK4l+njUEhMMzBFREdFMDQwNgBFZGdl
test (3): .github#9

! Failed to restore: Cache service responded with 400
test (3): .github#54

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Master Gate · 45846683375
Triggered via push about 13 minutes ago

JOBS
✓ docs in 43s (ID 140002064615)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Install just
  ✓ Set up Python
  ✓ Build and validate docs
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ core-wheel in 27s (ID 140002065096)
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
✓ lint in 4m54s (ID 140002347998)
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
✓ test (8) in 9m56s (ID 140002348205)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* test (6) (ID 140002348206)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (7) (ID 140002348215)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
✓ test (4) in 11m46s (ID 140002348218)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ test (5) in 8m38s (ID 140002348235)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ test (1) in 12m8s (ID 140002348268)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ test (3) in 10m27s (ID 140002348276)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ test (2) in 13m7s (ID 140002348307)
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

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0c0wIawAAAACOXf5NpvwsR4nFqoZbJwHEQ08xRURHRTE2MjAARWRnZQ==
docs: .github#7

! Failed to restore: Cache service responded with 400
docs: .github#26

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache/restore@v4, actions/checkout@v4, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
core-wheel: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache@v4, actions/checkout@v4, actions/download-artifact@v4, actions/setup-go@v5, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
lint: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0jE0IawAAAADNcL55q1IlRLnjbGxMCbSlUEhMMzBFREdFMDQxNwBFZGdl
lint: .github#9

! Failed to restore: Cache service responded with 400
lint: .github#54

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
test (8): .github#3

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0uk4IawAAAAC6tD3vPdkIRqIg1LVTj8WTU1RCRURHRTAzMTAARWRnZQ==
test (8): .github#9

! Failed to restore: Cache service responded with 400
test (8): .github#54

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
test (3): .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>02k4IawAAAACxtNaOOqIGRJm4BTK4l+njUEhMMzBFREdFMDQwNgBFZGdl
test (3): .github#9

! Failed to restore: Cache service responded with 400
test (3): .github#54

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
test (2): .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0eU8IawAAAABGhFRqvBpBT7p99t2m0Kp4TVNQMzExMDAwMTA3MDQ1AEVkZ2U=
test (2): .github#9

! Failed to restore: Cache service responded with 400
test (2): .github#54

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Master Gate · 45846683375
Triggered via push about 13 minutes ago

JOBS
✓ docs in 43s (ID 140002064615)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Install just
  ✓ Set up Python
  ✓ Build and validate docs
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ core-wheel in 27s (ID 140002065096)
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
✓ lint in 4m54s (ID 140002347998)
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
✓ test (8) in 9m56s (ID 140002348205)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* test (6) (ID 140002348206)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (7) (ID 140002348215)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
✓ test (4) in 11m46s (ID 140002348218)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ test (5) in 8m38s (ID 140002348235)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ test (1) in 12m8s (ID 140002348268)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ test (3) in 10m27s (ID 140002348276)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ test (2) in 13m7s (ID 140002348307)
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

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0c0wIawAAAACOXf5NpvwsR4nFqoZbJwHEQ08xRURHRTE2MjAARWRnZQ==
docs: .github#7

! Failed to restore: Cache service responded with 400
docs: .github#26

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache/restore@v4, actions/checkout@v4, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
core-wheel: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache@v4, actions/checkout@v4, actions/download-artifact@v4, actions/setup-go@v5, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
lint: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0jE0IawAAAADNcL55q1IlRLnjbGxMCbSlUEhMMzBFREdFMDQxNwBFZGdl
lint: .github#9

! Failed to restore: Cache service responded with 400
lint: .github#54

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
test (8): .github#3

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0uk4IawAAAAC6tD3vPdkIRqIg1LVTj8WTU1RCRURHRTAzMTAARWRnZQ==
test (8): .github#9

! Failed to restore: Cache service responded with 400
test (8): .github#54

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
test (3): .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>02k4IawAAAACxtNaOOqIGRJm4BTK4l+njUEhMMzBFREdFMDQwNgBFZGdl
test (3): .github#9

! Failed to restore: Cache service responded with 400
test (3): .github#54

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
test (2): .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0eU8IawAAAABGhFRqvBpBT7p99t2m0Kp4TVNQMzExMDAwMTA3MDQ1AEVkZ2U=
test (2): .github#9

! Failed to restore: Cache service responded with 400
test (2): .github#54

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Master Gate · 45846683375
Triggered via push about 13 minutes ago

JOBS
✓ docs in 43s (ID 140002064615)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Install just
  ✓ Set up Python
  ✓ Build and validate docs
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ core-wheel in 27s (ID 140002065096)
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
✓ lint in 4m54s (ID 140002347998)
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
✓ test (8) in 9m56s (ID 140002348205)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* test (6) (ID 140002348206)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (7) (ID 140002348215)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
✓ test (4) in 11m46s (ID 140002348218)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ test (5) in 8m38s (ID 140002348235)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ test (1) in 12m8s (ID 140002348268)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ test (3) in 10m27s (ID 140002348276)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ test (2) in 13m7s (ID 140002348307)
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

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0c0wIawAAAACOXf5NpvwsR4nFqoZbJwHEQ08xRURHRTE2MjAARWRnZQ==
docs: .github#7

! Failed to restore: Cache service responded with 400
docs: .github#26

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache/restore@v4, actions/checkout@v4, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
core-wheel: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache@v4, actions/checkout@v4, actions/download-artifact@v4, actions/setup-go@v5, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
lint: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0jE0IawAAAADNcL55q1IlRLnjbGxMCbSlUEhMMzBFREdFMDQxNwBFZGdl
lint: .github#9

! Failed to restore: Cache service responded with 400
lint: .github#54

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
test (8): .github#3

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0uk4IawAAAAC6tD3vPdkIRqIg1LVTj8WTU1RCRURHRTAzMTAARWRnZQ==
test (8): .github#9

! Failed to restore: Cache service responded with 400
test (8): .github#54

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
test (3): .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>02k4IawAAAACxtNaOOqIGRJm4BTK4l+njUEhMMzBFREdFMDQwNgBFZGdl
test (3): .github#9

! Failed to restore: Cache service responded with 400
test (3): .github#54

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
test (2): .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0eU8IawAAAABGhFRqvBpBT7p99t2m0Kp4TVNQMzExMDAwMTA3MDQ1AEVkZ2U=
test (2): .github#9

! Failed to restore: Cache service responded with 400
test (2): .github#54

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Master Gate · 45846683375
Triggered via push about 13 minutes ago

JOBS
✓ docs in 43s (ID 140002064615)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Install just
  ✓ Set up Python
  ✓ Build and validate docs
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ core-wheel in 27s (ID 140002065096)
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
✓ lint in 4m54s (ID 140002347998)
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
✓ test (8) in 9m56s (ID 140002348205)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* test (6) (ID 140002348206)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
✓ test (7) in 13m21s (ID 140002348215)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ test (4) in 11m46s (ID 140002348218)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ test (5) in 8m38s (ID 140002348235)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ test (1) in 12m8s (ID 140002348268)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ test (3) in 10m27s (ID 140002348276)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ test (2) in 13m7s (ID 140002348307)
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

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0c0wIawAAAACOXf5NpvwsR4nFqoZbJwHEQ08xRURHRTE2MjAARWRnZQ==
docs: .github#7

! Failed to restore: Cache service responded with 400
docs: .github#26

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache/restore@v4, actions/checkout@v4, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
core-wheel: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache@v4, actions/checkout@v4, actions/download-artifact@v4, actions/setup-go@v5, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
lint: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0jE0IawAAAADNcL55q1IlRLnjbGxMCbSlUEhMMzBFREdFMDQxNwBFZGdl
lint: .github#9

! Failed to restore: Cache service responded with 400
lint: .github#54

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
test (8): .github#3

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0uk4IawAAAAC6tD3vPdkIRqIg1LVTj8WTU1RCRURHRTAzMTAARWRnZQ==
test (8): .github#9

! Failed to restore: Cache service responded with 400
test (8): .github#54

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
test (3): .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>02k4IawAAAACxtNaOOqIGRJm4BTK4l+njUEhMMzBFREdFMDQwNgBFZGdl
test (3): .github#9

! Failed to restore: Cache service responded with 400
test (3): .github#54

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
test (2): .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0eU8IawAAAABGhFRqvBpBT7p99t2m0Kp4TVNQMzExMDAwMTA3MDQ1AEVkZ2U=
test (2): .github#9

! Failed to restore: Cache service responded with 400
test (2): .github#54

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Master Gate · 45846683375
Triggered via push about 13 minutes ago

JOBS
✓ docs in 43s (ID 140002064615)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Install just
  ✓ Set up Python
  ✓ Build and validate docs
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ core-wheel in 27s (ID 140002065096)
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
✓ lint in 4m54s (ID 140002347998)
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
✓ test (8) in 9m56s (ID 140002348205)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* test (6) (ID 140002348206)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
✓ test (7) in 13m21s (ID 140002348215)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ test (4) in 11m46s (ID 140002348218)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ test (5) in 8m38s (ID 140002348235)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ test (1) in 12m8s (ID 140002348268)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ test (3) in 10m27s (ID 140002348276)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ test (2) in 13m7s (ID 140002348307)
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

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0c0wIawAAAACOXf5NpvwsR4nFqoZbJwHEQ08xRURHRTE2MjAARWRnZQ==
docs: .github#7

! Failed to restore: Cache service responded with 400
docs: .github#26

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache/restore@v4, actions/checkout@v4, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
core-wheel: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache@v4, actions/checkout@v4, actions/download-artifact@v4, actions/setup-go@v5, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
lint: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0jE0IawAAAADNcL55q1IlRLnjbGxMCbSlUEhMMzBFREdFMDQxNwBFZGdl
lint: .github#9

! Failed to restore: Cache service responded with 400
lint: .github#54

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
test (8): .github#3

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0uk4IawAAAAC6tD3vPdkIRqIg1LVTj8WTU1RCRURHRTAzMTAARWRnZQ==
test (8): .github#9

! Failed to restore: Cache service responded with 400
test (8): .github#54

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
test (3): .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>02k4IawAAAACxtNaOOqIGRJm4BTK4l+njUEhMMzBFREdFMDQwNgBFZGdl
test (3): .github#9

! Failed to restore: Cache service responded with 400
test (3): .github#54

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
test (2): .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0eU8IawAAAABGhFRqvBpBT7p99t2m0Kp4TVNQMzExMDAwMTA3MDQ1AEVkZ2U=
test (2): .github#9

! Failed to restore: Cache service responded with 400
test (2): .github#54

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Master Gate · 45846683375
Triggered via push about 14 minutes ago

JOBS
✓ docs in 43s (ID 140002064615)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Install just
  ✓ Set up Python
  ✓ Build and validate docs
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ core-wheel in 27s (ID 140002065096)
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
✓ lint in 4m54s (ID 140002347998)
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
✓ test (8) in 9m56s (ID 140002348205)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* test (6) (ID 140002348206)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
✓ test (7) in 13m21s (ID 140002348215)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ test (4) in 11m46s (ID 140002348218)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ test (5) in 8m38s (ID 140002348235)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ test (1) in 12m8s (ID 140002348268)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ test (3) in 10m27s (ID 140002348276)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ test (2) in 13m7s (ID 140002348307)
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

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0c0wIawAAAACOXf5NpvwsR4nFqoZbJwHEQ08xRURHRTE2MjAARWRnZQ==
docs: .github#7

! Failed to restore: Cache service responded with 400
docs: .github#26

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache/restore@v4, actions/checkout@v4, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
core-wheel: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache@v4, actions/checkout@v4, actions/download-artifact@v4, actions/setup-go@v5, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
lint: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0jE0IawAAAADNcL55q1IlRLnjbGxMCbSlUEhMMzBFREdFMDQxNwBFZGdl
lint: .github#9

! Failed to restore: Cache service responded with 400
lint: .github#54

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
test (8): .github#3

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0uk4IawAAAAC6tD3vPdkIRqIg1LVTj8WTU1RCRURHRTAzMTAARWRnZQ==
test (8): .github#9

! Failed to restore: Cache service responded with 400
test (8): .github#54

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
test (3): .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>02k4IawAAAACxtNaOOqIGRJm4BTK4l+njUEhMMzBFREdFMDQwNgBFZGdl
test (3): .github#9

! Failed to restore: Cache service responded with 400
test (3): .github#54

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
test (2): .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0eU8IawAAAABGhFRqvBpBT7p99t2m0Kp4TVNQMzExMDAwMTA3MDQ1AEVkZ2U=
test (2): .github#9

! Failed to restore: Cache service responded with 400
test (2): .github#54

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Master Gate · 45846683375
Triggered via push about 14 minutes ago

JOBS
✓ docs in 43s (ID 140002064615)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Install just
  ✓ Set up Python
  ✓ Build and validate docs
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ core-wheel in 27s (ID 140002065096)
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
✓ lint in 4m54s (ID 140002347998)
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
✓ test (8) in 9m56s (ID 140002348205)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* test (6) (ID 140002348206)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
✓ test (7) in 13m21s (ID 140002348215)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ test (4) in 11m46s (ID 140002348218)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ test (5) in 8m38s (ID 140002348235)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ test (1) in 12m8s (ID 140002348268)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ test (3) in 10m27s (ID 140002348276)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ test (2) in 13m7s (ID 140002348307)
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

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0c0wIawAAAACOXf5NpvwsR4nFqoZbJwHEQ08xRURHRTE2MjAARWRnZQ==
docs: .github#7

! Failed to restore: Cache service responded with 400
docs: .github#26

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache/restore@v4, actions/checkout@v4, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
core-wheel: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache@v4, actions/checkout@v4, actions/download-artifact@v4, actions/setup-go@v5, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
lint: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0jE0IawAAAADNcL55q1IlRLnjbGxMCbSlUEhMMzBFREdFMDQxNwBFZGdl
lint: .github#9

! Failed to restore: Cache service responded with 400
lint: .github#54

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
test (8): .github#3

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0uk4IawAAAAC6tD3vPdkIRqIg1LVTj8WTU1RCRURHRTAzMTAARWRnZQ==
test (8): .github#9

! Failed to restore: Cache service responded with 400
test (8): .github#54

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
test (3): .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>02k4IawAAAACxtNaOOqIGRJm4BTK4l+njUEhMMzBFREdFMDQwNgBFZGdl
test (3): .github#9

! Failed to restore: Cache service responded with 400
test (3): .github#54

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
test (2): .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0eU8IawAAAABGhFRqvBpBT7p99t2m0Kp4TVNQMzExMDAwMTA3MDQ1AEVkZ2U=
test (2): .github#9

! Failed to restore: Cache service responded with 400
test (2): .github#54

✓ master Master Gate · 45846683375
Triggered via push about 14 minutes ago

JOBS
✓ docs in 43s (ID 140002064615)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Install just
  ✓ Set up Python
  ✓ Build and validate docs
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ core-wheel in 27s (ID 140002065096)
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
✓ lint in 4m54s (ID 140002347998)
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
✓ test (8) in 9m56s (ID 140002348205)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ test (6) in 13m34s (ID 140002348206)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ test (7) in 13m21s (ID 140002348215)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ test (4) in 11m46s (ID 140002348218)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ test (5) in 8m38s (ID 140002348235)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ test (1) in 12m8s (ID 140002348268)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ test (3) in 10m27s (ID 140002348276)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ test (2) in 13m7s (ID 140002348307)
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

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0c0wIawAAAACOXf5NpvwsR4nFqoZbJwHEQ08xRURHRTE2MjAARWRnZQ==
docs: .github#7

! Failed to restore: Cache service responded with 400
docs: .github#26

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache/restore@v4, actions/checkout@v4, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
core-wheel: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache@v4, actions/checkout@v4, actions/download-artifact@v4, actions/setup-go@v5, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
lint: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0jE0IawAAAADNcL55q1IlRLnjbGxMCbSlUEhMMzBFREdFMDQxNwBFZGdl
lint: .github#9

! Failed to restore: Cache service responded with 400
lint: .github#54

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
test (8): .github#3

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0uk4IawAAAAC6tD3vPdkIRqIg1LVTj8WTU1RCRURHRTAzMTAARWRnZQ==
test (8): .github#9

! Failed to restore: Cache service responded with 400
test (8): .github#54

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
test (3): .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>02k4IawAAAACxtNaOOqIGRJm4BTK4l+njUEhMMzBFREdFMDQwNgBFZGdl
test (3): .github#9

! Failed to restore: Cache service responded with 400
test (3): .github#54

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
test (2): .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0eU8IawAAAABGhFRqvBpBT7p99t2m0Kp4TVNQMzExMDAwMTA3MDQ1AEVkZ2U=
test (2): .github#9

! Failed to restore: Cache service responded with 400
test (2): .github#54


