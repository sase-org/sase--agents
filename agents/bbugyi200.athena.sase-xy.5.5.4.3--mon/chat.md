# Chat History - ace-run (sase-xy.5.5.4.3--mon)

- **TIMESTAMP:** 2026-09-08 00:01:26 EDT
- **MODEL:** codex/gpt-5.5
- **AGENT:** sase-xy.5.5.4.3--mon

## Prompt

sase monitor start --command 'set -euo pipefail\nprintf "[release-wait] watching sase-core Release-plz run 34184827262\\n"\ngh run watch 34184827262 --repo sase-org/sase-core --exit-status\nprintf "[release-wait] release PR workflow completed; waiting for PyPI 0.32.42\\n"\ndeadline=$((SECONDS + 5400))\nwhile (( SECONDS < deadline )); do\n  if git ls-remote --exit-code https://github.com/sase-org/sase-core.git refs/tags/v0.32.42 >/tmp/sase-core-v0.32.42-tag 2>/tmp/sase-core-v0.32.42-tag.err; then\n    cat /tmp/sase-core-v0.32.42-tag\n    if python3 - <<"PY"\nimport json, urllib.error, urllib.request\nurl = "https://pypi.org/pypi/sase-core-rs/0.32.42/json"\ntry:\n    with urllib.request.urlopen(urllib.request.Request(url, headers={"Accept": "application/json"}), timeout=20) as response:\n        payload = json.load(response)\nexcept urllib.error.HTTPError as error:\n    if error.code == 404:\n        raise SystemExit(1)\n    raise\nprint(f"[release-wait] PyPI published sase-core-rs {payload[info][version]}")\nPY\n    then\n      exit 0\n    fi\n    printf "[release-wait] tag exists but PyPI is not published yet\\n"\n  else\n    printf "[release-wait] tag v0.32.42 not visible yet\\n"\n  fi\n  gh run list --repo sase-org/sase-core --workflow Release-plz --limit 3 --json databaseId,status,conclusion,displayTitle,headBranch,createdAt,updatedAt --jq ".[] | [.databaseId,.status,(.conclusion // \\"\\"),.headBranch,.displayTitle,.updatedAt] | @tsv" || true\n  sleep 60\ndone\nprintf "[release-wait] timed out waiting for sase-core-rs 0.32.42 on PyPI\\n" >&2\nexit 1' --reason 'Wait for sase-core v0.32.42 release and PyPI publication before ratcheting sase clean-install floor for bead sase-xy.5.5.4.3'

## Response

[release-wait] watching sase-core Release-plz run 34184827262
Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Release-plz · 34184827262
Triggered via push about 9 minutes ago

JOBS
✓ Release-plz release in 26s (ID 101930947729)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz release output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ Publish plan in 4s (ID 101931026408)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Compute publish plan
  ✓ Post Checkout repository
  ✓ Complete job
✓ Release-plz PR in 4m25s (ID 101931026548)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz PR output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
- linux ${{ matrix.target }} (ID 101931047370)
- windows x86_64 (ID 101931047401)
- sdist (ID 101931047534)
- macos universal2 (ID 101931047835)
- twine check in 0s (ID 101931047843)
- publish to PyPI in 0s (ID 101931047975)
* Merge release PR (ID 101931764196)
  ✓ Set up job
  ✓ Resolve release PR
  ✓ Wait for checks to register
  * Wait for checks to pass
  * Squash-merge release PR

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz release: .github#5

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Publish plan: .github#5

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz PR: .github#2

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Release-plz · 34184827262
Triggered via push about 9 minutes ago

JOBS
✓ Release-plz release in 26s (ID 101930947729)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz release output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ Publish plan in 4s (ID 101931026408)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Compute publish plan
  ✓ Post Checkout repository
  ✓ Complete job
✓ Release-plz PR in 4m25s (ID 101931026548)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz PR output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
- linux ${{ matrix.target }} (ID 101931047370)
- windows x86_64 (ID 101931047401)
- sdist (ID 101931047534)
- macos universal2 (ID 101931047835)
- twine check in 0s (ID 101931047843)
- publish to PyPI in 0s (ID 101931047975)
* Merge release PR (ID 101931764196)
  ✓ Set up job
  ✓ Resolve release PR
  ✓ Wait for checks to register
  * Wait for checks to pass
  * Squash-merge release PR

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz release: .github#5

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Publish plan: .github#5

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz PR: .github#2

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Release-plz · 34184827262
Triggered via push about 9 minutes ago

JOBS
✓ Release-plz release in 26s (ID 101930947729)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz release output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ Publish plan in 4s (ID 101931026408)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Compute publish plan
  ✓ Post Checkout repository
  ✓ Complete job
✓ Release-plz PR in 4m25s (ID 101931026548)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz PR output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
- linux ${{ matrix.target }} (ID 101931047370)
- windows x86_64 (ID 101931047401)
- sdist (ID 101931047534)
- macos universal2 (ID 101931047835)
- twine check in 0s (ID 101931047843)
- publish to PyPI in 0s (ID 101931047975)
* Merge release PR (ID 101931764196)
  ✓ Set up job
  ✓ Resolve release PR
  ✓ Wait for checks to register
  * Wait for checks to pass
  * Squash-merge release PR

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz release: .github#5

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Publish plan: .github#5

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz PR: .github#2

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Release-plz · 34184827262
Triggered via push about 9 minutes ago

JOBS
✓ Release-plz release in 26s (ID 101930947729)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz release output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ Publish plan in 4s (ID 101931026408)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Compute publish plan
  ✓ Post Checkout repository
  ✓ Complete job
✓ Release-plz PR in 4m25s (ID 101931026548)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz PR output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
- linux ${{ matrix.target }} (ID 101931047370)
- windows x86_64 (ID 101931047401)
- sdist (ID 101931047534)
- macos universal2 (ID 101931047835)
- twine check in 0s (ID 101931047843)
- publish to PyPI in 0s (ID 101931047975)
* Merge release PR (ID 101931764196)
  ✓ Set up job
  ✓ Resolve release PR
  ✓ Wait for checks to register
  * Wait for checks to pass
  * Squash-merge release PR

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz release: .github#5

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Publish plan: .github#5

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz PR: .github#2

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Release-plz · 34184827262
Triggered via push about 9 minutes ago

