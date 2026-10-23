# Chat History - ace-run (research.2a.gem)

- **TIMESTAMP:** 2026-10-23 12:11:10 EDT
- **MODEL:** agy/gemini-3.8-flash-high
- **AGENT:** research.2a.gem
- **PROMPT:** `~/.sase/multi_prompts/202610/gh_sase_org__sase-multiprompt-261023_115726.md`

## Prompt

%id(gem, clan=research.2a)
%m:agy/gemini-3.8-flash-high %q(1.5x, w=0.25)
#gh:gh_sase-org__sase 
You are researcher gem in a 5-researcher swarm.
The other researchers, `research.2a.cdx`, `research.2a.cld`, `research.2a.grk`, `research.2a.mus`, are independently investigating the same request and will write their own self-named reports ending in `__cdx.md` and `__cld.md` and `__grk.md` and `__mus.md`. Your report will end in `__gem.md`.

Conduct your research independently and form your own conclusions. Do NOT attempt to
locate, open, read, or otherwise consult the other researcher's report from this swarm,
even if it becomes available before you finish. Do not obtain that peer's findings
indirectly through its chat transcript, summaries, or requests to the peer. You may
independently use the same external sources, shared input material, and unrelated prior
research. You may check filenames or file existence to avoid overwriting your own
output, but do not inspect the peer's report contents. If you encounter its filename,
leave the report alone. The lead researcher will read every report and synthesize their
findings after you have all finished.

I'm thinking about moving forward with the E3 epic described by the
pypi_release_reliability_design_and_work_split.md file in the research sidecar repo. Can
you do some research with the goal of making sure we are ready for this epic, describing
the work that has been done so far (e.g. E1 and E2) and what developer-facing behavior
has been changed by that work, and starting the design for the E3 epic? 
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

### Independent Research Report: Readiness and Design for Epic E3 (Trustworthy Signal)

**Researcher:** `gem`  
**Artifact Ref:** `file:explicit:cc08dab4f70e3125869fd5ab`  
**Artifact Label:** `research:202610/pypi_release_reliability_e3_trustworthy_signal_readiness_and_design__gem.md`  
**Source Path:** `/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/sase/repos/research/202610/pypi_release_reliability_e3_trustworthy_signal_readiness_and_design__gem.md`  

---

### 1. Executive Summary & Readiness Verdict

**Verdict: We are fully ready to move forward with Epic E3 ("Trustworthy Signal") immediately.**

Not only are there no blockers preventing Epic E3 from starting, but launching E3 is **urgent**:
- **E1 is complete and closed:** Epic `sase-1my` successfully landed all phases (protected retention, dual-OS canary, plugin release dependency floors, storage headroom tracking, and recovery runbooks).
- **E2 core architecture is landed:** Epic `sase-1n6` built the tag-dispatched `release.yml`, sealed candidate manifests, exact `sase-core-rs==X.Y.Z` pinning, clean headless Linux/macOS execution, and the stateless release steward (`release_watch` / `release_steward_decide`). Live rehearsals and qualification validation are active, alongside focused interim epic `sase-1nn` shipping `v0.18.1`.
- **Downstream work is waiting on E3:** The release candidate qualification lane in `release.yml` was designed to inherit the shared bounded rerun helper from E3.1, and Epic E4 (Revert-First Post-Submit) strictly depends on E3.1 and E3.5 (culprit attribution) before it can begin.
- **The developer tax remains high:** Today's Master Gate (8 fast shards, 20-minute ceiling) and scheduled Full CI (every 2 hours) have zero node-level retry. A single flake fails an entire shard or workflow, driving multi-hour whole-workflow retries.

---

### 2. Work Done So Far & Developer-Facing Impacts

#### Track 0: Shipping SASE 0.18.0 (`sase-1mk`)
- **Delivered:** SASE `0.18.0` was published to PyPI on 2026-10-19, ending a 50-day release freeze.
- **Developer Impact:** Resolved the issue where external resolvers silently backtracked to February's `0.1.0` release. Modern package installations (`uv tool install sase`) succeed cleanly.

#### Epic E1: Installable Family (`sase-1my`)
- **Delivered:**
  1. *Demand-Driven Retention (`sase-core`):* Replaced consumer-blind "newest 30" retention with a protected set that preserves the exact core versions and range windows needed by all supported SASE releases ($N \ge 10$) and requires complete platform file sets.
  2. *Dual-OS Family Canary (`install-smoke.yml`):* Runs daily on Ubuntu and macOS, verifying clean installation of `sase` and all plugins (`sase-github`, `sase-telegram`, `sase-research-artifacts`) and ensuring resolvers choose the newest version rather than older fallbacks.
  3. *Sibling Dependency Floor Checks (`release-dependency-floor.yml`):* Validates plugin release PRs to ensure sibling floors have actually landed on PyPI before a plugin can release.
  4. *Storage Headroom & Emergency Runbooks:* Added 30-day runway alerts against PyPI's 10 GiB cap and documented human-gated yanking and backfill procedures in `docs/contribute/release-safety.md`.
- **Developer Impact:**
  - Plugin authors cannot merge release PRs that name unreleased SASE dependencies.
  - Older SASE installations will never have their core dependencies pulled from PyPI.
  - Cross-plugin entry-point breaks or macOS dynamic link errors are detected within 24 hours.

