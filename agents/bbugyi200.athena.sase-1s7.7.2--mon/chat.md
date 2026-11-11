# Chat History - ace-run (sase-1s7.7.2--mon)

- **TIMESTAMP:** 2026-11-11 05:54:00 EST
- **MODEL:** muse/muse-spark-1.3-contributor
- **AGENT:** sase-1s7.7.2--mon

## Prompt

sase monitor start --command 'gh run watch 42992733019 -R sase-org/sase --interval 120 || true' --reason 'Wait for rehearse-mode release.yml run 42992733019 to complete'

## Response

sase: running unwrapped (no profile (monitor.tool_wrap is verify))
Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* release-please--branches--master Release sase-org/sase#322 · 42992733019
Triggered via workflow_dispatch about 56 minutes ago

JOBS
✓ identity in 51s (ID 130429292693)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Assert source and version identity
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ build in 35s (ID 130429702498)
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
✓ qualify-prepare in 27s (ID 130429998624)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Download the sealed candidate build
  ✓ Bind the sealed candidate identity
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ exercise-legs (ubuntu-latest, wheel) in 1m4s (ID 130429998685)
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
✓ exercise-legs (macos-latest, sdist) in 1m52s (ID 130429998700)
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
✓ exercise-legs (macos-latest, wheel) in 1m55s (ID 130429998736)
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
✓ exercise-legs (ubuntu-latest, sdist) in 53s (ID 130429998828)
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
- stash (ID 130430001268)
✓ qualify-ci / prepare in 24s (ID 130430236751)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Validate qualification inputs
  ✓ Download the sealed candidate manifest
  ✓ Bind published identity from the sealed manifest
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
- qualify-ci / docs-build in 0s (ID 130430238633)
- qualify-ci / release-core-floor-smoke in 0s (ID 130430239945)
✓ qualify-ci / build-core / build-core in 7m24s (ID 130430445331)
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
✓ exercise in 24s (ID 130430922757)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Download the sealed build
  ✓ Download the leg evidence
  ✓ Merge the legs into one exercise observation
  - Stash the exercise observation on the draft release
  ✓ Upload the exercise observation artifact
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ qualify-ci / ace-page-group-isolation in 1m36s (ID 130433914911)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  ✓ Run ACE shared-page isolation lane
  ✓ Post Install visual dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
X qualify-ci / visual-test in 23m57s (ID 130433914913)
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
✓ qualify-ci / perf-floors in 9m28s (ID 130433914961)
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
* qualify-ci / test (3.12) (ID 130433915030)
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
✓ qualify-ci / tutorial-tests in 1m1s (ID 130433915035)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run tutorial tests
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ qualify-ci / lint in 6m14s (ID 130433915045)
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
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* qualify-ci / test (3.13) (ID 130433915166)
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
* qualify-ci / test (3.14) (ID 130433915280)
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
identity: .github#7

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
identity: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
build: .github#4

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0DTH0agAAAAD7rbAUNBT8RL9zAt1UenRYTVNQMzExMDAwMTA0MDI3AEVkZ2U=
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
exercise-legs (ubuntu-latest, wheel): .github#2

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
exercise-legs (ubuntu-latest, wheel): .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
exercise-legs (macos-latest, sdist): .github#2

- Due to capacity constraints, jobs targeting macOS arm64 runners may experience longer queue times.
exercise-legs (macos-latest, sdist): .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
exercise-legs (macos-latest, wheel): .github#2

- Due to capacity constraints, jobs targeting macOS arm64 runners may experience longer queue times.
exercise-legs (macos-latest, wheel): .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
exercise-legs (ubuntu-latest, sdist): .github#2

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
exercise-legs (ubuntu-latest, sdist): .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / prepare: .github#10

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / prepare: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / build-core / build-core: .github#5

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0BTP0agAAAACIQtJKm5FTQLUbV1bojc6rUEhMMzBFREdFMDQxOABFZGdl
qualify-ci / build-core / build-core: .github#7

! Failed to restore: Cache service responded with 400
qualify-ci / build-core / build-core: .github#25

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / build-core / build-core: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
exercise: .github#4

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
exercise: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / ace-page-group-isolation: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0aDP0agAAAAB0dJofL/zsSp+UTSSgEcPMUEhMMzBFREdFMDExNwBFZGdl
qualify-ci / ace-page-group-isolation: .github#9

! Failed to restore: Cache service responded with 400
qualify-ci / ace-page-group-isolation: .github#49

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / ace-page-group-isolation: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / visual-test: .github#2

X agents_final_rows_80x40: updated | changed pixels 11761/1019844 (1.153216%) | expected=tests/ace/tui/visual/snapshots/png/agents_final_rows_80x40.png
qualify-ci / visual-test: tests/ace/tui/visual/test_ace_png_snapshots_agents_final_rows.py#86

X agents_final_rows_60x40: updated | changed pixels 8667/769500 (1.126316%) | expected=tests/ace/tui/visual/snapshots/png/agents_final_rows_60x40.png
qualify-ci / visual-test: tests/ace/tui/visual/test_ace_png_snapshots_agents_final_rows.py#86

X Process completed with exit code 1.
qualify-ci / visual-test: .github#382

! Failed to restore: Cache service responded with 400
qualify-ci / visual-test: .github#49

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / visual-test: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / perf-floors: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0QDX0agAAAADc89K4ImAPR5uO4uh7cK+OQ0gxQUEyMDMwODE0MDM0AEVkZ2U=
qualify-ci / perf-floors: .github#9

! Failed to restore: Cache service responded with 400
qualify-ci / perf-floors: .github#49

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / perf-floors: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / tutorial-tests: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0RDP0agAAAACTIjNRdoBhQoq9lzCQEBnsTEFYRURHRTIwMTgARWRnZQ==
qualify-ci / tutorial-tests: .github#9

! Failed to restore: Cache service responded with 400
qualify-ci / tutorial-tests: .github#49

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / tutorial-tests: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache@v4, actions/checkout@v4, actions/download-artifact@v4, actions/setup-go@v5, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / lint: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0fDT0agAAAADC2ngjG3dlSLM7Bf2Jk2t2TEFYMzExMDAwMTExMDMxAEVkZ2U=
qualify-ci / lint: .github#7

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0fDT0agAAAADPYoWa3hrYT7TlABl8zPO+TEFYMzExMDAwMTE1MDE5AEVkZ2U=
qualify-ci / lint: .github#9

! Failed to restore: Cache service responded with 400
qualify-ci / lint: .github#52

! Failed to restore: Cache service responded with 400
qualify-ci / lint: .github#24

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / lint: .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* release-please--branches--master Release sase-org/sase#322 · 42992733019
Triggered via workflow_dispatch about 58 minutes ago

JOBS
✓ identity in 51s (ID 130429292693)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Assert source and version identity
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ build in 35s (ID 130429702498)
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
✓ qualify-prepare in 27s (ID 130429998624)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Download the sealed candidate build
  ✓ Bind the sealed candidate identity
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ exercise-legs (ubuntu-latest, wheel) in 1m4s (ID 130429998685)
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
✓ exercise-legs (macos-latest, sdist) in 1m52s (ID 130429998700)
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
✓ exercise-legs (macos-latest, wheel) in 1m55s (ID 130429998736)
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
✓ exercise-legs (ubuntu-latest, sdist) in 53s (ID 130429998828)
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
- stash (ID 130430001268)
✓ qualify-ci / prepare in 24s (ID 130430236751)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Validate qualification inputs
  ✓ Download the sealed candidate manifest
  ✓ Bind published identity from the sealed manifest
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
- qualify-ci / docs-build in 0s (ID 130430238633)
- qualify-ci / release-core-floor-smoke in 0s (ID 130430239945)
✓ qualify-ci / build-core / build-core in 7m24s (ID 130430445331)
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
✓ exercise in 24s (ID 130430922757)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Download the sealed build
  ✓ Download the leg evidence
  ✓ Merge the legs into one exercise observation
  - Stash the exercise observation on the draft release
  ✓ Upload the exercise observation artifact
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ qualify-ci / ace-page-group-isolation in 1m36s (ID 130433914911)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  ✓ Run ACE shared-page isolation lane
  ✓ Post Install visual dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
X qualify-ci / visual-test in 23m57s (ID 130433914913)
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
✓ qualify-ci / perf-floors in 9m28s (ID 130433914961)
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
* qualify-ci / test (3.12) (ID 130433915030)
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
✓ qualify-ci / tutorial-tests in 1m1s (ID 130433915035)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run tutorial tests
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ qualify-ci / lint in 6m14s (ID 130433915045)
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
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* qualify-ci / test (3.13) (ID 130433915166)
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
* qualify-ci / test (3.14) (ID 130433915280)
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
identity: .github#7

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
identity: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
build: .github#4

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0DTH0agAAAAD7rbAUNBT8RL9zAt1UenRYTVNQMzExMDAwMTA0MDI3AEVkZ2U=
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
exercise-legs (ubuntu-latest, wheel): .github#2

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
exercise-legs (ubuntu-latest, wheel): .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
exercise-legs (macos-latest, sdist): .github#2

- Due to capacity constraints, jobs targeting macOS arm64 runners may experience longer queue times.
exercise-legs (macos-latest, sdist): .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
exercise-legs (macos-latest, wheel): .github#2

- Due to capacity constraints, jobs targeting macOS arm64 runners may experience longer queue times.
exercise-legs (macos-latest, wheel): .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
exercise-legs (ubuntu-latest, sdist): .github#2

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
exercise-legs (ubuntu-latest, sdist): .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / prepare: .github#10

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / prepare: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / build-core / build-core: .github#5

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0BTP0agAAAACIQtJKm5FTQLUbV1bojc6rUEhMMzBFREdFMDQxOABFZGdl
qualify-ci / build-core / build-core: .github#7

! Failed to restore: Cache service responded with 400
qualify-ci / build-core / build-core: .github#25

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / build-core / build-core: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
exercise: .github#4

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
exercise: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / ace-page-group-isolation: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0aDP0agAAAAB0dJofL/zsSp+UTSSgEcPMUEhMMzBFREdFMDExNwBFZGdl
qualify-ci / ace-page-group-isolation: .github#9

! Failed to restore: Cache service responded with 400
qualify-ci / ace-page-group-isolation: .github#49

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / ace-page-group-isolation: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / visual-test: .github#2

X agents_final_rows_80x40: updated | changed pixels 11761/1019844 (1.153216%) | expected=tests/ace/tui/visual/snapshots/png/agents_final_rows_80x40.png
qualify-ci / visual-test: tests/ace/tui/visual/test_ace_png_snapshots_agents_final_rows.py#86

X agents_final_rows_60x40: updated | changed pixels 8667/769500 (1.126316%) | expected=tests/ace/tui/visual/snapshots/png/agents_final_rows_60x40.png
qualify-ci / visual-test: tests/ace/tui/visual/test_ace_png_snapshots_agents_final_rows.py#86

X Process completed with exit code 1.
qualify-ci / visual-test: .github#382

! Failed to restore: Cache service responded with 400
qualify-ci / visual-test: .github#49

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / visual-test: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / perf-floors: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0QDX0agAAAADc89K4ImAPR5uO4uh7cK+OQ0gxQUEyMDMwODE0MDM0AEVkZ2U=
qualify-ci / perf-floors: .github#9

! Failed to restore: Cache service responded with 400
qualify-ci / perf-floors: .github#49

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / perf-floors: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / tutorial-tests: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0RDP0agAAAACTIjNRdoBhQoq9lzCQEBnsTEFYRURHRTIwMTgARWRnZQ==
qualify-ci / tutorial-tests: .github#9

! Failed to restore: Cache service responded with 400
qualify-ci / tutorial-tests: .github#49

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / tutorial-tests: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache@v4, actions/checkout@v4, actions/download-artifact@v4, actions/setup-go@v5, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / lint: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0fDT0agAAAADC2ngjG3dlSLM7Bf2Jk2t2TEFYMzExMDAwMTExMDMxAEVkZ2U=
qualify-ci / lint: .github#7

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0fDT0agAAAADPYoWa3hrYT7TlABl8zPO+TEFYMzExMDAwMTE1MDE5AEVkZ2U=
qualify-ci / lint: .github#9

! Failed to restore: Cache service responded with 400
qualify-ci / lint: .github#52

! Failed to restore: Cache service responded with 400
qualify-ci / lint: .github#24

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / lint: .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* release-please--branches--master Release sase-org/sase#322 · 42992733019
Triggered via workflow_dispatch about 1 hour ago

JOBS
✓ identity in 51s (ID 130429292693)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Assert source and version identity
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ build in 35s (ID 130429702498)
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
✓ qualify-prepare in 27s (ID 130429998624)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Download the sealed candidate build
  ✓ Bind the sealed candidate identity
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ exercise-legs (ubuntu-latest, wheel) in 1m4s (ID 130429998685)
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
✓ exercise-legs (macos-latest, sdist) in 1m52s (ID 130429998700)
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
✓ exercise-legs (macos-latest, wheel) in 1m55s (ID 130429998736)
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
✓ exercise-legs (ubuntu-latest, sdist) in 53s (ID 130429998828)
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
- stash (ID 130430001268)
✓ qualify-ci / prepare in 24s (ID 130430236751)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Validate qualification inputs
  ✓ Download the sealed candidate manifest
  ✓ Bind published identity from the sealed manifest
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
- qualify-ci / docs-build in 0s (ID 130430238633)
- qualify-ci / release-core-floor-smoke in 0s (ID 130430239945)
✓ qualify-ci / build-core / build-core in 7m24s (ID 130430445331)
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
✓ exercise in 24s (ID 130430922757)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Download the sealed build
  ✓ Download the leg evidence
  ✓ Merge the legs into one exercise observation
  - Stash the exercise observation on the draft release
  ✓ Upload the exercise observation artifact
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ qualify-ci / ace-page-group-isolation in 1m36s (ID 130433914911)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  ✓ Run ACE shared-page isolation lane
  ✓ Post Install visual dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
X qualify-ci / visual-test in 23m57s (ID 130433914913)
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
✓ qualify-ci / perf-floors in 9m28s (ID 130433914961)
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
* qualify-ci / test (3.12) (ID 130433915030)
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
✓ qualify-ci / tutorial-tests in 1m1s (ID 130433915035)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run tutorial tests
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ qualify-ci / lint in 6m14s (ID 130433915045)
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
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* qualify-ci / test (3.13) (ID 130433915166)
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
* qualify-ci / test (3.14) (ID 130433915280)
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
identity: .github#7

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
identity: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
build: .github#4

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0DTH0agAAAAD7rbAUNBT8RL9zAt1UenRYTVNQMzExMDAwMTA0MDI3AEVkZ2U=
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
exercise-legs (ubuntu-latest, wheel): .github#2

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
exercise-legs (ubuntu-latest, wheel): .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
exercise-legs (macos-latest, sdist): .github#2

- Due to capacity constraints, jobs targeting macOS arm64 runners may experience longer queue times.
exercise-legs (macos-latest, sdist): .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
exercise-legs (macos-latest, wheel): .github#2

- Due to capacity constraints, jobs targeting macOS arm64 runners may experience longer queue times.
exercise-legs (macos-latest, wheel): .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
exercise-legs (ubuntu-latest, sdist): .github#2

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
exercise-legs (ubuntu-latest, sdist): .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / prepare: .github#10

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / prepare: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / build-core / build-core: .github#5

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0BTP0agAAAACIQtJKm5FTQLUbV1bojc6rUEhMMzBFREdFMDQxOABFZGdl
qualify-ci / build-core / build-core: .github#7

! Failed to restore: Cache service responded with 400
qualify-ci / build-core / build-core: .github#25

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / build-core / build-core: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
exercise: .github#4

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
exercise: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / ace-page-group-isolation: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0aDP0agAAAAB0dJofL/zsSp+UTSSgEcPMUEhMMzBFREdFMDExNwBFZGdl
qualify-ci / ace-page-group-isolation: .github#9

! Failed to restore: Cache service responded with 400
qualify-ci / ace-page-group-isolation: .github#49

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / ace-page-group-isolation: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / visual-test: .github#2

X agents_final_rows_80x40: updated | changed pixels 11761/1019844 (1.153216%) | expected=tests/ace/tui/visual/snapshots/png/agents_final_rows_80x40.png
qualify-ci / visual-test: tests/ace/tui/visual/test_ace_png_snapshots_agents_final_rows.py#86

X agents_final_rows_60x40: updated | changed pixels 8667/769500 (1.126316%) | expected=tests/ace/tui/visual/snapshots/png/agents_final_rows_60x40.png
qualify-ci / visual-test: tests/ace/tui/visual/test_ace_png_snapshots_agents_final_rows.py#86

X Process completed with exit code 1.
qualify-ci / visual-test: .github#382

! Failed to restore: Cache service responded with 400
qualify-ci / visual-test: .github#49

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / visual-test: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / perf-floors: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0QDX0agAAAADc89K4ImAPR5uO4uh7cK+OQ0gxQUEyMDMwODE0MDM0AEVkZ2U=
qualify-ci / perf-floors: .github#9

! Failed to restore: Cache service responded with 400
qualify-ci / perf-floors: .github#49

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / perf-floors: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / tutorial-tests: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0RDP0agAAAACTIjNRdoBhQoq9lzCQEBnsTEFYRURHRTIwMTgARWRnZQ==
qualify-ci / tutorial-tests: .github#9

! Failed to restore: Cache service responded with 400
qualify-ci / tutorial-tests: .github#49

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / tutorial-tests: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache@v4, actions/checkout@v4, actions/download-artifact@v4, actions/setup-go@v5, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / lint: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0fDT0agAAAADC2ngjG3dlSLM7Bf2Jk2t2TEFYMzExMDAwMTExMDMxAEVkZ2U=
qualify-ci / lint: .github#7

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0fDT0agAAAADPYoWa3hrYT7TlABl8zPO+TEFYMzExMDAwMTE1MDE5AEVkZ2U=
qualify-ci / lint: .github#9

! Failed to restore: Cache service responded with 400
qualify-ci / lint: .github#52

! Failed to restore: Cache service responded with 400
qualify-ci / lint: .github#24

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / lint: .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* release-please--branches--master Release sase-org/sase#322 · 42992733019
Triggered via workflow_dispatch about 1 hour ago

JOBS
✓ identity in 51s (ID 130429292693)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Assert source and version identity
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ build in 35s (ID 130429702498)
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
✓ qualify-prepare in 27s (ID 130429998624)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Download the sealed candidate build
  ✓ Bind the sealed candidate identity
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ exercise-legs (ubuntu-latest, wheel) in 1m4s (ID 130429998685)
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
✓ exercise-legs (macos-latest, sdist) in 1m52s (ID 130429998700)
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
✓ exercise-legs (macos-latest, wheel) in 1m55s (ID 130429998736)
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
✓ exercise-legs (ubuntu-latest, sdist) in 53s (ID 130429998828)
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
- stash (ID 130430001268)
✓ qualify-ci / prepare in 24s (ID 130430236751)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Validate qualification inputs
  ✓ Download the sealed candidate manifest
  ✓ Bind published identity from the sealed manifest
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
- qualify-ci / docs-build in 0s (ID 130430238633)
- qualify-ci / release-core-floor-smoke in 0s (ID 130430239945)
✓ qualify-ci / build-core / build-core in 7m24s (ID 130430445331)
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
✓ exercise in 24s (ID 130430922757)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Download the sealed build
  ✓ Download the leg evidence
  ✓ Merge the legs into one exercise observation
  - Stash the exercise observation on the draft release
  ✓ Upload the exercise observation artifact
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ qualify-ci / ace-page-group-isolation in 1m36s (ID 130433914911)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  ✓ Run ACE shared-page isolation lane
  ✓ Post Install visual dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
