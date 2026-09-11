# Chat History - ace-run (sase-xe.16.11.7.14.6.4.f0--mon-1)

- **TIMESTAMP:** 2026-09-11 07:10:50 EDT
- **MODEL:** claude/opus
- **AGENT:** sase-xe.16.11.7.14.6.4.f0--mon-1

## Prompt

sase monitor start --command 'gh run watch 34591495282 --repo sase-org/sase-core --exit-status 2>&1' --reason 'Wait for the guarded manual recovery run that builds the v0.34.0 wheel matrix and publishes sase-core-rs 0.34.0 to PyPI'

## Response

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Release-plz · 34591495282
Triggered via workflow_dispatch about 1 minute ago

JOBS
✓ Release-plz release in 19s (ID 103237584133)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz release output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ Publish plan in 4s (ID 103237677116)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Compute publish plan
  ✓ Post Checkout repository
  ✓ Complete job
✓ Release-plz PR in 26s (ID 103237677379)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz PR output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ sdist in 20s (ID 103237708043)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Build sdist
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* macos universal2 (ID 103237708069)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
* linux x86_64 (ID 103237708088)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test (x86_64 only)
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
* linux aarch64 (ID 103237708095)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test (x86_64 only)
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
* windows x86_64 (ID 103237708155)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
✓ Merge release PR in 3s (ID 103237804576)
  ✓ Set up job
  ✓ Resolve release PR
  - Wait for checks to register
  - Wait for checks to pass
  - Squash-merge release PR
  ✓ Complete job

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz release: .github#5

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Publish plan: .github#6

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz PR: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/setup-python@v5, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
sdist: .github#2

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Release-plz · 34591495282
Triggered via workflow_dispatch about 1 minute ago

JOBS
✓ Release-plz release in 19s (ID 103237584133)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz release output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ Publish plan in 4s (ID 103237677116)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Compute publish plan
  ✓ Post Checkout repository
  ✓ Complete job
✓ Release-plz PR in 26s (ID 103237677379)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz PR output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ sdist in 20s (ID 103237708043)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Build sdist
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* macos universal2 (ID 103237708069)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
* linux x86_64 (ID 103237708088)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test (x86_64 only)
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
* linux aarch64 (ID 103237708095)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test (x86_64 only)
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
* windows x86_64 (ID 103237708155)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
✓ Merge release PR in 3s (ID 103237804576)
  ✓ Set up job
  ✓ Resolve release PR
  - Wait for checks to register
  - Wait for checks to pass
  - Squash-merge release PR
  ✓ Complete job

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz release: .github#5

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Publish plan: .github#6

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz PR: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/setup-python@v5, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
sdist: .github#2

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Release-plz · 34591495282
Triggered via workflow_dispatch about 2 minutes ago

JOBS
✓ Release-plz release in 19s (ID 103237584133)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz release output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ Publish plan in 4s (ID 103237677116)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Compute publish plan
  ✓ Post Checkout repository
  ✓ Complete job
✓ Release-plz PR in 26s (ID 103237677379)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz PR output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ sdist in 20s (ID 103237708043)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Build sdist
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* macos universal2 (ID 103237708069)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
* linux x86_64 (ID 103237708088)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test (x86_64 only)
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
* linux aarch64 (ID 103237708095)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test (x86_64 only)
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
* windows x86_64 (ID 103237708155)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
✓ Merge release PR in 3s (ID 103237804576)
  ✓ Set up job
  ✓ Resolve release PR
  - Wait for checks to register
  - Wait for checks to pass
  - Squash-merge release PR
  ✓ Complete job

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz release: .github#5

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Publish plan: .github#6

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz PR: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/setup-python@v5, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
sdist: .github#2

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Release-plz · 34591495282
Triggered via workflow_dispatch about 2 minutes ago

JOBS
✓ Release-plz release in 19s (ID 103237584133)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz release output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ Publish plan in 4s (ID 103237677116)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Compute publish plan
  ✓ Post Checkout repository
  ✓ Complete job
✓ Release-plz PR in 26s (ID 103237677379)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz PR output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ sdist in 20s (ID 103237708043)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Build sdist
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* macos universal2 (ID 103237708069)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
* linux x86_64 (ID 103237708088)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test (x86_64 only)
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
* linux aarch64 (ID 103237708095)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test (x86_64 only)
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
* windows x86_64 (ID 103237708155)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
✓ Merge release PR in 3s (ID 103237804576)
  ✓ Set up job
  ✓ Resolve release PR
  - Wait for checks to register
  - Wait for checks to pass
  - Squash-merge release PR
  ✓ Complete job

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz release: .github#5

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Publish plan: .github#6

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz PR: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/setup-python@v5, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
sdist: .github#2

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Release-plz · 34591495282
Triggered via workflow_dispatch about 2 minutes ago

JOBS
✓ Release-plz release in 19s (ID 103237584133)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz release output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ Publish plan in 4s (ID 103237677116)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Compute publish plan
  ✓ Post Checkout repository
  ✓ Complete job
✓ Release-plz PR in 26s (ID 103237677379)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz PR output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ sdist in 20s (ID 103237708043)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Build sdist
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* macos universal2 (ID 103237708069)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
* linux x86_64 (ID 103237708088)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test (x86_64 only)
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
* linux aarch64 (ID 103237708095)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test (x86_64 only)
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
* windows x86_64 (ID 103237708155)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
✓ Merge release PR in 3s (ID 103237804576)
  ✓ Set up job
  ✓ Resolve release PR
  - Wait for checks to register
  - Wait for checks to pass
  - Squash-merge release PR
  ✓ Complete job

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz release: .github#5

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Publish plan: .github#6

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz PR: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/setup-python@v5, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
sdist: .github#2

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Release-plz · 34591495282
Triggered via workflow_dispatch about 2 minutes ago

JOBS
✓ Release-plz release in 19s (ID 103237584133)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz release output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ Publish plan in 4s (ID 103237677116)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Compute publish plan
  ✓ Post Checkout repository
  ✓ Complete job
✓ Release-plz PR in 26s (ID 103237677379)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz PR output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ sdist in 20s (ID 103237708043)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Build sdist
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* macos universal2 (ID 103237708069)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
* linux x86_64 (ID 103237708088)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test (x86_64 only)
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
* linux aarch64 (ID 103237708095)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test (x86_64 only)
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
* windows x86_64 (ID 103237708155)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
✓ Merge release PR in 3s (ID 103237804576)
  ✓ Set up job
  ✓ Resolve release PR
  - Wait for checks to register
  - Wait for checks to pass
  - Squash-merge release PR
  ✓ Complete job

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz release: .github#5

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Publish plan: .github#6

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz PR: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/setup-python@v5, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
sdist: .github#2

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Release-plz · 34591495282
Triggered via workflow_dispatch about 2 minutes ago

JOBS
✓ Release-plz release in 19s (ID 103237584133)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz release output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ Publish plan in 4s (ID 103237677116)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Compute publish plan
  ✓ Post Checkout repository
  ✓ Complete job
✓ Release-plz PR in 26s (ID 103237677379)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz PR output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ sdist in 20s (ID 103237708043)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Build sdist
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* macos universal2 (ID 103237708069)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
* linux x86_64 (ID 103237708088)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test (x86_64 only)
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
* linux aarch64 (ID 103237708095)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test (x86_64 only)
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
* windows x86_64 (ID 103237708155)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
✓ Merge release PR in 3s (ID 103237804576)
  ✓ Set up job
  ✓ Resolve release PR
  - Wait for checks to register
  - Wait for checks to pass
  - Squash-merge release PR
  ✓ Complete job

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz release: .github#5

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Publish plan: .github#6

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz PR: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/setup-python@v5, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
sdist: .github#2

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Release-plz · 34591495282
Triggered via workflow_dispatch about 2 minutes ago

JOBS
✓ Release-plz release in 19s (ID 103237584133)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz release output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ Publish plan in 4s (ID 103237677116)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Compute publish plan
  ✓ Post Checkout repository
  ✓ Complete job
✓ Release-plz PR in 26s (ID 103237677379)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz PR output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ sdist in 20s (ID 103237708043)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Build sdist
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* macos universal2 (ID 103237708069)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
* linux x86_64 (ID 103237708088)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test (x86_64 only)
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
* linux aarch64 (ID 103237708095)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test (x86_64 only)
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
* windows x86_64 (ID 103237708155)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
✓ Merge release PR in 3s (ID 103237804576)
  ✓ Set up job
  ✓ Resolve release PR
  - Wait for checks to register
  - Wait for checks to pass
  - Squash-merge release PR
  ✓ Complete job

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz release: .github#5

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Publish plan: .github#6

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz PR: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/setup-python@v5, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
sdist: .github#2

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Release-plz · 34591495282
Triggered via workflow_dispatch about 2 minutes ago

JOBS
✓ Release-plz release in 19s (ID 103237584133)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz release output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ Publish plan in 4s (ID 103237677116)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Compute publish plan
  ✓ Post Checkout repository
  ✓ Complete job
✓ Release-plz PR in 26s (ID 103237677379)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz PR output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ sdist in 20s (ID 103237708043)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Build sdist
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* macos universal2 (ID 103237708069)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
* linux x86_64 (ID 103237708088)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test (x86_64 only)
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
* linux aarch64 (ID 103237708095)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test (x86_64 only)
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
* windows x86_64 (ID 103237708155)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
✓ Merge release PR in 3s (ID 103237804576)
  ✓ Set up job
  ✓ Resolve release PR
  - Wait for checks to register
  - Wait for checks to pass
  - Squash-merge release PR
  ✓ Complete job

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz release: .github#5

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Publish plan: .github#6

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz PR: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/setup-python@v5, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
sdist: .github#2

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Release-plz · 34591495282
Triggered via workflow_dispatch about 2 minutes ago

JOBS
✓ Release-plz release in 19s (ID 103237584133)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz release output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ Publish plan in 4s (ID 103237677116)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Compute publish plan
  ✓ Post Checkout repository
  ✓ Complete job
✓ Release-plz PR in 26s (ID 103237677379)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz PR output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ sdist in 20s (ID 103237708043)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Build sdist
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* macos universal2 (ID 103237708069)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
* linux x86_64 (ID 103237708088)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test (x86_64 only)
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
* linux aarch64 (ID 103237708095)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test (x86_64 only)
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
* windows x86_64 (ID 103237708155)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
✓ Merge release PR in 3s (ID 103237804576)
  ✓ Set up job
  ✓ Resolve release PR
  - Wait for checks to register
  - Wait for checks to pass
  - Squash-merge release PR
  ✓ Complete job

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz release: .github#5

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Publish plan: .github#6

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz PR: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/setup-python@v5, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
sdist: .github#2

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Release-plz · 34591495282
Triggered via workflow_dispatch about 2 minutes ago

JOBS
✓ Release-plz release in 19s (ID 103237584133)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz release output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ Publish plan in 4s (ID 103237677116)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Compute publish plan
  ✓ Post Checkout repository
  ✓ Complete job
✓ Release-plz PR in 26s (ID 103237677379)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz PR output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ sdist in 20s (ID 103237708043)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Build sdist
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* macos universal2 (ID 103237708069)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
* linux x86_64 (ID 103237708088)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test (x86_64 only)
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
* linux aarch64 (ID 103237708095)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test (x86_64 only)
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
* windows x86_64 (ID 103237708155)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
✓ Merge release PR in 3s (ID 103237804576)
  ✓ Set up job
  ✓ Resolve release PR
  - Wait for checks to register
  - Wait for checks to pass
  - Squash-merge release PR
  ✓ Complete job

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz release: .github#5

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Publish plan: .github#6

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz PR: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/setup-python@v5, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
sdist: .github#2

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Release-plz · 34591495282
Triggered via workflow_dispatch about 2 minutes ago

JOBS
✓ Release-plz release in 19s (ID 103237584133)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz release output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ Publish plan in 4s (ID 103237677116)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Compute publish plan
  ✓ Post Checkout repository
  ✓ Complete job
✓ Release-plz PR in 26s (ID 103237677379)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz PR output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ sdist in 20s (ID 103237708043)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Build sdist
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* macos universal2 (ID 103237708069)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
* linux x86_64 (ID 103237708088)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test (x86_64 only)
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
* linux aarch64 (ID 103237708095)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test (x86_64 only)
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
* windows x86_64 (ID 103237708155)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
✓ Merge release PR in 3s (ID 103237804576)
  ✓ Set up job
  ✓ Resolve release PR
  - Wait for checks to register
  - Wait for checks to pass
  - Squash-merge release PR
  ✓ Complete job

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz release: .github#5

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Publish plan: .github#6

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz PR: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/setup-python@v5, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
sdist: .github#2

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Release-plz · 34591495282
Triggered via workflow_dispatch about 2 minutes ago

JOBS
✓ Release-plz release in 19s (ID 103237584133)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz release output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ Publish plan in 4s (ID 103237677116)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Compute publish plan
  ✓ Post Checkout repository
  ✓ Complete job
✓ Release-plz PR in 26s (ID 103237677379)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz PR output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ sdist in 20s (ID 103237708043)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Build sdist
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* macos universal2 (ID 103237708069)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
* linux x86_64 (ID 103237708088)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test (x86_64 only)
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
* linux aarch64 (ID 103237708095)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test (x86_64 only)
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
* windows x86_64 (ID 103237708155)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
✓ Merge release PR in 3s (ID 103237804576)
  ✓ Set up job
  ✓ Resolve release PR
  - Wait for checks to register
  - Wait for checks to pass
  - Squash-merge release PR
  ✓ Complete job

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz release: .github#5

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Publish plan: .github#6

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz PR: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/setup-python@v5, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
sdist: .github#2

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Release-plz · 34591495282
Triggered via workflow_dispatch about 2 minutes ago

JOBS
✓ Release-plz release in 19s (ID 103237584133)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz release output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ Publish plan in 4s (ID 103237677116)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Compute publish plan
  ✓ Post Checkout repository
  ✓ Complete job
✓ Release-plz PR in 26s (ID 103237677379)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz PR output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ sdist in 20s (ID 103237708043)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Build sdist
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* macos universal2 (ID 103237708069)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
* linux x86_64 (ID 103237708088)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test (x86_64 only)
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
* linux aarch64 (ID 103237708095)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test (x86_64 only)
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
* windows x86_64 (ID 103237708155)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
✓ Merge release PR in 3s (ID 103237804576)
  ✓ Set up job
  ✓ Resolve release PR
  - Wait for checks to register
  - Wait for checks to pass
  - Squash-merge release PR
  ✓ Complete job

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz release: .github#5

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Publish plan: .github#6

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz PR: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/setup-python@v5, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
sdist: .github#2

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Release-plz · 34591495282
Triggered via workflow_dispatch about 2 minutes ago

JOBS
✓ Release-plz release in 19s (ID 103237584133)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz release output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ Publish plan in 4s (ID 103237677116)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Compute publish plan
  ✓ Post Checkout repository
  ✓ Complete job
✓ Release-plz PR in 26s (ID 103237677379)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz PR output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ sdist in 20s (ID 103237708043)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Build sdist
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* macos universal2 (ID 103237708069)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
* linux x86_64 (ID 103237708088)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test (x86_64 only)
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
* linux aarch64 (ID 103237708095)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test (x86_64 only)
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
* windows x86_64 (ID 103237708155)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
✓ Merge release PR in 3s (ID 103237804576)
  ✓ Set up job
  ✓ Resolve release PR
  - Wait for checks to register
  - Wait for checks to pass
  - Squash-merge release PR
  ✓ Complete job

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz release: .github#5

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Publish plan: .github#6

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz PR: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/setup-python@v5, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
sdist: .github#2

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Release-plz · 34591495282
Triggered via workflow_dispatch about 2 minutes ago

JOBS
✓ Release-plz release in 19s (ID 103237584133)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz release output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ Publish plan in 4s (ID 103237677116)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Compute publish plan
  ✓ Post Checkout repository
  ✓ Complete job
✓ Release-plz PR in 26s (ID 103237677379)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz PR output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ sdist in 20s (ID 103237708043)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Build sdist
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* macos universal2 (ID 103237708069)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
* linux x86_64 (ID 103237708088)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test (x86_64 only)
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
* linux aarch64 (ID 103237708095)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test (x86_64 only)
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
* windows x86_64 (ID 103237708155)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
✓ Merge release PR in 3s (ID 103237804576)
  ✓ Set up job
  ✓ Resolve release PR
  - Wait for checks to register
  - Wait for checks to pass
  - Squash-merge release PR
  ✓ Complete job

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz release: .github#5

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Publish plan: .github#6

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz PR: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/setup-python@v5, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
sdist: .github#2

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Release-plz · 34591495282
Triggered via workflow_dispatch about 3 minutes ago

JOBS
✓ Release-plz release in 19s (ID 103237584133)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz release output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ Publish plan in 4s (ID 103237677116)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Compute publish plan
  ✓ Post Checkout repository
  ✓ Complete job
✓ Release-plz PR in 26s (ID 103237677379)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz PR output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ sdist in 20s (ID 103237708043)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Build sdist
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* macos universal2 (ID 103237708069)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
* linux x86_64 (ID 103237708088)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test (x86_64 only)
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
* linux aarch64 (ID 103237708095)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test (x86_64 only)
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
* windows x86_64 (ID 103237708155)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
✓ Merge release PR in 3s (ID 103237804576)
  ✓ Set up job
  ✓ Resolve release PR
  - Wait for checks to register
  - Wait for checks to pass
  - Squash-merge release PR
  ✓ Complete job

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz release: .github#5

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Publish plan: .github#6

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz PR: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/setup-python@v5, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
sdist: .github#2

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Release-plz · 34591495282
Triggered via workflow_dispatch about 3 minutes ago

JOBS
✓ Release-plz release in 19s (ID 103237584133)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz release output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ Publish plan in 4s (ID 103237677116)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Compute publish plan
  ✓ Post Checkout repository
  ✓ Complete job
✓ Release-plz PR in 26s (ID 103237677379)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz PR output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ sdist in 20s (ID 103237708043)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Build sdist
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* macos universal2 (ID 103237708069)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
* linux x86_64 (ID 103237708088)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test (x86_64 only)
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
* linux aarch64 (ID 103237708095)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test (x86_64 only)
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
* windows x86_64 (ID 103237708155)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
✓ Merge release PR in 3s (ID 103237804576)
  ✓ Set up job
  ✓ Resolve release PR
  - Wait for checks to register
  - Wait for checks to pass
  - Squash-merge release PR
  ✓ Complete job

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz release: .github#5

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Publish plan: .github#6

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz PR: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/setup-python@v5, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
sdist: .github#2

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Release-plz · 34591495282
Triggered via workflow_dispatch about 3 minutes ago

JOBS
✓ Release-plz release in 19s (ID 103237584133)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz release output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ Publish plan in 4s (ID 103237677116)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Compute publish plan
  ✓ Post Checkout repository
  ✓ Complete job
✓ Release-plz PR in 26s (ID 103237677379)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz PR output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ sdist in 20s (ID 103237708043)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Build sdist
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* macos universal2 (ID 103237708069)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
* linux x86_64 (ID 103237708088)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test (x86_64 only)
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
* linux aarch64 (ID 103237708095)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test (x86_64 only)
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
* windows x86_64 (ID 103237708155)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
✓ Merge release PR in 3s (ID 103237804576)
  ✓ Set up job
  ✓ Resolve release PR
  - Wait for checks to register
  - Wait for checks to pass
  - Squash-merge release PR
  ✓ Complete job

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz release: .github#5

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Publish plan: .github#6

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz PR: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/setup-python@v5, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
sdist: .github#2

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Release-plz · 34591495282
Triggered via workflow_dispatch about 3 minutes ago

JOBS
✓ Release-plz release in 19s (ID 103237584133)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz release output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ Publish plan in 4s (ID 103237677116)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Compute publish plan
  ✓ Post Checkout repository
  ✓ Complete job
✓ Release-plz PR in 26s (ID 103237677379)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz PR output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ sdist in 20s (ID 103237708043)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Build sdist
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* macos universal2 (ID 103237708069)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
* linux x86_64 (ID 103237708088)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test (x86_64 only)
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
* linux aarch64 (ID 103237708095)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test (x86_64 only)
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
* windows x86_64 (ID 103237708155)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
✓ Merge release PR in 3s (ID 103237804576)
  ✓ Set up job
  ✓ Resolve release PR
  - Wait for checks to register
  - Wait for checks to pass
  - Squash-merge release PR
  ✓ Complete job

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz release: .github#5

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Publish plan: .github#6

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz PR: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/setup-python@v5, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
sdist: .github#2

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Release-plz · 34591495282
Triggered via workflow_dispatch about 3 minutes ago

JOBS
✓ Release-plz release in 19s (ID 103237584133)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz release output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ Publish plan in 4s (ID 103237677116)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Compute publish plan
  ✓ Post Checkout repository
  ✓ Complete job
✓ Release-plz PR in 26s (ID 103237677379)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz PR output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ sdist in 20s (ID 103237708043)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Build sdist
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* macos universal2 (ID 103237708069)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
* linux x86_64 (ID 103237708088)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test (x86_64 only)
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
* linux aarch64 (ID 103237708095)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test (x86_64 only)
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
* windows x86_64 (ID 103237708155)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
✓ Merge release PR in 3s (ID 103237804576)
  ✓ Set up job
  ✓ Resolve release PR
  - Wait for checks to register
  - Wait for checks to pass
  - Squash-merge release PR
  ✓ Complete job

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz release: .github#5

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Publish plan: .github#6

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz PR: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/setup-python@v5, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
sdist: .github#2

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Release-plz · 34591495282
Triggered via workflow_dispatch about 3 minutes ago

JOBS
✓ Release-plz release in 19s (ID 103237584133)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz release output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ Publish plan in 4s (ID 103237677116)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Compute publish plan
  ✓ Post Checkout repository
  ✓ Complete job
✓ Release-plz PR in 26s (ID 103237677379)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz PR output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ sdist in 20s (ID 103237708043)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Build sdist
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* macos universal2 (ID 103237708069)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
* linux x86_64 (ID 103237708088)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test (x86_64 only)
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
* linux aarch64 (ID 103237708095)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test (x86_64 only)
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
* windows x86_64 (ID 103237708155)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
✓ Merge release PR in 3s (ID 103237804576)
  ✓ Set up job
  ✓ Resolve release PR
  - Wait for checks to register
  - Wait for checks to pass
  - Squash-merge release PR
  ✓ Complete job

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz release: .github#5

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Publish plan: .github#6

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz PR: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/setup-python@v5, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
sdist: .github#2

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Release-plz · 34591495282
Triggered via workflow_dispatch about 3 minutes ago

JOBS
✓ Release-plz release in 19s (ID 103237584133)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz release output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ Publish plan in 4s (ID 103237677116)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Compute publish plan
  ✓ Post Checkout repository
  ✓ Complete job
✓ Release-plz PR in 26s (ID 103237677379)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz PR output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ sdist in 20s (ID 103237708043)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Build sdist
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* macos universal2 (ID 103237708069)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
* linux x86_64 (ID 103237708088)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test (x86_64 only)
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
* linux aarch64 (ID 103237708095)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test (x86_64 only)
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
* windows x86_64 (ID 103237708155)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
✓ Merge release PR in 3s (ID 103237804576)
  ✓ Set up job
  ✓ Resolve release PR
  - Wait for checks to register
  - Wait for checks to pass
  - Squash-merge release PR
  ✓ Complete job

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz release: .github#5

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Publish plan: .github#6

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz PR: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/setup-python@v5, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
sdist: .github#2

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Release-plz · 34591495282
Triggered via workflow_dispatch about 3 minutes ago

JOBS
✓ Release-plz release in 19s (ID 103237584133)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz release output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ Publish plan in 4s (ID 103237677116)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Compute publish plan
  ✓ Post Checkout repository
  ✓ Complete job
✓ Release-plz PR in 26s (ID 103237677379)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz PR output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ sdist in 20s (ID 103237708043)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Build sdist
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* macos universal2 (ID 103237708069)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
* linux x86_64 (ID 103237708088)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test (x86_64 only)
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
* linux aarch64 (ID 103237708095)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test (x86_64 only)
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
* windows x86_64 (ID 103237708155)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
✓ Merge release PR in 3s (ID 103237804576)
  ✓ Set up job
  ✓ Resolve release PR
  - Wait for checks to register
  - Wait for checks to pass
  - Squash-merge release PR
  ✓ Complete job

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz release: .github#5

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Publish plan: .github#6

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz PR: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/setup-python@v5, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
sdist: .github#2

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Release-plz · 34591495282
Triggered via workflow_dispatch about 3 minutes ago

JOBS
✓ Release-plz release in 19s (ID 103237584133)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz release output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ Publish plan in 4s (ID 103237677116)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Compute publish plan
  ✓ Post Checkout repository
  ✓ Complete job
✓ Release-plz PR in 26s (ID 103237677379)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz PR output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ sdist in 20s (ID 103237708043)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Build sdist
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* macos universal2 (ID 103237708069)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
* linux x86_64 (ID 103237708088)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test (x86_64 only)
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
* linux aarch64 (ID 103237708095)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test (x86_64 only)
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
* windows x86_64 (ID 103237708155)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
✓ Merge release PR in 3s (ID 103237804576)
  ✓ Set up job
  ✓ Resolve release PR
  - Wait for checks to register
  - Wait for checks to pass
  - Squash-merge release PR
  ✓ Complete job

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz release: .github#5

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Publish plan: .github#6

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz PR: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/setup-python@v5, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
sdist: .github#2

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Release-plz · 34591495282
Triggered via workflow_dispatch about 3 minutes ago

JOBS
✓ Release-plz release in 19s (ID 103237584133)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz release output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ Publish plan in 4s (ID 103237677116)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Compute publish plan
  ✓ Post Checkout repository
  ✓ Complete job
✓ Release-plz PR in 26s (ID 103237677379)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz PR output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ sdist in 20s (ID 103237708043)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Build sdist
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* macos universal2 (ID 103237708069)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
* linux x86_64 (ID 103237708088)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test (x86_64 only)
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
* linux aarch64 (ID 103237708095)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test (x86_64 only)
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
* windows x86_64 (ID 103237708155)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
✓ Merge release PR in 3s (ID 103237804576)
  ✓ Set up job
  ✓ Resolve release PR
  - Wait for checks to register
  - Wait for checks to pass
  - Squash-merge release PR
  ✓ Complete job

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz release: .github#5

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Publish plan: .github#6

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz PR: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/setup-python@v5, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
sdist: .github#2

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Release-plz · 34591495282
Triggered via workflow_dispatch about 3 minutes ago

JOBS
✓ Release-plz release in 19s (ID 103237584133)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz release output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ Publish plan in 4s (ID 103237677116)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Compute publish plan
  ✓ Post Checkout repository
  ✓ Complete job
✓ Release-plz PR in 26s (ID 103237677379)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz PR output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ sdist in 20s (ID 103237708043)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Build sdist
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* macos universal2 (ID 103237708069)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
* linux x86_64 (ID 103237708088)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test (x86_64 only)
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
* linux aarch64 (ID 103237708095)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test (x86_64 only)
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
* windows x86_64 (ID 103237708155)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
✓ Merge release PR in 3s (ID 103237804576)
  ✓ Set up job
  ✓ Resolve release PR
  - Wait for checks to register
  - Wait for checks to pass
  - Squash-merge release PR
  ✓ Complete job

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz release: .github#5

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Publish plan: .github#6

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz PR: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/setup-python@v5, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
sdist: .github#2

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Release-plz · 34591495282
Triggered via workflow_dispatch about 3 minutes ago

JOBS
✓ Release-plz release in 19s (ID 103237584133)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz release output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ Publish plan in 4s (ID 103237677116)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Compute publish plan
  ✓ Post Checkout repository
  ✓ Complete job
✓ Release-plz PR in 26s (ID 103237677379)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz PR output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ sdist in 20s (ID 103237708043)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Build sdist
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* macos universal2 (ID 103237708069)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
* linux x86_64 (ID 103237708088)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test (x86_64 only)
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
* linux aarch64 (ID 103237708095)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test (x86_64 only)
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
* windows x86_64 (ID 103237708155)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
✓ Merge release PR in 3s (ID 103237804576)
  ✓ Set up job
  ✓ Resolve release PR
  - Wait for checks to register
  - Wait for checks to pass
  - Squash-merge release PR
  ✓ Complete job

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz release: .github#5

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Publish plan: .github#6

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz PR: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/setup-python@v5, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
sdist: .github#2

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Release-plz · 34591495282
Triggered via workflow_dispatch about 3 minutes ago

JOBS
✓ Release-plz release in 19s (ID 103237584133)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz release output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ Publish plan in 4s (ID 103237677116)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Compute publish plan
  ✓ Post Checkout repository
  ✓ Complete job