JOBS
✓ Release-plz release in 26s (ID 101930947729)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz release output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ Publish plan in 4s (ID 101931026408)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Compute publish plan
  ✓ Post Checkout repository
  ✓ Complete job
✓ Release-plz PR in 4m25s (ID 101931026548)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz PR output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
- linux ${{ matrix.target }} (ID 101931047370)
- windows x86_64 (ID 101931047401)
- sdist (ID 101931047534)
- macos universal2 (ID 101931047835)
- twine check in 0s (ID 101931047843)
- publish to PyPI in 0s (ID 101931047975)
* Merge release PR (ID 101931764196)
  ✓ Set up job
  ✓ Resolve release PR
  ✓ Wait for checks to register
  * Wait for checks to pass
  * Squash-merge release PR

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz release: .github#5

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Publish plan: .github#5

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz PR: .github#2

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Release-plz · 34184827262
Triggered via push about 9 minutes ago

JOBS
✓ Release-plz release in 26s (ID 101930947729)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz release output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ Publish plan in 4s (ID 101931026408)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Compute publish plan
  ✓ Post Checkout repository
  ✓ Complete job
✓ Release-plz PR in 4m25s (ID 101931026548)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz PR output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
- linux ${{ matrix.target }} (ID 101931047370)
- windows x86_64 (ID 101931047401)
- sdist (ID 101931047534)
- macos universal2 (ID 101931047835)
- twine check in 0s (ID 101931047843)
- publish to PyPI in 0s (ID 101931047975)
* Merge release PR (ID 101931764196)
  ✓ Set up job
  ✓ Resolve release PR
  ✓ Wait for checks to register
  * Wait for checks to pass
  * Squash-merge release PR

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz release: .github#5

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Publish plan: .github#5

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz PR: .github#2

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Release-plz · 34184827262
Triggered via push about 9 minutes ago

JOBS
✓ Release-plz release in 26s (ID 101930947729)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz release output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ Publish plan in 4s (ID 101931026408)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Compute publish plan
  ✓ Post Checkout repository
  ✓ Complete job
✓ Release-plz PR in 4m25s (ID 101931026548)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz PR output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
- linux ${{ matrix.target }} (ID 101931047370)
- windows x86_64 (ID 101931047401)
- sdist (ID 101931047534)
- macos universal2 (ID 101931047835)
- twine check in 0s (ID 101931047843)
- publish to PyPI in 0s (ID 101931047975)
* Merge release PR (ID 101931764196)
  ✓ Set up job
  ✓ Resolve release PR
  ✓ Wait for checks to register
  * Wait for checks to pass
  * Squash-merge release PR

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz release: .github#5

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Publish plan: .github#5

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz PR: .github#2

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Release-plz · 34184827262
Triggered via push about 9 minutes ago

JOBS
✓ Release-plz release in 26s (ID 101930947729)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz release output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ Publish plan in 4s (ID 101931026408)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Compute publish plan
  ✓ Post Checkout repository
  ✓ Complete job
✓ Release-plz PR in 4m25s (ID 101931026548)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz PR output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
- linux ${{ matrix.target }} (ID 101931047370)
- windows x86_64 (ID 101931047401)
- sdist (ID 101931047534)
- macos universal2 (ID 101931047835)
- twine check in 0s (ID 101931047843)
- publish to PyPI in 0s (ID 101931047975)
* Merge release PR (ID 101931764196)
  ✓ Set up job
  ✓ Resolve release PR
  ✓ Wait for checks to register
  * Wait for checks to pass
  * Squash-merge release PR

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz release: .github#5

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Publish plan: .github#5

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz PR: .github#2

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Release-plz · 34184827262
Triggered via push about 9 minutes ago

JOBS
✓ Release-plz release in 26s (ID 101930947729)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz release output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ Publish plan in 4s (ID 101931026408)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Compute publish plan
  ✓ Post Checkout repository
  ✓ Complete job
✓ Release-plz PR in 4m25s (ID 101931026548)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz PR output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
- linux ${{ matrix.target }} (ID 101931047370)
- windows x86_64 (ID 101931047401)
- sdist (ID 101931047534)
- macos universal2 (ID 101931047835)
- twine check in 0s (ID 101931047843)
- publish to PyPI in 0s (ID 101931047975)
* Merge release PR (ID 101931764196)
  ✓ Set up job
  ✓ Resolve release PR
  ✓ Wait for checks to register
  * Wait for checks to pass
  * Squash-merge release PR

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz release: .github#5

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Publish plan: .github#5

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz PR: .github#2

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Release-plz · 34184827262
Triggered via push about 9 minutes ago

JOBS
✓ Release-plz release in 26s (ID 101930947729)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz release output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ Publish plan in 4s (ID 101931026408)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Compute publish plan
  ✓ Post Checkout repository
  ✓ Complete job
✓ Release-plz PR in 4m25s (ID 101931026548)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz PR output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
- linux ${{ matrix.target }} (ID 101931047370)
- windows x86_64 (ID 101931047401)
- sdist (ID 101931047534)
- macos universal2 (ID 101931047835)
- twine check in 0s (ID 101931047843)
- publish to PyPI in 0s (ID 101931047975)
* Merge release PR (ID 101931764196)
  ✓ Set up job
  ✓ Resolve release PR
  ✓ Wait for checks to register
  * Wait for checks to pass
  * Squash-merge release PR

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz release: .github#5

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Publish plan: .github#5

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz PR: .github#2

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Release-plz · 34184827262
Triggered via push about 9 minutes ago

JOBS
✓ Release-plz release in 26s (ID 101930947729)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz release output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ Publish plan in 4s (ID 101931026408)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Compute publish plan
  ✓ Post Checkout repository
  ✓ Complete job