X qualify-ci / visual-test in 23m57s (ID 130433914913)
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
✓ qualify-ci / perf-floors in 9m28s (ID 130433914961)
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
* qualify-ci / test (3.12) (ID 130433915030)
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
✓ qualify-ci / tutorial-tests in 1m1s (ID 130433915035)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run tutorial tests
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ qualify-ci / lint in 6m14s (ID 130433915045)
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
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* qualify-ci / test (3.13) (ID 130433915166)
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
✓ qualify-ci / test (3.14) in 52m6s (ID 130433915280)
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
identity: .github#7

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
identity: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
build: .github#4

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0DTH0agAAAAD7rbAUNBT8RL9zAt1UenRYTVNQMzExMDAwMTA0MDI3AEVkZ2U=
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
exercise-legs (ubuntu-latest, wheel): .github#2

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
exercise-legs (ubuntu-latest, wheel): .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
exercise-legs (macos-latest, sdist): .github#2

- Due to capacity constraints, jobs targeting macOS arm64 runners may experience longer queue times.
exercise-legs (macos-latest, sdist): .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
exercise-legs (macos-latest, wheel): .github#2

- Due to capacity constraints, jobs targeting macOS arm64 runners may experience longer queue times.
exercise-legs (macos-latest, wheel): .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
exercise-legs (ubuntu-latest, sdist): .github#2

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
exercise-legs (ubuntu-latest, sdist): .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / prepare: .github#10

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / prepare: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / build-core / build-core: .github#5

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0BTP0agAAAACIQtJKm5FTQLUbV1bojc6rUEhMMzBFREdFMDQxOABFZGdl
qualify-ci / build-core / build-core: .github#7

! Failed to restore: Cache service responded with 400
qualify-ci / build-core / build-core: .github#25

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / build-core / build-core: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
exercise: .github#4

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
exercise: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / ace-page-group-isolation: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0aDP0agAAAAB0dJofL/zsSp+UTSSgEcPMUEhMMzBFREdFMDExNwBFZGdl
qualify-ci / ace-page-group-isolation: .github#9

! Failed to restore: Cache service responded with 400
qualify-ci / ace-page-group-isolation: .github#49

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / ace-page-group-isolation: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / visual-test: .github#2

X agents_final_rows_80x40: updated | changed pixels 11761/1019844 (1.153216%) | expected=tests/ace/tui/visual/snapshots/png/agents_final_rows_80x40.png
qualify-ci / visual-test: tests/ace/tui/visual/test_ace_png_snapshots_agents_final_rows.py#86

X agents_final_rows_60x40: updated | changed pixels 8667/769500 (1.126316%) | expected=tests/ace/tui/visual/snapshots/png/agents_final_rows_60x40.png
qualify-ci / visual-test: tests/ace/tui/visual/test_ace_png_snapshots_agents_final_rows.py#86

X Process completed with exit code 1.
qualify-ci / visual-test: .github#382

! Failed to restore: Cache service responded with 400
qualify-ci / visual-test: .github#49

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / visual-test: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / perf-floors: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0QDX0agAAAADc89K4ImAPR5uO4uh7cK+OQ0gxQUEyMDMwODE0MDM0AEVkZ2U=
qualify-ci / perf-floors: .github#9

! Failed to restore: Cache service responded with 400
qualify-ci / perf-floors: .github#49

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / perf-floors: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / tutorial-tests: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0RDP0agAAAACTIjNRdoBhQoq9lzCQEBnsTEFYRURHRTIwMTgARWRnZQ==
qualify-ci / tutorial-tests: .github#9

! Failed to restore: Cache service responded with 400
qualify-ci / tutorial-tests: .github#49

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / tutorial-tests: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache@v4, actions/checkout@v4, actions/download-artifact@v4, actions/setup-go@v5, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / lint: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0fDT0agAAAADC2ngjG3dlSLM7Bf2Jk2t2TEFYMzExMDAwMTExMDMxAEVkZ2U=
qualify-ci / lint: .github#7

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0fDT0agAAAADPYoWa3hrYT7TlABl8zPO+TEFYMzExMDAwMTE1MDE5AEVkZ2U=
qualify-ci / lint: .github#9

! Failed to restore: Cache service responded with 400
qualify-ci / lint: .github#52

! Failed to restore: Cache service responded with 400
qualify-ci / lint: .github#24

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / lint: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / test (3.14): .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0Pj/0agAAAABgBovvJclhQKNoVa2a9C8fUEhMMzBFREdFMDIxOQBFZGdl
qualify-ci / test (3.14): .github#9

! Failed to restore: Cache service responded with 400
qualify-ci / test (3.14): .github#49

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / test (3.14): .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* release-please--branches--master Release sase-org/sase#322 · 42992733019
Triggered via workflow_dispatch about 1 hour ago

JOBS
✓ identity in 51s (ID 130429292693)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Assert source and version identity
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ build in 35s (ID 130429702498)
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
✓ qualify-prepare in 27s (ID 130429998624)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Download the sealed candidate build
  ✓ Bind the sealed candidate identity
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ exercise-legs (ubuntu-latest, wheel) in 1m4s (ID 130429998685)
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
✓ exercise-legs (macos-latest, sdist) in 1m52s (ID 130429998700)
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
✓ exercise-legs (macos-latest, wheel) in 1m55s (ID 130429998736)
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
✓ exercise-legs (ubuntu-latest, sdist) in 53s (ID 130429998828)
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
- stash (ID 130430001268)
✓ qualify-ci / prepare in 24s (ID 130430236751)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Validate qualification inputs
  ✓ Download the sealed candidate manifest
  ✓ Bind published identity from the sealed manifest
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
- qualify-ci / docs-build in 0s (ID 130430238633)
- qualify-ci / release-core-floor-smoke in 0s (ID 130430239945)
✓ qualify-ci / build-core / build-core in 7m24s (ID 130430445331)
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
✓ exercise in 24s (ID 130430922757)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Download the sealed build
  ✓ Download the leg evidence
  ✓ Merge the legs into one exercise observation
  - Stash the exercise observation on the draft release
  ✓ Upload the exercise observation artifact
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ qualify-ci / ace-page-group-isolation in 1m36s (ID 130433914911)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  ✓ Run ACE shared-page isolation lane
  ✓ Post Install visual dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
X qualify-ci / visual-test in 23m57s (ID 130433914913)
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
✓ qualify-ci / perf-floors in 9m28s (ID 130433914961)
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
* qualify-ci / test (3.12) (ID 130433915030)
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
✓ qualify-ci / tutorial-tests in 1m1s (ID 130433915035)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run tutorial tests
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ qualify-ci / lint in 6m14s (ID 130433915045)
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
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* qualify-ci / test (3.13) (ID 130433915166)
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
✓ qualify-ci / test (3.14) in 52m6s (ID 130433915280)
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
identity: .github#7

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
identity: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
build: .github#4

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0DTH0agAAAAD7rbAUNBT8RL9zAt1UenRYTVNQMzExMDAwMTA0MDI3AEVkZ2U=
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
exercise-legs (ubuntu-latest, wheel): .github#2

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
exercise-legs (ubuntu-latest, wheel): .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
exercise-legs (macos-latest, sdist): .github#2

- Due to capacity constraints, jobs targeting macOS arm64 runners may experience longer queue times.
exercise-legs (macos-latest, sdist): .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
exercise-legs (macos-latest, wheel): .github#2

- Due to capacity constraints, jobs targeting macOS arm64 runners may experience longer queue times.
exercise-legs (macos-latest, wheel): .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
exercise-legs (ubuntu-latest, sdist): .github#2

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
exercise-legs (ubuntu-latest, sdist): .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / prepare: .github#10

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / prepare: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / build-core / build-core: .github#5

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0BTP0agAAAACIQtJKm5FTQLUbV1bojc6rUEhMMzBFREdFMDQxOABFZGdl
qualify-ci / build-core / build-core: .github#7

! Failed to restore: Cache service responded with 400
qualify-ci / build-core / build-core: .github#25

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / build-core / build-core: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
exercise: .github#4

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
exercise: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / ace-page-group-isolation: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0aDP0agAAAAB0dJofL/zsSp+UTSSgEcPMUEhMMzBFREdFMDExNwBFZGdl
qualify-ci / ace-page-group-isolation: .github#9

! Failed to restore: Cache service responded with 400
qualify-ci / ace-page-group-isolation: .github#49

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / ace-page-group-isolation: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / visual-test: .github#2

X agents_final_rows_80x40: updated | changed pixels 11761/1019844 (1.153216%) | expected=tests/ace/tui/visual/snapshots/png/agents_final_rows_80x40.png
qualify-ci / visual-test: tests/ace/tui/visual/test_ace_png_snapshots_agents_final_rows.py#86

X agents_final_rows_60x40: updated | changed pixels 8667/769500 (1.126316%) | expected=tests/ace/tui/visual/snapshots/png/agents_final_rows_60x40.png
qualify-ci / visual-test: tests/ace/tui/visual/test_ace_png_snapshots_agents_final_rows.py#86

X Process completed with exit code 1.
qualify-ci / visual-test: .github#382

! Failed to restore: Cache service responded with 400
qualify-ci / visual-test: .github#49

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / visual-test: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / perf-floors: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0QDX0agAAAADc89K4ImAPR5uO4uh7cK+OQ0gxQUEyMDMwODE0MDM0AEVkZ2U=
qualify-ci / perf-floors: .github#9

! Failed to restore: Cache service responded with 400
qualify-ci / perf-floors: .github#49

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / perf-floors: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / tutorial-tests: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0RDP0agAAAACTIjNRdoBhQoq9lzCQEBnsTEFYRURHRTIwMTgARWRnZQ==
qualify-ci / tutorial-tests: .github#9

! Failed to restore: Cache service responded with 400
qualify-ci / tutorial-tests: .github#49

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / tutorial-tests: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache@v4, actions/checkout@v4, actions/download-artifact@v4, actions/setup-go@v5, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / lint: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0fDT0agAAAADC2ngjG3dlSLM7Bf2Jk2t2TEFYMzExMDAwMTExMDMxAEVkZ2U=
qualify-ci / lint: .github#7

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0fDT0agAAAADPYoWa3hrYT7TlABl8zPO+TEFYMzExMDAwMTE1MDE5AEVkZ2U=
qualify-ci / lint: .github#9

! Failed to restore: Cache service responded with 400
qualify-ci / lint: .github#52

! Failed to restore: Cache service responded with 400
qualify-ci / lint: .github#24

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / lint: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / test (3.14): .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0Pj/0agAAAABgBovvJclhQKNoVa2a9C8fUEhMMzBFREdFMDIxOQBFZGdl
qualify-ci / test (3.14): .github#9

! Failed to restore: Cache service responded with 400
qualify-ci / test (3.14): .github#49

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / test (3.14): .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* release-please--branches--master Release sase-org/sase#322 · 42992733019
Triggered via workflow_dispatch about 1 hour ago

JOBS
✓ identity in 51s (ID 130429292693)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Assert source and version identity
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ build in 35s (ID 130429702498)
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
✓ qualify-prepare in 27s (ID 130429998624)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Download the sealed candidate build
  ✓ Bind the sealed candidate identity
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ exercise-legs (ubuntu-latest, wheel) in 1m4s (ID 130429998685)
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
✓ exercise-legs (macos-latest, sdist) in 1m52s (ID 130429998700)
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
✓ exercise-legs (macos-latest, wheel) in 1m55s (ID 130429998736)
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
✓ exercise-legs (ubuntu-latest, sdist) in 53s (ID 130429998828)
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
- stash (ID 130430001268)
✓ qualify-ci / prepare in 24s (ID 130430236751)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Validate qualification inputs
  ✓ Download the sealed candidate manifest
  ✓ Bind published identity from the sealed manifest
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
- qualify-ci / docs-build in 0s (ID 130430238633)
- qualify-ci / release-core-floor-smoke in 0s (ID 130430239945)
✓ qualify-ci / build-core / build-core in 7m24s (ID 130430445331)
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
✓ exercise in 24s (ID 130430922757)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Download the sealed build
  ✓ Download the leg evidence
  ✓ Merge the legs into one exercise observation
  - Stash the exercise observation on the draft release
  ✓ Upload the exercise observation artifact
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ qualify-ci / ace-page-group-isolation in 1m36s (ID 130433914911)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  ✓ Run ACE shared-page isolation lane
  ✓ Post Install visual dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
X qualify-ci / visual-test in 23m57s (ID 130433914913)
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
✓ qualify-ci / perf-floors in 9m28s (ID 130433914961)
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
* qualify-ci / test (3.12) (ID 130433915030)
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
✓ qualify-ci / tutorial-tests in 1m1s (ID 130433915035)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run tutorial tests
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ qualify-ci / lint in 6m14s (ID 130433915045)
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
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* qualify-ci / test (3.13) (ID 130433915166)
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
✓ qualify-ci / test (3.14) in 52m6s (ID 130433915280)
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
identity: .github#7

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
identity: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
build: .github#4

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0DTH0agAAAAD7rbAUNBT8RL9zAt1UenRYTVNQMzExMDAwMTA0MDI3AEVkZ2U=
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
exercise-legs (ubuntu-latest, wheel): .github#2

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
exercise-legs (ubuntu-latest, wheel): .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
exercise-legs (macos-latest, sdist): .github#2

- Due to capacity constraints, jobs targeting macOS arm64 runners may experience longer queue times.
exercise-legs (macos-latest, sdist): .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
exercise-legs (macos-latest, wheel): .github#2

- Due to capacity constraints, jobs targeting macOS arm64 runners may experience longer queue times.
exercise-legs (macos-latest, wheel): .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
exercise-legs (ubuntu-latest, sdist): .github#2

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
exercise-legs (ubuntu-latest, sdist): .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / prepare: .github#10

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / prepare: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / build-core / build-core: .github#5

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0BTP0agAAAACIQtJKm5FTQLUbV1bojc6rUEhMMzBFREdFMDQxOABFZGdl
qualify-ci / build-core / build-core: .github#7

! Failed to restore: Cache service responded with 400
qualify-ci / build-core / build-core: .github#25

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / build-core / build-core: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
exercise: .github#4

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
exercise: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / ace-page-group-isolation: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0aDP0agAAAAB0dJofL/zsSp+UTSSgEcPMUEhMMzBFREdFMDExNwBFZGdl
qualify-ci / ace-page-group-isolation: .github#9

! Failed to restore: Cache service responded with 400
qualify-ci / ace-page-group-isolation: .github#49

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / ace-page-group-isolation: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / visual-test: .github#2

X agents_final_rows_80x40: updated | changed pixels 11761/1019844 (1.153216%) | expected=tests/ace/tui/visual/snapshots/png/agents_final_rows_80x40.png
qualify-ci / visual-test: tests/ace/tui/visual/test_ace_png_snapshots_agents_final_rows.py#86

X agents_final_rows_60x40: updated | changed pixels 8667/769500 (1.126316%) | expected=tests/ace/tui/visual/snapshots/png/agents_final_rows_60x40.png
qualify-ci / visual-test: tests/ace/tui/visual/test_ace_png_snapshots_agents_final_rows.py#86

X Process completed with exit code 1.
qualify-ci / visual-test: .github#382

! Failed to restore: Cache service responded with 400
qualify-ci / visual-test: .github#49

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / visual-test: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / perf-floors: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0QDX0agAAAADc89K4ImAPR5uO4uh7cK+OQ0gxQUEyMDMwODE0MDM0AEVkZ2U=
qualify-ci / perf-floors: .github#9

! Failed to restore: Cache service responded with 400
qualify-ci / perf-floors: .github#49

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / perf-floors: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / tutorial-tests: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0RDP0agAAAACTIjNRdoBhQoq9lzCQEBnsTEFYRURHRTIwMTgARWRnZQ==
qualify-ci / tutorial-tests: .github#9

! Failed to restore: Cache service responded with 400
qualify-ci / tutorial-tests: .github#49

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / tutorial-tests: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache@v4, actions/checkout@v4, actions/download-artifact@v4, actions/setup-go@v5, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / lint: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0fDT0agAAAADC2ngjG3dlSLM7Bf2Jk2t2TEFYMzExMDAwMTExMDMxAEVkZ2U=
qualify-ci / lint: .github#7

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0fDT0agAAAADPYoWa3hrYT7TlABl8zPO+TEFYMzExMDAwMTE1MDE5AEVkZ2U=
qualify-ci / lint: .github#9

! Failed to restore: Cache service responded with 400
qualify-ci / lint: .github#52

! Failed to restore: Cache service responded with 400
qualify-ci / lint: .github#24

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / lint: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / test (3.14): .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0Pj/0agAAAABgBovvJclhQKNoVa2a9C8fUEhMMzBFREdFMDIxOQBFZGdl
qualify-ci / test (3.14): .github#9

! Failed to restore: Cache service responded with 400
qualify-ci / test (3.14): .github#49

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / test (3.14): .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* release-please--branches--master Release sase-org/sase#322 · 42992733019
Triggered via workflow_dispatch about 1 hour ago

JOBS
✓ identity in 51s (ID 130429292693)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Assert source and version identity
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ build in 35s (ID 130429702498)
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
✓ qualify-prepare in 27s (ID 130429998624)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Download the sealed candidate build
  ✓ Bind the sealed candidate identity
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ exercise-legs (ubuntu-latest, wheel) in 1m4s (ID 130429998685)
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
✓ exercise-legs (macos-latest, sdist) in 1m52s (ID 130429998700)
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
✓ exercise-legs (macos-latest, wheel) in 1m55s (ID 130429998736)
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
✓ exercise-legs (ubuntu-latest, sdist) in 53s (ID 130429998828)
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
- stash (ID 130430001268)
✓ qualify-ci / prepare in 24s (ID 130430236751)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Validate qualification inputs
  ✓ Download the sealed candidate manifest
  ✓ Bind published identity from the sealed manifest
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
- qualify-ci / docs-build in 0s (ID 130430238633)
- qualify-ci / release-core-floor-smoke in 0s (ID 130430239945)
✓ qualify-ci / build-core / build-core in 7m24s (ID 130430445331)
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
✓ exercise in 24s (ID 130430922757)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Download the sealed build
  ✓ Download the leg evidence
  ✓ Merge the legs into one exercise observation
  - Stash the exercise observation on the draft release
  ✓ Upload the exercise observation artifact
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ qualify-ci / ace-page-group-isolation in 1m36s (ID 130433914911)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  ✓ Run ACE shared-page isolation lane
  ✓ Post Install visual dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
X qualify-ci / visual-test in 23m57s (ID 130433914913)
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
✓ qualify-ci / perf-floors in 9m28s (ID 130433914961)
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
* qualify-ci / test (3.12) (ID 130433915030)
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
✓ qualify-ci / tutorial-tests in 1m1s (ID 130433915035)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run tutorial tests
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ qualify-ci / lint in 6m14s (ID 130433915045)
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
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* qualify-ci / test (3.13) (ID 130433915166)
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
✓ qualify-ci / test (3.14) in 52m6s (ID 130433915280)
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
identity: .github#7

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
identity: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
build: .github#4

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0DTH0agAAAAD7rbAUNBT8RL9zAt1UenRYTVNQMzExMDAwMTA0MDI3AEVkZ2U=
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
exercise-legs (ubuntu-latest, wheel): .github#2

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
exercise-legs (ubuntu-latest, wheel): .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
exercise-legs (macos-latest, sdist): .github#2