✓ Release-plz PR in 26s (ID 103237677379)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz PR output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ sdist in 20s (ID 103237708043)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Build sdist
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* macos universal2 (ID 103237708069)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
* linux x86_64 (ID 103237708088)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test (x86_64 only)
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
* linux aarch64 (ID 103237708095)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test (x86_64 only)
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
* windows x86_64 (ID 103237708155)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
✓ Merge release PR in 3s (ID 103237804576)
  ✓ Set up job
  ✓ Resolve release PR
  - Wait for checks to register
  - Wait for checks to pass
  - Squash-merge release PR
  ✓ Complete job

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz release: .github#5

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Publish plan: .github#6

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz PR: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/setup-python@v5, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
sdist: .github#2

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Release-plz · 34591495282
Triggered via workflow_dispatch about 3 minutes ago

JOBS
✓ Release-plz release in 19s (ID 103237584133)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz release output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ Publish plan in 4s (ID 103237677116)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Compute publish plan
  ✓ Post Checkout repository
  ✓ Complete job
✓ Release-plz PR in 26s (ID 103237677379)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz PR output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ sdist in 20s (ID 103237708043)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Build sdist
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* macos universal2 (ID 103237708069)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
* linux x86_64 (ID 103237708088)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test (x86_64 only)
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
* linux aarch64 (ID 103237708095)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test (x86_64 only)
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
* windows x86_64 (ID 103237708155)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
✓ Merge release PR in 3s (ID 103237804576)
  ✓ Set up job
  ✓ Resolve release PR
  - Wait for checks to register
  - Wait for checks to pass
  - Squash-merge release PR
  ✓ Complete job

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz release: .github#5

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Publish plan: .github#6

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz PR: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/setup-python@v5, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
sdist: .github#2

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Release-plz · 34591495282
Triggered via workflow_dispatch about 4 minutes ago

JOBS
✓ Release-plz release in 19s (ID 103237584133)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz release output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ Publish plan in 4s (ID 103237677116)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Compute publish plan
  ✓ Post Checkout repository
  ✓ Complete job
✓ Release-plz PR in 26s (ID 103237677379)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz PR output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ sdist in 20s (ID 103237708043)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Build sdist
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* macos universal2 (ID 103237708069)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
* linux x86_64 (ID 103237708088)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test (x86_64 only)
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
* linux aarch64 (ID 103237708095)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test (x86_64 only)
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
* windows x86_64 (ID 103237708155)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
✓ Merge release PR in 3s (ID 103237804576)
  ✓ Set up job
  ✓ Resolve release PR
  - Wait for checks to register
  - Wait for checks to pass
  - Squash-merge release PR
  ✓ Complete job

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz release: .github#5

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Publish plan: .github#6

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz PR: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/setup-python@v5, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
sdist: .github#2

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Release-plz · 34591495282
Triggered via workflow_dispatch about 4 minutes ago

JOBS
✓ Release-plz release in 19s (ID 103237584133)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz release output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ Publish plan in 4s (ID 103237677116)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Compute publish plan
  ✓ Post Checkout repository
  ✓ Complete job
✓ Release-plz PR in 26s (ID 103237677379)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz PR output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ sdist in 20s (ID 103237708043)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Build sdist
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* macos universal2 (ID 103237708069)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
* linux x86_64 (ID 103237708088)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test (x86_64 only)
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
* linux aarch64 (ID 103237708095)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test (x86_64 only)
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
* windows x86_64 (ID 103237708155)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
✓ Merge release PR in 3s (ID 103237804576)
  ✓ Set up job
  ✓ Resolve release PR
  - Wait for checks to register
  - Wait for checks to pass
  - Squash-merge release PR
  ✓ Complete job

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz release: .github#5

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Publish plan: .github#6

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz PR: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/setup-python@v5, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
sdist: .github#2

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Release-plz · 34591495282
Triggered via workflow_dispatch about 4 minutes ago

JOBS
✓ Release-plz release in 19s (ID 103237584133)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz release output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ Publish plan in 4s (ID 103237677116)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Compute publish plan
  ✓ Post Checkout repository
  ✓ Complete job
✓ Release-plz PR in 26s (ID 103237677379)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz PR output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ sdist in 20s (ID 103237708043)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Build sdist
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* macos universal2 (ID 103237708069)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
* linux x86_64 (ID 103237708088)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test (x86_64 only)
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
* linux aarch64 (ID 103237708095)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test (x86_64 only)
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
* windows x86_64 (ID 103237708155)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
✓ Merge release PR in 3s (ID 103237804576)
  ✓ Set up job
  ✓ Resolve release PR
  - Wait for checks to register
  - Wait for checks to pass
  - Squash-merge release PR
  ✓ Complete job

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz release: .github#5

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Publish plan: .github#6

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz PR: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/setup-python@v5, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
sdist: .github#2

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Release-plz · 34591495282
Triggered via workflow_dispatch about 4 minutes ago

JOBS
✓ Release-plz release in 19s (ID 103237584133)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz release output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ Publish plan in 4s (ID 103237677116)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Compute publish plan
  ✓ Post Checkout repository
  ✓ Complete job
✓ Release-plz PR in 26s (ID 103237677379)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz PR output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ sdist in 20s (ID 103237708043)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Build sdist
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* macos universal2 (ID 103237708069)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
* linux x86_64 (ID 103237708088)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test (x86_64 only)
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
* linux aarch64 (ID 103237708095)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test (x86_64 only)
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
* windows x86_64 (ID 103237708155)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
✓ Merge release PR in 3s (ID 103237804576)
  ✓ Set up job
  ✓ Resolve release PR
  - Wait for checks to register
  - Wait for checks to pass
  - Squash-merge release PR
  ✓ Complete job

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz release: .github#5

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Publish plan: .github#6

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz PR: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/setup-python@v5, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
sdist: .github#2

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Release-plz · 34591495282
Triggered via workflow_dispatch about 4 minutes ago

JOBS
✓ Release-plz release in 19s (ID 103237584133)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz release output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ Publish plan in 4s (ID 103237677116)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Compute publish plan
  ✓ Post Checkout repository
  ✓ Complete job
✓ Release-plz PR in 26s (ID 103237677379)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz PR output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ sdist in 20s (ID 103237708043)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Build sdist
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* macos universal2 (ID 103237708069)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
* linux x86_64 (ID 103237708088)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test (x86_64 only)
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
* linux aarch64 (ID 103237708095)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test (x86_64 only)
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
* windows x86_64 (ID 103237708155)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
✓ Merge release PR in 3s (ID 103237804576)
  ✓ Set up job
  ✓ Resolve release PR
  - Wait for checks to register
  - Wait for checks to pass
  - Squash-merge release PR
  ✓ Complete job

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz release: .github#5

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Publish plan: .github#6

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz PR: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/setup-python@v5, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
sdist: .github#2

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Release-plz · 34591495282
Triggered via workflow_dispatch about 4 minutes ago

JOBS
✓ Release-plz release in 19s (ID 103237584133)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz release output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ Publish plan in 4s (ID 103237677116)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Compute publish plan
  ✓ Post Checkout repository
  ✓ Complete job
✓ Release-plz PR in 26s (ID 103237677379)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz PR output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ sdist in 20s (ID 103237708043)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Build sdist
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* macos universal2 (ID 103237708069)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
* linux x86_64 (ID 103237708088)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test (x86_64 only)
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
* linux aarch64 (ID 103237708095)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test (x86_64 only)
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
* windows x86_64 (ID 103237708155)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
✓ Merge release PR in 3s (ID 103237804576)
  ✓ Set up job
  ✓ Resolve release PR
  - Wait for checks to register
  - Wait for checks to pass
  - Squash-merge release PR
  ✓ Complete job

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz release: .github#5

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Publish plan: .github#6

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz PR: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/setup-python@v5, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
sdist: .github#2

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Release-plz · 34591495282
Triggered via workflow_dispatch about 4 minutes ago

JOBS
✓ Release-plz release in 19s (ID 103237584133)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz release output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ Publish plan in 4s (ID 103237677116)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Compute publish plan
  ✓ Post Checkout repository
  ✓ Complete job
✓ Release-plz PR in 26s (ID 103237677379)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz PR output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ sdist in 20s (ID 103237708043)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Build sdist
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* macos universal2 (ID 103237708069)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
* linux x86_64 (ID 103237708088)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test (x86_64 only)
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
* linux aarch64 (ID 103237708095)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test (x86_64 only)
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
* windows x86_64 (ID 103237708155)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
✓ Merge release PR in 3s (ID 103237804576)
  ✓ Set up job
  ✓ Resolve release PR
  - Wait for checks to register
  - Wait for checks to pass
  - Squash-merge release PR
  ✓ Complete job

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz release: .github#5

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Publish plan: .github#6

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz PR: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/setup-python@v5, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
sdist: .github#2

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Release-plz · 34591495282
Triggered via workflow_dispatch about 4 minutes ago

JOBS
✓ Release-plz release in 19s (ID 103237584133)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz release output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ Publish plan in 4s (ID 103237677116)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Compute publish plan
  ✓ Post Checkout repository
  ✓ Complete job
✓ Release-plz PR in 26s (ID 103237677379)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz PR output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ sdist in 20s (ID 103237708043)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Build sdist
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* macos universal2 (ID 103237708069)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
* linux x86_64 (ID 103237708088)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test (x86_64 only)
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
* linux aarch64 (ID 103237708095)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test (x86_64 only)
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
* windows x86_64 (ID 103237708155)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
✓ Merge release PR in 3s (ID 103237804576)
  ✓ Set up job
  ✓ Resolve release PR
  - Wait for checks to register
  - Wait for checks to pass
  - Squash-merge release PR
  ✓ Complete job

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz release: .github#5

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Publish plan: .github#6

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz PR: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/setup-python@v5, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
sdist: .github#2

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Release-plz · 34591495282
Triggered via workflow_dispatch about 4 minutes ago

JOBS
✓ Release-plz release in 19s (ID 103237584133)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz release output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ Publish plan in 4s (ID 103237677116)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Compute publish plan
  ✓ Post Checkout repository
  ✓ Complete job
✓ Release-plz PR in 26s (ID 103237677379)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz PR output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ sdist in 20s (ID 103237708043)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Build sdist
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* macos universal2 (ID 103237708069)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
* linux x86_64 (ID 103237708088)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test (x86_64 only)
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
* linux aarch64 (ID 103237708095)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test (x86_64 only)
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
* windows x86_64 (ID 103237708155)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
✓ Merge release PR in 3s (ID 103237804576)
  ✓ Set up job
  ✓ Resolve release PR
  - Wait for checks to register
  - Wait for checks to pass
  - Squash-merge release PR
  ✓ Complete job

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz release: .github#5

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Publish plan: .github#6

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz PR: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/setup-python@v5, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
sdist: .github#2

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Release-plz · 34591495282
Triggered via workflow_dispatch about 4 minutes ago

JOBS
✓ Release-plz release in 19s (ID 103237584133)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz release output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ Publish plan in 4s (ID 103237677116)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Compute publish plan
  ✓ Post Checkout repository
  ✓ Complete job
✓ Release-plz PR in 26s (ID 103237677379)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz PR output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ sdist in 20s (ID 103237708043)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Build sdist
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* macos universal2 (ID 103237708069)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
* linux x86_64 (ID 103237708088)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test (x86_64 only)
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
* linux aarch64 (ID 103237708095)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test (x86_64 only)
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
* windows x86_64 (ID 103237708155)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
✓ Merge release PR in 3s (ID 103237804576)
  ✓ Set up job
  ✓ Resolve release PR
  - Wait for checks to register
  - Wait for checks to pass
  - Squash-merge release PR
  ✓ Complete job

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz release: .github#5

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Publish plan: .github#6

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz PR: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/setup-python@v5, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
sdist: .github#2

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Release-plz · 34591495282
Triggered via workflow_dispatch about 4 minutes ago

JOBS
✓ Release-plz release in 19s (ID 103237584133)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz release output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ Publish plan in 4s (ID 103237677116)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Compute publish plan
  ✓ Post Checkout repository
  ✓ Complete job
✓ Release-plz PR in 26s (ID 103237677379)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz PR output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ sdist in 20s (ID 103237708043)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Build sdist
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* macos universal2 (ID 103237708069)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
* linux x86_64 (ID 103237708088)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test (x86_64 only)
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
* linux aarch64 (ID 103237708095)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test (x86_64 only)
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
* windows x86_64 (ID 103237708155)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
✓ Merge release PR in 3s (ID 103237804576)
  ✓ Set up job
  ✓ Resolve release PR
  - Wait for checks to register
  - Wait for checks to pass
  - Squash-merge release PR
  ✓ Complete job

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz release: .github#5

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Publish plan: .github#6

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz PR: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/setup-python@v5, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
sdist: .github#2

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Release-plz · 34591495282
Triggered via workflow_dispatch about 4 minutes ago

JOBS
✓ Release-plz release in 19s (ID 103237584133)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz release output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ Publish plan in 4s (ID 103237677116)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Compute publish plan
  ✓ Post Checkout repository
  ✓ Complete job
✓ Release-plz PR in 26s (ID 103237677379)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz PR output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ sdist in 20s (ID 103237708043)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Build sdist
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* macos universal2 (ID 103237708069)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
* linux x86_64 (ID 103237708088)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test (x86_64 only)
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
* linux aarch64 (ID 103237708095)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test (x86_64 only)
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
* windows x86_64 (ID 103237708155)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
✓ Merge release PR in 3s (ID 103237804576)
  ✓ Set up job
  ✓ Resolve release PR
  - Wait for checks to register
  - Wait for checks to pass
  - Squash-merge release PR
  ✓ Complete job

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz release: .github#5

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Publish plan: .github#6

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz PR: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/setup-python@v5, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
sdist: .github#2

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Release-plz · 34591495282
Triggered via workflow_dispatch about 4 minutes ago

JOBS
✓ Release-plz release in 19s (ID 103237584133)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz release output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ Publish plan in 4s (ID 103237677116)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Compute publish plan
  ✓ Post Checkout repository
  ✓ Complete job
✓ Release-plz PR in 26s (ID 103237677379)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz PR output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ sdist in 20s (ID 103237708043)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Build sdist
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* macos universal2 (ID 103237708069)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
* linux x86_64 (ID 103237708088)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test (x86_64 only)
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
* linux aarch64 (ID 103237708095)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test (x86_64 only)
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
* windows x86_64 (ID 103237708155)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
✓ Merge release PR in 3s (ID 103237804576)
  ✓ Set up job
  ✓ Resolve release PR
  - Wait for checks to register
  - Wait for checks to pass
  - Squash-merge release PR
  ✓ Complete job

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz release: .github#5

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Publish plan: .github#6

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz PR: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/setup-python@v5, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
sdist: .github#2

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Release-plz · 34591495282
Triggered via workflow_dispatch about 4 minutes ago

JOBS
✓ Release-plz release in 19s (ID 103237584133)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz release output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ Publish plan in 4s (ID 103237677116)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Compute publish plan
  ✓ Post Checkout repository
  ✓ Complete job
✓ Release-plz PR in 26s (ID 103237677379)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz PR output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ sdist in 20s (ID 103237708043)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Build sdist
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* macos universal2 (ID 103237708069)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
* linux x86_64 (ID 103237708088)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test (x86_64 only)
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
* linux aarch64 (ID 103237708095)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test (x86_64 only)
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
* windows x86_64 (ID 103237708155)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
✓ Merge release PR in 3s (ID 103237804576)
  ✓ Set up job
  ✓ Resolve release PR
  - Wait for checks to register
  - Wait for checks to pass
  - Squash-merge release PR
  ✓ Complete job

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz release: .github#5

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Publish plan: .github#6

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz PR: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/setup-python@v5, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
sdist: .github#2

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Release-plz · 34591495282
Triggered via workflow_dispatch about 4 minutes ago

JOBS
✓ Release-plz release in 19s (ID 103237584133)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz release output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ Publish plan in 4s (ID 103237677116)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Compute publish plan
  ✓ Post Checkout repository
  ✓ Complete job
✓ Release-plz PR in 26s (ID 103237677379)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz PR output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ sdist in 20s (ID 103237708043)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Build sdist
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* macos universal2 (ID 103237708069)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
* linux x86_64 (ID 103237708088)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test (x86_64 only)
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
* linux aarch64 (ID 103237708095)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test (x86_64 only)
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
* windows x86_64 (ID 103237708155)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
✓ Merge release PR in 3s (ID 103237804576)
  ✓ Set up job
  ✓ Resolve release PR
  - Wait for checks to register
  - Wait for checks to pass
  - Squash-merge release PR
  ✓ Complete job

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz release: .github#5

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Publish plan: .github#6

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz PR: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/setup-python@v5, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
sdist: .github#2

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Release-plz · 34591495282
Triggered via workflow_dispatch about 5 minutes ago

JOBS
✓ Release-plz release in 19s (ID 103237584133)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz release output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ Publish plan in 4s (ID 103237677116)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Compute publish plan
  ✓ Post Checkout repository
  ✓ Complete job
✓ Release-plz PR in 26s (ID 103237677379)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz PR output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ sdist in 20s (ID 103237708043)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Build sdist
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* macos universal2 (ID 103237708069)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
* linux x86_64 (ID 103237708088)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test (x86_64 only)
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
* linux aarch64 (ID 103237708095)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test (x86_64 only)
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
* windows x86_64 (ID 103237708155)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
✓ Merge release PR in 3s (ID 103237804576)
  ✓ Set up job
  ✓ Resolve release PR
  - Wait for checks to register
  - Wait for checks to pass
  - Squash-merge release PR
  ✓ Complete job

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz release: .github#5

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Publish plan: .github#6

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz PR: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/setup-python@v5, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
sdist: .github#2

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Release-plz · 34591495282
Triggered via workflow_dispatch about 5 minutes ago

JOBS
✓ Release-plz release in 19s (ID 103237584133)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz release output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ Publish plan in 4s (ID 103237677116)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Compute publish plan
  ✓ Post Checkout repository
  ✓ Complete job
✓ Release-plz PR in 26s (ID 103237677379)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz PR output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ sdist in 20s (ID 103237708043)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Build sdist
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* macos universal2 (ID 103237708069)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
* linux x86_64 (ID 103237708088)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test (x86_64 only)
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
* linux aarch64 (ID 103237708095)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test (x86_64 only)
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
* windows x86_64 (ID 103237708155)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
✓ Merge release PR in 3s (ID 103237804576)
  ✓ Set up job
  ✓ Resolve release PR
  - Wait for checks to register
  - Wait for checks to pass
  - Squash-merge release PR
  ✓ Complete job

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz release: .github#5

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Publish plan: .github#6

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz PR: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/setup-python@v5, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
sdist: .github#2

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Release-plz · 34591495282
Triggered via workflow_dispatch about 5 minutes ago

JOBS
✓ Release-plz release in 19s (ID 103237584133)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz release output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ Publish plan in 4s (ID 103237677116)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Compute publish plan
  ✓ Post Checkout repository
  ✓ Complete job
✓ Release-plz PR in 26s (ID 103237677379)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz PR output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ sdist in 20s (ID 103237708043)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Build sdist
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* macos universal2 (ID 103237708069)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
* linux x86_64 (ID 103237708088)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test (x86_64 only)
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
* linux aarch64 (ID 103237708095)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test (x86_64 only)
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
* windows x86_64 (ID 103237708155)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
✓ Merge release PR in 3s (ID 103237804576)
  ✓ Set up job
  ✓ Resolve release PR
  - Wait for checks to register
  - Wait for checks to pass
  - Squash-merge release PR
  ✓ Complete job

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz release: .github#5

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Publish plan: .github#6

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz PR: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/setup-python@v5, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
sdist: .github#2

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Release-plz · 34591495282
Triggered via workflow_dispatch about 5 minutes ago

JOBS
✓ Release-plz release in 19s (ID 103237584133)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz release output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ Publish plan in 4s (ID 103237677116)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Compute publish plan
  ✓ Post Checkout repository
  ✓ Complete job
✓ Release-plz PR in 26s (ID 103237677379)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz PR output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ sdist in 20s (ID 103237708043)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Build sdist
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* macos universal2 (ID 103237708069)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
* linux x86_64 (ID 103237708088)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test (x86_64 only)
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
* linux aarch64 (ID 103237708095)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test (x86_64 only)
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
* windows x86_64 (ID 103237708155)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
✓ Merge release PR in 3s (ID 103237804576)
  ✓ Set up job
  ✓ Resolve release PR
  - Wait for checks to register
  - Wait for checks to pass
  - Squash-merge release PR
  ✓ Complete job

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz release: .github#5

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Publish plan: .github#6

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz PR: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/setup-python@v5, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
sdist: .github#2

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Release-plz · 34591495282
Triggered via workflow_dispatch about 5 minutes ago

JOBS
✓ Release-plz release in 19s (ID 103237584133)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz release output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ Publish plan in 4s (ID 103237677116)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Compute publish plan
  ✓ Post Checkout repository
  ✓ Complete job
✓ Release-plz PR in 26s (ID 103237677379)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz PR output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ sdist in 20s (ID 103237708043)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Build sdist
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* macos universal2 (ID 103237708069)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
* linux x86_64 (ID 103237708088)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test (x86_64 only)
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
* linux aarch64 (ID 103237708095)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test (x86_64 only)
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
* windows x86_64 (ID 103237708155)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
✓ Merge release PR in 3s (ID 103237804576)
  ✓ Set up job
  ✓ Resolve release PR
  - Wait for checks to register
  - Wait for checks to pass
  - Squash-merge release PR
  ✓ Complete job

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz release: .github#5

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Publish plan: .github#6

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz PR: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/setup-python@v5, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
sdist: .github#2

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Release-plz · 34591495282
Triggered via workflow_dispatch about 5 minutes ago

JOBS
✓ Release-plz release in 19s (ID 103237584133)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz release output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ Publish plan in 4s (ID 103237677116)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Compute publish plan
  ✓ Post Checkout repository
  ✓ Complete job
✓ Release-plz PR in 26s (ID 103237677379)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz PR output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ sdist in 20s (ID 103237708043)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Build sdist
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* macos universal2 (ID 103237708069)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
* linux x86_64 (ID 103237708088)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test (x86_64 only)
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
* linux aarch64 (ID 103237708095)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test (x86_64 only)
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
* windows x86_64 (ID 103237708155)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
✓ Merge release PR in 3s (ID 103237804576)
  ✓ Set up job
  ✓ Resolve release PR
  - Wait for checks to register
  - Wait for checks to pass
  - Squash-merge release PR
  ✓ Complete job

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz release: .github#5

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Publish plan: .github#6

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz PR: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/setup-python@v5, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
sdist: .github#2

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Release-plz · 34591495282
Triggered via workflow_dispatch about 5 minutes ago

JOBS
✓ Release-plz release in 19s (ID 103237584133)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz release output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ Publish plan in 4s (ID 103237677116)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Compute publish plan
  ✓ Post Checkout repository
  ✓ Complete job
✓ Release-plz PR in 26s (ID 103237677379)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz PR output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ sdist in 20s (ID 103237708043)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Build sdist
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* macos universal2 (ID 103237708069)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
* linux x86_64 (ID 103237708088)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test (x86_64 only)
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
* linux aarch64 (ID 103237708095)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test (x86_64 only)
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
* windows x86_64 (ID 103237708155)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
✓ Merge release PR in 3s (ID 103237804576)
  ✓ Set up job
  ✓ Resolve release PR
  - Wait for checks to register
  - Wait for checks to pass
  - Squash-merge release PR
  ✓ Complete job

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz release: .github#5

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Publish plan: .github#6

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz PR: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/setup-python@v5, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
sdist: .github#2

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Release-plz · 34591495282
Triggered via workflow_dispatch about 5 minutes ago

JOBS
✓ Release-plz release in 19s (ID 103237584133)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz release output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ Publish plan in 4s (ID 103237677116)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Compute publish plan
  ✓ Post Checkout repository
  ✓ Complete job
✓ Release-plz PR in 26s (ID 103237677379)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz PR output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ sdist in 20s (ID 103237708043)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Build sdist
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* macos universal2 (ID 103237708069)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
* linux x86_64 (ID 103237708088)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test (x86_64 only)
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
* linux aarch64 (ID 103237708095)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test (x86_64 only)
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
* windows x86_64 (ID 103237708155)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
✓ Merge release PR in 3s (ID 103237804576)
  ✓ Set up job
  ✓ Resolve release PR
  - Wait for checks to register
  - Wait for checks to pass
  - Squash-merge release PR
  ✓ Complete job

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz release: .github#5

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Publish plan: .github#6

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz PR: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/setup-python@v5, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
sdist: .github#2

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Release-plz · 34591495282
Triggered via workflow_dispatch about 5 minutes ago

JOBS
✓ Release-plz release in 19s (ID 103237584133)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz release output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ Publish plan in 4s (ID 103237677116)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Compute publish plan
  ✓ Post Checkout repository
  ✓ Complete job
✓ Release-plz PR in 26s (ID 103237677379)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz PR output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ sdist in 20s (ID 103237708043)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Build sdist
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* macos universal2 (ID 103237708069)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
* linux x86_64 (ID 103237708088)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test (x86_64 only)
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
* linux aarch64 (ID 103237708095)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test (x86_64 only)
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
* windows x86_64 (ID 103237708155)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
✓ Merge release PR in 3s (ID 103237804576)
  ✓ Set up job
  ✓ Resolve release PR
  - Wait for checks to register
  - Wait for checks to pass
  - Squash-merge release PR
  ✓ Complete job

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz release: .github#5

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Publish plan: .github#6

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz PR: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/setup-python@v5, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
sdist: .github#2

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Release-plz · 34591495282
Triggered via workflow_dispatch about 5 minutes ago

JOBS
✓ Release-plz release in 19s (ID 103237584133)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz release output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ Publish plan in 4s (ID 103237677116)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Compute publish plan
  ✓ Post Checkout repository
  ✓ Complete job
✓ Release-plz PR in 26s (ID 103237677379)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz PR output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ sdist in 20s (ID 103237708043)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Build sdist
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* macos universal2 (ID 103237708069)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
* linux x86_64 (ID 103237708088)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test (x86_64 only)
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
* linux aarch64 (ID 103237708095)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test (x86_64 only)
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
* windows x86_64 (ID 103237708155)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
✓ Merge release PR in 3s (ID 103237804576)
  ✓ Set up job
  ✓ Resolve release PR
  - Wait for checks to register
  - Wait for checks to pass
  - Squash-merge release PR
  ✓ Complete job

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz release: .github#5

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Publish plan: .github#6

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz PR: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/setup-python@v5, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
sdist: .github#2

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Release-plz · 34591495282
Triggered via workflow_dispatch about 5 minutes ago

JOBS
✓ Release-plz release in 19s (ID 103237584133)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz release output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ Publish plan in 4s (ID 103237677116)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Compute publish plan
  ✓ Post Checkout repository
  ✓ Complete job
✓ Release-plz PR in 26s (ID 103237677379)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz PR output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ sdist in 20s (ID 103237708043)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Build sdist
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* macos universal2 (ID 103237708069)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
* linux x86_64 (ID 103237708088)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test (x86_64 only)
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
* linux aarch64 (ID 103237708095)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test (x86_64 only)
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
* windows x86_64 (ID 103237708155)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
✓ Merge release PR in 3s (ID 103237804576)
  ✓ Set up job
  ✓ Resolve release PR
  - Wait for checks to register
  - Wait for checks to pass
  - Squash-merge release PR
  ✓ Complete job

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz release: .github#5

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Publish plan: .github#6

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz PR: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/setup-python@v5, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
sdist: .github#2

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Release-plz · 34591495282
Triggered via workflow_dispatch about 5 minutes ago

JOBS
✓ Release-plz release in 19s (ID 103237584133)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz release output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ Publish plan in 4s (ID 103237677116)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Compute publish plan
  ✓ Post Checkout repository
  ✓ Complete job
✓ Release-plz PR in 26s (ID 103237677379)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz PR output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ sdist in 20s (ID 103237708043)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Build sdist
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* macos universal2 (ID 103237708069)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
* linux x86_64 (ID 103237708088)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test (x86_64 only)
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
* linux aarch64 (ID 103237708095)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test (x86_64 only)
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
* windows x86_64 (ID 103237708155)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
✓ Merge release PR in 3s (ID 103237804576)
  ✓ Set up job
  ✓ Resolve release PR
  - Wait for checks to register
  - Wait for checks to pass
  - Squash-merge release PR
  ✓ Complete job

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz release: .github#5

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Publish plan: .github#6

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz PR: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/setup-python@v5, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
sdist: .github#2

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Release-plz · 34591495282
Triggered via workflow_dispatch about 5 minutes ago

JOBS
✓ Release-plz release in 19s (ID 103237584133)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz release output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ Publish plan in 4s (ID 103237677116)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Compute publish plan
  ✓ Post Checkout repository
  ✓ Complete job
✓ Release-plz PR in 26s (ID 103237677379)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz PR output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ sdist in 20s (ID 103237708043)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Build sdist
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* macos universal2 (ID 103237708069)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
* linux x86_64 (ID 103237708088)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test (x86_64 only)
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
* linux aarch64 (ID 103237708095)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test (x86_64 only)
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
* windows x86_64 (ID 103237708155)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
✓ Merge release PR in 3s (ID 103237804576)
  ✓ Set up job
  ✓ Resolve release PR
  - Wait for checks to register
  - Wait for checks to pass
  - Squash-merge release PR
  ✓ Complete job

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz release: .github#5

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Publish plan: .github#6

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz PR: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/setup-python@v5, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
sdist: .github#2

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Release-plz · 34591495282
Triggered via workflow_dispatch about 5 minutes ago

