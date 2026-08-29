# Chat History - ace-run (sase-um.9.5.4--2)

- **TIMESTAMP:** 2026-08-29 00:15:38 EDT
- **MODEL:** grok/grok-4.6
- **AGENT:** sase-um.9.5.4--2

## Prompt

%xprompts_enabled:false
# Previous Conversation

**User:**

sase monitor start --command 'GH_FORCE_TTY=0 NO_COLOR=1 CLICOLOR=0 gh run watch 33232866336 --repo sase-org/sase --exit-status' --reason 'Wait for Master Gate 33232866336 on 49d6c4188 so ci_watch can leave gating_workflow_in_flight'

**Assistant:**

[?1049h[0;0H[JRefreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Master Gate · 33232866336
Triggered via push about 4 minutes ago

JOBS
✓ core-wheel in 18s (ID 99048616461)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Resolve pinned Rust core revision
  ✓ Restore cached core wheel
  - Check out Rust core
  - Run astral-sh/setup-uv@v4
  - Set up Rust
  - Cache Rust build
  - Build abi3 Rust core wheel
  - Build xprompt LSP
  - Record wheel provenance
  - Save core wheel cache
  ✓ Upload Rust core artifacts
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ lint in 3m21s (ID 99048656008)
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
* test (5) (ID 99048656072)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (6) (ID 99048656077)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (7) (ID 99048656078)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (1) (ID 99048656084)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (4) (ID 99048656104)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (3) (ID 99048656107)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (8) (ID 99048656108)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (2) (ID 99048656132)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache/restore@v4, actions/checkout@v4, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
core-wheel: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache@v4, actions/checkout@v4, actions/download-artifact@v4, actions/setup-go@v5, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
lint: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0ylqSagAAAADMk2TYDgMuT70dSAJGbLexUEhYMzFFREdFMDUxMQBFZGdl
lint: .github#10

! Failed to restore: Cache service responded with 400
lint: .github#55

[0;0H[JRefreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Master Gate · 33232866336
Triggered via push about 4 minutes ago

JOBS
✓ core-wheel in 18s (ID 99048616461)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Resolve pinned Rust core revision
  ✓ Restore cached core wheel
  - Check out Rust core
  - Run astral-sh/setup-uv@v4
  - Set up Rust
  - Cache Rust build
  - Build abi3 Rust core wheel
  - Build xprompt LSP
  - Record wheel provenance
  - Save core wheel cache
  ✓ Upload Rust core artifacts
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ lint in 3m21s (ID 99048656008)
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
* test (5) (ID 99048656072)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (6) (ID 99048656077)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (7) (ID 99048656078)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (1) (ID 99048656084)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (4) (ID 99048656104)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (3) (ID 99048656107)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (8) (ID 99048656108)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (2) (ID 99048656132)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache/restore@v4, actions/checkout@v4, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
core-wheel: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache@v4, actions/checkout@v4, actions/download-artifact@v4, actions/setup-go@v5, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
lint: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0ylqSagAAAADMk2TYDgMuT70dSAJGbLexUEhYMzFFREdFMDUxMQBFZGdl
lint: .github#10

! Failed to restore: Cache service responded with 400
lint: .github#55

[0;0H[JRefreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Master Gate · 33232866336
Triggered via push about 4 minutes ago

JOBS
✓ core-wheel in 18s (ID 99048616461)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Resolve pinned Rust core revision
  ✓ Restore cached core wheel
  - Check out Rust core
  - Run astral-sh/setup-uv@v4
  - Set up Rust
  - Cache Rust build
  - Build abi3 Rust core wheel
  - Build xprompt LSP
  - Record wheel provenance
  - Save core wheel cache
  ✓ Upload Rust core artifacts
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ lint in 3m21s (ID 99048656008)
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
* test (5) (ID 99048656072)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (6) (ID 99048656077)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (7) (ID 99048656078)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (1) (ID 99048656084)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (4) (ID 99048656104)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (3) (ID 99048656107)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (8) (ID 99048656108)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (2) (ID 99048656132)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache/restore@v4, actions/checkout@v4, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
core-wheel: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache@v4, actions/checkout@v4, actions/download-artifact@v4, actions/setup-go@v5, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
lint: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0ylqSagAAAADMk2TYDgMuT70dSAJGbLexUEhYMzFFREdFMDUxMQBFZGdl
lint: .github#10

! Failed to restore: Cache service responded with 400
lint: .github#55

[0;0H[JRefreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Master Gate · 33232866336
Triggered via push about 4 minutes ago

JOBS
✓ core-wheel in 18s (ID 99048616461)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Resolve pinned Rust core revision
  ✓ Restore cached core wheel
  - Check out Rust core
  - Run astral-sh/setup-uv@v4
  - Set up Rust
  - Cache Rust build
  - Build abi3 Rust core wheel
  - Build xprompt LSP
  - Record wheel provenance
  - Save core wheel cache
  ✓ Upload Rust core artifacts
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ lint in 3m21s (ID 99048656008)
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
* test (5) (ID 99048656072)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (6) (ID 99048656077)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (7) (ID 99048656078)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (1) (ID 99048656084)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (4) (ID 99048656104)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (3) (ID 99048656107)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (8) (ID 99048656108)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (2) (ID 99048656132)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache/restore@v4, actions/checkout@v4, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
core-wheel: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache@v4, actions/checkout@v4, actions/download-artifact@v4, actions/setup-go@v5, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
lint: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0ylqSagAAAADMk2TYDgMuT70dSAJGbLexUEhYMzFFREdFMDUxMQBFZGdl
lint: .github#10

! Failed to restore: Cache service responded with 400
lint: .github#55

[0;0H[JRefreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Master Gate · 33232866336
Triggered via push about 4 minutes ago

JOBS
✓ core-wheel in 18s (ID 99048616461)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Resolve pinned Rust core revision
  ✓ Restore cached core wheel
  - Check out Rust core
  - Run astral-sh/setup-uv@v4
  - Set up Rust
  - Cache Rust build
  - Build abi3 Rust core wheel
  - Build xprompt LSP
  - Record wheel provenance
  - Save core wheel cache
  ✓ Upload Rust core artifacts
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ lint in 3m21s (ID 99048656008)
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
* test (5) (ID 99048656072)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (6) (ID 99048656077)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (7) (ID 99048656078)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (1) (ID 99048656084)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (4) (ID 99048656104)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (3) (ID 99048656107)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (8) (ID 99048656108)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (2) (ID 99048656132)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache/restore@v4, actions/checkout@v4, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
core-wheel: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache@v4, actions/checkout@v4, actions/download-artifact@v4, actions/setup-go@v5, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
lint: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0ylqSagAAAADMk2TYDgMuT70dSAJGbLexUEhYMzFFREdFMDUxMQBFZGdl
lint: .github#10

! Failed to restore: Cache service responded with 400
lint: .github#55

[0;0H[JRefreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Master Gate · 33232866336
Triggered via push about 4 minutes ago

JOBS
✓ core-wheel in 18s (ID 99048616461)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Resolve pinned Rust core revision
  ✓ Restore cached core wheel
  - Check out Rust core
  - Run astral-sh/setup-uv@v4
  - Set up Rust
  - Cache Rust build
  - Build abi3 Rust core wheel
  - Build xprompt LSP
  - Record wheel provenance
  - Save core wheel cache
  ✓ Upload Rust core artifacts
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ lint in 3m21s (ID 99048656008)
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
* test (5) (ID 99048656072)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (6) (ID 99048656077)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (7) (ID 99048656078)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (1) (ID 99048656084)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (4) (ID 99048656104)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (3) (ID 99048656107)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (8) (ID 99048656108)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (2) (ID 99048656132)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache/restore@v4, actions/checkout@v4, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
core-wheel: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache@v4, actions/checkout@v4, actions/download-artifact@v4, actions/setup-go@v5, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
lint: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0ylqSagAAAADMk2TYDgMuT70dSAJGbLexUEhYMzFFREdFMDUxMQBFZGdl
lint: .github#10

! Failed to restore: Cache service responded with 400
lint: .github#55

[0;0H[JRefreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Master Gate · 33232866336
Triggered via push about 4 minutes ago

JOBS
✓ core-wheel in 18s (ID 99048616461)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Resolve pinned Rust core revision
  ✓ Restore cached core wheel
  - Check out Rust core
  - Run astral-sh/setup-uv@v4
  - Set up Rust
  - Cache Rust build
  - Build abi3 Rust core wheel
  - Build xprompt LSP
  - Record wheel provenance
  - Save core wheel cache
  ✓ Upload Rust core artifacts
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ lint in 3m21s (ID 99048656008)
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
* test (5) (ID 99048656072)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (6) (ID 99048656077)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (7) (ID 99048656078)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (1) (ID 99048656084)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (4) (ID 99048656104)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (3) (ID 99048656107)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (8) (ID 99048656108)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (2) (ID 99048656132)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache/restore@v4, actions/checkout@v4, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
core-wheel: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache@v4, actions/checkout@v4, actions/download-artifact@v4, actions/setup-go@v5, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
lint: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0ylqSagAAAADMk2TYDgMuT70dSAJGbLexUEhYMzFFREdFMDUxMQBFZGdl
lint: .github#10

! Failed to restore: Cache service responded with 400
lint: .github#55

[0;0H[JRefreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Master Gate · 33232866336
Triggered via push about 4 minutes ago

JOBS
✓ core-wheel in 18s (ID 99048616461)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Resolve pinned Rust core revision
  ✓ Restore cached core wheel
  - Check out Rust core
  - Run astral-sh/setup-uv@v4
  - Set up Rust
  - Cache Rust build
  - Build abi3 Rust core wheel
  - Build xprompt LSP
  - Record wheel provenance
  - Save core wheel cache
  ✓ Upload Rust core artifacts
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ lint in 3m21s (ID 99048656008)
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
* test (5) (ID 99048656072)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (6) (ID 99048656077)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (7) (ID 99048656078)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (1) (ID 99048656084)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (4) (ID 99048656104)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (3) (ID 99048656107)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (8) (ID 99048656108)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (2) (ID 99048656132)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache/restore@v4, actions/checkout@v4, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
core-wheel: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache@v4, actions/checkout@v4, actions/download-artifact@v4, actions/setup-go@v5, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
lint: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0ylqSagAAAADMk2TYDgMuT70dSAJGbLexUEhYMzFFREdFMDUxMQBFZGdl
lint: .github#10

! Failed to restore: Cache service responded with 400
lint: .github#55

[0;0H[JRefreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Master Gate · 33232866336
Triggered via push about 4 minutes ago

JOBS
✓ core-wheel in 18s (ID 99048616461)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Resolve pinned Rust core revision
  ✓ Restore cached core wheel
  - Check out Rust core
  - Run astral-sh/setup-uv@v4
  - Set up Rust
  - Cache Rust build
  - Build abi3 Rust core wheel
  - Build xprompt LSP
  - Record wheel provenance
  - Save core wheel cache
  ✓ Upload Rust core artifacts
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ lint in 3m21s (ID 99048656008)
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
* test (5) (ID 99048656072)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (6) (ID 99048656077)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (7) (ID 99048656078)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (1) (ID 99048656084)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (4) (ID 99048656104)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (3) (ID 99048656107)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (8) (ID 99048656108)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (2) (ID 99048656132)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache/restore@v4, actions/checkout@v4, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
core-wheel: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache@v4, actions/checkout@v4, actions/download-artifact@v4, actions/setup-go@v5, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
lint: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0ylqSagAAAADMk2TYDgMuT70dSAJGbLexUEhYMzFFREdFMDUxMQBFZGdl
lint: .github#10

! Failed to restore: Cache service responded with 400
lint: .github#55

[0;0H[JRefreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Master Gate · 33232866336
Triggered via push about 4 minutes ago

JOBS
✓ core-wheel in 18s (ID 99048616461)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Resolve pinned Rust core revision
  ✓ Restore cached core wheel
  - Check out Rust core
  - Run astral-sh/setup-uv@v4
  - Set up Rust
  - Cache Rust build
  - Build abi3 Rust core wheel
  - Build xprompt LSP
  - Record wheel provenance
  - Save core wheel cache
  ✓ Upload Rust core artifacts
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ lint in 3m21s (ID 99048656008)
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
* test (5) (ID 99048656072)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (6) (ID 99048656077)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (7) (ID 99048656078)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (1) (ID 99048656084)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (4) (ID 99048656104)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (3) (ID 99048656107)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (8) (ID 99048656108)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (2) (ID 99048656132)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache/restore@v4, actions/checkout@v4, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
core-wheel: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache@v4, actions/checkout@v4, actions/download-artifact@v4, actions/setup-go@v5, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
lint: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0ylqSagAAAADMk2TYDgMuT70dSAJGbLexUEhYMzFFREdFMDUxMQBFZGdl
lint: .github#10

! Failed to restore: Cache service responded with 400
lint: .github#55

[0;0H[JRefreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Master Gate · 33232866336
Triggered via push about 5 minutes ago

JOBS
✓ core-wheel in 18s (ID 99048616461)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Resolve pinned Rust core revision
  ✓ Restore cached core wheel
  - Check out Rust core
  - Run astral-sh/setup-uv@v4
  - Set up Rust
  - Cache Rust build
  - Build abi3 Rust core wheel
  - Build xprompt LSP
  - Record wheel provenance
  - Save core wheel cache
  ✓ Upload Rust core artifacts
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ lint in 3m21s (ID 99048656008)
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
* test (5) (ID 99048656072)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (6) (ID 99048656077)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (7) (ID 99048656078)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (1) (ID 99048656084)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (4) (ID 99048656104)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (3) (ID 99048656107)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (8) (ID 99048656108)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (2) (ID 99048656132)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache/restore@v4, actions/checkout@v4, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
core-wheel: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache@v4, actions/checkout@v4, actions/download-artifact@v4, actions/setup-go@v5, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
lint: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0ylqSagAAAADMk2TYDgMuT70dSAJGbLexUEhYMzFFREdFMDUxMQBFZGdl
lint: .github#10

! Failed to restore: Cache service responded with 400
lint: .github#55

[0;0H[JRefreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Master Gate · 33232866336
Triggered via push about 5 minutes ago

JOBS
✓ core-wheel in 18s (ID 99048616461)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Resolve pinned Rust core revision
  ✓ Restore cached core wheel
  - Check out Rust core
  - Run astral-sh/setup-uv@v4
  - Set up Rust
  - Cache Rust build
  - Build abi3 Rust core wheel
  - Build xprompt LSP
  - Record wheel provenance
  - Save core wheel cache
  ✓ Upload Rust core artifacts
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ lint in 3m21s (ID 99048656008)
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
* test (5) (ID 99048656072)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (6) (ID 99048656077)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (7) (ID 99048656078)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (1) (ID 99048656084)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (4) (ID 99048656104)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (3) (ID 99048656107)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (8) (ID 99048656108)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (2) (ID 99048656132)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache/restore@v4, actions/checkout@v4, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
core-wheel: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache@v4, actions/checkout@v4, actions/download-artifact@v4, actions/setup-go@v5, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
lint: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0ylqSagAAAADMk2TYDgMuT70dSAJGbLexUEhYMzFFREdFMDUxMQBFZGdl
lint: .github#10

! Failed to restore: Cache service responded with 400
lint: .github#55

[0;0H[JRefreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Master Gate · 33232866336
Triggered via push about 5 minutes ago

JOBS
✓ core-wheel in 18s (ID 99048616461)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Resolve pinned Rust core revision
  ✓ Restore cached core wheel
  - Check out Rust core
  - Run astral-sh/setup-uv@v4
  - Set up Rust
  - Cache Rust build
  - Build abi3 Rust core wheel
  - Build xprompt LSP
  - Record wheel provenance
  - Save core wheel cache
  ✓ Upload Rust core artifacts
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ lint in 3m21s (ID 99048656008)
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
* test (5) (ID 99048656072)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (6) (ID 99048656077)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (7) (ID 99048656078)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (1) (ID 99048656084)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (4) (ID 99048656104)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (3) (ID 99048656107)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (8) (ID 99048656108)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (2) (ID 99048656132)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache/restore@v4, actions/checkout@v4, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
core-wheel: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache@v4, actions/checkout@v4, actions/download-artifact@v4, actions/setup-go@v5, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
lint: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0ylqSagAAAADMk2TYDgMuT70dSAJGbLexUEhYMzFFREdFMDUxMQBFZGdl
lint: .github#10

! Failed to restore: Cache service responded with 400
lint: .github#55

[0;0H[JRefreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Master Gate · 33232866336
Triggered via push about 5 minutes ago

JOBS
✓ core-wheel in 18s (ID 99048616461)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Resolve pinned Rust core revision
  ✓ Restore cached core wheel
  - Check out Rust core
  - Run astral-sh/setup-uv@v4
  - Set up Rust
  - Cache Rust build
  - Build abi3 Rust core wheel
  - Build xprompt LSP
  - Record wheel provenance
  - Save core wheel cache
  ✓ Upload Rust core artifacts
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ lint in 3m21s (ID 99048656008)
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
* test (5) (ID 99048656072)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (6) (ID 99048656077)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (7) (ID 99048656078)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (1) (ID 99048656084)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (4) (ID 99048656104)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (3) (ID 99048656107)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (8) (ID 99048656108)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (2) (ID 99048656132)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache/restore@v4, actions/checkout@v4, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
core-wheel: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache@v4, actions/checkout@v4, actions/download-artifact@v4, actions/setup-go@v5, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
lint: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0ylqSagAAAADMk2TYDgMuT70dSAJGbLexUEhYMzFFREdFMDUxMQBFZGdl
lint: .github#10

! Failed to restore: Cache service responded with 400
lint: .github#55

[0;0H[JRefreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Master Gate · 33232866336
Triggered via push about 5 minutes ago

JOBS
✓ core-wheel in 18s (ID 99048616461)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Resolve pinned Rust core revision
  ✓ Restore cached core wheel
  - Check out Rust core
  - Run astral-sh/setup-uv@v4
  - Set up Rust
  - Cache Rust build
  - Build abi3 Rust core wheel
  - Build xprompt LSP
  - Record wheel provenance
  - Save core wheel cache
  ✓ Upload Rust core artifacts
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ lint in 3m21s (ID 99048656008)
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
* test (5) (ID 99048656072)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
✓ test (6) in 4m54s (ID 99048656077)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* test (7) (ID 99048656078)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (1) (ID 99048656084)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (4) (ID 99048656104)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (3) (ID 99048656107)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (8) (ID 99048656108)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (2) (ID 99048656132)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache/restore@v4, actions/checkout@v4, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
core-wheel: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache@v4, actions/checkout@v4, actions/download-artifact@v4, actions/setup-go@v5, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
lint: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0ylqSagAAAADMk2TYDgMuT70dSAJGbLexUEhYMzFFREdFMDUxMQBFZGdl
lint: .github#10

! Failed to restore: Cache service responded with 400
lint: .github#55

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
test (6): .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0KFuSagAAAAA5gQ57c4RXSaFbjrJnnjtbUEhMMzBFREdFMDQxNgBFZGdl
test (6): .github#10

! Failed to restore: Cache service responded with 400
test (6): .github#55

[0;0H[JRefreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Master Gate · 33232866336
Triggered via push about 5 minutes ago

JOBS
✓ core-wheel in 18s (ID 99048616461)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Resolve pinned Rust core revision
  ✓ Restore cached core wheel
  - Check out Rust core
  - Run astral-sh/setup-uv@v4
  - Set up Rust
  - Cache Rust build
  - Build abi3 Rust core wheel
  - Build xprompt LSP
  - Record wheel provenance
  - Save core wheel cache
  ✓ Upload Rust core artifacts
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ lint in 3m21s (ID 99048656008)
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
* test (5) (ID 99048656072)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
✓ test (6) in 4m54s (ID 99048656077)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* test (7) (ID 99048656078)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (1) (ID 99048656084)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (4) (ID 99048656104)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (3) (ID 99048656107)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (8) (ID 99048656108)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (2) (ID 99048656132)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache/restore@v4, actions/checkout@v4, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
core-wheel: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache@v4, actions/checkout@v4, actions/download-artifact@v4, actions/setup-go@v5, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
lint: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0ylqSagAAAADMk2TYDgMuT70dSAJGbLexUEhYMzFFREdFMDUxMQBFZGdl
lint: .github#10

! Failed to restore: Cache service responded with 400
lint: .github#55

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
test (6): .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0KFuSagAAAAA5gQ57c4RXSaFbjrJnnjtbUEhMMzBFREdFMDQxNgBFZGdl
test (6): .github#10

! Failed to restore: Cache service responded with 400
test (6): .github#55

[0;0H[JRefreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Master Gate · 33232866336
Triggered via push about 5 minutes ago

JOBS
✓ core-wheel in 18s (ID 99048616461)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Resolve pinned Rust core revision
  ✓ Restore cached core wheel
  - Check out Rust core
  - Run astral-sh/setup-uv@v4
  - Set up Rust
  - Cache Rust build
  - Build abi3 Rust core wheel
  - Build xprompt LSP
  - Record wheel provenance
  - Save core wheel cache
  ✓ Upload Rust core artifacts
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ lint in 3m21s (ID 99048656008)
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
* test (5) (ID 99048656072)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
✓ test (6) in 4m54s (ID 99048656077)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* test (7) (ID 99048656078)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (1) (ID 99048656084)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (4) (ID 99048656104)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (3) (ID 99048656107)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (8) (ID 99048656108)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (2) (ID 99048656132)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4

ANNOTATIONS
! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache/restore@v4, actions/checkout@v4, actions/upload-artifact@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
core-wheel: .github#2

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache@v4, actions/checkout@v4, actions/download-artifact@v4, actions/setup-go@v5, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
lint: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0ylqSagAAAADMk2TYDgMuT70dSAJGbLexUEhYMzFFREdFMDUxMQBFZGdl
lint: .github#10

! Failed to restore: Cache service responded with 400
lint: .github#55

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
test (6): .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0KFuSagAAAAA5gQ57c4RXSaFbjrJnnjtbUEhMMzBFREdFMDQxNgBFZGdl
test (6): .github#10

! Failed to restore: Cache service responded with 400
test (6): .github#55

[0;0H[JRefreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Master Gate · 33232866336
Triggered via push about 5 minutes ago

JOBS
✓ core-wheel in 18s (ID 99048616461)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Resolve pinned Rust core revision
  ✓ Restore cached core wheel
  - Check out Rust core
  - Run astral-sh/setup-uv@v4
  - Set up Rust
  - Cache Rust build
  - Build abi3 Rust core wheel
  - Build xprompt LSP
  - Record wheel provenance
  - Save core wheel cache
  ✓ Upload Rust core artifacts
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ lint in 3m21s (ID 99048656008)
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
* test (5) (ID 99048656072)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
✓ test (6) in 4m54s (ID 99048656077)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* test (7) (ID 99048656078)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (1) (ID 99048656084)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (4) (ID 99048656104)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (3) (ID 99048656107)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (8) (ID 99048656108)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (2) (ID 99048656132)
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

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache@v4, actions/checkout@v4, actions/download-artifact@v4, actions/setup-go@v5, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
lint: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0ylqSagAAAADMk2TYDgMuT70dSAJGbLexUEhYMzFFREdFMDUxMQBFZGdl
lint: .github#10

! Failed to restore: Cache service responded with 400
lint: .github#55

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
test (6): .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0KFuSagAAAAA5gQ57c4RXSaFbjrJnnjtbUEhMMzBFREdFMDQxNgBFZGdl
test (6): .github#10

! Failed to restore: Cache service responded with 400
test (6): .github#55

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
test (2): .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0OVuSagAAAACkvAwwq+yaSZwsFZi19CEuQ0gxQUEyMDMwODEzMDU0AEVkZ2U=
test (2): .github#10

! Failed to restore: Cache service responded with 400
test (2): .github#55

[0;0H[JRefreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Master Gate · 33232866336
Triggered via push about 5 minutes ago

JOBS
✓ core-wheel in 18s (ID 99048616461)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Resolve pinned Rust core revision
  ✓ Restore cached core wheel
  - Check out Rust core
  - Run astral-sh/setup-uv@v4
  - Set up Rust
  - Cache Rust build
  - Build abi3 Rust core wheel
  - Build xprompt LSP
  - Record wheel provenance
  - Save core wheel cache
  ✓ Upload Rust core artifacts
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ lint in 3m21s (ID 99048656008)
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
* test (5) (ID 99048656072)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
✓ test (6) in 4m54s (ID 99048656077)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* test (7) (ID 99048656078)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (1) (ID 99048656084)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (4) (ID 99048656104)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (3) (ID 99048656107)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (8) (ID 99048656108)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
✓ test (2) in 5m11s (ID 99048656132)
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

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache@v4, actions/checkout@v4, actions/download-artifact@v4, actions/setup-go@v5, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
lint: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0ylqSagAAAADMk2TYDgMuT70dSAJGbLexUEhYMzFFREdFMDUxMQBFZGdl
lint: .github#10

! Failed to restore: Cache service responded with 400
lint: .github#55

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
test (6): .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0KFuSagAAAAA5gQ57c4RXSaFbjrJnnjtbUEhMMzBFREdFMDQxNgBFZGdl
test (6): .github#10

! Failed to restore: Cache service responded with 400
test (6): .github#55

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
test (2): .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0OVuSagAAAACkvAwwq+yaSZwsFZi19CEuQ0gxQUEyMDMwODEzMDU0AEVkZ2U=
test (2): .github#10

! Failed to restore: Cache service responded with 400
test (2): .github#55

[0;0H[JRefreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Master Gate · 33232866336
Triggered via push about 5 minutes ago

JOBS
✓ core-wheel in 18s (ID 99048616461)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Resolve pinned Rust core revision
  ✓ Restore cached core wheel
  - Check out Rust core
  - Run astral-sh/setup-uv@v4
  - Set up Rust
  - Cache Rust build
  - Build abi3 Rust core wheel
  - Build xprompt LSP
  - Record wheel provenance
  - Save core wheel cache
  ✓ Upload Rust core artifacts
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ lint in 3m21s (ID 99048656008)
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
* test (5) (ID 99048656072)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
✓ test (6) in 4m54s (ID 99048656077)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* test (7) (ID 99048656078)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* test (1) (ID 99048656084)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (4) (ID 99048656104)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (3) (ID 99048656107)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (8) (ID 99048656108)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
✓ test (2) in 5m11s (ID 99048656132)
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

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache@v4, actions/checkout@v4, actions/download-artifact@v4, actions/setup-go@v5, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
lint: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0ylqSagAAAADMk2TYDgMuT70dSAJGbLexUEhYMzFFREdFMDUxMQBFZGdl
lint: .github#10

! Failed to restore: Cache service responded with 400
lint: .github#55

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
test (6): .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0KFuSagAAAAA5gQ57c4RXSaFbjrJnnjtbUEhMMzBFREdFMDQxNgBFZGdl
test (6): .github#10

! Failed to restore: Cache service responded with 400
test (6): .github#55

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
test (2): .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0OVuSagAAAACkvAwwq+yaSZwsFZi19CEuQ0gxQUEyMDMwODEzMDU0AEVkZ2U=
test (2): .github#10

! Failed to restore: Cache service responded with 400
test (2): .github#55

[0;0H[JRefreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Master Gate · 33232866336
Triggered via push about 5 minutes ago

JOBS
✓ core-wheel in 18s (ID 99048616461)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Resolve pinned Rust core revision
  ✓ Restore cached core wheel
  - Check out Rust core
  - Run astral-sh/setup-uv@v4
  - Set up Rust
  - Cache Rust build
  - Build abi3 Rust core wheel
  - Build xprompt LSP
  - Record wheel provenance
  - Save core wheel cache
  ✓ Upload Rust core artifacts
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ lint in 3m21s (ID 99048656008)
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
* test (5) (ID 99048656072)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
✓ test (6) in 4m54s (ID 99048656077)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ test (7) in 5m21s (ID 99048656078)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* test (1) (ID 99048656084)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (4) (ID 99048656104)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (3) (ID 99048656107)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (8) (ID 99048656108)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
✓ test (2) in 5m11s (ID 99048656132)
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

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache@v4, actions/checkout@v4, actions/download-artifact@v4, actions/setup-go@v5, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
lint: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0ylqSagAAAADMk2TYDgMuT70dSAJGbLexUEhYMzFFREdFMDUxMQBFZGdl
lint: .github#10

! Failed to restore: Cache service responded with 400
lint: .github#55

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
test (6): .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0KFuSagAAAAA5gQ57c4RXSaFbjrJnnjtbUEhMMzBFREdFMDQxNgBFZGdl
test (6): .github#10

! Failed to restore: Cache service responded with 400
test (6): .github#55

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
test (2): .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0OVuSagAAAACkvAwwq+yaSZwsFZi19CEuQ0gxQUEyMDMwODEzMDU0AEVkZ2U=
test (2): .github#10

! Failed to restore: Cache service responded with 400
test (2): .github#55

[0;0H[JRefreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Master Gate · 33232866336
Triggered via push about 5 minutes ago

JOBS
✓ core-wheel in 18s (ID 99048616461)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Resolve pinned Rust core revision
  ✓ Restore cached core wheel
  - Check out Rust core
  - Run astral-sh/setup-uv@v4
  - Set up Rust
  - Cache Rust build
  - Build abi3 Rust core wheel
  - Build xprompt LSP
  - Record wheel provenance
  - Save core wheel cache
  ✓ Upload Rust core artifacts
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ lint in 3m21s (ID 99048656008)
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
✓ test (5) in 5m27s (ID 99048656072)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ test (6) in 4m54s (ID 99048656077)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ test (7) in 5m21s (ID 99048656078)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* test (1) (ID 99048656084)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (4) (ID 99048656104)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (3) (ID 99048656107)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (8) (ID 99048656108)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
✓ test (2) in 5m11s (ID 99048656132)
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

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache@v4, actions/checkout@v4, actions/download-artifact@v4, actions/setup-go@v5, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
lint: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0ylqSagAAAADMk2TYDgMuT70dSAJGbLexUEhYMzFFREdFMDUxMQBFZGdl
lint: .github#10

! Failed to restore: Cache service responded with 400
lint: .github#55

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
test (6): .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0KFuSagAAAAA5gQ57c4RXSaFbjrJnnjtbUEhMMzBFREdFMDQxNgBFZGdl
test (6): .github#10

! Failed to restore: Cache service responded with 400
test (6): .github#55

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
test (2): .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0OVuSagAAAACkvAwwq+yaSZwsFZi19CEuQ0gxQUEyMDMwODEzMDU0AEVkZ2U=
test (2): .github#10

! Failed to restore: Cache service responded with 400
test (2): .github#55

[0;0H[JRefreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Master Gate · 33232866336
Triggered via push about 5 minutes ago

JOBS
✓ core-wheel in 18s (ID 99048616461)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Resolve pinned Rust core revision
  ✓ Restore cached core wheel
  - Check out Rust core
  - Run astral-sh/setup-uv@v4
  - Set up Rust
  - Cache Rust build
  - Build abi3 Rust core wheel
  - Build xprompt LSP
  - Record wheel provenance
  - Save core wheel cache
  ✓ Upload Rust core artifacts
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ lint in 3m21s (ID 99048656008)
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
✓ test (5) in 5m27s (ID 99048656072)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ test (6) in 4m54s (ID 99048656077)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ test (7) in 5m21s (ID 99048656078)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* test (1) (ID 99048656084)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* test (4) (ID 99048656104)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (3) (ID 99048656107)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (8) (ID 99048656108)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
✓ test (2) in 5m11s (ID 99048656132)
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

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache@v4, actions/checkout@v4, actions/download-artifact@v4, actions/setup-go@v5, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
lint: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0ylqSagAAAADMk2TYDgMuT70dSAJGbLexUEhYMzFFREdFMDUxMQBFZGdl
lint: .github#10

! Failed to restore: Cache service responded with 400
lint: .github#55

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
test (6): .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0KFuSagAAAAA5gQ57c4RXSaFbjrJnnjtbUEhMMzBFREdFMDQxNgBFZGdl
test (6): .github#10

! Failed to restore: Cache service responded with 400
test (6): .github#55

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
test (2): .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0OVuSagAAAACkvAwwq+yaSZwsFZi19CEuQ0gxQUEyMDMwODEzMDU0AEVkZ2U=
test (2): .github#10

! Failed to restore: Cache service responded with 400
test (2): .github#55

[0;0H[JRefreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Master Gate · 33232866336
Triggered via push about 6 minutes ago

JOBS
✓ core-wheel in 18s (ID 99048616461)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Resolve pinned Rust core revision
  ✓ Restore cached core wheel
  - Check out Rust core
  - Run astral-sh/setup-uv@v4
  - Set up Rust
  - Cache Rust build
  - Build abi3 Rust core wheel
  - Build xprompt LSP
  - Record wheel provenance
  - Save core wheel cache
  ✓ Upload Rust core artifacts
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ lint in 3m21s (ID 99048656008)
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
✓ test (5) in 5m27s (ID 99048656072)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ test (6) in 4m54s (ID 99048656077)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ test (7) in 5m21s (ID 99048656078)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ test (1) in 5m34s (ID 99048656084)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* test (4) (ID 99048656104)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (3) (ID 99048656107)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (8) (ID 99048656108)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
✓ test (2) in 5m11s (ID 99048656132)
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

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache@v4, actions/checkout@v4, actions/download-artifact@v4, actions/setup-go@v5, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
lint: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0ylqSagAAAADMk2TYDgMuT70dSAJGbLexUEhYMzFFREdFMDUxMQBFZGdl
lint: .github#10

! Failed to restore: Cache service responded with 400
lint: .github#55

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
test (6): .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0KFuSagAAAAA5gQ57c4RXSaFbjrJnnjtbUEhMMzBFREdFMDQxNgBFZGdl
test (6): .github#10

! Failed to restore: Cache service responded with 400
test (6): .github#55

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
test (2): .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0OVuSagAAAACkvAwwq+yaSZwsFZi19CEuQ0gxQUEyMDMwODEzMDU0AEVkZ2U=
test (2): .github#10

! Failed to restore: Cache service responded with 400
test (2): .github#55

[0;0H[JRefreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Master Gate · 33232866336
Triggered via push about 6 minutes ago

JOBS
✓ core-wheel in 18s (ID 99048616461)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Resolve pinned Rust core revision
  ✓ Restore cached core wheel
  - Check out Rust core
  - Run astral-sh/setup-uv@v4
  - Set up Rust
  - Cache Rust build
  - Build abi3 Rust core wheel
  - Build xprompt LSP
  - Record wheel provenance
  - Save core wheel cache
  ✓ Upload Rust core artifacts
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ lint in 3m21s (ID 99048656008)
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
✓ test (5) in 5m27s (ID 99048656072)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ test (6) in 4m54s (ID 99048656077)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ test (7) in 5m21s (ID 99048656078)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ test (1) in 5m34s (ID 99048656084)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* test (4) (ID 99048656104)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (3) (ID 99048656107)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (8) (ID 99048656108)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
✓ test (2) in 5m11s (ID 99048656132)
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

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache@v4, actions/checkout@v4, actions/download-artifact@v4, actions/setup-go@v5, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
lint: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0ylqSagAAAADMk2TYDgMuT70dSAJGbLexUEhYMzFFREdFMDUxMQBFZGdl
lint: .github#10

! Failed to restore: Cache service responded with 400
lint: .github#55

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
test (6): .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0KFuSagAAAAA5gQ57c4RXSaFbjrJnnjtbUEhMMzBFREdFMDQxNgBFZGdl
test (6): .github#10

! Failed to restore: Cache service responded with 400
test (6): .github#55

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
test (2): .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0OVuSagAAAACkvAwwq+yaSZwsFZi19CEuQ0gxQUEyMDMwODEzMDU0AEVkZ2U=
test (2): .github#10

! Failed to restore: Cache service responded with 400
test (2): .github#55

[0;0H[JRefreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Master Gate · 33232866336
Triggered via push about 6 minutes ago

JOBS
✓ core-wheel in 18s (ID 99048616461)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Resolve pinned Rust core revision
  ✓ Restore cached core wheel
  - Check out Rust core
  - Run astral-sh/setup-uv@v4
  - Set up Rust
  - Cache Rust build
  - Build abi3 Rust core wheel
  - Build xprompt LSP
  - Record wheel provenance
  - Save core wheel cache
  ✓ Upload Rust core artifacts
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ lint in 3m21s (ID 99048656008)
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
✓ test (5) in 5m27s (ID 99048656072)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ test (6) in 4m54s (ID 99048656077)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ test (7) in 5m21s (ID 99048656078)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ test (1) in 5m34s (ID 99048656084)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* test (4) (ID 99048656104)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (3) (ID 99048656107)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (8) (ID 99048656108)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ test (2) in 5m11s (ID 99048656132)
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

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache@v4, actions/checkout@v4, actions/download-artifact@v4, actions/setup-go@v5, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
lint: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0ylqSagAAAADMk2TYDgMuT70dSAJGbLexUEhYMzFFREdFMDUxMQBFZGdl
lint: .github#10

! Failed to restore: Cache service responded with 400
lint: .github#55

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
test (6): .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0KFuSagAAAAA5gQ57c4RXSaFbjrJnnjtbUEhMMzBFREdFMDQxNgBFZGdl
test (6): .github#10

! Failed to restore: Cache service responded with 400
test (6): .github#55

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
test (2): .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0OVuSagAAAACkvAwwq+yaSZwsFZi19CEuQ0gxQUEyMDMwODEzMDU0AEVkZ2U=
test (2): .github#10

! Failed to restore: Cache service responded with 400
test (2): .github#55

[0;0H[JRefreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Master Gate · 33232866336
Triggered via push about 6 minutes ago

JOBS
✓ core-wheel in 18s (ID 99048616461)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Resolve pinned Rust core revision
  ✓ Restore cached core wheel
  - Check out Rust core
  - Run astral-sh/setup-uv@v4
  - Set up Rust
  - Cache Rust build
  - Build abi3 Rust core wheel
  - Build xprompt LSP
  - Record wheel provenance
  - Save core wheel cache
  ✓ Upload Rust core artifacts
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ lint in 3m21s (ID 99048656008)
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
✓ test (5) in 5m27s (ID 99048656072)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ test (6) in 4m54s (ID 99048656077)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ test (7) in 5m21s (ID 99048656078)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ test (1) in 5m34s (ID 99048656084)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* test (4) (ID 99048656104)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (3) (ID 99048656107)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
✓ test (8) in 5m47s (ID 99048656108)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ test (2) in 5m11s (ID 99048656132)
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

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache@v4, actions/checkout@v4, actions/download-artifact@v4, actions/setup-go@v5, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
lint: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0ylqSagAAAADMk2TYDgMuT70dSAJGbLexUEhYMzFFREdFMDUxMQBFZGdl
lint: .github#10

! Failed to restore: Cache service responded with 400
lint: .github#55

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
test (6): .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0KFuSagAAAAA5gQ57c4RXSaFbjrJnnjtbUEhMMzBFREdFMDQxNgBFZGdl
test (6): .github#10

! Failed to restore: Cache service responded with 400
test (6): .github#55

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
test (2): .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0OVuSagAAAACkvAwwq+yaSZwsFZi19CEuQ0gxQUEyMDMwODEzMDU0AEVkZ2U=
test (2): .github#10

! Failed to restore: Cache service responded with 400
test (2): .github#55

[0;0H[JRefreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Master Gate · 33232866336
Triggered via push about 6 minutes ago

JOBS
✓ core-wheel in 18s (ID 99048616461)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Resolve pinned Rust core revision
  ✓ Restore cached core wheel
  - Check out Rust core
  - Run astral-sh/setup-uv@v4
  - Set up Rust
  - Cache Rust build
  - Build abi3 Rust core wheel
  - Build xprompt LSP
  - Record wheel provenance
  - Save core wheel cache
  ✓ Upload Rust core artifacts
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ lint in 3m21s (ID 99048656008)
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
✓ test (5) in 5m27s (ID 99048656072)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ test (6) in 4m54s (ID 99048656077)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ test (7) in 5m21s (ID 99048656078)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ test (1) in 5m34s (ID 99048656084)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* test (4) (ID 99048656104)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (3) (ID 99048656107)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
✓ test (8) in 5m47s (ID 99048656108)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ test (2) in 5m11s (ID 99048656132)
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

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache@v4, actions/checkout@v4, actions/download-artifact@v4, actions/setup-go@v5, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
lint: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0ylqSagAAAADMk2TYDgMuT70dSAJGbLexUEhYMzFFREdFMDUxMQBFZGdl
lint: .github#10

! Failed to restore: Cache service responded with 400
lint: .github#55

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
test (6): .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0KFuSagAAAAA5gQ57c4RXSaFbjrJnnjtbUEhMMzBFREdFMDQxNgBFZGdl
test (6): .github#10

! Failed to restore: Cache service responded with 400
test (6): .github#55

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
test (2): .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0OVuSagAAAACkvAwwq+yaSZwsFZi19CEuQ0gxQUEyMDMwODEzMDU0AEVkZ2U=
test (2): .github#10

! Failed to restore: Cache service responded with 400
test (2): .github#55

[0;0H[JRefreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Master Gate · 33232866336
Triggered via push about 6 minutes ago

JOBS
✓ core-wheel in 18s (ID 99048616461)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Resolve pinned Rust core revision
  ✓ Restore cached core wheel
  - Check out Rust core
  - Run astral-sh/setup-uv@v4
  - Set up Rust
  - Cache Rust build
  - Build abi3 Rust core wheel
  - Build xprompt LSP
  - Record wheel provenance
  - Save core wheel cache
  ✓ Upload Rust core artifacts
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ lint in 3m21s (ID 99048656008)
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
✓ test (5) in 5m27s (ID 99048656072)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ test (6) in 4m54s (ID 99048656077)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ test (7) in 5m21s (ID 99048656078)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ test (1) in 5m34s (ID 99048656084)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* test (4) (ID 99048656104)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (3) (ID 99048656107)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
✓ test (8) in 5m47s (ID 99048656108)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ test (2) in 5m11s (ID 99048656132)
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

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache@v4, actions/checkout@v4, actions/download-artifact@v4, actions/setup-go@v5, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
lint: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0ylqSagAAAADMk2TYDgMuT70dSAJGbLexUEhYMzFFREdFMDUxMQBFZGdl
lint: .github#10

! Failed to restore: Cache service responded with 400
lint: .github#55

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
test (6): .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0KFuSagAAAAA5gQ57c4RXSaFbjrJnnjtbUEhMMzBFREdFMDQxNgBFZGdl
test (6): .github#10

! Failed to restore: Cache service responded with 400
test (6): .github#55

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
test (2): .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0OVuSagAAAACkvAwwq+yaSZwsFZi19CEuQ0gxQUEyMDMwODEzMDU0AEVkZ2U=
test (2): .github#10

! Failed to restore: Cache service responded with 400
test (2): .github#55

[0;0H[JRefreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Master Gate · 33232866336
Triggered via push about 6 minutes ago

JOBS
✓ core-wheel in 18s (ID 99048616461)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Resolve pinned Rust core revision
  ✓ Restore cached core wheel
  - Check out Rust core
  - Run astral-sh/setup-uv@v4
  - Set up Rust
  - Cache Rust build
  - Build abi3 Rust core wheel
  - Build xprompt LSP
  - Record wheel provenance
  - Save core wheel cache
  ✓ Upload Rust core artifacts
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ lint in 3m21s (ID 99048656008)
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
✓ test (5) in 5m27s (ID 99048656072)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ test (6) in 4m54s (ID 99048656077)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ test (7) in 5m21s (ID 99048656078)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ test (1) in 5m34s (ID 99048656084)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* test (4) (ID 99048656104)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (3) (ID 99048656107)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
✓ test (8) in 5m47s (ID 99048656108)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ test (2) in 5m11s (ID 99048656132)
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

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache@v4, actions/checkout@v4, actions/download-artifact@v4, actions/setup-go@v5, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
lint: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0ylqSagAAAADMk2TYDgMuT70dSAJGbLexUEhYMzFFREdFMDUxMQBFZGdl
lint: .github#10

! Failed to restore: Cache service responded with 400
lint: .github#55

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
test (6): .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0KFuSagAAAAA5gQ57c4RXSaFbjrJnnjtbUEhMMzBFREdFMDQxNgBFZGdl
test (6): .github#10

! Failed to restore: Cache service responded with 400
test (6): .github#55

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
test (2): .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0OVuSagAAAACkvAwwq+yaSZwsFZi19CEuQ0gxQUEyMDMwODEzMDU0AEVkZ2U=
test (2): .github#10

! Failed to restore: Cache service responded with 400
test (2): .github#55

[0;0H[JRefreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Master Gate · 33232866336
Triggered via push about 6 minutes ago

JOBS
✓ core-wheel in 18s (ID 99048616461)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Resolve pinned Rust core revision
  ✓ Restore cached core wheel
  - Check out Rust core
  - Run astral-sh/setup-uv@v4
  - Set up Rust
  - Cache Rust build
  - Build abi3 Rust core wheel
  - Build xprompt LSP
  - Record wheel provenance
  - Save core wheel cache
  ✓ Upload Rust core artifacts
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ lint in 3m21s (ID 99048656008)
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
✓ test (5) in 5m27s (ID 99048656072)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ test (6) in 4m54s (ID 99048656077)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ test (7) in 5m21s (ID 99048656078)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ test (1) in 5m34s (ID 99048656084)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* test (4) (ID 99048656104)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (3) (ID 99048656107)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
✓ test (8) in 5m47s (ID 99048656108)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ test (2) in 5m11s (ID 99048656132)
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

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache@v4, actions/checkout@v4, actions/download-artifact@v4, actions/setup-go@v5, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
lint: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0ylqSagAAAADMk2TYDgMuT70dSAJGbLexUEhYMzFFREdFMDUxMQBFZGdl
lint: .github#10

! Failed to restore: Cache service responded with 400
lint: .github#55

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
test (6): .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0KFuSagAAAAA5gQ57c4RXSaFbjrJnnjtbUEhMMzBFREdFMDQxNgBFZGdl
test (6): .github#10

! Failed to restore: Cache service responded with 400
test (6): .github#55

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
test (2): .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0OVuSagAAAACkvAwwq+yaSZwsFZi19CEuQ0gxQUEyMDMwODEzMDU0AEVkZ2U=
test (2): .github#10

! Failed to restore: Cache service responded with 400
test (2): .github#55

[0;0H[JRefreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Master Gate · 33232866336
Triggered via push about 6 minutes ago

JOBS
✓ core-wheel in 18s (ID 99048616461)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Resolve pinned Rust core revision
  ✓ Restore cached core wheel
  - Check out Rust core
  - Run astral-sh/setup-uv@v4
  - Set up Rust
  - Cache Rust build
  - Build abi3 Rust core wheel
  - Build xprompt LSP
  - Record wheel provenance
  - Save core wheel cache
  ✓ Upload Rust core artifacts
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ lint in 3m21s (ID 99048656008)
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
✓ test (5) in 5m27s (ID 99048656072)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ test (6) in 4m54s (ID 99048656077)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ test (7) in 5m21s (ID 99048656078)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ test (1) in 5m34s (ID 99048656084)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* test (4) (ID 99048656104)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (3) (ID 99048656107)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
✓ test (8) in 5m47s (ID 99048656108)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ test (2) in 5m11s (ID 99048656132)
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

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache@v4, actions/checkout@v4, actions/download-artifact@v4, actions/setup-go@v5, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
lint: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0ylqSagAAAADMk2TYDgMuT70dSAJGbLexUEhYMzFFREdFMDUxMQBFZGdl
lint: .github#10

! Failed to restore: Cache service responded with 400
lint: .github#55

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
test (6): .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0KFuSagAAAAA5gQ57c4RXSaFbjrJnnjtbUEhMMzBFREdFMDQxNgBFZGdl
test (6): .github#10

! Failed to restore: Cache service responded with 400
test (6): .github#55

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
test (2): .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0OVuSagAAAACkvAwwq+yaSZwsFZi19CEuQ0gxQUEyMDMwODEzMDU0AEVkZ2U=
test (2): .github#10

! Failed to restore: Cache service responded with 400
test (2): .github#55

[0;0H[JRefreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Master Gate · 33232866336
Triggered via push about 6 minutes ago

JOBS
✓ core-wheel in 18s (ID 99048616461)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Resolve pinned Rust core revision
  ✓ Restore cached core wheel
  - Check out Rust core
  - Run astral-sh/setup-uv@v4
  - Set up Rust
  - Cache Rust build
  - Build abi3 Rust core wheel
  - Build xprompt LSP
  - Record wheel provenance
  - Save core wheel cache
  ✓ Upload Rust core artifacts
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ lint in 3m21s (ID 99048656008)
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
✓ test (5) in 5m27s (ID 99048656072)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ test (6) in 4m54s (ID 99048656077)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ test (7) in 5m21s (ID 99048656078)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ test (1) in 5m34s (ID 99048656084)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* test (4) (ID 99048656104)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (3) (ID 99048656107)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
✓ test (8) in 5m47s (ID 99048656108)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ test (2) in 5m11s (ID 99048656132)
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

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache@v4, actions/checkout@v4, actions/download-artifact@v4, actions/setup-go@v5, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
lint: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0ylqSagAAAADMk2TYDgMuT70dSAJGbLexUEhYMzFFREdFMDUxMQBFZGdl
lint: .github#10

! Failed to restore: Cache service responded with 400
lint: .github#55

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
test (6): .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0KFuSagAAAAA5gQ57c4RXSaFbjrJnnjtbUEhMMzBFREdFMDQxNgBFZGdl
test (6): .github#10

! Failed to restore: Cache service responded with 400
test (6): .github#55

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
test (2): .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0OVuSagAAAACkvAwwq+yaSZwsFZi19CEuQ0gxQUEyMDMwODEzMDU0AEVkZ2U=
test (2): .github#10

! Failed to restore: Cache service responded with 400
test (2): .github#55

[0;0H[JRefreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Master Gate · 33232866336
Triggered via push about 6 minutes ago

JOBS
✓ core-wheel in 18s (ID 99048616461)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Resolve pinned Rust core revision
  ✓ Restore cached core wheel
  - Check out Rust core
  - Run astral-sh/setup-uv@v4
  - Set up Rust
  - Cache Rust build
  - Build abi3 Rust core wheel
  - Build xprompt LSP
  - Record wheel provenance
  - Save core wheel cache
  ✓ Upload Rust core artifacts
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ lint in 3m21s (ID 99048656008)
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
✓ test (5) in 5m27s (ID 99048656072)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ test (6) in 4m54s (ID 99048656077)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ test (7) in 5m21s (ID 99048656078)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ test (1) in 5m34s (ID 99048656084)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* test (4) (ID 99048656104)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (3) (ID 99048656107)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
✓ test (8) in 5m47s (ID 99048656108)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ test (2) in 5m11s (ID 99048656132)
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

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache@v4, actions/checkout@v4, actions/download-artifact@v4, actions/setup-go@v5, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
lint: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0ylqSagAAAADMk2TYDgMuT70dSAJGbLexUEhYMzFFREdFMDUxMQBFZGdl
lint: .github#10

! Failed to restore: Cache service responded with 400
lint: .github#55

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
test (6): .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0KFuSagAAAAA5gQ57c4RXSaFbjrJnnjtbUEhMMzBFREdFMDQxNgBFZGdl
test (6): .github#10

! Failed to restore: Cache service responded with 400
test (6): .github#55

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
test (2): .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0OVuSagAAAACkvAwwq+yaSZwsFZi19CEuQ0gxQUEyMDMwODEzMDU0AEVkZ2U=
test (2): .github#10

! Failed to restore: Cache service responded with 400
test (2): .github#55

[0;0H[JRefreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Master Gate · 33232866336
Triggered via push about 6 minutes ago

JOBS
✓ core-wheel in 18s (ID 99048616461)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Resolve pinned Rust core revision
  ✓ Restore cached core wheel
  - Check out Rust core
  - Run astral-sh/setup-uv@v4
  - Set up Rust
  - Cache Rust build
  - Build abi3 Rust core wheel
  - Build xprompt LSP
  - Record wheel provenance
  - Save core wheel cache
  ✓ Upload Rust core artifacts
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ lint in 3m21s (ID 99048656008)
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
✓ test (5) in 5m27s (ID 99048656072)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ test (6) in 4m54s (ID 99048656077)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ test (7) in 5m21s (ID 99048656078)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ test (1) in 5m34s (ID 99048656084)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* test (4) (ID 99048656104)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
* test (3) (ID 99048656107)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
✓ test (8) in 5m47s (ID 99048656108)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ test (2) in 5m11s (ID 99048656132)
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

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache@v4, actions/checkout@v4, actions/download-artifact@v4, actions/setup-go@v5, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
lint: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0ylqSagAAAADMk2TYDgMuT70dSAJGbLexUEhYMzFFREdFMDUxMQBFZGdl
lint: .github#10

! Failed to restore: Cache service responded with 400
lint: .github#55

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
test (6): .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0KFuSagAAAAA5gQ57c4RXSaFbjrJnnjtbUEhMMzBFREdFMDQxNgBFZGdl
test (6): .github#10

! Failed to restore: Cache service responded with 400
test (6): .github#55

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
test (2): .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0OVuSagAAAACkvAwwq+yaSZwsFZi19CEuQ0gxQUEyMDMwODEzMDU0AEVkZ2U=
test (2): .github#10

! Failed to restore: Cache service responded with 400
test (2): .github#55

[0;0H[JRefreshing run status every 3 seconds. Press Ctrl+C to quit.

* master Master Gate · 33232866336
Triggered via push about 6 minutes ago

JOBS
✓ core-wheel in 18s (ID 99048616461)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Resolve pinned Rust core revision
  ✓ Restore cached core wheel
  - Check out Rust core
  - Run astral-sh/setup-uv@v4
  - Set up Rust
  - Cache Rust build
  - Build abi3 Rust core wheel
  - Build xprompt LSP
  - Record wheel provenance
  - Save core wheel cache
  ✓ Upload Rust core artifacts
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ lint in 3m21s (ID 99048656008)
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
✓ test (5) in 5m27s (ID 99048656072)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ test (6) in 4m54s (ID 99048656077)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ test (7) in 5m21s (ID 99048656078)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ test (1) in 5m34s (ID 99048656084)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* test (4) (ID 99048656104)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
* test (3) (ID 99048656107)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  * Run sharded fast suite
  * Post Install dependencies
  * Post Run actions/checkout@v4
✓ test (8) in 5m47s (ID 99048656108)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ test (2) in 5m11s (ID 99048656132)
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

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache@v4, actions/checkout@v4, actions/download-artifact@v4, actions/setup-go@v5, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
lint: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0ylqSagAAAADMk2TYDgMuT70dSAJGbLexUEhYMzFFREdFMDUxMQBFZGdl
lint: .github#10

! Failed to restore: Cache service responded with 400
lint: .github#55

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
test (6): .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0KFuSagAAAAA5gQ57c4RXSaFbjrJnnjtbUEhMMzBFREdFMDQxNgBFZGdl
test (6): .github#10

! Failed to restore: Cache service responded with 400
test (6): .github#55

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
test (2): .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0OVuSagAAAACkvAwwq+yaSZwsFZi19CEuQ0gxQUEyMDMwODEzMDU0AEVkZ2U=
test (2): .github#10

! Failed to restore: Cache service responded with 400
test (2): .github#55

[?1049l✓ master Master Gate · 33232866336
Triggered via push about 6 minutes ago

JOBS
✓ core-wheel in 18s (ID 99048616461)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Resolve pinned Rust core revision
  ✓ Restore cached core wheel
  - Check out Rust core
  - Run astral-sh/setup-uv@v4
  - Set up Rust
  - Cache Rust build
  - Build abi3 Rust core wheel
  - Build xprompt LSP
  - Record wheel provenance
  - Save core wheel cache
  ✓ Upload Rust core artifacts
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ lint in 3m21s (ID 99048656008)
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
✓ test (5) in 5m27s (ID 99048656072)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ test (6) in 4m54s (ID 99048656077)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ test (7) in 5m21s (ID 99048656078)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ test (1) in 5m34s (ID 99048656084)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ test (4) in 6m28s (ID 99048656104)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ test (3) in 6m30s (ID 99048656107)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ test (8) in 5m47s (ID 99048656108)
  ✓ Set up job
  ✓ Run actions/checkout@v4
  ✓ Install dependencies
  ✓ Run sharded fast suite
  ✓ Post Install dependencies
  ✓ Post Run actions/checkout@v4
  ✓ Complete job
✓ test (2) in 5m11s (ID 99048656132)
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

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/cache@v4, actions/checkout@v4, actions/download-artifact@v4, actions/setup-go@v5, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
lint: .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0ylqSagAAAADMk2TYDgMuT70dSAJGbLexUEhYMzFFREdFMDUxMQBFZGdl
lint: .github#10

! Failed to restore: Cache service responded with 400
lint: .github#55

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
test (6): .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0KFuSagAAAAA5gQ57c4RXSaFbjrJnnjtbUEhMMzBFREdFMDQxNgBFZGdl
test (6): .github#10

! Failed to restore: Cache service responded with 400
test (6): .github#55

! Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
test (2): .github#2

! Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0OVuSagAAAACkvAwwq+yaSZwsFZi19CEuQ0gxQUEyMDMwODEzMDU0AEVkZ2U=
test (2): .github#10

! Failed to restore: Cache service responded with 400
test (2): .github#55


✓ Run Master Gate (33232866336) completed with 'success'

---

%xprompts_enabled:true
# New Query
%model:grok-4.6
%effort:xhigh

%xprompts_enabled:false
# Monitored command finished

**Command:**

```text
GH_FORCE_TTY=0 NO_COLOR=1 CLICOLOR=0 gh run watch 33232866336 --repo sase-org/sase --exit-status
```

**Directory:**

```text
/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19
```

| | |
| --- | --- |
| **Outcome** | COMPLETED — exit 0 |
| **Started** | 2026-08-29T04:07:06.252983+00:00 |
| **Finished** | 2026-08-29T04:09:49.339719+00:00 |
| **Elapsed** | 2m 42s of a 45m 0s budget |
| **Output** | 168 KiB · full log: `sase monitor show b077fkzk4g9p --all-lines` |

**Why this was monitored:** Wait for Master Gate 33232866336 on 49d6c4188 so ci_watch can leave gating_workflow_in_flight

## Your next action

Continue bead sase-um.9.5.4 (ship). You are the same phase worker. Do NOT close parent sase-um.9.5 or any ancestor. Do NOT create beads; use PROPOSED FOLLOW-UP notes on sase-um.9.5.4. Do NOT hand-merge PR #284. Do NOT set status by hand. If this bead is closed, immediately run `sase bead open sase-um.9.5.4` — 9.5.5 is WAITING on it and v0.17.0 is unpublished. Mid-flight commits MUST use `sase_git_commit -B` (sase_final stitch auto-closes and would launch 9.5.5).

State already done: chopcolor 36c925f installed in live uv-tool env (ci_watch.py SHA256 matches repo HEAD). Chezmoi per-repo mapping is live (sase=merge+Master Gate+Full CI/6h; plugins=squash+empty allowlists). Dry-run `sase axe chop run ci_watch -n -V` parsed JSON with errors=0. Plugin GitHub settings confirmed. Tab-strip CI failure on 623788895 is fixed on origin/master e856c6804. Master Gate 33232113220 on e856c6804 went red solely on test(7) job 99046660131: tests/agents_sync/test_cross_machine_e2e.py::test_three_identities_converge_and_localize_through_non_fast_forward_race git-cloned the local bare remote into verify and got exit 128 after all identity/sync assertions passed (helper hid stderr). Local 5/5 PASS. Hardened that helper and landed 49d6c4188 with stitch -B (just check green, scoped). PROPOSED FOLLOW-UP already recorded for git_sync_fixtures.py and production GIT_OPTIONAL_LOCKS=0.

In flight:
- Master Gate 33232866336 on 49d6c4188 (this monitor).
- Full CI 33232978442 queued on 49d6c4188 behind 33231000542 (old SHA 623788895). 33232205513 on e856c6804 was cancelled.
- publish.yml 33232979152 (publish_existing=false) refreshing PR #284.

Then:
1. If Master Gate 33232866336 is red, attribute failed nodes, fix in-scope, `just check`, land with `sase_git_commit -B`, redispatch Full CI and publish.yml (publish_existing=false), and monitor the new gate. The e2e helper now raises AssertionError with git stdout/stderr — read that if the same clone fails again. Do not mute flakes; record PROPOSED FOLLOW-UP.
2. If Master Gate is green, confirm PR #284 is MERGEABLE/CLEAN (re-dispatch publish.yml without publish_existing if it is CONFLICTING/DIRTY). Dry-run ci_watch again. Then `sase monitor start` watching Full CI 33232978442 (or the newest Full CI on the integrated tip) with timeout at least 3h. Do not inline-wait Full CI.
3. Once Full CI is green on the final integrated tip and inside the 6-hour heavy window, watch live five-minute ci_watch ticks until sase-org/sase is eligible. The live `gh pr merge --merge --match-head-commit` is the acceptance evidence. Never hand-merge.
4. After #284 merges, let publish.yml tag and publish v0.17.0. Use workflow_dispatch publish_existing only if the three-hour schedule is the sole delay. Confirm the v0.17.0 tag, GitHub publish run, and PyPI 0.17.0.
5. Record all seven parent ACs numerically on this bead, then re-check plugin squash+empty allowlists and that telegram/github are not gating_workflow_missing or heavy_lane_not_green.
6. Baseline 2026-08-29T03:18Z before the tab-strip fix: (1) 1 cancelled in last 50 — 33127407974 test(1) failed then sibling shards cancelled under fail-fast:false, not push supersession; (2) trailing-49 completed median wall 9.02 min; (3) 39/39 master commits in 24h have a gate run, 38/39 completed; (4) ci_watch reasons are gating/heavy, never default_branch_not_green, not yet eligible; (5) #284 unmerged; (6) PR ci.yml pull_request queue p50 0s over 30 runs; (7) no v0.17.0 tag, PyPI 0.16.0.
7. Before close: `sase bead epic-symbols sase-um.9.5.4` and resolve leftovers. `just check` if you changed files. Then `sase bead close sase-um.9.5.4 --note "<what you verified>"` only.
%xprompts_enabled:true

## Response

# Monitor handoff

This agent delegated the remaining work to a monitor shell.
Monitor ID: 9c1bpznhkd99
Inspect with: sase monitor show 9c1bpznhkd99
Monitor shell: sase-um.9.5.4--mon-1
Directory: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19

Command:

```sh
GH_FORCE_TTY=0 NO_COLOR=1 CLICOLOR=0 gh run watch 33232978442 --repo sase-org/sase --exit-status
```

Reason:

Wait for Full CI 33232978442 on 49d6c4188 so ci_watch can leave heavy_workflow_not_green

Next action:

Continue bead sase-um.9.5.4 (ship). You are the same phase worker. Do NOT close parent sase-um.9.5 or any ancestor. Do NOT create beads; use PROPOSED FOLLOW-UP notes on sase-um.9.5.4. Do NOT hand-merge PR #284. Do NOT set status by hand. If this bead is closed, immediately run `sase bead open sase-um.9.5.4` — 9.5.5 is WAITING on it and v0.17.0 is unpublished. Mid-flight commits MUST use `sase_git_commit -B` (sase_final stitch auto-closes and would launch 9.5.5).

State already done: chopcolor 36c925f installed in live uv-tool env (ci_watch.py SHA256 matches repo HEAD). Chezmoi per-repo mapping is live (sase=merge+Master Gate+Full CI/6h; plugins=squash+empty allowlists). Plugin GitHub settings confirmed. Tab-strip CI failure on 623788895 is fixed on origin/master. Cross-machine e2e clone helper hardened and landed 49d6c4188 with stitch -B. PROPOSED FOLLOW-UP already recorded for git_sync_fixtures.py and production GIT_OPTIONAL_LOCKS=0. Master Gate 33232866336 on 49d6c4188 is GREEN (exit 0; core-wheel, lint, test 1-8 success; cache 400s are annotations only). PR #284 OPEN MERGEABLE/CLEAN (head eaeaf47f, title chore(master): release 0.17.0). publish.yml 33232979152 succeeded (publish_existing=false). Dry-run `sase axe chop run ci_watch -n -V` errors=0: sase-org/sase green on master@49d6c4188; #284 skipped heavy workflow not green; telegram #21 merge_state_not_clean (not gating_workflow_missing); github no_release_pr.

This monitor: Full CI 33232978442 on 49d6c4188. It was pending behind obsolete Full CI 33231000542 on 623788895 (concurrency group full-ci, cancel-in-progress:false; 33231000542 already had test 3.12/3.14 and coverage-contexts failed, test 3.13 still running when watch started). 33232205513 on e856c6804 was cancelled earlier.

Then:
1. If this monitor timed out while 33232978442 is still pending or in_progress, re-issue `sase monitor start` watching the same run (or the newest Full CI on origin/master) with timeout at least 3h. Do not inline-wait Full CI.
2. If Full CI 33232978442 is red or cancelled, attribute failed nodes on the 49d6c4188 run (ignore failures on obsolete 623788895). Fix in-scope, `just check`, land with `sase_git_commit -B`, redispatch Full CI and publish.yml (publish_existing=false), confirm PR #284 is still MERGEABLE/CLEAN (re-dispatch publish.yml without publish_existing if CONFLICTING/DIRTY), and monitor the new Full CI (3h+). Do not mute flakes; record PROPOSED FOLLOW-UP.
3. If Full CI is green on 49d6c4188 (or the newest Full CI on the integrated origin/master tip), dry-run ci_watch again. If still heavy_workflow_not_green, confirm the green Full CI SHA matches origin/master. Then watch live five-minute ci_watch ticks until sase-org/sase is eligible. The live `gh pr merge --merge --match-head-commit` is the acceptance evidence. Never hand-merge. Stay inside the 6-hour heavy window.
4. After #284 merges, let publish.yml tag and publish v0.17.0. Use workflow_dispatch publish_existing only if the three-hour schedule is the sole delay. Confirm the v0.17.0 tag, GitHub publish run, and PyPI 0.17.0.
5. Record all seven parent ACs numerically on this bead, then re-check plugin squash+empty allowlists and that telegram/github are not gating_workflow_missing or heavy_lane_not_green.
6. Baseline 2026-08-29T03:18Z before the tab-strip fix: (1) 1 cancelled in last 50 — 33127407974 test(1) failed then sibling shards cancelled under fail-fast:false, not push supersession; (2) trailing-49 completed median wall 9.02 min; (3) 39/39 master commits in 24h have a gate run, 38/39 completed; (4) ci_watch reasons are gating/heavy, never default_branch_not_green, not yet eligible; (5) #284 unmerged; (6) PR ci.yml pull_request queue p50 0s over 30 runs; (7) no v0.17.0 tag, PyPI 0.16.0.
7. Before close: `sase bead epic-symbols sase-um.9.5.4` and resolve leftovers. `just check` if you changed files. Then `sase bead close sase-um.9.5.4 --note "<what you verified>"` only.