✓ Release-plz PR in 4m25s (ID 101931026548)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz PR output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
- linux ${{ matrix.target }} (ID 101931047370)
- windows x86_64 (ID 101931047401)
- sdist (ID 101931047534)
- macos universal2 (ID 101931047835)
- twine check in 0s (ID 101931047843)
- publish to PyPI in 0s (ID 101931047975)
* Merge release PR (ID 101931764196)
  ✓ Set up job
  ✓ Resolve release PR
  ✓ Wait for checks to register
  * Wait for checks to pass
  * Squash-merge release PR

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz release: .github#5

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Publish plan: .github#5

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz PR: .github#2

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Release-plz · 34184827262
Triggered via push about 9 minutes ago

JOBS
✓ Release-plz release in 26s (ID 101930947729)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz release output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ Publish plan in 4s (ID 101931026408)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Compute publish plan
  ✓ Post Checkout repository
  ✓ Complete job
✓ Release-plz PR in 4m25s (ID 101931026548)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz PR output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
- linux ${{ matrix.target }} (ID 101931047370)
- windows x86_64 (ID 101931047401)
- sdist (ID 101931047534)
- macos universal2 (ID 101931047835)
- twine check in 0s (ID 101931047843)
- publish to PyPI in 0s (ID 101931047975)
* Merge release PR (ID 101931764196)
  ✓ Set up job
  ✓ Resolve release PR
  ✓ Wait for checks to register
  * Wait for checks to pass
  * Squash-merge release PR

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz release: .github#5

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Publish plan: .github#5

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz PR: .github#2

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Release-plz · 34184827262
Triggered via push about 9 minutes ago

JOBS
✓ Release-plz release in 26s (ID 101930947729)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz release output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ Publish plan in 4s (ID 101931026408)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Compute publish plan
  ✓ Post Checkout repository
  ✓ Complete job
✓ Release-plz PR in 4m25s (ID 101931026548)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz PR output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
- linux ${{ matrix.target }} (ID 101931047370)
- windows x86_64 (ID 101931047401)
- sdist (ID 101931047534)
- macos universal2 (ID 101931047835)
- twine check in 0s (ID 101931047843)
- publish to PyPI in 0s (ID 101931047975)
* Merge release PR (ID 101931764196)
  ✓ Set up job
  ✓ Resolve release PR
  ✓ Wait for checks to register
  * Wait for checks to pass
  * Squash-merge release PR

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz release: .github#5

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Publish plan: .github#5

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz PR: .github#2

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Release-plz · 34184827262
Triggered via push about 9 minutes ago

JOBS
✓ Release-plz release in 26s (ID 101930947729)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz release output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ Publish plan in 4s (ID 101931026408)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Compute publish plan
  ✓ Post Checkout repository
  ✓ Complete job
✓ Release-plz PR in 4m25s (ID 101931026548)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz PR output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
- linux ${{ matrix.target }} (ID 101931047370)
- windows x86_64 (ID 101931047401)
- sdist (ID 101931047534)
- macos universal2 (ID 101931047835)
- twine check in 0s (ID 101931047843)
- publish to PyPI in 0s (ID 101931047975)
* Merge release PR (ID 101931764196)
  ✓ Set up job
  ✓ Resolve release PR
  ✓ Wait for checks to register
  * Wait for checks to pass
  * Squash-merge release PR

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz release: .github#5

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Publish plan: .github#5

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz PR: .github#2

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Release-plz · 34184827262
Triggered via push about 10 minutes ago

JOBS
✓ Release-plz release in 26s (ID 101930947729)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz release output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ Publish plan in 4s (ID 101931026408)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Compute publish plan
  ✓ Post Checkout repository
  ✓ Complete job
✓ Release-plz PR in 4m25s (ID 101931026548)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz PR output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
- linux ${{ matrix.target }} (ID 101931047370)
- windows x86_64 (ID 101931047401)
- sdist (ID 101931047534)
- macos universal2 (ID 101931047835)
- twine check in 0s (ID 101931047843)
- publish to PyPI in 0s (ID 101931047975)
* Merge release PR (ID 101931764196)
  ✓ Set up job
  ✓ Resolve release PR
  ✓ Wait for checks to register
  * Wait for checks to pass
  * Squash-merge release PR

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz release: .github#5

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Publish plan: .github#5

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz PR: .github#2

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Release-plz · 34184827262
Triggered via push about 10 minutes ago

JOBS
✓ Release-plz release in 26s (ID 101930947729)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz release output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ Publish plan in 4s (ID 101931026408)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Compute publish plan
  ✓ Post Checkout repository
  ✓ Complete job
✓ Release-plz PR in 4m25s (ID 101931026548)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz PR output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
- linux ${{ matrix.target }} (ID 101931047370)
- windows x86_64 (ID 101931047401)
- sdist (ID 101931047534)
- macos universal2 (ID 101931047835)
- twine check in 0s (ID 101931047843)
- publish to PyPI in 0s (ID 101931047975)
* Merge release PR (ID 101931764196)
  ✓ Set up job
  ✓ Resolve release PR
  ✓ Wait for checks to register
  * Wait for checks to pass
  * Squash-merge release PR

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz release: .github#5

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Publish plan: .github#5

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz PR: .github#2

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Release-plz · 34184827262
Triggered via push about 10 minutes ago

JOBS
✓ Release-plz release in 26s (ID 101930947729)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz release output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ Publish plan in 4s (ID 101931026408)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Compute publish plan
  ✓ Post Checkout repository
  ✓ Complete job
✓ Release-plz PR in 4m25s (ID 101931026548)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz PR output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
- linux ${{ matrix.target }} (ID 101931047370)
- windows x86_64 (ID 101931047401)
- sdist (ID 101931047534)
- macos universal2 (ID 101931047835)
- twine check in 0s (ID 101931047843)
- publish to PyPI in 0s (ID 101931047975)
* Merge release PR (ID 101931764196)
  ✓ Set up job
  ✓ Resolve release PR
  ✓ Wait for checks to register
  * Wait for checks to pass
  * Squash-merge release PR

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz release: .github#5

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Publish plan: .github#5

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz PR: .github#2

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Release-plz · 34184827262
Triggered via push about 10 minutes ago

