# Chat History - ace-run (sase-1s7.4--mon-0)

- **TIMESTAMP:** 2026-11-10 17:08:55 EST
- **MODEL:** muse/muse-spark-1.3-contributor
- **AGENT:** sase-1s7.4--mon-0

## Prompt

sase monitor start --command 'gh run watch 42897628895 -R sase-org/sase --interval 120' --reason 'Watch rehearse-mode release.yml attempt-2 run 42897628895 for sase-1s7.4 acceptance'

## Response

sase: running unwrapped (no profile (monitor.tool_wrap is verify))
Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* release-please--branches--master Release sase-org/sase#322 · 42897628895
Triggered via workflow_dispatch about 10 minutes ago

JOBS
✓ identity in 57s (ID 130114862321)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Assert source and version identity
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ build in 38s (ID 130115420556)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up Python
  ✓ Build once and check the dist set
  ✓ Resolve the exact core pin
  ✓ Fetch the core file list and digests
  ✓ Read the core completeness set at the pin's tag
  ✓ Prove the core tag contains the source pin
  ✓ Seal the candidate manifest
  ✓ Upload the candidate build
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ qualify-prepare in 26s (ID 130115802507)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Download the sealed candidate build
  ✓ Bind the sealed candidate identity
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ exercise-legs (macos-latest, wheel) in 2m5s (ID 130115802596)
  ✓ Set up job
  ✓ Refuse probes outside rehearse
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up Python
  ✓ Ensure tmux for the TUI frame
  ✓ Download the sealed build
  ✓ Resolve the leg dist and manifest fields
  ✓ Verify digests before install
  ✓ Prepare the isolated leg environment
  ✓ Resolve the previous installable PyPI release
  ✓ Run the exercise leg
  ✓ Upload the leg evidence
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ exercise-legs (ubuntu-latest, sdist) in 54s (ID 130115802632)
  ✓ Set up job
  ✓ Refuse probes outside rehearse
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up Python
  - Ensure tmux for the TUI frame
  ✓ Download the sealed build
  ✓ Resolve the leg dist and manifest fields
  ✓ Verify digests before install
  ✓ Prepare the isolated leg environment
  - Resolve the previous installable PyPI release
  ✓ Run the exercise leg
  ✓ Upload the leg evidence
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ exercise-legs (ubuntu-latest, wheel) in 1m8s (ID 130115802657)
  ✓ Set up job
  ✓ Refuse probes outside rehearse
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up Python
  - Ensure tmux for the TUI frame
  ✓ Download the sealed build
  ✓ Resolve the leg dist and manifest fields
  ✓ Verify digests before install
  ✓ Prepare the isolated leg environment
  ✓ Resolve the previous installable PyPI release
  ✓ Run the exercise leg
  ✓ Upload the leg evidence
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ exercise-legs (macos-latest, sdist) in 1m18s (ID 130115802821)
  ✓ Set up job
  ✓ Refuse probes outside rehearse
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up Python
  ✓ Ensure tmux for the TUI frame
  ✓ Download the sealed build
  ✓ Resolve the leg dist and manifest fields
  ✓ Verify digests before install
  ✓ Prepare the isolated leg environment
  - Resolve the previous installable PyPI release
  ✓ Run the exercise leg
  ✓ Upload the leg evidence
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
- stash (ID 130115805318)
✓ qualify-ci / prepare in 26s (ID 130116069325)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Validate qualification inputs
  ✓ Download the sealed candidate manifest
  ✓ Bind published identity from the sealed manifest
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
- qualify-ci / release-core-floor-smoke (ID 130116071518)
- qualify-ci / docs-build (ID 130116072055)
* qualify-ci / build-core / build-core (ID 130116334196)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Resolve core mode
  - Resolve pinned Rust core revision
  - Check out Rust core
  ✓ Check out published Rust core tag
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up Rust
  ✓ Cache Rust build
  - Build abi3 Rust core wheel
  ✓ Download the sealed candidate manifest
  ✓ Fetch and verify the published core wheel
  * Build macro LSP
  * Record wheel provenance
  * Record published tag provenance
  * Upload Rust core artifacts
  * Post Cache Rust build
  * Post Run astral-sh/setup-uv@v4
  * Post Check out published Rust core tag
  * Post Run actions/checkout@v4
✓ exercise in 27s (ID 130117005549)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Download the sealed build
  ✓ Download the leg evidence
  ✓ Merge the legs into one exercise observation
  - Stash the exercise observation on the draft release
  ✓ Upload the exercise observation artifact
  ✓ Post Run actions/checkout@v4
  ✓ Complete job

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
identity: .github#7

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
identity: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
build: .github#4

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0sIHzagAAAAB30fM6H9ufTppmpzFOLFMkUEhMMzBFREdFMDEwOABFZGdl
build: .github#7

! Failed to restore: Cache service responded with 400
build: .github#24

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
build: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-prepare: .github#9

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-prepare: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
exercise-legs (macos-latest, wheel): .github#2

- Due to capacity constraints, jobs targeting macOS arm64 runners may experience longer queue times.
exercise-legs (macos-latest, wheel): .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
exercise-legs (ubuntu-latest, sdist): .github#2

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
exercise-legs (ubuntu-latest, sdist): .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
exercise-legs (ubuntu-latest, wheel): .github#2

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
exercise-legs (ubuntu-latest, wheel): .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
exercise-legs (macos-latest, sdist): .github#2

- Due to capacity constraints, jobs targeting macOS arm64 runners may experience longer queue times.
exercise-legs (macos-latest, sdist): .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / prepare: .github#10

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / prepare: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
exercise: .github#4

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
exercise: .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* release-please--branches--master Release sase-org/sase#322 · 42897628895
Triggered via workflow_dispatch about 12 minutes ago

JOBS
✓ identity in 57s (ID 130114862321)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Assert source and version identity
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ build in 38s (ID 130115420556)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up Python
  ✓ Build once and check the dist set
  ✓ Resolve the exact core pin
  ✓ Fetch the core file list and digests
  ✓ Read the core completeness set at the pin's tag
  ✓ Prove the core tag contains the source pin
  ✓ Seal the candidate manifest
  ✓ Upload the candidate build
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ qualify-prepare in 26s (ID 130115802507)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Download the sealed candidate build
  ✓ Bind the sealed candidate identity
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ exercise-legs (macos-latest, wheel) in 2m5s (ID 130115802596)
  ✓ Set up job
  ✓ Refuse probes outside rehearse
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up Python
  ✓ Ensure tmux for the TUI frame
  ✓ Download the sealed build
  ✓ Resolve the leg dist and manifest fields
  ✓ Verify digests before install
  ✓ Prepare the isolated leg environment
  ✓ Resolve the previous installable PyPI release
  ✓ Run the exercise leg
  ✓ Upload the leg evidence
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ exercise-legs (ubuntu-latest, sdist) in 54s (ID 130115802632)
  ✓ Set up job
  ✓ Refuse probes outside rehearse
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up Python
  - Ensure tmux for the TUI frame
  ✓ Download the sealed build
  ✓ Resolve the leg dist and manifest fields
  ✓ Verify digests before install
  ✓ Prepare the isolated leg environment
  - Resolve the previous installable PyPI release
  ✓ Run the exercise leg
  ✓ Upload the leg evidence
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ exercise-legs (ubuntu-latest, wheel) in 1m8s (ID 130115802657)
  ✓ Set up job
  ✓ Refuse probes outside rehearse
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up Python
  - Ensure tmux for the TUI frame
  ✓ Download the sealed build
  ✓ Resolve the leg dist and manifest fields
  ✓ Verify digests before install
  ✓ Prepare the isolated leg environment
  ✓ Resolve the previous installable PyPI release
  ✓ Run the exercise leg
  ✓ Upload the leg evidence
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ exercise-legs (macos-latest, sdist) in 1m18s (ID 130115802821)
  ✓ Set up job
  ✓ Refuse probes outside rehearse
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up Python
  ✓ Ensure tmux for the TUI frame
  ✓ Download the sealed build
  ✓ Resolve the leg dist and manifest fields
  ✓ Verify digests before install
  ✓ Prepare the isolated leg environment
  - Resolve the previous installable PyPI release
  ✓ Run the exercise leg
  ✓ Upload the leg evidence
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
- stash (ID 130115805318)
✓ qualify-ci / prepare in 26s (ID 130116069325)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Validate qualification inputs
  ✓ Download the sealed candidate manifest
  ✓ Bind published identity from the sealed manifest
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
- qualify-ci / release-core-floor-smoke (ID 130116071518)
- qualify-ci / docs-build (ID 130116072055)
✓ qualify-ci / build-core / build-core in 8m41s (ID 130116334196)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Resolve core mode
  - Resolve pinned Rust core revision
  - Check out Rust core
  ✓ Check out published Rust core tag
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up Rust
  ✓ Cache Rust build
  - Build abi3 Rust core wheel
  ✓ Download the sealed candidate manifest
  ✓ Fetch and verify the published core wheel
  ✓ Build macro LSP
  - Record wheel provenance
  ✓ Record published tag provenance
  ✓ Upload Rust core artifacts
  ✓ Post Cache Rust build
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Check out published Rust core tag
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ exercise in 27s (ID 130117005549)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Download the sealed build
  ✓ Download the leg evidence
  ✓ Merge the legs into one exercise observation
  - Stash the exercise observation on the draft release
  ✓ Upload the exercise observation artifact
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* qualify-ci / perf-floors (ID 130121174612)
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
✓ qualify-ci / tutorial-tests in 1m4s (ID 130121174619)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run tutorial tests
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* qualify-ci / visual-test (ID 130121174667)
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
* qualify-ci / lint (ID 130121174682)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up preflight Python
  ✓ Download Rust core artifacts for bindings preflight
  ✓ Preflight core bindings
  ✓ Install dependencies
  ✓ Check pinned core bindings
  ✓ Bootstrap SDD sidecars
  ✓ Initialize SASE home
  ✓ Run actions/setup-go@v5
  ✓ Cache Go binaries
  - Install Go tools (keep-sorted)
  ✓ Cache Prettier dependencies
  ✓ Check Python formatting
  ✓ Check Markdown formatting
  X Check generated model docs
  - Check shipped model policy
  - Lint
  - SASE validation
  - Validate committed plans
  - Build and verify package
  ✓ Record installed core version
  * Write qualification evidence
  * Upload qualification evidence
  * Post Cache Prettier dependencies
  * Post Cache Go binaries
  * Post Run actions/setup-go@v5
  * Post Install dependencies
  * Post Run astral-sh/setup-uv@v4
  * Post Run actions/checkout@v4
* qualify-ci / test (3.14) (ID 130121174714)
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
* qualify-ci / test (3.13) (ID 130121174802)
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
* qualify-ci / test (3.12) (ID 130121174849)
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
* qualify-ci / ace-page-group-isolation (ID 130121174850)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  * Run ACE shared-page isolation lane
  * Post Install visual dependencies
  * Post Run actions/checkout@v4

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
identity: .github#7

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
identity: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
build: .github#4

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0sIHzagAAAAB30fM6H9ufTppmpzFOLFMkUEhMMzBFREdFMDEwOABFZGdl
build: .github#7

! Failed to restore: Cache service responded with 400
build: .github#24

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
build: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-prepare: .github#9

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-prepare: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
exercise-legs (macos-latest, wheel): .github#2

- Due to capacity constraints, jobs targeting macOS arm64 runners may experience longer queue times.
exercise-legs (macos-latest, wheel): .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
exercise-legs (ubuntu-latest, sdist): .github#2

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
exercise-legs (ubuntu-latest, sdist): .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
exercise-legs (ubuntu-latest, wheel): .github#2

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
exercise-legs (ubuntu-latest, wheel): .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
exercise-legs (macos-latest, sdist): .github#2

- Due to capacity constraints, jobs targeting macOS arm64 runners may experience longer queue times.
exercise-legs (macos-latest, sdist): .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / prepare: .github#10

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / prepare: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / build-core / build-core: .github#5

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>09YPzagAAAAAiPR5XKRSoQpRg352ExmJxQ0gxQUEyMDMwODE0MDYwAEVkZ2U=
qualify-ci / build-core / build-core: .github#7

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / tutorial-tests: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0OITzagAAAACMpVdYEU0wTYGlMGZQR9ksQ0gxQUEyMDMwODEzMDYwAEVkZ2U=
qualify-ci / tutorial-tests: .github#9

! Failed to restore: Cache service responded with 400
qualify-ci / tutorial-tests: .github#49

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / tutorial-tests: .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* release-please--branches--master Release sase-org/sase#322 · 42897628895
Triggered via workflow_dispatch about 15 minutes ago

JOBS
✓ identity in 57s (ID 130114862321)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Assert source and version identity
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ build in 38s (ID 130115420556)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up Python
  ✓ Build once and check the dist set
  ✓ Resolve the exact core pin
  ✓ Fetch the core file list and digests
  ✓ Read the core completeness set at the pin's tag
  ✓ Prove the core tag contains the source pin
  ✓ Seal the candidate manifest
  ✓ Upload the candidate build
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ qualify-prepare in 26s (ID 130115802507)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Download the sealed candidate build
  ✓ Bind the sealed candidate identity
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ exercise-legs (macos-latest, wheel) in 2m5s (ID 130115802596)
  ✓ Set up job
  ✓ Refuse probes outside rehearse
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up Python
  ✓ Ensure tmux for the TUI frame
  ✓ Download the sealed build
  ✓ Resolve the leg dist and manifest fields
  ✓ Verify digests before install
  ✓ Prepare the isolated leg environment
  ✓ Resolve the previous installable PyPI release
  ✓ Run the exercise leg
  ✓ Upload the leg evidence
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ exercise-legs (ubuntu-latest, sdist) in 54s (ID 130115802632)
  ✓ Set up job
  ✓ Refuse probes outside rehearse
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up Python
  - Ensure tmux for the TUI frame
  ✓ Download the sealed build
  ✓ Resolve the leg dist and manifest fields
  ✓ Verify digests before install
  ✓ Prepare the isolated leg environment
  - Resolve the previous installable PyPI release
  ✓ Run the exercise leg
  ✓ Upload the leg evidence
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ exercise-legs (ubuntu-latest, wheel) in 1m8s (ID 130115802657)
  ✓ Set up job
  ✓ Refuse probes outside rehearse
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up Python
  - Ensure tmux for the TUI frame
  ✓ Download the sealed build
  ✓ Resolve the leg dist and manifest fields
  ✓ Verify digests before install
  ✓ Prepare the isolated leg environment
  ✓ Resolve the previous installable PyPI release
  ✓ Run the exercise leg
  ✓ Upload the leg evidence
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ exercise-legs (macos-latest, sdist) in 1m18s (ID 130115802821)
  ✓ Set up job
  ✓ Refuse probes outside rehearse
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up Python
  ✓ Ensure tmux for the TUI frame
  ✓ Download the sealed build
  ✓ Resolve the leg dist and manifest fields
  ✓ Verify digests before install
  ✓ Prepare the isolated leg environment
  - Resolve the previous installable PyPI release
  ✓ Run the exercise leg
  ✓ Upload the leg evidence
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
- stash (ID 130115805318)
✓ qualify-ci / prepare in 26s (ID 130116069325)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Validate qualification inputs
  ✓ Download the sealed candidate manifest
  ✓ Bind published identity from the sealed manifest
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
- qualify-ci / release-core-floor-smoke (ID 130116071518)
- qualify-ci / docs-build (ID 130116072055)
✓ qualify-ci / build-core / build-core in 8m41s (ID 130116334196)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Resolve core mode
  - Resolve pinned Rust core revision
  - Check out Rust core
  ✓ Check out published Rust core tag
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up Rust
  ✓ Cache Rust build
  - Build abi3 Rust core wheel
  ✓ Download the sealed candidate manifest
  ✓ Fetch and verify the published core wheel
  ✓ Build macro LSP
  - Record wheel provenance
  ✓ Record published tag provenance
  ✓ Upload Rust core artifacts
  ✓ Post Cache Rust build
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Check out published Rust core tag
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ exercise in 27s (ID 130117005549)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Download the sealed build
  ✓ Download the leg evidence
  ✓ Merge the legs into one exercise observation
  - Stash the exercise observation on the draft release
  ✓ Upload the exercise observation artifact
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* qualify-ci / perf-floors (ID 130121174612)
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
✓ qualify-ci / tutorial-tests in 1m4s (ID 130121174619)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run tutorial tests
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* qualify-ci / visual-test (ID 130121174667)
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
X qualify-ci / lint in 1m31s (ID 130121174682)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up preflight Python
  ✓ Download Rust core artifacts for bindings preflight
  ✓ Preflight core bindings
  ✓ Install dependencies
  ✓ Check pinned core bindings
  ✓ Bootstrap SDD sidecars
  ✓ Initialize SASE home
  ✓ Run actions/setup-go@v5
  ✓ Cache Go binaries
  - Install Go tools (keep-sorted)
  ✓ Cache Prettier dependencies
  ✓ Check Python formatting
  ✓ Check Markdown formatting
  X Check generated model docs
  - Check shipped model policy
  - Lint
  - SASE validation
  - Validate committed plans
  - Build and verify package
  ✓ Record installed core version
  ✓ Write qualification evidence
  ✓ Upload qualification evidence
  - Post Cache Prettier dependencies
  - Post Cache Go binaries
  - Post Run actions/setup-go@v5
  ✓ Post Install dependencies
  - Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* qualify-ci / test (3.14) (ID 130121174714)
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
* qualify-ci / test (3.13) (ID 130121174802)
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
* qualify-ci / test (3.12) (ID 130121174849)
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
✓ qualify-ci / ace-page-group-isolation in 1m37s (ID 130121174850)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  ✓ Run ACE shared-page isolation lane
  ✓ Post Install visual dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
identity: .github#7

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
identity: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
build: .github#4

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0sIHzagAAAAB30fM6H9ufTppmpzFOLFMkUEhMMzBFREdFMDEwOABFZGdl
build: .github#7

! Failed to restore: Cache service responded with 400
build: .github#24

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
build: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-prepare: .github#9

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-prepare: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
exercise-legs (macos-latest, wheel): .github#2

- Due to capacity constraints, jobs targeting macOS arm64 runners may experience longer queue times.
exercise-legs (macos-latest, wheel): .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
exercise-legs (ubuntu-latest, sdist): .github#2

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
exercise-legs (ubuntu-latest, sdist): .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
exercise-legs (ubuntu-latest, wheel): .github#2

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
exercise-legs (ubuntu-latest, wheel): .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
exercise-legs (macos-latest, sdist): .github#2

- Due to capacity constraints, jobs targeting macOS arm64 runners may experience longer queue times.
exercise-legs (macos-latest, sdist): .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / prepare: .github#10

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / prepare: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / build-core / build-core: .github#5

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>09YPzagAAAAAiPR5XKRSoQpRg352ExmJxQ0gxQUEyMDMwODE0MDYwAEVkZ2U=
qualify-ci / build-core / build-core: .github#7

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / tutorial-tests: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0OITzagAAAACMpVdYEU0wTYGlMGZQR9ksQ0gxQUEyMDMwODEzMDYwAEVkZ2U=
qualify-ci / tutorial-tests: .github#9

! Failed to restore: Cache service responded with 400
qualify-ci / tutorial-tests: .github#49

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / tutorial-tests: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache@v4, actions/checkout@v4, actions/download-artifact@v4, actions/setup-go@v5, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / lint: .github#2

X Process completed with exit code 1.
qualify-ci / lint: .github#16

! Failed to restore: Cache service responded with 400
qualify-ci / lint: .github#52

! Failed to restore: Cache service responded with 400
qualify-ci / lint: .github#24

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / lint: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / ace-page-group-isolation: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0WITzagAAAAAzCcEmW9wlRq5yhIB141iuQ0gxQUEyMDMwODEzMDI1AEVkZ2U=
qualify-ci / ace-page-group-isolation: .github#9

! Failed to restore: Cache service responded with 400
qualify-ci / ace-page-group-isolation: .github#49

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / ace-page-group-isolation: .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* release-please--branches--master Release sase-org/sase#322 · 42897628895
Triggered via workflow_dispatch about 17 minutes ago

JOBS
✓ identity in 57s (ID 130114862321)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Assert source and version identity
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ build in 38s (ID 130115420556)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up Python
  ✓ Build once and check the dist set
  ✓ Resolve the exact core pin
  ✓ Fetch the core file list and digests
  ✓ Read the core completeness set at the pin's tag
  ✓ Prove the core tag contains the source pin
  ✓ Seal the candidate manifest
  ✓ Upload the candidate build
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ qualify-prepare in 26s (ID 130115802507)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Download the sealed candidate build
  ✓ Bind the sealed candidate identity
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ exercise-legs (macos-latest, wheel) in 2m5s (ID 130115802596)
  ✓ Set up job
  ✓ Refuse probes outside rehearse
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up Python
  ✓ Ensure tmux for the TUI frame
  ✓ Download the sealed build
  ✓ Resolve the leg dist and manifest fields
  ✓ Verify digests before install
  ✓ Prepare the isolated leg environment
  ✓ Resolve the previous installable PyPI release
  ✓ Run the exercise leg
  ✓ Upload the leg evidence
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ exercise-legs (ubuntu-latest, sdist) in 54s (ID 130115802632)
  ✓ Set up job
  ✓ Refuse probes outside rehearse
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up Python
  - Ensure tmux for the TUI frame
  ✓ Download the sealed build
  ✓ Resolve the leg dist and manifest fields
  ✓ Verify digests before install
  ✓ Prepare the isolated leg environment
  - Resolve the previous installable PyPI release
  ✓ Run the exercise leg
  ✓ Upload the leg evidence
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ exercise-legs (ubuntu-latest, wheel) in 1m8s (ID 130115802657)
  ✓ Set up job
  ✓ Refuse probes outside rehearse
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up Python
  - Ensure tmux for the TUI frame
  ✓ Download the sealed build
  ✓ Resolve the leg dist and manifest fields
  ✓ Verify digests before install
  ✓ Prepare the isolated leg environment
  ✓ Resolve the previous installable PyPI release
  ✓ Run the exercise leg
  ✓ Upload the leg evidence
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ exercise-legs (macos-latest, sdist) in 1m18s (ID 130115802821)
  ✓ Set up job
  ✓ Refuse probes outside rehearse
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up Python
  ✓ Ensure tmux for the TUI frame
  ✓ Download the sealed build
  ✓ Resolve the leg dist and manifest fields
  ✓ Verify digests before install
  ✓ Prepare the isolated leg environment
  - Resolve the previous installable PyPI release
  ✓ Run the exercise leg
  ✓ Upload the leg evidence
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
- stash (ID 130115805318)
✓ qualify-ci / prepare in 26s (ID 130116069325)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Validate qualification inputs
  ✓ Download the sealed candidate manifest
  ✓ Bind published identity from the sealed manifest
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
- qualify-ci / release-core-floor-smoke (ID 130116071518)
- qualify-ci / docs-build (ID 130116072055)
✓ qualify-ci / build-core / build-core in 8m41s (ID 130116334196)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Resolve core mode
  - Resolve pinned Rust core revision
  - Check out Rust core
  ✓ Check out published Rust core tag
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up Rust
  ✓ Cache Rust build
  - Build abi3 Rust core wheel
  ✓ Download the sealed candidate manifest
  ✓ Fetch and verify the published core wheel
  ✓ Build macro LSP
  - Record wheel provenance
  ✓ Record published tag provenance
  ✓ Upload Rust core artifacts
  ✓ Post Cache Rust build
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Check out published Rust core tag
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ exercise in 27s (ID 130117005549)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Download the sealed build
  ✓ Download the leg evidence
  ✓ Merge the legs into one exercise observation
  - Stash the exercise observation on the draft release
  ✓ Upload the exercise observation artifact
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* qualify-ci / perf-floors (ID 130121174612)
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
✓ qualify-ci / tutorial-tests in 1m4s (ID 130121174619)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run tutorial tests
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* qualify-ci / visual-test (ID 130121174667)
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
X qualify-ci / lint in 1m31s (ID 130121174682)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up preflight Python
  ✓ Download Rust core artifacts for bindings preflight
  ✓ Preflight core bindings
  ✓ Install dependencies
  ✓ Check pinned core bindings
  ✓ Bootstrap SDD sidecars
  ✓ Initialize SASE home
  ✓ Run actions/setup-go@v5
  ✓ Cache Go binaries
  - Install Go tools (keep-sorted)
  ✓ Cache Prettier dependencies
  ✓ Check Python formatting
  ✓ Check Markdown formatting
  X Check generated model docs
  - Check shipped model policy
  - Lint
  - SASE validation
  - Validate committed plans
  - Build and verify package
  ✓ Record installed core version
  ✓ Write qualification evidence
  ✓ Upload qualification evidence
  - Post Cache Prettier dependencies
  - Post Cache Go binaries
  - Post Run actions/setup-go@v5
  ✓ Post Install dependencies
  - Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* qualify-ci / test (3.14) (ID 130121174714)
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
* qualify-ci / test (3.13) (ID 130121174802)
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
* qualify-ci / test (3.12) (ID 130121174849)
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
✓ qualify-ci / ace-page-group-isolation in 1m37s (ID 130121174850)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  ✓ Run ACE shared-page isolation lane
  ✓ Post Install visual dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
identity: .github#7

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
identity: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
build: .github#4

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0sIHzagAAAAB30fM6H9ufTppmpzFOLFMkUEhMMzBFREdFMDEwOABFZGdl
build: .github#7

! Failed to restore: Cache service responded with 400
build: .github#24

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
build: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-prepare: .github#9

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-prepare: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
exercise-legs (macos-latest, wheel): .github#2

- Due to capacity constraints, jobs targeting macOS arm64 runners may experience longer queue times.
exercise-legs (macos-latest, wheel): .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
exercise-legs (ubuntu-latest, sdist): .github#2

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
exercise-legs (ubuntu-latest, sdist): .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
exercise-legs (ubuntu-latest, wheel): .github#2

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
exercise-legs (ubuntu-latest, wheel): .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
exercise-legs (macos-latest, sdist): .github#2

- Due to capacity constraints, jobs targeting macOS arm64 runners may experience longer queue times.
exercise-legs (macos-latest, sdist): .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / prepare: .github#10

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / prepare: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / build-core / build-core: .github#5

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>09YPzagAAAAAiPR5XKRSoQpRg352ExmJxQ0gxQUEyMDMwODE0MDYwAEVkZ2U=
qualify-ci / build-core / build-core: .github#7

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / tutorial-tests: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0OITzagAAAACMpVdYEU0wTYGlMGZQR9ksQ0gxQUEyMDMwODEzMDYwAEVkZ2U=
qualify-ci / tutorial-tests: .github#9

! Failed to restore: Cache service responded with 400
qualify-ci / tutorial-tests: .github#49

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / tutorial-tests: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache@v4, actions/checkout@v4, actions/download-artifact@v4, actions/setup-go@v5, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / lint: .github#2

X Process completed with exit code 1.
qualify-ci / lint: .github#16

! Failed to restore: Cache service responded with 400
qualify-ci / lint: .github#52

! Failed to restore: Cache service responded with 400
qualify-ci / lint: .github#24

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / lint: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / ace-page-group-isolation: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0WITzagAAAAAzCcEmW9wlRq5yhIB141iuQ0gxQUEyMDMwODEzMDI1AEVkZ2U=
qualify-ci / ace-page-group-isolation: .github#9

! Failed to restore: Cache service responded with 400
qualify-ci / ace-page-group-isolation: .github#49

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / ace-page-group-isolation: .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* release-please--branches--master Release sase-org/sase#322 · 42897628895
Triggered via workflow_dispatch about 19 minutes ago

JOBS
✓ identity in 57s (ID 130114862321)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Assert source and version identity
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ build in 38s (ID 130115420556)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up Python
  ✓ Build once and check the dist set
  ✓ Resolve the exact core pin
  ✓ Fetch the core file list and digests
  ✓ Read the core completeness set at the pin's tag
  ✓ Prove the core tag contains the source pin
  ✓ Seal the candidate manifest
  ✓ Upload the candidate build
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ qualify-prepare in 26s (ID 130115802507)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Download the sealed candidate build
  ✓ Bind the sealed candidate identity
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ exercise-legs (macos-latest, wheel) in 2m5s (ID 130115802596)
  ✓ Set up job
  ✓ Refuse probes outside rehearse
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up Python
  ✓ Ensure tmux for the TUI frame
  ✓ Download the sealed build
  ✓ Resolve the leg dist and manifest fields
  ✓ Verify digests before install
  ✓ Prepare the isolated leg environment
  ✓ Resolve the previous installable PyPI release
  ✓ Run the exercise leg
  ✓ Upload the leg evidence
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ exercise-legs (ubuntu-latest, sdist) in 54s (ID 130115802632)
  ✓ Set up job
  ✓ Refuse probes outside rehearse
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up Python
  - Ensure tmux for the TUI frame
  ✓ Download the sealed build
  ✓ Resolve the leg dist and manifest fields
  ✓ Verify digests before install
  ✓ Prepare the isolated leg environment
  - Resolve the previous installable PyPI release
  ✓ Run the exercise leg
  ✓ Upload the leg evidence
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ exercise-legs (ubuntu-latest, wheel) in 1m8s (ID 130115802657)
  ✓ Set up job
  ✓ Refuse probes outside rehearse
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up Python
  - Ensure tmux for the TUI frame
  ✓ Download the sealed build
  ✓ Resolve the leg dist and manifest fields
  ✓ Verify digests before install
  ✓ Prepare the isolated leg environment
  ✓ Resolve the previous installable PyPI release
  ✓ Run the exercise leg
  ✓ Upload the leg evidence
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ exercise-legs (macos-latest, sdist) in 1m18s (ID 130115802821)
  ✓ Set up job
  ✓ Refuse probes outside rehearse
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up Python
  ✓ Ensure tmux for the TUI frame
  ✓ Download the sealed build
  ✓ Resolve the leg dist and manifest fields
  ✓ Verify digests before install
  ✓ Prepare the isolated leg environment
  - Resolve the previous installable PyPI release
  ✓ Run the exercise leg
  ✓ Upload the leg evidence
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
- stash (ID 130115805318)
✓ qualify-ci / prepare in 26s (ID 130116069325)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Validate qualification inputs
  ✓ Download the sealed candidate manifest
  ✓ Bind published identity from the sealed manifest
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
- qualify-ci / release-core-floor-smoke (ID 130116071518)
- qualify-ci / docs-build (ID 130116072055)
✓ qualify-ci / build-core / build-core in 8m41s (ID 130116334196)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Resolve core mode
  - Resolve pinned Rust core revision
  - Check out Rust core
  ✓ Check out published Rust core tag
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up Rust
  ✓ Cache Rust build
  - Build abi3 Rust core wheel
  ✓ Download the sealed candidate manifest
  ✓ Fetch and verify the published core wheel
  ✓ Build macro LSP
  - Record wheel provenance
  ✓ Record published tag provenance
  ✓ Upload Rust core artifacts
  ✓ Post Cache Rust build
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Check out published Rust core tag
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ exercise in 27s (ID 130117005549)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Download the sealed build
  ✓ Download the leg evidence
  ✓ Merge the legs into one exercise observation
  - Stash the exercise observation on the draft release
  ✓ Upload the exercise observation artifact
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* qualify-ci / perf-floors (ID 130121174612)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Health check (Rust extension loadable)
  ✓ Run slow tests
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
✓ qualify-ci / tutorial-tests in 1m4s (ID 130121174619)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run tutorial tests
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* qualify-ci / visual-test (ID 130121174667)
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
X qualify-ci / lint in 1m31s (ID 130121174682)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up preflight Python
  ✓ Download Rust core artifacts for bindings preflight
  ✓ Preflight core bindings
  ✓ Install dependencies
  ✓ Check pinned core bindings
  ✓ Bootstrap SDD sidecars
  ✓ Initialize SASE home
  ✓ Run actions/setup-go@v5
  ✓ Cache Go binaries
  - Install Go tools (keep-sorted)
  ✓ Cache Prettier dependencies
  ✓ Check Python formatting
  ✓ Check Markdown formatting
  X Check generated model docs
  - Check shipped model policy
  - Lint
  - SASE validation
  - Validate committed plans
  - Build and verify package
  ✓ Record installed core version
  ✓ Write qualification evidence
  ✓ Upload qualification evidence
  - Post Cache Prettier dependencies
  - Post Cache Go binaries
  - Post Run actions/setup-go@v5
  ✓ Post Install dependencies
  - Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* qualify-ci / test (3.14) (ID 130121174714)
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
* qualify-ci / test (3.13) (ID 130121174802)
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
* qualify-ci / test (3.12) (ID 130121174849)
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
✓ qualify-ci / ace-page-group-isolation in 1m37s (ID 130121174850)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  ✓ Run ACE shared-page isolation lane
  ✓ Post Install visual dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
identity: .github#7

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
identity: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
build: .github#4

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0sIHzagAAAAB30fM6H9ufTppmpzFOLFMkUEhMMzBFREdFMDEwOABFZGdl
build: .github#7

! Failed to restore: Cache service responded with 400
build: .github#24

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
build: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-prepare: .github#9

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-prepare: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
exercise-legs (macos-latest, wheel): .github#2

- Due to capacity constraints, jobs targeting macOS arm64 runners may experience longer queue times.
exercise-legs (macos-latest, wheel): .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
exercise-legs (ubuntu-latest, sdist): .github#2

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
exercise-legs (ubuntu-latest, sdist): .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
exercise-legs (ubuntu-latest, wheel): .github#2

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
exercise-legs (ubuntu-latest, wheel): .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
exercise-legs (macos-latest, sdist): .github#2

- Due to capacity constraints, jobs targeting macOS arm64 runners may experience longer queue times.
exercise-legs (macos-latest, sdist): .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / prepare: .github#10

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / prepare: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / build-core / build-core: .github#5

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>09YPzagAAAAAiPR5XKRSoQpRg352ExmJxQ0gxQUEyMDMwODE0MDYwAEVkZ2U=
qualify-ci / build-core / build-core: .github#7

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / tutorial-tests: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0OITzagAAAACMpVdYEU0wTYGlMGZQR9ksQ0gxQUEyMDMwODEzMDYwAEVkZ2U=
qualify-ci / tutorial-tests: .github#9

! Failed to restore: Cache service responded with 400
qualify-ci / tutorial-tests: .github#49

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / tutorial-tests: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache@v4, actions/checkout@v4, actions/download-artifact@v4, actions/setup-go@v5, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / lint: .github#2

X Process completed with exit code 1.
qualify-ci / lint: .github#16

! Failed to restore: Cache service responded with 400
qualify-ci / lint: .github#52

! Failed to restore: Cache service responded with 400
qualify-ci / lint: .github#24

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / lint: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / ace-page-group-isolation: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0WITzagAAAAAzCcEmW9wlRq5yhIB141iuQ0gxQUEyMDMwODEzMDI1AEVkZ2U=
qualify-ci / ace-page-group-isolation: .github#9

! Failed to restore: Cache service responded with 400
qualify-ci / ace-page-group-isolation: .github#49

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / ace-page-group-isolation: .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* release-please--branches--master Release sase-org/sase#322 · 42897628895
Triggered via workflow_dispatch about 21 minutes ago

