# Chat History - ace-run (research.5g.gem)

- **TIMESTAMP:** 2026-10-29 00:50:44 EDT
- **MODEL:** agy/gemini-3.8-flash-high
- **AGENT:** research.5g.gem
- **PROMPT:** `~/.sase/multi_prompts/202610/gh_sase_org__sase-multiprompt-261029_002947.md`

## Prompt

%id(gem, clan=research.5g)
%m:agy/gemini-3.8-flash-high %q(1.5x, w=0.25)
#gh:gh_sase-org__sase 
You are researcher gem in a 5-researcher swarm.
The other researchers, `research.5g.cdx`, `research.5g.cld`, `research.5g.grk`, `research.5g.mus`, are independently investigating the same request and will write their own self-named reports ending in `__cdx.md` and `__cld.md` and `__grk.md` and `__mus.md`. Your report will end in `__gem.md`.

Conduct your research independently and form your own conclusions. Do NOT attempt to
locate, open, read, or otherwise consult the other researcher's report from this swarm,
even if it becomes available before you finish. Do not obtain that peer's findings
indirectly through its chat transcript, summaries, or requests to the peer. You may
independently use the same external sources, shared input material, and unrelated prior
research. You may check filenames or file existence to avoid overwriting your own
output, but do not inspect the peer's report contents. If you encounter its filename,
leave the report alone. The lead researcher will read every report and synthesize their
findings after you have all finished.

The sase-core repo keeps failing CI. I'm wondering if there is a way we can fix this
with a post-commit hook or something like that to prevent these same types of failures
from continuing to recur. Can you do some research to help me understand the nature of
these failures? End your analysis with a recommended solution. 
Write this research to a new markdown file under the $(sase repo path research --ensure)/$(date +%Y%m)/ directory.
Choose a descriptive filename stem yourself, but the filename MUST end with the
`__gem` suffix, i.e. `<stem>__gem.md` (double underscore before the
suffix). Create the report without overwrite: if the exact file already exists, pick a
different stem instead of replacing it.


After the write succeeds, register the report as a durable snapshot:

sase artifact create -p "<absolute-report-path>" -l "research:<repo-relative-report-path>"

Use the report's actual absolute path and its path relative to the research repo root
(for example
`research:202609/topic__a.md`),
including any subdirectory the steps above put it in. Do not derive the label from
the current month, the clock, or a guessed name.
Do not pass `--move`; the source stays in the research repo for later reorganization. If
registration itself fails, report that failure — do not report the research task as
fully complete.

## Response

# Independent Research Report: Analysis of `sase-core` CI Failures and Git Hook Viability

**Researcher:** `research.5g.gem`  
**Report Path:** [`/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_25/sase/repos/research/202610/sase_core_ci_failures_analysis_and_hook_viability__gem.md`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_25/sase/repos/research/202610/sase_core_ci_failures_analysis_and_hook_viability__gem.md)  
**Registered Artifact:** `ref: file:explicit:94c780e24aec1c40ca1dd7aa` (`research:202610/sase_core_ci_failures_analysis_and_hook_viability__gem.md`)

---

## 1. Executive Summary & Nature of the Failures

Across an exhaustive audit of the 22 recent CI failures in [`sase-org/sase-core`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_25/sase/repos/linked/sase-core) spanning pushes to `master` and automated `release-plz` PRs:

1. **100% of the failures are runtime test flakes under CI load.**
   - Formatting checks (`cargo fmt --all -- --check`), dependency feature checks (`cargo hakari`), and clippy linting (`cargo clippy --workspace --all-targets -- -D warnings`) have **never failed** in these runs.
   - All failures occur exclusively in `cargo test --workspace`.