JOBS
✓ Release-plz release in 26s (ID 101930947729)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz release output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ Publish plan in 4s (ID 101931026408)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Compute publish plan
  ✓ Post Checkout repository
  ✓ Complete job
✓ Release-plz PR in 4m25s (ID 101931026548)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz PR output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
- linux ${{ matrix.target }} (ID 101931047370)
- windows x86_64 (ID 101931047401)
- sdist (ID 101931047534)
- macos universal2 (ID 101931047835)
- twine check in 0s (ID 101931047843)
- publish to PyPI in 0s (ID 101931047975)
* Merge release PR (ID 101931764196)
  ✓ Set up job
  ✓ Resolve release PR
  ✓ Wait for checks to register
  * Wait for checks to pass
  * Squash-merge release PR

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz release: .github#5

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Publish plan: .github#5

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz PR: .github#2

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Release-plz · 34184827262
Triggered via push about 10 minutes ago

JOBS
✓ Release-plz release in 26s (ID 101930947729)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz release output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ Publish plan in 4s (ID 101931026408)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Compute publish plan
  ✓ Post Checkout repository
  ✓ Complete job
✓ Release-plz PR in 4m25s (ID 101931026548)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz PR output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
- linux ${{ matrix.target }} (ID 101931047370)
- windows x86_64 (ID 101931047401)
- sdist (ID 101931047534)
- macos universal2 (ID 101931047835)
- twine check in 0s (ID 101931047843)
- publish to PyPI in 0s (ID 101931047975)
* Merge release PR (ID 101931764196)
  ✓ Set up job
  ✓ Resolve release PR
  ✓ Wait for checks to register
  * Wait for checks to pass
  * Squash-merge release PR

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz release: .github#5

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Publish plan: .github#5

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz PR: .github#2

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Release-plz · 34184827262
Triggered via push about 10 minutes ago

JOBS
✓ Release-plz release in 26s (ID 101930947729)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz release output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ Publish plan in 4s (ID 101931026408)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Compute publish plan
  ✓ Post Checkout repository
  ✓ Complete job
✓ Release-plz PR in 4m25s (ID 101931026548)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz PR output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
- linux ${{ matrix.target }} (ID 101931047370)
- windows x86_64 (ID 101931047401)
- sdist (ID 101931047534)
- macos universal2 (ID 101931047835)
- twine check in 0s (ID 101931047843)
- publish to PyPI in 0s (ID 101931047975)
* Merge release PR (ID 101931764196)
  ✓ Set up job
  ✓ Resolve release PR
  ✓ Wait for checks to register
  * Wait for checks to pass
  * Squash-merge release PR

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz release: .github#5

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Publish plan: .github#5

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz PR: .github#2

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Release-plz · 34184827262
Triggered via push about 10 minutes ago

JOBS
✓ Release-plz release in 26s (ID 101930947729)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz release output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ Publish plan in 4s (ID 101931026408)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Compute publish plan
  ✓ Post Checkout repository
  ✓ Complete job
✓ Release-plz PR in 4m25s (ID 101931026548)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz PR output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
- linux ${{ matrix.target }} (ID 101931047370)
- windows x86_64 (ID 101931047401)
- sdist (ID 101931047534)
- macos universal2 (ID 101931047835)
- twine check in 0s (ID 101931047843)
- publish to PyPI in 0s (ID 101931047975)
* Merge release PR (ID 101931764196)
  ✓ Set up job
  ✓ Resolve release PR
  ✓ Wait for checks to register
  * Wait for checks to pass
  * Squash-merge release PR

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz release: .github#5

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Publish plan: .github#5

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz PR: .github#2

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Release-plz · 34184827262
Triggered via push about 10 minutes ago

JOBS
✓ Release-plz release in 26s (ID 101930947729)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz release output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ Publish plan in 4s (ID 101931026408)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Compute publish plan
  ✓ Post Checkout repository
  ✓ Complete job
✓ Release-plz PR in 4m25s (ID 101931026548)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz PR output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
- linux ${{ matrix.target }} (ID 101931047370)
- windows x86_64 (ID 101931047401)
- sdist (ID 101931047534)
- macos universal2 (ID 101931047835)
- twine check in 0s (ID 101931047843)
- publish to PyPI in 0s (ID 101931047975)
* Merge release PR (ID 101931764196)
  ✓ Set up job
  ✓ Resolve release PR
  ✓ Wait for checks to register
  * Wait for checks to pass
  * Squash-merge release PR

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz release: .github#5

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Publish plan: .github#5

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz PR: .github#2

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Release-plz · 34184827262
Triggered via push about 10 minutes ago

JOBS
✓ Release-plz release in 26s (ID 101930947729)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz release output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ Publish plan in 4s (ID 101931026408)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Compute publish plan
  ✓ Post Checkout repository
  ✓ Complete job
✓ Release-plz PR in 4m25s (ID 101931026548)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz PR output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
- linux ${{ matrix.target }} (ID 101931047370)
- windows x86_64 (ID 101931047401)
- sdist (ID 101931047534)
- macos universal2 (ID 101931047835)
- twine check in 0s (ID 101931047843)
- publish to PyPI in 0s (ID 101931047975)
* Merge release PR (ID 101931764196)
  ✓ Set up job
  ✓ Resolve release PR
  ✓ Wait for checks to register
  * Wait for checks to pass
  * Squash-merge release PR

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz release: .github#5

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Publish plan: .github#5

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz PR: .github#2

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Release-plz · 34184827262
Triggered via push about 10 minutes ago

JOBS
✓ Release-plz release in 26s (ID 101930947729)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz release output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ Publish plan in 4s (ID 101931026408)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Compute publish plan
  ✓ Post Checkout repository
  ✓ Complete job