JOBS
✓ identity in 57s (ID 130114862321)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Assert source and version identity
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ build in 38s (ID 130115420556)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up Python
  ✓ Build once and check the dist set
  ✓ Resolve the exact core pin
  ✓ Fetch the core file list and digests
  ✓ Read the core completeness set at the pin's tag
  ✓ Prove the core tag contains the source pin
  ✓ Seal the candidate manifest
  ✓ Upload the candidate build
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ qualify-prepare in 26s (ID 130115802507)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Download the sealed candidate build
  ✓ Bind the sealed candidate identity
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ exercise-legs (macos-latest, wheel) in 2m5s (ID 130115802596)
  ✓ Set up job
  ✓ Refuse probes outside rehearse
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up Python
  ✓ Ensure tmux for the TUI frame
  ✓ Download the sealed build
  ✓ Resolve the leg dist and manifest fields
  ✓ Verify digests before install
  ✓ Prepare the isolated leg environment
  ✓ Resolve the previous installable PyPI release
  ✓ Run the exercise leg
  ✓ Upload the leg evidence
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ exercise-legs (ubuntu-latest, sdist) in 54s (ID 130115802632)
  ✓ Set up job
  ✓ Refuse probes outside rehearse
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up Python
  - Ensure tmux for the TUI frame
  ✓ Download the sealed build
  ✓ Resolve the leg dist and manifest fields
  ✓ Verify digests before install
  ✓ Prepare the isolated leg environment
  - Resolve the previous installable PyPI release
  ✓ Run the exercise leg
  ✓ Upload the leg evidence
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ exercise-legs (ubuntu-latest, wheel) in 1m8s (ID 130115802657)
  ✓ Set up job
  ✓ Refuse probes outside rehearse
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up Python
  - Ensure tmux for the TUI frame
  ✓ Download the sealed build
  ✓ Resolve the leg dist and manifest fields
  ✓ Verify digests before install
  ✓ Prepare the isolated leg environment
  ✓ Resolve the previous installable PyPI release
  ✓ Run the exercise leg
  ✓ Upload the leg evidence
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ exercise-legs (macos-latest, sdist) in 1m18s (ID 130115802821)
  ✓ Set up job
  ✓ Refuse probes outside rehearse
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up Python
  ✓ Ensure tmux for the TUI frame
  ✓ Download the sealed build
  ✓ Resolve the leg dist and manifest fields
  ✓ Verify digests before install
  ✓ Prepare the isolated leg environment
  - Resolve the previous installable PyPI release
  ✓ Run the exercise leg
  ✓ Upload the leg evidence
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
- stash (ID 130115805318)
✓ qualify-ci / prepare in 26s (ID 130116069325)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Validate qualification inputs
  ✓ Download the sealed candidate manifest
  ✓ Bind published identity from the sealed manifest
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
- qualify-ci / release-core-floor-smoke (ID 130116071518)
- qualify-ci / docs-build (ID 130116072055)
✓ qualify-ci / build-core / build-core in 8m41s (ID 130116334196)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Resolve core mode
  - Resolve pinned Rust core revision
  - Check out Rust core
  ✓ Check out published Rust core tag
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up Rust
  ✓ Cache Rust build
  - Build abi3 Rust core wheel
  ✓ Download the sealed candidate manifest
  ✓ Fetch and verify the published core wheel
  ✓ Build macro LSP
  - Record wheel provenance
  ✓ Record published tag provenance
  ✓ Upload Rust core artifacts
  ✓ Post Cache Rust build
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Check out published Rust core tag
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ exercise in 27s (ID 130117005549)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Download the sealed build
  ✓ Download the leg evidence
  ✓ Merge the legs into one exercise observation
  - Stash the exercise observation on the draft release
  ✓ Upload the exercise observation artifact
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* qualify-ci / perf-floors (ID 130121174612)
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
  * Run bead history-independence gate (1x+4x)
  * Upload bead history-independence gate report
  * Post Install dependencies
  * Post Run actions/checkout@v4
✓ qualify-ci / tutorial-tests in 1m4s (ID 130121174619)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run tutorial tests
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* qualify-ci / visual-test (ID 130121174667)
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
X qualify-ci / lint in 1m31s (ID 130121174682)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up preflight Python
  ✓ Download Rust core artifacts for bindings preflight
  ✓ Preflight core bindings
  ✓ Install dependencies
  ✓ Check pinned core bindings
  ✓ Bootstrap SDD sidecars
  ✓ Initialize SASE home
  ✓ Run actions/setup-go@v5
  ✓ Cache Go binaries
  - Install Go tools (keep-sorted)
  ✓ Cache Prettier dependencies
  ✓ Check Python formatting
  ✓ Check Markdown formatting
  X Check generated model docs
  - Check shipped model policy
  - Lint
  - SASE validation
  - Validate committed plans
  - Build and verify package
  ✓ Record installed core version
  ✓ Write qualification evidence
  ✓ Upload qualification evidence
  - Post Cache Prettier dependencies
  - Post Cache Go binaries
  - Post Run actions/setup-go@v5
  ✓ Post Install dependencies
  - Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* qualify-ci / test (3.14) (ID 130121174714)
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
* qualify-ci / test (3.13) (ID 130121174802)
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
* qualify-ci / test (3.12) (ID 130121174849)
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
✓ qualify-ci / ace-page-group-isolation in 1m37s (ID 130121174850)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  ✓ Run ACE shared-page isolation lane
  ✓ Post Install visual dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
identity: .github#7

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
identity: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
build: .github#4

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0sIHzagAAAAB30fM6H9ufTppmpzFOLFMkUEhMMzBFREdFMDEwOABFZGdl
build: .github#7

! Failed to restore: Cache service responded with 400
build: .github#24

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
build: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-prepare: .github#9

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-prepare: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
exercise-legs (macos-latest, wheel): .github#2

- Due to capacity constraints, jobs targeting macOS arm64 runners may experience longer queue times.
exercise-legs (macos-latest, wheel): .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
exercise-legs (ubuntu-latest, sdist): .github#2

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
exercise-legs (ubuntu-latest, sdist): .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
exercise-legs (ubuntu-latest, wheel): .github#2

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
exercise-legs (ubuntu-latest, wheel): .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
exercise-legs (macos-latest, sdist): .github#2

- Due to capacity constraints, jobs targeting macOS arm64 runners may experience longer queue times.
exercise-legs (macos-latest, sdist): .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / prepare: .github#10

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / prepare: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / build-core / build-core: .github#5

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>09YPzagAAAAAiPR5XKRSoQpRg352ExmJxQ0gxQUEyMDMwODE0MDYwAEVkZ2U=
qualify-ci / build-core / build-core: .github#7

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / tutorial-tests: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0OITzagAAAACMpVdYEU0wTYGlMGZQR9ksQ0gxQUEyMDMwODEzMDYwAEVkZ2U=
qualify-ci / tutorial-tests: .github#9

! Failed to restore: Cache service responded with 400
qualify-ci / tutorial-tests: .github#49

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / tutorial-tests: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache@v4, actions/checkout@v4, actions/download-artifact@v4, actions/setup-go@v5, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / lint: .github#2

X Process completed with exit code 1.
qualify-ci / lint: .github#16

! Failed to restore: Cache service responded with 400
qualify-ci / lint: .github#52

! Failed to restore: Cache service responded with 400
qualify-ci / lint: .github#24

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / lint: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / ace-page-group-isolation: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0WITzagAAAAAzCcEmW9wlRq5yhIB141iuQ0gxQUEyMDMwODEzMDI1AEVkZ2U=
qualify-ci / ace-page-group-isolation: .github#9

! Failed to restore: Cache service responded with 400
qualify-ci / ace-page-group-isolation: .github#49

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / ace-page-group-isolation: .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* release-please--branches--master Release sase-org/sase#322 · 42897628895
Triggered via workflow_dispatch about 23 minutes ago

JOBS
✓ identity in 57s (ID 130114862321)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Assert source and version identity
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ build in 38s (ID 130115420556)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up Python
  ✓ Build once and check the dist set
  ✓ Resolve the exact core pin
  ✓ Fetch the core file list and digests
  ✓ Read the core completeness set at the pin's tag
  ✓ Prove the core tag contains the source pin
  ✓ Seal the candidate manifest
  ✓ Upload the candidate build
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ qualify-prepare in 26s (ID 130115802507)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Download the sealed candidate build
  ✓ Bind the sealed candidate identity
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ exercise-legs (macos-latest, wheel) in 2m5s (ID 130115802596)
  ✓ Set up job
  ✓ Refuse probes outside rehearse
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up Python
  ✓ Ensure tmux for the TUI frame
  ✓ Download the sealed build
  ✓ Resolve the leg dist and manifest fields
  ✓ Verify digests before install
  ✓ Prepare the isolated leg environment
  ✓ Resolve the previous installable PyPI release
  ✓ Run the exercise leg
  ✓ Upload the leg evidence
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ exercise-legs (ubuntu-latest, sdist) in 54s (ID 130115802632)
  ✓ Set up job
  ✓ Refuse probes outside rehearse
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up Python
  - Ensure tmux for the TUI frame
  ✓ Download the sealed build
  ✓ Resolve the leg dist and manifest fields
  ✓ Verify digests before install
  ✓ Prepare the isolated leg environment
  - Resolve the previous installable PyPI release
  ✓ Run the exercise leg
  ✓ Upload the leg evidence
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ exercise-legs (ubuntu-latest, wheel) in 1m8s (ID 130115802657)
  ✓ Set up job
  ✓ Refuse probes outside rehearse
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up Python
  - Ensure tmux for the TUI frame
  ✓ Download the sealed build
  ✓ Resolve the leg dist and manifest fields
  ✓ Verify digests before install
  ✓ Prepare the isolated leg environment
  ✓ Resolve the previous installable PyPI release
  ✓ Run the exercise leg
  ✓ Upload the leg evidence
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ exercise-legs (macos-latest, sdist) in 1m18s (ID 130115802821)
  ✓ Set up job
  ✓ Refuse probes outside rehearse
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up Python
  ✓ Ensure tmux for the TUI frame
  ✓ Download the sealed build
  ✓ Resolve the leg dist and manifest fields
  ✓ Verify digests before install
  ✓ Prepare the isolated leg environment
  - Resolve the previous installable PyPI release
  ✓ Run the exercise leg
  ✓ Upload the leg evidence
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
- stash (ID 130115805318)
✓ qualify-ci / prepare in 26s (ID 130116069325)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Validate qualification inputs
  ✓ Download the sealed candidate manifest
  ✓ Bind published identity from the sealed manifest
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
- qualify-ci / release-core-floor-smoke (ID 130116071518)
- qualify-ci / docs-build (ID 130116072055)
✓ qualify-ci / build-core / build-core in 8m41s (ID 130116334196)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Resolve core mode
  - Resolve pinned Rust core revision
  - Check out Rust core
  ✓ Check out published Rust core tag
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up Rust
  ✓ Cache Rust build
  - Build abi3 Rust core wheel
  ✓ Download the sealed candidate manifest
  ✓ Fetch and verify the published core wheel
  ✓ Build macro LSP
  - Record wheel provenance
  ✓ Record published tag provenance
  ✓ Upload Rust core artifacts
  ✓ Post Cache Rust build
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Check out published Rust core tag
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ exercise in 27s (ID 130117005549)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Download the sealed build
  ✓ Download the leg evidence
  ✓ Merge the legs into one exercise observation
  - Stash the exercise observation on the draft release
  ✓ Upload the exercise observation artifact
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ qualify-ci / perf-floors in 9m50s (ID 130121174612)
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
✓ qualify-ci / tutorial-tests in 1m4s (ID 130121174619)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run tutorial tests
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* qualify-ci / visual-test (ID 130121174667)
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
X qualify-ci / lint in 1m31s (ID 130121174682)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up preflight Python
  ✓ Download Rust core artifacts for bindings preflight
  ✓ Preflight core bindings
  ✓ Install dependencies
  ✓ Check pinned core bindings
  ✓ Bootstrap SDD sidecars
  ✓ Initialize SASE home
  ✓ Run actions/setup-go@v5
  ✓ Cache Go binaries
  - Install Go tools (keep-sorted)
  ✓ Cache Prettier dependencies
  ✓ Check Python formatting
  ✓ Check Markdown formatting
  X Check generated model docs
  - Check shipped model policy
  - Lint
  - SASE validation
  - Validate committed plans
  - Build and verify package
  ✓ Record installed core version
  ✓ Write qualification evidence
  ✓ Upload qualification evidence
  - Post Cache Prettier dependencies
  - Post Cache Go binaries
  - Post Run actions/setup-go@v5
  ✓ Post Install dependencies
  - Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* qualify-ci / test (3.14) (ID 130121174714)
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
* qualify-ci / test (3.13) (ID 130121174802)
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
* qualify-ci / test (3.12) (ID 130121174849)
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
✓ qualify-ci / ace-page-group-isolation in 1m37s (ID 130121174850)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  ✓ Run ACE shared-page isolation lane
  ✓ Post Install visual dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
identity: .github#7

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
identity: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
build: .github#4

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0sIHzagAAAAB30fM6H9ufTppmpzFOLFMkUEhMMzBFREdFMDEwOABFZGdl
build: .github#7

! Failed to restore: Cache service responded with 400
build: .github#24

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
build: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-prepare: .github#9

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-prepare: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
exercise-legs (macos-latest, wheel): .github#2

- Due to capacity constraints, jobs targeting macOS arm64 runners may experience longer queue times.
exercise-legs (macos-latest, wheel): .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
exercise-legs (ubuntu-latest, sdist): .github#2

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
exercise-legs (ubuntu-latest, sdist): .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
exercise-legs (ubuntu-latest, wheel): .github#2

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
exercise-legs (ubuntu-latest, wheel): .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
exercise-legs (macos-latest, sdist): .github#2

- Due to capacity constraints, jobs targeting macOS arm64 runners may experience longer queue times.
exercise-legs (macos-latest, sdist): .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / prepare: .github#10

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / prepare: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / build-core / build-core: .github#5

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>09YPzagAAAAAiPR5XKRSoQpRg352ExmJxQ0gxQUEyMDMwODE0MDYwAEVkZ2U=
qualify-ci / build-core / build-core: .github#7

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / tutorial-tests: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0OITzagAAAACMpVdYEU0wTYGlMGZQR9ksQ0gxQUEyMDMwODEzMDYwAEVkZ2U=
qualify-ci / tutorial-tests: .github#9

! Failed to restore: Cache service responded with 400
qualify-ci / tutorial-tests: .github#49

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / tutorial-tests: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache@v4, actions/checkout@v4, actions/download-artifact@v4, actions/setup-go@v5, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / lint: .github#2

X Process completed with exit code 1.
qualify-ci / lint: .github#16

! Failed to restore: Cache service responded with 400
qualify-ci / lint: .github#52

! Failed to restore: Cache service responded with 400
qualify-ci / lint: .github#24

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / lint: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / ace-page-group-isolation: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0WITzagAAAAAzCcEmW9wlRq5yhIB141iuQ0gxQUEyMDMwODEzMDI1AEVkZ2U=
qualify-ci / ace-page-group-isolation: .github#9

! Failed to restore: Cache service responded with 400
qualify-ci / ace-page-group-isolation: .github#49

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / ace-page-group-isolation: .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* release-please--branches--master Release sase-org/sase#322 · 42897628895
Triggered via workflow_dispatch about 25 minutes ago

JOBS
✓ identity in 57s (ID 130114862321)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Assert source and version identity
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ build in 38s (ID 130115420556)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up Python
  ✓ Build once and check the dist set
  ✓ Resolve the exact core pin
  ✓ Fetch the core file list and digests
  ✓ Read the core completeness set at the pin's tag
  ✓ Prove the core tag contains the source pin
  ✓ Seal the candidate manifest
  ✓ Upload the candidate build
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ qualify-prepare in 26s (ID 130115802507)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Download the sealed candidate build
  ✓ Bind the sealed candidate identity
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ exercise-legs (macos-latest, wheel) in 2m5s (ID 130115802596)
  ✓ Set up job
  ✓ Refuse probes outside rehearse
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up Python
  ✓ Ensure tmux for the TUI frame
  ✓ Download the sealed build
  ✓ Resolve the leg dist and manifest fields
  ✓ Verify digests before install
  ✓ Prepare the isolated leg environment
  ✓ Resolve the previous installable PyPI release
  ✓ Run the exercise leg
  ✓ Upload the leg evidence
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ exercise-legs (ubuntu-latest, sdist) in 54s (ID 130115802632)
  ✓ Set up job
  ✓ Refuse probes outside rehearse
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up Python
  - Ensure tmux for the TUI frame
  ✓ Download the sealed build
  ✓ Resolve the leg dist and manifest fields
  ✓ Verify digests before install
  ✓ Prepare the isolated leg environment
  - Resolve the previous installable PyPI release
  ✓ Run the exercise leg
  ✓ Upload the leg evidence
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ exercise-legs (ubuntu-latest, wheel) in 1m8s (ID 130115802657)
  ✓ Set up job
  ✓ Refuse probes outside rehearse
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up Python
  - Ensure tmux for the TUI frame
  ✓ Download the sealed build
  ✓ Resolve the leg dist and manifest fields
  ✓ Verify digests before install
  ✓ Prepare the isolated leg environment
  ✓ Resolve the previous installable PyPI release
  ✓ Run the exercise leg
  ✓ Upload the leg evidence
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ exercise-legs (macos-latest, sdist) in 1m18s (ID 130115802821)
  ✓ Set up job
  ✓ Refuse probes outside rehearse
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up Python
  ✓ Ensure tmux for the TUI frame
  ✓ Download the sealed build
  ✓ Resolve the leg dist and manifest fields
  ✓ Verify digests before install
  ✓ Prepare the isolated leg environment
  - Resolve the previous installable PyPI release
  ✓ Run the exercise leg
  ✓ Upload the leg evidence
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
- stash (ID 130115805318)
✓ qualify-ci / prepare in 26s (ID 130116069325)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Validate qualification inputs
  ✓ Download the sealed candidate manifest
  ✓ Bind published identity from the sealed manifest
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
- qualify-ci / release-core-floor-smoke (ID 130116071518)
- qualify-ci / docs-build (ID 130116072055)
✓ qualify-ci / build-core / build-core in 8m41s (ID 130116334196)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Resolve core mode
  - Resolve pinned Rust core revision
  - Check out Rust core
  ✓ Check out published Rust core tag
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up Rust
  ✓ Cache Rust build
  - Build abi3 Rust core wheel
  ✓ Download the sealed candidate manifest
  ✓ Fetch and verify the published core wheel
  ✓ Build macro LSP
  - Record wheel provenance
  ✓ Record published tag provenance
  ✓ Upload Rust core artifacts
  ✓ Post Cache Rust build
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Check out published Rust core tag
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ exercise in 27s (ID 130117005549)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Download the sealed build
  ✓ Download the leg evidence
  ✓ Merge the legs into one exercise observation
  - Stash the exercise observation on the draft release
  ✓ Upload the exercise observation artifact
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ qualify-ci / perf-floors in 9m50s (ID 130121174612)
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
✓ qualify-ci / tutorial-tests in 1m4s (ID 130121174619)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run tutorial tests
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* qualify-ci / visual-test (ID 130121174667)
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
X qualify-ci / lint in 1m31s (ID 130121174682)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up preflight Python
  ✓ Download Rust core artifacts for bindings preflight
  ✓ Preflight core bindings
  ✓ Install dependencies
  ✓ Check pinned core bindings
  ✓ Bootstrap SDD sidecars
  ✓ Initialize SASE home
  ✓ Run actions/setup-go@v5
  ✓ Cache Go binaries
  - Install Go tools (keep-sorted)
  ✓ Cache Prettier dependencies
  ✓ Check Python formatting
  ✓ Check Markdown formatting
  X Check generated model docs
  - Check shipped model policy
  - Lint
  - SASE validation
  - Validate committed plans
  - Build and verify package
  ✓ Record installed core version
  ✓ Write qualification evidence
  ✓ Upload qualification evidence
  - Post Cache Prettier dependencies
  - Post Cache Go binaries
  - Post Run actions/setup-go@v5
  ✓ Post Install dependencies
  - Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* qualify-ci / test (3.14) (ID 130121174714)
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
* qualify-ci / test (3.13) (ID 130121174802)
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
* qualify-ci / test (3.12) (ID 130121174849)
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
✓ qualify-ci / ace-page-group-isolation in 1m37s (ID 130121174850)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  ✓ Run ACE shared-page isolation lane
  ✓ Post Install visual dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
identity: .github#7

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
identity: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
build: .github#4

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0sIHzagAAAAB30fM6H9ufTppmpzFOLFMkUEhMMzBFREdFMDEwOABFZGdl
build: .github#7

! Failed to restore: Cache service responded with 400
build: .github#24

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
build: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-prepare: .github#9

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-prepare: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
exercise-legs (macos-latest, wheel): .github#2

- Due to capacity constraints, jobs targeting macOS arm64 runners may experience longer queue times.
exercise-legs (macos-latest, wheel): .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
exercise-legs (ubuntu-latest, sdist): .github#2

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
exercise-legs (ubuntu-latest, sdist): .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
exercise-legs (ubuntu-latest, wheel): .github#2

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
exercise-legs (ubuntu-latest, wheel): .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
exercise-legs (macos-latest, sdist): .github#2

- Due to capacity constraints, jobs targeting macOS arm64 runners may experience longer queue times.
exercise-legs (macos-latest, sdist): .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / prepare: .github#10

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / prepare: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / build-core / build-core: .github#5

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>09YPzagAAAAAiPR5XKRSoQpRg352ExmJxQ0gxQUEyMDMwODE0MDYwAEVkZ2U=
qualify-ci / build-core / build-core: .github#7

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / tutorial-tests: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0OITzagAAAACMpVdYEU0wTYGlMGZQR9ksQ0gxQUEyMDMwODEzMDYwAEVkZ2U=
qualify-ci / tutorial-tests: .github#9

! Failed to restore: Cache service responded with 400
qualify-ci / tutorial-tests: .github#49

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / tutorial-tests: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache@v4, actions/checkout@v4, actions/download-artifact@v4, actions/setup-go@v5, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / lint: .github#2

X Process completed with exit code 1.
qualify-ci / lint: .github#16

! Failed to restore: Cache service responded with 400
qualify-ci / lint: .github#52

! Failed to restore: Cache service responded with 400
qualify-ci / lint: .github#24

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / lint: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / ace-page-group-isolation: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0WITzagAAAAAzCcEmW9wlRq5yhIB141iuQ0gxQUEyMDMwODEzMDI1AEVkZ2U=
qualify-ci / ace-page-group-isolation: .github#9

! Failed to restore: Cache service responded with 400
qualify-ci / ace-page-group-isolation: .github#49

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / ace-page-group-isolation: .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* release-please--branches--master Release sase-org/sase#322 · 42897628895
Triggered via workflow_dispatch about 27 minutes ago

JOBS
✓ identity in 57s (ID 130114862321)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Assert source and version identity
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ build in 38s (ID 130115420556)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up Python
  ✓ Build once and check the dist set
  ✓ Resolve the exact core pin
  ✓ Fetch the core file list and digests
  ✓ Read the core completeness set at the pin's tag
  ✓ Prove the core tag contains the source pin
  ✓ Seal the candidate manifest
  ✓ Upload the candidate build
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ qualify-prepare in 26s (ID 130115802507)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Download the sealed candidate build
  ✓ Bind the sealed candidate identity
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ exercise-legs (macos-latest, wheel) in 2m5s (ID 130115802596)
  ✓ Set up job
  ✓ Refuse probes outside rehearse
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up Python
  ✓ Ensure tmux for the TUI frame
  ✓ Download the sealed build
  ✓ Resolve the leg dist and manifest fields
  ✓ Verify digests before install
  ✓ Prepare the isolated leg environment
  ✓ Resolve the previous installable PyPI release
  ✓ Run the exercise leg
  ✓ Upload the leg evidence
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ exercise-legs (ubuntu-latest, sdist) in 54s (ID 130115802632)
  ✓ Set up job
  ✓ Refuse probes outside rehearse
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up Python
  - Ensure tmux for the TUI frame
  ✓ Download the sealed build
  ✓ Resolve the leg dist and manifest fields
  ✓ Verify digests before install
  ✓ Prepare the isolated leg environment
  - Resolve the previous installable PyPI release
  ✓ Run the exercise leg
  ✓ Upload the leg evidence
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ exercise-legs (ubuntu-latest, wheel) in 1m8s (ID 130115802657)
  ✓ Set up job
  ✓ Refuse probes outside rehearse
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up Python
  - Ensure tmux for the TUI frame
  ✓ Download the sealed build
  ✓ Resolve the leg dist and manifest fields
  ✓ Verify digests before install
  ✓ Prepare the isolated leg environment
  ✓ Resolve the previous installable PyPI release
  ✓ Run the exercise leg
  ✓ Upload the leg evidence
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ exercise-legs (macos-latest, sdist) in 1m18s (ID 130115802821)
  ✓ Set up job
  ✓ Refuse probes outside rehearse
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up Python
  ✓ Ensure tmux for the TUI frame
  ✓ Download the sealed build
  ✓ Resolve the leg dist and manifest fields
  ✓ Verify digests before install
  ✓ Prepare the isolated leg environment
  - Resolve the previous installable PyPI release
  ✓ Run the exercise leg
  ✓ Upload the leg evidence
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
- stash (ID 130115805318)
✓ qualify-ci / prepare in 26s (ID 130116069325)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Validate qualification inputs
  ✓ Download the sealed candidate manifest
  ✓ Bind published identity from the sealed manifest
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
- qualify-ci / release-core-floor-smoke (ID 130116071518)
- qualify-ci / docs-build (ID 130116072055)
✓ qualify-ci / build-core / build-core in 8m41s (ID 130116334196)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Resolve core mode
  - Resolve pinned Rust core revision
  - Check out Rust core
  ✓ Check out published Rust core tag
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up Rust
  ✓ Cache Rust build
  - Build abi3 Rust core wheel
  ✓ Download the sealed candidate manifest
  ✓ Fetch and verify the published core wheel
  ✓ Build macro LSP
  - Record wheel provenance
  ✓ Record published tag provenance
  ✓ Upload Rust core artifacts
  ✓ Post Cache Rust build
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Check out published Rust core tag
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ exercise in 27s (ID 130117005549)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Download the sealed build
  ✓ Download the leg evidence
  ✓ Merge the legs into one exercise observation
  - Stash the exercise observation on the draft release
  ✓ Upload the exercise observation artifact
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ qualify-ci / perf-floors in 9m50s (ID 130121174612)
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
✓ qualify-ci / tutorial-tests in 1m4s (ID 130121174619)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run tutorial tests
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* qualify-ci / visual-test (ID 130121174667)
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
X qualify-ci / lint in 1m31s (ID 130121174682)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up preflight Python
  ✓ Download Rust core artifacts for bindings preflight
  ✓ Preflight core bindings
  ✓ Install dependencies
  ✓ Check pinned core bindings
  ✓ Bootstrap SDD sidecars
  ✓ Initialize SASE home
  ✓ Run actions/setup-go@v5
  ✓ Cache Go binaries
  - Install Go tools (keep-sorted)
  ✓ Cache Prettier dependencies
  ✓ Check Python formatting
  ✓ Check Markdown formatting
  X Check generated model docs
  - Check shipped model policy
  - Lint
  - SASE validation
  - Validate committed plans
  - Build and verify package
  ✓ Record installed core version
  ✓ Write qualification evidence
  ✓ Upload qualification evidence
  - Post Cache Prettier dependencies
  - Post Cache Go binaries
  - Post Run actions/setup-go@v5
  ✓ Post Install dependencies
  - Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* qualify-ci / test (3.14) (ID 130121174714)
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
* qualify-ci / test (3.13) (ID 130121174802)
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
* qualify-ci / test (3.12) (ID 130121174849)
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
✓ qualify-ci / ace-page-group-isolation in 1m37s (ID 130121174850)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  ✓ Run ACE shared-page isolation lane
  ✓ Post Install visual dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
identity: .github#7

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
identity: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
build: .github#4

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0sIHzagAAAAB30fM6H9ufTppmpzFOLFMkUEhMMzBFREdFMDEwOABFZGdl
build: .github#7

! Failed to restore: Cache service responded with 400
build: .github#24

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
build: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-prepare: .github#9

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-prepare: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
exercise-legs (macos-latest, wheel): .github#2

- Due to capacity constraints, jobs targeting macOS arm64 runners may experience longer queue times.
exercise-legs (macos-latest, wheel): .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
exercise-legs (ubuntu-latest, sdist): .github#2

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
exercise-legs (ubuntu-latest, sdist): .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
exercise-legs (ubuntu-latest, wheel): .github#2

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
exercise-legs (ubuntu-latest, wheel): .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
exercise-legs (macos-latest, sdist): .github#2

- Due to capacity constraints, jobs targeting macOS arm64 runners may experience longer queue times.
exercise-legs (macos-latest, sdist): .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / prepare: .github#10

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / prepare: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / build-core / build-core: .github#5

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>09YPzagAAAAAiPR5XKRSoQpRg352ExmJxQ0gxQUEyMDMwODE0MDYwAEVkZ2U=
qualify-ci / build-core / build-core: .github#7

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / tutorial-tests: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0OITzagAAAACMpVdYEU0wTYGlMGZQR9ksQ0gxQUEyMDMwODEzMDYwAEVkZ2U=
qualify-ci / tutorial-tests: .github#9

! Failed to restore: Cache service responded with 400
qualify-ci / tutorial-tests: .github#49

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / tutorial-tests: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache@v4, actions/checkout@v4, actions/download-artifact@v4, actions/setup-go@v5, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / lint: .github#2

X Process completed with exit code 1.
qualify-ci / lint: .github#16

! Failed to restore: Cache service responded with 400
qualify-ci / lint: .github#52

! Failed to restore: Cache service responded with 400
qualify-ci / lint: .github#24

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / lint: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / ace-page-group-isolation: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0WITzagAAAAAzCcEmW9wlRq5yhIB141iuQ0gxQUEyMDMwODEzMDI1AEVkZ2U=
qualify-ci / ace-page-group-isolation: .github#9

! Failed to restore: Cache service responded with 400
qualify-ci / ace-page-group-isolation: .github#49

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / ace-page-group-isolation: .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* release-please--branches--master Release sase-org/sase#322 · 42897628895
Triggered via workflow_dispatch about 29 minutes ago

JOBS
✓ identity in 57s (ID 130114862321)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Assert source and version identity
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ build in 38s (ID 130115420556)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up Python
  ✓ Build once and check the dist set
  ✓ Resolve the exact core pin
  ✓ Fetch the core file list and digests
  ✓ Read the core completeness set at the pin's tag
  ✓ Prove the core tag contains the source pin
  ✓ Seal the candidate manifest
  ✓ Upload the candidate build
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ qualify-prepare in 26s (ID 130115802507)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Download the sealed candidate build
  ✓ Bind the sealed candidate identity
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ exercise-legs (macos-latest, wheel) in 2m5s (ID 130115802596)
  ✓ Set up job
  ✓ Refuse probes outside rehearse
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up Python
  ✓ Ensure tmux for the TUI frame
  ✓ Download the sealed build
  ✓ Resolve the leg dist and manifest fields
  ✓ Verify digests before install
  ✓ Prepare the isolated leg environment
  ✓ Resolve the previous installable PyPI release
  ✓ Run the exercise leg
  ✓ Upload the leg evidence
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ exercise-legs (ubuntu-latest, sdist) in 54s (ID 130115802632)
  ✓ Set up job
  ✓ Refuse probes outside rehearse
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up Python
  - Ensure tmux for the TUI frame
  ✓ Download the sealed build
  ✓ Resolve the leg dist and manifest fields
  ✓ Verify digests before install
  ✓ Prepare the isolated leg environment
  - Resolve the previous installable PyPI release
  ✓ Run the exercise leg
  ✓ Upload the leg evidence
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ exercise-legs (ubuntu-latest, wheel) in 1m8s (ID 130115802657)
  ✓ Set up job
  ✓ Refuse probes outside rehearse
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up Python
  - Ensure tmux for the TUI frame
  ✓ Download the sealed build
  ✓ Resolve the leg dist and manifest fields
  ✓ Verify digests before install
  ✓ Prepare the isolated leg environment
  ✓ Resolve the previous installable PyPI release
  ✓ Run the exercise leg
  ✓ Upload the leg evidence
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ exercise-legs (macos-latest, sdist) in 1m18s (ID 130115802821)
  ✓ Set up job
  ✓ Refuse probes outside rehearse
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up Python
  ✓ Ensure tmux for the TUI frame
  ✓ Download the sealed build
  ✓ Resolve the leg dist and manifest fields
  ✓ Verify digests before install
  ✓ Prepare the isolated leg environment
  - Resolve the previous installable PyPI release
  ✓ Run the exercise leg
  ✓ Upload the leg evidence
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
- stash (ID 130115805318)
✓ qualify-ci / prepare in 26s (ID 130116069325)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Validate qualification inputs
  ✓ Download the sealed candidate manifest
  ✓ Bind published identity from the sealed manifest
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
- qualify-ci / release-core-floor-smoke (ID 130116071518)
- qualify-ci / docs-build (ID 130116072055)
✓ qualify-ci / build-core / build-core in 8m41s (ID 130116334196)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Resolve core mode
  - Resolve pinned Rust core revision
  - Check out Rust core
  ✓ Check out published Rust core tag
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up Rust
  ✓ Cache Rust build
  - Build abi3 Rust core wheel
  ✓ Download the sealed candidate manifest
  ✓ Fetch and verify the published core wheel
  ✓ Build macro LSP
  - Record wheel provenance
  ✓ Record published tag provenance
  ✓ Upload Rust core artifacts
  ✓ Post Cache Rust build
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Check out published Rust core tag
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ exercise in 27s (ID 130117005549)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Download the sealed build
  ✓ Download the leg evidence
  ✓ Merge the legs into one exercise observation
  - Stash the exercise observation on the draft release
  ✓ Upload the exercise observation artifact
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ qualify-ci / perf-floors in 9m50s (ID 130121174612)
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
✓ qualify-ci / tutorial-tests in 1m4s (ID 130121174619)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run tutorial tests
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* qualify-ci / visual-test (ID 130121174667)
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
X qualify-ci / lint in 1m31s (ID 130121174682)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up preflight Python
  ✓ Download Rust core artifacts for bindings preflight
  ✓ Preflight core bindings
  ✓ Install dependencies
  ✓ Check pinned core bindings
  ✓ Bootstrap SDD sidecars
  ✓ Initialize SASE home
  ✓ Run actions/setup-go@v5
  ✓ Cache Go binaries
  - Install Go tools (keep-sorted)
  ✓ Cache Prettier dependencies
  ✓ Check Python formatting
  ✓ Check Markdown formatting
  X Check generated model docs
  - Check shipped model policy
  - Lint
  - SASE validation
  - Validate committed plans
  - Build and verify package
  ✓ Record installed core version
  ✓ Write qualification evidence
  ✓ Upload qualification evidence
  - Post Cache Prettier dependencies
  - Post Cache Go binaries
  - Post Run actions/setup-go@v5
  ✓ Post Install dependencies
  - Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* qualify-ci / test (3.14) (ID 130121174714)
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
* qualify-ci / test (3.13) (ID 130121174802)
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
* qualify-ci / test (3.12) (ID 130121174849)
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
✓ qualify-ci / ace-page-group-isolation in 1m37s (ID 130121174850)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  ✓ Run ACE shared-page isolation lane
  ✓ Post Install visual dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
identity: .github#7

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
identity: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
build: .github#4

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0sIHzagAAAAB30fM6H9ufTppmpzFOLFMkUEhMMzBFREdFMDEwOABFZGdl
build: .github#7

! Failed to restore: Cache service responded with 400
build: .github#24

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
build: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-prepare: .github#9

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-prepare: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
exercise-legs (macos-latest, wheel): .github#2

- Due to capacity constraints, jobs targeting macOS arm64 runners may experience longer queue times.
exercise-legs (macos-latest, wheel): .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
exercise-legs (ubuntu-latest, sdist): .github#2

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
exercise-legs (ubuntu-latest, sdist): .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
exercise-legs (ubuntu-latest, wheel): .github#2

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
exercise-legs (ubuntu-latest, wheel): .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
exercise-legs (macos-latest, sdist): .github#2

- Due to capacity constraints, jobs targeting macOS arm64 runners may experience longer queue times.
exercise-legs (macos-latest, sdist): .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / prepare: .github#10

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / prepare: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / build-core / build-core: .github#5

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>09YPzagAAAAAiPR5XKRSoQpRg352ExmJxQ0gxQUEyMDMwODE0MDYwAEVkZ2U=
qualify-ci / build-core / build-core: .github#7

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / tutorial-tests: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0OITzagAAAACMpVdYEU0wTYGlMGZQR9ksQ0gxQUEyMDMwODEzMDYwAEVkZ2U=
qualify-ci / tutorial-tests: .github#9

! Failed to restore: Cache service responded with 400
qualify-ci / tutorial-tests: .github#49

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / tutorial-tests: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache@v4, actions/checkout@v4, actions/download-artifact@v4, actions/setup-go@v5, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / lint: .github#2

X Process completed with exit code 1.
qualify-ci / lint: .github#16

! Failed to restore: Cache service responded with 400
qualify-ci / lint: .github#52

! Failed to restore: Cache service responded with 400
qualify-ci / lint: .github#24

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / lint: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / ace-page-group-isolation: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0WITzagAAAAAzCcEmW9wlRq5yhIB141iuQ0gxQUEyMDMwODEzMDI1AEVkZ2U=
qualify-ci / ace-page-group-isolation: .github#9

! Failed to restore: Cache service responded with 400
qualify-ci / ace-page-group-isolation: .github#49

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / ace-page-group-isolation: .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* release-please--branches--master Release sase-org/sase#322 · 42897628895
Triggered via workflow_dispatch about 31 minutes ago