2. **Every failure traces to exactly two tests:**
   - **[`tool_run::store::connection::tests::wal_mode_probe_consumes_conversion_budget`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_25/sase/repos/linked/sase-core/crates/sase_core/src/tool_run/store/connection.rs#L875)** (16 runs): Failed exclusively on `macos-latest` runners due to a brittle wall-clock assertion:
     ```rust
     assert!(elapsed < Duration::from_millis(425), "WAL setup renewed an exhausted budget: {elapsed:?}");
     ```
     Under heavy multi-threaded test execution on virtualized GitHub Actions macOS runners, scheduler context switching and thread wake latencies easily exceeded the 175 ms slack allowance (reaching 1.173 s in run `40794754688`).
   - **[`bead_read_model_parity::concurrent_readers_see_consistent_snapshots`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_25/sase/repos/linked/sase-core/crates/sase_core/tests/integration/bead_read_model_parity.rs#L869)** (7 runs, including the two most recent runs on `master` at commits `0fd85e4a` and `cd62c83d`):
     Failed with:
     ```
     panicked at crates/sase_core/tests/integration/bead_read_model_parity.rs:934:5:
     cache is stale: the next read rebuilds
     ```
     When 4 concurrent reader threads query the bead store during 10 note appends, transient SQLite lock contention causes a reader to encounter `Fault::Cache`. In [`store.rs`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_25/sase/repos/linked/sase-core/crates/sase_core/src/bead/read_model/store.rs#L1247), this triggers [`mark_failed_rebuild`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_25/sase/repos/linked/sase-core/crates/sase_core/src/bead/read_model/store.rs#L159), which arms a **10-minute process-wide rebuild backoff** (`FAILED_REBUILD_BACKOFF = 10 * 60s`). When the reader threads finish and `assert_parity` runs, `read_store_issues` hits this active backoff and silently falls back to replay from disk without rebuilding the cache file. Line 933 then runs [`read_model_verify_cache`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_25/sase/repos/linked/sase-core/crates/sase_core/src/bead/read_model/store.rs#L440), a read-only probe that finds the un-rebuilt SQLite cache stale and panics.

---

## 2. Why a Post-Commit (or Pre-Commit) Hook Cannot Solve This

A git hook is the wrong mechanism for this problem:

1. **`post-commit` hooks cannot block commits**: By git design, `post-commit` runs *after* the commit object has already been created. Its exit status is ignored by git; it cannot reject or abort commits.
2. **Environment & load divergence**: These tests pass locally in isolation and under ordinary desktop conditions. They fail almost exclusively under the thread saturation and virtualized hypervisor contention of GitHub Actions CI runners. A local hook running `cargo test` will pass and allow the commit/push anyway.
3. **Severe developer friction**: `sase-core` compiles PyO3 C-extensions and runs 5,500+ tests. `just check` takes 5 to 10 minutes. Running this suite on every local commit or push would destroy development velocity.
4. **SASE architecture incompatibility**: SASE agents run in ephemeral numbered workspace clones (`sase_<N>`) and commit through host-owned finalizers (`builtin@commit` via `sase stitch create`), bypassing client-side git hooks.

---

## 3. Recommended Solution

### 1. Fix the Read-Model Rebuild Backoff and Parity Test
- **Distinguish transient contention from corruption**: In [`crates/sase_core/src/bead/read_model/store.rs`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_25/sase/repos/linked/sase-core/crates/sase_core/src/bead/read_model/store.rs#L1244), transient SQLite `Busy` or `Locked` errors encountered during multi-threaded reads should not arm the 10-minute `mark_failed_rebuild` lockout.
- **Ensure test isolation**: In [`bead_read_model_parity.rs`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_25/sase/repos/linked/sase-core/crates/sase_core/tests/integration/bead_read_model_parity.rs#L930), clear any transient process-level rebuild backoff and perform an explicit synchronous rebuild (`cached_store_snapshot_at(..., true)`) after joining reader threads before asserting cache freshness with `read_model_verify_cache`.

### 2. Eliminate Wall-Clock Bounds in Timeout Tests
- Follow the pattern introduced in commit `0fd85e4a` (`busy_handler_stops_after_a_scheduler_oversleep`) by using mocked clocks or virtualized time generators instead of asserting tight wall-clock thresholds (`elapsed < 425ms`) under shared CI runners.

### 3. Use SASE Prepared Verification Monitors Instead of Client Hooks
- For automated gating prior to landing, use SASE's prepared completion workflow (`sase final prepare` + `sase monitor start -p verify ...`), which monitors `just check` asynchronously and authoritatively before committing to `master`.

---

The full research report has been saved to [`/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_25/sase/repos/research/202610/sase_core_ci_failures_analysis_and_hook_viability__gem.md`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_25/sase/repos/research/202610/sase_core_ci_failures_analysis_and_hook_viability__gem.md) and registered as artifact `research:202610/sase_core_ci_failures_analysis_and_hook_viability__gem.md`.