JOBS
✓ Release-plz release in 19s (ID 103237584133)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz release output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ Publish plan in 4s (ID 103237677116)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Compute publish plan
  ✓ Post Checkout repository
  ✓ Complete job
✓ Release-plz PR in 26s (ID 103237677379)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz PR output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ sdist in 20s (ID 103237708043)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Build sdist
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* macos universal2 (ID 103237708069)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
* linux x86_64 (ID 103237708088)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test (x86_64 only)
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
* linux aarch64 (ID 103237708095)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test (x86_64 only)
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
* windows x86_64 (ID 103237708155)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
✓ Merge release PR in 3s (ID 103237804576)
  ✓ Set up job
  ✓ Resolve release PR
  - Wait for checks to register
  - Wait for checks to pass
  - Squash-merge release PR
  ✓ Complete job

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz release: .github#5

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Publish plan: .github#6

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz PR: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/setup-python@v5, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
sdist: .github#2

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Release-plz · 34591495282
Triggered via workflow_dispatch about 6 minutes ago

JOBS
✓ Release-plz release in 19s (ID 103237584133)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz release output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ Publish plan in 4s (ID 103237677116)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Compute publish plan
  ✓ Post Checkout repository
  ✓ Complete job
✓ Release-plz PR in 26s (ID 103237677379)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz PR output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ sdist in 20s (ID 103237708043)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Build sdist
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* macos universal2 (ID 103237708069)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
* linux x86_64 (ID 103237708088)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test (x86_64 only)
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
* linux aarch64 (ID 103237708095)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test (x86_64 only)
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
* windows x86_64 (ID 103237708155)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
✓ Merge release PR in 3s (ID 103237804576)
  ✓ Set up job
  ✓ Resolve release PR
  - Wait for checks to register
  - Wait for checks to pass
  - Squash-merge release PR
  ✓ Complete job

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz release: .github#5

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Publish plan: .github#6

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz PR: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/setup-python@v5, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
sdist: .github#2

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Release-plz · 34591495282
Triggered via workflow_dispatch about 6 minutes ago

JOBS
✓ Release-plz release in 19s (ID 103237584133)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz release output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ Publish plan in 4s (ID 103237677116)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Compute publish plan
  ✓ Post Checkout repository
  ✓ Complete job
✓ Release-plz PR in 26s (ID 103237677379)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz PR output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ sdist in 20s (ID 103237708043)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Build sdist
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* macos universal2 (ID 103237708069)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
* linux x86_64 (ID 103237708088)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test (x86_64 only)
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
* linux aarch64 (ID 103237708095)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test (x86_64 only)
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
* windows x86_64 (ID 103237708155)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
✓ Merge release PR in 3s (ID 103237804576)
  ✓ Set up job
  ✓ Resolve release PR
  - Wait for checks to register
  - Wait for checks to pass
  - Squash-merge release PR
  ✓ Complete job

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz release: .github#5

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Publish plan: .github#6

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz PR: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/setup-python@v5, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
sdist: .github#2

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Release-plz · 34591495282
Triggered via workflow_dispatch about 6 minutes ago

JOBS
✓ Release-plz release in 19s (ID 103237584133)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz release output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ Publish plan in 4s (ID 103237677116)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Compute publish plan
  ✓ Post Checkout repository
  ✓ Complete job
✓ Release-plz PR in 26s (ID 103237677379)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz PR output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ sdist in 20s (ID 103237708043)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Build sdist
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* macos universal2 (ID 103237708069)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
* linux x86_64 (ID 103237708088)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test (x86_64 only)
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
* linux aarch64 (ID 103237708095)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test (x86_64 only)
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
* windows x86_64 (ID 103237708155)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
✓ Merge release PR in 3s (ID 103237804576)
  ✓ Set up job
  ✓ Resolve release PR
  - Wait for checks to register
  - Wait for checks to pass
  - Squash-merge release PR
  ✓ Complete job

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz release: .github#5

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Publish plan: .github#6

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz PR: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/setup-python@v5, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
sdist: .github#2

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Release-plz · 34591495282
Triggered via workflow_dispatch about 6 minutes ago

JOBS
✓ Release-plz release in 19s (ID 103237584133)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz release output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ Publish plan in 4s (ID 103237677116)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Compute publish plan
  ✓ Post Checkout repository
  ✓ Complete job
✓ Release-plz PR in 26s (ID 103237677379)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz PR output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ sdist in 20s (ID 103237708043)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Build sdist
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* macos universal2 (ID 103237708069)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
* linux x86_64 (ID 103237708088)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test (x86_64 only)
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
* linux aarch64 (ID 103237708095)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test (x86_64 only)
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
* windows x86_64 (ID 103237708155)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
✓ Merge release PR in 3s (ID 103237804576)
  ✓ Set up job
  ✓ Resolve release PR
  - Wait for checks to register
  - Wait for checks to pass
  - Squash-merge release PR
  ✓ Complete job

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz release: .github#5

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Publish plan: .github#6

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz PR: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/setup-python@v5, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
sdist: .github#2

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Release-plz · 34591495282
Triggered via workflow_dispatch about 6 minutes ago

JOBS
✓ Release-plz release in 19s (ID 103237584133)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz release output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ Publish plan in 4s (ID 103237677116)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Compute publish plan
  ✓ Post Checkout repository
  ✓ Complete job
✓ Release-plz PR in 26s (ID 103237677379)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz PR output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ sdist in 20s (ID 103237708043)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Build sdist
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* macos universal2 (ID 103237708069)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
* linux x86_64 (ID 103237708088)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test (x86_64 only)
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
* linux aarch64 (ID 103237708095)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test (x86_64 only)
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
* windows x86_64 (ID 103237708155)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
✓ Merge release PR in 3s (ID 103237804576)
  ✓ Set up job
  ✓ Resolve release PR
  - Wait for checks to register
  - Wait for checks to pass
  - Squash-merge release PR
  ✓ Complete job

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz release: .github#5

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Publish plan: .github#6

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz PR: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/setup-python@v5, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
sdist: .github#2

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Release-plz · 34591495282
Triggered via workflow_dispatch about 6 minutes ago

JOBS
✓ Release-plz release in 19s (ID 103237584133)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz release output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ Publish plan in 4s (ID 103237677116)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Compute publish plan
  ✓ Post Checkout repository
  ✓ Complete job
✓ Release-plz PR in 26s (ID 103237677379)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz PR output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ sdist in 20s (ID 103237708043)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Build sdist
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* macos universal2 (ID 103237708069)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
* linux x86_64 (ID 103237708088)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test (x86_64 only)
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
* linux aarch64 (ID 103237708095)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test (x86_64 only)
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
* windows x86_64 (ID 103237708155)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
✓ Merge release PR in 3s (ID 103237804576)
  ✓ Set up job
  ✓ Resolve release PR
  - Wait for checks to register
  - Wait for checks to pass
  - Squash-merge release PR
  ✓ Complete job

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz release: .github#5

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Publish plan: .github#6

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz PR: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/setup-python@v5, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
sdist: .github#2

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Release-plz · 34591495282
Triggered via workflow_dispatch about 6 minutes ago

JOBS
✓ Release-plz release in 19s (ID 103237584133)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz release output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ Publish plan in 4s (ID 103237677116)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Compute publish plan
  ✓ Post Checkout repository
  ✓ Complete job
✓ Release-plz PR in 26s (ID 103237677379)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz PR output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ sdist in 20s (ID 103237708043)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Build sdist
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* macos universal2 (ID 103237708069)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
* linux x86_64 (ID 103237708088)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test (x86_64 only)
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
* linux aarch64 (ID 103237708095)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test (x86_64 only)
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
* windows x86_64 (ID 103237708155)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
✓ Merge release PR in 3s (ID 103237804576)
  ✓ Set up job
  ✓ Resolve release PR
  - Wait for checks to register
  - Wait for checks to pass
  - Squash-merge release PR
  ✓ Complete job

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz release: .github#5

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Publish plan: .github#6

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz PR: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/setup-python@v5, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
sdist: .github#2

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Release-plz · 34591495282
Triggered via workflow_dispatch about 6 minutes ago

JOBS
✓ Release-plz release in 19s (ID 103237584133)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz release output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ Publish plan in 4s (ID 103237677116)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Compute publish plan
  ✓ Post Checkout repository
  ✓ Complete job
✓ Release-plz PR in 26s (ID 103237677379)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz PR output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ sdist in 20s (ID 103237708043)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Build sdist
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* macos universal2 (ID 103237708069)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
* linux x86_64 (ID 103237708088)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test (x86_64 only)
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
* linux aarch64 (ID 103237708095)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test (x86_64 only)
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
* windows x86_64 (ID 103237708155)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
✓ Merge release PR in 3s (ID 103237804576)
  ✓ Set up job
  ✓ Resolve release PR
  - Wait for checks to register
  - Wait for checks to pass
  - Squash-merge release PR
  ✓ Complete job

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz release: .github#5

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Publish plan: .github#6

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz PR: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/setup-python@v5, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
sdist: .github#2

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Release-plz · 34591495282
Triggered via workflow_dispatch about 6 minutes ago

JOBS
✓ Release-plz release in 19s (ID 103237584133)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz release output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ Publish plan in 4s (ID 103237677116)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Compute publish plan
  ✓ Post Checkout repository
  ✓ Complete job
✓ Release-plz PR in 26s (ID 103237677379)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz PR output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ sdist in 20s (ID 103237708043)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Build sdist
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* macos universal2 (ID 103237708069)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
* linux x86_64 (ID 103237708088)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test (x86_64 only)
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
* linux aarch64 (ID 103237708095)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test (x86_64 only)
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
* windows x86_64 (ID 103237708155)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
✓ Merge release PR in 3s (ID 103237804576)
  ✓ Set up job
  ✓ Resolve release PR
  - Wait for checks to register
  - Wait for checks to pass
  - Squash-merge release PR
  ✓ Complete job

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz release: .github#5

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Publish plan: .github#6

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz PR: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/setup-python@v5, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
sdist: .github#2

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Release-plz · 34591495282
Triggered via workflow_dispatch about 6 minutes ago

JOBS
✓ Release-plz release in 19s (ID 103237584133)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz release output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ Publish plan in 4s (ID 103237677116)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Compute publish plan
  ✓ Post Checkout repository
  ✓ Complete job
✓ Release-plz PR in 26s (ID 103237677379)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz PR output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ sdist in 20s (ID 103237708043)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Build sdist
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* macos universal2 (ID 103237708069)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
* linux x86_64 (ID 103237708088)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test (x86_64 only)
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
* linux aarch64 (ID 103237708095)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test (x86_64 only)
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
* windows x86_64 (ID 103237708155)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
✓ Merge release PR in 3s (ID 103237804576)
  ✓ Set up job
  ✓ Resolve release PR
  - Wait for checks to register
  - Wait for checks to pass
  - Squash-merge release PR
  ✓ Complete job

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz release: .github#5

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Publish plan: .github#6

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz PR: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/setup-python@v5, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
sdist: .github#2

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Release-plz · 34591495282
Triggered via workflow_dispatch about 6 minutes ago

JOBS
✓ Release-plz release in 19s (ID 103237584133)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz release output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ Publish plan in 4s (ID 103237677116)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Compute publish plan
  ✓ Post Checkout repository
  ✓ Complete job
✓ Release-plz PR in 26s (ID 103237677379)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz PR output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ sdist in 20s (ID 103237708043)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Build sdist
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* macos universal2 (ID 103237708069)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
* linux x86_64 (ID 103237708088)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test (x86_64 only)
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
* linux aarch64 (ID 103237708095)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test (x86_64 only)
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
* windows x86_64 (ID 103237708155)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
✓ Merge release PR in 3s (ID 103237804576)
  ✓ Set up job
  ✓ Resolve release PR
  - Wait for checks to register
  - Wait for checks to pass
  - Squash-merge release PR
  ✓ Complete job

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz release: .github#5

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Publish plan: .github#6

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz PR: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/setup-python@v5, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
sdist: .github#2

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Release-plz · 34591495282
Triggered via workflow_dispatch about 6 minutes ago

JOBS
✓ Release-plz release in 19s (ID 103237584133)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz release output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ Publish plan in 4s (ID 103237677116)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Compute publish plan
  ✓ Post Checkout repository
  ✓ Complete job
✓ Release-plz PR in 26s (ID 103237677379)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz PR output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ sdist in 20s (ID 103237708043)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Build sdist
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* macos universal2 (ID 103237708069)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
* linux x86_64 (ID 103237708088)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test (x86_64 only)
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
* linux aarch64 (ID 103237708095)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test (x86_64 only)
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
* windows x86_64 (ID 103237708155)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
✓ Merge release PR in 3s (ID 103237804576)
  ✓ Set up job
  ✓ Resolve release PR
  - Wait for checks to register
  - Wait for checks to pass
  - Squash-merge release PR
  ✓ Complete job

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz release: .github#5

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Publish plan: .github#6

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz PR: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/setup-python@v5, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
sdist: .github#2

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Release-plz · 34591495282
Triggered via workflow_dispatch about 6 minutes ago

JOBS
✓ Release-plz release in 19s (ID 103237584133)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz release output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ Publish plan in 4s (ID 103237677116)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Compute publish plan
  ✓ Post Checkout repository
  ✓ Complete job
✓ Release-plz PR in 26s (ID 103237677379)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz PR output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ sdist in 20s (ID 103237708043)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Build sdist
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* macos universal2 (ID 103237708069)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
* linux x86_64 (ID 103237708088)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test (x86_64 only)
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
* linux aarch64 (ID 103237708095)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test (x86_64 only)
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
* windows x86_64 (ID 103237708155)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
✓ Merge release PR in 3s (ID 103237804576)
  ✓ Set up job
  ✓ Resolve release PR
  - Wait for checks to register
  - Wait for checks to pass
  - Squash-merge release PR
  ✓ Complete job

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz release: .github#5

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Publish plan: .github#6

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz PR: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/setup-python@v5, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
sdist: .github#2

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Release-plz · 34591495282
Triggered via workflow_dispatch about 6 minutes ago

JOBS
✓ Release-plz release in 19s (ID 103237584133)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz release output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ Publish plan in 4s (ID 103237677116)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Compute publish plan
  ✓ Post Checkout repository
  ✓ Complete job
✓ Release-plz PR in 26s (ID 103237677379)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz PR output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ sdist in 20s (ID 103237708043)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Build sdist
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* macos universal2 (ID 103237708069)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
* linux x86_64 (ID 103237708088)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test (x86_64 only)
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
* linux aarch64 (ID 103237708095)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test (x86_64 only)
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
* windows x86_64 (ID 103237708155)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
✓ Merge release PR in 3s (ID 103237804576)
  ✓ Set up job
  ✓ Resolve release PR
  - Wait for checks to register
  - Wait for checks to pass
  - Squash-merge release PR
  ✓ Complete job

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz release: .github#5

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Publish plan: .github#6

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz PR: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/setup-python@v5, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
sdist: .github#2

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Release-plz · 34591495282
Triggered via workflow_dispatch about 7 minutes ago

JOBS
✓ Release-plz release in 19s (ID 103237584133)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz release output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ Publish plan in 4s (ID 103237677116)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Compute publish plan
  ✓ Post Checkout repository
  ✓ Complete job
✓ Release-plz PR in 26s (ID 103237677379)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz PR output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ sdist in 20s (ID 103237708043)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Build sdist
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* macos universal2 (ID 103237708069)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
* linux x86_64 (ID 103237708088)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test (x86_64 only)
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
* linux aarch64 (ID 103237708095)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test (x86_64 only)
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
* windows x86_64 (ID 103237708155)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
✓ Merge release PR in 3s (ID 103237804576)
  ✓ Set up job
  ✓ Resolve release PR
  - Wait for checks to register
  - Wait for checks to pass
  - Squash-merge release PR
  ✓ Complete job

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz release: .github#5

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Publish plan: .github#6

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz PR: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/setup-python@v5, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
sdist: .github#2

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Release-plz · 34591495282
Triggered via workflow_dispatch about 7 minutes ago

JOBS
✓ Release-plz release in 19s (ID 103237584133)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz release output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ Publish plan in 4s (ID 103237677116)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Compute publish plan
  ✓ Post Checkout repository
  ✓ Complete job
✓ Release-plz PR in 26s (ID 103237677379)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz PR output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ sdist in 20s (ID 103237708043)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Build sdist
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* macos universal2 (ID 103237708069)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
* linux x86_64 (ID 103237708088)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test (x86_64 only)
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
* linux aarch64 (ID 103237708095)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test (x86_64 only)
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
* windows x86_64 (ID 103237708155)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
✓ Merge release PR in 3s (ID 103237804576)
  ✓ Set up job
  ✓ Resolve release PR
  - Wait for checks to register
  - Wait for checks to pass
  - Squash-merge release PR
  ✓ Complete job

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz release: .github#5

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Publish plan: .github#6

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz PR: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/setup-python@v5, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
sdist: .github#2

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Release-plz · 34591495282
Triggered via workflow_dispatch about 7 minutes ago

JOBS
✓ Release-plz release in 19s (ID 103237584133)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz release output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ Publish plan in 4s (ID 103237677116)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Compute publish plan
  ✓ Post Checkout repository
  ✓ Complete job
✓ Release-plz PR in 26s (ID 103237677379)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz PR output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ sdist in 20s (ID 103237708043)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Build sdist
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* macos universal2 (ID 103237708069)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
* linux x86_64 (ID 103237708088)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test (x86_64 only)
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
* linux aarch64 (ID 103237708095)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test (x86_64 only)
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
* windows x86_64 (ID 103237708155)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
✓ Merge release PR in 3s (ID 103237804576)
  ✓ Set up job
  ✓ Resolve release PR
  - Wait for checks to register
  - Wait for checks to pass
  - Squash-merge release PR
  ✓ Complete job

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz release: .github#5

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Publish plan: .github#6

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz PR: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/setup-python@v5, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
sdist: .github#2

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Release-plz · 34591495282
Triggered via workflow_dispatch about 7 minutes ago

JOBS
✓ Release-plz release in 19s (ID 103237584133)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz release output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ Publish plan in 4s (ID 103237677116)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Compute publish plan
  ✓ Post Checkout repository
  ✓ Complete job
✓ Release-plz PR in 26s (ID 103237677379)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz PR output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ sdist in 20s (ID 103237708043)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Build sdist
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* macos universal2 (ID 103237708069)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
* linux x86_64 (ID 103237708088)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test (x86_64 only)
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
* linux aarch64 (ID 103237708095)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test (x86_64 only)
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
* windows x86_64 (ID 103237708155)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
✓ Merge release PR in 3s (ID 103237804576)
  ✓ Set up job
  ✓ Resolve release PR
  - Wait for checks to register
  - Wait for checks to pass
  - Squash-merge release PR
  ✓ Complete job

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz release: .github#5

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Publish plan: .github#6

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz PR: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/setup-python@v5, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
sdist: .github#2

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Release-plz · 34591495282
Triggered via workflow_dispatch about 7 minutes ago

JOBS
✓ Release-plz release in 19s (ID 103237584133)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz release output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ Publish plan in 4s (ID 103237677116)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Compute publish plan
  ✓ Post Checkout repository
  ✓ Complete job
✓ Release-plz PR in 26s (ID 103237677379)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz PR output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ sdist in 20s (ID 103237708043)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Build sdist
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* macos universal2 (ID 103237708069)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
* linux x86_64 (ID 103237708088)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test (x86_64 only)
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
* linux aarch64 (ID 103237708095)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test (x86_64 only)
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
* windows x86_64 (ID 103237708155)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
✓ Merge release PR in 3s (ID 103237804576)
  ✓ Set up job
  ✓ Resolve release PR
  - Wait for checks to register
  - Wait for checks to pass
  - Squash-merge release PR
  ✓ Complete job

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz release: .github#5

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Publish plan: .github#6

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz PR: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/setup-python@v5, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
sdist: .github#2

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Release-plz · 34591495282
Triggered via workflow_dispatch about 7 minutes ago

JOBS
✓ Release-plz release in 19s (ID 103237584133)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz release output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ Publish plan in 4s (ID 103237677116)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Compute publish plan
  ✓ Post Checkout repository
  ✓ Complete job
✓ Release-plz PR in 26s (ID 103237677379)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz PR output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ sdist in 20s (ID 103237708043)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Build sdist
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* macos universal2 (ID 103237708069)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
* linux x86_64 (ID 103237708088)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test (x86_64 only)
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
* linux aarch64 (ID 103237708095)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test (x86_64 only)
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
* windows x86_64 (ID 103237708155)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
✓ Merge release PR in 3s (ID 103237804576)
  ✓ Set up job
  ✓ Resolve release PR
  - Wait for checks to register
  - Wait for checks to pass
  - Squash-merge release PR
  ✓ Complete job

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz release: .github#5

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Publish plan: .github#6

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz PR: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/setup-python@v5, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
sdist: .github#2

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Release-plz · 34591495282
Triggered via workflow_dispatch about 7 minutes ago

JOBS
✓ Release-plz release in 19s (ID 103237584133)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz release output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ Publish plan in 4s (ID 103237677116)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Compute publish plan
  ✓ Post Checkout repository
  ✓ Complete job
✓ Release-plz PR in 26s (ID 103237677379)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz PR output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ sdist in 20s (ID 103237708043)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Build sdist
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* macos universal2 (ID 103237708069)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
* linux x86_64 (ID 103237708088)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test (x86_64 only)
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
* linux aarch64 (ID 103237708095)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test (x86_64 only)
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
* windows x86_64 (ID 103237708155)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
✓ Merge release PR in 3s (ID 103237804576)
  ✓ Set up job
  ✓ Resolve release PR
  - Wait for checks to register
  - Wait for checks to pass
  - Squash-merge release PR
  ✓ Complete job

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz release: .github#5

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Publish plan: .github#6

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz PR: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/setup-python@v5, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
sdist: .github#2

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Release-plz · 34591495282
Triggered via workflow_dispatch about 7 minutes ago

JOBS
✓ Release-plz release in 19s (ID 103237584133)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz release output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ Publish plan in 4s (ID 103237677116)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Compute publish plan
  ✓ Post Checkout repository
  ✓ Complete job
✓ Release-plz PR in 26s (ID 103237677379)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz PR output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ sdist in 20s (ID 103237708043)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Build sdist
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* macos universal2 (ID 103237708069)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
* linux x86_64 (ID 103237708088)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test (x86_64 only)
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
* linux aarch64 (ID 103237708095)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test (x86_64 only)
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
* windows x86_64 (ID 103237708155)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
✓ Merge release PR in 3s (ID 103237804576)
  ✓ Set up job
  ✓ Resolve release PR
  - Wait for checks to register
  - Wait for checks to pass
  - Squash-merge release PR
  ✓ Complete job

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz release: .github#5

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Publish plan: .github#6

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz PR: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/setup-python@v5, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
sdist: .github#2

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Release-plz · 34591495282
Triggered via workflow_dispatch about 7 minutes ago

JOBS
✓ Release-plz release in 19s (ID 103237584133)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz release output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ Publish plan in 4s (ID 103237677116)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Compute publish plan
  ✓ Post Checkout repository
  ✓ Complete job
✓ Release-plz PR in 26s (ID 103237677379)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz PR output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ sdist in 20s (ID 103237708043)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Build sdist
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* macos universal2 (ID 103237708069)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
* linux x86_64 (ID 103237708088)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test (x86_64 only)
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
* linux aarch64 (ID 103237708095)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test (x86_64 only)
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
* windows x86_64 (ID 103237708155)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
✓ Merge release PR in 3s (ID 103237804576)
  ✓ Set up job
  ✓ Resolve release PR
  - Wait for checks to register
  - Wait for checks to pass
  - Squash-merge release PR
  ✓ Complete job

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz release: .github#5

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Publish plan: .github#6

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz PR: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/setup-python@v5, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
sdist: .github#2

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Release-plz · 34591495282
Triggered via workflow_dispatch about 7 minutes ago

JOBS
✓ Release-plz release in 19s (ID 103237584133)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz release output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ Publish plan in 4s (ID 103237677116)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Compute publish plan
  ✓ Post Checkout repository
  ✓ Complete job
✓ Release-plz PR in 26s (ID 103237677379)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz PR output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ sdist in 20s (ID 103237708043)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Build sdist
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* macos universal2 (ID 103237708069)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
* linux x86_64 (ID 103237708088)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test (x86_64 only)
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
* linux aarch64 (ID 103237708095)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test (x86_64 only)
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
* windows x86_64 (ID 103237708155)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
✓ Merge release PR in 3s (ID 103237804576)
  ✓ Set up job
  ✓ Resolve release PR
  - Wait for checks to register
  - Wait for checks to pass
  - Squash-merge release PR
  ✓ Complete job

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz release: .github#5

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Publish plan: .github#6

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz PR: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/setup-python@v5, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
sdist: .github#2

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Release-plz · 34591495282
Triggered via workflow_dispatch about 7 minutes ago

JOBS
✓ Release-plz release in 19s (ID 103237584133)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz release output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ Publish plan in 4s (ID 103237677116)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Compute publish plan
  ✓ Post Checkout repository
  ✓ Complete job
✓ Release-plz PR in 26s (ID 103237677379)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz PR output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ sdist in 20s (ID 103237708043)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Build sdist
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* macos universal2 (ID 103237708069)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
* linux x86_64 (ID 103237708088)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test (x86_64 only)
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
* linux aarch64 (ID 103237708095)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test (x86_64 only)
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
* windows x86_64 (ID 103237708155)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
✓ Merge release PR in 3s (ID 103237804576)
  ✓ Set up job
  ✓ Resolve release PR
  - Wait for checks to register
  - Wait for checks to pass
  - Squash-merge release PR
  ✓ Complete job

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz release: .github#5

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Publish plan: .github#6

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz PR: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/setup-python@v5, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
sdist: .github#2

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Release-plz · 34591495282
Triggered via workflow_dispatch about 7 minutes ago

JOBS
✓ Release-plz release in 19s (ID 103237584133)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz release output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ Publish plan in 4s (ID 103237677116)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Compute publish plan
  ✓ Post Checkout repository
  ✓ Complete job
✓ Release-plz PR in 26s (ID 103237677379)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz PR output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ sdist in 20s (ID 103237708043)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Build sdist
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* macos universal2 (ID 103237708069)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
* linux x86_64 (ID 103237708088)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test (x86_64 only)
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
* linux aarch64 (ID 103237708095)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test (x86_64 only)
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
* windows x86_64 (ID 103237708155)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
✓ Merge release PR in 3s (ID 103237804576)
  ✓ Set up job
  ✓ Resolve release PR
  - Wait for checks to register
  - Wait for checks to pass
  - Squash-merge release PR
  ✓ Complete job

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz release: .github#5

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Publish plan: .github#6

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz PR: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/setup-python@v5, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
sdist: .github#2

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Release-plz · 34591495282
Triggered via workflow_dispatch about 7 minutes ago

JOBS
✓ Release-plz release in 19s (ID 103237584133)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz release output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ Publish plan in 4s (ID 103237677116)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Compute publish plan
  ✓ Post Checkout repository
  ✓ Complete job
✓ Release-plz PR in 26s (ID 103237677379)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz PR output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ sdist in 20s (ID 103237708043)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Build sdist
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* macos universal2 (ID 103237708069)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
* linux x86_64 (ID 103237708088)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test (x86_64 only)
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
* linux aarch64 (ID 103237708095)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test (x86_64 only)
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
* windows x86_64 (ID 103237708155)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
✓ Merge release PR in 3s (ID 103237804576)
  ✓ Set up job
  ✓ Resolve release PR
  - Wait for checks to register
  - Wait for checks to pass
  - Squash-merge release PR
  ✓ Complete job

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz release: .github#5

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Publish plan: .github#6

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz PR: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/setup-python@v5, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
sdist: .github#2

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Release-plz · 34591495282
Triggered via workflow_dispatch about 7 minutes ago

JOBS
✓ Release-plz release in 19s (ID 103237584133)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz release output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ Publish plan in 4s (ID 103237677116)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Compute publish plan
  ✓ Post Checkout repository
  ✓ Complete job
✓ Release-plz PR in 26s (ID 103237677379)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz PR output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ sdist in 20s (ID 103237708043)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Build sdist
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* macos universal2 (ID 103237708069)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
* linux x86_64 (ID 103237708088)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test (x86_64 only)
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
* linux aarch64 (ID 103237708095)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test (x86_64 only)
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
* windows x86_64 (ID 103237708155)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
✓ Merge release PR in 3s (ID 103237804576)
  ✓ Set up job
  ✓ Resolve release PR
  - Wait for checks to register
  - Wait for checks to pass
  - Squash-merge release PR
  ✓ Complete job

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz release: .github#5

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Publish plan: .github#6

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz PR: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/setup-python@v5, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
sdist: .github#2

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Release-plz · 34591495282
Triggered via workflow_dispatch about 8 minutes ago

JOBS
✓ Release-plz release in 19s (ID 103237584133)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz release output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ Publish plan in 4s (ID 103237677116)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Compute publish plan
  ✓ Post Checkout repository
  ✓ Complete job