- Due to capacity constraints, jobs targeting macOS arm64 runners may experience longer queue times.
exercise-legs (macos-latest, sdist): .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
exercise-legs (macos-latest, wheel): .github#2

- Due to capacity constraints, jobs targeting macOS arm64 runners may experience longer queue times.
exercise-legs (macos-latest, wheel): .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
exercise-legs (ubuntu-latest, sdist): .github#2

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
exercise-legs (ubuntu-latest, sdist): .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / prepare: .github#10

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / prepare: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / build-core / build-core: .github#5

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0BTP0agAAAACIQtJKm5FTQLUbV1bojc6rUEhMMzBFREdFMDQxOABFZGdl
qualify-ci / build-core / build-core: .github#7

! Failed to restore: Cache service responded with 400
qualify-ci / build-core / build-core: .github#25

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / build-core / build-core: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
exercise: .github#4

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
exercise: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / ace-page-group-isolation: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0aDP0agAAAAB0dJofL/zsSp+UTSSgEcPMUEhMMzBFREdFMDExNwBFZGdl
qualify-ci / ace-page-group-isolation: .github#9

! Failed to restore: Cache service responded with 400
qualify-ci / ace-page-group-isolation: .github#49

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / ace-page-group-isolation: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / visual-test: .github#2

X agents_final_rows_80x40: updated | changed pixels 11761/1019844 (1.153216%) | expected=tests/ace/tui/visual/snapshots/png/agents_final_rows_80x40.png
qualify-ci / visual-test: tests/ace/tui/visual/test_ace_png_snapshots_agents_final_rows.py#86

X agents_final_rows_60x40: updated | changed pixels 8667/769500 (1.126316%) | expected=tests/ace/tui/visual/snapshots/png/agents_final_rows_60x40.png
qualify-ci / visual-test: tests/ace/tui/visual/test_ace_png_snapshots_agents_final_rows.py#86

X Process completed with exit code 1.
qualify-ci / visual-test: .github#382

! Failed to restore: Cache service responded with 400
qualify-ci / visual-test: .github#49

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / visual-test: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / perf-floors: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0QDX0agAAAADc89K4ImAPR5uO4uh7cK+OQ0gxQUEyMDMwODE0MDM0AEVkZ2U=
qualify-ci / perf-floors: .github#9

! Failed to restore: Cache service responded with 400
qualify-ci / perf-floors: .github#49

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / perf-floors: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / tutorial-tests: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0RDP0agAAAACTIjNRdoBhQoq9lzCQEBnsTEFYRURHRTIwMTgARWRnZQ==
qualify-ci / tutorial-tests: .github#9

! Failed to restore: Cache service responded with 400
qualify-ci / tutorial-tests: .github#49

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / tutorial-tests: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache@v4, actions/checkout@v4, actions/download-artifact@v4, actions/setup-go@v5, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / lint: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0fDT0agAAAADC2ngjG3dlSLM7Bf2Jk2t2TEFYMzExMDAwMTExMDMxAEVkZ2U=
qualify-ci / lint: .github#7

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0fDT0agAAAADPYoWa3hrYT7TlABl8zPO+TEFYMzExMDAwMTE1MDE5AEVkZ2U=
qualify-ci / lint: .github#9

! Failed to restore: Cache service responded with 400
qualify-ci / lint: .github#52

! Failed to restore: Cache service responded with 400
qualify-ci / lint: .github#24

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / lint: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / test (3.14): .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0Pj/0agAAAABgBovvJclhQKNoVa2a9C8fUEhMMzBFREdFMDIxOQBFZGdl
qualify-ci / test (3.14): .github#9

! Failed to restore: Cache service responded with 400
qualify-ci / test (3.14): .github#49

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / test (3.14): .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* release-please--branches--master Release sase-org/sase#322 · 42992733019
Triggered via workflow_dispatch about 1 hour ago

JOBS
✓ identity in 51s (ID 130429292693)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Assert source and version identity
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ build in 35s (ID 130429702498)
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
✓ qualify-prepare in 27s (ID 130429998624)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Download the sealed candidate build
  ✓ Bind the sealed candidate identity
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ exercise-legs (ubuntu-latest, wheel) in 1m4s (ID 130429998685)
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
✓ exercise-legs (macos-latest, sdist) in 1m52s (ID 130429998700)
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
✓ exercise-legs (macos-latest, wheel) in 1m55s (ID 130429998736)
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
✓ exercise-legs (ubuntu-latest, sdist) in 53s (ID 130429998828)
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
- stash (ID 130430001268)
✓ qualify-ci / prepare in 24s (ID 130430236751)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Validate qualification inputs
  ✓ Download the sealed candidate manifest
  ✓ Bind published identity from the sealed manifest
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
- qualify-ci / docs-build in 0s (ID 130430238633)
- qualify-ci / release-core-floor-smoke in 0s (ID 130430239945)
✓ qualify-ci / build-core / build-core in 7m24s (ID 130430445331)
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
✓ exercise in 24s (ID 130430922757)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Download the sealed build
  ✓ Download the leg evidence
  ✓ Merge the legs into one exercise observation
  - Stash the exercise observation on the draft release
  ✓ Upload the exercise observation artifact
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ qualify-ci / ace-page-group-isolation in 1m36s (ID 130433914911)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  ✓ Run ACE shared-page isolation lane
  ✓ Post Install visual dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
X qualify-ci / visual-test in 23m57s (ID 130433914913)
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
✓ qualify-ci / perf-floors in 9m28s (ID 130433914961)
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
* qualify-ci / test (3.12) (ID 130433915030)
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
✓ qualify-ci / tutorial-tests in 1m1s (ID 130433915035)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run tutorial tests
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ qualify-ci / lint in 6m14s (ID 130433915045)
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
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* qualify-ci / test (3.13) (ID 130433915166)
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
✓ qualify-ci / test (3.14) in 52m6s (ID 130433915280)
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
identity: .github#7

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
identity: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
build: .github#4

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0DTH0agAAAAD7rbAUNBT8RL9zAt1UenRYTVNQMzExMDAwMTA0MDI3AEVkZ2U=
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
exercise-legs (ubuntu-latest, wheel): .github#2

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
exercise-legs (ubuntu-latest, wheel): .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
exercise-legs (macos-latest, sdist): .github#2

- Due to capacity constraints, jobs targeting macOS arm64 runners may experience longer queue times.
exercise-legs (macos-latest, sdist): .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
exercise-legs (macos-latest, wheel): .github#2

- Due to capacity constraints, jobs targeting macOS arm64 runners may experience longer queue times.
exercise-legs (macos-latest, wheel): .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
exercise-legs (ubuntu-latest, sdist): .github#2

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
exercise-legs (ubuntu-latest, sdist): .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / prepare: .github#10

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / prepare: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / build-core / build-core: .github#5

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0BTP0agAAAACIQtJKm5FTQLUbV1bojc6rUEhMMzBFREdFMDQxOABFZGdl
qualify-ci / build-core / build-core: .github#7

! Failed to restore: Cache service responded with 400
qualify-ci / build-core / build-core: .github#25

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / build-core / build-core: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
exercise: .github#4

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
exercise: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / ace-page-group-isolation: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0aDP0agAAAAB0dJofL/zsSp+UTSSgEcPMUEhMMzBFREdFMDExNwBFZGdl
qualify-ci / ace-page-group-isolation: .github#9

! Failed to restore: Cache service responded with 400
qualify-ci / ace-page-group-isolation: .github#49

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / ace-page-group-isolation: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / visual-test: .github#2

X agents_final_rows_80x40: updated | changed pixels 11761/1019844 (1.153216%) | expected=tests/ace/tui/visual/snapshots/png/agents_final_rows_80x40.png
qualify-ci / visual-test: tests/ace/tui/visual/test_ace_png_snapshots_agents_final_rows.py#86

X agents_final_rows_60x40: updated | changed pixels 8667/769500 (1.126316%) | expected=tests/ace/tui/visual/snapshots/png/agents_final_rows_60x40.png
qualify-ci / visual-test: tests/ace/tui/visual/test_ace_png_snapshots_agents_final_rows.py#86

X Process completed with exit code 1.
qualify-ci / visual-test: .github#382

! Failed to restore: Cache service responded with 400
qualify-ci / visual-test: .github#49

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / visual-test: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / perf-floors: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0QDX0agAAAADc89K4ImAPR5uO4uh7cK+OQ0gxQUEyMDMwODE0MDM0AEVkZ2U=
qualify-ci / perf-floors: .github#9

! Failed to restore: Cache service responded with 400
qualify-ci / perf-floors: .github#49

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / perf-floors: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / tutorial-tests: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0RDP0agAAAACTIjNRdoBhQoq9lzCQEBnsTEFYRURHRTIwMTgARWRnZQ==
qualify-ci / tutorial-tests: .github#9

! Failed to restore: Cache service responded with 400
qualify-ci / tutorial-tests: .github#49

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / tutorial-tests: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache@v4, actions/checkout@v4, actions/download-artifact@v4, actions/setup-go@v5, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / lint: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0fDT0agAAAADC2ngjG3dlSLM7Bf2Jk2t2TEFYMzExMDAwMTExMDMxAEVkZ2U=
qualify-ci / lint: .github#7

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0fDT0agAAAADPYoWa3hrYT7TlABl8zPO+TEFYMzExMDAwMTE1MDE5AEVkZ2U=
qualify-ci / lint: .github#9

! Failed to restore: Cache service responded with 400
qualify-ci / lint: .github#52

! Failed to restore: Cache service responded with 400
qualify-ci / lint: .github#24

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / lint: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / test (3.14): .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0Pj/0agAAAABgBovvJclhQKNoVa2a9C8fUEhMMzBFREdFMDIxOQBFZGdl
qualify-ci / test (3.14): .github#9

! Failed to restore: Cache service responded with 400
qualify-ci / test (3.14): .github#49

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / test (3.14): .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* release-please--branches--master Release sase-org/sase#322 · 42992733019
Triggered via workflow_dispatch about 1 hour ago

JOBS
✓ identity in 51s (ID 130429292693)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Assert source and version identity
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ build in 35s (ID 130429702498)
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
✓ qualify-prepare in 27s (ID 130429998624)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Download the sealed candidate build
  ✓ Bind the sealed candidate identity
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ exercise-legs (ubuntu-latest, wheel) in 1m4s (ID 130429998685)
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
✓ exercise-legs (macos-latest, sdist) in 1m52s (ID 130429998700)
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
✓ exercise-legs (macos-latest, wheel) in 1m55s (ID 130429998736)
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
✓ exercise-legs (ubuntu-latest, sdist) in 53s (ID 130429998828)
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
- stash (ID 130430001268)
✓ qualify-ci / prepare in 24s (ID 130430236751)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Validate qualification inputs
  ✓ Download the sealed candidate manifest
  ✓ Bind published identity from the sealed manifest
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
- qualify-ci / docs-build in 0s (ID 130430238633)
- qualify-ci / release-core-floor-smoke in 0s (ID 130430239945)
✓ qualify-ci / build-core / build-core in 7m24s (ID 130430445331)
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
✓ exercise in 24s (ID 130430922757)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Download the sealed build
  ✓ Download the leg evidence
  ✓ Merge the legs into one exercise observation
  - Stash the exercise observation on the draft release
  ✓ Upload the exercise observation artifact
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ qualify-ci / ace-page-group-isolation in 1m36s (ID 130433914911)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  ✓ Run ACE shared-page isolation lane
  ✓ Post Install visual dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
X qualify-ci / visual-test in 23m57s (ID 130433914913)
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
✓ qualify-ci / perf-floors in 9m28s (ID 130433914961)
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
* qualify-ci / test (3.12) (ID 130433915030)
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
✓ qualify-ci / tutorial-tests in 1m1s (ID 130433915035)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run tutorial tests
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ qualify-ci / lint in 6m14s (ID 130433915045)
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
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* qualify-ci / test (3.13) (ID 130433915166)
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
✓ qualify-ci / test (3.14) in 52m6s (ID 130433915280)
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
identity: .github#7

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
identity: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
build: .github#4

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0DTH0agAAAAD7rbAUNBT8RL9zAt1UenRYTVNQMzExMDAwMTA0MDI3AEVkZ2U=
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
exercise-legs (ubuntu-latest, wheel): .github#2

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
exercise-legs (ubuntu-latest, wheel): .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
exercise-legs (macos-latest, sdist): .github#2

- Due to capacity constraints, jobs targeting macOS arm64 runners may experience longer queue times.
exercise-legs (macos-latest, sdist): .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
exercise-legs (macos-latest, wheel): .github#2

- Due to capacity constraints, jobs targeting macOS arm64 runners may experience longer queue times.
exercise-legs (macos-latest, wheel): .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
exercise-legs (ubuntu-latest, sdist): .github#2

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
exercise-legs (ubuntu-latest, sdist): .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / prepare: .github#10

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / prepare: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / build-core / build-core: .github#5

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0BTP0agAAAACIQtJKm5FTQLUbV1bojc6rUEhMMzBFREdFMDQxOABFZGdl
qualify-ci / build-core / build-core: .github#7

! Failed to restore: Cache service responded with 400
qualify-ci / build-core / build-core: .github#25

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / build-core / build-core: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
exercise: .github#4

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
exercise: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / ace-page-group-isolation: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0aDP0agAAAAB0dJofL/zsSp+UTSSgEcPMUEhMMzBFREdFMDExNwBFZGdl
qualify-ci / ace-page-group-isolation: .github#9

! Failed to restore: Cache service responded with 400
qualify-ci / ace-page-group-isolation: .github#49

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / ace-page-group-isolation: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / visual-test: .github#2

X agents_final_rows_80x40: updated | changed pixels 11761/1019844 (1.153216%) | expected=tests/ace/tui/visual/snapshots/png/agents_final_rows_80x40.png
qualify-ci / visual-test: tests/ace/tui/visual/test_ace_png_snapshots_agents_final_rows.py#86

X agents_final_rows_60x40: updated | changed pixels 8667/769500 (1.126316%) | expected=tests/ace/tui/visual/snapshots/png/agents_final_rows_60x40.png
qualify-ci / visual-test: tests/ace/tui/visual/test_ace_png_snapshots_agents_final_rows.py#86

X Process completed with exit code 1.
qualify-ci / visual-test: .github#382

! Failed to restore: Cache service responded with 400
qualify-ci / visual-test: .github#49

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / visual-test: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / perf-floors: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0QDX0agAAAADc89K4ImAPR5uO4uh7cK+OQ0gxQUEyMDMwODE0MDM0AEVkZ2U=
qualify-ci / perf-floors: .github#9

! Failed to restore: Cache service responded with 400
qualify-ci / perf-floors: .github#49

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / perf-floors: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / tutorial-tests: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0RDP0agAAAACTIjNRdoBhQoq9lzCQEBnsTEFYRURHRTIwMTgARWRnZQ==
qualify-ci / tutorial-tests: .github#9

! Failed to restore: Cache service responded with 400
qualify-ci / tutorial-tests: .github#49

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / tutorial-tests: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache@v4, actions/checkout@v4, actions/download-artifact@v4, actions/setup-go@v5, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / lint: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0fDT0agAAAADC2ngjG3dlSLM7Bf2Jk2t2TEFYMzExMDAwMTExMDMxAEVkZ2U=
qualify-ci / lint: .github#7

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0fDT0agAAAADPYoWa3hrYT7TlABl8zPO+TEFYMzExMDAwMTE1MDE5AEVkZ2U=
qualify-ci / lint: .github#9

! Failed to restore: Cache service responded with 400
qualify-ci / lint: .github#52

! Failed to restore: Cache service responded with 400
qualify-ci / lint: .github#24

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / lint: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / test (3.14): .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0Pj/0agAAAABgBovvJclhQKNoVa2a9C8fUEhMMzBFREdFMDIxOQBFZGdl
qualify-ci / test (3.14): .github#9

! Failed to restore: Cache service responded with 400
qualify-ci / test (3.14): .github#49

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / test (3.14): .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* release-please--branches--master Release sase-org/sase#322 · 42992733019
Triggered via workflow_dispatch about 1 hour ago

JOBS
✓ identity in 51s (ID 130429292693)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Assert source and version identity
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ build in 35s (ID 130429702498)
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
✓ qualify-prepare in 27s (ID 130429998624)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Download the sealed candidate build
  ✓ Bind the sealed candidate identity
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ exercise-legs (ubuntu-latest, wheel) in 1m4s (ID 130429998685)
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
✓ exercise-legs (macos-latest, sdist) in 1m52s (ID 130429998700)
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
✓ exercise-legs (macos-latest, wheel) in 1m55s (ID 130429998736)
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
✓ exercise-legs (ubuntu-latest, sdist) in 53s (ID 130429998828)
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
- stash (ID 130430001268)
✓ qualify-ci / prepare in 24s (ID 130430236751)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Validate qualification inputs
  ✓ Download the sealed candidate manifest
  ✓ Bind published identity from the sealed manifest
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
- qualify-ci / docs-build in 0s (ID 130430238633)
- qualify-ci / release-core-floor-smoke in 0s (ID 130430239945)
✓ qualify-ci / build-core / build-core in 7m24s (ID 130430445331)
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
✓ exercise in 24s (ID 130430922757)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Download the sealed build
  ✓ Download the leg evidence
  ✓ Merge the legs into one exercise observation
  - Stash the exercise observation on the draft release
  ✓ Upload the exercise observation artifact
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ qualify-ci / ace-page-group-isolation in 1m36s (ID 130433914911)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  ✓ Run ACE shared-page isolation lane
  ✓ Post Install visual dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
X qualify-ci / visual-test in 23m57s (ID 130433914913)
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
✓ qualify-ci / perf-floors in 9m28s (ID 130433914961)
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
* qualify-ci / test (3.12) (ID 130433915030)
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
✓ qualify-ci / tutorial-tests in 1m1s (ID 130433915035)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run tutorial tests
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ qualify-ci / lint in 6m14s (ID 130433915045)
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
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* qualify-ci / test (3.13) (ID 130433915166)
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
✓ qualify-ci / test (3.14) in 52m6s (ID 130433915280)
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
identity: .github#7

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
identity: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
build: .github#4

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0DTH0agAAAAD7rbAUNBT8RL9zAt1UenRYTVNQMzExMDAwMTA0MDI3AEVkZ2U=
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
exercise-legs (ubuntu-latest, wheel): .github#2

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
exercise-legs (ubuntu-latest, wheel): .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
exercise-legs (macos-latest, sdist): .github#2

- Due to capacity constraints, jobs targeting macOS arm64 runners may experience longer queue times.
exercise-legs (macos-latest, sdist): .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
exercise-legs (macos-latest, wheel): .github#2

- Due to capacity constraints, jobs targeting macOS arm64 runners may experience longer queue times.
exercise-legs (macos-latest, wheel): .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
exercise-legs (ubuntu-latest, sdist): .github#2

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
exercise-legs (ubuntu-latest, sdist): .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / prepare: .github#10

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / prepare: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / build-core / build-core: .github#5

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0BTP0agAAAACIQtJKm5FTQLUbV1bojc6rUEhMMzBFREdFMDQxOABFZGdl
qualify-ci / build-core / build-core: .github#7

! Failed to restore: Cache service responded with 400
qualify-ci / build-core / build-core: .github#25

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / build-core / build-core: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
exercise: .github#4

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
exercise: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / ace-page-group-isolation: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0aDP0agAAAAB0dJofL/zsSp+UTSSgEcPMUEhMMzBFREdFMDExNwBFZGdl
qualify-ci / ace-page-group-isolation: .github#9

