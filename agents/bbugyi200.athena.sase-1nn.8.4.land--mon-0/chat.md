# Chat History - ace-run (sase-1nn.8.4.land--mon-0)

- **TIMESTAMP:** 2026-10-24 11:37:59 EDT
- **MODEL:** codex/gpt-6-luna
- **AGENT:** sase-1nn.8.4.land--mon-0

## Prompt

sase monitor start --command 'gh run watch 40101618059 -R sase-org/sase --interval 120 --exit-status' --reason 'Observe scheduled Full CI for the approved sase 0.18.1 release gates'

## Response

sase: running unwrapped (no profile (monitor.tool_wrap is verify))
Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* master Full CI · 40101618059
Triggered via workflow_dispatch about 18 minutes ago

JOBS
✓ full / prepare in 21s (ID 120894787205)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Validate qualification inputs
  - Download the sealed candidate manifest
  - Bind published identity from the sealed manifest
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
- full / docs-build in 0s (ID 120894788065)
- full / release-core-floor-smoke in 0s (ID 120894788195)
✓ full / build-core / build-core in 15m0s (ID 120894871757)
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
* full / visual-test (ID 120898126634)
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
* full / perf-floors (ID 120898126640)
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
✓ full / ace-page-group-isolation in 1m41s (ID 120898126672)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  ✓ Run ACE shared-page isolation lane
  ✓ Post Install visual dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* full / test (3.14) (ID 120898126703)
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
* full / test (3.13) (ID 120898126705)
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
✓ full / tutorial-tests in 57s (ID 120898126715)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run tutorial tests
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* full / test (3.12) (ID 120898126799)
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
* full / lint (ID 120898127009)
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

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / prepare: .github#6

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / prepare: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / build-core / build-core: .github#4

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>06MDcagAAAABlR3X2rL5lQKrpisTUl4fuU0xDMzFFREdFMDIyMABFZGdl
full / build-core / build-core: .github#7

! Failed to restore: Cache service responded with 400
full / build-core / build-core: .github#25

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / build-core / build-core: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / ace-page-group-isolation: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0UcHcagAAAABoxZI+wa2fSI+qzPyP3AN1UEhMMzBFREdFMDQxOABFZGdl
full / ace-page-group-isolation: .github#9

! Failed to restore: Cache service responded with 400
full / ace-page-group-isolation: .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / ace-page-group-isolation: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / tutorial-tests: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0JcHcagAAAABh43fuT51GRaeM4a3iJHApUEhYMzFFREdFMDIxNwBFZGdl
full / tutorial-tests: .github#9

! Failed to restore: Cache service responded with 400
full / tutorial-tests: .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / tutorial-tests: .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* master Full CI · 40101618059
Triggered via workflow_dispatch about 20 minutes ago

JOBS
✓ full / prepare in 21s (ID 120894787205)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Validate qualification inputs
  - Download the sealed candidate manifest
  - Bind published identity from the sealed manifest
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
- full / docs-build in 0s (ID 120894788065)
- full / release-core-floor-smoke in 0s (ID 120894788195)
✓ full / build-core / build-core in 15m0s (ID 120894871757)
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
* full / visual-test (ID 120898126634)
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
* full / perf-floors (ID 120898126640)
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
✓ full / ace-page-group-isolation in 1m41s (ID 120898126672)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  ✓ Run ACE shared-page isolation lane
  ✓ Post Install visual dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* full / test (3.14) (ID 120898126703)
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
* full / test (3.13) (ID 120898126705)
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
✓ full / tutorial-tests in 57s (ID 120898126715)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run tutorial tests
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* full / test (3.12) (ID 120898126799)
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
* full / lint (ID 120898127009)
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

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / prepare: .github#6

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / prepare: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / build-core / build-core: .github#4

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>06MDcagAAAABlR3X2rL5lQKrpisTUl4fuU0xDMzFFREdFMDIyMABFZGdl
full / build-core / build-core: .github#7

! Failed to restore: Cache service responded with 400
full / build-core / build-core: .github#25

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / build-core / build-core: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / ace-page-group-isolation: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0UcHcagAAAABoxZI+wa2fSI+qzPyP3AN1UEhMMzBFREdFMDQxOABFZGdl
full / ace-page-group-isolation: .github#9

! Failed to restore: Cache service responded with 400
full / ace-page-group-isolation: .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / ace-page-group-isolation: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / tutorial-tests: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0JcHcagAAAABh43fuT51GRaeM4a3iJHApUEhYMzFFREdFMDIxNwBFZGdl
full / tutorial-tests: .github#9

! Failed to restore: Cache service responded with 400
full / tutorial-tests: .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / tutorial-tests: .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* master Full CI · 40101618059
Triggered via workflow_dispatch about 22 minutes ago

JOBS
✓ full / prepare in 21s (ID 120894787205)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Validate qualification inputs
  - Download the sealed candidate manifest
  - Bind published identity from the sealed manifest
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
- full / docs-build in 0s (ID 120894788065)
- full / release-core-floor-smoke in 0s (ID 120894788195)
✓ full / build-core / build-core in 15m0s (ID 120894871757)
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
* full / visual-test (ID 120898126634)
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
* full / perf-floors (ID 120898126640)
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
✓ full / ace-page-group-isolation in 1m41s (ID 120898126672)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  ✓ Run ACE shared-page isolation lane
  ✓ Post Install visual dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* full / test (3.14) (ID 120898126703)
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
* full / test (3.13) (ID 120898126705)
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
✓ full / tutorial-tests in 57s (ID 120898126715)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run tutorial tests
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* full / test (3.12) (ID 120898126799)
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
✓ full / lint in 6m35s (ID 120898127009)
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

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / prepare: .github#6

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / prepare: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / build-core / build-core: .github#4

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>06MDcagAAAABlR3X2rL5lQKrpisTUl4fuU0xDMzFFREdFMDIyMABFZGdl
full / build-core / build-core: .github#7

! Failed to restore: Cache service responded with 400
full / build-core / build-core: .github#25

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / build-core / build-core: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / ace-page-group-isolation: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0UcHcagAAAABoxZI+wa2fSI+qzPyP3AN1UEhMMzBFREdFMDQxOABFZGdl
full / ace-page-group-isolation: .github#9

! Failed to restore: Cache service responded with 400
full / ace-page-group-isolation: .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / ace-page-group-isolation: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / tutorial-tests: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0JcHcagAAAABh43fuT51GRaeM4a3iJHApUEhYMzFFREdFMDIxNwBFZGdl
full / tutorial-tests: .github#9

! Failed to restore: Cache service responded with 400
full / tutorial-tests: .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / tutorial-tests: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache@v4, actions/checkout@v4, actions/download-artifact@v4, actions/setup-go@v5, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / lint: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0d8LcagAAAACYA++vdYxJTbF5QtY5X7vMUEhMMzBFREdFMDIwOQBFZGdl
full / lint: .github#9

! Failed to restore: Cache service responded with 400
full / lint: .github#46

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / lint: .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* master Full CI · 40101618059
Triggered via workflow_dispatch about 24 minutes ago

JOBS
✓ full / prepare in 21s (ID 120894787205)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Validate qualification inputs
  - Download the sealed candidate manifest
  - Bind published identity from the sealed manifest
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
- full / docs-build in 0s (ID 120894788065)
- full / release-core-floor-smoke in 0s (ID 120894788195)
✓ full / build-core / build-core in 15m0s (ID 120894871757)
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
* full / visual-test (ID 120898126634)
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
* full / perf-floors (ID 120898126640)
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
  * Run bead scaled-corpus benchmark (record-only 4x)
  * Upload bead scaled-corpus benchmark
  * Run bead history-independence gate (1x+4x)
  * Upload bead history-independence gate report
  * Post Install dependencies
  * Post Run actions/checkout@v4
✓ full / ace-page-group-isolation in 1m41s (ID 120898126672)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  ✓ Run ACE shared-page isolation lane
  ✓ Post Install visual dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* full / test (3.14) (ID 120898126703)
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
* full / test (3.13) (ID 120898126705)
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
✓ full / tutorial-tests in 57s (ID 120898126715)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run tutorial tests
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* full / test (3.12) (ID 120898126799)
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
✓ full / lint in 6m35s (ID 120898127009)
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

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / prepare: .github#6

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / prepare: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / build-core / build-core: .github#4

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>06MDcagAAAABlR3X2rL5lQKrpisTUl4fuU0xDMzFFREdFMDIyMABFZGdl
full / build-core / build-core: .github#7

! Failed to restore: Cache service responded with 400
full / build-core / build-core: .github#25

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / build-core / build-core: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / ace-page-group-isolation: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0UcHcagAAAABoxZI+wa2fSI+qzPyP3AN1UEhMMzBFREdFMDQxOABFZGdl
full / ace-page-group-isolation: .github#9

! Failed to restore: Cache service responded with 400
full / ace-page-group-isolation: .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / ace-page-group-isolation: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / tutorial-tests: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0JcHcagAAAABh43fuT51GRaeM4a3iJHApUEhYMzFFREdFMDIxNwBFZGdl
full / tutorial-tests: .github#9

! Failed to restore: Cache service responded with 400
full / tutorial-tests: .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / tutorial-tests: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache@v4, actions/checkout@v4, actions/download-artifact@v4, actions/setup-go@v5, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / lint: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0d8LcagAAAACYA++vdYxJTbF5QtY5X7vMUEhMMzBFREdFMDIwOQBFZGdl
full / lint: .github#9

! Failed to restore: Cache service responded with 400
full / lint: .github#46

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / lint: .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* master Full CI · 40101618059
Triggered via workflow_dispatch about 26 minutes ago