✓ Release-plz PR in 26s (ID 103237677379)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz PR output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ sdist in 20s (ID 103237708043)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Build sdist
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* macos universal2 (ID 103237708069)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
* linux x86_64 (ID 103237708088)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test (x86_64 only)
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
* linux aarch64 (ID 103237708095)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test (x86_64 only)
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
* windows x86_64 (ID 103237708155)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
✓ Merge release PR in 3s (ID 103237804576)
  ✓ Set up job
  ✓ Resolve release PR
  - Wait for checks to register
  - Wait for checks to pass
  - Squash-merge release PR
  ✓ Complete job

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz release: .github#5

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Publish plan: .github#6

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz PR: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/setup-python@v5, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
sdist: .github#2

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Release-plz · 34591495282
Triggered via workflow_dispatch about 8 minutes ago

JOBS
✓ Release-plz release in 19s (ID 103237584133)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz release output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ Publish plan in 4s (ID 103237677116)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Compute publish plan
  ✓ Post Checkout repository
  ✓ Complete job
✓ Release-plz PR in 26s (ID 103237677379)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz PR output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ sdist in 20s (ID 103237708043)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Build sdist
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* macos universal2 (ID 103237708069)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
* linux x86_64 (ID 103237708088)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test (x86_64 only)
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
* linux aarch64 (ID 103237708095)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test (x86_64 only)
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
* windows x86_64 (ID 103237708155)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
✓ Merge release PR in 3s (ID 103237804576)
  ✓ Set up job
  ✓ Resolve release PR
  - Wait for checks to register
  - Wait for checks to pass
  - Squash-merge release PR
  ✓ Complete job

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz release: .github#5

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Publish plan: .github#6

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz PR: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/setup-python@v5, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
sdist: .github#2

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Release-plz · 34591495282
Triggered via workflow_dispatch about 8 minutes ago

JOBS
✓ Release-plz release in 19s (ID 103237584133)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz release output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ Publish plan in 4s (ID 103237677116)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Compute publish plan
  ✓ Post Checkout repository
  ✓ Complete job
✓ Release-plz PR in 26s (ID 103237677379)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz PR output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ sdist in 20s (ID 103237708043)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Build sdist
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* macos universal2 (ID 103237708069)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
* linux x86_64 (ID 103237708088)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test (x86_64 only)
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
* linux aarch64 (ID 103237708095)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test (x86_64 only)
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
* windows x86_64 (ID 103237708155)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
✓ Merge release PR in 3s (ID 103237804576)
  ✓ Set up job
  ✓ Resolve release PR
  - Wait for checks to register
  - Wait for checks to pass
  - Squash-merge release PR
  ✓ Complete job

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz release: .github#5

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Publish plan: .github#6

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz PR: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/setup-python@v5, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
sdist: .github#2

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Release-plz · 34591495282
Triggered via workflow_dispatch about 8 minutes ago

JOBS
✓ Release-plz release in 19s (ID 103237584133)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz release output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ Publish plan in 4s (ID 103237677116)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Compute publish plan
  ✓ Post Checkout repository
  ✓ Complete job
✓ Release-plz PR in 26s (ID 103237677379)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz PR output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ sdist in 20s (ID 103237708043)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Build sdist
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* macos universal2 (ID 103237708069)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
* linux x86_64 (ID 103237708088)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  ✓ Build wheel
  * Smoke test (x86_64 only)
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
* linux aarch64 (ID 103237708095)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test (x86_64 only)
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
* windows x86_64 (ID 103237708155)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
✓ Merge release PR in 3s (ID 103237804576)
  ✓ Set up job
  ✓ Resolve release PR
  - Wait for checks to register
  - Wait for checks to pass
  - Squash-merge release PR
  ✓ Complete job

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz release: .github#5

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Publish plan: .github#6

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz PR: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/setup-python@v5, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
sdist: .github#2

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Release-plz · 34591495282
Triggered via workflow_dispatch about 8 minutes ago

JOBS
✓ Release-plz release in 19s (ID 103237584133)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz release output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ Publish plan in 4s (ID 103237677116)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Compute publish plan
  ✓ Post Checkout repository
  ✓ Complete job
✓ Release-plz PR in 26s (ID 103237677379)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz PR output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ sdist in 20s (ID 103237708043)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Build sdist
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* macos universal2 (ID 103237708069)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
* linux x86_64 (ID 103237708088)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  ✓ Build wheel
  ✓ Smoke test (x86_64 only)
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
* linux aarch64 (ID 103237708095)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test (x86_64 only)
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
* windows x86_64 (ID 103237708155)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
✓ Merge release PR in 3s (ID 103237804576)
  ✓ Set up job
  ✓ Resolve release PR
  - Wait for checks to register
  - Wait for checks to pass
  - Squash-merge release PR
  ✓ Complete job

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz release: .github#5

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Publish plan: .github#6

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz PR: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/setup-python@v5, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
sdist: .github#2

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Release-plz · 34591495282
Triggered via workflow_dispatch about 8 minutes ago

JOBS
✓ Release-plz release in 19s (ID 103237584133)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz release output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ Publish plan in 4s (ID 103237677116)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Compute publish plan
  ✓ Post Checkout repository
  ✓ Complete job
✓ Release-plz PR in 26s (ID 103237677379)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz PR output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ sdist in 20s (ID 103237708043)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Build sdist
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* macos universal2 (ID 103237708069)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
✓ linux x86_64 in 7m47s (ID 103237708088)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  ✓ Build wheel
  ✓ Smoke test (x86_64 only)
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* linux aarch64 (ID 103237708095)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test (x86_64 only)
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
* windows x86_64 (ID 103237708155)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
✓ Merge release PR in 3s (ID 103237804576)
  ✓ Set up job
  ✓ Resolve release PR
  - Wait for checks to register
  - Wait for checks to pass
  - Squash-merge release PR
  ✓ Complete job

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz release: .github#5

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Publish plan: .github#6

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz PR: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/setup-python@v5, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
sdist: .github#2

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Release-plz · 34591495282
Triggered via workflow_dispatch about 8 minutes ago

JOBS
✓ Release-plz release in 19s (ID 103237584133)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz release output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ Publish plan in 4s (ID 103237677116)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Compute publish plan
  ✓ Post Checkout repository
  ✓ Complete job
✓ Release-plz PR in 26s (ID 103237677379)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz PR output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ sdist in 20s (ID 103237708043)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Build sdist
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* macos universal2 (ID 103237708069)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
✓ linux x86_64 in 7m47s (ID 103237708088)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  ✓ Build wheel
  ✓ Smoke test (x86_64 only)
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* linux aarch64 (ID 103237708095)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  ✓ Build wheel
  - Smoke test (x86_64 only)
  ✓ Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
* windows x86_64 (ID 103237708155)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
✓ Merge release PR in 3s (ID 103237804576)
  ✓ Set up job
  ✓ Resolve release PR
  - Wait for checks to register
  - Wait for checks to pass
  - Squash-merge release PR
  ✓ Complete job

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz release: .github#5

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Publish plan: .github#6

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz PR: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/setup-python@v5, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
sdist: .github#2

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Release-plz · 34591495282
Triggered via workflow_dispatch about 8 minutes ago

JOBS
✓ Release-plz release in 19s (ID 103237584133)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz release output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ Publish plan in 4s (ID 103237677116)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Compute publish plan
  ✓ Post Checkout repository
  ✓ Complete job
✓ Release-plz PR in 26s (ID 103237677379)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz PR output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ sdist in 20s (ID 103237708043)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Build sdist
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* macos universal2 (ID 103237708069)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
✓ linux x86_64 in 7m47s (ID 103237708088)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  ✓ Build wheel
  ✓ Smoke test (x86_64 only)
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* linux aarch64 (ID 103237708095)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  ✓ Build wheel
  - Smoke test (x86_64 only)
  ✓ Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
* windows x86_64 (ID 103237708155)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
✓ Merge release PR in 3s (ID 103237804576)
  ✓ Set up job
  ✓ Resolve release PR
  - Wait for checks to register
  - Wait for checks to pass
  - Squash-merge release PR
  ✓ Complete job

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz release: .github#5

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Publish plan: .github#6

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz PR: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/setup-python@v5, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
sdist: .github#2

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Release-plz · 34591495282
Triggered via workflow_dispatch about 8 minutes ago

JOBS
✓ Release-plz release in 19s (ID 103237584133)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz release output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ Publish plan in 4s (ID 103237677116)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Compute publish plan
  ✓ Post Checkout repository
  ✓ Complete job
✓ Release-plz PR in 26s (ID 103237677379)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz PR output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ sdist in 20s (ID 103237708043)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Build sdist
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* macos universal2 (ID 103237708069)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
✓ linux x86_64 in 7m47s (ID 103237708088)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  ✓ Build wheel
  ✓ Smoke test (x86_64 only)
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* linux aarch64 (ID 103237708095)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  ✓ Build wheel
  - Smoke test (x86_64 only)
  ✓ Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
* windows x86_64 (ID 103237708155)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
✓ Merge release PR in 3s (ID 103237804576)
  ✓ Set up job
  ✓ Resolve release PR
  - Wait for checks to register
  - Wait for checks to pass
  - Squash-merge release PR
  ✓ Complete job

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz release: .github#5

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Publish plan: .github#6

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz PR: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/setup-python@v5, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
sdist: .github#2

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Release-plz · 34591495282
Triggered via workflow_dispatch about 8 minutes ago

JOBS
✓ Release-plz release in 19s (ID 103237584133)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz release output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ Publish plan in 4s (ID 103237677116)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Compute publish plan
  ✓ Post Checkout repository
  ✓ Complete job
✓ Release-plz PR in 26s (ID 103237677379)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz PR output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ sdist in 20s (ID 103237708043)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Build sdist
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* macos universal2 (ID 103237708069)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
✓ linux x86_64 in 7m47s (ID 103237708088)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  ✓ Build wheel
  ✓ Smoke test (x86_64 only)
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ linux aarch64 in 8m1s (ID 103237708095)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  ✓ Build wheel
  - Smoke test (x86_64 only)
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* windows x86_64 (ID 103237708155)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
✓ Merge release PR in 3s (ID 103237804576)
  ✓ Set up job
  ✓ Resolve release PR
  - Wait for checks to register
  - Wait for checks to pass
  - Squash-merge release PR
  ✓ Complete job

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz release: .github#5

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Publish plan: .github#6

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz PR: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/setup-python@v5, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
sdist: .github#2

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Release-plz · 34591495282
Triggered via workflow_dispatch about 8 minutes ago

JOBS
✓ Release-plz release in 19s (ID 103237584133)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz release output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ Publish plan in 4s (ID 103237677116)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Compute publish plan
  ✓ Post Checkout repository
  ✓ Complete job
✓ Release-plz PR in 26s (ID 103237677379)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz PR output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ sdist in 20s (ID 103237708043)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Build sdist
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* macos universal2 (ID 103237708069)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
✓ linux x86_64 in 7m47s (ID 103237708088)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  ✓ Build wheel
  ✓ Smoke test (x86_64 only)
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ linux aarch64 in 8m1s (ID 103237708095)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  ✓ Build wheel
  - Smoke test (x86_64 only)
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* windows x86_64 (ID 103237708155)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
✓ Merge release PR in 3s (ID 103237804576)
  ✓ Set up job
  ✓ Resolve release PR
  - Wait for checks to register
  - Wait for checks to pass
  - Squash-merge release PR
  ✓ Complete job

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz release: .github#5

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Publish plan: .github#6

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz PR: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/setup-python@v5, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
sdist: .github#2

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Release-plz · 34591495282
Triggered via workflow_dispatch about 8 minutes ago

JOBS
✓ Release-plz release in 19s (ID 103237584133)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz release output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ Publish plan in 4s (ID 103237677116)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Compute publish plan
  ✓ Post Checkout repository
  ✓ Complete job
✓ Release-plz PR in 26s (ID 103237677379)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz PR output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ sdist in 20s (ID 103237708043)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Build sdist
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* macos universal2 (ID 103237708069)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
✓ linux x86_64 in 7m47s (ID 103237708088)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  ✓ Build wheel
  ✓ Smoke test (x86_64 only)
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ linux aarch64 in 8m1s (ID 103237708095)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  ✓ Build wheel
  - Smoke test (x86_64 only)
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* windows x86_64 (ID 103237708155)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
✓ Merge release PR in 3s (ID 103237804576)
  ✓ Set up job
  ✓ Resolve release PR
  - Wait for checks to register
  - Wait for checks to pass
  - Squash-merge release PR
  ✓ Complete job

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz release: .github#5

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Publish plan: .github#6

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz PR: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/setup-python@v5, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
sdist: .github#2

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Release-plz · 34591495282
Triggered via workflow_dispatch about 8 minutes ago

JOBS
✓ Release-plz release in 19s (ID 103237584133)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz release output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ Publish plan in 4s (ID 103237677116)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Compute publish plan
  ✓ Post Checkout repository
  ✓ Complete job
✓ Release-plz PR in 26s (ID 103237677379)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz PR output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ sdist in 20s (ID 103237708043)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Build sdist
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* macos universal2 (ID 103237708069)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
✓ linux x86_64 in 7m47s (ID 103237708088)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  ✓ Build wheel
  ✓ Smoke test (x86_64 only)
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ linux aarch64 in 8m1s (ID 103237708095)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  ✓ Build wheel
  - Smoke test (x86_64 only)
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* windows x86_64 (ID 103237708155)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
✓ Merge release PR in 3s (ID 103237804576)
  ✓ Set up job
  ✓ Resolve release PR
  - Wait for checks to register
  - Wait for checks to pass
  - Squash-merge release PR
  ✓ Complete job

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz release: .github#5

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Publish plan: .github#6

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz PR: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/setup-python@v5, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
sdist: .github#2

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Release-plz · 34591495282
Triggered via workflow_dispatch about 8 minutes ago

JOBS
✓ Release-plz release in 19s (ID 103237584133)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz release output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ Publish plan in 4s (ID 103237677116)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Compute publish plan
  ✓ Post Checkout repository
  ✓ Complete job
✓ Release-plz PR in 26s (ID 103237677379)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz PR output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ sdist in 20s (ID 103237708043)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Build sdist
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* macos universal2 (ID 103237708069)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
✓ linux x86_64 in 7m47s (ID 103237708088)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  ✓ Build wheel
  ✓ Smoke test (x86_64 only)
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ linux aarch64 in 8m1s (ID 103237708095)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  ✓ Build wheel
  - Smoke test (x86_64 only)
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* windows x86_64 (ID 103237708155)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
✓ Merge release PR in 3s (ID 103237804576)
  ✓ Set up job
  ✓ Resolve release PR
  - Wait for checks to register
  - Wait for checks to pass
  - Squash-merge release PR
  ✓ Complete job

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz release: .github#5

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Publish plan: .github#6

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz PR: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/setup-python@v5, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
sdist: .github#2

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Release-plz · 34591495282
Triggered via workflow_dispatch about 9 minutes ago

JOBS
✓ Release-plz release in 19s (ID 103237584133)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz release output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ Publish plan in 4s (ID 103237677116)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Compute publish plan
  ✓ Post Checkout repository
  ✓ Complete job
✓ Release-plz PR in 26s (ID 103237677379)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz PR output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ sdist in 20s (ID 103237708043)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Build sdist
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* macos universal2 (ID 103237708069)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
✓ linux x86_64 in 7m47s (ID 103237708088)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  ✓ Build wheel
  ✓ Smoke test (x86_64 only)
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ linux aarch64 in 8m1s (ID 103237708095)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  ✓ Build wheel
  - Smoke test (x86_64 only)
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* windows x86_64 (ID 103237708155)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
✓ Merge release PR in 3s (ID 103237804576)
  ✓ Set up job
  ✓ Resolve release PR
  - Wait for checks to register
  - Wait for checks to pass
  - Squash-merge release PR
  ✓ Complete job

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz release: .github#5

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Publish plan: .github#6

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz PR: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/setup-python@v5, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
sdist: .github#2

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Release-plz · 34591495282
Triggered via workflow_dispatch about 9 minutes ago

JOBS
✓ Release-plz release in 19s (ID 103237584133)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz release output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ Publish plan in 4s (ID 103237677116)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Compute publish plan
  ✓ Post Checkout repository
  ✓ Complete job
✓ Release-plz PR in 26s (ID 103237677379)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz PR output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ sdist in 20s (ID 103237708043)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Build sdist
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* macos universal2 (ID 103237708069)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
✓ linux x86_64 in 7m47s (ID 103237708088)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  ✓ Build wheel
  ✓ Smoke test (x86_64 only)
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ linux aarch64 in 8m1s (ID 103237708095)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  ✓ Build wheel
  - Smoke test (x86_64 only)
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* windows x86_64 (ID 103237708155)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
✓ Merge release PR in 3s (ID 103237804576)
  ✓ Set up job
  ✓ Resolve release PR
  - Wait for checks to register
  - Wait for checks to pass
  - Squash-merge release PR
  ✓ Complete job

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz release: .github#5

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Publish plan: .github#6

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz PR: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/setup-python@v5, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
sdist: .github#2

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Release-plz · 34591495282
Triggered via workflow_dispatch about 9 minutes ago

JOBS
✓ Release-plz release in 19s (ID 103237584133)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz release output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ Publish plan in 4s (ID 103237677116)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Compute publish plan
  ✓ Post Checkout repository
  ✓ Complete job
✓ Release-plz PR in 26s (ID 103237677379)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz PR output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ sdist in 20s (ID 103237708043)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Build sdist
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* macos universal2 (ID 103237708069)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
✓ linux x86_64 in 7m47s (ID 103237708088)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  ✓ Build wheel
  ✓ Smoke test (x86_64 only)
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ linux aarch64 in 8m1s (ID 103237708095)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  ✓ Build wheel
  - Smoke test (x86_64 only)
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* windows x86_64 (ID 103237708155)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
✓ Merge release PR in 3s (ID 103237804576)
  ✓ Set up job
  ✓ Resolve release PR
  - Wait for checks to register
  - Wait for checks to pass
  - Squash-merge release PR
  ✓ Complete job

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz release: .github#5

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Publish plan: .github#6

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz PR: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/setup-python@v5, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
sdist: .github#2

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Release-plz · 34591495282
Triggered via workflow_dispatch about 9 minutes ago

JOBS
✓ Release-plz release in 19s (ID 103237584133)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz release output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ Publish plan in 4s (ID 103237677116)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Compute publish plan
  ✓ Post Checkout repository
  ✓ Complete job
✓ Release-plz PR in 26s (ID 103237677379)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz PR output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ sdist in 20s (ID 103237708043)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Build sdist
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* macos universal2 (ID 103237708069)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
✓ linux x86_64 in 7m47s (ID 103237708088)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  ✓ Build wheel
  ✓ Smoke test (x86_64 only)
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ linux aarch64 in 8m1s (ID 103237708095)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  ✓ Build wheel
  - Smoke test (x86_64 only)
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* windows x86_64 (ID 103237708155)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
✓ Merge release PR in 3s (ID 103237804576)
  ✓ Set up job
  ✓ Resolve release PR
  - Wait for checks to register
  - Wait for checks to pass
  - Squash-merge release PR
  ✓ Complete job

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz release: .github#5

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Publish plan: .github#6

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz PR: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/setup-python@v5, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
sdist: .github#2

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Release-plz · 34591495282
Triggered via workflow_dispatch about 9 minutes ago

JOBS
✓ Release-plz release in 19s (ID 103237584133)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz release output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ Publish plan in 4s (ID 103237677116)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Compute publish plan
  ✓ Post Checkout repository
  ✓ Complete job
✓ Release-plz PR in 26s (ID 103237677379)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz PR output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ sdist in 20s (ID 103237708043)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Build sdist
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* macos universal2 (ID 103237708069)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
✓ linux x86_64 in 7m47s (ID 103237708088)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  ✓ Build wheel
  ✓ Smoke test (x86_64 only)
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ linux aarch64 in 8m1s (ID 103237708095)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  ✓ Build wheel
  - Smoke test (x86_64 only)
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* windows x86_64 (ID 103237708155)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
✓ Merge release PR in 3s (ID 103237804576)
  ✓ Set up job
  ✓ Resolve release PR
  - Wait for checks to register
  - Wait for checks to pass
  - Squash-merge release PR
  ✓ Complete job

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz release: .github#5

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Publish plan: .github#6

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz PR: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/setup-python@v5, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
sdist: .github#2

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Release-plz · 34591495282
Triggered via workflow_dispatch about 9 minutes ago

JOBS
✓ Release-plz release in 19s (ID 103237584133)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz release output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ Publish plan in 4s (ID 103237677116)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Compute publish plan
  ✓ Post Checkout repository
  ✓ Complete job
✓ Release-plz PR in 26s (ID 103237677379)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz PR output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ sdist in 20s (ID 103237708043)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Build sdist
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* macos universal2 (ID 103237708069)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
✓ linux x86_64 in 7m47s (ID 103237708088)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  ✓ Build wheel
  ✓ Smoke test (x86_64 only)
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ linux aarch64 in 8m1s (ID 103237708095)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  ✓ Build wheel
  - Smoke test (x86_64 only)
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* windows x86_64 (ID 103237708155)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
✓ Merge release PR in 3s (ID 103237804576)
  ✓ Set up job
  ✓ Resolve release PR
  - Wait for checks to register
  - Wait for checks to pass
  - Squash-merge release PR
  ✓ Complete job

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz release: .github#5

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Publish plan: .github#6

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz PR: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/setup-python@v5, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
sdist: .github#2

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Release-plz · 34591495282
Triggered via workflow_dispatch about 9 minutes ago

JOBS
✓ Release-plz release in 19s (ID 103237584133)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz release output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ Publish plan in 4s (ID 103237677116)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Compute publish plan
  ✓ Post Checkout repository
  ✓ Complete job
✓ Release-plz PR in 26s (ID 103237677379)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz PR output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ sdist in 20s (ID 103237708043)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Build sdist
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* macos universal2 (ID 103237708069)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
✓ linux x86_64 in 7m47s (ID 103237708088)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  ✓ Build wheel
  ✓ Smoke test (x86_64 only)
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ linux aarch64 in 8m1s (ID 103237708095)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  ✓ Build wheel
  - Smoke test (x86_64 only)
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* windows x86_64 (ID 103237708155)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
✓ Merge release PR in 3s (ID 103237804576)
  ✓ Set up job
  ✓ Resolve release PR
  - Wait for checks to register
  - Wait for checks to pass
  - Squash-merge release PR
  ✓ Complete job

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz release: .github#5

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Publish plan: .github#6

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz PR: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/setup-python@v5, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
sdist: .github#2

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Release-plz · 34591495282
Triggered via workflow_dispatch about 9 minutes ago

JOBS
✓ Release-plz release in 19s (ID 103237584133)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz release output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ Publish plan in 4s (ID 103237677116)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Compute publish plan
  ✓ Post Checkout repository
  ✓ Complete job
✓ Release-plz PR in 26s (ID 103237677379)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz PR output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ sdist in 20s (ID 103237708043)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Build sdist
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* macos universal2 (ID 103237708069)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
✓ linux x86_64 in 7m47s (ID 103237708088)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  ✓ Build wheel
  ✓ Smoke test (x86_64 only)
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ linux aarch64 in 8m1s (ID 103237708095)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  ✓ Build wheel
  - Smoke test (x86_64 only)
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* windows x86_64 (ID 103237708155)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
✓ Merge release PR in 3s (ID 103237804576)
  ✓ Set up job
  ✓ Resolve release PR
  - Wait for checks to register
  - Wait for checks to pass
  - Squash-merge release PR
  ✓ Complete job

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz release: .github#5

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Publish plan: .github#6

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz PR: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/setup-python@v5, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
sdist: .github#2

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Release-plz · 34591495282
Triggered via workflow_dispatch about 9 minutes ago

JOBS
✓ Release-plz release in 19s (ID 103237584133)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz release output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ Publish plan in 4s (ID 103237677116)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Compute publish plan
  ✓ Post Checkout repository
  ✓ Complete job
✓ Release-plz PR in 26s (ID 103237677379)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz PR output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ sdist in 20s (ID 103237708043)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Build sdist
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* macos universal2 (ID 103237708069)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
✓ linux x86_64 in 7m47s (ID 103237708088)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  ✓ Build wheel
  ✓ Smoke test (x86_64 only)
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ linux aarch64 in 8m1s (ID 103237708095)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  ✓ Build wheel
  - Smoke test (x86_64 only)
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* windows x86_64 (ID 103237708155)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
✓ Merge release PR in 3s (ID 103237804576)
  ✓ Set up job
  ✓ Resolve release PR
  - Wait for checks to register
  - Wait for checks to pass
  - Squash-merge release PR
  ✓ Complete job

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz release: .github#5

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Publish plan: .github#6

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz PR: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/setup-python@v5, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
sdist: .github#2

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Release-plz · 34591495282
Triggered via workflow_dispatch about 9 minutes ago

JOBS
✓ Release-plz release in 19s (ID 103237584133)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz release output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ Publish plan in 4s (ID 103237677116)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Compute publish plan
  ✓ Post Checkout repository
  ✓ Complete job
✓ Release-plz PR in 26s (ID 103237677379)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz PR output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ sdist in 20s (ID 103237708043)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Build sdist
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* macos universal2 (ID 103237708069)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
✓ linux x86_64 in 7m47s (ID 103237708088)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  ✓ Build wheel
  ✓ Smoke test (x86_64 only)
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ linux aarch64 in 8m1s (ID 103237708095)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  ✓ Build wheel
  - Smoke test (x86_64 only)
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* windows x86_64 (ID 103237708155)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
✓ Merge release PR in 3s (ID 103237804576)
  ✓ Set up job
  ✓ Resolve release PR
  - Wait for checks to register
  - Wait for checks to pass
  - Squash-merge release PR
  ✓ Complete job

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz release: .github#5

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Publish plan: .github#6

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz PR: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/setup-python@v5, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
sdist: .github#2

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Release-plz · 34591495282
Triggered via workflow_dispatch about 9 minutes ago

JOBS
✓ Release-plz release in 19s (ID 103237584133)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz release output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ Publish plan in 4s (ID 103237677116)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Compute publish plan
  ✓ Post Checkout repository
  ✓ Complete job
✓ Release-plz PR in 26s (ID 103237677379)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz PR output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ sdist in 20s (ID 103237708043)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Build sdist
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* macos universal2 (ID 103237708069)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
✓ linux x86_64 in 7m47s (ID 103237708088)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  ✓ Build wheel
  ✓ Smoke test (x86_64 only)
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ linux aarch64 in 8m1s (ID 103237708095)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  ✓ Build wheel
  - Smoke test (x86_64 only)
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* windows x86_64 (ID 103237708155)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
✓ Merge release PR in 3s (ID 103237804576)
  ✓ Set up job
  ✓ Resolve release PR
  - Wait for checks to register
  - Wait for checks to pass
  - Squash-merge release PR
  ✓ Complete job

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz release: .github#5

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Publish plan: .github#6

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz PR: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/setup-python@v5, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
sdist: .github#2

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Release-plz · 34591495282
Triggered via workflow_dispatch about 9 minutes ago

JOBS
✓ Release-plz release in 19s (ID 103237584133)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz release output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ Publish plan in 4s (ID 103237677116)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Compute publish plan
  ✓ Post Checkout repository
  ✓ Complete job
✓ Release-plz PR in 26s (ID 103237677379)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz PR output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ sdist in 20s (ID 103237708043)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Build sdist
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* macos universal2 (ID 103237708069)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
✓ linux x86_64 in 7m47s (ID 103237708088)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  ✓ Build wheel
  ✓ Smoke test (x86_64 only)
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ linux aarch64 in 8m1s (ID 103237708095)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  ✓ Build wheel
  - Smoke test (x86_64 only)
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* windows x86_64 (ID 103237708155)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
✓ Merge release PR in 3s (ID 103237804576)
  ✓ Set up job
  ✓ Resolve release PR
  - Wait for checks to register
  - Wait for checks to pass
  - Squash-merge release PR
  ✓ Complete job

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz release: .github#5

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Publish plan: .github#6

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz PR: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/setup-python@v5, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
sdist: .github#2

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Release-plz · 34591495282
Triggered via workflow_dispatch about 9 minutes ago

JOBS
✓ Release-plz release in 19s (ID 103237584133)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz release output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ Publish plan in 4s (ID 103237677116)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Compute publish plan
  ✓ Post Checkout repository
  ✓ Complete job
✓ Release-plz PR in 26s (ID 103237677379)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz PR output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ sdist in 20s (ID 103237708043)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Build sdist
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* macos universal2 (ID 103237708069)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
✓ linux x86_64 in 7m47s (ID 103237708088)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  ✓ Build wheel
  ✓ Smoke test (x86_64 only)
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ linux aarch64 in 8m1s (ID 103237708095)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  ✓ Build wheel
  - Smoke test (x86_64 only)
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* windows x86_64 (ID 103237708155)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
✓ Merge release PR in 3s (ID 103237804576)
  ✓ Set up job
  ✓ Resolve release PR
  - Wait for checks to register
  - Wait for checks to pass
  - Squash-merge release PR
  ✓ Complete job

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz release: .github#5

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Publish plan: .github#6

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz PR: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/setup-python@v5, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
sdist: .github#2

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Release-plz · 34591495282
Triggered via workflow_dispatch about 9 minutes ago