! Failed to restore: Cache service responded with 400
qualify-ci / ace-page-group-isolation: .github#49

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / ace-page-group-isolation: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / visual-test: .github#2

X agents_final_rows_80x40: updated | changed pixels 11761/1019844 (1.153216%) | expected=tests/ace/tui/visual/snapshots/png/agents_final_rows_80x40.png
qualify-ci / visual-test: tests/ace/tui/visual/test_ace_png_snapshots_agents_final_rows.py#86

X agents_final_rows_60x40: updated | changed pixels 8667/769500 (1.126316%) | expected=tests/ace/tui/visual/snapshots/png/agents_final_rows_60x40.png
qualify-ci / visual-test: tests/ace/tui/visual/test_ace_png_snapshots_agents_final_rows.py#86

X Process completed with exit code 1.
qualify-ci / visual-test: .github#382

! Failed to restore: Cache service responded with 400
qualify-ci / visual-test: .github#49

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / visual-test: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / perf-floors: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0QDX0agAAAADc89K4ImAPR5uO4uh7cK+OQ0gxQUEyMDMwODE0MDM0AEVkZ2U=
qualify-ci / perf-floors: .github#9

! Failed to restore: Cache service responded with 400
qualify-ci / perf-floors: .github#49

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / perf-floors: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / tutorial-tests: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0RDP0agAAAACTIjNRdoBhQoq9lzCQEBnsTEFYRURHRTIwMTgARWRnZQ==
qualify-ci / tutorial-tests: .github#9

! Failed to restore: Cache service responded with 400
qualify-ci / tutorial-tests: .github#49

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / tutorial-tests: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache@v4, actions/checkout@v4, actions/download-artifact@v4, actions/setup-go@v5, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / lint: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0fDT0agAAAADC2ngjG3dlSLM7Bf2Jk2t2TEFYMzExMDAwMTExMDMxAEVkZ2U=
qualify-ci / lint: .github#7

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0fDT0agAAAADPYoWa3hrYT7TlABl8zPO+TEFYMzExMDAwMTE1MDE5AEVkZ2U=
qualify-ci / lint: .github#9

! Failed to restore: Cache service responded with 400
qualify-ci / lint: .github#52

! Failed to restore: Cache service responded with 400
qualify-ci / lint: .github#24

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / lint: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / test (3.14): .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0Pj/0agAAAABgBovvJclhQKNoVa2a9C8fUEhMMzBFREdFMDIxOQBFZGdl
qualify-ci / test (3.14): .github#9

! Failed to restore: Cache service responded with 400
qualify-ci / test (3.14): .github#49

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / test (3.14): .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* release-please--branches--master Release sase-org/sase#322 · 42992733019
Triggered via workflow_dispatch about 1 hour ago

JOBS
✓ identity in 51s (ID 130429292693)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Assert source and version identity
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ build in 35s (ID 130429702498)
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
✓ qualify-prepare in 27s (ID 130429998624)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Download the sealed candidate build
  ✓ Bind the sealed candidate identity
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ exercise-legs (ubuntu-latest, wheel) in 1m4s (ID 130429998685)
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
✓ exercise-legs (macos-latest, sdist) in 1m52s (ID 130429998700)
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
✓ exercise-legs (macos-latest, wheel) in 1m55s (ID 130429998736)
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
✓ exercise-legs (ubuntu-latest, sdist) in 53s (ID 130429998828)
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
- stash (ID 130430001268)
✓ qualify-ci / prepare in 24s (ID 130430236751)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Validate qualification inputs
  ✓ Download the sealed candidate manifest
  ✓ Bind published identity from the sealed manifest
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
- qualify-ci / docs-build in 0s (ID 130430238633)
- qualify-ci / release-core-floor-smoke in 0s (ID 130430239945)
✓ qualify-ci / build-core / build-core in 7m24s (ID 130430445331)
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
✓ exercise in 24s (ID 130430922757)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Download the sealed build
  ✓ Download the leg evidence
  ✓ Merge the legs into one exercise observation
  - Stash the exercise observation on the draft release
  ✓ Upload the exercise observation artifact
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ qualify-ci / ace-page-group-isolation in 1m36s (ID 130433914911)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  ✓ Run ACE shared-page isolation lane
  ✓ Post Install visual dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
X qualify-ci / visual-test in 23m57s (ID 130433914913)
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
✓ qualify-ci / perf-floors in 9m28s (ID 130433914961)
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
* qualify-ci / test (3.12) (ID 130433915030)
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
✓ qualify-ci / tutorial-tests in 1m1s (ID 130433915035)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run tutorial tests
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ qualify-ci / lint in 6m14s (ID 130433915045)
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
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ qualify-ci / test (3.13) in 1h4m44s (ID 130433915166)
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
✓ qualify-ci / test (3.14) in 52m6s (ID 130433915280)
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
identity: .github#7

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
identity: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
build: .github#4

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0DTH0agAAAAD7rbAUNBT8RL9zAt1UenRYTVNQMzExMDAwMTA0MDI3AEVkZ2U=
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
exercise-legs (ubuntu-latest, wheel): .github#2

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
exercise-legs (ubuntu-latest, wheel): .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
exercise-legs (macos-latest, sdist): .github#2

- Due to capacity constraints, jobs targeting macOS arm64 runners may experience longer queue times.
exercise-legs (macos-latest, sdist): .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
exercise-legs (macos-latest, wheel): .github#2

- Due to capacity constraints, jobs targeting macOS arm64 runners may experience longer queue times.
exercise-legs (macos-latest, wheel): .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
exercise-legs (ubuntu-latest, sdist): .github#2

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
exercise-legs (ubuntu-latest, sdist): .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / prepare: .github#10

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / prepare: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / build-core / build-core: .github#5

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0BTP0agAAAACIQtJKm5FTQLUbV1bojc6rUEhMMzBFREdFMDQxOABFZGdl
qualify-ci / build-core / build-core: .github#7

! Failed to restore: Cache service responded with 400
qualify-ci / build-core / build-core: .github#25

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / build-core / build-core: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
exercise: .github#4

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
exercise: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / ace-page-group-isolation: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0aDP0agAAAAB0dJofL/zsSp+UTSSgEcPMUEhMMzBFREdFMDExNwBFZGdl
qualify-ci / ace-page-group-isolation: .github#9

! Failed to restore: Cache service responded with 400
qualify-ci / ace-page-group-isolation: .github#49

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / ace-page-group-isolation: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / visual-test: .github#2

X agents_final_rows_80x40: updated | changed pixels 11761/1019844 (1.153216%) | expected=tests/ace/tui/visual/snapshots/png/agents_final_rows_80x40.png
qualify-ci / visual-test: tests/ace/tui/visual/test_ace_png_snapshots_agents_final_rows.py#86

X agents_final_rows_60x40: updated | changed pixels 8667/769500 (1.126316%) | expected=tests/ace/tui/visual/snapshots/png/agents_final_rows_60x40.png
qualify-ci / visual-test: tests/ace/tui/visual/test_ace_png_snapshots_agents_final_rows.py#86

X Process completed with exit code 1.
qualify-ci / visual-test: .github#382

! Failed to restore: Cache service responded with 400
qualify-ci / visual-test: .github#49

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / visual-test: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / perf-floors: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0QDX0agAAAADc89K4ImAPR5uO4uh7cK+OQ0gxQUEyMDMwODE0MDM0AEVkZ2U=
qualify-ci / perf-floors: .github#9

! Failed to restore: Cache service responded with 400
qualify-ci / perf-floors: .github#49

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / perf-floors: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / tutorial-tests: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0RDP0agAAAACTIjNRdoBhQoq9lzCQEBnsTEFYRURHRTIwMTgARWRnZQ==
qualify-ci / tutorial-tests: .github#9

! Failed to restore: Cache service responded with 400
qualify-ci / tutorial-tests: .github#49

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / tutorial-tests: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache@v4, actions/checkout@v4, actions/download-artifact@v4, actions/setup-go@v5, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / lint: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0fDT0agAAAADC2ngjG3dlSLM7Bf2Jk2t2TEFYMzExMDAwMTExMDMxAEVkZ2U=
qualify-ci / lint: .github#7

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0fDT0agAAAADPYoWa3hrYT7TlABl8zPO+TEFYMzExMDAwMTE1MDE5AEVkZ2U=
qualify-ci / lint: .github#9

! Failed to restore: Cache service responded with 400
qualify-ci / lint: .github#52

! Failed to restore: Cache service responded with 400
qualify-ci / lint: .github#24

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / lint: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / test (3.13): .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0NEL0agAAAADFfLy0J7M2TbDeN/ibumMcQ08xRURHRTEyMTEARWRnZQ==
qualify-ci / test (3.13): .github#9

! Failed to restore: Cache service responded with 400
qualify-ci / test (3.13): .github#49

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / test (3.13): .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* release-please--branches--master Release sase-org/sase#322 · 42992733019
Triggered via workflow_dispatch about 1 hour ago

JOBS
✓ identity in 51s (ID 130429292693)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Assert source and version identity
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ build in 35s (ID 130429702498)
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
✓ qualify-prepare in 27s (ID 130429998624)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Download the sealed candidate build
  ✓ Bind the sealed candidate identity
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ exercise-legs (ubuntu-latest, wheel) in 1m4s (ID 130429998685)
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
✓ exercise-legs (macos-latest, sdist) in 1m52s (ID 130429998700)
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
✓ exercise-legs (macos-latest, wheel) in 1m55s (ID 130429998736)
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
✓ exercise-legs (ubuntu-latest, sdist) in 53s (ID 130429998828)
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
- stash (ID 130430001268)
✓ qualify-ci / prepare in 24s (ID 130430236751)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Validate qualification inputs
  ✓ Download the sealed candidate manifest
  ✓ Bind published identity from the sealed manifest
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
- qualify-ci / docs-build in 0s (ID 130430238633)
- qualify-ci / release-core-floor-smoke in 0s (ID 130430239945)
✓ qualify-ci / build-core / build-core in 7m24s (ID 130430445331)
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
✓ exercise in 24s (ID 130430922757)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Download the sealed build
  ✓ Download the leg evidence
  ✓ Merge the legs into one exercise observation
  - Stash the exercise observation on the draft release
  ✓ Upload the exercise observation artifact
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ qualify-ci / ace-page-group-isolation in 1m36s (ID 130433914911)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  ✓ Run ACE shared-page isolation lane
  ✓ Post Install visual dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
X qualify-ci / visual-test in 23m57s (ID 130433914913)
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
✓ qualify-ci / perf-floors in 9m28s (ID 130433914961)
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
* qualify-ci / test (3.12) (ID 130433915030)
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
✓ qualify-ci / tutorial-tests in 1m1s (ID 130433915035)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run tutorial tests
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ qualify-ci / lint in 6m14s (ID 130433915045)
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
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ qualify-ci / test (3.13) in 1h4m44s (ID 130433915166)
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
✓ qualify-ci / test (3.14) in 52m6s (ID 130433915280)
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
identity: .github#7

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
identity: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
build: .github#4

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0DTH0agAAAAD7rbAUNBT8RL9zAt1UenRYTVNQMzExMDAwMTA0MDI3AEVkZ2U=
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
exercise-legs (ubuntu-latest, wheel): .github#2

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
exercise-legs (ubuntu-latest, wheel): .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
exercise-legs (macos-latest, sdist): .github#2

- Due to capacity constraints, jobs targeting macOS arm64 runners may experience longer queue times.
exercise-legs (macos-latest, sdist): .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
exercise-legs (macos-latest, wheel): .github#2

- Due to capacity constraints, jobs targeting macOS arm64 runners may experience longer queue times.
exercise-legs (macos-latest, wheel): .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
exercise-legs (ubuntu-latest, sdist): .github#2

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
exercise-legs (ubuntu-latest, sdist): .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / prepare: .github#10

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / prepare: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / build-core / build-core: .github#5

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0BTP0agAAAACIQtJKm5FTQLUbV1bojc6rUEhMMzBFREdFMDQxOABFZGdl
qualify-ci / build-core / build-core: .github#7

! Failed to restore: Cache service responded with 400
qualify-ci / build-core / build-core: .github#25

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / build-core / build-core: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
exercise: .github#4

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
exercise: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / ace-page-group-isolation: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0aDP0agAAAAB0dJofL/zsSp+UTSSgEcPMUEhMMzBFREdFMDExNwBFZGdl
qualify-ci / ace-page-group-isolation: .github#9

! Failed to restore: Cache service responded with 400
qualify-ci / ace-page-group-isolation: .github#49

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / ace-page-group-isolation: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / visual-test: .github#2

X agents_final_rows_80x40: updated | changed pixels 11761/1019844 (1.153216%) | expected=tests/ace/tui/visual/snapshots/png/agents_final_rows_80x40.png
qualify-ci / visual-test: tests/ace/tui/visual/test_ace_png_snapshots_agents_final_rows.py#86

X agents_final_rows_60x40: updated | changed pixels 8667/769500 (1.126316%) | expected=tests/ace/tui/visual/snapshots/png/agents_final_rows_60x40.png
qualify-ci / visual-test: tests/ace/tui/visual/test_ace_png_snapshots_agents_final_rows.py#86

X Process completed with exit code 1.
qualify-ci / visual-test: .github#382

! Failed to restore: Cache service responded with 400
qualify-ci / visual-test: .github#49

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / visual-test: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / perf-floors: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0QDX0agAAAADc89K4ImAPR5uO4uh7cK+OQ0gxQUEyMDMwODE0MDM0AEVkZ2U=
qualify-ci / perf-floors: .github#9

! Failed to restore: Cache service responded with 400
qualify-ci / perf-floors: .github#49

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / perf-floors: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / tutorial-tests: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0RDP0agAAAACTIjNRdoBhQoq9lzCQEBnsTEFYRURHRTIwMTgARWRnZQ==
qualify-ci / tutorial-tests: .github#9

! Failed to restore: Cache service responded with 400
qualify-ci / tutorial-tests: .github#49

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / tutorial-tests: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache@v4, actions/checkout@v4, actions/download-artifact@v4, actions/setup-go@v5, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / lint: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0fDT0agAAAADC2ngjG3dlSLM7Bf2Jk2t2TEFYMzExMDAwMTExMDMxAEVkZ2U=
qualify-ci / lint: .github#7

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0fDT0agAAAADPYoWa3hrYT7TlABl8zPO+TEFYMzExMDAwMTE1MDE5AEVkZ2U=
qualify-ci / lint: .github#9

! Failed to restore: Cache service responded with 400
qualify-ci / lint: .github#52

! Failed to restore: Cache service responded with 400
qualify-ci / lint: .github#24

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / lint: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / test (3.13): .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0NEL0agAAAADFfLy0J7M2TbDeN/ibumMcQ08xRURHRTEyMTEARWRnZQ==
qualify-ci / test (3.13): .github#9

! Failed to restore: Cache service responded with 400
qualify-ci / test (3.13): .github#49

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / test (3.13): .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* release-please--branches--master Release sase-org/sase#322 · 42992733019
Triggered via workflow_dispatch about 1 hour ago

JOBS
✓ identity in 51s (ID 130429292693)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Assert source and version identity
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ build in 35s (ID 130429702498)
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
✓ qualify-prepare in 27s (ID 130429998624)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Download the sealed candidate build
  ✓ Bind the sealed candidate identity
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ exercise-legs (ubuntu-latest, wheel) in 1m4s (ID 130429998685)
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
✓ exercise-legs (macos-latest, sdist) in 1m52s (ID 130429998700)
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
✓ exercise-legs (macos-latest, wheel) in 1m55s (ID 130429998736)
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
✓ exercise-legs (ubuntu-latest, sdist) in 53s (ID 130429998828)
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
- stash (ID 130430001268)
✓ qualify-ci / prepare in 24s (ID 130430236751)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Validate qualification inputs
  ✓ Download the sealed candidate manifest
  ✓ Bind published identity from the sealed manifest
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
- qualify-ci / docs-build in 0s (ID 130430238633)
- qualify-ci / release-core-floor-smoke in 0s (ID 130430239945)
✓ qualify-ci / build-core / build-core in 7m24s (ID 130430445331)
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
✓ exercise in 24s (ID 130430922757)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Download the sealed build
  ✓ Download the leg evidence
  ✓ Merge the legs into one exercise observation
  - Stash the exercise observation on the draft release
  ✓ Upload the exercise observation artifact
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ qualify-ci / ace-page-group-isolation in 1m36s (ID 130433914911)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  ✓ Run ACE shared-page isolation lane
  ✓ Post Install visual dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
X qualify-ci / visual-test in 23m57s (ID 130433914913)
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
✓ qualify-ci / perf-floors in 9m28s (ID 130433914961)
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
* qualify-ci / test (3.12) (ID 130433915030)
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
✓ qualify-ci / tutorial-tests in 1m1s (ID 130433915035)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run tutorial tests
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ qualify-ci / lint in 6m14s (ID 130433915045)
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
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ qualify-ci / test (3.13) in 1h4m44s (ID 130433915166)
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
✓ qualify-ci / test (3.14) in 52m6s (ID 130433915280)
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
identity: .github#7

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
identity: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
build: .github#4

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0DTH0agAAAAD7rbAUNBT8RL9zAt1UenRYTVNQMzExMDAwMTA0MDI3AEVkZ2U=
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
exercise-legs (ubuntu-latest, wheel): .github#2

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
exercise-legs (ubuntu-latest, wheel): .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
exercise-legs (macos-latest, sdist): .github#2

- Due to capacity constraints, jobs targeting macOS arm64 runners may experience longer queue times.
exercise-legs (macos-latest, sdist): .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
exercise-legs (macos-latest, wheel): .github#2

- Due to capacity constraints, jobs targeting macOS arm64 runners may experience longer queue times.
exercise-legs (macos-latest, wheel): .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
exercise-legs (ubuntu-latest, sdist): .github#2

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
exercise-legs (ubuntu-latest, sdist): .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / prepare: .github#10

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / prepare: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / build-core / build-core: .github#5

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0BTP0agAAAACIQtJKm5FTQLUbV1bojc6rUEhMMzBFREdFMDQxOABFZGdl
qualify-ci / build-core / build-core: .github#7

! Failed to restore: Cache service responded with 400
qualify-ci / build-core / build-core: .github#25

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / build-core / build-core: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
exercise: .github#4

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
exercise: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / ace-page-group-isolation: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0aDP0agAAAAB0dJofL/zsSp+UTSSgEcPMUEhMMzBFREdFMDExNwBFZGdl
qualify-ci / ace-page-group-isolation: .github#9

! Failed to restore: Cache service responded with 400
qualify-ci / ace-page-group-isolation: .github#49

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / ace-page-group-isolation: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / visual-test: .github#2

X agents_final_rows_80x40: updated | changed pixels 11761/1019844 (1.153216%) | expected=tests/ace/tui/visual/snapshots/png/agents_final_rows_80x40.png
qualify-ci / visual-test: tests/ace/tui/visual/test_ace_png_snapshots_agents_final_rows.py#86

X agents_final_rows_60x40: updated | changed pixels 8667/769500 (1.126316%) | expected=tests/ace/tui/visual/snapshots/png/agents_final_rows_60x40.png
qualify-ci / visual-test: tests/ace/tui/visual/test_ace_png_snapshots_agents_final_rows.py#86