✓ Release-plz PR in 4m25s (ID 101931026548)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz PR output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
- linux ${{ matrix.target }} (ID 101931047370)
- windows x86_64 (ID 101931047401)
- sdist (ID 101931047534)
- macos universal2 (ID 101931047835)
- twine check in 0s (ID 101931047843)
- publish to PyPI in 0s (ID 101931047975)
* Merge release PR (ID 101931764196)
  ✓ Set up job
  ✓ Resolve release PR
  ✓ Wait for checks to register
  * Wait for checks to pass
  * Squash-merge release PR

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz release: .github#5

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Publish plan: .github#5

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz PR: .github#2

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Release-plz · 34184827262
Triggered via push about 10 minutes ago

JOBS
✓ Release-plz release in 26s (ID 101930947729)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz release output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ Publish plan in 4s (ID 101931026408)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Compute publish plan
  ✓ Post Checkout repository
  ✓ Complete job
✓ Release-plz PR in 4m25s (ID 101931026548)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz PR output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
- linux ${{ matrix.target }} (ID 101931047370)
- windows x86_64 (ID 101931047401)
- sdist (ID 101931047534)
- macos universal2 (ID 101931047835)
- twine check in 0s (ID 101931047843)
- publish to PyPI in 0s (ID 101931047975)
* Merge release PR (ID 101931764196)
  ✓ Set up job
  ✓ Resolve release PR
  ✓ Wait for checks to register
  * Wait for checks to pass
  * Squash-merge release PR

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz release: .github#5

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Publish plan: .github#5

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz PR: .github#2

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Release-plz · 34184827262
Triggered via push about 10 minutes ago

JOBS
✓ Release-plz release in 26s (ID 101930947729)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz release output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ Publish plan in 4s (ID 101931026408)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Compute publish plan
  ✓ Post Checkout repository
  ✓ Complete job
✓ Release-plz PR in 4m25s (ID 101931026548)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz PR output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
- linux ${{ matrix.target }} (ID 101931047370)
- windows x86_64 (ID 101931047401)
- sdist (ID 101931047534)
- macos universal2 (ID 101931047835)
- twine check in 0s (ID 101931047843)
- publish to PyPI in 0s (ID 101931047975)
* Merge release PR (ID 101931764196)
  ✓ Set up job
  ✓ Resolve release PR
  ✓ Wait for checks to register
  * Wait for checks to pass
  * Squash-merge release PR

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz release: .github#5

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Publish plan: .github#5

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz PR: .github#2

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Release-plz · 34184827262
Triggered via push about 10 minutes ago

JOBS
✓ Release-plz release in 26s (ID 101930947729)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz release output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ Publish plan in 4s (ID 101931026408)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Compute publish plan
  ✓ Post Checkout repository
  ✓ Complete job
✓ Release-plz PR in 4m25s (ID 101931026548)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz PR output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
- linux ${{ matrix.target }} (ID 101931047370)
- windows x86_64 (ID 101931047401)
- sdist (ID 101931047534)
- macos universal2 (ID 101931047835)
- twine check in 0s (ID 101931047843)
- publish to PyPI in 0s (ID 101931047975)
* Merge release PR (ID 101931764196)
  ✓ Set up job
  ✓ Resolve release PR
  ✓ Wait for checks to register
  * Wait for checks to pass
  * Squash-merge release PR

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz release: .github#5

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Publish plan: .github#5

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz PR: .github#2

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Release-plz · 34184827262
Triggered via push about 10 minutes ago

JOBS
✓ Release-plz release in 26s (ID 101930947729)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz release output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ Publish plan in 4s (ID 101931026408)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Compute publish plan
  ✓ Post Checkout repository
  ✓ Complete job
✓ Release-plz PR in 4m25s (ID 101931026548)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz PR output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
- linux ${{ matrix.target }} (ID 101931047370)
- windows x86_64 (ID 101931047401)
- sdist (ID 101931047534)
- macos universal2 (ID 101931047835)
- twine check in 0s (ID 101931047843)
- publish to PyPI in 0s (ID 101931047975)
* Merge release PR (ID 101931764196)
  ✓ Set up job
  ✓ Resolve release PR
  ✓ Wait for checks to register
  * Wait for checks to pass
  * Squash-merge release PR

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz release: .github#5

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Publish plan: .github#5

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz PR: .github#2

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Release-plz · 34184827262
Triggered via push about 10 minutes ago

JOBS
✓ Release-plz release in 26s (ID 101930947729)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz release output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ Publish plan in 4s (ID 101931026408)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Compute publish plan
  ✓ Post Checkout repository
  ✓ Complete job
✓ Release-plz PR in 4m25s (ID 101931026548)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz PR output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
- linux ${{ matrix.target }} (ID 101931047370)
- windows x86_64 (ID 101931047401)
- sdist (ID 101931047534)
- macos universal2 (ID 101931047835)
- twine check in 0s (ID 101931047843)
- publish to PyPI in 0s (ID 101931047975)
* Merge release PR (ID 101931764196)
  ✓ Set up job
  ✓ Resolve release PR
  ✓ Wait for checks to register
  * Wait for checks to pass
  * Squash-merge release PR

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz release: .github#5

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Publish plan: .github#5

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz PR: .github#2

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Release-plz · 34184827262
Triggered via push about 10 minutes ago

JOBS
✓ Release-plz release in 26s (ID 101930947729)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz release output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ Publish plan in 4s (ID 101931026408)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Compute publish plan
  ✓ Post Checkout repository
  ✓ Complete job
✓ Release-plz PR in 4m25s (ID 101931026548)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz PR output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
- linux ${{ matrix.target }} (ID 101931047370)
- windows x86_64 (ID 101931047401)
- sdist (ID 101931047534)
- macos universal2 (ID 101931047835)
- twine check in 0s (ID 101931047843)
- publish to PyPI in 0s (ID 101931047975)
* Merge release PR (ID 101931764196)
  ✓ Set up job
  ✓ Resolve release PR
  ✓ Wait for checks to register
  * Wait for checks to pass
  * Squash-merge release PR

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz release: .github#5

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Publish plan: .github#5

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz PR: .github#2

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Release-plz · 34184827262
Triggered via push about 11 minutes ago

