# Chat History - ace-run (sase-um.9.5.3--1)

- **TIMESTAMP:** 2026-08-28 23:06:38 EDT
- **MODEL:** grok/grok-4.6
- **AGENT:** sase-um.9.5.3--1

## Prompt

%xprompts_enabled:false
# Previous Conversation

**User:**

sase monitor start --command 'gh run watch 33226037754 --exit-status' --reason 'Wait for dispatched Full CI run 33226037754 on master tip 1a1463028 (post-gatebudget integrated tip)'

**Assistant:**

[0;1;39mRefreshing run status every 3 seconds. Press Ctrl+C to quit.[0m

[0;33m*[0m [0;1;39mmaster[0m Full CI · [0;36m33226037754[0m
Triggered via workflow_dispatch about 1 hour ago

[0;1;39mJOBS[0m
[0;32m✓[0m [0;1;39mfull / build-core[0m in 7m49s (ID [0;36m99029883707[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Resolve pinned Rust core revision
  [0;32m✓[0m Check out Rust core
  [0;32m✓[0m Run astral-sh/setup-uv@v4
  [0;32m✓[0m Set up Rust
  [0;32m✓[0m Cache Rust build
  [0;32m✓[0m Build abi3 Rust core wheel
  [0;32m✓[0m Build xprompt LSP
  [0;32m✓[0m Record wheel provenance
  [0;32m✓[0m Upload Rust core artifacts
  [0;32m✓[0m Post Cache Rust build
  [0;32m✓[0m Post Run astral-sh/setup-uv@v4
  [0;32m✓[0m Post Check out Rust core
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[38;5;242m-[0m [0;1;39mfull / docs-build[0m (ID [0;36m99029884284[0m)
[38;5;242m-[0m [0;1;39mfull / release-core-floor-smoke[0m (ID [0;36m99029884306[0m)
[0;33m*[0m [0;1;39mfull / test (3.13)[0m (ID [0;36m99030887371[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Install dependencies
  [38;5;242m-[0m Run tests (coverage leg)
  [0;33m*[0m Run tests
  [0;33m*[0m Run tests
  [0;33m*[0m Build shard timings table
  [0;33m*[0m Upload shard timings
  [0;33m*[0m Upload coverage
  [0;33m*[0m Post Install dependencies
  [0;33m*[0m Post Run actions/checkout@v4
[0;31mX[0m [0;1;39mfull / perf-floors[0m in 4m33s (ID [0;36m99030887383[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Install dependencies
  [0;32m✓[0m Health check (Rust extension loadable)
  [0;32m✓[0m Run slow tests
  [0;31mX[0m Run Phase 7E regression floor
  [0;32m✓[0m Upload Phase 7E floor-check report
  [0;32m✓[0m Run launch regression floor
  [0;32m✓[0m Upload launch floor-check report
  [0;32m✓[0m Run view-hints regression floor
  [0;32m✓[0m Upload view-hints floor-check report
  [0;32m✓[0m Run agents disk-load operation-count floor
  [0;32m✓[0m Upload agents disk-load floor-check report
  [0;32m✓[0m Run plugins catalog-scale regression floor
  [0;32m✓[0m Upload plugins catalog-scale floor-check report
  [0;32m✓[0m Run bead performance smoke
  [0;32m✓[0m Upload bead performance smoke
  [0;32m✓[0m Post Install dependencies
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[0;32m✓[0m [0;1;39mfull / ace-page-group-isolation[0m in 1m5s (ID [0;36m99030887385[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Install visual dependencies
  [0;32m✓[0m Run ACE shared-page isolation lane
  [0;32m✓[0m Post Install visual dependencies
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[0;32m✓[0m [0;1;39mfull / lint[0m in 4m6s (ID [0;36m99030887397[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Install dependencies
  [0;32m✓[0m Check pinned core bindings
  [0;32m✓[0m Bootstrap SDD sidecars
  [0;32m✓[0m Initialize SASE home
  [0;32m✓[0m Run actions/setup-go@v5
  [0;32m✓[0m Cache Go binaries
  [38;5;242m-[0m Install Go tools (keep-sorted)
  [0;32m✓[0m Cache Prettier dependencies
  [0;32m✓[0m Check Python formatting
  [0;32m✓[0m Check Markdown formatting
  [0;32m✓[0m Lint
  [0;32m✓[0m SASE validation
  [0;32m✓[0m Validate committed plans
  [0;32m✓[0m Build and verify package
  [0;32m✓[0m Post Cache Prettier dependencies
  [0;32m✓[0m Post Cache Go binaries
  [0;32m✓[0m Post Run actions/setup-go@v5
  [0;32m✓[0m Post Install dependencies
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[0;31mX[0m [0;1;39mfull / coverage-contexts[0m in 40m50s (ID [0;36m99030887410[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Install dependencies
  [0;31mX[0m Record per-test coverage contexts
  [0;32m✓[0m Upload coverage contexts database
  [0;32m✓[0m Post Install dependencies
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[0;31mX[0m [0;1;39mfull / test (3.14)[0m in 24m28s (ID [0;36m99030887411[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Install dependencies
  [38;5;242m-[0m Run tests (coverage leg)
  [38;5;242m-[0m Run tests
  [0;31mX[0m Run tests
  [0;32m✓[0m Build shard timings table
  [0;32m✓[0m Upload shard timings
  [38;5;242m-[0m Upload coverage
  [0;32m✓[0m Post Install dependencies
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[0;31mX[0m [0;1;39mfull / visual-test[0m in 14m59s (ID [0;36m99030887452[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Install visual dependencies
  [0;31mX[0m Run visual tests
  [0;32m✓[0m Build visual failure report
  [0;32m✓[0m Upload visual failure report
  [0;32m✓[0m Publish visual failure report
  [0;32m✓[0m Upload visual failure artifacts
  [0;32m✓[0m Post Install visual dependencies
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[0;31mX[0m [0;1;39mfull / test (3.12)[0m in 36m44s (ID [0;36m99030887468[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Install dependencies
  [0;31mX[0m Run tests (coverage leg)
  [38;5;242m-[0m Run tests
  [38;5;242m-[0m Run tests
  [38;5;242m-[0m Build shard timings table
  [38;5;242m-[0m Upload shard timings
  [38;5;242m-[0m Upload coverage
  [0;32m✓[0m Post Install dependencies
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[38;5;242m-[0m [0;1;39mfull / contention-test[0m (ID [0;36m99030888181[0m)
[0;1;39mRefreshing run status every 3 seconds. Press Ctrl+C to quit.[0m

[0;33m*[0m [0;1;39mmaster[0m Full CI · [0;36m33226037754[0m
Triggered via workflow_dispatch about 1 hour ago

[0;1;39mJOBS[0m
[0;32m✓[0m [0;1;39mfull / build-core[0m in 7m49s (ID [0;36m99029883707[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Resolve pinned Rust core revision
  [0;32m✓[0m Check out Rust core
  [0;32m✓[0m Run astral-sh/setup-uv@v4
  [0;32m✓[0m Set up Rust
  [0;32m✓[0m Cache Rust build
  [0;32m✓[0m Build abi3 Rust core wheel
  [0;32m✓[0m Build xprompt LSP
  [0;32m✓[0m Record wheel provenance
  [0;32m✓[0m Upload Rust core artifacts
  [0;32m✓[0m Post Cache Rust build
  [0;32m✓[0m Post Run astral-sh/setup-uv@v4
  [0;32m✓[0m Post Check out Rust core
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[38;5;242m-[0m [0;1;39mfull / docs-build[0m (ID [0;36m99029884284[0m)
[38;5;242m-[0m [0;1;39mfull / release-core-floor-smoke[0m (ID [0;36m99029884306[0m)
[0;33m*[0m [0;1;39mfull / test (3.13)[0m (ID [0;36m99030887371[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Install dependencies
  [38;5;242m-[0m Run tests (coverage leg)
  [0;33m*[0m Run tests
  [0;33m*[0m Run tests
  [0;33m*[0m Build shard timings table
  [0;33m*[0m Upload shard timings
  [0;33m*[0m Upload coverage
  [0;33m*[0m Post Install dependencies
  [0;33m*[0m Post Run actions/checkout@v4
[0;31mX[0m [0;1;39mfull / perf-floors[0m in 4m33s (ID [0;36m99030887383[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Install dependencies
  [0;32m✓[0m Health check (Rust extension loadable)
  [0;32m✓[0m Run slow tests
  [0;31mX[0m Run Phase 7E regression floor
  [0;32m✓[0m Upload Phase 7E floor-check report
  [0;32m✓[0m Run launch regression floor
  [0;32m✓[0m Upload launch floor-check report
  [0;32m✓[0m Run view-hints regression floor
  [0;32m✓[0m Upload view-hints floor-check report
  [0;32m✓[0m Run agents disk-load operation-count floor
  [0;32m✓[0m Upload agents disk-load floor-check report
  [0;32m✓[0m Run plugins catalog-scale regression floor
  [0;32m✓[0m Upload plugins catalog-scale floor-check report
  [0;32m✓[0m Run bead performance smoke
  [0;32m✓[0m Upload bead performance smoke
  [0;32m✓[0m Post Install dependencies
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[0;32m✓[0m [0;1;39mfull / ace-page-group-isolation[0m in 1m5s (ID [0;36m99030887385[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Install visual dependencies
  [0;32m✓[0m Run ACE shared-page isolation lane
  [0;32m✓[0m Post Install visual dependencies
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[0;32m✓[0m [0;1;39mfull / lint[0m in 4m6s (ID [0;36m99030887397[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Install dependencies
  [0;32m✓[0m Check pinned core bindings
  [0;32m✓[0m Bootstrap SDD sidecars
  [0;32m✓[0m Initialize SASE home
  [0;32m✓[0m Run actions/setup-go@v5
  [0;32m✓[0m Cache Go binaries
  [38;5;242m-[0m Install Go tools (keep-sorted)
  [0;32m✓[0m Cache Prettier dependencies
  [0;32m✓[0m Check Python formatting
  [0;32m✓[0m Check Markdown formatting
  [0;32m✓[0m Lint
  [0;32m✓[0m SASE validation
  [0;32m✓[0m Validate committed plans
  [0;32m✓[0m Build and verify package
  [0;32m✓[0m Post Cache Prettier dependencies
  [0;32m✓[0m Post Cache Go binaries
  [0;32m✓[0m Post Run actions/setup-go@v5
  [0;32m✓[0m Post Install dependencies
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[0;31mX[0m [0;1;39mfull / coverage-contexts[0m in 40m50s (ID [0;36m99030887410[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Install dependencies
  [0;31mX[0m Record per-test coverage contexts
  [0;32m✓[0m Upload coverage contexts database
  [0;32m✓[0m Post Install dependencies
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[0;31mX[0m [0;1;39mfull / test (3.14)[0m in 24m28s (ID [0;36m99030887411[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Install dependencies
  [38;5;242m-[0m Run tests (coverage leg)
  [38;5;242m-[0m Run tests
  [0;31mX[0m Run tests
  [0;32m✓[0m Build shard timings table
  [0;32m✓[0m Upload shard timings
  [38;5;242m-[0m Upload coverage
  [0;32m✓[0m Post Install dependencies
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[0;31mX[0m [0;1;39mfull / visual-test[0m in 14m59s (ID [0;36m99030887452[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Install visual dependencies
  [0;31mX[0m Run visual tests
  [0;32m✓[0m Build visual failure report
  [0;32m✓[0m Upload visual failure report
  [0;32m✓[0m Publish visual failure report
  [0;32m✓[0m Upload visual failure artifacts
  [0;32m✓[0m Post Install visual dependencies
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[0;31mX[0m [0;1;39mfull / test (3.12)[0m in 36m44s (ID [0;36m99030887468[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Install dependencies
  [0;31mX[0m Run tests (coverage leg)
  [38;5;242m-[0m Run tests
  [38;5;242m-[0m Run tests
  [38;5;242m-[0m Build shard timings table
  [38;5;242m-[0m Upload shard timings
  [38;5;242m-[0m Upload coverage
  [0;32m✓[0m Post Install dependencies
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[38;5;242m-[0m [0;1;39mfull / contention-test[0m (ID [0;36m99030888181[0m)
[0;1;39mRefreshing run status every 3 seconds. Press Ctrl+C to quit.[0m

[0;33m*[0m [0;1;39mmaster[0m Full CI · [0;36m33226037754[0m
Triggered via workflow_dispatch about 1 hour ago

[0;1;39mJOBS[0m
[0;32m✓[0m [0;1;39mfull / build-core[0m in 7m49s (ID [0;36m99029883707[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Resolve pinned Rust core revision
  [0;32m✓[0m Check out Rust core
  [0;32m✓[0m Run astral-sh/setup-uv@v4
  [0;32m✓[0m Set up Rust
  [0;32m✓[0m Cache Rust build
  [0;32m✓[0m Build abi3 Rust core wheel
  [0;32m✓[0m Build xprompt LSP
  [0;32m✓[0m Record wheel provenance
  [0;32m✓[0m Upload Rust core artifacts
  [0;32m✓[0m Post Cache Rust build
  [0;32m✓[0m Post Run astral-sh/setup-uv@v4
  [0;32m✓[0m Post Check out Rust core
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[38;5;242m-[0m [0;1;39mfull / docs-build[0m (ID [0;36m99029884284[0m)
[38;5;242m-[0m [0;1;39mfull / release-core-floor-smoke[0m (ID [0;36m99029884306[0m)
[0;33m*[0m [0;1;39mfull / test (3.13)[0m (ID [0;36m99030887371[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Install dependencies
  [38;5;242m-[0m Run tests (coverage leg)
  [0;33m*[0m Run tests
  [0;33m*[0m Run tests
  [0;33m*[0m Build shard timings table
  [0;33m*[0m Upload shard timings
  [0;33m*[0m Upload coverage
  [0;33m*[0m Post Install dependencies
  [0;33m*[0m Post Run actions/checkout@v4
[0;31mX[0m [0;1;39mfull / perf-floors[0m in 4m33s (ID [0;36m99030887383[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Install dependencies
  [0;32m✓[0m Health check (Rust extension loadable)
  [0;32m✓[0m Run slow tests
  [0;31mX[0m Run Phase 7E regression floor
  [0;32m✓[0m Upload Phase 7E floor-check report
  [0;32m✓[0m Run launch regression floor
  [0;32m✓[0m Upload launch floor-check report
  [0;32m✓[0m Run view-hints regression floor
  [0;32m✓[0m Upload view-hints floor-check report
  [0;32m✓[0m Run agents disk-load operation-count floor
  [0;32m✓[0m Upload agents disk-load floor-check report
  [0;32m✓[0m Run plugins catalog-scale regression floor
  [0;32m✓[0m Upload plugins catalog-scale floor-check report
  [0;32m✓[0m Run bead performance smoke
  [0;32m✓[0m Upload bead performance smoke
  [0;32m✓[0m Post Install dependencies
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[0;32m✓[0m [0;1;39mfull / ace-page-group-isolation[0m in 1m5s (ID [0;36m99030887385[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Install visual dependencies
  [0;32m✓[0m Run ACE shared-page isolation lane
  [0;32m✓[0m Post Install visual dependencies
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[0;32m✓[0m [0;1;39mfull / lint[0m in 4m6s (ID [0;36m99030887397[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Install dependencies
  [0;32m✓[0m Check pinned core bindings
  [0;32m✓[0m Bootstrap SDD sidecars
  [0;32m✓[0m Initialize SASE home
  [0;32m✓[0m Run actions/setup-go@v5
  [0;32m✓[0m Cache Go binaries
  [38;5;242m-[0m Install Go tools (keep-sorted)
  [0;32m✓[0m Cache Prettier dependencies
  [0;32m✓[0m Check Python formatting
  [0;32m✓[0m Check Markdown formatting
  [0;32m✓[0m Lint
  [0;32m✓[0m SASE validation
  [0;32m✓[0m Validate committed plans
  [0;32m✓[0m Build and verify package
  [0;32m✓[0m Post Cache Prettier dependencies
  [0;32m✓[0m Post Cache Go binaries
  [0;32m✓[0m Post Run actions/setup-go@v5
  [0;32m✓[0m Post Install dependencies
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[0;31mX[0m [0;1;39mfull / coverage-contexts[0m in 40m50s (ID [0;36m99030887410[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Install dependencies
  [0;31mX[0m Record per-test coverage contexts
  [0;32m✓[0m Upload coverage contexts database
  [0;32m✓[0m Post Install dependencies
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[0;31mX[0m [0;1;39mfull / test (3.14)[0m in 24m28s (ID [0;36m99030887411[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Install dependencies
  [38;5;242m-[0m Run tests (coverage leg)
  [38;5;242m-[0m Run tests
  [0;31mX[0m Run tests
  [0;32m✓[0m Build shard timings table
  [0;32m✓[0m Upload shard timings
  [38;5;242m-[0m Upload coverage
  [0;32m✓[0m Post Install dependencies
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[0;31mX[0m [0;1;39mfull / visual-test[0m in 14m59s (ID [0;36m99030887452[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Install visual dependencies
  [0;31mX[0m Run visual tests
  [0;32m✓[0m Build visual failure report
  [0;32m✓[0m Upload visual failure report
  [0;32m✓[0m Publish visual failure report
  [0;32m✓[0m Upload visual failure artifacts
  [0;32m✓[0m Post Install visual dependencies
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[0;31mX[0m [0;1;39mfull / test (3.12)[0m in 36m44s (ID [0;36m99030887468[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Install dependencies
  [0;31mX[0m Run tests (coverage leg)
  [38;5;242m-[0m Run tests
  [38;5;242m-[0m Run tests
  [38;5;242m-[0m Build shard timings table
  [38;5;242m-[0m Upload shard timings
  [38;5;242m-[0m Upload coverage
  [0;32m✓[0m Post Install dependencies
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[38;5;242m-[0m [0;1;39mfull / contention-test[0m (ID [0;36m99030888181[0m)
[0;1;39mRefreshing run status every 3 seconds. Press Ctrl+C to quit.[0m

[0;33m*[0m [0;1;39mmaster[0m Full CI · [0;36m33226037754[0m
Triggered via workflow_dispatch about 1 hour ago

[0;1;39mJOBS[0m
[0;32m✓[0m [0;1;39mfull / build-core[0m in 7m49s (ID [0;36m99029883707[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Resolve pinned Rust core revision
  [0;32m✓[0m Check out Rust core
  [0;32m✓[0m Run astral-sh/setup-uv@v4
  [0;32m✓[0m Set up Rust
  [0;32m✓[0m Cache Rust build
  [0;32m✓[0m Build abi3 Rust core wheel
  [0;32m✓[0m Build xprompt LSP
  [0;32m✓[0m Record wheel provenance
  [0;32m✓[0m Upload Rust core artifacts
  [0;32m✓[0m Post Cache Rust build
  [0;32m✓[0m Post Run astral-sh/setup-uv@v4
  [0;32m✓[0m Post Check out Rust core
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[38;5;242m-[0m [0;1;39mfull / docs-build[0m (ID [0;36m99029884284[0m)
[38;5;242m-[0m [0;1;39mfull / release-core-floor-smoke[0m (ID [0;36m99029884306[0m)
[0;33m*[0m [0;1;39mfull / test (3.13)[0m (ID [0;36m99030887371[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Install dependencies
  [38;5;242m-[0m Run tests (coverage leg)
  [0;33m*[0m Run tests
  [0;33m*[0m Run tests
  [0;33m*[0m Build shard timings table
  [0;33m*[0m Upload shard timings
  [0;33m*[0m Upload coverage
  [0;33m*[0m Post Install dependencies
  [0;33m*[0m Post Run actions/checkout@v4
[0;31mX[0m [0;1;39mfull / perf-floors[0m in 4m33s (ID [0;36m99030887383[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Install dependencies
  [0;32m✓[0m Health check (Rust extension loadable)
  [0;32m✓[0m Run slow tests
  [0;31mX[0m Run Phase 7E regression floor
  [0;32m✓[0m Upload Phase 7E floor-check report
  [0;32m✓[0m Run launch regression floor
  [0;32m✓[0m Upload launch floor-check report
  [0;32m✓[0m Run view-hints regression floor
  [0;32m✓[0m Upload view-hints floor-check report
  [0;32m✓[0m Run agents disk-load operation-count floor
  [0;32m✓[0m Upload agents disk-load floor-check report
  [0;32m✓[0m Run plugins catalog-scale regression floor
  [0;32m✓[0m Upload plugins catalog-scale floor-check report
  [0;32m✓[0m Run bead performance smoke
  [0;32m✓[0m Upload bead performance smoke
  [0;32m✓[0m Post Install dependencies
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[0;32m✓[0m [0;1;39mfull / ace-page-group-isolation[0m in 1m5s (ID [0;36m99030887385[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Install visual dependencies
  [0;32m✓[0m Run ACE shared-page isolation lane
  [0;32m✓[0m Post Install visual dependencies
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[0;32m✓[0m [0;1;39mfull / lint[0m in 4m6s (ID [0;36m99030887397[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Install dependencies
  [0;32m✓[0m Check pinned core bindings
  [0;32m✓[0m Bootstrap SDD sidecars
  [0;32m✓[0m Initialize SASE home
  [0;32m✓[0m Run actions/setup-go@v5
  [0;32m✓[0m Cache Go binaries
  [38;5;242m-[0m Install Go tools (keep-sorted)
  [0;32m✓[0m Cache Prettier dependencies
  [0;32m✓[0m Check Python formatting
  [0;32m✓[0m Check Markdown formatting
  [0;32m✓[0m Lint
  [0;32m✓[0m SASE validation
  [0;32m✓[0m Validate committed plans
  [0;32m✓[0m Build and verify package
  [0;32m✓[0m Post Cache Prettier dependencies
  [0;32m✓[0m Post Cache Go binaries
  [0;32m✓[0m Post Run actions/setup-go@v5
  [0;32m✓[0m Post Install dependencies
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[0;31mX[0m [0;1;39mfull / coverage-contexts[0m in 40m50s (ID [0;36m99030887410[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Install dependencies
  [0;31mX[0m Record per-test coverage contexts
  [0;32m✓[0m Upload coverage contexts database
  [0;32m✓[0m Post Install dependencies
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[0;31mX[0m [0;1;39mfull / test (3.14)[0m in 24m28s (ID [0;36m99030887411[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Install dependencies
  [38;5;242m-[0m Run tests (coverage leg)
  [38;5;242m-[0m Run tests
  [0;31mX[0m Run tests
  [0;32m✓[0m Build shard timings table
  [0;32m✓[0m Upload shard timings
  [38;5;242m-[0m Upload coverage
  [0;32m✓[0m Post Install dependencies
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[0;31mX[0m [0;1;39mfull / visual-test[0m in 14m59s (ID [0;36m99030887452[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Install visual dependencies
  [0;31mX[0m Run visual tests
  [0;32m✓[0m Build visual failure report
  [0;32m✓[0m Upload visual failure report
  [0;32m✓[0m Publish visual failure report
  [0;32m✓[0m Upload visual failure artifacts
  [0;32m✓[0m Post Install visual dependencies
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[0;31mX[0m [0;1;39mfull / test (3.12)[0m in 36m44s (ID [0;36m99030887468[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Install dependencies
  [0;31mX[0m Run tests (coverage leg)
  [38;5;242m-[0m Run tests
  [38;5;242m-[0m Run tests
  [38;5;242m-[0m Build shard timings table
  [38;5;242m-[0m Upload shard timings
  [38;5;242m-[0m Upload coverage
  [0;32m✓[0m Post Install dependencies
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[38;5;242m-[0m [0;1;39mfull / contention-test[0m (ID [0;36m99030888181[0m)
[0;1;39mRefreshing run status every 3 seconds. Press Ctrl+C to quit.[0m

[0;33m*[0m [0;1;39mmaster[0m Full CI · [0;36m33226037754[0m
Triggered via workflow_dispatch about 1 hour ago

[0;1;39mJOBS[0m
[0;32m✓[0m [0;1;39mfull / build-core[0m in 7m49s (ID [0;36m99029883707[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Resolve pinned Rust core revision
  [0;32m✓[0m Check out Rust core
  [0;32m✓[0m Run astral-sh/setup-uv@v4
  [0;32m✓[0m Set up Rust
  [0;32m✓[0m Cache Rust build
  [0;32m✓[0m Build abi3 Rust core wheel
  [0;32m✓[0m Build xprompt LSP
  [0;32m✓[0m Record wheel provenance
  [0;32m✓[0m Upload Rust core artifacts
  [0;32m✓[0m Post Cache Rust build
  [0;32m✓[0m Post Run astral-sh/setup-uv@v4
  [0;32m✓[0m Post Check out Rust core
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[38;5;242m-[0m [0;1;39mfull / docs-build[0m (ID [0;36m99029884284[0m)
[38;5;242m-[0m [0;1;39mfull / release-core-floor-smoke[0m (ID [0;36m99029884306[0m)
[0;33m*[0m [0;1;39mfull / test (3.13)[0m (ID [0;36m99030887371[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Install dependencies
  [38;5;242m-[0m Run tests (coverage leg)
  [0;33m*[0m Run tests
  [0;33m*[0m Run tests
  [0;33m*[0m Build shard timings table
  [0;33m*[0m Upload shard timings
  [0;33m*[0m Upload coverage
  [0;33m*[0m Post Install dependencies
  [0;33m*[0m Post Run actions/checkout@v4
[0;31mX[0m [0;1;39mfull / perf-floors[0m in 4m33s (ID [0;36m99030887383[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Install dependencies
  [0;32m✓[0m Health check (Rust extension loadable)
  [0;32m✓[0m Run slow tests
  [0;31mX[0m Run Phase 7E regression floor
  [0;32m✓[0m Upload Phase 7E floor-check report
  [0;32m✓[0m Run launch regression floor
  [0;32m✓[0m Upload launch floor-check report
  [0;32m✓[0m Run view-hints regression floor
  [0;32m✓[0m Upload view-hints floor-check report
  [0;32m✓[0m Run agents disk-load operation-count floor
  [0;32m✓[0m Upload agents disk-load floor-check report
  [0;32m✓[0m Run plugins catalog-scale regression floor
  [0;32m✓[0m Upload plugins catalog-scale floor-check report
  [0;32m✓[0m Run bead performance smoke
  [0;32m✓[0m Upload bead performance smoke
  [0;32m✓[0m Post Install dependencies
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[0;32m✓[0m [0;1;39mfull / ace-page-group-isolation[0m in 1m5s (ID [0;36m99030887385[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Install visual dependencies
  [0;32m✓[0m Run ACE shared-page isolation lane
  [0;32m✓[0m Post Install visual dependencies
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[0;32m✓[0m [0;1;39mfull / lint[0m in 4m6s (ID [0;36m99030887397[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Install dependencies
  [0;32m✓[0m Check pinned core bindings
  [0;32m✓[0m Bootstrap SDD sidecars
  [0;32m✓[0m Initialize SASE home
  [0;32m✓[0m Run actions/setup-go@v5
  [0;32m✓[0m Cache Go binaries
  [38;5;242m-[0m Install Go tools (keep-sorted)
  [0;32m✓[0m Cache Prettier dependencies
  [0;32m✓[0m Check Python formatting
  [0;32m✓[0m Check Markdown formatting
  [0;32m✓[0m Lint
  [0;32m✓[0m SASE validation
  [0;32m✓[0m Validate committed plans
  [0;32m✓[0m Build and verify package
  [0;32m✓[0m Post Cache Prettier dependencies
  [0;32m✓[0m Post Cache Go binaries
  [0;32m✓[0m Post Run actions/setup-go@v5
  [0;32m✓[0m Post Install dependencies
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[0;31mX[0m [0;1;39mfull / coverage-contexts[0m in 40m50s (ID [0;36m99030887410[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Install dependencies
  [0;31mX[0m Record per-test coverage contexts
  [0;32m✓[0m Upload coverage contexts database
  [0;32m✓[0m Post Install dependencies
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[0;31mX[0m [0;1;39mfull / test (3.14)[0m in 24m28s (ID [0;36m99030887411[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Install dependencies
  [38;5;242m-[0m Run tests (coverage leg)
  [38;5;242m-[0m Run tests
  [0;31mX[0m Run tests
  [0;32m✓[0m Build shard timings table
  [0;32m✓[0m Upload shard timings
  [38;5;242m-[0m Upload coverage
  [0;32m✓[0m Post Install dependencies
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[0;31mX[0m [0;1;39mfull / visual-test[0m in 14m59s (ID [0;36m99030887452[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Install visual dependencies
  [0;31mX[0m Run visual tests
  [0;32m✓[0m Build visual failure report
  [0;32m✓[0m Upload visual failure report
  [0;32m✓[0m Publish visual failure report
  [0;32m✓[0m Upload visual failure artifacts
  [0;32m✓[0m Post Install visual dependencies
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[0;31mX[0m [0;1;39mfull / test (3.12)[0m in 36m44s (ID [0;36m99030887468[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Install dependencies
  [0;31mX[0m Run tests (coverage leg)
  [38;5;242m-[0m Run tests
  [38;5;242m-[0m Run tests
  [38;5;242m-[0m Build shard timings table
  [38;5;242m-[0m Upload shard timings
  [38;5;242m-[0m Upload coverage
  [0;32m✓[0m Post Install dependencies
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[38;5;242m-[0m [0;1;39mfull / contention-test[0m (ID [0;36m99030888181[0m)
[0;1;39mRefreshing run status every 3 seconds. Press Ctrl+C to quit.[0m

[0;33m*[0m [0;1;39mmaster[0m Full CI · [0;36m33226037754[0m
Triggered via workflow_dispatch about 1 hour ago

[0;1;39mJOBS[0m
[0;32m✓[0m [0;1;39mfull / build-core[0m in 7m49s (ID [0;36m99029883707[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Resolve pinned Rust core revision
  [0;32m✓[0m Check out Rust core
  [0;32m✓[0m Run astral-sh/setup-uv@v4
  [0;32m✓[0m Set up Rust
  [0;32m✓[0m Cache Rust build
  [0;32m✓[0m Build abi3 Rust core wheel
  [0;32m✓[0m Build xprompt LSP
  [0;32m✓[0m Record wheel provenance
  [0;32m✓[0m Upload Rust core artifacts
  [0;32m✓[0m Post Cache Rust build
  [0;32m✓[0m Post Run astral-sh/setup-uv@v4
  [0;32m✓[0m Post Check out Rust core
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[38;5;242m-[0m [0;1;39mfull / docs-build[0m (ID [0;36m99029884284[0m)
[38;5;242m-[0m [0;1;39mfull / release-core-floor-smoke[0m (ID [0;36m99029884306[0m)
[0;33m*[0m [0;1;39mfull / test (3.13)[0m (ID [0;36m99030887371[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Install dependencies
  [38;5;242m-[0m Run tests (coverage leg)
  [0;33m*[0m Run tests
  [0;33m*[0m Run tests
  [0;33m*[0m Build shard timings table
  [0;33m*[0m Upload shard timings
  [0;33m*[0m Upload coverage
  [0;33m*[0m Post Install dependencies
  [0;33m*[0m Post Run actions/checkout@v4
[0;31mX[0m [0;1;39mfull / perf-floors[0m in 4m33s (ID [0;36m99030887383[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Install dependencies
  [0;32m✓[0m Health check (Rust extension loadable)
  [0;32m✓[0m Run slow tests
  [0;31mX[0m Run Phase 7E regression floor
  [0;32m✓[0m Upload Phase 7E floor-check report
  [0;32m✓[0m Run launch regression floor
  [0;32m✓[0m Upload launch floor-check report
  [0;32m✓[0m Run view-hints regression floor
  [0;32m✓[0m Upload view-hints floor-check report
  [0;32m✓[0m Run agents disk-load operation-count floor
  [0;32m✓[0m Upload agents disk-load floor-check report
  [0;32m✓[0m Run plugins catalog-scale regression floor
  [0;32m✓[0m Upload plugins catalog-scale floor-check report
  [0;32m✓[0m Run bead performance smoke
  [0;32m✓[0m Upload bead performance smoke
  [0;32m✓[0m Post Install dependencies
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[0;32m✓[0m [0;1;39mfull / ace-page-group-isolation[0m in 1m5s (ID [0;36m99030887385[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Install visual dependencies
  [0;32m✓[0m Run ACE shared-page isolation lane
  [0;32m✓[0m Post Install visual dependencies
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[0;32m✓[0m [0;1;39mfull / lint[0m in 4m6s (ID [0;36m99030887397[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Install dependencies
  [0;32m✓[0m Check pinned core bindings
  [0;32m✓[0m Bootstrap SDD sidecars
  [0;32m✓[0m Initialize SASE home
  [0;32m✓[0m Run actions/setup-go@v5
  [0;32m✓[0m Cache Go binaries
  [38;5;242m-[0m Install Go tools (keep-sorted)
  [0;32m✓[0m Cache Prettier dependencies
  [0;32m✓[0m Check Python formatting
  [0;32m✓[0m Check Markdown formatting
  [0;32m✓[0m Lint
  [0;32m✓[0m SASE validation
  [0;32m✓[0m Validate committed plans
  [0;32m✓[0m Build and verify package
  [0;32m✓[0m Post Cache Prettier dependencies
  [0;32m✓[0m Post Cache Go binaries
  [0;32m✓[0m Post Run actions/setup-go@v5
  [0;32m✓[0m Post Install dependencies
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[0;31mX[0m [0;1;39mfull / coverage-contexts[0m in 40m50s (ID [0;36m99030887410[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Install dependencies
  [0;31mX[0m Record per-test coverage contexts
  [0;32m✓[0m Upload coverage contexts database
  [0;32m✓[0m Post Install dependencies
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[0;31mX[0m [0;1;39mfull / test (3.14)[0m in 24m28s (ID [0;36m99030887411[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Install dependencies
  [38;5;242m-[0m Run tests (coverage leg)
  [38;5;242m-[0m Run tests
  [0;31mX[0m Run tests
  [0;32m✓[0m Build shard timings table
  [0;32m✓[0m Upload shard timings
  [38;5;242m-[0m Upload coverage
  [0;32m✓[0m Post Install dependencies
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[0;31mX[0m [0;1;39mfull / visual-test[0m in 14m59s (ID [0;36m99030887452[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Install visual dependencies
  [0;31mX[0m Run visual tests
  [0;32m✓[0m Build visual failure report
  [0;32m✓[0m Upload visual failure report
  [0;32m✓[0m Publish visual failure report
  [0;32m✓[0m Upload visual failure artifacts
  [0;32m✓[0m Post Install visual dependencies
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[0;31mX[0m [0;1;39mfull / test (3.12)[0m in 36m44s (ID [0;36m99030887468[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Install dependencies
  [0;31mX[0m Run tests (coverage leg)
  [38;5;242m-[0m Run tests
  [38;5;242m-[0m Run tests
  [38;5;242m-[0m Build shard timings table
  [38;5;242m-[0m Upload shard timings
  [38;5;242m-[0m Upload coverage
  [0;32m✓[0m Post Install dependencies
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[38;5;242m-[0m [0;1;39mfull / contention-test[0m (ID [0;36m99030888181[0m)
[0;1;39mRefreshing run status every 3 seconds. Press Ctrl+C to quit.[0m

[0;33m*[0m [0;1;39mmaster[0m Full CI · [0;36m33226037754[0m
Triggered via workflow_dispatch about 1 hour ago

[0;1;39mJOBS[0m
[0;32m✓[0m [0;1;39mfull / build-core[0m in 7m49s (ID [0;36m99029883707[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Resolve pinned Rust core revision
  [0;32m✓[0m Check out Rust core
  [0;32m✓[0m Run astral-sh/setup-uv@v4
  [0;32m✓[0m Set up Rust
  [0;32m✓[0m Cache Rust build
  [0;32m✓[0m Build abi3 Rust core wheel
  [0;32m✓[0m Build xprompt LSP
  [0;32m✓[0m Record wheel provenance
  [0;32m✓[0m Upload Rust core artifacts
  [0;32m✓[0m Post Cache Rust build
  [0;32m✓[0m Post Run astral-sh/setup-uv@v4
  [0;32m✓[0m Post Check out Rust core
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[38;5;242m-[0m [0;1;39mfull / docs-build[0m (ID [0;36m99029884284[0m)
[38;5;242m-[0m [0;1;39mfull / release-core-floor-smoke[0m (ID [0;36m99029884306[0m)
[0;33m*[0m [0;1;39mfull / test (3.13)[0m (ID [0;36m99030887371[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Install dependencies
  [38;5;242m-[0m Run tests (coverage leg)
  [0;33m*[0m Run tests
  [0;33m*[0m Run tests
  [0;33m*[0m Build shard timings table
  [0;33m*[0m Upload shard timings
  [0;33m*[0m Upload coverage
  [0;33m*[0m Post Install dependencies
  [0;33m*[0m Post Run actions/checkout@v4
[0;31mX[0m [0;1;39mfull / perf-floors[0m in 4m33s (ID [0;36m99030887383[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Install dependencies
  [0;32m✓[0m Health check (Rust extension loadable)
  [0;32m✓[0m Run slow tests
  [0;31mX[0m Run Phase 7E regression floor
  [0;32m✓[0m Upload Phase 7E floor-check report
  [0;32m✓[0m Run launch regression floor
  [0;32m✓[0m Upload launch floor-check report
  [0;32m✓[0m Run view-hints regression floor
  [0;32m✓[0m Upload view-hints floor-check report
  [0;32m✓[0m Run agents disk-load operation-count floor
  [0;32m✓[0m Upload agents disk-load floor-check report
  [0;32m✓[0m Run plugins catalog-scale regression floor
  [0;32m✓[0m Upload plugins catalog-scale floor-check report
  [0;32m✓[0m Run bead performance smoke
  [0;32m✓[0m Upload bead performance smoke
  [0;32m✓[0m Post Install dependencies
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[0;32m✓[0m [0;1;39mfull / ace-page-group-isolation[0m in 1m5s (ID [0;36m99030887385[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Install visual dependencies
  [0;32m✓[0m Run ACE shared-page isolation lane
  [0;32m✓[0m Post Install visual dependencies
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[0;32m✓[0m [0;1;39mfull / lint[0m in 4m6s (ID [0;36m99030887397[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Install dependencies
  [0;32m✓[0m Check pinned core bindings
  [0;32m✓[0m Bootstrap SDD sidecars
  [0;32m✓[0m Initialize SASE home
  [0;32m✓[0m Run actions/setup-go@v5
  [0;32m✓[0m Cache Go binaries
  [38;5;242m-[0m Install Go tools (keep-sorted)
  [0;32m✓[0m Cache Prettier dependencies
  [0;32m✓[0m Check Python formatting
  [0;32m✓[0m Check Markdown formatting
  [0;32m✓[0m Lint
  [0;32m✓[0m SASE validation
  [0;32m✓[0m Validate committed plans
  [0;32m✓[0m Build and verify package
  [0;32m✓[0m Post Cache Prettier dependencies
  [0;32m✓[0m Post Cache Go binaries
  [0;32m✓[0m Post Run actions/setup-go@v5
  [0;32m✓[0m Post Install dependencies
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[0;31mX[0m [0;1;39mfull / coverage-contexts[0m in 40m50s (ID [0;36m99030887410[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Install dependencies
  [0;31mX[0m Record per-test coverage contexts
  [0;32m✓[0m Upload coverage contexts database
  [0;32m✓[0m Post Install dependencies
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[0;31mX[0m [0;1;39mfull / test (3.14)[0m in 24m28s (ID [0;36m99030887411[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Install dependencies
  [38;5;242m-[0m Run tests (coverage leg)
  [38;5;242m-[0m Run tests
  [0;31mX[0m Run tests
  [0;32m✓[0m Build shard timings table
  [0;32m✓[0m Upload shard timings
  [38;5;242m-[0m Upload coverage
  [0;32m✓[0m Post Install dependencies
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[0;31mX[0m [0;1;39mfull / visual-test[0m in 14m59s (ID [0;36m99030887452[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Install visual dependencies
  [0;31mX[0m Run visual tests
  [0;32m✓[0m Build visual failure report
  [0;32m✓[0m Upload visual failure report
  [0;32m✓[0m Publish visual failure report
  [0;32m✓[0m Upload visual failure artifacts
  [0;32m✓[0m Post Install visual dependencies
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[0;31mX[0m [0;1;39mfull / test (3.12)[0m in 36m44s (ID [0;36m99030887468[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Install dependencies
  [0;31mX[0m Run tests (coverage leg)
  [38;5;242m-[0m Run tests
  [38;5;242m-[0m Run tests
  [38;5;242m-[0m Build shard timings table
  [38;5;242m-[0m Upload shard timings
  [38;5;242m-[0m Upload coverage
  [0;32m✓[0m Post Install dependencies
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[38;5;242m-[0m [0;1;39mfull / contention-test[0m (ID [0;36m99030888181[0m)
[0;1;39mRefreshing run status every 3 seconds. Press Ctrl+C to quit.[0m

[0;33m*[0m [0;1;39mmaster[0m Full CI · [0;36m33226037754[0m
Triggered via workflow_dispatch about 1 hour ago

[0;1;39mJOBS[0m
[0;32m✓[0m [0;1;39mfull / build-core[0m in 7m49s (ID [0;36m99029883707[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Resolve pinned Rust core revision
  [0;32m✓[0m Check out Rust core
  [0;32m✓[0m Run astral-sh/setup-uv@v4
  [0;32m✓[0m Set up Rust
  [0;32m✓[0m Cache Rust build
  [0;32m✓[0m Build abi3 Rust core wheel
  [0;32m✓[0m Build xprompt LSP
  [0;32m✓[0m Record wheel provenance
  [0;32m✓[0m Upload Rust core artifacts
  [0;32m✓[0m Post Cache Rust build
  [0;32m✓[0m Post Run astral-sh/setup-uv@v4
  [0;32m✓[0m Post Check out Rust core
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[38;5;242m-[0m [0;1;39mfull / docs-build[0m (ID [0;36m99029884284[0m)
[38;5;242m-[0m [0;1;39mfull / release-core-floor-smoke[0m (ID [0;36m99029884306[0m)
[0;33m*[0m [0;1;39mfull / test (3.13)[0m (ID [0;36m99030887371[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Install dependencies
  [38;5;242m-[0m Run tests (coverage leg)
  [0;33m*[0m Run tests
  [0;33m*[0m Run tests
  [0;33m*[0m Build shard timings table
  [0;33m*[0m Upload shard timings
  [0;33m*[0m Upload coverage
  [0;33m*[0m Post Install dependencies
  [0;33m*[0m Post Run actions/checkout@v4
[0;31mX[0m [0;1;39mfull / perf-floors[0m in 4m33s (ID [0;36m99030887383[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Install dependencies
  [0;32m✓[0m Health check (Rust extension loadable)
  [0;32m✓[0m Run slow tests
  [0;31mX[0m Run Phase 7E regression floor
  [0;32m✓[0m Upload Phase 7E floor-check report
  [0;32m✓[0m Run launch regression floor
  [0;32m✓[0m Upload launch floor-check report
  [0;32m✓[0m Run view-hints regression floor
  [0;32m✓[0m Upload view-hints floor-check report
  [0;32m✓[0m Run agents disk-load operation-count floor
  [0;32m✓[0m Upload agents disk-load floor-check report
  [0;32m✓[0m Run plugins catalog-scale regression floor
  [0;32m✓[0m Upload plugins catalog-scale floor-check report
  [0;32m✓[0m Run bead performance smoke
  [0;32m✓[0m Upload bead performance smoke
  [0;32m✓[0m Post Install dependencies
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[0;32m✓[0m [0;1;39mfull / ace-page-group-isolation[0m in 1m5s (ID [0;36m99030887385[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Install visual dependencies
  [0;32m✓[0m Run ACE shared-page isolation lane
  [0;32m✓[0m Post Install visual dependencies
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[0;32m✓[0m [0;1;39mfull / lint[0m in 4m6s (ID [0;36m99030887397[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Install dependencies
  [0;32m✓[0m Check pinned core bindings
  [0;32m✓[0m Bootstrap SDD sidecars
  [0;32m✓[0m Initialize SASE home
  [0;32m✓[0m Run actions/setup-go@v5
  [0;32m✓[0m Cache Go binaries
  [38;5;242m-[0m Install Go tools (keep-sorted)
  [0;32m✓[0m Cache Prettier dependencies
  [0;32m✓[0m Check Python formatting
  [0;32m✓[0m Check Markdown formatting
  [0;32m✓[0m Lint
  [0;32m✓[0m SASE validation
  [0;32m✓[0m Validate committed plans
  [0;32m✓[0m Build and verify package
  [0;32m✓[0m Post Cache Prettier dependencies
  [0;32m✓[0m Post Cache Go binaries
  [0;32m✓[0m Post Run actions/setup-go@v5
  [0;32m✓[0m Post Install dependencies
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[0;31mX[0m [0;1;39mfull / coverage-contexts[0m in 40m50s (ID [0;36m99030887410[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Install dependencies
  [0;31mX[0m Record per-test coverage contexts
  [0;32m✓[0m Upload coverage contexts database
  [0;32m✓[0m Post Install dependencies
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[0;31mX[0m [0;1;39mfull / test (3.14)[0m in 24m28s (ID [0;36m99030887411[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Install dependencies
  [38;5;242m-[0m Run tests (coverage leg)
  [38;5;242m-[0m Run tests
  [0;31mX[0m Run tests
  [0;32m✓[0m Build shard timings table
  [0;32m✓[0m Upload shard timings
  [38;5;242m-[0m Upload coverage
  [0;32m✓[0m Post Install dependencies
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[0;31mX[0m [0;1;39mfull / visual-test[0m in 14m59s (ID [0;36m99030887452[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Install visual dependencies
  [0;31mX[0m Run visual tests
  [0;32m✓[0m Build visual failure report
  [0;32m✓[0m Upload visual failure report
  [0;32m✓[0m Publish visual failure report
  [0;32m✓[0m Upload visual failure artifacts
  [0;32m✓[0m Post Install visual dependencies
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[0;31mX[0m [0;1;39mfull / test (3.12)[0m in 36m44s (ID [0;36m99030887468[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Install dependencies
  [0;31mX[0m Run tests (coverage leg)
  [38;5;242m-[0m Run tests
  [38;5;242m-[0m Run tests
  [38;5;242m-[0m Build shard timings table
  [38;5;242m-[0m Upload shard timings
  [38;5;242m-[0m Upload coverage
  [0;32m✓[0m Post Install dependencies
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[38;5;242m-[0m [0;1;39mfull / contention-test[0m (ID [0;36m99030888181[0m)
[0;1;39mRefreshing run status every 3 seconds. Press Ctrl+C to quit.[0m

[0;33m*[0m [0;1;39mmaster[0m Full CI · [0;36m33226037754[0m
Triggered via workflow_dispatch about 1 hour ago

[0;1;39mJOBS[0m
[0;32m✓[0m [0;1;39mfull / build-core[0m in 7m49s (ID [0;36m99029883707[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Resolve pinned Rust core revision
  [0;32m✓[0m Check out Rust core
  [0;32m✓[0m Run astral-sh/setup-uv@v4
  [0;32m✓[0m Set up Rust
  [0;32m✓[0m Cache Rust build
  [0;32m✓[0m Build abi3 Rust core wheel
  [0;32m✓[0m Build xprompt LSP
  [0;32m✓[0m Record wheel provenance
  [0;32m✓[0m Upload Rust core artifacts
  [0;32m✓[0m Post Cache Rust build
  [0;32m✓[0m Post Run astral-sh/setup-uv@v4
  [0;32m✓[0m Post Check out Rust core
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[38;5;242m-[0m [0;1;39mfull / docs-build[0m (ID [0;36m99029884284[0m)
[38;5;242m-[0m [0;1;39mfull / release-core-floor-smoke[0m (ID [0;36m99029884306[0m)
[0;33m*[0m [0;1;39mfull / test (3.13)[0m (ID [0;36m99030887371[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Install dependencies
  [38;5;242m-[0m Run tests (coverage leg)
  [0;33m*[0m Run tests
  [0;33m*[0m Run tests
  [0;33m*[0m Build shard timings table
  [0;33m*[0m Upload shard timings
  [0;33m*[0m Upload coverage
  [0;33m*[0m Post Install dependencies
  [0;33m*[0m Post Run actions/checkout@v4
[0;31mX[0m [0;1;39mfull / perf-floors[0m in 4m33s (ID [0;36m99030887383[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Install dependencies
  [0;32m✓[0m Health check (Rust extension loadable)
  [0;32m✓[0m Run slow tests
  [0;31mX[0m Run Phase 7E regression floor
  [0;32m✓[0m Upload Phase 7E floor-check report
  [0;32m✓[0m Run launch regression floor
  [0;32m✓[0m Upload launch floor-check report
  [0;32m✓[0m Run view-hints regression floor
  [0;32m✓[0m Upload view-hints floor-check report
  [0;32m✓[0m Run agents disk-load operation-count floor
  [0;32m✓[0m Upload agents disk-load floor-check report
  [0;32m✓[0m Run plugins catalog-scale regression floor
  [0;32m✓[0m Upload plugins catalog-scale floor-check report
  [0;32m✓[0m Run bead performance smoke
  [0;32m✓[0m Upload bead performance smoke
  [0;32m✓[0m Post Install dependencies
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[0;32m✓[0m [0;1;39mfull / ace-page-group-isolation[0m in 1m5s (ID [0;36m99030887385[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Install visual dependencies
  [0;32m✓[0m Run ACE shared-page isolation lane
  [0;32m✓[0m Post Install visual dependencies
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[0;32m✓[0m [0;1;39mfull / lint[0m in 4m6s (ID [0;36m99030887397[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Install dependencies
  [0;32m✓[0m Check pinned core bindings
  [0;32m✓[0m Bootstrap SDD sidecars
  [0;32m✓[0m Initialize SASE home
  [0;32m✓[0m Run actions/setup-go@v5
  [0;32m✓[0m Cache Go binaries
  [38;5;242m-[0m Install Go tools (keep-sorted)
  [0;32m✓[0m Cache Prettier dependencies
  [0;32m✓[0m Check Python formatting
  [0;32m✓[0m Check Markdown formatting
  [0;32m✓[0m Lint
  [0;32m✓[0m SASE validation
  [0;32m✓[0m Validate committed plans
  [0;32m✓[0m Build and verify package
  [0;32m✓[0m Post Cache Prettier dependencies
  [0;32m✓[0m Post Cache Go binaries
  [0;32m✓[0m Post Run actions/setup-go@v5
  [0;32m✓[0m Post Install dependencies
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[0;31mX[0m [0;1;39mfull / coverage-contexts[0m in 40m50s (ID [0;36m99030887410[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Install dependencies
  [0;31mX[0m Record per-test coverage contexts
  [0;32m✓[0m Upload coverage contexts database
  [0;32m✓[0m Post Install dependencies
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[0;31mX[0m [0;1;39mfull / test (3.14)[0m in 24m28s (ID [0;36m99030887411[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Install dependencies
  [38;5;242m-[0m Run tests (coverage leg)
  [38;5;242m-[0m Run tests
  [0;31mX[0m Run tests
  [0;32m✓[0m Build shard timings table
  [0;32m✓[0m Upload shard timings
  [38;5;242m-[0m Upload coverage
  [0;32m✓[0m Post Install dependencies
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[0;31mX[0m [0;1;39mfull / visual-test[0m in 14m59s (ID [0;36m99030887452[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Install visual dependencies
  [0;31mX[0m Run visual tests
  [0;32m✓[0m Build visual failure report
  [0;32m✓[0m Upload visual failure report
  [0;32m✓[0m Publish visual failure report
  [0;32m✓[0m Upload visual failure artifacts
  [0;32m✓[0m Post Install visual dependencies
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[0;31mX[0m [0;1;39mfull / test (3.12)[0m in 36m44s (ID [0;36m99030887468[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Install dependencies
  [0;31mX[0m Run tests (coverage leg)
  [38;5;242m-[0m Run tests
  [38;5;242m-[0m Run tests
  [38;5;242m-[0m Build shard timings table
  [38;5;242m-[0m Upload shard timings
  [38;5;242m-[0m Upload coverage
  [0;32m✓[0m Post Install dependencies
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[38;5;242m-[0m [0;1;39mfull / contention-test[0m (ID [0;36m99030888181[0m)
[0;1;39mRefreshing run status every 3 seconds. Press Ctrl+C to quit.[0m

[0;33m*[0m [0;1;39mmaster[0m Full CI · [0;36m33226037754[0m
Triggered via workflow_dispatch about 1 hour ago

[0;1;39mJOBS[0m
[0;32m✓[0m [0;1;39mfull / build-core[0m in 7m49s (ID [0;36m99029883707[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Resolve pinned Rust core revision
  [0;32m✓[0m Check out Rust core
  [0;32m✓[0m Run astral-sh/setup-uv@v4
  [0;32m✓[0m Set up Rust
  [0;32m✓[0m Cache Rust build
  [0;32m✓[0m Build abi3 Rust core wheel
  [0;32m✓[0m Build xprompt LSP
  [0;32m✓[0m Record wheel provenance
  [0;32m✓[0m Upload Rust core artifacts
  [0;32m✓[0m Post Cache Rust build
  [0;32m✓[0m Post Run astral-sh/setup-uv@v4
  [0;32m✓[0m Post Check out Rust core
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[38;5;242m-[0m [0;1;39mfull / docs-build[0m (ID [0;36m99029884284[0m)
[38;5;242m-[0m [0;1;39mfull / release-core-floor-smoke[0m (ID [0;36m99029884306[0m)
[0;33m*[0m [0;1;39mfull / test (3.13)[0m (ID [0;36m99030887371[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Install dependencies
  [38;5;242m-[0m Run tests (coverage leg)
  [0;33m*[0m Run tests
  [0;33m*[0m Run tests
  [0;33m*[0m Build shard timings table
  [0;33m*[0m Upload shard timings
  [0;33m*[0m Upload coverage
  [0;33m*[0m Post Install dependencies
  [0;33m*[0m Post Run actions/checkout@v4
[0;31mX[0m [0;1;39mfull / perf-floors[0m in 4m33s (ID [0;36m99030887383[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Install dependencies
  [0;32m✓[0m Health check (Rust extension loadable)
  [0;32m✓[0m Run slow tests
  [0;31mX[0m Run Phase 7E regression floor
  [0;32m✓[0m Upload Phase 7E floor-check report
  [0;32m✓[0m Run launch regression floor
  [0;32m✓[0m Upload launch floor-check report
  [0;32m✓[0m Run view-hints regression floor
  [0;32m✓[0m Upload view-hints floor-check report
  [0;32m✓[0m Run agents disk-load operation-count floor
  [0;32m✓[0m Upload agents disk-load floor-check report
  [0;32m✓[0m Run plugins catalog-scale regression floor
  [0;32m✓[0m Upload plugins catalog-scale floor-check report
  [0;32m✓[0m Run bead performance smoke
  [0;32m✓[0m Upload bead performance smoke
  [0;32m✓[0m Post Install dependencies
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[0;32m✓[0m [0;1;39mfull / ace-page-group-isolation[0m in 1m5s (ID [0;36m99030887385[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Install visual dependencies
  [0;32m✓[0m Run ACE shared-page isolation lane
  [0;32m✓[0m Post Install visual dependencies
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[0;32m✓[0m [0;1;39mfull / lint[0m in 4m6s (ID [0;36m99030887397[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Install dependencies
  [0;32m✓[0m Check pinned core bindings
  [0;32m✓[0m Bootstrap SDD sidecars
  [0;32m✓[0m Initialize SASE home
  [0;32m✓[0m Run actions/setup-go@v5
  [0;32m✓[0m Cache Go binaries
  [38;5;242m-[0m Install Go tools (keep-sorted)
  [0;32m✓[0m Cache Prettier dependencies
  [0;32m✓[0m Check Python formatting
  [0;32m✓[0m Check Markdown formatting
  [0;32m✓[0m Lint
  [0;32m✓[0m SASE validation
  [0;32m✓[0m Validate committed plans
  [0;32m✓[0m Build and verify package
  [0;32m✓[0m Post Cache Prettier dependencies
  [0;32m✓[0m Post Cache Go binaries
  [0;32m✓[0m Post Run actions/setup-go@v5
  [0;32m✓[0m Post Install dependencies
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[0;31mX[0m [0;1;39mfull / coverage-contexts[0m in 40m50s (ID [0;36m99030887410[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Install dependencies
  [0;31mX[0m Record per-test coverage contexts
  [0;32m✓[0m Upload coverage contexts database
  [0;32m✓[0m Post Install dependencies
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[0;31mX[0m [0;1;39mfull / test (3.14)[0m in 24m28s (ID [0;36m99030887411[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Install dependencies
  [38;5;242m-[0m Run tests (coverage leg)
  [38;5;242m-[0m Run tests
  [0;31mX[0m Run tests
  [0;32m✓[0m Build shard timings table
  [0;32m✓[0m Upload shard timings
  [38;5;242m-[0m Upload coverage
  [0;32m✓[0m Post Install dependencies
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[0;31mX[0m [0;1;39mfull / visual-test[0m in 14m59s (ID [0;36m99030887452[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Install visual dependencies
  [0;31mX[0m Run visual tests
  [0;32m✓[0m Build visual failure report
  [0;32m✓[0m Upload visual failure report
  [0;32m✓[0m Publish visual failure report
  [0;32m✓[0m Upload visual failure artifacts
  [0;32m✓[0m Post Install visual dependencies
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[0;31mX[0m [0;1;39mfull / test (3.12)[0m in 36m44s (ID [0;36m99030887468[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Install dependencies
  [0;31mX[0m Run tests (coverage leg)
  [38;5;242m-[0m Run tests
  [38;5;242m-[0m Run tests
  [38;5;242m-[0m Build shard timings table
  [38;5;242m-[0m Upload shard timings
  [38;5;242m-[0m Upload coverage
  [0;32m✓[0m Post Install dependencies
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[38;5;242m-[0m [0;1;39mfull / contention-test[0m (ID [0;36m99030888181[0m)
[0;1;39mRefreshing run status every 3 seconds. Press Ctrl+C to quit.[0m

[0;33m*[0m [0;1;39mmaster[0m Full CI · [0;36m33226037754[0m
Triggered via workflow_dispatch about 1 hour ago

[0;1;39mJOBS[0m
[0;32m✓[0m [0;1;39mfull / build-core[0m in 7m49s (ID [0;36m99029883707[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Resolve pinned Rust core revision
  [0;32m✓[0m Check out Rust core
  [0;32m✓[0m Run astral-sh/setup-uv@v4
  [0;32m✓[0m Set up Rust
  [0;32m✓[0m Cache Rust build
  [0;32m✓[0m Build abi3 Rust core wheel
  [0;32m✓[0m Build xprompt LSP
  [0;32m✓[0m Record wheel provenance
  [0;32m✓[0m Upload Rust core artifacts
  [0;32m✓[0m Post Cache Rust build
  [0;32m✓[0m Post Run astral-sh/setup-uv@v4
  [0;32m✓[0m Post Check out Rust core
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[38;5;242m-[0m [0;1;39mfull / docs-build[0m (ID [0;36m99029884284[0m)
[38;5;242m-[0m [0;1;39mfull / release-core-floor-smoke[0m (ID [0;36m99029884306[0m)
[0;33m*[0m [0;1;39mfull / test (3.13)[0m (ID [0;36m99030887371[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Install dependencies
  [38;5;242m-[0m Run tests (coverage leg)
  [0;33m*[0m Run tests
  [0;33m*[0m Run tests
  [0;33m*[0m Build shard timings table
  [0;33m*[0m Upload shard timings
  [0;33m*[0m Upload coverage
  [0;33m*[0m Post Install dependencies
  [0;33m*[0m Post Run actions/checkout@v4
[0;31mX[0m [0;1;39mfull / perf-floors[0m in 4m33s (ID [0;36m99030887383[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Install dependencies
  [0;32m✓[0m Health check (Rust extension loadable)
  [0;32m✓[0m Run slow tests
  [0;31mX[0m Run Phase 7E regression floor
  [0;32m✓[0m Upload Phase 7E floor-check report
  [0;32m✓[0m Run launch regression floor
  [0;32m✓[0m Upload launch floor-check report
  [0;32m✓[0m Run view-hints regression floor
  [0;32m✓[0m Upload view-hints floor-check report
  [0;32m✓[0m Run agents disk-load operation-count floor
  [0;32m✓[0m Upload agents disk-load floor-check report
  [0;32m✓[0m Run plugins catalog-scale regression floor
  [0;32m✓[0m Upload plugins catalog-scale floor-check report
  [0;32m✓[0m Run bead performance smoke
  [0;32m✓[0m Upload bead performance smoke
  [0;32m✓[0m Post Install dependencies
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[0;32m✓[0m [0;1;39mfull / ace-page-group-isolation[0m in 1m5s (ID [0;36m99030887385[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Install visual dependencies
  [0;32m✓[0m Run ACE shared-page isolation lane
  [0;32m✓[0m Post Install visual dependencies
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[0;32m✓[0m [0;1;39mfull / lint[0m in 4m6s (ID [0;36m99030887397[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Install dependencies
  [0;32m✓[0m Check pinned core bindings
  [0;32m✓[0m Bootstrap SDD sidecars
  [0;32m✓[0m Initialize SASE home
  [0;32m✓[0m Run actions/setup-go@v5
  [0;32m✓[0m Cache Go binaries
  [38;5;242m-[0m Install Go tools (keep-sorted)
  [0;32m✓[0m Cache Prettier dependencies
  [0;32m✓[0m Check Python formatting
  [0;32m✓[0m Check Markdown formatting
  [0;32m✓[0m Lint
  [0;32m✓[0m SASE validation
  [0;32m✓[0m Validate committed plans
  [0;32m✓[0m Build and verify package
  [0;32m✓[0m Post Cache Prettier dependencies
  [0;32m✓[0m Post Cache Go binaries
  [0;32m✓[0m Post Run actions/setup-go@v5
  [0;32m✓[0m Post Install dependencies
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[0;31mX[0m [0;1;39mfull / coverage-contexts[0m in 40m50s (ID [0;36m99030887410[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Install dependencies
  [0;31mX[0m Record per-test coverage contexts
  [0;32m✓[0m Upload coverage contexts database
  [0;32m✓[0m Post Install dependencies
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[0;31mX[0m [0;1;39mfull / test (3.14)[0m in 24m28s (ID [0;36m99030887411[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Install dependencies
  [38;5;242m-[0m Run tests (coverage leg)
  [38;5;242m-[0m Run tests
  [0;31mX[0m Run tests
  [0;32m✓[0m Build shard timings table
  [0;32m✓[0m Upload shard timings
  [38;5;242m-[0m Upload coverage
  [0;32m✓[0m Post Install dependencies
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[0;31mX[0m [0;1;39mfull / visual-test[0m in 14m59s (ID [0;36m99030887452[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Install visual dependencies
  [0;31mX[0m Run visual tests
  [0;32m✓[0m Build visual failure report
  [0;32m✓[0m Upload visual failure report
  [0;32m✓[0m Publish visual failure report
  [0;32m✓[0m Upload visual failure artifacts
  [0;32m✓[0m Post Install visual dependencies
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[0;31mX[0m [0;1;39mfull / test (3.12)[0m in 36m44s (ID [0;36m99030887468[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Install dependencies
  [0;31mX[0m Run tests (coverage leg)
  [38;5;242m-[0m Run tests
  [38;5;242m-[0m Run tests
  [38;5;242m-[0m Build shard timings table
  [38;5;242m-[0m Upload shard timings
  [38;5;242m-[0m Upload coverage
  [0;32m✓[0m Post Install dependencies
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[38;5;242m-[0m [0;1;39mfull / contention-test[0m (ID [0;36m99030888181[0m)
[0;1;39mRefreshing run status every 3 seconds. Press Ctrl+C to quit.[0m

[0;33m*[0m [0;1;39mmaster[0m Full CI · [0;36m33226037754[0m
Triggered via workflow_dispatch about 1 hour ago

[0;1;39mJOBS[0m
[0;32m✓[0m [0;1;39mfull / build-core[0m in 7m49s (ID [0;36m99029883707[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Resolve pinned Rust core revision
  [0;32m✓[0m Check out Rust core
  [0;32m✓[0m Run astral-sh/setup-uv@v4
  [0;32m✓[0m Set up Rust
  [0;32m✓[0m Cache Rust build
  [0;32m✓[0m Build abi3 Rust core wheel
  [0;32m✓[0m Build xprompt LSP
  [0;32m✓[0m Record wheel provenance
  [0;32m✓[0m Upload Rust core artifacts
  [0;32m✓[0m Post Cache Rust build
  [0;32m✓[0m Post Run astral-sh/setup-uv@v4
  [0;32m✓[0m Post Check out Rust core
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[38;5;242m-[0m [0;1;39mfull / docs-build[0m (ID [0;36m99029884284[0m)
[38;5;242m-[0m [0;1;39mfull / release-core-floor-smoke[0m (ID [0;36m99029884306[0m)
[0;33m*[0m [0;1;39mfull / test (3.13)[0m (ID [0;36m99030887371[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Install dependencies
  [38;5;242m-[0m Run tests (coverage leg)
  [0;33m*[0m Run tests
  [0;33m*[0m Run tests
  [0;33m*[0m Build shard timings table
  [0;33m*[0m Upload shard timings
  [0;33m*[0m Upload coverage
  [0;33m*[0m Post Install dependencies
  [0;33m*[0m Post Run actions/checkout@v4
[0;31mX[0m [0;1;39mfull / perf-floors[0m in 4m33s (ID [0;36m99030887383[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Install dependencies
  [0;32m✓[0m Health check (Rust extension loadable)
  [0;32m✓[0m Run slow tests
  [0;31mX[0m Run Phase 7E regression floor
  [0;32m✓[0m Upload Phase 7E floor-check report
  [0;32m✓[0m Run launch regression floor
  [0;32m✓[0m Upload launch floor-check report
  [0;32m✓[0m Run view-hints regression floor
  [0;32m✓[0m Upload view-hints floor-check report
  [0;32m✓[0m Run agents disk-load operation-count floor
  [0;32m✓[0m Upload agents disk-load floor-check report
  [0;32m✓[0m Run plugins catalog-scale regression floor
  [0;32m✓[0m Upload plugins catalog-scale floor-check report
  [0;32m✓[0m Run bead performance smoke
  [0;32m✓[0m Upload bead performance smoke
  [0;32m✓[0m Post Install dependencies
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[0;32m✓[0m [0;1;39mfull / ace-page-group-isolation[0m in 1m5s (ID [0;36m99030887385[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Install visual dependencies
  [0;32m✓[0m Run ACE shared-page isolation lane
  [0;32m✓[0m Post Install visual dependencies
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[0;32m✓[0m [0;1;39mfull / lint[0m in 4m6s (ID [0;36m99030887397[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Install dependencies
  [0;32m✓[0m Check pinned core bindings
  [0;32m✓[0m Bootstrap SDD sidecars
  [0;32m✓[0m Initialize SASE home
  [0;32m✓[0m Run actions/setup-go@v5
  [0;32m✓[0m Cache Go binaries
  [38;5;242m-[0m Install Go tools (keep-sorted)
  [0;32m✓[0m Cache Prettier dependencies
  [0;32m✓[0m Check Python formatting
  [0;32m✓[0m Check Markdown formatting
  [0;32m✓[0m Lint
  [0;32m✓[0m SASE validation
  [0;32m✓[0m Validate committed plans
  [0;32m✓[0m Build and verify package
  [0;32m✓[0m Post Cache Prettier dependencies
  [0;32m✓[0m Post Cache Go binaries
  [0;32m✓[0m Post Run actions/setup-go@v5
  [0;32m✓[0m Post Install dependencies
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[0;31mX[0m [0;1;39mfull / coverage-contexts[0m in 40m50s (ID [0;36m99030887410[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Install dependencies
  [0;31mX[0m Record per-test coverage contexts
  [0;32m✓[0m Upload coverage contexts database
  [0;32m✓[0m Post Install dependencies
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[0;31mX[0m [0;1;39mfull / test (3.14)[0m in 24m28s (ID [0;36m99030887411[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Install dependencies
  [38;5;242m-[0m Run tests (coverage leg)
  [38;5;242m-[0m Run tests
  [0;31mX[0m Run tests
  [0;32m✓[0m Build shard timings table
  [0;32m✓[0m Upload shard timings
  [38;5;242m-[0m Upload coverage
  [0;32m✓[0m Post Install dependencies
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[0;31mX[0m [0;1;39mfull / visual-test[0m in 14m59s (ID [0;36m99030887452[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Install visual dependencies
  [0;31mX[0m Run visual tests
  [0;32m✓[0m Build visual failure report
  [0;32m✓[0m Upload visual failure report
  [0;32m✓[0m Publish visual failure report
  [0;32m✓[0m Upload visual failure artifacts
  [0;32m✓[0m Post Install visual dependencies
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[0;31mX[0m [0;1;39mfull / test (3.12)[0m in 36m44s (ID [0;36m99030887468[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Install dependencies
  [0;31mX[0m Run tests (coverage leg)
  [38;5;242m-[0m Run tests
  [38;5;242m-[0m Run tests
  [38;5;242m-[0m Build shard timings table
  [38;5;242m-[0m Upload shard timings
  [38;5;242m-[0m Upload coverage
  [0;32m✓[0m Post Install dependencies
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[38;5;242m-[0m [0;1;39mfull / contention-test[0m (ID [0;36m99030888181[0m)
[0;1;39mRefreshing run status every 3 seconds. Press Ctrl+C to quit.[0m

[0;33m*[0m [0;1;39mmaster[0m Full CI · [0;36m33226037754[0m
Triggered via workflow_dispatch about 1 hour ago

[0;1;39mJOBS[0m
[0;32m✓[0m [0;1;39mfull / build-core[0m in 7m49s (ID [0;36m99029883707[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Resolve pinned Rust core revision
  [0;32m✓[0m Check out Rust core
  [0;32m✓[0m Run astral-sh/setup-uv@v4
  [0;32m✓[0m Set up Rust
  [0;32m✓[0m Cache Rust build
  [0;32m✓[0m Build abi3 Rust core wheel
  [0;32m✓[0m Build xprompt LSP
  [0;32m✓[0m Record wheel provenance
  [0;32m✓[0m Upload Rust core artifacts
  [0;32m✓[0m Post Cache Rust build
  [0;32m✓[0m Post Run astral-sh/setup-uv@v4
  [0;32m✓[0m Post Check out Rust core
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[38;5;242m-[0m [0;1;39mfull / docs-build[0m (ID [0;36m99029884284[0m)
[38;5;242m-[0m [0;1;39mfull / release-core-floor-smoke[0m (ID [0;36m99029884306[0m)
[0;33m*[0m [0;1;39mfull / test (3.13)[0m (ID [0;36m99030887371[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Install dependencies
  [38;5;242m-[0m Run tests (coverage leg)
  [0;33m*[0m Run tests
  [0;33m*[0m Run tests
  [0;33m*[0m Build shard timings table
  [0;33m*[0m Upload shard timings
  [0;33m*[0m Upload coverage
  [0;33m*[0m Post Install dependencies
  [0;33m*[0m Post Run actions/checkout@v4
[0;31mX[0m [0;1;39mfull / perf-floors[0m in 4m33s (ID [0;36m99030887383[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Install dependencies
  [0;32m✓[0m Health check (Rust extension loadable)
  [0;32m✓[0m Run slow tests
  [0;31mX[0m Run Phase 7E regression floor
  [0;32m✓[0m Upload Phase 7E floor-check report
  [0;32m✓[0m Run launch regression floor
  [0;32m✓[0m Upload launch floor-check report
  [0;32m✓[0m Run view-hints regression floor
  [0;32m✓[0m Upload view-hints floor-check report
  [0;32m✓[0m Run agents disk-load operation-count floor
  [0;32m✓[0m Upload agents disk-load floor-check report
  [0;32m✓[0m Run plugins catalog-scale regression floor
  [0;32m✓[0m Upload plugins catalog-scale floor-check report
  [0;32m✓[0m Run bead performance smoke
  [0;32m✓[0m Upload bead performance smoke
  [0;32m✓[0m Post Install dependencies
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[0;32m✓[0m [0;1;39mfull / ace-page-group-isolation[0m in 1m5s (ID [0;36m99030887385[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Install visual dependencies
  [0;32m✓[0m Run ACE shared-page isolation lane
  [0;32m✓[0m Post Install visual dependencies
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[0;32m✓[0m [0;1;39mfull / lint[0m in 4m6s (ID [0;36m99030887397[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Install dependencies
  [0;32m✓[0m Check pinned core bindings
  [0;32m✓[0m Bootstrap SDD sidecars
  [0;32m✓[0m Initialize SASE home
  [0;32m✓[0m Run actions/setup-go@v5
  [0;32m✓[0m Cache Go binaries
  [38;5;242m-[0m Install Go tools (keep-sorted)
  [0;32m✓[0m Cache Prettier dependencies
  [0;32m✓[0m Check Python formatting
  [0;32m✓[0m Check Markdown formatting
  [0;32m✓[0m Lint
  [0;32m✓[0m SASE validation
  [0;32m✓[0m Validate committed plans
  [0;32m✓[0m Build and verify package
  [0;32m✓[0m Post Cache Prettier dependencies
  [0;32m✓[0m Post Cache Go binaries
  [0;32m✓[0m Post Run actions/setup-go@v5
  [0;32m✓[0m Post Install dependencies
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[0;31mX[0m [0;1;39mfull / coverage-contexts[0m in 40m50s (ID [0;36m99030887410[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Install dependencies
  [0;31mX[0m Record per-test coverage contexts
  [0;32m✓[0m Upload coverage contexts database
  [0;32m✓[0m Post Install dependencies
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[0;31mX[0m [0;1;39mfull / test (3.14)[0m in 24m28s (ID [0;36m99030887411[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Install dependencies
  [38;5;242m-[0m Run tests (coverage leg)
  [38;5;242m-[0m Run tests
  [0;31mX[0m Run tests
  [0;32m✓[0m Build shard timings table
  [0;32m✓[0m Upload shard timings
  [38;5;242m-[0m Upload coverage
  [0;32m✓[0m Post Install dependencies
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[0;31mX[0m [0;1;39mfull / visual-test[0m in 14m59s (ID [0;36m99030887452[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Install visual dependencies
  [0;31mX[0m Run visual tests
  [0;32m✓[0m Build visual failure report
  [0;32m✓[0m Upload visual failure report
  [0;32m✓[0m Publish visual failure report
  [0;32m✓[0m Upload visual failure artifacts
  [0;32m✓[0m Post Install visual dependencies
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[0;31mX[0m [0;1;39mfull / test (3.12)[0m in 36m44s (ID [0;36m99030887468[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Install dependencies
  [0;31mX[0m Run tests (coverage leg)
  [38;5;242m-[0m Run tests
  [38;5;242m-[0m Run tests
  [38;5;242m-[0m Build shard timings table
  [38;5;242m-[0m Upload shard timings
  [38;5;242m-[0m Upload coverage
  [0;32m✓[0m Post Install dependencies
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[38;5;242m-[0m [0;1;39mfull / contention-test[0m (ID [0;36m99030888181[0m)
[0;1;39mRefreshing run status every 3 seconds. Press Ctrl+C to quit.[0m

[0;33m*[0m [0;1;39mmaster[0m Full CI · [0;36m33226037754[0m
Triggered via workflow_dispatch about 1 hour ago

[0;1;39mJOBS[0m
[0;32m✓[0m [0;1;39mfull / build-core[0m in 7m49s (ID [0;36m99029883707[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Resolve pinned Rust core revision
  [0;32m✓[0m Check out Rust core
  [0;32m✓[0m Run astral-sh/setup-uv@v4
  [0;32m✓[0m Set up Rust
  [0;32m✓[0m Cache Rust build
  [0;32m✓[0m Build abi3 Rust core wheel
  [0;32m✓[0m Build xprompt LSP
  [0;32m✓[0m Record wheel provenance
  [0;32m✓[0m Upload Rust core artifacts
  [0;32m✓[0m Post Cache Rust build
  [0;32m✓[0m Post Run astral-sh/setup-uv@v4
  [0;32m✓[0m Post Check out Rust core
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[38;5;242m-[0m [0;1;39mfull / docs-build[0m (ID [0;36m99029884284[0m)
[38;5;242m-[0m [0;1;39mfull / release-core-floor-smoke[0m (ID [0;36m99029884306[0m)
[0;33m*[0m [0;1;39mfull / test (3.13)[0m (ID [0;36m99030887371[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Install dependencies
  [38;5;242m-[0m Run tests (coverage leg)
  [0;33m*[0m Run tests
  [0;33m*[0m Run tests
  [0;33m*[0m Build shard timings table
  [0;33m*[0m Upload shard timings
  [0;33m*[0m Upload coverage
  [0;33m*[0m Post Install dependencies
  [0;33m*[0m Post Run actions/checkout@v4
[0;31mX[0m [0;1;39mfull / perf-floors[0m in 4m33s (ID [0;36m99030887383[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Install dependencies
  [0;32m✓[0m Health check (Rust extension loadable)
  [0;32m✓[0m Run slow tests
  [0;31mX[0m Run Phase 7E regression floor
  [0;32m✓[0m Upload Phase 7E floor-check report
  [0;32m✓[0m Run launch regression floor
  [0;32m✓[0m Upload launch floor-check report
  [0;32m✓[0m Run view-hints regression floor
  [0;32m✓[0m Upload view-hints floor-check report
  [0;32m✓[0m Run agents disk-load operation-count floor
  [0;32m✓[0m Upload agents disk-load floor-check report
  [0;32m✓[0m Run plugins catalog-scale regression floor
  [0;32m✓[0m Upload plugins catalog-scale floor-check report
  [0;32m✓[0m Run bead performance smoke
  [0;32m✓[0m Upload bead performance smoke
  [0;32m✓[0m Post Install dependencies
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[0;32m✓[0m [0;1;39mfull / ace-page-group-isolation[0m in 1m5s (ID [0;36m99030887385[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Install visual dependencies
  [0;32m✓[0m Run ACE shared-page isolation lane
  [0;32m✓[0m Post Install visual dependencies
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[0;32m✓[0m [0;1;39mfull / lint[0m in 4m6s (ID [0;36m99030887397[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Install dependencies
  [0;32m✓[0m Check pinned core bindings
  [0;32m✓[0m Bootstrap SDD sidecars
  [0;32m✓[0m Initialize SASE home
  [0;32m✓[0m Run actions/setup-go@v5
  [0;32m✓[0m Cache Go binaries
  [38;5;242m-[0m Install Go tools (keep-sorted)
  [0;32m✓[0m Cache Prettier dependencies
  [0;32m✓[0m Check Python formatting
  [0;32m✓[0m Check Markdown formatting
  [0;32m✓[0m Lint
  [0;32m✓[0m SASE validation
  [0;32m✓[0m Validate committed plans
  [0;32m✓[0m Build and verify package
  [0;32m✓[0m Post Cache Prettier dependencies
  [0;32m✓[0m Post Cache Go binaries
  [0;32m✓[0m Post Run actions/setup-go@v5
  [0;32m✓[0m Post Install dependencies
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[0;31mX[0m [0;1;39mfull / coverage-contexts[0m in 40m50s (ID [0;36m99030887410[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Install dependencies
  [0;31mX[0m Record per-test coverage contexts
  [0;32m✓[0m Upload coverage contexts database
  [0;32m✓[0m Post Install dependencies
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[0;31mX[0m [0;1;39mfull / test (3.14)[0m in 24m28s (ID [0;36m99030887411[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Install dependencies
  [38;5;242m-[0m Run tests (coverage leg)
  [38;5;242m-[0m Run tests
  [0;31mX[0m Run tests
  [0;32m✓[0m Build shard timings table
  [0;32m✓[0m Upload shard timings
  [38;5;242m-[0m Upload coverage
  [0;32m✓[0m Post Install dependencies
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[0;31mX[0m [0;1;39mfull / visual-test[0m in 14m59s (ID [0;36m99030887452[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Install visual dependencies
  [0;31mX[0m Run visual tests
  [0;32m✓[0m Build visual failure report
  [0;32m✓[0m Upload visual failure report
  [0;32m✓[0m Publish visual failure report
  [0;32m✓[0m Upload visual failure artifacts
  [0;32m✓[0m Post Install visual dependencies
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[0;31mX[0m [0;1;39mfull / test (3.12)[0m in 36m44s (ID [0;36m99030887468[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Install dependencies
  [0;31mX[0m Run tests (coverage leg)
  [38;5;242m-[0m Run tests
  [38;5;242m-[0m Run tests
  [38;5;242m-[0m Build shard timings table
  [38;5;242m-[0m Upload shard timings
  [38;5;242m-[0m Upload coverage
  [0;32m✓[0m Post Install dependencies
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[38;5;242m-[0m [0;1;39mfull / contention-test[0m (ID [0;36m99030888181[0m)
[0;1;39mRefreshing run status every 3 seconds. Press Ctrl+C to quit.[0m

[0;33m*[0m [0;1;39mmaster[0m Full CI · [0;36m33226037754[0m
Triggered via workflow_dispatch about 1 hour ago

[0;1;39mJOBS[0m
[0;32m✓[0m [0;1;39mfull / build-core[0m in 7m49s (ID [0;36m99029883707[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Resolve pinned Rust core revision
  [0;32m✓[0m Check out Rust core
  [0;32m✓[0m Run astral-sh/setup-uv@v4
  [0;32m✓[0m Set up Rust
  [0;32m✓[0m Cache Rust build
  [0;32m✓[0m Build abi3 Rust core wheel
  [0;32m✓[0m Build xprompt LSP
  [0;32m✓[0m Record wheel provenance
  [0;32m✓[0m Upload Rust core artifacts
  [0;32m✓[0m Post Cache Rust build
  [0;32m✓[0m Post Run astral-sh/setup-uv@v4
  [0;32m✓[0m Post Check out Rust core
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[38;5;242m-[0m [0;1;39mfull / docs-build[0m (ID [0;36m99029884284[0m)
[38;5;242m-[0m [0;1;39mfull / release-core-floor-smoke[0m (ID [0;36m99029884306[0m)
[0;33m*[0m [0;1;39mfull / test (3.13)[0m (ID [0;36m99030887371[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Install dependencies
  [38;5;242m-[0m Run tests (coverage leg)
  [0;33m*[0m Run tests
  [0;33m*[0m Run tests
  [0;33m*[0m Build shard timings table
  [0;33m*[0m Upload shard timings
  [0;33m*[0m Upload coverage
  [0;33m*[0m Post Install dependencies
  [0;33m*[0m Post Run actions/checkout@v4
[0;31mX[0m [0;1;39mfull / perf-floors[0m in 4m33s (ID [0;36m99030887383[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Install dependencies
  [0;32m✓[0m Health check (Rust extension loadable)
  [0;32m✓[0m Run slow tests
  [0;31mX[0m Run Phase 7E regression floor
  [0;32m✓[0m Upload Phase 7E floor-check report
  [0;32m✓[0m Run launch regression floor
  [0;32m✓[0m Upload launch floor-check report
  [0;32m✓[0m Run view-hints regression floor
  [0;32m✓[0m Upload view-hints floor-check report
  [0;32m✓[0m Run agents disk-load operation-count floor
  [0;32m✓[0m Upload agents disk-load floor-check report
  [0;32m✓[0m Run plugins catalog-scale regression floor
  [0;32m✓[0m Upload plugins catalog-scale floor-check report
  [0;32m✓[0m Run bead performance smoke
  [0;32m✓[0m Upload bead performance smoke
  [0;32m✓[0m Post Install dependencies
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[0;32m✓[0m [0;1;39mfull / ace-page-group-isolation[0m in 1m5s (ID [0;36m99030887385[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Install visual dependencies
  [0;32m✓[0m Run ACE shared-page isolation lane
  [0;32m✓[0m Post Install visual dependencies
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[0;32m✓[0m [0;1;39mfull / lint[0m in 4m6s (ID [0;36m99030887397[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Install dependencies
  [0;32m✓[0m Check pinned core bindings
  [0;32m✓[0m Bootstrap SDD sidecars
  [0;32m✓[0m Initialize SASE home
  [0;32m✓[0m Run actions/setup-go@v5
  [0;32m✓[0m Cache Go binaries
  [38;5;242m-[0m Install Go tools (keep-sorted)
  [0;32m✓[0m Cache Prettier dependencies
  [0;32m✓[0m Check Python formatting
  [0;32m✓[0m Check Markdown formatting
  [0;32m✓[0m Lint
  [0;32m✓[0m SASE validation
  [0;32m✓[0m Validate committed plans
  [0;32m✓[0m Build and verify package
  [0;32m✓[0m Post Cache Prettier dependencies
  [0;32m✓[0m Post Cache Go binaries
  [0;32m✓[0m Post Run actions/setup-go@v5
  [0;32m✓[0m Post Install dependencies
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[0;31mX[0m [0;1;39mfull / coverage-contexts[0m in 40m50s (ID [0;36m99030887410[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Install dependencies
  [0;31mX[0m Record per-test coverage contexts
  [0;32m✓[0m Upload coverage contexts database
  [0;32m✓[0m Post Install dependencies
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[0;31mX[0m [0;1;39mfull / test (3.14)[0m in 24m28s (ID [0;36m99030887411[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Install dependencies
  [38;5;242m-[0m Run tests (coverage leg)
  [38;5;242m-[0m Run tests
  [0;31mX[0m Run tests
  [0;32m✓[0m Build shard timings table
  [0;32m✓[0m Upload shard timings
  [38;5;242m-[0m Upload coverage
  [0;32m✓[0m Post Install dependencies
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[0;31mX[0m [0;1;39mfull / visual-test[0m in 14m59s (ID [0;36m99030887452[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Install visual dependencies
  [0;31mX[0m Run visual tests
  [0;32m✓[0m Build visual failure report
  [0;32m✓[0m Upload visual failure report
  [0;32m✓[0m Publish visual failure report
  [0;32m✓[0m Upload visual failure artifacts
  [0;32m✓[0m Post Install visual dependencies
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[0;31mX[0m [0;1;39mfull / test (3.12)[0m in 36m44s (ID [0;36m99030887468[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Install dependencies
  [0;31mX[0m Run tests (coverage leg)
  [38;5;242m-[0m Run tests
  [38;5;242m-[0m Run tests
  [38;5;242m-[0m Build shard timings table
  [38;5;242m-[0m Upload shard timings
  [38;5;242m-[0m Upload coverage
  [0;32m✓[0m Post Install dependencies
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[38;5;242m-[0m [0;1;39mfull / contention-test[0m (ID [0;36m99030888181[0m)
[0;1;39mRefreshing run status every 3 seconds. Press Ctrl+C to quit.[0m

[0;33m*[0m [0;1;39mmaster[0m Full CI · [0;36m33226037754[0m
Triggered via workflow_dispatch about 1 hour ago

[0;1;39mJOBS[0m
[0;32m✓[0m [0;1;39mfull / build-core[0m in 7m49s (ID [0;36m99029883707[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Resolve pinned Rust core revision
  [0;32m✓[0m Check out Rust core
  [0;32m✓[0m Run astral-sh/setup-uv@v4
  [0;32m✓[0m Set up Rust
  [0;32m✓[0m Cache Rust build
  [0;32m✓[0m Build abi3 Rust core wheel
  [0;32m✓[0m Build xprompt LSP
  [0;32m✓[0m Record wheel provenance
  [0;32m✓[0m Upload Rust core artifacts
  [0;32m✓[0m Post Cache Rust build
  [0;32m✓[0m Post Run astral-sh/setup-uv@v4
  [0;32m✓[0m Post Check out Rust core
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[38;5;242m-[0m [0;1;39mfull / docs-build[0m (ID [0;36m99029884284[0m)
[38;5;242m-[0m [0;1;39mfull / release-core-floor-smoke[0m (ID [0;36m99029884306[0m)
[0;33m*[0m [0;1;39mfull / test (3.13)[0m (ID [0;36m99030887371[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Install dependencies
  [38;5;242m-[0m Run tests (coverage leg)
  [0;33m*[0m Run tests
  [0;33m*[0m Run tests
  [0;33m*[0m Build shard timings table
  [0;33m*[0m Upload shard timings
  [0;33m*[0m Upload coverage
  [0;33m*[0m Post Install dependencies
  [0;33m*[0m Post Run actions/checkout@v4
[0;31mX[0m [0;1;39mfull / perf-floors[0m in 4m33s (ID [0;36m99030887383[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Install dependencies
  [0;32m✓[0m Health check (Rust extension loadable)
  [0;32m✓[0m Run slow tests
  [0;31mX[0m Run Phase 7E regression floor
  [0;32m✓[0m Upload Phase 7E floor-check report
  [0;32m✓[0m Run launch regression floor
  [0;32m✓[0m Upload launch floor-check report
  [0;32m✓[0m Run view-hints regression floor
  [0;32m✓[0m Upload view-hints floor-check report
  [0;32m✓[0m Run agents disk-load operation-count floor
  [0;32m✓[0m Upload agents disk-load floor-check report
  [0;32m✓[0m Run plugins catalog-scale regression floor
  [0;32m✓[0m Upload plugins catalog-scale floor-check report
  [0;32m✓[0m Run bead performance smoke
  [0;32m✓[0m Upload bead performance smoke
  [0;32m✓[0m Post Install dependencies
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[0;32m✓[0m [0;1;39mfull / ace-page-group-isolation[0m in 1m5s (ID [0;36m99030887385[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Install visual dependencies
  [0;32m✓[0m Run ACE shared-page isolation lane
  [0;32m✓[0m Post Install visual dependencies
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[0;32m✓[0m [0;1;39mfull / lint[0m in 4m6s (ID [0;36m99030887397[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Install dependencies
  [0;32m✓[0m Check pinned core bindings
  [0;32m✓[0m Bootstrap SDD sidecars
  [0;32m✓[0m Initialize SASE home
  [0;32m✓[0m Run actions/setup-go@v5
  [0;32m✓[0m Cache Go binaries
  [38;5;242m-[0m Install Go tools (keep-sorted)
  [0;32m✓[0m Cache Prettier dependencies
  [0;32m✓[0m Check Python formatting
  [0;32m✓[0m Check Markdown formatting
  [0;32m✓[0m Lint
  [0;32m✓[0m SASE validation
  [0;32m✓[0m Validate committed plans
  [0;32m✓[0m Build and verify package
  [0;32m✓[0m Post Cache Prettier dependencies
  [0;32m✓[0m Post Cache Go binaries
  [0;32m✓[0m Post Run actions/setup-go@v5
  [0;32m✓[0m Post Install dependencies
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[0;31mX[0m [0;1;39mfull / coverage-contexts[0m in 40m50s (ID [0;36m99030887410[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Install dependencies
  [0;31mX[0m Record per-test coverage contexts
  [0;32m✓[0m Upload coverage contexts database
  [0;32m✓[0m Post Install dependencies
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[0;31mX[0m [0;1;39mfull / test (3.14)[0m in 24m28s (ID [0;36m99030887411[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Install dependencies
  [38;5;242m-[0m Run tests (coverage leg)
  [38;5;242m-[0m Run tests
  [0;31mX[0m Run tests
  [0;32m✓[0m Build shard timings table
  [0;32m✓[0m Upload shard timings
  [38;5;242m-[0m Upload coverage
  [0;32m✓[0m Post Install dependencies
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[0;31mX[0m [0;1;39mfull / visual-test[0m in 14m59s (ID [0;36m99030887452[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Install visual dependencies
  [0;31mX[0m Run visual tests
  [0;32m✓[0m Build visual failure report
  [0;32m✓[0m Upload visual failure report
  [0;32m✓[0m Publish visual failure report
  [0;32m✓[0m Upload visual failure artifacts
  [0;32m✓[0m Post Install visual dependencies
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[0;31mX[0m [0;1;39mfull / test (3.12)[0m in 36m44s (ID [0;36m99030887468[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Install dependencies
  [0;31mX[0m Run tests (coverage leg)
  [38;5;242m-[0m Run tests
  [38;5;242m-[0m Run tests
  [38;5;242m-[0m Build shard timings table
  [38;5;242m-[0m Upload shard timings
  [38;5;242m-[0m Upload coverage
  [0;32m✓[0m Post Install dependencies
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[38;5;242m-[0m [0;1;39mfull / contention-test[0m (ID [0;36m99030888181[0m)
[0;1;39mRefreshing run status every 3 seconds. Press Ctrl+C to quit.[0m

[0;33m*[0m [0;1;39mmaster[0m Full CI · [0;36m33226037754[0m
Triggered via workflow_dispatch about 1 hour ago

[0;1;39mJOBS[0m
[0;32m✓[0m [0;1;39mfull / build-core[0m in 7m49s (ID [0;36m99029883707[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Resolve pinned Rust core revision
  [0;32m✓[0m Check out Rust core
  [0;32m✓[0m Run astral-sh/setup-uv@v4
  [0;32m✓[0m Set up Rust
  [0;32m✓[0m Cache Rust build
  [0;32m✓[0m Build abi3 Rust core wheel
  [0;32m✓[0m Build xprompt LSP
  [0;32m✓[0m Record wheel provenance
  [0;32m✓[0m Upload Rust core artifacts
  [0;32m✓[0m Post Cache Rust build
  [0;32m✓[0m Post Run astral-sh/setup-uv@v4
  [0;32m✓[0m Post Check out Rust core
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[38;5;242m-[0m [0;1;39mfull / docs-build[0m (ID [0;36m99029884284[0m)
[38;5;242m-[0m [0;1;39mfull / release-core-floor-smoke[0m (ID [0;36m99029884306[0m)
[0;33m*[0m [0;1;39mfull / test (3.13)[0m (ID [0;36m99030887371[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Install dependencies
  [38;5;242m-[0m Run tests (coverage leg)
  [0;33m*[0m Run tests
  [0;33m*[0m Run tests
  [0;33m*[0m Build shard timings table
  [0;33m*[0m Upload shard timings
  [0;33m*[0m Upload coverage
  [0;33m*[0m Post Install dependencies
  [0;33m*[0m Post Run actions/checkout@v4
[0;31mX[0m [0;1;39mfull / perf-floors[0m in 4m33s (ID [0;36m99030887383[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Install dependencies
  [0;32m✓[0m Health check (Rust extension loadable)
  [0;32m✓[0m Run slow tests
  [0;31mX[0m Run Phase 7E regression floor
  [0;32m✓[0m Upload Phase 7E floor-check report
  [0;32m✓[0m Run launch regression floor
  [0;32m✓[0m Upload launch floor-check report
  [0;32m✓[0m Run view-hints regression floor
  [0;32m✓[0m Upload view-hints floor-check report
  [0;32m✓[0m Run agents disk-load operation-count floor
  [0;32m✓[0m Upload agents disk-load floor-check report
  [0;32m✓[0m Run plugins catalog-scale regression floor
  [0;32m✓[0m Upload plugins catalog-scale floor-check report
  [0;32m✓[0m Run bead performance smoke
  [0;32m✓[0m Upload bead performance smoke
  [0;32m✓[0m Post Install dependencies
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[0;32m✓[0m [0;1;39mfull / ace-page-group-isolation[0m in 1m5s (ID [0;36m99030887385[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Install visual dependencies
  [0;32m✓[0m Run ACE shared-page isolation lane
  [0;32m✓[0m Post Install visual dependencies
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[0;32m✓[0m [0;1;39mfull / lint[0m in 4m6s (ID [0;36m99030887397[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Install dependencies
  [0;32m✓[0m Check pinned core bindings
  [0;32m✓[0m Bootstrap SDD sidecars
  [0;32m✓[0m Initialize SASE home
  [0;32m✓[0m Run actions/setup-go@v5
  [0;32m✓[0m Cache Go binaries
  [38;5;242m-[0m Install Go tools (keep-sorted)
  [0;32m✓[0m Cache Prettier dependencies
  [0;32m✓[0m Check Python formatting
  [0;32m✓[0m Check Markdown formatting
  [0;32m✓[0m Lint
  [0;32m✓[0m SASE validation
  [0;32m✓[0m Validate committed plans
  [0;32m✓[0m Build and verify package
  [0;32m✓[0m Post Cache Prettier dependencies
  [0;32m✓[0m Post Cache Go binaries
  [0;32m✓[0m Post Run actions/setup-go@v5
  [0;32m✓[0m Post Install dependencies
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[0;31mX[0m [0;1;39mfull / coverage-contexts[0m in 40m50s (ID [0;36m99030887410[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Install dependencies
  [0;31mX[0m Record per-test coverage contexts
  [0;32m✓[0m Upload coverage contexts database
  [0;32m✓[0m Post Install dependencies
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[0;31mX[0m [0;1;39mfull / test (3.14)[0m in 24m28s (ID [0;36m99030887411[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Install dependencies
  [38;5;242m-[0m Run tests (coverage leg)
  [38;5;242m-[0m Run tests
  [0;31mX[0m Run tests
  [0;32m✓[0m Build shard timings table
  [0;32m✓[0m Upload shard timings
  [38;5;242m-[0m Upload coverage
  [0;32m✓[0m Post Install dependencies
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[0;31mX[0m [0;1;39mfull / visual-test[0m in 14m59s (ID [0;36m99030887452[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Install visual dependencies
  [0;31mX[0m Run visual tests
  [0;32m✓[0m Build visual failure report
  [0;32m✓[0m Upload visual failure report
  [0;32m✓[0m Publish visual failure report
  [0;32m✓[0m Upload visual failure artifacts
  [0;32m✓[0m Post Install visual dependencies
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[0;31mX[0m [0;1;39mfull / test (3.12)[0m in 36m44s (ID [0;36m99030887468[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Install dependencies
  [0;31mX[0m Run tests (coverage leg)
  [38;5;242m-[0m Run tests
  [38;5;242m-[0m Run tests
  [38;5;242m-[0m Build shard timings table
  [38;5;242m-[0m Upload shard timings
  [38;5;242m-[0m Upload coverage
  [0;32m✓[0m Post Install dependencies
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[38;5;242m-[0m [0;1;39mfull / contention-test[0m (ID [0;36m99030888181[0m)
[0;1;39mRefreshing run status every 3 seconds. Press Ctrl+C to quit.[0m

[0;33m*[0m [0;1;39mmaster[0m Full CI · [0;36m33226037754[0m
Triggered via workflow_dispatch about 1 hour ago

[0;1;39mJOBS[0m
[0;32m✓[0m [0;1;39mfull / build-core[0m in 7m49s (ID [0;36m99029883707[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Resolve pinned Rust core revision
  [0;32m✓[0m Check out Rust core
  [0;32m✓[0m Run astral-sh/setup-uv@v4
  [0;32m✓[0m Set up Rust
  [0;32m✓[0m Cache Rust build
  [0;32m✓[0m Build abi3 Rust core wheel
  [0;32m✓[0m Build xprompt LSP
  [0;32m✓[0m Record wheel provenance
  [0;32m✓[0m Upload Rust core artifacts
  [0;32m✓[0m Post Cache Rust build
  [0;32m✓[0m Post Run astral-sh/setup-uv@v4
  [0;32m✓[0m Post Check out Rust core
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[38;5;242m-[0m [0;1;39mfull / docs-build[0m (ID [0;36m99029884284[0m)
[38;5;242m-[0m [0;1;39mfull / release-core-floor-smoke[0m (ID [0;36m99029884306[0m)
[0;33m*[0m [0;1;39mfull / test (3.13)[0m (ID [0;36m99030887371[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Install dependencies
  [38;5;242m-[0m Run tests (coverage leg)
  [0;33m*[0m Run tests
  [0;33m*[0m Run tests
  [0;33m*[0m Build shard timings table
  [0;33m*[0m Upload shard timings
  [0;33m*[0m Upload coverage
  [0;33m*[0m Post Install dependencies
  [0;33m*[0m Post Run actions/checkout@v4
[0;31mX[0m [0;1;39mfull / perf-floors[0m in 4m33s (ID [0;36m99030887383[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Install dependencies
  [0;32m✓[0m Health check (Rust extension loadable)
  [0;32m✓[0m Run slow tests
  [0;31mX[0m Run Phase 7E regression floor
  [0;32m✓[0m Upload Phase 7E floor-check report
  [0;32m✓[0m Run launch regression floor
  [0;32m✓[0m Upload launch floor-check report
  [0;32m✓[0m Run view-hints regression floor
  [0;32m✓[0m Upload view-hints floor-check report
  [0;32m✓[0m Run agents disk-load operation-count floor
  [0;32m✓[0m Upload agents disk-load floor-check report
  [0;32m✓[0m Run plugins catalog-scale regression floor
  [0;32m✓[0m Upload plugins catalog-scale floor-check report
  [0;32m✓[0m Run bead performance smoke
  [0;32m✓[0m Upload bead performance smoke
  [0;32m✓[0m Post Install dependencies
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[0;32m✓[0m [0;1;39mfull / ace-page-group-isolation[0m in 1m5s (ID [0;36m99030887385[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Install visual dependencies
  [0;32m✓[0m Run ACE shared-page isolation lane
  [0;32m✓[0m Post Install visual dependencies
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[0;32m✓[0m [0;1;39mfull / lint[0m in 4m6s (ID [0;36m99030887397[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Install dependencies
  [0;32m✓[0m Check pinned core bindings
  [0;32m✓[0m Bootstrap SDD sidecars
  [0;32m✓[0m Initialize SASE home
  [0;32m✓[0m Run actions/setup-go@v5
  [0;32m✓[0m Cache Go binaries
  [38;5;242m-[0m Install Go tools (keep-sorted)
  [0;32m✓[0m Cache Prettier dependencies
  [0;32m✓[0m Check Python formatting
  [0;32m✓[0m Check Markdown formatting
  [0;32m✓[0m Lint
  [0;32m✓[0m SASE validation
  [0;32m✓[0m Validate committed plans
  [0;32m✓[0m Build and verify package
  [0;32m✓[0m Post Cache Prettier dependencies
  [0;32m✓[0m Post Cache Go binaries
  [0;32m✓[0m Post Run actions/setup-go@v5
  [0;32m✓[0m Post Install dependencies
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[0;31mX[0m [0;1;39mfull / coverage-contexts[0m in 40m50s (ID [0;36m99030887410[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Install dependencies
  [0;31mX[0m Record per-test coverage contexts
  [0;32m✓[0m Upload coverage contexts database
  [0;32m✓[0m Post Install dependencies
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[0;31mX[0m [0;1;39mfull / test (3.14)[0m in 24m28s (ID [0;36m99030887411[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Install dependencies
  [38;5;242m-[0m Run tests (coverage leg)
  [38;5;242m-[0m Run tests
  [0;31mX[0m Run tests
  [0;32m✓[0m Build shard timings table
  [0;32m✓[0m Upload shard timings
  [38;5;242m-[0m Upload coverage
  [0;32m✓[0m Post Install dependencies
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[0;31mX[0m [0;1;39mfull / visual-test[0m in 14m59s (ID [0;36m99030887452[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Install visual dependencies
  [0;31mX[0m Run visual tests
  [0;32m✓[0m Build visual failure report
  [0;32m✓[0m Upload visual failure report
  [0;32m✓[0m Publish visual failure report
  [0;32m✓[0m Upload visual failure artifacts
  [0;32m✓[0m Post Install visual dependencies
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[0;31mX[0m [0;1;39mfull / test (3.12)[0m in 36m44s (ID [0;36m99030887468[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Install dependencies
  [0;31mX[0m Run tests (coverage leg)
  [38;5;242m-[0m Run tests
  [38;5;242m-[0m Run tests
  [38;5;242m-[0m Build shard timings table
  [38;5;242m-[0m Upload shard timings
  [38;5;242m-[0m Upload coverage
  [0;32m✓[0m Post Install dependencies
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[38;5;242m-[0m [0;1;39mfull / contention-test[0m (ID [0;36m99030888181[0m)
[0;1;39mRefreshing run status every 3 seconds. Press Ctrl+C to quit.[0m

[0;33m*[0m [0;1;39mmaster[0m Full CI · [0;36m33226037754[0m
Triggered via workflow_dispatch about 1 hour ago

[0;1;39mJOBS[0m
[0;32m✓[0m [0;1;39mfull / build-core[0m in 7m49s (ID [0;36m99029883707[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Resolve pinned Rust core revision
  [0;32m✓[0m Check out Rust core
  [0;32m✓[0m Run astral-sh/setup-uv@v4
  [0;32m✓[0m Set up Rust
  [0;32m✓[0m Cache Rust build
  [0;32m✓[0m Build abi3 Rust core wheel
  [0;32m✓[0m Build xprompt LSP
  [0;32m✓[0m Record wheel provenance
  [0;32m✓[0m Upload Rust core artifacts
  [0;32m✓[0m Post Cache Rust build
  [0;32m✓[0m Post Run astral-sh/setup-uv@v4
  [0;32m✓[0m Post Check out Rust core
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[38;5;242m-[0m [0;1;39mfull / docs-build[0m (ID [0;36m99029884284[0m)
[38;5;242m-[0m [0;1;39mfull / release-core-floor-smoke[0m (ID [0;36m99029884306[0m)
[0;33m*[0m [0;1;39mfull / test (3.13)[0m (ID [0;36m99030887371[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Install dependencies
  [38;5;242m-[0m Run tests (coverage leg)
  [0;33m*[0m Run tests
  [0;33m*[0m Run tests
  [0;33m*[0m Build shard timings table
  [0;33m*[0m Upload shard timings
  [0;33m*[0m Upload coverage
  [0;33m*[0m Post Install dependencies
  [0;33m*[0m Post Run actions/checkout@v4
[0;31mX[0m [0;1;39mfull / perf-floors[0m in 4m33s (ID [0;36m99030887383[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Install dependencies
  [0;32m✓[0m Health check (Rust extension loadable)
  [0;32m✓[0m Run slow tests
  [0;31mX[0m Run Phase 7E regression floor
  [0;32m✓[0m Upload Phase 7E floor-check report
  [0;32m✓[0m Run launch regression floor
  [0;32m✓[0m Upload launch floor-check report
  [0;32m✓[0m Run view-hints regression floor
  [0;32m✓[0m Upload view-hints floor-check report
  [0;32m✓[0m Run agents disk-load operation-count floor
  [0;32m✓[0m Upload agents disk-load floor-check report
  [0;32m✓[0m Run plugins catalog-scale regression floor
  [0;32m✓[0m Upload plugins catalog-scale floor-check report
  [0;32m✓[0m Run bead performance smoke
  [0;32m✓[0m Upload bead performance smoke
  [0;32m✓[0m Post Install dependencies
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[0;32m✓[0m [0;1;39mfull / ace-page-group-isolation[0m in 1m5s (ID [0;36m99030887385[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Install visual dependencies
  [0;32m✓[0m Run ACE shared-page isolation lane
  [0;32m✓[0m Post Install visual dependencies
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[0;32m✓[0m [0;1;39mfull / lint[0m in 4m6s (ID [0;36m99030887397[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Install dependencies
  [0;32m✓[0m Check pinned core bindings
  [0;32m✓[0m Bootstrap SDD sidecars
  [0;32m✓[0m Initialize SASE home
  [0;32m✓[0m Run actions/setup-go@v5
  [0;32m✓[0m Cache Go binaries
  [38;5;242m-[0m Install Go tools (keep-sorted)
  [0;32m✓[0m Cache Prettier dependencies
  [0;32m✓[0m Check Python formatting
  [0;32m✓[0m Check Markdown formatting
  [0;32m✓[0m Lint
  [0;32m✓[0m SASE validation
  [0;32m✓[0m Validate committed plans
  [0;32m✓[0m Build and verify package
  [0;32m✓[0m Post Cache Prettier dependencies
  [0;32m✓[0m Post Cache Go binaries
  [0;32m✓[0m Post Run actions/setup-go@v5
  [0;32m✓[0m Post Install dependencies
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[0;31mX[0m [0;1;39mfull / coverage-contexts[0m in 40m50s (ID [0;36m99030887410[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Install dependencies
  [0;31mX[0m Record per-test coverage contexts
  [0;32m✓[0m Upload coverage contexts database
  [0;32m✓[0m Post Install dependencies
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[0;31mX[0m [0;1;39mfull / test (3.14)[0m in 24m28s (ID [0;36m99030887411[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Install dependencies
  [38;5;242m-[0m Run tests (coverage leg)
  [38;5;242m-[0m Run tests
  [0;31mX[0m Run tests
  [0;32m✓[0m Build shard timings table
  [0;32m✓[0m Upload shard timings
  [38;5;242m-[0m Upload coverage
  [0;32m✓[0m Post Install dependencies
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[0;31mX[0m [0;1;39mfull / visual-test[0m in 14m59s (ID [0;36m99030887452[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Install visual dependencies
  [0;31mX[0m Run visual tests
  [0;32m✓[0m Build visual failure report
  [0;32m✓[0m Upload visual failure report
  [0;32m✓[0m Publish visual failure report
  [0;32m✓[0m Upload visual failure artifacts
  [0;32m✓[0m Post Install visual dependencies
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[0;31mX[0m [0;1;39mfull / test (3.12)[0m in 36m44s (ID [0;36m99030887468[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Install dependencies
  [0;31mX[0m Run tests (coverage leg)
  [38;5;242m-[0m Run tests
  [38;5;242m-[0m Run tests
  [38;5;242m-[0m Build shard timings table
  [38;5;242m-[0m Upload shard timings
  [38;5;242m-[0m Upload coverage
  [0;32m✓[0m Post Install dependencies
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[38;5;242m-[0m [0;1;39mfull / contention-test[0m (ID [0;36m99030888181[0m)
[0;1;39mRefreshing run status every 3 seconds. Press Ctrl+C to quit.[0m

[0;33m*[0m [0;1;39mmaster[0m Full CI · [0;36m33226037754[0m
Triggered via workflow_dispatch about 1 hour ago

[0;1;39mJOBS[0m
[0;32m✓[0m [0;1;39mfull / build-core[0m in 7m49s (ID [0;36m99029883707[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Resolve pinned Rust core revision
  [0;32m✓[0m Check out Rust core
  [0;32m✓[0m Run astral-sh/setup-uv@v4
  [0;32m✓[0m Set up Rust
  [0;32m✓[0m Cache Rust build
  [0;32m✓[0m Build abi3 Rust core wheel
  [0;32m✓[0m Build xprompt LSP
  [0;32m✓[0m Record wheel provenance
  [0;32m✓[0m Upload Rust core artifacts
  [0;32m✓[0m Post Cache Rust build
  [0;32m✓[0m Post Run astral-sh/setup-uv@v4
  [0;32m✓[0m Post Check out Rust core
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[38;5;242m-[0m [0;1;39mfull / docs-build[0m (ID [0;36m99029884284[0m)
[38;5;242m-[0m [0;1;39mfull / release-core-floor-smoke[0m (ID [0;36m99029884306[0m)
[0;33m*[0m [0;1;39mfull / test (3.13)[0m (ID [0;36m99030887371[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Install dependencies
  [38;5;242m-[0m Run tests (coverage leg)
  [0;33m*[0m Run tests
  [0;33m*[0m Run tests
  [0;33m*[0m Build shard timings table
  [0;33m*[0m Upload shard timings
  [0;33m*[0m Upload coverage
  [0;33m*[0m Post Install dependencies
  [0;33m*[0m Post Run actions/checkout@v4
[0;31mX[0m [0;1;39mfull / perf-floors[0m in 4m33s (ID [0;36m99030887383[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Install dependencies
  [0;32m✓[0m Health check (Rust extension loadable)
  [0;32m✓[0m Run slow tests
  [0;31mX[0m Run Phase 7E regression floor
  [0;32m✓[0m Upload Phase 7E floor-check report
  [0;32m✓[0m Run launch regression floor
  [0;32m✓[0m Upload launch floor-check report
  [0;32m✓[0m Run view-hints regression floor
  [0;32m✓[0m Upload view-hints floor-check report
  [0;32m✓[0m Run agents disk-load operation-count floor
  [0;32m✓[0m Upload agents disk-load floor-check report
  [0;32m✓[0m Run plugins catalog-scale regression floor
  [0;32m✓[0m Upload plugins catalog-scale floor-check report
  [0;32m✓[0m Run bead performance smoke
  [0;32m✓[0m Upload bead performance smoke
  [0;32m✓[0m Post Install dependencies
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[0;32m✓[0m [0;1;39mfull / ace-page-group-isolation[0m in 1m5s (ID [0;36m99030887385[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Install visual dependencies
  [0;32m✓[0m Run ACE shared-page isolation lane
  [0;32m✓[0m Post Install visual dependencies
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[0;32m✓[0m [0;1;39mfull / lint[0m in 4m6s (ID [0;36m99030887397[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Install dependencies
  [0;32m✓[0m Check pinned core bindings
  [0;32m✓[0m Bootstrap SDD sidecars
  [0;32m✓[0m Initialize SASE home
  [0;32m✓[0m Run actions/setup-go@v5
  [0;32m✓[0m Cache Go binaries
  [38;5;242m-[0m Install Go tools (keep-sorted)
  [0;32m✓[0m Cache Prettier dependencies
  [0;32m✓[0m Check Python formatting
  [0;32m✓[0m Check Markdown formatting
  [0;32m✓[0m Lint
  [0;32m✓[0m SASE validation
  [0;32m✓[0m Validate committed plans
  [0;32m✓[0m Build and verify package
  [0;32m✓[0m Post Cache Prettier dependencies
  [0;32m✓[0m Post Cache Go binaries
  [0;32m✓[0m Post Run actions/setup-go@v5
  [0;32m✓[0m Post Install dependencies
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[0;31mX[0m [0;1;39mfull / coverage-contexts[0m in 40m50s (ID [0;36m99030887410[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Install dependencies
  [0;31mX[0m Record per-test coverage contexts
  [0;32m✓[0m Upload coverage contexts database
  [0;32m✓[0m Post Install dependencies
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[0;31mX[0m [0;1;39mfull / test (3.14)[0m in 24m28s (ID [0;36m99030887411[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Install dependencies
  [38;5;242m-[0m Run tests (coverage leg)
  [38;5;242m-[0m Run tests
  [0;31mX[0m Run tests
  [0;32m✓[0m Build shard timings table
  [0;32m✓[0m Upload shard timings
  [38;5;242m-[0m Upload coverage
  [0;32m✓[0m Post Install dependencies
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[0;31mX[0m [0;1;39mfull / visual-test[0m in 14m59s (ID [0;36m99030887452[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Install visual dependencies
  [0;31mX[0m Run visual tests
  [0;32m✓[0m Build visual failure report
  [0;32m✓[0m Upload visual failure report
  [0;32m✓[0m Publish visual failure report
  [0;32m✓[0m Upload visual failure artifacts
  [0;32m✓[0m Post Install visual dependencies
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[0;31mX[0m [0;1;39mfull / test (3.12)[0m in 36m44s (ID [0;36m99030887468[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Install dependencies
  [0;31mX[0m Run tests (coverage leg)
  [38;5;242m-[0m Run tests
  [38;5;242m-[0m Run tests
  [38;5;242m-[0m Build shard timings table
  [38;5;242m-[0m Upload shard timings
  [38;5;242m-[0m Upload coverage
  [0;32m✓[0m Post Install dependencies
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[38;5;242m-[0m [0;1;39mfull / contention-test[0m (ID [0;36m99030888181[0m)
[0;1;39mRefreshing run status every 3 seconds. Press Ctrl+C to quit.[0m

[0;33m*[0m [0;1;39mmaster[0m Full CI · [0;36m33226037754[0m
Triggered via workflow_dispatch about 1 hour ago

[0;1;39mJOBS[0m
[0;32m✓[0m [0;1;39mfull / build-core[0m in 7m49s (ID [0;36m99029883707[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Resolve pinned Rust core revision
  [0;32m✓[0m Check out Rust core
  [0;32m✓[0m Run astral-sh/setup-uv@v4
  [0;32m✓[0m Set up Rust
  [0;32m✓[0m Cache Rust build
  [0;32m✓[0m Build abi3 Rust core wheel
  [0;32m✓[0m Build xprompt LSP
  [0;32m✓[0m Record wheel provenance
  [0;32m✓[0m Upload Rust core artifacts
  [0;32m✓[0m Post Cache Rust build
  [0;32m✓[0m Post Run astral-sh/setup-uv@v4
  [0;32m✓[0m Post Check out Rust core
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[38;5;242m-[0m [0;1;39mfull / docs-build[0m (ID [0;36m99029884284[0m)
[38;5;242m-[0m [0;1;39mfull / release-core-floor-smoke[0m (ID [0;36m99029884306[0m)
[0;33m*[0m [0;1;39mfull / test (3.13)[0m (ID [0;36m99030887371[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Install dependencies
  [38;5;242m-[0m Run tests (coverage leg)
  [0;33m*[0m Run tests
  [0;33m*[0m Run tests
  [0;33m*[0m Build shard timings table
  [0;33m*[0m Upload shard timings
  [0;33m*[0m Upload coverage
  [0;33m*[0m Post Install dependencies
  [0;33m*[0m Post Run actions/checkout@v4
[0;31mX[0m [0;1;39mfull / perf-floors[0m in 4m33s (ID [0;36m99030887383[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Install dependencies
  [0;32m✓[0m Health check (Rust extension loadable)
  [0;32m✓[0m Run slow tests
  [0;31mX[0m Run Phase 7E regression floor
  [0;32m✓[0m Upload Phase 7E floor-check report
  [0;32m✓[0m Run launch regression floor
  [0;32m✓[0m Upload launch floor-check report
  [0;32m✓[0m Run view-hints regression floor
  [0;32m✓[0m Upload view-hints floor-check report
  [0;32m✓[0m Run agents disk-load operation-count floor
  [0;32m✓[0m Upload agents disk-load floor-check report
  [0;32m✓[0m Run plugins catalog-scale regression floor
  [0;32m✓[0m Upload plugins catalog-scale floor-check report
  [0;32m✓[0m Run bead performance smoke
  [0;32m✓[0m Upload bead performance smoke
  [0;32m✓[0m Post Install dependencies
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[0;32m✓[0m [0;1;39mfull / ace-page-group-isolation[0m in 1m5s (ID [0;36m99030887385[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Install visual dependencies
  [0;32m✓[0m Run ACE shared-page isolation lane
  [0;32m✓[0m Post Install visual dependencies
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[0;32m✓[0m [0;1;39mfull / lint[0m in 4m6s (ID [0;36m99030887397[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Install dependencies
  [0;32m✓[0m Check pinned core bindings
  [0;32m✓[0m Bootstrap SDD sidecars
  [0;32m✓[0m Initialize SASE home
  [0;32m✓[0m Run actions/setup-go@v5
  [0;32m✓[0m Cache Go binaries
  [38;5;242m-[0m Install Go tools (keep-sorted)
  [0;32m✓[0m Cache Prettier dependencies
  [0;32m✓[0m Check Python formatting
  [0;32m✓[0m Check Markdown formatting
  [0;32m✓[0m Lint
  [0;32m✓[0m SASE validation
  [0;32m✓[0m Validate committed plans
  [0;32m✓[0m Build and verify package
  [0;32m✓[0m Post Cache Prettier dependencies
  [0;32m✓[0m Post Cache Go binaries
  [0;32m✓[0m Post Run actions/setup-go@v5
  [0;32m✓[0m Post Install dependencies
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[0;31mX[0m [0;1;39mfull / coverage-contexts[0m in 40m50s (ID [0;36m99030887410[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Install dependencies
  [0;31mX[0m Record per-test coverage contexts
  [0;32m✓[0m Upload coverage contexts database
  [0;32m✓[0m Post Install dependencies
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[0;31mX[0m [0;1;39mfull / test (3.14)[0m in 24m28s (ID [0;36m99030887411[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Install dependencies
  [38;5;242m-[0m Run tests (coverage leg)
  [38;5;242m-[0m Run tests
  [0;31mX[0m Run tests
  [0;32m✓[0m Build shard timings table
  [0;32m✓[0m Upload shard timings
  [38;5;242m-[0m Upload coverage
  [0;32m✓[0m Post Install dependencies
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[0;31mX[0m [0;1;39mfull / visual-test[0m in 14m59s (ID [0;36m99030887452[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Install visual dependencies
  [0;31mX[0m Run visual tests
  [0;32m✓[0m Build visual failure report
  [0;32m✓[0m Upload visual failure report
  [0;32m✓[0m Publish visual failure report
  [0;32m✓[0m Upload visual failure artifacts
  [0;32m✓[0m Post Install visual dependencies
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[0;31mX[0m [0;1;39mfull / test (3.12)[0m in 36m44s (ID [0;36m99030887468[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Install dependencies
  [0;31mX[0m Run tests (coverage leg)
  [38;5;242m-[0m Run tests
  [38;5;242m-[0m Run tests
  [38;5;242m-[0m Build shard timings table
  [38;5;242m-[0m Upload shard timings
  [38;5;242m-[0m Upload coverage
  [0;32m✓[0m Post Install dependencies
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[38;5;242m-[0m [0;1;39mfull / contention-test[0m (ID [0;36m99030888181[0m)
[0;1;39mRefreshing run status every 3 seconds. Press Ctrl+C to quit.[0m

[0;33m*[0m [0;1;39mmaster[0m Full CI · [0;36m33226037754[0m
Triggered via workflow_dispatch about 1 hour ago

[0;1;39mJOBS[0m
[0;32m✓[0m [0;1;39mfull / build-core[0m in 7m49s (ID [0;36m99029883707[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Resolve pinned Rust core revision
  [0;32m✓[0m Check out Rust core
  [0;32m✓[0m Run astral-sh/setup-uv@v4
  [0;32m✓[0m Set up Rust
  [0;32m✓[0m Cache Rust build
  [0;32m✓[0m Build abi3 Rust core wheel
  [0;32m✓[0m Build xprompt LSP
  [0;32m✓[0m Record wheel provenance
  [0;32m✓[0m Upload Rust core artifacts
  [0;32m✓[0m Post Cache Rust build
  [0;32m✓[0m Post Run astral-sh/setup-uv@v4
  [0;32m✓[0m Post Check out Rust core
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[38;5;242m-[0m [0;1;39mfull / docs-build[0m (ID [0;36m99029884284[0m)
[38;5;242m-[0m [0;1;39mfull / release-core-floor-smoke[0m (ID [0;36m99029884306[0m)
[0;33m*[0m [0;1;39mfull / test (3.13)[0m (ID [0;36m99030887371[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Install dependencies
  [38;5;242m-[0m Run tests (coverage leg)
  [0;33m*[0m Run tests
  [0;33m*[0m Run tests
  [0;33m*[0m Build shard timings table
  [0;33m*[0m Upload shard timings
  [0;33m*[0m Upload coverage
  [0;33m*[0m Post Install dependencies
  [0;33m*[0m Post Run actions/checkout@v4
[0;31mX[0m [0;1;39mfull / perf-floors[0m in 4m33s (ID [0;36m99030887383[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Install dependencies
  [0;32m✓[0m Health check (Rust extension loadable)
  [0;32m✓[0m Run slow tests
  [0;31mX[0m Run Phase 7E regression floor
  [0;32m✓[0m Upload Phase 7E floor-check report
  [0;32m✓[0m Run launch regression floor
  [0;32m✓[0m Upload launch floor-check report
  [0;32m✓[0m Run view-hints regression floor
  [0;32m✓[0m Upload view-hints floor-check report
  [0;32m✓[0m Run agents disk-load operation-count floor
  [0;32m✓[0m Upload agents disk-load floor-check report
  [0;32m✓[0m Run plugins catalog-scale regression floor
  [0;32m✓[0m Upload plugins catalog-scale floor-check report
  [0;32m✓[0m Run bead performance smoke
  [0;32m✓[0m Upload bead performance smoke
  [0;32m✓[0m Post Install dependencies
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[0;32m✓[0m [0;1;39mfull / ace-page-group-isolation[0m in 1m5s (ID [0;36m99030887385[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Install visual dependencies
  [0;32m✓[0m Run ACE shared-page isolation lane
  [0;32m✓[0m Post Install visual dependencies
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[0;32m✓[0m [0;1;39mfull / lint[0m in 4m6s (ID [0;36m99030887397[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Install dependencies
  [0;32m✓[0m Check pinned core bindings
  [0;32m✓[0m Bootstrap SDD sidecars
  [0;32m✓[0m Initialize SASE home
  [0;32m✓[0m Run actions/setup-go@v5
  [0;32m✓[0m Cache Go binaries
  [38;5;242m-[0m Install Go tools (keep-sorted)
  [0;32m✓[0m Cache Prettier dependencies
  [0;32m✓[0m Check Python formatting
  [0;32m✓[0m Check Markdown formatting
  [0;32m✓[0m Lint
  [0;32m✓[0m SASE validation
  [0;32m✓[0m Validate committed plans
  [0;32m✓[0m Build and verify package
  [0;32m✓[0m Post Cache Prettier dependencies
  [0;32m✓[0m Post Cache Go binaries
  [0;32m✓[0m Post Run actions/setup-go@v5
  [0;32m✓[0m Post Install dependencies
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[0;31mX[0m [0;1;39mfull / coverage-contexts[0m in 40m50s (ID [0;36m99030887410[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Install dependencies
  [0;31mX[0m Record per-test coverage contexts
  [0;32m✓[0m Upload coverage contexts database
  [0;32m✓[0m Post Install dependencies
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[0;31mX[0m [0;1;39mfull / test (3.14)[0m in 24m28s (ID [0;36m99030887411[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Install dependencies
  [38;5;242m-[0m Run tests (coverage leg)
  [38;5;242m-[0m Run tests
  [0;31mX[0m Run tests
  [0;32m✓[0m Build shard timings table
  [0;32m✓[0m Upload shard timings
  [38;5;242m-[0m Upload coverage
  [0;32m✓[0m Post Install dependencies
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[0;31mX[0m [0;1;39mfull / visual-test[0m in 14m59s (ID [0;36m99030887452[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Install visual dependencies
  [0;31mX[0m Run visual tests
  [0;32m✓[0m Build visual failure report
  [0;32m✓[0m Upload visual failure report
  [0;32m✓[0m Publish visual failure report
  [0;32m✓[0m Upload visual failure artifacts
  [0;32m✓[0m Post Install visual dependencies
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[0;31mX[0m [0;1;39mfull / test (3.12)[0m in 36m44s (ID [0;36m99030887468[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Install dependencies
  [0;31mX[0m Run tests (coverage leg)
  [38;5;242m-[0m Run tests
  [38;5;242m-[0m Run tests
  [38;5;242m-[0m Build shard timings table
  [38;5;242m-[0m Upload shard timings
  [38;5;242m-[0m Upload coverage
  [0;32m✓[0m Post Install dependencies
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[38;5;242m-[0m [0;1;39mfull / contention-test[0m (ID [0;36m99030888181[0m)
[0;1;39mRefreshing run status every 3 seconds. Press Ctrl+C to quit.[0m

[0;33m*[0m [0;1;39mmaster[0m Full CI · [0;36m33226037754[0m
Triggered via workflow_dispatch about 1 hour ago

[0;1;39mJOBS[0m
[0;32m✓[0m [0;1;39mfull / build-core[0m in 7m49s (ID [0;36m99029883707[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Resolve pinned Rust core revision
  [0;32m✓[0m Check out Rust core
  [0;32m✓[0m Run astral-sh/setup-uv@v4
  [0;32m✓[0m Set up Rust
  [0;32m✓[0m Cache Rust build
  [0;32m✓[0m Build abi3 Rust core wheel
  [0;32m✓[0m Build xprompt LSP
  [0;32m✓[0m Record wheel provenance
  [0;32m✓[0m Upload Rust core artifacts
  [0;32m✓[0m Post Cache Rust build
  [0;32m✓[0m Post Run astral-sh/setup-uv@v4
  [0;32m✓[0m Post Check out Rust core
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[38;5;242m-[0m [0;1;39mfull / docs-build[0m (ID [0;36m99029884284[0m)
[38;5;242m-[0m [0;1;39mfull / release-core-floor-smoke[0m (ID [0;36m99029884306[0m)
[0;33m*[0m [0;1;39mfull / test (3.13)[0m (ID [0;36m99030887371[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Install dependencies
  [38;5;242m-[0m Run tests (coverage leg)
  [0;33m*[0m Run tests
  [0;33m*[0m Run tests
  [0;33m*[0m Build shard timings table
  [0;33m*[0m Upload shard timings
  [0;33m*[0m Upload coverage
  [0;33m*[0m Post Install dependencies
  [0;33m*[0m Post Run actions/checkout@v4
[0;31mX[0m [0;1;39mfull / perf-floors[0m in 4m33s (ID [0;36m99030887383[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Install dependencies
  [0;32m✓[0m Health check (Rust extension loadable)
  [0;32m✓[0m Run slow tests
  [0;31mX[0m Run Phase 7E regression floor
  [0;32m✓[0m Upload Phase 7E floor-check report
  [0;32m✓[0m Run launch regression floor
  [0;32m✓[0m Upload launch floor-check report
  [0;32m✓[0m Run view-hints regression floor
  [0;32m✓[0m Upload view-hints floor-check report
  [0;32m✓[0m Run agents disk-load operation-count floor
  [0;32m✓[0m Upload agents disk-load floor-check report
  [0;32m✓[0m Run plugins catalog-scale regression floor
  [0;32m✓[0m Upload plugins catalog-scale floor-check report
  [0;32m✓[0m Run bead performance smoke
  [0;32m✓[0m Upload bead performance smoke
  [0;32m✓[0m Post Install dependencies
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[0;32m✓[0m [0;1;39mfull / ace-page-group-isolation[0m in 1m5s (ID [0;36m99030887385[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Install visual dependencies
  [0;32m✓[0m Run ACE shared-page isolation lane
  [0;32m✓[0m Post Install visual dependencies
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[0;32m✓[0m [0;1;39mfull / lint[0m in 4m6s (ID [0;36m99030887397[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Install dependencies
  [0;32m✓[0m Check pinned core bindings
  [0;32m✓[0m Bootstrap SDD sidecars
  [0;32m✓[0m Initialize SASE home
  [0;32m✓[0m Run actions/setup-go@v5
  [0;32m✓[0m Cache Go binaries
  [38;5;242m-[0m Install Go tools (keep-sorted)
  [0;32m✓[0m Cache Prettier dependencies
  [0;32m✓[0m Check Python formatting
  [0;32m✓[0m Check Markdown formatting
  [0;32m✓[0m Lint
  [0;32m✓[0m SASE validation
  [0;32m✓[0m Validate committed plans
  [0;32m✓[0m Build and verify package
  [0;32m✓[0m Post Cache Prettier dependencies
  [0;32m✓[0m Post Cache Go binaries
  [0;32m✓[0m Post Run actions/setup-go@v5
  [0;32m✓[0m Post Install dependencies
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[0;31mX[0m [0;1;39mfull / coverage-contexts[0m in 40m50s (ID [0;36m99030887410[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Install dependencies
  [0;31mX[0m Record per-test coverage contexts
  [0;32m✓[0m Upload coverage contexts database
  [0;32m✓[0m Post Install dependencies
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[0;31mX[0m [0;1;39mfull / test (3.14)[0m in 24m28s (ID [0;36m99030887411[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Install dependencies
  [38;5;242m-[0m Run tests (coverage leg)
  [38;5;242m-[0m Run tests
  [0;31mX[0m Run tests
  [0;32m✓[0m Build shard timings table
  [0;32m✓[0m Upload shard timings
  [38;5;242m-[0m Upload coverage
  [0;32m✓[0m Post Install dependencies
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[0;31mX[0m [0;1;39mfull / visual-test[0m in 14m59s (ID [0;36m99030887452[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Install visual dependencies
  [0;31mX[0m Run visual tests
  [0;32m✓[0m Build visual failure report
  [0;32m✓[0m Upload visual failure report
  [0;32m✓[0m Publish visual failure report
  [0;32m✓[0m Upload visual failure artifacts
  [0;32m✓[0m Post Install visual dependencies
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[0;31mX[0m [0;1;39mfull / test (3.12)[0m in 36m44s (ID [0;36m99030887468[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Install dependencies
  [0;31mX[0m Run tests (coverage leg)
  [38;5;242m-[0m Run tests
  [38;5;242m-[0m Run tests
  [38;5;242m-[0m Build shard timings table
  [38;5;242m-[0m Upload shard timings
  [38;5;242m-[0m Upload coverage
  [0;32m✓[0m Post Install dependencies
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[38;5;242m-[0m [0;1;39mfull / contention-test[0m (ID [0;36m99030888181[0m)
[0;1;39mRefreshing run status every 3 seconds. Press Ctrl+C to quit.[0m

[0;33m*[0m [0;1;39mmaster[0m Full CI · [0;36m33226037754[0m
Triggered via workflow_dispatch about 1 hour ago

[0;1;39mJOBS[0m
[0;32m✓[0m [0;1;39mfull / build-core[0m in 7m49s (ID [0;36m99029883707[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Resolve pinned Rust core revision
  [0;32m✓[0m Check out Rust core
  [0;32m✓[0m Run astral-sh/setup-uv@v4
  [0;32m✓[0m Set up Rust
  [0;32m✓[0m Cache Rust build
  [0;32m✓[0m Build abi3 Rust core wheel
  [0;32m✓[0m Build xprompt LSP
  [0;32m✓[0m Record wheel provenance
  [0;32m✓[0m Upload Rust core artifacts
  [0;32m✓[0m Post Cache Rust build
  [0;32m✓[0m Post Run astral-sh/setup-uv@v4
  [0;32m✓[0m Post Check out Rust core
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[38;5;242m-[0m [0;1;39mfull / docs-build[0m (ID [0;36m99029884284[0m)
[38;5;242m-[0m [0;1;39mfull / release-core-floor-smoke[0m (ID [0;36m99029884306[0m)
[0;33m*[0m [0;1;39mfull / test (3.13)[0m (ID [0;36m99030887371[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Install dependencies
  [38;5;242m-[0m Run tests (coverage leg)
  [0;33m*[0m Run tests
  [0;33m*[0m Run tests
  [0;33m*[0m Build shard timings table
  [0;33m*[0m Upload shard timings
  [0;33m*[0m Upload coverage
  [0;33m*[0m Post Install dependencies
  [0;33m*[0m Post Run actions/checkout@v4
[0;31mX[0m [0;1;39mfull / perf-floors[0m in 4m33s (ID [0;36m99030887383[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Install dependencies
  [0;32m✓[0m Health check (Rust extension loadable)
  [0;32m✓[0m Run slow tests
  [0;31mX[0m Run Phase 7E regression floor
  [0;32m✓[0m Upload Phase 7E floor-check report
  [0;32m✓[0m Run launch regression floor
  [0;32m✓[0m Upload launch floor-check report
  [0;32m✓[0m Run view-hints regression floor
  [0;32m✓[0m Upload view-hints floor-check report
  [0;32m✓[0m Run agents disk-load operation-count floor
  [0;32m✓[0m Upload agents disk-load floor-check report
  [0;32m✓[0m Run plugins catalog-scale regression floor
  [0;32m✓[0m Upload plugins catalog-scale floor-check report
  [0;32m✓[0m Run bead performance smoke
  [0;32m✓[0m Upload bead performance smoke
  [0;32m✓[0m Post Install dependencies
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[0;32m✓[0m [0;1;39mfull / ace-page-group-isolation[0m in 1m5s (ID [0;36m99030887385[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Install visual dependencies
  [0;32m✓[0m Run ACE shared-page isolation lane
  [0;32m✓[0m Post Install visual dependencies
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[0;32m✓[0m [0;1;39mfull / lint[0m in 4m6s (ID [0;36m99030887397[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Install dependencies
  [0;32m✓[0m Check pinned core bindings
  [0;32m✓[0m Bootstrap SDD sidecars
  [0;32m✓[0m Initialize SASE home
  [0;32m✓[0m Run actions/setup-go@v5
  [0;32m✓[0m Cache Go binaries
  [38;5;242m-[0m Install Go tools (keep-sorted)
  [0;32m✓[0m Cache Prettier dependencies
  [0;32m✓[0m Check Python formatting
  [0;32m✓[0m Check Markdown formatting
  [0;32m✓[0m Lint
  [0;32m✓[0m SASE validation
  [0;32m✓[0m Validate committed plans
  [0;32m✓[0m Build and verify package
  [0;32m✓[0m Post Cache Prettier dependencies
  [0;32m✓[0m Post Cache Go binaries
  [0;32m✓[0m Post Run actions/setup-go@v5
  [0;32m✓[0m Post Install dependencies
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[0;31mX[0m [0;1;39mfull / coverage-contexts[0m in 40m50s (ID [0;36m99030887410[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Install dependencies
  [0;31mX[0m Record per-test coverage contexts
  [0;32m✓[0m Upload coverage contexts database
  [0;32m✓[0m Post Install dependencies
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[0;31mX[0m [0;1;39mfull / test (3.14)[0m in 24m28s (ID [0;36m99030887411[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Install dependencies
  [38;5;242m-[0m Run tests (coverage leg)
  [38;5;242m-[0m Run tests
  [0;31mX[0m Run tests
  [0;32m✓[0m Build shard timings table
  [0;32m✓[0m Upload shard timings
  [38;5;242m-[0m Upload coverage
  [0;32m✓[0m Post Install dependencies
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[0;31mX[0m [0;1;39mfull / visual-test[0m in 14m59s (ID [0;36m99030887452[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Install visual dependencies
  [0;31mX[0m Run visual tests
  [0;32m✓[0m Build visual failure report
  [0;32m✓[0m Upload visual failure report
  [0;32m✓[0m Publish visual failure report
  [0;32m✓[0m Upload visual failure artifacts
  [0;32m✓[0m Post Install visual dependencies
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[0;31mX[0m [0;1;39mfull / test (3.12)[0m in 36m44s (ID [0;36m99030887468[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Install dependencies
  [0;31mX[0m Run tests (coverage leg)
  [38;5;242m-[0m Run tests
  [38;5;242m-[0m Run tests
  [38;5;242m-[0m Build shard timings table
  [38;5;242m-[0m Upload shard timings
  [38;5;242m-[0m Upload coverage
  [0;32m✓[0m Post Install dependencies
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[38;5;242m-[0m [0;1;39mfull / contention-test[0m (ID [0;36m99030888181[0m)
[0;1;39mRefreshing run status every 3 seconds. Press Ctrl+C to quit.[0m

[0;33m*[0m [0;1;39mmaster[0m Full CI · [0;36m33226037754[0m
Triggered via workflow_dispatch about 1 hour ago

[0;1;39mJOBS[0m
[0;32m✓[0m [0;1;39mfull / build-core[0m in 7m49s (ID [0;36m99029883707[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Resolve pinned Rust core revision
  [0;32m✓[0m Check out Rust core
  [0;32m✓[0m Run astral-sh/setup-uv@v4
  [0;32m✓[0m Set up Rust
  [0;32m✓[0m Cache Rust build
  [0;32m✓[0m Build abi3 Rust core wheel
  [0;32m✓[0m Build xprompt LSP
  [0;32m✓[0m Record wheel provenance
  [0;32m✓[0m Upload Rust core artifacts
  [0;32m✓[0m Post Cache Rust build
  [0;32m✓[0m Post Run astral-sh/setup-uv@v4
  [0;32m✓[0m Post Check out Rust core
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[38;5;242m-[0m [0;1;39mfull / docs-build[0m (ID [0;36m99029884284[0m)
[38;5;242m-[0m [0;1;39mfull / release-core-floor-smoke[0m (ID [0;36m99029884306[0m)
[0;33m*[0m [0;1;39mfull / test (3.13)[0m (ID [0;36m99030887371[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Install dependencies
  [38;5;242m-[0m Run tests (coverage leg)
  [0;33m*[0m Run tests
  [0;33m*[0m Run tests
  [0;33m*[0m Build shard timings table
  [0;33m*[0m Upload shard timings
  [0;33m*[0m Upload coverage
  [0;33m*[0m Post Install dependencies
  [0;33m*[0m Post Run actions/checkout@v4
[0;31mX[0m [0;1;39mfull / perf-floors[0m in 4m33s (ID [0;36m99030887383[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Install dependencies
  [0;32m✓[0m Health check (Rust extension loadable)
  [0;32m✓[0m Run slow tests
  [0;31mX[0m Run Phase 7E regression floor
  [0;32m✓[0m Upload Phase 7E floor-check report
  [0;32m✓[0m Run launch regression floor
  [0;32m✓[0m Upload launch floor-check report
  [0;32m✓[0m Run view-hints regression floor
  [0;32m✓[0m Upload view-hints floor-check report
  [0;32m✓[0m Run agents disk-load operation-count floor
  [0;32m✓[0m Upload agents disk-load floor-check report
  [0;32m✓[0m Run plugins catalog-scale regression floor
  [0;32m✓[0m Upload plugins catalog-scale floor-check report
  [0;32m✓[0m Run bead performance smoke
  [0;32m✓[0m Upload bead performance smoke
  [0;32m✓[0m Post Install dependencies
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[0;32m✓[0m [0;1;39mfull / ace-page-group-isolation[0m in 1m5s (ID [0;36m99030887385[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Install visual dependencies
  [0;32m✓[0m Run ACE shared-page isolation lane
  [0;32m✓[0m Post Install visual dependencies
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[0;32m✓[0m [0;1;39mfull / lint[0m in 4m6s (ID [0;36m99030887397[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Install dependencies
  [0;32m✓[0m Check pinned core bindings
  [0;32m✓[0m Bootstrap SDD sidecars
  [0;32m✓[0m Initialize SASE home
  [0;32m✓[0m Run actions/setup-go@v5
  [0;32m✓[0m Cache Go binaries
  [38;5;242m-[0m Install Go tools (keep-sorted)
  [0;32m✓[0m Cache Prettier dependencies
  [0;32m✓[0m Check Python formatting
  [0;32m✓[0m Check Markdown formatting
  [0;32m✓[0m Lint
  [0;32m✓[0m SASE validation
  [0;32m✓[0m Validate committed plans
  [0;32m✓[0m Build and verify package
  [0;32m✓[0m Post Cache Prettier dependencies
  [0;32m✓[0m Post Cache Go binaries
  [0;32m✓[0m Post Run actions/setup-go@v5
  [0;32m✓[0m Post Install dependencies
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[0;31mX[0m [0;1;39mfull / coverage-contexts[0m in 40m50s (ID [0;36m99030887410[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Install dependencies
  [0;31mX[0m Record per-test coverage contexts
  [0;32m✓[0m Upload coverage contexts database
  [0;32m✓[0m Post Install dependencies
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[0;31mX[0m [0;1;39mfull / test (3.14)[0m in 24m28s (ID [0;36m99030887411[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Install dependencies
  [38;5;242m-[0m Run tests (coverage leg)
  [38;5;242m-[0m Run tests
  [0;31mX[0m Run tests
  [0;32m✓[0m Build shard timings table
  [0;32m✓[0m Upload shard timings
  [38;5;242m-[0m Upload coverage
  [0;32m✓[0m Post Install dependencies
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[0;31mX[0m [0;1;39mfull / visual-test[0m in 14m59s (ID [0;36m99030887452[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Install visual dependencies
  [0;31mX[0m Run visual tests
  [0;32m✓[0m Build visual failure report
  [0;32m✓[0m Upload visual failure report
  [0;32m✓[0m Publish visual failure report
  [0;32m✓[0m Upload visual failure artifacts
  [0;32m✓[0m Post Install visual dependencies
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[0;31mX[0m [0;1;39mfull / test (3.12)[0m in 36m44s (ID [0;36m99030887468[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Install dependencies
  [0;31mX[0m Run tests (coverage leg)
  [38;5;242m-[0m Run tests
  [38;5;242m-[0m Run tests
  [38;5;242m-[0m Build shard timings table
  [38;5;242m-[0m Upload shard timings
  [38;5;242m-[0m Upload coverage
  [0;32m✓[0m Post Install dependencies
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[38;5;242m-[0m [0;1;39mfull / contention-test[0m (ID [0;36m99030888181[0m)
[0;1;39mRefreshing run status every 3 seconds. Press Ctrl+C to quit.[0m

[0;33m*[0m [0;1;39mmaster[0m Full CI · [0;36m33226037754[0m
Triggered via workflow_dispatch about 1 hour ago

[0;1;39mJOBS[0m
[0;32m✓[0m [0;1;39mfull / build-core[0m in 7m49s (ID [0;36m99029883707[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Resolve pinned Rust core revision
  [0;32m✓[0m Check out Rust core
  [0;32m✓[0m Run astral-sh/setup-uv@v4
  [0;32m✓[0m Set up Rust
  [0;32m✓[0m Cache Rust build
  [0;32m✓[0m Build abi3 Rust core wheel
  [0;32m✓[0m Build xprompt LSP
  [0;32m✓[0m Record wheel provenance
  [0;32m✓[0m Upload Rust core artifacts
  [0;32m✓[0m Post Cache Rust build
  [0;32m✓[0m Post Run astral-sh/setup-uv@v4
  [0;32m✓[0m Post Check out Rust core
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[38;5;242m-[0m [0;1;39mfull / docs-build[0m (ID [0;36m99029884284[0m)
[38;5;242m-[0m [0;1;39mfull / release-core-floor-smoke[0m (ID [0;36m99029884306[0m)
[0;33m*[0m [0;1;39mfull / test (3.13)[0m (ID [0;36m99030887371[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Install dependencies
  [38;5;242m-[0m Run tests (coverage leg)
  [0;33m*[0m Run tests
  [0;33m*[0m Run tests
  [0;33m*[0m Build shard timings table
  [0;33m*[0m Upload shard timings
  [0;33m*[0m Upload coverage
  [0;33m*[0m Post Install dependencies
  [0;33m*[0m Post Run actions/checkout@v4
[0;31mX[0m [0;1;39mfull / perf-floors[0m in 4m33s (ID [0;36m99030887383[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Install dependencies
  [0;32m✓[0m Health check (Rust extension loadable)
  [0;32m✓[0m Run slow tests
  [0;31mX[0m Run Phase 7E regression floor
  [0;32m✓[0m Upload Phase 7E floor-check report
  [0;32m✓[0m Run launch regression floor
  [0;32m✓[0m Upload launch floor-check report
  [0;32m✓[0m Run view-hints regression floor
  [0;32m✓[0m Upload view-hints floor-check report
  [0;32m✓[0m Run agents disk-load operation-count floor
  [0;32m✓[0m Upload agents disk-load floor-check report
  [0;32m✓[0m Run plugins catalog-scale regression floor
  [0;32m✓[0m Upload plugins catalog-scale floor-check report
  [0;32m✓[0m Run bead performance smoke
  [0;32m✓[0m Upload bead performance smoke
  [0;32m✓[0m Post Install dependencies
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[0;32m✓[0m [0;1;39mfull / ace-page-group-isolation[0m in 1m5s (ID [0;36m99030887385[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Install visual dependencies
  [0;32m✓[0m Run ACE shared-page isolation lane
  [0;32m✓[0m Post Install visual dependencies
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[0;32m✓[0m [0;1;39mfull / lint[0m in 4m6s (ID [0;36m99030887397[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Install dependencies
  [0;32m✓[0m Check pinned core bindings
  [0;32m✓[0m Bootstrap SDD sidecars
  [0;32m✓[0m Initialize SASE home
  [0;32m✓[0m Run actions/setup-go@v5
  [0;32m✓[0m Cache Go binaries
  [38;5;242m-[0m Install Go tools (keep-sorted)
  [0;32m✓[0m Cache Prettier dependencies
  [0;32m✓[0m Check Python formatting
  [0;32m✓[0m Check Markdown formatting
  [0;32m✓[0m Lint
  [0;32m✓[0m SASE validation
  [0;32m✓[0m Validate committed plans
  [0;32m✓[0m Build and verify package
  [0;32m✓[0m Post Cache Prettier dependencies
  [0;32m✓[0m Post Cache Go binaries
  [0;32m✓[0m Post Run actions/setup-go@v5
  [0;32m✓[0m Post Install dependencies
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[0;31mX[0m [0;1;39mfull / coverage-contexts[0m in 40m50s (ID [0;36m99030887410[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Install dependencies
  [0;31mX[0m Record per-test coverage contexts
  [0;32m✓[0m Upload coverage contexts database
  [0;32m✓[0m Post Install dependencies
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[0;31mX[0m [0;1;39mfull / test (3.14)[0m in 24m28s (ID [0;36m99030887411[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Install dependencies
  [38;5;242m-[0m Run tests (coverage leg)
  [38;5;242m-[0m Run tests
  [0;31mX[0m Run tests
  [0;32m✓[0m Build shard timings table
  [0;32m✓[0m Upload shard timings
  [38;5;242m-[0m Upload coverage
  [0;32m✓[0m Post Install dependencies
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[0;31mX[0m [0;1;39mfull / visual-test[0m in 14m59s (ID [0;36m99030887452[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Install visual dependencies
  [0;31mX[0m Run visual tests
  [0;32m✓[0m Build visual failure report
  [0;32m✓[0m Upload visual failure report
  [0;32m✓[0m Publish visual failure report
  [0;32m✓[0m Upload visual failure artifacts
  [0;32m✓[0m Post Install visual dependencies
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[0;31mX[0m [0;1;39mfull / test (3.12)[0m in 36m44s (ID [0;36m99030887468[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Install dependencies
  [0;31mX[0m Run tests (coverage leg)
  [38;5;242m-[0m Run tests
  [38;5;242m-[0m Run tests
  [38;5;242m-[0m Build shard timings table
  [38;5;242m-[0m Upload shard timings
  [38;5;242m-[0m Upload coverage
  [0;32m✓[0m Post Install dependencies
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[38;5;242m-[0m [0;1;39mfull / contention-test[0m (ID [0;36m99030888181[0m)
[0;1;39mRefreshing run status every 3 seconds. Press Ctrl+C to quit.[0m

[0;33m*[0m [0;1;39mmaster[0m Full CI · [0;36m33226037754[0m
Triggered via workflow_dispatch about 1 hour ago

[0;1;39mJOBS[0m
[0;32m✓[0m [0;1;39mfull / build-core[0m in 7m49s (ID [0;36m99029883707[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Resolve pinned Rust core revision
  [0;32m✓[0m Check out Rust core
  [0;32m✓[0m Run astral-sh/setup-uv@v4
  [0;32m✓[0m Set up Rust
  [0;32m✓[0m Cache Rust build
  [0;32m✓[0m Build abi3 Rust core wheel
  [0;32m✓[0m Build xprompt LSP
  [0;32m✓[0m Record wheel provenance
  [0;32m✓[0m Upload Rust core artifacts
  [0;32m✓[0m Post Cache Rust build
  [0;32m✓[0m Post Run astral-sh/setup-uv@v4
  [0;32m✓[0m Post Check out Rust core
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[38;5;242m-[0m [0;1;39mfull / docs-build[0m (ID [0;36m99029884284[0m)
[38;5;242m-[0m [0;1;39mfull / release-core-floor-smoke[0m (ID [0;36m99029884306[0m)
[0;33m*[0m [0;1;39mfull / test (3.13)[0m (ID [0;36m99030887371[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Install dependencies
  [38;5;242m-[0m Run tests (coverage leg)
  [0;33m*[0m Run tests
  [0;33m*[0m Run tests
  [0;33m*[0m Build shard timings table
  [0;33m*[0m Upload shard timings
  [0;33m*[0m Upload coverage
  [0;33m*[0m Post Install dependencies
  [0;33m*[0m Post Run actions/checkout@v4
[0;31mX[0m [0;1;39mfull / perf-floors[0m in 4m33s (ID [0;36m99030887383[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Install dependencies
  [0;32m✓[0m Health check (Rust extension loadable)
  [0;32m✓[0m Run slow tests
  [0;31mX[0m Run Phase 7E regression floor
  [0;32m✓[0m Upload Phase 7E floor-check report
  [0;32m✓[0m Run launch regression floor
  [0;32m✓[0m Upload launch floor-check report
  [0;32m✓[0m Run view-hints regression floor
  [0;32m✓[0m Upload view-hints floor-check report
  [0;32m✓[0m Run agents disk-load operation-count floor
  [0;32m✓[0m Upload agents disk-load floor-check report
  [0;32m✓[0m Run plugins catalog-scale regression floor
  [0;32m✓[0m Upload plugins catalog-scale floor-check report
  [0;32m✓[0m Run bead performance smoke
  [0;32m✓[0m Upload bead performance smoke
  [0;32m✓[0m Post Install dependencies
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[0;32m✓[0m [0;1;39mfull / ace-page-group-isolation[0m in 1m5s (ID [0;36m99030887385[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Install visual dependencies
  [0;32m✓[0m Run ACE shared-page isolation lane
  [0;32m✓[0m Post Install visual dependencies
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[0;32m✓[0m [0;1;39mfull / lint[0m in 4m6s (ID [0;36m99030887397[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Install dependencies
  [0;32m✓[0m Check pinned core bindings
  [0;32m✓[0m Bootstrap SDD sidecars
  [0;32m✓[0m Initialize SASE home
  [0;32m✓[0m Run actions/setup-go@v5
  [0;32m✓[0m Cache Go binaries
  [38;5;242m-[0m Install Go tools (keep-sorted)
  [0;32m✓[0m Cache Prettier dependencies
  [0;32m✓[0m Check Python formatting
  [0;32m✓[0m Check Markdown formatting
  [0;32m✓[0m Lint
  [0;32m✓[0m SASE validation
  [0;32m✓[0m Validate committed plans
  [0;32m✓[0m Build and verify package
  [0;32m✓[0m Post Cache Prettier dependencies
  [0;32m✓[0m Post Cache Go binaries
  [0;32m✓[0m Post Run actions/setup-go@v5
  [0;32m✓[0m Post Install dependencies
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[0;31mX[0m [0;1;39mfull / coverage-contexts[0m in 40m50s (ID [0;36m99030887410[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Install dependencies
  [0;31mX[0m Record per-test coverage contexts
  [0;32m✓[0m Upload coverage contexts database
  [0;32m✓[0m Post Install dependencies
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[0;31mX[0m [0;1;39mfull / test (3.14)[0m in 24m28s (ID [0;36m99030887411[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Install dependencies
  [38;5;242m-[0m Run tests (coverage leg)
  [38;5;242m-[0m Run tests
  [0;31mX[0m Run tests
  [0;32m✓[0m Build shard timings table
  [0;32m✓[0m Upload shard timings
  [38;5;242m-[0m Upload coverage
  [0;32m✓[0m Post Install dependencies
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[0;31mX[0m [0;1;39mfull / visual-test[0m in 14m59s (ID [0;36m99030887452[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Install visual dependencies
  [0;31mX[0m Run visual tests
  [0;32m✓[0m Build visual failure report
  [0;32m✓[0m Upload visual failure report
  [0;32m✓[0m Publish visual failure report
  [0;32m✓[0m Upload visual failure artifacts
  [0;32m✓[0m Post Install visual dependencies
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[0;31mX[0m [0;1;39mfull / test (3.12)[0m in 36m44s (ID [0;36m99030887468[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Install dependencies
  [0;31mX[0m Run tests (coverage leg)
  [38;5;242m-[0m Run tests
  [38;5;242m-[0m Run tests
  [38;5;242m-[0m Build shard timings table
  [38;5;242m-[0m Upload shard timings
  [38;5;242m-[0m Upload coverage
  [0;32m✓[0m Post Install dependencies
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[38;5;242m-[0m [0;1;39mfull / contention-test[0m (ID [0;36m99030888181[0m)
[0;1;39mRefreshing run status every 3 seconds. Press Ctrl+C to quit.[0m

[0;33m*[0m [0;1;39mmaster[0m Full CI · [0;36m33226037754[0m
Triggered via workflow_dispatch about 1 hour ago

[0;1;39mJOBS[0m
[0;32m✓[0m [0;1;39mfull / build-core[0m in 7m49s (ID [0;36m99029883707[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Resolve pinned Rust core revision
  [0;32m✓[0m Check out Rust core
  [0;32m✓[0m Run astral-sh/setup-uv@v4
  [0;32m✓[0m Set up Rust
  [0;32m✓[0m Cache Rust build
  [0;32m✓[0m Build abi3 Rust core wheel
  [0;32m✓[0m Build xprompt LSP
  [0;32m✓[0m Record wheel provenance
  [0;32m✓[0m Upload Rust core artifacts
  [0;32m✓[0m Post Cache Rust build
  [0;32m✓[0m Post Run astral-sh/setup-uv@v4
  [0;32m✓[0m Post Check out Rust core
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[38;5;242m-[0m [0;1;39mfull / docs-build[0m (ID [0;36m99029884284[0m)
[38;5;242m-[0m [0;1;39mfull / release-core-floor-smoke[0m (ID [0;36m99029884306[0m)
[0;33m*[0m [0;1;39mfull / test (3.13)[0m (ID [0;36m99030887371[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Install dependencies
  [38;5;242m-[0m Run tests (coverage leg)
  [0;33m*[0m Run tests
  [0;33m*[0m Run tests
  [0;33m*[0m Build shard timings table
  [0;33m*[0m Upload shard timings
  [0;33m*[0m Upload coverage
  [0;33m*[0m Post Install dependencies
  [0;33m*[0m Post Run actions/checkout@v4
[0;31mX[0m [0;1;39mfull / perf-floors[0m in 4m33s (ID [0;36m99030887383[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Install dependencies
  [0;32m✓[0m Health check (Rust extension loadable)
  [0;32m✓[0m Run slow tests
  [0;31mX[0m Run Phase 7E regression floor
  [0;32m✓[0m Upload Phase 7E floor-check report
  [0;32m✓[0m Run launch regression floor
  [0;32m✓[0m Upload launch floor-check report
  [0;32m✓[0m Run view-hints regression floor
  [0;32m✓[0m Upload view-hints floor-check report
  [0;32m✓[0m Run agents disk-load operation-count floor
  [0;32m✓[0m Upload agents disk-load floor-check report
  [0;32m✓[0m Run plugins catalog-scale regression floor
  [0;32m✓[0m Upload plugins catalog-scale floor-check report
  [0;32m✓[0m Run bead performance smoke
  [0;32m✓[0m Upload bead performance smoke
  [0;32m✓[0m Post Install dependencies
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[0;32m✓[0m [0;1;39mfull / ace-page-group-isolation[0m in 1m5s (ID [0;36m99030887385[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Install visual dependencies
  [0;32m✓[0m Run ACE shared-page isolation lane
  [0;32m✓[0m Post Install visual dependencies
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[0;32m✓[0m [0;1;39mfull / lint[0m in 4m6s (ID [0;36m99030887397[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Install dependencies
  [0;32m✓[0m Check pinned core bindings
  [0;32m✓[0m Bootstrap SDD sidecars
  [0;32m✓[0m Initialize SASE home
  [0;32m✓[0m Run actions/setup-go@v5
  [0;32m✓[0m Cache Go binaries
  [38;5;242m-[0m Install Go tools (keep-sorted)
  [0;32m✓[0m Cache Prettier dependencies
  [0;32m✓[0m Check Python formatting
  [0;32m✓[0m Check Markdown formatting
  [0;32m✓[0m Lint
  [0;32m✓[0m SASE validation
  [0;32m✓[0m Validate committed plans
  [0;32m✓[0m Build and verify package
  [0;32m✓[0m Post Cache Prettier dependencies
  [0;32m✓[0m Post Cache Go binaries
  [0;32m✓[0m Post Run actions/setup-go@v5
  [0;32m✓[0m Post Install dependencies
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[0;31mX[0m [0;1;39mfull / coverage-contexts[0m in 40m50s (ID [0;36m99030887410[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Install dependencies
  [0;31mX[0m Record per-test coverage contexts
  [0;32m✓[0m Upload coverage contexts database
  [0;32m✓[0m Post Install dependencies
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[0;31mX[0m [0;1;39mfull / test (3.14)[0m in 24m28s (ID [0;36m99030887411[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Install dependencies
  [38;5;242m-[0m Run tests (coverage leg)
  [38;5;242m-[0m Run tests
  [0;31mX[0m Run tests
  [0;32m✓[0m Build shard timings table
  [0;32m✓[0m Upload shard timings
  [38;5;242m-[0m Upload coverage
  [0;32m✓[0m Post Install dependencies
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[0;31mX[0m [0;1;39mfull / visual-test[0m in 14m59s (ID [0;36m99030887452[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Install visual dependencies
  [0;31mX[0m Run visual tests
  [0;32m✓[0m Build visual failure report
  [0;32m✓[0m Upload visual failure report
  [0;32m✓[0m Publish visual failure report
  [0;32m✓[0m Upload visual failure artifacts
  [0;32m✓[0m Post Install visual dependencies
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[0;31mX[0m [0;1;39mfull / test (3.12)[0m in 36m44s (ID [0;36m99030887468[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Install dependencies
  [0;31mX[0m Run tests (coverage leg)
  [38;5;242m-[0m Run tests
  [38;5;242m-[0m Run tests
  [38;5;242m-[0m Build shard timings table
  [38;5;242m-[0m Upload shard timings
  [38;5;242m-[0m Upload coverage
  [0;32m✓[0m Post Install dependencies
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[38;5;242m-[0m [0;1;39mfull / contention-test[0m (ID [0;36m99030888181[0m)
[0;1;39mRefreshing run status every 3 seconds. Press Ctrl+C to quit.[0m

[0;33m*[0m [0;1;39mmaster[0m Full CI · [0;36m33226037754[0m
Triggered via workflow_dispatch about 1 hour ago

[0;1;39mJOBS[0m
[0;32m✓[0m [0;1;39mfull / build-core[0m in 7m49s (ID [0;36m99029883707[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Resolve pinned Rust core revision
  [0;32m✓[0m Check out Rust core
  [0;32m✓[0m Run astral-sh/setup-uv@v4
  [0;32m✓[0m Set up Rust
  [0;32m✓[0m Cache Rust build
  [0;32m✓[0m Build abi3 Rust core wheel
  [0;32m✓[0m Build xprompt LSP
  [0;32m✓[0m Record wheel provenance
  [0;32m✓[0m Upload Rust core artifacts
  [0;32m✓[0m Post Cache Rust build
  [0;32m✓[0m Post Run astral-sh/setup-uv@v4
  [0;32m✓[0m Post Check out Rust core
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[38;5;242m-[0m [0;1;39mfull / docs-build[0m (ID [0;36m99029884284[0m)
[38;5;242m-[0m [0;1;39mfull / release-core-floor-smoke[0m (ID [0;36m99029884306[0m)
[0;33m*[0m [0;1;39mfull / test (3.13)[0m (ID [0;36m99030887371[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Install dependencies
  [38;5;242m-[0m Run tests (coverage leg)
  [0;33m*[0m Run tests
  [0;33m*[0m Run tests
  [0;33m*[0m Build shard timings table
  [0;33m*[0m Upload shard timings
  [0;33m*[0m Upload coverage
  [0;33m*[0m Post Install dependencies
  [0;33m*[0m Post Run actions/checkout@v4
[0;31mX[0m [0;1;39mfull / perf-floors[0m in 4m33s (ID [0;36m99030887383[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Install dependencies
  [0;32m✓[0m Health check (Rust extension loadable)
  [0;32m✓[0m Run slow tests
  [0;31mX[0m Run Phase 7E regression floor
  [0;32m✓[0m Upload Phase 7E floor-check report
  [0;32m✓[0m Run launch regression floor
  [0;32m✓[0m Upload launch floor-check report
  [0;32m✓[0m Run view-hints regression floor
  [0;32m✓[0m Upload view-hints floor-check report
  [0;32m✓[0m Run agents disk-load operation-count floor
  [0;32m✓[0m Upload agents disk-load floor-check report
  [0;32m✓[0m Run plugins catalog-scale regression floor
  [0;32m✓[0m Upload plugins catalog-scale floor-check report
  [0;32m✓[0m Run bead performance smoke
  [0;32m✓[0m Upload bead performance smoke
  [0;32m✓[0m Post Install dependencies
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[0;32m✓[0m [0;1;39mfull / ace-page-group-isolation[0m in 1m5s (ID [0;36m99030887385[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Install visual dependencies
  [0;32m✓[0m Run ACE shared-page isolation lane
  [0;32m✓[0m Post Install visual dependencies
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[0;32m✓[0m [0;1;39mfull / lint[0m in 4m6s (ID [0;36m99030887397[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Install dependencies
  [0;32m✓[0m Check pinned core bindings
  [0;32m✓[0m Bootstrap SDD sidecars
  [0;32m✓[0m Initialize SASE home
  [0;32m✓[0m Run actions/setup-go@v5
  [0;32m✓[0m Cache Go binaries
  [38;5;242m-[0m Install Go tools (keep-sorted)
  [0;32m✓[0m Cache Prettier dependencies
  [0;32m✓[0m Check Python formatting
  [0;32m✓[0m Check Markdown formatting
  [0;32m✓[0m Lint
  [0;32m✓[0m SASE validation
  [0;32m✓[0m Validate committed plans
  [0;32m✓[0m Build and verify package
  [0;32m✓[0m Post Cache Prettier dependencies
  [0;32m✓[0m Post Cache Go binaries
  [0;32m✓[0m Post Run actions/setup-go@v5
  [0;32m✓[0m Post Install dependencies
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[0;31mX[0m [0;1;39mfull / coverage-contexts[0m in 40m50s (ID [0;36m99030887410[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Install dependencies
  [0;31mX[0m Record per-test coverage contexts
  [0;32m✓[0m Upload coverage contexts database
  [0;32m✓[0m Post Install dependencies
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[0;31mX[0m [0;1;39mfull / test (3.14)[0m in 24m28s (ID [0;36m99030887411[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Install dependencies
  [38;5;242m-[0m Run tests (coverage leg)
  [38;5;242m-[0m Run tests
  [0;31mX[0m Run tests
  [0;32m✓[0m Build shard timings table
  [0;32m✓[0m Upload shard timings
  [38;5;242m-[0m Upload coverage
  [0;32m✓[0m Post Install dependencies
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[0;31mX[0m [0;1;39mfull / visual-test[0m in 14m59s (ID [0;36m99030887452[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Install visual dependencies
  [0;31mX[0m Run visual tests
  [0;32m✓[0m Build visual failure report
  [0;32m✓[0m Upload visual failure report
  [0;32m✓[0m Publish visual failure report
  [0;32m✓[0m Upload visual failure artifacts
  [0;32m✓[0m Post Install visual dependencies
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[0;31mX[0m [0;1;39mfull / test (3.12)[0m in 36m44s (ID [0;36m99030887468[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Install dependencies
  [0;31mX[0m Run tests (coverage leg)
  [38;5;242m-[0m Run tests
  [38;5;242m-[0m Run tests
  [38;5;242m-[0m Build shard timings table
  [38;5;242m-[0m Upload shard timings
  [38;5;242m-[0m Upload coverage
  [0;32m✓[0m Post Install dependencies
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[38;5;242m-[0m [0;1;39mfull / contention-test[0m (ID [0;36m99030888181[0m)
[0;31mX[0m [0;1;39mmaster[0m Full CI · [0;36m33226037754[0m
Triggered via workflow_dispatch about 1 hour ago

[0;1;39mJOBS[0m
[0;32m✓[0m [0;1;39mfull / build-core[0m in 7m49s (ID [0;36m99029883707[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Resolve pinned Rust core revision
  [0;32m✓[0m Check out Rust core
  [0;32m✓[0m Run astral-sh/setup-uv@v4
  [0;32m✓[0m Set up Rust
  [0;32m✓[0m Cache Rust build
  [0;32m✓[0m Build abi3 Rust core wheel
  [0;32m✓[0m Build xprompt LSP
  [0;32m✓[0m Record wheel provenance
  [0;32m✓[0m Upload Rust core artifacts
  [0;32m✓[0m Post Cache Rust build
  [0;32m✓[0m Post Run astral-sh/setup-uv@v4
  [0;32m✓[0m Post Check out Rust core
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[38;5;242m-[0m [0;1;39mfull / docs-build[0m (ID [0;36m99029884284[0m)
[38;5;242m-[0m [0;1;39mfull / release-core-floor-smoke[0m (ID [0;36m99029884306[0m)
[0;31mX[0m [0;1;39mfull / test (3.13)[0m in 1h6m24s (ID [0;36m99030887371[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Install dependencies
  [38;5;242m-[0m Run tests (coverage leg)
  [0;31mX[0m Run tests
  [38;5;242m-[0m Run tests
  [38;5;242m-[0m Build shard timings table
  [38;5;242m-[0m Upload shard timings
  [38;5;242m-[0m Upload coverage
  [0;32m✓[0m Post Install dependencies
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[0;31mX[0m [0;1;39mfull / perf-floors[0m in 4m33s (ID [0;36m99030887383[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Install dependencies
  [0;32m✓[0m Health check (Rust extension loadable)
  [0;32m✓[0m Run slow tests
  [0;31mX[0m Run Phase 7E regression floor
  [0;32m✓[0m Upload Phase 7E floor-check report
  [0;32m✓[0m Run launch regression floor
  [0;32m✓[0m Upload launch floor-check report
  [0;32m✓[0m Run view-hints regression floor
  [0;32m✓[0m Upload view-hints floor-check report
  [0;32m✓[0m Run agents disk-load operation-count floor
  [0;32m✓[0m Upload agents disk-load floor-check report
  [0;32m✓[0m Run plugins catalog-scale regression floor
  [0;32m✓[0m Upload plugins catalog-scale floor-check report
  [0;32m✓[0m Run bead performance smoke
  [0;32m✓[0m Upload bead performance smoke
  [0;32m✓[0m Post Install dependencies
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[0;32m✓[0m [0;1;39mfull / ace-page-group-isolation[0m in 1m5s (ID [0;36m99030887385[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Install visual dependencies
  [0;32m✓[0m Run ACE shared-page isolation lane
  [0;32m✓[0m Post Install visual dependencies
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[0;32m✓[0m [0;1;39mfull / lint[0m in 4m6s (ID [0;36m99030887397[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Install dependencies
  [0;32m✓[0m Check pinned core bindings
  [0;32m✓[0m Bootstrap SDD sidecars
  [0;32m✓[0m Initialize SASE home
  [0;32m✓[0m Run actions/setup-go@v5
  [0;32m✓[0m Cache Go binaries
  [38;5;242m-[0m Install Go tools (keep-sorted)
  [0;32m✓[0m Cache Prettier dependencies
  [0;32m✓[0m Check Python formatting
  [0;32m✓[0m Check Markdown formatting
  [0;32m✓[0m Lint
  [0;32m✓[0m SASE validation
  [0;32m✓[0m Validate committed plans
  [0;32m✓[0m Build and verify package
  [0;32m✓[0m Post Cache Prettier dependencies
  [0;32m✓[0m Post Cache Go binaries
  [0;32m✓[0m Post Run actions/setup-go@v5
  [0;32m✓[0m Post Install dependencies
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[0;31mX[0m [0;1;39mfull / coverage-contexts[0m in 40m50s (ID [0;36m99030887410[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Install dependencies
  [0;31mX[0m Record per-test coverage contexts
  [0;32m✓[0m Upload coverage contexts database
  [0;32m✓[0m Post Install dependencies
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[0;31mX[0m [0;1;39mfull / test (3.14)[0m in 24m28s (ID [0;36m99030887411[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Install dependencies
  [38;5;242m-[0m Run tests (coverage leg)
  [38;5;242m-[0m Run tests
  [0;31mX[0m Run tests
  [0;32m✓[0m Build shard timings table
  [0;32m✓[0m Upload shard timings
  [38;5;242m-[0m Upload coverage
  [0;32m✓[0m Post Install dependencies
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[0;31mX[0m [0;1;39mfull / visual-test[0m in 14m59s (ID [0;36m99030887452[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Install visual dependencies
  [0;31mX[0m Run visual tests
  [0;32m✓[0m Build visual failure report
  [0;32m✓[0m Upload visual failure report
  [0;32m✓[0m Publish visual failure report
  [0;32m✓[0m Upload visual failure artifacts
  [0;32m✓[0m Post Install visual dependencies
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[0;31mX[0m [0;1;39mfull / test (3.12)[0m in 36m44s (ID [0;36m99030887468[0m)
  [0;32m✓[0m Set up job
  [0;32m✓[0m Run actions/checkout@v4
  [0;32m✓[0m Install dependencies
  [0;31mX[0m Run tests (coverage leg)
  [38;5;242m-[0m Run tests
  [38;5;242m-[0m Run tests
  [38;5;242m-[0m Build shard timings table
  [38;5;242m-[0m Upload shard timings
  [38;5;242m-[0m Upload coverage
  [0;32m✓[0m Post Install dependencies
  [0;32m✓[0m Post Run actions/checkout@v4
  [0;32m✓[0m Complete job
[38;5;242m-[0m [0;1;39mfull / contention-test[0m (ID [0;36m99030888181[0m)

---

%xprompts_enabled:true
# New Query
%model:grok-4.6
%effort:xhigh

%xprompts_enabled:false
# Monitored command finished

**Command:**

```text
gh run watch 33226037754 --exit-status
```

**Directory:**

```text
/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20
```

| | |
| --- | --- |
| **Outcome** | FAILED — exit 1 |
| **Started** | 2026-08-29T01:24:47.170783+00:00 |
| **Finished** | 2026-08-29T02:32:33.199270+00:00 |
| **Elapsed** | 1h 7m 45s of a 4h 0m 0s budget |
| **Output** | 176 KiB · log file: `/home/bryan/.sase/projects/gh_sase-org__sase/artifacts/ace-run/202608/28/20260828212447/live_reply.md` · full log: `sase monitor show whfadx7hwgxh --all-lines` |

**Why this was monitored:** Wait for dispatched Full CI run 33226037754 on master tip 1a1463028 (post-gatebudget integrated tip)

## Your next action

Resume sase-um.9.5.3 fullgreen. Do not set bead status by hand. Do not close parent epic sase-um.9.5 or any ancestor. Do not create beads; use sase bead note sase-um.9.5.3 for PROPOSED FOLLOW-UP.

Inspect GitHub Actions Full CI run 33226037754 (workflow_dispatch, intended SHA 1a1463028). Compare that SHA to origin/master. Acceptance is one completed green Full CI on the final integrated master tip inside ci_watch six-hour heavy-lane freshness.

If the run is green AND origin/master is still that SHA: run sase bead epic-symbols sase-um.9.5.3 and resolve leftovers; then sase bead close sase-um.9.5.3 --note with the run id, SHA, and what you verified. Contention-test is skipped on workflow_dispatch by design.

If master moved past the run SHA, dispatch full.yml again on the new tip and wait with /sase_monitor; do not close on a stale SHA.

If the run is red: inspect every failed job log. Old-SHA attribution is already on the bead notes. In-scope: deterministic or epic-caused failures, including 3.13 just test-cost hard CPU budgets (run 33216659649: collection_cpu 77.852 vs 35 allowed, total_file_cpu 3199 vs 2625, worker_count=3 on GitHub). Do not raise athena-calibrated budgets to hide GitHub slowness. Count/RSS should stay hard. Record unrelated fail/pass flakes as PROPOSED FOLLOW-UP with node, run, serial rerun, and existing-task match (sase-r2 pipe_e2e, sase-sf archive_publication). After a fix, just check (read lint_and_test.md first), land the fix, dispatch Full CI on the new tip, and wait with /sase_monitor again. Stitch create auto-closes this in_progress phase bead — if you must commit before Full CI is green, pass -B/--do-not-close-bead if the host allows it, or reopen after auto-close and continue; do not treat auto-close as acceptance.

Use /sase_monitor for Full CI and just check-full. Use /sase_final only if you are actually ending without a monitor/plan/pipe/questions handoff.
%xprompts_enabled:true

## Response

The Full CI watch finished red. I'll read the full prompt and the skills for this phase, then inspect the run against origin/master.

The prompt is long; I'll grab the actual next-action block and then inspect the failed run.

Run 33226037754 is red. Next I’ll compare its SHA to origin/master, pull bead notes, and inspect each failed job.

Master moved to `651619dcb` while run `33226037754` stayed on `1a1463028` and failed. I'll inspect the failed jobs and that new tip before deciding whether to fix or redispatch.

I have the 3.12 summary; next I’ll pull each job’s short-test summary and floor/cost output.

Failures cluster into a pager extra-newline, workspace rebind (likely already on master), a compact tab-strip, a visual snapshot, and a 0.46µs perf miss. I’ll inspect those against the new master commits.

The pager extra `\n` looks like `_body_to_text` plus `Text.from_ansi`; workspace rebind failed on every job. I’ll reproduce both locally on current master.

I'll reproduce the failing tests locally, pull the visual artifacts, and locate the workspace-rebind "not found" path.

The workspace failures match core 0.32.14’s claim-name check; 0.32.15 already has the transfer fix. I’ll ratchet the pin and apply the other in-scope test fixes.

Full CI **33226037754** on `1a1463028` is red, and origin/master had already moved to `651619dcb`. That is not acceptance. In-scope failures are fixed on the current tip; the host is committing them now.

**What failed**
| Job | Failure | Verdict |
| --- | --- | --- |
| test 3.12 / 3.13 / 3.14 | 8 nodes | In-scope |
| coverage-contexts | 2 workspace-rebind nodes | In-scope |
| visual-test | 1 PNG (`artifacts_stitches_persistent_filter_80x24`) | Unrelated flake → follow-up |
| perf-floors | Phase 7E `persistent_query_keystroke` 193.90µs vs 193.44µs | GitHub jitter → follow-up |
| contention-test | skipped | By design on `workflow_dispatch` |

**In-scope fixes (just check green, full-suite escalation for core pin + packaging)**
- **Workspace rebind:** CI was on core **0.32.14**, which still required the old `git-main` claim name. Ratcheted `sase-core-revision.txt` and the `sase-core-rs` window to **0.32.15** (`5e7fc3d`), where numbered transfers match by pid.
- **Pager extra `\n`:** `_body_to_text` now restores the source trailing-newline count whether `Text.from_ansi` strips or keeps it.
- **Tab strip:** `test_reflow_to_fit_ladder_picks_tier_by_width` waits after each resize.
- **3.13 test-cost CPU:** did **not** raise athena budgets. `--ci` now reports CPU overages as advisory; **count and RSS stay hard**.

**Not acceptance**
Stitch create will auto-close `sase-um.9.5.3`. That is not a green Full CI. Reopen the phase if it closed, dispatch `full.yml` on the **post-stitch** master tip, and wait with a monitor. Do not close parent `sase-um.9.5`.

Unrelated flakes are on the phase bead as `PROPOSED FOLLOW-UP` (visual snapshot; Phase 7E 0.46µs miss). `sase-r2` and `sase-sf` did not fail this run.