X Process completed with exit code 1.
qualify-ci / visual-test: .github#382

! Failed to restore: Cache service responded with 400
qualify-ci / visual-test: .github#49

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / visual-test: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / perf-floors: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0QDX0agAAAADc89K4ImAPR5uO4uh7cK+OQ0gxQUEyMDMwODE0MDM0AEVkZ2U=
qualify-ci / perf-floors: .github#9

! Failed to restore: Cache service responded with 400
qualify-ci / perf-floors: .github#49

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / perf-floors: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / tutorial-tests: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0RDP0agAAAACTIjNRdoBhQoq9lzCQEBnsTEFYRURHRTIwMTgARWRnZQ==
qualify-ci / tutorial-tests: .github#9

! Failed to restore: Cache service responded with 400
qualify-ci / tutorial-tests: .github#49

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / tutorial-tests: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache@v4, actions/checkout@v4, actions/download-artifact@v4, actions/setup-go@v5, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / lint: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0fDT0agAAAADC2ngjG3dlSLM7Bf2Jk2t2TEFYMzExMDAwMTExMDMxAEVkZ2U=
qualify-ci / lint: .github#7

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0fDT0agAAAADPYoWa3hrYT7TlABl8zPO+TEFYMzExMDAwMTE1MDE5AEVkZ2U=
qualify-ci / lint: .github#9

! Failed to restore: Cache service responded with 400
qualify-ci / lint: .github#52

! Failed to restore: Cache service responded with 400
qualify-ci / lint: .github#24

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / lint: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / test (3.13): .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0NEL0agAAAADFfLy0J7M2TbDeN/ibumMcQ08xRURHRTEyMTEARWRnZQ==
qualify-ci / test (3.13): .github#9

! Failed to restore: Cache service responded with 400
qualify-ci / test (3.13): .github#49

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / test (3.13): .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* release-please--branches--master Release sase-org/sase#322 · 42992733019
Triggered via workflow_dispatch about 1 hour ago

JOBS
✓ identity in 51s (ID 130429292693)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Assert source and version identity
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ build in 35s (ID 130429702498)
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
✓ qualify-prepare in 27s (ID 130429998624)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Download the sealed candidate build
  ✓ Bind the sealed candidate identity
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ exercise-legs (ubuntu-latest, wheel) in 1m4s (ID 130429998685)
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
✓ exercise-legs (macos-latest, sdist) in 1m52s (ID 130429998700)
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
✓ exercise-legs (macos-latest, wheel) in 1m55s (ID 130429998736)
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
✓ exercise-legs (ubuntu-latest, sdist) in 53s (ID 130429998828)
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
- stash (ID 130430001268)
✓ qualify-ci / prepare in 24s (ID 130430236751)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Validate qualification inputs
  ✓ Download the sealed candidate manifest
  ✓ Bind published identity from the sealed manifest
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
- qualify-ci / docs-build in 0s (ID 130430238633)
- qualify-ci / release-core-floor-smoke in 0s (ID 130430239945)
✓ qualify-ci / build-core / build-core in 7m24s (ID 130430445331)
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
✓ exercise in 24s (ID 130430922757)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Download the sealed build
  ✓ Download the leg evidence
  ✓ Merge the legs into one exercise observation
  - Stash the exercise observation on the draft release
  ✓ Upload the exercise observation artifact
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ qualify-ci / ace-page-group-isolation in 1m36s (ID 130433914911)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  ✓ Run ACE shared-page isolation lane
  ✓ Post Install visual dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
X qualify-ci / visual-test in 23m57s (ID 130433914913)
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
✓ qualify-ci / perf-floors in 9m28s (ID 130433914961)
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
* qualify-ci / test (3.12) (ID 130433915030)
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
✓ qualify-ci / tutorial-tests in 1m1s (ID 130433915035)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run tutorial tests
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ qualify-ci / lint in 6m14s (ID 130433915045)
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
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ qualify-ci / test (3.13) in 1h4m44s (ID 130433915166)
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
✓ qualify-ci / test (3.14) in 52m6s (ID 130433915280)
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
identity: .github#7

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
identity: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
build: .github#4

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0DTH0agAAAAD7rbAUNBT8RL9zAt1UenRYTVNQMzExMDAwMTA0MDI3AEVkZ2U=
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
exercise-legs (ubuntu-latest, wheel): .github#2

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
exercise-legs (ubuntu-latest, wheel): .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
exercise-legs (macos-latest, sdist): .github#2

- Due to capacity constraints, jobs targeting macOS arm64 runners may experience longer queue times.
exercise-legs (macos-latest, sdist): .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
exercise-legs (macos-latest, wheel): .github#2

- Due to capacity constraints, jobs targeting macOS arm64 runners may experience longer queue times.
exercise-legs (macos-latest, wheel): .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
exercise-legs (ubuntu-latest, sdist): .github#2

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
exercise-legs (ubuntu-latest, sdist): .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / prepare: .github#10

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / prepare: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / build-core / build-core: .github#5

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0BTP0agAAAACIQtJKm5FTQLUbV1bojc6rUEhMMzBFREdFMDQxOABFZGdl
qualify-ci / build-core / build-core: .github#7

! Failed to restore: Cache service responded with 400
qualify-ci / build-core / build-core: .github#25

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / build-core / build-core: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
exercise: .github#4

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
exercise: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / ace-page-group-isolation: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0aDP0agAAAAB0dJofL/zsSp+UTSSgEcPMUEhMMzBFREdFMDExNwBFZGdl
qualify-ci / ace-page-group-isolation: .github#9

! Failed to restore: Cache service responded with 400
qualify-ci / ace-page-group-isolation: .github#49

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / ace-page-group-isolation: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / visual-test: .github#2

X agents_final_rows_80x40: updated | changed pixels 11761/1019844 (1.153216%) | expected=tests/ace/tui/visual/snapshots/png/agents_final_rows_80x40.png
qualify-ci / visual-test: tests/ace/tui/visual/test_ace_png_snapshots_agents_final_rows.py#86

X agents_final_rows_60x40: updated | changed pixels 8667/769500 (1.126316%) | expected=tests/ace/tui/visual/snapshots/png/agents_final_rows_60x40.png
qualify-ci / visual-test: tests/ace/tui/visual/test_ace_png_snapshots_agents_final_rows.py#86

X Process completed with exit code 1.
qualify-ci / visual-test: .github#382

! Failed to restore: Cache service responded with 400
qualify-ci / visual-test: .github#49

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / visual-test: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / perf-floors: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0QDX0agAAAADc89K4ImAPR5uO4uh7cK+OQ0gxQUEyMDMwODE0MDM0AEVkZ2U=
qualify-ci / perf-floors: .github#9

! Failed to restore: Cache service responded with 400
qualify-ci / perf-floors: .github#49

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / perf-floors: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / tutorial-tests: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0RDP0agAAAACTIjNRdoBhQoq9lzCQEBnsTEFYRURHRTIwMTgARWRnZQ==
qualify-ci / tutorial-tests: .github#9

! Failed to restore: Cache service responded with 400
qualify-ci / tutorial-tests: .github#49

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / tutorial-tests: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache@v4, actions/checkout@v4, actions/download-artifact@v4, actions/setup-go@v5, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / lint: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0fDT0agAAAADC2ngjG3dlSLM7Bf2Jk2t2TEFYMzExMDAwMTExMDMxAEVkZ2U=
qualify-ci / lint: .github#7

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0fDT0agAAAADPYoWa3hrYT7TlABl8zPO+TEFYMzExMDAwMTE1MDE5AEVkZ2U=
qualify-ci / lint: .github#9

! Failed to restore: Cache service responded with 400
qualify-ci / lint: .github#52

! Failed to restore: Cache service responded with 400
qualify-ci / lint: .github#24

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / lint: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / test (3.13): .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0NEL0agAAAADFfLy0J7M2TbDeN/ibumMcQ08xRURHRTEyMTEARWRnZQ==
qualify-ci / test (3.13): .github#9

! Failed to restore: Cache service responded with 400
qualify-ci / test (3.13): .github#49

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / test (3.13): .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* release-please--branches--master Release sase-org/sase#322 · 42992733019
Triggered via workflow_dispatch about 1 hour ago

JOBS
✓ identity in 51s (ID 130429292693)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Assert source and version identity
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ build in 35s (ID 130429702498)
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
✓ qualify-prepare in 27s (ID 130429998624)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Download the sealed candidate build
  ✓ Bind the sealed candidate identity
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ exercise-legs (ubuntu-latest, wheel) in 1m4s (ID 130429998685)
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
✓ exercise-legs (macos-latest, sdist) in 1m52s (ID 130429998700)
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
✓ exercise-legs (macos-latest, wheel) in 1m55s (ID 130429998736)
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
✓ exercise-legs (ubuntu-latest, sdist) in 53s (ID 130429998828)
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
- stash (ID 130430001268)
✓ qualify-ci / prepare in 24s (ID 130430236751)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Validate qualification inputs
  ✓ Download the sealed candidate manifest
  ✓ Bind published identity from the sealed manifest
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
- qualify-ci / docs-build in 0s (ID 130430238633)
- qualify-ci / release-core-floor-smoke in 0s (ID 130430239945)
✓ qualify-ci / build-core / build-core in 7m24s (ID 130430445331)
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
✓ exercise in 24s (ID 130430922757)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Download the sealed build
  ✓ Download the leg evidence
  ✓ Merge the legs into one exercise observation
  - Stash the exercise observation on the draft release
  ✓ Upload the exercise observation artifact
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ qualify-ci / ace-page-group-isolation in 1m36s (ID 130433914911)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  ✓ Run ACE shared-page isolation lane
  ✓ Post Install visual dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
X qualify-ci / visual-test in 23m57s (ID 130433914913)
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
✓ qualify-ci / perf-floors in 9m28s (ID 130433914961)
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
* qualify-ci / test (3.12) (ID 130433915030)
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
✓ qualify-ci / tutorial-tests in 1m1s (ID 130433915035)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run tutorial tests
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ qualify-ci / lint in 6m14s (ID 130433915045)
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
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ qualify-ci / test (3.13) in 1h4m44s (ID 130433915166)
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
✓ qualify-ci / test (3.14) in 52m6s (ID 130433915280)
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
identity: .github#7

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
identity: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
build: .github#4

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0DTH0agAAAAD7rbAUNBT8RL9zAt1UenRYTVNQMzExMDAwMTA0MDI3AEVkZ2U=
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
exercise-legs (ubuntu-latest, wheel): .github#2

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
exercise-legs (ubuntu-latest, wheel): .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
exercise-legs (macos-latest, sdist): .github#2

- Due to capacity constraints, jobs targeting macOS arm64 runners may experience longer queue times.
exercise-legs (macos-latest, sdist): .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
exercise-legs (macos-latest, wheel): .github#2

- Due to capacity constraints, jobs targeting macOS arm64 runners may experience longer queue times.
exercise-legs (macos-latest, wheel): .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
exercise-legs (ubuntu-latest, sdist): .github#2

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
exercise-legs (ubuntu-latest, sdist): .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / prepare: .github#10

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / prepare: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / build-core / build-core: .github#5

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0BTP0agAAAACIQtJKm5FTQLUbV1bojc6rUEhMMzBFREdFMDQxOABFZGdl
qualify-ci / build-core / build-core: .github#7

! Failed to restore: Cache service responded with 400
qualify-ci / build-core / build-core: .github#25

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / build-core / build-core: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
exercise: .github#4

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
exercise: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / ace-page-group-isolation: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0aDP0agAAAAB0dJofL/zsSp+UTSSgEcPMUEhMMzBFREdFMDExNwBFZGdl
qualify-ci / ace-page-group-isolation: .github#9

! Failed to restore: Cache service responded with 400
qualify-ci / ace-page-group-isolation: .github#49

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / ace-page-group-isolation: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / visual-test: .github#2

X agents_final_rows_80x40: updated | changed pixels 11761/1019844 (1.153216%) | expected=tests/ace/tui/visual/snapshots/png/agents_final_rows_80x40.png
qualify-ci / visual-test: tests/ace/tui/visual/test_ace_png_snapshots_agents_final_rows.py#86

X agents_final_rows_60x40: updated | changed pixels 8667/769500 (1.126316%) | expected=tests/ace/tui/visual/snapshots/png/agents_final_rows_60x40.png
qualify-ci / visual-test: tests/ace/tui/visual/test_ace_png_snapshots_agents_final_rows.py#86

X Process completed with exit code 1.
qualify-ci / visual-test: .github#382

! Failed to restore: Cache service responded with 400
qualify-ci / visual-test: .github#49

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / visual-test: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / perf-floors: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0QDX0agAAAADc89K4ImAPR5uO4uh7cK+OQ0gxQUEyMDMwODE0MDM0AEVkZ2U=
qualify-ci / perf-floors: .github#9

! Failed to restore: Cache service responded with 400
qualify-ci / perf-floors: .github#49

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / perf-floors: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / tutorial-tests: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0RDP0agAAAACTIjNRdoBhQoq9lzCQEBnsTEFYRURHRTIwMTgARWRnZQ==
qualify-ci / tutorial-tests: .github#9

! Failed to restore: Cache service responded with 400
qualify-ci / tutorial-tests: .github#49

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / tutorial-tests: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache@v4, actions/checkout@v4, actions/download-artifact@v4, actions/setup-go@v5, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / lint: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0fDT0agAAAADC2ngjG3dlSLM7Bf2Jk2t2TEFYMzExMDAwMTExMDMxAEVkZ2U=
qualify-ci / lint: .github#7

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0fDT0agAAAADPYoWa3hrYT7TlABl8zPO+TEFYMzExMDAwMTE1MDE5AEVkZ2U=
qualify-ci / lint: .github#9

! Failed to restore: Cache service responded with 400
qualify-ci / lint: .github#52

! Failed to restore: Cache service responded with 400
qualify-ci / lint: .github#24

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / lint: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / test (3.13): .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0NEL0agAAAADFfLy0J7M2TbDeN/ibumMcQ08xRURHRTEyMTEARWRnZQ==
qualify-ci / test (3.13): .github#9

! Failed to restore: Cache service responded with 400
qualify-ci / test (3.13): .github#49

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / test (3.13): .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* release-please--branches--master Release sase-org/sase#322 · 42992733019
Triggered via workflow_dispatch about 1 hour ago

JOBS
✓ identity in 51s (ID 130429292693)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Assert source and version identity
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ build in 35s (ID 130429702498)
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
✓ qualify-prepare in 27s (ID 130429998624)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Download the sealed candidate build
  ✓ Bind the sealed candidate identity
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ exercise-legs (ubuntu-latest, wheel) in 1m4s (ID 130429998685)
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
✓ exercise-legs (macos-latest, sdist) in 1m52s (ID 130429998700)
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
✓ exercise-legs (macos-latest, wheel) in 1m55s (ID 130429998736)
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
✓ exercise-legs (ubuntu-latest, sdist) in 53s (ID 130429998828)
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
- stash (ID 130430001268)
✓ qualify-ci / prepare in 24s (ID 130430236751)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Validate qualification inputs
  ✓ Download the sealed candidate manifest
  ✓ Bind published identity from the sealed manifest
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
- qualify-ci / docs-build in 0s (ID 130430238633)
- qualify-ci / release-core-floor-smoke in 0s (ID 130430239945)
✓ qualify-ci / build-core / build-core in 7m24s (ID 130430445331)
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
✓ exercise in 24s (ID 130430922757)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Download the sealed build
  ✓ Download the leg evidence
  ✓ Merge the legs into one exercise observation
  - Stash the exercise observation on the draft release
  ✓ Upload the exercise observation artifact
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ qualify-ci / ace-page-group-isolation in 1m36s (ID 130433914911)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  ✓ Run ACE shared-page isolation lane
  ✓ Post Install visual dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
X qualify-ci / visual-test in 23m57s (ID 130433914913)
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
✓ qualify-ci / perf-floors in 9m28s (ID 130433914961)
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
* qualify-ci / test (3.12) (ID 130433915030)
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
✓ qualify-ci / tutorial-tests in 1m1s (ID 130433915035)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run tutorial tests
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ qualify-ci / lint in 6m14s (ID 130433915045)
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
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ qualify-ci / test (3.13) in 1h4m44s (ID 130433915166)
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
✓ qualify-ci / test (3.14) in 52m6s (ID 130433915280)
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
identity: .github#7

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
identity: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
build: .github#4

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0DTH0agAAAAD7rbAUNBT8RL9zAt1UenRYTVNQMzExMDAwMTA0MDI3AEVkZ2U=
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
exercise-legs (ubuntu-latest, wheel): .github#2

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
exercise-legs (ubuntu-latest, wheel): .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
exercise-legs (macos-latest, sdist): .github#2

- Due to capacity constraints, jobs targeting macOS arm64 runners may experience longer queue times.
exercise-legs (macos-latest, sdist): .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
exercise-legs (macos-latest, wheel): .github#2

- Due to capacity constraints, jobs targeting macOS arm64 runners may experience longer queue times.
exercise-legs (macos-latest, wheel): .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
exercise-legs (ubuntu-latest, sdist): .github#2

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
exercise-legs (ubuntu-latest, sdist): .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / prepare: .github#10

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / prepare: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / build-core / build-core: .github#5

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0BTP0agAAAACIQtJKm5FTQLUbV1bojc6rUEhMMzBFREdFMDQxOABFZGdl
qualify-ci / build-core / build-core: .github#7

! Failed to restore: Cache service responded with 400
qualify-ci / build-core / build-core: .github#25

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / build-core / build-core: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
exercise: .github#4

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
exercise: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / ace-page-group-isolation: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0aDP0agAAAAB0dJofL/zsSp+UTSSgEcPMUEhMMzBFREdFMDExNwBFZGdl
qualify-ci / ace-page-group-isolation: .github#9

! Failed to restore: Cache service responded with 400
qualify-ci / ace-page-group-isolation: .github#49

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / ace-page-group-isolation: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / visual-test: .github#2

X agents_final_rows_80x40: updated | changed pixels 11761/1019844 (1.153216%) | expected=tests/ace/tui/visual/snapshots/png/agents_final_rows_80x40.png
qualify-ci / visual-test: tests/ace/tui/visual/test_ace_png_snapshots_agents_final_rows.py#86

X agents_final_rows_60x40: updated | changed pixels 8667/769500 (1.126316%) | expected=tests/ace/tui/visual/snapshots/png/agents_final_rows_60x40.png
qualify-ci / visual-test: tests/ace/tui/visual/test_ace_png_snapshots_agents_final_rows.py#86

X Process completed with exit code 1.
qualify-ci / visual-test: .github#382

! Failed to restore: Cache service responded with 400
qualify-ci / visual-test: .github#49

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / visual-test: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / perf-floors: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0QDX0agAAAADc89K4ImAPR5uO4uh7cK+OQ0gxQUEyMDMwODE0MDM0AEVkZ2U=
qualify-ci / perf-floors: .github#9

! Failed to restore: Cache service responded with 400
qualify-ci / perf-floors: .github#49

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / perf-floors: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / tutorial-tests: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0RDP0agAAAACTIjNRdoBhQoq9lzCQEBnsTEFYRURHRTIwMTgARWRnZQ==
qualify-ci / tutorial-tests: .github#9

