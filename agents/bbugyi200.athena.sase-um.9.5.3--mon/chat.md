# Chat History - ace-run (sase-um.9.5.3--mon)

- **TIMESTAMP:** 2026-08-28 22:32:33 EDT
- **MODEL:** grok/grok-4.6
- **AGENT:** sase-um.9.5.3--mon

## Prompt

sase monitor start --command 'gh run watch 33226037754 --exit-status' --reason 'Wait for dispatched Full CI run 33226037754 on master tip 1a1463028 (post-gatebudget integrated tip)'

## Response

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

