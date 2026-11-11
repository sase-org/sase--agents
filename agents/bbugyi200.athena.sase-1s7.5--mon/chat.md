# Chat History - ace-run (sase-1s7.5--mon)

- **TIMESTAMP:** 2026-11-10 19:25:18 EST
- **MODEL:** grok/grok-4.6
- **AGENT:** sase-1s7.5--mon

## Prompt

sase monitor start --command 'gh run watch 42895182653 -R sase-org/sase --interval 120 || true; gh run watch 42897320508 -R sase-org/sase --interval 120 || true; gh run watch 42897324688 -R sase-org/sase --interval 120 || true' --reason 'Wait for Master Gate, Full CI, and Telemetry on 1df3ade04d for sase-1s7.5'

## Response

sase: running unwrapped (no profile (monitor.tool_wrap is verify))
Run Master Gate (42895182653) has already completed with 'success'
Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* master Full CI · 42897320508
Triggered via workflow_dispatch about 2 minutes ago

JOBS
✓ full / prepare in 22s (ID 130113766345)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Validate qualification inputs
  - Download the sealed candidate manifest
  - Bind published identity from the sealed manifest
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
- full / docs-build (ID 130113768089)
- full / release-core-floor-smoke (ID 130113769703)
* full / build-core / build-core (ID 130113996267)
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

* master Full CI · 42897320508
Triggered via workflow_dispatch about 4 minutes ago

JOBS
✓ full / prepare in 22s (ID 130113766345)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Validate qualification inputs
  - Download the sealed candidate manifest
  - Bind published identity from the sealed manifest
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
- full / docs-build (ID 130113768089)
- full / release-core-floor-smoke (ID 130113769703)
* full / build-core / build-core (ID 130113996267)
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

* master Full CI · 42897320508
Triggered via workflow_dispatch about 6 minutes ago

JOBS
✓ full / prepare in 22s (ID 130113766345)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Validate qualification inputs
  - Download the sealed candidate manifest
  - Bind published identity from the sealed manifest
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
- full / docs-build (ID 130113768089)
- full / release-core-floor-smoke (ID 130113769703)
* full / build-core / build-core (ID 130113996267)
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

* master Full CI · 42897320508
Triggered via workflow_dispatch about 8 minutes ago

JOBS
✓ full / prepare in 22s (ID 130113766345)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Validate qualification inputs
  - Download the sealed candidate manifest
  - Bind published identity from the sealed manifest
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
- full / docs-build (ID 130113768089)
- full / release-core-floor-smoke (ID 130113769703)
* full / build-core / build-core (ID 130113996267)
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

* master Full CI · 42897320508
Triggered via workflow_dispatch about 10 minutes ago

JOBS
✓ full / prepare in 22s (ID 130113766345)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Validate qualification inputs
  - Download the sealed candidate manifest
  - Bind published identity from the sealed manifest
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
- full / docs-build (ID 130113768089)
- full / release-core-floor-smoke (ID 130113769703)
* full / build-core / build-core (ID 130113996267)
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

* master Full CI · 42897320508
Triggered via workflow_dispatch about 12 minutes ago

JOBS
✓ full / prepare in 22s (ID 130113766345)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Validate qualification inputs
  - Download the sealed candidate manifest
  - Bind published identity from the sealed manifest
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
- full / docs-build (ID 130113768089)
- full / release-core-floor-smoke (ID 130113769703)
* full / build-core / build-core (ID 130113996267)
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

* master Full CI · 42897320508
Triggered via workflow_dispatch about 14 minutes ago

JOBS
✓ full / prepare in 22s (ID 130113766345)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Validate qualification inputs
  - Download the sealed candidate manifest
  - Bind published identity from the sealed manifest
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
- full / docs-build (ID 130113768089)
- full / release-core-floor-smoke (ID 130113769703)
* full / build-core / build-core (ID 130113996267)
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

* master Full CI · 42897320508
Triggered via workflow_dispatch about 16 minutes ago

JOBS
✓ full / prepare in 22s (ID 130113766345)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Validate qualification inputs
  - Download the sealed candidate manifest
  - Bind published identity from the sealed manifest
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
- full / docs-build (ID 130113768089)
- full / release-core-floor-smoke (ID 130113769703)
✓ full / build-core / build-core in 15m56s (ID 130113996267)
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
* full / visual-test (ID 130122872417)
* full / lint (ID 130122872426)
* full / test (3.13) (ID 130122872481)
* full / test (3.12) (ID 130122872519)
* full / ace-page-group-isolation (ID 130122872542)
* full / perf-floors (ID 130122872543)
* full / test (3.14) (ID 130122872544)
* full / tutorial-tests (ID 130122872691)

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / prepare: .github#6

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / prepare: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
full / build-core / build-core: .github#4

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0rITzagAAAACbilJCp1gURZWQuZlQNOw0UEhMMzBFREdFMDExMABFZGdl
full / build-core / build-core: .github#7

! Failed to restore: Cache service responded with 400
full / build-core / build-core: .github#25

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / build-core / build-core: .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* master Full CI · 42897320508
Triggered via workflow_dispatch about 18 minutes ago

JOBS
✓ full / prepare in 22s (ID 130113766345)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Validate qualification inputs
  - Download the sealed candidate manifest
  - Bind published identity from the sealed manifest
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
- full / docs-build (ID 130113768089)
- full / release-core-floor-smoke (ID 130113769703)
✓ full / build-core / build-core in 15m56s (ID 130113996267)
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
* full / visual-test (ID 130122872417)
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
* full / lint (ID 130122872426)
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
* full / test (3.13) (ID 130122872481)
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
* full / test (3.12) (ID 130122872519)
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
✓ full / ace-page-group-isolation in 1m38s (ID 130122872542)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  ✓ Run ACE shared-page isolation lane
  ✓ Post Install visual dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* full / perf-floors (ID 130122872543)
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
* full / test (3.14) (ID 130122872544)
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
✓ full / tutorial-tests in 1m1s (ID 130122872691)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run tutorial tests
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

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0rITzagAAAACbilJCp1gURZWQuZlQNOw0UEhMMzBFREdFMDExMABFZGdl
full / build-core / build-core: .github#7

! Failed to restore: Cache service responded with 400
full / build-core / build-core: .github#25

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / build-core / build-core: .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* master Full CI · 42897320508
Triggered via workflow_dispatch about 20 minutes ago

JOBS
✓ full / prepare in 22s (ID 130113766345)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Validate qualification inputs
  - Download the sealed candidate manifest
  - Bind published identity from the sealed manifest
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
- full / docs-build (ID 130113768089)
- full / release-core-floor-smoke (ID 130113769703)
✓ full / build-core / build-core in 15m56s (ID 130113996267)
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
* full / visual-test (ID 130122872417)
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
* full / lint (ID 130122872426)
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
* full / test (3.13) (ID 130122872481)
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
* full / test (3.12) (ID 130122872519)
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
✓ full / ace-page-group-isolation in 1m38s (ID 130122872542)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  ✓ Run ACE shared-page isolation lane
  ✓ Post Install visual dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* full / perf-floors (ID 130122872543)
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
* full / test (3.14) (ID 130122872544)
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
✓ full / tutorial-tests in 1m1s (ID 130122872691)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run tutorial tests
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

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0rITzagAAAACbilJCp1gURZWQuZlQNOw0UEhMMzBFREdFMDExMABFZGdl
full / build-core / build-core: .github#7

! Failed to restore: Cache service responded with 400
full / build-core / build-core: .github#25

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / build-core / build-core: .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* master Full CI · 42897320508
Triggered via workflow_dispatch about 22 minutes ago

JOBS
✓ full / prepare in 22s (ID 130113766345)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Validate qualification inputs
  - Download the sealed candidate manifest
  - Bind published identity from the sealed manifest
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
- full / docs-build (ID 130113768089)
- full / release-core-floor-smoke (ID 130113769703)
✓ full / build-core / build-core in 15m56s (ID 130113996267)
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
* full / visual-test (ID 130122872417)
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
✓ full / lint in 5m58s (ID 130122872426)
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
* full / test (3.13) (ID 130122872481)
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
* full / test (3.12) (ID 130122872519)
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
✓ full / ace-page-group-isolation in 1m38s (ID 130122872542)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  ✓ Run ACE shared-page isolation lane
  ✓ Post Install visual dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* full / perf-floors (ID 130122872543)
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
* full / test (3.14) (ID 130122872544)
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
✓ full / tutorial-tests in 1m1s (ID 130122872691)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run tutorial tests
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

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0rITzagAAAACbilJCp1gURZWQuZlQNOw0UEhMMzBFREdFMDExMABFZGdl
full / build-core / build-core: .github#7

! Failed to restore: Cache service responded with 400
full / build-core / build-core: .github#25

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / build-core / build-core: .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* master Full CI · 42897320508
Triggered via workflow_dispatch about 24 minutes ago

JOBS
✓ full / prepare in 22s (ID 130113766345)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Validate qualification inputs
  - Download the sealed candidate manifest
  - Bind published identity from the sealed manifest
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
- full / docs-build (ID 130113768089)
- full / release-core-floor-smoke (ID 130113769703)
✓ full / build-core / build-core in 15m56s (ID 130113996267)
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
* full / visual-test (ID 130122872417)
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
✓ full / lint in 5m58s (ID 130122872426)
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
* full / test (3.13) (ID 130122872481)
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
* full / test (3.12) (ID 130122872519)
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
✓ full / ace-page-group-isolation in 1m38s (ID 130122872542)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  ✓ Run ACE shared-page isolation lane
  ✓ Post Install visual dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* full / perf-floors (ID 130122872543)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Health check (Rust extension loadable)
  ✓ Run slow tests
  ✓ Run Phase 7E regression floor
  ✓ Upload Phase 7E floor-check report
  ✓ Run launch regression floor
  ✓ Upload launch floor-check report
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
* full / test (3.14) (ID 130122872544)
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
✓ full / tutorial-tests in 1m1s (ID 130122872691)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run tutorial tests
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

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0rITzagAAAACbilJCp1gURZWQuZlQNOw0UEhMMzBFREdFMDExMABFZGdl
full / build-core / build-core: .github#7

! Failed to restore: Cache service responded with 400
full / build-core / build-core: .github#25

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / build-core / build-core: .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* master Full CI · 42897320508
Triggered via workflow_dispatch about 26 minutes ago

JOBS
✓ full / prepare in 22s (ID 130113766345)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Validate qualification inputs
  - Download the sealed candidate manifest
  - Bind published identity from the sealed manifest
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
- full / docs-build (ID 130113768089)
- full / release-core-floor-smoke (ID 130113769703)
✓ full / build-core / build-core in 15m56s (ID 130113996267)
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
* full / visual-test (ID 130122872417)
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
✓ full / lint in 5m58s (ID 130122872426)
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
* full / test (3.13) (ID 130122872481)
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
* full / test (3.12) (ID 130122872519)
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
✓ full / ace-page-group-isolation in 1m38s (ID 130122872542)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  ✓ Run ACE shared-page isolation lane
  ✓ Post Install visual dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ full / perf-floors in 9m21s (ID 130122872543)
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
* full / test (3.14) (ID 130122872544)
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
✓ full / tutorial-tests in 1m1s (ID 130122872691)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run tutorial tests
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

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0rITzagAAAACbilJCp1gURZWQuZlQNOw0UEhMMzBFREdFMDExMABFZGdl
full / build-core / build-core: .github#7

! Failed to restore: Cache service responded with 400
full / build-core / build-core: .github#25

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / build-core / build-core: .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* master Full CI · 42897320508
Triggered via workflow_dispatch about 28 minutes ago

JOBS
✓ full / prepare in 22s (ID 130113766345)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Validate qualification inputs
  - Download the sealed candidate manifest
  - Bind published identity from the sealed manifest
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
- full / docs-build (ID 130113768089)
- full / release-core-floor-smoke (ID 130113769703)
✓ full / build-core / build-core in 15m56s (ID 130113996267)
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
* full / visual-test (ID 130122872417)
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
✓ full / lint in 5m58s (ID 130122872426)
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
* full / test (3.13) (ID 130122872481)
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
* full / test (3.12) (ID 130122872519)
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
✓ full / ace-page-group-isolation in 1m38s (ID 130122872542)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  ✓ Run ACE shared-page isolation lane
  ✓ Post Install visual dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ full / perf-floors in 9m21s (ID 130122872543)
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
* full / test (3.14) (ID 130122872544)
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
✓ full / tutorial-tests in 1m1s (ID 130122872691)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run tutorial tests
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

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0rITzagAAAACbilJCp1gURZWQuZlQNOw0UEhMMzBFREdFMDExMABFZGdl
full / build-core / build-core: .github#7

! Failed to restore: Cache service responded with 400
full / build-core / build-core: .github#25

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / build-core / build-core: .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* master Full CI · 42897320508
Triggered via workflow_dispatch about 30 minutes ago

JOBS
✓ full / prepare in 22s (ID 130113766345)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Validate qualification inputs
  - Download the sealed candidate manifest
  - Bind published identity from the sealed manifest
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
- full / docs-build (ID 130113768089)
- full / release-core-floor-smoke (ID 130113769703)
✓ full / build-core / build-core in 15m56s (ID 130113996267)
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
* full / visual-test (ID 130122872417)
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
✓ full / lint in 5m58s (ID 130122872426)
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
* full / test (3.13) (ID 130122872481)
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
* full / test (3.12) (ID 130122872519)
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
✓ full / ace-page-group-isolation in 1m38s (ID 130122872542)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  ✓ Run ACE shared-page isolation lane
  ✓ Post Install visual dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ full / perf-floors in 9m21s (ID 130122872543)
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
* full / test (3.14) (ID 130122872544)
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
✓ full / tutorial-tests in 1m1s (ID 130122872691)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run tutorial tests
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

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0rITzagAAAACbilJCp1gURZWQuZlQNOw0UEhMMzBFREdFMDExMABFZGdl
full / build-core / build-core: .github#7

! Failed to restore: Cache service responded with 400
full / build-core / build-core: .github#25

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / build-core / build-core: .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* master Full CI · 42897320508
Triggered via workflow_dispatch about 32 minutes ago