JOBS
✓ full / prepare in 21s (ID 120894787205)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Validate qualification inputs
  - Download the sealed candidate manifest
  - Bind published identity from the sealed manifest
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
- full / docs-build in 0s (ID 120894788065)
- full / release-core-floor-smoke in 0s (ID 120894788195)
✓ full / build-core / build-core in 15m0s (ID 120894871757)
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
* full / visual-test (ID 120898126634)
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
✓ full / perf-floors in 9m54s (ID 120898126640)
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
✓ full / ace-page-group-isolation in 1m41s (ID 120898126672)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  ✓ Run ACE shared-page isolation lane
  ✓ Post Install visual dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* full / test (3.14) (ID 120898126703)
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
* full / test (3.13) (ID 120898126705)
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
✓ full / tutorial-tests in 57s (ID 120898126715)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run tutorial tests
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* full / test (3.12) (ID 120898126799)
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
✓ full / lint in 6m35s (ID 120898127009)
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

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / prepare: .github#6

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / prepare: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / build-core / build-core: .github#4

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>06MDcagAAAABlR3X2rL5lQKrpisTUl4fuU0xDMzFFREdFMDIyMABFZGdl
full / build-core / build-core: .github#7

! Failed to restore: Cache service responded with 400
full / build-core / build-core: .github#25

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / build-core / build-core: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / ace-page-group-isolation: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0UcHcagAAAABoxZI+wa2fSI+qzPyP3AN1UEhMMzBFREdFMDQxOABFZGdl
full / ace-page-group-isolation: .github#9

! Failed to restore: Cache service responded with 400
full / ace-page-group-isolation: .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / ace-page-group-isolation: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / tutorial-tests: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0JcHcagAAAABh43fuT51GRaeM4a3iJHApUEhYMzFFREdFMDIxNwBFZGdl
full / tutorial-tests: .github#9

! Failed to restore: Cache service responded with 400
full / tutorial-tests: .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / tutorial-tests: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache@v4, actions/checkout@v4, actions/download-artifact@v4, actions/setup-go@v5, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / lint: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0d8LcagAAAACYA++vdYxJTbF5QtY5X7vMUEhMMzBFREdFMDIwOQBFZGdl
full / lint: .github#9

! Failed to restore: Cache service responded with 400
full / lint: .github#46

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / lint: .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* master Full CI · 40101618059
Triggered via workflow_dispatch about 28 minutes ago

JOBS
✓ full / prepare in 21s (ID 120894787205)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Validate qualification inputs
  - Download the sealed candidate manifest
  - Bind published identity from the sealed manifest
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
- full / docs-build in 0s (ID 120894788065)
- full / release-core-floor-smoke in 0s (ID 120894788195)
✓ full / build-core / build-core in 15m0s (ID 120894871757)
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
* full / visual-test (ID 120898126634)
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
✓ full / perf-floors in 9m54s (ID 120898126640)
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
✓ full / ace-page-group-isolation in 1m41s (ID 120898126672)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  ✓ Run ACE shared-page isolation lane
  ✓ Post Install visual dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* full / test (3.14) (ID 120898126703)
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
* full / test (3.13) (ID 120898126705)
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
✓ full / tutorial-tests in 57s (ID 120898126715)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run tutorial tests
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* full / test (3.12) (ID 120898126799)
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
✓ full / lint in 6m35s (ID 120898127009)
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

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / prepare: .github#6

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / prepare: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / build-core / build-core: .github#4

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>06MDcagAAAABlR3X2rL5lQKrpisTUl4fuU0xDMzFFREdFMDIyMABFZGdl
full / build-core / build-core: .github#7

! Failed to restore: Cache service responded with 400
full / build-core / build-core: .github#25

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / build-core / build-core: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / ace-page-group-isolation: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0UcHcagAAAABoxZI+wa2fSI+qzPyP3AN1UEhMMzBFREdFMDQxOABFZGdl
full / ace-page-group-isolation: .github#9

! Failed to restore: Cache service responded with 400
full / ace-page-group-isolation: .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / ace-page-group-isolation: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / tutorial-tests: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0JcHcagAAAABh43fuT51GRaeM4a3iJHApUEhYMzFFREdFMDIxNwBFZGdl
full / tutorial-tests: .github#9

! Failed to restore: Cache service responded with 400
full / tutorial-tests: .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / tutorial-tests: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache@v4, actions/checkout@v4, actions/download-artifact@v4, actions/setup-go@v5, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / lint: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0d8LcagAAAACYA++vdYxJTbF5QtY5X7vMUEhMMzBFREdFMDIwOQBFZGdl
full / lint: .github#9

! Failed to restore: Cache service responded with 400
full / lint: .github#46

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / lint: .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* master Full CI · 40101618059
Triggered via workflow_dispatch about 30 minutes ago

JOBS
✓ full / prepare in 21s (ID 120894787205)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Validate qualification inputs
  - Download the sealed candidate manifest
  - Bind published identity from the sealed manifest
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
- full / docs-build in 0s (ID 120894788065)
- full / release-core-floor-smoke in 0s (ID 120894788195)
✓ full / build-core / build-core in 15m0s (ID 120894871757)
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
* full / visual-test (ID 120898126634)
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
✓ full / perf-floors in 9m54s (ID 120898126640)
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
✓ full / ace-page-group-isolation in 1m41s (ID 120898126672)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  ✓ Run ACE shared-page isolation lane
  ✓ Post Install visual dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* full / test (3.14) (ID 120898126703)
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
* full / test (3.13) (ID 120898126705)
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
✓ full / tutorial-tests in 57s (ID 120898126715)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run tutorial tests
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* full / test (3.12) (ID 120898126799)
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
✓ full / lint in 6m35s (ID 120898127009)
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

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / prepare: .github#6

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / prepare: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / build-core / build-core: .github#4

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>06MDcagAAAABlR3X2rL5lQKrpisTUl4fuU0xDMzFFREdFMDIyMABFZGdl
full / build-core / build-core: .github#7

! Failed to restore: Cache service responded with 400
full / build-core / build-core: .github#25

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / build-core / build-core: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / ace-page-group-isolation: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0UcHcagAAAABoxZI+wa2fSI+qzPyP3AN1UEhMMzBFREdFMDQxOABFZGdl
full / ace-page-group-isolation: .github#9

! Failed to restore: Cache service responded with 400
full / ace-page-group-isolation: .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / ace-page-group-isolation: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / tutorial-tests: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0JcHcagAAAABh43fuT51GRaeM4a3iJHApUEhYMzFFREdFMDIxNwBFZGdl
full / tutorial-tests: .github#9

! Failed to restore: Cache service responded with 400
full / tutorial-tests: .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / tutorial-tests: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache@v4, actions/checkout@v4, actions/download-artifact@v4, actions/setup-go@v5, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / lint: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0d8LcagAAAACYA++vdYxJTbF5QtY5X7vMUEhMMzBFREdFMDIwOQBFZGdl
full / lint: .github#9

! Failed to restore: Cache service responded with 400
full / lint: .github#46

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / lint: .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* master Full CI · 40101618059
Triggered via workflow_dispatch about 32 minutes ago

JOBS
✓ full / prepare in 21s (ID 120894787205)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Validate qualification inputs
  - Download the sealed candidate manifest
  - Bind published identity from the sealed manifest
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
- full / docs-build in 0s (ID 120894788065)
- full / release-core-floor-smoke in 0s (ID 120894788195)
✓ full / build-core / build-core in 15m0s (ID 120894871757)
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
* full / visual-test (ID 120898126634)
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
✓ full / perf-floors in 9m54s (ID 120898126640)
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
✓ full / ace-page-group-isolation in 1m41s (ID 120898126672)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  ✓ Run ACE shared-page isolation lane
  ✓ Post Install visual dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* full / test (3.14) (ID 120898126703)
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
* full / test (3.13) (ID 120898126705)
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
✓ full / tutorial-tests in 57s (ID 120898126715)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run tutorial tests
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* full / test (3.12) (ID 120898126799)
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
✓ full / lint in 6m35s (ID 120898127009)
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

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / prepare: .github#6

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / prepare: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / build-core / build-core: .github#4

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>06MDcagAAAABlR3X2rL5lQKrpisTUl4fuU0xDMzFFREdFMDIyMABFZGdl
full / build-core / build-core: .github#7

! Failed to restore: Cache service responded with 400
full / build-core / build-core: .github#25

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / build-core / build-core: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / ace-page-group-isolation: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0UcHcagAAAABoxZI+wa2fSI+qzPyP3AN1UEhMMzBFREdFMDQxOABFZGdl
full / ace-page-group-isolation: .github#9

! Failed to restore: Cache service responded with 400
full / ace-page-group-isolation: .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / ace-page-group-isolation: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / tutorial-tests: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0JcHcagAAAABh43fuT51GRaeM4a3iJHApUEhYMzFFREdFMDIxNwBFZGdl
full / tutorial-tests: .github#9

! Failed to restore: Cache service responded with 400
full / tutorial-tests: .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / tutorial-tests: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache@v4, actions/checkout@v4, actions/download-artifact@v4, actions/setup-go@v5, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / lint: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0d8LcagAAAACYA++vdYxJTbF5QtY5X7vMUEhMMzBFREdFMDIwOQBFZGdl
full / lint: .github#9

! Failed to restore: Cache service responded with 400
full / lint: .github#46

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / lint: .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* master Full CI · 40101618059
Triggered via workflow_dispatch about 34 minutes ago

JOBS
✓ full / prepare in 21s (ID 120894787205)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Validate qualification inputs
  - Download the sealed candidate manifest
  - Bind published identity from the sealed manifest
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
- full / docs-build in 0s (ID 120894788065)
- full / release-core-floor-smoke in 0s (ID 120894788195)
✓ full / build-core / build-core in 15m0s (ID 120894871757)
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
* full / visual-test (ID 120898126634)
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
✓ full / perf-floors in 9m54s (ID 120898126640)
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
✓ full / ace-page-group-isolation in 1m41s (ID 120898126672)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  ✓ Run ACE shared-page isolation lane
  ✓ Post Install visual dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* full / test (3.14) (ID 120898126703)
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
* full / test (3.13) (ID 120898126705)
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
✓ full / tutorial-tests in 57s (ID 120898126715)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run tutorial tests
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* full / test (3.12) (ID 120898126799)
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
✓ full / lint in 6m35s (ID 120898127009)
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

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / prepare: .github#6

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / prepare: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / build-core / build-core: .github#4

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>06MDcagAAAABlR3X2rL5lQKrpisTUl4fuU0xDMzFFREdFMDIyMABFZGdl
full / build-core / build-core: .github#7