JOBS
✓ Release-plz release in 19s (ID 103237584133)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz release output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ Publish plan in 4s (ID 103237677116)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Compute publish plan
  ✓ Post Checkout repository
  ✓ Complete job
✓ Release-plz PR in 26s (ID 103237677379)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz PR output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ sdist in 20s (ID 103237708043)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Build sdist
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* macos universal2 (ID 103237708069)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
✓ linux x86_64 in 7m47s (ID 103237708088)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  ✓ Build wheel
  ✓ Smoke test (x86_64 only)
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ linux aarch64 in 8m1s (ID 103237708095)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  ✓ Build wheel
  - Smoke test (x86_64 only)
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* windows x86_64 (ID 103237708155)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
✓ Merge release PR in 3s (ID 103237804576)
  ✓ Set up job
  ✓ Resolve release PR
  - Wait for checks to register
  - Wait for checks to pass
  - Squash-merge release PR
  ✓ Complete job

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz release: .github#5

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Publish plan: .github#6

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz PR: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/setup-python@v5, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
sdist: .github#2

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Release-plz · 34591495282
Triggered via workflow_dispatch about 9 minutes ago

JOBS
✓ Release-plz release in 19s (ID 103237584133)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz release output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ Publish plan in 4s (ID 103237677116)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Compute publish plan
  ✓ Post Checkout repository
  ✓ Complete job
✓ Release-plz PR in 26s (ID 103237677379)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz PR output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ sdist in 20s (ID 103237708043)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Build sdist
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* macos universal2 (ID 103237708069)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
✓ linux x86_64 in 7m47s (ID 103237708088)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  ✓ Build wheel
  ✓ Smoke test (x86_64 only)
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ linux aarch64 in 8m1s (ID 103237708095)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  ✓ Build wheel
  - Smoke test (x86_64 only)
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* windows x86_64 (ID 103237708155)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
✓ Merge release PR in 3s (ID 103237804576)
  ✓ Set up job
  ✓ Resolve release PR
  - Wait for checks to register
  - Wait for checks to pass
  - Squash-merge release PR
  ✓ Complete job

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz release: .github#5

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Publish plan: .github#6

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz PR: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/setup-python@v5, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
sdist: .github#2

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Release-plz · 34591495282
Triggered via workflow_dispatch about 10 minutes ago

JOBS
✓ Release-plz release in 19s (ID 103237584133)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz release output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ Publish plan in 4s (ID 103237677116)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Compute publish plan
  ✓ Post Checkout repository
  ✓ Complete job
✓ Release-plz PR in 26s (ID 103237677379)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz PR output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ sdist in 20s (ID 103237708043)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Build sdist
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* macos universal2 (ID 103237708069)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
✓ linux x86_64 in 7m47s (ID 103237708088)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  ✓ Build wheel
  ✓ Smoke test (x86_64 only)
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ linux aarch64 in 8m1s (ID 103237708095)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  ✓ Build wheel
  - Smoke test (x86_64 only)
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* windows x86_64 (ID 103237708155)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
✓ Merge release PR in 3s (ID 103237804576)
  ✓ Set up job
  ✓ Resolve release PR
  - Wait for checks to register
  - Wait for checks to pass
  - Squash-merge release PR
  ✓ Complete job

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz release: .github#5

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Publish plan: .github#6

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz PR: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/setup-python@v5, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
sdist: .github#2

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Release-plz · 34591495282
Triggered via workflow_dispatch about 10 minutes ago

JOBS
✓ Release-plz release in 19s (ID 103237584133)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz release output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ Publish plan in 4s (ID 103237677116)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Compute publish plan
  ✓ Post Checkout repository
  ✓ Complete job
✓ Release-plz PR in 26s (ID 103237677379)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz PR output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ sdist in 20s (ID 103237708043)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Build sdist
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* macos universal2 (ID 103237708069)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
✓ linux x86_64 in 7m47s (ID 103237708088)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  ✓ Build wheel
  ✓ Smoke test (x86_64 only)
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ linux aarch64 in 8m1s (ID 103237708095)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  ✓ Build wheel
  - Smoke test (x86_64 only)
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* windows x86_64 (ID 103237708155)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
✓ Merge release PR in 3s (ID 103237804576)
  ✓ Set up job
  ✓ Resolve release PR
  - Wait for checks to register
  - Wait for checks to pass
  - Squash-merge release PR
  ✓ Complete job

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz release: .github#5

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Publish plan: .github#6

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz PR: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/setup-python@v5, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
sdist: .github#2

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Release-plz · 34591495282
Triggered via workflow_dispatch about 10 minutes ago

JOBS
✓ Release-plz release in 19s (ID 103237584133)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz release output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ Publish plan in 4s (ID 103237677116)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Compute publish plan
  ✓ Post Checkout repository
  ✓ Complete job
✓ Release-plz PR in 26s (ID 103237677379)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz PR output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ sdist in 20s (ID 103237708043)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Build sdist
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* macos universal2 (ID 103237708069)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
✓ linux x86_64 in 7m47s (ID 103237708088)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  ✓ Build wheel
  ✓ Smoke test (x86_64 only)
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ linux aarch64 in 8m1s (ID 103237708095)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  ✓ Build wheel
  - Smoke test (x86_64 only)
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* windows x86_64 (ID 103237708155)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
✓ Merge release PR in 3s (ID 103237804576)
  ✓ Set up job
  ✓ Resolve release PR
  - Wait for checks to register
  - Wait for checks to pass
  - Squash-merge release PR
  ✓ Complete job

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz release: .github#5

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Publish plan: .github#6

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz PR: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/setup-python@v5, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
sdist: .github#2

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Release-plz · 34591495282
Triggered via workflow_dispatch about 10 minutes ago

JOBS
✓ Release-plz release in 19s (ID 103237584133)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz release output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ Publish plan in 4s (ID 103237677116)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Compute publish plan
  ✓ Post Checkout repository
  ✓ Complete job
✓ Release-plz PR in 26s (ID 103237677379)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz PR output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ sdist in 20s (ID 103237708043)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Build sdist
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* macos universal2 (ID 103237708069)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
✓ linux x86_64 in 7m47s (ID 103237708088)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  ✓ Build wheel
  ✓ Smoke test (x86_64 only)
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ linux aarch64 in 8m1s (ID 103237708095)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  ✓ Build wheel
  - Smoke test (x86_64 only)
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* windows x86_64 (ID 103237708155)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
✓ Merge release PR in 3s (ID 103237804576)
  ✓ Set up job
  ✓ Resolve release PR
  - Wait for checks to register
  - Wait for checks to pass
  - Squash-merge release PR
  ✓ Complete job

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz release: .github#5

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Publish plan: .github#6

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz PR: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/setup-python@v5, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
sdist: .github#2

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Release-plz · 34591495282
Triggered via workflow_dispatch about 10 minutes ago

JOBS
✓ Release-plz release in 19s (ID 103237584133)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz release output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ Publish plan in 4s (ID 103237677116)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Compute publish plan
  ✓ Post Checkout repository
  ✓ Complete job
✓ Release-plz PR in 26s (ID 103237677379)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz PR output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ sdist in 20s (ID 103237708043)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Build sdist
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* macos universal2 (ID 103237708069)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
✓ linux x86_64 in 7m47s (ID 103237708088)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  ✓ Build wheel
  ✓ Smoke test (x86_64 only)
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ linux aarch64 in 8m1s (ID 103237708095)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  ✓ Build wheel
  - Smoke test (x86_64 only)
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* windows x86_64 (ID 103237708155)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
✓ Merge release PR in 3s (ID 103237804576)
  ✓ Set up job
  ✓ Resolve release PR
  - Wait for checks to register
  - Wait for checks to pass
  - Squash-merge release PR
  ✓ Complete job

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz release: .github#5

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Publish plan: .github#6

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz PR: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/setup-python@v5, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
sdist: .github#2

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Release-plz · 34591495282
Triggered via workflow_dispatch about 10 minutes ago

JOBS
✓ Release-plz release in 19s (ID 103237584133)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz release output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ Publish plan in 4s (ID 103237677116)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Compute publish plan
  ✓ Post Checkout repository
  ✓ Complete job
✓ Release-plz PR in 26s (ID 103237677379)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz PR output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ sdist in 20s (ID 103237708043)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Build sdist
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* macos universal2 (ID 103237708069)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
✓ linux x86_64 in 7m47s (ID 103237708088)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  ✓ Build wheel
  ✓ Smoke test (x86_64 only)
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ linux aarch64 in 8m1s (ID 103237708095)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  ✓ Build wheel
  - Smoke test (x86_64 only)
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* windows x86_64 (ID 103237708155)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
✓ Merge release PR in 3s (ID 103237804576)
  ✓ Set up job
  ✓ Resolve release PR
  - Wait for checks to register
  - Wait for checks to pass
  - Squash-merge release PR
  ✓ Complete job

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz release: .github#5

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Publish plan: .github#6

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz PR: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/setup-python@v5, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
sdist: .github#2

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Release-plz · 34591495282
Triggered via workflow_dispatch about 10 minutes ago

JOBS
✓ Release-plz release in 19s (ID 103237584133)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz release output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ Publish plan in 4s (ID 103237677116)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Compute publish plan
  ✓ Post Checkout repository
  ✓ Complete job
✓ Release-plz PR in 26s (ID 103237677379)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz PR output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ sdist in 20s (ID 103237708043)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Build sdist
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* macos universal2 (ID 103237708069)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
✓ linux x86_64 in 7m47s (ID 103237708088)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  ✓ Build wheel
  ✓ Smoke test (x86_64 only)
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ linux aarch64 in 8m1s (ID 103237708095)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  ✓ Build wheel
  - Smoke test (x86_64 only)
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* windows x86_64 (ID 103237708155)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
✓ Merge release PR in 3s (ID 103237804576)
  ✓ Set up job
  ✓ Resolve release PR
  - Wait for checks to register
  - Wait for checks to pass
  - Squash-merge release PR
  ✓ Complete job

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz release: .github#5

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Publish plan: .github#6

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz PR: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/setup-python@v5, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
sdist: .github#2

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Release-plz · 34591495282
Triggered via workflow_dispatch about 10 minutes ago

JOBS
✓ Release-plz release in 19s (ID 103237584133)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz release output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ Publish plan in 4s (ID 103237677116)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Compute publish plan
  ✓ Post Checkout repository
  ✓ Complete job
✓ Release-plz PR in 26s (ID 103237677379)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz PR output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ sdist in 20s (ID 103237708043)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Build sdist
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* macos universal2 (ID 103237708069)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
✓ linux x86_64 in 7m47s (ID 103237708088)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  ✓ Build wheel
  ✓ Smoke test (x86_64 only)
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ linux aarch64 in 8m1s (ID 103237708095)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  ✓ Build wheel
  - Smoke test (x86_64 only)
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* windows x86_64 (ID 103237708155)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
✓ Merge release PR in 3s (ID 103237804576)
  ✓ Set up job
  ✓ Resolve release PR
  - Wait for checks to register
  - Wait for checks to pass
  - Squash-merge release PR
  ✓ Complete job

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz release: .github#5

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Publish plan: .github#6

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz PR: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/setup-python@v5, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
sdist: .github#2

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Release-plz · 34591495282
Triggered via workflow_dispatch about 10 minutes ago

JOBS
✓ Release-plz release in 19s (ID 103237584133)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz release output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ Publish plan in 4s (ID 103237677116)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Compute publish plan
  ✓ Post Checkout repository
  ✓ Complete job
✓ Release-plz PR in 26s (ID 103237677379)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz PR output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ sdist in 20s (ID 103237708043)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Build sdist
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* macos universal2 (ID 103237708069)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
✓ linux x86_64 in 7m47s (ID 103237708088)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  ✓ Build wheel
  ✓ Smoke test (x86_64 only)
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ linux aarch64 in 8m1s (ID 103237708095)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  ✓ Build wheel
  - Smoke test (x86_64 only)
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* windows x86_64 (ID 103237708155)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
✓ Merge release PR in 3s (ID 103237804576)
  ✓ Set up job
  ✓ Resolve release PR
  - Wait for checks to register
  - Wait for checks to pass
  - Squash-merge release PR
  ✓ Complete job

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz release: .github#5

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Publish plan: .github#6

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz PR: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/setup-python@v5, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
sdist: .github#2

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Release-plz · 34591495282
Triggered via workflow_dispatch about 10 minutes ago

JOBS
✓ Release-plz release in 19s (ID 103237584133)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz release output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ Publish plan in 4s (ID 103237677116)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Compute publish plan
  ✓ Post Checkout repository
  ✓ Complete job
✓ Release-plz PR in 26s (ID 103237677379)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz PR output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ sdist in 20s (ID 103237708043)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Build sdist
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* macos universal2 (ID 103237708069)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
✓ linux x86_64 in 7m47s (ID 103237708088)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  ✓ Build wheel
  ✓ Smoke test (x86_64 only)
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ linux aarch64 in 8m1s (ID 103237708095)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  ✓ Build wheel
  - Smoke test (x86_64 only)
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* windows x86_64 (ID 103237708155)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
✓ Merge release PR in 3s (ID 103237804576)
  ✓ Set up job
  ✓ Resolve release PR
  - Wait for checks to register
  - Wait for checks to pass
  - Squash-merge release PR
  ✓ Complete job

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz release: .github#5

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Publish plan: .github#6

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz PR: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/setup-python@v5, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
sdist: .github#2

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Release-plz · 34591495282
Triggered via workflow_dispatch about 10 minutes ago

JOBS
✓ Release-plz release in 19s (ID 103237584133)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz release output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ Publish plan in 4s (ID 103237677116)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Compute publish plan
  ✓ Post Checkout repository
  ✓ Complete job
✓ Release-plz PR in 26s (ID 103237677379)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz PR output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ sdist in 20s (ID 103237708043)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Build sdist
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* macos universal2 (ID 103237708069)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
✓ linux x86_64 in 7m47s (ID 103237708088)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  ✓ Build wheel
  ✓ Smoke test (x86_64 only)
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ linux aarch64 in 8m1s (ID 103237708095)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  ✓ Build wheel
  - Smoke test (x86_64 only)
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* windows x86_64 (ID 103237708155)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
✓ Merge release PR in 3s (ID 103237804576)
  ✓ Set up job
  ✓ Resolve release PR
  - Wait for checks to register
  - Wait for checks to pass
  - Squash-merge release PR
  ✓ Complete job

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz release: .github#5

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Publish plan: .github#6

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz PR: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/setup-python@v5, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
sdist: .github#2

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Release-plz · 34591495282
Triggered via workflow_dispatch about 10 minutes ago

JOBS
✓ Release-plz release in 19s (ID 103237584133)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz release output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ Publish plan in 4s (ID 103237677116)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Compute publish plan
  ✓ Post Checkout repository
  ✓ Complete job
✓ Release-plz PR in 26s (ID 103237677379)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz PR output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ sdist in 20s (ID 103237708043)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Build sdist
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* macos universal2 (ID 103237708069)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
✓ linux x86_64 in 7m47s (ID 103237708088)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  ✓ Build wheel
  ✓ Smoke test (x86_64 only)
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ linux aarch64 in 8m1s (ID 103237708095)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  ✓ Build wheel
  - Smoke test (x86_64 only)
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* windows x86_64 (ID 103237708155)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
✓ Merge release PR in 3s (ID 103237804576)
  ✓ Set up job
  ✓ Resolve release PR
  - Wait for checks to register
  - Wait for checks to pass
  - Squash-merge release PR
  ✓ Complete job

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz release: .github#5

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Publish plan: .github#6

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz PR: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/setup-python@v5, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
sdist: .github#2

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Release-plz · 34591495282
Triggered via workflow_dispatch about 10 minutes ago

JOBS
✓ Release-plz release in 19s (ID 103237584133)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz release output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ Publish plan in 4s (ID 103237677116)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Compute publish plan
  ✓ Post Checkout repository
  ✓ Complete job
✓ Release-plz PR in 26s (ID 103237677379)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz PR output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ sdist in 20s (ID 103237708043)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Build sdist
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* macos universal2 (ID 103237708069)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
✓ linux x86_64 in 7m47s (ID 103237708088)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  ✓ Build wheel
  ✓ Smoke test (x86_64 only)
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ linux aarch64 in 8m1s (ID 103237708095)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  ✓ Build wheel
  - Smoke test (x86_64 only)
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* windows x86_64 (ID 103237708155)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
✓ Merge release PR in 3s (ID 103237804576)
  ✓ Set up job
  ✓ Resolve release PR
  - Wait for checks to register
  - Wait for checks to pass
  - Squash-merge release PR
  ✓ Complete job

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz release: .github#5

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Publish plan: .github#6

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz PR: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/setup-python@v5, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
sdist: .github#2

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Release-plz · 34591495282
Triggered via workflow_dispatch about 10 minutes ago

JOBS
✓ Release-plz release in 19s (ID 103237584133)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz release output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ Publish plan in 4s (ID 103237677116)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Compute publish plan
  ✓ Post Checkout repository
  ✓ Complete job
✓ Release-plz PR in 26s (ID 103237677379)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz PR output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ sdist in 20s (ID 103237708043)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Build sdist
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* macos universal2 (ID 103237708069)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
✓ linux x86_64 in 7m47s (ID 103237708088)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  ✓ Build wheel
  ✓ Smoke test (x86_64 only)
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ linux aarch64 in 8m1s (ID 103237708095)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  ✓ Build wheel
  - Smoke test (x86_64 only)
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* windows x86_64 (ID 103237708155)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
✓ Merge release PR in 3s (ID 103237804576)
  ✓ Set up job
  ✓ Resolve release PR
  - Wait for checks to register
  - Wait for checks to pass
  - Squash-merge release PR
  ✓ Complete job

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz release: .github#5

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Publish plan: .github#6

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz PR: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/setup-python@v5, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
sdist: .github#2

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Release-plz · 34591495282
Triggered via workflow_dispatch about 10 minutes ago

JOBS
✓ Release-plz release in 19s (ID 103237584133)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz release output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ Publish plan in 4s (ID 103237677116)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Compute publish plan
  ✓ Post Checkout repository
  ✓ Complete job
✓ Release-plz PR in 26s (ID 103237677379)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz PR output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ sdist in 20s (ID 103237708043)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Build sdist
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* macos universal2 (ID 103237708069)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
✓ linux x86_64 in 7m47s (ID 103237708088)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  ✓ Build wheel
  ✓ Smoke test (x86_64 only)
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ linux aarch64 in 8m1s (ID 103237708095)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  ✓ Build wheel
  - Smoke test (x86_64 only)
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* windows x86_64 (ID 103237708155)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
✓ Merge release PR in 3s (ID 103237804576)
  ✓ Set up job
  ✓ Resolve release PR
  - Wait for checks to register
  - Wait for checks to pass
  - Squash-merge release PR
  ✓ Complete job

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz release: .github#5

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Publish plan: .github#6

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz PR: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/setup-python@v5, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
sdist: .github#2

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Release-plz · 34591495282
Triggered via workflow_dispatch about 11 minutes ago

JOBS
✓ Release-plz release in 19s (ID 103237584133)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz release output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ Publish plan in 4s (ID 103237677116)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Compute publish plan
  ✓ Post Checkout repository
  ✓ Complete job
✓ Release-plz PR in 26s (ID 103237677379)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz PR output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ sdist in 20s (ID 103237708043)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Build sdist
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* macos universal2 (ID 103237708069)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
✓ linux x86_64 in 7m47s (ID 103237708088)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  ✓ Build wheel
  ✓ Smoke test (x86_64 only)
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ linux aarch64 in 8m1s (ID 103237708095)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  ✓ Build wheel
  - Smoke test (x86_64 only)
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* windows x86_64 (ID 103237708155)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
✓ Merge release PR in 3s (ID 103237804576)
  ✓ Set up job
  ✓ Resolve release PR
  - Wait for checks to register
  - Wait for checks to pass
  - Squash-merge release PR
  ✓ Complete job

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz release: .github#5

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Publish plan: .github#6

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz PR: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/setup-python@v5, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
sdist: .github#2

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Release-plz · 34591495282
Triggered via workflow_dispatch about 11 minutes ago

JOBS
✓ Release-plz release in 19s (ID 103237584133)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz release output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ Publish plan in 4s (ID 103237677116)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Compute publish plan
  ✓ Post Checkout repository
  ✓ Complete job
✓ Release-plz PR in 26s (ID 103237677379)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz PR output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ sdist in 20s (ID 103237708043)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Build sdist
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* macos universal2 (ID 103237708069)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
✓ linux x86_64 in 7m47s (ID 103237708088)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  ✓ Build wheel
  ✓ Smoke test (x86_64 only)
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ linux aarch64 in 8m1s (ID 103237708095)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  ✓ Build wheel
  - Smoke test (x86_64 only)
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* windows x86_64 (ID 103237708155)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
✓ Merge release PR in 3s (ID 103237804576)
  ✓ Set up job
  ✓ Resolve release PR
  - Wait for checks to register
  - Wait for checks to pass
  - Squash-merge release PR
  ✓ Complete job

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz release: .github#5

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Publish plan: .github#6

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz PR: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/setup-python@v5, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
sdist: .github#2

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Release-plz · 34591495282
Triggered via workflow_dispatch about 11 minutes ago

JOBS
✓ Release-plz release in 19s (ID 103237584133)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz release output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ Publish plan in 4s (ID 103237677116)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Compute publish plan
  ✓ Post Checkout repository
  ✓ Complete job
✓ Release-plz PR in 26s (ID 103237677379)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz PR output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ sdist in 20s (ID 103237708043)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Build sdist
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* macos universal2 (ID 103237708069)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
✓ linux x86_64 in 7m47s (ID 103237708088)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  ✓ Build wheel
  ✓ Smoke test (x86_64 only)
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ linux aarch64 in 8m1s (ID 103237708095)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  ✓ Build wheel
  - Smoke test (x86_64 only)
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* windows x86_64 (ID 103237708155)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
✓ Merge release PR in 3s (ID 103237804576)
  ✓ Set up job
  ✓ Resolve release PR
  - Wait for checks to register
  - Wait for checks to pass
  - Squash-merge release PR
  ✓ Complete job

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz release: .github#5

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Publish plan: .github#6

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz PR: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/setup-python@v5, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
sdist: .github#2

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Release-plz · 34591495282
Triggered via workflow_dispatch about 11 minutes ago

JOBS
✓ Release-plz release in 19s (ID 103237584133)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz release output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ Publish plan in 4s (ID 103237677116)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Compute publish plan
  ✓ Post Checkout repository
  ✓ Complete job
✓ Release-plz PR in 26s (ID 103237677379)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz PR output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ sdist in 20s (ID 103237708043)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Build sdist
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* macos universal2 (ID 103237708069)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
✓ linux x86_64 in 7m47s (ID 103237708088)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  ✓ Build wheel
  ✓ Smoke test (x86_64 only)
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ linux aarch64 in 8m1s (ID 103237708095)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  ✓ Build wheel
  - Smoke test (x86_64 only)
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* windows x86_64 (ID 103237708155)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
✓ Merge release PR in 3s (ID 103237804576)
  ✓ Set up job
  ✓ Resolve release PR
  - Wait for checks to register
  - Wait for checks to pass
  - Squash-merge release PR
  ✓ Complete job

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz release: .github#5

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Publish plan: .github#6

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz PR: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/setup-python@v5, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
sdist: .github#2

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Release-plz · 34591495282
Triggered via workflow_dispatch about 11 minutes ago

JOBS
✓ Release-plz release in 19s (ID 103237584133)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz release output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ Publish plan in 4s (ID 103237677116)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Compute publish plan
  ✓ Post Checkout repository
  ✓ Complete job
✓ Release-plz PR in 26s (ID 103237677379)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz PR output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ sdist in 20s (ID 103237708043)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Build sdist
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* macos universal2 (ID 103237708069)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
✓ linux x86_64 in 7m47s (ID 103237708088)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  ✓ Build wheel
  ✓ Smoke test (x86_64 only)
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ linux aarch64 in 8m1s (ID 103237708095)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  ✓ Build wheel
  - Smoke test (x86_64 only)
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* windows x86_64 (ID 103237708155)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
✓ Merge release PR in 3s (ID 103237804576)
  ✓ Set up job
  ✓ Resolve release PR
  - Wait for checks to register
  - Wait for checks to pass
  - Squash-merge release PR
  ✓ Complete job

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz release: .github#5

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Publish plan: .github#6

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz PR: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/setup-python@v5, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
sdist: .github#2

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Release-plz · 34591495282
Triggered via workflow_dispatch about 11 minutes ago

JOBS
✓ Release-plz release in 19s (ID 103237584133)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz release output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ Publish plan in 4s (ID 103237677116)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Compute publish plan
  ✓ Post Checkout repository
  ✓ Complete job
✓ Release-plz PR in 26s (ID 103237677379)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz PR output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ sdist in 20s (ID 103237708043)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Build sdist
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* macos universal2 (ID 103237708069)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
✓ linux x86_64 in 7m47s (ID 103237708088)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  ✓ Build wheel
  ✓ Smoke test (x86_64 only)
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ linux aarch64 in 8m1s (ID 103237708095)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  ✓ Build wheel
  - Smoke test (x86_64 only)
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* windows x86_64 (ID 103237708155)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
✓ Merge release PR in 3s (ID 103237804576)
  ✓ Set up job
  ✓ Resolve release PR
  - Wait for checks to register
  - Wait for checks to pass
  - Squash-merge release PR
  ✓ Complete job

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz release: .github#5

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Publish plan: .github#6

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz PR: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/setup-python@v5, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
sdist: .github#2

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Release-plz · 34591495282
Triggered via workflow_dispatch about 11 minutes ago

JOBS
✓ Release-plz release in 19s (ID 103237584133)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz release output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ Publish plan in 4s (ID 103237677116)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Compute publish plan
  ✓ Post Checkout repository
  ✓ Complete job
✓ Release-plz PR in 26s (ID 103237677379)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz PR output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ sdist in 20s (ID 103237708043)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Build sdist
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* macos universal2 (ID 103237708069)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
✓ linux x86_64 in 7m47s (ID 103237708088)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  ✓ Build wheel
  ✓ Smoke test (x86_64 only)
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ linux aarch64 in 8m1s (ID 103237708095)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  ✓ Build wheel
  - Smoke test (x86_64 only)
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* windows x86_64 (ID 103237708155)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
✓ Merge release PR in 3s (ID 103237804576)
  ✓ Set up job
  ✓ Resolve release PR
  - Wait for checks to register
  - Wait for checks to pass
  - Squash-merge release PR
  ✓ Complete job

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz release: .github#5

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Publish plan: .github#6

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz PR: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/setup-python@v5, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
sdist: .github#2

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Release-plz · 34591495282
Triggered via workflow_dispatch about 11 minutes ago

JOBS
✓ Release-plz release in 19s (ID 103237584133)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz release output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ Publish plan in 4s (ID 103237677116)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Compute publish plan
  ✓ Post Checkout repository
  ✓ Complete job
✓ Release-plz PR in 26s (ID 103237677379)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz PR output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ sdist in 20s (ID 103237708043)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Build sdist
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* macos universal2 (ID 103237708069)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
✓ linux x86_64 in 7m47s (ID 103237708088)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  ✓ Build wheel
  ✓ Smoke test (x86_64 only)
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ linux aarch64 in 8m1s (ID 103237708095)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  ✓ Build wheel
  - Smoke test (x86_64 only)
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* windows x86_64 (ID 103237708155)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
✓ Merge release PR in 3s (ID 103237804576)
  ✓ Set up job
  ✓ Resolve release PR
  - Wait for checks to register
  - Wait for checks to pass
  - Squash-merge release PR
  ✓ Complete job

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz release: .github#5

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Publish plan: .github#6

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz PR: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/setup-python@v5, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
sdist: .github#2

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Release-plz · 34591495282
Triggered via workflow_dispatch about 11 minutes ago

JOBS
✓ Release-plz release in 19s (ID 103237584133)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz release output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ Publish plan in 4s (ID 103237677116)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Compute publish plan
  ✓ Post Checkout repository
  ✓ Complete job
✓ Release-plz PR in 26s (ID 103237677379)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz PR output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ sdist in 20s (ID 103237708043)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Build sdist
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* macos universal2 (ID 103237708069)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
✓ linux x86_64 in 7m47s (ID 103237708088)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  ✓ Build wheel
  ✓ Smoke test (x86_64 only)
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ linux aarch64 in 8m1s (ID 103237708095)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  ✓ Build wheel
  - Smoke test (x86_64 only)
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* windows x86_64 (ID 103237708155)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
✓ Merge release PR in 3s (ID 103237804576)
  ✓ Set up job
  ✓ Resolve release PR
  - Wait for checks to register
  - Wait for checks to pass
  - Squash-merge release PR
  ✓ Complete job

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz release: .github#5

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Publish plan: .github#6

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz PR: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/setup-python@v5, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
sdist: .github#2

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Release-plz · 34591495282
Triggered via workflow_dispatch about 11 minutes ago

