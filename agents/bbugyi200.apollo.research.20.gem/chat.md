# Chat History - ace-run (research.20.gem)

- **TIMESTAMP:** 2026-10-18 10:04:11 EDT
- **MODEL:** agy/gemini-3.8-flash-high
- **AGENT:** research.20.gem
- **PROMPT:** `~/.sase/multi_prompts/202610/gh_sase_org__sase-multiprompt-261018_095054.md`

## Prompt

%id(gem, clan=research.20)
%m:agy/gemini-3.8-flash-high %q(1.5x, w=0.25)
#gh:gh_sase-org__sase 
You are researcher gem in a 4-researcher swarm.
The other researchers, `research.20.cdx`, `research.20.cld`, `research.20.grk`, are independently investigating the same request and will write their own self-named reports ending in `__cdx.md` and `__cld.md` and `__grk.md`. Your report will end in `__gem.md`.

Conduct your research independently and form your own conclusions. Do NOT attempt to
locate, open, read, or otherwise consult the other researcher's report from this swarm,
even if it becomes available before you finish. Do not obtain that peer's findings
indirectly through its chat transcript, summaries, or requests to the peer. You may
independently use the same external sources, shared input material, and unrelated prior
research. You may check filenames or file existence to avoid overwriting your own
output, but do not inspect the peer's report contents. If you encounter its filename,
leave the report alone. The lead researcher will read every report and synthesize their
findings after you have all finished.

I've been thinking about making some big changes to sase's release process with the goal
of making them much more reliable. See the
merge_queue_fenced_master_and_exact_sha_releases.md and
merge_queue_fence_reassessment_and_epic_split.md files in the research sidecar repo for
context.

I used to work at Google where our release process was pretty good. How does our planned
release process compare to Google's release process? Is there any inspiration that sase
can take from this release process? End your analysis with a ranked list of changes that
you think I should consider making to this planned change in our release process. If your
report does not indicate that any changes need to be made, that is fine. 
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

# Google Release Engineering vs. SASE Planned Release Process: Comparative Analysis & Recommendations

**Research Report:** [`google_release_engineering_lessons_for_sase__gem.md`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/sase/repos/research/202610/google_release_engineering_lessons_for_sase__gem.md)  
**Registered Artifact:** `research:202610/google_release_engineering_lessons_for_sase__gem.md` (`file:explicit:4feb532e57b3a56c6496af68`)

---

## 1. Executive Summary & Core Comparison

SASE's planned release overhaul—split across **Epic A** (exact-candidate releases), **Epic B** (trustworthy gate), **Epic C** (queue-aware landing feature), and **Epic D** (production cutover to a GitHub native merge queue on `master`)—adopts several foundational principles pioneered by Google Release Engineering:
1. **Single-Build Binary Provenance:** Build once from an exact commit, hash the artifacts, qualify those exact files, and upload only what was qualified.
2. **Two-Speed Verification:** Decouple fast, attributable pre-merge gating from heavy, slow integration suites.
3. **Speculative Integration Gating:** Server-enforced verification of integrated change sets before landing on `master`.

However, comparing SASE's planned architecture to Google's release engineering model (*Google SRE Book*, Chapter 8; *Software Engineering at Google*, Chapters 23 & 24) reveals **two critical architectural gaps**:
1. **Releasing Directly from Trunk (HEAD) vs. Isolated Release Baselines:** SASE plans to execute release-please directly on `master`. If a release candidate fails qualification (e.g., on Python 3.14 or packaging smoke), SASE must "fix forward" on trunk while ~43 autonomous agent landings continue to pour into `master` every day. At Google, major systems **never release directly from the tip of trunk**; they branch an isolated release branch from a Known-Good / Gate-Green baseline, allowing active trunk development to continue uninterrupted while stabilizing the candidate via targeted cherry-picks.
2. **Post-Publish vs. Pre-Flight Canarying:** SASE's planned install canary (Phase A6) runs *after* public upload to PyPI. Because PyPI packages are immutable, discovering a broken C-extension or missing runtime dependency (such as the `sase-core-rs` retention deletion that caused `pip install sase` to resolve to `0.1.0`) *after* publication burns the release version and exposes users. Google never pushes to production without automated pre-flight canary verification in an isolated staging ring.

---

## 2. Comparative Matrix: SASE Planned Process vs. Google