! Failed to restore: Cache service responded with 400
full / build-core / build-core: .github#25

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / build-core / build-core: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / ace-page-group-isolation: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0UcHcagAAAABoxZI+wa2fSI+qzPyP3AN1UEhMMzBFREdFMDQxOABFZGdl
full / ace-page-group-isolation: .github#9

! Failed to restore: Cache service responded with 400
full / ace-page-group-isolation: .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / ace-page-group-isolation: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / tutorial-tests: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0JcHcagAAAABh43fuT51GRaeM4a3iJHApUEhYMzFFREdFMDIxNwBFZGdl
full / tutorial-tests: .github#9

! Failed to restore: Cache service responded with 400
full / tutorial-tests: .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / tutorial-tests: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache@v4, actions/checkout@v4, actions/download-artifact@v4, actions/setup-go@v5, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / lint: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0d8LcagAAAACYA++vdYxJTbF5QtY5X7vMUEhMMzBFREdFMDIwOQBFZGdl
full / lint: .github#9

! Failed to restore: Cache service responded with 400
full / lint: .github#46

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / lint: .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* master Full CI · 40101618059
Triggered via workflow_dispatch about 36 minutes ago

JOBS
✓ full / prepare in 21s (ID 120894787205)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Validate qualification inputs
  - Download the sealed candidate manifest
  - Bind published identity from the sealed manifest
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
- full / docs-build in 0s (ID 120894788065)
- full / release-core-floor-smoke in 0s (ID 120894788195)
✓ full / build-core / build-core in 15m0s (ID 120894871757)
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
* full / visual-test (ID 120898126634)
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
✓ full / perf-floors in 9m54s (ID 120898126640)
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
✓ full / ace-page-group-isolation in 1m41s (ID 120898126672)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  ✓ Run ACE shared-page isolation lane
  ✓ Post Install visual dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* full / test (3.14) (ID 120898126703)
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
* full / test (3.13) (ID 120898126705)
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
✓ full / tutorial-tests in 57s (ID 120898126715)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run tutorial tests
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* full / test (3.12) (ID 120898126799)
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
✓ full / lint in 6m35s (ID 120898127009)
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

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / prepare: .github#6

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / prepare: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / build-core / build-core: .github#4

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>06MDcagAAAABlR3X2rL5lQKrpisTUl4fuU0xDMzFFREdFMDIyMABFZGdl
full / build-core / build-core: .github#7

! Failed to restore: Cache service responded with 400
full / build-core / build-core: .github#25

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / build-core / build-core: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / ace-page-group-isolation: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0UcHcagAAAABoxZI+wa2fSI+qzPyP3AN1UEhMMzBFREdFMDQxOABFZGdl
full / ace-page-group-isolation: .github#9

! Failed to restore: Cache service responded with 400
full / ace-page-group-isolation: .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / ace-page-group-isolation: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / tutorial-tests: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0JcHcagAAAABh43fuT51GRaeM4a3iJHApUEhYMzFFREdFMDIxNwBFZGdl
full / tutorial-tests: .github#9

! Failed to restore: Cache service responded with 400
full / tutorial-tests: .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / tutorial-tests: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache@v4, actions/checkout@v4, actions/download-artifact@v4, actions/setup-go@v5, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / lint: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0d8LcagAAAACYA++vdYxJTbF5QtY5X7vMUEhMMzBFREdFMDIwOQBFZGdl
full / lint: .github#9

! Failed to restore: Cache service responded with 400
full / lint: .github#46

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / lint: .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* master Full CI · 40101618059
Triggered via workflow_dispatch about 38 minutes ago

JOBS
✓ full / prepare in 21s (ID 120894787205)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Validate qualification inputs
  - Download the sealed candidate manifest
  - Bind published identity from the sealed manifest
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
- full / docs-build in 0s (ID 120894788065)
- full / release-core-floor-smoke in 0s (ID 120894788195)
✓ full / build-core / build-core in 15m0s (ID 120894871757)
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
* full / visual-test (ID 120898126634)
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
✓ full / perf-floors in 9m54s (ID 120898126640)
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
✓ full / ace-page-group-isolation in 1m41s (ID 120898126672)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  ✓ Run ACE shared-page isolation lane
  ✓ Post Install visual dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* full / test (3.14) (ID 120898126703)
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
* full / test (3.13) (ID 120898126705)
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
✓ full / tutorial-tests in 57s (ID 120898126715)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run tutorial tests
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* full / test (3.12) (ID 120898126799)
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
✓ full / lint in 6m35s (ID 120898127009)
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

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / prepare: .github#6

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / prepare: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / build-core / build-core: .github#4

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>06MDcagAAAABlR3X2rL5lQKrpisTUl4fuU0xDMzFFREdFMDIyMABFZGdl
full / build-core / build-core: .github#7

! Failed to restore: Cache service responded with 400
full / build-core / build-core: .github#25

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / build-core / build-core: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / ace-page-group-isolation: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0UcHcagAAAABoxZI+wa2fSI+qzPyP3AN1UEhMMzBFREdFMDQxOABFZGdl
full / ace-page-group-isolation: .github#9

! Failed to restore: Cache service responded with 400
full / ace-page-group-isolation: .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / ace-page-group-isolation: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / tutorial-tests: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0JcHcagAAAABh43fuT51GRaeM4a3iJHApUEhYMzFFREdFMDIxNwBFZGdl
full / tutorial-tests: .github#9

! Failed to restore: Cache service responded with 400
full / tutorial-tests: .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / tutorial-tests: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache@v4, actions/checkout@v4, actions/download-artifact@v4, actions/setup-go@v5, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / lint: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0d8LcagAAAACYA++vdYxJTbF5QtY5X7vMUEhMMzBFREdFMDIwOQBFZGdl
full / lint: .github#9

! Failed to restore: Cache service responded with 400
full / lint: .github#46

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / lint: .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* master Full CI · 40101618059
Triggered via workflow_dispatch about 40 minutes ago

JOBS
✓ full / prepare in 21s (ID 120894787205)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Validate qualification inputs
  - Download the sealed candidate manifest
  - Bind published identity from the sealed manifest
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
- full / docs-build in 0s (ID 120894788065)
- full / release-core-floor-smoke in 0s (ID 120894788195)
✓ full / build-core / build-core in 15m0s (ID 120894871757)
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
* full / visual-test (ID 120898126634)
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
✓ full / perf-floors in 9m54s (ID 120898126640)
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
✓ full / ace-page-group-isolation in 1m41s (ID 120898126672)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  ✓ Run ACE shared-page isolation lane
  ✓ Post Install visual dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* full / test (3.14) (ID 120898126703)
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
* full / test (3.13) (ID 120898126705)
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
✓ full / tutorial-tests in 57s (ID 120898126715)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run tutorial tests
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* full / test (3.12) (ID 120898126799)
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
✓ full / lint in 6m35s (ID 120898127009)
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

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / prepare: .github#6

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / prepare: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / build-core / build-core: .github#4

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>06MDcagAAAABlR3X2rL5lQKrpisTUl4fuU0xDMzFFREdFMDIyMABFZGdl
full / build-core / build-core: .github#7

! Failed to restore: Cache service responded with 400
full / build-core / build-core: .github#25

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / build-core / build-core: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / ace-page-group-isolation: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0UcHcagAAAABoxZI+wa2fSI+qzPyP3AN1UEhMMzBFREdFMDQxOABFZGdl
full / ace-page-group-isolation: .github#9

! Failed to restore: Cache service responded with 400
full / ace-page-group-isolation: .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / ace-page-group-isolation: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / tutorial-tests: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0JcHcagAAAABh43fuT51GRaeM4a3iJHApUEhYMzFFREdFMDIxNwBFZGdl
full / tutorial-tests: .github#9

! Failed to restore: Cache service responded with 400
full / tutorial-tests: .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / tutorial-tests: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache@v4, actions/checkout@v4, actions/download-artifact@v4, actions/setup-go@v5, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / lint: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0d8LcagAAAACYA++vdYxJTbF5QtY5X7vMUEhMMzBFREdFMDIwOQBFZGdl
full / lint: .github#9

! Failed to restore: Cache service responded with 400
full / lint: .github#46

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / lint: .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* master Full CI · 40101618059
Triggered via workflow_dispatch about 42 minutes ago

JOBS
✓ full / prepare in 21s (ID 120894787205)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Validate qualification inputs
  - Download the sealed candidate manifest
  - Bind published identity from the sealed manifest
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
- full / docs-build in 0s (ID 120894788065)
- full / release-core-floor-smoke in 0s (ID 120894788195)
✓ full / build-core / build-core in 15m0s (ID 120894871757)
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
X full / visual-test in 26m44s (ID 120898126634)
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
✓ full / perf-floors in 9m54s (ID 120898126640)
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
✓ full / ace-page-group-isolation in 1m41s (ID 120898126672)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  ✓ Run ACE shared-page isolation lane
  ✓ Post Install visual dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* full / test (3.14) (ID 120898126703)
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
* full / test (3.13) (ID 120898126705)
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
✓ full / tutorial-tests in 57s (ID 120898126715)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run tutorial tests
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* full / test (3.12) (ID 120898126799)
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
✓ full / lint in 6m35s (ID 120898127009)
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

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / prepare: .github#6

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / prepare: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / build-core / build-core: .github#4

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>06MDcagAAAABlR3X2rL5lQKrpisTUl4fuU0xDMzFFREdFMDIyMABFZGdl
full / build-core / build-core: .github#7