! Failed to restore: Cache service responded with 400
qualify-ci / tutorial-tests: .github#49

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / tutorial-tests: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache@v4, actions/checkout@v4, actions/download-artifact@v4, actions/setup-go@v5, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / lint: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0fDT0agAAAADC2ngjG3dlSLM7Bf2Jk2t2TEFYMzExMDAwMTExMDMxAEVkZ2U=
qualify-ci / lint: .github#7

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0fDT0agAAAADPYoWa3hrYT7TlABl8zPO+TEFYMzExMDAwMTE1MDE5AEVkZ2U=
qualify-ci / lint: .github#9

! Failed to restore: Cache service responded with 400
qualify-ci / lint: .github#52

! Failed to restore: Cache service responded with 400
qualify-ci / lint: .github#24

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / lint: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / test (3.13): .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0NEL0agAAAADFfLy0J7M2TbDeN/ibumMcQ08xRURHRTEyMTEARWRnZQ==
qualify-ci / test (3.13): .github#9

! Failed to restore: Cache service responded with 400
qualify-ci / test (3.13): .github#49

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / test (3.13): .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* release-please--branches--master Release sase-org/sase#322 · 42992733019
Triggered via workflow_dispatch about 1 hour ago

JOBS
✓ identity in 51s (ID 130429292693)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Assert source and version identity
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ build in 35s (ID 130429702498)
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
✓ qualify-prepare in 27s (ID 130429998624)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Download the sealed candidate build
  ✓ Bind the sealed candidate identity
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ exercise-legs (ubuntu-latest, wheel) in 1m4s (ID 130429998685)
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
✓ exercise-legs (macos-latest, sdist) in 1m52s (ID 130429998700)
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
✓ exercise-legs (macos-latest, wheel) in 1m55s (ID 130429998736)
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
✓ exercise-legs (ubuntu-latest, sdist) in 53s (ID 130429998828)
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
- stash (ID 130430001268)
✓ qualify-ci / prepare in 24s (ID 130430236751)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Validate qualification inputs
  ✓ Download the sealed candidate manifest
  ✓ Bind published identity from the sealed manifest
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
- qualify-ci / docs-build in 0s (ID 130430238633)
- qualify-ci / release-core-floor-smoke in 0s (ID 130430239945)
✓ qualify-ci / build-core / build-core in 7m24s (ID 130430445331)
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
✓ exercise in 24s (ID 130430922757)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Download the sealed build
  ✓ Download the leg evidence
  ✓ Merge the legs into one exercise observation
  - Stash the exercise observation on the draft release
  ✓ Upload the exercise observation artifact
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ qualify-ci / ace-page-group-isolation in 1m36s (ID 130433914911)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  ✓ Run ACE shared-page isolation lane
  ✓ Post Install visual dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
X qualify-ci / visual-test in 23m57s (ID 130433914913)
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
✓ qualify-ci / perf-floors in 9m28s (ID 130433914961)
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
* qualify-ci / test (3.12) (ID 130433915030)
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
✓ qualify-ci / tutorial-tests in 1m1s (ID 130433915035)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run tutorial tests
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ qualify-ci / lint in 6m14s (ID 130433915045)
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
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ qualify-ci / test (3.13) in 1h4m44s (ID 130433915166)
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
✓ qualify-ci / test (3.14) in 52m6s (ID 130433915280)
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
identity: .github#7

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
identity: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
build: .github#4

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0DTH0agAAAAD7rbAUNBT8RL9zAt1UenRYTVNQMzExMDAwMTA0MDI3AEVkZ2U=
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
exercise-legs (ubuntu-latest, wheel): .github#2

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
exercise-legs (ubuntu-latest, wheel): .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
exercise-legs (macos-latest, sdist): .github#2

- Due to capacity constraints, jobs targeting macOS arm64 runners may experience longer queue times.
exercise-legs (macos-latest, sdist): .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
exercise-legs (macos-latest, wheel): .github#2

- Due to capacity constraints, jobs targeting macOS arm64 runners may experience longer queue times.
exercise-legs (macos-latest, wheel): .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
exercise-legs (ubuntu-latest, sdist): .github#2

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
exercise-legs (ubuntu-latest, sdist): .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / prepare: .github#10

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / prepare: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / build-core / build-core: .github#5

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0BTP0agAAAACIQtJKm5FTQLUbV1bojc6rUEhMMzBFREdFMDQxOABFZGdl
qualify-ci / build-core / build-core: .github#7

! Failed to restore: Cache service responded with 400
qualify-ci / build-core / build-core: .github#25

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / build-core / build-core: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
exercise: .github#4

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
exercise: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / ace-page-group-isolation: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0aDP0agAAAAB0dJofL/zsSp+UTSSgEcPMUEhMMzBFREdFMDExNwBFZGdl
qualify-ci / ace-page-group-isolation: .github#9

! Failed to restore: Cache service responded with 400
qualify-ci / ace-page-group-isolation: .github#49

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / ace-page-group-isolation: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / visual-test: .github#2

X agents_final_rows_80x40: updated | changed pixels 11761/1019844 (1.153216%) | expected=tests/ace/tui/visual/snapshots/png/agents_final_rows_80x40.png
qualify-ci / visual-test: tests/ace/tui/visual/test_ace_png_snapshots_agents_final_rows.py#86

X agents_final_rows_60x40: updated | changed pixels 8667/769500 (1.126316%) | expected=tests/ace/tui/visual/snapshots/png/agents_final_rows_60x40.png
qualify-ci / visual-test: tests/ace/tui/visual/test_ace_png_snapshots_agents_final_rows.py#86

X Process completed with exit code 1.
qualify-ci / visual-test: .github#382

! Failed to restore: Cache service responded with 400
qualify-ci / visual-test: .github#49

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / visual-test: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / perf-floors: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0QDX0agAAAADc89K4ImAPR5uO4uh7cK+OQ0gxQUEyMDMwODE0MDM0AEVkZ2U=
qualify-ci / perf-floors: .github#9

! Failed to restore: Cache service responded with 400
qualify-ci / perf-floors: .github#49

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / perf-floors: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / tutorial-tests: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0RDP0agAAAACTIjNRdoBhQoq9lzCQEBnsTEFYRURHRTIwMTgARWRnZQ==
qualify-ci / tutorial-tests: .github#9

! Failed to restore: Cache service responded with 400
qualify-ci / tutorial-tests: .github#49

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / tutorial-tests: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache@v4, actions/checkout@v4, actions/download-artifact@v4, actions/setup-go@v5, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / lint: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0fDT0agAAAADC2ngjG3dlSLM7Bf2Jk2t2TEFYMzExMDAwMTExMDMxAEVkZ2U=
qualify-ci / lint: .github#7

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0fDT0agAAAADPYoWa3hrYT7TlABl8zPO+TEFYMzExMDAwMTE1MDE5AEVkZ2U=
qualify-ci / lint: .github#9

! Failed to restore: Cache service responded with 400
qualify-ci / lint: .github#52

! Failed to restore: Cache service responded with 400
qualify-ci / lint: .github#24

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / lint: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / test (3.13): .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0NEL0agAAAADFfLy0J7M2TbDeN/ibumMcQ08xRURHRTEyMTEARWRnZQ==
qualify-ci / test (3.13): .github#9

! Failed to restore: Cache service responded with 400
qualify-ci / test (3.13): .github#49

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / test (3.13): .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* release-please--branches--master Release sase-org/sase#322 · 42992733019
Triggered via workflow_dispatch about 1 hour ago

JOBS
✓ identity in 51s (ID 130429292693)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Assert source and version identity
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ build in 35s (ID 130429702498)
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
✓ qualify-prepare in 27s (ID 130429998624)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Download the sealed candidate build
  ✓ Bind the sealed candidate identity
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ exercise-legs (ubuntu-latest, wheel) in 1m4s (ID 130429998685)
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
✓ exercise-legs (macos-latest, sdist) in 1m52s (ID 130429998700)
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
✓ exercise-legs (macos-latest, wheel) in 1m55s (ID 130429998736)
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
✓ exercise-legs (ubuntu-latest, sdist) in 53s (ID 130429998828)
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
- stash (ID 130430001268)
✓ qualify-ci / prepare in 24s (ID 130430236751)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Validate qualification inputs
  ✓ Download the sealed candidate manifest
  ✓ Bind published identity from the sealed manifest
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
- qualify-ci / docs-build in 0s (ID 130430238633)
- qualify-ci / release-core-floor-smoke in 0s (ID 130430239945)
✓ qualify-ci / build-core / build-core in 7m24s (ID 130430445331)
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
✓ exercise in 24s (ID 130430922757)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Download the sealed build
  ✓ Download the leg evidence
  ✓ Merge the legs into one exercise observation
  - Stash the exercise observation on the draft release
  ✓ Upload the exercise observation artifact
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ qualify-ci / ace-page-group-isolation in 1m36s (ID 130433914911)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  ✓ Run ACE shared-page isolation lane
  ✓ Post Install visual dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
X qualify-ci / visual-test in 23m57s (ID 130433914913)
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
✓ qualify-ci / perf-floors in 9m28s (ID 130433914961)
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
* qualify-ci / test (3.12) (ID 130433915030)
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
✓ qualify-ci / tutorial-tests in 1m1s (ID 130433915035)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run tutorial tests
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ qualify-ci / lint in 6m14s (ID 130433915045)
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
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ qualify-ci / test (3.13) in 1h4m44s (ID 130433915166)
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
✓ qualify-ci / test (3.14) in 52m6s (ID 130433915280)
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
identity: .github#7

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
identity: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
build: .github#4

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0DTH0agAAAAD7rbAUNBT8RL9zAt1UenRYTVNQMzExMDAwMTA0MDI3AEVkZ2U=
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
exercise-legs (ubuntu-latest, wheel): .github#2

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
exercise-legs (ubuntu-latest, wheel): .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
exercise-legs (macos-latest, sdist): .github#2

- Due to capacity constraints, jobs targeting macOS arm64 runners may experience longer queue times.
exercise-legs (macos-latest, sdist): .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
exercise-legs (macos-latest, wheel): .github#2

- Due to capacity constraints, jobs targeting macOS arm64 runners may experience longer queue times.
exercise-legs (macos-latest, wheel): .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
exercise-legs (ubuntu-latest, sdist): .github#2

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
exercise-legs (ubuntu-latest, sdist): .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / prepare: .github#10

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / prepare: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / build-core / build-core: .github#5

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0BTP0agAAAACIQtJKm5FTQLUbV1bojc6rUEhMMzBFREdFMDQxOABFZGdl
qualify-ci / build-core / build-core: .github#7

! Failed to restore: Cache service responded with 400
qualify-ci / build-core / build-core: .github#25

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / build-core / build-core: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
exercise: .github#4

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
exercise: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / ace-page-group-isolation: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0aDP0agAAAAB0dJofL/zsSp+UTSSgEcPMUEhMMzBFREdFMDExNwBFZGdl
qualify-ci / ace-page-group-isolation: .github#9

! Failed to restore: Cache service responded with 400
qualify-ci / ace-page-group-isolation: .github#49

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / ace-page-group-isolation: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / visual-test: .github#2

X agents_final_rows_80x40: updated | changed pixels 11761/1019844 (1.153216%) | expected=tests/ace/tui/visual/snapshots/png/agents_final_rows_80x40.png
qualify-ci / visual-test: tests/ace/tui/visual/test_ace_png_snapshots_agents_final_rows.py#86

X agents_final_rows_60x40: updated | changed pixels 8667/769500 (1.126316%) | expected=tests/ace/tui/visual/snapshots/png/agents_final_rows_60x40.png
qualify-ci / visual-test: tests/ace/tui/visual/test_ace_png_snapshots_agents_final_rows.py#86

X Process completed with exit code 1.
qualify-ci / visual-test: .github#382

! Failed to restore: Cache service responded with 400
qualify-ci / visual-test: .github#49

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / visual-test: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / perf-floors: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0QDX0agAAAADc89K4ImAPR5uO4uh7cK+OQ0gxQUEyMDMwODE0MDM0AEVkZ2U=
qualify-ci / perf-floors: .github#9

! Failed to restore: Cache service responded with 400
qualify-ci / perf-floors: .github#49

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / perf-floors: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / tutorial-tests: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0RDP0agAAAACTIjNRdoBhQoq9lzCQEBnsTEFYRURHRTIwMTgARWRnZQ==
qualify-ci / tutorial-tests: .github#9

! Failed to restore: Cache service responded with 400
qualify-ci / tutorial-tests: .github#49

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / tutorial-tests: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache@v4, actions/checkout@v4, actions/download-artifact@v4, actions/setup-go@v5, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / lint: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0fDT0agAAAADC2ngjG3dlSLM7Bf2Jk2t2TEFYMzExMDAwMTExMDMxAEVkZ2U=
qualify-ci / lint: .github#7

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0fDT0agAAAADPYoWa3hrYT7TlABl8zPO+TEFYMzExMDAwMTE1MDE5AEVkZ2U=
qualify-ci / lint: .github#9

! Failed to restore: Cache service responded with 400
qualify-ci / lint: .github#52

! Failed to restore: Cache service responded with 400
qualify-ci / lint: .github#24

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / lint: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / test (3.13): .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0NEL0agAAAADFfLy0J7M2TbDeN/ibumMcQ08xRURHRTEyMTEARWRnZQ==
qualify-ci / test (3.13): .github#9

! Failed to restore: Cache service responded with 400
qualify-ci / test (3.13): .github#49

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / test (3.13): .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* release-please--branches--master Release sase-org/sase#322 · 42992733019
Triggered via workflow_dispatch about 1 hour ago

JOBS
✓ identity in 51s (ID 130429292693)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Assert source and version identity
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ build in 35s (ID 130429702498)
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
✓ qualify-prepare in 27s (ID 130429998624)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Download the sealed candidate build
  ✓ Bind the sealed candidate identity
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ exercise-legs (ubuntu-latest, wheel) in 1m4s (ID 130429998685)
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
✓ exercise-legs (macos-latest, sdist) in 1m52s (ID 130429998700)
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
✓ exercise-legs (macos-latest, wheel) in 1m55s (ID 130429998736)
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
✓ exercise-legs (ubuntu-latest, sdist) in 53s (ID 130429998828)
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
- stash (ID 130430001268)
✓ qualify-ci / prepare in 24s (ID 130430236751)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Validate qualification inputs
  ✓ Download the sealed candidate manifest
  ✓ Bind published identity from the sealed manifest
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
- qualify-ci / docs-build in 0s (ID 130430238633)
- qualify-ci / release-core-floor-smoke in 0s (ID 130430239945)
✓ qualify-ci / build-core / build-core in 7m24s (ID 130430445331)
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
✓ exercise in 24s (ID 130430922757)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Download the sealed build
  ✓ Download the leg evidence
  ✓ Merge the legs into one exercise observation
  - Stash the exercise observation on the draft release
  ✓ Upload the exercise observation artifact
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ qualify-ci / ace-page-group-isolation in 1m36s (ID 130433914911)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  ✓ Run ACE shared-page isolation lane
  ✓ Post Install visual dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
X qualify-ci / visual-test in 23m57s (ID 130433914913)
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
✓ qualify-ci / perf-floors in 9m28s (ID 130433914961)
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
* qualify-ci / test (3.12) (ID 130433915030)
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
✓ qualify-ci / tutorial-tests in 1m1s (ID 130433915035)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run tutorial tests
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ qualify-ci / lint in 6m14s (ID 130433915045)
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
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ qualify-ci / test (3.13) in 1h4m44s (ID 130433915166)
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
✓ qualify-ci / test (3.14) in 52m6s (ID 130433915280)
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
identity: .github#7

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
identity: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
build: .github#4

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0DTH0agAAAAD7rbAUNBT8RL9zAt1UenRYTVNQMzExMDAwMTA0MDI3AEVkZ2U=
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
exercise-legs (ubuntu-latest, wheel): .github#2

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
exercise-legs (ubuntu-latest, wheel): .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
exercise-legs (macos-latest, sdist): .github#2

- Due to capacity constraints, jobs targeting macOS arm64 runners may experience longer queue times.
exercise-legs (macos-latest, sdist): .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
exercise-legs (macos-latest, wheel): .github#2

- Due to capacity constraints, jobs targeting macOS arm64 runners may experience longer queue times.
exercise-legs (macos-latest, wheel): .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
exercise-legs (ubuntu-latest, sdist): .github#2

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
exercise-legs (ubuntu-latest, sdist): .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / prepare: .github#10

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / prepare: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / build-core / build-core: .github#5

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0BTP0agAAAACIQtJKm5FTQLUbV1bojc6rUEhMMzBFREdFMDQxOABFZGdl
qualify-ci / build-core / build-core: .github#7

! Failed to restore: Cache service responded with 400
qualify-ci / build-core / build-core: .github#25

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / build-core / build-core: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
exercise: .github#4

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
exercise: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / ace-page-group-isolation: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0aDP0agAAAAB0dJofL/zsSp+UTSSgEcPMUEhMMzBFREdFMDExNwBFZGdl
qualify-ci / ace-page-group-isolation: .github#9

! Failed to restore: Cache service responded with 400
qualify-ci / ace-page-group-isolation: .github#49

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / ace-page-group-isolation: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / visual-test: .github#2

X agents_final_rows_80x40: updated | changed pixels 11761/1019844 (1.153216%) | expected=tests/ace/tui/visual/snapshots/png/agents_final_rows_80x40.png
qualify-ci / visual-test: tests/ace/tui/visual/test_ace_png_snapshots_agents_final_rows.py#86

X agents_final_rows_60x40: updated | changed pixels 8667/769500 (1.126316%) | expected=tests/ace/tui/visual/snapshots/png/agents_final_rows_60x40.png
qualify-ci / visual-test: tests/ace/tui/visual/test_ace_png_snapshots_agents_final_rows.py#86

X Process completed with exit code 1.
qualify-ci / visual-test: .github#382

! Failed to restore: Cache service responded with 400
qualify-ci / visual-test: .github#49

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / visual-test: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / perf-floors: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0QDX0agAAAADc89K4ImAPR5uO4uh7cK+OQ0gxQUEyMDMwODE0MDM0AEVkZ2U=
qualify-ci / perf-floors: .github#9

! Failed to restore: Cache service responded with 400
qualify-ci / perf-floors: .github#49

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / perf-floors: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / tutorial-tests: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0RDP0agAAAACTIjNRdoBhQoq9lzCQEBnsTEFYRURHRTIwMTgARWRnZQ==
qualify-ci / tutorial-tests: .github#9

! Failed to restore: Cache service responded with 400
qualify-ci / tutorial-tests: .github#49

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / tutorial-tests: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache@v4, actions/checkout@v4, actions/download-artifact@v4, actions/setup-go@v5, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / lint: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0fDT0agAAAADC2ngjG3dlSLM7Bf2Jk2t2TEFYMzExMDAwMTExMDMxAEVkZ2U=
qualify-ci / lint: .github#7

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0fDT0agAAAADPYoWa3hrYT7TlABl8zPO+TEFYMzExMDAwMTE1MDE5AEVkZ2U=
qualify-ci / lint: .github#9

! Failed to restore: Cache service responded with 400
qualify-ci / lint: .github#52

! Failed to restore: Cache service responded with 400
qualify-ci / lint: .github#24

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / lint: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / test (3.13): .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0NEL0agAAAADFfLy0J7M2TbDeN/ibumMcQ08xRURHRTEyMTEARWRnZQ==
qualify-ci / test (3.13): .github#9

! Failed to restore: Cache service responded with 400
qualify-ci / test (3.13): .github#49

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / test (3.13): .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* release-please--branches--master Release sase-org/sase#322 · 42992733019
Triggered via workflow_dispatch about 1 hour ago