JOBS
✓ Release-plz release in 26s (ID 101930947729)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz release output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ Publish plan in 4s (ID 101931026408)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Compute publish plan
  ✓ Post Checkout repository
  ✓ Complete job
✓ Release-plz PR in 4m25s (ID 101931026548)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz PR output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
- linux ${{ matrix.target }} (ID 101931047370)
- windows x86_64 (ID 101931047401)
- sdist (ID 101931047534)
- macos universal2 (ID 101931047835)
- twine check in 0s (ID 101931047843)
- publish to PyPI in 0s (ID 101931047975)
* Merge release PR (ID 101931764196)
  ✓ Set up job
  ✓ Resolve release PR
  ✓ Wait for checks to register
  * Wait for checks to pass
  * Squash-merge release PR

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz release: .github#5

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Publish plan: .github#5

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz PR: .github#2

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Release-plz · 34184827262
Triggered via push about 11 minutes ago

JOBS
✓ Release-plz release in 26s (ID 101930947729)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz release output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ Publish plan in 4s (ID 101931026408)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Compute publish plan
  ✓ Post Checkout repository
  ✓ Complete job
✓ Release-plz PR in 4m25s (ID 101931026548)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz PR output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
- linux ${{ matrix.target }} (ID 101931047370)
- windows x86_64 (ID 101931047401)
- sdist (ID 101931047534)
- macos universal2 (ID 101931047835)
- twine check in 0s (ID 101931047843)
- publish to PyPI in 0s (ID 101931047975)
* Merge release PR (ID 101931764196)
  ✓ Set up job
  ✓ Resolve release PR
  ✓ Wait for checks to register
  * Wait for checks to pass
  * Squash-merge release PR

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz release: .github#5

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Publish plan: .github#5

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz PR: .github#2

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Release-plz · 34184827262
Triggered via push about 11 minutes ago

JOBS
✓ Release-plz release in 26s (ID 101930947729)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz release output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ Publish plan in 4s (ID 101931026408)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Compute publish plan
  ✓ Post Checkout repository
  ✓ Complete job
✓ Release-plz PR in 4m25s (ID 101931026548)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz PR output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
- linux ${{ matrix.target }} (ID 101931047370)
- windows x86_64 (ID 101931047401)
- sdist (ID 101931047534)
- macos universal2 (ID 101931047835)
- twine check in 0s (ID 101931047843)
- publish to PyPI in 0s (ID 101931047975)
* Merge release PR (ID 101931764196)
  ✓ Set up job
  ✓ Resolve release PR
  ✓ Wait for checks to register
  * Wait for checks to pass
  * Squash-merge release PR

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz release: .github#5

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Publish plan: .github#5

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz PR: .github#2

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Release-plz · 34184827262
Triggered via push about 11 minutes ago

JOBS
✓ Release-plz release in 26s (ID 101930947729)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz release output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ Publish plan in 4s (ID 101931026408)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Compute publish plan
  ✓ Post Checkout repository
  ✓ Complete job
✓ Release-plz PR in 4m25s (ID 101931026548)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz PR output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
- linux ${{ matrix.target }} (ID 101931047370)
- windows x86_64 (ID 101931047401)
- sdist (ID 101931047534)
- macos universal2 (ID 101931047835)
- twine check in 0s (ID 101931047843)
- publish to PyPI in 0s (ID 101931047975)
* Merge release PR (ID 101931764196)
  ✓ Set up job
  ✓ Resolve release PR
  ✓ Wait for checks to register
  * Wait for checks to pass
  * Squash-merge release PR

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz release: .github#5

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Publish plan: .github#5

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz PR: .github#2

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Release-plz · 34184827262
Triggered via push about 11 minutes ago

JOBS
✓ Release-plz release in 26s (ID 101930947729)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz release output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ Publish plan in 4s (ID 101931026408)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Compute publish plan
  ✓ Post Checkout repository
  ✓ Complete job
✓ Release-plz PR in 4m25s (ID 101931026548)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz PR output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
- linux ${{ matrix.target }} (ID 101931047370)
- windows x86_64 (ID 101931047401)
- sdist (ID 101931047534)
- macos universal2 (ID 101931047835)
- twine check in 0s (ID 101931047843)
- publish to PyPI in 0s (ID 101931047975)
* Merge release PR (ID 101931764196)
  ✓ Set up job
  ✓ Resolve release PR
  ✓ Wait for checks to register
  * Wait for checks to pass
  * Squash-merge release PR

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz release: .github#5

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Publish plan: .github#5

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz PR: .github#2

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Release-plz · 34184827262
Triggered via push about 11 minutes ago

JOBS
✓ Release-plz release in 26s (ID 101930947729)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz release output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ Publish plan in 4s (ID 101931026408)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Compute publish plan
  ✓ Post Checkout repository
  ✓ Complete job
✓ Release-plz PR in 4m25s (ID 101931026548)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz PR output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
- linux ${{ matrix.target }} (ID 101931047370)
- windows x86_64 (ID 101931047401)
- sdist (ID 101931047534)
- macos universal2 (ID 101931047835)
- twine check in 0s (ID 101931047843)
- publish to PyPI in 0s (ID 101931047975)
* Merge release PR (ID 101931764196)
  ✓ Set up job
  ✓ Resolve release PR
  ✓ Wait for checks to register
  * Wait for checks to pass
  * Squash-merge release PR

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz release: .github#5

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Publish plan: .github#5

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz PR: .github#2

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Release-plz · 34184827262
Triggered via push about 11 minutes ago

JOBS
✓ Release-plz release in 26s (ID 101930947729)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz release output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ Publish plan in 4s (ID 101931026408)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Compute publish plan
  ✓ Post Checkout repository
  ✓ Complete job