JOBS
✓ identity in 57s (ID 130114862321)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Assert source and version identity
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ build in 38s (ID 130115420556)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up Python
  ✓ Build once and check the dist set
  ✓ Resolve the exact core pin
  ✓ Fetch the core file list and digests
  ✓ Read the core completeness set at the pin's tag
  ✓ Prove the core tag contains the source pin
  ✓ Seal the candidate manifest
  ✓ Upload the candidate build
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ qualify-prepare in 26s (ID 130115802507)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Download the sealed candidate build
  ✓ Bind the sealed candidate identity
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ exercise-legs (macos-latest, wheel) in 2m5s (ID 130115802596)
  ✓ Set up job
  ✓ Refuse probes outside rehearse
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up Python
  ✓ Ensure tmux for the TUI frame
  ✓ Download the sealed build
  ✓ Resolve the leg dist and manifest fields
  ✓ Verify digests before install
  ✓ Prepare the isolated leg environment
  ✓ Resolve the previous installable PyPI release
  ✓ Run the exercise leg
  ✓ Upload the leg evidence
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ exercise-legs (ubuntu-latest, sdist) in 54s (ID 130115802632)
  ✓ Set up job
  ✓ Refuse probes outside rehearse
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up Python
  - Ensure tmux for the TUI frame
  ✓ Download the sealed build
  ✓ Resolve the leg dist and manifest fields
  ✓ Verify digests before install
  ✓ Prepare the isolated leg environment
  - Resolve the previous installable PyPI release
  ✓ Run the exercise leg
  ✓ Upload the leg evidence
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ exercise-legs (ubuntu-latest, wheel) in 1m8s (ID 130115802657)
  ✓ Set up job
  ✓ Refuse probes outside rehearse
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up Python
  - Ensure tmux for the TUI frame
  ✓ Download the sealed build
  ✓ Resolve the leg dist and manifest fields
  ✓ Verify digests before install
  ✓ Prepare the isolated leg environment
  ✓ Resolve the previous installable PyPI release
  ✓ Run the exercise leg
  ✓ Upload the leg evidence
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ exercise-legs (macos-latest, sdist) in 1m18s (ID 130115802821)
  ✓ Set up job
  ✓ Refuse probes outside rehearse
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up Python
  ✓ Ensure tmux for the TUI frame
  ✓ Download the sealed build
  ✓ Resolve the leg dist and manifest fields
  ✓ Verify digests before install
  ✓ Prepare the isolated leg environment
  - Resolve the previous installable PyPI release
  ✓ Run the exercise leg
  ✓ Upload the leg evidence
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
- stash (ID 130115805318)
✓ qualify-ci / prepare in 26s (ID 130116069325)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Validate qualification inputs
  ✓ Download the sealed candidate manifest
  ✓ Bind published identity from the sealed manifest
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
- qualify-ci / release-core-floor-smoke (ID 130116071518)
- qualify-ci / docs-build (ID 130116072055)
✓ qualify-ci / build-core / build-core in 8m41s (ID 130116334196)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Resolve core mode
  - Resolve pinned Rust core revision
  - Check out Rust core
  ✓ Check out published Rust core tag
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up Rust
  ✓ Cache Rust build
  - Build abi3 Rust core wheel
  ✓ Download the sealed candidate manifest
  ✓ Fetch and verify the published core wheel
  ✓ Build macro LSP
  - Record wheel provenance
  ✓ Record published tag provenance
  ✓ Upload Rust core artifacts
  ✓ Post Cache Rust build
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Check out published Rust core tag
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ exercise in 27s (ID 130117005549)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Download the sealed build
  ✓ Download the leg evidence
  ✓ Merge the legs into one exercise observation
  - Stash the exercise observation on the draft release
  ✓ Upload the exercise observation artifact
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ qualify-ci / perf-floors in 9m50s (ID 130121174612)
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
✓ qualify-ci / tutorial-tests in 1m4s (ID 130121174619)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run tutorial tests
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* qualify-ci / visual-test (ID 130121174667)
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
X qualify-ci / lint in 1m31s (ID 130121174682)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up preflight Python
  ✓ Download Rust core artifacts for bindings preflight
  ✓ Preflight core bindings
  ✓ Install dependencies
  ✓ Check pinned core bindings
  ✓ Bootstrap SDD sidecars
  ✓ Initialize SASE home
  ✓ Run actions/setup-go@v5
  ✓ Cache Go binaries
  - Install Go tools (keep-sorted)
  ✓ Cache Prettier dependencies
  ✓ Check Python formatting
  ✓ Check Markdown formatting
  X Check generated model docs
  - Check shipped model policy
  - Lint
  - SASE validation
  - Validate committed plans
  - Build and verify package
  ✓ Record installed core version
  ✓ Write qualification evidence
  ✓ Upload qualification evidence
  - Post Cache Prettier dependencies
  - Post Cache Go binaries
  - Post Run actions/setup-go@v5
  ✓ Post Install dependencies
  - Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* qualify-ci / test (3.14) (ID 130121174714)
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
* qualify-ci / test (3.13) (ID 130121174802)
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
* qualify-ci / test (3.12) (ID 130121174849)
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
✓ qualify-ci / ace-page-group-isolation in 1m37s (ID 130121174850)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  ✓ Run ACE shared-page isolation lane
  ✓ Post Install visual dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
identity: .github#7

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
identity: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
build: .github#4

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0sIHzagAAAAB30fM6H9ufTppmpzFOLFMkUEhMMzBFREdFMDEwOABFZGdl
build: .github#7

! Failed to restore: Cache service responded with 400
build: .github#24

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
build: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-prepare: .github#9

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-prepare: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
exercise-legs (macos-latest, wheel): .github#2

- Due to capacity constraints, jobs targeting macOS arm64 runners may experience longer queue times.
exercise-legs (macos-latest, wheel): .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
exercise-legs (ubuntu-latest, sdist): .github#2

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
exercise-legs (ubuntu-latest, sdist): .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
exercise-legs (ubuntu-latest, wheel): .github#2

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
exercise-legs (ubuntu-latest, wheel): .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
exercise-legs (macos-latest, sdist): .github#2

- Due to capacity constraints, jobs targeting macOS arm64 runners may experience longer queue times.
exercise-legs (macos-latest, sdist): .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / prepare: .github#10

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / prepare: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / build-core / build-core: .github#5

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>09YPzagAAAAAiPR5XKRSoQpRg352ExmJxQ0gxQUEyMDMwODE0MDYwAEVkZ2U=
qualify-ci / build-core / build-core: .github#7

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / tutorial-tests: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0OITzagAAAACMpVdYEU0wTYGlMGZQR9ksQ0gxQUEyMDMwODEzMDYwAEVkZ2U=
qualify-ci / tutorial-tests: .github#9

! Failed to restore: Cache service responded with 400
qualify-ci / tutorial-tests: .github#49

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / tutorial-tests: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache@v4, actions/checkout@v4, actions/download-artifact@v4, actions/setup-go@v5, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / lint: .github#2

X Process completed with exit code 1.
qualify-ci / lint: .github#16

! Failed to restore: Cache service responded with 400
qualify-ci / lint: .github#52

! Failed to restore: Cache service responded with 400
qualify-ci / lint: .github#24

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / lint: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / ace-page-group-isolation: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0WITzagAAAAAzCcEmW9wlRq5yhIB141iuQ0gxQUEyMDMwODEzMDI1AEVkZ2U=
qualify-ci / ace-page-group-isolation: .github#9

! Failed to restore: Cache service responded with 400
qualify-ci / ace-page-group-isolation: .github#49

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / ace-page-group-isolation: .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* release-please--branches--master Release sase-org/sase#322 · 42897628895
Triggered via workflow_dispatch about 33 minutes ago

JOBS
✓ identity in 57s (ID 130114862321)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Assert source and version identity
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ build in 38s (ID 130115420556)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up Python
  ✓ Build once and check the dist set
  ✓ Resolve the exact core pin
  ✓ Fetch the core file list and digests
  ✓ Read the core completeness set at the pin's tag
  ✓ Prove the core tag contains the source pin
  ✓ Seal the candidate manifest
  ✓ Upload the candidate build
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ qualify-prepare in 26s (ID 130115802507)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Download the sealed candidate build
  ✓ Bind the sealed candidate identity
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ exercise-legs (macos-latest, wheel) in 2m5s (ID 130115802596)
  ✓ Set up job
  ✓ Refuse probes outside rehearse
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up Python
  ✓ Ensure tmux for the TUI frame
  ✓ Download the sealed build
  ✓ Resolve the leg dist and manifest fields
  ✓ Verify digests before install
  ✓ Prepare the isolated leg environment
  ✓ Resolve the previous installable PyPI release
  ✓ Run the exercise leg
  ✓ Upload the leg evidence
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ exercise-legs (ubuntu-latest, sdist) in 54s (ID 130115802632)
  ✓ Set up job
  ✓ Refuse probes outside rehearse
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up Python
  - Ensure tmux for the TUI frame
  ✓ Download the sealed build
  ✓ Resolve the leg dist and manifest fields
  ✓ Verify digests before install
  ✓ Prepare the isolated leg environment
  - Resolve the previous installable PyPI release
  ✓ Run the exercise leg
  ✓ Upload the leg evidence
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ exercise-legs (ubuntu-latest, wheel) in 1m8s (ID 130115802657)
  ✓ Set up job
  ✓ Refuse probes outside rehearse
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up Python
  - Ensure tmux for the TUI frame
  ✓ Download the sealed build
  ✓ Resolve the leg dist and manifest fields
  ✓ Verify digests before install
  ✓ Prepare the isolated leg environment
  ✓ Resolve the previous installable PyPI release
  ✓ Run the exercise leg
  ✓ Upload the leg evidence
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ exercise-legs (macos-latest, sdist) in 1m18s (ID 130115802821)
  ✓ Set up job
  ✓ Refuse probes outside rehearse
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up Python
  ✓ Ensure tmux for the TUI frame
  ✓ Download the sealed build
  ✓ Resolve the leg dist and manifest fields
  ✓ Verify digests before install
  ✓ Prepare the isolated leg environment
  - Resolve the previous installable PyPI release
  ✓ Run the exercise leg
  ✓ Upload the leg evidence
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
- stash (ID 130115805318)
✓ qualify-ci / prepare in 26s (ID 130116069325)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Validate qualification inputs
  ✓ Download the sealed candidate manifest
  ✓ Bind published identity from the sealed manifest
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
- qualify-ci / release-core-floor-smoke (ID 130116071518)
- qualify-ci / docs-build (ID 130116072055)
✓ qualify-ci / build-core / build-core in 8m41s (ID 130116334196)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Resolve core mode
  - Resolve pinned Rust core revision
  - Check out Rust core
  ✓ Check out published Rust core tag
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up Rust
  ✓ Cache Rust build
  - Build abi3 Rust core wheel
  ✓ Download the sealed candidate manifest
  ✓ Fetch and verify the published core wheel
  ✓ Build macro LSP
  - Record wheel provenance
  ✓ Record published tag provenance
  ✓ Upload Rust core artifacts
  ✓ Post Cache Rust build
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Check out published Rust core tag
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ exercise in 27s (ID 130117005549)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Download the sealed build
  ✓ Download the leg evidence
  ✓ Merge the legs into one exercise observation
  - Stash the exercise observation on the draft release
  ✓ Upload the exercise observation artifact
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ qualify-ci / perf-floors in 9m50s (ID 130121174612)
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
✓ qualify-ci / tutorial-tests in 1m4s (ID 130121174619)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run tutorial tests
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* qualify-ci / visual-test (ID 130121174667)
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
X qualify-ci / lint in 1m31s (ID 130121174682)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up preflight Python
  ✓ Download Rust core artifacts for bindings preflight
  ✓ Preflight core bindings
  ✓ Install dependencies
  ✓ Check pinned core bindings
  ✓ Bootstrap SDD sidecars
  ✓ Initialize SASE home
  ✓ Run actions/setup-go@v5
  ✓ Cache Go binaries
  - Install Go tools (keep-sorted)
  ✓ Cache Prettier dependencies
  ✓ Check Python formatting
  ✓ Check Markdown formatting
  X Check generated model docs
  - Check shipped model policy
  - Lint
  - SASE validation
  - Validate committed plans
  - Build and verify package
  ✓ Record installed core version
  ✓ Write qualification evidence
  ✓ Upload qualification evidence
  - Post Cache Prettier dependencies
  - Post Cache Go binaries
  - Post Run actions/setup-go@v5
  ✓ Post Install dependencies
  - Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* qualify-ci / test (3.14) (ID 130121174714)
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
* qualify-ci / test (3.13) (ID 130121174802)
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
* qualify-ci / test (3.12) (ID 130121174849)
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
✓ qualify-ci / ace-page-group-isolation in 1m37s (ID 130121174850)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  ✓ Run ACE shared-page isolation lane
  ✓ Post Install visual dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
identity: .github#7

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
identity: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
build: .github#4

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0sIHzagAAAAB30fM6H9ufTppmpzFOLFMkUEhMMzBFREdFMDEwOABFZGdl
build: .github#7

! Failed to restore: Cache service responded with 400
build: .github#24

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
build: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-prepare: .github#9

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-prepare: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
exercise-legs (macos-latest, wheel): .github#2

- Due to capacity constraints, jobs targeting macOS arm64 runners may experience longer queue times.
exercise-legs (macos-latest, wheel): .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
exercise-legs (ubuntu-latest, sdist): .github#2

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
exercise-legs (ubuntu-latest, sdist): .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
exercise-legs (ubuntu-latest, wheel): .github#2

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
exercise-legs (ubuntu-latest, wheel): .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
exercise-legs (macos-latest, sdist): .github#2

- Due to capacity constraints, jobs targeting macOS arm64 runners may experience longer queue times.
exercise-legs (macos-latest, sdist): .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / prepare: .github#10

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / prepare: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / build-core / build-core: .github#5

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>09YPzagAAAAAiPR5XKRSoQpRg352ExmJxQ0gxQUEyMDMwODE0MDYwAEVkZ2U=
qualify-ci / build-core / build-core: .github#7

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / tutorial-tests: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0OITzagAAAACMpVdYEU0wTYGlMGZQR9ksQ0gxQUEyMDMwODEzMDYwAEVkZ2U=
qualify-ci / tutorial-tests: .github#9

! Failed to restore: Cache service responded with 400
qualify-ci / tutorial-tests: .github#49

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / tutorial-tests: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache@v4, actions/checkout@v4, actions/download-artifact@v4, actions/setup-go@v5, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / lint: .github#2

X Process completed with exit code 1.
qualify-ci / lint: .github#16

! Failed to restore: Cache service responded with 400
qualify-ci / lint: .github#52

! Failed to restore: Cache service responded with 400
qualify-ci / lint: .github#24

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / lint: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / ace-page-group-isolation: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0WITzagAAAAAzCcEmW9wlRq5yhIB141iuQ0gxQUEyMDMwODEzMDI1AEVkZ2U=
qualify-ci / ace-page-group-isolation: .github#9

! Failed to restore: Cache service responded with 400
qualify-ci / ace-page-group-isolation: .github#49

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / ace-page-group-isolation: .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* release-please--branches--master Release sase-org/sase#322 · 42897628895
Triggered via workflow_dispatch about 35 minutes ago

JOBS
✓ identity in 57s (ID 130114862321)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Assert source and version identity
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ build in 38s (ID 130115420556)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up Python
  ✓ Build once and check the dist set
  ✓ Resolve the exact core pin
  ✓ Fetch the core file list and digests
  ✓ Read the core completeness set at the pin's tag
  ✓ Prove the core tag contains the source pin
  ✓ Seal the candidate manifest
  ✓ Upload the candidate build
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ qualify-prepare in 26s (ID 130115802507)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Download the sealed candidate build
  ✓ Bind the sealed candidate identity
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ exercise-legs (macos-latest, wheel) in 2m5s (ID 130115802596)
  ✓ Set up job
  ✓ Refuse probes outside rehearse
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up Python
  ✓ Ensure tmux for the TUI frame
  ✓ Download the sealed build
  ✓ Resolve the leg dist and manifest fields
  ✓ Verify digests before install
  ✓ Prepare the isolated leg environment
  ✓ Resolve the previous installable PyPI release
  ✓ Run the exercise leg
  ✓ Upload the leg evidence
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ exercise-legs (ubuntu-latest, sdist) in 54s (ID 130115802632)
  ✓ Set up job
  ✓ Refuse probes outside rehearse
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up Python
  - Ensure tmux for the TUI frame
  ✓ Download the sealed build
  ✓ Resolve the leg dist and manifest fields
  ✓ Verify digests before install
  ✓ Prepare the isolated leg environment
  - Resolve the previous installable PyPI release
  ✓ Run the exercise leg
  ✓ Upload the leg evidence
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ exercise-legs (ubuntu-latest, wheel) in 1m8s (ID 130115802657)
  ✓ Set up job
  ✓ Refuse probes outside rehearse
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up Python
  - Ensure tmux for the TUI frame
  ✓ Download the sealed build
  ✓ Resolve the leg dist and manifest fields
  ✓ Verify digests before install
  ✓ Prepare the isolated leg environment
  ✓ Resolve the previous installable PyPI release
  ✓ Run the exercise leg
  ✓ Upload the leg evidence
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ exercise-legs (macos-latest, sdist) in 1m18s (ID 130115802821)
  ✓ Set up job
  ✓ Refuse probes outside rehearse
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up Python
  ✓ Ensure tmux for the TUI frame
  ✓ Download the sealed build
  ✓ Resolve the leg dist and manifest fields
  ✓ Verify digests before install
  ✓ Prepare the isolated leg environment
  - Resolve the previous installable PyPI release
  ✓ Run the exercise leg
  ✓ Upload the leg evidence
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
- stash (ID 130115805318)
✓ qualify-ci / prepare in 26s (ID 130116069325)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Validate qualification inputs
  ✓ Download the sealed candidate manifest
  ✓ Bind published identity from the sealed manifest
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
- qualify-ci / release-core-floor-smoke (ID 130116071518)
- qualify-ci / docs-build (ID 130116072055)
✓ qualify-ci / build-core / build-core in 8m41s (ID 130116334196)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Resolve core mode
  - Resolve pinned Rust core revision
  - Check out Rust core
  ✓ Check out published Rust core tag
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up Rust
  ✓ Cache Rust build
  - Build abi3 Rust core wheel
  ✓ Download the sealed candidate manifest
  ✓ Fetch and verify the published core wheel
  ✓ Build macro LSP
  - Record wheel provenance
  ✓ Record published tag provenance
  ✓ Upload Rust core artifacts
  ✓ Post Cache Rust build
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Check out published Rust core tag
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ exercise in 27s (ID 130117005549)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Download the sealed build
  ✓ Download the leg evidence
  ✓ Merge the legs into one exercise observation
  - Stash the exercise observation on the draft release
  ✓ Upload the exercise observation artifact
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ qualify-ci / perf-floors in 9m50s (ID 130121174612)
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
✓ qualify-ci / tutorial-tests in 1m4s (ID 130121174619)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run tutorial tests
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* qualify-ci / visual-test (ID 130121174667)
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
X qualify-ci / lint in 1m31s (ID 130121174682)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up preflight Python
  ✓ Download Rust core artifacts for bindings preflight
  ✓ Preflight core bindings
  ✓ Install dependencies
  ✓ Check pinned core bindings
  ✓ Bootstrap SDD sidecars
  ✓ Initialize SASE home
  ✓ Run actions/setup-go@v5
  ✓ Cache Go binaries
  - Install Go tools (keep-sorted)
  ✓ Cache Prettier dependencies
  ✓ Check Python formatting
  ✓ Check Markdown formatting
  X Check generated model docs
  - Check shipped model policy
  - Lint
  - SASE validation
  - Validate committed plans
  - Build and verify package
  ✓ Record installed core version
  ✓ Write qualification evidence
  ✓ Upload qualification evidence
  - Post Cache Prettier dependencies
  - Post Cache Go binaries
  - Post Run actions/setup-go@v5
  ✓ Post Install dependencies
  - Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* qualify-ci / test (3.14) (ID 130121174714)
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
* qualify-ci / test (3.13) (ID 130121174802)
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
* qualify-ci / test (3.12) (ID 130121174849)
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
✓ qualify-ci / ace-page-group-isolation in 1m37s (ID 130121174850)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  ✓ Run ACE shared-page isolation lane
  ✓ Post Install visual dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
identity: .github#7

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
identity: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
build: .github#4

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0sIHzagAAAAB30fM6H9ufTppmpzFOLFMkUEhMMzBFREdFMDEwOABFZGdl
build: .github#7

! Failed to restore: Cache service responded with 400
build: .github#24

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
build: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-prepare: .github#9

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-prepare: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
exercise-legs (macos-latest, wheel): .github#2

- Due to capacity constraints, jobs targeting macOS arm64 runners may experience longer queue times.
exercise-legs (macos-latest, wheel): .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
exercise-legs (ubuntu-latest, sdist): .github#2

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
exercise-legs (ubuntu-latest, sdist): .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
exercise-legs (ubuntu-latest, wheel): .github#2

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
exercise-legs (ubuntu-latest, wheel): .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
exercise-legs (macos-latest, sdist): .github#2

- Due to capacity constraints, jobs targeting macOS arm64 runners may experience longer queue times.
exercise-legs (macos-latest, sdist): .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / prepare: .github#10

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / prepare: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / build-core / build-core: .github#5

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>09YPzagAAAAAiPR5XKRSoQpRg352ExmJxQ0gxQUEyMDMwODE0MDYwAEVkZ2U=
qualify-ci / build-core / build-core: .github#7

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / tutorial-tests: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0OITzagAAAACMpVdYEU0wTYGlMGZQR9ksQ0gxQUEyMDMwODEzMDYwAEVkZ2U=
qualify-ci / tutorial-tests: .github#9

! Failed to restore: Cache service responded with 400
qualify-ci / tutorial-tests: .github#49

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / tutorial-tests: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache@v4, actions/checkout@v4, actions/download-artifact@v4, actions/setup-go@v5, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / lint: .github#2

X Process completed with exit code 1.
qualify-ci / lint: .github#16

! Failed to restore: Cache service responded with 400
qualify-ci / lint: .github#52

! Failed to restore: Cache service responded with 400
qualify-ci / lint: .github#24

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / lint: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / ace-page-group-isolation: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0WITzagAAAAAzCcEmW9wlRq5yhIB141iuQ0gxQUEyMDMwODEzMDI1AEVkZ2U=
qualify-ci / ace-page-group-isolation: .github#9

! Failed to restore: Cache service responded with 400
qualify-ci / ace-page-group-isolation: .github#49

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / ace-page-group-isolation: .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* release-please--branches--master Release sase-org/sase#322 · 42897628895
Triggered via workflow_dispatch about 37 minutes ago

JOBS
✓ identity in 57s (ID 130114862321)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Assert source and version identity
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ build in 38s (ID 130115420556)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up Python
  ✓ Build once and check the dist set
  ✓ Resolve the exact core pin
  ✓ Fetch the core file list and digests
  ✓ Read the core completeness set at the pin's tag
  ✓ Prove the core tag contains the source pin
  ✓ Seal the candidate manifest
  ✓ Upload the candidate build
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ qualify-prepare in 26s (ID 130115802507)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Download the sealed candidate build
  ✓ Bind the sealed candidate identity
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ exercise-legs (macos-latest, wheel) in 2m5s (ID 130115802596)
  ✓ Set up job
  ✓ Refuse probes outside rehearse
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up Python
  ✓ Ensure tmux for the TUI frame
  ✓ Download the sealed build
  ✓ Resolve the leg dist and manifest fields
  ✓ Verify digests before install
  ✓ Prepare the isolated leg environment
  ✓ Resolve the previous installable PyPI release
  ✓ Run the exercise leg
  ✓ Upload the leg evidence
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ exercise-legs (ubuntu-latest, sdist) in 54s (ID 130115802632)
  ✓ Set up job
  ✓ Refuse probes outside rehearse
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up Python
  - Ensure tmux for the TUI frame
  ✓ Download the sealed build
  ✓ Resolve the leg dist and manifest fields
  ✓ Verify digests before install
  ✓ Prepare the isolated leg environment
  - Resolve the previous installable PyPI release
  ✓ Run the exercise leg
  ✓ Upload the leg evidence
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ exercise-legs (ubuntu-latest, wheel) in 1m8s (ID 130115802657)
  ✓ Set up job
  ✓ Refuse probes outside rehearse
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up Python
  - Ensure tmux for the TUI frame
  ✓ Download the sealed build
  ✓ Resolve the leg dist and manifest fields
  ✓ Verify digests before install
  ✓ Prepare the isolated leg environment
  ✓ Resolve the previous installable PyPI release
  ✓ Run the exercise leg
  ✓ Upload the leg evidence
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ exercise-legs (macos-latest, sdist) in 1m18s (ID 130115802821)
  ✓ Set up job
  ✓ Refuse probes outside rehearse
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up Python
  ✓ Ensure tmux for the TUI frame
  ✓ Download the sealed build
  ✓ Resolve the leg dist and manifest fields
  ✓ Verify digests before install
  ✓ Prepare the isolated leg environment
  - Resolve the previous installable PyPI release
  ✓ Run the exercise leg
  ✓ Upload the leg evidence
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
- stash (ID 130115805318)
✓ qualify-ci / prepare in 26s (ID 130116069325)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Validate qualification inputs
  ✓ Download the sealed candidate manifest
  ✓ Bind published identity from the sealed manifest
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
- qualify-ci / release-core-floor-smoke (ID 130116071518)
- qualify-ci / docs-build (ID 130116072055)
✓ qualify-ci / build-core / build-core in 8m41s (ID 130116334196)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Resolve core mode
  - Resolve pinned Rust core revision
  - Check out Rust core
  ✓ Check out published Rust core tag
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up Rust
  ✓ Cache Rust build
  - Build abi3 Rust core wheel
  ✓ Download the sealed candidate manifest
  ✓ Fetch and verify the published core wheel
  ✓ Build macro LSP
  - Record wheel provenance
  ✓ Record published tag provenance
  ✓ Upload Rust core artifacts
  ✓ Post Cache Rust build
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Check out published Rust core tag
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ exercise in 27s (ID 130117005549)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Download the sealed build
  ✓ Download the leg evidence
  ✓ Merge the legs into one exercise observation
  - Stash the exercise observation on the draft release
  ✓ Upload the exercise observation artifact
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ qualify-ci / perf-floors in 9m50s (ID 130121174612)
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
✓ qualify-ci / tutorial-tests in 1m4s (ID 130121174619)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run tutorial tests
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* qualify-ci / visual-test (ID 130121174667)
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
X qualify-ci / lint in 1m31s (ID 130121174682)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up preflight Python
  ✓ Download Rust core artifacts for bindings preflight
  ✓ Preflight core bindings
  ✓ Install dependencies
  ✓ Check pinned core bindings
  ✓ Bootstrap SDD sidecars
  ✓ Initialize SASE home
  ✓ Run actions/setup-go@v5
  ✓ Cache Go binaries
  - Install Go tools (keep-sorted)
  ✓ Cache Prettier dependencies
  ✓ Check Python formatting
  ✓ Check Markdown formatting
  X Check generated model docs
  - Check shipped model policy
  - Lint
  - SASE validation
  - Validate committed plans
  - Build and verify package
  ✓ Record installed core version
  ✓ Write qualification evidence
  ✓ Upload qualification evidence
  - Post Cache Prettier dependencies
  - Post Cache Go binaries
  - Post Run actions/setup-go@v5
  ✓ Post Install dependencies
  - Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* qualify-ci / test (3.14) (ID 130121174714)
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
* qualify-ci / test (3.13) (ID 130121174802)
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
* qualify-ci / test (3.12) (ID 130121174849)
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
✓ qualify-ci / ace-page-group-isolation in 1m37s (ID 130121174850)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  ✓ Run ACE shared-page isolation lane
  ✓ Post Install visual dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
identity: .github#7

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
identity: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
build: .github#4

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0sIHzagAAAAB30fM6H9ufTppmpzFOLFMkUEhMMzBFREdFMDEwOABFZGdl
build: .github#7

! Failed to restore: Cache service responded with 400
build: .github#24

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
build: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-prepare: .github#9

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-prepare: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
exercise-legs (macos-latest, wheel): .github#2

- Due to capacity constraints, jobs targeting macOS arm64 runners may experience longer queue times.
exercise-legs (macos-latest, wheel): .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
exercise-legs (ubuntu-latest, sdist): .github#2

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
exercise-legs (ubuntu-latest, sdist): .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
exercise-legs (ubuntu-latest, wheel): .github#2

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
exercise-legs (ubuntu-latest, wheel): .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
exercise-legs (macos-latest, sdist): .github#2

- Due to capacity constraints, jobs targeting macOS arm64 runners may experience longer queue times.
exercise-legs (macos-latest, sdist): .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / prepare: .github#10

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / prepare: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / build-core / build-core: .github#5

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>09YPzagAAAAAiPR5XKRSoQpRg352ExmJxQ0gxQUEyMDMwODE0MDYwAEVkZ2U=
qualify-ci / build-core / build-core: .github#7

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / tutorial-tests: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0OITzagAAAACMpVdYEU0wTYGlMGZQR9ksQ0gxQUEyMDMwODEzMDYwAEVkZ2U=
qualify-ci / tutorial-tests: .github#9

! Failed to restore: Cache service responded with 400
qualify-ci / tutorial-tests: .github#49

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / tutorial-tests: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache@v4, actions/checkout@v4, actions/download-artifact@v4, actions/setup-go@v5, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / lint: .github#2

X Process completed with exit code 1.
qualify-ci / lint: .github#16

! Failed to restore: Cache service responded with 400
qualify-ci / lint: .github#52

! Failed to restore: Cache service responded with 400
qualify-ci / lint: .github#24

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / lint: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / ace-page-group-isolation: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0WITzagAAAAAzCcEmW9wlRq5yhIB141iuQ0gxQUEyMDMwODEzMDI1AEVkZ2U=
qualify-ci / ace-page-group-isolation: .github#9

! Failed to restore: Cache service responded with 400
qualify-ci / ace-page-group-isolation: .github#49

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / ace-page-group-isolation: .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* release-please--branches--master Release sase-org/sase#322 · 42897628895
Triggered via workflow_dispatch about 39 minutes ago

JOBS
✓ identity in 57s (ID 130114862321)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Assert source and version identity
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ build in 38s (ID 130115420556)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up Python
  ✓ Build once and check the dist set
  ✓ Resolve the exact core pin
  ✓ Fetch the core file list and digests
  ✓ Read the core completeness set at the pin's tag
  ✓ Prove the core tag contains the source pin
  ✓ Seal the candidate manifest
  ✓ Upload the candidate build
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ qualify-prepare in 26s (ID 130115802507)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Download the sealed candidate build
  ✓ Bind the sealed candidate identity
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ exercise-legs (macos-latest, wheel) in 2m5s (ID 130115802596)
  ✓ Set up job
  ✓ Refuse probes outside rehearse
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up Python
  ✓ Ensure tmux for the TUI frame
  ✓ Download the sealed build
  ✓ Resolve the leg dist and manifest fields
  ✓ Verify digests before install
  ✓ Prepare the isolated leg environment
  ✓ Resolve the previous installable PyPI release
  ✓ Run the exercise leg
  ✓ Upload the leg evidence
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ exercise-legs (ubuntu-latest, sdist) in 54s (ID 130115802632)
  ✓ Set up job
  ✓ Refuse probes outside rehearse
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up Python
  - Ensure tmux for the TUI frame
  ✓ Download the sealed build
  ✓ Resolve the leg dist and manifest fields
  ✓ Verify digests before install
  ✓ Prepare the isolated leg environment
  - Resolve the previous installable PyPI release
  ✓ Run the exercise leg
  ✓ Upload the leg evidence
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ exercise-legs (ubuntu-latest, wheel) in 1m8s (ID 130115802657)
  ✓ Set up job
  ✓ Refuse probes outside rehearse
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up Python
  - Ensure tmux for the TUI frame
  ✓ Download the sealed build
  ✓ Resolve the leg dist and manifest fields
  ✓ Verify digests before install
  ✓ Prepare the isolated leg environment
  ✓ Resolve the previous installable PyPI release
  ✓ Run the exercise leg
  ✓ Upload the leg evidence
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ exercise-legs (macos-latest, sdist) in 1m18s (ID 130115802821)
  ✓ Set up job
  ✓ Refuse probes outside rehearse
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up Python
  ✓ Ensure tmux for the TUI frame
  ✓ Download the sealed build
  ✓ Resolve the leg dist and manifest fields
  ✓ Verify digests before install
  ✓ Prepare the isolated leg environment
  - Resolve the previous installable PyPI release
  ✓ Run the exercise leg
  ✓ Upload the leg evidence
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
- stash (ID 130115805318)
✓ qualify-ci / prepare in 26s (ID 130116069325)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Validate qualification inputs
  ✓ Download the sealed candidate manifest
  ✓ Bind published identity from the sealed manifest
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
- qualify-ci / release-core-floor-smoke (ID 130116071518)
- qualify-ci / docs-build (ID 130116072055)
✓ qualify-ci / build-core / build-core in 8m41s (ID 130116334196)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Resolve core mode
  - Resolve pinned Rust core revision
  - Check out Rust core
  ✓ Check out published Rust core tag
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up Rust
  ✓ Cache Rust build
  - Build abi3 Rust core wheel
  ✓ Download the sealed candidate manifest
  ✓ Fetch and verify the published core wheel
  ✓ Build macro LSP
  - Record wheel provenance
  ✓ Record published tag provenance
  ✓ Upload Rust core artifacts
  ✓ Post Cache Rust build
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Check out published Rust core tag
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ exercise in 27s (ID 130117005549)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Download the sealed build
  ✓ Download the leg evidence
  ✓ Merge the legs into one exercise observation
  - Stash the exercise observation on the draft release
  ✓ Upload the exercise observation artifact
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ qualify-ci / perf-floors in 9m50s (ID 130121174612)
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
✓ qualify-ci / tutorial-tests in 1m4s (ID 130121174619)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run tutorial tests
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* qualify-ci / visual-test (ID 130121174667)
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
X qualify-ci / lint in 1m31s (ID 130121174682)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up preflight Python
  ✓ Download Rust core artifacts for bindings preflight
  ✓ Preflight core bindings
  ✓ Install dependencies
  ✓ Check pinned core bindings
  ✓ Bootstrap SDD sidecars
  ✓ Initialize SASE home
  ✓ Run actions/setup-go@v5
  ✓ Cache Go binaries
  - Install Go tools (keep-sorted)
  ✓ Cache Prettier dependencies
  ✓ Check Python formatting
  ✓ Check Markdown formatting
  X Check generated model docs
  - Check shipped model policy
  - Lint
  - SASE validation
  - Validate committed plans
  - Build and verify package
  ✓ Record installed core version
  ✓ Write qualification evidence
  ✓ Upload qualification evidence
  - Post Cache Prettier dependencies
  - Post Cache Go binaries
  - Post Run actions/setup-go@v5
  ✓ Post Install dependencies
  - Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* qualify-ci / test (3.14) (ID 130121174714)
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
* qualify-ci / test (3.13) (ID 130121174802)
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
* qualify-ci / test (3.12) (ID 130121174849)
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
✓ qualify-ci / ace-page-group-isolation in 1m37s (ID 130121174850)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  ✓ Run ACE shared-page isolation lane
  ✓ Post Install visual dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
identity: .github#7

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
identity: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
build: .github#4

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0sIHzagAAAAB30fM6H9ufTppmpzFOLFMkUEhMMzBFREdFMDEwOABFZGdl
build: .github#7

! Failed to restore: Cache service responded with 400
build: .github#24

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
build: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-prepare: .github#9

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-prepare: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
exercise-legs (macos-latest, wheel): .github#2

- Due to capacity constraints, jobs targeting macOS arm64 runners may experience longer queue times.
exercise-legs (macos-latest, wheel): .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
exercise-legs (ubuntu-latest, sdist): .github#2

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
exercise-legs (ubuntu-latest, sdist): .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
exercise-legs (ubuntu-latest, wheel): .github#2

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
exercise-legs (ubuntu-latest, wheel): .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
exercise-legs (macos-latest, sdist): .github#2

- Due to capacity constraints, jobs targeting macOS arm64 runners may experience longer queue times.
exercise-legs (macos-latest, sdist): .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / prepare: .github#10

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / prepare: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / build-core / build-core: .github#5

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>09YPzagAAAAAiPR5XKRSoQpRg352ExmJxQ0gxQUEyMDMwODE0MDYwAEVkZ2U=
qualify-ci / build-core / build-core: .github#7

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / tutorial-tests: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0OITzagAAAACMpVdYEU0wTYGlMGZQR9ksQ0gxQUEyMDMwODEzMDYwAEVkZ2U=
qualify-ci / tutorial-tests: .github#9

! Failed to restore: Cache service responded with 400
qualify-ci / tutorial-tests: .github#49

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / tutorial-tests: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache@v4, actions/checkout@v4, actions/download-artifact@v4, actions/setup-go@v5, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / lint: .github#2

X Process completed with exit code 1.
qualify-ci / lint: .github#16

! Failed to restore: Cache service responded with 400
qualify-ci / lint: .github#52

! Failed to restore: Cache service responded with 400
qualify-ci / lint: .github#24

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / lint: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / ace-page-group-isolation: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0WITzagAAAAAzCcEmW9wlRq5yhIB141iuQ0gxQUEyMDMwODEzMDI1AEVkZ2U=
qualify-ci / ace-page-group-isolation: .github#9