JOBS
✓ Release-plz release in 19s (ID 103237584133)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz release output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ Publish plan in 4s (ID 103237677116)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Compute publish plan
  ✓ Post Checkout repository
  ✓ Complete job
✓ Release-plz PR in 26s (ID 103237677379)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz PR output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ sdist in 20s (ID 103237708043)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Build sdist
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* macos universal2 (ID 103237708069)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
✓ linux x86_64 in 7m47s (ID 103237708088)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  ✓ Build wheel
  ✓ Smoke test (x86_64 only)
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ linux aarch64 in 8m1s (ID 103237708095)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  ✓ Build wheel
  - Smoke test (x86_64 only)
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* windows x86_64 (ID 103237708155)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
✓ Merge release PR in 3s (ID 103237804576)
  ✓ Set up job
  ✓ Resolve release PR
  - Wait for checks to register
  - Wait for checks to pass
  - Squash-merge release PR
  ✓ Complete job

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz release: .github#5

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Publish plan: .github#6

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz PR: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/setup-python@v5, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
sdist: .github#2

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Release-plz · 34591495282
Triggered via workflow_dispatch about 11 minutes ago

JOBS
✓ Release-plz release in 19s (ID 103237584133)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz release output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ Publish plan in 4s (ID 103237677116)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Compute publish plan
  ✓ Post Checkout repository
  ✓ Complete job
✓ Release-plz PR in 26s (ID 103237677379)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz PR output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ sdist in 20s (ID 103237708043)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Build sdist
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* macos universal2 (ID 103237708069)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
✓ linux x86_64 in 7m47s (ID 103237708088)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  ✓ Build wheel
  ✓ Smoke test (x86_64 only)
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ linux aarch64 in 8m1s (ID 103237708095)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  ✓ Build wheel
  - Smoke test (x86_64 only)
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* windows x86_64 (ID 103237708155)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
✓ Merge release PR in 3s (ID 103237804576)
  ✓ Set up job
  ✓ Resolve release PR
  - Wait for checks to register
  - Wait for checks to pass
  - Squash-merge release PR
  ✓ Complete job

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz release: .github#5

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Publish plan: .github#6

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz PR: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/setup-python@v5, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
sdist: .github#2

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Release-plz · 34591495282
Triggered via workflow_dispatch about 11 minutes ago

JOBS
✓ Release-plz release in 19s (ID 103237584133)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz release output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ Publish plan in 4s (ID 103237677116)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Compute publish plan
  ✓ Post Checkout repository
  ✓ Complete job
✓ Release-plz PR in 26s (ID 103237677379)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz PR output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ sdist in 20s (ID 103237708043)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Build sdist
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* macos universal2 (ID 103237708069)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
✓ linux x86_64 in 7m47s (ID 103237708088)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  ✓ Build wheel
  ✓ Smoke test (x86_64 only)
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ linux aarch64 in 8m1s (ID 103237708095)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  ✓ Build wheel
  - Smoke test (x86_64 only)
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* windows x86_64 (ID 103237708155)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
✓ Merge release PR in 3s (ID 103237804576)
  ✓ Set up job
  ✓ Resolve release PR
  - Wait for checks to register
  - Wait for checks to pass
  - Squash-merge release PR
  ✓ Complete job

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz release: .github#5

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Publish plan: .github#6

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz PR: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/setup-python@v5, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
sdist: .github#2

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Release-plz · 34591495282
Triggered via workflow_dispatch about 11 minutes ago

JOBS
✓ Release-plz release in 19s (ID 103237584133)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz release output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ Publish plan in 4s (ID 103237677116)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Compute publish plan
  ✓ Post Checkout repository
  ✓ Complete job
✓ Release-plz PR in 26s (ID 103237677379)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz PR output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ sdist in 20s (ID 103237708043)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Build sdist
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* macos universal2 (ID 103237708069)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
✓ linux x86_64 in 7m47s (ID 103237708088)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  ✓ Build wheel
  ✓ Smoke test (x86_64 only)
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ linux aarch64 in 8m1s (ID 103237708095)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  ✓ Build wheel
  - Smoke test (x86_64 only)
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* windows x86_64 (ID 103237708155)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
✓ Merge release PR in 3s (ID 103237804576)
  ✓ Set up job
  ✓ Resolve release PR
  - Wait for checks to register
  - Wait for checks to pass
  - Squash-merge release PR
  ✓ Complete job

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz release: .github#5

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Publish plan: .github#6

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz PR: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/setup-python@v5, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
sdist: .github#2

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Release-plz · 34591495282
Triggered via workflow_dispatch about 11 minutes ago

JOBS
✓ Release-plz release in 19s (ID 103237584133)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz release output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ Publish plan in 4s (ID 103237677116)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Compute publish plan
  ✓ Post Checkout repository
  ✓ Complete job
✓ Release-plz PR in 26s (ID 103237677379)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz PR output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ sdist in 20s (ID 103237708043)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Build sdist
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* macos universal2 (ID 103237708069)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
✓ linux x86_64 in 7m47s (ID 103237708088)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  ✓ Build wheel
  ✓ Smoke test (x86_64 only)
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ linux aarch64 in 8m1s (ID 103237708095)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  ✓ Build wheel
  - Smoke test (x86_64 only)
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* windows x86_64 (ID 103237708155)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
✓ Merge release PR in 3s (ID 103237804576)
  ✓ Set up job
  ✓ Resolve release PR
  - Wait for checks to register
  - Wait for checks to pass
  - Squash-merge release PR
  ✓ Complete job

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz release: .github#5

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Publish plan: .github#6

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz PR: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/setup-python@v5, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
sdist: .github#2

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Release-plz · 34591495282
Triggered via workflow_dispatch about 11 minutes ago

JOBS
✓ Release-plz release in 19s (ID 103237584133)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz release output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ Publish plan in 4s (ID 103237677116)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Compute publish plan
  ✓ Post Checkout repository
  ✓ Complete job
✓ Release-plz PR in 26s (ID 103237677379)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz PR output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ sdist in 20s (ID 103237708043)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Build sdist
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* macos universal2 (ID 103237708069)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
✓ linux x86_64 in 7m47s (ID 103237708088)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  ✓ Build wheel
  ✓ Smoke test (x86_64 only)
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ linux aarch64 in 8m1s (ID 103237708095)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  ✓ Build wheel
  - Smoke test (x86_64 only)
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* windows x86_64 (ID 103237708155)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
✓ Merge release PR in 3s (ID 103237804576)
  ✓ Set up job
  ✓ Resolve release PR
  - Wait for checks to register
  - Wait for checks to pass
  - Squash-merge release PR
  ✓ Complete job

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz release: .github#5

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Publish plan: .github#6

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz PR: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/setup-python@v5, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
sdist: .github#2

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Release-plz · 34591495282
Triggered via workflow_dispatch about 12 minutes ago

JOBS
✓ Release-plz release in 19s (ID 103237584133)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz release output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ Publish plan in 4s (ID 103237677116)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Compute publish plan
  ✓ Post Checkout repository
  ✓ Complete job
✓ Release-plz PR in 26s (ID 103237677379)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz PR output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ sdist in 20s (ID 103237708043)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Build sdist
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* macos universal2 (ID 103237708069)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
✓ linux x86_64 in 7m47s (ID 103237708088)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  ✓ Build wheel
  ✓ Smoke test (x86_64 only)
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ linux aarch64 in 8m1s (ID 103237708095)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  ✓ Build wheel
  - Smoke test (x86_64 only)
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* windows x86_64 (ID 103237708155)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
✓ Merge release PR in 3s (ID 103237804576)
  ✓ Set up job
  ✓ Resolve release PR
  - Wait for checks to register
  - Wait for checks to pass
  - Squash-merge release PR
  ✓ Complete job

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz release: .github#5

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Publish plan: .github#6

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz PR: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/setup-python@v5, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
sdist: .github#2

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Release-plz · 34591495282
Triggered via workflow_dispatch about 12 minutes ago

JOBS
✓ Release-plz release in 19s (ID 103237584133)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz release output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ Publish plan in 4s (ID 103237677116)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Compute publish plan
  ✓ Post Checkout repository
  ✓ Complete job
✓ Release-plz PR in 26s (ID 103237677379)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz PR output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ sdist in 20s (ID 103237708043)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Build sdist
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* macos universal2 (ID 103237708069)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
✓ linux x86_64 in 7m47s (ID 103237708088)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  ✓ Build wheel
  ✓ Smoke test (x86_64 only)
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ linux aarch64 in 8m1s (ID 103237708095)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  ✓ Build wheel
  - Smoke test (x86_64 only)
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* windows x86_64 (ID 103237708155)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
✓ Merge release PR in 3s (ID 103237804576)
  ✓ Set up job
  ✓ Resolve release PR
  - Wait for checks to register
  - Wait for checks to pass
  - Squash-merge release PR
  ✓ Complete job

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz release: .github#5

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Publish plan: .github#6

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz PR: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/setup-python@v5, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
sdist: .github#2

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Release-plz · 34591495282
Triggered via workflow_dispatch about 12 minutes ago

JOBS
✓ Release-plz release in 19s (ID 103237584133)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz release output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ Publish plan in 4s (ID 103237677116)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Compute publish plan
  ✓ Post Checkout repository
  ✓ Complete job
✓ Release-plz PR in 26s (ID 103237677379)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz PR output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ sdist in 20s (ID 103237708043)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Build sdist
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* macos universal2 (ID 103237708069)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
✓ linux x86_64 in 7m47s (ID 103237708088)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  ✓ Build wheel
  ✓ Smoke test (x86_64 only)
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ linux aarch64 in 8m1s (ID 103237708095)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  ✓ Build wheel
  - Smoke test (x86_64 only)
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* windows x86_64 (ID 103237708155)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
✓ Merge release PR in 3s (ID 103237804576)
  ✓ Set up job
  ✓ Resolve release PR
  - Wait for checks to register
  - Wait for checks to pass
  - Squash-merge release PR
  ✓ Complete job

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz release: .github#5

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Publish plan: .github#6

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz PR: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/setup-python@v5, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
sdist: .github#2

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Release-plz · 34591495282
Triggered via workflow_dispatch about 12 minutes ago

JOBS
✓ Release-plz release in 19s (ID 103237584133)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz release output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ Publish plan in 4s (ID 103237677116)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Compute publish plan
  ✓ Post Checkout repository
  ✓ Complete job
✓ Release-plz PR in 26s (ID 103237677379)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz PR output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ sdist in 20s (ID 103237708043)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Build sdist
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* macos universal2 (ID 103237708069)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
✓ linux x86_64 in 7m47s (ID 103237708088)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  ✓ Build wheel
  ✓ Smoke test (x86_64 only)
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ linux aarch64 in 8m1s (ID 103237708095)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  ✓ Build wheel
  - Smoke test (x86_64 only)
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* windows x86_64 (ID 103237708155)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
✓ Merge release PR in 3s (ID 103237804576)
  ✓ Set up job
  ✓ Resolve release PR
  - Wait for checks to register
  - Wait for checks to pass
  - Squash-merge release PR
  ✓ Complete job

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz release: .github#5

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Publish plan: .github#6

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz PR: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/setup-python@v5, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
sdist: .github#2

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Release-plz · 34591495282
Triggered via workflow_dispatch about 12 minutes ago

JOBS
✓ Release-plz release in 19s (ID 103237584133)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz release output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ Publish plan in 4s (ID 103237677116)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Compute publish plan
  ✓ Post Checkout repository
  ✓ Complete job
✓ Release-plz PR in 26s (ID 103237677379)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz PR output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ sdist in 20s (ID 103237708043)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Build sdist
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* macos universal2 (ID 103237708069)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
✓ linux x86_64 in 7m47s (ID 103237708088)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  ✓ Build wheel
  ✓ Smoke test (x86_64 only)
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ linux aarch64 in 8m1s (ID 103237708095)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  ✓ Build wheel
  - Smoke test (x86_64 only)
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* windows x86_64 (ID 103237708155)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
✓ Merge release PR in 3s (ID 103237804576)
  ✓ Set up job
  ✓ Resolve release PR
  - Wait for checks to register
  - Wait for checks to pass
  - Squash-merge release PR
  ✓ Complete job

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz release: .github#5

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Publish plan: .github#6

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz PR: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/setup-python@v5, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
sdist: .github#2

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Release-plz · 34591495282
Triggered via workflow_dispatch about 12 minutes ago

JOBS
✓ Release-plz release in 19s (ID 103237584133)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz release output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ Publish plan in 4s (ID 103237677116)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Compute publish plan
  ✓ Post Checkout repository
  ✓ Complete job
✓ Release-plz PR in 26s (ID 103237677379)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz PR output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ sdist in 20s (ID 103237708043)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Build sdist
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* macos universal2 (ID 103237708069)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
✓ linux x86_64 in 7m47s (ID 103237708088)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  ✓ Build wheel
  ✓ Smoke test (x86_64 only)
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ linux aarch64 in 8m1s (ID 103237708095)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  ✓ Build wheel
  - Smoke test (x86_64 only)
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* windows x86_64 (ID 103237708155)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
✓ Merge release PR in 3s (ID 103237804576)
  ✓ Set up job
  ✓ Resolve release PR
  - Wait for checks to register
  - Wait for checks to pass
  - Squash-merge release PR
  ✓ Complete job

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz release: .github#5

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Publish plan: .github#6

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz PR: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/setup-python@v5, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
sdist: .github#2

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Release-plz · 34591495282
Triggered via workflow_dispatch about 12 minutes ago

JOBS
✓ Release-plz release in 19s (ID 103237584133)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz release output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ Publish plan in 4s (ID 103237677116)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Compute publish plan
  ✓ Post Checkout repository
  ✓ Complete job
✓ Release-plz PR in 26s (ID 103237677379)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz PR output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ sdist in 20s (ID 103237708043)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Build sdist
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* macos universal2 (ID 103237708069)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
✓ linux x86_64 in 7m47s (ID 103237708088)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  ✓ Build wheel
  ✓ Smoke test (x86_64 only)
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ linux aarch64 in 8m1s (ID 103237708095)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  ✓ Build wheel
  - Smoke test (x86_64 only)
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* windows x86_64 (ID 103237708155)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
✓ Merge release PR in 3s (ID 103237804576)
  ✓ Set up job
  ✓ Resolve release PR
  - Wait for checks to register
  - Wait for checks to pass
  - Squash-merge release PR
  ✓ Complete job

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz release: .github#5

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Publish plan: .github#6

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz PR: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/setup-python@v5, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
sdist: .github#2

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Release-plz · 34591495282
Triggered via workflow_dispatch about 12 minutes ago

JOBS
✓ Release-plz release in 19s (ID 103237584133)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz release output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ Publish plan in 4s (ID 103237677116)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Compute publish plan
  ✓ Post Checkout repository
  ✓ Complete job
✓ Release-plz PR in 26s (ID 103237677379)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz PR output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ sdist in 20s (ID 103237708043)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Build sdist
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* macos universal2 (ID 103237708069)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
✓ linux x86_64 in 7m47s (ID 103237708088)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  ✓ Build wheel
  ✓ Smoke test (x86_64 only)
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ linux aarch64 in 8m1s (ID 103237708095)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  ✓ Build wheel
  - Smoke test (x86_64 only)
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* windows x86_64 (ID 103237708155)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
✓ Merge release PR in 3s (ID 103237804576)
  ✓ Set up job
  ✓ Resolve release PR
  - Wait for checks to register
  - Wait for checks to pass
  - Squash-merge release PR
  ✓ Complete job

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz release: .github#5

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Publish plan: .github#6

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz PR: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/setup-python@v5, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
sdist: .github#2

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Release-plz · 34591495282
Triggered via workflow_dispatch about 12 minutes ago

JOBS
✓ Release-plz release in 19s (ID 103237584133)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz release output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ Publish plan in 4s (ID 103237677116)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Compute publish plan
  ✓ Post Checkout repository
  ✓ Complete job
✓ Release-plz PR in 26s (ID 103237677379)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz PR output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ sdist in 20s (ID 103237708043)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Build sdist
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* macos universal2 (ID 103237708069)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
✓ linux x86_64 in 7m47s (ID 103237708088)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  ✓ Build wheel
  ✓ Smoke test (x86_64 only)
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ linux aarch64 in 8m1s (ID 103237708095)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  ✓ Build wheel
  - Smoke test (x86_64 only)
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* windows x86_64 (ID 103237708155)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
✓ Merge release PR in 3s (ID 103237804576)
  ✓ Set up job
  ✓ Resolve release PR
  - Wait for checks to register
  - Wait for checks to pass
  - Squash-merge release PR
  ✓ Complete job

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz release: .github#5

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Publish plan: .github#6

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz PR: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/setup-python@v5, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
sdist: .github#2

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Release-plz · 34591495282
Triggered via workflow_dispatch about 12 minutes ago

JOBS
✓ Release-plz release in 19s (ID 103237584133)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz release output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ Publish plan in 4s (ID 103237677116)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Compute publish plan
  ✓ Post Checkout repository
  ✓ Complete job
✓ Release-plz PR in 26s (ID 103237677379)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz PR output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ sdist in 20s (ID 103237708043)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Build sdist
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* macos universal2 (ID 103237708069)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
✓ linux x86_64 in 7m47s (ID 103237708088)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  ✓ Build wheel
  ✓ Smoke test (x86_64 only)
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ linux aarch64 in 8m1s (ID 103237708095)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  ✓ Build wheel
  - Smoke test (x86_64 only)
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* windows x86_64 (ID 103237708155)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
✓ Merge release PR in 3s (ID 103237804576)
  ✓ Set up job
  ✓ Resolve release PR
  - Wait for checks to register
  - Wait for checks to pass
  - Squash-merge release PR
  ✓ Complete job

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz release: .github#5

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Publish plan: .github#6

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz PR: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/setup-python@v5, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
sdist: .github#2

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Release-plz · 34591495282
Triggered via workflow_dispatch about 12 minutes ago

JOBS
✓ Release-plz release in 19s (ID 103237584133)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz release output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ Publish plan in 4s (ID 103237677116)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Compute publish plan
  ✓ Post Checkout repository
  ✓ Complete job
✓ Release-plz PR in 26s (ID 103237677379)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz PR output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ sdist in 20s (ID 103237708043)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Build sdist
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* macos universal2 (ID 103237708069)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
✓ linux x86_64 in 7m47s (ID 103237708088)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  ✓ Build wheel
  ✓ Smoke test (x86_64 only)
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ linux aarch64 in 8m1s (ID 103237708095)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  ✓ Build wheel
  - Smoke test (x86_64 only)
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* windows x86_64 (ID 103237708155)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
✓ Merge release PR in 3s (ID 103237804576)
  ✓ Set up job
  ✓ Resolve release PR
  - Wait for checks to register
  - Wait for checks to pass
  - Squash-merge release PR
  ✓ Complete job

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz release: .github#5

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Publish plan: .github#6

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz PR: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/setup-python@v5, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
sdist: .github#2

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Release-plz · 34591495282
Triggered via workflow_dispatch about 12 minutes ago

JOBS
✓ Release-plz release in 19s (ID 103237584133)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz release output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ Publish plan in 4s (ID 103237677116)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Compute publish plan
  ✓ Post Checkout repository
  ✓ Complete job
✓ Release-plz PR in 26s (ID 103237677379)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz PR output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ sdist in 20s (ID 103237708043)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Build sdist
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* macos universal2 (ID 103237708069)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
✓ linux x86_64 in 7m47s (ID 103237708088)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  ✓ Build wheel
  ✓ Smoke test (x86_64 only)
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ linux aarch64 in 8m1s (ID 103237708095)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  ✓ Build wheel
  - Smoke test (x86_64 only)
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* windows x86_64 (ID 103237708155)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
✓ Merge release PR in 3s (ID 103237804576)
  ✓ Set up job
  ✓ Resolve release PR
  - Wait for checks to register
  - Wait for checks to pass
  - Squash-merge release PR
  ✓ Complete job

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz release: .github#5

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Publish plan: .github#6

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz PR: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/setup-python@v5, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
sdist: .github#2

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Release-plz · 34591495282
Triggered via workflow_dispatch about 12 minutes ago

JOBS
✓ Release-plz release in 19s (ID 103237584133)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz release output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ Publish plan in 4s (ID 103237677116)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Compute publish plan
  ✓ Post Checkout repository
  ✓ Complete job
✓ Release-plz PR in 26s (ID 103237677379)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz PR output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ sdist in 20s (ID 103237708043)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Build sdist
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* macos universal2 (ID 103237708069)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
✓ linux x86_64 in 7m47s (ID 103237708088)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  ✓ Build wheel
  ✓ Smoke test (x86_64 only)
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ linux aarch64 in 8m1s (ID 103237708095)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  ✓ Build wheel
  - Smoke test (x86_64 only)
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* windows x86_64 (ID 103237708155)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
✓ Merge release PR in 3s (ID 103237804576)
  ✓ Set up job
  ✓ Resolve release PR
  - Wait for checks to register
  - Wait for checks to pass
  - Squash-merge release PR
  ✓ Complete job

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz release: .github#5

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Publish plan: .github#6

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz PR: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/setup-python@v5, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
sdist: .github#2

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Release-plz · 34591495282
Triggered via workflow_dispatch about 12 minutes ago

JOBS
✓ Release-plz release in 19s (ID 103237584133)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz release output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ Publish plan in 4s (ID 103237677116)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Compute publish plan
  ✓ Post Checkout repository
  ✓ Complete job
✓ Release-plz PR in 26s (ID 103237677379)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz PR output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ sdist in 20s (ID 103237708043)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Build sdist
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* macos universal2 (ID 103237708069)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
✓ linux x86_64 in 7m47s (ID 103237708088)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  ✓ Build wheel
  ✓ Smoke test (x86_64 only)
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ linux aarch64 in 8m1s (ID 103237708095)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  ✓ Build wheel
  - Smoke test (x86_64 only)
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* windows x86_64 (ID 103237708155)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
✓ Merge release PR in 3s (ID 103237804576)
  ✓ Set up job
  ✓ Resolve release PR
  - Wait for checks to register
  - Wait for checks to pass
  - Squash-merge release PR
  ✓ Complete job

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz release: .github#5

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Publish plan: .github#6

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz PR: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/setup-python@v5, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
sdist: .github#2

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Release-plz · 34591495282
Triggered via workflow_dispatch about 12 minutes ago

JOBS
✓ Release-plz release in 19s (ID 103237584133)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz release output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ Publish plan in 4s (ID 103237677116)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Compute publish plan
  ✓ Post Checkout repository
  ✓ Complete job
✓ Release-plz PR in 26s (ID 103237677379)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz PR output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ sdist in 20s (ID 103237708043)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Build sdist
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* macos universal2 (ID 103237708069)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
✓ linux x86_64 in 7m47s (ID 103237708088)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  ✓ Build wheel
  ✓ Smoke test (x86_64 only)
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ linux aarch64 in 8m1s (ID 103237708095)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  ✓ Build wheel
  - Smoke test (x86_64 only)
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* windows x86_64 (ID 103237708155)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
✓ Merge release PR in 3s (ID 103237804576)
  ✓ Set up job
  ✓ Resolve release PR
  - Wait for checks to register
  - Wait for checks to pass
  - Squash-merge release PR
  ✓ Complete job

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz release: .github#5

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Publish plan: .github#6

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz PR: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/setup-python@v5, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
sdist: .github#2

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Release-plz · 34591495282
Triggered via workflow_dispatch about 13 minutes ago

JOBS
✓ Release-plz release in 19s (ID 103237584133)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz release output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ Publish plan in 4s (ID 103237677116)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Compute publish plan
  ✓ Post Checkout repository
  ✓ Complete job
✓ Release-plz PR in 26s (ID 103237677379)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz PR output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ sdist in 20s (ID 103237708043)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Build sdist
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* macos universal2 (ID 103237708069)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
✓ linux x86_64 in 7m47s (ID 103237708088)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  ✓ Build wheel
  ✓ Smoke test (x86_64 only)
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ linux aarch64 in 8m1s (ID 103237708095)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  ✓ Build wheel
  - Smoke test (x86_64 only)
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* windows x86_64 (ID 103237708155)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
✓ Merge release PR in 3s (ID 103237804576)
  ✓ Set up job
  ✓ Resolve release PR
  - Wait for checks to register
  - Wait for checks to pass
  - Squash-merge release PR
  ✓ Complete job

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz release: .github#5

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Publish plan: .github#6

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz PR: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/setup-python@v5, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
sdist: .github#2

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Release-plz · 34591495282
Triggered via workflow_dispatch about 13 minutes ago

JOBS
✓ Release-plz release in 19s (ID 103237584133)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz release output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ Publish plan in 4s (ID 103237677116)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Compute publish plan
  ✓ Post Checkout repository
  ✓ Complete job
✓ Release-plz PR in 26s (ID 103237677379)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz PR output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ sdist in 20s (ID 103237708043)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Build sdist
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* macos universal2 (ID 103237708069)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
✓ linux x86_64 in 7m47s (ID 103237708088)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  ✓ Build wheel
  ✓ Smoke test (x86_64 only)
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ linux aarch64 in 8m1s (ID 103237708095)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  ✓ Build wheel
  - Smoke test (x86_64 only)
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* windows x86_64 (ID 103237708155)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
✓ Merge release PR in 3s (ID 103237804576)
  ✓ Set up job
  ✓ Resolve release PR
  - Wait for checks to register
  - Wait for checks to pass
  - Squash-merge release PR
  ✓ Complete job

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz release: .github#5

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Publish plan: .github#6

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz PR: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/setup-python@v5, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
sdist: .github#2

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Release-plz · 34591495282
Triggered via workflow_dispatch about 13 minutes ago

JOBS
✓ Release-plz release in 19s (ID 103237584133)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz release output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ Publish plan in 4s (ID 103237677116)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Compute publish plan
  ✓ Post Checkout repository
  ✓ Complete job
✓ Release-plz PR in 26s (ID 103237677379)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz PR output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ sdist in 20s (ID 103237708043)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Build sdist
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* macos universal2 (ID 103237708069)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
✓ linux x86_64 in 7m47s (ID 103237708088)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  ✓ Build wheel
  ✓ Smoke test (x86_64 only)
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ linux aarch64 in 8m1s (ID 103237708095)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  ✓ Build wheel
  - Smoke test (x86_64 only)
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* windows x86_64 (ID 103237708155)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
✓ Merge release PR in 3s (ID 103237804576)
  ✓ Set up job
  ✓ Resolve release PR
  - Wait for checks to register
  - Wait for checks to pass
  - Squash-merge release PR
  ✓ Complete job

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz release: .github#5

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Publish plan: .github#6

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz PR: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/setup-python@v5, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
sdist: .github#2

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Release-plz · 34591495282
Triggered via workflow_dispatch about 13 minutes ago

JOBS
✓ Release-plz release in 19s (ID 103237584133)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz release output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ Publish plan in 4s (ID 103237677116)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Compute publish plan
  ✓ Post Checkout repository
  ✓ Complete job
✓ Release-plz PR in 26s (ID 103237677379)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz PR output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ sdist in 20s (ID 103237708043)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Build sdist
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* macos universal2 (ID 103237708069)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
✓ linux x86_64 in 7m47s (ID 103237708088)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  ✓ Build wheel
  ✓ Smoke test (x86_64 only)
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ linux aarch64 in 8m1s (ID 103237708095)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  ✓ Build wheel
  - Smoke test (x86_64 only)
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* windows x86_64 (ID 103237708155)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
✓ Merge release PR in 3s (ID 103237804576)
  ✓ Set up job
  ✓ Resolve release PR
  - Wait for checks to register
  - Wait for checks to pass
  - Squash-merge release PR
  ✓ Complete job

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz release: .github#5

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Publish plan: .github#6

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz PR: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/setup-python@v5, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
sdist: .github#2

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Release-plz · 34591495282
Triggered via workflow_dispatch about 13 minutes ago

JOBS
✓ Release-plz release in 19s (ID 103237584133)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz release output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ Publish plan in 4s (ID 103237677116)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Compute publish plan
  ✓ Post Checkout repository
  ✓ Complete job
✓ Release-plz PR in 26s (ID 103237677379)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz PR output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ sdist in 20s (ID 103237708043)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Build sdist
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* macos universal2 (ID 103237708069)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
✓ linux x86_64 in 7m47s (ID 103237708088)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  ✓ Build wheel
  ✓ Smoke test (x86_64 only)
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ linux aarch64 in 8m1s (ID 103237708095)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  ✓ Build wheel
  - Smoke test (x86_64 only)
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* windows x86_64 (ID 103237708155)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
✓ Merge release PR in 3s (ID 103237804576)
  ✓ Set up job
  ✓ Resolve release PR
  - Wait for checks to register
  - Wait for checks to pass
  - Squash-merge release PR
  ✓ Complete job

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz release: .github#5

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Publish plan: .github#6

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz PR: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/setup-python@v5, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
sdist: .github#2

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Release-plz · 34591495282
Triggered via workflow_dispatch about 13 minutes ago