#### Epic E2: Exact-Candidate Release Train and Steward (`sase-1n6`)
- **Delivered:**
  1. *Build-Once Tag Workflow (`release.yml`):* Releases are built once at the tag ref (`v*`), sealing an immutable candidate manifest with cryptographic digests of all distribution files and the exact `sase-core-rs` wheels, stored as draft GitHub release assets.
  2. *Exact Core Pinning (`ratchet_core_pin.py`):* Replaced loose range windows with exact `sase-core-rs==X.Y.Z` pins, accompanied by local dev-environment adapters so development checkouts tolerate exact pins cleanly.
  3. *Multi-Platform Exercise:* Clean Linux and macOS runners install the stashed wheel and sdist, running headless TUI checks, `fakey` agent turns, N−1 upgrades, and `pip check`.
  4. *Qualification Against Published Core:* Added `ref` and `core-source: published` to `ci.yml`, qualifying candidate artifacts against published PyPI wheels.
  5. *Stateless Release Steward:* Replaced stateful pollers with a pure reconciler (`tools/release_watch.py` calling Rust `release_steward_decide`) that emits typed blocking reasons (`CORE_LAG`, `QUALIFY_RED`, `INSTALL_BROKEN`) and escalates after 24 hours.
  6. *Release Metrics (`tools/release_metrics.py`):* Measures release-green per SHA, lead time from landing to PyPI, and core-lag hours.
- **Developer Impact:**
  - Releases are guaranteed deterministic pairs (what is qualified against published core is identically what ships to PyPI).
  - Failed candidates burn patch versions cheaply (leaving an abandoned draft release) rather than contaminating PyPI or wedging merge queues.
  - Reusable CI (`ci.yml`) can be invoked against explicit refs and with published core binaries.

---

### 3. Architecture & Design for Epic E3: Trustworthy Signal

Epic E3 establishes Promise 3 ("Landable") by delivering bounded reruns, escalating quarantine, drift canaries, and automated culprit attribution.

#### Core Principles & Invariants
1. **A Single Red Never Costs a Day:** A single flaky test must not fail a 20-minute Master Gate shard or a 90-minute Full CI run.
2. **An Isolated Pass is Diagnostic, Not Exoneration:** Flakes that pass on retry emit a `FLAKY:` trailer and are tracked; repeat signatures escalate. Safety-critical tests get no retries.
3. **Escalating Quarantine Never Blocks Admission:** Expired quarantine entries fail hygiene audits and escalate bead priority, but never block gate admission (eliminating the Google report's time-bomb flaw).
4. **Attribution is Deterministic:** Because Master Gate runs once per SHA and is never cancelled, the first red commit with a green parent is the prime suspect, verified by $k$-of-$k$ confirmation.
5. **Time Injection Over System Clock Manipulation:** Drift canaries virtualize test time (+30 days) in-process rather than shifting runner system clocks, preserving TLS, OIDC, and caching.
6. **Decision Record:** Add `decisions:ci-trustworthy-signal` to SASE memory.

#### Phase Breakdown (Size M–L)

- **Phase E3.1: Shared Bounded-Rerun Helper (Size: M)**
  - Implemented in `tools/run_pytest` and `tests/_bounded_rerun_plugin.py`.
  - Rules: Rerun only if $\le 3$ test nodes fail, exactly 1 retry per node.
  - Refuses retries on collection errors, harness errors, zero-test runs, or `@pytest.mark.no_rerun` tests.
  - On pass, logs `FLAKY: <node_id>`, exits 0, and appends to the flake record store.
  - Inherited uniformly by `just test`, `master-gate.yml`, `ci.yml`, and `release.yml`.

- **Phase E3.2: Escalating Quarantine Engine (Size: M)**
  - Schema-validated manifest `.github/quarantine.json` requiring `node_id`, active SASE `bead`, `owner`, and `expires_at`.
  - Quarantined tests run non-blocking (`xfail(strict=False)`).
  - When expired, fails non-blocking hygiene check `just check-quarantine-hygiene` and bumps bead priority; gate admission remains green.

- **Phase E3.3: CI Parity & Fast-Fail Hardening (Size: S)**
  - Enforce Python 3.12 parity across all actions and runners.
  - Fail fast ($< 5\text{s}$) on core revision or binding mismatches before executing dependency builds.
  - Eliminate blanket `if: always()` in workflows, restricting it strictly to diagnostic reporting and artifact uploads.

- **Phase E3.4: Drift Canaries with Injected Time (Size: M)**
  - Scheduled nightly workflow `drift-canary.yml`.
  - Virtualizes $+30$ days into test environments via `SASE_TEST_TIME_OFFSET_DAYS=30`.
  - Detects time bombs and token rollover issues before they reach production.

- **Phase E3.5: Culprit Attribution & `culprit-check.yml` (Size: M)**
  - Automated suspect identification on `master` failures.
  - Dispatchable workflow `culprit-check.yml` running $k=3$ confirmation on suspect $C_n$ and parent $C_{n-1}$.
  - Emits typed verdicts: `culprit=<sha>`, `recovered`, `drift`, or `unknown`.
  - Performs release-lane bisection between candidate SHA and the release-green bookmark.

- **Phase E3.6: False-Red Metrics & Digest (Size: S)**
  - Automated weekly digest tracking false-red rate (target: $< 3\%$), mean red minutes per day, and quarantine debt.

- **Phase E3.7: Visual Promotion Study & Decision Record (Size: S)**
  - Confirms policy keeping Textual visual snapshots off the blocking Master Gate path.
  - Authors and commits `decisions:ci-trustworthy-signal`.

---

### 4. Durable Registration & Finalizer Confirmation

The full research report has been authored and registered in SASE artifact storage:
- **Registered Path:** `/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/sase/repos/research/202610/pypi_release_reliability_e3_trustworthy_signal_readiness_and_design__gem.md`
- **Artifact Ref:** `file:explicit:cc08dab4f70e3125869fd5ab` (`research:202610/pypi_release_reliability_e3_trustworthy_signal_readiness_and_design__gem.md`)
- **Finalizer Declaration:** Submitted and accepted (`commit` payload for `sdd:research`).