! Failed to restore: Cache service responded with 400
qualify-ci / ace-page-group-isolation: .github#49

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / ace-page-group-isolation: .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* release-please--branches--master Release sase-org/sase#322 · 42897628895
Triggered via workflow_dispatch about 41 minutes ago

JOBS
✓ identity in 57s (ID 130114862321)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Assert source and version identity
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ build in 38s (ID 130115420556)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up Python
  ✓ Build once and check the dist set
  ✓ Resolve the exact core pin
  ✓ Fetch the core file list and digests
  ✓ Read the core completeness set at the pin's tag
  ✓ Prove the core tag contains the source pin
  ✓ Seal the candidate manifest
  ✓ Upload the candidate build
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ qualify-prepare in 26s (ID 130115802507)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Download the sealed candidate build
  ✓ Bind the sealed candidate identity
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ exercise-legs (macos-latest, wheel) in 2m5s (ID 130115802596)
  ✓ Set up job
  ✓ Refuse probes outside rehearse
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up Python
  ✓ Ensure tmux for the TUI frame
  ✓ Download the sealed build
  ✓ Resolve the leg dist and manifest fields
  ✓ Verify digests before install
  ✓ Prepare the isolated leg environment
  ✓ Resolve the previous installable PyPI release
  ✓ Run the exercise leg
  ✓ Upload the leg evidence
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ exercise-legs (ubuntu-latest, sdist) in 54s (ID 130115802632)
  ✓ Set up job
  ✓ Refuse probes outside rehearse
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up Python
  - Ensure tmux for the TUI frame
  ✓ Download the sealed build
  ✓ Resolve the leg dist and manifest fields
  ✓ Verify digests before install
  ✓ Prepare the isolated leg environment
  - Resolve the previous installable PyPI release
  ✓ Run the exercise leg
  ✓ Upload the leg evidence
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ exercise-legs (ubuntu-latest, wheel) in 1m8s (ID 130115802657)
  ✓ Set up job
  ✓ Refuse probes outside rehearse
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up Python
  - Ensure tmux for the TUI frame
  ✓ Download the sealed build
  ✓ Resolve the leg dist and manifest fields
  ✓ Verify digests before install
  ✓ Prepare the isolated leg environment
  ✓ Resolve the previous installable PyPI release
  ✓ Run the exercise leg
  ✓ Upload the leg evidence
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ exercise-legs (macos-latest, sdist) in 1m18s (ID 130115802821)
  ✓ Set up job
  ✓ Refuse probes outside rehearse
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up Python
  ✓ Ensure tmux for the TUI frame
  ✓ Download the sealed build
  ✓ Resolve the leg dist and manifest fields
  ✓ Verify digests before install
  ✓ Prepare the isolated leg environment
  - Resolve the previous installable PyPI release
  ✓ Run the exercise leg
  ✓ Upload the leg evidence
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
- stash (ID 130115805318)
✓ qualify-ci / prepare in 26s (ID 130116069325)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Validate qualification inputs
  ✓ Download the sealed candidate manifest
  ✓ Bind published identity from the sealed manifest
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
- qualify-ci / release-core-floor-smoke (ID 130116071518)
- qualify-ci / docs-build (ID 130116072055)
✓ qualify-ci / build-core / build-core in 8m41s (ID 130116334196)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Resolve core mode
  - Resolve pinned Rust core revision
  - Check out Rust core
  ✓ Check out published Rust core tag
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up Rust
  ✓ Cache Rust build
  - Build abi3 Rust core wheel
  ✓ Download the sealed candidate manifest
  ✓ Fetch and verify the published core wheel
  ✓ Build macro LSP
  - Record wheel provenance
  ✓ Record published tag provenance
  ✓ Upload Rust core artifacts
  ✓ Post Cache Rust build
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Check out published Rust core tag
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ exercise in 27s (ID 130117005549)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Download the sealed build
  ✓ Download the leg evidence
  ✓ Merge the legs into one exercise observation
  - Stash the exercise observation on the draft release
  ✓ Upload the exercise observation artifact
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ qualify-ci / perf-floors in 9m50s (ID 130121174612)
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
✓ qualify-ci / tutorial-tests in 1m4s (ID 130121174619)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run tutorial tests
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* qualify-ci / visual-test (ID 130121174667)
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
X qualify-ci / lint in 1m31s (ID 130121174682)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up preflight Python
  ✓ Download Rust core artifacts for bindings preflight
  ✓ Preflight core bindings
  ✓ Install dependencies
  ✓ Check pinned core bindings
  ✓ Bootstrap SDD sidecars
  ✓ Initialize SASE home
  ✓ Run actions/setup-go@v5
  ✓ Cache Go binaries
  - Install Go tools (keep-sorted)
  ✓ Cache Prettier dependencies
  ✓ Check Python formatting
  ✓ Check Markdown formatting
  X Check generated model docs
  - Check shipped model policy
  - Lint
  - SASE validation
  - Validate committed plans
  - Build and verify package
  ✓ Record installed core version
  ✓ Write qualification evidence
  ✓ Upload qualification evidence
  - Post Cache Prettier dependencies
  - Post Cache Go binaries
  - Post Run actions/setup-go@v5
  ✓ Post Install dependencies
  - Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* qualify-ci / test (3.14) (ID 130121174714)
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
* qualify-ci / test (3.13) (ID 130121174802)
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
* qualify-ci / test (3.12) (ID 130121174849)
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
✓ qualify-ci / ace-page-group-isolation in 1m37s (ID 130121174850)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  ✓ Run ACE shared-page isolation lane
  ✓ Post Install visual dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
identity: .github#7

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
identity: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
build: .github#4

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0sIHzagAAAAB30fM6H9ufTppmpzFOLFMkUEhMMzBFREdFMDEwOABFZGdl
build: .github#7

! Failed to restore: Cache service responded with 400
build: .github#24

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
build: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-prepare: .github#9

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-prepare: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
exercise-legs (macos-latest, wheel): .github#2

- Due to capacity constraints, jobs targeting macOS arm64 runners may experience longer queue times.
exercise-legs (macos-latest, wheel): .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
exercise-legs (ubuntu-latest, sdist): .github#2

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
exercise-legs (ubuntu-latest, sdist): .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
exercise-legs (ubuntu-latest, wheel): .github#2

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
exercise-legs (ubuntu-latest, wheel): .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
exercise-legs (macos-latest, sdist): .github#2

- Due to capacity constraints, jobs targeting macOS arm64 runners may experience longer queue times.
exercise-legs (macos-latest, sdist): .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / prepare: .github#10

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / prepare: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / build-core / build-core: .github#5

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>09YPzagAAAAAiPR5XKRSoQpRg352ExmJxQ0gxQUEyMDMwODE0MDYwAEVkZ2U=
qualify-ci / build-core / build-core: .github#7

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / tutorial-tests: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0OITzagAAAACMpVdYEU0wTYGlMGZQR9ksQ0gxQUEyMDMwODEzMDYwAEVkZ2U=
qualify-ci / tutorial-tests: .github#9

! Failed to restore: Cache service responded with 400
qualify-ci / tutorial-tests: .github#49

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / tutorial-tests: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache@v4, actions/checkout@v4, actions/download-artifact@v4, actions/setup-go@v5, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / lint: .github#2

X Process completed with exit code 1.
qualify-ci / lint: .github#16

! Failed to restore: Cache service responded with 400
qualify-ci / lint: .github#52

! Failed to restore: Cache service responded with 400
qualify-ci / lint: .github#24

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / lint: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / ace-page-group-isolation: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0WITzagAAAAAzCcEmW9wlRq5yhIB141iuQ0gxQUEyMDMwODEzMDI1AEVkZ2U=
qualify-ci / ace-page-group-isolation: .github#9

! Failed to restore: Cache service responded with 400
qualify-ci / ace-page-group-isolation: .github#49

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / ace-page-group-isolation: .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* release-please--branches--master Release sase-org/sase#322 · 42897628895
Triggered via workflow_dispatch about 43 minutes ago

JOBS
✓ identity in 57s (ID 130114862321)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Assert source and version identity
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ build in 38s (ID 130115420556)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up Python
  ✓ Build once and check the dist set
  ✓ Resolve the exact core pin
  ✓ Fetch the core file list and digests
  ✓ Read the core completeness set at the pin's tag
  ✓ Prove the core tag contains the source pin
  ✓ Seal the candidate manifest
  ✓ Upload the candidate build
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ qualify-prepare in 26s (ID 130115802507)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Download the sealed candidate build
  ✓ Bind the sealed candidate identity
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ exercise-legs (macos-latest, wheel) in 2m5s (ID 130115802596)
  ✓ Set up job
  ✓ Refuse probes outside rehearse
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up Python
  ✓ Ensure tmux for the TUI frame
  ✓ Download the sealed build
  ✓ Resolve the leg dist and manifest fields
  ✓ Verify digests before install
  ✓ Prepare the isolated leg environment
  ✓ Resolve the previous installable PyPI release
  ✓ Run the exercise leg
  ✓ Upload the leg evidence
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ exercise-legs (ubuntu-latest, sdist) in 54s (ID 130115802632)
  ✓ Set up job
  ✓ Refuse probes outside rehearse
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up Python
  - Ensure tmux for the TUI frame
  ✓ Download the sealed build
  ✓ Resolve the leg dist and manifest fields
  ✓ Verify digests before install
  ✓ Prepare the isolated leg environment
  - Resolve the previous installable PyPI release
  ✓ Run the exercise leg
  ✓ Upload the leg evidence
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ exercise-legs (ubuntu-latest, wheel) in 1m8s (ID 130115802657)
  ✓ Set up job
  ✓ Refuse probes outside rehearse
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up Python
  - Ensure tmux for the TUI frame
  ✓ Download the sealed build
  ✓ Resolve the leg dist and manifest fields
  ✓ Verify digests before install
  ✓ Prepare the isolated leg environment
  ✓ Resolve the previous installable PyPI release
  ✓ Run the exercise leg
  ✓ Upload the leg evidence
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ exercise-legs (macos-latest, sdist) in 1m18s (ID 130115802821)
  ✓ Set up job
  ✓ Refuse probes outside rehearse
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up Python
  ✓ Ensure tmux for the TUI frame
  ✓ Download the sealed build
  ✓ Resolve the leg dist and manifest fields
  ✓ Verify digests before install
  ✓ Prepare the isolated leg environment
  - Resolve the previous installable PyPI release
  ✓ Run the exercise leg
  ✓ Upload the leg evidence
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
- stash (ID 130115805318)
✓ qualify-ci / prepare in 26s (ID 130116069325)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Validate qualification inputs
  ✓ Download the sealed candidate manifest
  ✓ Bind published identity from the sealed manifest
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
- qualify-ci / release-core-floor-smoke (ID 130116071518)
- qualify-ci / docs-build (ID 130116072055)
✓ qualify-ci / build-core / build-core in 8m41s (ID 130116334196)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Resolve core mode
  - Resolve pinned Rust core revision
  - Check out Rust core
  ✓ Check out published Rust core tag
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up Rust
  ✓ Cache Rust build
  - Build abi3 Rust core wheel
  ✓ Download the sealed candidate manifest
  ✓ Fetch and verify the published core wheel
  ✓ Build macro LSP
  - Record wheel provenance
  ✓ Record published tag provenance
  ✓ Upload Rust core artifacts
  ✓ Post Cache Rust build
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Check out published Rust core tag
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ exercise in 27s (ID 130117005549)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Download the sealed build
  ✓ Download the leg evidence
  ✓ Merge the legs into one exercise observation
  - Stash the exercise observation on the draft release
  ✓ Upload the exercise observation artifact
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ qualify-ci / perf-floors in 9m50s (ID 130121174612)
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
✓ qualify-ci / tutorial-tests in 1m4s (ID 130121174619)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run tutorial tests
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* qualify-ci / visual-test (ID 130121174667)
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
X qualify-ci / lint in 1m31s (ID 130121174682)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up preflight Python
  ✓ Download Rust core artifacts for bindings preflight
  ✓ Preflight core bindings
  ✓ Install dependencies
  ✓ Check pinned core bindings
  ✓ Bootstrap SDD sidecars
  ✓ Initialize SASE home
  ✓ Run actions/setup-go@v5
  ✓ Cache Go binaries
  - Install Go tools (keep-sorted)
  ✓ Cache Prettier dependencies
  ✓ Check Python formatting
  ✓ Check Markdown formatting
  X Check generated model docs
  - Check shipped model policy
  - Lint
  - SASE validation
  - Validate committed plans
  - Build and verify package
  ✓ Record installed core version
  ✓ Write qualification evidence
  ✓ Upload qualification evidence
  - Post Cache Prettier dependencies
  - Post Cache Go binaries
  - Post Run actions/setup-go@v5
  ✓ Post Install dependencies
  - Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* qualify-ci / test (3.14) (ID 130121174714)
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
* qualify-ci / test (3.13) (ID 130121174802)
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
* qualify-ci / test (3.12) (ID 130121174849)
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
✓ qualify-ci / ace-page-group-isolation in 1m37s (ID 130121174850)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  ✓ Run ACE shared-page isolation lane
  ✓ Post Install visual dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
identity: .github#7

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
identity: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
build: .github#4

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0sIHzagAAAAB30fM6H9ufTppmpzFOLFMkUEhMMzBFREdFMDEwOABFZGdl
build: .github#7

! Failed to restore: Cache service responded with 400
build: .github#24

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
build: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-prepare: .github#9

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-prepare: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
exercise-legs (macos-latest, wheel): .github#2

- Due to capacity constraints, jobs targeting macOS arm64 runners may experience longer queue times.
exercise-legs (macos-latest, wheel): .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
exercise-legs (ubuntu-latest, sdist): .github#2

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
exercise-legs (ubuntu-latest, sdist): .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
exercise-legs (ubuntu-latest, wheel): .github#2

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
exercise-legs (ubuntu-latest, wheel): .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
exercise-legs (macos-latest, sdist): .github#2

- Due to capacity constraints, jobs targeting macOS arm64 runners may experience longer queue times.
exercise-legs (macos-latest, sdist): .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / prepare: .github#10

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / prepare: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / build-core / build-core: .github#5

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>09YPzagAAAAAiPR5XKRSoQpRg352ExmJxQ0gxQUEyMDMwODE0MDYwAEVkZ2U=
qualify-ci / build-core / build-core: .github#7

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / tutorial-tests: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0OITzagAAAACMpVdYEU0wTYGlMGZQR9ksQ0gxQUEyMDMwODEzMDYwAEVkZ2U=
qualify-ci / tutorial-tests: .github#9

! Failed to restore: Cache service responded with 400
qualify-ci / tutorial-tests: .github#49

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / tutorial-tests: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache@v4, actions/checkout@v4, actions/download-artifact@v4, actions/setup-go@v5, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / lint: .github#2

X Process completed with exit code 1.
qualify-ci / lint: .github#16

! Failed to restore: Cache service responded with 400
qualify-ci / lint: .github#52

! Failed to restore: Cache service responded with 400
qualify-ci / lint: .github#24

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / lint: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / ace-page-group-isolation: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0WITzagAAAAAzCcEmW9wlRq5yhIB141iuQ0gxQUEyMDMwODEzMDI1AEVkZ2U=
qualify-ci / ace-page-group-isolation: .github#9

! Failed to restore: Cache service responded with 400
qualify-ci / ace-page-group-isolation: .github#49

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / ace-page-group-isolation: .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* release-please--branches--master Release sase-org/sase#322 · 42897628895
Triggered via workflow_dispatch about 45 minutes ago

JOBS
✓ identity in 57s (ID 130114862321)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Assert source and version identity
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ build in 38s (ID 130115420556)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up Python
  ✓ Build once and check the dist set
  ✓ Resolve the exact core pin
  ✓ Fetch the core file list and digests
  ✓ Read the core completeness set at the pin's tag
  ✓ Prove the core tag contains the source pin
  ✓ Seal the candidate manifest
  ✓ Upload the candidate build
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ qualify-prepare in 26s (ID 130115802507)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Download the sealed candidate build
  ✓ Bind the sealed candidate identity
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ exercise-legs (macos-latest, wheel) in 2m5s (ID 130115802596)
  ✓ Set up job
  ✓ Refuse probes outside rehearse
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up Python
  ✓ Ensure tmux for the TUI frame
  ✓ Download the sealed build
  ✓ Resolve the leg dist and manifest fields
  ✓ Verify digests before install
  ✓ Prepare the isolated leg environment
  ✓ Resolve the previous installable PyPI release
  ✓ Run the exercise leg
  ✓ Upload the leg evidence
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ exercise-legs (ubuntu-latest, sdist) in 54s (ID 130115802632)
  ✓ Set up job
  ✓ Refuse probes outside rehearse
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up Python
  - Ensure tmux for the TUI frame
  ✓ Download the sealed build
  ✓ Resolve the leg dist and manifest fields
  ✓ Verify digests before install
  ✓ Prepare the isolated leg environment
  - Resolve the previous installable PyPI release
  ✓ Run the exercise leg
  ✓ Upload the leg evidence
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ exercise-legs (ubuntu-latest, wheel) in 1m8s (ID 130115802657)
  ✓ Set up job
  ✓ Refuse probes outside rehearse
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up Python
  - Ensure tmux for the TUI frame
  ✓ Download the sealed build
  ✓ Resolve the leg dist and manifest fields
  ✓ Verify digests before install
  ✓ Prepare the isolated leg environment
  ✓ Resolve the previous installable PyPI release
  ✓ Run the exercise leg
  ✓ Upload the leg evidence
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ exercise-legs (macos-latest, sdist) in 1m18s (ID 130115802821)
  ✓ Set up job
  ✓ Refuse probes outside rehearse
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up Python
  ✓ Ensure tmux for the TUI frame
  ✓ Download the sealed build
  ✓ Resolve the leg dist and manifest fields
  ✓ Verify digests before install
  ✓ Prepare the isolated leg environment
  - Resolve the previous installable PyPI release
  ✓ Run the exercise leg
  ✓ Upload the leg evidence
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
- stash (ID 130115805318)
✓ qualify-ci / prepare in 26s (ID 130116069325)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Validate qualification inputs
  ✓ Download the sealed candidate manifest
  ✓ Bind published identity from the sealed manifest
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
- qualify-ci / release-core-floor-smoke (ID 130116071518)
- qualify-ci / docs-build (ID 130116072055)
✓ qualify-ci / build-core / build-core in 8m41s (ID 130116334196)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Resolve core mode
  - Resolve pinned Rust core revision
  - Check out Rust core
  ✓ Check out published Rust core tag
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up Rust
  ✓ Cache Rust build
  - Build abi3 Rust core wheel
  ✓ Download the sealed candidate manifest
  ✓ Fetch and verify the published core wheel
  ✓ Build macro LSP
  - Record wheel provenance
  ✓ Record published tag provenance
  ✓ Upload Rust core artifacts
  ✓ Post Cache Rust build
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Check out published Rust core tag
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ exercise in 27s (ID 130117005549)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Download the sealed build
  ✓ Download the leg evidence
  ✓ Merge the legs into one exercise observation
  - Stash the exercise observation on the draft release
  ✓ Upload the exercise observation artifact
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ qualify-ci / perf-floors in 9m50s (ID 130121174612)
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
✓ qualify-ci / tutorial-tests in 1m4s (ID 130121174619)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run tutorial tests
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* qualify-ci / visual-test (ID 130121174667)
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
X qualify-ci / lint in 1m31s (ID 130121174682)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up preflight Python
  ✓ Download Rust core artifacts for bindings preflight
  ✓ Preflight core bindings
  ✓ Install dependencies
  ✓ Check pinned core bindings
  ✓ Bootstrap SDD sidecars
  ✓ Initialize SASE home
  ✓ Run actions/setup-go@v5
  ✓ Cache Go binaries
  - Install Go tools (keep-sorted)
  ✓ Cache Prettier dependencies
  ✓ Check Python formatting
  ✓ Check Markdown formatting
  X Check generated model docs
  - Check shipped model policy
  - Lint
  - SASE validation
  - Validate committed plans
  - Build and verify package
  ✓ Record installed core version
  ✓ Write qualification evidence
  ✓ Upload qualification evidence
  - Post Cache Prettier dependencies
  - Post Cache Go binaries
  - Post Run actions/setup-go@v5
  ✓ Post Install dependencies
  - Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* qualify-ci / test (3.14) (ID 130121174714)
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
* qualify-ci / test (3.13) (ID 130121174802)
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
* qualify-ci / test (3.12) (ID 130121174849)
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
✓ qualify-ci / ace-page-group-isolation in 1m37s (ID 130121174850)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  ✓ Run ACE shared-page isolation lane
  ✓ Post Install visual dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
identity: .github#7

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
identity: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
build: .github#4

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0sIHzagAAAAB30fM6H9ufTppmpzFOLFMkUEhMMzBFREdFMDEwOABFZGdl
build: .github#7

! Failed to restore: Cache service responded with 400
build: .github#24

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
build: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-prepare: .github#9

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-prepare: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
exercise-legs (macos-latest, wheel): .github#2

- Due to capacity constraints, jobs targeting macOS arm64 runners may experience longer queue times.
exercise-legs (macos-latest, wheel): .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
exercise-legs (ubuntu-latest, sdist): .github#2

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
exercise-legs (ubuntu-latest, sdist): .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
exercise-legs (ubuntu-latest, wheel): .github#2

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
exercise-legs (ubuntu-latest, wheel): .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
exercise-legs (macos-latest, sdist): .github#2

- Due to capacity constraints, jobs targeting macOS arm64 runners may experience longer queue times.
exercise-legs (macos-latest, sdist): .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / prepare: .github#10

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / prepare: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / build-core / build-core: .github#5

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>09YPzagAAAAAiPR5XKRSoQpRg352ExmJxQ0gxQUEyMDMwODE0MDYwAEVkZ2U=
qualify-ci / build-core / build-core: .github#7

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / tutorial-tests: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0OITzagAAAACMpVdYEU0wTYGlMGZQR9ksQ0gxQUEyMDMwODEzMDYwAEVkZ2U=
qualify-ci / tutorial-tests: .github#9

! Failed to restore: Cache service responded with 400
qualify-ci / tutorial-tests: .github#49

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / tutorial-tests: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache@v4, actions/checkout@v4, actions/download-artifact@v4, actions/setup-go@v5, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / lint: .github#2

X Process completed with exit code 1.
qualify-ci / lint: .github#16

! Failed to restore: Cache service responded with 400
qualify-ci / lint: .github#52

! Failed to restore: Cache service responded with 400
qualify-ci / lint: .github#24

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / lint: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / ace-page-group-isolation: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0WITzagAAAAAzCcEmW9wlRq5yhIB141iuQ0gxQUEyMDMwODEzMDI1AEVkZ2U=
qualify-ci / ace-page-group-isolation: .github#9

! Failed to restore: Cache service responded with 400
qualify-ci / ace-page-group-isolation: .github#49

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / ace-page-group-isolation: .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* release-please--branches--master Release sase-org/sase#322 · 42897628895
Triggered via workflow_dispatch about 47 minutes ago

JOBS
✓ identity in 57s (ID 130114862321)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Assert source and version identity
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ build in 38s (ID 130115420556)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up Python
  ✓ Build once and check the dist set
  ✓ Resolve the exact core pin
  ✓ Fetch the core file list and digests
  ✓ Read the core completeness set at the pin's tag
  ✓ Prove the core tag contains the source pin
  ✓ Seal the candidate manifest
  ✓ Upload the candidate build
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ qualify-prepare in 26s (ID 130115802507)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Download the sealed candidate build
  ✓ Bind the sealed candidate identity
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ exercise-legs (macos-latest, wheel) in 2m5s (ID 130115802596)
  ✓ Set up job
  ✓ Refuse probes outside rehearse
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up Python
  ✓ Ensure tmux for the TUI frame
  ✓ Download the sealed build
  ✓ Resolve the leg dist and manifest fields
  ✓ Verify digests before install
  ✓ Prepare the isolated leg environment
  ✓ Resolve the previous installable PyPI release
  ✓ Run the exercise leg
  ✓ Upload the leg evidence
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ exercise-legs (ubuntu-latest, sdist) in 54s (ID 130115802632)
  ✓ Set up job
  ✓ Refuse probes outside rehearse
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up Python
  - Ensure tmux for the TUI frame
  ✓ Download the sealed build
  ✓ Resolve the leg dist and manifest fields
  ✓ Verify digests before install
  ✓ Prepare the isolated leg environment
  - Resolve the previous installable PyPI release
  ✓ Run the exercise leg
  ✓ Upload the leg evidence
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ exercise-legs (ubuntu-latest, wheel) in 1m8s (ID 130115802657)
  ✓ Set up job
  ✓ Refuse probes outside rehearse
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up Python
  - Ensure tmux for the TUI frame
  ✓ Download the sealed build
  ✓ Resolve the leg dist and manifest fields
  ✓ Verify digests before install
  ✓ Prepare the isolated leg environment
  ✓ Resolve the previous installable PyPI release
  ✓ Run the exercise leg
  ✓ Upload the leg evidence
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ exercise-legs (macos-latest, sdist) in 1m18s (ID 130115802821)
  ✓ Set up job
  ✓ Refuse probes outside rehearse
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up Python
  ✓ Ensure tmux for the TUI frame
  ✓ Download the sealed build
  ✓ Resolve the leg dist and manifest fields
  ✓ Verify digests before install
  ✓ Prepare the isolated leg environment
  - Resolve the previous installable PyPI release
  ✓ Run the exercise leg
  ✓ Upload the leg evidence
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
- stash (ID 130115805318)
✓ qualify-ci / prepare in 26s (ID 130116069325)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Validate qualification inputs
  ✓ Download the sealed candidate manifest
  ✓ Bind published identity from the sealed manifest
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
- qualify-ci / release-core-floor-smoke (ID 130116071518)
- qualify-ci / docs-build (ID 130116072055)
✓ qualify-ci / build-core / build-core in 8m41s (ID 130116334196)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Resolve core mode
  - Resolve pinned Rust core revision
  - Check out Rust core
  ✓ Check out published Rust core tag
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up Rust
  ✓ Cache Rust build
  - Build abi3 Rust core wheel
  ✓ Download the sealed candidate manifest
  ✓ Fetch and verify the published core wheel
  ✓ Build macro LSP
  - Record wheel provenance
  ✓ Record published tag provenance
  ✓ Upload Rust core artifacts
  ✓ Post Cache Rust build
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Check out published Rust core tag
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ exercise in 27s (ID 130117005549)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Download the sealed build
  ✓ Download the leg evidence
  ✓ Merge the legs into one exercise observation
  - Stash the exercise observation on the draft release
  ✓ Upload the exercise observation artifact
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ qualify-ci / perf-floors in 9m50s (ID 130121174612)
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
✓ qualify-ci / tutorial-tests in 1m4s (ID 130121174619)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run tutorial tests
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
X qualify-ci / visual-test in 34m4s (ID 130121174667)
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
X qualify-ci / lint in 1m31s (ID 130121174682)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up preflight Python
  ✓ Download Rust core artifacts for bindings preflight
  ✓ Preflight core bindings
  ✓ Install dependencies
  ✓ Check pinned core bindings
  ✓ Bootstrap SDD sidecars
  ✓ Initialize SASE home
  ✓ Run actions/setup-go@v5
  ✓ Cache Go binaries
  - Install Go tools (keep-sorted)
  ✓ Cache Prettier dependencies
  ✓ Check Python formatting
  ✓ Check Markdown formatting
  X Check generated model docs
  - Check shipped model policy
  - Lint
  - SASE validation
  - Validate committed plans
  - Build and verify package
  ✓ Record installed core version
  ✓ Write qualification evidence
  ✓ Upload qualification evidence
  - Post Cache Prettier dependencies
  - Post Cache Go binaries
  - Post Run actions/setup-go@v5
  ✓ Post Install dependencies
  - Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* qualify-ci / test (3.14) (ID 130121174714)
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
* qualify-ci / test (3.13) (ID 130121174802)
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
* qualify-ci / test (3.12) (ID 130121174849)
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
✓ qualify-ci / ace-page-group-isolation in 1m37s (ID 130121174850)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  ✓ Run ACE shared-page isolation lane
  ✓ Post Install visual dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
identity: .github#7

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
identity: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
build: .github#4

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0sIHzagAAAAB30fM6H9ufTppmpzFOLFMkUEhMMzBFREdFMDEwOABFZGdl
build: .github#7

! Failed to restore: Cache service responded with 400
build: .github#24

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
build: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-prepare: .github#9

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-prepare: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
exercise-legs (macos-latest, wheel): .github#2

- Due to capacity constraints, jobs targeting macOS arm64 runners may experience longer queue times.
exercise-legs (macos-latest, wheel): .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
exercise-legs (ubuntu-latest, sdist): .github#2

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
exercise-legs (ubuntu-latest, sdist): .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
exercise-legs (ubuntu-latest, wheel): .github#2

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
exercise-legs (ubuntu-latest, wheel): .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
exercise-legs (macos-latest, sdist): .github#2

- Due to capacity constraints, jobs targeting macOS arm64 runners may experience longer queue times.
exercise-legs (macos-latest, sdist): .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / prepare: .github#10

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / prepare: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / build-core / build-core: .github#5

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>09YPzagAAAAAiPR5XKRSoQpRg352ExmJxQ0gxQUEyMDMwODE0MDYwAEVkZ2U=
qualify-ci / build-core / build-core: .github#7

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / tutorial-tests: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0OITzagAAAACMpVdYEU0wTYGlMGZQR9ksQ0gxQUEyMDMwODEzMDYwAEVkZ2U=
qualify-ci / tutorial-tests: .github#9

! Failed to restore: Cache service responded with 400
qualify-ci / tutorial-tests: .github#49

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / tutorial-tests: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache@v4, actions/checkout@v4, actions/download-artifact@v4, actions/setup-go@v5, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / lint: .github#2

X Process completed with exit code 1.
qualify-ci / lint: .github#16

! Failed to restore: Cache service responded with 400
qualify-ci / lint: .github#52

! Failed to restore: Cache service responded with 400
qualify-ci / lint: .github#24

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / lint: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / ace-page-group-isolation: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0WITzagAAAAAzCcEmW9wlRq5yhIB141iuQ0gxQUEyMDMwODEzMDI1AEVkZ2U=
qualify-ci / ace-page-group-isolation: .github#9

! Failed to restore: Cache service responded with 400
qualify-ci / ace-page-group-isolation: .github#49

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / ace-page-group-isolation: .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* release-please--branches--master Release sase-org/sase#322 · 42897628895
Triggered via workflow_dispatch about 49 minutes ago

JOBS
✓ identity in 57s (ID 130114862321)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Assert source and version identity
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ build in 38s (ID 130115420556)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up Python
  ✓ Build once and check the dist set
  ✓ Resolve the exact core pin
  ✓ Fetch the core file list and digests
  ✓ Read the core completeness set at the pin's tag
  ✓ Prove the core tag contains the source pin
  ✓ Seal the candidate manifest
  ✓ Upload the candidate build
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ qualify-prepare in 26s (ID 130115802507)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Download the sealed candidate build
  ✓ Bind the sealed candidate identity
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ exercise-legs (macos-latest, wheel) in 2m5s (ID 130115802596)
  ✓ Set up job
  ✓ Refuse probes outside rehearse
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up Python
  ✓ Ensure tmux for the TUI frame
  ✓ Download the sealed build
  ✓ Resolve the leg dist and manifest fields
  ✓ Verify digests before install
  ✓ Prepare the isolated leg environment
  ✓ Resolve the previous installable PyPI release
  ✓ Run the exercise leg
  ✓ Upload the leg evidence
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ exercise-legs (ubuntu-latest, sdist) in 54s (ID 130115802632)
  ✓ Set up job
  ✓ Refuse probes outside rehearse
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up Python
  - Ensure tmux for the TUI frame
  ✓ Download the sealed build
  ✓ Resolve the leg dist and manifest fields
  ✓ Verify digests before install
  ✓ Prepare the isolated leg environment
  - Resolve the previous installable PyPI release
  ✓ Run the exercise leg
  ✓ Upload the leg evidence
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ exercise-legs (ubuntu-latest, wheel) in 1m8s (ID 130115802657)
  ✓ Set up job
  ✓ Refuse probes outside rehearse
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up Python
  - Ensure tmux for the TUI frame
  ✓ Download the sealed build
  ✓ Resolve the leg dist and manifest fields
  ✓ Verify digests before install
  ✓ Prepare the isolated leg environment
  ✓ Resolve the previous installable PyPI release
  ✓ Run the exercise leg
  ✓ Upload the leg evidence
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ exercise-legs (macos-latest, sdist) in 1m18s (ID 130115802821)
  ✓ Set up job
  ✓ Refuse probes outside rehearse
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up Python
  ✓ Ensure tmux for the TUI frame
  ✓ Download the sealed build
  ✓ Resolve the leg dist and manifest fields
  ✓ Verify digests before install
  ✓ Prepare the isolated leg environment
  - Resolve the previous installable PyPI release
  ✓ Run the exercise leg
  ✓ Upload the leg evidence
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
- stash (ID 130115805318)
✓ qualify-ci / prepare in 26s (ID 130116069325)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Validate qualification inputs
  ✓ Download the sealed candidate manifest
  ✓ Bind published identity from the sealed manifest
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
- qualify-ci / release-core-floor-smoke (ID 130116071518)
- qualify-ci / docs-build (ID 130116072055)
✓ qualify-ci / build-core / build-core in 8m41s (ID 130116334196)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Resolve core mode
  - Resolve pinned Rust core revision
  - Check out Rust core
  ✓ Check out published Rust core tag
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up Rust
  ✓ Cache Rust build
  - Build abi3 Rust core wheel
  ✓ Download the sealed candidate manifest
  ✓ Fetch and verify the published core wheel
  ✓ Build macro LSP
  - Record wheel provenance
  ✓ Record published tag provenance
  ✓ Upload Rust core artifacts
  ✓ Post Cache Rust build
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Check out published Rust core tag
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ exercise in 27s (ID 130117005549)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Download the sealed build
  ✓ Download the leg evidence
  ✓ Merge the legs into one exercise observation
  - Stash the exercise observation on the draft release
  ✓ Upload the exercise observation artifact
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ qualify-ci / perf-floors in 9m50s (ID 130121174612)
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
✓ qualify-ci / tutorial-tests in 1m4s (ID 130121174619)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run tutorial tests
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
X qualify-ci / visual-test in 34m4s (ID 130121174667)
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
X qualify-ci / lint in 1m31s (ID 130121174682)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up preflight Python
  ✓ Download Rust core artifacts for bindings preflight
  ✓ Preflight core bindings
  ✓ Install dependencies
  ✓ Check pinned core bindings
  ✓ Bootstrap SDD sidecars
  ✓ Initialize SASE home
  ✓ Run actions/setup-go@v5
  ✓ Cache Go binaries
  - Install Go tools (keep-sorted)
  ✓ Cache Prettier dependencies
  ✓ Check Python formatting
  ✓ Check Markdown formatting
  X Check generated model docs
  - Check shipped model policy
  - Lint
  - SASE validation
  - Validate committed plans
  - Build and verify package
  ✓ Record installed core version
  ✓ Write qualification evidence
  ✓ Upload qualification evidence
  - Post Cache Prettier dependencies
  - Post Cache Go binaries
  - Post Run actions/setup-go@v5
  ✓ Post Install dependencies
  - Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* qualify-ci / test (3.14) (ID 130121174714)
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
* qualify-ci / test (3.13) (ID 130121174802)
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
* qualify-ci / test (3.12) (ID 130121174849)
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
✓ qualify-ci / ace-page-group-isolation in 1m37s (ID 130121174850)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  ✓ Run ACE shared-page isolation lane
  ✓ Post Install visual dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
identity: .github#7

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
identity: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
build: .github#4

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0sIHzagAAAAB30fM6H9ufTppmpzFOLFMkUEhMMzBFREdFMDEwOABFZGdl
build: .github#7

! Failed to restore: Cache service responded with 400
build: .github#24

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
build: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-prepare: .github#9

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-prepare: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
exercise-legs (macos-latest, wheel): .github#2

- Due to capacity constraints, jobs targeting macOS arm64 runners may experience longer queue times.
exercise-legs (macos-latest, wheel): .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
exercise-legs (ubuntu-latest, sdist): .github#2

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
exercise-legs (ubuntu-latest, sdist): .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
exercise-legs (ubuntu-latest, wheel): .github#2

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
exercise-legs (ubuntu-latest, wheel): .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
exercise-legs (macos-latest, sdist): .github#2

- Due to capacity constraints, jobs targeting macOS arm64 runners may experience longer queue times.
exercise-legs (macos-latest, sdist): .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / prepare: .github#10

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / prepare: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / build-core / build-core: .github#5

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>09YPzagAAAAAiPR5XKRSoQpRg352ExmJxQ0gxQUEyMDMwODE0MDYwAEVkZ2U=
qualify-ci / build-core / build-core: .github#7

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / tutorial-tests: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0OITzagAAAACMpVdYEU0wTYGlMGZQR9ksQ0gxQUEyMDMwODEzMDYwAEVkZ2U=
qualify-ci / tutorial-tests: .github#9