JOBS
✓ full / prepare in 22s (ID 130113766345)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Validate qualification inputs
  - Download the sealed candidate manifest
  - Bind published identity from the sealed manifest
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
- full / docs-build (ID 130113768089)
- full / release-core-floor-smoke (ID 130113769703)
✓ full / build-core / build-core in 15m56s (ID 130113996267)
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
* full / visual-test (ID 130122872417)
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
✓ full / lint in 5m58s (ID 130122872426)
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
* full / test (3.13) (ID 130122872481)
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
* full / test (3.12) (ID 130122872519)
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
✓ full / ace-page-group-isolation in 1m38s (ID 130122872542)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  ✓ Run ACE shared-page isolation lane
  ✓ Post Install visual dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ full / perf-floors in 9m21s (ID 130122872543)
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
* full / test (3.14) (ID 130122872544)
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
✓ full / tutorial-tests in 1m1s (ID 130122872691)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run tutorial tests
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

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0rITzagAAAACbilJCp1gURZWQuZlQNOw0UEhMMzBFREdFMDExMABFZGdl
full / build-core / build-core: .github#7

! Failed to restore: Cache service responded with 400
full / build-core / build-core: .github#25

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / build-core / build-core: .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* master Full CI · 42897320508
Triggered via workflow_dispatch about 34 minutes ago

JOBS
✓ full / prepare in 22s (ID 130113766345)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Validate qualification inputs
  - Download the sealed candidate manifest
  - Bind published identity from the sealed manifest
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
- full / docs-build (ID 130113768089)
- full / release-core-floor-smoke (ID 130113769703)
✓ full / build-core / build-core in 15m56s (ID 130113996267)
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
* full / visual-test (ID 130122872417)
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
✓ full / lint in 5m58s (ID 130122872426)
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
* full / test (3.13) (ID 130122872481)
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
* full / test (3.12) (ID 130122872519)
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
✓ full / ace-page-group-isolation in 1m38s (ID 130122872542)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  ✓ Run ACE shared-page isolation lane
  ✓ Post Install visual dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ full / perf-floors in 9m21s (ID 130122872543)
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
* full / test (3.14) (ID 130122872544)
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
✓ full / tutorial-tests in 1m1s (ID 130122872691)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run tutorial tests
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

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0rITzagAAAACbilJCp1gURZWQuZlQNOw0UEhMMzBFREdFMDExMABFZGdl
full / build-core / build-core: .github#7

! Failed to restore: Cache service responded with 400
full / build-core / build-core: .github#25

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / build-core / build-core: .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* master Full CI · 42897320508
Triggered via workflow_dispatch about 36 minutes ago

JOBS
✓ full / prepare in 22s (ID 130113766345)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Validate qualification inputs
  - Download the sealed candidate manifest
  - Bind published identity from the sealed manifest
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
- full / docs-build (ID 130113768089)
- full / release-core-floor-smoke (ID 130113769703)
✓ full / build-core / build-core in 15m56s (ID 130113996267)
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
* full / visual-test (ID 130122872417)
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
✓ full / lint in 5m58s (ID 130122872426)
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
* full / test (3.13) (ID 130122872481)
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
* full / test (3.12) (ID 130122872519)
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
✓ full / ace-page-group-isolation in 1m38s (ID 130122872542)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  ✓ Run ACE shared-page isolation lane
  ✓ Post Install visual dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ full / perf-floors in 9m21s (ID 130122872543)
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
* full / test (3.14) (ID 130122872544)
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
✓ full / tutorial-tests in 1m1s (ID 130122872691)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run tutorial tests
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

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0rITzagAAAACbilJCp1gURZWQuZlQNOw0UEhMMzBFREdFMDExMABFZGdl
full / build-core / build-core: .github#7

! Failed to restore: Cache service responded with 400
full / build-core / build-core: .github#25

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / build-core / build-core: .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* master Full CI · 42897320508
Triggered via workflow_dispatch about 38 minutes ago

JOBS
✓ full / prepare in 22s (ID 130113766345)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Validate qualification inputs
  - Download the sealed candidate manifest
  - Bind published identity from the sealed manifest
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
- full / docs-build (ID 130113768089)
- full / release-core-floor-smoke (ID 130113769703)
✓ full / build-core / build-core in 15m56s (ID 130113996267)
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
* full / visual-test (ID 130122872417)
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
✓ full / lint in 5m58s (ID 130122872426)
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
* full / test (3.13) (ID 130122872481)
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
* full / test (3.12) (ID 130122872519)
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
✓ full / ace-page-group-isolation in 1m38s (ID 130122872542)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  ✓ Run ACE shared-page isolation lane
  ✓ Post Install visual dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ full / perf-floors in 9m21s (ID 130122872543)
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
* full / test (3.14) (ID 130122872544)
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
✓ full / tutorial-tests in 1m1s (ID 130122872691)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run tutorial tests
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

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0rITzagAAAACbilJCp1gURZWQuZlQNOw0UEhMMzBFREdFMDExMABFZGdl
full / build-core / build-core: .github#7

! Failed to restore: Cache service responded with 400
full / build-core / build-core: .github#25

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / build-core / build-core: .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* master Full CI · 42897320508
Triggered via workflow_dispatch about 40 minutes ago

JOBS
✓ full / prepare in 22s (ID 130113766345)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Validate qualification inputs
  - Download the sealed candidate manifest
  - Bind published identity from the sealed manifest
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
- full / docs-build (ID 130113768089)
- full / release-core-floor-smoke (ID 130113769703)
✓ full / build-core / build-core in 15m56s (ID 130113996267)
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
* full / visual-test (ID 130122872417)
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
✓ full / lint in 5m58s (ID 130122872426)
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
* full / test (3.13) (ID 130122872481)
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
* full / test (3.12) (ID 130122872519)
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
✓ full / ace-page-group-isolation in 1m38s (ID 130122872542)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  ✓ Run ACE shared-page isolation lane
  ✓ Post Install visual dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ full / perf-floors in 9m21s (ID 130122872543)
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
* full / test (3.14) (ID 130122872544)
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
✓ full / tutorial-tests in 1m1s (ID 130122872691)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run tutorial tests
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

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0rITzagAAAACbilJCp1gURZWQuZlQNOw0UEhMMzBFREdFMDExMABFZGdl
full / build-core / build-core: .github#7

! Failed to restore: Cache service responded with 400
full / build-core / build-core: .github#25

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / build-core / build-core: .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* master Full CI · 42897320508
Triggered via workflow_dispatch about 42 minutes ago

JOBS
✓ full / prepare in 22s (ID 130113766345)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Validate qualification inputs
  - Download the sealed candidate manifest
  - Bind published identity from the sealed manifest
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
- full / docs-build (ID 130113768089)
- full / release-core-floor-smoke (ID 130113769703)
✓ full / build-core / build-core in 15m56s (ID 130113996267)
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
* full / visual-test (ID 130122872417)
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
✓ full / lint in 5m58s (ID 130122872426)
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
* full / test (3.13) (ID 130122872481)
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
* full / test (3.12) (ID 130122872519)
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
✓ full / ace-page-group-isolation in 1m38s (ID 130122872542)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  ✓ Run ACE shared-page isolation lane
  ✓ Post Install visual dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ full / perf-floors in 9m21s (ID 130122872543)
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
* full / test (3.14) (ID 130122872544)
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
✓ full / tutorial-tests in 1m1s (ID 130122872691)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run tutorial tests
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

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0rITzagAAAACbilJCp1gURZWQuZlQNOw0UEhMMzBFREdFMDExMABFZGdl
full / build-core / build-core: .github#7

! Failed to restore: Cache service responded with 400
full / build-core / build-core: .github#25

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / build-core / build-core: .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* master Full CI · 42897320508
Triggered via workflow_dispatch about 44 minutes ago

JOBS
✓ full / prepare in 22s (ID 130113766345)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Validate qualification inputs
  - Download the sealed candidate manifest
  - Bind published identity from the sealed manifest
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
- full / docs-build (ID 130113768089)
- full / release-core-floor-smoke (ID 130113769703)
✓ full / build-core / build-core in 15m56s (ID 130113996267)
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
* full / visual-test (ID 130122872417)
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
✓ full / lint in 5m58s (ID 130122872426)
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
* full / test (3.13) (ID 130122872481)
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
* full / test (3.12) (ID 130122872519)
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
✓ full / ace-page-group-isolation in 1m38s (ID 130122872542)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  ✓ Run ACE shared-page isolation lane
  ✓ Post Install visual dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ full / perf-floors in 9m21s (ID 130122872543)
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
* full / test (3.14) (ID 130122872544)
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
✓ full / tutorial-tests in 1m1s (ID 130122872691)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run tutorial tests
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

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0rITzagAAAACbilJCp1gURZWQuZlQNOw0UEhMMzBFREdFMDExMABFZGdl
full / build-core / build-core: .github#7

! Failed to restore: Cache service responded with 400
full / build-core / build-core: .github#25

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / build-core / build-core: .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* master Full CI · 42897320508
Triggered via workflow_dispatch about 46 minutes ago

JOBS
✓ full / prepare in 22s (ID 130113766345)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Validate qualification inputs
  - Download the sealed candidate manifest
  - Bind published identity from the sealed manifest
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
- full / docs-build (ID 130113768089)
- full / release-core-floor-smoke (ID 130113769703)
✓ full / build-core / build-core in 15m56s (ID 130113996267)
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
* full / visual-test (ID 130122872417)
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
✓ full / lint in 5m58s (ID 130122872426)
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
* full / test (3.13) (ID 130122872481)
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
* full / test (3.12) (ID 130122872519)
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
✓ full / ace-page-group-isolation in 1m38s (ID 130122872542)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  ✓ Run ACE shared-page isolation lane
  ✓ Post Install visual dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ full / perf-floors in 9m21s (ID 130122872543)
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
* full / test (3.14) (ID 130122872544)
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
✓ full / tutorial-tests in 1m1s (ID 130122872691)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run tutorial tests
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

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0rITzagAAAACbilJCp1gURZWQuZlQNOw0UEhMMzBFREdFMDExMABFZGdl
full / build-core / build-core: .github#7

! Failed to restore: Cache service responded with 400
full / build-core / build-core: .github#25

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / build-core / build-core: .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* master Full CI · 42897320508
Triggered via workflow_dispatch about 48 minutes ago

JOBS
✓ full / prepare in 22s (ID 130113766345)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Validate qualification inputs
  - Download the sealed candidate manifest
  - Bind published identity from the sealed manifest
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
- full / docs-build (ID 130113768089)
- full / release-core-floor-smoke (ID 130113769703)
✓ full / build-core / build-core in 15m56s (ID 130113996267)
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
* full / visual-test (ID 130122872417)
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
✓ full / lint in 5m58s (ID 130122872426)
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
* full / test (3.13) (ID 130122872481)
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
* full / test (3.12) (ID 130122872519)
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
✓ full / ace-page-group-isolation in 1m38s (ID 130122872542)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  ✓ Run ACE shared-page isolation lane
  ✓ Post Install visual dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ full / perf-floors in 9m21s (ID 130122872543)
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
* full / test (3.14) (ID 130122872544)
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
✓ full / tutorial-tests in 1m1s (ID 130122872691)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run tutorial tests
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

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0rITzagAAAACbilJCp1gURZWQuZlQNOw0UEhMMzBFREdFMDExMABFZGdl
full / build-core / build-core: .github#7

! Failed to restore: Cache service responded with 400
full / build-core / build-core: .github#25

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / build-core / build-core: .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* master Full CI · 42897320508
Triggered via workflow_dispatch about 50 minutes ago

JOBS
✓ full / prepare in 22s (ID 130113766345)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Validate qualification inputs
  - Download the sealed candidate manifest
  - Bind published identity from the sealed manifest
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
- full / docs-build (ID 130113768089)
- full / release-core-floor-smoke (ID 130113769703)
✓ full / build-core / build-core in 15m56s (ID 130113996267)
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
✓ full / visual-test in 32m58s (ID 130122872417)
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
✓ full / lint in 5m58s (ID 130122872426)
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
* full / test (3.13) (ID 130122872481)
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
* full / test (3.12) (ID 130122872519)
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
✓ full / ace-page-group-isolation in 1m38s (ID 130122872542)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  ✓ Run ACE shared-page isolation lane
  ✓ Post Install visual dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ full / perf-floors in 9m21s (ID 130122872543)
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
* full / test (3.14) (ID 130122872544)
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
✓ full / tutorial-tests in 1m1s (ID 130122872691)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run tutorial tests
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

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0rITzagAAAACbilJCp1gURZWQuZlQNOw0UEhMMzBFREdFMDExMABFZGdl
full / build-core / build-core: .github#7

! Failed to restore: Cache service responded with 400
full / build-core / build-core: .github#25

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / build-core / build-core: .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* master Full CI · 42897320508
Triggered via workflow_dispatch about 52 minutes ago

JOBS
✓ full / prepare in 22s (ID 130113766345)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Validate qualification inputs
  - Download the sealed candidate manifest
  - Bind published identity from the sealed manifest
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
- full / docs-build (ID 130113768089)
- full / release-core-floor-smoke (ID 130113769703)
✓ full / build-core / build-core in 15m56s (ID 130113996267)
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
✓ full / visual-test in 32m58s (ID 130122872417)
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
✓ full / lint in 5m58s (ID 130122872426)
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
* full / test (3.13) (ID 130122872481)
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
* full / test (3.12) (ID 130122872519)
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
✓ full / ace-page-group-isolation in 1m38s (ID 130122872542)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  ✓ Run ACE shared-page isolation lane
  ✓ Post Install visual dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ full / perf-floors in 9m21s (ID 130122872543)
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
* full / test (3.14) (ID 130122872544)
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
✓ full / tutorial-tests in 1m1s (ID 130122872691)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run tutorial tests
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

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0rITzagAAAACbilJCp1gURZWQuZlQNOw0UEhMMzBFREdFMDExMABFZGdl
full / build-core / build-core: .github#7

! Failed to restore: Cache service responded with 400
full / build-core / build-core: .github#25

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / build-core / build-core: .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* master Full CI · 42897320508
Triggered via workflow_dispatch about 54 minutes ago