! Failed to restore: Cache service responded with 400
full / build-core / build-core: .github#25

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / build-core / build-core: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / ace-page-group-isolation: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0UcHcagAAAABoxZI+wa2fSI+qzPyP3AN1UEhMMzBFREdFMDQxOABFZGdl
full / ace-page-group-isolation: .github#9

! Failed to restore: Cache service responded with 400
full / ace-page-group-isolation: .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / ace-page-group-isolation: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / tutorial-tests: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0JcHcagAAAABh43fuT51GRaeM4a3iJHApUEhYMzFFREdFMDIxNwBFZGdl
full / tutorial-tests: .github#9

! Failed to restore: Cache service responded with 400
full / tutorial-tests: .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / tutorial-tests: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache@v4, actions/checkout@v4, actions/download-artifact@v4, actions/setup-go@v5, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / lint: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0d8LcagAAAACYA++vdYxJTbF5QtY5X7vMUEhMMzBFREdFMDIwOQBFZGdl
full / lint: .github#9

! Failed to restore: Cache service responded with 400
full / lint: .github#46

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / lint: .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* master Full CI · 40101618059
Triggered via workflow_dispatch about 44 minutes ago

JOBS
✓ full / prepare in 21s (ID 120894787205)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Validate qualification inputs
  - Download the sealed candidate manifest
  - Bind published identity from the sealed manifest
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
- full / docs-build in 0s (ID 120894788065)
- full / release-core-floor-smoke in 0s (ID 120894788195)
✓ full / build-core / build-core in 15m0s (ID 120894871757)
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
X full / visual-test in 26m44s (ID 120898126634)
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
✓ full / perf-floors in 9m54s (ID 120898126640)
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
✓ full / ace-page-group-isolation in 1m41s (ID 120898126672)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  ✓ Run ACE shared-page isolation lane
  ✓ Post Install visual dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* full / test (3.14) (ID 120898126703)
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
* full / test (3.13) (ID 120898126705)
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
✓ full / tutorial-tests in 57s (ID 120898126715)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run tutorial tests
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* full / test (3.12) (ID 120898126799)
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
✓ full / lint in 6m35s (ID 120898127009)
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

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / prepare: .github#6

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / prepare: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / build-core / build-core: .github#4

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>06MDcagAAAABlR3X2rL5lQKrpisTUl4fuU0xDMzFFREdFMDIyMABFZGdl
full / build-core / build-core: .github#7

! Failed to restore: Cache service responded with 400
full / build-core / build-core: .github#25

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / build-core / build-core: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / ace-page-group-isolation: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0UcHcagAAAABoxZI+wa2fSI+qzPyP3AN1UEhMMzBFREdFMDQxOABFZGdl
full / ace-page-group-isolation: .github#9

! Failed to restore: Cache service responded with 400
full / ace-page-group-isolation: .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / ace-page-group-isolation: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / tutorial-tests: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0JcHcagAAAABh43fuT51GRaeM4a3iJHApUEhYMzFFREdFMDIxNwBFZGdl
full / tutorial-tests: .github#9

! Failed to restore: Cache service responded with 400
full / tutorial-tests: .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / tutorial-tests: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache@v4, actions/checkout@v4, actions/download-artifact@v4, actions/setup-go@v5, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / lint: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0d8LcagAAAACYA++vdYxJTbF5QtY5X7vMUEhMMzBFREdFMDIwOQBFZGdl
full / lint: .github#9

! Failed to restore: Cache service responded with 400
full / lint: .github#46

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / lint: .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* master Full CI · 40101618059
Triggered via workflow_dispatch about 46 minutes ago

JOBS
✓ full / prepare in 21s (ID 120894787205)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Validate qualification inputs
  - Download the sealed candidate manifest
  - Bind published identity from the sealed manifest
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
- full / docs-build in 0s (ID 120894788065)
- full / release-core-floor-smoke in 0s (ID 120894788195)
✓ full / build-core / build-core in 15m0s (ID 120894871757)
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
X full / visual-test in 26m44s (ID 120898126634)
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
✓ full / perf-floors in 9m54s (ID 120898126640)
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
✓ full / ace-page-group-isolation in 1m41s (ID 120898126672)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  ✓ Run ACE shared-page isolation lane
  ✓ Post Install visual dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* full / test (3.14) (ID 120898126703)
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
* full / test (3.13) (ID 120898126705)
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
✓ full / tutorial-tests in 57s (ID 120898126715)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run tutorial tests
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* full / test (3.12) (ID 120898126799)
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
✓ full / lint in 6m35s (ID 120898127009)
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

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / prepare: .github#6

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / prepare: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / build-core / build-core: .github#4

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>06MDcagAAAABlR3X2rL5lQKrpisTUl4fuU0xDMzFFREdFMDIyMABFZGdl
full / build-core / build-core: .github#7

! Failed to restore: Cache service responded with 400
full / build-core / build-core: .github#25

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / build-core / build-core: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / ace-page-group-isolation: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0UcHcagAAAABoxZI+wa2fSI+qzPyP3AN1UEhMMzBFREdFMDQxOABFZGdl
full / ace-page-group-isolation: .github#9

! Failed to restore: Cache service responded with 400
full / ace-page-group-isolation: .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / ace-page-group-isolation: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / tutorial-tests: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0JcHcagAAAABh43fuT51GRaeM4a3iJHApUEhYMzFFREdFMDIxNwBFZGdl
full / tutorial-tests: .github#9

! Failed to restore: Cache service responded with 400
full / tutorial-tests: .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / tutorial-tests: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache@v4, actions/checkout@v4, actions/download-artifact@v4, actions/setup-go@v5, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / lint: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0d8LcagAAAACYA++vdYxJTbF5QtY5X7vMUEhMMzBFREdFMDIwOQBFZGdl
full / lint: .github#9

! Failed to restore: Cache service responded with 400
full / lint: .github#46

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / lint: .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* master Full CI · 40101618059
Triggered via workflow_dispatch about 48 minutes ago

JOBS
✓ full / prepare in 21s (ID 120894787205)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Validate qualification inputs
  - Download the sealed candidate manifest
  - Bind published identity from the sealed manifest
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
- full / docs-build in 0s (ID 120894788065)
- full / release-core-floor-smoke in 0s (ID 120894788195)
✓ full / build-core / build-core in 15m0s (ID 120894871757)
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
X full / visual-test in 26m44s (ID 120898126634)
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
✓ full / perf-floors in 9m54s (ID 120898126640)
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
✓ full / ace-page-group-isolation in 1m41s (ID 120898126672)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  ✓ Run ACE shared-page isolation lane
  ✓ Post Install visual dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* full / test (3.14) (ID 120898126703)
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
* full / test (3.13) (ID 120898126705)
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
✓ full / tutorial-tests in 57s (ID 120898126715)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run tutorial tests
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* full / test (3.12) (ID 120898126799)
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
✓ full / lint in 6m35s (ID 120898127009)
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

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / prepare: .github#6

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / prepare: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / build-core / build-core: .github#4

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>06MDcagAAAABlR3X2rL5lQKrpisTUl4fuU0xDMzFFREdFMDIyMABFZGdl
full / build-core / build-core: .github#7

! Failed to restore: Cache service responded with 400
full / build-core / build-core: .github#25

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / build-core / build-core: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / ace-page-group-isolation: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0UcHcagAAAABoxZI+wa2fSI+qzPyP3AN1UEhMMzBFREdFMDQxOABFZGdl
full / ace-page-group-isolation: .github#9

! Failed to restore: Cache service responded with 400
full / ace-page-group-isolation: .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / ace-page-group-isolation: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / tutorial-tests: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0JcHcagAAAABh43fuT51GRaeM4a3iJHApUEhYMzFFREdFMDIxNwBFZGdl
full / tutorial-tests: .github#9

! Failed to restore: Cache service responded with 400
full / tutorial-tests: .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / tutorial-tests: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache@v4, actions/checkout@v4, actions/download-artifact@v4, actions/setup-go@v5, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / lint: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0d8LcagAAAACYA++vdYxJTbF5QtY5X7vMUEhMMzBFREdFMDIwOQBFZGdl
full / lint: .github#9

! Failed to restore: Cache service responded with 400
full / lint: .github#46

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / lint: .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* master Full CI · 40101618059
Triggered via workflow_dispatch about 50 minutes ago

JOBS
✓ full / prepare in 21s (ID 120894787205)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Validate qualification inputs
  - Download the sealed candidate manifest
  - Bind published identity from the sealed manifest
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
- full / docs-build in 0s (ID 120894788065)
- full / release-core-floor-smoke in 0s (ID 120894788195)
✓ full / build-core / build-core in 15m0s (ID 120894871757)
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
X full / visual-test in 26m44s (ID 120898126634)
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
✓ full / perf-floors in 9m54s (ID 120898126640)
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
✓ full / ace-page-group-isolation in 1m41s (ID 120898126672)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  ✓ Run ACE shared-page isolation lane
  ✓ Post Install visual dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* full / test (3.14) (ID 120898126703)
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
* full / test (3.13) (ID 120898126705)
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
✓ full / tutorial-tests in 57s (ID 120898126715)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run tutorial tests
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* full / test (3.12) (ID 120898126799)
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
✓ full / lint in 6m35s (ID 120898127009)
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

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / prepare: .github#6

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / prepare: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / build-core / build-core: .github#4

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>06MDcagAAAABlR3X2rL5lQKrpisTUl4fuU0xDMzFFREdFMDIyMABFZGdl
full / build-core / build-core: .github#7