! Failed to restore: Cache service responded with 400
qualify-ci / tutorial-tests: .github#49

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / tutorial-tests: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache@v4, actions/checkout@v4, actions/download-artifact@v4, actions/setup-go@v5, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / lint: .github#2

X Process completed with exit code 1.
qualify-ci / lint: .github#16

! Failed to restore: Cache service responded with 400
qualify-ci / lint: .github#52

! Failed to restore: Cache service responded with 400
qualify-ci / lint: .github#24

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / lint: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / ace-page-group-isolation: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0WITzagAAAAAzCcEmW9wlRq5yhIB141iuQ0gxQUEyMDMwODEzMDI1AEVkZ2U=
qualify-ci / ace-page-group-isolation: .github#9

! Failed to restore: Cache service responded with 400
qualify-ci / ace-page-group-isolation: .github#49

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / ace-page-group-isolation: .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* release-please--branches--master Release sase-org/sase#322 · 42897628895
Triggered via workflow_dispatch about 51 minutes ago

JOBS
✓ identity in 57s (ID 130114862321)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Assert source and version identity
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ build in 38s (ID 130115420556)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up Python
  ✓ Build once and check the dist set
  ✓ Resolve the exact core pin
  ✓ Fetch the core file list and digests
  ✓ Read the core completeness set at the pin's tag
  ✓ Prove the core tag contains the source pin
  ✓ Seal the candidate manifest
  ✓ Upload the candidate build
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ qualify-prepare in 26s (ID 130115802507)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Download the sealed candidate build
  ✓ Bind the sealed candidate identity
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ exercise-legs (macos-latest, wheel) in 2m5s (ID 130115802596)
  ✓ Set up job
  ✓ Refuse probes outside rehearse
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up Python
  ✓ Ensure tmux for the TUI frame
  ✓ Download the sealed build
  ✓ Resolve the leg dist and manifest fields
  ✓ Verify digests before install
  ✓ Prepare the isolated leg environment
  ✓ Resolve the previous installable PyPI release
  ✓ Run the exercise leg
  ✓ Upload the leg evidence
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ exercise-legs (ubuntu-latest, sdist) in 54s (ID 130115802632)
  ✓ Set up job
  ✓ Refuse probes outside rehearse
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up Python
  - Ensure tmux for the TUI frame
  ✓ Download the sealed build
  ✓ Resolve the leg dist and manifest fields
  ✓ Verify digests before install
  ✓ Prepare the isolated leg environment
  - Resolve the previous installable PyPI release
  ✓ Run the exercise leg
  ✓ Upload the leg evidence
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ exercise-legs (ubuntu-latest, wheel) in 1m8s (ID 130115802657)
  ✓ Set up job
  ✓ Refuse probes outside rehearse
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up Python
  - Ensure tmux for the TUI frame
  ✓ Download the sealed build
  ✓ Resolve the leg dist and manifest fields
  ✓ Verify digests before install
  ✓ Prepare the isolated leg environment
  ✓ Resolve the previous installable PyPI release
  ✓ Run the exercise leg
  ✓ Upload the leg evidence
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ exercise-legs (macos-latest, sdist) in 1m18s (ID 130115802821)
  ✓ Set up job
  ✓ Refuse probes outside rehearse
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up Python
  ✓ Ensure tmux for the TUI frame
  ✓ Download the sealed build
  ✓ Resolve the leg dist and manifest fields
  ✓ Verify digests before install
  ✓ Prepare the isolated leg environment
  - Resolve the previous installable PyPI release
  ✓ Run the exercise leg
  ✓ Upload the leg evidence
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
- stash (ID 130115805318)
✓ qualify-ci / prepare in 26s (ID 130116069325)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Validate qualification inputs
  ✓ Download the sealed candidate manifest
  ✓ Bind published identity from the sealed manifest
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
- qualify-ci / release-core-floor-smoke (ID 130116071518)
- qualify-ci / docs-build (ID 130116072055)
✓ qualify-ci / build-core / build-core in 8m41s (ID 130116334196)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Resolve core mode
  - Resolve pinned Rust core revision
  - Check out Rust core
  ✓ Check out published Rust core tag
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up Rust
  ✓ Cache Rust build
  - Build abi3 Rust core wheel
  ✓ Download the sealed candidate manifest
  ✓ Fetch and verify the published core wheel
  ✓ Build macro LSP
  - Record wheel provenance
  ✓ Record published tag provenance
  ✓ Upload Rust core artifacts
  ✓ Post Cache Rust build
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Check out published Rust core tag
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ exercise in 27s (ID 130117005549)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Download the sealed build
  ✓ Download the leg evidence
  ✓ Merge the legs into one exercise observation
  - Stash the exercise observation on the draft release
  ✓ Upload the exercise observation artifact
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ qualify-ci / perf-floors in 9m50s (ID 130121174612)
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
✓ qualify-ci / tutorial-tests in 1m4s (ID 130121174619)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run tutorial tests
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
X qualify-ci / visual-test in 34m4s (ID 130121174667)
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
X qualify-ci / lint in 1m31s (ID 130121174682)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up preflight Python
  ✓ Download Rust core artifacts for bindings preflight
  ✓ Preflight core bindings
  ✓ Install dependencies
  ✓ Check pinned core bindings
  ✓ Bootstrap SDD sidecars
  ✓ Initialize SASE home
  ✓ Run actions/setup-go@v5
  ✓ Cache Go binaries
  - Install Go tools (keep-sorted)
  ✓ Cache Prettier dependencies
  ✓ Check Python formatting
  ✓ Check Markdown formatting
  X Check generated model docs
  - Check shipped model policy
  - Lint
  - SASE validation
  - Validate committed plans
  - Build and verify package
  ✓ Record installed core version
  ✓ Write qualification evidence
  ✓ Upload qualification evidence
  - Post Cache Prettier dependencies
  - Post Cache Go binaries
  - Post Run actions/setup-go@v5
  ✓ Post Install dependencies
  - Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* qualify-ci / test (3.14) (ID 130121174714)
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
* qualify-ci / test (3.13) (ID 130121174802)
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
* qualify-ci / test (3.12) (ID 130121174849)
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
✓ qualify-ci / ace-page-group-isolation in 1m37s (ID 130121174850)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  ✓ Run ACE shared-page isolation lane
  ✓ Post Install visual dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
identity: .github#7

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
identity: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
build: .github#4

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0sIHzagAAAAB30fM6H9ufTppmpzFOLFMkUEhMMzBFREdFMDEwOABFZGdl
build: .github#7

! Failed to restore: Cache service responded with 400
build: .github#24

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
build: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-prepare: .github#9

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-prepare: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
exercise-legs (macos-latest, wheel): .github#2

- Due to capacity constraints, jobs targeting macOS arm64 runners may experience longer queue times.
exercise-legs (macos-latest, wheel): .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
exercise-legs (ubuntu-latest, sdist): .github#2

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
exercise-legs (ubuntu-latest, sdist): .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
exercise-legs (ubuntu-latest, wheel): .github#2

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
exercise-legs (ubuntu-latest, wheel): .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
exercise-legs (macos-latest, sdist): .github#2

- Due to capacity constraints, jobs targeting macOS arm64 runners may experience longer queue times.
exercise-legs (macos-latest, sdist): .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / prepare: .github#10

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / prepare: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / build-core / build-core: .github#5

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>09YPzagAAAAAiPR5XKRSoQpRg352ExmJxQ0gxQUEyMDMwODE0MDYwAEVkZ2U=
qualify-ci / build-core / build-core: .github#7

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / tutorial-tests: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0OITzagAAAACMpVdYEU0wTYGlMGZQR9ksQ0gxQUEyMDMwODEzMDYwAEVkZ2U=
qualify-ci / tutorial-tests: .github#9

! Failed to restore: Cache service responded with 400
qualify-ci / tutorial-tests: .github#49

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / tutorial-tests: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache@v4, actions/checkout@v4, actions/download-artifact@v4, actions/setup-go@v5, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / lint: .github#2

X Process completed with exit code 1.
qualify-ci / lint: .github#16

! Failed to restore: Cache service responded with 400
qualify-ci / lint: .github#52

! Failed to restore: Cache service responded with 400
qualify-ci / lint: .github#24

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / lint: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / ace-page-group-isolation: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0WITzagAAAAAzCcEmW9wlRq5yhIB141iuQ0gxQUEyMDMwODEzMDI1AEVkZ2U=
qualify-ci / ace-page-group-isolation: .github#9

! Failed to restore: Cache service responded with 400
qualify-ci / ace-page-group-isolation: .github#49

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / ace-page-group-isolation: .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* release-please--branches--master Release sase-org/sase#322 · 42897628895
Triggered via workflow_dispatch about 53 minutes ago

JOBS
✓ identity in 57s (ID 130114862321)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Assert source and version identity
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ build in 38s (ID 130115420556)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up Python
  ✓ Build once and check the dist set
  ✓ Resolve the exact core pin
  ✓ Fetch the core file list and digests
  ✓ Read the core completeness set at the pin's tag
  ✓ Prove the core tag contains the source pin
  ✓ Seal the candidate manifest
  ✓ Upload the candidate build
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ qualify-prepare in 26s (ID 130115802507)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Download the sealed candidate build
  ✓ Bind the sealed candidate identity
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ exercise-legs (macos-latest, wheel) in 2m5s (ID 130115802596)
  ✓ Set up job
  ✓ Refuse probes outside rehearse
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up Python
  ✓ Ensure tmux for the TUI frame
  ✓ Download the sealed build
  ✓ Resolve the leg dist and manifest fields
  ✓ Verify digests before install
  ✓ Prepare the isolated leg environment
  ✓ Resolve the previous installable PyPI release
  ✓ Run the exercise leg
  ✓ Upload the leg evidence
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ exercise-legs (ubuntu-latest, sdist) in 54s (ID 130115802632)
  ✓ Set up job
  ✓ Refuse probes outside rehearse
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up Python
  - Ensure tmux for the TUI frame
  ✓ Download the sealed build
  ✓ Resolve the leg dist and manifest fields
  ✓ Verify digests before install
  ✓ Prepare the isolated leg environment
  - Resolve the previous installable PyPI release
  ✓ Run the exercise leg
  ✓ Upload the leg evidence
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ exercise-legs (ubuntu-latest, wheel) in 1m8s (ID 130115802657)
  ✓ Set up job
  ✓ Refuse probes outside rehearse
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up Python
  - Ensure tmux for the TUI frame
  ✓ Download the sealed build
  ✓ Resolve the leg dist and manifest fields
  ✓ Verify digests before install
  ✓ Prepare the isolated leg environment
  ✓ Resolve the previous installable PyPI release
  ✓ Run the exercise leg
  ✓ Upload the leg evidence
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ exercise-legs (macos-latest, sdist) in 1m18s (ID 130115802821)
  ✓ Set up job
  ✓ Refuse probes outside rehearse
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up Python
  ✓ Ensure tmux for the TUI frame
  ✓ Download the sealed build
  ✓ Resolve the leg dist and manifest fields
  ✓ Verify digests before install
  ✓ Prepare the isolated leg environment
  - Resolve the previous installable PyPI release
  ✓ Run the exercise leg
  ✓ Upload the leg evidence
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
- stash (ID 130115805318)
✓ qualify-ci / prepare in 26s (ID 130116069325)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Validate qualification inputs
  ✓ Download the sealed candidate manifest
  ✓ Bind published identity from the sealed manifest
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
- qualify-ci / release-core-floor-smoke (ID 130116071518)
- qualify-ci / docs-build (ID 130116072055)
✓ qualify-ci / build-core / build-core in 8m41s (ID 130116334196)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Resolve core mode
  - Resolve pinned Rust core revision
  - Check out Rust core
  ✓ Check out published Rust core tag
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up Rust
  ✓ Cache Rust build
  - Build abi3 Rust core wheel
  ✓ Download the sealed candidate manifest
  ✓ Fetch and verify the published core wheel
  ✓ Build macro LSP
  - Record wheel provenance
  ✓ Record published tag provenance
  ✓ Upload Rust core artifacts
  ✓ Post Cache Rust build
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Check out published Rust core tag
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ exercise in 27s (ID 130117005549)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Download the sealed build
  ✓ Download the leg evidence
  ✓ Merge the legs into one exercise observation
  - Stash the exercise observation on the draft release
  ✓ Upload the exercise observation artifact
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ qualify-ci / perf-floors in 9m50s (ID 130121174612)
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
✓ qualify-ci / tutorial-tests in 1m4s (ID 130121174619)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run tutorial tests
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
X qualify-ci / visual-test in 34m4s (ID 130121174667)
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
X qualify-ci / lint in 1m31s (ID 130121174682)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up preflight Python
  ✓ Download Rust core artifacts for bindings preflight
  ✓ Preflight core bindings
  ✓ Install dependencies
  ✓ Check pinned core bindings
  ✓ Bootstrap SDD sidecars
  ✓ Initialize SASE home
  ✓ Run actions/setup-go@v5
  ✓ Cache Go binaries
  - Install Go tools (keep-sorted)
  ✓ Cache Prettier dependencies
  ✓ Check Python formatting
  ✓ Check Markdown formatting
  X Check generated model docs
  - Check shipped model policy
  - Lint
  - SASE validation
  - Validate committed plans
  - Build and verify package
  ✓ Record installed core version
  ✓ Write qualification evidence
  ✓ Upload qualification evidence
  - Post Cache Prettier dependencies
  - Post Cache Go binaries
  - Post Run actions/setup-go@v5
  ✓ Post Install dependencies
  - Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* qualify-ci / test (3.14) (ID 130121174714)
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
* qualify-ci / test (3.13) (ID 130121174802)
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
* qualify-ci / test (3.12) (ID 130121174849)
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
✓ qualify-ci / ace-page-group-isolation in 1m37s (ID 130121174850)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  ✓ Run ACE shared-page isolation lane
  ✓ Post Install visual dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
identity: .github#7

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
identity: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
build: .github#4

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0sIHzagAAAAB30fM6H9ufTppmpzFOLFMkUEhMMzBFREdFMDEwOABFZGdl
build: .github#7

! Failed to restore: Cache service responded with 400
build: .github#24

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
build: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-prepare: .github#9

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-prepare: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
exercise-legs (macos-latest, wheel): .github#2

- Due to capacity constraints, jobs targeting macOS arm64 runners may experience longer queue times.
exercise-legs (macos-latest, wheel): .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
exercise-legs (ubuntu-latest, sdist): .github#2

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
exercise-legs (ubuntu-latest, sdist): .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
exercise-legs (ubuntu-latest, wheel): .github#2

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
exercise-legs (ubuntu-latest, wheel): .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
exercise-legs (macos-latest, sdist): .github#2

- Due to capacity constraints, jobs targeting macOS arm64 runners may experience longer queue times.
exercise-legs (macos-latest, sdist): .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / prepare: .github#10

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / prepare: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / build-core / build-core: .github#5

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>09YPzagAAAAAiPR5XKRSoQpRg352ExmJxQ0gxQUEyMDMwODE0MDYwAEVkZ2U=
qualify-ci / build-core / build-core: .github#7

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / tutorial-tests: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0OITzagAAAACMpVdYEU0wTYGlMGZQR9ksQ0gxQUEyMDMwODEzMDYwAEVkZ2U=
qualify-ci / tutorial-tests: .github#9

! Failed to restore: Cache service responded with 400
qualify-ci / tutorial-tests: .github#49

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / tutorial-tests: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache@v4, actions/checkout@v4, actions/download-artifact@v4, actions/setup-go@v5, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / lint: .github#2

X Process completed with exit code 1.
qualify-ci / lint: .github#16

! Failed to restore: Cache service responded with 400
qualify-ci / lint: .github#52

! Failed to restore: Cache service responded with 400
qualify-ci / lint: .github#24

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / lint: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / ace-page-group-isolation: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0WITzagAAAAAzCcEmW9wlRq5yhIB141iuQ0gxQUEyMDMwODEzMDI1AEVkZ2U=
qualify-ci / ace-page-group-isolation: .github#9

! Failed to restore: Cache service responded with 400
qualify-ci / ace-page-group-isolation: .github#49

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / ace-page-group-isolation: .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* release-please--branches--master Release sase-org/sase#322 · 42897628895
Triggered via workflow_dispatch about 55 minutes ago

JOBS
✓ identity in 57s (ID 130114862321)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Assert source and version identity
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ build in 38s (ID 130115420556)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up Python
  ✓ Build once and check the dist set
  ✓ Resolve the exact core pin
  ✓ Fetch the core file list and digests
  ✓ Read the core completeness set at the pin's tag
  ✓ Prove the core tag contains the source pin
  ✓ Seal the candidate manifest
  ✓ Upload the candidate build
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ qualify-prepare in 26s (ID 130115802507)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Download the sealed candidate build
  ✓ Bind the sealed candidate identity
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ exercise-legs (macos-latest, wheel) in 2m5s (ID 130115802596)
  ✓ Set up job
  ✓ Refuse probes outside rehearse
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up Python
  ✓ Ensure tmux for the TUI frame
  ✓ Download the sealed build
  ✓ Resolve the leg dist and manifest fields
  ✓ Verify digests before install
  ✓ Prepare the isolated leg environment
  ✓ Resolve the previous installable PyPI release
  ✓ Run the exercise leg
  ✓ Upload the leg evidence
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ exercise-legs (ubuntu-latest, sdist) in 54s (ID 130115802632)
  ✓ Set up job
  ✓ Refuse probes outside rehearse
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up Python
  - Ensure tmux for the TUI frame
  ✓ Download the sealed build
  ✓ Resolve the leg dist and manifest fields
  ✓ Verify digests before install
  ✓ Prepare the isolated leg environment
  - Resolve the previous installable PyPI release
  ✓ Run the exercise leg
  ✓ Upload the leg evidence
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ exercise-legs (ubuntu-latest, wheel) in 1m8s (ID 130115802657)
  ✓ Set up job
  ✓ Refuse probes outside rehearse
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up Python
  - Ensure tmux for the TUI frame
  ✓ Download the sealed build
  ✓ Resolve the leg dist and manifest fields
  ✓ Verify digests before install
  ✓ Prepare the isolated leg environment
  ✓ Resolve the previous installable PyPI release
  ✓ Run the exercise leg
  ✓ Upload the leg evidence
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ exercise-legs (macos-latest, sdist) in 1m18s (ID 130115802821)
  ✓ Set up job
  ✓ Refuse probes outside rehearse
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up Python
  ✓ Ensure tmux for the TUI frame
  ✓ Download the sealed build
  ✓ Resolve the leg dist and manifest fields
  ✓ Verify digests before install
  ✓ Prepare the isolated leg environment
  - Resolve the previous installable PyPI release
  ✓ Run the exercise leg
  ✓ Upload the leg evidence
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
- stash (ID 130115805318)
✓ qualify-ci / prepare in 26s (ID 130116069325)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Validate qualification inputs
  ✓ Download the sealed candidate manifest
  ✓ Bind published identity from the sealed manifest
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
- qualify-ci / release-core-floor-smoke (ID 130116071518)
- qualify-ci / docs-build (ID 130116072055)
✓ qualify-ci / build-core / build-core in 8m41s (ID 130116334196)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Resolve core mode
  - Resolve pinned Rust core revision
  - Check out Rust core
  ✓ Check out published Rust core tag
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up Rust
  ✓ Cache Rust build
  - Build abi3 Rust core wheel
  ✓ Download the sealed candidate manifest
  ✓ Fetch and verify the published core wheel
  ✓ Build macro LSP
  - Record wheel provenance
  ✓ Record published tag provenance
  ✓ Upload Rust core artifacts
  ✓ Post Cache Rust build
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Check out published Rust core tag
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ exercise in 27s (ID 130117005549)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Download the sealed build
  ✓ Download the leg evidence
  ✓ Merge the legs into one exercise observation
  - Stash the exercise observation on the draft release
  ✓ Upload the exercise observation artifact
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ qualify-ci / perf-floors in 9m50s (ID 130121174612)
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
✓ qualify-ci / tutorial-tests in 1m4s (ID 130121174619)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run tutorial tests
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
X qualify-ci / visual-test in 34m4s (ID 130121174667)
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
X qualify-ci / lint in 1m31s (ID 130121174682)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up preflight Python
  ✓ Download Rust core artifacts for bindings preflight
  ✓ Preflight core bindings
  ✓ Install dependencies
  ✓ Check pinned core bindings
  ✓ Bootstrap SDD sidecars
  ✓ Initialize SASE home
  ✓ Run actions/setup-go@v5
  ✓ Cache Go binaries
  - Install Go tools (keep-sorted)
  ✓ Cache Prettier dependencies
  ✓ Check Python formatting
  ✓ Check Markdown formatting
  X Check generated model docs
  - Check shipped model policy
  - Lint
  - SASE validation
  - Validate committed plans
  - Build and verify package
  ✓ Record installed core version
  ✓ Write qualification evidence
  ✓ Upload qualification evidence
  - Post Cache Prettier dependencies
  - Post Cache Go binaries
  - Post Run actions/setup-go@v5
  ✓ Post Install dependencies
  - Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* qualify-ci / test (3.14) (ID 130121174714)
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
* qualify-ci / test (3.13) (ID 130121174802)
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
* qualify-ci / test (3.12) (ID 130121174849)
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
✓ qualify-ci / ace-page-group-isolation in 1m37s (ID 130121174850)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  ✓ Run ACE shared-page isolation lane
  ✓ Post Install visual dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
identity: .github#7

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
identity: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
build: .github#4

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0sIHzagAAAAB30fM6H9ufTppmpzFOLFMkUEhMMzBFREdFMDEwOABFZGdl
build: .github#7

! Failed to restore: Cache service responded with 400
build: .github#24

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
build: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-prepare: .github#9

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-prepare: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
exercise-legs (macos-latest, wheel): .github#2

- Due to capacity constraints, jobs targeting macOS arm64 runners may experience longer queue times.
exercise-legs (macos-latest, wheel): .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
exercise-legs (ubuntu-latest, sdist): .github#2

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
exercise-legs (ubuntu-latest, sdist): .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
exercise-legs (ubuntu-latest, wheel): .github#2

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
exercise-legs (ubuntu-latest, wheel): .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
exercise-legs (macos-latest, sdist): .github#2

- Due to capacity constraints, jobs targeting macOS arm64 runners may experience longer queue times.
exercise-legs (macos-latest, sdist): .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / prepare: .github#10

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / prepare: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / build-core / build-core: .github#5

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>09YPzagAAAAAiPR5XKRSoQpRg352ExmJxQ0gxQUEyMDMwODE0MDYwAEVkZ2U=
qualify-ci / build-core / build-core: .github#7

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / tutorial-tests: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0OITzagAAAACMpVdYEU0wTYGlMGZQR9ksQ0gxQUEyMDMwODEzMDYwAEVkZ2U=
qualify-ci / tutorial-tests: .github#9

! Failed to restore: Cache service responded with 400
qualify-ci / tutorial-tests: .github#49

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / tutorial-tests: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache@v4, actions/checkout@v4, actions/download-artifact@v4, actions/setup-go@v5, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / lint: .github#2

X Process completed with exit code 1.
qualify-ci / lint: .github#16

! Failed to restore: Cache service responded with 400
qualify-ci / lint: .github#52

! Failed to restore: Cache service responded with 400
qualify-ci / lint: .github#24

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / lint: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / ace-page-group-isolation: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0WITzagAAAAAzCcEmW9wlRq5yhIB141iuQ0gxQUEyMDMwODEzMDI1AEVkZ2U=
qualify-ci / ace-page-group-isolation: .github#9

! Failed to restore: Cache service responded with 400
qualify-ci / ace-page-group-isolation: .github#49

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / ace-page-group-isolation: .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* release-please--branches--master Release sase-org/sase#322 · 42897628895
Triggered via workflow_dispatch about 57 minutes ago

JOBS
✓ identity in 57s (ID 130114862321)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Assert source and version identity
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ build in 38s (ID 130115420556)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up Python
  ✓ Build once and check the dist set
  ✓ Resolve the exact core pin
  ✓ Fetch the core file list and digests
  ✓ Read the core completeness set at the pin's tag
  ✓ Prove the core tag contains the source pin
  ✓ Seal the candidate manifest
  ✓ Upload the candidate build
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ qualify-prepare in 26s (ID 130115802507)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Download the sealed candidate build
  ✓ Bind the sealed candidate identity
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ exercise-legs (macos-latest, wheel) in 2m5s (ID 130115802596)
  ✓ Set up job
  ✓ Refuse probes outside rehearse
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up Python
  ✓ Ensure tmux for the TUI frame
  ✓ Download the sealed build
  ✓ Resolve the leg dist and manifest fields
  ✓ Verify digests before install
  ✓ Prepare the isolated leg environment
  ✓ Resolve the previous installable PyPI release
  ✓ Run the exercise leg
  ✓ Upload the leg evidence
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ exercise-legs (ubuntu-latest, sdist) in 54s (ID 130115802632)
  ✓ Set up job
  ✓ Refuse probes outside rehearse
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up Python
  - Ensure tmux for the TUI frame
  ✓ Download the sealed build
  ✓ Resolve the leg dist and manifest fields
  ✓ Verify digests before install
  ✓ Prepare the isolated leg environment
  - Resolve the previous installable PyPI release
  ✓ Run the exercise leg
  ✓ Upload the leg evidence
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ exercise-legs (ubuntu-latest, wheel) in 1m8s (ID 130115802657)
  ✓ Set up job
  ✓ Refuse probes outside rehearse
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up Python
  - Ensure tmux for the TUI frame
  ✓ Download the sealed build
  ✓ Resolve the leg dist and manifest fields
  ✓ Verify digests before install
  ✓ Prepare the isolated leg environment
  ✓ Resolve the previous installable PyPI release
  ✓ Run the exercise leg
  ✓ Upload the leg evidence
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ exercise-legs (macos-latest, sdist) in 1m18s (ID 130115802821)
  ✓ Set up job
  ✓ Refuse probes outside rehearse
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up Python
  ✓ Ensure tmux for the TUI frame
  ✓ Download the sealed build
  ✓ Resolve the leg dist and manifest fields
  ✓ Verify digests before install
  ✓ Prepare the isolated leg environment
  - Resolve the previous installable PyPI release
  ✓ Run the exercise leg
  ✓ Upload the leg evidence
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
- stash (ID 130115805318)
✓ qualify-ci / prepare in 26s (ID 130116069325)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Validate qualification inputs
  ✓ Download the sealed candidate manifest
  ✓ Bind published identity from the sealed manifest
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
- qualify-ci / release-core-floor-smoke (ID 130116071518)
- qualify-ci / docs-build (ID 130116072055)
✓ qualify-ci / build-core / build-core in 8m41s (ID 130116334196)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Resolve core mode
  - Resolve pinned Rust core revision
  - Check out Rust core
  ✓ Check out published Rust core tag
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up Rust
  ✓ Cache Rust build
  - Build abi3 Rust core wheel
  ✓ Download the sealed candidate manifest
  ✓ Fetch and verify the published core wheel
  ✓ Build macro LSP
  - Record wheel provenance
  ✓ Record published tag provenance
  ✓ Upload Rust core artifacts
  ✓ Post Cache Rust build
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Check out published Rust core tag
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ exercise in 27s (ID 130117005549)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Download the sealed build
  ✓ Download the leg evidence
  ✓ Merge the legs into one exercise observation
  - Stash the exercise observation on the draft release
  ✓ Upload the exercise observation artifact
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ qualify-ci / perf-floors in 9m50s (ID 130121174612)
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
✓ qualify-ci / tutorial-tests in 1m4s (ID 130121174619)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run tutorial tests
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
X qualify-ci / visual-test in 34m4s (ID 130121174667)
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
X qualify-ci / lint in 1m31s (ID 130121174682)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up preflight Python
  ✓ Download Rust core artifacts for bindings preflight
  ✓ Preflight core bindings
  ✓ Install dependencies
  ✓ Check pinned core bindings
  ✓ Bootstrap SDD sidecars
  ✓ Initialize SASE home
  ✓ Run actions/setup-go@v5
  ✓ Cache Go binaries
  - Install Go tools (keep-sorted)
  ✓ Cache Prettier dependencies
  ✓ Check Python formatting
  ✓ Check Markdown formatting
  X Check generated model docs
  - Check shipped model policy
  - Lint
  - SASE validation
  - Validate committed plans
  - Build and verify package
  ✓ Record installed core version
  ✓ Write qualification evidence
  ✓ Upload qualification evidence
  - Post Cache Prettier dependencies
  - Post Cache Go binaries
  - Post Run actions/setup-go@v5
  ✓ Post Install dependencies
  - Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* qualify-ci / test (3.14) (ID 130121174714)
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
* qualify-ci / test (3.13) (ID 130121174802)
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
* qualify-ci / test (3.12) (ID 130121174849)
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
✓ qualify-ci / ace-page-group-isolation in 1m37s (ID 130121174850)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  ✓ Run ACE shared-page isolation lane
  ✓ Post Install visual dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
identity: .github#7

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
identity: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
build: .github#4

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0sIHzagAAAAB30fM6H9ufTppmpzFOLFMkUEhMMzBFREdFMDEwOABFZGdl
build: .github#7

! Failed to restore: Cache service responded with 400
build: .github#24

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
build: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-prepare: .github#9

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-prepare: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
exercise-legs (macos-latest, wheel): .github#2

- Due to capacity constraints, jobs targeting macOS arm64 runners may experience longer queue times.
exercise-legs (macos-latest, wheel): .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
exercise-legs (ubuntu-latest, sdist): .github#2

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
exercise-legs (ubuntu-latest, sdist): .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
exercise-legs (ubuntu-latest, wheel): .github#2

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
exercise-legs (ubuntu-latest, wheel): .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
exercise-legs (macos-latest, sdist): .github#2

- Due to capacity constraints, jobs targeting macOS arm64 runners may experience longer queue times.
exercise-legs (macos-latest, sdist): .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / prepare: .github#10

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / prepare: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / build-core / build-core: .github#5

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>09YPzagAAAAAiPR5XKRSoQpRg352ExmJxQ0gxQUEyMDMwODE0MDYwAEVkZ2U=
qualify-ci / build-core / build-core: .github#7

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / tutorial-tests: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0OITzagAAAACMpVdYEU0wTYGlMGZQR9ksQ0gxQUEyMDMwODEzMDYwAEVkZ2U=
qualify-ci / tutorial-tests: .github#9

! Failed to restore: Cache service responded with 400
qualify-ci / tutorial-tests: .github#49

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / tutorial-tests: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache@v4, actions/checkout@v4, actions/download-artifact@v4, actions/setup-go@v5, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / lint: .github#2

X Process completed with exit code 1.
qualify-ci / lint: .github#16

! Failed to restore: Cache service responded with 400
qualify-ci / lint: .github#52

! Failed to restore: Cache service responded with 400
qualify-ci / lint: .github#24

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / lint: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / ace-page-group-isolation: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0WITzagAAAAAzCcEmW9wlRq5yhIB141iuQ0gxQUEyMDMwODEzMDI1AEVkZ2U=
qualify-ci / ace-page-group-isolation: .github#9

! Failed to restore: Cache service responded with 400
qualify-ci / ace-page-group-isolation: .github#49

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / ace-page-group-isolation: .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* release-please--branches--master Release sase-org/sase#322 · 42897628895
Triggered via workflow_dispatch about 59 minutes ago

JOBS
✓ identity in 57s (ID 130114862321)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Assert source and version identity
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ build in 38s (ID 130115420556)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up Python
  ✓ Build once and check the dist set
  ✓ Resolve the exact core pin
  ✓ Fetch the core file list and digests
  ✓ Read the core completeness set at the pin's tag
  ✓ Prove the core tag contains the source pin
  ✓ Seal the candidate manifest
  ✓ Upload the candidate build
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ qualify-prepare in 26s (ID 130115802507)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Download the sealed candidate build
  ✓ Bind the sealed candidate identity
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ exercise-legs (macos-latest, wheel) in 2m5s (ID 130115802596)
  ✓ Set up job
  ✓ Refuse probes outside rehearse
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up Python
  ✓ Ensure tmux for the TUI frame
  ✓ Download the sealed build
  ✓ Resolve the leg dist and manifest fields
  ✓ Verify digests before install
  ✓ Prepare the isolated leg environment
  ✓ Resolve the previous installable PyPI release
  ✓ Run the exercise leg
  ✓ Upload the leg evidence
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ exercise-legs (ubuntu-latest, sdist) in 54s (ID 130115802632)
  ✓ Set up job
  ✓ Refuse probes outside rehearse
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up Python
  - Ensure tmux for the TUI frame
  ✓ Download the sealed build
  ✓ Resolve the leg dist and manifest fields
  ✓ Verify digests before install
  ✓ Prepare the isolated leg environment
  - Resolve the previous installable PyPI release
  ✓ Run the exercise leg
  ✓ Upload the leg evidence
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ exercise-legs (ubuntu-latest, wheel) in 1m8s (ID 130115802657)
  ✓ Set up job
  ✓ Refuse probes outside rehearse
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up Python
  - Ensure tmux for the TUI frame
  ✓ Download the sealed build
  ✓ Resolve the leg dist and manifest fields
  ✓ Verify digests before install
  ✓ Prepare the isolated leg environment
  ✓ Resolve the previous installable PyPI release
  ✓ Run the exercise leg
  ✓ Upload the leg evidence
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ exercise-legs (macos-latest, sdist) in 1m18s (ID 130115802821)
  ✓ Set up job
  ✓ Refuse probes outside rehearse
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up Python
  ✓ Ensure tmux for the TUI frame
  ✓ Download the sealed build
  ✓ Resolve the leg dist and manifest fields
  ✓ Verify digests before install
  ✓ Prepare the isolated leg environment
  - Resolve the previous installable PyPI release
  ✓ Run the exercise leg
  ✓ Upload the leg evidence
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
- stash (ID 130115805318)
✓ qualify-ci / prepare in 26s (ID 130116069325)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Validate qualification inputs
  ✓ Download the sealed candidate manifest
  ✓ Bind published identity from the sealed manifest
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
- qualify-ci / release-core-floor-smoke (ID 130116071518)
- qualify-ci / docs-build (ID 130116072055)
✓ qualify-ci / build-core / build-core in 8m41s (ID 130116334196)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Resolve core mode
  - Resolve pinned Rust core revision
  - Check out Rust core
  ✓ Check out published Rust core tag
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up Rust
  ✓ Cache Rust build
  - Build abi3 Rust core wheel
  ✓ Download the sealed candidate manifest
  ✓ Fetch and verify the published core wheel
  ✓ Build macro LSP
  - Record wheel provenance
  ✓ Record published tag provenance
  ✓ Upload Rust core artifacts
  ✓ Post Cache Rust build
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Check out published Rust core tag
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ exercise in 27s (ID 130117005549)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Download the sealed build
  ✓ Download the leg evidence
  ✓ Merge the legs into one exercise observation
  - Stash the exercise observation on the draft release
  ✓ Upload the exercise observation artifact
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ qualify-ci / perf-floors in 9m50s (ID 130121174612)
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
✓ qualify-ci / tutorial-tests in 1m4s (ID 130121174619)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run tutorial tests
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
X qualify-ci / visual-test in 34m4s (ID 130121174667)
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
X qualify-ci / lint in 1m31s (ID 130121174682)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up preflight Python
  ✓ Download Rust core artifacts for bindings preflight
  ✓ Preflight core bindings
  ✓ Install dependencies
  ✓ Check pinned core bindings
  ✓ Bootstrap SDD sidecars
  ✓ Initialize SASE home
  ✓ Run actions/setup-go@v5
  ✓ Cache Go binaries
  - Install Go tools (keep-sorted)
  ✓ Cache Prettier dependencies
  ✓ Check Python formatting
  ✓ Check Markdown formatting
  X Check generated model docs
  - Check shipped model policy
  - Lint
  - SASE validation
  - Validate committed plans
  - Build and verify package
  ✓ Record installed core version
  ✓ Write qualification evidence
  ✓ Upload qualification evidence
  - Post Cache Prettier dependencies
  - Post Cache Go binaries
  - Post Run actions/setup-go@v5
  ✓ Post Install dependencies
  - Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* qualify-ci / test (3.14) (ID 130121174714)
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
* qualify-ci / test (3.13) (ID 130121174802)
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
* qualify-ci / test (3.12) (ID 130121174849)
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
✓ qualify-ci / ace-page-group-isolation in 1m37s (ID 130121174850)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  ✓ Run ACE shared-page isolation lane
  ✓ Post Install visual dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
identity: .github#7

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
identity: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
build: .github#4

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0sIHzagAAAAB30fM6H9ufTppmpzFOLFMkUEhMMzBFREdFMDEwOABFZGdl
build: .github#7