JOBS
✓ full / prepare in 22s (ID 130113766345)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Validate qualification inputs
  - Download the sealed candidate manifest
  - Bind published identity from the sealed manifest
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
- full / docs-build (ID 130113768089)
- full / release-core-floor-smoke (ID 130113769703)
✓ full / build-core / build-core in 15m56s (ID 130113996267)
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
✓ full / visual-test in 32m58s (ID 130122872417)
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
✓ full / lint in 5m58s (ID 130122872426)
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
* full / test (3.13) (ID 130122872481)
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
* full / test (3.12) (ID 130122872519)
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
✓ full / ace-page-group-isolation in 1m38s (ID 130122872542)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  ✓ Run ACE shared-page isolation lane
  ✓ Post Install visual dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ full / perf-floors in 9m21s (ID 130122872543)
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
* full / test (3.14) (ID 130122872544)
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
✓ full / tutorial-tests in 1m1s (ID 130122872691)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run tutorial tests
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

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0rITzagAAAACbilJCp1gURZWQuZlQNOw0UEhMMzBFREdFMDExMABFZGdl
full / build-core / build-core: .github#7

! Failed to restore: Cache service responded with 400
full / build-core / build-core: .github#25

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / build-core / build-core: .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* master Full CI · 42897320508
Triggered via workflow_dispatch about 56 minutes ago

JOBS
✓ full / prepare in 22s (ID 130113766345)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Validate qualification inputs
  - Download the sealed candidate manifest
  - Bind published identity from the sealed manifest
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
- full / docs-build (ID 130113768089)
- full / release-core-floor-smoke (ID 130113769703)
✓ full / build-core / build-core in 15m56s (ID 130113996267)
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
✓ full / visual-test in 32m58s (ID 130122872417)
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
✓ full / lint in 5m58s (ID 130122872426)
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
* full / test (3.13) (ID 130122872481)
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
* full / test (3.12) (ID 130122872519)
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
✓ full / ace-page-group-isolation in 1m38s (ID 130122872542)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  ✓ Run ACE shared-page isolation lane
  ✓ Post Install visual dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ full / perf-floors in 9m21s (ID 130122872543)
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
* full / test (3.14) (ID 130122872544)
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
✓ full / tutorial-tests in 1m1s (ID 130122872691)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run tutorial tests
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

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0rITzagAAAACbilJCp1gURZWQuZlQNOw0UEhMMzBFREdFMDExMABFZGdl
full / build-core / build-core: .github#7

! Failed to restore: Cache service responded with 400
full / build-core / build-core: .github#25

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / build-core / build-core: .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* master Full CI · 42897320508
Triggered via workflow_dispatch about 58 minutes ago

JOBS
✓ full / prepare in 22s (ID 130113766345)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Validate qualification inputs
  - Download the sealed candidate manifest
  - Bind published identity from the sealed manifest
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
- full / docs-build (ID 130113768089)
- full / release-core-floor-smoke (ID 130113769703)
✓ full / build-core / build-core in 15m56s (ID 130113996267)
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
✓ full / visual-test in 32m58s (ID 130122872417)
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
✓ full / lint in 5m58s (ID 130122872426)
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
* full / test (3.13) (ID 130122872481)
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
* full / test (3.12) (ID 130122872519)
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
✓ full / ace-page-group-isolation in 1m38s (ID 130122872542)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  ✓ Run ACE shared-page isolation lane
  ✓ Post Install visual dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ full / perf-floors in 9m21s (ID 130122872543)
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
* full / test (3.14) (ID 130122872544)
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
✓ full / tutorial-tests in 1m1s (ID 130122872691)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run tutorial tests
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

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0rITzagAAAACbilJCp1gURZWQuZlQNOw0UEhMMzBFREdFMDExMABFZGdl
full / build-core / build-core: .github#7

! Failed to restore: Cache service responded with 400
full / build-core / build-core: .github#25

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / build-core / build-core: .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* master Full CI · 42897320508
Triggered via workflow_dispatch about 1 hour ago

JOBS
✓ full / prepare in 22s (ID 130113766345)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Validate qualification inputs
  - Download the sealed candidate manifest
  - Bind published identity from the sealed manifest
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
- full / docs-build (ID 130113768089)
- full / release-core-floor-smoke (ID 130113769703)
✓ full / build-core / build-core in 15m56s (ID 130113996267)
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
✓ full / visual-test in 32m58s (ID 130122872417)
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
✓ full / lint in 5m58s (ID 130122872426)
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
* full / test (3.13) (ID 130122872481)
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
* full / test (3.12) (ID 130122872519)
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
✓ full / ace-page-group-isolation in 1m38s (ID 130122872542)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  ✓ Run ACE shared-page isolation lane
  ✓ Post Install visual dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ full / perf-floors in 9m21s (ID 130122872543)
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
✓ full / test (3.14) in 43m36s (ID 130122872544)
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
✓ full / tutorial-tests in 1m1s (ID 130122872691)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run tutorial tests
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

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0rITzagAAAACbilJCp1gURZWQuZlQNOw0UEhMMzBFREdFMDExMABFZGdl
full / build-core / build-core: .github#7

! Failed to restore: Cache service responded with 400
full / build-core / build-core: .github#25

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / build-core / build-core: .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* master Full CI · 42897320508
Triggered via workflow_dispatch about 1 hour ago

JOBS
✓ full / prepare in 22s (ID 130113766345)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Validate qualification inputs
  - Download the sealed candidate manifest
  - Bind published identity from the sealed manifest
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
- full / docs-build (ID 130113768089)
- full / release-core-floor-smoke (ID 130113769703)
✓ full / build-core / build-core in 15m56s (ID 130113996267)
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
✓ full / visual-test in 32m58s (ID 130122872417)
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
✓ full / lint in 5m58s (ID 130122872426)
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
* full / test (3.13) (ID 130122872481)
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
* full / test (3.12) (ID 130122872519)
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
✓ full / ace-page-group-isolation in 1m38s (ID 130122872542)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  ✓ Run ACE shared-page isolation lane
  ✓ Post Install visual dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ full / perf-floors in 9m21s (ID 130122872543)
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
✓ full / test (3.14) in 43m36s (ID 130122872544)
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
✓ full / tutorial-tests in 1m1s (ID 130122872691)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run tutorial tests
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

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0rITzagAAAACbilJCp1gURZWQuZlQNOw0UEhMMzBFREdFMDExMABFZGdl
full / build-core / build-core: .github#7

! Failed to restore: Cache service responded with 400
full / build-core / build-core: .github#25

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / build-core / build-core: .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* master Full CI · 42897320508
Triggered via workflow_dispatch about 1 hour ago

JOBS
✓ full / prepare in 22s (ID 130113766345)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Validate qualification inputs
  - Download the sealed candidate manifest
  - Bind published identity from the sealed manifest
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
- full / docs-build (ID 130113768089)
- full / release-core-floor-smoke (ID 130113769703)
✓ full / build-core / build-core in 15m56s (ID 130113996267)
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
✓ full / visual-test in 32m58s (ID 130122872417)
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
✓ full / lint in 5m58s (ID 130122872426)
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
* full / test (3.13) (ID 130122872481)
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
* full / test (3.12) (ID 130122872519)
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
✓ full / ace-page-group-isolation in 1m38s (ID 130122872542)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  ✓ Run ACE shared-page isolation lane
  ✓ Post Install visual dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ full / perf-floors in 9m21s (ID 130122872543)
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
✓ full / test (3.14) in 43m36s (ID 130122872544)
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
✓ full / tutorial-tests in 1m1s (ID 130122872691)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run tutorial tests
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

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0rITzagAAAACbilJCp1gURZWQuZlQNOw0UEhMMzBFREdFMDExMABFZGdl
full / build-core / build-core: .github#7

! Failed to restore: Cache service responded with 400
full / build-core / build-core: .github#25

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / build-core / build-core: .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* master Full CI · 42897320508
Triggered via workflow_dispatch about 1 hour ago

JOBS
✓ full / prepare in 22s (ID 130113766345)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Validate qualification inputs
  - Download the sealed candidate manifest
  - Bind published identity from the sealed manifest
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
- full / docs-build (ID 130113768089)
- full / release-core-floor-smoke (ID 130113769703)
✓ full / build-core / build-core in 15m56s (ID 130113996267)
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
✓ full / visual-test in 32m58s (ID 130122872417)
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
✓ full / lint in 5m58s (ID 130122872426)
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
* full / test (3.13) (ID 130122872481)
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
* full / test (3.12) (ID 130122872519)
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
✓ full / ace-page-group-isolation in 1m38s (ID 130122872542)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  ✓ Run ACE shared-page isolation lane
  ✓ Post Install visual dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ full / perf-floors in 9m21s (ID 130122872543)
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
✓ full / test (3.14) in 43m36s (ID 130122872544)
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
✓ full / tutorial-tests in 1m1s (ID 130122872691)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run tutorial tests
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

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0rITzagAAAACbilJCp1gURZWQuZlQNOw0UEhMMzBFREdFMDExMABFZGdl
full / build-core / build-core: .github#7

! Failed to restore: Cache service responded with 400
full / build-core / build-core: .github#25

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / build-core / build-core: .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* master Full CI · 42897320508
Triggered via workflow_dispatch about 1 hour ago

JOBS
✓ full / prepare in 22s (ID 130113766345)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Validate qualification inputs
  - Download the sealed candidate manifest
  - Bind published identity from the sealed manifest
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
- full / docs-build (ID 130113768089)
- full / release-core-floor-smoke (ID 130113769703)
✓ full / build-core / build-core in 15m56s (ID 130113996267)
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
✓ full / visual-test in 32m58s (ID 130122872417)
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
✓ full / lint in 5m58s (ID 130122872426)
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
* full / test (3.13) (ID 130122872481)
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
* full / test (3.12) (ID 130122872519)
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
✓ full / ace-page-group-isolation in 1m38s (ID 130122872542)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  ✓ Run ACE shared-page isolation lane
  ✓ Post Install visual dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ full / perf-floors in 9m21s (ID 130122872543)
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
✓ full / test (3.14) in 43m36s (ID 130122872544)
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
✓ full / tutorial-tests in 1m1s (ID 130122872691)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run tutorial tests
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

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0rITzagAAAACbilJCp1gURZWQuZlQNOw0UEhMMzBFREdFMDExMABFZGdl
full / build-core / build-core: .github#7

! Failed to restore: Cache service responded with 400
full / build-core / build-core: .github#25

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / build-core / build-core: .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* master Full CI · 42897320508
Triggered via workflow_dispatch about 1 hour ago

JOBS
✓ full / prepare in 22s (ID 130113766345)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Validate qualification inputs
  - Download the sealed candidate manifest
  - Bind published identity from the sealed manifest
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
- full / docs-build (ID 130113768089)
- full / release-core-floor-smoke (ID 130113769703)
✓ full / build-core / build-core in 15m56s (ID 130113996267)
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
✓ full / visual-test in 32m58s (ID 130122872417)
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
✓ full / lint in 5m58s (ID 130122872426)
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
* full / test (3.13) (ID 130122872481)
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
* full / test (3.12) (ID 130122872519)
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
✓ full / ace-page-group-isolation in 1m38s (ID 130122872542)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  ✓ Run ACE shared-page isolation lane
  ✓ Post Install visual dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ full / perf-floors in 9m21s (ID 130122872543)
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
✓ full / test (3.14) in 43m36s (ID 130122872544)
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
✓ full / tutorial-tests in 1m1s (ID 130122872691)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run tutorial tests
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

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0rITzagAAAACbilJCp1gURZWQuZlQNOw0UEhMMzBFREdFMDExMABFZGdl
full / build-core / build-core: .github#7

! Failed to restore: Cache service responded with 400
full / build-core / build-core: .github#25

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / build-core / build-core: .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* master Full CI · 42897320508
Triggered via workflow_dispatch about 1 hour ago

JOBS
✓ full / prepare in 22s (ID 130113766345)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Validate qualification inputs
  - Download the sealed candidate manifest
  - Bind published identity from the sealed manifest
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
- full / docs-build (ID 130113768089)
- full / release-core-floor-smoke (ID 130113769703)
✓ full / build-core / build-core in 15m56s (ID 130113996267)
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
✓ full / visual-test in 32m58s (ID 130122872417)
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
✓ full / lint in 5m58s (ID 130122872426)
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
* full / test (3.13) (ID 130122872481)
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
* full / test (3.12) (ID 130122872519)
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
✓ full / ace-page-group-isolation in 1m38s (ID 130122872542)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  ✓ Run ACE shared-page isolation lane
  ✓ Post Install visual dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ full / perf-floors in 9m21s (ID 130122872543)
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
✓ full / test (3.14) in 43m36s (ID 130122872544)
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
✓ full / tutorial-tests in 1m1s (ID 130122872691)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run tutorial tests
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

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0rITzagAAAACbilJCp1gURZWQuZlQNOw0UEhMMzBFREdFMDExMABFZGdl
full / build-core / build-core: .github#7

! Failed to restore: Cache service responded with 400
full / build-core / build-core: .github#25

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / build-core / build-core: .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* master Full CI · 42897320508
Triggered via workflow_dispatch about 1 hour ago

JOBS
✓ full / prepare in 22s (ID 130113766345)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Validate qualification inputs
  - Download the sealed candidate manifest
  - Bind published identity from the sealed manifest
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
- full / docs-build (ID 130113768089)
- full / release-core-floor-smoke (ID 130113769703)
✓ full / build-core / build-core in 15m56s (ID 130113996267)
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
✓ full / visual-test in 32m58s (ID 130122872417)
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
✓ full / lint in 5m58s (ID 130122872426)
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
* full / test (3.13) (ID 130122872481)
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
* full / test (3.12) (ID 130122872519)
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
✓ full / ace-page-group-isolation in 1m38s (ID 130122872542)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  ✓ Run ACE shared-page isolation lane
  ✓ Post Install visual dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ full / perf-floors in 9m21s (ID 130122872543)
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
✓ full / test (3.14) in 43m36s (ID 130122872544)
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
✓ full / tutorial-tests in 1m1s (ID 130122872691)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run tutorial tests
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

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0rITzagAAAACbilJCp1gURZWQuZlQNOw0UEhMMzBFREdFMDExMABFZGdl
full / build-core / build-core: .github#7

! Failed to restore: Cache service responded with 400
full / build-core / build-core: .github#25

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / build-core / build-core: .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* master Full CI · 42897320508
Triggered via workflow_dispatch about 1 hour ago