! Failed to restore: Cache service responded with 400
full / build-core / build-core: .github#25

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / build-core / build-core: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / ace-page-group-isolation: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0UcHcagAAAABoxZI+wa2fSI+qzPyP3AN1UEhMMzBFREdFMDQxOABFZGdl
full / ace-page-group-isolation: .github#9

! Failed to restore: Cache service responded with 400
full / ace-page-group-isolation: .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / ace-page-group-isolation: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / tutorial-tests: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0JcHcagAAAABh43fuT51GRaeM4a3iJHApUEhYMzFFREdFMDIxNwBFZGdl
full / tutorial-tests: .github#9

! Failed to restore: Cache service responded with 400
full / tutorial-tests: .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / tutorial-tests: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache@v4, actions/checkout@v4, actions/download-artifact@v4, actions/setup-go@v5, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / lint: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0d8LcagAAAACYA++vdYxJTbF5QtY5X7vMUEhMMzBFREdFMDIwOQBFZGdl
full / lint: .github#9

! Failed to restore: Cache service responded with 400
full / lint: .github#46

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / lint: .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* master Full CI · 40101618059
Triggered via workflow_dispatch about 53 minutes ago

JOBS
✓ full / prepare in 21s (ID 120894787205)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Validate qualification inputs
  - Download the sealed candidate manifest
  - Bind published identity from the sealed manifest
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
- full / docs-build in 0s (ID 120894788065)
- full / release-core-floor-smoke in 0s (ID 120894788195)
✓ full / build-core / build-core in 15m0s (ID 120894871757)
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
X full / visual-test in 26m44s (ID 120898126634)
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
✓ full / perf-floors in 9m54s (ID 120898126640)
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
✓ full / ace-page-group-isolation in 1m41s (ID 120898126672)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  ✓ Run ACE shared-page isolation lane
  ✓ Post Install visual dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* full / test (3.14) (ID 120898126703)
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
* full / test (3.13) (ID 120898126705)
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
✓ full / tutorial-tests in 57s (ID 120898126715)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run tutorial tests
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* full / test (3.12) (ID 120898126799)
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
✓ full / lint in 6m35s (ID 120898127009)
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

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / prepare: .github#6

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / prepare: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / build-core / build-core: .github#4

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>06MDcagAAAABlR3X2rL5lQKrpisTUl4fuU0xDMzFFREdFMDIyMABFZGdl
full / build-core / build-core: .github#7

! Failed to restore: Cache service responded with 400
full / build-core / build-core: .github#25

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / build-core / build-core: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / ace-page-group-isolation: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0UcHcagAAAABoxZI+wa2fSI+qzPyP3AN1UEhMMzBFREdFMDQxOABFZGdl
full / ace-page-group-isolation: .github#9

! Failed to restore: Cache service responded with 400
full / ace-page-group-isolation: .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / ace-page-group-isolation: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / tutorial-tests: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0JcHcagAAAABh43fuT51GRaeM4a3iJHApUEhYMzFFREdFMDIxNwBFZGdl
full / tutorial-tests: .github#9

! Failed to restore: Cache service responded with 400
full / tutorial-tests: .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / tutorial-tests: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache@v4, actions/checkout@v4, actions/download-artifact@v4, actions/setup-go@v5, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / lint: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0d8LcagAAAACYA++vdYxJTbF5QtY5X7vMUEhMMzBFREdFMDIwOQBFZGdl
full / lint: .github#9

! Failed to restore: Cache service responded with 400
full / lint: .github#46

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / lint: .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* master Full CI · 40101618059
Triggered via workflow_dispatch about 55 minutes ago

JOBS
✓ full / prepare in 21s (ID 120894787205)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Validate qualification inputs
  - Download the sealed candidate manifest
  - Bind published identity from the sealed manifest
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
- full / docs-build in 0s (ID 120894788065)
- full / release-core-floor-smoke in 0s (ID 120894788195)
✓ full / build-core / build-core in 15m0s (ID 120894871757)
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
X full / visual-test in 26m44s (ID 120898126634)
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
✓ full / perf-floors in 9m54s (ID 120898126640)
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
✓ full / ace-page-group-isolation in 1m41s (ID 120898126672)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  ✓ Run ACE shared-page isolation lane
  ✓ Post Install visual dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* full / test (3.14) (ID 120898126703)
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
* full / test (3.13) (ID 120898126705)
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
✓ full / tutorial-tests in 57s (ID 120898126715)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run tutorial tests
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* full / test (3.12) (ID 120898126799)
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
✓ full / lint in 6m35s (ID 120898127009)
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

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / prepare: .github#6

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / prepare: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / build-core / build-core: .github#4

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>06MDcagAAAABlR3X2rL5lQKrpisTUl4fuU0xDMzFFREdFMDIyMABFZGdl
full / build-core / build-core: .github#7

! Failed to restore: Cache service responded with 400
full / build-core / build-core: .github#25

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / build-core / build-core: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / ace-page-group-isolation: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0UcHcagAAAABoxZI+wa2fSI+qzPyP3AN1UEhMMzBFREdFMDQxOABFZGdl
full / ace-page-group-isolation: .github#9

! Failed to restore: Cache service responded with 400
full / ace-page-group-isolation: .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / ace-page-group-isolation: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / tutorial-tests: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0JcHcagAAAABh43fuT51GRaeM4a3iJHApUEhYMzFFREdFMDIxNwBFZGdl
full / tutorial-tests: .github#9

! Failed to restore: Cache service responded with 400
full / tutorial-tests: .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / tutorial-tests: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache@v4, actions/checkout@v4, actions/download-artifact@v4, actions/setup-go@v5, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / lint: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0d8LcagAAAACYA++vdYxJTbF5QtY5X7vMUEhMMzBFREdFMDIwOQBFZGdl
full / lint: .github#9

! Failed to restore: Cache service responded with 400
full / lint: .github#46

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / lint: .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* master Full CI · 40101618059
Triggered via workflow_dispatch about 57 minutes ago

JOBS
✓ full / prepare in 21s (ID 120894787205)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Validate qualification inputs
  - Download the sealed candidate manifest
  - Bind published identity from the sealed manifest
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
- full / docs-build in 0s (ID 120894788065)
- full / release-core-floor-smoke in 0s (ID 120894788195)
✓ full / build-core / build-core in 15m0s (ID 120894871757)
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
X full / visual-test in 26m44s (ID 120898126634)
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
✓ full / perf-floors in 9m54s (ID 120898126640)
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
✓ full / ace-page-group-isolation in 1m41s (ID 120898126672)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  ✓ Run ACE shared-page isolation lane
  ✓ Post Install visual dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* full / test (3.14) (ID 120898126703)
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
* full / test (3.13) (ID 120898126705)
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
✓ full / tutorial-tests in 57s (ID 120898126715)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run tutorial tests
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* full / test (3.12) (ID 120898126799)
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
✓ full / lint in 6m35s (ID 120898127009)
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

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / prepare: .github#6

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / prepare: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / build-core / build-core: .github#4

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>06MDcagAAAABlR3X2rL5lQKrpisTUl4fuU0xDMzFFREdFMDIyMABFZGdl
full / build-core / build-core: .github#7

! Failed to restore: Cache service responded with 400
full / build-core / build-core: .github#25

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / build-core / build-core: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / ace-page-group-isolation: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0UcHcagAAAABoxZI+wa2fSI+qzPyP3AN1UEhMMzBFREdFMDQxOABFZGdl
full / ace-page-group-isolation: .github#9

! Failed to restore: Cache service responded with 400
full / ace-page-group-isolation: .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / ace-page-group-isolation: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / tutorial-tests: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0JcHcagAAAABh43fuT51GRaeM4a3iJHApUEhYMzFFREdFMDIxNwBFZGdl
full / tutorial-tests: .github#9

! Failed to restore: Cache service responded with 400
full / tutorial-tests: .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / tutorial-tests: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache@v4, actions/checkout@v4, actions/download-artifact@v4, actions/setup-go@v5, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / lint: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0d8LcagAAAACYA++vdYxJTbF5QtY5X7vMUEhMMzBFREdFMDIwOQBFZGdl
full / lint: .github#9

! Failed to restore: Cache service responded with 400
full / lint: .github#46

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / lint: .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* master Full CI · 40101618059
Triggered via workflow_dispatch about 59 minutes ago

JOBS
✓ full / prepare in 21s (ID 120894787205)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Validate qualification inputs
  - Download the sealed candidate manifest
  - Bind published identity from the sealed manifest
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
- full / docs-build in 0s (ID 120894788065)
- full / release-core-floor-smoke in 0s (ID 120894788195)
✓ full / build-core / build-core in 15m0s (ID 120894871757)
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
X full / visual-test in 26m44s (ID 120898126634)
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
✓ full / perf-floors in 9m54s (ID 120898126640)
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
✓ full / ace-page-group-isolation in 1m41s (ID 120898126672)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  ✓ Run ACE shared-page isolation lane
  ✓ Post Install visual dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* full / test (3.14) (ID 120898126703)
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
* full / test (3.13) (ID 120898126705)
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
✓ full / tutorial-tests in 57s (ID 120898126715)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run tutorial tests
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* full / test (3.12) (ID 120898126799)
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
✓ full / lint in 6m35s (ID 120898127009)
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

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / prepare: .github#6

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / prepare: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / build-core / build-core: .github#4

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>06MDcagAAAABlR3X2rL5lQKrpisTUl4fuU0xDMzFFREdFMDIyMABFZGdl
full / build-core / build-core: .github#7

! Failed to restore: Cache service responded with 400
full / build-core / build-core: .github#25

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / build-core / build-core: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / ace-page-group-isolation: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0UcHcagAAAABoxZI+wa2fSI+qzPyP3AN1UEhMMzBFREdFMDQxOABFZGdl
full / ace-page-group-isolation: .github#9