✓ Release-plz PR in 4m25s (ID 101931026548)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz PR output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
- linux ${{ matrix.target }} (ID 101931047370)
- windows x86_64 (ID 101931047401)
- sdist (ID 101931047534)
- macos universal2 (ID 101931047835)
- twine check in 0s (ID 101931047843)
- publish to PyPI in 0s (ID 101931047975)
* Merge release PR (ID 101931764196)
  ✓ Set up job
  ✓ Resolve release PR
  ✓ Wait for checks to register
  * Wait for checks to pass
  * Squash-merge release PR

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz release: .github#5

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Publish plan: .github#5

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz PR: .github#2

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Release-plz · 34184827262
Triggered via push about 11 minutes ago

JOBS
✓ Release-plz release in 26s (ID 101930947729)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz release output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ Publish plan in 4s (ID 101931026408)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Compute publish plan
  ✓ Post Checkout repository
  ✓ Complete job
✓ Release-plz PR in 4m25s (ID 101931026548)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz PR output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
- linux ${{ matrix.target }} (ID 101931047370)
- windows x86_64 (ID 101931047401)
- sdist (ID 101931047534)
- macos universal2 (ID 101931047835)
- twine check in 0s (ID 101931047843)
- publish to PyPI in 0s (ID 101931047975)
* Merge release PR (ID 101931764196)
  ✓ Set up job
  ✓ Resolve release PR
  ✓ Wait for checks to register
  * Wait for checks to pass
  * Squash-merge release PR

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz release: .github#5

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Publish plan: .github#5

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz PR: .github#2

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Release-plz · 34184827262
Triggered via push about 11 minutes ago

JOBS
✓ Release-plz release in 26s (ID 101930947729)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz release output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ Publish plan in 4s (ID 101931026408)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Compute publish plan
  ✓ Post Checkout repository
  ✓ Complete job
✓ Release-plz PR in 4m25s (ID 101931026548)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz PR output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
- linux ${{ matrix.target }} (ID 101931047370)
- windows x86_64 (ID 101931047401)
- sdist (ID 101931047534)
- macos universal2 (ID 101931047835)
- twine check in 0s (ID 101931047843)
- publish to PyPI in 0s (ID 101931047975)
* Merge release PR (ID 101931764196)
  ✓ Set up job
  ✓ Resolve release PR
  ✓ Wait for checks to register
  * Wait for checks to pass
  * Squash-merge release PR

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz release: .github#5

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Publish plan: .github#5

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz PR: .github#2

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Release-plz · 34184827262
Triggered via push about 11 minutes ago

JOBS
✓ Release-plz release in 26s (ID 101930947729)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz release output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ Publish plan in 4s (ID 101931026408)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Compute publish plan
  ✓ Post Checkout repository
  ✓ Complete job
✓ Release-plz PR in 4m25s (ID 101931026548)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz PR output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
- linux ${{ matrix.target }} (ID 101931047370)
- windows x86_64 (ID 101931047401)
- sdist (ID 101931047534)
- macos universal2 (ID 101931047835)
- twine check in 0s (ID 101931047843)
- publish to PyPI in 0s (ID 101931047975)
* Merge release PR (ID 101931764196)
  ✓ Set up job
  ✓ Resolve release PR
  ✓ Wait for checks to register
  * Wait for checks to pass
  * Squash-merge release PR

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz release: .github#5

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Publish plan: .github#5

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz PR: .github#2

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Release-plz · 34184827262
Triggered via push about 11 minutes ago

JOBS
✓ Release-plz release in 26s (ID 101930947729)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz release output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ Publish plan in 4s (ID 101931026408)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Compute publish plan
  ✓ Post Checkout repository
  ✓ Complete job
✓ Release-plz PR in 4m25s (ID 101931026548)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz PR output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
- linux ${{ matrix.target }} (ID 101931047370)
- windows x86_64 (ID 101931047401)
- sdist (ID 101931047534)
- macos universal2 (ID 101931047835)
- twine check in 0s (ID 101931047843)
- publish to PyPI in 0s (ID 101931047975)
* Merge release PR (ID 101931764196)
  ✓ Set up job
  ✓ Resolve release PR
  ✓ Wait for checks to register
  * Wait for checks to pass
  * Squash-merge release PR

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz release: .github#5

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Publish plan: .github#5

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz PR: .github#2

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Release-plz · 34184827262
Triggered via push about 11 minutes ago

JOBS
✓ Release-plz release in 26s (ID 101930947729)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz release output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ Publish plan in 4s (ID 101931026408)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Compute publish plan
  ✓ Post Checkout repository
  ✓ Complete job
✓ Release-plz PR in 4m25s (ID 101931026548)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz PR output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
- linux ${{ matrix.target }} (ID 101931047370)
- windows x86_64 (ID 101931047401)
- sdist (ID 101931047534)
- macos universal2 (ID 101931047835)
- twine check in 0s (ID 101931047843)
- publish to PyPI in 0s (ID 101931047975)
* Merge release PR (ID 101931764196)
  ✓ Set up job
  ✓ Resolve release PR
  ✓ Wait for checks to register
  * Wait for checks to pass
  * Squash-merge release PR

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz release: .github#5

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Publish plan: .github#5

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz PR: .github#2

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Release-plz · 34184827262
Triggered via push about 11 minutes ago

JOBS
✓ Release-plz release in 26s (ID 101930947729)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz release output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ Publish plan in 4s (ID 101931026408)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Compute publish plan
  ✓ Post Checkout repository
  ✓ Complete job
✓ Release-plz PR in 4m25s (ID 101931026548)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz PR output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
- linux ${{ matrix.target }} (ID 101931047370)
- windows x86_64 (ID 101931047401)
- sdist (ID 101931047534)
- macos universal2 (ID 101931047835)
- twine check in 0s (ID 101931047843)
- publish to PyPI in 0s (ID 101931047975)
* Merge release PR (ID 101931764196)
  ✓ Set up job
  ✓ Resolve release PR
  ✓ Wait for checks to register
  * Wait for checks to pass
  * Squash-merge release PR

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz release: .github#5

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Publish plan: .github#5

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz PR: .github#2

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Release-plz · 34184827262
Triggered via push about 11 minutes ago