JOBS
✓ full / prepare in 22s (ID 130113766345)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Validate qualification inputs
  - Download the sealed candidate manifest
  - Bind published identity from the sealed manifest
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
- full / docs-build (ID 130113768089)
- full / release-core-floor-smoke (ID 130113769703)
✓ full / build-core / build-core in 15m56s (ID 130113996267)
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
✓ full / visual-test in 32m58s (ID 130122872417)
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
✓ full / lint in 5m58s (ID 130122872426)
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
* full / test (3.13) (ID 130122872481)
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
* full / test (3.12) (ID 130122872519)
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
✓ full / ace-page-group-isolation in 1m38s (ID 130122872542)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  ✓ Run ACE shared-page isolation lane
  ✓ Post Install visual dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ full / perf-floors in 9m21s (ID 130122872543)
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
✓ full / test (3.14) in 43m36s (ID 130122872544)
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
✓ full / tutorial-tests in 1m1s (ID 130122872691)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run tutorial tests
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

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0rITzagAAAACbilJCp1gURZWQuZlQNOw0UEhMMzBFREdFMDExMABFZGdl
full / build-core / build-core: .github#7

! Failed to restore: Cache service responded with 400
full / build-core / build-core: .github#25

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / build-core / build-core: .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* master Full CI · 42897320508
Triggered via workflow_dispatch about 1 hour ago

JOBS
✓ full / prepare in 22s (ID 130113766345)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Validate qualification inputs
  - Download the sealed candidate manifest
  - Bind published identity from the sealed manifest
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
- full / docs-build (ID 130113768089)
- full / release-core-floor-smoke (ID 130113769703)
✓ full / build-core / build-core in 15m56s (ID 130113996267)
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
✓ full / visual-test in 32m58s (ID 130122872417)
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
✓ full / lint in 5m58s (ID 130122872426)
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
* full / test (3.13) (ID 130122872481)
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
* full / test (3.12) (ID 130122872519)
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
✓ full / ace-page-group-isolation in 1m38s (ID 130122872542)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  ✓ Run ACE shared-page isolation lane
  ✓ Post Install visual dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ full / perf-floors in 9m21s (ID 130122872543)
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
✓ full / test (3.14) in 43m36s (ID 130122872544)
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
✓ full / tutorial-tests in 1m1s (ID 130122872691)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run tutorial tests
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

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0rITzagAAAACbilJCp1gURZWQuZlQNOw0UEhMMzBFREdFMDExMABFZGdl
full / build-core / build-core: .github#7

! Failed to restore: Cache service responded with 400
full / build-core / build-core: .github#25

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / build-core / build-core: .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* master Full CI · 42897320508
Triggered via workflow_dispatch about 1 hour ago

JOBS
✓ full / prepare in 22s (ID 130113766345)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Validate qualification inputs
  - Download the sealed candidate manifest
  - Bind published identity from the sealed manifest
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
- full / docs-build (ID 130113768089)
- full / release-core-floor-smoke (ID 130113769703)
✓ full / build-core / build-core in 15m56s (ID 130113996267)
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
✓ full / visual-test in 32m58s (ID 130122872417)
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
✓ full / lint in 5m58s (ID 130122872426)
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
✓ full / test (3.13) in 1h4m9s (ID 130122872481)
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
* full / test (3.12) (ID 130122872519)
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
✓ full / ace-page-group-isolation in 1m38s (ID 130122872542)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  ✓ Run ACE shared-page isolation lane
  ✓ Post Install visual dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ full / perf-floors in 9m21s (ID 130122872543)
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
✓ full / test (3.14) in 43m36s (ID 130122872544)
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
✓ full / tutorial-tests in 1m1s (ID 130122872691)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run tutorial tests
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

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0rITzagAAAACbilJCp1gURZWQuZlQNOw0UEhMMzBFREdFMDExMABFZGdl
full / build-core / build-core: .github#7

! Failed to restore: Cache service responded with 400
full / build-core / build-core: .github#25

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / build-core / build-core: .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* master Full CI · 42897320508
Triggered via workflow_dispatch about 1 hour ago

JOBS
✓ full / prepare in 22s (ID 130113766345)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Validate qualification inputs
  - Download the sealed candidate manifest
  - Bind published identity from the sealed manifest
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
- full / docs-build (ID 130113768089)
- full / release-core-floor-smoke (ID 130113769703)
✓ full / build-core / build-core in 15m56s (ID 130113996267)
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
✓ full / visual-test in 32m58s (ID 130122872417)
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
✓ full / lint in 5m58s (ID 130122872426)
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
✓ full / test (3.13) in 1h4m9s (ID 130122872481)
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
* full / test (3.12) (ID 130122872519)
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
✓ full / ace-page-group-isolation in 1m38s (ID 130122872542)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  ✓ Run ACE shared-page isolation lane
  ✓ Post Install visual dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ full / perf-floors in 9m21s (ID 130122872543)
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
✓ full / test (3.14) in 43m36s (ID 130122872544)
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
✓ full / tutorial-tests in 1m1s (ID 130122872691)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run tutorial tests
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

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0rITzagAAAACbilJCp1gURZWQuZlQNOw0UEhMMzBFREdFMDExMABFZGdl
full / build-core / build-core: .github#7

! Failed to restore: Cache service responded with 400
full / build-core / build-core: .github#25

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / build-core / build-core: .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* master Full CI · 42897320508
Triggered via workflow_dispatch about 1 hour ago

JOBS
✓ full / prepare in 22s (ID 130113766345)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Validate qualification inputs
  - Download the sealed candidate manifest
  - Bind published identity from the sealed manifest
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
- full / docs-build (ID 130113768089)
- full / release-core-floor-smoke (ID 130113769703)
✓ full / build-core / build-core in 15m56s (ID 130113996267)
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
✓ full / visual-test in 32m58s (ID 130122872417)
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
✓ full / lint in 5m58s (ID 130122872426)
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
✓ full / test (3.13) in 1h4m9s (ID 130122872481)
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
* full / test (3.12) (ID 130122872519)
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
✓ full / ace-page-group-isolation in 1m38s (ID 130122872542)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  ✓ Run ACE shared-page isolation lane
  ✓ Post Install visual dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ full / perf-floors in 9m21s (ID 130122872543)
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
✓ full / test (3.14) in 43m36s (ID 130122872544)
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
✓ full / tutorial-tests in 1m1s (ID 130122872691)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run tutorial tests
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

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0rITzagAAAACbilJCp1gURZWQuZlQNOw0UEhMMzBFREdFMDExMABFZGdl
full / build-core / build-core: .github#7

! Failed to restore: Cache service responded with 400
full / build-core / build-core: .github#25

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / build-core / build-core: .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* master Full CI · 42897320508
Triggered via workflow_dispatch about 1 hour ago

JOBS
✓ full / prepare in 22s (ID 130113766345)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Validate qualification inputs
  - Download the sealed candidate manifest
  - Bind published identity from the sealed manifest
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
- full / docs-build (ID 130113768089)
- full / release-core-floor-smoke (ID 130113769703)
✓ full / build-core / build-core in 15m56s (ID 130113996267)
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
✓ full / visual-test in 32m58s (ID 130122872417)
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
✓ full / lint in 5m58s (ID 130122872426)
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
✓ full / test (3.13) in 1h4m9s (ID 130122872481)
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
* full / test (3.12) (ID 130122872519)
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
✓ full / ace-page-group-isolation in 1m38s (ID 130122872542)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  ✓ Run ACE shared-page isolation lane
  ✓ Post Install visual dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ full / perf-floors in 9m21s (ID 130122872543)
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
✓ full / test (3.14) in 43m36s (ID 130122872544)
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
✓ full / tutorial-tests in 1m1s (ID 130122872691)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run tutorial tests
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

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0rITzagAAAACbilJCp1gURZWQuZlQNOw0UEhMMzBFREdFMDExMABFZGdl
full / build-core / build-core: .github#7

! Failed to restore: Cache service responded with 400
full / build-core / build-core: .github#25

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / build-core / build-core: .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* master Full CI · 42897320508
Triggered via workflow_dispatch about 1 hour ago

JOBS
✓ full / prepare in 22s (ID 130113766345)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Validate qualification inputs
  - Download the sealed candidate manifest
  - Bind published identity from the sealed manifest
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
- full / docs-build (ID 130113768089)
- full / release-core-floor-smoke (ID 130113769703)
✓ full / build-core / build-core in 15m56s (ID 130113996267)
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
✓ full / visual-test in 32m58s (ID 130122872417)
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
✓ full / lint in 5m58s (ID 130122872426)
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
✓ full / test (3.13) in 1h4m9s (ID 130122872481)
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
* full / test (3.12) (ID 130122872519)
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
✓ full / ace-page-group-isolation in 1m38s (ID 130122872542)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  ✓ Run ACE shared-page isolation lane
  ✓ Post Install visual dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ full / perf-floors in 9m21s (ID 130122872543)
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
✓ full / test (3.14) in 43m36s (ID 130122872544)
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
✓ full / tutorial-tests in 1m1s (ID 130122872691)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run tutorial tests
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

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0rITzagAAAACbilJCp1gURZWQuZlQNOw0UEhMMzBFREdFMDExMABFZGdl
full / build-core / build-core: .github#7

! Failed to restore: Cache service responded with 400
full / build-core / build-core: .github#25

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / build-core / build-core: .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* master Full CI · 42897320508
Triggered via workflow_dispatch about 1 hour ago

JOBS
✓ full / prepare in 22s (ID 130113766345)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Validate qualification inputs
  - Download the sealed candidate manifest
  - Bind published identity from the sealed manifest
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
- full / docs-build (ID 130113768089)
- full / release-core-floor-smoke (ID 130113769703)
✓ full / build-core / build-core in 15m56s (ID 130113996267)
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
✓ full / visual-test in 32m58s (ID 130122872417)
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
✓ full / lint in 5m58s (ID 130122872426)
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
✓ full / test (3.13) in 1h4m9s (ID 130122872481)
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
* full / test (3.12) (ID 130122872519)
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
✓ full / ace-page-group-isolation in 1m38s (ID 130122872542)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  ✓ Run ACE shared-page isolation lane
  ✓ Post Install visual dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ full / perf-floors in 9m21s (ID 130122872543)
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
✓ full / test (3.14) in 43m36s (ID 130122872544)
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
✓ full / tutorial-tests in 1m1s (ID 130122872691)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run tutorial tests
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

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0rITzagAAAACbilJCp1gURZWQuZlQNOw0UEhMMzBFREdFMDExMABFZGdl
full / build-core / build-core: .github#7

! Failed to restore: Cache service responded with 400
full / build-core / build-core: .github#25

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / build-core / build-core: .github#1

✓ master Full CI · 42897320508
Triggered via workflow_dispatch about 1 hour ago

JOBS
✓ full / prepare in 22s (ID 130113766345)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Validate qualification inputs
  - Download the sealed candidate manifest
  - Bind published identity from the sealed manifest
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
- full / docs-build (ID 130113768089)
- full / release-core-floor-smoke (ID 130113769703)
✓ full / build-core / build-core in 15m56s (ID 130113996267)
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
✓ full / visual-test in 32m58s (ID 130122872417)
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
✓ full / lint in 5m58s (ID 130122872426)
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
✓ full / test (3.13) in 1h4m9s (ID 130122872481)
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
✓ full / test (3.12) in 1h15m0s (ID 130122872519)
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
✓ full / ace-page-group-isolation in 1m38s (ID 130122872542)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  ✓ Run ACE shared-page isolation lane
  ✓ Post Install visual dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ full / perf-floors in 9m21s (ID 130122872543)
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
✓ full / test (3.14) in 43m36s (ID 130122872544)
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
✓ full / tutorial-tests in 1m1s (ID 130122872691)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run tutorial tests
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

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0rITzagAAAACbilJCp1gURZWQuZlQNOw0UEhMMzBFREdFMDExMABFZGdl
full / build-core / build-core: .github#7

! Failed to restore: Cache service responded with 400
full / build-core / build-core: .github#25

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
full / build-core / build-core: .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* master CI Telemetry · 42897324688
Triggered via workflow_dispatch about 1 hour ago

JOBS
* build-core / build-core (ID 130163626240)
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
Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* master CI Telemetry · 42897324688
Triggered via workflow_dispatch about 1 hour ago

JOBS
* build-core / build-core (ID 130163626240)
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
Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* master CI Telemetry · 42897324688
Triggered via workflow_dispatch about 1 hour ago

JOBS
* build-core / build-core (ID 130163626240)
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
Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* master CI Telemetry · 42897324688
Triggered via workflow_dispatch about 1 hour ago

JOBS
* build-core / build-core (ID 130163626240)
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
Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* master CI Telemetry · 42897324688
Triggered via workflow_dispatch about 1 hour ago

JOBS
* build-core / build-core (ID 130163626240)
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
Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* master CI Telemetry · 42897324688
Triggered via workflow_dispatch about 1 hour ago

JOBS
* build-core / build-core (ID 130163626240)
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
Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* master CI Telemetry · 42897324688
Triggered via workflow_dispatch about 1 hour ago

JOBS
* build-core / build-core (ID 130163626240)
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
  * Build macro LSP
  * Record wheel provenance
  * Record published tag provenance
  * Upload Rust core artifacts
  * Post Cache Rust build
  * Post Run astral-sh/setup-uv@v4
  * Post Check out Rust core
  * Post Run actions/checkout@v4
Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* master CI Telemetry · 42897324688
Triggered via workflow_dispatch about 1 hour ago

JOBS
✓ build-core / build-core in 17m0s (ID 130163626240)
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
* coverage-contexts (ID 130172846731)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Record per-test coverage contexts
  * Upload coverage contexts database
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test-cost (ID 130172846806)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run cost-attribution suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* contention-test (ID 130172847126)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  * Run default-lane contention harness
  * Upload contention failure records
  * Post Install visual dependencies
  * Post Run actions/checkout@v4

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
build-core / build-core: .github#4

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0wZnzagAAAAAQibZjKxiXRbBwadvAiZWKUEhMMzBFREdFMDQxMwBFZGdl
build-core / build-core: .github#7

! Failed to restore: Cache service responded with 400
build-core / build-core: .github#25

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
build-core / build-core: .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* master CI Telemetry · 42897324688
Triggered via workflow_dispatch about 1 hour ago

JOBS
✓ build-core / build-core in 17m0s (ID 130163626240)
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
* coverage-contexts (ID 130172846731)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Record per-test coverage contexts
  * Upload coverage contexts database
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test-cost (ID 130172846806)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run cost-attribution suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* contention-test (ID 130172847126)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  * Run default-lane contention harness
  * Upload contention failure records
  * Post Install visual dependencies
  * Post Run actions/checkout@v4

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
build-core / build-core: .github#4

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0wZnzagAAAAAQibZjKxiXRbBwadvAiZWKUEhMMzBFREdFMDQxMwBFZGdl
build-core / build-core: .github#7