! Failed to restore: Cache service responded with 400
full / ace-page-group-isolation: .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / ace-page-group-isolation: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / tutorial-tests: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0JcHcagAAAABh43fuT51GRaeM4a3iJHApUEhYMzFFREdFMDIxNwBFZGdl
full / tutorial-tests: .github#9

! Failed to restore: Cache service responded with 400
full / tutorial-tests: .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / tutorial-tests: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache@v4, actions/checkout@v4, actions/download-artifact@v4, actions/setup-go@v5, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / lint: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0d8LcagAAAACYA++vdYxJTbF5QtY5X7vMUEhMMzBFREdFMDIwOQBFZGdl
full / lint: .github#9

! Failed to restore: Cache service responded with 400
full / lint: .github#46

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / lint: .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* master Full CI · 40101618059
Triggered via workflow_dispatch about 1 hour ago

JOBS
✓ full / prepare in 21s (ID 120894787205)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Validate qualification inputs
  - Download the sealed candidate manifest
  - Bind published identity from the sealed manifest
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
- full / docs-build in 0s (ID 120894788065)
- full / release-core-floor-smoke in 0s (ID 120894788195)
✓ full / build-core / build-core in 15m0s (ID 120894871757)
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
X full / visual-test in 26m44s (ID 120898126634)
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
✓ full / perf-floors in 9m54s (ID 120898126640)
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
✓ full / ace-page-group-isolation in 1m41s (ID 120898126672)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  ✓ Run ACE shared-page isolation lane
  ✓ Post Install visual dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* full / test (3.14) (ID 120898126703)
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
✓ full / test (3.13) in 45m14s (ID 120898126705)
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
✓ full / tutorial-tests in 57s (ID 120898126715)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run tutorial tests
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* full / test (3.12) (ID 120898126799)
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
✓ full / lint in 6m35s (ID 120898127009)
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

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / prepare: .github#6

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / prepare: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / build-core / build-core: .github#4

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>06MDcagAAAABlR3X2rL5lQKrpisTUl4fuU0xDMzFFREdFMDIyMABFZGdl
full / build-core / build-core: .github#7

! Failed to restore: Cache service responded with 400
full / build-core / build-core: .github#25

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / build-core / build-core: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / ace-page-group-isolation: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0UcHcagAAAABoxZI+wa2fSI+qzPyP3AN1UEhMMzBFREdFMDQxOABFZGdl
full / ace-page-group-isolation: .github#9

! Failed to restore: Cache service responded with 400
full / ace-page-group-isolation: .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / ace-page-group-isolation: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / tutorial-tests: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0JcHcagAAAABh43fuT51GRaeM4a3iJHApUEhYMzFFREdFMDIxNwBFZGdl
full / tutorial-tests: .github#9

! Failed to restore: Cache service responded with 400
full / tutorial-tests: .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / tutorial-tests: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache@v4, actions/checkout@v4, actions/download-artifact@v4, actions/setup-go@v5, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / lint: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0d8LcagAAAACYA++vdYxJTbF5QtY5X7vMUEhMMzBFREdFMDIwOQBFZGdl
full / lint: .github#9

! Failed to restore: Cache service responded with 400
full / lint: .github#46

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / lint: .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* master Full CI · 40101618059
Triggered via workflow_dispatch about 1 hour ago

JOBS
✓ full / prepare in 21s (ID 120894787205)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Validate qualification inputs
  - Download the sealed candidate manifest
  - Bind published identity from the sealed manifest
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
- full / docs-build in 0s (ID 120894788065)
- full / release-core-floor-smoke in 0s (ID 120894788195)
✓ full / build-core / build-core in 15m0s (ID 120894871757)
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
X full / visual-test in 26m44s (ID 120898126634)
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
✓ full / perf-floors in 9m54s (ID 120898126640)
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
✓ full / ace-page-group-isolation in 1m41s (ID 120898126672)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  ✓ Run ACE shared-page isolation lane
  ✓ Post Install visual dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* full / test (3.14) (ID 120898126703)
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
✓ full / test (3.13) in 45m14s (ID 120898126705)
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
✓ full / tutorial-tests in 57s (ID 120898126715)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run tutorial tests
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* full / test (3.12) (ID 120898126799)
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
✓ full / lint in 6m35s (ID 120898127009)
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

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / prepare: .github#6

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / prepare: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / build-core / build-core: .github#4

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>06MDcagAAAABlR3X2rL5lQKrpisTUl4fuU0xDMzFFREdFMDIyMABFZGdl
full / build-core / build-core: .github#7

! Failed to restore: Cache service responded with 400
full / build-core / build-core: .github#25

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / build-core / build-core: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / ace-page-group-isolation: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0UcHcagAAAABoxZI+wa2fSI+qzPyP3AN1UEhMMzBFREdFMDQxOABFZGdl
full / ace-page-group-isolation: .github#9

! Failed to restore: Cache service responded with 400
full / ace-page-group-isolation: .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / ace-page-group-isolation: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / tutorial-tests: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0JcHcagAAAABh43fuT51GRaeM4a3iJHApUEhYMzFFREdFMDIxNwBFZGdl
full / tutorial-tests: .github#9

! Failed to restore: Cache service responded with 400
full / tutorial-tests: .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / tutorial-tests: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache@v4, actions/checkout@v4, actions/download-artifact@v4, actions/setup-go@v5, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / lint: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0d8LcagAAAACYA++vdYxJTbF5QtY5X7vMUEhMMzBFREdFMDIwOQBFZGdl
full / lint: .github#9

! Failed to restore: Cache service responded with 400
full / lint: .github#46

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / lint: .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* master Full CI · 40101618059
Triggered via workflow_dispatch about 1 hour ago

JOBS
✓ full / prepare in 21s (ID 120894787205)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Validate qualification inputs
  - Download the sealed candidate manifest
  - Bind published identity from the sealed manifest
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
- full / docs-build in 0s (ID 120894788065)
- full / release-core-floor-smoke in 0s (ID 120894788195)
✓ full / build-core / build-core in 15m0s (ID 120894871757)
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
X full / visual-test in 26m44s (ID 120898126634)
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
✓ full / perf-floors in 9m54s (ID 120898126640)
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
✓ full / ace-page-group-isolation in 1m41s (ID 120898126672)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  ✓ Run ACE shared-page isolation lane
  ✓ Post Install visual dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* full / test (3.14) (ID 120898126703)
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
✓ full / test (3.13) in 45m14s (ID 120898126705)
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
✓ full / tutorial-tests in 57s (ID 120898126715)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run tutorial tests
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* full / test (3.12) (ID 120898126799)
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
✓ full / lint in 6m35s (ID 120898127009)
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

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / prepare: .github#6

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / prepare: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / build-core / build-core: .github#4

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>06MDcagAAAABlR3X2rL5lQKrpisTUl4fuU0xDMzFFREdFMDIyMABFZGdl
full / build-core / build-core: .github#7

! Failed to restore: Cache service responded with 400
full / build-core / build-core: .github#25

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / build-core / build-core: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / ace-page-group-isolation: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0UcHcagAAAABoxZI+wa2fSI+qzPyP3AN1UEhMMzBFREdFMDQxOABFZGdl
full / ace-page-group-isolation: .github#9

! Failed to restore: Cache service responded with 400
full / ace-page-group-isolation: .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / ace-page-group-isolation: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / tutorial-tests: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0JcHcagAAAABh43fuT51GRaeM4a3iJHApUEhYMzFFREdFMDIxNwBFZGdl
full / tutorial-tests: .github#9

! Failed to restore: Cache service responded with 400
full / tutorial-tests: .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / tutorial-tests: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache@v4, actions/checkout@v4, actions/download-artifact@v4, actions/setup-go@v5, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / lint: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0d8LcagAAAACYA++vdYxJTbF5QtY5X7vMUEhMMzBFREdFMDIwOQBFZGdl
full / lint: .github#9

! Failed to restore: Cache service responded with 400
full / lint: .github#46

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / lint: .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* master Full CI · 40101618059
Triggered via workflow_dispatch about 1 hour ago

JOBS
✓ full / prepare in 21s (ID 120894787205)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Validate qualification inputs
  - Download the sealed candidate manifest
  - Bind published identity from the sealed manifest
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
- full / docs-build in 0s (ID 120894788065)
- full / release-core-floor-smoke in 0s (ID 120894788195)
✓ full / build-core / build-core in 15m0s (ID 120894871757)
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
X full / visual-test in 26m44s (ID 120898126634)
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
✓ full / perf-floors in 9m54s (ID 120898126640)
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
✓ full / ace-page-group-isolation in 1m41s (ID 120898126672)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  ✓ Run ACE shared-page isolation lane
  ✓ Post Install visual dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* full / test (3.14) (ID 120898126703)
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
✓ full / test (3.13) in 45m14s (ID 120898126705)
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
✓ full / tutorial-tests in 57s (ID 120898126715)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run tutorial tests
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* full / test (3.12) (ID 120898126799)
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
✓ full / lint in 6m35s (ID 120898127009)
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

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / prepare: .github#6

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / prepare: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / build-core / build-core: .github#4

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>06MDcagAAAABlR3X2rL5lQKrpisTUl4fuU0xDMzFFREdFMDIyMABFZGdl
full / build-core / build-core: .github#7

! Failed to restore: Cache service responded with 400
full / build-core / build-core: .github#25

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / build-core / build-core: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / ace-page-group-isolation: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0UcHcagAAAABoxZI+wa2fSI+qzPyP3AN1UEhMMzBFREdFMDQxOABFZGdl
full / ace-page-group-isolation: .github#9

! Failed to restore: Cache service responded with 400
full / ace-page-group-isolation: .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / ace-page-group-isolation: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / tutorial-tests: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0JcHcagAAAABh43fuT51GRaeM4a3iJHApUEhYMzFFREdFMDIxNwBFZGdl
full / tutorial-tests: .github#9