JOBS
✓ identity in 51s (ID 130429292693)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Assert source and version identity
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ build in 35s (ID 130429702498)
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
✓ qualify-prepare in 27s (ID 130429998624)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Download the sealed candidate build
  ✓ Bind the sealed candidate identity
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ exercise-legs (ubuntu-latest, wheel) in 1m4s (ID 130429998685)
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
✓ exercise-legs (macos-latest, sdist) in 1m52s (ID 130429998700)
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
✓ exercise-legs (macos-latest, wheel) in 1m55s (ID 130429998736)
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
✓ exercise-legs (ubuntu-latest, sdist) in 53s (ID 130429998828)
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
- stash (ID 130430001268)
✓ qualify-ci / prepare in 24s (ID 130430236751)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Validate qualification inputs
  ✓ Download the sealed candidate manifest
  ✓ Bind published identity from the sealed manifest
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
- qualify-ci / docs-build in 0s (ID 130430238633)
- qualify-ci / release-core-floor-smoke in 0s (ID 130430239945)
✓ qualify-ci / build-core / build-core in 7m24s (ID 130430445331)
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
✓ exercise in 24s (ID 130430922757)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Download the sealed build
  ✓ Download the leg evidence
  ✓ Merge the legs into one exercise observation
  - Stash the exercise observation on the draft release
  ✓ Upload the exercise observation artifact
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ qualify-ci / ace-page-group-isolation in 1m36s (ID 130433914911)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  ✓ Run ACE shared-page isolation lane
  ✓ Post Install visual dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
X qualify-ci / visual-test in 23m57s (ID 130433914913)
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
✓ qualify-ci / perf-floors in 9m28s (ID 130433914961)
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
* qualify-ci / test (3.12) (ID 130433915030)
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
✓ qualify-ci / tutorial-tests in 1m1s (ID 130433915035)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run tutorial tests
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ qualify-ci / lint in 6m14s (ID 130433915045)
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
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ qualify-ci / test (3.13) in 1h4m44s (ID 130433915166)
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
✓ qualify-ci / test (3.14) in 52m6s (ID 130433915280)
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
identity: .github#7

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
identity: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
build: .github#4

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0DTH0agAAAAD7rbAUNBT8RL9zAt1UenRYTVNQMzExMDAwMTA0MDI3AEVkZ2U=
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
exercise-legs (ubuntu-latest, wheel): .github#2

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
exercise-legs (ubuntu-latest, wheel): .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
exercise-legs (macos-latest, sdist): .github#2

- Due to capacity constraints, jobs targeting macOS arm64 runners may experience longer queue times.
exercise-legs (macos-latest, sdist): .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
exercise-legs (macos-latest, wheel): .github#2

- Due to capacity constraints, jobs targeting macOS arm64 runners may experience longer queue times.
exercise-legs (macos-latest, wheel): .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
exercise-legs (ubuntu-latest, sdist): .github#2

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
exercise-legs (ubuntu-latest, sdist): .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / prepare: .github#10

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / prepare: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / build-core / build-core: .github#5

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0BTP0agAAAACIQtJKm5FTQLUbV1bojc6rUEhMMzBFREdFMDQxOABFZGdl
qualify-ci / build-core / build-core: .github#7

! Failed to restore: Cache service responded with 400
qualify-ci / build-core / build-core: .github#25

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / build-core / build-core: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
exercise: .github#4

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
exercise: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / ace-page-group-isolation: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0aDP0agAAAAB0dJofL/zsSp+UTSSgEcPMUEhMMzBFREdFMDExNwBFZGdl
qualify-ci / ace-page-group-isolation: .github#9

! Failed to restore: Cache service responded with 400
qualify-ci / ace-page-group-isolation: .github#49

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / ace-page-group-isolation: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / visual-test: .github#2

X agents_final_rows_80x40: updated | changed pixels 11761/1019844 (1.153216%) | expected=tests/ace/tui/visual/snapshots/png/agents_final_rows_80x40.png
qualify-ci / visual-test: tests/ace/tui/visual/test_ace_png_snapshots_agents_final_rows.py#86

X agents_final_rows_60x40: updated | changed pixels 8667/769500 (1.126316%) | expected=tests/ace/tui/visual/snapshots/png/agents_final_rows_60x40.png
qualify-ci / visual-test: tests/ace/tui/visual/test_ace_png_snapshots_agents_final_rows.py#86

X Process completed with exit code 1.
qualify-ci / visual-test: .github#382

! Failed to restore: Cache service responded with 400
qualify-ci / visual-test: .github#49

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / visual-test: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / perf-floors: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0QDX0agAAAADc89K4ImAPR5uO4uh7cK+OQ0gxQUEyMDMwODE0MDM0AEVkZ2U=
qualify-ci / perf-floors: .github#9

! Failed to restore: Cache service responded with 400
qualify-ci / perf-floors: .github#49

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / perf-floors: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / tutorial-tests: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0RDP0agAAAACTIjNRdoBhQoq9lzCQEBnsTEFYRURHRTIwMTgARWRnZQ==
qualify-ci / tutorial-tests: .github#9

! Failed to restore: Cache service responded with 400
qualify-ci / tutorial-tests: .github#49

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / tutorial-tests: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache@v4, actions/checkout@v4, actions/download-artifact@v4, actions/setup-go@v5, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / lint: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0fDT0agAAAADC2ngjG3dlSLM7Bf2Jk2t2TEFYMzExMDAwMTExMDMxAEVkZ2U=
qualify-ci / lint: .github#7

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0fDT0agAAAADPYoWa3hrYT7TlABl8zPO+TEFYMzExMDAwMTE1MDE5AEVkZ2U=
qualify-ci / lint: .github#9

! Failed to restore: Cache service responded with 400
qualify-ci / lint: .github#52

! Failed to restore: Cache service responded with 400
qualify-ci / lint: .github#24

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / lint: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / test (3.13): .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0NEL0agAAAADFfLy0J7M2TbDeN/ibumMcQ08xRURHRTEyMTEARWRnZQ==
qualify-ci / test (3.13): .github#9

! Failed to restore: Cache service responded with 400
qualify-ci / test (3.13): .github#49

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / test (3.13): .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* release-please--branches--master Release sase-org/sase#322 · 42992733019
Triggered via workflow_dispatch about 1 hour ago

JOBS
✓ identity in 51s (ID 130429292693)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Assert source and version identity
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ build in 35s (ID 130429702498)
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
✓ qualify-prepare in 27s (ID 130429998624)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Download the sealed candidate build
  ✓ Bind the sealed candidate identity
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ exercise-legs (ubuntu-latest, wheel) in 1m4s (ID 130429998685)
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
✓ exercise-legs (macos-latest, sdist) in 1m52s (ID 130429998700)
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
✓ exercise-legs (macos-latest, wheel) in 1m55s (ID 130429998736)
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
✓ exercise-legs (ubuntu-latest, sdist) in 53s (ID 130429998828)
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
- stash (ID 130430001268)
✓ qualify-ci / prepare in 24s (ID 130430236751)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Validate qualification inputs
  ✓ Download the sealed candidate manifest
  ✓ Bind published identity from the sealed manifest
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
- qualify-ci / docs-build in 0s (ID 130430238633)
- qualify-ci / release-core-floor-smoke in 0s (ID 130430239945)
✓ qualify-ci / build-core / build-core in 7m24s (ID 130430445331)
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
✓ exercise in 24s (ID 130430922757)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Download the sealed build
  ✓ Download the leg evidence
  ✓ Merge the legs into one exercise observation
  - Stash the exercise observation on the draft release
  ✓ Upload the exercise observation artifact
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ qualify-ci / ace-page-group-isolation in 1m36s (ID 130433914911)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  ✓ Run ACE shared-page isolation lane
  ✓ Post Install visual dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
X qualify-ci / visual-test in 23m57s (ID 130433914913)
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
✓ qualify-ci / perf-floors in 9m28s (ID 130433914961)
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
* qualify-ci / test (3.12) (ID 130433915030)
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
✓ qualify-ci / tutorial-tests in 1m1s (ID 130433915035)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run tutorial tests
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ qualify-ci / lint in 6m14s (ID 130433915045)
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
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ qualify-ci / test (3.13) in 1h4m44s (ID 130433915166)
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
✓ qualify-ci / test (3.14) in 52m6s (ID 130433915280)
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
identity: .github#7

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
identity: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
build: .github#4

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0DTH0agAAAAD7rbAUNBT8RL9zAt1UenRYTVNQMzExMDAwMTA0MDI3AEVkZ2U=
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
exercise-legs (ubuntu-latest, wheel): .github#2

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
exercise-legs (ubuntu-latest, wheel): .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
exercise-legs (macos-latest, sdist): .github#2

- Due to capacity constraints, jobs targeting macOS arm64 runners may experience longer queue times.
exercise-legs (macos-latest, sdist): .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
exercise-legs (macos-latest, wheel): .github#2

- Due to capacity constraints, jobs targeting macOS arm64 runners may experience longer queue times.
exercise-legs (macos-latest, wheel): .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
exercise-legs (ubuntu-latest, sdist): .github#2

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
exercise-legs (ubuntu-latest, sdist): .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / prepare: .github#10

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / prepare: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / build-core / build-core: .github#5

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0BTP0agAAAACIQtJKm5FTQLUbV1bojc6rUEhMMzBFREdFMDQxOABFZGdl
qualify-ci / build-core / build-core: .github#7

! Failed to restore: Cache service responded with 400
qualify-ci / build-core / build-core: .github#25

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / build-core / build-core: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
exercise: .github#4

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
exercise: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / ace-page-group-isolation: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0aDP0agAAAAB0dJofL/zsSp+UTSSgEcPMUEhMMzBFREdFMDExNwBFZGdl
qualify-ci / ace-page-group-isolation: .github#9

! Failed to restore: Cache service responded with 400
qualify-ci / ace-page-group-isolation: .github#49

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / ace-page-group-isolation: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / visual-test: .github#2

X agents_final_rows_80x40: updated | changed pixels 11761/1019844 (1.153216%) | expected=tests/ace/tui/visual/snapshots/png/agents_final_rows_80x40.png
qualify-ci / visual-test: tests/ace/tui/visual/test_ace_png_snapshots_agents_final_rows.py#86

X agents_final_rows_60x40: updated | changed pixels 8667/769500 (1.126316%) | expected=tests/ace/tui/visual/snapshots/png/agents_final_rows_60x40.png
qualify-ci / visual-test: tests/ace/tui/visual/test_ace_png_snapshots_agents_final_rows.py#86

X Process completed with exit code 1.
qualify-ci / visual-test: .github#382

! Failed to restore: Cache service responded with 400
qualify-ci / visual-test: .github#49

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / visual-test: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / perf-floors: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0QDX0agAAAADc89K4ImAPR5uO4uh7cK+OQ0gxQUEyMDMwODE0MDM0AEVkZ2U=
qualify-ci / perf-floors: .github#9

! Failed to restore: Cache service responded with 400
qualify-ci / perf-floors: .github#49

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / perf-floors: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / tutorial-tests: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0RDP0agAAAACTIjNRdoBhQoq9lzCQEBnsTEFYRURHRTIwMTgARWRnZQ==
qualify-ci / tutorial-tests: .github#9

! Failed to restore: Cache service responded with 400
qualify-ci / tutorial-tests: .github#49

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / tutorial-tests: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache@v4, actions/checkout@v4, actions/download-artifact@v4, actions/setup-go@v5, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / lint: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0fDT0agAAAADC2ngjG3dlSLM7Bf2Jk2t2TEFYMzExMDAwMTExMDMxAEVkZ2U=
qualify-ci / lint: .github#7

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0fDT0agAAAADPYoWa3hrYT7TlABl8zPO+TEFYMzExMDAwMTE1MDE5AEVkZ2U=
qualify-ci / lint: .github#9

! Failed to restore: Cache service responded with 400
qualify-ci / lint: .github#52

! Failed to restore: Cache service responded with 400
qualify-ci / lint: .github#24

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / lint: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / test (3.13): .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0NEL0agAAAADFfLy0J7M2TbDeN/ibumMcQ08xRURHRTEyMTEARWRnZQ==
qualify-ci / test (3.13): .github#9

! Failed to restore: Cache service responded with 400
qualify-ci / test (3.13): .github#49

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / test (3.13): .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* release-please--branches--master Release sase-org/sase#322 · 42992733019
Triggered via workflow_dispatch about 1 hour ago

JOBS
✓ identity in 51s (ID 130429292693)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Assert source and version identity
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ build in 35s (ID 130429702498)
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
✓ qualify-prepare in 27s (ID 130429998624)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Download the sealed candidate build
  ✓ Bind the sealed candidate identity
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ exercise-legs (ubuntu-latest, wheel) in 1m4s (ID 130429998685)
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
✓ exercise-legs (macos-latest, sdist) in 1m52s (ID 130429998700)
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
✓ exercise-legs (macos-latest, wheel) in 1m55s (ID 130429998736)
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
✓ exercise-legs (ubuntu-latest, sdist) in 53s (ID 130429998828)
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
- stash (ID 130430001268)
✓ qualify-ci / prepare in 24s (ID 130430236751)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Validate qualification inputs
  ✓ Download the sealed candidate manifest
  ✓ Bind published identity from the sealed manifest
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
- qualify-ci / docs-build in 0s (ID 130430238633)
- qualify-ci / release-core-floor-smoke in 0s (ID 130430239945)
✓ qualify-ci / build-core / build-core in 7m24s (ID 130430445331)
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
✓ exercise in 24s (ID 130430922757)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Download the sealed build
  ✓ Download the leg evidence
  ✓ Merge the legs into one exercise observation
  - Stash the exercise observation on the draft release
  ✓ Upload the exercise observation artifact
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ qualify-ci / ace-page-group-isolation in 1m36s (ID 130433914911)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  ✓ Run ACE shared-page isolation lane
  ✓ Post Install visual dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
X qualify-ci / visual-test in 23m57s (ID 130433914913)
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
✓ qualify-ci / perf-floors in 9m28s (ID 130433914961)
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
* qualify-ci / test (3.12) (ID 130433915030)
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
✓ qualify-ci / tutorial-tests in 1m1s (ID 130433915035)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run tutorial tests
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ qualify-ci / lint in 6m14s (ID 130433915045)
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
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ qualify-ci / test (3.13) in 1h4m44s (ID 130433915166)
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
✓ qualify-ci / test (3.14) in 52m6s (ID 130433915280)
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
identity: .github#7

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
identity: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
build: .github#4

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0DTH0agAAAAD7rbAUNBT8RL9zAt1UenRYTVNQMzExMDAwMTA0MDI3AEVkZ2U=
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
exercise-legs (ubuntu-latest, wheel): .github#2

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
exercise-legs (ubuntu-latest, wheel): .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
exercise-legs (macos-latest, sdist): .github#2

- Due to capacity constraints, jobs targeting macOS arm64 runners may experience longer queue times.
exercise-legs (macos-latest, sdist): .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
exercise-legs (macos-latest, wheel): .github#2

- Due to capacity constraints, jobs targeting macOS arm64 runners may experience longer queue times.
exercise-legs (macos-latest, wheel): .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
exercise-legs (ubuntu-latest, sdist): .github#2

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
exercise-legs (ubuntu-latest, sdist): .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / prepare: .github#10

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / prepare: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / build-core / build-core: .github#5

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0BTP0agAAAACIQtJKm5FTQLUbV1bojc6rUEhMMzBFREdFMDQxOABFZGdl
qualify-ci / build-core / build-core: .github#7

! Failed to restore: Cache service responded with 400
qualify-ci / build-core / build-core: .github#25

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / build-core / build-core: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
exercise: .github#4

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
exercise: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / ace-page-group-isolation: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0aDP0agAAAAB0dJofL/zsSp+UTSSgEcPMUEhMMzBFREdFMDExNwBFZGdl
qualify-ci / ace-page-group-isolation: .github#9

! Failed to restore: Cache service responded with 400
qualify-ci / ace-page-group-isolation: .github#49

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / ace-page-group-isolation: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / visual-test: .github#2

X agents_final_rows_80x40: updated | changed pixels 11761/1019844 (1.153216%) | expected=tests/ace/tui/visual/snapshots/png/agents_final_rows_80x40.png
qualify-ci / visual-test: tests/ace/tui/visual/test_ace_png_snapshots_agents_final_rows.py#86

X agents_final_rows_60x40: updated | changed pixels 8667/769500 (1.126316%) | expected=tests/ace/tui/visual/snapshots/png/agents_final_rows_60x40.png
qualify-ci / visual-test: tests/ace/tui/visual/test_ace_png_snapshots_agents_final_rows.py#86

X Process completed with exit code 1.
qualify-ci / visual-test: .github#382

! Failed to restore: Cache service responded with 400
qualify-ci / visual-test: .github#49

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / visual-test: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / perf-floors: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0QDX0agAAAADc89K4ImAPR5uO4uh7cK+OQ0gxQUEyMDMwODE0MDM0AEVkZ2U=
qualify-ci / perf-floors: .github#9

! Failed to restore: Cache service responded with 400
qualify-ci / perf-floors: .github#49

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / perf-floors: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / tutorial-tests: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0RDP0agAAAACTIjNRdoBhQoq9lzCQEBnsTEFYRURHRTIwMTgARWRnZQ==
qualify-ci / tutorial-tests: .github#9

! Failed to restore: Cache service responded with 400
qualify-ci / tutorial-tests: .github#49

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / tutorial-tests: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache@v4, actions/checkout@v4, actions/download-artifact@v4, actions/setup-go@v5, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / lint: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0fDT0agAAAADC2ngjG3dlSLM7Bf2Jk2t2TEFYMzExMDAwMTExMDMxAEVkZ2U=
qualify-ci / lint: .github#7

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0fDT0agAAAADPYoWa3hrYT7TlABl8zPO+TEFYMzExMDAwMTE1MDE5AEVkZ2U=
qualify-ci / lint: .github#9

! Failed to restore: Cache service responded with 400
qualify-ci / lint: .github#52

! Failed to restore: Cache service responded with 400
qualify-ci / lint: .github#24

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / lint: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / test (3.13): .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0NEL0agAAAADFfLy0J7M2TbDeN/ibumMcQ08xRURHRTEyMTEARWRnZQ==
qualify-ci / test (3.13): .github#9

! Failed to restore: Cache service responded with 400
qualify-ci / test (3.13): .github#49

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / test (3.13): .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* release-please--branches--master Release sase-org/sase#322 · 42992733019
Triggered via workflow_dispatch about 1 hour ago

JOBS
✓ identity in 51s (ID 130429292693)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Assert source and version identity
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ build in 35s (ID 130429702498)
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
✓ qualify-prepare in 27s (ID 130429998624)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Download the sealed candidate build
  ✓ Bind the sealed candidate identity
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ exercise-legs (ubuntu-latest, wheel) in 1m4s (ID 130429998685)
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
✓ exercise-legs (macos-latest, sdist) in 1m52s (ID 130429998700)
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
✓ exercise-legs (macos-latest, wheel) in 1m55s (ID 130429998736)
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
✓ exercise-legs (ubuntu-latest, sdist) in 53s (ID 130429998828)
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
- stash (ID 130430001268)
✓ qualify-ci / prepare in 24s (ID 130430236751)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Validate qualification inputs
  ✓ Download the sealed candidate manifest
  ✓ Bind published identity from the sealed manifest
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
- qualify-ci / docs-build in 0s (ID 130430238633)
- qualify-ci / release-core-floor-smoke in 0s (ID 130430239945)
✓ qualify-ci / build-core / build-core in 7m24s (ID 130430445331)
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
✓ exercise in 24s (ID 130430922757)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Download the sealed build
  ✓ Download the leg evidence
  ✓ Merge the legs into one exercise observation
  - Stash the exercise observation on the draft release
  ✓ Upload the exercise observation artifact
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ qualify-ci / ace-page-group-isolation in 1m36s (ID 130433914911)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  ✓ Run ACE shared-page isolation lane
  ✓ Post Install visual dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