! Failed to restore: Cache service responded with 400
build-core / build-core: .github#25

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
build-core / build-core: .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* master CI Telemetry · 42897324688
Triggered via workflow_dispatch about 1 hour ago

JOBS
✓ build-core / build-core in 17m0s (ID 130163626240)
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
* coverage-contexts (ID 130172846731)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Record per-test coverage contexts
  * Upload coverage contexts database
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test-cost (ID 130172846806)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run cost-attribution suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* contention-test (ID 130172847126)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  * Run default-lane contention harness
  * Upload contention failure records
  * Post Install visual dependencies
  * Post Run actions/checkout@v4

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
build-core / build-core: .github#4

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0wZnzagAAAAAQibZjKxiXRbBwadvAiZWKUEhMMzBFREdFMDQxMwBFZGdl
build-core / build-core: .github#7

! Failed to restore: Cache service responded with 400
build-core / build-core: .github#25

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
build-core / build-core: .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* master CI Telemetry · 42897324688
Triggered via workflow_dispatch about 1 hour ago

JOBS
✓ build-core / build-core in 17m0s (ID 130163626240)
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
* coverage-contexts (ID 130172846731)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Record per-test coverage contexts
  * Upload coverage contexts database
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test-cost (ID 130172846806)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run cost-attribution suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* contention-test (ID 130172847126)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  * Run default-lane contention harness
  * Upload contention failure records
  * Post Install visual dependencies
  * Post Run actions/checkout@v4

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
build-core / build-core: .github#4

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0wZnzagAAAAAQibZjKxiXRbBwadvAiZWKUEhMMzBFREdFMDQxMwBFZGdl
build-core / build-core: .github#7

! Failed to restore: Cache service responded with 400
build-core / build-core: .github#25

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
build-core / build-core: .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* master CI Telemetry · 42897324688
Triggered via workflow_dispatch about 1 hour ago

JOBS
✓ build-core / build-core in 17m0s (ID 130163626240)
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
* coverage-contexts (ID 130172846731)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Record per-test coverage contexts
  * Upload coverage contexts database
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test-cost (ID 130172846806)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run cost-attribution suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* contention-test (ID 130172847126)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  * Run default-lane contention harness
  * Upload contention failure records
  * Post Install visual dependencies
  * Post Run actions/checkout@v4

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
build-core / build-core: .github#4

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0wZnzagAAAAAQibZjKxiXRbBwadvAiZWKUEhMMzBFREdFMDQxMwBFZGdl
build-core / build-core: .github#7

! Failed to restore: Cache service responded with 400
build-core / build-core: .github#25

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
build-core / build-core: .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* master CI Telemetry · 42897324688
Triggered via workflow_dispatch about 1 hour ago

JOBS
✓ build-core / build-core in 17m0s (ID 130163626240)
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
* coverage-contexts (ID 130172846731)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Record per-test coverage contexts
  * Upload coverage contexts database
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test-cost (ID 130172846806)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run cost-attribution suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* contention-test (ID 130172847126)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  * Run default-lane contention harness
  * Upload contention failure records
  * Post Install visual dependencies
  * Post Run actions/checkout@v4

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
build-core / build-core: .github#4

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0wZnzagAAAAAQibZjKxiXRbBwadvAiZWKUEhMMzBFREdFMDQxMwBFZGdl
build-core / build-core: .github#7

! Failed to restore: Cache service responded with 400
build-core / build-core: .github#25

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
build-core / build-core: .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* master CI Telemetry · 42897324688
Triggered via workflow_dispatch about 1 hour ago

JOBS
✓ build-core / build-core in 17m0s (ID 130163626240)
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
* coverage-contexts (ID 130172846731)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Record per-test coverage contexts
  * Upload coverage contexts database
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test-cost (ID 130172846806)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run cost-attribution suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* contention-test (ID 130172847126)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  * Run default-lane contention harness
  * Upload contention failure records
  * Post Install visual dependencies
  * Post Run actions/checkout@v4

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
build-core / build-core: .github#4

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0wZnzagAAAAAQibZjKxiXRbBwadvAiZWKUEhMMzBFREdFMDQxMwBFZGdl
build-core / build-core: .github#7

! Failed to restore: Cache service responded with 400
build-core / build-core: .github#25

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
build-core / build-core: .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* master CI Telemetry · 42897324688
Triggered via workflow_dispatch about 2 hours ago

JOBS
✓ build-core / build-core in 17m0s (ID 130163626240)
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
* coverage-contexts (ID 130172846731)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Record per-test coverage contexts
  * Upload coverage contexts database
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test-cost (ID 130172846806)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run cost-attribution suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* contention-test (ID 130172847126)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  * Run default-lane contention harness
  * Upload contention failure records
  * Post Install visual dependencies
  * Post Run actions/checkout@v4

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
build-core / build-core: .github#4

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0wZnzagAAAAAQibZjKxiXRbBwadvAiZWKUEhMMzBFREdFMDQxMwBFZGdl
build-core / build-core: .github#7

! Failed to restore: Cache service responded with 400
build-core / build-core: .github#25

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
build-core / build-core: .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* master CI Telemetry · 42897324688
Triggered via workflow_dispatch about 2 hours ago

JOBS
✓ build-core / build-core in 17m0s (ID 130163626240)
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
* coverage-contexts (ID 130172846731)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Record per-test coverage contexts
  * Upload coverage contexts database
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test-cost (ID 130172846806)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run cost-attribution suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* contention-test (ID 130172847126)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  * Run default-lane contention harness
  * Upload contention failure records
  * Post Install visual dependencies
  * Post Run actions/checkout@v4

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
build-core / build-core: .github#4

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0wZnzagAAAAAQibZjKxiXRbBwadvAiZWKUEhMMzBFREdFMDQxMwBFZGdl
build-core / build-core: .github#7

! Failed to restore: Cache service responded with 400
build-core / build-core: .github#25

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
build-core / build-core: .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* master CI Telemetry · 42897324688
Triggered via workflow_dispatch about 2 hours ago

JOBS
✓ build-core / build-core in 17m0s (ID 130163626240)
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
* coverage-contexts (ID 130172846731)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Record per-test coverage contexts
  * Upload coverage contexts database
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test-cost (ID 130172846806)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run cost-attribution suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* contention-test (ID 130172847126)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  * Run default-lane contention harness
  * Upload contention failure records
  * Post Install visual dependencies
  * Post Run actions/checkout@v4

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
build-core / build-core: .github#4

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0wZnzagAAAAAQibZjKxiXRbBwadvAiZWKUEhMMzBFREdFMDQxMwBFZGdl
build-core / build-core: .github#7

! Failed to restore: Cache service responded with 400
build-core / build-core: .github#25

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
build-core / build-core: .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* master CI Telemetry · 42897324688
Triggered via workflow_dispatch about 2 hours ago

JOBS
✓ build-core / build-core in 17m0s (ID 130163626240)
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
* coverage-contexts (ID 130172846731)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Record per-test coverage contexts
  * Upload coverage contexts database
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test-cost (ID 130172846806)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run cost-attribution suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* contention-test (ID 130172847126)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  * Run default-lane contention harness
  * Upload contention failure records
  * Post Install visual dependencies
  * Post Run actions/checkout@v4

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
build-core / build-core: .github#4

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0wZnzagAAAAAQibZjKxiXRbBwadvAiZWKUEhMMzBFREdFMDQxMwBFZGdl
build-core / build-core: .github#7

! Failed to restore: Cache service responded with 400
build-core / build-core: .github#25

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
build-core / build-core: .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* master CI Telemetry · 42897324688
Triggered via workflow_dispatch about 2 hours ago

JOBS
✓ build-core / build-core in 17m0s (ID 130163626240)
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
* coverage-contexts (ID 130172846731)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Record per-test coverage contexts
  * Upload coverage contexts database
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test-cost (ID 130172846806)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run cost-attribution suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* contention-test (ID 130172847126)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  * Run default-lane contention harness
  * Upload contention failure records
  * Post Install visual dependencies
  * Post Run actions/checkout@v4

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
build-core / build-core: .github#4

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0wZnzagAAAAAQibZjKxiXRbBwadvAiZWKUEhMMzBFREdFMDQxMwBFZGdl
build-core / build-core: .github#7

! Failed to restore: Cache service responded with 400
build-core / build-core: .github#25

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
build-core / build-core: .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* master CI Telemetry · 42897324688
Triggered via workflow_dispatch about 2 hours ago

JOBS
✓ build-core / build-core in 17m0s (ID 130163626240)
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
* coverage-contexts (ID 130172846731)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Record per-test coverage contexts
  * Upload coverage contexts database
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test-cost (ID 130172846806)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run cost-attribution suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* contention-test (ID 130172847126)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  * Run default-lane contention harness
  * Upload contention failure records
  * Post Install visual dependencies
  * Post Run actions/checkout@v4

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
build-core / build-core: .github#4

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0wZnzagAAAAAQibZjKxiXRbBwadvAiZWKUEhMMzBFREdFMDQxMwBFZGdl
build-core / build-core: .github#7

! Failed to restore: Cache service responded with 400
build-core / build-core: .github#25

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
build-core / build-core: .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* master CI Telemetry · 42897324688
Triggered via workflow_dispatch about 2 hours ago

JOBS
✓ build-core / build-core in 17m0s (ID 130163626240)
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
* coverage-contexts (ID 130172846731)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Record per-test coverage contexts
  * Upload coverage contexts database
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test-cost (ID 130172846806)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run cost-attribution suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* contention-test (ID 130172847126)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  * Run default-lane contention harness
  * Upload contention failure records
  * Post Install visual dependencies
  * Post Run actions/checkout@v4

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
build-core / build-core: .github#4

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0wZnzagAAAAAQibZjKxiXRbBwadvAiZWKUEhMMzBFREdFMDQxMwBFZGdl
build-core / build-core: .github#7

! Failed to restore: Cache service responded with 400
build-core / build-core: .github#25

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
build-core / build-core: .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* master CI Telemetry · 42897324688
Triggered via workflow_dispatch about 2 hours ago

JOBS
✓ build-core / build-core in 17m0s (ID 130163626240)
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
* coverage-contexts (ID 130172846731)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Record per-test coverage contexts
  * Upload coverage contexts database
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test-cost (ID 130172846806)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run cost-attribution suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* contention-test (ID 130172847126)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  * Run default-lane contention harness
  * Upload contention failure records
  * Post Install visual dependencies
  * Post Run actions/checkout@v4

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
build-core / build-core: .github#4

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0wZnzagAAAAAQibZjKxiXRbBwadvAiZWKUEhMMzBFREdFMDQxMwBFZGdl
build-core / build-core: .github#7

! Failed to restore: Cache service responded with 400
build-core / build-core: .github#25

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
build-core / build-core: .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* master CI Telemetry · 42897324688
Triggered via workflow_dispatch about 2 hours ago

JOBS
✓ build-core / build-core in 17m0s (ID 130163626240)
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
* coverage-contexts (ID 130172846731)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Record per-test coverage contexts
  * Upload coverage contexts database
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test-cost (ID 130172846806)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run cost-attribution suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* contention-test (ID 130172847126)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  * Run default-lane contention harness
  * Upload contention failure records
  * Post Install visual dependencies
  * Post Run actions/checkout@v4

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
build-core / build-core: .github#4

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0wZnzagAAAAAQibZjKxiXRbBwadvAiZWKUEhMMzBFREdFMDQxMwBFZGdl
build-core / build-core: .github#7

! Failed to restore: Cache service responded with 400
build-core / build-core: .github#25

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
build-core / build-core: .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* master CI Telemetry · 42897324688
Triggered via workflow_dispatch about 2 hours ago

JOBS
✓ build-core / build-core in 17m0s (ID 130163626240)
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
* coverage-contexts (ID 130172846731)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Record per-test coverage contexts
  * Upload coverage contexts database
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test-cost (ID 130172846806)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run cost-attribution suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* contention-test (ID 130172847126)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  * Run default-lane contention harness
  * Upload contention failure records
  * Post Install visual dependencies
  * Post Run actions/checkout@v4

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
build-core / build-core: .github#4

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0wZnzagAAAAAQibZjKxiXRbBwadvAiZWKUEhMMzBFREdFMDQxMwBFZGdl
build-core / build-core: .github#7

! Failed to restore: Cache service responded with 400
build-core / build-core: .github#25

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
build-core / build-core: .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* master CI Telemetry · 42897324688
Triggered via workflow_dispatch about 2 hours ago

JOBS
✓ build-core / build-core in 17m0s (ID 130163626240)
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
* coverage-contexts (ID 130172846731)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Record per-test coverage contexts
  * Upload coverage contexts database
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test-cost (ID 130172846806)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run cost-attribution suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* contention-test (ID 130172847126)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  * Run default-lane contention harness
  * Upload contention failure records
  * Post Install visual dependencies
  * Post Run actions/checkout@v4

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
build-core / build-core: .github#4

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0wZnzagAAAAAQibZjKxiXRbBwadvAiZWKUEhMMzBFREdFMDQxMwBFZGdl
build-core / build-core: .github#7

! Failed to restore: Cache service responded with 400
build-core / build-core: .github#25

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
build-core / build-core: .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* master CI Telemetry · 42897324688
Triggered via workflow_dispatch about 2 hours ago

JOBS
✓ build-core / build-core in 17m0s (ID 130163626240)
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
* coverage-contexts (ID 130172846731)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Record per-test coverage contexts
  * Upload coverage contexts database
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test-cost (ID 130172846806)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run cost-attribution suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* contention-test (ID 130172847126)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  * Run default-lane contention harness
  * Upload contention failure records
  * Post Install visual dependencies
  * Post Run actions/checkout@v4

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
build-core / build-core: .github#4

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0wZnzagAAAAAQibZjKxiXRbBwadvAiZWKUEhMMzBFREdFMDQxMwBFZGdl
build-core / build-core: .github#7

! Failed to restore: Cache service responded with 400
build-core / build-core: .github#25

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
build-core / build-core: .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* master CI Telemetry · 42897324688
Triggered via workflow_dispatch about 2 hours ago