! Failed to restore: Cache service responded with 400
full / tutorial-tests: .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / tutorial-tests: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache@v4, actions/checkout@v4, actions/download-artifact@v4, actions/setup-go@v5, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / lint: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0d8LcagAAAACYA++vdYxJTbF5QtY5X7vMUEhMMzBFREdFMDIwOQBFZGdl
full / lint: .github#9

! Failed to restore: Cache service responded with 400
full / lint: .github#46

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / lint: .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* master Full CI · 40101618059
Triggered via workflow_dispatch about 1 hour ago

JOBS
✓ full / prepare in 21s (ID 120894787205)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Validate qualification inputs
  - Download the sealed candidate manifest
  - Bind published identity from the sealed manifest
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
- full / docs-build in 0s (ID 120894788065)
- full / release-core-floor-smoke in 0s (ID 120894788195)
✓ full / build-core / build-core in 15m0s (ID 120894871757)
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
X full / visual-test in 26m44s (ID 120898126634)
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
✓ full / perf-floors in 9m54s (ID 120898126640)
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
✓ full / ace-page-group-isolation in 1m41s (ID 120898126672)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  ✓ Run ACE shared-page isolation lane
  ✓ Post Install visual dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* full / test (3.14) (ID 120898126703)
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
✓ full / test (3.13) in 45m14s (ID 120898126705)
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
✓ full / tutorial-tests in 57s (ID 120898126715)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run tutorial tests
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* full / test (3.12) (ID 120898126799)
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
✓ full / lint in 6m35s (ID 120898127009)
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

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / prepare: .github#6

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / prepare: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / build-core / build-core: .github#4

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>06MDcagAAAABlR3X2rL5lQKrpisTUl4fuU0xDMzFFREdFMDIyMABFZGdl
full / build-core / build-core: .github#7

! Failed to restore: Cache service responded with 400
full / build-core / build-core: .github#25

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / build-core / build-core: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / ace-page-group-isolation: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0UcHcagAAAABoxZI+wa2fSI+qzPyP3AN1UEhMMzBFREdFMDQxOABFZGdl
full / ace-page-group-isolation: .github#9

! Failed to restore: Cache service responded with 400
full / ace-page-group-isolation: .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / ace-page-group-isolation: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / tutorial-tests: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0JcHcagAAAABh43fuT51GRaeM4a3iJHApUEhYMzFFREdFMDIxNwBFZGdl
full / tutorial-tests: .github#9

! Failed to restore: Cache service responded with 400
full / tutorial-tests: .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / tutorial-tests: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache@v4, actions/checkout@v4, actions/download-artifact@v4, actions/setup-go@v5, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / lint: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0d8LcagAAAACYA++vdYxJTbF5QtY5X7vMUEhMMzBFREdFMDIwOQBFZGdl
full / lint: .github#9

! Failed to restore: Cache service responded with 400
full / lint: .github#46

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / lint: .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* master Full CI · 40101618059
Triggered via workflow_dispatch about 1 hour ago

JOBS
✓ full / prepare in 21s (ID 120894787205)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Validate qualification inputs
  - Download the sealed candidate manifest
  - Bind published identity from the sealed manifest
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
- full / docs-build in 0s (ID 120894788065)
- full / release-core-floor-smoke in 0s (ID 120894788195)
✓ full / build-core / build-core in 15m0s (ID 120894871757)
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
X full / visual-test in 26m44s (ID 120898126634)
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
✓ full / perf-floors in 9m54s (ID 120898126640)
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
✓ full / ace-page-group-isolation in 1m41s (ID 120898126672)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  ✓ Run ACE shared-page isolation lane
  ✓ Post Install visual dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* full / test (3.14) (ID 120898126703)
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
✓ full / test (3.13) in 45m14s (ID 120898126705)
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
✓ full / tutorial-tests in 57s (ID 120898126715)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run tutorial tests
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* full / test (3.12) (ID 120898126799)
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
✓ full / lint in 6m35s (ID 120898127009)
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

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / prepare: .github#6

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / prepare: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / build-core / build-core: .github#4

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>06MDcagAAAABlR3X2rL5lQKrpisTUl4fuU0xDMzFFREdFMDIyMABFZGdl
full / build-core / build-core: .github#7

! Failed to restore: Cache service responded with 400
full / build-core / build-core: .github#25

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / build-core / build-core: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / ace-page-group-isolation: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0UcHcagAAAABoxZI+wa2fSI+qzPyP3AN1UEhMMzBFREdFMDQxOABFZGdl
full / ace-page-group-isolation: .github#9

! Failed to restore: Cache service responded with 400
full / ace-page-group-isolation: .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / ace-page-group-isolation: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / tutorial-tests: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0JcHcagAAAABh43fuT51GRaeM4a3iJHApUEhYMzFFREdFMDIxNwBFZGdl
full / tutorial-tests: .github#9

! Failed to restore: Cache service responded with 400
full / tutorial-tests: .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / tutorial-tests: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache@v4, actions/checkout@v4, actions/download-artifact@v4, actions/setup-go@v5, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / lint: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0d8LcagAAAACYA++vdYxJTbF5QtY5X7vMUEhMMzBFREdFMDIwOQBFZGdl
full / lint: .github#9

! Failed to restore: Cache service responded with 400
full / lint: .github#46

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / lint: .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* master Full CI · 40101618059
Triggered via workflow_dispatch about 1 hour ago

JOBS
✓ full / prepare in 21s (ID 120894787205)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Validate qualification inputs
  - Download the sealed candidate manifest
  - Bind published identity from the sealed manifest
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
- full / docs-build in 0s (ID 120894788065)
- full / release-core-floor-smoke in 0s (ID 120894788195)
✓ full / build-core / build-core in 15m0s (ID 120894871757)
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
X full / visual-test in 26m44s (ID 120898126634)
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
✓ full / perf-floors in 9m54s (ID 120898126640)
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
✓ full / ace-page-group-isolation in 1m41s (ID 120898126672)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  ✓ Run ACE shared-page isolation lane
  ✓ Post Install visual dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ full / test (3.14) in 57m30s (ID 120898126703)
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
✓ full / test (3.13) in 45m14s (ID 120898126705)
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
✓ full / tutorial-tests in 57s (ID 120898126715)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run tutorial tests
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* full / test (3.12) (ID 120898126799)
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
✓ full / lint in 6m35s (ID 120898127009)
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

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / prepare: .github#6

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / prepare: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / build-core / build-core: .github#4

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>06MDcagAAAABlR3X2rL5lQKrpisTUl4fuU0xDMzFFREdFMDIyMABFZGdl
full / build-core / build-core: .github#7

! Failed to restore: Cache service responded with 400
full / build-core / build-core: .github#25

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / build-core / build-core: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / ace-page-group-isolation: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0UcHcagAAAABoxZI+wa2fSI+qzPyP3AN1UEhMMzBFREdFMDQxOABFZGdl
full / ace-page-group-isolation: .github#9

! Failed to restore: Cache service responded with 400
full / ace-page-group-isolation: .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / ace-page-group-isolation: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / tutorial-tests: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0JcHcagAAAABh43fuT51GRaeM4a3iJHApUEhYMzFFREdFMDIxNwBFZGdl
full / tutorial-tests: .github#9

! Failed to restore: Cache service responded with 400
full / tutorial-tests: .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / tutorial-tests: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache@v4, actions/checkout@v4, actions/download-artifact@v4, actions/setup-go@v5, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / lint: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0d8LcagAAAACYA++vdYxJTbF5QtY5X7vMUEhMMzBFREdFMDIwOQBFZGdl
full / lint: .github#9

! Failed to restore: Cache service responded with 400
full / lint: .github#46

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / lint: .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* master Full CI · 40101618059
Triggered via workflow_dispatch about 1 hour ago

JOBS
✓ full / prepare in 21s (ID 120894787205)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Validate qualification inputs
  - Download the sealed candidate manifest
  - Bind published identity from the sealed manifest
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
- full / docs-build in 0s (ID 120894788065)
- full / release-core-floor-smoke in 0s (ID 120894788195)
✓ full / build-core / build-core in 15m0s (ID 120894871757)
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
X full / visual-test in 26m44s (ID 120898126634)
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
✓ full / perf-floors in 9m54s (ID 120898126640)
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
✓ full / ace-page-group-isolation in 1m41s (ID 120898126672)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  ✓ Run ACE shared-page isolation lane
  ✓ Post Install visual dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ full / test (3.14) in 57m30s (ID 120898126703)
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
✓ full / test (3.13) in 45m14s (ID 120898126705)
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
✓ full / tutorial-tests in 57s (ID 120898126715)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run tutorial tests
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* full / test (3.12) (ID 120898126799)
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
✓ full / lint in 6m35s (ID 120898127009)
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

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / prepare: .github#6

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / prepare: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / build-core / build-core: .github#4

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>06MDcagAAAABlR3X2rL5lQKrpisTUl4fuU0xDMzFFREdFMDIyMABFZGdl
full / build-core / build-core: .github#7

! Failed to restore: Cache service responded with 400
full / build-core / build-core: .github#25

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / build-core / build-core: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / ace-page-group-isolation: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0UcHcagAAAABoxZI+wa2fSI+qzPyP3AN1UEhMMzBFREdFMDQxOABFZGdl
full / ace-page-group-isolation: .github#9

! Failed to restore: Cache service responded with 400
full / ace-page-group-isolation: .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / ace-page-group-isolation: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / tutorial-tests: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0JcHcagAAAABh43fuT51GRaeM4a3iJHApUEhYMzFFREdFMDIxNwBFZGdl
full / tutorial-tests: .github#9

! Failed to restore: Cache service responded with 400
full / tutorial-tests: .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / tutorial-tests: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache@v4, actions/checkout@v4, actions/download-artifact@v4, actions/setup-go@v5, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / lint: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0d8LcagAAAACYA++vdYxJTbF5QtY5X7vMUEhMMzBFREdFMDIwOQBFZGdl
full / lint: .github#9