! Failed to restore: Cache service responded with 400
build: .github#24

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
build: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-prepare: .github#9

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-prepare: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
exercise-legs (macos-latest, wheel): .github#2

- Due to capacity constraints, jobs targeting macOS arm64 runners may experience longer queue times.
exercise-legs (macos-latest, wheel): .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
exercise-legs (ubuntu-latest, sdist): .github#2

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
exercise-legs (ubuntu-latest, sdist): .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
exercise-legs (ubuntu-latest, wheel): .github#2

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
exercise-legs (ubuntu-latest, wheel): .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
exercise-legs (macos-latest, sdist): .github#2

- Due to capacity constraints, jobs targeting macOS arm64 runners may experience longer queue times.
exercise-legs (macos-latest, sdist): .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / prepare: .github#10

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / prepare: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / build-core / build-core: .github#5

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>09YPzagAAAAAiPR5XKRSoQpRg352ExmJxQ0gxQUEyMDMwODE0MDYwAEVkZ2U=
qualify-ci / build-core / build-core: .github#7

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / tutorial-tests: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0OITzagAAAACMpVdYEU0wTYGlMGZQR9ksQ0gxQUEyMDMwODEzMDYwAEVkZ2U=
qualify-ci / tutorial-tests: .github#9

! Failed to restore: Cache service responded with 400
qualify-ci / tutorial-tests: .github#49

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / tutorial-tests: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache@v4, actions/checkout@v4, actions/download-artifact@v4, actions/setup-go@v5, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / lint: .github#2

X Process completed with exit code 1.
qualify-ci / lint: .github#16

! Failed to restore: Cache service responded with 400
qualify-ci / lint: .github#52

! Failed to restore: Cache service responded with 400
qualify-ci / lint: .github#24

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / lint: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / ace-page-group-isolation: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0WITzagAAAAAzCcEmW9wlRq5yhIB141iuQ0gxQUEyMDMwODEzMDI1AEVkZ2U=
qualify-ci / ace-page-group-isolation: .github#9

! Failed to restore: Cache service responded with 400
qualify-ci / ace-page-group-isolation: .github#49

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / ace-page-group-isolation: .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* release-please--branches--master Release sase-org/sase#322 · 42897628895
Triggered via workflow_dispatch about 1 hour ago

JOBS
✓ identity in 57s (ID 130114862321)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Assert source and version identity
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ build in 38s (ID 130115420556)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up Python
  ✓ Build once and check the dist set
  ✓ Resolve the exact core pin
  ✓ Fetch the core file list and digests
  ✓ Read the core completeness set at the pin's tag
  ✓ Prove the core tag contains the source pin
  ✓ Seal the candidate manifest
  ✓ Upload the candidate build
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ qualify-prepare in 26s (ID 130115802507)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Download the sealed candidate build
  ✓ Bind the sealed candidate identity
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ exercise-legs (macos-latest, wheel) in 2m5s (ID 130115802596)
  ✓ Set up job
  ✓ Refuse probes outside rehearse
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up Python
  ✓ Ensure tmux for the TUI frame
  ✓ Download the sealed build
  ✓ Resolve the leg dist and manifest fields
  ✓ Verify digests before install
  ✓ Prepare the isolated leg environment
  ✓ Resolve the previous installable PyPI release
  ✓ Run the exercise leg
  ✓ Upload the leg evidence
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ exercise-legs (ubuntu-latest, sdist) in 54s (ID 130115802632)
  ✓ Set up job
  ✓ Refuse probes outside rehearse
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up Python
  - Ensure tmux for the TUI frame
  ✓ Download the sealed build
  ✓ Resolve the leg dist and manifest fields
  ✓ Verify digests before install
  ✓ Prepare the isolated leg environment
  - Resolve the previous installable PyPI release
  ✓ Run the exercise leg
  ✓ Upload the leg evidence
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ exercise-legs (ubuntu-latest, wheel) in 1m8s (ID 130115802657)
  ✓ Set up job
  ✓ Refuse probes outside rehearse
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up Python
  - Ensure tmux for the TUI frame
  ✓ Download the sealed build
  ✓ Resolve the leg dist and manifest fields
  ✓ Verify digests before install
  ✓ Prepare the isolated leg environment
  ✓ Resolve the previous installable PyPI release
  ✓ Run the exercise leg
  ✓ Upload the leg evidence
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ exercise-legs (macos-latest, sdist) in 1m18s (ID 130115802821)
  ✓ Set up job
  ✓ Refuse probes outside rehearse
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up Python
  ✓ Ensure tmux for the TUI frame
  ✓ Download the sealed build
  ✓ Resolve the leg dist and manifest fields
  ✓ Verify digests before install
  ✓ Prepare the isolated leg environment
  - Resolve the previous installable PyPI release
  ✓ Run the exercise leg
  ✓ Upload the leg evidence
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
- stash (ID 130115805318)
✓ qualify-ci / prepare in 26s (ID 130116069325)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Validate qualification inputs
  ✓ Download the sealed candidate manifest
  ✓ Bind published identity from the sealed manifest
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
- qualify-ci / release-core-floor-smoke (ID 130116071518)
- qualify-ci / docs-build (ID 130116072055)
✓ qualify-ci / build-core / build-core in 8m41s (ID 130116334196)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Resolve core mode
  - Resolve pinned Rust core revision
  - Check out Rust core
  ✓ Check out published Rust core tag
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up Rust
  ✓ Cache Rust build
  - Build abi3 Rust core wheel
  ✓ Download the sealed candidate manifest
  ✓ Fetch and verify the published core wheel
  ✓ Build macro LSP
  - Record wheel provenance
  ✓ Record published tag provenance
  ✓ Upload Rust core artifacts
  ✓ Post Cache Rust build
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Check out published Rust core tag
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ exercise in 27s (ID 130117005549)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Download the sealed build
  ✓ Download the leg evidence
  ✓ Merge the legs into one exercise observation
  - Stash the exercise observation on the draft release
  ✓ Upload the exercise observation artifact
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ qualify-ci / perf-floors in 9m50s (ID 130121174612)
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
✓ qualify-ci / tutorial-tests in 1m4s (ID 130121174619)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run tutorial tests
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
X qualify-ci / visual-test in 34m4s (ID 130121174667)
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
X qualify-ci / lint in 1m31s (ID 130121174682)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up preflight Python
  ✓ Download Rust core artifacts for bindings preflight
  ✓ Preflight core bindings
  ✓ Install dependencies
  ✓ Check pinned core bindings
  ✓ Bootstrap SDD sidecars
  ✓ Initialize SASE home
  ✓ Run actions/setup-go@v5
  ✓ Cache Go binaries
  - Install Go tools (keep-sorted)
  ✓ Cache Prettier dependencies
  ✓ Check Python formatting
  ✓ Check Markdown formatting
  X Check generated model docs
  - Check shipped model policy
  - Lint
  - SASE validation
  - Validate committed plans
  - Build and verify package
  ✓ Record installed core version
  ✓ Write qualification evidence
  ✓ Upload qualification evidence
  - Post Cache Prettier dependencies
  - Post Cache Go binaries
  - Post Run actions/setup-go@v5
  ✓ Post Install dependencies
  - Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* qualify-ci / test (3.14) (ID 130121174714)
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
* qualify-ci / test (3.13) (ID 130121174802)
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
* qualify-ci / test (3.12) (ID 130121174849)
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
✓ qualify-ci / ace-page-group-isolation in 1m37s (ID 130121174850)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  ✓ Run ACE shared-page isolation lane
  ✓ Post Install visual dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
identity: .github#7

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
identity: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
build: .github#4

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0sIHzagAAAAB30fM6H9ufTppmpzFOLFMkUEhMMzBFREdFMDEwOABFZGdl
build: .github#7

! Failed to restore: Cache service responded with 400
build: .github#24

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
build: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-prepare: .github#9

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-prepare: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
exercise-legs (macos-latest, wheel): .github#2

- Due to capacity constraints, jobs targeting macOS arm64 runners may experience longer queue times.
exercise-legs (macos-latest, wheel): .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
exercise-legs (ubuntu-latest, sdist): .github#2

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
exercise-legs (ubuntu-latest, sdist): .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
exercise-legs (ubuntu-latest, wheel): .github#2

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
exercise-legs (ubuntu-latest, wheel): .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
exercise-legs (macos-latest, sdist): .github#2

- Due to capacity constraints, jobs targeting macOS arm64 runners may experience longer queue times.
exercise-legs (macos-latest, sdist): .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / prepare: .github#10

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / prepare: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / build-core / build-core: .github#5

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>09YPzagAAAAAiPR5XKRSoQpRg352ExmJxQ0gxQUEyMDMwODE0MDYwAEVkZ2U=
qualify-ci / build-core / build-core: .github#7

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / tutorial-tests: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0OITzagAAAACMpVdYEU0wTYGlMGZQR9ksQ0gxQUEyMDMwODEzMDYwAEVkZ2U=
qualify-ci / tutorial-tests: .github#9

! Failed to restore: Cache service responded with 400
qualify-ci / tutorial-tests: .github#49

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / tutorial-tests: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache@v4, actions/checkout@v4, actions/download-artifact@v4, actions/setup-go@v5, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / lint: .github#2

X Process completed with exit code 1.
qualify-ci / lint: .github#16

! Failed to restore: Cache service responded with 400
qualify-ci / lint: .github#52

! Failed to restore: Cache service responded with 400
qualify-ci / lint: .github#24

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / lint: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / ace-page-group-isolation: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0WITzagAAAAAzCcEmW9wlRq5yhIB141iuQ0gxQUEyMDMwODEzMDI1AEVkZ2U=
qualify-ci / ace-page-group-isolation: .github#9

! Failed to restore: Cache service responded with 400
qualify-ci / ace-page-group-isolation: .github#49

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / ace-page-group-isolation: .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* release-please--branches--master Release sase-org/sase#322 · 42897628895
Triggered via workflow_dispatch about 1 hour ago

JOBS
✓ identity in 57s (ID 130114862321)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Assert source and version identity
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ build in 38s (ID 130115420556)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up Python
  ✓ Build once and check the dist set
  ✓ Resolve the exact core pin
  ✓ Fetch the core file list and digests
  ✓ Read the core completeness set at the pin's tag
  ✓ Prove the core tag contains the source pin
  ✓ Seal the candidate manifest
  ✓ Upload the candidate build
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ qualify-prepare in 26s (ID 130115802507)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Download the sealed candidate build
  ✓ Bind the sealed candidate identity
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ exercise-legs (macos-latest, wheel) in 2m5s (ID 130115802596)
  ✓ Set up job
  ✓ Refuse probes outside rehearse
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up Python
  ✓ Ensure tmux for the TUI frame
  ✓ Download the sealed build
  ✓ Resolve the leg dist and manifest fields
  ✓ Verify digests before install
  ✓ Prepare the isolated leg environment
  ✓ Resolve the previous installable PyPI release
  ✓ Run the exercise leg
  ✓ Upload the leg evidence
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ exercise-legs (ubuntu-latest, sdist) in 54s (ID 130115802632)
  ✓ Set up job
  ✓ Refuse probes outside rehearse
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up Python
  - Ensure tmux for the TUI frame
  ✓ Download the sealed build
  ✓ Resolve the leg dist and manifest fields
  ✓ Verify digests before install
  ✓ Prepare the isolated leg environment
  - Resolve the previous installable PyPI release
  ✓ Run the exercise leg
  ✓ Upload the leg evidence
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ exercise-legs (ubuntu-latest, wheel) in 1m8s (ID 130115802657)
  ✓ Set up job
  ✓ Refuse probes outside rehearse
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up Python
  - Ensure tmux for the TUI frame
  ✓ Download the sealed build
  ✓ Resolve the leg dist and manifest fields
  ✓ Verify digests before install
  ✓ Prepare the isolated leg environment
  ✓ Resolve the previous installable PyPI release
  ✓ Run the exercise leg
  ✓ Upload the leg evidence
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ exercise-legs (macos-latest, sdist) in 1m18s (ID 130115802821)
  ✓ Set up job
  ✓ Refuse probes outside rehearse
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up Python
  ✓ Ensure tmux for the TUI frame
  ✓ Download the sealed build
  ✓ Resolve the leg dist and manifest fields
  ✓ Verify digests before install
  ✓ Prepare the isolated leg environment
  - Resolve the previous installable PyPI release
  ✓ Run the exercise leg
  ✓ Upload the leg evidence
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
- stash (ID 130115805318)
✓ qualify-ci / prepare in 26s (ID 130116069325)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Validate qualification inputs
  ✓ Download the sealed candidate manifest
  ✓ Bind published identity from the sealed manifest
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
- qualify-ci / release-core-floor-smoke (ID 130116071518)
- qualify-ci / docs-build (ID 130116072055)
✓ qualify-ci / build-core / build-core in 8m41s (ID 130116334196)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Resolve core mode
  - Resolve pinned Rust core revision
  - Check out Rust core
  ✓ Check out published Rust core tag
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up Rust
  ✓ Cache Rust build
  - Build abi3 Rust core wheel
  ✓ Download the sealed candidate manifest
  ✓ Fetch and verify the published core wheel
  ✓ Build macro LSP
  - Record wheel provenance
  ✓ Record published tag provenance
  ✓ Upload Rust core artifacts
  ✓ Post Cache Rust build
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Check out published Rust core tag
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ exercise in 27s (ID 130117005549)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Download the sealed build
  ✓ Download the leg evidence
  ✓ Merge the legs into one exercise observation
  - Stash the exercise observation on the draft release
  ✓ Upload the exercise observation artifact
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ qualify-ci / perf-floors in 9m50s (ID 130121174612)
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
✓ qualify-ci / tutorial-tests in 1m4s (ID 130121174619)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run tutorial tests
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
X qualify-ci / visual-test in 34m4s (ID 130121174667)
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
X qualify-ci / lint in 1m31s (ID 130121174682)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up preflight Python
  ✓ Download Rust core artifacts for bindings preflight
  ✓ Preflight core bindings
  ✓ Install dependencies
  ✓ Check pinned core bindings
  ✓ Bootstrap SDD sidecars
  ✓ Initialize SASE home
  ✓ Run actions/setup-go@v5
  ✓ Cache Go binaries
  - Install Go tools (keep-sorted)
  ✓ Cache Prettier dependencies
  ✓ Check Python formatting
  ✓ Check Markdown formatting
  X Check generated model docs
  - Check shipped model policy
  - Lint
  - SASE validation
  - Validate committed plans
  - Build and verify package
  ✓ Record installed core version
  ✓ Write qualification evidence
  ✓ Upload qualification evidence
  - Post Cache Prettier dependencies
  - Post Cache Go binaries
  - Post Run actions/setup-go@v5
  ✓ Post Install dependencies
  - Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* qualify-ci / test (3.14) (ID 130121174714)
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
* qualify-ci / test (3.13) (ID 130121174802)
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
* qualify-ci / test (3.12) (ID 130121174849)
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
✓ qualify-ci / ace-page-group-isolation in 1m37s (ID 130121174850)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  ✓ Run ACE shared-page isolation lane
  ✓ Post Install visual dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
identity: .github#7

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
identity: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
build: .github#4

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0sIHzagAAAAB30fM6H9ufTppmpzFOLFMkUEhMMzBFREdFMDEwOABFZGdl
build: .github#7

! Failed to restore: Cache service responded with 400
build: .github#24

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
build: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-prepare: .github#9

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-prepare: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
exercise-legs (macos-latest, wheel): .github#2

- Due to capacity constraints, jobs targeting macOS arm64 runners may experience longer queue times.
exercise-legs (macos-latest, wheel): .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
exercise-legs (ubuntu-latest, sdist): .github#2

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
exercise-legs (ubuntu-latest, sdist): .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
exercise-legs (ubuntu-latest, wheel): .github#2

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
exercise-legs (ubuntu-latest, wheel): .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
exercise-legs (macos-latest, sdist): .github#2

- Due to capacity constraints, jobs targeting macOS arm64 runners may experience longer queue times.
exercise-legs (macos-latest, sdist): .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / prepare: .github#10

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / prepare: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / build-core / build-core: .github#5

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>09YPzagAAAAAiPR5XKRSoQpRg352ExmJxQ0gxQUEyMDMwODE0MDYwAEVkZ2U=
qualify-ci / build-core / build-core: .github#7

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / tutorial-tests: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0OITzagAAAACMpVdYEU0wTYGlMGZQR9ksQ0gxQUEyMDMwODEzMDYwAEVkZ2U=
qualify-ci / tutorial-tests: .github#9

! Failed to restore: Cache service responded with 400
qualify-ci / tutorial-tests: .github#49

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / tutorial-tests: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache@v4, actions/checkout@v4, actions/download-artifact@v4, actions/setup-go@v5, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / lint: .github#2

X Process completed with exit code 1.
qualify-ci / lint: .github#16

! Failed to restore: Cache service responded with 400
qualify-ci / lint: .github#52

! Failed to restore: Cache service responded with 400
qualify-ci / lint: .github#24

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / lint: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / ace-page-group-isolation: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0WITzagAAAAAzCcEmW9wlRq5yhIB141iuQ0gxQUEyMDMwODEzMDI1AEVkZ2U=
qualify-ci / ace-page-group-isolation: .github#9

! Failed to restore: Cache service responded with 400
qualify-ci / ace-page-group-isolation: .github#49

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / ace-page-group-isolation: .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* release-please--branches--master Release sase-org/sase#322 · 42897628895
Triggered via workflow_dispatch about 1 hour ago

JOBS
✓ identity in 57s (ID 130114862321)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Assert source and version identity
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ build in 38s (ID 130115420556)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up Python
  ✓ Build once and check the dist set
  ✓ Resolve the exact core pin
  ✓ Fetch the core file list and digests
  ✓ Read the core completeness set at the pin's tag
  ✓ Prove the core tag contains the source pin
  ✓ Seal the candidate manifest
  ✓ Upload the candidate build
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ qualify-prepare in 26s (ID 130115802507)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Download the sealed candidate build
  ✓ Bind the sealed candidate identity
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ exercise-legs (macos-latest, wheel) in 2m5s (ID 130115802596)
  ✓ Set up job
  ✓ Refuse probes outside rehearse
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up Python
  ✓ Ensure tmux for the TUI frame
  ✓ Download the sealed build
  ✓ Resolve the leg dist and manifest fields
  ✓ Verify digests before install
  ✓ Prepare the isolated leg environment
  ✓ Resolve the previous installable PyPI release
  ✓ Run the exercise leg
  ✓ Upload the leg evidence
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ exercise-legs (ubuntu-latest, sdist) in 54s (ID 130115802632)
  ✓ Set up job
  ✓ Refuse probes outside rehearse
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up Python
  - Ensure tmux for the TUI frame
  ✓ Download the sealed build
  ✓ Resolve the leg dist and manifest fields
  ✓ Verify digests before install
  ✓ Prepare the isolated leg environment
  - Resolve the previous installable PyPI release
  ✓ Run the exercise leg
  ✓ Upload the leg evidence
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ exercise-legs (ubuntu-latest, wheel) in 1m8s (ID 130115802657)
  ✓ Set up job
  ✓ Refuse probes outside rehearse
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up Python
  - Ensure tmux for the TUI frame
  ✓ Download the sealed build
  ✓ Resolve the leg dist and manifest fields
  ✓ Verify digests before install
  ✓ Prepare the isolated leg environment
  ✓ Resolve the previous installable PyPI release
  ✓ Run the exercise leg
  ✓ Upload the leg evidence
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ exercise-legs (macos-latest, sdist) in 1m18s (ID 130115802821)
  ✓ Set up job
  ✓ Refuse probes outside rehearse
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up Python
  ✓ Ensure tmux for the TUI frame
  ✓ Download the sealed build
  ✓ Resolve the leg dist and manifest fields
  ✓ Verify digests before install
  ✓ Prepare the isolated leg environment
  - Resolve the previous installable PyPI release
  ✓ Run the exercise leg
  ✓ Upload the leg evidence
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
- stash (ID 130115805318)
✓ qualify-ci / prepare in 26s (ID 130116069325)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Validate qualification inputs
  ✓ Download the sealed candidate manifest
  ✓ Bind published identity from the sealed manifest
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
- qualify-ci / release-core-floor-smoke (ID 130116071518)
- qualify-ci / docs-build (ID 130116072055)
✓ qualify-ci / build-core / build-core in 8m41s (ID 130116334196)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Resolve core mode
  - Resolve pinned Rust core revision
  - Check out Rust core
  ✓ Check out published Rust core tag
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up Rust
  ✓ Cache Rust build
  - Build abi3 Rust core wheel
  ✓ Download the sealed candidate manifest
  ✓ Fetch and verify the published core wheel
  ✓ Build macro LSP
  - Record wheel provenance
  ✓ Record published tag provenance
  ✓ Upload Rust core artifacts
  ✓ Post Cache Rust build
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Check out published Rust core tag
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ exercise in 27s (ID 130117005549)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Download the sealed build
  ✓ Download the leg evidence
  ✓ Merge the legs into one exercise observation
  - Stash the exercise observation on the draft release
  ✓ Upload the exercise observation artifact
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ qualify-ci / perf-floors in 9m50s (ID 130121174612)
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
✓ qualify-ci / tutorial-tests in 1m4s (ID 130121174619)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run tutorial tests
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
X qualify-ci / visual-test in 34m4s (ID 130121174667)
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
X qualify-ci / lint in 1m31s (ID 130121174682)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up preflight Python
  ✓ Download Rust core artifacts for bindings preflight
  ✓ Preflight core bindings
  ✓ Install dependencies
  ✓ Check pinned core bindings
  ✓ Bootstrap SDD sidecars
  ✓ Initialize SASE home
  ✓ Run actions/setup-go@v5
  ✓ Cache Go binaries
  - Install Go tools (keep-sorted)
  ✓ Cache Prettier dependencies
  ✓ Check Python formatting
  ✓ Check Markdown formatting
  X Check generated model docs
  - Check shipped model policy
  - Lint
  - SASE validation
  - Validate committed plans
  - Build and verify package
  ✓ Record installed core version
  ✓ Write qualification evidence
  ✓ Upload qualification evidence
  - Post Cache Prettier dependencies
  - Post Cache Go binaries
  - Post Run actions/setup-go@v5
  ✓ Post Install dependencies
  - Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* qualify-ci / test (3.14) (ID 130121174714)
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
* qualify-ci / test (3.13) (ID 130121174802)
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
* qualify-ci / test (3.12) (ID 130121174849)
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
✓ qualify-ci / ace-page-group-isolation in 1m37s (ID 130121174850)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  ✓ Run ACE shared-page isolation lane
  ✓ Post Install visual dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
identity: .github#7

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
identity: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
build: .github#4

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0sIHzagAAAAB30fM6H9ufTppmpzFOLFMkUEhMMzBFREdFMDEwOABFZGdl
build: .github#7

! Failed to restore: Cache service responded with 400
build: .github#24

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
build: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-prepare: .github#9

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-prepare: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
exercise-legs (macos-latest, wheel): .github#2

- Due to capacity constraints, jobs targeting macOS arm64 runners may experience longer queue times.
exercise-legs (macos-latest, wheel): .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
exercise-legs (ubuntu-latest, sdist): .github#2

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
exercise-legs (ubuntu-latest, sdist): .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
exercise-legs (ubuntu-latest, wheel): .github#2

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
exercise-legs (ubuntu-latest, wheel): .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
exercise-legs (macos-latest, sdist): .github#2

- Due to capacity constraints, jobs targeting macOS arm64 runners may experience longer queue times.
exercise-legs (macos-latest, sdist): .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / prepare: .github#10

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / prepare: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / build-core / build-core: .github#5

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>09YPzagAAAAAiPR5XKRSoQpRg352ExmJxQ0gxQUEyMDMwODE0MDYwAEVkZ2U=
qualify-ci / build-core / build-core: .github#7

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / tutorial-tests: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0OITzagAAAACMpVdYEU0wTYGlMGZQR9ksQ0gxQUEyMDMwODEzMDYwAEVkZ2U=
qualify-ci / tutorial-tests: .github#9

! Failed to restore: Cache service responded with 400
qualify-ci / tutorial-tests: .github#49

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / tutorial-tests: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache@v4, actions/checkout@v4, actions/download-artifact@v4, actions/setup-go@v5, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / lint: .github#2

X Process completed with exit code 1.
qualify-ci / lint: .github#16

! Failed to restore: Cache service responded with 400
qualify-ci / lint: .github#52

! Failed to restore: Cache service responded with 400
qualify-ci / lint: .github#24

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / lint: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / ace-page-group-isolation: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0WITzagAAAAAzCcEmW9wlRq5yhIB141iuQ0gxQUEyMDMwODEzMDI1AEVkZ2U=
qualify-ci / ace-page-group-isolation: .github#9

! Failed to restore: Cache service responded with 400
qualify-ci / ace-page-group-isolation: .github#49

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / ace-page-group-isolation: .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* release-please--branches--master Release sase-org/sase#322 · 42897628895
Triggered via workflow_dispatch about 1 hour ago

JOBS
✓ identity in 57s (ID 130114862321)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Assert source and version identity
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ build in 38s (ID 130115420556)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up Python
  ✓ Build once and check the dist set
  ✓ Resolve the exact core pin
  ✓ Fetch the core file list and digests
  ✓ Read the core completeness set at the pin's tag
  ✓ Prove the core tag contains the source pin
  ✓ Seal the candidate manifest
  ✓ Upload the candidate build
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ qualify-prepare in 26s (ID 130115802507)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Download the sealed candidate build
  ✓ Bind the sealed candidate identity
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ exercise-legs (macos-latest, wheel) in 2m5s (ID 130115802596)
  ✓ Set up job
  ✓ Refuse probes outside rehearse
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up Python
  ✓ Ensure tmux for the TUI frame
  ✓ Download the sealed build
  ✓ Resolve the leg dist and manifest fields
  ✓ Verify digests before install
  ✓ Prepare the isolated leg environment
  ✓ Resolve the previous installable PyPI release
  ✓ Run the exercise leg
  ✓ Upload the leg evidence
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ exercise-legs (ubuntu-latest, sdist) in 54s (ID 130115802632)
  ✓ Set up job
  ✓ Refuse probes outside rehearse
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up Python
  - Ensure tmux for the TUI frame
  ✓ Download the sealed build
  ✓ Resolve the leg dist and manifest fields
  ✓ Verify digests before install
  ✓ Prepare the isolated leg environment
  - Resolve the previous installable PyPI release
  ✓ Run the exercise leg
  ✓ Upload the leg evidence
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ exercise-legs (ubuntu-latest, wheel) in 1m8s (ID 130115802657)
  ✓ Set up job
  ✓ Refuse probes outside rehearse
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up Python
  - Ensure tmux for the TUI frame
  ✓ Download the sealed build
  ✓ Resolve the leg dist and manifest fields
  ✓ Verify digests before install
  ✓ Prepare the isolated leg environment
  ✓ Resolve the previous installable PyPI release
  ✓ Run the exercise leg
  ✓ Upload the leg evidence
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ exercise-legs (macos-latest, sdist) in 1m18s (ID 130115802821)
  ✓ Set up job
  ✓ Refuse probes outside rehearse
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up Python
  ✓ Ensure tmux for the TUI frame
  ✓ Download the sealed build
  ✓ Resolve the leg dist and manifest fields
  ✓ Verify digests before install
  ✓ Prepare the isolated leg environment
  - Resolve the previous installable PyPI release
  ✓ Run the exercise leg
  ✓ Upload the leg evidence
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
- stash (ID 130115805318)
✓ qualify-ci / prepare in 26s (ID 130116069325)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Validate qualification inputs
  ✓ Download the sealed candidate manifest
  ✓ Bind published identity from the sealed manifest
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
- qualify-ci / release-core-floor-smoke (ID 130116071518)
- qualify-ci / docs-build (ID 130116072055)
✓ qualify-ci / build-core / build-core in 8m41s (ID 130116334196)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Resolve core mode
  - Resolve pinned Rust core revision
  - Check out Rust core
  ✓ Check out published Rust core tag
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up Rust
  ✓ Cache Rust build
  - Build abi3 Rust core wheel
  ✓ Download the sealed candidate manifest
  ✓ Fetch and verify the published core wheel
  ✓ Build macro LSP
  - Record wheel provenance
  ✓ Record published tag provenance
  ✓ Upload Rust core artifacts
  ✓ Post Cache Rust build
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Check out published Rust core tag
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ exercise in 27s (ID 130117005549)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Download the sealed build
  ✓ Download the leg evidence
  ✓ Merge the legs into one exercise observation
  - Stash the exercise observation on the draft release
  ✓ Upload the exercise observation artifact
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ qualify-ci / perf-floors in 9m50s (ID 130121174612)
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
✓ qualify-ci / tutorial-tests in 1m4s (ID 130121174619)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run tutorial tests
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
X qualify-ci / visual-test in 34m4s (ID 130121174667)
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
X qualify-ci / lint in 1m31s (ID 130121174682)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up preflight Python
  ✓ Download Rust core artifacts for bindings preflight
  ✓ Preflight core bindings
  ✓ Install dependencies
  ✓ Check pinned core bindings
  ✓ Bootstrap SDD sidecars
  ✓ Initialize SASE home
  ✓ Run actions/setup-go@v5
  ✓ Cache Go binaries
  - Install Go tools (keep-sorted)
  ✓ Cache Prettier dependencies
  ✓ Check Python formatting
  ✓ Check Markdown formatting
  X Check generated model docs
  - Check shipped model policy
  - Lint
  - SASE validation
  - Validate committed plans
  - Build and verify package
  ✓ Record installed core version
  ✓ Write qualification evidence
  ✓ Upload qualification evidence
  - Post Cache Prettier dependencies
  - Post Cache Go binaries
  - Post Run actions/setup-go@v5
  ✓ Post Install dependencies
  - Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* qualify-ci / test (3.14) (ID 130121174714)
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
* qualify-ci / test (3.13) (ID 130121174802)
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
* qualify-ci / test (3.12) (ID 130121174849)
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
✓ qualify-ci / ace-page-group-isolation in 1m37s (ID 130121174850)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  ✓ Run ACE shared-page isolation lane
  ✓ Post Install visual dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
identity: .github#7

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
identity: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
build: .github#4

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0sIHzagAAAAB30fM6H9ufTppmpzFOLFMkUEhMMzBFREdFMDEwOABFZGdl
build: .github#7

! Failed to restore: Cache service responded with 400
build: .github#24

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
build: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-prepare: .github#9

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-prepare: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
exercise-legs (macos-latest, wheel): .github#2

- Due to capacity constraints, jobs targeting macOS arm64 runners may experience longer queue times.
exercise-legs (macos-latest, wheel): .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
exercise-legs (ubuntu-latest, sdist): .github#2

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
exercise-legs (ubuntu-latest, sdist): .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
exercise-legs (ubuntu-latest, wheel): .github#2

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
exercise-legs (ubuntu-latest, wheel): .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
exercise-legs (macos-latest, sdist): .github#2

- Due to capacity constraints, jobs targeting macOS arm64 runners may experience longer queue times.
exercise-legs (macos-latest, sdist): .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / prepare: .github#10

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / prepare: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / build-core / build-core: .github#5

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>09YPzagAAAAAiPR5XKRSoQpRg352ExmJxQ0gxQUEyMDMwODE0MDYwAEVkZ2U=
qualify-ci / build-core / build-core: .github#7

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / tutorial-tests: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0OITzagAAAACMpVdYEU0wTYGlMGZQR9ksQ0gxQUEyMDMwODEzMDYwAEVkZ2U=
qualify-ci / tutorial-tests: .github#9

! Failed to restore: Cache service responded with 400
qualify-ci / tutorial-tests: .github#49

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / tutorial-tests: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache@v4, actions/checkout@v4, actions/download-artifact@v4, actions/setup-go@v5, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / lint: .github#2

X Process completed with exit code 1.
qualify-ci / lint: .github#16

! Failed to restore: Cache service responded with 400
qualify-ci / lint: .github#52

! Failed to restore: Cache service responded with 400
qualify-ci / lint: .github#24

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / lint: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / ace-page-group-isolation: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0WITzagAAAAAzCcEmW9wlRq5yhIB141iuQ0gxQUEyMDMwODEzMDI1AEVkZ2U=
qualify-ci / ace-page-group-isolation: .github#9

! Failed to restore: Cache service responded with 400
qualify-ci / ace-page-group-isolation: .github#49

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / ace-page-group-isolation: .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* release-please--branches--master Release sase-org/sase#322 · 42897628895
Triggered via workflow_dispatch about 1 hour ago

JOBS
✓ identity in 57s (ID 130114862321)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Assert source and version identity
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ build in 38s (ID 130115420556)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up Python
  ✓ Build once and check the dist set
  ✓ Resolve the exact core pin
  ✓ Fetch the core file list and digests
  ✓ Read the core completeness set at the pin's tag
  ✓ Prove the core tag contains the source pin
  ✓ Seal the candidate manifest
  ✓ Upload the candidate build
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ qualify-prepare in 26s (ID 130115802507)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Download the sealed candidate build
  ✓ Bind the sealed candidate identity
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ exercise-legs (macos-latest, wheel) in 2m5s (ID 130115802596)
  ✓ Set up job
  ✓ Refuse probes outside rehearse
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up Python
  ✓ Ensure tmux for the TUI frame
  ✓ Download the sealed build
  ✓ Resolve the leg dist and manifest fields
  ✓ Verify digests before install
  ✓ Prepare the isolated leg environment
  ✓ Resolve the previous installable PyPI release
  ✓ Run the exercise leg
  ✓ Upload the leg evidence
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ exercise-legs (ubuntu-latest, sdist) in 54s (ID 130115802632)
  ✓ Set up job
  ✓ Refuse probes outside rehearse
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up Python
  - Ensure tmux for the TUI frame
  ✓ Download the sealed build
  ✓ Resolve the leg dist and manifest fields
  ✓ Verify digests before install
  ✓ Prepare the isolated leg environment
  - Resolve the previous installable PyPI release
  ✓ Run the exercise leg
  ✓ Upload the leg evidence
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ exercise-legs (ubuntu-latest, wheel) in 1m8s (ID 130115802657)
  ✓ Set up job
  ✓ Refuse probes outside rehearse
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up Python
  - Ensure tmux for the TUI frame
  ✓ Download the sealed build
  ✓ Resolve the leg dist and manifest fields
  ✓ Verify digests before install
  ✓ Prepare the isolated leg environment
  ✓ Resolve the previous installable PyPI release
  ✓ Run the exercise leg
  ✓ Upload the leg evidence
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ exercise-legs (macos-latest, sdist) in 1m18s (ID 130115802821)
  ✓ Set up job
  ✓ Refuse probes outside rehearse
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up Python
  ✓ Ensure tmux for the TUI frame
  ✓ Download the sealed build
  ✓ Resolve the leg dist and manifest fields
  ✓ Verify digests before install
  ✓ Prepare the isolated leg environment
  - Resolve the previous installable PyPI release
  ✓ Run the exercise leg
  ✓ Upload the leg evidence
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
- stash (ID 130115805318)
✓ qualify-ci / prepare in 26s (ID 130116069325)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Validate qualification inputs
  ✓ Download the sealed candidate manifest
  ✓ Bind published identity from the sealed manifest
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
- qualify-ci / release-core-floor-smoke (ID 130116071518)
- qualify-ci / docs-build (ID 130116072055)
✓ qualify-ci / build-core / build-core in 8m41s (ID 130116334196)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Resolve core mode
  - Resolve pinned Rust core revision
  - Check out Rust core
  ✓ Check out published Rust core tag
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up Rust
  ✓ Cache Rust build
  - Build abi3 Rust core wheel
  ✓ Download the sealed candidate manifest
  ✓ Fetch and verify the published core wheel
  ✓ Build macro LSP
  - Record wheel provenance
  ✓ Record published tag provenance
  ✓ Upload Rust core artifacts
  ✓ Post Cache Rust build
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Check out published Rust core tag
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ exercise in 27s (ID 130117005549)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Download the sealed build
  ✓ Download the leg evidence
  ✓ Merge the legs into one exercise observation
  - Stash the exercise observation on the draft release
  ✓ Upload the exercise observation artifact
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ qualify-ci / perf-floors in 9m50s (ID 130121174612)
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
✓ qualify-ci / tutorial-tests in 1m4s (ID 130121174619)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run tutorial tests
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
X qualify-ci / visual-test in 34m4s (ID 130121174667)
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
X qualify-ci / lint in 1m31s (ID 130121174682)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up preflight Python
  ✓ Download Rust core artifacts for bindings preflight
  ✓ Preflight core bindings
  ✓ Install dependencies
  ✓ Check pinned core bindings
  ✓ Bootstrap SDD sidecars
  ✓ Initialize SASE home
  ✓ Run actions/setup-go@v5
  ✓ Cache Go binaries
  - Install Go tools (keep-sorted)
  ✓ Cache Prettier dependencies
  ✓ Check Python formatting
  ✓ Check Markdown formatting
  X Check generated model docs
  - Check shipped model policy
  - Lint
  - SASE validation
  - Validate committed plans
  - Build and verify package
  ✓ Record installed core version
  ✓ Write qualification evidence
  ✓ Upload qualification evidence
  - Post Cache Prettier dependencies
  - Post Cache Go binaries
  - Post Run actions/setup-go@v5
  ✓ Post Install dependencies
  - Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* qualify-ci / test (3.14) (ID 130121174714)
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
* qualify-ci / test (3.13) (ID 130121174802)
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
* qualify-ci / test (3.12) (ID 130121174849)
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
✓ qualify-ci / ace-page-group-isolation in 1m37s (ID 130121174850)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  ✓ Run ACE shared-page isolation lane
  ✓ Post Install visual dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