JOBS
✓ Release-plz release in 19s (ID 103237584133)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz release output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ Publish plan in 4s (ID 103237677116)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Compute publish plan
  ✓ Post Checkout repository
  ✓ Complete job
✓ Release-plz PR in 26s (ID 103237677379)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz PR output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ sdist in 20s (ID 103237708043)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Build sdist
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* macos universal2 (ID 103237708069)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
✓ linux x86_64 in 7m47s (ID 103237708088)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  ✓ Build wheel
  ✓ Smoke test (x86_64 only)
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ linux aarch64 in 8m1s (ID 103237708095)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  ✓ Build wheel
  - Smoke test (x86_64 only)
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* windows x86_64 (ID 103237708155)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
✓ Merge release PR in 3s (ID 103237804576)
  ✓ Set up job
  ✓ Resolve release PR
  - Wait for checks to register
  - Wait for checks to pass
  - Squash-merge release PR
  ✓ Complete job

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz release: .github#5

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Publish plan: .github#6

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz PR: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/setup-python@v5, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
sdist: .github#2

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Release-plz · 34591495282
Triggered via workflow_dispatch about 13 minutes ago

JOBS
✓ Release-plz release in 19s (ID 103237584133)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz release output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ Publish plan in 4s (ID 103237677116)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Compute publish plan
  ✓ Post Checkout repository
  ✓ Complete job
✓ Release-plz PR in 26s (ID 103237677379)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz PR output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ sdist in 20s (ID 103237708043)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Build sdist
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* macos universal2 (ID 103237708069)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
✓ linux x86_64 in 7m47s (ID 103237708088)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  ✓ Build wheel
  ✓ Smoke test (x86_64 only)
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ linux aarch64 in 8m1s (ID 103237708095)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  ✓ Build wheel
  - Smoke test (x86_64 only)
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* windows x86_64 (ID 103237708155)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
✓ Merge release PR in 3s (ID 103237804576)
  ✓ Set up job
  ✓ Resolve release PR
  - Wait for checks to register
  - Wait for checks to pass
  - Squash-merge release PR
  ✓ Complete job

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz release: .github#5

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Publish plan: .github#6

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz PR: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/setup-python@v5, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
sdist: .github#2

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Release-plz · 34591495282
Triggered via workflow_dispatch about 13 minutes ago

JOBS
✓ Release-plz release in 19s (ID 103237584133)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz release output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ Publish plan in 4s (ID 103237677116)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Compute publish plan
  ✓ Post Checkout repository
  ✓ Complete job
✓ Release-plz PR in 26s (ID 103237677379)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz PR output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ sdist in 20s (ID 103237708043)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Build sdist
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* macos universal2 (ID 103237708069)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
✓ linux x86_64 in 7m47s (ID 103237708088)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  ✓ Build wheel
  ✓ Smoke test (x86_64 only)
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ linux aarch64 in 8m1s (ID 103237708095)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  ✓ Build wheel
  - Smoke test (x86_64 only)
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* windows x86_64 (ID 103237708155)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
✓ Merge release PR in 3s (ID 103237804576)
  ✓ Set up job
  ✓ Resolve release PR
  - Wait for checks to register
  - Wait for checks to pass
  - Squash-merge release PR
  ✓ Complete job

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz release: .github#5

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Publish plan: .github#6

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz PR: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/setup-python@v5, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
sdist: .github#2

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Release-plz · 34591495282
Triggered via workflow_dispatch about 13 minutes ago

JOBS
✓ Release-plz release in 19s (ID 103237584133)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz release output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ Publish plan in 4s (ID 103237677116)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Compute publish plan
  ✓ Post Checkout repository
  ✓ Complete job
✓ Release-plz PR in 26s (ID 103237677379)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz PR output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ sdist in 20s (ID 103237708043)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Build sdist
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* macos universal2 (ID 103237708069)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
✓ linux x86_64 in 7m47s (ID 103237708088)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  ✓ Build wheel
  ✓ Smoke test (x86_64 only)
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ linux aarch64 in 8m1s (ID 103237708095)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  ✓ Build wheel
  - Smoke test (x86_64 only)
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* windows x86_64 (ID 103237708155)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
✓ Merge release PR in 3s (ID 103237804576)
  ✓ Set up job
  ✓ Resolve release PR
  - Wait for checks to register
  - Wait for checks to pass
  - Squash-merge release PR
  ✓ Complete job

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz release: .github#5

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Publish plan: .github#6

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz PR: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/setup-python@v5, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
sdist: .github#2

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Release-plz · 34591495282
Triggered via workflow_dispatch about 13 minutes ago

JOBS
✓ Release-plz release in 19s (ID 103237584133)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz release output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ Publish plan in 4s (ID 103237677116)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Compute publish plan
  ✓ Post Checkout repository
  ✓ Complete job
✓ Release-plz PR in 26s (ID 103237677379)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz PR output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ sdist in 20s (ID 103237708043)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Build sdist
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* macos universal2 (ID 103237708069)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
✓ linux x86_64 in 7m47s (ID 103237708088)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  ✓ Build wheel
  ✓ Smoke test (x86_64 only)
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ linux aarch64 in 8m1s (ID 103237708095)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  ✓ Build wheel
  - Smoke test (x86_64 only)
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* windows x86_64 (ID 103237708155)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
✓ Merge release PR in 3s (ID 103237804576)
  ✓ Set up job
  ✓ Resolve release PR
  - Wait for checks to register
  - Wait for checks to pass
  - Squash-merge release PR
  ✓ Complete job

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz release: .github#5

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Publish plan: .github#6

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz PR: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/setup-python@v5, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
sdist: .github#2

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Release-plz · 34591495282
Triggered via workflow_dispatch about 13 minutes ago

JOBS
✓ Release-plz release in 19s (ID 103237584133)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz release output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ Publish plan in 4s (ID 103237677116)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Compute publish plan
  ✓ Post Checkout repository
  ✓ Complete job
✓ Release-plz PR in 26s (ID 103237677379)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz PR output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ sdist in 20s (ID 103237708043)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Build sdist
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* macos universal2 (ID 103237708069)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
✓ linux x86_64 in 7m47s (ID 103237708088)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  ✓ Build wheel
  ✓ Smoke test (x86_64 only)
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ linux aarch64 in 8m1s (ID 103237708095)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  ✓ Build wheel
  - Smoke test (x86_64 only)
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* windows x86_64 (ID 103237708155)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
✓ Merge release PR in 3s (ID 103237804576)
  ✓ Set up job
  ✓ Resolve release PR
  - Wait for checks to register
  - Wait for checks to pass
  - Squash-merge release PR
  ✓ Complete job

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz release: .github#5

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Publish plan: .github#6

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz PR: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/setup-python@v5, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
sdist: .github#2

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Release-plz · 34591495282
Triggered via workflow_dispatch about 13 minutes ago

JOBS
✓ Release-plz release in 19s (ID 103237584133)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz release output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ Publish plan in 4s (ID 103237677116)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Compute publish plan
  ✓ Post Checkout repository
  ✓ Complete job
✓ Release-plz PR in 26s (ID 103237677379)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz PR output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ sdist in 20s (ID 103237708043)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Build sdist
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* macos universal2 (ID 103237708069)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
✓ linux x86_64 in 7m47s (ID 103237708088)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  ✓ Build wheel
  ✓ Smoke test (x86_64 only)
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ linux aarch64 in 8m1s (ID 103237708095)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  ✓ Build wheel
  - Smoke test (x86_64 only)
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* windows x86_64 (ID 103237708155)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
✓ Merge release PR in 3s (ID 103237804576)
  ✓ Set up job
  ✓ Resolve release PR
  - Wait for checks to register
  - Wait for checks to pass
  - Squash-merge release PR
  ✓ Complete job

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz release: .github#5

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Publish plan: .github#6

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz PR: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/setup-python@v5, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
sdist: .github#2

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Release-plz · 34591495282
Triggered via workflow_dispatch about 13 minutes ago

JOBS
✓ Release-plz release in 19s (ID 103237584133)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz release output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ Publish plan in 4s (ID 103237677116)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Compute publish plan
  ✓ Post Checkout repository
  ✓ Complete job
✓ Release-plz PR in 26s (ID 103237677379)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz PR output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ sdist in 20s (ID 103237708043)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Build sdist
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* macos universal2 (ID 103237708069)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
✓ linux x86_64 in 7m47s (ID 103237708088)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  ✓ Build wheel
  ✓ Smoke test (x86_64 only)
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ linux aarch64 in 8m1s (ID 103237708095)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  ✓ Build wheel
  - Smoke test (x86_64 only)
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* windows x86_64 (ID 103237708155)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
✓ Merge release PR in 3s (ID 103237804576)
  ✓ Set up job
  ✓ Resolve release PR
  - Wait for checks to register
  - Wait for checks to pass
  - Squash-merge release PR
  ✓ Complete job

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz release: .github#5

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Publish plan: .github#6

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz PR: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/setup-python@v5, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
sdist: .github#2

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Release-plz · 34591495282
Triggered via workflow_dispatch about 13 minutes ago

JOBS
✓ Release-plz release in 19s (ID 103237584133)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz release output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ Publish plan in 4s (ID 103237677116)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Compute publish plan
  ✓ Post Checkout repository
  ✓ Complete job
✓ Release-plz PR in 26s (ID 103237677379)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz PR output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ sdist in 20s (ID 103237708043)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Build sdist
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* macos universal2 (ID 103237708069)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
✓ linux x86_64 in 7m47s (ID 103237708088)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  ✓ Build wheel
  ✓ Smoke test (x86_64 only)
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ linux aarch64 in 8m1s (ID 103237708095)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  ✓ Build wheel
  - Smoke test (x86_64 only)
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* windows x86_64 (ID 103237708155)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
✓ Merge release PR in 3s (ID 103237804576)
  ✓ Set up job
  ✓ Resolve release PR
  - Wait for checks to register
  - Wait for checks to pass
  - Squash-merge release PR
  ✓ Complete job

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz release: .github#5

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Publish plan: .github#6

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz PR: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/setup-python@v5, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
sdist: .github#2

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Release-plz · 34591495282
Triggered via workflow_dispatch about 13 minutes ago

JOBS
✓ Release-plz release in 19s (ID 103237584133)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz release output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ Publish plan in 4s (ID 103237677116)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Compute publish plan
  ✓ Post Checkout repository
  ✓ Complete job
✓ Release-plz PR in 26s (ID 103237677379)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz PR output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ sdist in 20s (ID 103237708043)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Build sdist
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* macos universal2 (ID 103237708069)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
✓ linux x86_64 in 7m47s (ID 103237708088)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  ✓ Build wheel
  ✓ Smoke test (x86_64 only)
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ linux aarch64 in 8m1s (ID 103237708095)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  ✓ Build wheel
  - Smoke test (x86_64 only)
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* windows x86_64 (ID 103237708155)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
✓ Merge release PR in 3s (ID 103237804576)
  ✓ Set up job
  ✓ Resolve release PR
  - Wait for checks to register
  - Wait for checks to pass
  - Squash-merge release PR
  ✓ Complete job

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz release: .github#5

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Publish plan: .github#6

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz PR: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/setup-python@v5, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
sdist: .github#2

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Release-plz · 34591495282
Triggered via workflow_dispatch about 14 minutes ago

JOBS
✓ Release-plz release in 19s (ID 103237584133)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz release output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ Publish plan in 4s (ID 103237677116)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Compute publish plan
  ✓ Post Checkout repository
  ✓ Complete job
✓ Release-plz PR in 26s (ID 103237677379)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz PR output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ sdist in 20s (ID 103237708043)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Build sdist
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* macos universal2 (ID 103237708069)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
✓ linux x86_64 in 7m47s (ID 103237708088)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  ✓ Build wheel
  ✓ Smoke test (x86_64 only)
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ linux aarch64 in 8m1s (ID 103237708095)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  ✓ Build wheel
  - Smoke test (x86_64 only)
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* windows x86_64 (ID 103237708155)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
✓ Merge release PR in 3s (ID 103237804576)
  ✓ Set up job
  ✓ Resolve release PR
  - Wait for checks to register
  - Wait for checks to pass
  - Squash-merge release PR
  ✓ Complete job

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz release: .github#5

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Publish plan: .github#6

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz PR: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/setup-python@v5, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
sdist: .github#2

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Release-plz · 34591495282
Triggered via workflow_dispatch about 14 minutes ago

JOBS
✓ Release-plz release in 19s (ID 103237584133)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz release output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ Publish plan in 4s (ID 103237677116)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Compute publish plan
  ✓ Post Checkout repository
  ✓ Complete job
✓ Release-plz PR in 26s (ID 103237677379)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz PR output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ sdist in 20s (ID 103237708043)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Build sdist
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* macos universal2 (ID 103237708069)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
✓ linux x86_64 in 7m47s (ID 103237708088)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  ✓ Build wheel
  ✓ Smoke test (x86_64 only)
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ linux aarch64 in 8m1s (ID 103237708095)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  ✓ Build wheel
  - Smoke test (x86_64 only)
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* windows x86_64 (ID 103237708155)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
✓ Merge release PR in 3s (ID 103237804576)
  ✓ Set up job
  ✓ Resolve release PR
  - Wait for checks to register
  - Wait for checks to pass
  - Squash-merge release PR
  ✓ Complete job

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz release: .github#5

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Publish plan: .github#6

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz PR: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/setup-python@v5, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
sdist: .github#2

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Release-plz · 34591495282
Triggered via workflow_dispatch about 14 minutes ago

JOBS
✓ Release-plz release in 19s (ID 103237584133)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz release output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ Publish plan in 4s (ID 103237677116)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Compute publish plan
  ✓ Post Checkout repository
  ✓ Complete job
✓ Release-plz PR in 26s (ID 103237677379)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz PR output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ sdist in 20s (ID 103237708043)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Build sdist
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* macos universal2 (ID 103237708069)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  ✓ Build wheel
  ✓ Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
✓ linux x86_64 in 7m47s (ID 103237708088)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  ✓ Build wheel
  ✓ Smoke test (x86_64 only)
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ linux aarch64 in 8m1s (ID 103237708095)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  ✓ Build wheel
  - Smoke test (x86_64 only)
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* windows x86_64 (ID 103237708155)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
✓ Merge release PR in 3s (ID 103237804576)
  ✓ Set up job
  ✓ Resolve release PR
  - Wait for checks to register
  - Wait for checks to pass
  - Squash-merge release PR
  ✓ Complete job

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz release: .github#5

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Publish plan: .github#6

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz PR: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/setup-python@v5, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
sdist: .github#2

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Release-plz · 34591495282
Triggered via workflow_dispatch about 14 minutes ago

JOBS
✓ Release-plz release in 19s (ID 103237584133)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz release output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ Publish plan in 4s (ID 103237677116)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Compute publish plan
  ✓ Post Checkout repository
  ✓ Complete job
✓ Release-plz PR in 26s (ID 103237677379)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz PR output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ sdist in 20s (ID 103237708043)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Build sdist
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* macos universal2 (ID 103237708069)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  ✓ Build wheel
  ✓ Smoke test
  ✓ Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
✓ linux x86_64 in 7m47s (ID 103237708088)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  ✓ Build wheel
  ✓ Smoke test (x86_64 only)
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ linux aarch64 in 8m1s (ID 103237708095)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  ✓ Build wheel
  - Smoke test (x86_64 only)
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* windows x86_64 (ID 103237708155)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
✓ Merge release PR in 3s (ID 103237804576)
  ✓ Set up job
  ✓ Resolve release PR
  - Wait for checks to register
  - Wait for checks to pass
  - Squash-merge release PR
  ✓ Complete job

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz release: .github#5

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Publish plan: .github#6

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz PR: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/setup-python@v5, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
sdist: .github#2

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Release-plz · 34591495282
Triggered via workflow_dispatch about 14 minutes ago

JOBS
✓ Release-plz release in 19s (ID 103237584133)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz release output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ Publish plan in 4s (ID 103237677116)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Compute publish plan
  ✓ Post Checkout repository
  ✓ Complete job
✓ Release-plz PR in 26s (ID 103237677379)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz PR output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ sdist in 20s (ID 103237708043)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Build sdist
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* macos universal2 (ID 103237708069)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  ✓ Build wheel
  ✓ Smoke test
  ✓ Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
✓ linux x86_64 in 7m47s (ID 103237708088)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  ✓ Build wheel
  ✓ Smoke test (x86_64 only)
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ linux aarch64 in 8m1s (ID 103237708095)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  ✓ Build wheel
  - Smoke test (x86_64 only)
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* windows x86_64 (ID 103237708155)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  * Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
✓ Merge release PR in 3s (ID 103237804576)
  ✓ Set up job
  ✓ Resolve release PR
  - Wait for checks to register
  - Wait for checks to pass
  - Squash-merge release PR
  ✓ Complete job

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz release: .github#5

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Publish plan: .github#6

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz PR: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/setup-python@v5, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
sdist: .github#2

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Release-plz · 34591495282
Triggered via workflow_dispatch about 14 minutes ago

JOBS
✓ Release-plz release in 19s (ID 103237584133)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz release output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ Publish plan in 4s (ID 103237677116)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Compute publish plan
  ✓ Post Checkout repository
  ✓ Complete job
✓ Release-plz PR in 26s (ID 103237677379)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz PR output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ sdist in 20s (ID 103237708043)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Build sdist
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* macos universal2 (ID 103237708069)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  ✓ Build wheel
  ✓ Smoke test
  ✓ Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
✓ linux x86_64 in 7m47s (ID 103237708088)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  ✓ Build wheel
  ✓ Smoke test (x86_64 only)
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ linux aarch64 in 8m1s (ID 103237708095)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  ✓ Build wheel
  - Smoke test (x86_64 only)
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* windows x86_64 (ID 103237708155)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  ✓ Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
✓ Merge release PR in 3s (ID 103237804576)
  ✓ Set up job
  ✓ Resolve release PR
  - Wait for checks to register
  - Wait for checks to pass
  - Squash-merge release PR
  ✓ Complete job

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz release: .github#5

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Publish plan: .github#6

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz PR: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/setup-python@v5, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
sdist: .github#2

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Release-plz · 34591495282
Triggered via workflow_dispatch about 14 minutes ago

JOBS
✓ Release-plz release in 19s (ID 103237584133)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz release output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ Publish plan in 4s (ID 103237677116)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Compute publish plan
  ✓ Post Checkout repository
  ✓ Complete job
✓ Release-plz PR in 26s (ID 103237677379)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz PR output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ sdist in 20s (ID 103237708043)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Build sdist
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* macos universal2 (ID 103237708069)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  ✓ Build wheel
  ✓ Smoke test
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
✓ linux x86_64 in 7m47s (ID 103237708088)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  ✓ Build wheel
  ✓ Smoke test (x86_64 only)
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ linux aarch64 in 8m1s (ID 103237708095)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  ✓ Build wheel
  - Smoke test (x86_64 only)
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* windows x86_64 (ID 103237708155)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  ✓ Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
✓ Merge release PR in 3s (ID 103237804576)
  ✓ Set up job
  ✓ Resolve release PR
  - Wait for checks to register
  - Wait for checks to pass
  - Squash-merge release PR
  ✓ Complete job

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz release: .github#5

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Publish plan: .github#6

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz PR: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/setup-python@v5, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
sdist: .github#2

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Release-plz · 34591495282
Triggered via workflow_dispatch about 14 minutes ago

JOBS
✓ Release-plz release in 19s (ID 103237584133)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz release output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ Publish plan in 4s (ID 103237677116)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Compute publish plan
  ✓ Post Checkout repository
  ✓ Complete job
✓ Release-plz PR in 26s (ID 103237677379)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz PR output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ sdist in 20s (ID 103237708043)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Build sdist
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ macos universal2 in 13m48s (ID 103237708069)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  ✓ Build wheel
  ✓ Smoke test
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ linux x86_64 in 7m47s (ID 103237708088)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  ✓ Build wheel
  ✓ Smoke test (x86_64 only)
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ linux aarch64 in 8m1s (ID 103237708095)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  ✓ Build wheel
  - Smoke test (x86_64 only)
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* windows x86_64 (ID 103237708155)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  ✓ Build wheel
  * Smoke test
  * Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
✓ Merge release PR in 3s (ID 103237804576)
  ✓ Set up job
  ✓ Resolve release PR
  - Wait for checks to register
  - Wait for checks to pass
  - Squash-merge release PR
  ✓ Complete job

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz release: .github#5

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Publish plan: .github#6

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz PR: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/setup-python@v5, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
sdist: .github#2

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Release-plz · 34591495282
Triggered via workflow_dispatch about 14 minutes ago

JOBS
✓ Release-plz release in 19s (ID 103237584133)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz release output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ Publish plan in 4s (ID 103237677116)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Compute publish plan
  ✓ Post Checkout repository
  ✓ Complete job
✓ Release-plz PR in 26s (ID 103237677379)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz PR output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ sdist in 20s (ID 103237708043)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Build sdist
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ macos universal2 in 13m48s (ID 103237708069)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  ✓ Build wheel
  ✓ Smoke test
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ linux x86_64 in 7m47s (ID 103237708088)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  ✓ Build wheel
  ✓ Smoke test (x86_64 only)
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ linux aarch64 in 8m1s (ID 103237708095)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  ✓ Build wheel
  - Smoke test (x86_64 only)
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* windows x86_64 (ID 103237708155)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  ✓ Build wheel
  ✓ Smoke test
  ✓ Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
✓ Merge release PR in 3s (ID 103237804576)
  ✓ Set up job
  ✓ Resolve release PR
  - Wait for checks to register
  - Wait for checks to pass
  - Squash-merge release PR
  ✓ Complete job

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz release: .github#5

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Publish plan: .github#6

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz PR: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/setup-python@v5, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
sdist: .github#2

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Release-plz · 34591495282
Triggered via workflow_dispatch about 14 minutes ago

JOBS
✓ Release-plz release in 19s (ID 103237584133)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz release output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ Publish plan in 4s (ID 103237677116)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Compute publish plan
  ✓ Post Checkout repository
  ✓ Complete job
✓ Release-plz PR in 26s (ID 103237677379)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz PR output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ sdist in 20s (ID 103237708043)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Build sdist
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ macos universal2 in 13m48s (ID 103237708069)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  ✓ Build wheel
  ✓ Smoke test
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ linux x86_64 in 7m47s (ID 103237708088)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  ✓ Build wheel
  ✓ Smoke test (x86_64 only)
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ linux aarch64 in 8m1s (ID 103237708095)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  ✓ Build wheel
  - Smoke test (x86_64 only)
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* windows x86_64 (ID 103237708155)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  ✓ Build wheel
  ✓ Smoke test
  ✓ Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
✓ Merge release PR in 3s (ID 103237804576)
  ✓ Set up job
  ✓ Resolve release PR
  - Wait for checks to register
  - Wait for checks to pass
  - Squash-merge release PR
  ✓ Complete job

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz release: .github#5

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Publish plan: .github#6

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz PR: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/setup-python@v5, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
sdist: .github#2

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Release-plz · 34591495282
Triggered via workflow_dispatch about 14 minutes ago

JOBS
✓ Release-plz release in 19s (ID 103237584133)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz release output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ Publish plan in 4s (ID 103237677116)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Compute publish plan
  ✓ Post Checkout repository
  ✓ Complete job
✓ Release-plz PR in 26s (ID 103237677379)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz PR output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ sdist in 20s (ID 103237708043)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Build sdist
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ macos universal2 in 13m48s (ID 103237708069)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  ✓ Build wheel
  ✓ Smoke test
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ linux x86_64 in 7m47s (ID 103237708088)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  ✓ Build wheel
  ✓ Smoke test (x86_64 only)
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ linux aarch64 in 8m1s (ID 103237708095)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  ✓ Build wheel
  - Smoke test (x86_64 only)
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* windows x86_64 (ID 103237708155)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  ✓ Build wheel
  ✓ Smoke test
  ✓ Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
✓ Merge release PR in 3s (ID 103237804576)
  ✓ Set up job
  ✓ Resolve release PR
  - Wait for checks to register
  - Wait for checks to pass
  - Squash-merge release PR
  ✓ Complete job

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz release: .github#5

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Publish plan: .github#6

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz PR: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/setup-python@v5, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
sdist: .github#2

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Release-plz · 34591495282
Triggered via workflow_dispatch about 14 minutes ago

JOBS
✓ Release-plz release in 19s (ID 103237584133)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz release output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ Publish plan in 4s (ID 103237677116)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Compute publish plan
  ✓ Post Checkout repository
  ✓ Complete job
✓ Release-plz PR in 26s (ID 103237677379)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz PR output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ sdist in 20s (ID 103237708043)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Build sdist
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ macos universal2 in 13m48s (ID 103237708069)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  ✓ Build wheel
  ✓ Smoke test
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ linux x86_64 in 7m47s (ID 103237708088)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  ✓ Build wheel
  ✓ Smoke test (x86_64 only)
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ linux aarch64 in 8m1s (ID 103237708095)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  ✓ Build wheel
  - Smoke test (x86_64 only)
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* windows x86_64 (ID 103237708155)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  ✓ Build wheel
  ✓ Smoke test
  ✓ Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
✓ Merge release PR in 3s (ID 103237804576)
  ✓ Set up job
  ✓ Resolve release PR
  - Wait for checks to register
  - Wait for checks to pass
  - Squash-merge release PR
  ✓ Complete job

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz release: .github#5

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Publish plan: .github#6

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz PR: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/setup-python@v5, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
sdist: .github#2

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Release-plz · 34591495282
Triggered via workflow_dispatch about 14 minutes ago

JOBS
✓ Release-plz release in 19s (ID 103237584133)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz release output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ Publish plan in 4s (ID 103237677116)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Compute publish plan
  ✓ Post Checkout repository
  ✓ Complete job
✓ Release-plz PR in 26s (ID 103237677379)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz PR output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ sdist in 20s (ID 103237708043)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Build sdist
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ macos universal2 in 13m48s (ID 103237708069)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  ✓ Build wheel
  ✓ Smoke test
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ linux x86_64 in 7m47s (ID 103237708088)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  ✓ Build wheel
  ✓ Smoke test (x86_64 only)
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ linux aarch64 in 8m1s (ID 103237708095)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  ✓ Build wheel
  - Smoke test (x86_64 only)
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* windows x86_64 (ID 103237708155)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  ✓ Build wheel
  ✓ Smoke test
  ✓ Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
✓ Merge release PR in 3s (ID 103237804576)
  ✓ Set up job
  ✓ Resolve release PR
  - Wait for checks to register
  - Wait for checks to pass
  - Squash-merge release PR
  ✓ Complete job

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz release: .github#5

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Publish plan: .github#6

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz PR: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/setup-python@v5, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
sdist: .github#2

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Release-plz · 34591495282
Triggered via workflow_dispatch about 14 minutes ago

JOBS
✓ Release-plz release in 19s (ID 103237584133)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz release output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ Publish plan in 4s (ID 103237677116)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Compute publish plan
  ✓ Post Checkout repository
  ✓ Complete job
✓ Release-plz PR in 26s (ID 103237677379)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz PR output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ sdist in 20s (ID 103237708043)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Build sdist
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ macos universal2 in 13m48s (ID 103237708069)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  ✓ Build wheel
  ✓ Smoke test
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ linux x86_64 in 7m47s (ID 103237708088)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  ✓ Build wheel
  ✓ Smoke test (x86_64 only)
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ linux aarch64 in 8m1s (ID 103237708095)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  ✓ Build wheel
  - Smoke test (x86_64 only)
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* windows x86_64 (ID 103237708155)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  ✓ Build wheel
  ✓ Smoke test
  ✓ Run actions/upload-artifact@v4
  * Post Run Swatinem/rust-cache@v2
  * Post Run actions/setup-python@v5
  * Post Run actions/checkout@v4
✓ Merge release PR in 3s (ID 103237804576)
  ✓ Set up job
  ✓ Resolve release PR
  - Wait for checks to register
  - Wait for checks to pass
  - Squash-merge release PR
  ✓ Complete job

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz release: .github#5

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Publish plan: .github#6

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz PR: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/setup-python@v5, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
sdist: .github#2

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Release-plz · 34591495282
Triggered via workflow_dispatch about 14 minutes ago

JOBS
✓ Release-plz release in 19s (ID 103237584133)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz release output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ Publish plan in 4s (ID 103237677116)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Compute publish plan
  ✓ Post Checkout repository
  ✓ Complete job
✓ Release-plz PR in 26s (ID 103237677379)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz PR output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ sdist in 20s (ID 103237708043)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Build sdist
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ macos universal2 in 13m48s (ID 103237708069)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  ✓ Build wheel
  ✓ Smoke test
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ linux x86_64 in 7m47s (ID 103237708088)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  ✓ Build wheel
  ✓ Smoke test (x86_64 only)
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ linux aarch64 in 8m1s (ID 103237708095)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  ✓ Build wheel
  - Smoke test (x86_64 only)
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* windows x86_64 (ID 103237708155)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  ✓ Build wheel
  ✓ Smoke test
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ Merge release PR in 3s (ID 103237804576)
  ✓ Set up job
  ✓ Resolve release PR
  - Wait for checks to register
  - Wait for checks to pass
  - Squash-merge release PR
  ✓ Complete job

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz release: .github#5

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Publish plan: .github#6

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz PR: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/setup-python@v5, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
sdist: .github#2

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Release-plz · 34591495282
Triggered via workflow_dispatch about 15 minutes ago