JOBS
✓ build-core / build-core in 17m0s (ID 130163626240)
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
* coverage-contexts (ID 130172846731)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Record per-test coverage contexts
  * Upload coverage contexts database
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test-cost (ID 130172846806)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run cost-attribution suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* contention-test (ID 130172847126)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  * Run default-lane contention harness
  * Upload contention failure records
  * Post Install visual dependencies
  * Post Run actions/checkout@v4

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
build-core / build-core: .github#4

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0wZnzagAAAAAQibZjKxiXRbBwadvAiZWKUEhMMzBFREdFMDQxMwBFZGdl
build-core / build-core: .github#7

! Failed to restore: Cache service responded with 400
build-core / build-core: .github#25

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
build-core / build-core: .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* master CI Telemetry · 42897324688
Triggered via workflow_dispatch about 2 hours ago

JOBS
✓ build-core / build-core in 17m0s (ID 130163626240)
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
* coverage-contexts (ID 130172846731)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Record per-test coverage contexts
  * Upload coverage contexts database
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test-cost (ID 130172846806)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run cost-attribution suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* contention-test (ID 130172847126)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  * Run default-lane contention harness
  * Upload contention failure records
  * Post Install visual dependencies
  * Post Run actions/checkout@v4

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
build-core / build-core: .github#4

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0wZnzagAAAAAQibZjKxiXRbBwadvAiZWKUEhMMzBFREdFMDQxMwBFZGdl
build-core / build-core: .github#7

! Failed to restore: Cache service responded with 400
build-core / build-core: .github#25

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
build-core / build-core: .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* master CI Telemetry · 42897324688
Triggered via workflow_dispatch about 2 hours ago

JOBS
✓ build-core / build-core in 17m0s (ID 130163626240)
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
* coverage-contexts (ID 130172846731)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Record per-test coverage contexts
  * Upload coverage contexts database
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test-cost (ID 130172846806)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run cost-attribution suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* contention-test (ID 130172847126)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  * Run default-lane contention harness
  * Upload contention failure records
  * Post Install visual dependencies
  * Post Run actions/checkout@v4

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
build-core / build-core: .github#4

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0wZnzagAAAAAQibZjKxiXRbBwadvAiZWKUEhMMzBFREdFMDQxMwBFZGdl
build-core / build-core: .github#7

! Failed to restore: Cache service responded with 400
build-core / build-core: .github#25

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
build-core / build-core: .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* master CI Telemetry · 42897324688
Triggered via workflow_dispatch about 2 hours ago

JOBS
✓ build-core / build-core in 17m0s (ID 130163626240)
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
* coverage-contexts (ID 130172846731)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Record per-test coverage contexts
  * Upload coverage contexts database
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test-cost (ID 130172846806)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run cost-attribution suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* contention-test (ID 130172847126)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  * Run default-lane contention harness
  * Upload contention failure records
  * Post Install visual dependencies
  * Post Run actions/checkout@v4

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
build-core / build-core: .github#4

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0wZnzagAAAAAQibZjKxiXRbBwadvAiZWKUEhMMzBFREdFMDQxMwBFZGdl
build-core / build-core: .github#7

! Failed to restore: Cache service responded with 400
build-core / build-core: .github#25

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
build-core / build-core: .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* master CI Telemetry · 42897324688
Triggered via workflow_dispatch about 2 hours ago

JOBS
✓ build-core / build-core in 17m0s (ID 130163626240)
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
* coverage-contexts (ID 130172846731)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Record per-test coverage contexts
  * Upload coverage contexts database
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test-cost (ID 130172846806)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run cost-attribution suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* contention-test (ID 130172847126)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  * Run default-lane contention harness
  * Upload contention failure records
  * Post Install visual dependencies
  * Post Run actions/checkout@v4

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
build-core / build-core: .github#4

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0wZnzagAAAAAQibZjKxiXRbBwadvAiZWKUEhMMzBFREdFMDQxMwBFZGdl
build-core / build-core: .github#7

! Failed to restore: Cache service responded with 400
build-core / build-core: .github#25

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
build-core / build-core: .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* master CI Telemetry · 42897324688
Triggered via workflow_dispatch about 2 hours ago

JOBS
✓ build-core / build-core in 17m0s (ID 130163626240)
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
* coverage-contexts (ID 130172846731)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Record per-test coverage contexts
  * Upload coverage contexts database
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test-cost (ID 130172846806)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run cost-attribution suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* contention-test (ID 130172847126)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  * Run default-lane contention harness
  * Upload contention failure records
  * Post Install visual dependencies
  * Post Run actions/checkout@v4

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
build-core / build-core: .github#4

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0wZnzagAAAAAQibZjKxiXRbBwadvAiZWKUEhMMzBFREdFMDQxMwBFZGdl
build-core / build-core: .github#7

! Failed to restore: Cache service responded with 400
build-core / build-core: .github#25

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
build-core / build-core: .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* master CI Telemetry · 42897324688
Triggered via workflow_dispatch about 2 hours ago

JOBS
✓ build-core / build-core in 17m0s (ID 130163626240)
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
* coverage-contexts (ID 130172846731)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Record per-test coverage contexts
  * Upload coverage contexts database
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test-cost (ID 130172846806)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run cost-attribution suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* contention-test (ID 130172847126)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  * Run default-lane contention harness
  * Upload contention failure records
  * Post Install visual dependencies
  * Post Run actions/checkout@v4

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
build-core / build-core: .github#4

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0wZnzagAAAAAQibZjKxiXRbBwadvAiZWKUEhMMzBFREdFMDQxMwBFZGdl
build-core / build-core: .github#7

! Failed to restore: Cache service responded with 400
build-core / build-core: .github#25

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
build-core / build-core: .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* master CI Telemetry · 42897324688
Triggered via workflow_dispatch about 2 hours ago

JOBS
✓ build-core / build-core in 17m0s (ID 130163626240)
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
* coverage-contexts (ID 130172846731)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Record per-test coverage contexts
  * Upload coverage contexts database
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test-cost (ID 130172846806)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run cost-attribution suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* contention-test (ID 130172847126)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  * Run default-lane contention harness
  * Upload contention failure records
  * Post Install visual dependencies
  * Post Run actions/checkout@v4

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
build-core / build-core: .github#4

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0wZnzagAAAAAQibZjKxiXRbBwadvAiZWKUEhMMzBFREdFMDQxMwBFZGdl
build-core / build-core: .github#7

! Failed to restore: Cache service responded with 400
build-core / build-core: .github#25

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
build-core / build-core: .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* master CI Telemetry · 42897324688
Triggered via workflow_dispatch about 2 hours ago

JOBS
✓ build-core / build-core in 17m0s (ID 130163626240)
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
* coverage-contexts (ID 130172846731)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Record per-test coverage contexts
  * Upload coverage contexts database
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test-cost (ID 130172846806)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run cost-attribution suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* contention-test (ID 130172847126)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  * Run default-lane contention harness
  * Upload contention failure records
  * Post Install visual dependencies
  * Post Run actions/checkout@v4

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
build-core / build-core: .github#4

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0wZnzagAAAAAQibZjKxiXRbBwadvAiZWKUEhMMzBFREdFMDQxMwBFZGdl
build-core / build-core: .github#7

! Failed to restore: Cache service responded with 400
build-core / build-core: .github#25

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
build-core / build-core: .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* master CI Telemetry · 42897324688
Triggered via workflow_dispatch about 2 hours ago

JOBS
✓ build-core / build-core in 17m0s (ID 130163626240)
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
* coverage-contexts (ID 130172846731)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Record per-test coverage contexts
  * Upload coverage contexts database
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test-cost (ID 130172846806)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run cost-attribution suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* contention-test (ID 130172847126)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  * Run default-lane contention harness
  * Upload contention failure records
  * Post Install visual dependencies
  * Post Run actions/checkout@v4

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
build-core / build-core: .github#4

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0wZnzagAAAAAQibZjKxiXRbBwadvAiZWKUEhMMzBFREdFMDQxMwBFZGdl
build-core / build-core: .github#7

! Failed to restore: Cache service responded with 400
build-core / build-core: .github#25

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
build-core / build-core: .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* master CI Telemetry · 42897324688
Triggered via workflow_dispatch about 2 hours ago

JOBS
✓ build-core / build-core in 17m0s (ID 130163626240)
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
* coverage-contexts (ID 130172846731)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Record per-test coverage contexts
  * Upload coverage contexts database
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test-cost (ID 130172846806)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run cost-attribution suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* contention-test (ID 130172847126)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  * Run default-lane contention harness
  * Upload contention failure records
  * Post Install visual dependencies
  * Post Run actions/checkout@v4

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
build-core / build-core: .github#4

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0wZnzagAAAAAQibZjKxiXRbBwadvAiZWKUEhMMzBFREdFMDQxMwBFZGdl
build-core / build-core: .github#7

! Failed to restore: Cache service responded with 400
build-core / build-core: .github#25

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
build-core / build-core: .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* master CI Telemetry · 42897324688
Triggered via workflow_dispatch about 2 hours ago

JOBS
✓ build-core / build-core in 17m0s (ID 130163626240)
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
* coverage-contexts (ID 130172846731)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Record per-test coverage contexts
  * Upload coverage contexts database
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test-cost (ID 130172846806)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run cost-attribution suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* contention-test (ID 130172847126)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  * Run default-lane contention harness
  * Upload contention failure records
  * Post Install visual dependencies
  * Post Run actions/checkout@v4

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
build-core / build-core: .github#4

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0wZnzagAAAAAQibZjKxiXRbBwadvAiZWKUEhMMzBFREdFMDQxMwBFZGdl
build-core / build-core: .github#7

! Failed to restore: Cache service responded with 400
build-core / build-core: .github#25

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
build-core / build-core: .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* master CI Telemetry · 42897324688
Triggered via workflow_dispatch about 2 hours ago

JOBS
✓ build-core / build-core in 17m0s (ID 130163626240)
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
* coverage-contexts (ID 130172846731)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Record per-test coverage contexts
  * Upload coverage contexts database
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test-cost (ID 130172846806)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run cost-attribution suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* contention-test (ID 130172847126)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  * Run default-lane contention harness
  * Upload contention failure records
  * Post Install visual dependencies
  * Post Run actions/checkout@v4

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
build-core / build-core: .github#4

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0wZnzagAAAAAQibZjKxiXRbBwadvAiZWKUEhMMzBFREdFMDQxMwBFZGdl
build-core / build-core: .github#7

! Failed to restore: Cache service responded with 400
build-core / build-core: .github#25

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
build-core / build-core: .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* master CI Telemetry · 42897324688
Triggered via workflow_dispatch about 2 hours ago

JOBS
✓ build-core / build-core in 17m0s (ID 130163626240)
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
* coverage-contexts (ID 130172846731)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Record per-test coverage contexts
  * Upload coverage contexts database
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test-cost (ID 130172846806)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run cost-attribution suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* contention-test (ID 130172847126)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  * Run default-lane contention harness
  * Upload contention failure records
  * Post Install visual dependencies
  * Post Run actions/checkout@v4

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
build-core / build-core: .github#4

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0wZnzagAAAAAQibZjKxiXRbBwadvAiZWKUEhMMzBFREdFMDQxMwBFZGdl
build-core / build-core: .github#7

! Failed to restore: Cache service responded with 400
build-core / build-core: .github#25

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
build-core / build-core: .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* master CI Telemetry · 42897324688
Triggered via workflow_dispatch about 2 hours ago

JOBS
✓ build-core / build-core in 17m0s (ID 130163626240)
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
* coverage-contexts (ID 130172846731)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Record per-test coverage contexts
  * Upload coverage contexts database
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test-cost (ID 130172846806)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run cost-attribution suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* contention-test (ID 130172847126)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  * Run default-lane contention harness
  * Upload contention failure records
  * Post Install visual dependencies
  * Post Run actions/checkout@v4

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
build-core / build-core: .github#4

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0wZnzagAAAAAQibZjKxiXRbBwadvAiZWKUEhMMzBFREdFMDQxMwBFZGdl
build-core / build-core: .github#7

! Failed to restore: Cache service responded with 400
build-core / build-core: .github#25

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
build-core / build-core: .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* master CI Telemetry · 42897324688
Triggered via workflow_dispatch about 2 hours ago

JOBS
✓ build-core / build-core in 17m0s (ID 130163626240)
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
* coverage-contexts (ID 130172846731)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Record per-test coverage contexts
  * Upload coverage contexts database
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test-cost (ID 130172846806)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run cost-attribution suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* contention-test (ID 130172847126)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  * Run default-lane contention harness
  * Upload contention failure records
  * Post Install visual dependencies
  * Post Run actions/checkout@v4

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
build-core / build-core: .github#4

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0wZnzagAAAAAQibZjKxiXRbBwadvAiZWKUEhMMzBFREdFMDQxMwBFZGdl
build-core / build-core: .github#7

! Failed to restore: Cache service responded with 400
build-core / build-core: .github#25

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
build-core / build-core: .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* master CI Telemetry · 42897324688
Triggered via workflow_dispatch about 2 hours ago

JOBS
✓ build-core / build-core in 17m0s (ID 130163626240)
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
* coverage-contexts (ID 130172846731)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Record per-test coverage contexts
  * Upload coverage contexts database
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test-cost (ID 130172846806)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run cost-attribution suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* contention-test (ID 130172847126)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  * Run default-lane contention harness
  * Upload contention failure records
  * Post Install visual dependencies
  * Post Run actions/checkout@v4

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
build-core / build-core: .github#4

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0wZnzagAAAAAQibZjKxiXRbBwadvAiZWKUEhMMzBFREdFMDQxMwBFZGdl
build-core / build-core: .github#7

! Failed to restore: Cache service responded with 400
build-core / build-core: .github#25

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
build-core / build-core: .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* master CI Telemetry · 42897324688
Triggered via workflow_dispatch about 3 hours ago

JOBS
✓ build-core / build-core in 17m0s (ID 130163626240)
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
* coverage-contexts (ID 130172846731)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Record per-test coverage contexts
  * Upload coverage contexts database
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test-cost (ID 130172846806)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run cost-attribution suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* contention-test (ID 130172847126)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  * Run default-lane contention harness
  * Upload contention failure records
  * Post Install visual dependencies
  * Post Run actions/checkout@v4

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
build-core / build-core: .github#4

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0wZnzagAAAAAQibZjKxiXRbBwadvAiZWKUEhMMzBFREdFMDQxMwBFZGdl
build-core / build-core: .github#7

! Failed to restore: Cache service responded with 400
build-core / build-core: .github#25

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
build-core / build-core: .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* master CI Telemetry · 42897324688
Triggered via workflow_dispatch about 3 hours ago