identity: .github#7

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
identity: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
build: .github#4

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0sIHzagAAAAB30fM6H9ufTppmpzFOLFMkUEhMMzBFREdFMDEwOABFZGdl
build: .github#7

! Failed to restore: Cache service responded with 400
build: .github#24

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
build: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-prepare: .github#9

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-prepare: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
exercise-legs (macos-latest, wheel): .github#2

- Due to capacity constraints, jobs targeting macOS arm64 runners may experience longer queue times.
exercise-legs (macos-latest, wheel): .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
exercise-legs (ubuntu-latest, sdist): .github#2

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
exercise-legs (ubuntu-latest, sdist): .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
exercise-legs (ubuntu-latest, wheel): .github#2

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
exercise-legs (ubuntu-latest, wheel): .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
exercise-legs (macos-latest, sdist): .github#2

- Due to capacity constraints, jobs targeting macOS arm64 runners may experience longer queue times.
exercise-legs (macos-latest, sdist): .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / prepare: .github#10

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / prepare: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / build-core / build-core: .github#5

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>09YPzagAAAAAiPR5XKRSoQpRg352ExmJxQ0gxQUEyMDMwODE0MDYwAEVkZ2U=
qualify-ci / build-core / build-core: .github#7

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / tutorial-tests: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0OITzagAAAACMpVdYEU0wTYGlMGZQR9ksQ0gxQUEyMDMwODEzMDYwAEVkZ2U=
qualify-ci / tutorial-tests: .github#9

! Failed to restore: Cache service responded with 400
qualify-ci / tutorial-tests: .github#49

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / tutorial-tests: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache@v4, actions/checkout@v4, actions/download-artifact@v4, actions/setup-go@v5, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / lint: .github#2

X Process completed with exit code 1.
qualify-ci / lint: .github#16

! Failed to restore: Cache service responded with 400
qualify-ci / lint: .github#52

! Failed to restore: Cache service responded with 400
qualify-ci / lint: .github#24

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / lint: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / ace-page-group-isolation: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0WITzagAAAAAzCcEmW9wlRq5yhIB141iuQ0gxQUEyMDMwODEzMDI1AEVkZ2U=
qualify-ci / ace-page-group-isolation: .github#9

! Failed to restore: Cache service responded with 400
qualify-ci / ace-page-group-isolation: .github#49

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / ace-page-group-isolation: .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* release-please--branches--master Release sase-org/sase#322 · 42897628895
Triggered via workflow_dispatch about 1 hour ago

JOBS
✓ identity in 57s (ID 130114862321)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Assert source and version identity
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ build in 38s (ID 130115420556)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up Python
  ✓ Build once and check the dist set
  ✓ Resolve the exact core pin
  ✓ Fetch the core file list and digests
  ✓ Read the core completeness set at the pin's tag
  ✓ Prove the core tag contains the source pin
  ✓ Seal the candidate manifest
  ✓ Upload the candidate build
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ qualify-prepare in 26s (ID 130115802507)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Download the sealed candidate build
  ✓ Bind the sealed candidate identity
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ exercise-legs (macos-latest, wheel) in 2m5s (ID 130115802596)
  ✓ Set up job
  ✓ Refuse probes outside rehearse
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up Python
  ✓ Ensure tmux for the TUI frame
  ✓ Download the sealed build
  ✓ Resolve the leg dist and manifest fields
  ✓ Verify digests before install
  ✓ Prepare the isolated leg environment
  ✓ Resolve the previous installable PyPI release
  ✓ Run the exercise leg
  ✓ Upload the leg evidence
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ exercise-legs (ubuntu-latest, sdist) in 54s (ID 130115802632)
  ✓ Set up job
  ✓ Refuse probes outside rehearse
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up Python
  - Ensure tmux for the TUI frame
  ✓ Download the sealed build
  ✓ Resolve the leg dist and manifest fields
  ✓ Verify digests before install
  ✓ Prepare the isolated leg environment
  - Resolve the previous installable PyPI release
  ✓ Run the exercise leg
  ✓ Upload the leg evidence
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ exercise-legs (ubuntu-latest, wheel) in 1m8s (ID 130115802657)
  ✓ Set up job
  ✓ Refuse probes outside rehearse
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up Python
  - Ensure tmux for the TUI frame
  ✓ Download the sealed build
  ✓ Resolve the leg dist and manifest fields
  ✓ Verify digests before install
  ✓ Prepare the isolated leg environment
  ✓ Resolve the previous installable PyPI release
  ✓ Run the exercise leg
  ✓ Upload the leg evidence
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ exercise-legs (macos-latest, sdist) in 1m18s (ID 130115802821)
  ✓ Set up job
  ✓ Refuse probes outside rehearse
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up Python
  ✓ Ensure tmux for the TUI frame
  ✓ Download the sealed build
  ✓ Resolve the leg dist and manifest fields
  ✓ Verify digests before install
  ✓ Prepare the isolated leg environment
  - Resolve the previous installable PyPI release
  ✓ Run the exercise leg
  ✓ Upload the leg evidence
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
- stash (ID 130115805318)
✓ qualify-ci / prepare in 26s (ID 130116069325)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Validate qualification inputs
  ✓ Download the sealed candidate manifest
  ✓ Bind published identity from the sealed manifest
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
- qualify-ci / release-core-floor-smoke (ID 130116071518)
- qualify-ci / docs-build (ID 130116072055)
✓ qualify-ci / build-core / build-core in 8m41s (ID 130116334196)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Resolve core mode
  - Resolve pinned Rust core revision
  - Check out Rust core
  ✓ Check out published Rust core tag
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up Rust
  ✓ Cache Rust build
  - Build abi3 Rust core wheel
  ✓ Download the sealed candidate manifest
  ✓ Fetch and verify the published core wheel
  ✓ Build macro LSP
  - Record wheel provenance
  ✓ Record published tag provenance
  ✓ Upload Rust core artifacts
  ✓ Post Cache Rust build
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Check out published Rust core tag
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ exercise in 27s (ID 130117005549)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Download the sealed build
  ✓ Download the leg evidence
  ✓ Merge the legs into one exercise observation
  - Stash the exercise observation on the draft release
  ✓ Upload the exercise observation artifact
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ qualify-ci / perf-floors in 9m50s (ID 130121174612)
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
✓ qualify-ci / tutorial-tests in 1m4s (ID 130121174619)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run tutorial tests
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
X qualify-ci / visual-test in 34m4s (ID 130121174667)
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
X qualify-ci / lint in 1m31s (ID 130121174682)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up preflight Python
  ✓ Download Rust core artifacts for bindings preflight
  ✓ Preflight core bindings
  ✓ Install dependencies
  ✓ Check pinned core bindings
  ✓ Bootstrap SDD sidecars
  ✓ Initialize SASE home
  ✓ Run actions/setup-go@v5
  ✓ Cache Go binaries
  - Install Go tools (keep-sorted)
  ✓ Cache Prettier dependencies
  ✓ Check Python formatting
  ✓ Check Markdown formatting
  X Check generated model docs
  - Check shipped model policy
  - Lint
  - SASE validation
  - Validate committed plans
  - Build and verify package
  ✓ Record installed core version
  ✓ Write qualification evidence
  ✓ Upload qualification evidence
  - Post Cache Prettier dependencies
  - Post Cache Go binaries
  - Post Run actions/setup-go@v5
  ✓ Post Install dependencies
  - Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* qualify-ci / test (3.14) (ID 130121174714)
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
* qualify-ci / test (3.13) (ID 130121174802)
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
* qualify-ci / test (3.12) (ID 130121174849)
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
✓ qualify-ci / ace-page-group-isolation in 1m37s (ID 130121174850)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  ✓ Run ACE shared-page isolation lane
  ✓ Post Install visual dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
identity: .github#7

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
identity: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
build: .github#4

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0sIHzagAAAAB30fM6H9ufTppmpzFOLFMkUEhMMzBFREdFMDEwOABFZGdl
build: .github#7

! Failed to restore: Cache service responded with 400
build: .github#24

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
build: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-prepare: .github#9

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-prepare: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
exercise-legs (macos-latest, wheel): .github#2

- Due to capacity constraints, jobs targeting macOS arm64 runners may experience longer queue times.
exercise-legs (macos-latest, wheel): .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
exercise-legs (ubuntu-latest, sdist): .github#2

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
exercise-legs (ubuntu-latest, sdist): .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
exercise-legs (ubuntu-latest, wheel): .github#2

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
exercise-legs (ubuntu-latest, wheel): .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
exercise-legs (macos-latest, sdist): .github#2

- Due to capacity constraints, jobs targeting macOS arm64 runners may experience longer queue times.
exercise-legs (macos-latest, sdist): .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / prepare: .github#10

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / prepare: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / build-core / build-core: .github#5

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>09YPzagAAAAAiPR5XKRSoQpRg352ExmJxQ0gxQUEyMDMwODE0MDYwAEVkZ2U=
qualify-ci / build-core / build-core: .github#7

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / tutorial-tests: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0OITzagAAAACMpVdYEU0wTYGlMGZQR9ksQ0gxQUEyMDMwODEzMDYwAEVkZ2U=
qualify-ci / tutorial-tests: .github#9

! Failed to restore: Cache service responded with 400
qualify-ci / tutorial-tests: .github#49

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / tutorial-tests: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache@v4, actions/checkout@v4, actions/download-artifact@v4, actions/setup-go@v5, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / lint: .github#2

X Process completed with exit code 1.
qualify-ci / lint: .github#16

! Failed to restore: Cache service responded with 400
qualify-ci / lint: .github#52

! Failed to restore: Cache service responded with 400
qualify-ci / lint: .github#24

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / lint: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / ace-page-group-isolation: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0WITzagAAAAAzCcEmW9wlRq5yhIB141iuQ0gxQUEyMDMwODEzMDI1AEVkZ2U=
qualify-ci / ace-page-group-isolation: .github#9

! Failed to restore: Cache service responded with 400
qualify-ci / ace-page-group-isolation: .github#49

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / ace-page-group-isolation: .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* release-please--branches--master Release sase-org/sase#322 · 42897628895
Triggered via workflow_dispatch about 1 hour ago

JOBS
✓ identity in 57s (ID 130114862321)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Assert source and version identity
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ build in 38s (ID 130115420556)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up Python
  ✓ Build once and check the dist set
  ✓ Resolve the exact core pin
  ✓ Fetch the core file list and digests
  ✓ Read the core completeness set at the pin's tag
  ✓ Prove the core tag contains the source pin
  ✓ Seal the candidate manifest
  ✓ Upload the candidate build
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ qualify-prepare in 26s (ID 130115802507)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Download the sealed candidate build
  ✓ Bind the sealed candidate identity
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ exercise-legs (macos-latest, wheel) in 2m5s (ID 130115802596)
  ✓ Set up job
  ✓ Refuse probes outside rehearse
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up Python
  ✓ Ensure tmux for the TUI frame
  ✓ Download the sealed build
  ✓ Resolve the leg dist and manifest fields
  ✓ Verify digests before install
  ✓ Prepare the isolated leg environment
  ✓ Resolve the previous installable PyPI release
  ✓ Run the exercise leg
  ✓ Upload the leg evidence
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ exercise-legs (ubuntu-latest, sdist) in 54s (ID 130115802632)
  ✓ Set up job
  ✓ Refuse probes outside rehearse
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up Python
  - Ensure tmux for the TUI frame
  ✓ Download the sealed build
  ✓ Resolve the leg dist and manifest fields
  ✓ Verify digests before install
  ✓ Prepare the isolated leg environment
  - Resolve the previous installable PyPI release
  ✓ Run the exercise leg
  ✓ Upload the leg evidence
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ exercise-legs (ubuntu-latest, wheel) in 1m8s (ID 130115802657)
  ✓ Set up job
  ✓ Refuse probes outside rehearse
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up Python
  - Ensure tmux for the TUI frame
  ✓ Download the sealed build
  ✓ Resolve the leg dist and manifest fields
  ✓ Verify digests before install
  ✓ Prepare the isolated leg environment
  ✓ Resolve the previous installable PyPI release
  ✓ Run the exercise leg
  ✓ Upload the leg evidence
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ exercise-legs (macos-latest, sdist) in 1m18s (ID 130115802821)
  ✓ Set up job
  ✓ Refuse probes outside rehearse
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up Python
  ✓ Ensure tmux for the TUI frame
  ✓ Download the sealed build
  ✓ Resolve the leg dist and manifest fields
  ✓ Verify digests before install
  ✓ Prepare the isolated leg environment
  - Resolve the previous installable PyPI release
  ✓ Run the exercise leg
  ✓ Upload the leg evidence
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
- stash (ID 130115805318)
✓ qualify-ci / prepare in 26s (ID 130116069325)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Validate qualification inputs
  ✓ Download the sealed candidate manifest
  ✓ Bind published identity from the sealed manifest
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
- qualify-ci / release-core-floor-smoke (ID 130116071518)
- qualify-ci / docs-build (ID 130116072055)
✓ qualify-ci / build-core / build-core in 8m41s (ID 130116334196)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Resolve core mode
  - Resolve pinned Rust core revision
  - Check out Rust core
  ✓ Check out published Rust core tag
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up Rust
  ✓ Cache Rust build
  - Build abi3 Rust core wheel
  ✓ Download the sealed candidate manifest
  ✓ Fetch and verify the published core wheel
  ✓ Build macro LSP
  - Record wheel provenance
  ✓ Record published tag provenance
  ✓ Upload Rust core artifacts
  ✓ Post Cache Rust build
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Check out published Rust core tag
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ exercise in 27s (ID 130117005549)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Download the sealed build
  ✓ Download the leg evidence
  ✓ Merge the legs into one exercise observation
  - Stash the exercise observation on the draft release
  ✓ Upload the exercise observation artifact
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ qualify-ci / perf-floors in 9m50s (ID 130121174612)
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
✓ qualify-ci / tutorial-tests in 1m4s (ID 130121174619)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run tutorial tests
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
X qualify-ci / visual-test in 34m4s (ID 130121174667)
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
X qualify-ci / lint in 1m31s (ID 130121174682)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up preflight Python
  ✓ Download Rust core artifacts for bindings preflight
  ✓ Preflight core bindings
  ✓ Install dependencies
  ✓ Check pinned core bindings
  ✓ Bootstrap SDD sidecars
  ✓ Initialize SASE home
  ✓ Run actions/setup-go@v5
  ✓ Cache Go binaries
  - Install Go tools (keep-sorted)
  ✓ Cache Prettier dependencies
  ✓ Check Python formatting
  ✓ Check Markdown formatting
  X Check generated model docs
  - Check shipped model policy
  - Lint
  - SASE validation
  - Validate committed plans
  - Build and verify package
  ✓ Record installed core version
  ✓ Write qualification evidence
  ✓ Upload qualification evidence
  - Post Cache Prettier dependencies
  - Post Cache Go binaries
  - Post Run actions/setup-go@v5
  ✓ Post Install dependencies
  - Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ qualify-ci / test (3.14) in 1h1m23s (ID 130121174714)
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
* qualify-ci / test (3.13) (ID 130121174802)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  - Run tests (coverage leg)
  ✓ Run tests
  - Build shard timings table
  - Upload shard timings
  - Upload coverage
  ✓ Record installed core version
  * Write qualification evidence
  * Upload qualification evidence
  * Post Install dependencies
  * Post Run actions/checkout@v4
* qualify-ci / test (3.12) (ID 130121174849)
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
✓ qualify-ci / ace-page-group-isolation in 1m37s (ID 130121174850)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  ✓ Run ACE shared-page isolation lane
  ✓ Post Install visual dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
identity: .github#7

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
identity: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
build: .github#4

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0sIHzagAAAAB30fM6H9ufTppmpzFOLFMkUEhMMzBFREdFMDEwOABFZGdl
build: .github#7

! Failed to restore: Cache service responded with 400
build: .github#24

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
build: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-prepare: .github#9

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-prepare: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
exercise-legs (macos-latest, wheel): .github#2

- Due to capacity constraints, jobs targeting macOS arm64 runners may experience longer queue times.
exercise-legs (macos-latest, wheel): .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
exercise-legs (ubuntu-latest, sdist): .github#2

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
exercise-legs (ubuntu-latest, sdist): .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
exercise-legs (ubuntu-latest, wheel): .github#2

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
exercise-legs (ubuntu-latest, wheel): .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
exercise-legs (macos-latest, sdist): .github#2

- Due to capacity constraints, jobs targeting macOS arm64 runners may experience longer queue times.
exercise-legs (macos-latest, sdist): .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / prepare: .github#10

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / prepare: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / build-core / build-core: .github#5

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>09YPzagAAAAAiPR5XKRSoQpRg352ExmJxQ0gxQUEyMDMwODE0MDYwAEVkZ2U=
qualify-ci / build-core / build-core: .github#7

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / tutorial-tests: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0OITzagAAAACMpVdYEU0wTYGlMGZQR9ksQ0gxQUEyMDMwODEzMDYwAEVkZ2U=
qualify-ci / tutorial-tests: .github#9

! Failed to restore: Cache service responded with 400
qualify-ci / tutorial-tests: .github#49

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / tutorial-tests: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache@v4, actions/checkout@v4, actions/download-artifact@v4, actions/setup-go@v5, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / lint: .github#2

X Process completed with exit code 1.
qualify-ci / lint: .github#16

! Failed to restore: Cache service responded with 400
qualify-ci / lint: .github#52

! Failed to restore: Cache service responded with 400
qualify-ci / lint: .github#24

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / lint: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / test (3.14): .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0WpLzagAAAAAKTuCr9zQ+Qb/obHbru8aMTEFYMzExMDAwMTE0MDMxAEVkZ2U=
qualify-ci / test (3.14): .github#9

! Failed to restore: Cache service responded with 400
qualify-ci / test (3.14): .github#49

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / test (3.14): .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* release-please--branches--master Release sase-org/sase#322 · 42897628895
Triggered via workflow_dispatch about 1 hour ago

JOBS
✓ identity in 57s (ID 130114862321)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Assert source and version identity
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ build in 38s (ID 130115420556)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up Python
  ✓ Build once and check the dist set
  ✓ Resolve the exact core pin
  ✓ Fetch the core file list and digests
  ✓ Read the core completeness set at the pin's tag
  ✓ Prove the core tag contains the source pin
  ✓ Seal the candidate manifest
  ✓ Upload the candidate build
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ qualify-prepare in 26s (ID 130115802507)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Download the sealed candidate build
  ✓ Bind the sealed candidate identity
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ exercise-legs (macos-latest, wheel) in 2m5s (ID 130115802596)
  ✓ Set up job
  ✓ Refuse probes outside rehearse
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up Python
  ✓ Ensure tmux for the TUI frame
  ✓ Download the sealed build
  ✓ Resolve the leg dist and manifest fields
  ✓ Verify digests before install
  ✓ Prepare the isolated leg environment
  ✓ Resolve the previous installable PyPI release
  ✓ Run the exercise leg
  ✓ Upload the leg evidence
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ exercise-legs (ubuntu-latest, sdist) in 54s (ID 130115802632)
  ✓ Set up job
  ✓ Refuse probes outside rehearse
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up Python
  - Ensure tmux for the TUI frame
  ✓ Download the sealed build
  ✓ Resolve the leg dist and manifest fields
  ✓ Verify digests before install
  ✓ Prepare the isolated leg environment
  - Resolve the previous installable PyPI release
  ✓ Run the exercise leg
  ✓ Upload the leg evidence
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ exercise-legs (ubuntu-latest, wheel) in 1m8s (ID 130115802657)
  ✓ Set up job
  ✓ Refuse probes outside rehearse
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up Python
  - Ensure tmux for the TUI frame
  ✓ Download the sealed build
  ✓ Resolve the leg dist and manifest fields
  ✓ Verify digests before install
  ✓ Prepare the isolated leg environment
  ✓ Resolve the previous installable PyPI release
  ✓ Run the exercise leg
  ✓ Upload the leg evidence
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ exercise-legs (macos-latest, sdist) in 1m18s (ID 130115802821)
  ✓ Set up job
  ✓ Refuse probes outside rehearse
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up Python
  ✓ Ensure tmux for the TUI frame
  ✓ Download the sealed build
  ✓ Resolve the leg dist and manifest fields
  ✓ Verify digests before install
  ✓ Prepare the isolated leg environment
  - Resolve the previous installable PyPI release
  ✓ Run the exercise leg
  ✓ Upload the leg evidence
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
- stash (ID 130115805318)
✓ qualify-ci / prepare in 26s (ID 130116069325)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Validate qualification inputs
  ✓ Download the sealed candidate manifest
  ✓ Bind published identity from the sealed manifest
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
- qualify-ci / release-core-floor-smoke (ID 130116071518)
- qualify-ci / docs-build (ID 130116072055)
✓ qualify-ci / build-core / build-core in 8m41s (ID 130116334196)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Resolve core mode
  - Resolve pinned Rust core revision
  - Check out Rust core
  ✓ Check out published Rust core tag
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up Rust
  ✓ Cache Rust build
  - Build abi3 Rust core wheel
  ✓ Download the sealed candidate manifest
  ✓ Fetch and verify the published core wheel
  ✓ Build macro LSP
  - Record wheel provenance
  ✓ Record published tag provenance
  ✓ Upload Rust core artifacts
  ✓ Post Cache Rust build
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Check out published Rust core tag
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ exercise in 27s (ID 130117005549)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Download the sealed build
  ✓ Download the leg evidence
  ✓ Merge the legs into one exercise observation
  - Stash the exercise observation on the draft release
  ✓ Upload the exercise observation artifact
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ qualify-ci / perf-floors in 9m50s (ID 130121174612)
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
✓ qualify-ci / tutorial-tests in 1m4s (ID 130121174619)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run tutorial tests
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
X qualify-ci / visual-test in 34m4s (ID 130121174667)
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
X qualify-ci / lint in 1m31s (ID 130121174682)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up preflight Python
  ✓ Download Rust core artifacts for bindings preflight
  ✓ Preflight core bindings
  ✓ Install dependencies
  ✓ Check pinned core bindings
  ✓ Bootstrap SDD sidecars
  ✓ Initialize SASE home
  ✓ Run actions/setup-go@v5
  ✓ Cache Go binaries
  - Install Go tools (keep-sorted)
  ✓ Cache Prettier dependencies
  ✓ Check Python formatting
  ✓ Check Markdown formatting
  X Check generated model docs
  - Check shipped model policy
  - Lint
  - SASE validation
  - Validate committed plans
  - Build and verify package
  ✓ Record installed core version
  ✓ Write qualification evidence
  ✓ Upload qualification evidence
  - Post Cache Prettier dependencies
  - Post Cache Go binaries
  - Post Run actions/setup-go@v5
  ✓ Post Install dependencies
  - Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ qualify-ci / test (3.14) in 1h1m23s (ID 130121174714)
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
✓ qualify-ci / test (3.13) in 1h2m30s (ID 130121174802)
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
* qualify-ci / test (3.12) (ID 130121174849)
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
✓ qualify-ci / ace-page-group-isolation in 1m37s (ID 130121174850)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  ✓ Run ACE shared-page isolation lane
  ✓ Post Install visual dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
identity: .github#7

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
identity: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
build: .github#4

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0sIHzagAAAAB30fM6H9ufTppmpzFOLFMkUEhMMzBFREdFMDEwOABFZGdl
build: .github#7

! Failed to restore: Cache service responded with 400
build: .github#24

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
build: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-prepare: .github#9

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-prepare: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
exercise-legs (macos-latest, wheel): .github#2

- Due to capacity constraints, jobs targeting macOS arm64 runners may experience longer queue times.
exercise-legs (macos-latest, wheel): .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
exercise-legs (ubuntu-latest, sdist): .github#2

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
exercise-legs (ubuntu-latest, sdist): .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
exercise-legs (ubuntu-latest, wheel): .github#2

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
exercise-legs (ubuntu-latest, wheel): .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
exercise-legs (macos-latest, sdist): .github#2

- Due to capacity constraints, jobs targeting macOS arm64 runners may experience longer queue times.
exercise-legs (macos-latest, sdist): .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / prepare: .github#10

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / prepare: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / build-core / build-core: .github#5

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>09YPzagAAAAAiPR5XKRSoQpRg352ExmJxQ0gxQUEyMDMwODE0MDYwAEVkZ2U=
qualify-ci / build-core / build-core: .github#7

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / tutorial-tests: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0OITzagAAAACMpVdYEU0wTYGlMGZQR9ksQ0gxQUEyMDMwODEzMDYwAEVkZ2U=
qualify-ci / tutorial-tests: .github#9

! Failed to restore: Cache service responded with 400
qualify-ci / tutorial-tests: .github#49

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / tutorial-tests: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache@v4, actions/checkout@v4, actions/download-artifact@v4, actions/setup-go@v5, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / lint: .github#2

X Process completed with exit code 1.
qualify-ci / lint: .github#16

! Failed to restore: Cache service responded with 400
qualify-ci / lint: .github#52

! Failed to restore: Cache service responded with 400
qualify-ci / lint: .github#24

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / lint: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / test (3.14): .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0WpLzagAAAAAKTuCr9zQ+Qb/obHbru8aMTEFYMzExMDAwMTE0MDMxAEVkZ2U=
qualify-ci / test (3.14): .github#9

! Failed to restore: Cache service responded with 400
qualify-ci / test (3.14): .github#49

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / test (3.14): .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* release-please--branches--master Release sase-org/sase#322 · 42897628895
Triggered via workflow_dispatch about 1 hour ago

JOBS
✓ identity in 57s (ID 130114862321)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Assert source and version identity
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ build in 38s (ID 130115420556)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up Python
  ✓ Build once and check the dist set
  ✓ Resolve the exact core pin
  ✓ Fetch the core file list and digests
  ✓ Read the core completeness set at the pin's tag
  ✓ Prove the core tag contains the source pin
  ✓ Seal the candidate manifest
  ✓ Upload the candidate build
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ qualify-prepare in 26s (ID 130115802507)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Download the sealed candidate build
  ✓ Bind the sealed candidate identity
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ exercise-legs (macos-latest, wheel) in 2m5s (ID 130115802596)
  ✓ Set up job
  ✓ Refuse probes outside rehearse
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up Python
  ✓ Ensure tmux for the TUI frame
  ✓ Download the sealed build
  ✓ Resolve the leg dist and manifest fields
  ✓ Verify digests before install
  ✓ Prepare the isolated leg environment
  ✓ Resolve the previous installable PyPI release
  ✓ Run the exercise leg
  ✓ Upload the leg evidence
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ exercise-legs (ubuntu-latest, sdist) in 54s (ID 130115802632)
  ✓ Set up job
  ✓ Refuse probes outside rehearse
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up Python
  - Ensure tmux for the TUI frame
  ✓ Download the sealed build
  ✓ Resolve the leg dist and manifest fields
  ✓ Verify digests before install
  ✓ Prepare the isolated leg environment
  - Resolve the previous installable PyPI release
  ✓ Run the exercise leg
  ✓ Upload the leg evidence
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ exercise-legs (ubuntu-latest, wheel) in 1m8s (ID 130115802657)
  ✓ Set up job
  ✓ Refuse probes outside rehearse
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up Python
  - Ensure tmux for the TUI frame
  ✓ Download the sealed build
  ✓ Resolve the leg dist and manifest fields
  ✓ Verify digests before install
  ✓ Prepare the isolated leg environment
  ✓ Resolve the previous installable PyPI release
  ✓ Run the exercise leg
  ✓ Upload the leg evidence
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ exercise-legs (macos-latest, sdist) in 1m18s (ID 130115802821)
  ✓ Set up job
  ✓ Refuse probes outside rehearse
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up Python
  ✓ Ensure tmux for the TUI frame
  ✓ Download the sealed build
  ✓ Resolve the leg dist and manifest fields
  ✓ Verify digests before install
  ✓ Prepare the isolated leg environment
  - Resolve the previous installable PyPI release
  ✓ Run the exercise leg
  ✓ Upload the leg evidence
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
- stash (ID 130115805318)
✓ qualify-ci / prepare in 26s (ID 130116069325)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Validate qualification inputs
  ✓ Download the sealed candidate manifest
  ✓ Bind published identity from the sealed manifest
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
- qualify-ci / release-core-floor-smoke (ID 130116071518)
- qualify-ci / docs-build (ID 130116072055)
✓ qualify-ci / build-core / build-core in 8m41s (ID 130116334196)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Resolve core mode
  - Resolve pinned Rust core revision
  - Check out Rust core
  ✓ Check out published Rust core tag
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up Rust
  ✓ Cache Rust build
  - Build abi3 Rust core wheel
  ✓ Download the sealed candidate manifest
  ✓ Fetch and verify the published core wheel
  ✓ Build macro LSP
  - Record wheel provenance
  ✓ Record published tag provenance
  ✓ Upload Rust core artifacts
  ✓ Post Cache Rust build
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Check out published Rust core tag
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ exercise in 27s (ID 130117005549)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Download the sealed build
  ✓ Download the leg evidence
  ✓ Merge the legs into one exercise observation
  - Stash the exercise observation on the draft release
  ✓ Upload the exercise observation artifact
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ qualify-ci / perf-floors in 9m50s (ID 130121174612)
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
✓ qualify-ci / tutorial-tests in 1m4s (ID 130121174619)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run tutorial tests
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
X qualify-ci / visual-test in 34m4s (ID 130121174667)
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
X qualify-ci / lint in 1m31s (ID 130121174682)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up preflight Python
  ✓ Download Rust core artifacts for bindings preflight
  ✓ Preflight core bindings
  ✓ Install dependencies
  ✓ Check pinned core bindings
  ✓ Bootstrap SDD sidecars
  ✓ Initialize SASE home
  ✓ Run actions/setup-go@v5
  ✓ Cache Go binaries
  - Install Go tools (keep-sorted)
  ✓ Cache Prettier dependencies
  ✓ Check Python formatting
  ✓ Check Markdown formatting
  X Check generated model docs
  - Check shipped model policy
  - Lint
  - SASE validation
  - Validate committed plans
  - Build and verify package
  ✓ Record installed core version
  ✓ Write qualification evidence
  ✓ Upload qualification evidence
  - Post Cache Prettier dependencies
  - Post Cache Go binaries
  - Post Run actions/setup-go@v5
  ✓ Post Install dependencies
  - Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ qualify-ci / test (3.14) in 1h1m23s (ID 130121174714)
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
✓ qualify-ci / test (3.13) in 1h2m30s (ID 130121174802)
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
* qualify-ci / test (3.12) (ID 130121174849)
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
✓ qualify-ci / ace-page-group-isolation in 1m37s (ID 130121174850)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  ✓ Run ACE shared-page isolation lane
  ✓ Post Install visual dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
identity: .github#7

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
identity: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
build: .github#4

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0sIHzagAAAAB30fM6H9ufTppmpzFOLFMkUEhMMzBFREdFMDEwOABFZGdl
build: .github#7

! Failed to restore: Cache service responded with 400
build: .github#24

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
build: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-prepare: .github#9

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-prepare: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
exercise-legs (macos-latest, wheel): .github#2

- Due to capacity constraints, jobs targeting macOS arm64 runners may experience longer queue times.
exercise-legs (macos-latest, wheel): .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
exercise-legs (ubuntu-latest, sdist): .github#2

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
exercise-legs (ubuntu-latest, sdist): .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
exercise-legs (ubuntu-latest, wheel): .github#2

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
exercise-legs (ubuntu-latest, wheel): .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
exercise-legs (macos-latest, sdist): .github#2

- Due to capacity constraints, jobs targeting macOS arm64 runners may experience longer queue times.
exercise-legs (macos-latest, sdist): .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / prepare: .github#10

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / prepare: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / build-core / build-core: .github#5

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>09YPzagAAAAAiPR5XKRSoQpRg352ExmJxQ0gxQUEyMDMwODE0MDYwAEVkZ2U=
qualify-ci / build-core / build-core: .github#7

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / tutorial-tests: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0OITzagAAAACMpVdYEU0wTYGlMGZQR9ksQ0gxQUEyMDMwODEzMDYwAEVkZ2U=
qualify-ci / tutorial-tests: .github#9

! Failed to restore: Cache service responded with 400
qualify-ci / tutorial-tests: .github#49

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / tutorial-tests: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache@v4, actions/checkout@v4, actions/download-artifact@v4, actions/setup-go@v5, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / lint: .github#2

X Process completed with exit code 1.
qualify-ci / lint: .github#16

! Failed to restore: Cache service responded with 400
qualify-ci / lint: .github#52

! Failed to restore: Cache service responded with 400
qualify-ci / lint: .github#24

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / lint: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / test (3.14): .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0WpLzagAAAAAKTuCr9zQ+Qb/obHbru8aMTEFYMzExMDAwMTE0MDMxAEVkZ2U=
qualify-ci / test (3.14): .github#9

! Failed to restore: Cache service responded with 400
qualify-ci / test (3.14): .github#49

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / test (3.14): .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* release-please--branches--master Release sase-org/sase#322 · 42897628895
Triggered via workflow_dispatch about 1 hour ago

JOBS
✓ identity in 57s (ID 130114862321)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Assert source and version identity
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ build in 38s (ID 130115420556)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up Python
  ✓ Build once and check the dist set
  ✓ Resolve the exact core pin
  ✓ Fetch the core file list and digests
  ✓ Read the core completeness set at the pin's tag
  ✓ Prove the core tag contains the source pin
  ✓ Seal the candidate manifest
  ✓ Upload the candidate build
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ qualify-prepare in 26s (ID 130115802507)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Download the sealed candidate build
  ✓ Bind the sealed candidate identity
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ exercise-legs (macos-latest, wheel) in 2m5s (ID 130115802596)
  ✓ Set up job
  ✓ Refuse probes outside rehearse
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up Python
  ✓ Ensure tmux for the TUI frame
  ✓ Download the sealed build
  ✓ Resolve the leg dist and manifest fields
  ✓ Verify digests before install
  ✓ Prepare the isolated leg environment
  ✓ Resolve the previous installable PyPI release
  ✓ Run the exercise leg
  ✓ Upload the leg evidence
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ exercise-legs (ubuntu-latest, sdist) in 54s (ID 130115802632)
  ✓ Set up job
  ✓ Refuse probes outside rehearse
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up Python
  - Ensure tmux for the TUI frame
  ✓ Download the sealed build
  ✓ Resolve the leg dist and manifest fields
  ✓ Verify digests before install
  ✓ Prepare the isolated leg environment
  - Resolve the previous installable PyPI release
  ✓ Run the exercise leg
  ✓ Upload the leg evidence
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ exercise-legs (ubuntu-latest, wheel) in 1m8s (ID 130115802657)
  ✓ Set up job
  ✓ Refuse probes outside rehearse
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up Python
  - Ensure tmux for the TUI frame
  ✓ Download the sealed build
  ✓ Resolve the leg dist and manifest fields
  ✓ Verify digests before install
  ✓ Prepare the isolated leg environment
  ✓ Resolve the previous installable PyPI release
  ✓ Run the exercise leg
  ✓ Upload the leg evidence
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ exercise-legs (macos-latest, sdist) in 1m18s (ID 130115802821)
  ✓ Set up job
  ✓ Refuse probes outside rehearse
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up Python
  ✓ Ensure tmux for the TUI frame
  ✓ Download the sealed build
  ✓ Resolve the leg dist and manifest fields
  ✓ Verify digests before install
  ✓ Prepare the isolated leg environment
  - Resolve the previous installable PyPI release
  ✓ Run the exercise leg
  ✓ Upload the leg evidence
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
- stash (ID 130115805318)
✓ qualify-ci / prepare in 26s (ID 130116069325)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Validate qualification inputs
  ✓ Download the sealed candidate manifest
  ✓ Bind published identity from the sealed manifest
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
- qualify-ci / release-core-floor-smoke (ID 130116071518)
- qualify-ci / docs-build (ID 130116072055)
✓ qualify-ci / build-core / build-core in 8m41s (ID 130116334196)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Resolve core mode
  - Resolve pinned Rust core revision
  - Check out Rust core
  ✓ Check out published Rust core tag
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up Rust
  ✓ Cache Rust build
  - Build abi3 Rust core wheel
  ✓ Download the sealed candidate manifest
  ✓ Fetch and verify the published core wheel
  ✓ Build macro LSP
  - Record wheel provenance
  ✓ Record published tag provenance
  ✓ Upload Rust core artifacts
  ✓ Post Cache Rust build
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Check out published Rust core tag
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ exercise in 27s (ID 130117005549)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Download the sealed build
  ✓ Download the leg evidence
  ✓ Merge the legs into one exercise observation
  - Stash the exercise observation on the draft release
  ✓ Upload the exercise observation artifact
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ qualify-ci / perf-floors in 9m50s (ID 130121174612)
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
✓ qualify-ci / tutorial-tests in 1m4s (ID 130121174619)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run tutorial tests
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
X qualify-ci / visual-test in 34m4s (ID 130121174667)
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
X qualify-ci / lint in 1m31s (ID 130121174682)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up preflight Python
  ✓ Download Rust core artifacts for bindings preflight
  ✓ Preflight core bindings
  ✓ Install dependencies
  ✓ Check pinned core bindings
  ✓ Bootstrap SDD sidecars
  ✓ Initialize SASE home
  ✓ Run actions/setup-go@v5
  ✓ Cache Go binaries
  - Install Go tools (keep-sorted)
  ✓ Cache Prettier dependencies
  ✓ Check Python formatting
  ✓ Check Markdown formatting
  X Check generated model docs
  - Check shipped model policy
  - Lint
  - SASE validation
  - Validate committed plans
  - Build and verify package
  ✓ Record installed core version
  ✓ Write qualification evidence
  ✓ Upload qualification evidence
  - Post Cache Prettier dependencies
  - Post Cache Go binaries
  - Post Run actions/setup-go@v5
  ✓ Post Install dependencies
  - Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ qualify-ci / test (3.14) in 1h1m23s (ID 130121174714)
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
✓ qualify-ci / test (3.13) in 1h2m30s (ID 130121174802)
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
* qualify-ci / test (3.12) (ID 130121174849)
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
✓ qualify-ci / ace-page-group-isolation in 1m37s (ID 130121174850)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  ✓ Run ACE shared-page isolation lane
  ✓ Post Install visual dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