JOBS
✓ Release-plz release in 19s (ID 103237584133)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz release output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ Publish plan in 4s (ID 103237677116)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Compute publish plan
  ✓ Post Checkout repository
  ✓ Complete job
✓ Release-plz PR in 26s (ID 103237677379)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz PR output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ sdist in 20s (ID 103237708043)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Build sdist
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ macos universal2 in 13m48s (ID 103237708069)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  ✓ Build wheel
  ✓ Smoke test
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ linux x86_64 in 7m47s (ID 103237708088)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  ✓ Build wheel
  ✓ Smoke test (x86_64 only)
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ linux aarch64 in 8m1s (ID 103237708095)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  ✓ Build wheel
  - Smoke test (x86_64 only)
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ windows x86_64 in 14m21s (ID 103237708155)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  ✓ Build wheel
  ✓ Smoke test
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ Merge release PR in 3s (ID 103237804576)
  ✓ Set up job
  ✓ Resolve release PR
  - Wait for checks to register
  - Wait for checks to pass
  - Squash-merge release PR
  ✓ Complete job
* twine check (ID 103241319166)

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz release: .github#5

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Publish plan: .github#6

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz PR: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/setup-python@v5, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
sdist: .github#2

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Release-plz · 34591495282
Triggered via workflow_dispatch about 15 minutes ago

JOBS
✓ Release-plz release in 19s (ID 103237584133)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz release output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ Publish plan in 4s (ID 103237677116)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Compute publish plan
  ✓ Post Checkout repository
  ✓ Complete job
✓ Release-plz PR in 26s (ID 103237677379)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz PR output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ sdist in 20s (ID 103237708043)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Build sdist
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ macos universal2 in 13m48s (ID 103237708069)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  ✓ Build wheel
  ✓ Smoke test
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ linux x86_64 in 7m47s (ID 103237708088)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  ✓ Build wheel
  ✓ Smoke test (x86_64 only)
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ linux aarch64 in 8m1s (ID 103237708095)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  ✓ Build wheel
  - Smoke test (x86_64 only)
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ windows x86_64 in 14m21s (ID 103237708155)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  ✓ Build wheel
  ✓ Smoke test
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ Merge release PR in 3s (ID 103237804576)
  ✓ Set up job
  ✓ Resolve release PR
  - Wait for checks to register
  - Wait for checks to pass
  - Squash-merge release PR
  ✓ Complete job
* twine check (ID 103241319166)
  ✓ Set up job
  * Run actions/download-artifact@v4
  * Run actions/setup-python@v5
  * Run pip install --quiet twine
  * Run ls -la dist
  * Run twine check dist/*

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz release: .github#5

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Publish plan: .github#6

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz PR: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/setup-python@v5, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
sdist: .github#2

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Release-plz · 34591495282
Triggered via workflow_dispatch about 15 minutes ago

JOBS
✓ Release-plz release in 19s (ID 103237584133)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz release output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ Publish plan in 4s (ID 103237677116)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Compute publish plan
  ✓ Post Checkout repository
  ✓ Complete job
✓ Release-plz PR in 26s (ID 103237677379)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz PR output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ sdist in 20s (ID 103237708043)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Build sdist
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ macos universal2 in 13m48s (ID 103237708069)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  ✓ Build wheel
  ✓ Smoke test
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ linux x86_64 in 7m47s (ID 103237708088)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  ✓ Build wheel
  ✓ Smoke test (x86_64 only)
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ linux aarch64 in 8m1s (ID 103237708095)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  ✓ Build wheel
  - Smoke test (x86_64 only)
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ windows x86_64 in 14m21s (ID 103237708155)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  ✓ Build wheel
  ✓ Smoke test
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ Merge release PR in 3s (ID 103237804576)
  ✓ Set up job
  ✓ Resolve release PR
  - Wait for checks to register
  - Wait for checks to pass
  - Squash-merge release PR
  ✓ Complete job
* twine check (ID 103241319166)
  ✓ Set up job
  ✓ Run actions/download-artifact@v4
  ✓ Run actions/setup-python@v5
  * Run pip install --quiet twine
  * Run ls -la dist
  * Run twine check dist/*
  * Post Run actions/setup-python@v5

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz release: .github#5

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Publish plan: .github#6

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz PR: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/setup-python@v5, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
sdist: .github#2

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Release-plz · 34591495282
Triggered via workflow_dispatch about 15 minutes ago

JOBS
✓ Release-plz release in 19s (ID 103237584133)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz release output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ Publish plan in 4s (ID 103237677116)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Compute publish plan
  ✓ Post Checkout repository
  ✓ Complete job
✓ Release-plz PR in 26s (ID 103237677379)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz PR output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ sdist in 20s (ID 103237708043)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Build sdist
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ macos universal2 in 13m48s (ID 103237708069)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  ✓ Build wheel
  ✓ Smoke test
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ linux x86_64 in 7m47s (ID 103237708088)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  ✓ Build wheel
  ✓ Smoke test (x86_64 only)
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ linux aarch64 in 8m1s (ID 103237708095)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  ✓ Build wheel
  - Smoke test (x86_64 only)
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ windows x86_64 in 14m21s (ID 103237708155)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  ✓ Build wheel
  ✓ Smoke test
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ Merge release PR in 3s (ID 103237804576)
  ✓ Set up job
  ✓ Resolve release PR
  - Wait for checks to register
  - Wait for checks to pass
  - Squash-merge release PR
  ✓ Complete job
* twine check (ID 103241319166)
  ✓ Set up job
  ✓ Run actions/download-artifact@v4
  ✓ Run actions/setup-python@v5
  ✓ Run pip install --quiet twine
  ✓ Run ls -la dist
  * Run twine check dist/*
  * Post Run actions/setup-python@v5

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz release: .github#5

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Publish plan: .github#6

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz PR: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/setup-python@v5, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
sdist: .github#2

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Release-plz · 34591495282
Triggered via workflow_dispatch about 15 minutes ago

JOBS
✓ Release-plz release in 19s (ID 103237584133)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz release output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ Publish plan in 4s (ID 103237677116)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Compute publish plan
  ✓ Post Checkout repository
  ✓ Complete job
✓ Release-plz PR in 26s (ID 103237677379)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz PR output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ sdist in 20s (ID 103237708043)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Build sdist
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ macos universal2 in 13m48s (ID 103237708069)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  ✓ Build wheel
  ✓ Smoke test
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ linux x86_64 in 7m47s (ID 103237708088)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  ✓ Build wheel
  ✓ Smoke test (x86_64 only)
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ linux aarch64 in 8m1s (ID 103237708095)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  ✓ Build wheel
  - Smoke test (x86_64 only)
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ windows x86_64 in 14m21s (ID 103237708155)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  ✓ Build wheel
  ✓ Smoke test
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ Merge release PR in 3s (ID 103237804576)
  ✓ Set up job
  ✓ Resolve release PR
  - Wait for checks to register
  - Wait for checks to pass
  - Squash-merge release PR
  ✓ Complete job
✓ twine check in 14s (ID 103241319166)
  ✓ Set up job
  ✓ Run actions/download-artifact@v4
  ✓ Run actions/setup-python@v5
  ✓ Run pip install --quiet twine
  ✓ Run ls -la dist
  ✓ Run twine check dist/*
  ✓ Post Run actions/setup-python@v5
  ✓ Complete job
* publish to PyPI (ID 103241386646)

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz release: .github#5

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Publish plan: .github#6

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz PR: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/setup-python@v5, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
sdist: .github#2

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Release-plz · 34591495282
Triggered via workflow_dispatch about 15 minutes ago

JOBS
✓ Release-plz release in 19s (ID 103237584133)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz release output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ Publish plan in 4s (ID 103237677116)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Compute publish plan
  ✓ Post Checkout repository
  ✓ Complete job
✓ Release-plz PR in 26s (ID 103237677379)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz PR output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ sdist in 20s (ID 103237708043)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Build sdist
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ macos universal2 in 13m48s (ID 103237708069)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  ✓ Build wheel
  ✓ Smoke test
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ linux x86_64 in 7m47s (ID 103237708088)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  ✓ Build wheel
  ✓ Smoke test (x86_64 only)
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ linux aarch64 in 8m1s (ID 103237708095)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  ✓ Build wheel
  - Smoke test (x86_64 only)
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ windows x86_64 in 14m21s (ID 103237708155)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  ✓ Build wheel
  ✓ Smoke test
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ Merge release PR in 3s (ID 103237804576)
  ✓ Set up job
  ✓ Resolve release PR
  - Wait for checks to register
  - Wait for checks to pass
  - Squash-merge release PR
  ✓ Complete job
✓ twine check in 14s (ID 103241319166)
  ✓ Set up job
  ✓ Run actions/download-artifact@v4
  ✓ Run actions/setup-python@v5
  ✓ Run pip install --quiet twine
  ✓ Run ls -la dist
  ✓ Run twine check dist/*
  ✓ Post Run actions/setup-python@v5
  ✓ Complete job
* publish to PyPI (ID 103241386646)
  * Set up job

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz release: .github#5

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Publish plan: .github#6

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz PR: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/setup-python@v5, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
sdist: .github#2

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Release-plz · 34591495282
Triggered via workflow_dispatch about 15 minutes ago

JOBS
✓ Release-plz release in 19s (ID 103237584133)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz release output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ Publish plan in 4s (ID 103237677116)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Compute publish plan
  ✓ Post Checkout repository
  ✓ Complete job
✓ Release-plz PR in 26s (ID 103237677379)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz PR output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ sdist in 20s (ID 103237708043)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Build sdist
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ macos universal2 in 13m48s (ID 103237708069)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  ✓ Build wheel
  ✓ Smoke test
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ linux x86_64 in 7m47s (ID 103237708088)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  ✓ Build wheel
  ✓ Smoke test (x86_64 only)
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ linux aarch64 in 8m1s (ID 103237708095)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  ✓ Build wheel
  - Smoke test (x86_64 only)
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ windows x86_64 in 14m21s (ID 103237708155)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  ✓ Build wheel
  ✓ Smoke test
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ Merge release PR in 3s (ID 103237804576)
  ✓ Set up job
  ✓ Resolve release PR
  - Wait for checks to register
  - Wait for checks to pass
  - Squash-merge release PR
  ✓ Complete job
✓ twine check in 14s (ID 103241319166)
  ✓ Set up job
  ✓ Run actions/download-artifact@v4
  ✓ Run actions/setup-python@v5
  ✓ Run pip install --quiet twine
  ✓ Run ls -la dist
  ✓ Run twine check dist/*
  ✓ Post Run actions/setup-python@v5
  ✓ Complete job
* publish to PyPI (ID 103241386646)
  ✓ Set up job
  * Checkout repository
  * Run actions/download-artifact@v4
  * Guard PyPI publish
  * Publish to PyPI
  * Post Checkout repository

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz release: .github#5

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Publish plan: .github#6

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz PR: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/setup-python@v5, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
sdist: .github#2

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Release-plz · 34591495282
Triggered via workflow_dispatch about 15 minutes ago

JOBS
✓ Release-plz release in 19s (ID 103237584133)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz release output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ Publish plan in 4s (ID 103237677116)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Compute publish plan
  ✓ Post Checkout repository
  ✓ Complete job
✓ Release-plz PR in 26s (ID 103237677379)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz PR output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ sdist in 20s (ID 103237708043)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Build sdist
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ macos universal2 in 13m48s (ID 103237708069)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  ✓ Build wheel
  ✓ Smoke test
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ linux x86_64 in 7m47s (ID 103237708088)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  ✓ Build wheel
  ✓ Smoke test (x86_64 only)
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ linux aarch64 in 8m1s (ID 103237708095)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  ✓ Build wheel
  - Smoke test (x86_64 only)
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ windows x86_64 in 14m21s (ID 103237708155)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  ✓ Build wheel
  ✓ Smoke test
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ Merge release PR in 3s (ID 103237804576)
  ✓ Set up job
  ✓ Resolve release PR
  - Wait for checks to register
  - Wait for checks to pass
  - Squash-merge release PR
  ✓ Complete job
✓ twine check in 14s (ID 103241319166)
  ✓ Set up job
  ✓ Run actions/download-artifact@v4
  ✓ Run actions/setup-python@v5
  ✓ Run pip install --quiet twine
  ✓ Run ls -la dist
  ✓ Run twine check dist/*
  ✓ Post Run actions/setup-python@v5
  ✓ Complete job
* publish to PyPI (ID 103241386646)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run actions/download-artifact@v4
  ✓ Guard PyPI publish
  * Publish to PyPI
  * Post Publish to PyPI
  * Post Checkout repository

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz release: .github#5

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Publish plan: .github#6

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz PR: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/setup-python@v5, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
sdist: .github#2

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Release-plz · 34591495282
Triggered via workflow_dispatch about 15 minutes ago

JOBS
✓ Release-plz release in 19s (ID 103237584133)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz release output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ Publish plan in 4s (ID 103237677116)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Compute publish plan
  ✓ Post Checkout repository
  ✓ Complete job
✓ Release-plz PR in 26s (ID 103237677379)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz PR output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ sdist in 20s (ID 103237708043)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Build sdist
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ macos universal2 in 13m48s (ID 103237708069)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  ✓ Build wheel
  ✓ Smoke test
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ linux x86_64 in 7m47s (ID 103237708088)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  ✓ Build wheel
  ✓ Smoke test (x86_64 only)
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ linux aarch64 in 8m1s (ID 103237708095)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  ✓ Build wheel
  - Smoke test (x86_64 only)
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ windows x86_64 in 14m21s (ID 103237708155)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  ✓ Build wheel
  ✓ Smoke test
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ Merge release PR in 3s (ID 103237804576)
  ✓ Set up job
  ✓ Resolve release PR
  - Wait for checks to register
  - Wait for checks to pass
  - Squash-merge release PR
  ✓ Complete job
✓ twine check in 14s (ID 103241319166)
  ✓ Set up job
  ✓ Run actions/download-artifact@v4
  ✓ Run actions/setup-python@v5
  ✓ Run pip install --quiet twine
  ✓ Run ls -la dist
  ✓ Run twine check dist/*
  ✓ Post Run actions/setup-python@v5
  ✓ Complete job
* publish to PyPI (ID 103241386646)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run actions/download-artifact@v4
  ✓ Guard PyPI publish
  * Publish to PyPI
  * Post Publish to PyPI
  * Post Checkout repository

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz release: .github#5

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Publish plan: .github#6

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz PR: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/setup-python@v5, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
sdist: .github#2

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Release-plz · 34591495282
Triggered via workflow_dispatch about 15 minutes ago

JOBS
✓ Release-plz release in 19s (ID 103237584133)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz release output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ Publish plan in 4s (ID 103237677116)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Compute publish plan
  ✓ Post Checkout repository
  ✓ Complete job
✓ Release-plz PR in 26s (ID 103237677379)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz PR output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ sdist in 20s (ID 103237708043)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Build sdist
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ macos universal2 in 13m48s (ID 103237708069)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  ✓ Build wheel
  ✓ Smoke test
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ linux x86_64 in 7m47s (ID 103237708088)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  ✓ Build wheel
  ✓ Smoke test (x86_64 only)
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ linux aarch64 in 8m1s (ID 103237708095)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  ✓ Build wheel
  - Smoke test (x86_64 only)
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ windows x86_64 in 14m21s (ID 103237708155)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  ✓ Build wheel
  ✓ Smoke test
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ Merge release PR in 3s (ID 103237804576)
  ✓ Set up job
  ✓ Resolve release PR
  - Wait for checks to register
  - Wait for checks to pass
  - Squash-merge release PR
  ✓ Complete job
✓ twine check in 14s (ID 103241319166)
  ✓ Set up job
  ✓ Run actions/download-artifact@v4
  ✓ Run actions/setup-python@v5
  ✓ Run pip install --quiet twine
  ✓ Run ls -la dist
  ✓ Run twine check dist/*
  ✓ Post Run actions/setup-python@v5
  ✓ Complete job
* publish to PyPI (ID 103241386646)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run actions/download-artifact@v4
  ✓ Guard PyPI publish
  * Publish to PyPI
  * Post Publish to PyPI
  * Post Checkout repository

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz release: .github#5

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Publish plan: .github#6

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz PR: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/setup-python@v5, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
sdist: .github#2

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Release-plz · 34591495282
Triggered via workflow_dispatch about 15 minutes ago

JOBS
✓ Release-plz release in 19s (ID 103237584133)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz release output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ Publish plan in 4s (ID 103237677116)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Compute publish plan
  ✓ Post Checkout repository
  ✓ Complete job
✓ Release-plz PR in 26s (ID 103237677379)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz PR output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ sdist in 20s (ID 103237708043)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Build sdist
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ macos universal2 in 13m48s (ID 103237708069)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  ✓ Build wheel
  ✓ Smoke test
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ linux x86_64 in 7m47s (ID 103237708088)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  ✓ Build wheel
  ✓ Smoke test (x86_64 only)
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ linux aarch64 in 8m1s (ID 103237708095)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  ✓ Build wheel
  - Smoke test (x86_64 only)
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ windows x86_64 in 14m21s (ID 103237708155)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  ✓ Build wheel
  ✓ Smoke test
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ Merge release PR in 3s (ID 103237804576)
  ✓ Set up job
  ✓ Resolve release PR
  - Wait for checks to register
  - Wait for checks to pass
  - Squash-merge release PR
  ✓ Complete job
✓ twine check in 14s (ID 103241319166)
  ✓ Set up job
  ✓ Run actions/download-artifact@v4
  ✓ Run actions/setup-python@v5
  ✓ Run pip install --quiet twine
  ✓ Run ls -la dist
  ✓ Run twine check dist/*
  ✓ Post Run actions/setup-python@v5
  ✓ Complete job
* publish to PyPI (ID 103241386646)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run actions/download-artifact@v4
  ✓ Guard PyPI publish
  * Publish to PyPI
  * Post Publish to PyPI
  * Post Checkout repository

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz release: .github#5

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Publish plan: .github#6

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz PR: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/setup-python@v5, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
sdist: .github#2

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Release-plz · 34591495282
Triggered via workflow_dispatch about 15 minutes ago

JOBS
✓ Release-plz release in 19s (ID 103237584133)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz release output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ Publish plan in 4s (ID 103237677116)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Compute publish plan
  ✓ Post Checkout repository
  ✓ Complete job
✓ Release-plz PR in 26s (ID 103237677379)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz PR output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ sdist in 20s (ID 103237708043)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Build sdist
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ macos universal2 in 13m48s (ID 103237708069)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  ✓ Build wheel
  ✓ Smoke test
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ linux x86_64 in 7m47s (ID 103237708088)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  ✓ Build wheel
  ✓ Smoke test (x86_64 only)
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ linux aarch64 in 8m1s (ID 103237708095)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  ✓ Build wheel
  - Smoke test (x86_64 only)
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ windows x86_64 in 14m21s (ID 103237708155)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  ✓ Build wheel
  ✓ Smoke test
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ Merge release PR in 3s (ID 103237804576)
  ✓ Set up job
  ✓ Resolve release PR
  - Wait for checks to register
  - Wait for checks to pass
  - Squash-merge release PR
  ✓ Complete job
✓ twine check in 14s (ID 103241319166)
  ✓ Set up job
  ✓ Run actions/download-artifact@v4
  ✓ Run actions/setup-python@v5
  ✓ Run pip install --quiet twine
  ✓ Run ls -la dist
  ✓ Run twine check dist/*
  ✓ Post Run actions/setup-python@v5
  ✓ Complete job
* publish to PyPI (ID 103241386646)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run actions/download-artifact@v4
  ✓ Guard PyPI publish
  * Publish to PyPI
  * Post Publish to PyPI
  * Post Checkout repository

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz release: .github#5

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Publish plan: .github#6

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz PR: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/setup-python@v5, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
sdist: .github#2

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Release-plz · 34591495282
Triggered via workflow_dispatch about 15 minutes ago

JOBS
✓ Release-plz release in 19s (ID 103237584133)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz release output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ Publish plan in 4s (ID 103237677116)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Compute publish plan
  ✓ Post Checkout repository
  ✓ Complete job
✓ Release-plz PR in 26s (ID 103237677379)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz PR output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ sdist in 20s (ID 103237708043)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Build sdist
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ macos universal2 in 13m48s (ID 103237708069)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  ✓ Build wheel
  ✓ Smoke test
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ linux x86_64 in 7m47s (ID 103237708088)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  ✓ Build wheel
  ✓ Smoke test (x86_64 only)
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ linux aarch64 in 8m1s (ID 103237708095)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  ✓ Build wheel
  - Smoke test (x86_64 only)
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ windows x86_64 in 14m21s (ID 103237708155)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  ✓ Build wheel
  ✓ Smoke test
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ Merge release PR in 3s (ID 103237804576)
  ✓ Set up job
  ✓ Resolve release PR
  - Wait for checks to register
  - Wait for checks to pass
  - Squash-merge release PR
  ✓ Complete job
✓ twine check in 14s (ID 103241319166)
  ✓ Set up job
  ✓ Run actions/download-artifact@v4
  ✓ Run actions/setup-python@v5
  ✓ Run pip install --quiet twine
  ✓ Run ls -la dist
  ✓ Run twine check dist/*
  ✓ Post Run actions/setup-python@v5
  ✓ Complete job
* publish to PyPI (ID 103241386646)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run actions/download-artifact@v4
  ✓ Guard PyPI publish
  * Publish to PyPI
  * Post Publish to PyPI
  * Post Checkout repository

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz release: .github#5

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Publish plan: .github#6

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz PR: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/setup-python@v5, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
sdist: .github#2

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Release-plz · 34591495282
Triggered via workflow_dispatch about 15 minutes ago

JOBS
✓ Release-plz release in 19s (ID 103237584133)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz release output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ Publish plan in 4s (ID 103237677116)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Compute publish plan
  ✓ Post Checkout repository
  ✓ Complete job
✓ Release-plz PR in 26s (ID 103237677379)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz PR output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ sdist in 20s (ID 103237708043)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Build sdist
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ macos universal2 in 13m48s (ID 103237708069)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  ✓ Build wheel
  ✓ Smoke test
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ linux x86_64 in 7m47s (ID 103237708088)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  ✓ Build wheel
  ✓ Smoke test (x86_64 only)
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ linux aarch64 in 8m1s (ID 103237708095)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  ✓ Build wheel
  - Smoke test (x86_64 only)
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ windows x86_64 in 14m21s (ID 103237708155)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  ✓ Build wheel
  ✓ Smoke test
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ Merge release PR in 3s (ID 103237804576)
  ✓ Set up job
  ✓ Resolve release PR
  - Wait for checks to register
  - Wait for checks to pass
  - Squash-merge release PR
  ✓ Complete job
✓ twine check in 14s (ID 103241319166)
  ✓ Set up job
  ✓ Run actions/download-artifact@v4
  ✓ Run actions/setup-python@v5
  ✓ Run pip install --quiet twine
  ✓ Run ls -la dist
  ✓ Run twine check dist/*
  ✓ Post Run actions/setup-python@v5
  ✓ Complete job
* publish to PyPI (ID 103241386646)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run actions/download-artifact@v4
  ✓ Guard PyPI publish
  * Publish to PyPI
  * Post Publish to PyPI
  * Post Checkout repository

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz release: .github#5

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Publish plan: .github#6

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz PR: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/setup-python@v5, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
sdist: .github#2

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Release-plz · 34591495282
Triggered via workflow_dispatch about 15 minutes ago

JOBS
✓ Release-plz release in 19s (ID 103237584133)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz release output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ Publish plan in 4s (ID 103237677116)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Compute publish plan
  ✓ Post Checkout repository
  ✓ Complete job
✓ Release-plz PR in 26s (ID 103237677379)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz PR output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ sdist in 20s (ID 103237708043)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Build sdist
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ macos universal2 in 13m48s (ID 103237708069)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  ✓ Build wheel
  ✓ Smoke test
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ linux x86_64 in 7m47s (ID 103237708088)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  ✓ Build wheel
  ✓ Smoke test (x86_64 only)
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ linux aarch64 in 8m1s (ID 103237708095)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  ✓ Build wheel
  - Smoke test (x86_64 only)
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ windows x86_64 in 14m21s (ID 103237708155)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  ✓ Build wheel
  ✓ Smoke test
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ Merge release PR in 3s (ID 103237804576)
  ✓ Set up job
  ✓ Resolve release PR
  - Wait for checks to register
  - Wait for checks to pass
  - Squash-merge release PR
  ✓ Complete job
✓ twine check in 14s (ID 103241319166)
  ✓ Set up job
  ✓ Run actions/download-artifact@v4
  ✓ Run actions/setup-python@v5
  ✓ Run pip install --quiet twine
  ✓ Run ls -la dist
  ✓ Run twine check dist/*
  ✓ Post Run actions/setup-python@v5
  ✓ Complete job
* publish to PyPI (ID 103241386646)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run actions/download-artifact@v4
  ✓ Guard PyPI publish
  * Publish to PyPI
  * Post Publish to PyPI
  * Post Checkout repository

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz release: .github#5

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Publish plan: .github#6

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz PR: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/setup-python@v5, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
sdist: .github#2

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Release-plz · 34591495282
Triggered via workflow_dispatch about 15 minutes ago

JOBS
✓ Release-plz release in 19s (ID 103237584133)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz release output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ Publish plan in 4s (ID 103237677116)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Compute publish plan
  ✓ Post Checkout repository
  ✓ Complete job
✓ Release-plz PR in 26s (ID 103237677379)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz PR output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ sdist in 20s (ID 103237708043)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Build sdist
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ macos universal2 in 13m48s (ID 103237708069)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  ✓ Build wheel
  ✓ Smoke test
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ linux x86_64 in 7m47s (ID 103237708088)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  ✓ Build wheel
  ✓ Smoke test (x86_64 only)
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ linux aarch64 in 8m1s (ID 103237708095)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  ✓ Build wheel
  - Smoke test (x86_64 only)
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ windows x86_64 in 14m21s (ID 103237708155)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  ✓ Build wheel
  ✓ Smoke test
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ Merge release PR in 3s (ID 103237804576)
  ✓ Set up job
  ✓ Resolve release PR
  - Wait for checks to register
  - Wait for checks to pass
  - Squash-merge release PR
  ✓ Complete job
✓ twine check in 14s (ID 103241319166)
  ✓ Set up job
  ✓ Run actions/download-artifact@v4
  ✓ Run actions/setup-python@v5
  ✓ Run pip install --quiet twine
  ✓ Run ls -la dist
  ✓ Run twine check dist/*
  ✓ Post Run actions/setup-python@v5
  ✓ Complete job
* publish to PyPI (ID 103241386646)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run actions/download-artifact@v4
  ✓ Guard PyPI publish
  ✓ Publish to PyPI
  ✓ Post Publish to PyPI
  ✓ Post Checkout repository
  ✓ Complete job

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz release: .github#5

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Publish plan: .github#6

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz PR: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/setup-python@v5, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
sdist: .github#2

✓ master Release-plz · 34591495282
Triggered via workflow_dispatch about 16 minutes ago

JOBS
✓ Release-plz release in 19s (ID 103237584133)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz release output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ Publish plan in 4s (ID 103237677116)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Compute publish plan
  ✓ Post Checkout repository
  ✓ Complete job
✓ Release-plz PR in 26s (ID 103237677379)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz PR output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ sdist in 20s (ID 103237708043)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Build sdist
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ macos universal2 in 13m48s (ID 103237708069)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  ✓ Build wheel
  ✓ Smoke test
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ linux x86_64 in 7m47s (ID 103237708088)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  ✓ Build wheel
  ✓ Smoke test (x86_64 only)
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ linux aarch64 in 8m1s (ID 103237708095)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  ✓ Build wheel
  - Smoke test (x86_64 only)
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ windows x86_64 in 14m21s (ID 103237708155)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Run actions/setup-python@v5
  ✓ Run Swatinem/rust-cache@v2
  ✓ Build wheel
  ✓ Smoke test
  ✓ Run actions/upload-artifact@v4
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Run actions/setup-python@v5
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ Merge release PR in 3s (ID 103237804576)
  ✓ Set up job
  ✓ Resolve release PR
  - Wait for checks to register
  - Wait for checks to pass
  - Squash-merge release PR
  ✓ Complete job
✓ twine check in 14s (ID 103241319166)
  ✓ Set up job
  ✓ Run actions/download-artifact@v4
  ✓ Run actions/setup-python@v5
  ✓ Run pip install --quiet twine
  ✓ Run ls -la dist
  ✓ Run twine check dist/*
  ✓ Post Run actions/setup-python@v5
  ✓ Complete job
✓ publish to PyPI in 39s (ID 103241386646)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run actions/download-artifact@v4
  ✓ Guard PyPI publish
  ✓ Publish to PyPI
  ✓ Post Publish to PyPI
  ✓ Post Checkout repository
  ✓ Complete job

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz release: .github#5

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Publish plan: .github#6

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz PR: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/setup-python@v5, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
sdist: .github#2