JOBS
✓ Release-plz release in 26s (ID 101930947729)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz release output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ Publish plan in 4s (ID 101931026408)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Compute publish plan
  ✓ Post Checkout repository
  ✓ Complete job
✓ Release-plz PR in 4m25s (ID 101931026548)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz PR output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
- linux ${{ matrix.target }} (ID 101931047370)
- windows x86_64 (ID 101931047401)
- sdist (ID 101931047534)
- macos universal2 (ID 101931047835)
- twine check in 0s (ID 101931047843)
- publish to PyPI in 0s (ID 101931047975)
* Merge release PR (ID 101931764196)
  ✓ Set up job
  ✓ Resolve release PR
  ✓ Wait for checks to register
  * Wait for checks to pass
  * Squash-merge release PR

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz release: .github#5

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Publish plan: .github#5

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz PR: .github#2

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Release-plz · 34184827262
Triggered via push about 11 minutes ago

JOBS
✓ Release-plz release in 26s (ID 101930947729)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz release output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ Publish plan in 4s (ID 101931026408)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Compute publish plan
  ✓ Post Checkout repository
  ✓ Complete job
✓ Release-plz PR in 4m25s (ID 101931026548)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz PR output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
- linux ${{ matrix.target }} (ID 101931047370)
- windows x86_64 (ID 101931047401)
- sdist (ID 101931047534)
- macos universal2 (ID 101931047835)
- twine check in 0s (ID 101931047843)
- publish to PyPI in 0s (ID 101931047975)
* Merge release PR (ID 101931764196)
  ✓ Set up job
  ✓ Resolve release PR
  ✓ Wait for checks to register
  * Wait for checks to pass
  * Squash-merge release PR

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz release: .github#5

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Publish plan: .github#5

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz PR: .github#2

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Release-plz · 34184827262
Triggered via push about 11 minutes ago

JOBS
✓ Release-plz release in 26s (ID 101930947729)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz release output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ Publish plan in 4s (ID 101931026408)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Compute publish plan
  ✓ Post Checkout repository
  ✓ Complete job
✓ Release-plz PR in 4m25s (ID 101931026548)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz PR output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
- linux ${{ matrix.target }} (ID 101931047370)
- windows x86_64 (ID 101931047401)
- sdist (ID 101931047534)
- macos universal2 (ID 101931047835)
- twine check in 0s (ID 101931047843)
- publish to PyPI in 0s (ID 101931047975)
* Merge release PR (ID 101931764196)
  ✓ Set up job
  ✓ Resolve release PR
  ✓ Wait for checks to register
  * Wait for checks to pass
  * Squash-merge release PR

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz release: .github#5

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Publish plan: .github#5

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz PR: .github#2

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Release-plz · 34184827262
Triggered via push about 12 minutes ago

JOBS
✓ Release-plz release in 26s (ID 101930947729)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz release output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ Publish plan in 4s (ID 101931026408)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Compute publish plan
  ✓ Post Checkout repository
  ✓ Complete job
✓ Release-plz PR in 4m25s (ID 101931026548)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz PR output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
- linux ${{ matrix.target }} (ID 101931047370)
- windows x86_64 (ID 101931047401)
- sdist (ID 101931047534)
- macos universal2 (ID 101931047835)
- twine check in 0s (ID 101931047843)
- publish to PyPI in 0s (ID 101931047975)
* Merge release PR (ID 101931764196)
  ✓ Set up job
  ✓ Resolve release PR
  ✓ Wait for checks to register
  ✓ Wait for checks to pass
  * Squash-merge release PR

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz release: .github#5

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Publish plan: .github#5

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz PR: .github#2

Refreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Release-plz · 34184827262
Triggered via push about 12 minutes ago

JOBS
✓ Release-plz release in 26s (ID 101930947729)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz release output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ Publish plan in 4s (ID 101931026408)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Compute publish plan
  ✓ Post Checkout repository
  ✓ Complete job
✓ Release-plz PR in 4m25s (ID 101931026548)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz PR output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
- linux ${{ matrix.target }} (ID 101931047370)
- windows x86_64 (ID 101931047401)
- sdist (ID 101931047534)
- macos universal2 (ID 101931047835)
- twine check in 0s (ID 101931047843)
- publish to PyPI in 0s (ID 101931047975)
* Merge release PR (ID 101931764196)
  ✓ Set up job
  ✓ Resolve release PR
  ✓ Wait for checks to register
  ✓ Wait for checks to pass
  ✓ Squash-merge release PR
  ✓ Complete job

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz release: .github#5

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Publish plan: .github#5

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz PR: .github#2

✓ master Release-plz · 34184827262
Triggered via push about 12 minutes ago

JOBS
✓ Release-plz release in 26s (ID 101930947729)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz release output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
✓ Publish plan in 4s (ID 101931026408)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Compute publish plan
  ✓ Post Checkout repository
  ✓ Complete job
✓ Release-plz PR in 4m25s (ID 101931026548)
  ✓ Set up job
  ✓ Checkout repository
  ✓ Run dtolnay/rust-toolchain@stable
  ✓ Run Swatinem/rust-cache@v2
  ✓ Run release-plz
  ✓ Print release-plz PR output
  ✓ Post Run Swatinem/rust-cache@v2
  ✓ Post Checkout repository
  ✓ Complete job
- linux ${{ matrix.target }} (ID 101931047370)
- windows x86_64 (ID 101931047401)
- sdist (ID 101931047534)
- macos universal2 (ID 101931047835)
- twine check in 0s (ID 101931047843)
- publish to PyPI in 0s (ID 101931047975)
✓ Merge release PR in 7m3s (ID 101931764196)
  ✓ Set up job
  ✓ Resolve release PR
  ✓ Wait for checks to register
  ✓ Wait for checks to pass
  ✓ Squash-merge release PR
  ✓ Complete job

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz release: .github#5

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Publish plan: .github#5

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
Release-plz PR: .github#2

[release-wait] release PR workflow completed; waiting for PyPI 0.32.42
/bin/sh: 6: cannot open deadline: No such file
[release-wait] timed out waiting for sase-core-rs 0.32.42 on PyPI