| Dimension | Google Release Engineering | SASE Planned Process (Epics A–D) | Verdict & Alignment |
| :--- | :--- | :--- | :--- |
| **Branching & Trunk Strategy** | Trunk-based development with **isolated release branches** cut from a green baseline (LKG); stabilization via cherry-picks; trunk velocity never stalled. | Trunk-based development; release-please PRs merged **directly on `master`**; fix-forward on trunk. | **Major Divergence:** SASE release qualification competes with 43+ agent landings/day. A broken release candidate creates trunk contention. |
| **Build & Binary Provenance** | Hermetic builds (Blaze); build once, record hashes, test exact binaries, deploy exact binaries. | Build once from exact release SHA; record SHA-256 digests; qualify exact wheel/sdist; upload exact files (Epic A). | **Strong Alignment:** SASE's Epic A directly mirrors Google's exact-binary provenance discipline. |
| **Admission Gate (Presubmit)** | TAP Presubmit: fast, affected-only, strictly hermetic Small/Medium tests; zero approvals required for automated bot landings. | GitHub Native Merge Queue: speculative rebase builds; fast Master Gate (~13 min p50); zero human approvals. | **Strong Alignment:** Server-enforced speculative integration checking; zero-approval autonomous landing. |
| **Heavy / Slow Verification** | Continuous postsubmit runs; Large/system tests off the critical presubmit path; Build Cop reverts. | Heavy lane (`ci.yml`: visual tests, multi-Python 3.13/3.14, perf floors, ~30–76 min) decoupled from merge queue; nightly + candidate qualification. | **Strong Alignment:** Adopts Google's two-speed separation to prevent merge queue starvation. |
| **Flake Management** | Automated flake scoring/tracking; flaky tests automatically demoted from presubmit blockers. | Bounded serial rerun ($\le 3$ nodes); 14-day expiring quarantine list (fails lint on expiration) (Epic B). | **Partial Gap:** SASE's expiring quarantine punishes unrelated agent PRs with synthetic lint failures instead of de-escalating the test. |
| **Rollout & Canarying** | Automated Canary Analysis (ACA) across Dogfood $\to$ Canary (1%) $\to$ Staged Prod; automated rollback before 100% rollout. | Direct upload to public PyPI; daily clean-environment "install canary" runs **after publication** (Epic A6). | **Critical Gap:** SASE discovers package installation or runtime dependency breakage *after* the immutable PyPI release is live. |
| **Cross-Repo Dependencies** | Monorepo (Piper) ensures atomic cross-library updates; external dependencies mirrored with immutable retention. | Multi-repo sidecars (`sase`, `sase-core`); `sase` consumes binary `sase-core-rs` wheels from PyPI; retention script previously broke installs. | **Moderate Gap:** SASE's multi-repo boundary creates cross-repo version skew and retention fragility. |

---

## 3. What SASE Should NOT Borrow from Google (Avoid Over-Engineering)

1. **Do NOT build custom Affected Target Test Selection (Bazel TAP):**
   Google maintains a multi-billion-line monorepo requiring granular test impact graphs. SASE has ~150k lines of Python/Rust; GitHub Actions running sharded pytest in 12–15 minutes is fast enough.
2. **Do NOT introduce human code review or approval gates:**
   Google requires human `OWNERS` approvals on every CL. SASE is fundamentally an autonomous agentic system; human approvals would throttle throughput and deadlock self-authored agent PRs.
3. **Do NOT build complex multi-cluster canary analysis (ACA):**
   SASE is a Python CLI/TUI packaged on PyPI, not a distributed microservice serving live RPC traffic. Progressive traffic shifting (1% $\to$ 10% $\to$ 100%) does not apply to PyPI. A pre-flight virtual environment install smoke achieves 95% of the safety with minimal overhead.

---

## 4. Ranked List of Recommended Changes to SASE's Planned Release Process

Here is the prioritized, actionable ranking of adjustments to incorporate into the four-epic plan:

### Rank 1: Pre-Publication Staged Verification (Pre-Flight Clean Install Smoke)
- **Target Epic:** **Epic A** (Phase A3 / Phase A6).
- **The Problem:** Phase A3 publishes directly to PyPI, and Phase A6 runs an install canary on a daily schedule *after* the release is live. If a wheel has a missing shared library, an unresolvable dependency, or an entry-point crash, public users get the broken package immediately, permanently burning that PyPI version.
- **The Change:** Insert a **Pre-Flight Staging Verification** step immediately prior to PyPI publication:
  1. Build the wheel and sdist once.
  2. Upload them to an isolated staging area (GitHub Actions artifacts or TestPyPI).
  3. Spin up fresh, clean virtual environments across all supported Python versions (3.11, 3.12, 3.13, 3.14).
  4. Execute `uv/pip install` from the staged artifacts.
  5. Run `sase core health` and basic CLI smoke commands (`sase --help`, `sase repo list`).
  6. Only if all staging checks exit 0, proceed to the public PyPI upload step.
- **Impact:** **Highest.** Eliminates the risk of publishing an uninstallable package to PyPI, directly solving the root cause of the 49-day release stall *before* public release.