X qualify-ci / visual-test in 23m57s (ID 130433914913)
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
✓ qualify-ci / perf-floors in 9m28s (ID 130433914961)
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
* qualify-ci / test (3.12) (ID 130433915030)
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
✓ qualify-ci / tutorial-tests in 1m1s (ID 130433915035)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run tutorial tests
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ qualify-ci / lint in 6m14s (ID 130433915045)
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
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ qualify-ci / test (3.13) in 1h4m44s (ID 130433915166)
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
✓ qualify-ci / test (3.14) in 52m6s (ID 130433915280)
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
identity: .github#7

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
identity: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
build: .github#4

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0DTH0agAAAAD7rbAUNBT8RL9zAt1UenRYTVNQMzExMDAwMTA0MDI3AEVkZ2U=
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
exercise-legs (ubuntu-latest, wheel): .github#2

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
exercise-legs (ubuntu-latest, wheel): .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
exercise-legs (macos-latest, sdist): .github#2

- Due to capacity constraints, jobs targeting macOS arm64 runners may experience longer queue times.
exercise-legs (macos-latest, sdist): .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
exercise-legs (macos-latest, wheel): .github#2

- Due to capacity constraints, jobs targeting macOS arm64 runners may experience longer queue times.
exercise-legs (macos-latest, wheel): .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
exercise-legs (ubuntu-latest, sdist): .github#2

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
exercise-legs (ubuntu-latest, sdist): .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / prepare: .github#10

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / prepare: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / build-core / build-core: .github#5

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0BTP0agAAAACIQtJKm5FTQLUbV1bojc6rUEhMMzBFREdFMDQxOABFZGdl
qualify-ci / build-core / build-core: .github#7

! Failed to restore: Cache service responded with 400
qualify-ci / build-core / build-core: .github#25

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / build-core / build-core: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
exercise: .github#4

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
exercise: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / ace-page-group-isolation: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0aDP0agAAAAB0dJofL/zsSp+UTSSgEcPMUEhMMzBFREdFMDExNwBFZGdl
qualify-ci / ace-page-group-isolation: .github#9

! Failed to restore: Cache service responded with 400
qualify-ci / ace-page-group-isolation: .github#49

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / ace-page-group-isolation: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / visual-test: .github#2

X agents_final_rows_80x40: updated | changed pixels 11761/1019844 (1.153216%) | expected=tests/ace/tui/visual/snapshots/png/agents_final_rows_80x40.png
qualify-ci / visual-test: tests/ace/tui/visual/test_ace_png_snapshots_agents_final_rows.py#86

X agents_final_rows_60x40: updated | changed pixels 8667/769500 (1.126316%) | expected=tests/ace/tui/visual/snapshots/png/agents_final_rows_60x40.png
qualify-ci / visual-test: tests/ace/tui/visual/test_ace_png_snapshots_agents_final_rows.py#86

X Process completed with exit code 1.
qualify-ci / visual-test: .github#382

! Failed to restore: Cache service responded with 400
qualify-ci / visual-test: .github#49

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / visual-test: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / perf-floors: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0QDX0agAAAADc89K4ImAPR5uO4uh7cK+OQ0gxQUEyMDMwODE0MDM0AEVkZ2U=
qualify-ci / perf-floors: .github#9

! Failed to restore: Cache service responded with 400
qualify-ci / perf-floors: .github#49

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / perf-floors: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / tutorial-tests: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0RDP0agAAAACTIjNRdoBhQoq9lzCQEBnsTEFYRURHRTIwMTgARWRnZQ==
qualify-ci / tutorial-tests: .github#9

! Failed to restore: Cache service responded with 400
qualify-ci / tutorial-tests: .github#49

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / tutorial-tests: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache@v4, actions/checkout@v4, actions/download-artifact@v4, actions/setup-go@v5, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / lint: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0fDT0agAAAADC2ngjG3dlSLM7Bf2Jk2t2TEFYMzExMDAwMTExMDMxAEVkZ2U=
qualify-ci / lint: .github#7

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0fDT0agAAAADPYoWa3hrYT7TlABl8zPO+TEFYMzExMDAwMTE1MDE5AEVkZ2U=
qualify-ci / lint: .github#9

! Failed to restore: Cache service responded with 400
qualify-ci / lint: .github#52

! Failed to restore: Cache service responded with 400
qualify-ci / lint: .github#24

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / lint: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / test (3.13): .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0NEL0agAAAADFfLy0J7M2TbDeN/ibumMcQ08xRURHRTEyMTEARWRnZQ==
qualify-ci / test (3.13): .github#9

! Failed to restore: Cache service responded with 400
qualify-ci / test (3.13): .github#49

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / test (3.13): .github#1

Refreshing run status every 120 seconds. Press Ctrl+C to quit.

* release-please--branches--master Release sase-org/sase#322 · 42992733019
Triggered via workflow_dispatch about 1 hour ago

JOBS
✓ identity in 51s (ID 130429292693)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Assert source and version identity
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ build in 35s (ID 130429702498)
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
✓ qualify-prepare in 27s (ID 130429998624)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Download the sealed candidate build
  ✓ Bind the sealed candidate identity
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ exercise-legs (ubuntu-latest, wheel) in 1m4s (ID 130429998685)
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
✓ exercise-legs (macos-latest, sdist) in 1m52s (ID 130429998700)
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
✓ exercise-legs (macos-latest, wheel) in 1m55s (ID 130429998736)
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
✓ exercise-legs (ubuntu-latest, sdist) in 53s (ID 130429998828)
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
- stash (ID 130430001268)
✓ qualify-ci / prepare in 24s (ID 130430236751)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Validate qualification inputs
  ✓ Download the sealed candidate manifest
  ✓ Bind published identity from the sealed manifest
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
- qualify-ci / docs-build in 0s (ID 130430238633)
- qualify-ci / release-core-floor-smoke in 0s (ID 130430239945)
✓ qualify-ci / build-core / build-core in 7m24s (ID 130430445331)
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
✓ exercise in 24s (ID 130430922757)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Download the sealed build
  ✓ Download the leg evidence
  ✓ Merge the legs into one exercise observation
  - Stash the exercise observation on the draft release
  ✓ Upload the exercise observation artifact
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ qualify-ci / ace-page-group-isolation in 1m36s (ID 130433914911)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  ✓ Run ACE shared-page isolation lane
  ✓ Post Install visual dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
X qualify-ci / visual-test in 23m57s (ID 130433914913)
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
✓ qualify-ci / perf-floors in 9m28s (ID 130433914961)
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
✓ qualify-ci / test (3.12) in 1h32m5s (ID 130433915030)
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
✓ qualify-ci / tutorial-tests in 1m1s (ID 130433915035)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run tutorial tests
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ qualify-ci / lint in 6m14s (ID 130433915045)
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
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ qualify-ci / test (3.13) in 1h4m44s (ID 130433915166)
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
✓ qualify-ci / test (3.14) in 52m6s (ID 130433915280)
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
✓ qualify in 31s (ID 130477053141)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Download the sealed candidate build
  ✓ Evaluate the qualification evidence
  ✓ Upload the qualification observation
  - Attach the qualification observation to the draft
  ✓ Fail the verdict when qualification is red
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* publish (ID 130477312316)
  * Set up job

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
identity: .github#7

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
identity: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
build: .github#4

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0DTH0agAAAAD7rbAUNBT8RL9zAt1UenRYTVNQMzExMDAwMTA0MDI3AEVkZ2U=
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
exercise-legs (ubuntu-latest, wheel): .github#2

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
exercise-legs (ubuntu-latest, wheel): .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
exercise-legs (macos-latest, sdist): .github#2

- Due to capacity constraints, jobs targeting macOS arm64 runners may experience longer queue times.
exercise-legs (macos-latest, sdist): .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
exercise-legs (macos-latest, wheel): .github#2

- Due to capacity constraints, jobs targeting macOS arm64 runners may experience longer queue times.
exercise-legs (macos-latest, wheel): .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
exercise-legs (ubuntu-latest, sdist): .github#2

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
exercise-legs (ubuntu-latest, sdist): .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / prepare: .github#10

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / prepare: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / build-core / build-core: .github#5

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0BTP0agAAAACIQtJKm5FTQLUbV1bojc6rUEhMMzBFREdFMDQxOABFZGdl
qualify-ci / build-core / build-core: .github#7

! Failed to restore: Cache service responded with 400
qualify-ci / build-core / build-core: .github#25

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / build-core / build-core: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
exercise: .github#4

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
exercise: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / ace-page-group-isolation: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0aDP0agAAAAB0dJofL/zsSp+UTSSgEcPMUEhMMzBFREdFMDExNwBFZGdl
qualify-ci / ace-page-group-isolation: .github#9

! Failed to restore: Cache service responded with 400
qualify-ci / ace-page-group-isolation: .github#49

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / ace-page-group-isolation: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / visual-test: .github#2

X agents_final_rows_80x40: updated | changed pixels 11761/1019844 (1.153216%) | expected=tests/ace/tui/visual/snapshots/png/agents_final_rows_80x40.png
qualify-ci / visual-test: tests/ace/tui/visual/test_ace_png_snapshots_agents_final_rows.py#86

X agents_final_rows_60x40: updated | changed pixels 8667/769500 (1.126316%) | expected=tests/ace/tui/visual/snapshots/png/agents_final_rows_60x40.png
qualify-ci / visual-test: tests/ace/tui/visual/test_ace_png_snapshots_agents_final_rows.py#86

X Process completed with exit code 1.
qualify-ci / visual-test: .github#382

! Failed to restore: Cache service responded with 400
qualify-ci / visual-test: .github#49

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / visual-test: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / perf-floors: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0QDX0agAAAADc89K4ImAPR5uO4uh7cK+OQ0gxQUEyMDMwODE0MDM0AEVkZ2U=
qualify-ci / perf-floors: .github#9

! Failed to restore: Cache service responded with 400
qualify-ci / perf-floors: .github#49

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / perf-floors: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4, codecov/codecov-action@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / test (3.12): .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0nUj0agAAAADI/iwIt+glRIiwm8v//1HPTVNQMzExMDAwMTAzMDUzAEVkZ2U=
qualify-ci / test (3.12): .github#9

! Failed to restore: Cache service responded with 400
qualify-ci / test (3.12): .github#49

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / test (3.12): .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache@v4, actions/checkout@v4, actions/download-artifact@v4, actions/setup-go@v5, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / lint: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0fDT0agAAAADC2ngjG3dlSLM7Bf2Jk2t2TEFYMzExMDAwMTExMDMxAEVkZ2U=
qualify-ci / lint: .github#7

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0fDT0agAAAADPYoWa3hrYT7TlABl8zPO+TEFYMzExMDAwMTE1MDE5AEVkZ2U=
qualify-ci / lint: .github#9

! Failed to restore: Cache service responded with 400
qualify-ci / lint: .github#52

! Failed to restore: Cache service responded with 400
qualify-ci / lint: .github#24

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / lint: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / test (3.13): .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0NEL0agAAAADFfLy0J7M2TbDeN/ibumMcQ08xRURHRTEyMTEARWRnZQ==
qualify-ci / test (3.13): .github#9

! Failed to restore: Cache service responded with 400
qualify-ci / test (3.13): .github#49

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / test (3.13): .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify: .github#11

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify: .github#1

X release-please--branches--master Release sase-org/sase#322 · 42992733019
Triggered via workflow_dispatch about 1 hour ago

JOBS
✓ identity in 51s (ID 130429292693)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Assert source and version identity
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ build in 35s (ID 130429702498)
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
✓ qualify-prepare in 27s (ID 130429998624)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Download the sealed candidate build
  ✓ Bind the sealed candidate identity
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ exercise-legs (ubuntu-latest, wheel) in 1m4s (ID 130429998685)
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
✓ exercise-legs (macos-latest, sdist) in 1m52s (ID 130429998700)
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
✓ exercise-legs (macos-latest, wheel) in 1m55s (ID 130429998736)
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
✓ exercise-legs (ubuntu-latest, sdist) in 53s (ID 130429998828)
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
- stash (ID 130430001268)
✓ qualify-ci / prepare in 24s (ID 130430236751)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Validate qualification inputs
  ✓ Download the sealed candidate manifest
  ✓ Bind published identity from the sealed manifest
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
- qualify-ci / docs-build in 0s (ID 130430238633)
- qualify-ci / release-core-floor-smoke in 0s (ID 130430239945)
✓ qualify-ci / build-core / build-core in 7m24s (ID 130430445331)
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
✓ exercise in 24s (ID 130430922757)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Download the sealed build
  ✓ Download the leg evidence
  ✓ Merge the legs into one exercise observation
  - Stash the exercise observation on the draft release
  ✓ Upload the exercise observation artifact
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ qualify-ci / ace-page-group-isolation in 1m36s (ID 130433914911)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install visual dependencies
  ✓ Run ACE shared-page isolation lane
  ✓ Post Install visual dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
X qualify-ci / visual-test in 23m57s (ID 130433914913)
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
✓ qualify-ci / perf-floors in 9m28s (ID 130433914961)
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
✓ qualify-ci / test (3.12) in 1h32m5s (ID 130433915030)
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
✓ qualify-ci / tutorial-tests in 1m1s (ID 130433915035)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run tutorial tests
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ qualify-ci / lint in 6m14s (ID 130433915045)
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
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ qualify-ci / test (3.13) in 1h4m44s (ID 130433915166)
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
✓ qualify-ci / test (3.14) in 52m6s (ID 130433915280)
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
✓ qualify in 31s (ID 130477053141)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Download the sealed candidate build
  ✓ Evaluate the qualification evidence
  ✓ Upload the qualification observation
  - Attach the qualification observation to the draft
  ✓ Fail the verdict when qualification is red
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ publish in 29s (ID 130477312316)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run astral-sh/setup-uv@v4
  ✓ Refuse probes outside rehearse
  ✓ Stage the sealed dists from the build artifact
  - Stage the sealed dists from the draft release
  ✓ Normalize the manifest and staged paths
  ✓ Re-verify every digest against the sealed manifest
  ✓ Collect the generation evidence observations
  ✓ Download the evidence observation artifacts
  ✓ Run the promotion predicate for this candidate
  ✓ Fetch the PyPI file list for the version
  ✓ Compute the digest-checked upload plan
  - Copy only the planned uploads
  - Publish the missing files to PyPI
  ✓ Record the publication observation
  ✓ Upload the publication observation artifact
  ✓ Post Run astral-sh/setup-uv@v4
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
- confirm-install in 0s (ID 130477553780)
- confirm in 0s (ID 130477554743)

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
identity: .github#7

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
identity: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
build: .github#4

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0DTH0agAAAAD7rbAUNBT8RL9zAt1UenRYTVNQMzExMDAwMTA0MDI3AEVkZ2U=
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
exercise-legs (ubuntu-latest, wheel): .github#2

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
exercise-legs (ubuntu-latest, wheel): .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
exercise-legs (macos-latest, sdist): .github#2

- Due to capacity constraints, jobs targeting macOS arm64 runners may experience longer queue times.
exercise-legs (macos-latest, sdist): .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
exercise-legs (macos-latest, wheel): .github#2

- Due to capacity constraints, jobs targeting macOS arm64 runners may experience longer queue times.
exercise-legs (macos-latest, wheel): .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
exercise-legs (ubuntu-latest, sdist): .github#2

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
exercise-legs (ubuntu-latest, sdist): .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / prepare: .github#10

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / prepare: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / build-core / build-core: .github#5

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0BTP0agAAAACIQtJKm5FTQLUbV1bojc6rUEhMMzBFREdFMDQxOABFZGdl
qualify-ci / build-core / build-core: .github#7

! Failed to restore: Cache service responded with 400
qualify-ci / build-core / build-core: .github#25

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / build-core / build-core: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
exercise: .github#4

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
exercise: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / ace-page-group-isolation: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0aDP0agAAAAB0dJofL/zsSp+UTSSgEcPMUEhMMzBFREdFMDExNwBFZGdl
qualify-ci / ace-page-group-isolation: .github#9

! Failed to restore: Cache service responded with 400
qualify-ci / ace-page-group-isolation: .github#49

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / ace-page-group-isolation: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / visual-test: .github#2

X agents_final_rows_80x40: updated | changed pixels 11761/1019844 (1.153216%) | expected=tests/ace/tui/visual/snapshots/png/agents_final_rows_80x40.png
qualify-ci / visual-test: tests/ace/tui/visual/test_ace_png_snapshots_agents_final_rows.py#86

X agents_final_rows_60x40: updated | changed pixels 8667/769500 (1.126316%) | expected=tests/ace/tui/visual/snapshots/png/agents_final_rows_60x40.png
qualify-ci / visual-test: tests/ace/tui/visual/test_ace_png_snapshots_agents_final_rows.py#86

X Process completed with exit code 1.
qualify-ci / visual-test: .github#382

! Failed to restore: Cache service responded with 400
qualify-ci / visual-test: .github#49

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / visual-test: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / perf-floors: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0QDX0agAAAADc89K4ImAPR5uO4uh7cK+OQ0gxQUEyMDMwODE0MDM0AEVkZ2U=
qualify-ci / perf-floors: .github#9

! Failed to restore: Cache service responded with 400
qualify-ci / perf-floors: .github#49

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / perf-floors: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4, codecov/codecov-action@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / test (3.12): .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0nUj0agAAAADI/iwIt+glRIiwm8v//1HPTVNQMzExMDAwMTAzMDUzAEVkZ2U=
qualify-ci / test (3.12): .github#9

! Failed to restore: Cache service responded with 400
qualify-ci / test (3.12): .github#49

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / test (3.12): .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache@v4, actions/checkout@v4, actions/download-artifact@v4, actions/setup-go@v5, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / lint: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0fDT0agAAAADC2ngjG3dlSLM7Bf2Jk2t2TEFYMzExMDAwMTExMDMxAEVkZ2U=
qualify-ci / lint: .github#7

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0fDT0agAAAADPYoWa3hrYT7TlABl8zPO+TEFYMzExMDAwMTE1MDE5AEVkZ2U=
qualify-ci / lint: .github#9

! Failed to restore: Cache service responded with 400
qualify-ci / lint: .github#52

! Failed to restore: Cache service responded with 400
qualify-ci / lint: .github#24

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / lint: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify-ci / test (3.13): .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0NEL0agAAAADFfLy0J7M2TbDeN/ibumMcQ08xRURHRTEyMTEARWRnZQ==
qualify-ci / test (3.13): .github#9

! Failed to restore: Cache service responded with 400
qualify-ci / test (3.13): .github#49

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify-ci / test (3.13): .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
qualify: .github#11

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
qualify: .github#1

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
publish: .github#5

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>03kj0agAAAADLoILnWff8TLim45omD4nRU04xRURHRTIwMjAARWRnZQ==
publish: .github#7

! Failed to restore: Cache service responded with 400
publish: .github#24

- "The ubuntu-latest label will migrate to Ubuntu 26 beginning October 19, 2026. For more information, see https://github.com/actions/runner-images/issues/14748"
publish: .github#1


