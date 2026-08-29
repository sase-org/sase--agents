# Chat History - ace-run (sase-um.9.5.4--mon-1)

- **TIMESTAMP:** 2026-08-29 02:17:00 EDT
- **MODEL:** grok/grok-4.6
- **AGENT:** sase-um.9.5.4--mon-1

## Prompt

sase monitor start --command 'GH_FORCE_TTY=0 NO_COLOR=1 CLICOLOR=0 gh run watch 33232978442 --repo sase-org/sase --exit-status' --reason 'Wait for Full CI 33232978442 on 49d6c4188 so ci_watch can leave heavy_workflow_not_green'

## Response

[0;0H[JRefreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Full CI · 33232978442
Triggered via workflow_dispatch about 2 hours ago

JOBS
✓ full / build-core in 8m4s (ID 99052470284)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Resolve pinned Rust core revision
  ✓ Check out Rust core
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up Rust
  ✓ Cache Rust build
  ✓ Build abi3 Rust core wheel
  ✓ Build xprompt LSP
  ✓ Record wheel provenance
  ✓ Upload Rust core artifacts
  ✓ Post Cache Rust build
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Check out Rust core
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
- full / docs-build (ID 99052470671)
- full / release-core-floor-smoke (ID 99052483684)
✓ full / lint in 4m6s (ID 99053300926)
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
✓ full / ace-page-group-isolation in 1m16s (ID 99053300933)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  ✓ Run ACE shared-page isolation lane
  ✓ Post Install visual dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ full / perf-floors in 4m28s (ID 99053300941)
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
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
X full / test (3.12) in 44m7s (ID 99053300955)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  X Run tests (coverage leg)
  - Run tests
  - Run tests
  - Build shard timings table
  - Upload shard timings
  - Upload coverage
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
X full / visual-test in 14m38s (ID 99053300958)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  X Run visual tests
  ✓ Build visual failure report
  ✓ Upload visual failure report
  ✓ Publish visual failure report
  ✓ Upload visual failure artifacts
  ✓ Post Install visual dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ full / coverage-contexts in 44m12s (ID 99053300965)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Record per-test coverage contexts
  ✓ Upload coverage contexts database
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ full / test (3.14) in 27m3s (ID 99053300979)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  - Run tests (coverage leg)
  - Run tests
  ✓ Run tests
  ✓ Build shard timings table
  ✓ Upload shard timings
  - Upload coverage
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* full / test (3.13) (ID 99053301016)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  - Run tests (coverage leg)
  * Run tests
  * Run tests
  * Build shard timings table
  * Upload shard timings
  * Upload coverage
  * Post Install dependencies
  * Post Run actions/checkout@v4
- full / contention-test in 0s (ID 99053301394)
[0;0H[JRefreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Full CI · 33232978442
Triggered via workflow_dispatch about 2 hours ago

JOBS
✓ full / build-core in 8m4s (ID 99052470284)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Resolve pinned Rust core revision
  ✓ Check out Rust core
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up Rust
  ✓ Cache Rust build
  ✓ Build abi3 Rust core wheel
  ✓ Build xprompt LSP
  ✓ Record wheel provenance
  ✓ Upload Rust core artifacts
  ✓ Post Cache Rust build
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Check out Rust core
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
- full / docs-build (ID 99052470671)
- full / release-core-floor-smoke (ID 99052483684)
✓ full / lint in 4m6s (ID 99053300926)
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
✓ full / ace-page-group-isolation in 1m16s (ID 99053300933)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  ✓ Run ACE shared-page isolation lane
  ✓ Post Install visual dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ full / perf-floors in 4m28s (ID 99053300941)
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
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
X full / test (3.12) in 44m7s (ID 99053300955)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  X Run tests (coverage leg)
  - Run tests
  - Run tests
  - Build shard timings table
  - Upload shard timings
  - Upload coverage
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
X full / visual-test in 14m38s (ID 99053300958)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  X Run visual tests
  ✓ Build visual failure report
  ✓ Upload visual failure report
  ✓ Publish visual failure report
  ✓ Upload visual failure artifacts
  ✓ Post Install visual dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ full / coverage-contexts in 44m12s (ID 99053300965)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Record per-test coverage contexts
  ✓ Upload coverage contexts database
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ full / test (3.14) in 27m3s (ID 99053300979)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  - Run tests (coverage leg)
  - Run tests
  ✓ Run tests
  ✓ Build shard timings table
  ✓ Upload shard timings
  - Upload coverage
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* full / test (3.13) (ID 99053301016)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  - Run tests (coverage leg)
  * Run tests
  * Run tests
  * Build shard timings table
  * Upload shard timings
  * Upload coverage
  * Post Install dependencies
  * Post Run actions/checkout@v4
- full / contention-test in 0s (ID 99053301394)
[0;0H[JRefreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Full CI · 33232978442
Triggered via workflow_dispatch about 2 hours ago

JOBS
✓ full / build-core in 8m4s (ID 99052470284)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Resolve pinned Rust core revision
  ✓ Check out Rust core
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up Rust
  ✓ Cache Rust build
  ✓ Build abi3 Rust core wheel
  ✓ Build xprompt LSP
  ✓ Record wheel provenance
  ✓ Upload Rust core artifacts
  ✓ Post Cache Rust build
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Check out Rust core
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
- full / docs-build (ID 99052470671)
- full / release-core-floor-smoke (ID 99052483684)
✓ full / lint in 4m6s (ID 99053300926)
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
✓ full / ace-page-group-isolation in 1m16s (ID 99053300933)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  ✓ Run ACE shared-page isolation lane
  ✓ Post Install visual dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ full / perf-floors in 4m28s (ID 99053300941)
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
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
X full / test (3.12) in 44m7s (ID 99053300955)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  X Run tests (coverage leg)
  - Run tests
  - Run tests
  - Build shard timings table
  - Upload shard timings
  - Upload coverage
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
X full / visual-test in 14m38s (ID 99053300958)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  X Run visual tests
  ✓ Build visual failure report
  ✓ Upload visual failure report
  ✓ Publish visual failure report
  ✓ Upload visual failure artifacts
  ✓ Post Install visual dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ full / coverage-contexts in 44m12s (ID 99053300965)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Record per-test coverage contexts
  ✓ Upload coverage contexts database
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ full / test (3.14) in 27m3s (ID 99053300979)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  - Run tests (coverage leg)
  - Run tests
  ✓ Run tests
  ✓ Build shard timings table
  ✓ Upload shard timings
  - Upload coverage
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* full / test (3.13) (ID 99053301016)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  - Run tests (coverage leg)
  * Run tests
  * Run tests
  * Build shard timings table
  * Upload shard timings
  * Upload coverage
  * Post Install dependencies
  * Post Run actions/checkout@v4
- full / contention-test in 0s (ID 99053301394)
[0;0H[JRefreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Full CI · 33232978442
Triggered via workflow_dispatch about 2 hours ago

JOBS
✓ full / build-core in 8m4s (ID 99052470284)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Resolve pinned Rust core revision
  ✓ Check out Rust core
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up Rust
  ✓ Cache Rust build
  ✓ Build abi3 Rust core wheel
  ✓ Build xprompt LSP
  ✓ Record wheel provenance
  ✓ Upload Rust core artifacts
  ✓ Post Cache Rust build
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Check out Rust core
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
- full / docs-build (ID 99052470671)
- full / release-core-floor-smoke (ID 99052483684)
✓ full / lint in 4m6s (ID 99053300926)
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
✓ full / ace-page-group-isolation in 1m16s (ID 99053300933)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  ✓ Run ACE shared-page isolation lane
  ✓ Post Install visual dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ full / perf-floors in 4m28s (ID 99053300941)
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
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
X full / test (3.12) in 44m7s (ID 99053300955)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  X Run tests (coverage leg)
  - Run tests
  - Run tests
  - Build shard timings table
  - Upload shard timings
  - Upload coverage
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
X full / visual-test in 14m38s (ID 99053300958)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  X Run visual tests
  ✓ Build visual failure report
  ✓ Upload visual failure report
  ✓ Publish visual failure report
  ✓ Upload visual failure artifacts
  ✓ Post Install visual dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ full / coverage-contexts in 44m12s (ID 99053300965)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Record per-test coverage contexts
  ✓ Upload coverage contexts database
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ full / test (3.14) in 27m3s (ID 99053300979)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  - Run tests (coverage leg)
  - Run tests
  ✓ Run tests
  ✓ Build shard timings table
  ✓ Upload shard timings
  - Upload coverage
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* full / test (3.13) (ID 99053301016)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  - Run tests (coverage leg)
  * Run tests
  * Run tests
  * Build shard timings table
  * Upload shard timings
  * Upload coverage
  * Post Install dependencies
  * Post Run actions/checkout@v4
- full / contention-test in 0s (ID 99053301394)
[0;0H[JRefreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Full CI · 33232978442
Triggered via workflow_dispatch about 2 hours ago

JOBS
✓ full / build-core in 8m4s (ID 99052470284)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Resolve pinned Rust core revision
  ✓ Check out Rust core
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up Rust
  ✓ Cache Rust build
  ✓ Build abi3 Rust core wheel
  ✓ Build xprompt LSP
  ✓ Record wheel provenance
  ✓ Upload Rust core artifacts
  ✓ Post Cache Rust build
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Check out Rust core
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
- full / docs-build (ID 99052470671)
- full / release-core-floor-smoke (ID 99052483684)
✓ full / lint in 4m6s (ID 99053300926)
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
✓ full / ace-page-group-isolation in 1m16s (ID 99053300933)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  ✓ Run ACE shared-page isolation lane
  ✓ Post Install visual dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ full / perf-floors in 4m28s (ID 99053300941)
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
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
X full / test (3.12) in 44m7s (ID 99053300955)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  X Run tests (coverage leg)
  - Run tests
  - Run tests
  - Build shard timings table
  - Upload shard timings
  - Upload coverage
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
X full / visual-test in 14m38s (ID 99053300958)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  X Run visual tests
  ✓ Build visual failure report
  ✓ Upload visual failure report
  ✓ Publish visual failure report
  ✓ Upload visual failure artifacts
  ✓ Post Install visual dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ full / coverage-contexts in 44m12s (ID 99053300965)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Record per-test coverage contexts
  ✓ Upload coverage contexts database
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ full / test (3.14) in 27m3s (ID 99053300979)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  - Run tests (coverage leg)
  - Run tests
  ✓ Run tests
  ✓ Build shard timings table
  ✓ Upload shard timings
  - Upload coverage
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* full / test (3.13) (ID 99053301016)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  - Run tests (coverage leg)
  * Run tests
  * Run tests
  * Build shard timings table
  * Upload shard timings
  * Upload coverage
  * Post Install dependencies
  * Post Run actions/checkout@v4
- full / contention-test in 0s (ID 99053301394)
[0;0H[JRefreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Full CI · 33232978442
Triggered via workflow_dispatch about 2 hours ago

JOBS
✓ full / build-core in 8m4s (ID 99052470284)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Resolve pinned Rust core revision
  ✓ Check out Rust core
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up Rust
  ✓ Cache Rust build
  ✓ Build abi3 Rust core wheel
  ✓ Build xprompt LSP
  ✓ Record wheel provenance
  ✓ Upload Rust core artifacts
  ✓ Post Cache Rust build
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Check out Rust core
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
- full / docs-build (ID 99052470671)
- full / release-core-floor-smoke (ID 99052483684)
✓ full / lint in 4m6s (ID 99053300926)
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
✓ full / ace-page-group-isolation in 1m16s (ID 99053300933)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  ✓ Run ACE shared-page isolation lane
  ✓ Post Install visual dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ full / perf-floors in 4m28s (ID 99053300941)
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
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
X full / test (3.12) in 44m7s (ID 99053300955)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  X Run tests (coverage leg)
  - Run tests
  - Run tests
  - Build shard timings table
  - Upload shard timings
  - Upload coverage
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
X full / visual-test in 14m38s (ID 99053300958)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  X Run visual tests
  ✓ Build visual failure report
  ✓ Upload visual failure report
  ✓ Publish visual failure report
  ✓ Upload visual failure artifacts
  ✓ Post Install visual dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ full / coverage-contexts in 44m12s (ID 99053300965)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Record per-test coverage contexts
  ✓ Upload coverage contexts database
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ full / test (3.14) in 27m3s (ID 99053300979)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  - Run tests (coverage leg)
  - Run tests
  ✓ Run tests
  ✓ Build shard timings table
  ✓ Upload shard timings
  - Upload coverage
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* full / test (3.13) (ID 99053301016)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  - Run tests (coverage leg)
  * Run tests
  * Run tests
  * Build shard timings table
  * Upload shard timings
  * Upload coverage
  * Post Install dependencies
  * Post Run actions/checkout@v4
- full / contention-test in 0s (ID 99053301394)
[0;0H[JRefreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Full CI · 33232978442
Triggered via workflow_dispatch about 2 hours ago

JOBS
✓ full / build-core in 8m4s (ID 99052470284)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Resolve pinned Rust core revision
  ✓ Check out Rust core
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up Rust
  ✓ Cache Rust build
  ✓ Build abi3 Rust core wheel
  ✓ Build xprompt LSP
  ✓ Record wheel provenance
  ✓ Upload Rust core artifacts
  ✓ Post Cache Rust build
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Check out Rust core
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
- full / docs-build (ID 99052470671)
- full / release-core-floor-smoke (ID 99052483684)
✓ full / lint in 4m6s (ID 99053300926)
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
✓ full / ace-page-group-isolation in 1m16s (ID 99053300933)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  ✓ Run ACE shared-page isolation lane
  ✓ Post Install visual dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ full / perf-floors in 4m28s (ID 99053300941)
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
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
X full / test (3.12) in 44m7s (ID 99053300955)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  X Run tests (coverage leg)
  - Run tests
  - Run tests
  - Build shard timings table
  - Upload shard timings
  - Upload coverage
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
X full / visual-test in 14m38s (ID 99053300958)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  X Run visual tests
  ✓ Build visual failure report
  ✓ Upload visual failure report
  ✓ Publish visual failure report
  ✓ Upload visual failure artifacts
  ✓ Post Install visual dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ full / coverage-contexts in 44m12s (ID 99053300965)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Record per-test coverage contexts
  ✓ Upload coverage contexts database
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ full / test (3.14) in 27m3s (ID 99053300979)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  - Run tests (coverage leg)
  - Run tests
  ✓ Run tests
  ✓ Build shard timings table
  ✓ Upload shard timings
  - Upload coverage
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* full / test (3.13) (ID 99053301016)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  - Run tests (coverage leg)
  * Run tests
  * Run tests
  * Build shard timings table
  * Upload shard timings
  * Upload coverage
  * Post Install dependencies
  * Post Run actions/checkout@v4
- full / contention-test in 0s (ID 99053301394)
[0;0H[JRefreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Full CI · 33232978442
Triggered via workflow_dispatch about 2 hours ago

JOBS
✓ full / build-core in 8m4s (ID 99052470284)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Resolve pinned Rust core revision
  ✓ Check out Rust core
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up Rust
  ✓ Cache Rust build
  ✓ Build abi3 Rust core wheel
  ✓ Build xprompt LSP
  ✓ Record wheel provenance
  ✓ Upload Rust core artifacts
  ✓ Post Cache Rust build
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Check out Rust core
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
- full / docs-build (ID 99052470671)
- full / release-core-floor-smoke (ID 99052483684)
✓ full / lint in 4m6s (ID 99053300926)
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
✓ full / ace-page-group-isolation in 1m16s (ID 99053300933)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  ✓ Run ACE shared-page isolation lane
  ✓ Post Install visual dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ full / perf-floors in 4m28s (ID 99053300941)
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
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
X full / test (3.12) in 44m7s (ID 99053300955)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  X Run tests (coverage leg)
  - Run tests
  - Run tests
  - Build shard timings table
  - Upload shard timings
  - Upload coverage
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
X full / visual-test in 14m38s (ID 99053300958)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  X Run visual tests
  ✓ Build visual failure report
  ✓ Upload visual failure report
  ✓ Publish visual failure report
  ✓ Upload visual failure artifacts
  ✓ Post Install visual dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ full / coverage-contexts in 44m12s (ID 99053300965)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Record per-test coverage contexts
  ✓ Upload coverage contexts database
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ full / test (3.14) in 27m3s (ID 99053300979)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  - Run tests (coverage leg)
  - Run tests
  ✓ Run tests
  ✓ Build shard timings table
  ✓ Upload shard timings
  - Upload coverage
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* full / test (3.13) (ID 99053301016)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  - Run tests (coverage leg)
  * Run tests
  * Run tests
  * Build shard timings table
  * Upload shard timings
  * Upload coverage
  * Post Install dependencies
  * Post Run actions/checkout@v4
- full / contention-test in 0s (ID 99053301394)
[0;0H[JRefreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Full CI · 33232978442
Triggered via workflow_dispatch about 2 hours ago

JOBS
✓ full / build-core in 8m4s (ID 99052470284)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Resolve pinned Rust core revision
  ✓ Check out Rust core
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up Rust
  ✓ Cache Rust build
  ✓ Build abi3 Rust core wheel
  ✓ Build xprompt LSP
  ✓ Record wheel provenance
  ✓ Upload Rust core artifacts
  ✓ Post Cache Rust build
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Check out Rust core
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
- full / docs-build (ID 99052470671)
- full / release-core-floor-smoke (ID 99052483684)
✓ full / lint in 4m6s (ID 99053300926)
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
✓ full / ace-page-group-isolation in 1m16s (ID 99053300933)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  ✓ Run ACE shared-page isolation lane
  ✓ Post Install visual dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ full / perf-floors in 4m28s (ID 99053300941)
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
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
X full / test (3.12) in 44m7s (ID 99053300955)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  X Run tests (coverage leg)
  - Run tests
  - Run tests
  - Build shard timings table
  - Upload shard timings
  - Upload coverage
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
X full / visual-test in 14m38s (ID 99053300958)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  X Run visual tests
  ✓ Build visual failure report
  ✓ Upload visual failure report
  ✓ Publish visual failure report
  ✓ Upload visual failure artifacts
  ✓ Post Install visual dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ full / coverage-contexts in 44m12s (ID 99053300965)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Record per-test coverage contexts
  ✓ Upload coverage contexts database
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ full / test (3.14) in 27m3s (ID 99053300979)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  - Run tests (coverage leg)
  - Run tests
  ✓ Run tests
  ✓ Build shard timings table
  ✓ Upload shard timings
  - Upload coverage
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* full / test (3.13) (ID 99053301016)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  - Run tests (coverage leg)
  * Run tests
  * Run tests
  * Build shard timings table
  * Upload shard timings
  * Upload coverage
  * Post Install dependencies
  * Post Run actions/checkout@v4
- full / contention-test in 0s (ID 99053301394)
[0;0H[JRefreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Full CI · 33232978442
Triggered via workflow_dispatch about 2 hours ago

JOBS
✓ full / build-core in 8m4s (ID 99052470284)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Resolve pinned Rust core revision
  ✓ Check out Rust core
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up Rust
  ✓ Cache Rust build
  ✓ Build abi3 Rust core wheel
  ✓ Build xprompt LSP
  ✓ Record wheel provenance
  ✓ Upload Rust core artifacts
  ✓ Post Cache Rust build
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Check out Rust core
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
- full / docs-build (ID 99052470671)
- full / release-core-floor-smoke (ID 99052483684)
✓ full / lint in 4m6s (ID 99053300926)
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
✓ full / ace-page-group-isolation in 1m16s (ID 99053300933)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  ✓ Run ACE shared-page isolation lane
  ✓ Post Install visual dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ full / perf-floors in 4m28s (ID 99053300941)
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
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
X full / test (3.12) in 44m7s (ID 99053300955)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  X Run tests (coverage leg)
  - Run tests
  - Run tests
  - Build shard timings table
  - Upload shard timings
  - Upload coverage
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
X full / visual-test in 14m38s (ID 99053300958)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  X Run visual tests
  ✓ Build visual failure report
  ✓ Upload visual failure report
  ✓ Publish visual failure report
  ✓ Upload visual failure artifacts
  ✓ Post Install visual dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ full / coverage-contexts in 44m12s (ID 99053300965)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Record per-test coverage contexts
  ✓ Upload coverage contexts database
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ full / test (3.14) in 27m3s (ID 99053300979)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  - Run tests (coverage leg)
  - Run tests
  ✓ Run tests
  ✓ Build shard timings table
  ✓ Upload shard timings
  - Upload coverage
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* full / test (3.13) (ID 99053301016)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  - Run tests (coverage leg)
  * Run tests
  * Run tests
  * Build shard timings table
  * Upload shard timings
  * Upload coverage
  * Post Install dependencies
  * Post Run actions/checkout@v4
- full / contention-test in 0s (ID 99053301394)
[0;0H[JRefreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Full CI · 33232978442
Triggered via workflow_dispatch about 2 hours ago

JOBS
✓ full / build-core in 8m4s (ID 99052470284)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Resolve pinned Rust core revision
  ✓ Check out Rust core
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up Rust
  ✓ Cache Rust build
  ✓ Build abi3 Rust core wheel
  ✓ Build xprompt LSP
  ✓ Record wheel provenance
  ✓ Upload Rust core artifacts
  ✓ Post Cache Rust build
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Check out Rust core
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
- full / docs-build (ID 99052470671)
- full / release-core-floor-smoke (ID 99052483684)
✓ full / lint in 4m6s (ID 99053300926)
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
✓ full / ace-page-group-isolation in 1m16s (ID 99053300933)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  ✓ Run ACE shared-page isolation lane
  ✓ Post Install visual dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ full / perf-floors in 4m28s (ID 99053300941)
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
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
X full / test (3.12) in 44m7s (ID 99053300955)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  X Run tests (coverage leg)
  - Run tests
  - Run tests
  - Build shard timings table
  - Upload shard timings
  - Upload coverage
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
X full / visual-test in 14m38s (ID 99053300958)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  X Run visual tests
  ✓ Build visual failure report
  ✓ Upload visual failure report
  ✓ Publish visual failure report
  ✓ Upload visual failure artifacts
  ✓ Post Install visual dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ full / coverage-contexts in 44m12s (ID 99053300965)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Record per-test coverage contexts
  ✓ Upload coverage contexts database
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ full / test (3.14) in 27m3s (ID 99053300979)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  - Run tests (coverage leg)
  - Run tests
  ✓ Run tests
  ✓ Build shard timings table
  ✓ Upload shard timings
  - Upload coverage
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* full / test (3.13) (ID 99053301016)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  - Run tests (coverage leg)
  * Run tests
  * Run tests
  * Build shard timings table
  * Upload shard timings
  * Upload coverage
  * Post Install dependencies
  * Post Run actions/checkout@v4
- full / contention-test in 0s (ID 99053301394)
[0;0H[JRefreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Full CI · 33232978442
Triggered via workflow_dispatch about 2 hours ago

JOBS
✓ full / build-core in 8m4s (ID 99052470284)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Resolve pinned Rust core revision
  ✓ Check out Rust core
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up Rust
  ✓ Cache Rust build
  ✓ Build abi3 Rust core wheel
  ✓ Build xprompt LSP
  ✓ Record wheel provenance
  ✓ Upload Rust core artifacts
  ✓ Post Cache Rust build
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Check out Rust core
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
- full / docs-build (ID 99052470671)
- full / release-core-floor-smoke (ID 99052483684)
✓ full / lint in 4m6s (ID 99053300926)
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
✓ full / ace-page-group-isolation in 1m16s (ID 99053300933)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  ✓ Run ACE shared-page isolation lane
  ✓ Post Install visual dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ full / perf-floors in 4m28s (ID 99053300941)
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
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
X full / test (3.12) in 44m7s (ID 99053300955)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  X Run tests (coverage leg)
  - Run tests
  - Run tests
  - Build shard timings table
  - Upload shard timings
  - Upload coverage
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
X full / visual-test in 14m38s (ID 99053300958)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  X Run visual tests
  ✓ Build visual failure report
  ✓ Upload visual failure report
  ✓ Publish visual failure report
  ✓ Upload visual failure artifacts
  ✓ Post Install visual dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ full / coverage-contexts in 44m12s (ID 99053300965)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Record per-test coverage contexts
  ✓ Upload coverage contexts database
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ full / test (3.14) in 27m3s (ID 99053300979)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  - Run tests (coverage leg)
  - Run tests
  ✓ Run tests
  ✓ Build shard timings table
  ✓ Upload shard timings
  - Upload coverage
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* full / test (3.13) (ID 99053301016)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  - Run tests (coverage leg)
  * Run tests
  * Run tests
  * Build shard timings table
  * Upload shard timings
  * Upload coverage
  * Post Install dependencies
  * Post Run actions/checkout@v4
- full / contention-test in 0s (ID 99053301394)
[0;0H[JRefreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Full CI · 33232978442
Triggered via workflow_dispatch about 2 hours ago

JOBS
✓ full / build-core in 8m4s (ID 99052470284)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Resolve pinned Rust core revision
  ✓ Check out Rust core
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up Rust
  ✓ Cache Rust build
  ✓ Build abi3 Rust core wheel
  ✓ Build xprompt LSP
  ✓ Record wheel provenance
  ✓ Upload Rust core artifacts
  ✓ Post Cache Rust build
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Check out Rust core
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
- full / docs-build (ID 99052470671)
- full / release-core-floor-smoke (ID 99052483684)
✓ full / lint in 4m6s (ID 99053300926)
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
✓ full / ace-page-group-isolation in 1m16s (ID 99053300933)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  ✓ Run ACE shared-page isolation lane
  ✓ Post Install visual dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ full / perf-floors in 4m28s (ID 99053300941)
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
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
X full / test (3.12) in 44m7s (ID 99053300955)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  X Run tests (coverage leg)
  - Run tests
  - Run tests
  - Build shard timings table
  - Upload shard timings
  - Upload coverage
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
X full / visual-test in 14m38s (ID 99053300958)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  X Run visual tests
  ✓ Build visual failure report
  ✓ Upload visual failure report
  ✓ Publish visual failure report
  ✓ Upload visual failure artifacts
  ✓ Post Install visual dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ full / coverage-contexts in 44m12s (ID 99053300965)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Record per-test coverage contexts
  ✓ Upload coverage contexts database
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ full / test (3.14) in 27m3s (ID 99053300979)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  - Run tests (coverage leg)
  - Run tests
  ✓ Run tests
  ✓ Build shard timings table
  ✓ Upload shard timings
  - Upload coverage
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* full / test (3.13) (ID 99053301016)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  - Run tests (coverage leg)
  * Run tests
  * Run tests
  * Build shard timings table
  * Upload shard timings
  * Upload coverage
  * Post Install dependencies
  * Post Run actions/checkout@v4
- full / contention-test in 0s (ID 99053301394)
[0;0H[JRefreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Full CI · 33232978442
Triggered via workflow_dispatch about 2 hours ago

JOBS
✓ full / build-core in 8m4s (ID 99052470284)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Resolve pinned Rust core revision
  ✓ Check out Rust core
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up Rust
  ✓ Cache Rust build
  ✓ Build abi3 Rust core wheel
  ✓ Build xprompt LSP
  ✓ Record wheel provenance
  ✓ Upload Rust core artifacts
  ✓ Post Cache Rust build
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Check out Rust core
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
- full / docs-build (ID 99052470671)
- full / release-core-floor-smoke (ID 99052483684)
✓ full / lint in 4m6s (ID 99053300926)
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
✓ full / ace-page-group-isolation in 1m16s (ID 99053300933)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  ✓ Run ACE shared-page isolation lane
  ✓ Post Install visual dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ full / perf-floors in 4m28s (ID 99053300941)
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
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
X full / test (3.12) in 44m7s (ID 99053300955)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  X Run tests (coverage leg)
  - Run tests
  - Run tests
  - Build shard timings table
  - Upload shard timings
  - Upload coverage
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
X full / visual-test in 14m38s (ID 99053300958)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  X Run visual tests
  ✓ Build visual failure report
  ✓ Upload visual failure report
  ✓ Publish visual failure report
  ✓ Upload visual failure artifacts
  ✓ Post Install visual dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ full / coverage-contexts in 44m12s (ID 99053300965)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Record per-test coverage contexts
  ✓ Upload coverage contexts database
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ full / test (3.14) in 27m3s (ID 99053300979)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  - Run tests (coverage leg)
  - Run tests
  ✓ Run tests
  ✓ Build shard timings table
  ✓ Upload shard timings
  - Upload coverage
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* full / test (3.13) (ID 99053301016)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  - Run tests (coverage leg)
  * Run tests
  * Run tests
  * Build shard timings table
  * Upload shard timings
  * Upload coverage
  * Post Install dependencies
  * Post Run actions/checkout@v4
- full / contention-test in 0s (ID 99053301394)
[0;0H[JRefreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Full CI · 33232978442
Triggered via workflow_dispatch about 2 hours ago

JOBS
✓ full / build-core in 8m4s (ID 99052470284)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Resolve pinned Rust core revision
  ✓ Check out Rust core
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up Rust
  ✓ Cache Rust build
  ✓ Build abi3 Rust core wheel
  ✓ Build xprompt LSP
  ✓ Record wheel provenance
  ✓ Upload Rust core artifacts
  ✓ Post Cache Rust build
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Check out Rust core
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
- full / docs-build (ID 99052470671)
- full / release-core-floor-smoke (ID 99052483684)
✓ full / lint in 4m6s (ID 99053300926)
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
✓ full / ace-page-group-isolation in 1m16s (ID 99053300933)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  ✓ Run ACE shared-page isolation lane
  ✓ Post Install visual dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ full / perf-floors in 4m28s (ID 99053300941)
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
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
X full / test (3.12) in 44m7s (ID 99053300955)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  X Run tests (coverage leg)
  - Run tests
  - Run tests
  - Build shard timings table
  - Upload shard timings
  - Upload coverage
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
X full / visual-test in 14m38s (ID 99053300958)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  X Run visual tests
  ✓ Build visual failure report
  ✓ Upload visual failure report
  ✓ Publish visual failure report
  ✓ Upload visual failure artifacts
  ✓ Post Install visual dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ full / coverage-contexts in 44m12s (ID 99053300965)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Record per-test coverage contexts
  ✓ Upload coverage contexts database
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ full / test (3.14) in 27m3s (ID 99053300979)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  - Run tests (coverage leg)
  - Run tests
  ✓ Run tests
  ✓ Build shard timings table
  ✓ Upload shard timings
  - Upload coverage
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* full / test (3.13) (ID 99053301016)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  - Run tests (coverage leg)
  * Run tests
  * Run tests
  * Build shard timings table
  * Upload shard timings
  * Upload coverage
  * Post Install dependencies
  * Post Run actions/checkout@v4
- full / contention-test in 0s (ID 99053301394)
[?1049lX master Full CI · 33232978442
Triggered via workflow_dispatch about 2 hours ago

JOBS
✓ full / build-core in 8m4s (ID 99052470284)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Resolve pinned Rust core revision
  ✓ Check out Rust core
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up Rust
  ✓ Cache Rust build
  ✓ Build abi3 Rust core wheel
  ✓ Build xprompt LSP
  ✓ Record wheel provenance
  ✓ Upload Rust core artifacts
  ✓ Post Cache Rust build
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Check out Rust core
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
- full / docs-build (ID 99052470671)
- full / release-core-floor-smoke (ID 99052483684)
✓ full / lint in 4m6s (ID 99053300926)
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
✓ full / ace-page-group-isolation in 1m16s (ID 99053300933)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  ✓ Run ACE shared-page isolation lane
  ✓ Post Install visual dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ full / perf-floors in 4m28s (ID 99053300941)
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
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
X full / test (3.12) in 44m7s (ID 99053300955)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  X Run tests (coverage leg)
  - Run tests
  - Run tests
  - Build shard timings table
  - Upload shard timings
  - Upload coverage
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
X full / visual-test in 14m38s (ID 99053300958)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  X Run visual tests
  ✓ Build visual failure report
  ✓ Upload visual failure report
  ✓ Publish visual failure report
  ✓ Upload visual failure artifacts
  ✓ Post Install visual dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ full / coverage-contexts in 44m12s (ID 99053300965)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Record per-test coverage contexts
  ✓ Upload coverage contexts database
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ full / test (3.14) in 27m3s (ID 99053300979)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  - Run tests (coverage leg)
  - Run tests
  ✓ Run tests
  ✓ Build shard timings table
  ✓ Upload shard timings
  - Upload coverage
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
X full / test (3.13) in 1h30m15s (ID 99053301016)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  - Run tests (coverage leg)
  X Run tests
  - Run tests
  - Build shard timings table
  - Upload shard timings
  - Upload coverage
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
- full / contention-test in 0s (ID 99053301394)

X Run Full CI (33232978442) completed with 'failure'