! Failed to restore: Cache service responded with 400
full / lint: .github#46

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / lint: .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* master Full CI · 40101618059
Triggered via workflow_dispatch about 1 hour ago

JOBS
✓ full / prepare in 21s (ID 120894787205)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Validate qualification inputs
  - Download the sealed candidate manifest
  - Bind published identity from the sealed manifest
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
- full / docs-build in 0s (ID 120894788065)
- full / release-core-floor-smoke in 0s (ID 120894788195)
✓ full / build-core / build-core in 15m0s (ID 120894871757)
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
X full / visual-test in 26m44s (ID 120898126634)
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
✓ full / perf-floors in 9m54s (ID 120898126640)
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
✓ full / ace-page-group-isolation in 1m41s (ID 120898126672)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  ✓ Run ACE shared-page isolation lane
  ✓ Post Install visual dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ full / test (3.14) in 57m30s (ID 120898126703)
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
✓ full / test (3.13) in 45m14s (ID 120898126705)
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
✓ full / tutorial-tests in 57s (ID 120898126715)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run tutorial tests
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* full / test (3.12) (ID 120898126799)
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
✓ full / lint in 6m35s (ID 120898127009)
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

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / prepare: .github#6

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / prepare: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / build-core / build-core: .github#4

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>06MDcagAAAABlR3X2rL5lQKrpisTUl4fuU0xDMzFFREdFMDIyMABFZGdl
full / build-core / build-core: .github#7

! Failed to restore: Cache service responded with 400
full / build-core / build-core: .github#25

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / build-core / build-core: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / ace-page-group-isolation: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0UcHcagAAAABoxZI+wa2fSI+qzPyP3AN1UEhMMzBFREdFMDQxOABFZGdl
full / ace-page-group-isolation: .github#9

! Failed to restore: Cache service responded with 400
full / ace-page-group-isolation: .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / ace-page-group-isolation: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / tutorial-tests: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0JcHcagAAAABh43fuT51GRaeM4a3iJHApUEhYMzFFREdFMDIxNwBFZGdl
full / tutorial-tests: .github#9

! Failed to restore: Cache service responded with 400
full / tutorial-tests: .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / tutorial-tests: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache@v4, actions/checkout@v4, actions/download-artifact@v4, actions/setup-go@v5, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / lint: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0d8LcagAAAACYA++vdYxJTbF5QtY5X7vMUEhMMzBFREdFMDIwOQBFZGdl
full / lint: .github#9

! Failed to restore: Cache service responded with 400
full / lint: .github#46

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / lint: .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* master Full CI · 40101618059
Triggered via workflow_dispatch about 1 hour ago

JOBS
✓ full / prepare in 21s (ID 120894787205)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Validate qualification inputs
  - Download the sealed candidate manifest
  - Bind published identity from the sealed manifest
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
- full / docs-build in 0s (ID 120894788065)
- full / release-core-floor-smoke in 0s (ID 120894788195)
✓ full / build-core / build-core in 15m0s (ID 120894871757)
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
X full / visual-test in 26m44s (ID 120898126634)
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
✓ full / perf-floors in 9m54s (ID 120898126640)
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
✓ full / ace-page-group-isolation in 1m41s (ID 120898126672)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  ✓ Run ACE shared-page isolation lane
  ✓ Post Install visual dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ full / test (3.14) in 57m30s (ID 120898126703)
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
✓ full / test (3.13) in 45m14s (ID 120898126705)
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
✓ full / tutorial-tests in 57s (ID 120898126715)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run tutorial tests
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* full / test (3.12) (ID 120898126799)
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
✓ full / lint in 6m35s (ID 120898127009)
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

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / prepare: .github#6

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / prepare: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / build-core / build-core: .github#4

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>06MDcagAAAABlR3X2rL5lQKrpisTUl4fuU0xDMzFFREdFMDIyMABFZGdl
full / build-core / build-core: .github#7

! Failed to restore: Cache service responded with 400
full / build-core / build-core: .github#25

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / build-core / build-core: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / ace-page-group-isolation: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0UcHcagAAAABoxZI+wa2fSI+qzPyP3AN1UEhMMzBFREdFMDQxOABFZGdl
full / ace-page-group-isolation: .github#9

! Failed to restore: Cache service responded with 400
full / ace-page-group-isolation: .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / ace-page-group-isolation: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / tutorial-tests: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0JcHcagAAAABh43fuT51GRaeM4a3iJHApUEhYMzFFREdFMDIxNwBFZGdl
full / tutorial-tests: .github#9

! Failed to restore: Cache service responded with 400
full / tutorial-tests: .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / tutorial-tests: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache@v4, actions/checkout@v4, actions/download-artifact@v4, actions/setup-go@v5, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / lint: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0d8LcagAAAACYA++vdYxJTbF5QtY5X7vMUEhMMzBFREdFMDIwOQBFZGdl
full / lint: .github#9

! Failed to restore: Cache service responded with 400
full / lint: .github#46

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / lint: .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* master Full CI · 40101618059
Triggered via workflow_dispatch about 1 hour ago

JOBS
✓ full / prepare in 21s (ID 120894787205)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Validate qualification inputs
  - Download the sealed candidate manifest
  - Bind published identity from the sealed manifest
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
- full / docs-build in 0s (ID 120894788065)
- full / release-core-floor-smoke in 0s (ID 120894788195)
✓ full / build-core / build-core in 15m0s (ID 120894871757)
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
X full / visual-test in 26m44s (ID 120898126634)
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
✓ full / perf-floors in 9m54s (ID 120898126640)
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
✓ full / ace-page-group-isolation in 1m41s (ID 120898126672)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  ✓ Run ACE shared-page isolation lane
  ✓ Post Install visual dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ full / test (3.14) in 57m30s (ID 120898126703)
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
✓ full / test (3.13) in 45m14s (ID 120898126705)
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
✓ full / tutorial-tests in 57s (ID 120898126715)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run tutorial tests
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* full / test (3.12) (ID 120898126799)
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
✓ full / lint in 6m35s (ID 120898127009)
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

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / prepare: .github#6

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / prepare: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / build-core / build-core: .github#4

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>06MDcagAAAABlR3X2rL5lQKrpisTUl4fuU0xDMzFFREdFMDIyMABFZGdl
full / build-core / build-core: .github#7

! Failed to restore: Cache service responded with 400
full / build-core / build-core: .github#25

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / build-core / build-core: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / ace-page-group-isolation: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0UcHcagAAAABoxZI+wa2fSI+qzPyP3AN1UEhMMzBFREdFMDQxOABFZGdl
full / ace-page-group-isolation: .github#9

! Failed to restore: Cache service responded with 400
full / ace-page-group-isolation: .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / ace-page-group-isolation: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / tutorial-tests: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0JcHcagAAAABh43fuT51GRaeM4a3iJHApUEhYMzFFREdFMDIxNwBFZGdl
full / tutorial-tests: .github#9

! Failed to restore: Cache service responded with 400
full / tutorial-tests: .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / tutorial-tests: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache@v4, actions/checkout@v4, actions/download-artifact@v4, actions/setup-go@v5, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / lint: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0d8LcagAAAACYA++vdYxJTbF5QtY5X7vMUEhMMzBFREdFMDIwOQBFZGdl
full / lint: .github#9

! Failed to restore: Cache service responded with 400
full / lint: .github#46

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / lint: .github#1

X master Full CI · 40101618059
Triggered via workflow_dispatch about 1 hour ago

JOBS
✓ full / prepare in 21s (ID 120894787205)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Validate qualification inputs
  - Download the sealed candidate manifest
  - Bind published identity from the sealed manifest
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
- full / docs-build in 0s (ID 120894788065)
- full / release-core-floor-smoke in 0s (ID 120894788195)
✓ full / build-core / build-core in 15m0s (ID 120894871757)
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
X full / visual-test in 26m44s (ID 120898126634)
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
✓ full / perf-floors in 9m54s (ID 120898126640)
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
✓ full / ace-page-group-isolation in 1m41s (ID 120898126672)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  ✓ Run ACE shared-page isolation lane
  ✓ Post Install visual dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ full / test (3.14) in 57m30s (ID 120898126703)
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
✓ full / test (3.13) in 45m14s (ID 120898126705)
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
✓ full / tutorial-tests in 57s (ID 120898126715)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run tutorial tests
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ full / test (3.12) in 1h6m14s (ID 120898126799)
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
✓ full / lint in 6m35s (ID 120898127009)
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

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / prepare: .github#6

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / prepare: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / build-core / build-core: .github#4

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>06MDcagAAAABlR3X2rL5lQKrpisTUl4fuU0xDMzFFREdFMDIyMABFZGdl
full / build-core / build-core: .github#7

! Failed to restore: Cache service responded with 400
full / build-core / build-core: .github#25

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / build-core / build-core: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / ace-page-group-isolation: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0UcHcagAAAABoxZI+wa2fSI+qzPyP3AN1UEhMMzBFREdFMDQxOABFZGdl
full / ace-page-group-isolation: .github#9

! Failed to restore: Cache service responded with 400
full / ace-page-group-isolation: .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / ace-page-group-isolation: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / tutorial-tests: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0JcHcagAAAABh43fuT51GRaeM4a3iJHApUEhYMzFFREdFMDIxNwBFZGdl
full / tutorial-tests: .github#9

! Failed to restore: Cache service responded with 400
full / tutorial-tests: .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / tutorial-tests: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4, codecov/codecov-action@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / test (3.12): .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0cdDcagAAAABTVyk3dOTNTLQAjB8BDHodTVNQMzExMDAwMTAzMDQ3AEVkZ2U=
full / test (3.12): .github#9

! Failed to restore: Cache service responded with 400
full / test (3.12): .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / test (3.12): .github#1


