# Chat History - ace-run (sase-pt.3--mon)

- **TIMESTAMP:** 2026-08-18 12:31:57 EDT
- **MODEL:** grok/grok-4.6
- **AGENT:** sase-pt.3--mon

## Prompt

sase monitor start --command 'gh run watch 32160158404 --exit-status -R sase-org/sase-research-artifacts' --reason 'Watch first post-merge Publish run 32160158404 (release, build, install-smoke, publish) after squash-merging PR #1 as 253aa62'

## Response

[0;1;39mRefreshing run status every 3 seconds. Press Ctrl+C to quit.[0m

[0;33m*[0m [0;1;39mmaster[0m Publish · [0;36m32160158404[0m
Triggered via push about 1 minute ago

[0;1;39mJOBS[0m
[0;32m✓[0m [0;1;39mrelease[0m in 11s (ID [0;36m95786865377[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run googleapis/release-please-action@v5
  [0;32m✓[0m Complete job
[0;32m✓[0m [0;1;39mbuild[0m in 10s (ID [0;36m95786940152[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Run astral-sh/setup-uv@v4
  [0;32m✓[0m Set up Python
  [0;32m✓[0m Build package
  [0;32m✓[0m Run actions/upload-artifact@v4
  [0;32m✓[0m Post Run astral-sh/setup-uv@v4
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[0;33m*[0m [0;1;39minstall-smoke[0m (ID [0;36m95787010707[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Run actions/download-artifact@v4
  [0;32m✓[0m Check out SASE
  [0;32m✓[0m Check out SASE Rust core
  [0;32m✓[0m Run astral-sh/setup-uv@v4
  [0;32m✓[0m Run extractions/setup-just@v2
  [0;32m✓[0m Run dtolnay/rust-toolchain@stable
  [0;32m✓[0m Set up Python
  [0;33m*[0m Install built sase-research-artifacts wheel into a fresh venv
  [0;33m*[0m Smoke check
  [0;33m*[0m Assemble the real artifact provider registry
  [0;33m*[0m Post Run astral-sh/setup-uv@v4
  [0;33m*[0m Post Check out SASE Rust core
  [0;33m*[0m Post Check out SASE
  [0;33m*[0m Post Run actions/checkout@v4

[0;1;39mANNOTATIONS[0m
[0;33m![0m Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
[38;5;242mbuild: .github#2
[0m
[0;33m![0m Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0a4eEagAAAADZtmRcHu09TbNQl71+FwrXQ08xRURHRTI1MTQARWRnZQ==
[38;5;242mbuild: .github#8
[0m
[0;33m![0m Failed to restore: Cache service responded with 400
[38;5;242mbuild: .github#26
[0m
[0;1;39mRefreshing run status every 3 seconds. Press Ctrl+C to quit.[0m

[0;33m*[0m [0;1;39mmaster[0m Publish · [0;36m32160158404[0m
Triggered via push about 1 minute ago

[0;1;39mJOBS[0m
[0;32m✓[0m [0;1;39mrelease[0m in 11s (ID [0;36m95786865377[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run googleapis/release-please-action@v5
  [0;32m✓[0m Complete job
[0;32m✓[0m [0;1;39mbuild[0m in 10s (ID [0;36m95786940152[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Run astral-sh/setup-uv@v4
  [0;32m✓[0m Set up Python
  [0;32m✓[0m Build package
  [0;32m✓[0m Run actions/upload-artifact@v4
  [0;32m✓[0m Post Run astral-sh/setup-uv@v4
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[0;33m*[0m [0;1;39minstall-smoke[0m (ID [0;36m95787010707[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Run actions/download-artifact@v4
  [0;32m✓[0m Check out SASE
  [0;32m✓[0m Check out SASE Rust core
  [0;32m✓[0m Run astral-sh/setup-uv@v4
  [0;32m✓[0m Run extractions/setup-just@v2
  [0;32m✓[0m Run dtolnay/rust-toolchain@stable
  [0;32m✓[0m Set up Python
  [0;33m*[0m Install built sase-research-artifacts wheel into a fresh venv
  [0;33m*[0m Smoke check
  [0;33m*[0m Assemble the real artifact provider registry
  [0;33m*[0m Post Run astral-sh/setup-uv@v4
  [0;33m*[0m Post Check out SASE Rust core
  [0;33m*[0m Post Check out SASE
  [0;33m*[0m Post Run actions/checkout@v4

[0;1;39mANNOTATIONS[0m
[0;33m![0m Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
[38;5;242mbuild: .github#2
[0m
[0;33m![0m Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0a4eEagAAAADZtmRcHu09TbNQl71+FwrXQ08xRURHRTI1MTQARWRnZQ==
[38;5;242mbuild: .github#8
[0m
[0;33m![0m Failed to restore: Cache service responded with 400
[38;5;242mbuild: .github#26
[0m
[0;1;39mRefreshing run status every 3 seconds. Press Ctrl+C to quit.[0m

[0;33m*[0m [0;1;39mmaster[0m Publish · [0;36m32160158404[0m
Triggered via push about 1 minute ago

[0;1;39mJOBS[0m
[0;32m✓[0m [0;1;39mrelease[0m in 11s (ID [0;36m95786865377[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run googleapis/release-please-action@v5
  [0;32m✓[0m Complete job
[0;32m✓[0m [0;1;39mbuild[0m in 10s (ID [0;36m95786940152[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Run astral-sh/setup-uv@v4
  [0;32m✓[0m Set up Python
  [0;32m✓[0m Build package
  [0;32m✓[0m Run actions/upload-artifact@v4
  [0;32m✓[0m Post Run astral-sh/setup-uv@v4
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[0;33m*[0m [0;1;39minstall-smoke[0m (ID [0;36m95787010707[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Run actions/download-artifact@v4
  [0;32m✓[0m Check out SASE
  [0;32m✓[0m Check out SASE Rust core
  [0;32m✓[0m Run astral-sh/setup-uv@v4
  [0;32m✓[0m Run extractions/setup-just@v2
  [0;32m✓[0m Run dtolnay/rust-toolchain@stable
  [0;32m✓[0m Set up Python
  [0;33m*[0m Install built sase-research-artifacts wheel into a fresh venv
  [0;33m*[0m Smoke check
  [0;33m*[0m Assemble the real artifact provider registry
  [0;33m*[0m Post Run astral-sh/setup-uv@v4
  [0;33m*[0m Post Check out SASE Rust core
  [0;33m*[0m Post Check out SASE
  [0;33m*[0m Post Run actions/checkout@v4

[0;1;39mANNOTATIONS[0m
[0;33m![0m Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
[38;5;242mbuild: .github#2
[0m
[0;33m![0m Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0a4eEagAAAADZtmRcHu09TbNQl71+FwrXQ08xRURHRTI1MTQARWRnZQ==
[38;5;242mbuild: .github#8
[0m
[0;33m![0m Failed to restore: Cache service responded with 400
[38;5;242mbuild: .github#26
[0m
[0;1;39mRefreshing run status every 3 seconds. Press Ctrl+C to quit.[0m

[0;33m*[0m [0;1;39mmaster[0m Publish · [0;36m32160158404[0m
Triggered via push about 1 minute ago

[0;1;39mJOBS[0m
[0;32m✓[0m [0;1;39mrelease[0m in 11s (ID [0;36m95786865377[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run googleapis/release-please-action@v5
  [0;32m✓[0m Complete job
[0;32m✓[0m [0;1;39mbuild[0m in 10s (ID [0;36m95786940152[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Run astral-sh/setup-uv@v4
  [0;32m✓[0m Set up Python
  [0;32m✓[0m Build package
  [0;32m✓[0m Run actions/upload-artifact@v4
  [0;32m✓[0m Post Run astral-sh/setup-uv@v4
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[0;33m*[0m [0;1;39minstall-smoke[0m (ID [0;36m95787010707[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Run actions/download-artifact@v4
  [0;32m✓[0m Check out SASE
  [0;32m✓[0m Check out SASE Rust core
  [0;32m✓[0m Run astral-sh/setup-uv@v4
  [0;32m✓[0m Run extractions/setup-just@v2
  [0;32m✓[0m Run dtolnay/rust-toolchain@stable
  [0;32m✓[0m Set up Python
  [0;33m*[0m Install built sase-research-artifacts wheel into a fresh venv
  [0;33m*[0m Smoke check
  [0;33m*[0m Assemble the real artifact provider registry
  [0;33m*[0m Post Run astral-sh/setup-uv@v4
  [0;33m*[0m Post Check out SASE Rust core
  [0;33m*[0m Post Check out SASE
  [0;33m*[0m Post Run actions/checkout@v4

[0;1;39mANNOTATIONS[0m
[0;33m![0m Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
[38;5;242mbuild: .github#2
[0m
[0;33m![0m Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0a4eEagAAAADZtmRcHu09TbNQl71+FwrXQ08xRURHRTI1MTQARWRnZQ==
[38;5;242mbuild: .github#8
[0m
[0;33m![0m Failed to restore: Cache service responded with 400
[38;5;242mbuild: .github#26
[0m
[0;1;39mRefreshing run status every 3 seconds. Press Ctrl+C to quit.[0m

[0;33m*[0m [0;1;39mmaster[0m Publish · [0;36m32160158404[0m
Triggered via push about 1 minute ago

[0;1;39mJOBS[0m
[0;32m✓[0m [0;1;39mrelease[0m in 11s (ID [0;36m95786865377[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run googleapis/release-please-action@v5
  [0;32m✓[0m Complete job
[0;32m✓[0m [0;1;39mbuild[0m in 10s (ID [0;36m95786940152[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Run astral-sh/setup-uv@v4
  [0;32m✓[0m Set up Python
  [0;32m✓[0m Build package
  [0;32m✓[0m Run actions/upload-artifact@v4
  [0;32m✓[0m Post Run astral-sh/setup-uv@v4
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[0;33m*[0m [0;1;39minstall-smoke[0m (ID [0;36m95787010707[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Run actions/download-artifact@v4
  [0;32m✓[0m Check out SASE
  [0;32m✓[0m Check out SASE Rust core
  [0;32m✓[0m Run astral-sh/setup-uv@v4
  [0;32m✓[0m Run extractions/setup-just@v2
  [0;32m✓[0m Run dtolnay/rust-toolchain@stable
  [0;32m✓[0m Set up Python
  [0;33m*[0m Install built sase-research-artifacts wheel into a fresh venv
  [0;33m*[0m Smoke check
  [0;33m*[0m Assemble the real artifact provider registry
  [0;33m*[0m Post Run astral-sh/setup-uv@v4
  [0;33m*[0m Post Check out SASE Rust core
  [0;33m*[0m Post Check out SASE
  [0;33m*[0m Post Run actions/checkout@v4

[0;1;39mANNOTATIONS[0m
[0;33m![0m Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
[38;5;242mbuild: .github#2
[0m
[0;33m![0m Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0a4eEagAAAADZtmRcHu09TbNQl71+FwrXQ08xRURHRTI1MTQARWRnZQ==
[38;5;242mbuild: .github#8
[0m
[0;33m![0m Failed to restore: Cache service responded with 400
[38;5;242mbuild: .github#26
[0m
[0;1;39mRefreshing run status every 3 seconds. Press Ctrl+C to quit.[0m

[0;33m*[0m [0;1;39mmaster[0m Publish · [0;36m32160158404[0m
Triggered via push about 1 minute ago

[0;1;39mJOBS[0m
[0;32m✓[0m [0;1;39mrelease[0m in 11s (ID [0;36m95786865377[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run googleapis/release-please-action@v5
  [0;32m✓[0m Complete job
[0;32m✓[0m [0;1;39mbuild[0m in 10s (ID [0;36m95786940152[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Run astral-sh/setup-uv@v4
  [0;32m✓[0m Set up Python
  [0;32m✓[0m Build package
  [0;32m✓[0m Run actions/upload-artifact@v4
  [0;32m✓[0m Post Run astral-sh/setup-uv@v4
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[0;33m*[0m [0;1;39minstall-smoke[0m (ID [0;36m95787010707[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Run actions/download-artifact@v4
  [0;32m✓[0m Check out SASE
  [0;32m✓[0m Check out SASE Rust core
  [0;32m✓[0m Run astral-sh/setup-uv@v4
  [0;32m✓[0m Run extractions/setup-just@v2
  [0;32m✓[0m Run dtolnay/rust-toolchain@stable
  [0;32m✓[0m Set up Python
  [0;33m*[0m Install built sase-research-artifacts wheel into a fresh venv
  [0;33m*[0m Smoke check
  [0;33m*[0m Assemble the real artifact provider registry
  [0;33m*[0m Post Run astral-sh/setup-uv@v4
  [0;33m*[0m Post Check out SASE Rust core
  [0;33m*[0m Post Check out SASE
  [0;33m*[0m Post Run actions/checkout@v4

[0;1;39mANNOTATIONS[0m
[0;33m![0m Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
[38;5;242mbuild: .github#2
[0m
[0;33m![0m Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0a4eEagAAAADZtmRcHu09TbNQl71+FwrXQ08xRURHRTI1MTQARWRnZQ==
[38;5;242mbuild: .github#8
[0m
[0;33m![0m Failed to restore: Cache service responded with 400
[38;5;242mbuild: .github#26
[0m
[0;1;39mRefreshing run status every 3 seconds. Press Ctrl+C to quit.[0m

[0;33m*[0m [0;1;39mmaster[0m Publish · [0;36m32160158404[0m
Triggered via push about 1 minute ago

[0;1;39mJOBS[0m
[0;32m✓[0m [0;1;39mrelease[0m in 11s (ID [0;36m95786865377[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run googleapis/release-please-action@v5
  [0;32m✓[0m Complete job
[0;32m✓[0m [0;1;39mbuild[0m in 10s (ID [0;36m95786940152[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Run astral-sh/setup-uv@v4
  [0;32m✓[0m Set up Python
  [0;32m✓[0m Build package
  [0;32m✓[0m Run actions/upload-artifact@v4
  [0;32m✓[0m Post Run astral-sh/setup-uv@v4
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[0;33m*[0m [0;1;39minstall-smoke[0m (ID [0;36m95787010707[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Run actions/download-artifact@v4
  [0;32m✓[0m Check out SASE
  [0;32m✓[0m Check out SASE Rust core
  [0;32m✓[0m Run astral-sh/setup-uv@v4
  [0;32m✓[0m Run extractions/setup-just@v2
  [0;32m✓[0m Run dtolnay/rust-toolchain@stable
  [0;32m✓[0m Set up Python
  [0;33m*[0m Install built sase-research-artifacts wheel into a fresh venv
  [0;33m*[0m Smoke check
  [0;33m*[0m Assemble the real artifact provider registry
  [0;33m*[0m Post Run astral-sh/setup-uv@v4
  [0;33m*[0m Post Check out SASE Rust core
  [0;33m*[0m Post Check out SASE
  [0;33m*[0m Post Run actions/checkout@v4

[0;1;39mANNOTATIONS[0m
[0;33m![0m Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
[38;5;242mbuild: .github#2
[0m
[0;33m![0m Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0a4eEagAAAADZtmRcHu09TbNQl71+FwrXQ08xRURHRTI1MTQARWRnZQ==
[38;5;242mbuild: .github#8
[0m
[0;33m![0m Failed to restore: Cache service responded with 400
[38;5;242mbuild: .github#26
[0m
[0;1;39mRefreshing run status every 3 seconds. Press Ctrl+C to quit.[0m

[0;33m*[0m [0;1;39mmaster[0m Publish · [0;36m32160158404[0m
Triggered via push about 1 minute ago

[0;1;39mJOBS[0m
[0;32m✓[0m [0;1;39mrelease[0m in 11s (ID [0;36m95786865377[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run googleapis/release-please-action@v5
  [0;32m✓[0m Complete job
[0;32m✓[0m [0;1;39mbuild[0m in 10s (ID [0;36m95786940152[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Run astral-sh/setup-uv@v4
  [0;32m✓[0m Set up Python
  [0;32m✓[0m Build package
  [0;32m✓[0m Run actions/upload-artifact@v4
  [0;32m✓[0m Post Run astral-sh/setup-uv@v4
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[0;33m*[0m [0;1;39minstall-smoke[0m (ID [0;36m95787010707[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Run actions/download-artifact@v4
  [0;32m✓[0m Check out SASE
  [0;32m✓[0m Check out SASE Rust core
  [0;32m✓[0m Run astral-sh/setup-uv@v4
  [0;32m✓[0m Run extractions/setup-just@v2
  [0;32m✓[0m Run dtolnay/rust-toolchain@stable
  [0;32m✓[0m Set up Python
  [0;33m*[0m Install built sase-research-artifacts wheel into a fresh venv
  [0;33m*[0m Smoke check
  [0;33m*[0m Assemble the real artifact provider registry
  [0;33m*[0m Post Run astral-sh/setup-uv@v4
  [0;33m*[0m Post Check out SASE Rust core
  [0;33m*[0m Post Check out SASE
  [0;33m*[0m Post Run actions/checkout@v4

[0;1;39mANNOTATIONS[0m
[0;33m![0m Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
[38;5;242mbuild: .github#2
[0m
[0;33m![0m Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0a4eEagAAAADZtmRcHu09TbNQl71+FwrXQ08xRURHRTI1MTQARWRnZQ==
[38;5;242mbuild: .github#8
[0m
[0;33m![0m Failed to restore: Cache service responded with 400
[38;5;242mbuild: .github#26
[0m
[0;1;39mRefreshing run status every 3 seconds. Press Ctrl+C to quit.[0m

[0;33m*[0m [0;1;39mmaster[0m Publish · [0;36m32160158404[0m
Triggered via push about 1 minute ago

[0;1;39mJOBS[0m
[0;32m✓[0m [0;1;39mrelease[0m in 11s (ID [0;36m95786865377[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run googleapis/release-please-action@v5
  [0;32m✓[0m Complete job
[0;32m✓[0m [0;1;39mbuild[0m in 10s (ID [0;36m95786940152[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Run astral-sh/setup-uv@v4
  [0;32m✓[0m Set up Python
  [0;32m✓[0m Build package
  [0;32m✓[0m Run actions/upload-artifact@v4
  [0;32m✓[0m Post Run astral-sh/setup-uv@v4
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[0;33m*[0m [0;1;39minstall-smoke[0m (ID [0;36m95787010707[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Run actions/download-artifact@v4
  [0;32m✓[0m Check out SASE
  [0;32m✓[0m Check out SASE Rust core
  [0;32m✓[0m Run astral-sh/setup-uv@v4
  [0;32m✓[0m Run extractions/setup-just@v2
  [0;32m✓[0m Run dtolnay/rust-toolchain@stable
  [0;32m✓[0m Set up Python
  [0;33m*[0m Install built sase-research-artifacts wheel into a fresh venv
  [0;33m*[0m Smoke check
  [0;33m*[0m Assemble the real artifact provider registry
  [0;33m*[0m Post Run astral-sh/setup-uv@v4
  [0;33m*[0m Post Check out SASE Rust core
  [0;33m*[0m Post Check out SASE
  [0;33m*[0m Post Run actions/checkout@v4

[0;1;39mANNOTATIONS[0m
[0;33m![0m Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
[38;5;242mbuild: .github#2
[0m
[0;33m![0m Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0a4eEagAAAADZtmRcHu09TbNQl71+FwrXQ08xRURHRTI1MTQARWRnZQ==
[38;5;242mbuild: .github#8
[0m
[0;33m![0m Failed to restore: Cache service responded with 400
[38;5;242mbuild: .github#26
[0m
[0;1;39mRefreshing run status every 3 seconds. Press Ctrl+C to quit.[0m

[0;33m*[0m [0;1;39mmaster[0m Publish · [0;36m32160158404[0m
Triggered via push about 2 minutes ago

[0;1;39mJOBS[0m
[0;32m✓[0m [0;1;39mrelease[0m in 11s (ID [0;36m95786865377[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run googleapis/release-please-action@v5
  [0;32m✓[0m Complete job
[0;32m✓[0m [0;1;39mbuild[0m in 10s (ID [0;36m95786940152[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Run astral-sh/setup-uv@v4
  [0;32m✓[0m Set up Python
  [0;32m✓[0m Build package
  [0;32m✓[0m Run actions/upload-artifact@v4
  [0;32m✓[0m Post Run astral-sh/setup-uv@v4
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[0;33m*[0m [0;1;39minstall-smoke[0m (ID [0;36m95787010707[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Run actions/download-artifact@v4
  [0;32m✓[0m Check out SASE
  [0;32m✓[0m Check out SASE Rust core
  [0;32m✓[0m Run astral-sh/setup-uv@v4
  [0;32m✓[0m Run extractions/setup-just@v2
  [0;32m✓[0m Run dtolnay/rust-toolchain@stable
  [0;32m✓[0m Set up Python
  [0;33m*[0m Install built sase-research-artifacts wheel into a fresh venv
  [0;33m*[0m Smoke check
  [0;33m*[0m Assemble the real artifact provider registry
  [0;33m*[0m Post Run astral-sh/setup-uv@v4
  [0;33m*[0m Post Check out SASE Rust core
  [0;33m*[0m Post Check out SASE
  [0;33m*[0m Post Run actions/checkout@v4

[0;1;39mANNOTATIONS[0m
[0;33m![0m Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
[38;5;242mbuild: .github#2
[0m
[0;33m![0m Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0a4eEagAAAADZtmRcHu09TbNQl71+FwrXQ08xRURHRTI1MTQARWRnZQ==
[38;5;242mbuild: .github#8
[0m
[0;33m![0m Failed to restore: Cache service responded with 400
[38;5;242mbuild: .github#26
[0m
[0;1;39mRefreshing run status every 3 seconds. Press Ctrl+C to quit.[0m

[0;33m*[0m [0;1;39mmaster[0m Publish · [0;36m32160158404[0m
Triggered via push about 2 minutes ago

[0;1;39mJOBS[0m
[0;32m✓[0m [0;1;39mrelease[0m in 11s (ID [0;36m95786865377[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run googleapis/release-please-action@v5
  [0;32m✓[0m Complete job
[0;32m✓[0m [0;1;39mbuild[0m in 10s (ID [0;36m95786940152[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Run astral-sh/setup-uv@v4
  [0;32m✓[0m Set up Python
  [0;32m✓[0m Build package
  [0;32m✓[0m Run actions/upload-artifact@v4
  [0;32m✓[0m Post Run astral-sh/setup-uv@v4
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[0;33m*[0m [0;1;39minstall-smoke[0m (ID [0;36m95787010707[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Run actions/download-artifact@v4
  [0;32m✓[0m Check out SASE
  [0;32m✓[0m Check out SASE Rust core
  [0;32m✓[0m Run astral-sh/setup-uv@v4
  [0;32m✓[0m Run extractions/setup-just@v2
  [0;32m✓[0m Run dtolnay/rust-toolchain@stable
  [0;32m✓[0m Set up Python
  [0;33m*[0m Install built sase-research-artifacts wheel into a fresh venv
  [0;33m*[0m Smoke check
  [0;33m*[0m Assemble the real artifact provider registry
  [0;33m*[0m Post Run astral-sh/setup-uv@v4
  [0;33m*[0m Post Check out SASE Rust core
  [0;33m*[0m Post Check out SASE
  [0;33m*[0m Post Run actions/checkout@v4

[0;1;39mANNOTATIONS[0m
[0;33m![0m Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
[38;5;242mbuild: .github#2
[0m
[0;33m![0m Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0a4eEagAAAADZtmRcHu09TbNQl71+FwrXQ08xRURHRTI1MTQARWRnZQ==
[38;5;242mbuild: .github#8
[0m
[0;33m![0m Failed to restore: Cache service responded with 400
[38;5;242mbuild: .github#26
[0m
[0;1;39mRefreshing run status every 3 seconds. Press Ctrl+C to quit.[0m

[0;33m*[0m [0;1;39mmaster[0m Publish · [0;36m32160158404[0m
Triggered via push about 2 minutes ago

[0;1;39mJOBS[0m
[0;32m✓[0m [0;1;39mrelease[0m in 11s (ID [0;36m95786865377[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run googleapis/release-please-action@v5
  [0;32m✓[0m Complete job
[0;32m✓[0m [0;1;39mbuild[0m in 10s (ID [0;36m95786940152[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Run astral-sh/setup-uv@v4
  [0;32m✓[0m Set up Python
  [0;32m✓[0m Build package
  [0;32m✓[0m Run actions/upload-artifact@v4
  [0;32m✓[0m Post Run astral-sh/setup-uv@v4
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[0;33m*[0m [0;1;39minstall-smoke[0m (ID [0;36m95787010707[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Run actions/download-artifact@v4
  [0;32m✓[0m Check out SASE
  [0;32m✓[0m Check out SASE Rust core
  [0;32m✓[0m Run astral-sh/setup-uv@v4
  [0;32m✓[0m Run extractions/setup-just@v2
  [0;32m✓[0m Run dtolnay/rust-toolchain@stable
  [0;32m✓[0m Set up Python
  [0;33m*[0m Install built sase-research-artifacts wheel into a fresh venv
  [0;33m*[0m Smoke check
  [0;33m*[0m Assemble the real artifact provider registry
  [0;33m*[0m Post Run astral-sh/setup-uv@v4
  [0;33m*[0m Post Check out SASE Rust core
  [0;33m*[0m Post Check out SASE
  [0;33m*[0m Post Run actions/checkout@v4

[0;1;39mANNOTATIONS[0m
[0;33m![0m Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
[38;5;242mbuild: .github#2
[0m
[0;33m![0m Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0a4eEagAAAADZtmRcHu09TbNQl71+FwrXQ08xRURHRTI1MTQARWRnZQ==
[38;5;242mbuild: .github#8
[0m
[0;33m![0m Failed to restore: Cache service responded with 400
[38;5;242mbuild: .github#26
[0m
[0;1;39mRefreshing run status every 3 seconds. Press Ctrl+C to quit.[0m

[0;33m*[0m [0;1;39mmaster[0m Publish · [0;36m32160158404[0m
Triggered via push about 2 minutes ago

[0;1;39mJOBS[0m
[0;32m✓[0m [0;1;39mrelease[0m in 11s (ID [0;36m95786865377[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run googleapis/release-please-action@v5
  [0;32m✓[0m Complete job
[0;32m✓[0m [0;1;39mbuild[0m in 10s (ID [0;36m95786940152[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Run astral-sh/setup-uv@v4
  [0;32m✓[0m Set up Python
  [0;32m✓[0m Build package
  [0;32m✓[0m Run actions/upload-artifact@v4
  [0;32m✓[0m Post Run astral-sh/setup-uv@v4
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[0;33m*[0m [0;1;39minstall-smoke[0m (ID [0;36m95787010707[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Run actions/download-artifact@v4
  [0;32m✓[0m Check out SASE
  [0;32m✓[0m Check out SASE Rust core
  [0;32m✓[0m Run astral-sh/setup-uv@v4
  [0;32m✓[0m Run extractions/setup-just@v2
  [0;32m✓[0m Run dtolnay/rust-toolchain@stable
  [0;32m✓[0m Set up Python
  [0;33m*[0m Install built sase-research-artifacts wheel into a fresh venv
  [0;33m*[0m Smoke check
  [0;33m*[0m Assemble the real artifact provider registry
  [0;33m*[0m Post Run astral-sh/setup-uv@v4
  [0;33m*[0m Post Check out SASE Rust core
  [0;33m*[0m Post Check out SASE
  [0;33m*[0m Post Run actions/checkout@v4

[0;1;39mANNOTATIONS[0m
[0;33m![0m Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
[38;5;242mbuild: .github#2
[0m
[0;33m![0m Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0a4eEagAAAADZtmRcHu09TbNQl71+FwrXQ08xRURHRTI1MTQARWRnZQ==
[38;5;242mbuild: .github#8
[0m
[0;33m![0m Failed to restore: Cache service responded with 400
[38;5;242mbuild: .github#26
[0m
[0;1;39mRefreshing run status every 3 seconds. Press Ctrl+C to quit.[0m

[0;33m*[0m [0;1;39mmaster[0m Publish · [0;36m32160158404[0m
Triggered via push about 2 minutes ago

[0;1;39mJOBS[0m
[0;32m✓[0m [0;1;39mrelease[0m in 11s (ID [0;36m95786865377[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run googleapis/release-please-action@v5
  [0;32m✓[0m Complete job
[0;32m✓[0m [0;1;39mbuild[0m in 10s (ID [0;36m95786940152[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Run astral-sh/setup-uv@v4
  [0;32m✓[0m Set up Python
  [0;32m✓[0m Build package
  [0;32m✓[0m Run actions/upload-artifact@v4
  [0;32m✓[0m Post Run astral-sh/setup-uv@v4
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[0;33m*[0m [0;1;39minstall-smoke[0m (ID [0;36m95787010707[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Run actions/download-artifact@v4
  [0;32m✓[0m Check out SASE
  [0;32m✓[0m Check out SASE Rust core
  [0;32m✓[0m Run astral-sh/setup-uv@v4
  [0;32m✓[0m Run extractions/setup-just@v2
  [0;32m✓[0m Run dtolnay/rust-toolchain@stable
  [0;32m✓[0m Set up Python
  [0;33m*[0m Install built sase-research-artifacts wheel into a fresh venv
  [0;33m*[0m Smoke check
  [0;33m*[0m Assemble the real artifact provider registry
  [0;33m*[0m Post Run astral-sh/setup-uv@v4
  [0;33m*[0m Post Check out SASE Rust core
  [0;33m*[0m Post Check out SASE
  [0;33m*[0m Post Run actions/checkout@v4

[0;1;39mANNOTATIONS[0m
[0;33m![0m Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
[38;5;242mbuild: .github#2
[0m
[0;33m![0m Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0a4eEagAAAADZtmRcHu09TbNQl71+FwrXQ08xRURHRTI1MTQARWRnZQ==
[38;5;242mbuild: .github#8
[0m
[0;33m![0m Failed to restore: Cache service responded with 400
[38;5;242mbuild: .github#26
[0m
[0;1;39mRefreshing run status every 3 seconds. Press Ctrl+C to quit.[0m

[0;33m*[0m [0;1;39mmaster[0m Publish · [0;36m32160158404[0m
Triggered via push about 2 minutes ago

[0;1;39mJOBS[0m
[0;32m✓[0m [0;1;39mrelease[0m in 11s (ID [0;36m95786865377[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run googleapis/release-please-action@v5
  [0;32m✓[0m Complete job
[0;32m✓[0m [0;1;39mbuild[0m in 10s (ID [0;36m95786940152[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Run astral-sh/setup-uv@v4
  [0;32m✓[0m Set up Python
  [0;32m✓[0m Build package
  [0;32m✓[0m Run actions/upload-artifact@v4
  [0;32m✓[0m Post Run astral-sh/setup-uv@v4
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[0;33m*[0m [0;1;39minstall-smoke[0m (ID [0;36m95787010707[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Run actions/download-artifact@v4
  [0;32m✓[0m Check out SASE
  [0;32m✓[0m Check out SASE Rust core
  [0;32m✓[0m Run astral-sh/setup-uv@v4
  [0;32m✓[0m Run extractions/setup-just@v2
  [0;32m✓[0m Run dtolnay/rust-toolchain@stable
  [0;32m✓[0m Set up Python
  [0;33m*[0m Install built sase-research-artifacts wheel into a fresh venv
  [0;33m*[0m Smoke check
  [0;33m*[0m Assemble the real artifact provider registry
  [0;33m*[0m Post Run astral-sh/setup-uv@v4
  [0;33m*[0m Post Check out SASE Rust core
  [0;33m*[0m Post Check out SASE
  [0;33m*[0m Post Run actions/checkout@v4

[0;1;39mANNOTATIONS[0m
[0;33m![0m Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
[38;5;242mbuild: .github#2
[0m
[0;33m![0m Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0a4eEagAAAADZtmRcHu09TbNQl71+FwrXQ08xRURHRTI1MTQARWRnZQ==
[38;5;242mbuild: .github#8
[0m
[0;33m![0m Failed to restore: Cache service responded with 400
[38;5;242mbuild: .github#26
[0m
[0;1;39mRefreshing run status every 3 seconds. Press Ctrl+C to quit.[0m

[0;33m*[0m [0;1;39mmaster[0m Publish · [0;36m32160158404[0m
Triggered via push about 2 minutes ago

[0;1;39mJOBS[0m
[0;32m✓[0m [0;1;39mrelease[0m in 11s (ID [0;36m95786865377[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run googleapis/release-please-action@v5
  [0;32m✓[0m Complete job
[0;32m✓[0m [0;1;39mbuild[0m in 10s (ID [0;36m95786940152[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Run astral-sh/setup-uv@v4
  [0;32m✓[0m Set up Python
  [0;32m✓[0m Build package
  [0;32m✓[0m Run actions/upload-artifact@v4
  [0;32m✓[0m Post Run astral-sh/setup-uv@v4
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[0;33m*[0m [0;1;39minstall-smoke[0m (ID [0;36m95787010707[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Run actions/download-artifact@v4
  [0;32m✓[0m Check out SASE
  [0;32m✓[0m Check out SASE Rust core
  [0;32m✓[0m Run astral-sh/setup-uv@v4
  [0;32m✓[0m Run extractions/setup-just@v2
  [0;32m✓[0m Run dtolnay/rust-toolchain@stable
  [0;32m✓[0m Set up Python
  [0;33m*[0m Install built sase-research-artifacts wheel into a fresh venv
  [0;33m*[0m Smoke check
  [0;33m*[0m Assemble the real artifact provider registry
  [0;33m*[0m Post Run astral-sh/setup-uv@v4
  [0;33m*[0m Post Check out SASE Rust core
  [0;33m*[0m Post Check out SASE
  [0;33m*[0m Post Run actions/checkout@v4

[0;1;39mANNOTATIONS[0m
[0;33m![0m Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
[38;5;242mbuild: .github#2
[0m
[0;33m![0m Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0a4eEagAAAADZtmRcHu09TbNQl71+FwrXQ08xRURHRTI1MTQARWRnZQ==
[38;5;242mbuild: .github#8
[0m
[0;33m![0m Failed to restore: Cache service responded with 400
[38;5;242mbuild: .github#26
[0m
[0;1;39mRefreshing run status every 3 seconds. Press Ctrl+C to quit.[0m

[0;33m*[0m [0;1;39mmaster[0m Publish · [0;36m32160158404[0m
Triggered via push about 2 minutes ago

[0;1;39mJOBS[0m
[0;32m✓[0m [0;1;39mrelease[0m in 11s (ID [0;36m95786865377[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run googleapis/release-please-action@v5
  [0;32m✓[0m Complete job
[0;32m✓[0m [0;1;39mbuild[0m in 10s (ID [0;36m95786940152[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Run astral-sh/setup-uv@v4
  [0;32m✓[0m Set up Python
  [0;32m✓[0m Build package
  [0;32m✓[0m Run actions/upload-artifact@v4
  [0;32m✓[0m Post Run astral-sh/setup-uv@v4
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[0;33m*[0m [0;1;39minstall-smoke[0m (ID [0;36m95787010707[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Run actions/download-artifact@v4
  [0;32m✓[0m Check out SASE
  [0;32m✓[0m Check out SASE Rust core
  [0;32m✓[0m Run astral-sh/setup-uv@v4
  [0;32m✓[0m Run extractions/setup-just@v2
  [0;32m✓[0m Run dtolnay/rust-toolchain@stable
  [0;32m✓[0m Set up Python
  [0;33m*[0m Install built sase-research-artifacts wheel into a fresh venv
  [0;33m*[0m Smoke check
  [0;33m*[0m Assemble the real artifact provider registry
  [0;33m*[0m Post Run astral-sh/setup-uv@v4
  [0;33m*[0m Post Check out SASE Rust core
  [0;33m*[0m Post Check out SASE
  [0;33m*[0m Post Run actions/checkout@v4

[0;1;39mANNOTATIONS[0m
[0;33m![0m Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
[38;5;242mbuild: .github#2
[0m
[0;33m![0m Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0a4eEagAAAADZtmRcHu09TbNQl71+FwrXQ08xRURHRTI1MTQARWRnZQ==
[38;5;242mbuild: .github#8
[0m
[0;33m![0m Failed to restore: Cache service responded with 400
[38;5;242mbuild: .github#26
[0m
[0;1;39mRefreshing run status every 3 seconds. Press Ctrl+C to quit.[0m

[0;33m*[0m [0;1;39mmaster[0m Publish · [0;36m32160158404[0m
Triggered via push about 2 minutes ago

[0;1;39mJOBS[0m
[0;32m✓[0m [0;1;39mrelease[0m in 11s (ID [0;36m95786865377[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run googleapis/release-please-action@v5
  [0;32m✓[0m Complete job
[0;32m✓[0m [0;1;39mbuild[0m in 10s (ID [0;36m95786940152[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Run astral-sh/setup-uv@v4
  [0;32m✓[0m Set up Python
  [0;32m✓[0m Build package
  [0;32m✓[0m Run actions/upload-artifact@v4
  [0;32m✓[0m Post Run astral-sh/setup-uv@v4
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[0;33m*[0m [0;1;39minstall-smoke[0m (ID [0;36m95787010707[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Run actions/download-artifact@v4
  [0;32m✓[0m Check out SASE
  [0;32m✓[0m Check out SASE Rust core
  [0;32m✓[0m Run astral-sh/setup-uv@v4
  [0;32m✓[0m Run extractions/setup-just@v2
  [0;32m✓[0m Run dtolnay/rust-toolchain@stable
  [0;32m✓[0m Set up Python
  [0;33m*[0m Install built sase-research-artifacts wheel into a fresh venv
  [0;33m*[0m Smoke check
  [0;33m*[0m Assemble the real artifact provider registry
  [0;33m*[0m Post Run astral-sh/setup-uv@v4
  [0;33m*[0m Post Check out SASE Rust core
  [0;33m*[0m Post Check out SASE
  [0;33m*[0m Post Run actions/checkout@v4

[0;1;39mANNOTATIONS[0m
[0;33m![0m Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
[38;5;242mbuild: .github#2
[0m
[0;33m![0m Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0a4eEagAAAADZtmRcHu09TbNQl71+FwrXQ08xRURHRTI1MTQARWRnZQ==
[38;5;242mbuild: .github#8
[0m
[0;33m![0m Failed to restore: Cache service responded with 400
[38;5;242mbuild: .github#26
[0m
[0;1;39mRefreshing run status every 3 seconds. Press Ctrl+C to quit.[0m

[0;33m*[0m [0;1;39mmaster[0m Publish · [0;36m32160158404[0m
Triggered via push about 2 minutes ago

[0;1;39mJOBS[0m
[0;32m✓[0m [0;1;39mrelease[0m in 11s (ID [0;36m95786865377[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run googleapis/release-please-action@v5
  [0;32m✓[0m Complete job
[0;32m✓[0m [0;1;39mbuild[0m in 10s (ID [0;36m95786940152[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Run astral-sh/setup-uv@v4
  [0;32m✓[0m Set up Python
  [0;32m✓[0m Build package
  [0;32m✓[0m Run actions/upload-artifact@v4
  [0;32m✓[0m Post Run astral-sh/setup-uv@v4
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[0;33m*[0m [0;1;39minstall-smoke[0m (ID [0;36m95787010707[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Run actions/download-artifact@v4
  [0;32m✓[0m Check out SASE
  [0;32m✓[0m Check out SASE Rust core
  [0;32m✓[0m Run astral-sh/setup-uv@v4
  [0;32m✓[0m Run extractions/setup-just@v2
  [0;32m✓[0m Run dtolnay/rust-toolchain@stable
  [0;32m✓[0m Set up Python
  [0;33m*[0m Install built sase-research-artifacts wheel into a fresh venv
  [0;33m*[0m Smoke check
  [0;33m*[0m Assemble the real artifact provider registry
  [0;33m*[0m Post Run astral-sh/setup-uv@v4
  [0;33m*[0m Post Check out SASE Rust core
  [0;33m*[0m Post Check out SASE
  [0;33m*[0m Post Run actions/checkout@v4

[0;1;39mANNOTATIONS[0m
[0;33m![0m Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
[38;5;242mbuild: .github#2
[0m
[0;33m![0m Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0a4eEagAAAADZtmRcHu09TbNQl71+FwrXQ08xRURHRTI1MTQARWRnZQ==
[38;5;242mbuild: .github#8
[0m
[0;33m![0m Failed to restore: Cache service responded with 400
[38;5;242mbuild: .github#26
[0m
[0;1;39mRefreshing run status every 3 seconds. Press Ctrl+C to quit.[0m

[0;33m*[0m [0;1;39mmaster[0m Publish · [0;36m32160158404[0m
Triggered via push about 2 minutes ago

[0;1;39mJOBS[0m
[0;32m✓[0m [0;1;39mrelease[0m in 11s (ID [0;36m95786865377[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run googleapis/release-please-action@v5
  [0;32m✓[0m Complete job
[0;32m✓[0m [0;1;39mbuild[0m in 10s (ID [0;36m95786940152[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Run astral-sh/setup-uv@v4
  [0;32m✓[0m Set up Python
  [0;32m✓[0m Build package
  [0;32m✓[0m Run actions/upload-artifact@v4
  [0;32m✓[0m Post Run astral-sh/setup-uv@v4
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[0;33m*[0m [0;1;39minstall-smoke[0m (ID [0;36m95787010707[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Run actions/download-artifact@v4
  [0;32m✓[0m Check out SASE
  [0;32m✓[0m Check out SASE Rust core
  [0;32m✓[0m Run astral-sh/setup-uv@v4
  [0;32m✓[0m Run extractions/setup-just@v2
  [0;32m✓[0m Run dtolnay/rust-toolchain@stable
  [0;32m✓[0m Set up Python
  [0;33m*[0m Install built sase-research-artifacts wheel into a fresh venv
  [0;33m*[0m Smoke check
  [0;33m*[0m Assemble the real artifact provider registry
  [0;33m*[0m Post Run astral-sh/setup-uv@v4
  [0;33m*[0m Post Check out SASE Rust core
  [0;33m*[0m Post Check out SASE
  [0;33m*[0m Post Run actions/checkout@v4

[0;1;39mANNOTATIONS[0m
[0;33m![0m Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
[38;5;242mbuild: .github#2
[0m
[0;33m![0m Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0a4eEagAAAADZtmRcHu09TbNQl71+FwrXQ08xRURHRTI1MTQARWRnZQ==
[38;5;242mbuild: .github#8
[0m
[0;33m![0m Failed to restore: Cache service responded with 400
[38;5;242mbuild: .github#26
[0m
[0;1;39mRefreshing run status every 3 seconds. Press Ctrl+C to quit.[0m

[0;33m*[0m [0;1;39mmaster[0m Publish · [0;36m32160158404[0m
Triggered via push about 2 minutes ago

[0;1;39mJOBS[0m
[0;32m✓[0m [0;1;39mrelease[0m in 11s (ID [0;36m95786865377[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run googleapis/release-please-action@v5
  [0;32m✓[0m Complete job
[0;32m✓[0m [0;1;39mbuild[0m in 10s (ID [0;36m95786940152[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Run astral-sh/setup-uv@v4
  [0;32m✓[0m Set up Python
  [0;32m✓[0m Build package
  [0;32m✓[0m Run actions/upload-artifact@v4
  [0;32m✓[0m Post Run astral-sh/setup-uv@v4
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[0;33m*[0m [0;1;39minstall-smoke[0m (ID [0;36m95787010707[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Run actions/download-artifact@v4
  [0;32m✓[0m Check out SASE
  [0;32m✓[0m Check out SASE Rust core
  [0;32m✓[0m Run astral-sh/setup-uv@v4
  [0;32m✓[0m Run extractions/setup-just@v2
  [0;32m✓[0m Run dtolnay/rust-toolchain@stable
  [0;32m✓[0m Set up Python
  [0;33m*[0m Install built sase-research-artifacts wheel into a fresh venv
  [0;33m*[0m Smoke check
  [0;33m*[0m Assemble the real artifact provider registry
  [0;33m*[0m Post Run astral-sh/setup-uv@v4
  [0;33m*[0m Post Check out SASE Rust core
  [0;33m*[0m Post Check out SASE
  [0;33m*[0m Post Run actions/checkout@v4

[0;1;39mANNOTATIONS[0m
[0;33m![0m Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
[38;5;242mbuild: .github#2
[0m
[0;33m![0m Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0a4eEagAAAADZtmRcHu09TbNQl71+FwrXQ08xRURHRTI1MTQARWRnZQ==
[38;5;242mbuild: .github#8
[0m
[0;33m![0m Failed to restore: Cache service responded with 400
[38;5;242mbuild: .github#26
[0m
[0;1;39mRefreshing run status every 3 seconds. Press Ctrl+C to quit.[0m

[0;33m*[0m [0;1;39mmaster[0m Publish · [0;36m32160158404[0m
Triggered via push about 2 minutes ago

[0;1;39mJOBS[0m
[0;32m✓[0m [0;1;39mrelease[0m in 11s (ID [0;36m95786865377[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run googleapis/release-please-action@v5
  [0;32m✓[0m Complete job
[0;32m✓[0m [0;1;39mbuild[0m in 10s (ID [0;36m95786940152[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Run astral-sh/setup-uv@v4
  [0;32m✓[0m Set up Python
  [0;32m✓[0m Build package
  [0;32m✓[0m Run actions/upload-artifact@v4
  [0;32m✓[0m Post Run astral-sh/setup-uv@v4
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[0;33m*[0m [0;1;39minstall-smoke[0m (ID [0;36m95787010707[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Run actions/download-artifact@v4
  [0;32m✓[0m Check out SASE
  [0;32m✓[0m Check out SASE Rust core
  [0;32m✓[0m Run astral-sh/setup-uv@v4
  [0;32m✓[0m Run extractions/setup-just@v2
  [0;32m✓[0m Run dtolnay/rust-toolchain@stable
  [0;32m✓[0m Set up Python
  [0;33m*[0m Install built sase-research-artifacts wheel into a fresh venv
  [0;33m*[0m Smoke check
  [0;33m*[0m Assemble the real artifact provider registry
  [0;33m*[0m Post Run astral-sh/setup-uv@v4
  [0;33m*[0m Post Check out SASE Rust core
  [0;33m*[0m Post Check out SASE
  [0;33m*[0m Post Run actions/checkout@v4

[0;1;39mANNOTATIONS[0m
[0;33m![0m Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
[38;5;242mbuild: .github#2
[0m
[0;33m![0m Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0a4eEagAAAADZtmRcHu09TbNQl71+FwrXQ08xRURHRTI1MTQARWRnZQ==
[38;5;242mbuild: .github#8
[0m
[0;33m![0m Failed to restore: Cache service responded with 400
[38;5;242mbuild: .github#26
[0m
[0;1;39mRefreshing run status every 3 seconds. Press Ctrl+C to quit.[0m

[0;33m*[0m [0;1;39mmaster[0m Publish · [0;36m32160158404[0m
Triggered via push about 2 minutes ago

[0;1;39mJOBS[0m
[0;32m✓[0m [0;1;39mrelease[0m in 11s (ID [0;36m95786865377[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run googleapis/release-please-action@v5
  [0;32m✓[0m Complete job
[0;32m✓[0m [0;1;39mbuild[0m in 10s (ID [0;36m95786940152[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Run astral-sh/setup-uv@v4
  [0;32m✓[0m Set up Python
  [0;32m✓[0m Build package
  [0;32m✓[0m Run actions/upload-artifact@v4
  [0;32m✓[0m Post Run astral-sh/setup-uv@v4
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[0;33m*[0m [0;1;39minstall-smoke[0m (ID [0;36m95787010707[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Run actions/download-artifact@v4
  [0;32m✓[0m Check out SASE
  [0;32m✓[0m Check out SASE Rust core
  [0;32m✓[0m Run astral-sh/setup-uv@v4
  [0;32m✓[0m Run extractions/setup-just@v2
  [0;32m✓[0m Run dtolnay/rust-toolchain@stable
  [0;32m✓[0m Set up Python
  [0;33m*[0m Install built sase-research-artifacts wheel into a fresh venv
  [0;33m*[0m Smoke check
  [0;33m*[0m Assemble the real artifact provider registry
  [0;33m*[0m Post Run astral-sh/setup-uv@v4
  [0;33m*[0m Post Check out SASE Rust core
  [0;33m*[0m Post Check out SASE
  [0;33m*[0m Post Run actions/checkout@v4

[0;1;39mANNOTATIONS[0m
[0;33m![0m Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
[38;5;242mbuild: .github#2
[0m
[0;33m![0m Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0a4eEagAAAADZtmRcHu09TbNQl71+FwrXQ08xRURHRTI1MTQARWRnZQ==
[38;5;242mbuild: .github#8
[0m
[0;33m![0m Failed to restore: Cache service responded with 400
[38;5;242mbuild: .github#26
[0m
[0;1;39mRefreshing run status every 3 seconds. Press Ctrl+C to quit.[0m

[0;33m*[0m [0;1;39mmaster[0m Publish · [0;36m32160158404[0m
Triggered via push about 2 minutes ago

[0;1;39mJOBS[0m
[0;32m✓[0m [0;1;39mrelease[0m in 11s (ID [0;36m95786865377[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run googleapis/release-please-action@v5
  [0;32m✓[0m Complete job
[0;32m✓[0m [0;1;39mbuild[0m in 10s (ID [0;36m95786940152[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Run astral-sh/setup-uv@v4
  [0;32m✓[0m Set up Python
  [0;32m✓[0m Build package
  [0;32m✓[0m Run actions/upload-artifact@v4
  [0;32m✓[0m Post Run astral-sh/setup-uv@v4
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[0;33m*[0m [0;1;39minstall-smoke[0m (ID [0;36m95787010707[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Run actions/download-artifact@v4
  [0;32m✓[0m Check out SASE
  [0;32m✓[0m Check out SASE Rust core
  [0;32m✓[0m Run astral-sh/setup-uv@v4
  [0;32m✓[0m Run extractions/setup-just@v2
  [0;32m✓[0m Run dtolnay/rust-toolchain@stable
  [0;32m✓[0m Set up Python
  [0;33m*[0m Install built sase-research-artifacts wheel into a fresh venv
  [0;33m*[0m Smoke check
  [0;33m*[0m Assemble the real artifact provider registry
  [0;33m*[0m Post Run astral-sh/setup-uv@v4
  [0;33m*[0m Post Check out SASE Rust core
  [0;33m*[0m Post Check out SASE
  [0;33m*[0m Post Run actions/checkout@v4

[0;1;39mANNOTATIONS[0m
[0;33m![0m Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
[38;5;242mbuild: .github#2
[0m
[0;33m![0m Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0a4eEagAAAADZtmRcHu09TbNQl71+FwrXQ08xRURHRTI1MTQARWRnZQ==
[38;5;242mbuild: .github#8
[0m
[0;33m![0m Failed to restore: Cache service responded with 400
[38;5;242mbuild: .github#26
[0m
[0;1;39mRefreshing run status every 3 seconds. Press Ctrl+C to quit.[0m

[0;33m*[0m [0;1;39mmaster[0m Publish · [0;36m32160158404[0m
Triggered via push about 2 minutes ago

[0;1;39mJOBS[0m
[0;32m✓[0m [0;1;39mrelease[0m in 11s (ID [0;36m95786865377[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run googleapis/release-please-action@v5
  [0;32m✓[0m Complete job
[0;32m✓[0m [0;1;39mbuild[0m in 10s (ID [0;36m95786940152[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Run astral-sh/setup-uv@v4
  [0;32m✓[0m Set up Python
  [0;32m✓[0m Build package
  [0;32m✓[0m Run actions/upload-artifact@v4
  [0;32m✓[0m Post Run astral-sh/setup-uv@v4
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[0;33m*[0m [0;1;39minstall-smoke[0m (ID [0;36m95787010707[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Run actions/download-artifact@v4
  [0;32m✓[0m Check out SASE
  [0;32m✓[0m Check out SASE Rust core
  [0;32m✓[0m Run astral-sh/setup-uv@v4
  [0;32m✓[0m Run extractions/setup-just@v2
  [0;32m✓[0m Run dtolnay/rust-toolchain@stable
  [0;32m✓[0m Set up Python
  [0;33m*[0m Install built sase-research-artifacts wheel into a fresh venv
  [0;33m*[0m Smoke check
  [0;33m*[0m Assemble the real artifact provider registry
  [0;33m*[0m Post Run astral-sh/setup-uv@v4
  [0;33m*[0m Post Check out SASE Rust core
  [0;33m*[0m Post Check out SASE
  [0;33m*[0m Post Run actions/checkout@v4

[0;1;39mANNOTATIONS[0m
[0;33m![0m Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
[38;5;242mbuild: .github#2
[0m
[0;33m![0m Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0a4eEagAAAADZtmRcHu09TbNQl71+FwrXQ08xRURHRTI1MTQARWRnZQ==
[38;5;242mbuild: .github#8
[0m
[0;33m![0m Failed to restore: Cache service responded with 400
[38;5;242mbuild: .github#26
[0m
[0;1;39mRefreshing run status every 3 seconds. Press Ctrl+C to quit.[0m

[0;33m*[0m [0;1;39mmaster[0m Publish · [0;36m32160158404[0m
Triggered via push about 2 minutes ago

[0;1;39mJOBS[0m
[0;32m✓[0m [0;1;39mrelease[0m in 11s (ID [0;36m95786865377[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run googleapis/release-please-action@v5
  [0;32m✓[0m Complete job
[0;32m✓[0m [0;1;39mbuild[0m in 10s (ID [0;36m95786940152[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Run astral-sh/setup-uv@v4
  [0;32m✓[0m Set up Python
  [0;32m✓[0m Build package
  [0;32m✓[0m Run actions/upload-artifact@v4
  [0;32m✓[0m Post Run astral-sh/setup-uv@v4
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[0;33m*[0m [0;1;39minstall-smoke[0m (ID [0;36m95787010707[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Run actions/download-artifact@v4
  [0;32m✓[0m Check out SASE
  [0;32m✓[0m Check out SASE Rust core
  [0;32m✓[0m Run astral-sh/setup-uv@v4
  [0;32m✓[0m Run extractions/setup-just@v2
  [0;32m✓[0m Run dtolnay/rust-toolchain@stable
  [0;32m✓[0m Set up Python
  [0;33m*[0m Install built sase-research-artifacts wheel into a fresh venv
  [0;33m*[0m Smoke check
  [0;33m*[0m Assemble the real artifact provider registry
  [0;33m*[0m Post Run astral-sh/setup-uv@v4
  [0;33m*[0m Post Check out SASE Rust core
  [0;33m*[0m Post Check out SASE
  [0;33m*[0m Post Run actions/checkout@v4

[0;1;39mANNOTATIONS[0m
[0;33m![0m Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
[38;5;242mbuild: .github#2
[0m
[0;33m![0m Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0a4eEagAAAADZtmRcHu09TbNQl71+FwrXQ08xRURHRTI1MTQARWRnZQ==
[38;5;242mbuild: .github#8
[0m
[0;33m![0m Failed to restore: Cache service responded with 400
[38;5;242mbuild: .github#26
[0m
[0;1;39mRefreshing run status every 3 seconds. Press Ctrl+C to quit.[0m

[0;33m*[0m [0;1;39mmaster[0m Publish · [0;36m32160158404[0m
Triggered via push about 3 minutes ago

[0;1;39mJOBS[0m
[0;32m✓[0m [0;1;39mrelease[0m in 11s (ID [0;36m95786865377[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run googleapis/release-please-action@v5
  [0;32m✓[0m Complete job
[0;32m✓[0m [0;1;39mbuild[0m in 10s (ID [0;36m95786940152[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Run astral-sh/setup-uv@v4
  [0;32m✓[0m Set up Python
  [0;32m✓[0m Build package
  [0;32m✓[0m Run actions/upload-artifact@v4
  [0;32m✓[0m Post Run astral-sh/setup-uv@v4
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[0;33m*[0m [0;1;39minstall-smoke[0m (ID [0;36m95787010707[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Run actions/download-artifact@v4
  [0;32m✓[0m Check out SASE
  [0;32m✓[0m Check out SASE Rust core
  [0;32m✓[0m Run astral-sh/setup-uv@v4
  [0;32m✓[0m Run extractions/setup-just@v2
  [0;32m✓[0m Run dtolnay/rust-toolchain@stable
  [0;32m✓[0m Set up Python
  [0;33m*[0m Install built sase-research-artifacts wheel into a fresh venv
  [0;33m*[0m Smoke check
  [0;33m*[0m Assemble the real artifact provider registry
  [0;33m*[0m Post Run astral-sh/setup-uv@v4
  [0;33m*[0m Post Check out SASE Rust core
  [0;33m*[0m Post Check out SASE
  [0;33m*[0m Post Run actions/checkout@v4

[0;1;39mANNOTATIONS[0m
[0;33m![0m Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
[38;5;242mbuild: .github#2
[0m
[0;33m![0m Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0a4eEagAAAADZtmRcHu09TbNQl71+FwrXQ08xRURHRTI1MTQARWRnZQ==
[38;5;242mbuild: .github#8
[0m
[0;33m![0m Failed to restore: Cache service responded with 400
[38;5;242mbuild: .github#26
[0m
[0;1;39mRefreshing run status every 3 seconds. Press Ctrl+C to quit.[0m

[0;33m*[0m [0;1;39mmaster[0m Publish · [0;36m32160158404[0m
Triggered via push about 3 minutes ago

[0;1;39mJOBS[0m
[0;32m✓[0m [0;1;39mrelease[0m in 11s (ID [0;36m95786865377[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run googleapis/release-please-action@v5
  [0;32m✓[0m Complete job
[0;32m✓[0m [0;1;39mbuild[0m in 10s (ID [0;36m95786940152[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Run astral-sh/setup-uv@v4
  [0;32m✓[0m Set up Python
  [0;32m✓[0m Build package
  [0;32m✓[0m Run actions/upload-artifact@v4
  [0;32m✓[0m Post Run astral-sh/setup-uv@v4
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[0;33m*[0m [0;1;39minstall-smoke[0m (ID [0;36m95787010707[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Run actions/download-artifact@v4
  [0;32m✓[0m Check out SASE
  [0;32m✓[0m Check out SASE Rust core
  [0;32m✓[0m Run astral-sh/setup-uv@v4
  [0;32m✓[0m Run extractions/setup-just@v2
  [0;32m✓[0m Run dtolnay/rust-toolchain@stable
  [0;32m✓[0m Set up Python
  [0;33m*[0m Install built sase-research-artifacts wheel into a fresh venv
  [0;33m*[0m Smoke check
  [0;33m*[0m Assemble the real artifact provider registry
  [0;33m*[0m Post Run astral-sh/setup-uv@v4
  [0;33m*[0m Post Check out SASE Rust core
  [0;33m*[0m Post Check out SASE
  [0;33m*[0m Post Run actions/checkout@v4

[0;1;39mANNOTATIONS[0m
[0;33m![0m Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
[38;5;242mbuild: .github#2
[0m
[0;33m![0m Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0a4eEagAAAADZtmRcHu09TbNQl71+FwrXQ08xRURHRTI1MTQARWRnZQ==
[38;5;242mbuild: .github#8
[0m
[0;33m![0m Failed to restore: Cache service responded with 400
[38;5;242mbuild: .github#26
[0m
[0;1;39mRefreshing run status every 3 seconds. Press Ctrl+C to quit.[0m

[0;33m*[0m [0;1;39mmaster[0m Publish · [0;36m32160158404[0m
Triggered via push about 3 minutes ago

[0;1;39mJOBS[0m
[0;32m✓[0m [0;1;39mrelease[0m in 11s (ID [0;36m95786865377[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run googleapis/release-please-action@v5
  [0;32m✓[0m Complete job
[0;32m✓[0m [0;1;39mbuild[0m in 10s (ID [0;36m95786940152[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Run astral-sh/setup-uv@v4
  [0;32m✓[0m Set up Python
  [0;32m✓[0m Build package
  [0;32m✓[0m Run actions/upload-artifact@v4
  [0;32m✓[0m Post Run astral-sh/setup-uv@v4
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[0;33m*[0m [0;1;39minstall-smoke[0m (ID [0;36m95787010707[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Run actions/download-artifact@v4
  [0;32m✓[0m Check out SASE
  [0;32m✓[0m Check out SASE Rust core
  [0;32m✓[0m Run astral-sh/setup-uv@v4
  [0;32m✓[0m Run extractions/setup-just@v2
  [0;32m✓[0m Run dtolnay/rust-toolchain@stable
  [0;32m✓[0m Set up Python
  [0;33m*[0m Install built sase-research-artifacts wheel into a fresh venv
  [0;33m*[0m Smoke check
  [0;33m*[0m Assemble the real artifact provider registry
  [0;33m*[0m Post Run astral-sh/setup-uv@v4
  [0;33m*[0m Post Check out SASE Rust core
  [0;33m*[0m Post Check out SASE
  [0;33m*[0m Post Run actions/checkout@v4

[0;1;39mANNOTATIONS[0m
[0;33m![0m Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
[38;5;242mbuild: .github#2
[0m
[0;33m![0m Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0a4eEagAAAADZtmRcHu09TbNQl71+FwrXQ08xRURHRTI1MTQARWRnZQ==
[38;5;242mbuild: .github#8
[0m
[0;33m![0m Failed to restore: Cache service responded with 400
[38;5;242mbuild: .github#26
[0m
[0;1;39mRefreshing run status every 3 seconds. Press Ctrl+C to quit.[0m

[0;33m*[0m [0;1;39mmaster[0m Publish · [0;36m32160158404[0m
Triggered via push about 3 minutes ago

[0;1;39mJOBS[0m
[0;32m✓[0m [0;1;39mrelease[0m in 11s (ID [0;36m95786865377[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run googleapis/release-please-action@v5
  [0;32m✓[0m Complete job
[0;32m✓[0m [0;1;39mbuild[0m in 10s (ID [0;36m95786940152[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Run astral-sh/setup-uv@v4
  [0;32m✓[0m Set up Python
  [0;32m✓[0m Build package
  [0;32m✓[0m Run actions/upload-artifact@v4
  [0;32m✓[0m Post Run astral-sh/setup-uv@v4
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[0;33m*[0m [0;1;39minstall-smoke[0m (ID [0;36m95787010707[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Run actions/download-artifact@v4
  [0;32m✓[0m Check out SASE
  [0;32m✓[0m Check out SASE Rust core
  [0;32m✓[0m Run astral-sh/setup-uv@v4
  [0;32m✓[0m Run extractions/setup-just@v2
  [0;32m✓[0m Run dtolnay/rust-toolchain@stable
  [0;32m✓[0m Set up Python
  [0;33m*[0m Install built sase-research-artifacts wheel into a fresh venv
  [0;33m*[0m Smoke check
  [0;33m*[0m Assemble the real artifact provider registry
  [0;33m*[0m Post Run astral-sh/setup-uv@v4
  [0;33m*[0m Post Check out SASE Rust core
  [0;33m*[0m Post Check out SASE
  [0;33m*[0m Post Run actions/checkout@v4

[0;1;39mANNOTATIONS[0m
[0;33m![0m Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
[38;5;242mbuild: .github#2
[0m
[0;33m![0m Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0a4eEagAAAADZtmRcHu09TbNQl71+FwrXQ08xRURHRTI1MTQARWRnZQ==
[38;5;242mbuild: .github#8
[0m
[0;33m![0m Failed to restore: Cache service responded with 400
[38;5;242mbuild: .github#26
[0m
[0;1;39mRefreshing run status every 3 seconds. Press Ctrl+C to quit.[0m

[0;33m*[0m [0;1;39mmaster[0m Publish · [0;36m32160158404[0m
Triggered via push about 3 minutes ago

[0;1;39mJOBS[0m
[0;32m✓[0m [0;1;39mrelease[0m in 11s (ID [0;36m95786865377[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run googleapis/release-please-action@v5
  [0;32m✓[0m Complete job
[0;32m✓[0m [0;1;39mbuild[0m in 10s (ID [0;36m95786940152[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Run astral-sh/setup-uv@v4
  [0;32m✓[0m Set up Python
  [0;32m✓[0m Build package
  [0;32m✓[0m Run actions/upload-artifact@v4
  [0;32m✓[0m Post Run astral-sh/setup-uv@v4
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[0;33m*[0m [0;1;39minstall-smoke[0m (ID [0;36m95787010707[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Run actions/download-artifact@v4
  [0;32m✓[0m Check out SASE
  [0;32m✓[0m Check out SASE Rust core
  [0;32m✓[0m Run astral-sh/setup-uv@v4
  [0;32m✓[0m Run extractions/setup-just@v2
  [0;32m✓[0m Run dtolnay/rust-toolchain@stable
  [0;32m✓[0m Set up Python
  [0;33m*[0m Install built sase-research-artifacts wheel into a fresh venv
  [0;33m*[0m Smoke check
  [0;33m*[0m Assemble the real artifact provider registry
  [0;33m*[0m Post Run astral-sh/setup-uv@v4
  [0;33m*[0m Post Check out SASE Rust core
  [0;33m*[0m Post Check out SASE
  [0;33m*[0m Post Run actions/checkout@v4

[0;1;39mANNOTATIONS[0m
[0;33m![0m Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
[38;5;242mbuild: .github#2
[0m
[0;33m![0m Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0a4eEagAAAADZtmRcHu09TbNQl71+FwrXQ08xRURHRTI1MTQARWRnZQ==
[38;5;242mbuild: .github#8
[0m
[0;33m![0m Failed to restore: Cache service responded with 400
[38;5;242mbuild: .github#26
[0m
[0;1;39mRefreshing run status every 3 seconds. Press Ctrl+C to quit.[0m

[0;33m*[0m [0;1;39mmaster[0m Publish · [0;36m32160158404[0m
Triggered via push about 3 minutes ago

[0;1;39mJOBS[0m
[0;32m✓[0m [0;1;39mrelease[0m in 11s (ID [0;36m95786865377[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run googleapis/release-please-action@v5
  [0;32m✓[0m Complete job
[0;32m✓[0m [0;1;39mbuild[0m in 10s (ID [0;36m95786940152[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Run astral-sh/setup-uv@v4
  [0;32m✓[0m Set up Python
  [0;32m✓[0m Build package
  [0;32m✓[0m Run actions/upload-artifact@v4
  [0;32m✓[0m Post Run astral-sh/setup-uv@v4
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[0;33m*[0m [0;1;39minstall-smoke[0m (ID [0;36m95787010707[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Run actions/download-artifact@v4
  [0;32m✓[0m Check out SASE
  [0;32m✓[0m Check out SASE Rust core
  [0;32m✓[0m Run astral-sh/setup-uv@v4
  [0;32m✓[0m Run extractions/setup-just@v2
  [0;32m✓[0m Run dtolnay/rust-toolchain@stable
  [0;32m✓[0m Set up Python
  [0;33m*[0m Install built sase-research-artifacts wheel into a fresh venv
  [0;33m*[0m Smoke check
  [0;33m*[0m Assemble the real artifact provider registry
  [0;33m*[0m Post Run astral-sh/setup-uv@v4
  [0;33m*[0m Post Check out SASE Rust core
  [0;33m*[0m Post Check out SASE
  [0;33m*[0m Post Run actions/checkout@v4

[0;1;39mANNOTATIONS[0m
[0;33m![0m Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
[38;5;242mbuild: .github#2
[0m
[0;33m![0m Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0a4eEagAAAADZtmRcHu09TbNQl71+FwrXQ08xRURHRTI1MTQARWRnZQ==
[38;5;242mbuild: .github#8
[0m
[0;33m![0m Failed to restore: Cache service responded with 400
[38;5;242mbuild: .github#26
[0m
[0;1;39mRefreshing run status every 3 seconds. Press Ctrl+C to quit.[0m

[0;33m*[0m [0;1;39mmaster[0m Publish · [0;36m32160158404[0m
Triggered via push about 3 minutes ago

[0;1;39mJOBS[0m
[0;32m✓[0m [0;1;39mrelease[0m in 11s (ID [0;36m95786865377[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run googleapis/release-please-action@v5
  [0;32m✓[0m Complete job
[0;32m✓[0m [0;1;39mbuild[0m in 10s (ID [0;36m95786940152[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Run astral-sh/setup-uv@v4
  [0;32m✓[0m Set up Python
  [0;32m✓[0m Build package
  [0;32m✓[0m Run actions/upload-artifact@v4
  [0;32m✓[0m Post Run astral-sh/setup-uv@v4
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[0;33m*[0m [0;1;39minstall-smoke[0m (ID [0;36m95787010707[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Run actions/download-artifact@v4
  [0;32m✓[0m Check out SASE
  [0;32m✓[0m Check out SASE Rust core
  [0;32m✓[0m Run astral-sh/setup-uv@v4
  [0;32m✓[0m Run extractions/setup-just@v2
  [0;32m✓[0m Run dtolnay/rust-toolchain@stable
  [0;32m✓[0m Set up Python
  [0;33m*[0m Install built sase-research-artifacts wheel into a fresh venv
  [0;33m*[0m Smoke check
  [0;33m*[0m Assemble the real artifact provider registry
  [0;33m*[0m Post Run astral-sh/setup-uv@v4
  [0;33m*[0m Post Check out SASE Rust core
  [0;33m*[0m Post Check out SASE
  [0;33m*[0m Post Run actions/checkout@v4

[0;1;39mANNOTATIONS[0m
[0;33m![0m Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
[38;5;242mbuild: .github#2
[0m
[0;33m![0m Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0a4eEagAAAADZtmRcHu09TbNQl71+FwrXQ08xRURHRTI1MTQARWRnZQ==
[38;5;242mbuild: .github#8
[0m
[0;33m![0m Failed to restore: Cache service responded with 400
[38;5;242mbuild: .github#26
[0m
[0;1;39mRefreshing run status every 3 seconds. Press Ctrl+C to quit.[0m

[0;33m*[0m [0;1;39mmaster[0m Publish · [0;36m32160158404[0m
Triggered via push about 3 minutes ago

[0;1;39mJOBS[0m
[0;32m✓[0m [0;1;39mrelease[0m in 11s (ID [0;36m95786865377[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run googleapis/release-please-action@v5
  [0;32m✓[0m Complete job
[0;32m✓[0m [0;1;39mbuild[0m in 10s (ID [0;36m95786940152[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Run astral-sh/setup-uv@v4
  [0;32m✓[0m Set up Python
  [0;32m✓[0m Build package
  [0;32m✓[0m Run actions/upload-artifact@v4
  [0;32m✓[0m Post Run astral-sh/setup-uv@v4
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[0;33m*[0m [0;1;39minstall-smoke[0m (ID [0;36m95787010707[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Run actions/download-artifact@v4
  [0;32m✓[0m Check out SASE
  [0;32m✓[0m Check out SASE Rust core
  [0;32m✓[0m Run astral-sh/setup-uv@v4
  [0;32m✓[0m Run extractions/setup-just@v2
  [0;32m✓[0m Run dtolnay/rust-toolchain@stable
  [0;32m✓[0m Set up Python
  [0;33m*[0m Install built sase-research-artifacts wheel into a fresh venv
  [0;33m*[0m Smoke check
  [0;33m*[0m Assemble the real artifact provider registry
  [0;33m*[0m Post Run astral-sh/setup-uv@v4
  [0;33m*[0m Post Check out SASE Rust core
  [0;33m*[0m Post Check out SASE
  [0;33m*[0m Post Run actions/checkout@v4

[0;1;39mANNOTATIONS[0m
[0;33m![0m Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
[38;5;242mbuild: .github#2
[0m
[0;33m![0m Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0a4eEagAAAADZtmRcHu09TbNQl71+FwrXQ08xRURHRTI1MTQARWRnZQ==
[38;5;242mbuild: .github#8
[0m
[0;33m![0m Failed to restore: Cache service responded with 400
[38;5;242mbuild: .github#26
[0m
[0;1;39mRefreshing run status every 3 seconds. Press Ctrl+C to quit.[0m

[0;33m*[0m [0;1;39mmaster[0m Publish · [0;36m32160158404[0m
Triggered via push about 3 minutes ago

[0;1;39mJOBS[0m
[0;32m✓[0m [0;1;39mrelease[0m in 11s (ID [0;36m95786865377[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run googleapis/release-please-action@v5
  [0;32m✓[0m Complete job
[0;32m✓[0m [0;1;39mbuild[0m in 10s (ID [0;36m95786940152[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Run astral-sh/setup-uv@v4
  [0;32m✓[0m Set up Python
  [0;32m✓[0m Build package
  [0;32m✓[0m Run actions/upload-artifact@v4
  [0;32m✓[0m Post Run astral-sh/setup-uv@v4
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[0;33m*[0m [0;1;39minstall-smoke[0m (ID [0;36m95787010707[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Run actions/download-artifact@v4
  [0;32m✓[0m Check out SASE
  [0;32m✓[0m Check out SASE Rust core
  [0;32m✓[0m Run astral-sh/setup-uv@v4
  [0;32m✓[0m Run extractions/setup-just@v2
  [0;32m✓[0m Run dtolnay/rust-toolchain@stable
  [0;32m✓[0m Set up Python
  [0;33m*[0m Install built sase-research-artifacts wheel into a fresh venv
  [0;33m*[0m Smoke check
  [0;33m*[0m Assemble the real artifact provider registry
  [0;33m*[0m Post Run astral-sh/setup-uv@v4
  [0;33m*[0m Post Check out SASE Rust core
  [0;33m*[0m Post Check out SASE
  [0;33m*[0m Post Run actions/checkout@v4

[0;1;39mANNOTATIONS[0m
[0;33m![0m Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
[38;5;242mbuild: .github#2
[0m
[0;33m![0m Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0a4eEagAAAADZtmRcHu09TbNQl71+FwrXQ08xRURHRTI1MTQARWRnZQ==
[38;5;242mbuild: .github#8
[0m
[0;33m![0m Failed to restore: Cache service responded with 400
[38;5;242mbuild: .github#26
[0m
[0;1;39mRefreshing run status every 3 seconds. Press Ctrl+C to quit.[0m

[0;33m*[0m [0;1;39mmaster[0m Publish · [0;36m32160158404[0m
Triggered via push about 3 minutes ago

[0;1;39mJOBS[0m
[0;32m✓[0m [0;1;39mrelease[0m in 11s (ID [0;36m95786865377[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run googleapis/release-please-action@v5
  [0;32m✓[0m Complete job
[0;32m✓[0m [0;1;39mbuild[0m in 10s (ID [0;36m95786940152[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Run astral-sh/setup-uv@v4
  [0;32m✓[0m Set up Python
  [0;32m✓[0m Build package
  [0;32m✓[0m Run actions/upload-artifact@v4
  [0;32m✓[0m Post Run astral-sh/setup-uv@v4
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[0;33m*[0m [0;1;39minstall-smoke[0m (ID [0;36m95787010707[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Run actions/download-artifact@v4
  [0;32m✓[0m Check out SASE
  [0;32m✓[0m Check out SASE Rust core
  [0;32m✓[0m Run astral-sh/setup-uv@v4
  [0;32m✓[0m Run extractions/setup-just@v2
  [0;32m✓[0m Run dtolnay/rust-toolchain@stable
  [0;32m✓[0m Set up Python
  [0;33m*[0m Install built sase-research-artifacts wheel into a fresh venv
  [0;33m*[0m Smoke check
  [0;33m*[0m Assemble the real artifact provider registry
  [0;33m*[0m Post Run astral-sh/setup-uv@v4
  [0;33m*[0m Post Check out SASE Rust core
  [0;33m*[0m Post Check out SASE
  [0;33m*[0m Post Run actions/checkout@v4

[0;1;39mANNOTATIONS[0m
[0;33m![0m Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
[38;5;242mbuild: .github#2
[0m
[0;33m![0m Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0a4eEagAAAADZtmRcHu09TbNQl71+FwrXQ08xRURHRTI1MTQARWRnZQ==
[38;5;242mbuild: .github#8
[0m
[0;33m![0m Failed to restore: Cache service responded with 400
[38;5;242mbuild: .github#26
[0m
[0;1;39mRefreshing run status every 3 seconds. Press Ctrl+C to quit.[0m

[0;33m*[0m [0;1;39mmaster[0m Publish · [0;36m32160158404[0m
Triggered via push about 3 minutes ago

[0;1;39mJOBS[0m
[0;32m✓[0m [0;1;39mrelease[0m in 11s (ID [0;36m95786865377[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run googleapis/release-please-action@v5
  [0;32m✓[0m Complete job
[0;32m✓[0m [0;1;39mbuild[0m in 10s (ID [0;36m95786940152[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Run astral-sh/setup-uv@v4
  [0;32m✓[0m Set up Python
  [0;32m✓[0m Build package
  [0;32m✓[0m Run actions/upload-artifact@v4
  [0;32m✓[0m Post Run astral-sh/setup-uv@v4
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[0;33m*[0m [0;1;39minstall-smoke[0m (ID [0;36m95787010707[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Run actions/download-artifact@v4
  [0;32m✓[0m Check out SASE
  [0;32m✓[0m Check out SASE Rust core
  [0;32m✓[0m Run astral-sh/setup-uv@v4
  [0;32m✓[0m Run extractions/setup-just@v2
  [0;32m✓[0m Run dtolnay/rust-toolchain@stable
  [0;32m✓[0m Set up Python
  [0;33m*[0m Install built sase-research-artifacts wheel into a fresh venv
  [0;33m*[0m Smoke check
  [0;33m*[0m Assemble the real artifact provider registry
  [0;33m*[0m Post Run astral-sh/setup-uv@v4
  [0;33m*[0m Post Check out SASE Rust core
  [0;33m*[0m Post Check out SASE
  [0;33m*[0m Post Run actions/checkout@v4

[0;1;39mANNOTATIONS[0m
[0;33m![0m Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
[38;5;242mbuild: .github#2
[0m
[0;33m![0m Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0a4eEagAAAADZtmRcHu09TbNQl71+FwrXQ08xRURHRTI1MTQARWRnZQ==
[38;5;242mbuild: .github#8
[0m
[0;33m![0m Failed to restore: Cache service responded with 400
[38;5;242mbuild: .github#26
[0m
[0;1;39mRefreshing run status every 3 seconds. Press Ctrl+C to quit.[0m

[0;33m*[0m [0;1;39mmaster[0m Publish · [0;36m32160158404[0m
Triggered via push about 3 minutes ago

[0;1;39mJOBS[0m
[0;32m✓[0m [0;1;39mrelease[0m in 11s (ID [0;36m95786865377[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run googleapis/release-please-action@v5
  [0;32m✓[0m Complete job
[0;32m✓[0m [0;1;39mbuild[0m in 10s (ID [0;36m95786940152[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Run astral-sh/setup-uv@v4
  [0;32m✓[0m Set up Python
  [0;32m✓[0m Build package
  [0;32m✓[0m Run actions/upload-artifact@v4
  [0;32m✓[0m Post Run astral-sh/setup-uv@v4
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[0;33m*[0m [0;1;39minstall-smoke[0m (ID [0;36m95787010707[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Run actions/download-artifact@v4
  [0;32m✓[0m Check out SASE
  [0;32m✓[0m Check out SASE Rust core
  [0;32m✓[0m Run astral-sh/setup-uv@v4
  [0;32m✓[0m Run extractions/setup-just@v2
  [0;32m✓[0m Run dtolnay/rust-toolchain@stable
  [0;32m✓[0m Set up Python
  [0;33m*[0m Install built sase-research-artifacts wheel into a fresh venv
  [0;33m*[0m Smoke check
  [0;33m*[0m Assemble the real artifact provider registry
  [0;33m*[0m Post Run astral-sh/setup-uv@v4
  [0;33m*[0m Post Check out SASE Rust core
  [0;33m*[0m Post Check out SASE
  [0;33m*[0m Post Run actions/checkout@v4

[0;1;39mANNOTATIONS[0m
[0;33m![0m Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
[38;5;242mbuild: .github#2
[0m
[0;33m![0m Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0a4eEagAAAADZtmRcHu09TbNQl71+FwrXQ08xRURHRTI1MTQARWRnZQ==
[38;5;242mbuild: .github#8
[0m
[0;33m![0m Failed to restore: Cache service responded with 400
[38;5;242mbuild: .github#26
[0m
[0;1;39mRefreshing run status every 3 seconds. Press Ctrl+C to quit.[0m

[0;33m*[0m [0;1;39mmaster[0m Publish · [0;36m32160158404[0m
Triggered via push about 3 minutes ago

[0;1;39mJOBS[0m
[0;32m✓[0m [0;1;39mrelease[0m in 11s (ID [0;36m95786865377[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run googleapis/release-please-action@v5
  [0;32m✓[0m Complete job
[0;32m✓[0m [0;1;39mbuild[0m in 10s (ID [0;36m95786940152[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Run astral-sh/setup-uv@v4
  [0;32m✓[0m Set up Python
  [0;32m✓[0m Build package
  [0;32m✓[0m Run actions/upload-artifact@v4
  [0;32m✓[0m Post Run astral-sh/setup-uv@v4
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[0;33m*[0m [0;1;39minstall-smoke[0m (ID [0;36m95787010707[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Run actions/download-artifact@v4
  [0;32m✓[0m Check out SASE
  [0;32m✓[0m Check out SASE Rust core
  [0;32m✓[0m Run astral-sh/setup-uv@v4
  [0;32m✓[0m Run extractions/setup-just@v2
  [0;32m✓[0m Run dtolnay/rust-toolchain@stable
  [0;32m✓[0m Set up Python
  [0;33m*[0m Install built sase-research-artifacts wheel into a fresh venv
  [0;33m*[0m Smoke check
  [0;33m*[0m Assemble the real artifact provider registry
  [0;33m*[0m Post Run astral-sh/setup-uv@v4
  [0;33m*[0m Post Check out SASE Rust core
  [0;33m*[0m Post Check out SASE
  [0;33m*[0m Post Run actions/checkout@v4

[0;1;39mANNOTATIONS[0m
[0;33m![0m Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
[38;5;242mbuild: .github#2
[0m
[0;33m![0m Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0a4eEagAAAADZtmRcHu09TbNQl71+FwrXQ08xRURHRTI1MTQARWRnZQ==
[38;5;242mbuild: .github#8
[0m
[0;33m![0m Failed to restore: Cache service responded with 400
[38;5;242mbuild: .github#26
[0m
[0;1;39mRefreshing run status every 3 seconds. Press Ctrl+C to quit.[0m

[0;33m*[0m [0;1;39mmaster[0m Publish · [0;36m32160158404[0m
Triggered via push about 3 minutes ago

[0;1;39mJOBS[0m
[0;32m✓[0m [0;1;39mrelease[0m in 11s (ID [0;36m95786865377[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run googleapis/release-please-action@v5
  [0;32m✓[0m Complete job
[0;32m✓[0m [0;1;39mbuild[0m in 10s (ID [0;36m95786940152[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Run astral-sh/setup-uv@v4
  [0;32m✓[0m Set up Python
  [0;32m✓[0m Build package
  [0;32m✓[0m Run actions/upload-artifact@v4
  [0;32m✓[0m Post Run astral-sh/setup-uv@v4
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[0;33m*[0m [0;1;39minstall-smoke[0m (ID [0;36m95787010707[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Run actions/download-artifact@v4
  [0;32m✓[0m Check out SASE
  [0;32m✓[0m Check out SASE Rust core
  [0;32m✓[0m Run astral-sh/setup-uv@v4
  [0;32m✓[0m Run extractions/setup-just@v2
  [0;32m✓[0m Run dtolnay/rust-toolchain@stable
  [0;32m✓[0m Set up Python
  [0;33m*[0m Install built sase-research-artifacts wheel into a fresh venv
  [0;33m*[0m Smoke check
  [0;33m*[0m Assemble the real artifact provider registry
  [0;33m*[0m Post Run astral-sh/setup-uv@v4
  [0;33m*[0m Post Check out SASE Rust core
  [0;33m*[0m Post Check out SASE
  [0;33m*[0m Post Run actions/checkout@v4

[0;1;39mANNOTATIONS[0m
[0;33m![0m Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
[38;5;242mbuild: .github#2
[0m
[0;33m![0m Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0a4eEagAAAADZtmRcHu09TbNQl71+FwrXQ08xRURHRTI1MTQARWRnZQ==
[38;5;242mbuild: .github#8
[0m
[0;33m![0m Failed to restore: Cache service responded with 400
[38;5;242mbuild: .github#26
[0m
[0;1;39mRefreshing run status every 3 seconds. Press Ctrl+C to quit.[0m

[0;33m*[0m [0;1;39mmaster[0m Publish · [0;36m32160158404[0m
Triggered via push about 3 minutes ago

[0;1;39mJOBS[0m
[0;32m✓[0m [0;1;39mrelease[0m in 11s (ID [0;36m95786865377[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run googleapis/release-please-action@v5
  [0;32m✓[0m Complete job
[0;32m✓[0m [0;1;39mbuild[0m in 10s (ID [0;36m95786940152[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Run astral-sh/setup-uv@v4
  [0;32m✓[0m Set up Python
  [0;32m✓[0m Build package
  [0;32m✓[0m Run actions/upload-artifact@v4
  [0;32m✓[0m Post Run astral-sh/setup-uv@v4
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[0;33m*[0m [0;1;39minstall-smoke[0m (ID [0;36m95787010707[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Run actions/download-artifact@v4
  [0;32m✓[0m Check out SASE
  [0;32m✓[0m Check out SASE Rust core
  [0;32m✓[0m Run astral-sh/setup-uv@v4
  [0;32m✓[0m Run extractions/setup-just@v2
  [0;32m✓[0m Run dtolnay/rust-toolchain@stable
  [0;32m✓[0m Set up Python
  [0;33m*[0m Install built sase-research-artifacts wheel into a fresh venv
  [0;33m*[0m Smoke check
  [0;33m*[0m Assemble the real artifact provider registry
  [0;33m*[0m Post Run astral-sh/setup-uv@v4
  [0;33m*[0m Post Check out SASE Rust core
  [0;33m*[0m Post Check out SASE
  [0;33m*[0m Post Run actions/checkout@v4

[0;1;39mANNOTATIONS[0m
[0;33m![0m Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
[38;5;242mbuild: .github#2
[0m
[0;33m![0m Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0a4eEagAAAADZtmRcHu09TbNQl71+FwrXQ08xRURHRTI1MTQARWRnZQ==
[38;5;242mbuild: .github#8
[0m
[0;33m![0m Failed to restore: Cache service responded with 400
[38;5;242mbuild: .github#26
[0m
[0;1;39mRefreshing run status every 3 seconds. Press Ctrl+C to quit.[0m

[0;33m*[0m [0;1;39mmaster[0m Publish · [0;36m32160158404[0m
Triggered via push about 3 minutes ago

[0;1;39mJOBS[0m
[0;32m✓[0m [0;1;39mrelease[0m in 11s (ID [0;36m95786865377[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run googleapis/release-please-action@v5
  [0;32m✓[0m Complete job
[0;32m✓[0m [0;1;39mbuild[0m in 10s (ID [0;36m95786940152[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Run astral-sh/setup-uv@v4
  [0;32m✓[0m Set up Python
  [0;32m✓[0m Build package
  [0;32m✓[0m Run actions/upload-artifact@v4
  [0;32m✓[0m Post Run astral-sh/setup-uv@v4
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[0;33m*[0m [0;1;39minstall-smoke[0m (ID [0;36m95787010707[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Run actions/download-artifact@v4
  [0;32m✓[0m Check out SASE
  [0;32m✓[0m Check out SASE Rust core
  [0;32m✓[0m Run astral-sh/setup-uv@v4
  [0;32m✓[0m Run extractions/setup-just@v2
  [0;32m✓[0m Run dtolnay/rust-toolchain@stable
  [0;32m✓[0m Set up Python
  [0;33m*[0m Install built sase-research-artifacts wheel into a fresh venv
  [0;33m*[0m Smoke check
  [0;33m*[0m Assemble the real artifact provider registry
  [0;33m*[0m Post Run astral-sh/setup-uv@v4
  [0;33m*[0m Post Check out SASE Rust core
  [0;33m*[0m Post Check out SASE
  [0;33m*[0m Post Run actions/checkout@v4

[0;1;39mANNOTATIONS[0m
[0;33m![0m Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
[38;5;242mbuild: .github#2
[0m
[0;33m![0m Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0a4eEagAAAADZtmRcHu09TbNQl71+FwrXQ08xRURHRTI1MTQARWRnZQ==
[38;5;242mbuild: .github#8
[0m
[0;33m![0m Failed to restore: Cache service responded with 400
[38;5;242mbuild: .github#26
[0m
[0;1;39mRefreshing run status every 3 seconds. Press Ctrl+C to quit.[0m

[0;33m*[0m [0;1;39mmaster[0m Publish · [0;36m32160158404[0m
Triggered via push about 4 minutes ago

[0;1;39mJOBS[0m
[0;32m✓[0m [0;1;39mrelease[0m in 11s (ID [0;36m95786865377[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run googleapis/release-please-action@v5
  [0;32m✓[0m Complete job
[0;32m✓[0m [0;1;39mbuild[0m in 10s (ID [0;36m95786940152[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Run astral-sh/setup-uv@v4
  [0;32m✓[0m Set up Python
  [0;32m✓[0m Build package
  [0;32m✓[0m Run actions/upload-artifact@v4
  [0;32m✓[0m Post Run astral-sh/setup-uv@v4
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[0;33m*[0m [0;1;39minstall-smoke[0m (ID [0;36m95787010707[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Run actions/download-artifact@v4
  [0;32m✓[0m Check out SASE
  [0;32m✓[0m Check out SASE Rust core
  [0;32m✓[0m Run astral-sh/setup-uv@v4
  [0;32m✓[0m Run extractions/setup-just@v2
  [0;32m✓[0m Run dtolnay/rust-toolchain@stable
  [0;32m✓[0m Set up Python
  [0;33m*[0m Install built sase-research-artifacts wheel into a fresh venv
  [0;33m*[0m Smoke check
  [0;33m*[0m Assemble the real artifact provider registry
  [0;33m*[0m Post Run astral-sh/setup-uv@v4
  [0;33m*[0m Post Check out SASE Rust core
  [0;33m*[0m Post Check out SASE
  [0;33m*[0m Post Run actions/checkout@v4

[0;1;39mANNOTATIONS[0m
[0;33m![0m Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
[38;5;242mbuild: .github#2
[0m
[0;33m![0m Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0a4eEagAAAADZtmRcHu09TbNQl71+FwrXQ08xRURHRTI1MTQARWRnZQ==
[38;5;242mbuild: .github#8
[0m
[0;33m![0m Failed to restore: Cache service responded with 400
[38;5;242mbuild: .github#26
[0m
[0;1;39mRefreshing run status every 3 seconds. Press Ctrl+C to quit.[0m

[0;33m*[0m [0;1;39mmaster[0m Publish · [0;36m32160158404[0m
Triggered via push about 4 minutes ago

[0;1;39mJOBS[0m
[0;32m✓[0m [0;1;39mrelease[0m in 11s (ID [0;36m95786865377[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run googleapis/release-please-action@v5
  [0;32m✓[0m Complete job
[0;32m✓[0m [0;1;39mbuild[0m in 10s (ID [0;36m95786940152[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Run astral-sh/setup-uv@v4
  [0;32m✓[0m Set up Python
  [0;32m✓[0m Build package
  [0;32m✓[0m Run actions/upload-artifact@v4
  [0;32m✓[0m Post Run astral-sh/setup-uv@v4
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[0;33m*[0m [0;1;39minstall-smoke[0m (ID [0;36m95787010707[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Run actions/download-artifact@v4
  [0;32m✓[0m Check out SASE
  [0;32m✓[0m Check out SASE Rust core
  [0;32m✓[0m Run astral-sh/setup-uv@v4
  [0;32m✓[0m Run extractions/setup-just@v2
  [0;32m✓[0m Run dtolnay/rust-toolchain@stable
  [0;32m✓[0m Set up Python
  [0;33m*[0m Install built sase-research-artifacts wheel into a fresh venv
  [0;33m*[0m Smoke check
  [0;33m*[0m Assemble the real artifact provider registry
  [0;33m*[0m Post Run astral-sh/setup-uv@v4
  [0;33m*[0m Post Check out SASE Rust core
  [0;33m*[0m Post Check out SASE
  [0;33m*[0m Post Run actions/checkout@v4

[0;1;39mANNOTATIONS[0m
[0;33m![0m Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
[38;5;242mbuild: .github#2
[0m
[0;33m![0m Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0a4eEagAAAADZtmRcHu09TbNQl71+FwrXQ08xRURHRTI1MTQARWRnZQ==
[38;5;242mbuild: .github#8
[0m
[0;33m![0m Failed to restore: Cache service responded with 400
[38;5;242mbuild: .github#26
[0m
[0;1;39mRefreshing run status every 3 seconds. Press Ctrl+C to quit.[0m

[0;33m*[0m [0;1;39mmaster[0m Publish · [0;36m32160158404[0m
Triggered via push about 4 minutes ago

[0;1;39mJOBS[0m
[0;32m✓[0m [0;1;39mrelease[0m in 11s (ID [0;36m95786865377[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run googleapis/release-please-action@v5
  [0;32m✓[0m Complete job
[0;32m✓[0m [0;1;39mbuild[0m in 10s (ID [0;36m95786940152[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Run astral-sh/setup-uv@v4
  [0;32m✓[0m Set up Python
  [0;32m✓[0m Build package
  [0;32m✓[0m Run actions/upload-artifact@v4
  [0;32m✓[0m Post Run astral-sh/setup-uv@v4
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[0;33m*[0m [0;1;39minstall-smoke[0m (ID [0;36m95787010707[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Run actions/download-artifact@v4
  [0;32m✓[0m Check out SASE
  [0;32m✓[0m Check out SASE Rust core
  [0;32m✓[0m Run astral-sh/setup-uv@v4
  [0;32m✓[0m Run extractions/setup-just@v2
  [0;32m✓[0m Run dtolnay/rust-toolchain@stable
  [0;32m✓[0m Set up Python
  [0;33m*[0m Install built sase-research-artifacts wheel into a fresh venv
  [0;33m*[0m Smoke check
  [0;33m*[0m Assemble the real artifact provider registry
  [0;33m*[0m Post Run astral-sh/setup-uv@v4
  [0;33m*[0m Post Check out SASE Rust core
  [0;33m*[0m Post Check out SASE
  [0;33m*[0m Post Run actions/checkout@v4

[0;1;39mANNOTATIONS[0m
[0;33m![0m Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
[38;5;242mbuild: .github#2
[0m
[0;33m![0m Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0a4eEagAAAADZtmRcHu09TbNQl71+FwrXQ08xRURHRTI1MTQARWRnZQ==
[38;5;242mbuild: .github#8
[0m
[0;33m![0m Failed to restore: Cache service responded with 400
[38;5;242mbuild: .github#26
[0m
[0;1;39mRefreshing run status every 3 seconds. Press Ctrl+C to quit.[0m

[0;33m*[0m [0;1;39mmaster[0m Publish · [0;36m32160158404[0m
Triggered via push about 4 minutes ago

[0;1;39mJOBS[0m
[0;32m✓[0m [0;1;39mrelease[0m in 11s (ID [0;36m95786865377[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run googleapis/release-please-action@v5
  [0;32m✓[0m Complete job
[0;32m✓[0m [0;1;39mbuild[0m in 10s (ID [0;36m95786940152[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Run astral-sh/setup-uv@v4
  [0;32m✓[0m Set up Python
  [0;32m✓[0m Build package
  [0;32m✓[0m Run actions/upload-artifact@v4
  [0;32m✓[0m Post Run astral-sh/setup-uv@v4
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[0;33m*[0m [0;1;39minstall-smoke[0m (ID [0;36m95787010707[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Run actions/download-artifact@v4
  [0;32m✓[0m Check out SASE
  [0;32m✓[0m Check out SASE Rust core
  [0;32m✓[0m Run astral-sh/setup-uv@v4
  [0;32m✓[0m Run extractions/setup-just@v2
  [0;32m✓[0m Run dtolnay/rust-toolchain@stable
  [0;32m✓[0m Set up Python
  [0;33m*[0m Install built sase-research-artifacts wheel into a fresh venv
  [0;33m*[0m Smoke check
  [0;33m*[0m Assemble the real artifact provider registry
  [0;33m*[0m Post Run astral-sh/setup-uv@v4
  [0;33m*[0m Post Check out SASE Rust core
  [0;33m*[0m Post Check out SASE
  [0;33m*[0m Post Run actions/checkout@v4

[0;1;39mANNOTATIONS[0m
[0;33m![0m Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
[38;5;242mbuild: .github#2
[0m
[0;33m![0m Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0a4eEagAAAADZtmRcHu09TbNQl71+FwrXQ08xRURHRTI1MTQARWRnZQ==
[38;5;242mbuild: .github#8
[0m
[0;33m![0m Failed to restore: Cache service responded with 400
[38;5;242mbuild: .github#26
[0m
[0;1;39mRefreshing run status every 3 seconds. Press Ctrl+C to quit.[0m

[0;33m*[0m [0;1;39mmaster[0m Publish · [0;36m32160158404[0m
Triggered via push about 4 minutes ago

[0;1;39mJOBS[0m
[0;32m✓[0m [0;1;39mrelease[0m in 11s (ID [0;36m95786865377[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run googleapis/release-please-action@v5
  [0;32m✓[0m Complete job
[0;32m✓[0m [0;1;39mbuild[0m in 10s (ID [0;36m95786940152[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Run astral-sh/setup-uv@v4
  [0;32m✓[0m Set up Python
  [0;32m✓[0m Build package
  [0;32m✓[0m Run actions/upload-artifact@v4
  [0;32m✓[0m Post Run astral-sh/setup-uv@v4
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[0;33m*[0m [0;1;39minstall-smoke[0m (ID [0;36m95787010707[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Run actions/download-artifact@v4
  [0;32m✓[0m Check out SASE
  [0;32m✓[0m Check out SASE Rust core
  [0;32m✓[0m Run astral-sh/setup-uv@v4
  [0;32m✓[0m Run extractions/setup-just@v2
  [0;32m✓[0m Run dtolnay/rust-toolchain@stable
  [0;32m✓[0m Set up Python
  [0;33m*[0m Install built sase-research-artifacts wheel into a fresh venv
  [0;33m*[0m Smoke check
  [0;33m*[0m Assemble the real artifact provider registry
  [0;33m*[0m Post Run astral-sh/setup-uv@v4
  [0;33m*[0m Post Check out SASE Rust core
  [0;33m*[0m Post Check out SASE
  [0;33m*[0m Post Run actions/checkout@v4

[0;1;39mANNOTATIONS[0m
[0;33m![0m Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
[38;5;242mbuild: .github#2
[0m
[0;33m![0m Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0a4eEagAAAADZtmRcHu09TbNQl71+FwrXQ08xRURHRTI1MTQARWRnZQ==
[38;5;242mbuild: .github#8
[0m
[0;33m![0m Failed to restore: Cache service responded with 400
[38;5;242mbuild: .github#26
[0m
[0;1;39mRefreshing run status every 3 seconds. Press Ctrl+C to quit.[0m

[0;33m*[0m [0;1;39mmaster[0m Publish · [0;36m32160158404[0m
Triggered via push about 4 minutes ago

[0;1;39mJOBS[0m
[0;32m✓[0m [0;1;39mrelease[0m in 11s (ID [0;36m95786865377[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run googleapis/release-please-action@v5
  [0;32m✓[0m Complete job
[0;32m✓[0m [0;1;39mbuild[0m in 10s (ID [0;36m95786940152[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Run astral-sh/setup-uv@v4
  [0;32m✓[0m Set up Python
  [0;32m✓[0m Build package
  [0;32m✓[0m Run actions/upload-artifact@v4
  [0;32m✓[0m Post Run astral-sh/setup-uv@v4
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[0;33m*[0m [0;1;39minstall-smoke[0m (ID [0;36m95787010707[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Run actions/download-artifact@v4
  [0;32m✓[0m Check out SASE
  [0;32m✓[0m Check out SASE Rust core
  [0;32m✓[0m Run astral-sh/setup-uv@v4
  [0;32m✓[0m Run extractions/setup-just@v2
  [0;32m✓[0m Run dtolnay/rust-toolchain@stable
  [0;32m✓[0m Set up Python
  [0;33m*[0m Install built sase-research-artifacts wheel into a fresh venv
  [0;33m*[0m Smoke check
  [0;33m*[0m Assemble the real artifact provider registry
  [0;33m*[0m Post Run astral-sh/setup-uv@v4
  [0;33m*[0m Post Check out SASE Rust core
  [0;33m*[0m Post Check out SASE
  [0;33m*[0m Post Run actions/checkout@v4

[0;1;39mANNOTATIONS[0m
[0;33m![0m Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
[38;5;242mbuild: .github#2
[0m
[0;33m![0m Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0a4eEagAAAADZtmRcHu09TbNQl71+FwrXQ08xRURHRTI1MTQARWRnZQ==
[38;5;242mbuild: .github#8
[0m
[0;33m![0m Failed to restore: Cache service responded with 400
[38;5;242mbuild: .github#26
[0m
[0;1;39mRefreshing run status every 3 seconds. Press Ctrl+C to quit.[0m

[0;33m*[0m [0;1;39mmaster[0m Publish · [0;36m32160158404[0m
Triggered via push about 4 minutes ago

[0;1;39mJOBS[0m
[0;32m✓[0m [0;1;39mrelease[0m in 11s (ID [0;36m95786865377[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run googleapis/release-please-action@v5
  [0;32m✓[0m Complete job
[0;32m✓[0m [0;1;39mbuild[0m in 10s (ID [0;36m95786940152[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Run astral-sh/setup-uv@v4
  [0;32m✓[0m Set up Python
  [0;32m✓[0m Build package
  [0;32m✓[0m Run actions/upload-artifact@v4
  [0;32m✓[0m Post Run astral-sh/setup-uv@v4
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[0;33m*[0m [0;1;39minstall-smoke[0m (ID [0;36m95787010707[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Run actions/download-artifact@v4
  [0;32m✓[0m Check out SASE
  [0;32m✓[0m Check out SASE Rust core
  [0;32m✓[0m Run astral-sh/setup-uv@v4
  [0;32m✓[0m Run extractions/setup-just@v2
  [0;32m✓[0m Run dtolnay/rust-toolchain@stable
  [0;32m✓[0m Set up Python
  [0;33m*[0m Install built sase-research-artifacts wheel into a fresh venv
  [0;33m*[0m Smoke check
  [0;33m*[0m Assemble the real artifact provider registry
  [0;33m*[0m Post Run astral-sh/setup-uv@v4
  [0;33m*[0m Post Check out SASE Rust core
  [0;33m*[0m Post Check out SASE
  [0;33m*[0m Post Run actions/checkout@v4

[0;1;39mANNOTATIONS[0m
[0;33m![0m Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
[38;5;242mbuild: .github#2
[0m
[0;33m![0m Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0a4eEagAAAADZtmRcHu09TbNQl71+FwrXQ08xRURHRTI1MTQARWRnZQ==
[38;5;242mbuild: .github#8
[0m
[0;33m![0m Failed to restore: Cache service responded with 400
[38;5;242mbuild: .github#26
[0m
[0;1;39mRefreshing run status every 3 seconds. Press Ctrl+C to quit.[0m

[0;33m*[0m [0;1;39mmaster[0m Publish · [0;36m32160158404[0m
Triggered via push about 4 minutes ago

[0;1;39mJOBS[0m
[0;32m✓[0m [0;1;39mrelease[0m in 11s (ID [0;36m95786865377[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run googleapis/release-please-action@v5
  [0;32m✓[0m Complete job
[0;32m✓[0m [0;1;39mbuild[0m in 10s (ID [0;36m95786940152[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Run astral-sh/setup-uv@v4
  [0;32m✓[0m Set up Python
  [0;32m✓[0m Build package
  [0;32m✓[0m Run actions/upload-artifact@v4
  [0;32m✓[0m Post Run astral-sh/setup-uv@v4
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[0;33m*[0m [0;1;39minstall-smoke[0m (ID [0;36m95787010707[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Run actions/download-artifact@v4
  [0;32m✓[0m Check out SASE
  [0;32m✓[0m Check out SASE Rust core
  [0;32m✓[0m Run astral-sh/setup-uv@v4
  [0;32m✓[0m Run extractions/setup-just@v2
  [0;32m✓[0m Run dtolnay/rust-toolchain@stable
  [0;32m✓[0m Set up Python
  [0;33m*[0m Install built sase-research-artifacts wheel into a fresh venv
  [0;33m*[0m Smoke check
  [0;33m*[0m Assemble the real artifact provider registry
  [0;33m*[0m Post Run astral-sh/setup-uv@v4
  [0;33m*[0m Post Check out SASE Rust core
  [0;33m*[0m Post Check out SASE
  [0;33m*[0m Post Run actions/checkout@v4

[0;1;39mANNOTATIONS[0m
[0;33m![0m Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
[38;5;242mbuild: .github#2
[0m
[0;33m![0m Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0a4eEagAAAADZtmRcHu09TbNQl71+FwrXQ08xRURHRTI1MTQARWRnZQ==
[38;5;242mbuild: .github#8
[0m
[0;33m![0m Failed to restore: Cache service responded with 400
[38;5;242mbuild: .github#26
[0m
[0;1;39mRefreshing run status every 3 seconds. Press Ctrl+C to quit.[0m

[0;33m*[0m [0;1;39mmaster[0m Publish · [0;36m32160158404[0m
Triggered via push about 4 minutes ago

[0;1;39mJOBS[0m
[0;32m✓[0m [0;1;39mrelease[0m in 11s (ID [0;36m95786865377[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run googleapis/release-please-action@v5
  [0;32m✓[0m Complete job
[0;32m✓[0m [0;1;39mbuild[0m in 10s (ID [0;36m95786940152[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Run astral-sh/setup-uv@v4
  [0;32m✓[0m Set up Python
  [0;32m✓[0m Build package
  [0;32m✓[0m Run actions/upload-artifact@v4
  [0;32m✓[0m Post Run astral-sh/setup-uv@v4
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[0;33m*[0m [0;1;39minstall-smoke[0m (ID [0;36m95787010707[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Run actions/download-artifact@v4
  [0;32m✓[0m Check out SASE
  [0;32m✓[0m Check out SASE Rust core
  [0;32m✓[0m Run astral-sh/setup-uv@v4
  [0;32m✓[0m Run extractions/setup-just@v2
  [0;32m✓[0m Run dtolnay/rust-toolchain@stable
  [0;32m✓[0m Set up Python
  [0;33m*[0m Install built sase-research-artifacts wheel into a fresh venv
  [0;33m*[0m Smoke check
  [0;33m*[0m Assemble the real artifact provider registry
  [0;33m*[0m Post Run astral-sh/setup-uv@v4
  [0;33m*[0m Post Check out SASE Rust core
  [0;33m*[0m Post Check out SASE
  [0;33m*[0m Post Run actions/checkout@v4

[0;1;39mANNOTATIONS[0m
[0;33m![0m Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
[38;5;242mbuild: .github#2
[0m
[0;33m![0m Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0a4eEagAAAADZtmRcHu09TbNQl71+FwrXQ08xRURHRTI1MTQARWRnZQ==
[38;5;242mbuild: .github#8
[0m
[0;33m![0m Failed to restore: Cache service responded with 400
[38;5;242mbuild: .github#26
[0m
[0;1;39mRefreshing run status every 3 seconds. Press Ctrl+C to quit.[0m

[0;33m*[0m [0;1;39mmaster[0m Publish · [0;36m32160158404[0m
Triggered via push about 4 minutes ago

[0;1;39mJOBS[0m
[0;32m✓[0m [0;1;39mrelease[0m in 11s (ID [0;36m95786865377[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run googleapis/release-please-action@v5
  [0;32m✓[0m Complete job
[0;32m✓[0m [0;1;39mbuild[0m in 10s (ID [0;36m95786940152[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Run astral-sh/setup-uv@v4
  [0;32m✓[0m Set up Python
  [0;32m✓[0m Build package
  [0;32m✓[0m Run actions/upload-artifact@v4
  [0;32m✓[0m Post Run astral-sh/setup-uv@v4
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[0;33m*[0m [0;1;39minstall-smoke[0m (ID [0;36m95787010707[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Run actions/download-artifact@v4
  [0;32m✓[0m Check out SASE
  [0;32m✓[0m Check out SASE Rust core
  [0;32m✓[0m Run astral-sh/setup-uv@v4
  [0;32m✓[0m Run extractions/setup-just@v2
  [0;32m✓[0m Run dtolnay/rust-toolchain@stable
  [0;32m✓[0m Set up Python
  [0;33m*[0m Install built sase-research-artifacts wheel into a fresh venv
  [0;33m*[0m Smoke check
  [0;33m*[0m Assemble the real artifact provider registry
  [0;33m*[0m Post Run astral-sh/setup-uv@v4
  [0;33m*[0m Post Check out SASE Rust core
  [0;33m*[0m Post Check out SASE
  [0;33m*[0m Post Run actions/checkout@v4

[0;1;39mANNOTATIONS[0m
[0;33m![0m Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
[38;5;242mbuild: .github#2
[0m
[0;33m![0m Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0a4eEagAAAADZtmRcHu09TbNQl71+FwrXQ08xRURHRTI1MTQARWRnZQ==
[38;5;242mbuild: .github#8
[0m
[0;33m![0m Failed to restore: Cache service responded with 400
[38;5;242mbuild: .github#26
[0m
[0;1;39mRefreshing run status every 3 seconds. Press Ctrl+C to quit.[0m

[0;33m*[0m [0;1;39mmaster[0m Publish · [0;36m32160158404[0m
Triggered via push about 4 minutes ago

[0;1;39mJOBS[0m
[0;32m✓[0m [0;1;39mrelease[0m in 11s (ID [0;36m95786865377[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run googleapis/release-please-action@v5
  [0;32m✓[0m Complete job
[0;32m✓[0m [0;1;39mbuild[0m in 10s (ID [0;36m95786940152[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Run astral-sh/setup-uv@v4
  [0;32m✓[0m Set up Python
  [0;32m✓[0m Build package
  [0;32m✓[0m Run actions/upload-artifact@v4
  [0;32m✓[0m Post Run astral-sh/setup-uv@v4
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[0;33m*[0m [0;1;39minstall-smoke[0m (ID [0;36m95787010707[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Run actions/download-artifact@v4
  [0;32m✓[0m Check out SASE
  [0;32m✓[0m Check out SASE Rust core
  [0;32m✓[0m Run astral-sh/setup-uv@v4
  [0;32m✓[0m Run extractions/setup-just@v2
  [0;32m✓[0m Run dtolnay/rust-toolchain@stable
  [0;32m✓[0m Set up Python
  [0;33m*[0m Install built sase-research-artifacts wheel into a fresh venv
  [0;33m*[0m Smoke check
  [0;33m*[0m Assemble the real artifact provider registry
  [0;33m*[0m Post Run astral-sh/setup-uv@v4
  [0;33m*[0m Post Check out SASE Rust core
  [0;33m*[0m Post Check out SASE
  [0;33m*[0m Post Run actions/checkout@v4

[0;1;39mANNOTATIONS[0m
[0;33m![0m Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
[38;5;242mbuild: .github#2
[0m
[0;33m![0m Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0a4eEagAAAADZtmRcHu09TbNQl71+FwrXQ08xRURHRTI1MTQARWRnZQ==
[38;5;242mbuild: .github#8
[0m
[0;33m![0m Failed to restore: Cache service responded with 400
[38;5;242mbuild: .github#26
[0m
[0;1;39mRefreshing run status every 3 seconds. Press Ctrl+C to quit.[0m

[0;33m*[0m [0;1;39mmaster[0m Publish · [0;36m32160158404[0m
Triggered via push about 4 minutes ago

[0;1;39mJOBS[0m
[0;32m✓[0m [0;1;39mrelease[0m in 11s (ID [0;36m95786865377[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run googleapis/release-please-action@v5
  [0;32m✓[0m Complete job
[0;32m✓[0m [0;1;39mbuild[0m in 10s (ID [0;36m95786940152[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Run astral-sh/setup-uv@v4
  [0;32m✓[0m Set up Python
  [0;32m✓[0m Build package
  [0;32m✓[0m Run actions/upload-artifact@v4
  [0;32m✓[0m Post Run astral-sh/setup-uv@v4
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[0;33m*[0m [0;1;39minstall-smoke[0m (ID [0;36m95787010707[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Run actions/download-artifact@v4
  [0;32m✓[0m Check out SASE
  [0;32m✓[0m Check out SASE Rust core
  [0;32m✓[0m Run astral-sh/setup-uv@v4
  [0;32m✓[0m Run extractions/setup-just@v2
  [0;32m✓[0m Run dtolnay/rust-toolchain@stable
  [0;32m✓[0m Set up Python
  [0;33m*[0m Install built sase-research-artifacts wheel into a fresh venv
  [0;33m*[0m Smoke check
  [0;33m*[0m Assemble the real artifact provider registry
  [0;33m*[0m Post Run astral-sh/setup-uv@v4
  [0;33m*[0m Post Check out SASE Rust core
  [0;33m*[0m Post Check out SASE
  [0;33m*[0m Post Run actions/checkout@v4

[0;1;39mANNOTATIONS[0m
[0;33m![0m Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
[38;5;242mbuild: .github#2
[0m
[0;33m![0m Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0a4eEagAAAADZtmRcHu09TbNQl71+FwrXQ08xRURHRTI1MTQARWRnZQ==
[38;5;242mbuild: .github#8
[0m
[0;33m![0m Failed to restore: Cache service responded with 400
[38;5;242mbuild: .github#26
[0m
[0;1;39mRefreshing run status every 3 seconds. Press Ctrl+C to quit.[0m

[0;33m*[0m [0;1;39mmaster[0m Publish · [0;36m32160158404[0m
Triggered via push about 4 minutes ago

[0;1;39mJOBS[0m
[0;32m✓[0m [0;1;39mrelease[0m in 11s (ID [0;36m95786865377[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run googleapis/release-please-action@v5
  [0;32m✓[0m Complete job
[0;32m✓[0m [0;1;39mbuild[0m in 10s (ID [0;36m95786940152[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Run astral-sh/setup-uv@v4
  [0;32m✓[0m Set up Python
  [0;32m✓[0m Build package
  [0;32m✓[0m Run actions/upload-artifact@v4
  [0;32m✓[0m Post Run astral-sh/setup-uv@v4
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[0;33m*[0m [0;1;39minstall-smoke[0m (ID [0;36m95787010707[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Run actions/download-artifact@v4
  [0;32m✓[0m Check out SASE
  [0;32m✓[0m Check out SASE Rust core
  [0;32m✓[0m Run astral-sh/setup-uv@v4
  [0;32m✓[0m Run extractions/setup-just@v2
  [0;32m✓[0m Run dtolnay/rust-toolchain@stable
  [0;32m✓[0m Set up Python
  [0;33m*[0m Install built sase-research-artifacts wheel into a fresh venv
  [0;33m*[0m Smoke check
  [0;33m*[0m Assemble the real artifact provider registry
  [0;33m*[0m Post Run astral-sh/setup-uv@v4
  [0;33m*[0m Post Check out SASE Rust core
  [0;33m*[0m Post Check out SASE
  [0;33m*[0m Post Run actions/checkout@v4

[0;1;39mANNOTATIONS[0m
[0;33m![0m Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
[38;5;242mbuild: .github#2
[0m
[0;33m![0m Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0a4eEagAAAADZtmRcHu09TbNQl71+FwrXQ08xRURHRTI1MTQARWRnZQ==
[38;5;242mbuild: .github#8
[0m
[0;33m![0m Failed to restore: Cache service responded with 400
[38;5;242mbuild: .github#26
[0m
[0;1;39mRefreshing run status every 3 seconds. Press Ctrl+C to quit.[0m

[0;33m*[0m [0;1;39mmaster[0m Publish · [0;36m32160158404[0m
Triggered via push about 4 minutes ago

[0;1;39mJOBS[0m
[0;32m✓[0m [0;1;39mrelease[0m in 11s (ID [0;36m95786865377[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run googleapis/release-please-action@v5
  [0;32m✓[0m Complete job
[0;32m✓[0m [0;1;39mbuild[0m in 10s (ID [0;36m95786940152[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Run astral-sh/setup-uv@v4
  [0;32m✓[0m Set up Python
  [0;32m✓[0m Build package
  [0;32m✓[0m Run actions/upload-artifact@v4
  [0;32m✓[0m Post Run astral-sh/setup-uv@v4
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[0;33m*[0m [0;1;39minstall-smoke[0m (ID [0;36m95787010707[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Run actions/download-artifact@v4
  [0;32m✓[0m Check out SASE
  [0;32m✓[0m Check out SASE Rust core
  [0;32m✓[0m Run astral-sh/setup-uv@v4
  [0;32m✓[0m Run extractions/setup-just@v2
  [0;32m✓[0m Run dtolnay/rust-toolchain@stable
  [0;32m✓[0m Set up Python
  [0;33m*[0m Install built sase-research-artifacts wheel into a fresh venv
  [0;33m*[0m Smoke check
  [0;33m*[0m Assemble the real artifact provider registry
  [0;33m*[0m Post Run astral-sh/setup-uv@v4
  [0;33m*[0m Post Check out SASE Rust core
  [0;33m*[0m Post Check out SASE
  [0;33m*[0m Post Run actions/checkout@v4

[0;1;39mANNOTATIONS[0m
[0;33m![0m Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
[38;5;242mbuild: .github#2
[0m
[0;33m![0m Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0a4eEagAAAADZtmRcHu09TbNQl71+FwrXQ08xRURHRTI1MTQARWRnZQ==
[38;5;242mbuild: .github#8
[0m
[0;33m![0m Failed to restore: Cache service responded with 400
[38;5;242mbuild: .github#26
[0m
[0;1;39mRefreshing run status every 3 seconds. Press Ctrl+C to quit.[0m

[0;33m*[0m [0;1;39mmaster[0m Publish · [0;36m32160158404[0m
Triggered via push about 4 minutes ago

[0;1;39mJOBS[0m
[0;32m✓[0m [0;1;39mrelease[0m in 11s (ID [0;36m95786865377[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run googleapis/release-please-action@v5
  [0;32m✓[0m Complete job
[0;32m✓[0m [0;1;39mbuild[0m in 10s (ID [0;36m95786940152[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Run astral-sh/setup-uv@v4
  [0;32m✓[0m Set up Python
  [0;32m✓[0m Build package
  [0;32m✓[0m Run actions/upload-artifact@v4
  [0;32m✓[0m Post Run astral-sh/setup-uv@v4
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[0;33m*[0m [0;1;39minstall-smoke[0m (ID [0;36m95787010707[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Run actions/download-artifact@v4
  [0;32m✓[0m Check out SASE
  [0;32m✓[0m Check out SASE Rust core
  [0;32m✓[0m Run astral-sh/setup-uv@v4
  [0;32m✓[0m Run extractions/setup-just@v2
  [0;32m✓[0m Run dtolnay/rust-toolchain@stable
  [0;32m✓[0m Set up Python
  [0;33m*[0m Install built sase-research-artifacts wheel into a fresh venv
  [0;33m*[0m Smoke check
  [0;33m*[0m Assemble the real artifact provider registry
  [0;33m*[0m Post Run astral-sh/setup-uv@v4
  [0;33m*[0m Post Check out SASE Rust core
  [0;33m*[0m Post Check out SASE
  [0;33m*[0m Post Run actions/checkout@v4

[0;1;39mANNOTATIONS[0m
[0;33m![0m Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
[38;5;242mbuild: .github#2
[0m
[0;33m![0m Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0a4eEagAAAADZtmRcHu09TbNQl71+FwrXQ08xRURHRTI1MTQARWRnZQ==
[38;5;242mbuild: .github#8
[0m
[0;33m![0m Failed to restore: Cache service responded with 400
[38;5;242mbuild: .github#26
[0m
[0;1;39mRefreshing run status every 3 seconds. Press Ctrl+C to quit.[0m

[0;33m*[0m [0;1;39mmaster[0m Publish · [0;36m32160158404[0m
Triggered via push about 4 minutes ago

[0;1;39mJOBS[0m
[0;32m✓[0m [0;1;39mrelease[0m in 11s (ID [0;36m95786865377[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run googleapis/release-please-action@v5
  [0;32m✓[0m Complete job
[0;32m✓[0m [0;1;39mbuild[0m in 10s (ID [0;36m95786940152[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Run astral-sh/setup-uv@v4
  [0;32m✓[0m Set up Python
  [0;32m✓[0m Build package
  [0;32m✓[0m Run actions/upload-artifact@v4
  [0;32m✓[0m Post Run astral-sh/setup-uv@v4
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[0;33m*[0m [0;1;39minstall-smoke[0m (ID [0;36m95787010707[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Run actions/download-artifact@v4
  [0;32m✓[0m Check out SASE
  [0;32m✓[0m Check out SASE Rust core
  [0;32m✓[0m Run astral-sh/setup-uv@v4
  [0;32m✓[0m Run extractions/setup-just@v2
  [0;32m✓[0m Run dtolnay/rust-toolchain@stable
  [0;32m✓[0m Set up Python
  [0;33m*[0m Install built sase-research-artifacts wheel into a fresh venv
  [0;33m*[0m Smoke check
  [0;33m*[0m Assemble the real artifact provider registry
  [0;33m*[0m Post Run astral-sh/setup-uv@v4
  [0;33m*[0m Post Check out SASE Rust core
  [0;33m*[0m Post Check out SASE
  [0;33m*[0m Post Run actions/checkout@v4

[0;1;39mANNOTATIONS[0m
[0;33m![0m Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
[38;5;242mbuild: .github#2
[0m
[0;33m![0m Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0a4eEagAAAADZtmRcHu09TbNQl71+FwrXQ08xRURHRTI1MTQARWRnZQ==
[38;5;242mbuild: .github#8
[0m
[0;33m![0m Failed to restore: Cache service responded with 400
[38;5;242mbuild: .github#26
[0m
[0;1;39mRefreshing run status every 3 seconds. Press Ctrl+C to quit.[0m

[0;33m*[0m [0;1;39mmaster[0m Publish · [0;36m32160158404[0m
Triggered via push about 5 minutes ago

[0;1;39mJOBS[0m
[0;32m✓[0m [0;1;39mrelease[0m in 11s (ID [0;36m95786865377[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run googleapis/release-please-action@v5
  [0;32m✓[0m Complete job
[0;32m✓[0m [0;1;39mbuild[0m in 10s (ID [0;36m95786940152[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Run astral-sh/setup-uv@v4
  [0;32m✓[0m Set up Python
  [0;32m✓[0m Build package
  [0;32m✓[0m Run actions/upload-artifact@v4
  [0;32m✓[0m Post Run astral-sh/setup-uv@v4
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[0;33m*[0m [0;1;39minstall-smoke[0m (ID [0;36m95787010707[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Run actions/download-artifact@v4
  [0;32m✓[0m Check out SASE
  [0;32m✓[0m Check out SASE Rust core
  [0;32m✓[0m Run astral-sh/setup-uv@v4
  [0;32m✓[0m Run extractions/setup-just@v2
  [0;32m✓[0m Run dtolnay/rust-toolchain@stable
  [0;32m✓[0m Set up Python
  [0;33m*[0m Install built sase-research-artifacts wheel into a fresh venv
  [0;33m*[0m Smoke check
  [0;33m*[0m Assemble the real artifact provider registry
  [0;33m*[0m Post Run astral-sh/setup-uv@v4
  [0;33m*[0m Post Check out SASE Rust core
  [0;33m*[0m Post Check out SASE
  [0;33m*[0m Post Run actions/checkout@v4

[0;1;39mANNOTATIONS[0m
[0;33m![0m Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
[38;5;242mbuild: .github#2
[0m
[0;33m![0m Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0a4eEagAAAADZtmRcHu09TbNQl71+FwrXQ08xRURHRTI1MTQARWRnZQ==
[38;5;242mbuild: .github#8
[0m
[0;33m![0m Failed to restore: Cache service responded with 400
[38;5;242mbuild: .github#26
[0m
[0;1;39mRefreshing run status every 3 seconds. Press Ctrl+C to quit.[0m

[0;33m*[0m [0;1;39mmaster[0m Publish · [0;36m32160158404[0m
Triggered via push about 5 minutes ago

[0;1;39mJOBS[0m
[0;32m✓[0m [0;1;39mrelease[0m in 11s (ID [0;36m95786865377[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run googleapis/release-please-action@v5
  [0;32m✓[0m Complete job
[0;32m✓[0m [0;1;39mbuild[0m in 10s (ID [0;36m95786940152[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Run astral-sh/setup-uv@v4
  [0;32m✓[0m Set up Python
  [0;32m✓[0m Build package
  [0;32m✓[0m Run actions/upload-artifact@v4
  [0;32m✓[0m Post Run astral-sh/setup-uv@v4
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[0;33m*[0m [0;1;39minstall-smoke[0m (ID [0;36m95787010707[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Run actions/download-artifact@v4
  [0;32m✓[0m Check out SASE
  [0;32m✓[0m Check out SASE Rust core
  [0;32m✓[0m Run astral-sh/setup-uv@v4
  [0;32m✓[0m Run extractions/setup-just@v2
  [0;32m✓[0m Run dtolnay/rust-toolchain@stable
  [0;32m✓[0m Set up Python
  [0;33m*[0m Install built sase-research-artifacts wheel into a fresh venv
  [0;33m*[0m Smoke check
  [0;33m*[0m Assemble the real artifact provider registry
  [0;33m*[0m Post Run astral-sh/setup-uv@v4
  [0;33m*[0m Post Check out SASE Rust core
  [0;33m*[0m Post Check out SASE
  [0;33m*[0m Post Run actions/checkout@v4

[0;1;39mANNOTATIONS[0m
[0;33m![0m Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
[38;5;242mbuild: .github#2
[0m
[0;33m![0m Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0a4eEagAAAADZtmRcHu09TbNQl71+FwrXQ08xRURHRTI1MTQARWRnZQ==
[38;5;242mbuild: .github#8
[0m
[0;33m![0m Failed to restore: Cache service responded with 400
[38;5;242mbuild: .github#26
[0m
[0;1;39mRefreshing run status every 3 seconds. Press Ctrl+C to quit.[0m

[0;33m*[0m [0;1;39mmaster[0m Publish · [0;36m32160158404[0m
Triggered via push about 5 minutes ago

[0;1;39mJOBS[0m
[0;32m✓[0m [0;1;39mrelease[0m in 11s (ID [0;36m95786865377[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run googleapis/release-please-action@v5
  [0;32m✓[0m Complete job
[0;32m✓[0m [0;1;39mbuild[0m in 10s (ID [0;36m95786940152[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Run astral-sh/setup-uv@v4
  [0;32m✓[0m Set up Python
  [0;32m✓[0m Build package
  [0;32m✓[0m Run actions/upload-artifact@v4
  [0;32m✓[0m Post Run astral-sh/setup-uv@v4
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[0;33m*[0m [0;1;39minstall-smoke[0m (ID [0;36m95787010707[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Run actions/download-artifact@v4
  [0;32m✓[0m Check out SASE
  [0;32m✓[0m Check out SASE Rust core
  [0;32m✓[0m Run astral-sh/setup-uv@v4
  [0;32m✓[0m Run extractions/setup-just@v2
  [0;32m✓[0m Run dtolnay/rust-toolchain@stable
  [0;32m✓[0m Set up Python
  [0;33m*[0m Install built sase-research-artifacts wheel into a fresh venv
  [0;33m*[0m Smoke check
  [0;33m*[0m Assemble the real artifact provider registry
  [0;33m*[0m Post Run astral-sh/setup-uv@v4
  [0;33m*[0m Post Check out SASE Rust core
  [0;33m*[0m Post Check out SASE
  [0;33m*[0m Post Run actions/checkout@v4

[0;1;39mANNOTATIONS[0m
[0;33m![0m Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
[38;5;242mbuild: .github#2
[0m
[0;33m![0m Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0a4eEagAAAADZtmRcHu09TbNQl71+FwrXQ08xRURHRTI1MTQARWRnZQ==
[38;5;242mbuild: .github#8
[0m
[0;33m![0m Failed to restore: Cache service responded with 400
[38;5;242mbuild: .github#26
[0m
[0;1;39mRefreshing run status every 3 seconds. Press Ctrl+C to quit.[0m

[0;33m*[0m [0;1;39mmaster[0m Publish · [0;36m32160158404[0m
Triggered via push about 5 minutes ago

[0;1;39mJOBS[0m
[0;32m✓[0m [0;1;39mrelease[0m in 11s (ID [0;36m95786865377[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run googleapis/release-please-action@v5
  [0;32m✓[0m Complete job
[0;32m✓[0m [0;1;39mbuild[0m in 10s (ID [0;36m95786940152[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Run astral-sh/setup-uv@v4
  [0;32m✓[0m Set up Python
  [0;32m✓[0m Build package
  [0;32m✓[0m Run actions/upload-artifact@v4
  [0;32m✓[0m Post Run astral-sh/setup-uv@v4
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[0;33m*[0m [0;1;39minstall-smoke[0m (ID [0;36m95787010707[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Run actions/download-artifact@v4
  [0;32m✓[0m Check out SASE
  [0;32m✓[0m Check out SASE Rust core
  [0;32m✓[0m Run astral-sh/setup-uv@v4
  [0;32m✓[0m Run extractions/setup-just@v2
  [0;32m✓[0m Run dtolnay/rust-toolchain@stable
  [0;32m✓[0m Set up Python
  [0;33m*[0m Install built sase-research-artifacts wheel into a fresh venv
  [0;33m*[0m Smoke check
  [0;33m*[0m Assemble the real artifact provider registry
  [0;33m*[0m Post Run astral-sh/setup-uv@v4
  [0;33m*[0m Post Check out SASE Rust core
  [0;33m*[0m Post Check out SASE
  [0;33m*[0m Post Run actions/checkout@v4

[0;1;39mANNOTATIONS[0m
[0;33m![0m Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
[38;5;242mbuild: .github#2
[0m
[0;33m![0m Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0a4eEagAAAADZtmRcHu09TbNQl71+FwrXQ08xRURHRTI1MTQARWRnZQ==
[38;5;242mbuild: .github#8
[0m
[0;33m![0m Failed to restore: Cache service responded with 400
[38;5;242mbuild: .github#26
[0m
[0;1;39mRefreshing run status every 3 seconds. Press Ctrl+C to quit.[0m

[0;33m*[0m [0;1;39mmaster[0m Publish · [0;36m32160158404[0m
Triggered via push about 5 minutes ago

[0;1;39mJOBS[0m
[0;32m✓[0m [0;1;39mrelease[0m in 11s (ID [0;36m95786865377[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run googleapis/release-please-action@v5
  [0;32m✓[0m Complete job
[0;32m✓[0m [0;1;39mbuild[0m in 10s (ID [0;36m95786940152[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Run astral-sh/setup-uv@v4
  [0;32m✓[0m Set up Python
  [0;32m✓[0m Build package
  [0;32m✓[0m Run actions/upload-artifact@v4
  [0;32m✓[0m Post Run astral-sh/setup-uv@v4
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[0;33m*[0m [0;1;39minstall-smoke[0m (ID [0;36m95787010707[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Run actions/download-artifact@v4
  [0;32m✓[0m Check out SASE
  [0;32m✓[0m Check out SASE Rust core
  [0;32m✓[0m Run astral-sh/setup-uv@v4
  [0;32m✓[0m Run extractions/setup-just@v2
  [0;32m✓[0m Run dtolnay/rust-toolchain@stable
  [0;32m✓[0m Set up Python
  [0;33m*[0m Install built sase-research-artifacts wheel into a fresh venv
  [0;33m*[0m Smoke check
  [0;33m*[0m Assemble the real artifact provider registry
  [0;33m*[0m Post Run astral-sh/setup-uv@v4
  [0;33m*[0m Post Check out SASE Rust core
  [0;33m*[0m Post Check out SASE
  [0;33m*[0m Post Run actions/checkout@v4

[0;1;39mANNOTATIONS[0m
[0;33m![0m Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
[38;5;242mbuild: .github#2
[0m
[0;33m![0m Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0a4eEagAAAADZtmRcHu09TbNQl71+FwrXQ08xRURHRTI1MTQARWRnZQ==
[38;5;242mbuild: .github#8
[0m
[0;33m![0m Failed to restore: Cache service responded with 400
[38;5;242mbuild: .github#26
[0m
[0;1;39mRefreshing run status every 3 seconds. Press Ctrl+C to quit.[0m

[0;33m*[0m [0;1;39mmaster[0m Publish · [0;36m32160158404[0m
Triggered via push about 5 minutes ago

[0;1;39mJOBS[0m
[0;32m✓[0m [0;1;39mrelease[0m in 11s (ID [0;36m95786865377[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run googleapis/release-please-action@v5
  [0;32m✓[0m Complete job
[0;32m✓[0m [0;1;39mbuild[0m in 10s (ID [0;36m95786940152[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Run astral-sh/setup-uv@v4
  [0;32m✓[0m Set up Python
  [0;32m✓[0m Build package
  [0;32m✓[0m Run actions/upload-artifact@v4
  [0;32m✓[0m Post Run astral-sh/setup-uv@v4
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[0;33m*[0m [0;1;39minstall-smoke[0m (ID [0;36m95787010707[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Run actions/download-artifact@v4
  [0;32m✓[0m Check out SASE
  [0;32m✓[0m Check out SASE Rust core
  [0;32m✓[0m Run astral-sh/setup-uv@v4
  [0;32m✓[0m Run extractions/setup-just@v2
  [0;32m✓[0m Run dtolnay/rust-toolchain@stable
  [0;32m✓[0m Set up Python
  [0;33m*[0m Install built sase-research-artifacts wheel into a fresh venv
  [0;33m*[0m Smoke check
  [0;33m*[0m Assemble the real artifact provider registry
  [0;33m*[0m Post Run astral-sh/setup-uv@v4
  [0;33m*[0m Post Check out SASE Rust core
  [0;33m*[0m Post Check out SASE
  [0;33m*[0m Post Run actions/checkout@v4

[0;1;39mANNOTATIONS[0m
[0;33m![0m Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
[38;5;242mbuild: .github#2
[0m
[0;33m![0m Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0a4eEagAAAADZtmRcHu09TbNQl71+FwrXQ08xRURHRTI1MTQARWRnZQ==
[38;5;242mbuild: .github#8
[0m
[0;33m![0m Failed to restore: Cache service responded with 400
[38;5;242mbuild: .github#26
[0m
[0;1;39mRefreshing run status every 3 seconds. Press Ctrl+C to quit.[0m

[0;33m*[0m [0;1;39mmaster[0m Publish · [0;36m32160158404[0m
Triggered via push about 5 minutes ago

[0;1;39mJOBS[0m
[0;32m✓[0m [0;1;39mrelease[0m in 11s (ID [0;36m95786865377[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run googleapis/release-please-action@v5
  [0;32m✓[0m Complete job
[0;32m✓[0m [0;1;39mbuild[0m in 10s (ID [0;36m95786940152[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Run astral-sh/setup-uv@v4
  [0;32m✓[0m Set up Python
  [0;32m✓[0m Build package
  [0;32m✓[0m Run actions/upload-artifact@v4
  [0;32m✓[0m Post Run astral-sh/setup-uv@v4
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[0;33m*[0m [0;1;39minstall-smoke[0m (ID [0;36m95787010707[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Run actions/download-artifact@v4
  [0;32m✓[0m Check out SASE
  [0;32m✓[0m Check out SASE Rust core
  [0;32m✓[0m Run astral-sh/setup-uv@v4
  [0;32m✓[0m Run extractions/setup-just@v2
  [0;32m✓[0m Run dtolnay/rust-toolchain@stable
  [0;32m✓[0m Set up Python
  [0;33m*[0m Install built sase-research-artifacts wheel into a fresh venv
  [0;33m*[0m Smoke check
  [0;33m*[0m Assemble the real artifact provider registry
  [0;33m*[0m Post Run astral-sh/setup-uv@v4
  [0;33m*[0m Post Check out SASE Rust core
  [0;33m*[0m Post Check out SASE
  [0;33m*[0m Post Run actions/checkout@v4

[0;1;39mANNOTATIONS[0m
[0;33m![0m Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
[38;5;242mbuild: .github#2
[0m
[0;33m![0m Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0a4eEagAAAADZtmRcHu09TbNQl71+FwrXQ08xRURHRTI1MTQARWRnZQ==
[38;5;242mbuild: .github#8
[0m
[0;33m![0m Failed to restore: Cache service responded with 400
[38;5;242mbuild: .github#26
[0m
[0;1;39mRefreshing run status every 3 seconds. Press Ctrl+C to quit.[0m

[0;33m*[0m [0;1;39mmaster[0m Publish · [0;36m32160158404[0m
Triggered via push about 5 minutes ago

[0;1;39mJOBS[0m
[0;32m✓[0m [0;1;39mrelease[0m in 11s (ID [0;36m95786865377[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run googleapis/release-please-action@v5
  [0;32m✓[0m Complete job
[0;32m✓[0m [0;1;39mbuild[0m in 10s (ID [0;36m95786940152[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Run astral-sh/setup-uv@v4
  [0;32m✓[0m Set up Python
  [0;32m✓[0m Build package
  [0;32m✓[0m Run actions/upload-artifact@v4
  [0;32m✓[0m Post Run astral-sh/setup-uv@v4
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[0;33m*[0m [0;1;39minstall-smoke[0m (ID [0;36m95787010707[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Run actions/download-artifact@v4
  [0;32m✓[0m Check out SASE
  [0;32m✓[0m Check out SASE Rust core
  [0;32m✓[0m Run astral-sh/setup-uv@v4
  [0;32m✓[0m Run extractions/setup-just@v2
  [0;32m✓[0m Run dtolnay/rust-toolchain@stable
  [0;32m✓[0m Set up Python
  [0;33m*[0m Install built sase-research-artifacts wheel into a fresh venv
  [0;33m*[0m Smoke check
  [0;33m*[0m Assemble the real artifact provider registry
  [0;33m*[0m Post Run astral-sh/setup-uv@v4
  [0;33m*[0m Post Check out SASE Rust core
  [0;33m*[0m Post Check out SASE
  [0;33m*[0m Post Run actions/checkout@v4

[0;1;39mANNOTATIONS[0m
[0;33m![0m Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
[38;5;242mbuild: .github#2
[0m
[0;33m![0m Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0a4eEagAAAADZtmRcHu09TbNQl71+FwrXQ08xRURHRTI1MTQARWRnZQ==
[38;5;242mbuild: .github#8
[0m
[0;33m![0m Failed to restore: Cache service responded with 400
[38;5;242mbuild: .github#26
[0m
[0;1;39mRefreshing run status every 3 seconds. Press Ctrl+C to quit.[0m

[0;33m*[0m [0;1;39mmaster[0m Publish · [0;36m32160158404[0m
Triggered via push about 5 minutes ago

[0;1;39mJOBS[0m
[0;32m✓[0m [0;1;39mrelease[0m in 11s (ID [0;36m95786865377[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run googleapis/release-please-action@v5
  [0;32m✓[0m Complete job
[0;32m✓[0m [0;1;39mbuild[0m in 10s (ID [0;36m95786940152[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Run astral-sh/setup-uv@v4
  [0;32m✓[0m Set up Python
  [0;32m✓[0m Build package
  [0;32m✓[0m Run actions/upload-artifact@v4
  [0;32m✓[0m Post Run astral-sh/setup-uv@v4
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[0;33m*[0m [0;1;39minstall-smoke[0m (ID [0;36m95787010707[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Run actions/download-artifact@v4
  [0;32m✓[0m Check out SASE
  [0;32m✓[0m Check out SASE Rust core
  [0;32m✓[0m Run astral-sh/setup-uv@v4
  [0;32m✓[0m Run extractions/setup-just@v2
  [0;32m✓[0m Run dtolnay/rust-toolchain@stable
  [0;32m✓[0m Set up Python
  [0;33m*[0m Install built sase-research-artifacts wheel into a fresh venv
  [0;33m*[0m Smoke check
  [0;33m*[0m Assemble the real artifact provider registry
  [0;33m*[0m Post Run astral-sh/setup-uv@v4
  [0;33m*[0m Post Check out SASE Rust core
  [0;33m*[0m Post Check out SASE
  [0;33m*[0m Post Run actions/checkout@v4

[0;1;39mANNOTATIONS[0m
[0;33m![0m Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
[38;5;242mbuild: .github#2
[0m
[0;33m![0m Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0a4eEagAAAADZtmRcHu09TbNQl71+FwrXQ08xRURHRTI1MTQARWRnZQ==
[38;5;242mbuild: .github#8
[0m
[0;33m![0m Failed to restore: Cache service responded with 400
[38;5;242mbuild: .github#26
[0m
[0;1;39mRefreshing run status every 3 seconds. Press Ctrl+C to quit.[0m

[0;33m*[0m [0;1;39mmaster[0m Publish · [0;36m32160158404[0m
Triggered via push about 5 minutes ago

[0;1;39mJOBS[0m
[0;32m✓[0m [0;1;39mrelease[0m in 11s (ID [0;36m95786865377[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run googleapis/release-please-action@v5
  [0;32m✓[0m Complete job
[0;32m✓[0m [0;1;39mbuild[0m in 10s (ID [0;36m95786940152[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Run astral-sh/setup-uv@v4
  [0;32m✓[0m Set up Python
  [0;32m✓[0m Build package
  [0;32m✓[0m Run actions/upload-artifact@v4
  [0;32m✓[0m Post Run astral-sh/setup-uv@v4
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[0;33m*[0m [0;1;39minstall-smoke[0m (ID [0;36m95787010707[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Run actions/download-artifact@v4
  [0;32m✓[0m Check out SASE
  [0;32m✓[0m Check out SASE Rust core
  [0;32m✓[0m Run astral-sh/setup-uv@v4
  [0;32m✓[0m Run extractions/setup-just@v2
  [0;32m✓[0m Run dtolnay/rust-toolchain@stable
  [0;32m✓[0m Set up Python
  [0;33m*[0m Install built sase-research-artifacts wheel into a fresh venv
  [0;33m*[0m Smoke check
  [0;33m*[0m Assemble the real artifact provider registry
  [0;33m*[0m Post Run astral-sh/setup-uv@v4
  [0;33m*[0m Post Check out SASE Rust core
  [0;33m*[0m Post Check out SASE
  [0;33m*[0m Post Run actions/checkout@v4

[0;1;39mANNOTATIONS[0m
[0;33m![0m Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
[38;5;242mbuild: .github#2
[0m
[0;33m![0m Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0a4eEagAAAADZtmRcHu09TbNQl71+FwrXQ08xRURHRTI1MTQARWRnZQ==
[38;5;242mbuild: .github#8
[0m
[0;33m![0m Failed to restore: Cache service responded with 400
[38;5;242mbuild: .github#26
[0m
[0;1;39mRefreshing run status every 3 seconds. Press Ctrl+C to quit.[0m

[0;33m*[0m [0;1;39mmaster[0m Publish · [0;36m32160158404[0m
Triggered via push about 5 minutes ago

[0;1;39mJOBS[0m
[0;32m✓[0m [0;1;39mrelease[0m in 11s (ID [0;36m95786865377[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run googleapis/release-please-action@v5
  [0;32m✓[0m Complete job
[0;32m✓[0m [0;1;39mbuild[0m in 10s (ID [0;36m95786940152[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Run astral-sh/setup-uv@v4
  [0;32m✓[0m Set up Python
  [0;32m✓[0m Build package
  [0;32m✓[0m Run actions/upload-artifact@v4
  [0;32m✓[0m Post Run astral-sh/setup-uv@v4
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[0;33m*[0m [0;1;39minstall-smoke[0m (ID [0;36m95787010707[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Run actions/download-artifact@v4
  [0;32m✓[0m Check out SASE
  [0;32m✓[0m Check out SASE Rust core
  [0;32m✓[0m Run astral-sh/setup-uv@v4
  [0;32m✓[0m Run extractions/setup-just@v2
  [0;32m✓[0m Run dtolnay/rust-toolchain@stable
  [0;32m✓[0m Set up Python
  [0;33m*[0m Install built sase-research-artifacts wheel into a fresh venv
  [0;33m*[0m Smoke check
  [0;33m*[0m Assemble the real artifact provider registry
  [0;33m*[0m Post Run astral-sh/setup-uv@v4
  [0;33m*[0m Post Check out SASE Rust core
  [0;33m*[0m Post Check out SASE
  [0;33m*[0m Post Run actions/checkout@v4

[0;1;39mANNOTATIONS[0m
[0;33m![0m Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
[38;5;242mbuild: .github#2
[0m
[0;33m![0m Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0a4eEagAAAADZtmRcHu09TbNQl71+FwrXQ08xRURHRTI1MTQARWRnZQ==
[38;5;242mbuild: .github#8
[0m
[0;33m![0m Failed to restore: Cache service responded with 400
[38;5;242mbuild: .github#26
[0m
[0;1;39mRefreshing run status every 3 seconds. Press Ctrl+C to quit.[0m

[0;33m*[0m [0;1;39mmaster[0m Publish · [0;36m32160158404[0m
Triggered via push about 5 minutes ago

[0;1;39mJOBS[0m
[0;32m✓[0m [0;1;39mrelease[0m in 11s (ID [0;36m95786865377[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run googleapis/release-please-action@v5
  [0;32m✓[0m Complete job
[0;32m✓[0m [0;1;39mbuild[0m in 10s (ID [0;36m95786940152[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Run astral-sh/setup-uv@v4
  [0;32m✓[0m Set up Python
  [0;32m✓[0m Build package
  [0;32m✓[0m Run actions/upload-artifact@v4
  [0;32m✓[0m Post Run astral-sh/setup-uv@v4
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[0;33m*[0m [0;1;39minstall-smoke[0m (ID [0;36m95787010707[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Run actions/download-artifact@v4
  [0;32m✓[0m Check out SASE
  [0;32m✓[0m Check out SASE Rust core
  [0;32m✓[0m Run astral-sh/setup-uv@v4
  [0;32m✓[0m Run extractions/setup-just@v2
  [0;32m✓[0m Run dtolnay/rust-toolchain@stable
  [0;32m✓[0m Set up Python
  [0;33m*[0m Install built sase-research-artifacts wheel into a fresh venv
  [0;33m*[0m Smoke check
  [0;33m*[0m Assemble the real artifact provider registry
  [0;33m*[0m Post Run astral-sh/setup-uv@v4
  [0;33m*[0m Post Check out SASE Rust core
  [0;33m*[0m Post Check out SASE
  [0;33m*[0m Post Run actions/checkout@v4

[0;1;39mANNOTATIONS[0m
[0;33m![0m Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
[38;5;242mbuild: .github#2
[0m
[0;33m![0m Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0a4eEagAAAADZtmRcHu09TbNQl71+FwrXQ08xRURHRTI1MTQARWRnZQ==
[38;5;242mbuild: .github#8
[0m
[0;33m![0m Failed to restore: Cache service responded with 400
[38;5;242mbuild: .github#26
[0m
[0;1;39mRefreshing run status every 3 seconds. Press Ctrl+C to quit.[0m

[0;33m*[0m [0;1;39mmaster[0m Publish · [0;36m32160158404[0m
Triggered via push about 5 minutes ago

[0;1;39mJOBS[0m
[0;32m✓[0m [0;1;39mrelease[0m in 11s (ID [0;36m95786865377[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run googleapis/release-please-action@v5
  [0;32m✓[0m Complete job
[0;32m✓[0m [0;1;39mbuild[0m in 10s (ID [0;36m95786940152[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Run astral-sh/setup-uv@v4
  [0;32m✓[0m Set up Python
  [0;32m✓[0m Build package
  [0;32m✓[0m Run actions/upload-artifact@v4
  [0;32m✓[0m Post Run astral-sh/setup-uv@v4
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[0;33m*[0m [0;1;39minstall-smoke[0m (ID [0;36m95787010707[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Run actions/download-artifact@v4
  [0;32m✓[0m Check out SASE
  [0;32m✓[0m Check out SASE Rust core
  [0;32m✓[0m Run astral-sh/setup-uv@v4
  [0;32m✓[0m Run extractions/setup-just@v2
  [0;32m✓[0m Run dtolnay/rust-toolchain@stable
  [0;32m✓[0m Set up Python
  [0;33m*[0m Install built sase-research-artifacts wheel into a fresh venv
  [0;33m*[0m Smoke check
  [0;33m*[0m Assemble the real artifact provider registry
  [0;33m*[0m Post Run astral-sh/setup-uv@v4
  [0;33m*[0m Post Check out SASE Rust core
  [0;33m*[0m Post Check out SASE
  [0;33m*[0m Post Run actions/checkout@v4

[0;1;39mANNOTATIONS[0m
[0;33m![0m Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
[38;5;242mbuild: .github#2
[0m
[0;33m![0m Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0a4eEagAAAADZtmRcHu09TbNQl71+FwrXQ08xRURHRTI1MTQARWRnZQ==
[38;5;242mbuild: .github#8
[0m
[0;33m![0m Failed to restore: Cache service responded with 400
[38;5;242mbuild: .github#26
[0m
[0;1;39mRefreshing run status every 3 seconds. Press Ctrl+C to quit.[0m

[0;33m*[0m [0;1;39mmaster[0m Publish · [0;36m32160158404[0m
Triggered via push about 5 minutes ago

[0;1;39mJOBS[0m
[0;32m✓[0m [0;1;39mrelease[0m in 11s (ID [0;36m95786865377[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run googleapis/release-please-action@v5
  [0;32m✓[0m Complete job
[0;32m✓[0m [0;1;39mbuild[0m in 10s (ID [0;36m95786940152[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Run astral-sh/setup-uv@v4
  [0;32m✓[0m Set up Python
  [0;32m✓[0m Build package
  [0;32m✓[0m Run actions/upload-artifact@v4
  [0;32m✓[0m Post Run astral-sh/setup-uv@v4
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[0;33m*[0m [0;1;39minstall-smoke[0m (ID [0;36m95787010707[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Run actions/download-artifact@v4
  [0;32m✓[0m Check out SASE
  [0;32m✓[0m Check out SASE Rust core
  [0;32m✓[0m Run astral-sh/setup-uv@v4
  [0;32m✓[0m Run extractions/setup-just@v2
  [0;32m✓[0m Run dtolnay/rust-toolchain@stable
  [0;32m✓[0m Set up Python
  [0;33m*[0m Install built sase-research-artifacts wheel into a fresh venv
  [0;33m*[0m Smoke check
  [0;33m*[0m Assemble the real artifact provider registry
  [0;33m*[0m Post Run astral-sh/setup-uv@v4
  [0;33m*[0m Post Check out SASE Rust core
  [0;33m*[0m Post Check out SASE
  [0;33m*[0m Post Run actions/checkout@v4

[0;1;39mANNOTATIONS[0m
[0;33m![0m Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
[38;5;242mbuild: .github#2
[0m
[0;33m![0m Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0a4eEagAAAADZtmRcHu09TbNQl71+FwrXQ08xRURHRTI1MTQARWRnZQ==
[38;5;242mbuild: .github#8
[0m
[0;33m![0m Failed to restore: Cache service responded with 400
[38;5;242mbuild: .github#26
[0m
[0;1;39mRefreshing run status every 3 seconds. Press Ctrl+C to quit.[0m

[0;33m*[0m [0;1;39mmaster[0m Publish · [0;36m32160158404[0m
Triggered via push about 5 minutes ago

[0;1;39mJOBS[0m
[0;32m✓[0m [0;1;39mrelease[0m in 11s (ID [0;36m95786865377[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run googleapis/release-please-action@v5
  [0;32m✓[0m Complete job
[0;32m✓[0m [0;1;39mbuild[0m in 10s (ID [0;36m95786940152[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Run astral-sh/setup-uv@v4
  [0;32m✓[0m Set up Python
  [0;32m✓[0m Build package
  [0;32m✓[0m Run actions/upload-artifact@v4
  [0;32m✓[0m Post Run astral-sh/setup-uv@v4
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[0;33m*[0m [0;1;39minstall-smoke[0m (ID [0;36m95787010707[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Run actions/download-artifact@v4
  [0;32m✓[0m Check out SASE
  [0;32m✓[0m Check out SASE Rust core
  [0;32m✓[0m Run astral-sh/setup-uv@v4
  [0;32m✓[0m Run extractions/setup-just@v2
  [0;32m✓[0m Run dtolnay/rust-toolchain@stable
  [0;32m✓[0m Set up Python
  [0;33m*[0m Install built sase-research-artifacts wheel into a fresh venv
  [0;33m*[0m Smoke check
  [0;33m*[0m Assemble the real artifact provider registry
  [0;33m*[0m Post Run astral-sh/setup-uv@v4
  [0;33m*[0m Post Check out SASE Rust core
  [0;33m*[0m Post Check out SASE
  [0;33m*[0m Post Run actions/checkout@v4

[0;1;39mANNOTATIONS[0m
[0;33m![0m Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
[38;5;242mbuild: .github#2
[0m
[0;33m![0m Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0a4eEagAAAADZtmRcHu09TbNQl71+FwrXQ08xRURHRTI1MTQARWRnZQ==
[38;5;242mbuild: .github#8
[0m
[0;33m![0m Failed to restore: Cache service responded with 400
[38;5;242mbuild: .github#26
[0m
[0;1;39mRefreshing run status every 3 seconds. Press Ctrl+C to quit.[0m

[0;33m*[0m [0;1;39mmaster[0m Publish · [0;36m32160158404[0m
Triggered via push about 5 minutes ago

[0;1;39mJOBS[0m
[0;32m✓[0m [0;1;39mrelease[0m in 11s (ID [0;36m95786865377[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run googleapis/release-please-action@v5
  [0;32m✓[0m Complete job
[0;32m✓[0m [0;1;39mbuild[0m in 10s (ID [0;36m95786940152[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Run astral-sh/setup-uv@v4
  [0;32m✓[0m Set up Python
  [0;32m✓[0m Build package
  [0;32m✓[0m Run actions/upload-artifact@v4
  [0;32m✓[0m Post Run astral-sh/setup-uv@v4
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[0;33m*[0m [0;1;39minstall-smoke[0m (ID [0;36m95787010707[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Run actions/download-artifact@v4
  [0;32m✓[0m Check out SASE
  [0;32m✓[0m Check out SASE Rust core
  [0;32m✓[0m Run astral-sh/setup-uv@v4
  [0;32m✓[0m Run extractions/setup-just@v2
  [0;32m✓[0m Run dtolnay/rust-toolchain@stable
  [0;32m✓[0m Set up Python
  [0;33m*[0m Install built sase-research-artifacts wheel into a fresh venv
  [0;33m*[0m Smoke check
  [0;33m*[0m Assemble the real artifact provider registry
  [0;33m*[0m Post Run astral-sh/setup-uv@v4
  [0;33m*[0m Post Check out SASE Rust core
  [0;33m*[0m Post Check out SASE
  [0;33m*[0m Post Run actions/checkout@v4

[0;1;39mANNOTATIONS[0m
[0;33m![0m Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
[38;5;242mbuild: .github#2
[0m
[0;33m![0m Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0a4eEagAAAADZtmRcHu09TbNQl71+FwrXQ08xRURHRTI1MTQARWRnZQ==
[38;5;242mbuild: .github#8
[0m
[0;33m![0m Failed to restore: Cache service responded with 400
[38;5;242mbuild: .github#26
[0m
[0;1;39mRefreshing run status every 3 seconds. Press Ctrl+C to quit.[0m

[0;33m*[0m [0;1;39mmaster[0m Publish · [0;36m32160158404[0m
Triggered via push about 5 minutes ago

[0;1;39mJOBS[0m
[0;32m✓[0m [0;1;39mrelease[0m in 11s (ID [0;36m95786865377[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run googleapis/release-please-action@v5
  [0;32m✓[0m Complete job
[0;32m✓[0m [0;1;39mbuild[0m in 10s (ID [0;36m95786940152[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Run astral-sh/setup-uv@v4
  [0;32m✓[0m Set up Python
  [0;32m✓[0m Build package
  [0;32m✓[0m Run actions/upload-artifact@v4
  [0;32m✓[0m Post Run astral-sh/setup-uv@v4
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[0;33m*[0m [0;1;39minstall-smoke[0m (ID [0;36m95787010707[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Run actions/download-artifact@v4
  [0;32m✓[0m Check out SASE
  [0;32m✓[0m Check out SASE Rust core
  [0;32m✓[0m Run astral-sh/setup-uv@v4
  [0;32m✓[0m Run extractions/setup-just@v2
  [0;32m✓[0m Run dtolnay/rust-toolchain@stable
  [0;32m✓[0m Set up Python
  [0;33m*[0m Install built sase-research-artifacts wheel into a fresh venv
  [0;33m*[0m Smoke check
  [0;33m*[0m Assemble the real artifact provider registry
  [0;33m*[0m Post Run astral-sh/setup-uv@v4
  [0;33m*[0m Post Check out SASE Rust core
  [0;33m*[0m Post Check out SASE
  [0;33m*[0m Post Run actions/checkout@v4

[0;1;39mANNOTATIONS[0m
[0;33m![0m Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
[38;5;242mbuild: .github#2
[0m
[0;33m![0m Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0a4eEagAAAADZtmRcHu09TbNQl71+FwrXQ08xRURHRTI1MTQARWRnZQ==
[38;5;242mbuild: .github#8
[0m
[0;33m![0m Failed to restore: Cache service responded with 400
[38;5;242mbuild: .github#26
[0m
[0;1;39mRefreshing run status every 3 seconds. Press Ctrl+C to quit.[0m

[0;33m*[0m [0;1;39mmaster[0m Publish · [0;36m32160158404[0m
Triggered via push about 6 minutes ago

[0;1;39mJOBS[0m
[0;32m✓[0m [0;1;39mrelease[0m in 11s (ID [0;36m95786865377[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run googleapis/release-please-action@v5
  [0;32m✓[0m Complete job
[0;32m✓[0m [0;1;39mbuild[0m in 10s (ID [0;36m95786940152[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Run astral-sh/setup-uv@v4
  [0;32m✓[0m Set up Python
  [0;32m✓[0m Build package
  [0;32m✓[0m Run actions/upload-artifact@v4
  [0;32m✓[0m Post Run astral-sh/setup-uv@v4
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[0;33m*[0m [0;1;39minstall-smoke[0m (ID [0;36m95787010707[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Run actions/download-artifact@v4
  [0;32m✓[0m Check out SASE
  [0;32m✓[0m Check out SASE Rust core
  [0;32m✓[0m Run astral-sh/setup-uv@v4
  [0;32m✓[0m Run extractions/setup-just@v2
  [0;32m✓[0m Run dtolnay/rust-toolchain@stable
  [0;32m✓[0m Set up Python
  [0;33m*[0m Install built sase-research-artifacts wheel into a fresh venv
  [0;33m*[0m Smoke check
  [0;33m*[0m Assemble the real artifact provider registry
  [0;33m*[0m Post Run astral-sh/setup-uv@v4
  [0;33m*[0m Post Check out SASE Rust core
  [0;33m*[0m Post Check out SASE
  [0;33m*[0m Post Run actions/checkout@v4

[0;1;39mANNOTATIONS[0m
[0;33m![0m Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
[38;5;242mbuild: .github#2
[0m
[0;33m![0m Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0a4eEagAAAADZtmRcHu09TbNQl71+FwrXQ08xRURHRTI1MTQARWRnZQ==
[38;5;242mbuild: .github#8
[0m
[0;33m![0m Failed to restore: Cache service responded with 400
[38;5;242mbuild: .github#26
[0m
[0;1;39mRefreshing run status every 3 seconds. Press Ctrl+C to quit.[0m

[0;33m*[0m [0;1;39mmaster[0m Publish · [0;36m32160158404[0m
Triggered via push about 6 minutes ago

[0;1;39mJOBS[0m
[0;32m✓[0m [0;1;39mrelease[0m in 11s (ID [0;36m95786865377[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run googleapis/release-please-action@v5
  [0;32m✓[0m Complete job
[0;32m✓[0m [0;1;39mbuild[0m in 10s (ID [0;36m95786940152[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Run astral-sh/setup-uv@v4
  [0;32m✓[0m Set up Python
  [0;32m✓[0m Build package
  [0;32m✓[0m Run actions/upload-artifact@v4
  [0;32m✓[0m Post Run astral-sh/setup-uv@v4
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[0;33m*[0m [0;1;39minstall-smoke[0m (ID [0;36m95787010707[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Run actions/download-artifact@v4
  [0;32m✓[0m Check out SASE
  [0;32m✓[0m Check out SASE Rust core
  [0;32m✓[0m Run astral-sh/setup-uv@v4
  [0;32m✓[0m Run extractions/setup-just@v2
  [0;32m✓[0m Run dtolnay/rust-toolchain@stable
  [0;32m✓[0m Set up Python
  [0;33m*[0m Install built sase-research-artifacts wheel into a fresh venv
  [0;33m*[0m Smoke check
  [0;33m*[0m Assemble the real artifact provider registry
  [0;33m*[0m Post Run astral-sh/setup-uv@v4
  [0;33m*[0m Post Check out SASE Rust core
  [0;33m*[0m Post Check out SASE
  [0;33m*[0m Post Run actions/checkout@v4

[0;1;39mANNOTATIONS[0m
[0;33m![0m Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
[38;5;242mbuild: .github#2
[0m
[0;33m![0m Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0a4eEagAAAADZtmRcHu09TbNQl71+FwrXQ08xRURHRTI1MTQARWRnZQ==
[38;5;242mbuild: .github#8
[0m
[0;33m![0m Failed to restore: Cache service responded with 400
[38;5;242mbuild: .github#26
[0m
[0;1;39mRefreshing run status every 3 seconds. Press Ctrl+C to quit.[0m

[0;33m*[0m [0;1;39mmaster[0m Publish · [0;36m32160158404[0m
Triggered via push about 6 minutes ago

[0;1;39mJOBS[0m
[0;32m✓[0m [0;1;39mrelease[0m in 11s (ID [0;36m95786865377[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run googleapis/release-please-action@v5
  [0;32m✓[0m Complete job
[0;32m✓[0m [0;1;39mbuild[0m in 10s (ID [0;36m95786940152[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Run astral-sh/setup-uv@v4
  [0;32m✓[0m Set up Python
  [0;32m✓[0m Build package
  [0;32m✓[0m Run actions/upload-artifact@v4
  [0;32m✓[0m Post Run astral-sh/setup-uv@v4
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[0;33m*[0m [0;1;39minstall-smoke[0m (ID [0;36m95787010707[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Run actions/download-artifact@v4
  [0;32m✓[0m Check out SASE
  [0;32m✓[0m Check out SASE Rust core
  [0;32m✓[0m Run astral-sh/setup-uv@v4
  [0;32m✓[0m Run extractions/setup-just@v2
  [0;32m✓[0m Run dtolnay/rust-toolchain@stable
  [0;32m✓[0m Set up Python
  [0;33m*[0m Install built sase-research-artifacts wheel into a fresh venv
  [0;33m*[0m Smoke check
  [0;33m*[0m Assemble the real artifact provider registry
  [0;33m*[0m Post Run astral-sh/setup-uv@v4
  [0;33m*[0m Post Check out SASE Rust core
  [0;33m*[0m Post Check out SASE
  [0;33m*[0m Post Run actions/checkout@v4

[0;1;39mANNOTATIONS[0m
[0;33m![0m Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
[38;5;242mbuild: .github#2
[0m
[0;33m![0m Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0a4eEagAAAADZtmRcHu09TbNQl71+FwrXQ08xRURHRTI1MTQARWRnZQ==
[38;5;242mbuild: .github#8
[0m
[0;33m![0m Failed to restore: Cache service responded with 400
[38;5;242mbuild: .github#26
[0m
[0;1;39mRefreshing run status every 3 seconds. Press Ctrl+C to quit.[0m

[0;33m*[0m [0;1;39mmaster[0m Publish · [0;36m32160158404[0m
Triggered via push about 6 minutes ago

[0;1;39mJOBS[0m
[0;32m✓[0m [0;1;39mrelease[0m in 11s (ID [0;36m95786865377[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run googleapis/release-please-action@v5
  [0;32m✓[0m Complete job
[0;32m✓[0m [0;1;39mbuild[0m in 10s (ID [0;36m95786940152[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Run astral-sh/setup-uv@v4
  [0;32m✓[0m Set up Python
  [0;32m✓[0m Build package
  [0;32m✓[0m Run actions/upload-artifact@v4
  [0;32m✓[0m Post Run astral-sh/setup-uv@v4
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[0;33m*[0m [0;1;39minstall-smoke[0m (ID [0;36m95787010707[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Run actions/download-artifact@v4
  [0;32m✓[0m Check out SASE
  [0;32m✓[0m Check out SASE Rust core
  [0;32m✓[0m Run astral-sh/setup-uv@v4
  [0;32m✓[0m Run extractions/setup-just@v2
  [0;32m✓[0m Run dtolnay/rust-toolchain@stable
  [0;32m✓[0m Set up Python
  [0;33m*[0m Install built sase-research-artifacts wheel into a fresh venv
  [0;33m*[0m Smoke check
  [0;33m*[0m Assemble the real artifact provider registry
  [0;33m*[0m Post Run astral-sh/setup-uv@v4
  [0;33m*[0m Post Check out SASE Rust core
  [0;33m*[0m Post Check out SASE
  [0;33m*[0m Post Run actions/checkout@v4

[0;1;39mANNOTATIONS[0m
[0;33m![0m Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
[38;5;242mbuild: .github#2
[0m
[0;33m![0m Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0a4eEagAAAADZtmRcHu09TbNQl71+FwrXQ08xRURHRTI1MTQARWRnZQ==
[38;5;242mbuild: .github#8
[0m
[0;33m![0m Failed to restore: Cache service responded with 400
[38;5;242mbuild: .github#26
[0m
[0;1;39mRefreshing run status every 3 seconds. Press Ctrl+C to quit.[0m

[0;33m*[0m [0;1;39mmaster[0m Publish · [0;36m32160158404[0m
Triggered via push about 6 minutes ago

[0;1;39mJOBS[0m
[0;32m✓[0m [0;1;39mrelease[0m in 11s (ID [0;36m95786865377[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run googleapis/release-please-action@v5
  [0;32m✓[0m Complete job
[0;32m✓[0m [0;1;39mbuild[0m in 10s (ID [0;36m95786940152[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Run astral-sh/setup-uv@v4
  [0;32m✓[0m Set up Python
  [0;32m✓[0m Build package
  [0;32m✓[0m Run actions/upload-artifact@v4
  [0;32m✓[0m Post Run astral-sh/setup-uv@v4
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[0;33m*[0m [0;1;39minstall-smoke[0m (ID [0;36m95787010707[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Run actions/download-artifact@v4
  [0;32m✓[0m Check out SASE
  [0;32m✓[0m Check out SASE Rust core
  [0;32m✓[0m Run astral-sh/setup-uv@v4
  [0;32m✓[0m Run extractions/setup-just@v2
  [0;32m✓[0m Run dtolnay/rust-toolchain@stable
  [0;32m✓[0m Set up Python
  [0;33m*[0m Install built sase-research-artifacts wheel into a fresh venv
  [0;33m*[0m Smoke check
  [0;33m*[0m Assemble the real artifact provider registry
  [0;33m*[0m Post Run astral-sh/setup-uv@v4
  [0;33m*[0m Post Check out SASE Rust core
  [0;33m*[0m Post Check out SASE
  [0;33m*[0m Post Run actions/checkout@v4

[0;1;39mANNOTATIONS[0m
[0;33m![0m Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
[38;5;242mbuild: .github#2
[0m
[0;33m![0m Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0a4eEagAAAADZtmRcHu09TbNQl71+FwrXQ08xRURHRTI1MTQARWRnZQ==
[38;5;242mbuild: .github#8
[0m
[0;33m![0m Failed to restore: Cache service responded with 400
[38;5;242mbuild: .github#26
[0m
[0;1;39mRefreshing run status every 3 seconds. Press Ctrl+C to quit.[0m

[0;33m*[0m [0;1;39mmaster[0m Publish · [0;36m32160158404[0m
Triggered via push about 6 minutes ago

[0;1;39mJOBS[0m
[0;32m✓[0m [0;1;39mrelease[0m in 11s (ID [0;36m95786865377[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run googleapis/release-please-action@v5
  [0;32m✓[0m Complete job
[0;32m✓[0m [0;1;39mbuild[0m in 10s (ID [0;36m95786940152[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Run astral-sh/setup-uv@v4
  [0;32m✓[0m Set up Python
  [0;32m✓[0m Build package
  [0;32m✓[0m Run actions/upload-artifact@v4
  [0;32m✓[0m Post Run astral-sh/setup-uv@v4
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[0;33m*[0m [0;1;39minstall-smoke[0m (ID [0;36m95787010707[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Run actions/download-artifact@v4
  [0;32m✓[0m Check out SASE
  [0;32m✓[0m Check out SASE Rust core
  [0;32m✓[0m Run astral-sh/setup-uv@v4
  [0;32m✓[0m Run extractions/setup-just@v2
  [0;32m✓[0m Run dtolnay/rust-toolchain@stable
  [0;32m✓[0m Set up Python
  [0;33m*[0m Install built sase-research-artifacts wheel into a fresh venv
  [0;33m*[0m Smoke check
  [0;33m*[0m Assemble the real artifact provider registry
  [0;33m*[0m Post Run astral-sh/setup-uv@v4
  [0;33m*[0m Post Check out SASE Rust core
  [0;33m*[0m Post Check out SASE
  [0;33m*[0m Post Run actions/checkout@v4

[0;1;39mANNOTATIONS[0m
[0;33m![0m Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
[38;5;242mbuild: .github#2
[0m
[0;33m![0m Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0a4eEagAAAADZtmRcHu09TbNQl71+FwrXQ08xRURHRTI1MTQARWRnZQ==
[38;5;242mbuild: .github#8
[0m
[0;33m![0m Failed to restore: Cache service responded with 400
[38;5;242mbuild: .github#26
[0m
[0;1;39mRefreshing run status every 3 seconds. Press Ctrl+C to quit.[0m

[0;33m*[0m [0;1;39mmaster[0m Publish · [0;36m32160158404[0m
Triggered via push about 6 minutes ago

[0;1;39mJOBS[0m
[0;32m✓[0m [0;1;39mrelease[0m in 11s (ID [0;36m95786865377[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run googleapis/release-please-action@v5
  [0;32m✓[0m Complete job
[0;32m✓[0m [0;1;39mbuild[0m in 10s (ID [0;36m95786940152[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Run astral-sh/setup-uv@v4
  [0;32m✓[0m Set up Python
  [0;32m✓[0m Build package
  [0;32m✓[0m Run actions/upload-artifact@v4
  [0;32m✓[0m Post Run astral-sh/setup-uv@v4
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[0;33m*[0m [0;1;39minstall-smoke[0m (ID [0;36m95787010707[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Run actions/download-artifact@v4
  [0;32m✓[0m Check out SASE
  [0;32m✓[0m Check out SASE Rust core
  [0;32m✓[0m Run astral-sh/setup-uv@v4
  [0;32m✓[0m Run extractions/setup-just@v2
  [0;32m✓[0m Run dtolnay/rust-toolchain@stable
  [0;32m✓[0m Set up Python
  [0;33m*[0m Install built sase-research-artifacts wheel into a fresh venv
  [0;33m*[0m Smoke check
  [0;33m*[0m Assemble the real artifact provider registry
  [0;33m*[0m Post Run astral-sh/setup-uv@v4
  [0;33m*[0m Post Check out SASE Rust core
  [0;33m*[0m Post Check out SASE
  [0;33m*[0m Post Run actions/checkout@v4

[0;1;39mANNOTATIONS[0m
[0;33m![0m Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
[38;5;242mbuild: .github#2
[0m
[0;33m![0m Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0a4eEagAAAADZtmRcHu09TbNQl71+FwrXQ08xRURHRTI1MTQARWRnZQ==
[38;5;242mbuild: .github#8
[0m
[0;33m![0m Failed to restore: Cache service responded with 400
[38;5;242mbuild: .github#26
[0m
[0;1;39mRefreshing run status every 3 seconds. Press Ctrl+C to quit.[0m

[0;33m*[0m [0;1;39mmaster[0m Publish · [0;36m32160158404[0m
Triggered via push about 6 minutes ago

[0;1;39mJOBS[0m
[0;32m✓[0m [0;1;39mrelease[0m in 11s (ID [0;36m95786865377[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run googleapis/release-please-action@v5
  [0;32m✓[0m Complete job
[0;32m✓[0m [0;1;39mbuild[0m in 10s (ID [0;36m95786940152[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Run astral-sh/setup-uv@v4
  [0;32m✓[0m Set up Python
  [0;32m✓[0m Build package
  [0;32m✓[0m Run actions/upload-artifact@v4
  [0;32m✓[0m Post Run astral-sh/setup-uv@v4
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[0;33m*[0m [0;1;39minstall-smoke[0m (ID [0;36m95787010707[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Run actions/download-artifact@v4
  [0;32m✓[0m Check out SASE
  [0;32m✓[0m Check out SASE Rust core
  [0;32m✓[0m Run astral-sh/setup-uv@v4
  [0;32m✓[0m Run extractions/setup-just@v2
  [0;32m✓[0m Run dtolnay/rust-toolchain@stable
  [0;32m✓[0m Set up Python
  [0;33m*[0m Install built sase-research-artifacts wheel into a fresh venv
  [0;33m*[0m Smoke check
  [0;33m*[0m Assemble the real artifact provider registry
  [0;33m*[0m Post Run astral-sh/setup-uv@v4
  [0;33m*[0m Post Check out SASE Rust core
  [0;33m*[0m Post Check out SASE
  [0;33m*[0m Post Run actions/checkout@v4

[0;1;39mANNOTATIONS[0m
[0;33m![0m Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
[38;5;242mbuild: .github#2
[0m
[0;33m![0m Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0a4eEagAAAADZtmRcHu09TbNQl71+FwrXQ08xRURHRTI1MTQARWRnZQ==
[38;5;242mbuild: .github#8
[0m
[0;33m![0m Failed to restore: Cache service responded with 400
[38;5;242mbuild: .github#26
[0m
[0;1;39mRefreshing run status every 3 seconds. Press Ctrl+C to quit.[0m

[0;33m*[0m [0;1;39mmaster[0m Publish · [0;36m32160158404[0m
Triggered via push about 6 minutes ago

[0;1;39mJOBS[0m
[0;32m✓[0m [0;1;39mrelease[0m in 11s (ID [0;36m95786865377[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run googleapis/release-please-action@v5
  [0;32m✓[0m Complete job
[0;32m✓[0m [0;1;39mbuild[0m in 10s (ID [0;36m95786940152[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Run astral-sh/setup-uv@v4
  [0;32m✓[0m Set up Python
  [0;32m✓[0m Build package
  [0;32m✓[0m Run actions/upload-artifact@v4
  [0;32m✓[0m Post Run astral-sh/setup-uv@v4
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[0;33m*[0m [0;1;39minstall-smoke[0m (ID [0;36m95787010707[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Run actions/download-artifact@v4
  [0;32m✓[0m Check out SASE
  [0;32m✓[0m Check out SASE Rust core
  [0;32m✓[0m Run astral-sh/setup-uv@v4
  [0;32m✓[0m Run extractions/setup-just@v2
  [0;32m✓[0m Run dtolnay/rust-toolchain@stable
  [0;32m✓[0m Set up Python
  [0;33m*[0m Install built sase-research-artifacts wheel into a fresh venv
  [0;33m*[0m Smoke check
  [0;33m*[0m Assemble the real artifact provider registry
  [0;33m*[0m Post Run astral-sh/setup-uv@v4
  [0;33m*[0m Post Check out SASE Rust core
  [0;33m*[0m Post Check out SASE
  [0;33m*[0m Post Run actions/checkout@v4

[0;1;39mANNOTATIONS[0m
[0;33m![0m Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
[38;5;242mbuild: .github#2
[0m
[0;33m![0m Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0a4eEagAAAADZtmRcHu09TbNQl71+FwrXQ08xRURHRTI1MTQARWRnZQ==
[38;5;242mbuild: .github#8
[0m
[0;33m![0m Failed to restore: Cache service responded with 400
[38;5;242mbuild: .github#26
[0m
[0;1;39mRefreshing run status every 3 seconds. Press Ctrl+C to quit.[0m

[0;33m*[0m [0;1;39mmaster[0m Publish · [0;36m32160158404[0m
Triggered via push about 6 minutes ago

[0;1;39mJOBS[0m
[0;32m✓[0m [0;1;39mrelease[0m in 11s (ID [0;36m95786865377[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run googleapis/release-please-action@v5
  [0;32m✓[0m Complete job
[0;32m✓[0m [0;1;39mbuild[0m in 10s (ID [0;36m95786940152[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Run astral-sh/setup-uv@v4
  [0;32m✓[0m Set up Python
  [0;32m✓[0m Build package
  [0;32m✓[0m Run actions/upload-artifact@v4
  [0;32m✓[0m Post Run astral-sh/setup-uv@v4
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[0;33m*[0m [0;1;39minstall-smoke[0m (ID [0;36m95787010707[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Run actions/download-artifact@v4
  [0;32m✓[0m Check out SASE
  [0;32m✓[0m Check out SASE Rust core
  [0;32m✓[0m Run astral-sh/setup-uv@v4
  [0;32m✓[0m Run extractions/setup-just@v2
  [0;32m✓[0m Run dtolnay/rust-toolchain@stable
  [0;32m✓[0m Set up Python
  [0;33m*[0m Install built sase-research-artifacts wheel into a fresh venv
  [0;33m*[0m Smoke check
  [0;33m*[0m Assemble the real artifact provider registry
  [0;33m*[0m Post Run astral-sh/setup-uv@v4
  [0;33m*[0m Post Check out SASE Rust core
  [0;33m*[0m Post Check out SASE
  [0;33m*[0m Post Run actions/checkout@v4

[0;1;39mANNOTATIONS[0m
[0;33m![0m Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
[38;5;242mbuild: .github#2
[0m
[0;33m![0m Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0a4eEagAAAADZtmRcHu09TbNQl71+FwrXQ08xRURHRTI1MTQARWRnZQ==
[38;5;242mbuild: .github#8
[0m
[0;33m![0m Failed to restore: Cache service responded with 400
[38;5;242mbuild: .github#26
[0m
[0;1;39mRefreshing run status every 3 seconds. Press Ctrl+C to quit.[0m

[0;33m*[0m [0;1;39mmaster[0m Publish · [0;36m32160158404[0m
Triggered via push about 6 minutes ago

[0;1;39mJOBS[0m
[0;32m✓[0m [0;1;39mrelease[0m in 11s (ID [0;36m95786865377[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run googleapis/release-please-action@v5
  [0;32m✓[0m Complete job
[0;32m✓[0m [0;1;39mbuild[0m in 10s (ID [0;36m95786940152[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Run astral-sh/setup-uv@v4
  [0;32m✓[0m Set up Python
  [0;32m✓[0m Build package
  [0;32m✓[0m Run actions/upload-artifact@v4
  [0;32m✓[0m Post Run astral-sh/setup-uv@v4
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[0;33m*[0m [0;1;39minstall-smoke[0m (ID [0;36m95787010707[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Run actions/download-artifact@v4
  [0;32m✓[0m Check out SASE
  [0;32m✓[0m Check out SASE Rust core
  [0;32m✓[0m Run astral-sh/setup-uv@v4
  [0;32m✓[0m Run extractions/setup-just@v2
  [0;32m✓[0m Run dtolnay/rust-toolchain@stable
  [0;32m✓[0m Set up Python
  [0;33m*[0m Install built sase-research-artifacts wheel into a fresh venv
  [0;33m*[0m Smoke check
  [0;33m*[0m Assemble the real artifact provider registry
  [0;33m*[0m Post Run astral-sh/setup-uv@v4
  [0;33m*[0m Post Check out SASE Rust core
  [0;33m*[0m Post Check out SASE
  [0;33m*[0m Post Run actions/checkout@v4

[0;1;39mANNOTATIONS[0m
[0;33m![0m Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
[38;5;242mbuild: .github#2
[0m
[0;33m![0m Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0a4eEagAAAADZtmRcHu09TbNQl71+FwrXQ08xRURHRTI1MTQARWRnZQ==
[38;5;242mbuild: .github#8
[0m
[0;33m![0m Failed to restore: Cache service responded with 400
[38;5;242mbuild: .github#26
[0m
[0;1;39mRefreshing run status every 3 seconds. Press Ctrl+C to quit.[0m

[0;33m*[0m [0;1;39mmaster[0m Publish · [0;36m32160158404[0m
Triggered via push about 6 minutes ago

[0;1;39mJOBS[0m
[0;32m✓[0m [0;1;39mrelease[0m in 11s (ID [0;36m95786865377[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run googleapis/release-please-action@v5
  [0;32m✓[0m Complete job
[0;32m✓[0m [0;1;39mbuild[0m in 10s (ID [0;36m95786940152[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Run astral-sh/setup-uv@v4
  [0;32m✓[0m Set up Python
  [0;32m✓[0m Build package
  [0;32m✓[0m Run actions/upload-artifact@v4
  [0;32m✓[0m Post Run astral-sh/setup-uv@v4
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[0;33m*[0m [0;1;39minstall-smoke[0m (ID [0;36m95787010707[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Run actions/download-artifact@v4
  [0;32m✓[0m Check out SASE
  [0;32m✓[0m Check out SASE Rust core
  [0;32m✓[0m Run astral-sh/setup-uv@v4
  [0;32m✓[0m Run extractions/setup-just@v2
  [0;32m✓[0m Run dtolnay/rust-toolchain@stable
  [0;32m✓[0m Set up Python
  [0;32m✓[0m Install built sase-research-artifacts wheel into a fresh venv
  [0;32m✓[0m Smoke check
  [0;32m✓[0m Assemble the real artifact provider registry
  [0;32m✓[0m Post Run astral-sh/setup-uv@v4
  [0;33m*[0m Post Check out SASE Rust core
  [0;33m*[0m Post Check out SASE
  [0;33m*[0m Post Run actions/checkout@v4

[0;1;39mANNOTATIONS[0m
[0;33m![0m Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
[38;5;242mbuild: .github#2
[0m
[0;33m![0m Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0a4eEagAAAADZtmRcHu09TbNQl71+FwrXQ08xRURHRTI1MTQARWRnZQ==
[38;5;242mbuild: .github#8
[0m
[0;33m![0m Failed to restore: Cache service responded with 400
[38;5;242mbuild: .github#26
[0m
[0;1;39mRefreshing run status every 3 seconds. Press Ctrl+C to quit.[0m

[0;33m*[0m [0;1;39mmaster[0m Publish · [0;36m32160158404[0m
Triggered via push about 6 minutes ago

[0;1;39mJOBS[0m
[0;32m✓[0m [0;1;39mrelease[0m in 11s (ID [0;36m95786865377[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run googleapis/release-please-action@v5
  [0;32m✓[0m Complete job
[0;32m✓[0m [0;1;39mbuild[0m in 10s (ID [0;36m95786940152[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Run astral-sh/setup-uv@v4
  [0;32m✓[0m Set up Python
  [0;32m✓[0m Build package
  [0;32m✓[0m Run actions/upload-artifact@v4
  [0;32m✓[0m Post Run astral-sh/setup-uv@v4
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[0;32m✓[0m [0;1;39minstall-smoke[0m in 6m12s (ID [0;36m95787010707[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Run actions/download-artifact@v4
  [0;32m✓[0m Check out SASE
  [0;32m✓[0m Check out SASE Rust core
  [0;32m✓[0m Run astral-sh/setup-uv@v4
  [0;32m✓[0m Run extractions/setup-just@v2
  [0;32m✓[0m Run dtolnay/rust-toolchain@stable
  [0;32m✓[0m Set up Python
  [0;32m✓[0m Install built sase-research-artifacts wheel into a fresh venv
  [0;32m✓[0m Smoke check
  [0;32m✓[0m Assemble the real artifact provider registry
  [0;32m✓[0m Post Run astral-sh/setup-uv@v4
  [0;32m✓[0m Post Check out SASE Rust core
  [0;32m✓[0m Post Check out SASE
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[0;33m*[0m [0;1;39mpublish[0m (ID [0;36m95788835674[0m)

[0;1;39mANNOTATIONS[0m
[0;33m![0m Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
[38;5;242mbuild: .github#2
[0m
[0;33m![0m Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0a4eEagAAAADZtmRcHu09TbNQl71+FwrXQ08xRURHRTI1MTQARWRnZQ==
[38;5;242mbuild: .github#8
[0m
[0;33m![0m Failed to restore: Cache service responded with 400
[38;5;242mbuild: .github#26
[0m
[0;33m![0m Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4, extractions/setup-just@v2. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
[38;5;242minstall-smoke: .github#2
[0m
[0;1;39mRefreshing run status every 3 seconds. Press Ctrl+C to quit.[0m

[0;33m*[0m [0;1;39mmaster[0m Publish · [0;36m32160158404[0m
Triggered via push about 6 minutes ago

[0;1;39mJOBS[0m
[0;32m✓[0m [0;1;39mrelease[0m in 11s (ID [0;36m95786865377[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run googleapis/release-please-action@v5
  [0;32m✓[0m Complete job
[0;32m✓[0m [0;1;39mbuild[0m in 10s (ID [0;36m95786940152[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Run astral-sh/setup-uv@v4
  [0;32m✓[0m Set up Python
  [0;32m✓[0m Build package
  [0;32m✓[0m Run actions/upload-artifact@v4
  [0;32m✓[0m Post Run astral-sh/setup-uv@v4
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[0;32m✓[0m [0;1;39minstall-smoke[0m in 6m12s (ID [0;36m95787010707[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Run actions/download-artifact@v4
  [0;32m✓[0m Check out SASE
  [0;32m✓[0m Check out SASE Rust core
  [0;32m✓[0m Run astral-sh/setup-uv@v4
  [0;32m✓[0m Run extractions/setup-just@v2
  [0;32m✓[0m Run dtolnay/rust-toolchain@stable
  [0;32m✓[0m Set up Python
  [0;32m✓[0m Install built sase-research-artifacts wheel into a fresh venv
  [0;32m✓[0m Smoke check
  [0;32m✓[0m Assemble the real artifact provider registry
  [0;32m✓[0m Post Run astral-sh/setup-uv@v4
  [0;32m✓[0m Post Check out SASE Rust core
  [0;32m✓[0m Post Check out SASE
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[0;33m*[0m [0;1;39mpublish[0m (ID [0;36m95788835674[0m)
  [0;32m✓[0m Set up job
  [0;33m*[0m Run actions/download-artifact@v4
  [0;33m*[0m Run pypa/gh-action-pypi-publish@release/v1

[0;1;39mANNOTATIONS[0m
[0;33m![0m Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
[38;5;242mbuild: .github#2
[0m
[0;33m![0m Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0a4eEagAAAADZtmRcHu09TbNQl71+FwrXQ08xRURHRTI1MTQARWRnZQ==
[38;5;242mbuild: .github#8
[0m
[0;33m![0m Failed to restore: Cache service responded with 400
[38;5;242mbuild: .github#26
[0m
[0;33m![0m Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4, extractions/setup-just@v2. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
[38;5;242minstall-smoke: .github#2
[0m
[0;1;39mRefreshing run status every 3 seconds. Press Ctrl+C to quit.[0m

[0;33m*[0m [0;1;39mmaster[0m Publish · [0;36m32160158404[0m
Triggered via push about 6 minutes ago

[0;1;39mJOBS[0m
[0;32m✓[0m [0;1;39mrelease[0m in 11s (ID [0;36m95786865377[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run googleapis/release-please-action@v5
  [0;32m✓[0m Complete job
[0;32m✓[0m [0;1;39mbuild[0m in 10s (ID [0;36m95786940152[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Run astral-sh/setup-uv@v4
  [0;32m✓[0m Set up Python
  [0;32m✓[0m Build package
  [0;32m✓[0m Run actions/upload-artifact@v4
  [0;32m✓[0m Post Run astral-sh/setup-uv@v4
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[0;32m✓[0m [0;1;39minstall-smoke[0m in 6m12s (ID [0;36m95787010707[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Run actions/download-artifact@v4
  [0;32m✓[0m Check out SASE
  [0;32m✓[0m Check out SASE Rust core
  [0;32m✓[0m Run astral-sh/setup-uv@v4
  [0;32m✓[0m Run extractions/setup-just@v2
  [0;32m✓[0m Run dtolnay/rust-toolchain@stable
  [0;32m✓[0m Set up Python
  [0;32m✓[0m Install built sase-research-artifacts wheel into a fresh venv
  [0;32m✓[0m Smoke check
  [0;32m✓[0m Assemble the real artifact provider registry
  [0;32m✓[0m Post Run astral-sh/setup-uv@v4
  [0;32m✓[0m Post Check out SASE Rust core
  [0;32m✓[0m Post Check out SASE
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[0;33m*[0m [0;1;39mpublish[0m (ID [0;36m95788835674[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/download-artifact@v4
  [0;33m*[0m Run pypa/gh-action-pypi-publish@release/v1
  [0;33m*[0m Post Run pypa/gh-action-pypi-publish@release/v1

[0;1;39mANNOTATIONS[0m
[0;33m![0m Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
[38;5;242mbuild: .github#2
[0m
[0;33m![0m Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0a4eEagAAAADZtmRcHu09TbNQl71+FwrXQ08xRURHRTI1MTQARWRnZQ==
[38;5;242mbuild: .github#8
[0m
[0;33m![0m Failed to restore: Cache service responded with 400
[38;5;242mbuild: .github#26
[0m
[0;33m![0m Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4, extractions/setup-just@v2. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
[38;5;242minstall-smoke: .github#2
[0m
[0;1;39mRefreshing run status every 3 seconds. Press Ctrl+C to quit.[0m

[0;33m*[0m [0;1;39mmaster[0m Publish · [0;36m32160158404[0m
Triggered via push about 6 minutes ago

[0;1;39mJOBS[0m
[0;32m✓[0m [0;1;39mrelease[0m in 11s (ID [0;36m95786865377[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run googleapis/release-please-action@v5
  [0;32m✓[0m Complete job
[0;32m✓[0m [0;1;39mbuild[0m in 10s (ID [0;36m95786940152[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Run astral-sh/setup-uv@v4
  [0;32m✓[0m Set up Python
  [0;32m✓[0m Build package
  [0;32m✓[0m Run actions/upload-artifact@v4
  [0;32m✓[0m Post Run astral-sh/setup-uv@v4
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[0;32m✓[0m [0;1;39minstall-smoke[0m in 6m12s (ID [0;36m95787010707[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Run actions/download-artifact@v4
  [0;32m✓[0m Check out SASE
  [0;32m✓[0m Check out SASE Rust core
  [0;32m✓[0m Run astral-sh/setup-uv@v4
  [0;32m✓[0m Run extractions/setup-just@v2
  [0;32m✓[0m Run dtolnay/rust-toolchain@stable
  [0;32m✓[0m Set up Python
  [0;32m✓[0m Install built sase-research-artifacts wheel into a fresh venv
  [0;32m✓[0m Smoke check
  [0;32m✓[0m Assemble the real artifact provider registry
  [0;32m✓[0m Post Run astral-sh/setup-uv@v4
  [0;32m✓[0m Post Check out SASE Rust core
  [0;32m✓[0m Post Check out SASE
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[0;33m*[0m [0;1;39mpublish[0m (ID [0;36m95788835674[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/download-artifact@v4
  [0;33m*[0m Run pypa/gh-action-pypi-publish@release/v1
  [0;33m*[0m Post Run pypa/gh-action-pypi-publish@release/v1

[0;1;39mANNOTATIONS[0m
[0;33m![0m Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
[38;5;242mbuild: .github#2
[0m
[0;33m![0m Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0a4eEagAAAADZtmRcHu09TbNQl71+FwrXQ08xRURHRTI1MTQARWRnZQ==
[38;5;242mbuild: .github#8
[0m
[0;33m![0m Failed to restore: Cache service responded with 400
[38;5;242mbuild: .github#26
[0m
[0;33m![0m Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4, extractions/setup-just@v2. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
[38;5;242minstall-smoke: .github#2
[0m
[0;1;39mRefreshing run status every 3 seconds. Press Ctrl+C to quit.[0m

[0;33m*[0m [0;1;39mmaster[0m Publish · [0;36m32160158404[0m
Triggered via push about 7 minutes ago

[0;1;39mJOBS[0m
[0;32m✓[0m [0;1;39mrelease[0m in 11s (ID [0;36m95786865377[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run googleapis/release-please-action@v5
  [0;32m✓[0m Complete job
[0;32m✓[0m [0;1;39mbuild[0m in 10s (ID [0;36m95786940152[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Run astral-sh/setup-uv@v4
  [0;32m✓[0m Set up Python
  [0;32m✓[0m Build package
  [0;32m✓[0m Run actions/upload-artifact@v4
  [0;32m✓[0m Post Run astral-sh/setup-uv@v4
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[0;32m✓[0m [0;1;39minstall-smoke[0m in 6m12s (ID [0;36m95787010707[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Run actions/download-artifact@v4
  [0;32m✓[0m Check out SASE
  [0;32m✓[0m Check out SASE Rust core
  [0;32m✓[0m Run astral-sh/setup-uv@v4
  [0;32m✓[0m Run extractions/setup-just@v2
  [0;32m✓[0m Run dtolnay/rust-toolchain@stable
  [0;32m✓[0m Set up Python
  [0;32m✓[0m Install built sase-research-artifacts wheel into a fresh venv
  [0;32m✓[0m Smoke check
  [0;32m✓[0m Assemble the real artifact provider registry
  [0;32m✓[0m Post Run astral-sh/setup-uv@v4
  [0;32m✓[0m Post Check out SASE Rust core
  [0;32m✓[0m Post Check out SASE
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[0;33m*[0m [0;1;39mpublish[0m (ID [0;36m95788835674[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/download-artifact@v4
  [0;33m*[0m Run pypa/gh-action-pypi-publish@release/v1
  [0;33m*[0m Post Run pypa/gh-action-pypi-publish@release/v1

[0;1;39mANNOTATIONS[0m
[0;33m![0m Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
[38;5;242mbuild: .github#2
[0m
[0;33m![0m Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0a4eEagAAAADZtmRcHu09TbNQl71+FwrXQ08xRURHRTI1MTQARWRnZQ==
[38;5;242mbuild: .github#8
[0m
[0;33m![0m Failed to restore: Cache service responded with 400
[38;5;242mbuild: .github#26
[0m
[0;33m![0m Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4, extractions/setup-just@v2. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
[38;5;242minstall-smoke: .github#2
[0m
[0;1;39mRefreshing run status every 3 seconds. Press Ctrl+C to quit.[0m

[0;33m*[0m [0;1;39mmaster[0m Publish · [0;36m32160158404[0m
Triggered via push about 7 minutes ago

[0;1;39mJOBS[0m
[0;32m✓[0m [0;1;39mrelease[0m in 11s (ID [0;36m95786865377[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run googleapis/release-please-action@v5
  [0;32m✓[0m Complete job
[0;32m✓[0m [0;1;39mbuild[0m in 10s (ID [0;36m95786940152[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Run astral-sh/setup-uv@v4
  [0;32m✓[0m Set up Python
  [0;32m✓[0m Build package
  [0;32m✓[0m Run actions/upload-artifact@v4
  [0;32m✓[0m Post Run astral-sh/setup-uv@v4
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[0;32m✓[0m [0;1;39minstall-smoke[0m in 6m12s (ID [0;36m95787010707[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Run actions/download-artifact@v4
  [0;32m✓[0m Check out SASE
  [0;32m✓[0m Check out SASE Rust core
  [0;32m✓[0m Run astral-sh/setup-uv@v4
  [0;32m✓[0m Run extractions/setup-just@v2
  [0;32m✓[0m Run dtolnay/rust-toolchain@stable
  [0;32m✓[0m Set up Python
  [0;32m✓[0m Install built sase-research-artifacts wheel into a fresh venv
  [0;32m✓[0m Smoke check
  [0;32m✓[0m Assemble the real artifact provider registry
  [0;32m✓[0m Post Run astral-sh/setup-uv@v4
  [0;32m✓[0m Post Check out SASE Rust core
  [0;32m✓[0m Post Check out SASE
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[0;33m*[0m [0;1;39mpublish[0m (ID [0;36m95788835674[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/download-artifact@v4
  [0;33m*[0m Run pypa/gh-action-pypi-publish@release/v1
  [0;33m*[0m Post Run pypa/gh-action-pypi-publish@release/v1

[0;1;39mANNOTATIONS[0m
[0;33m![0m Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
[38;5;242mbuild: .github#2
[0m
[0;33m![0m Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0a4eEagAAAADZtmRcHu09TbNQl71+FwrXQ08xRURHRTI1MTQARWRnZQ==
[38;5;242mbuild: .github#8
[0m
[0;33m![0m Failed to restore: Cache service responded with 400
[38;5;242mbuild: .github#26
[0m
[0;33m![0m Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4, extractions/setup-just@v2. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
[38;5;242minstall-smoke: .github#2
[0m
[0;32m✓[0m [0;1;39mmaster[0m Publish · [0;36m32160158404[0m
Triggered via push about 7 minutes ago

[0;1;39mJOBS[0m
[0;32m✓[0m [0;1;39mrelease[0m in 11s (ID [0;36m95786865377[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run googleapis/release-please-action@v5
  [0;32m✓[0m Complete job
[0;32m✓[0m [0;1;39mbuild[0m in 10s (ID [0;36m95786940152[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Run astral-sh/setup-uv@v4
  [0;32m✓[0m Set up Python
  [0;32m✓[0m Build package
  [0;32m✓[0m Run actions/upload-artifact@v4
  [0;32m✓[0m Post Run astral-sh/setup-uv@v4
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[0;32m✓[0m [0;1;39minstall-smoke[0m in 6m12s (ID [0;36m95787010707[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Run actions/download-artifact@v4
  [0;32m✓[0m Check out SASE
  [0;32m✓[0m Check out SASE Rust core
  [0;32m✓[0m Run astral-sh/setup-uv@v4
  [0;32m✓[0m Run extractions/setup-just@v2
  [0;32m✓[0m Run dtolnay/rust-toolchain@stable
  [0;32m✓[0m Set up Python
  [0;32m✓[0m Install built sase-research-artifacts wheel into a fresh venv
  [0;32m✓[0m Smoke check
  [0;32m✓[0m Assemble the real artifact provider registry
  [0;32m✓[0m Post Run astral-sh/setup-uv@v4
  [0;32m✓[0m Post Check out SASE Rust core
  [0;32m✓[0m Post Check out SASE
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[0;32m✓[0m [0;1;39mpublish[0m in 17s (ID [0;36m95788835674[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/download-artifact@v4
  [0;32m✓[0m Run pypa/gh-action-pypi-publish@release/v1
  [0;32m✓[0m Post Run pypa/gh-action-pypi-publish@release/v1
  [0;32m✓[0m Complete job

[0;1;39mANNOTATIONS[0m
[0;33m![0m Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/upload-artifact@v4, astral-sh/setup-uv@v4. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
[38;5;242mbuild: .github#2
[0m
[0;33m![0m Failed to save: <h2>Our services aren't available right now</h2><p>We're working to restore all services as soon as possible. Please check back soon.</p>0a4eEagAAAADZtmRcHu09TbNQl71+FwrXQ08xRURHRTI1MTQARWRnZQ==
[38;5;242mbuild: .github#8
[0m
[0;33m![0m Failed to restore: Cache service responded with 400
[38;5;242mbuild: .github#26
[0m
[0;33m![0m Node.js 20 is deprecated. The following actions target Node.js 20 but are being forced to run on Node.js 24: actions/checkout@v4, actions/download-artifact@v4, astral-sh/setup-uv@v4, extractions/setup-just@v2. For more information see: https://github.blog/changelog/2025-09-19-deprecation-of-node-20-on-github-actions-runners/
[38;5;242minstall-smoke: .github#2
[0m