identity: .github#7

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
identity: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
build: .github#4

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0sIHzagAAAAB30fM6H9ufTppmpzFOLFMkUEhMMzBFREdFMDEwOABFZGdl
build: .github#7

! Failed to restore: Cache service responded with 400
build: .github#24

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
build: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-prepare: .github#9

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-prepare: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
exercise-legs (macos-latest, wheel): .github#2

- Due to capacity constraints, jobs targeting macOS arm64 runners may experience longer queue times.
exercise-legs (macos-latest, wheel): .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
exercise-legs (ubuntu-latest, sdist): .github#2

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
exercise-legs (ubuntu-latest, sdist): .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
exercise-legs (ubuntu-latest, wheel): .github#2

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
exercise-legs (ubuntu-latest, wheel): .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
exercise-legs (macos-latest, sdist): .github#2

- Due to capacity constraints, jobs targeting macOS arm64 runners may experience longer queue times.
exercise-legs (macos-latest, sdist): .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / prepare: .github#10

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / prepare: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / build-core / build-core: .github#5

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>09YPzagAAAAAiPR5XKRSoQpRg352ExmJxQ0gxQUEyMDMwODE0MDYwAEVkZ2U=
qualify-ci / build-core / build-core: .github#7

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / tutorial-tests: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0OITzagAAAACMpVdYEU0wTYGlMGZQR9ksQ0gxQUEyMDMwODEzMDYwAEVkZ2U=
qualify-ci / tutorial-tests: .github#9

! Failed to restore: Cache service responded with 400
qualify-ci / tutorial-tests: .github#49

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / tutorial-tests: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache@v4, actions/checkout@v4, actions/download-artifact@v4, actions/setup-go@v5, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / lint: .github#2

X Process completed with exit code 1.
qualify-ci / lint: .github#16

! Failed to restore: Cache service responded with 400
qualify-ci / lint: .github#52

! Failed to restore: Cache service responded with 400
qualify-ci / lint: .github#24

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / lint: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / test (3.14): .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0WpLzagAAAAAKTuCr9zQ+Qb/obHbru8aMTEFYMzExMDAwMTE0MDMxAEVkZ2U=
qualify-ci / test (3.14): .github#9

! Failed to restore: Cache service responded with 400
qualify-ci / test (3.14): .github#49

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / test (3.14): .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* release-please--branches--master Release sase-org/sase#322 · 42897628895
Triggered via workflow_dispatch about 1 hour ago

JOBS
✓ identity in 57s (ID 130114862321)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Assert source and version identity
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ build in 38s (ID 130115420556)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up Python
  ✓ Build once and check the dist set
  ✓ Resolve the exact core pin
  ✓ Fetch the core file list and digests
  ✓ Read the core completeness set at the pin's tag
  ✓ Prove the core tag contains the source pin
  ✓ Seal the candidate manifest
  ✓ Upload the candidate build
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ qualify-prepare in 26s (ID 130115802507)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Download the sealed candidate build
  ✓ Bind the sealed candidate identity
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ exercise-legs (macos-latest, wheel) in 2m5s (ID 130115802596)
  ✓ Set up job
  ✓ Refuse probes outside rehearse
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up Python
  ✓ Ensure tmux for the TUI frame
  ✓ Download the sealed build
  ✓ Resolve the leg dist and manifest fields
  ✓ Verify digests before install
  ✓ Prepare the isolated leg environment
  ✓ Resolve the previous installable PyPI release
  ✓ Run the exercise leg
  ✓ Upload the leg evidence
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ exercise-legs (ubuntu-latest, sdist) in 54s (ID 130115802632)
  ✓ Set up job
  ✓ Refuse probes outside rehearse
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up Python
  - Ensure tmux for the TUI frame
  ✓ Download the sealed build
  ✓ Resolve the leg dist and manifest fields
  ✓ Verify digests before install
  ✓ Prepare the isolated leg environment
  - Resolve the previous installable PyPI release
  ✓ Run the exercise leg
  ✓ Upload the leg evidence
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ exercise-legs (ubuntu-latest, wheel) in 1m8s (ID 130115802657)
  ✓ Set up job
  ✓ Refuse probes outside rehearse
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up Python
  - Ensure tmux for the TUI frame
  ✓ Download the sealed build
  ✓ Resolve the leg dist and manifest fields
  ✓ Verify digests before install
  ✓ Prepare the isolated leg environment
  ✓ Resolve the previous installable PyPI release
  ✓ Run the exercise leg
  ✓ Upload the leg evidence
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ exercise-legs (macos-latest, sdist) in 1m18s (ID 130115802821)
  ✓ Set up job
  ✓ Refuse probes outside rehearse
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up Python
  ✓ Ensure tmux for the TUI frame
  ✓ Download the sealed build
  ✓ Resolve the leg dist and manifest fields
  ✓ Verify digests before install
  ✓ Prepare the isolated leg environment
  - Resolve the previous installable PyPI release
  ✓ Run the exercise leg
  ✓ Upload the leg evidence
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
- stash (ID 130115805318)
✓ qualify-ci / prepare in 26s (ID 130116069325)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Validate qualification inputs
  ✓ Download the sealed candidate manifest
  ✓ Bind published identity from the sealed manifest
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
- qualify-ci / release-core-floor-smoke (ID 130116071518)
- qualify-ci / docs-build (ID 130116072055)
✓ qualify-ci / build-core / build-core in 8m41s (ID 130116334196)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Resolve core mode
  - Resolve pinned Rust core revision
  - Check out Rust core
  ✓ Check out published Rust core tag
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up Rust
  ✓ Cache Rust build
  - Build abi3 Rust core wheel
  ✓ Download the sealed candidate manifest
  ✓ Fetch and verify the published core wheel
  ✓ Build macro LSP
  - Record wheel provenance
  ✓ Record published tag provenance
  ✓ Upload Rust core artifacts
  ✓ Post Cache Rust build
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Check out published Rust core tag
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ exercise in 27s (ID 130117005549)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Download the sealed build
  ✓ Download the leg evidence
  ✓ Merge the legs into one exercise observation
  - Stash the exercise observation on the draft release
  ✓ Upload the exercise observation artifact
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ qualify-ci / perf-floors in 9m50s (ID 130121174612)
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
✓ qualify-ci / tutorial-tests in 1m4s (ID 130121174619)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run tutorial tests
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
X qualify-ci / visual-test in 34m4s (ID 130121174667)
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
X qualify-ci / lint in 1m31s (ID 130121174682)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up preflight Python
  ✓ Download Rust core artifacts for bindings preflight
  ✓ Preflight core bindings
  ✓ Install dependencies
  ✓ Check pinned core bindings
  ✓ Bootstrap SDD sidecars
  ✓ Initialize SASE home
  ✓ Run actions/setup-go@v5
  ✓ Cache Go binaries
  - Install Go tools (keep-sorted)
  ✓ Cache Prettier dependencies
  ✓ Check Python formatting
  ✓ Check Markdown formatting
  X Check generated model docs
  - Check shipped model policy
  - Lint
  - SASE validation
  - Validate committed plans
  - Build and verify package
  ✓ Record installed core version
  ✓ Write qualification evidence
  ✓ Upload qualification evidence
  - Post Cache Prettier dependencies
  - Post Cache Go binaries
  - Post Run actions/setup-go@v5
  ✓ Post Install dependencies
  - Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ qualify-ci / test (3.14) in 1h1m23s (ID 130121174714)
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
✓ qualify-ci / test (3.13) in 1h2m30s (ID 130121174802)
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
* qualify-ci / test (3.12) (ID 130121174849)
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
✓ qualify-ci / ace-page-group-isolation in 1m37s (ID 130121174850)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  ✓ Run ACE shared-page isolation lane
  ✓ Post Install visual dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
identity: .github#7

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
identity: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
build: .github#4

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0sIHzagAAAAB30fM6H9ufTppmpzFOLFMkUEhMMzBFREdFMDEwOABFZGdl
build: .github#7

! Failed to restore: Cache service responded with 400
build: .github#24

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
build: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-prepare: .github#9

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-prepare: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
exercise-legs (macos-latest, wheel): .github#2

- Due to capacity constraints, jobs targeting macOS arm64 runners may experience longer queue times.
exercise-legs (macos-latest, wheel): .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
exercise-legs (ubuntu-latest, sdist): .github#2

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
exercise-legs (ubuntu-latest, sdist): .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
exercise-legs (ubuntu-latest, wheel): .github#2

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
exercise-legs (ubuntu-latest, wheel): .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
exercise-legs (macos-latest, sdist): .github#2

- Due to capacity constraints, jobs targeting macOS arm64 runners may experience longer queue times.
exercise-legs (macos-latest, sdist): .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / prepare: .github#10

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / prepare: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / build-core / build-core: .github#5

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>09YPzagAAAAAiPR5XKRSoQpRg352ExmJxQ0gxQUEyMDMwODE0MDYwAEVkZ2U=
qualify-ci / build-core / build-core: .github#7

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / tutorial-tests: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0OITzagAAAACMpVdYEU0wTYGlMGZQR9ksQ0gxQUEyMDMwODEzMDYwAEVkZ2U=
qualify-ci / tutorial-tests: .github#9

! Failed to restore: Cache service responded with 400
qualify-ci / tutorial-tests: .github#49

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / tutorial-tests: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache@v4, actions/checkout@v4, actions/download-artifact@v4, actions/setup-go@v5, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / lint: .github#2

X Process completed with exit code 1.
qualify-ci / lint: .github#16

! Failed to restore: Cache service responded with 400
qualify-ci / lint: .github#52

! Failed to restore: Cache service responded with 400
qualify-ci / lint: .github#24

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / lint: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / test (3.14): .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0WpLzagAAAAAKTuCr9zQ+Qb/obHbru8aMTEFYMzExMDAwMTE0MDMxAEVkZ2U=
qualify-ci / test (3.14): .github#9

! Failed to restore: Cache service responded with 400
qualify-ci / test (3.14): .github#49

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / test (3.14): .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* release-please--branches--master Release sase-org/sase#322 · 42897628895
Triggered via workflow_dispatch about 1 hour ago

JOBS
✓ identity in 57s (ID 130114862321)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Assert source and version identity
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ build in 38s (ID 130115420556)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up Python
  ✓ Build once and check the dist set
  ✓ Resolve the exact core pin
  ✓ Fetch the core file list and digests
  ✓ Read the core completeness set at the pin's tag
  ✓ Prove the core tag contains the source pin
  ✓ Seal the candidate manifest
  ✓ Upload the candidate build
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ qualify-prepare in 26s (ID 130115802507)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Download the sealed candidate build
  ✓ Bind the sealed candidate identity
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ exercise-legs (macos-latest, wheel) in 2m5s (ID 130115802596)
  ✓ Set up job
  ✓ Refuse probes outside rehearse
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up Python
  ✓ Ensure tmux for the TUI frame
  ✓ Download the sealed build
  ✓ Resolve the leg dist and manifest fields
  ✓ Verify digests before install
  ✓ Prepare the isolated leg environment
  ✓ Resolve the previous installable PyPI release
  ✓ Run the exercise leg
  ✓ Upload the leg evidence
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ exercise-legs (ubuntu-latest, sdist) in 54s (ID 130115802632)
  ✓ Set up job
  ✓ Refuse probes outside rehearse
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up Python
  - Ensure tmux for the TUI frame
  ✓ Download the sealed build
  ✓ Resolve the leg dist and manifest fields
  ✓ Verify digests before install
  ✓ Prepare the isolated leg environment
  - Resolve the previous installable PyPI release
  ✓ Run the exercise leg
  ✓ Upload the leg evidence
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ exercise-legs (ubuntu-latest, wheel) in 1m8s (ID 130115802657)
  ✓ Set up job
  ✓ Refuse probes outside rehearse
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up Python
  - Ensure tmux for the TUI frame
  ✓ Download the sealed build
  ✓ Resolve the leg dist and manifest fields
  ✓ Verify digests before install
  ✓ Prepare the isolated leg environment
  ✓ Resolve the previous installable PyPI release
  ✓ Run the exercise leg
  ✓ Upload the leg evidence
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ exercise-legs (macos-latest, sdist) in 1m18s (ID 130115802821)
  ✓ Set up job
  ✓ Refuse probes outside rehearse
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up Python
  ✓ Ensure tmux for the TUI frame
  ✓ Download the sealed build
  ✓ Resolve the leg dist and manifest fields
  ✓ Verify digests before install
  ✓ Prepare the isolated leg environment
  - Resolve the previous installable PyPI release
  ✓ Run the exercise leg
  ✓ Upload the leg evidence
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
- stash (ID 130115805318)
✓ qualify-ci / prepare in 26s (ID 130116069325)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Validate qualification inputs
  ✓ Download the sealed candidate manifest
  ✓ Bind published identity from the sealed manifest
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
- qualify-ci / release-core-floor-smoke (ID 130116071518)
- qualify-ci / docs-build (ID 130116072055)
✓ qualify-ci / build-core / build-core in 8m41s (ID 130116334196)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Resolve core mode
  - Resolve pinned Rust core revision
  - Check out Rust core
  ✓ Check out published Rust core tag
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up Rust
  ✓ Cache Rust build
  - Build abi3 Rust core wheel
  ✓ Download the sealed candidate manifest
  ✓ Fetch and verify the published core wheel
  ✓ Build macro LSP
  - Record wheel provenance
  ✓ Record published tag provenance
  ✓ Upload Rust core artifacts
  ✓ Post Cache Rust build
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Check out published Rust core tag
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ exercise in 27s (ID 130117005549)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Download the sealed build
  ✓ Download the leg evidence
  ✓ Merge the legs into one exercise observation
  - Stash the exercise observation on the draft release
  ✓ Upload the exercise observation artifact
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ qualify-ci / perf-floors in 9m50s (ID 130121174612)
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
✓ qualify-ci / tutorial-tests in 1m4s (ID 130121174619)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run tutorial tests
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
X qualify-ci / visual-test in 34m4s (ID 130121174667)
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
X qualify-ci / lint in 1m31s (ID 130121174682)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up preflight Python
  ✓ Download Rust core artifacts for bindings preflight
  ✓ Preflight core bindings
  ✓ Install dependencies
  ✓ Check pinned core bindings
  ✓ Bootstrap SDD sidecars
  ✓ Initialize SASE home
  ✓ Run actions/setup-go@v5
  ✓ Cache Go binaries
  - Install Go tools (keep-sorted)
  ✓ Cache Prettier dependencies
  ✓ Check Python formatting
  ✓ Check Markdown formatting
  X Check generated model docs
  - Check shipped model policy
  - Lint
  - SASE validation
  - Validate committed plans
  - Build and verify package
  ✓ Record installed core version
  ✓ Write qualification evidence
  ✓ Upload qualification evidence
  - Post Cache Prettier dependencies
  - Post Cache Go binaries
  - Post Run actions/setup-go@v5
  ✓ Post Install dependencies
  - Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ qualify-ci / test (3.14) in 1h1m23s (ID 130121174714)
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
✓ qualify-ci / test (3.13) in 1h2m30s (ID 130121174802)
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
* qualify-ci / test (3.12) (ID 130121174849)
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
✓ qualify-ci / ace-page-group-isolation in 1m37s (ID 130121174850)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  ✓ Run ACE shared-page isolation lane
  ✓ Post Install visual dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
identity: .github#7

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
identity: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
build: .github#4

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0sIHzagAAAAB30fM6H9ufTppmpzFOLFMkUEhMMzBFREdFMDEwOABFZGdl
build: .github#7

! Failed to restore: Cache service responded with 400
build: .github#24

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
build: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-prepare: .github#9

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-prepare: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
exercise-legs (macos-latest, wheel): .github#2

- Due to capacity constraints, jobs targeting macOS arm64 runners may experience longer queue times.
exercise-legs (macos-latest, wheel): .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
exercise-legs (ubuntu-latest, sdist): .github#2

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
exercise-legs (ubuntu-latest, sdist): .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
exercise-legs (ubuntu-latest, wheel): .github#2

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
exercise-legs (ubuntu-latest, wheel): .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
exercise-legs (macos-latest, sdist): .github#2

- Due to capacity constraints, jobs targeting macOS arm64 runners may experience longer queue times.
exercise-legs (macos-latest, sdist): .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / prepare: .github#10

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / prepare: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / build-core / build-core: .github#5

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>09YPzagAAAAAiPR5XKRSoQpRg352ExmJxQ0gxQUEyMDMwODE0MDYwAEVkZ2U=
qualify-ci / build-core / build-core: .github#7

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / tutorial-tests: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0OITzagAAAACMpVdYEU0wTYGlMGZQR9ksQ0gxQUEyMDMwODEzMDYwAEVkZ2U=
qualify-ci / tutorial-tests: .github#9

! Failed to restore: Cache service responded with 400
qualify-ci / tutorial-tests: .github#49

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / tutorial-tests: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache@v4, actions/checkout@v4, actions/download-artifact@v4, actions/setup-go@v5, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / lint: .github#2

X Process completed with exit code 1.
qualify-ci / lint: .github#16

! Failed to restore: Cache service responded with 400
qualify-ci / lint: .github#52

! Failed to restore: Cache service responded with 400
qualify-ci / lint: .github#24

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / lint: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / test (3.14): .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0WpLzagAAAAAKTuCr9zQ+Qb/obHbru8aMTEFYMzExMDAwMTE0MDMxAEVkZ2U=
qualify-ci / test (3.14): .github#9

! Failed to restore: Cache service responded with 400
qualify-ci / test (3.14): .github#49

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / test (3.14): .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* release-please--branches--master Release sase-org/sase#322 · 42897628895
Triggered via workflow_dispatch about 1 hour ago

JOBS
✓ identity in 57s (ID 130114862321)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Assert source and version identity
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ build in 38s (ID 130115420556)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up Python
  ✓ Build once and check the dist set
  ✓ Resolve the exact core pin
  ✓ Fetch the core file list and digests
  ✓ Read the core completeness set at the pin's tag
  ✓ Prove the core tag contains the source pin
  ✓ Seal the candidate manifest
  ✓ Upload the candidate build
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ qualify-prepare in 26s (ID 130115802507)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Download the sealed candidate build
  ✓ Bind the sealed candidate identity
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ exercise-legs (macos-latest, wheel) in 2m5s (ID 130115802596)
  ✓ Set up job
  ✓ Refuse probes outside rehearse
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up Python
  ✓ Ensure tmux for the TUI frame
  ✓ Download the sealed build
  ✓ Resolve the leg dist and manifest fields
  ✓ Verify digests before install
  ✓ Prepare the isolated leg environment
  ✓ Resolve the previous installable PyPI release
  ✓ Run the exercise leg
  ✓ Upload the leg evidence
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ exercise-legs (ubuntu-latest, sdist) in 54s (ID 130115802632)
  ✓ Set up job
  ✓ Refuse probes outside rehearse
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up Python
  - Ensure tmux for the TUI frame
  ✓ Download the sealed build
  ✓ Resolve the leg dist and manifest fields
  ✓ Verify digests before install
  ✓ Prepare the isolated leg environment
  - Resolve the previous installable PyPI release
  ✓ Run the exercise leg
  ✓ Upload the leg evidence
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ exercise-legs (ubuntu-latest, wheel) in 1m8s (ID 130115802657)
  ✓ Set up job
  ✓ Refuse probes outside rehearse
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up Python
  - Ensure tmux for the TUI frame
  ✓ Download the sealed build
  ✓ Resolve the leg dist and manifest fields
  ✓ Verify digests before install
  ✓ Prepare the isolated leg environment
  ✓ Resolve the previous installable PyPI release
  ✓ Run the exercise leg
  ✓ Upload the leg evidence
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ exercise-legs (macos-latest, sdist) in 1m18s (ID 130115802821)
  ✓ Set up job
  ✓ Refuse probes outside rehearse
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up Python
  ✓ Ensure tmux for the TUI frame
  ✓ Download the sealed build
  ✓ Resolve the leg dist and manifest fields
  ✓ Verify digests before install
  ✓ Prepare the isolated leg environment
  - Resolve the previous installable PyPI release
  ✓ Run the exercise leg
  ✓ Upload the leg evidence
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
- stash (ID 130115805318)
✓ qualify-ci / prepare in 26s (ID 130116069325)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Validate qualification inputs
  ✓ Download the sealed candidate manifest
  ✓ Bind published identity from the sealed manifest
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
- qualify-ci / release-core-floor-smoke (ID 130116071518)
- qualify-ci / docs-build (ID 130116072055)
✓ qualify-ci / build-core / build-core in 8m41s (ID 130116334196)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Resolve core mode
  - Resolve pinned Rust core revision
  - Check out Rust core
  ✓ Check out published Rust core tag
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up Rust
  ✓ Cache Rust build
  - Build abi3 Rust core wheel
  ✓ Download the sealed candidate manifest
  ✓ Fetch and verify the published core wheel
  ✓ Build macro LSP
  - Record wheel provenance
  ✓ Record published tag provenance
  ✓ Upload Rust core artifacts
  ✓ Post Cache Rust build
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Check out published Rust core tag
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ exercise in 27s (ID 130117005549)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Download the sealed build
  ✓ Download the leg evidence
  ✓ Merge the legs into one exercise observation
  - Stash the exercise observation on the draft release
  ✓ Upload the exercise observation artifact
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ qualify-ci / perf-floors in 9m50s (ID 130121174612)
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
✓ qualify-ci / tutorial-tests in 1m4s (ID 130121174619)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run tutorial tests
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
X qualify-ci / visual-test in 34m4s (ID 130121174667)
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
X qualify-ci / lint in 1m31s (ID 130121174682)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up preflight Python
  ✓ Download Rust core artifacts for bindings preflight
  ✓ Preflight core bindings
  ✓ Install dependencies
  ✓ Check pinned core bindings
  ✓ Bootstrap SDD sidecars
  ✓ Initialize SASE home
  ✓ Run actions/setup-go@v5
  ✓ Cache Go binaries
  - Install Go tools (keep-sorted)
  ✓ Cache Prettier dependencies
  ✓ Check Python formatting
  ✓ Check Markdown formatting
  X Check generated model docs
  - Check shipped model policy
  - Lint
  - SASE validation
  - Validate committed plans
  - Build and verify package
  ✓ Record installed core version
  ✓ Write qualification evidence
  ✓ Upload qualification evidence
  - Post Cache Prettier dependencies
  - Post Cache Go binaries
  - Post Run actions/setup-go@v5
  ✓ Post Install dependencies
  - Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ qualify-ci / test (3.14) in 1h1m23s (ID 130121174714)
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
✓ qualify-ci / test (3.13) in 1h2m30s (ID 130121174802)
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
✓ qualify-ci / test (3.12) in 1h13m41s (ID 130121174849)
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
✓ qualify-ci / ace-page-group-isolation in 1m37s (ID 130121174850)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  ✓ Run ACE shared-page isolation lane
  ✓ Post Install visual dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
X qualify in 29s (ID 130162387963)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Download the sealed candidate build
  ✓ Evaluate the qualification evidence
  ✓ Upload the qualification observation
  - Attach the qualification observation to the draft
  X Fail the verdict when qualification is red
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* publish (ID 130162681835)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Refuse probes outside rehearse
  * Stage the sealed dists from the build artifact
  * Stage the sealed dists from the draft release
  * Normalize the manifest and staged paths
  * Re-verify every digest against the sealed manifest
  * Collect the generation evidence observations
  * Download the evidence observation artifacts
  * Run the promotion predicate for this candidate
  * Fetch the PyPI file list for the version
  * Compute the digest-checked upload plan
  * Copy only the planned uploads
  * Publish the missing files to PyPI
  * Record the publication observation
  * Upload the publication observation artifact
  * Post Run actions/checkout@v4

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
identity: .github#7

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
identity: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
build: .github#4

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0sIHzagAAAAB30fM6H9ufTppmpzFOLFMkUEhMMzBFREdFMDEwOABFZGdl
build: .github#7

! Failed to restore: Cache service responded with 400
build: .github#24

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
build: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-prepare: .github#9

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-prepare: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
exercise-legs (macos-latest, wheel): .github#2

- Due to capacity constraints, jobs targeting macOS arm64 runners may experience longer queue times.
exercise-legs (macos-latest, wheel): .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
exercise-legs (ubuntu-latest, sdist): .github#2

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
exercise-legs (ubuntu-latest, sdist): .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
exercise-legs (ubuntu-latest, wheel): .github#2

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
exercise-legs (ubuntu-latest, wheel): .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
exercise-legs (macos-latest, sdist): .github#2

- Due to capacity constraints, jobs targeting macOS arm64 runners may experience longer queue times.
exercise-legs (macos-latest, sdist): .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / prepare: .github#10

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / prepare: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / build-core / build-core: .github#5

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>09YPzagAAAAAiPR5XKRSoQpRg352ExmJxQ0gxQUEyMDMwODE0MDYwAEVkZ2U=
qualify-ci / build-core / build-core: .github#7

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / tutorial-tests: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0OITzagAAAACMpVdYEU0wTYGlMGZQR9ksQ0gxQUEyMDMwODEzMDYwAEVkZ2U=
qualify-ci / tutorial-tests: .github#9

! Failed to restore: Cache service responded with 400
qualify-ci / tutorial-tests: .github#49

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / tutorial-tests: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache@v4, actions/checkout@v4, actions/download-artifact@v4, actions/setup-go@v5, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / lint: .github#2

X Process completed with exit code 1.
qualify-ci / lint: .github#16

! Failed to restore: Cache service responded with 400
qualify-ci / lint: .github#52

! Failed to restore: Cache service responded with 400
qualify-ci / lint: .github#24

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / lint: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / test (3.14): .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0WpLzagAAAAAKTuCr9zQ+Qb/obHbru8aMTEFYMzExMDAwMTE0MDMxAEVkZ2U=
qualify-ci / test (3.14): .github#9

! Failed to restore: Cache service responded with 400
qualify-ci / test (3.14): .github#49

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / test (3.14): .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify: .github#12

X Process completed with exit code 1.
qualify: .github#35

X QUALIFY_RED(lint:harness)
qualify: .github#34

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify: .github#1

X release-please--branches--master Release sase-org/sase#322 · 42897628895
Triggered via workflow_dispatch about 1 hour ago

JOBS
✓ identity in 57s (ID 130114862321)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Assert source and version identity
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ build in 38s (ID 130115420556)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up Python
  ✓ Build once and check the dist set
  ✓ Resolve the exact core pin
  ✓ Fetch the core file list and digests
  ✓ Read the core completeness set at the pin's tag
  ✓ Prove the core tag contains the source pin
  ✓ Seal the candidate manifest
  ✓ Upload the candidate build
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ qualify-prepare in 26s (ID 130115802507)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Download the sealed candidate build
  ✓ Bind the sealed candidate identity
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ exercise-legs (macos-latest, wheel) in 2m5s (ID 130115802596)
  ✓ Set up job
  ✓ Refuse probes outside rehearse
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up Python
  ✓ Ensure tmux for the TUI frame
  ✓ Download the sealed build
  ✓ Resolve the leg dist and manifest fields
  ✓ Verify digests before install
  ✓ Prepare the isolated leg environment
  ✓ Resolve the previous installable PyPI release
  ✓ Run the exercise leg
  ✓ Upload the leg evidence
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ exercise-legs (ubuntu-latest, sdist) in 54s (ID 130115802632)
  ✓ Set up job
  ✓ Refuse probes outside rehearse
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up Python
  - Ensure tmux for the TUI frame
  ✓ Download the sealed build
  ✓ Resolve the leg dist and manifest fields
  ✓ Verify digests before install
  ✓ Prepare the isolated leg environment
  - Resolve the previous installable PyPI release
  ✓ Run the exercise leg
  ✓ Upload the leg evidence
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ exercise-legs (ubuntu-latest, wheel) in 1m8s (ID 130115802657)
  ✓ Set up job
  ✓ Refuse probes outside rehearse
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up Python
  - Ensure tmux for the TUI frame
  ✓ Download the sealed build
  ✓ Resolve the leg dist and manifest fields
  ✓ Verify digests before install
  ✓ Prepare the isolated leg environment
  ✓ Resolve the previous installable PyPI release
  ✓ Run the exercise leg
  ✓ Upload the leg evidence
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ exercise-legs (macos-latest, sdist) in 1m18s (ID 130115802821)
  ✓ Set up job
  ✓ Refuse probes outside rehearse
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up Python
  ✓ Ensure tmux for the TUI frame
  ✓ Download the sealed build
  ✓ Resolve the leg dist and manifest fields
  ✓ Verify digests before install
  ✓ Prepare the isolated leg environment
  - Resolve the previous installable PyPI release
  ✓ Run the exercise leg
  ✓ Upload the leg evidence
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
- stash (ID 130115805318)
✓ qualify-ci / prepare in 26s (ID 130116069325)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Validate qualification inputs
  ✓ Download the sealed candidate manifest
  ✓ Bind published identity from the sealed manifest
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
- qualify-ci / release-core-floor-smoke (ID 130116071518)
- qualify-ci / docs-build (ID 130116072055)
✓ qualify-ci / build-core / build-core in 8m41s (ID 130116334196)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Resolve core mode
  - Resolve pinned Rust core revision
  - Check out Rust core
  ✓ Check out published Rust core tag
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up Rust
  ✓ Cache Rust build
  - Build abi3 Rust core wheel
  ✓ Download the sealed candidate manifest
  ✓ Fetch and verify the published core wheel
  ✓ Build macro LSP
  - Record wheel provenance
  ✓ Record published tag provenance
  ✓ Upload Rust core artifacts
  ✓ Post Cache Rust build
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Check out published Rust core tag
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ exercise in 27s (ID 130117005549)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Download the sealed build
  ✓ Download the leg evidence
  ✓ Merge the legs into one exercise observation
  - Stash the exercise observation on the draft release
  ✓ Upload the exercise observation artifact
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ qualify-ci / perf-floors in 9m50s (ID 130121174612)
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
✓ qualify-ci / tutorial-tests in 1m4s (ID 130121174619)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run tutorial tests
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
X qualify-ci / visual-test in 34m4s (ID 130121174667)
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
X qualify-ci / lint in 1m31s (ID 130121174682)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Set up preflight Python
  ✓ Download Rust core artifacts for bindings preflight
  ✓ Preflight core bindings
  ✓ Install dependencies
  ✓ Check pinned core bindings
  ✓ Bootstrap SDD sidecars
  ✓ Initialize SASE home
  ✓ Run actions/setup-go@v5
  ✓ Cache Go binaries
  - Install Go tools (keep-sorted)
  ✓ Cache Prettier dependencies
  ✓ Check Python formatting
  ✓ Check Markdown formatting
  X Check generated model docs
  - Check shipped model policy
  - Lint
  - SASE validation
  - Validate committed plans
  - Build and verify package
  ✓ Record installed core version
  ✓ Write qualification evidence
  ✓ Upload qualification evidence
  - Post Cache Prettier dependencies
  - Post Cache Go binaries
  - Post Run actions/setup-go@v5
  ✓ Post Install dependencies
  - Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ qualify-ci / test (3.14) in 1h1m23s (ID 130121174714)
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
✓ qualify-ci / test (3.13) in 1h2m30s (ID 130121174802)
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
✓ qualify-ci / test (3.12) in 1h13m41s (ID 130121174849)
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
✓ qualify-ci / ace-page-group-isolation in 1m37s (ID 130121174850)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  ✓ Run ACE shared-page isolation lane
  ✓ Post Install visual dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
X qualify in 29s (ID 130162387963)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Download the sealed candidate build
  ✓ Evaluate the qualification evidence
  ✓ Upload the qualification observation
  - Attach the qualification observation to the draft
  X Fail the verdict when qualification is red
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
X publish in 24s (ID 130162681835)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Refuse probes outside rehearse
  ✓ Stage the sealed dists from the build artifact
  - Stage the sealed dists from the draft release
  ✓ Normalize the manifest and staged paths
  ✓ Re-verify every digest against the sealed manifest
  ✓ Collect the generation evidence observations
  ✓ Download the evidence observation artifacts
  X Run the promotion predicate for this candidate
  - Fetch the PyPI file list for the version
  - Compute the digest-checked upload plan
  - Copy only the planned uploads
  - Publish the missing files to PyPI
  - Record the publication observation
  - Upload the publication observation artifact
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
- confirm-install (ID 130162937721)
- confirm in 0s (ID 130162937919)

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
identity: .github#7

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
identity: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
build: .github#4

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0sIHzagAAAAB30fM6H9ufTppmpzFOLFMkUEhMMzBFREdFMDEwOABFZGdl
build: .github#7

! Failed to restore: Cache service responded with 400
build: .github#24

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
build: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-prepare: .github#9

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-prepare: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
exercise-legs (macos-latest, wheel): .github#2

- Due to capacity constraints, jobs targeting macOS arm64 runners may experience longer queue times.
exercise-legs (macos-latest, wheel): .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
exercise-legs (ubuntu-latest, sdist): .github#2

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
exercise-legs (ubuntu-latest, sdist): .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
exercise-legs (ubuntu-latest, wheel): .github#2

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
exercise-legs (ubuntu-latest, wheel): .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
exercise-legs (macos-latest, sdist): .github#2

- Due to capacity constraints, jobs targeting macOS arm64 runners may experience longer queue times.
exercise-legs (macos-latest, sdist): .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / prepare: .github#10

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / prepare: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / build-core / build-core: .github#5

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>09YPzagAAAAAiPR5XKRSoQpRg352ExmJxQ0gxQUEyMDMwODE0MDYwAEVkZ2U=
qualify-ci / build-core / build-core: .github#7

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / tutorial-tests: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0OITzagAAAACMpVdYEU0wTYGlMGZQR9ksQ0gxQUEyMDMwODEzMDYwAEVkZ2U=
qualify-ci / tutorial-tests: .github#9

! Failed to restore: Cache service responded with 400
qualify-ci / tutorial-tests: .github#49

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / tutorial-tests: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache@v4, actions/checkout@v4, actions/download-artifact@v4, actions/setup-go@v5, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / lint: .github#2

X Process completed with exit code 1.
qualify-ci / lint: .github#16

! Failed to restore: Cache service responded with 400
qualify-ci / lint: .github#52

! Failed to restore: Cache service responded with 400
qualify-ci / lint: .github#24

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / lint: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / test (3.14): .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0WpLzagAAAAAKTuCr9zQ+Qb/obHbru8aMTEFYMzExMDAwMTE0MDMxAEVkZ2U=
qualify-ci / test (3.14): .github#9

! Failed to restore: Cache service responded with 400
qualify-ci / test (3.14): .github#49

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / test (3.14): .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify: .github#12

X Process completed with exit code 1.
qualify: .github#35

X QUALIFY_RED(lint:harness)
qualify: .github#34

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
publish: .github#3

X Process completed with exit code 1.
publish: .github#64

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
publish: .github#1