JOBS
✓ build-core / build-core in 17m0s (ID 130163626240)
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
* coverage-contexts (ID 130172846731)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Record per-test coverage contexts
  * Upload coverage contexts database
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test-cost (ID 130172846806)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run cost-attribution suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* contention-test (ID 130172847126)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  * Run default-lane contention harness
  * Upload contention failure records
  * Post Install visual dependencies
  * Post Run actions/checkout@v4

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
build-core / build-core: .github#4

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0wZnzagAAAAAQibZjKxiXRbBwadvAiZWKUEhMMzBFREdFMDQxMwBFZGdl
build-core / build-core: .github#7

! Failed to restore: Cache service responded with 400
build-core / build-core: .github#25

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
build-core / build-core: .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* master CI Telemetry · 42897324688
Triggered via workflow_dispatch about 3 hours ago

JOBS
✓ build-core / build-core in 17m0s (ID 130163626240)
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
* coverage-contexts (ID 130172846731)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Record per-test coverage contexts
  * Upload coverage contexts database
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test-cost (ID 130172846806)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run cost-attribution suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* contention-test (ID 130172847126)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  * Run default-lane contention harness
  * Upload contention failure records
  * Post Install visual dependencies
  * Post Run actions/checkout@v4

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
build-core / build-core: .github#4

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0wZnzagAAAAAQibZjKxiXRbBwadvAiZWKUEhMMzBFREdFMDQxMwBFZGdl
build-core / build-core: .github#7

! Failed to restore: Cache service responded with 400
build-core / build-core: .github#25

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
build-core / build-core: .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* master CI Telemetry · 42897324688
Triggered via workflow_dispatch about 3 hours ago

JOBS
✓ build-core / build-core in 17m0s (ID 130163626240)
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
* coverage-contexts (ID 130172846731)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Record per-test coverage contexts
  * Upload coverage contexts database
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test-cost (ID 130172846806)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run cost-attribution suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* contention-test (ID 130172847126)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  * Run default-lane contention harness
  * Upload contention failure records
  * Post Install visual dependencies
  * Post Run actions/checkout@v4

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
build-core / build-core: .github#4

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0wZnzagAAAAAQibZjKxiXRbBwadvAiZWKUEhMMzBFREdFMDQxMwBFZGdl
build-core / build-core: .github#7

! Failed to restore: Cache service responded with 400
build-core / build-core: .github#25

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
build-core / build-core: .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* master CI Telemetry · 42897324688
Triggered via workflow_dispatch about 3 hours ago

JOBS
✓ build-core / build-core in 17m0s (ID 130163626240)
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
* coverage-contexts (ID 130172846731)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Record per-test coverage contexts
  * Upload coverage contexts database
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test-cost (ID 130172846806)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run cost-attribution suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* contention-test (ID 130172847126)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  * Run default-lane contention harness
  * Upload contention failure records
  * Post Install visual dependencies
  * Post Run actions/checkout@v4

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
build-core / build-core: .github#4

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0wZnzagAAAAAQibZjKxiXRbBwadvAiZWKUEhMMzBFREdFMDQxMwBFZGdl
build-core / build-core: .github#7

! Failed to restore: Cache service responded with 400
build-core / build-core: .github#25

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
build-core / build-core: .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* master CI Telemetry · 42897324688
Triggered via workflow_dispatch about 3 hours ago

JOBS
✓ build-core / build-core in 17m0s (ID 130163626240)
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
* coverage-contexts (ID 130172846731)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Record per-test coverage contexts
  * Upload coverage contexts database
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test-cost (ID 130172846806)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run cost-attribution suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* contention-test (ID 130172847126)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  * Run default-lane contention harness
  * Upload contention failure records
  * Post Install visual dependencies
  * Post Run actions/checkout@v4

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
build-core / build-core: .github#4

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0wZnzagAAAAAQibZjKxiXRbBwadvAiZWKUEhMMzBFREdFMDQxMwBFZGdl
build-core / build-core: .github#7

! Failed to restore: Cache service responded with 400
build-core / build-core: .github#25

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
build-core / build-core: .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* master CI Telemetry · 42897324688
Triggered via workflow_dispatch about 3 hours ago

JOBS
✓ build-core / build-core in 17m0s (ID 130163626240)
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
* coverage-contexts (ID 130172846731)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Record per-test coverage contexts
  * Upload coverage contexts database
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test-cost (ID 130172846806)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run cost-attribution suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* contention-test (ID 130172847126)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  * Run default-lane contention harness
  * Upload contention failure records
  * Post Install visual dependencies
  * Post Run actions/checkout@v4

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
build-core / build-core: .github#4

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0wZnzagAAAAAQibZjKxiXRbBwadvAiZWKUEhMMzBFREdFMDQxMwBFZGdl
build-core / build-core: .github#7

! Failed to restore: Cache service responded with 400
build-core / build-core: .github#25

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
build-core / build-core: .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* master CI Telemetry · 42897324688
Triggered via workflow_dispatch about 3 hours ago

JOBS
✓ build-core / build-core in 17m0s (ID 130163626240)
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
* coverage-contexts (ID 130172846731)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Record per-test coverage contexts
  * Upload coverage contexts database
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test-cost (ID 130172846806)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run cost-attribution suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* contention-test (ID 130172847126)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  * Run default-lane contention harness
  * Upload contention failure records
  * Post Install visual dependencies
  * Post Run actions/checkout@v4

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
build-core / build-core: .github#4

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0wZnzagAAAAAQibZjKxiXRbBwadvAiZWKUEhMMzBFREdFMDQxMwBFZGdl
build-core / build-core: .github#7

! Failed to restore: Cache service responded with 400
build-core / build-core: .github#25

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
build-core / build-core: .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* master CI Telemetry · 42897324688
Triggered via workflow_dispatch about 3 hours ago

JOBS
✓ build-core / build-core in 17m0s (ID 130163626240)
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
✓ coverage-contexts in 1h28m50s (ID 130172846731)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Record per-test coverage contexts
  ✓ Upload coverage contexts database
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* test-cost (ID 130172846806)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run cost-attribution suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* contention-test (ID 130172847126)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  * Run default-lane contention harness
  * Upload contention failure records
  * Post Install visual dependencies
  * Post Run actions/checkout@v4

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
build-core / build-core: .github#4

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0wZnzagAAAAAQibZjKxiXRbBwadvAiZWKUEhMMzBFREdFMDQxMwBFZGdl
build-core / build-core: .github#7

! Failed to restore: Cache service responded with 400
build-core / build-core: .github#25

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
build-core / build-core: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
coverage-contexts: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0lq7zagAAAAB7qOIpC039T4tu8IE1NEKdUEhYMzFFREdFMDIwNwBFZGdl
coverage-contexts: .github#9

! No files were found with the provided path: .coverage. No artifacts will be uploaded.
coverage-contexts: .github#16

! Failed to restore: Cache service responded with 400
coverage-contexts: .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
coverage-contexts: .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* master CI Telemetry · 42897324688
Triggered via workflow_dispatch about 3 hours ago

JOBS
✓ build-core / build-core in 17m0s (ID 130163626240)
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
✓ coverage-contexts in 1h28m50s (ID 130172846731)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Record per-test coverage contexts
  ✓ Upload coverage contexts database
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* test-cost (ID 130172846806)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run cost-attribution suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
X contention-test in 1h30m17s (ID 130172847126)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  X Run default-lane contention harness
  ✓ Upload contention failure records
  ✓ Post Install visual dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
build-core / build-core: .github#4

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0wZnzagAAAAAQibZjKxiXRbBwadvAiZWKUEhMMzBFREdFMDQxMwBFZGdl
build-core / build-core: .github#7

! Failed to restore: Cache service responded with 400
build-core / build-core: .github#25

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
build-core / build-core: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
coverage-contexts: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0lq7zagAAAAB7qOIpC039T4tu8IE1NEKdUEhYMzFFREdFMDIwNwBFZGdl
coverage-contexts: .github#9

! No files were found with the provided path: .coverage. No artifacts will be uploaded.
coverage-contexts: .github#16

! Failed to restore: Cache service responded with 400
coverage-contexts: .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
coverage-contexts: .github#1

X The job has exceeded the maximum execution time of 1h30m0s
contention-test: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
contention-test: .github#48

X The operation was canceled.
contention-test: .github#1262

! Failed to restore: Cache service responded with 400
contention-test: .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
contention-test: .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* master CI Telemetry · 42897324688
Triggered via workflow_dispatch about 3 hours ago

JOBS
✓ build-core / build-core in 17m0s (ID 130163626240)
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
✓ coverage-contexts in 1h28m50s (ID 130172846731)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Record per-test coverage contexts
  ✓ Upload coverage contexts database
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* test-cost (ID 130172846806)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run cost-attribution suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
X contention-test in 1h30m17s (ID 130172847126)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  X Run default-lane contention harness
  ✓ Upload contention failure records
  ✓ Post Install visual dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
build-core / build-core: .github#4

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0wZnzagAAAAAQibZjKxiXRbBwadvAiZWKUEhMMzBFREdFMDQxMwBFZGdl
build-core / build-core: .github#7

! Failed to restore: Cache service responded with 400
build-core / build-core: .github#25

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
build-core / build-core: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
coverage-contexts: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0lq7zagAAAAB7qOIpC039T4tu8IE1NEKdUEhYMzFFREdFMDIwNwBFZGdl
coverage-contexts: .github#9

! No files were found with the provided path: .coverage. No artifacts will be uploaded.
coverage-contexts: .github#16

! Failed to restore: Cache service responded with 400
coverage-contexts: .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
coverage-contexts: .github#1

X The job has exceeded the maximum execution time of 1h30m0s
contention-test: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
contention-test: .github#48

X The operation was canceled.
contention-test: .github#1262

! Failed to restore: Cache service responded with 400
contention-test: .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
contention-test: .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* master CI Telemetry · 42897324688
Triggered via workflow_dispatch about 3 hours ago

JOBS
✓ build-core / build-core in 17m0s (ID 130163626240)
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
✓ coverage-contexts in 1h28m50s (ID 130172846731)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Record per-test coverage contexts
  ✓ Upload coverage contexts database
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* test-cost (ID 130172846806)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run cost-attribution suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
X contention-test in 1h30m17s (ID 130172847126)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  X Run default-lane contention harness
  ✓ Upload contention failure records
  ✓ Post Install visual dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
build-core / build-core: .github#4

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0wZnzagAAAAAQibZjKxiXRbBwadvAiZWKUEhMMzBFREdFMDQxMwBFZGdl
build-core / build-core: .github#7

! Failed to restore: Cache service responded with 400
build-core / build-core: .github#25

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
build-core / build-core: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
coverage-contexts: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0lq7zagAAAAB7qOIpC039T4tu8IE1NEKdUEhYMzFFREdFMDIwNwBFZGdl
coverage-contexts: .github#9

! No files were found with the provided path: .coverage. No artifacts will be uploaded.
coverage-contexts: .github#16

! Failed to restore: Cache service responded with 400
coverage-contexts: .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
coverage-contexts: .github#1

X The job has exceeded the maximum execution time of 1h30m0s
contention-test: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
contention-test: .github#48

X The operation was canceled.
contention-test: .github#1262

! Failed to restore: Cache service responded with 400
contention-test: .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
contention-test: .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* master CI Telemetry · 42897324688
Triggered via workflow_dispatch about 3 hours ago

JOBS
✓ build-core / build-core in 17m0s (ID 130163626240)
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
✓ coverage-contexts in 1h28m50s (ID 130172846731)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Record per-test coverage contexts
  ✓ Upload coverage contexts database
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* test-cost (ID 130172846806)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run cost-attribution suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
X contention-test in 1h30m17s (ID 130172847126)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  X Run default-lane contention harness
  ✓ Upload contention failure records
  ✓ Post Install visual dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
build-core / build-core: .github#4

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0wZnzagAAAAAQibZjKxiXRbBwadvAiZWKUEhMMzBFREdFMDQxMwBFZGdl
build-core / build-core: .github#7

! Failed to restore: Cache service responded with 400
build-core / build-core: .github#25

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
build-core / build-core: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
coverage-contexts: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0lq7zagAAAAB7qOIpC039T4tu8IE1NEKdUEhYMzFFREdFMDIwNwBFZGdl
coverage-contexts: .github#9

! No files were found with the provided path: .coverage. No artifacts will be uploaded.
coverage-contexts: .github#16

! Failed to restore: Cache service responded with 400
coverage-contexts: .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
coverage-contexts: .github#1

X The job has exceeded the maximum execution time of 1h30m0s
contention-test: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
contention-test: .github#48

X The operation was canceled.
contention-test: .github#1262

! Failed to restore: Cache service responded with 400
contention-test: .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
contention-test: .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* master CI Telemetry · 42897324688
Triggered via workflow_dispatch about 3 hours ago

JOBS
✓ build-core / build-core in 17m0s (ID 130163626240)
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
✓ coverage-contexts in 1h28m50s (ID 130172846731)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Record per-test coverage contexts
  ✓ Upload coverage contexts database
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* test-cost (ID 130172846806)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run cost-attribution suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
X contention-test in 1h30m17s (ID 130172847126)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  X Run default-lane contention harness
  ✓ Upload contention failure records
  ✓ Post Install visual dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
build-core / build-core: .github#4

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0wZnzagAAAAAQibZjKxiXRbBwadvAiZWKUEhMMzBFREdFMDQxMwBFZGdl
build-core / build-core: .github#7

! Failed to restore: Cache service responded with 400
build-core / build-core: .github#25

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
build-core / build-core: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
coverage-contexts: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0lq7zagAAAAB7qOIpC039T4tu8IE1NEKdUEhYMzFFREdFMDIwNwBFZGdl
coverage-contexts: .github#9

! No files were found with the provided path: .coverage. No artifacts will be uploaded.
coverage-contexts: .github#16

! Failed to restore: Cache service responded with 400
coverage-contexts: .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
coverage-contexts: .github#1

X The job has exceeded the maximum execution time of 1h30m0s
contention-test: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
contention-test: .github#48

X The operation was canceled.
contention-test: .github#1262

! Failed to restore: Cache service responded with 400
contention-test: .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
contention-test: .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* master CI Telemetry · 42897324688
Triggered via workflow_dispatch about 3 hours ago