### Rank 2: Isolate Release Candidates from Trunk Velocity (Branch/Baseline Isolation)
- **Target Epics:** **Epic A** (Phase A1) and **Epic D** (Phase D6).
- **The Problem:** Release-please creates version PRs directly on `master`. Qualification occurs against `master`. If qualification fails, trunk is blocked or maintainers must "fix forward" on `master` while 43 agent landings per day are entering the merge queue.
- **The Change:** Adopt Google's release-branch / candidate-baseline isolation:
  1. The nightly release train identifies the latest commit on `master` that is verified **gate-green**.
  2. Cut an isolated candidate baseline (or temporary release branch `release/vX.Y.Z`).
  3. Execute qualification on this isolated commit.
  4. If qualification passes, tag and publish the release, then merge the changelog/version bump back to `master`.
  5. If qualification fails, active development on `master` continues unaffected. Maintainers can cherry-pick a targeted fix to the release branch or discard the candidate without rolling back trunk.
- **Impact:** **High.** Decouples the release pipeline from the high-frequency agent merge queue, preventing release stalls caused by transient trunk instability.

### Rank 3: Non-Punitive Flake Quarantine (De-escalation Instead of Expiring Lint Failure)
- **Target Epic:** **Epic B** (Phase B2).
- **The Problem:** Phase B2 specifies that quarantine entries expire after $\le 14$ days, and "an expired entry fails lint". This introduces a synthetic time-bomb into the gate: an unrelated agent trying to land a critical bug fix on day 15 will fail lint because an unrelated test owner hasn't resolved a quarantined flake.
- **The Change:** Replace the expiring lint failure with **automated de-escalation and alert escalation**:
  1. When a quarantine entry reaches 14 days without resolution, it does *not* fail lint on agent PRs.
  2. Instead, the test is automatically moved to disabled/ignored status in presubmit.
  3. A high-priority `ci` bead is filed or escalated directly to the maintainer/owner.
  4. Weekly flake digests report expired quarantine tests prominently.
- **Impact:** **Medium-High.** Protects the merge queue from synthetic breakage and maintains agent landing velocity while still holding owners accountable for test debt.

### Rank 4: Enforce Hermetic Cross-Repo Retention Contract
- **Target Epic:** **Epic A** (Phase A5).
- **The Problem:** Phase A5 plans to modify `pypi_retention.py` in `sase-core` to retain versions needed by the last $N \ge 2$ SASE releases. However, this is a soft script heuristic that runs in another repository.
- **The Change:** Turn this into a strict, verifiable contract:
  1. SASE's build/qualification pipeline must assert that the exact range of `sase-core-rs` declared in `pyproject.toml` exists on PyPI and can be resolved cleanly *before* building the release candidate.
  2. In `sase-core`, `pypi_retention.py` must require an explicit, cryptographically checked manifest of all active downstream SASE versions before executing any PyPI deletion command (`--dry-run` by default, fails closed on any API error).
- **Impact:** **Medium.** Ensures the multi-repo sidecar architecture cannot silently orphan published releases.

### Rank 5: Formalize Test Sizing for Merge Gate vs. Qualification Matrix
- **Target Epics:** **Epic B** (Phase B6) and **Epic D**.
- **The Problem:** Ambiguity over which tests belong in the pre-merge gate vs. post-merge/release lanes leads to slow gate times or flakiness leaks (e.g., visual snapshot tests taking ~30 min).
- **The Change:** Formally adopt Google's **Test Sizing Standard**:
  1. **Small/Medium (Presubmit / Merge Queue Gate):** Must be strictly hermetic, mock external networks/processes, run in $<1$ minute per test, and complete the full gate in $<15$ minutes. Only these tests can gate a merge.
  2. **Large (Nightly / Release Qualification):** TUI visual snapshots, multi-Python matrices (3.13, 3.14), performance floor benchmarks, and tutorial tests. These run exclusively in the decoupled nightly and pre-release qualification pipelines.
  3. Enforce an automated contract test in CI that fails if any test in the merge gate exceeds 60 seconds of execution time.
- **Impact:** **Medium.** Prevents gradual test suite bloat from slowing down the merge queue and keeps landing latency within the p50 $<15$ min target.

---

## 5. Artifact Verification & Deliverables

- **Markdown Report Created:** [`google_release_engineering_lessons_for_sase__gem.md`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/sase/repos/research/202610/google_release_engineering_lessons_for_sase__gem.md)
- **Snapshot Registered:** `sase artifact show file:explicit:4feb532e57b3a56c6496af68`
  - Ref: `file:explicit:4feb532e57b3a56c6496af68`
  - Label: `research:202610/google_release_engineering_lessons_for_sase__gem.md`
  - Status: `live` / verified

The SASE finalizer declaration has been submitted and accepted for the required commit payload (`repo-8caa19a02d02` in `sdd:research`). The host finalizer will commit the changes upon turn completion.