JOBS
✓ build-core / build-core in 17m0s (ID 130163626240)
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
✓ coverage-contexts in 1h28m50s (ID 130172846731)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Record per-test coverage contexts
  ✓ Upload coverage contexts database
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* test-cost (ID 130172846806)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run cost-attribution suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
X contention-test in 1h30m17s (ID 130172847126)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  X Run default-lane contention harness
  ✓ Upload contention failure records
  ✓ Post Install visual dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
build-core / build-core: .github#4

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0wZnzagAAAAAQibZjKxiXRbBwadvAiZWKUEhMMzBFREdFMDQxMwBFZGdl
build-core / build-core: .github#7

! Failed to restore: Cache service responded with 400
build-core / build-core: .github#25

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
build-core / build-core: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
coverage-contexts: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0lq7zagAAAAB7qOIpC039T4tu8IE1NEKdUEhYMzFFREdFMDIwNwBFZGdl
coverage-contexts: .github#9

! No files were found with the provided path: .coverage. No artifacts will be uploaded.
coverage-contexts: .github#16

! Failed to restore: Cache service responded with 400
coverage-contexts: .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
coverage-contexts: .github#1

X The job has exceeded the maximum execution time of 1h30m0s
contention-test: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
contention-test: .github#48

X The operation was canceled.
contention-test: .github#1262

! Failed to restore: Cache service responded with 400
contention-test: .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
contention-test: .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* master CI Telemetry · 42897324688
Triggered via workflow_dispatch about 3 hours ago

JOBS
✓ build-core / build-core in 17m0s (ID 130163626240)
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
✓ coverage-contexts in 1h28m50s (ID 130172846731)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Record per-test coverage contexts
  ✓ Upload coverage contexts database
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* test-cost (ID 130172846806)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run cost-attribution suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
X contention-test in 1h30m17s (ID 130172847126)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  X Run default-lane contention harness
  ✓ Upload contention failure records
  ✓ Post Install visual dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
build-core / build-core: .github#4

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0wZnzagAAAAAQibZjKxiXRbBwadvAiZWKUEhMMzBFREdFMDQxMwBFZGdl
build-core / build-core: .github#7

! Failed to restore: Cache service responded with 400
build-core / build-core: .github#25

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
build-core / build-core: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
coverage-contexts: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0lq7zagAAAAB7qOIpC039T4tu8IE1NEKdUEhYMzFFREdFMDIwNwBFZGdl
coverage-contexts: .github#9

! No files were found with the provided path: .coverage. No artifacts will be uploaded.
coverage-contexts: .github#16

! Failed to restore: Cache service responded with 400
coverage-contexts: .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
coverage-contexts: .github#1

X The job has exceeded the maximum execution time of 1h30m0s
contention-test: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
contention-test: .github#48

X The operation was canceled.
contention-test: .github#1262

! Failed to restore: Cache service responded with 400
contention-test: .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
contention-test: .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* master CI Telemetry · 42897324688
Triggered via workflow_dispatch about 3 hours ago

JOBS
✓ build-core / build-core in 17m0s (ID 130163626240)
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
✓ coverage-contexts in 1h28m50s (ID 130172846731)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Record per-test coverage contexts
  ✓ Upload coverage contexts database
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* test-cost (ID 130172846806)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run cost-attribution suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
X contention-test in 1h30m17s (ID 130172847126)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  X Run default-lane contention harness
  ✓ Upload contention failure records
  ✓ Post Install visual dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
build-core / build-core: .github#4

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0wZnzagAAAAAQibZjKxiXRbBwadvAiZWKUEhMMzBFREdFMDQxMwBFZGdl
build-core / build-core: .github#7

! Failed to restore: Cache service responded with 400
build-core / build-core: .github#25

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
build-core / build-core: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
coverage-contexts: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0lq7zagAAAAB7qOIpC039T4tu8IE1NEKdUEhYMzFFREdFMDIwNwBFZGdl
coverage-contexts: .github#9

! No files were found with the provided path: .coverage. No artifacts will be uploaded.
coverage-contexts: .github#16

! Failed to restore: Cache service responded with 400
coverage-contexts: .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
coverage-contexts: .github#1

X The job has exceeded the maximum execution time of 1h30m0s
contention-test: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
contention-test: .github#48

X The operation was canceled.
contention-test: .github#1262

! Failed to restore: Cache service responded with 400
contention-test: .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
contention-test: .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* master CI Telemetry · 42897324688
Triggered via workflow_dispatch about 3 hours ago

JOBS
✓ build-core / build-core in 17m0s (ID 130163626240)
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
✓ coverage-contexts in 1h28m50s (ID 130172846731)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Record per-test coverage contexts
  ✓ Upload coverage contexts database
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* test-cost (ID 130172846806)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run cost-attribution suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
X contention-test in 1h30m17s (ID 130172847126)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  X Run default-lane contention harness
  ✓ Upload contention failure records
  ✓ Post Install visual dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
build-core / build-core: .github#4

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0wZnzagAAAAAQibZjKxiXRbBwadvAiZWKUEhMMzBFREdFMDQxMwBFZGdl
build-core / build-core: .github#7

! Failed to restore: Cache service responded with 400
build-core / build-core: .github#25

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
build-core / build-core: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
coverage-contexts: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0lq7zagAAAAB7qOIpC039T4tu8IE1NEKdUEhYMzFFREdFMDIwNwBFZGdl
coverage-contexts: .github#9

! No files were found with the provided path: .coverage. No artifacts will be uploaded.
coverage-contexts: .github#16

! Failed to restore: Cache service responded with 400
coverage-contexts: .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
coverage-contexts: .github#1

X The job has exceeded the maximum execution time of 1h30m0s
contention-test: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
contention-test: .github#48

X The operation was canceled.
contention-test: .github#1262

! Failed to restore: Cache service responded with 400
contention-test: .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
contention-test: .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* master CI Telemetry · 42897324688
Triggered via workflow_dispatch about 3 hours ago

JOBS
✓ build-core / build-core in 17m0s (ID 130163626240)
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
✓ coverage-contexts in 1h28m50s (ID 130172846731)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Record per-test coverage contexts
  ✓ Upload coverage contexts database
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* test-cost (ID 130172846806)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run cost-attribution suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
X contention-test in 1h30m17s (ID 130172847126)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  X Run default-lane contention harness
  ✓ Upload contention failure records
  ✓ Post Install visual dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
build-core / build-core: .github#4

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0wZnzagAAAAAQibZjKxiXRbBwadvAiZWKUEhMMzBFREdFMDQxMwBFZGdl
build-core / build-core: .github#7

! Failed to restore: Cache service responded with 400
build-core / build-core: .github#25

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
build-core / build-core: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
coverage-contexts: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0lq7zagAAAAB7qOIpC039T4tu8IE1NEKdUEhYMzFFREdFMDIwNwBFZGdl
coverage-contexts: .github#9

! No files were found with the provided path: .coverage. No artifacts will be uploaded.
coverage-contexts: .github#16

! Failed to restore: Cache service responded with 400
coverage-contexts: .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
coverage-contexts: .github#1

X The job has exceeded the maximum execution time of 1h30m0s
contention-test: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
contention-test: .github#48

X The operation was canceled.
contention-test: .github#1262

! Failed to restore: Cache service responded with 400
contention-test: .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
contention-test: .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* master CI Telemetry · 42897324688
Triggered via workflow_dispatch about 3 hours ago

JOBS
✓ build-core / build-core in 17m0s (ID 130163626240)
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
✓ coverage-contexts in 1h28m50s (ID 130172846731)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Record per-test coverage contexts
  ✓ Upload coverage contexts database
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* test-cost (ID 130172846806)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run cost-attribution suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
X contention-test in 1h30m17s (ID 130172847126)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  X Run default-lane contention harness
  ✓ Upload contention failure records
  ✓ Post Install visual dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
build-core / build-core: .github#4

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0wZnzagAAAAAQibZjKxiXRbBwadvAiZWKUEhMMzBFREdFMDQxMwBFZGdl
build-core / build-core: .github#7

! Failed to restore: Cache service responded with 400
build-core / build-core: .github#25

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
build-core / build-core: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
coverage-contexts: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0lq7zagAAAAB7qOIpC039T4tu8IE1NEKdUEhYMzFFREdFMDIwNwBFZGdl
coverage-contexts: .github#9

! No files were found with the provided path: .coverage. No artifacts will be uploaded.
coverage-contexts: .github#16

! Failed to restore: Cache service responded with 400
coverage-contexts: .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
coverage-contexts: .github#1

X The job has exceeded the maximum execution time of 1h30m0s
contention-test: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
contention-test: .github#48

X The operation was canceled.
contention-test: .github#1262

! Failed to restore: Cache service responded with 400
contention-test: .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
contention-test: .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* master CI Telemetry · 42897324688
Triggered via workflow_dispatch about 3 hours ago

JOBS
✓ build-core / build-core in 17m0s (ID 130163626240)
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
✓ coverage-contexts in 1h28m50s (ID 130172846731)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Record per-test coverage contexts
  ✓ Upload coverage contexts database
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* test-cost (ID 130172846806)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run cost-attribution suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
X contention-test in 1h30m17s (ID 130172847126)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  X Run default-lane contention harness
  ✓ Upload contention failure records
  ✓ Post Install visual dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
build-core / build-core: .github#4

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0wZnzagAAAAAQibZjKxiXRbBwadvAiZWKUEhMMzBFREdFMDQxMwBFZGdl
build-core / build-core: .github#7

! Failed to restore: Cache service responded with 400
build-core / build-core: .github#25

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
build-core / build-core: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
coverage-contexts: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0lq7zagAAAAB7qOIpC039T4tu8IE1NEKdUEhYMzFFREdFMDIwNwBFZGdl
coverage-contexts: .github#9

! No files were found with the provided path: .coverage. No artifacts will be uploaded.
coverage-contexts: .github#16

! Failed to restore: Cache service responded with 400
coverage-contexts: .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
coverage-contexts: .github#1

X The job has exceeded the maximum execution time of 1h30m0s
contention-test: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
contention-test: .github#48

X The operation was canceled.
contention-test: .github#1262

! Failed to restore: Cache service responded with 400
contention-test: .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
contention-test: .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* master CI Telemetry · 42897324688
Triggered via workflow_dispatch about 3 hours ago

JOBS
✓ build-core / build-core in 17m0s (ID 130163626240)
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
✓ coverage-contexts in 1h28m50s (ID 130172846731)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Record per-test coverage contexts
  ✓ Upload coverage contexts database
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* test-cost (ID 130172846806)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run cost-attribution suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
X contention-test in 1h30m17s (ID 130172847126)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  X Run default-lane contention harness
  ✓ Upload contention failure records
  ✓ Post Install visual dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
build-core / build-core: .github#4

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0wZnzagAAAAAQibZjKxiXRbBwadvAiZWKUEhMMzBFREdFMDQxMwBFZGdl
build-core / build-core: .github#7

! Failed to restore: Cache service responded with 400
build-core / build-core: .github#25

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
build-core / build-core: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
coverage-contexts: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0lq7zagAAAAB7qOIpC039T4tu8IE1NEKdUEhYMzFFREdFMDIwNwBFZGdl
coverage-contexts: .github#9

! No files were found with the provided path: .coverage. No artifacts will be uploaded.
coverage-contexts: .github#16

! Failed to restore: Cache service responded with 400
coverage-contexts: .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
coverage-contexts: .github#1

X The job has exceeded the maximum execution time of 1h30m0s
contention-test: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
contention-test: .github#48

X The operation was canceled.
contention-test: .github#1262

! Failed to restore: Cache service responded with 400
contention-test: .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
contention-test: .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* master CI Telemetry · 42897324688
Triggered via workflow_dispatch about 3 hours ago

JOBS
✓ build-core / build-core in 17m0s (ID 130163626240)
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
✓ coverage-contexts in 1h28m50s (ID 130172846731)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Record per-test coverage contexts
  ✓ Upload coverage contexts database
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* test-cost (ID 130172846806)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run cost-attribution suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
X contention-test in 1h30m17s (ID 130172847126)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  X Run default-lane contention harness
  ✓ Upload contention failure records
  ✓ Post Install visual dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
build-core / build-core: .github#4

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0wZnzagAAAAAQibZjKxiXRbBwadvAiZWKUEhMMzBFREdFMDQxMwBFZGdl
build-core / build-core: .github#7

! Failed to restore: Cache service responded with 400
build-core / build-core: .github#25

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
build-core / build-core: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
coverage-contexts: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0lq7zagAAAAB7qOIpC039T4tu8IE1NEKdUEhYMzFFREdFMDIwNwBFZGdl
coverage-contexts: .github#9

! No files were found with the provided path: .coverage. No artifacts will be uploaded.
coverage-contexts: .github#16

! Failed to restore: Cache service responded with 400
coverage-contexts: .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
coverage-contexts: .github#1

X The job has exceeded the maximum execution time of 1h30m0s
contention-test: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
contention-test: .github#48

X The operation was canceled.
contention-test: .github#1262

! Failed to restore: Cache service responded with 400
contention-test: .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
contention-test: .github#1

X master CI Telemetry · 42897324688
Triggered via workflow_dispatch about 3 hours ago

JOBS
✓ build-core / build-core in 17m0s (ID 130163626240)
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
✓ coverage-contexts in 1h28m50s (ID 130172846731)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Record per-test coverage contexts
  ✓ Upload coverage contexts database
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
X test-cost in 1h59m16s (ID 130172846806)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  X Run cost-attribution suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
X contention-test in 1h30m17s (ID 130172847126)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  X Run default-lane contention harness
  ✓ Upload contention failure records
  ✓ Post Install visual dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
build-core / build-core: .github#4

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0wZnzagAAAAAQibZjKxiXRbBwadvAiZWKUEhMMzBFREdFMDQxMwBFZGdl
build-core / build-core: .github#7

! Failed to restore: Cache service responded with 400
build-core / build-core: .github#25

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
build-core / build-core: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
coverage-contexts: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0lq7zagAAAAB7qOIpC039T4tu8IE1NEKdUEhYMzFFREdFMDIwNwBFZGdl
coverage-contexts: .github#9

! No files were found with the provided path: .coverage. No artifacts will be uploaded.
coverage-contexts: .github#16

! Failed to restore: Cache service responded with 400
coverage-contexts: .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
coverage-contexts: .github#1

X The job has exceeded the maximum execution time of 1h30m0s
contention-test: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
contention-test: .github#48

X The operation was canceled.
contention-test: .github#1262

! Failed to restore: Cache service responded with 400
contention-test: .github#48

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
contention-test: .github#1


