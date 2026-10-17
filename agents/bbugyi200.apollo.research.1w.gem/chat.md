# Chat History - ace-run (research.1w.gem)

- **TIMESTAMP:** 2026-10-16 22:04:04 EDT
- **MODEL:** agy/gemini-3.8-flash-high
- **AGENT:** research.1w.gem
- **PROMPT:** `~/.sase/multi_prompts/202610/gh_sase_org__sase-multiprompt-261016_215155.md`

## Prompt

%id(gem, clan=research.1w)
%m:agy/gemini-3.8-flash-high %q(1.5x, w=0.25)
#gh:gh_sase-org__sase 
You are researcher gem in a 5-researcher swarm.
The other researchers, `research.1w.cdx`, `research.1w.cld`, `research.1w.grk`, `research.1w.mus`, are independently investigating the same request and will write their own self-named reports ending in `__cdx.md` and `__cld.md` and `__grk.md` and `__mus.md`. Your report will end in `__gem.md`.

Conduct your research independently and form your own conclusions. Do NOT attempt to
locate, open, read, or otherwise consult the other researcher's report from this swarm,
even if it becomes available before you finish. Do not obtain that peer's findings
indirectly through its chat transcript, summaries, or requests to the peer. You may
independently use the same external sources, shared input material, and unrelated prior
research. You may check filenames or file existence to avoid overwriting your own
output, but do not inspect the peer's report contents. If you encounter its filename,
leave the report alone. The lead researcher will read every report and synthesize their
findings after you have all finished.

After reading the gastown_vs_sase_lessons_to_borrow.md file in the research sidecar
repo, it seems like to me that sase needs better merge discipline.

- Namely, we need a way to ensure that master stays green so we can start publishing new
  versions of sase to PyPI more often.
- I'm not sure if we need to adopt a PR-only (i.e. protected master branch) workflow to
  achieve this (or if that's recommended anyway) or if there is some other way.

Can you do some research with the goal of helping me decide the best way to implement
this? Also, critique this plan in general. Is this a good idea? Would you take a
different approach? Make any adjustments to the requirements that you think are
justified but clearly call these out. End your analysis with a recommended solution. 
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

# Research Report: SASE Merge Discipline, Protected Branches, and Master Health

**Author:** researcher gem (`research.1w.gem`)  
**Artifact ID:** `explicit:e1d5ef46b84412c99e264901`  
**Artifact Ref:** `file:explicit:e1d5ef46b84412c99e264901`  
**Report Path:** [`sase_merge_discipline_and_green_master_architecture__gem.md`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/sase/repos/research/202610/sase_merge_discipline_and_green_master_architecture__gem.md)  
**Registered Label:** `research:202610/sase_merge_discipline_and_green_master_architecture__gem.md`

---

## 1. Executive Summary & Verdict

### Is a PR-Only (Protected Master Branch) Workflow a Good Idea?
**Verdict:** **No.** While standard in human engineering organizations, imposing a mandatory GitHub PR-only workflow with branch protection would severely cripple SASE's autonomous multi-agent software factory.

1. **Queue Saturation:** SASE runs at a high cadence of **40 to 90 commits per day**. Master Gate takes **12.7 minutes (p50)** and **31.5 minutes (p90)**. A serialized GitHub PR merge queue testing every PR on the merged tip requires between **19.0 and 47.3 hours of single-threaded CI runner capacity per calendar day**, guaranteeing continuous backlog growth and queue exhaustion.
2. **Quadratic Rebase Churn:** When PR 1 merges, open PRs 2 through $N$ become out-of-date and must rebase, invalidating their prior CI runs and creating rebase storms.
3. **Agent Impedance Mismatch:** Requiring human PR reviews stops autonomous swarms; using an automated bot merge queue adds 30–60 minutes of landing latency to every turn, halting topological execution waves (`sase bead work` Kahn waves) where downstream agents depend on landed code.

### What is the Real Root Cause of Master Breakage?
The lack of merge discipline is a very real problem (e.g., 198 of 198 runs red leading into October; 52 failures out of 58 on Oct 16; live regressions failing today). However, the root cause is **not** the lack of GitHub pull requests; it is that **SASE's host commit finalizer (`builtin@commit` via `_git_commit_dispatch.py`) rebases onto `origin/master` and pushes immediately without ever verifying the integrated rebased tree**. Master Gate runs strictly *post-push*, and 42% of commits land before the prior commit's CI has even finished. Furthermore, red test runs are routinely ignored under the assumption that failures are "inherited."

### Adjusting the Requirements: Decoupling PyPI Releases from Trunk
The prompt links keeping master green to publishing to PyPI more often (PyPI remains stuck on v0.17.1 since August 29; Release PR #299 for v0.18.0 has been blocked for over six weeks because `ci_watch` refuses to merge release PRs on a red master).

**Adjustment:** Development trunk velocity must be decoupled from release safety. Expecting trunk (`master`) to be green 100% of the time under high-throughput autonomous agent development is unrealistic. SASE should **not** gate releases on the instantaneous state of `master HEAD`. Instead, SASE should establish a **Proven-Green Release Train** (`stable` branch or release pointer tag) that automatically fast-forwards only to commits that have verified green on both `Master Gate` and `Full CI`. Releases to PyPI can then flow continuously and safely from this proven pointer, completely insulated from in-flight development breakage on `master`.

---

## 2. Critique & Comparison of Alternative Approaches

| Approach | CI Runner Cost | Landing Latency | Blast Radius of Breaks | Multi-Agent Fit | Verdict |
| :--- | :--- | :--- | :--- | :--- | :--- |
| **Option 1: GitHub PR-Only + Required Checks** | **Extreme** (19–47 h/day; queue saturation) | **Very High** (30–90 min per turn) | Zero on master | **Very Poor** (destroys wave dependencies; requires human bottleneck or bot) | **Rejected:** Mathematically saturates CI capacity; throttles agent throughput. |
| **Option 2: GitHub Merge Queue (Speculative Batching)** | **High** (re-runs batches on failure) | **High** (15–45 min per turn) | Zero on master | **Poor** (batch evictions cause latency spikes for agents) | **Rejected:** Re-evaluating `decisions:ci-two-speed-split` shows cloud queue overhead is unnecessary. |
| **Option 3: Post-Push Auto-Revert Bot** | **Low** (runs on existing CI) | **Zero** (immediate push) | High (master is red until reverted) | **Medium** (creates rebase churn and revert commit noise) | **Insufficient:** Does not stop 42% race where newer commits land before gate finishes. |
| **Option 4: Host-Owned Pre-Push Landing Lane (Local Rebase & Ratchet)** | **Zero GitHub CI cost** (runs locally on agent host) | **Low** (2–4 min local check) | Minimal (catches 95%+ of breaks before push) | **Excellent** (fits `host-owned-completion` & `receipts-prove-before-they-skip`) | **Recommended:** Solves trunk health at the source without cloud bottlenecks. |
| **Option 5: Decoupled `stable` Release Train** | **Zero additional cost** (reuses scheduled Full CI) | **N/A** (background release sync) | Zero for external PyPI users | **Flawless** (development never blocks releases; releases never block agents) | **Recommended:** Instantly unblocks frequent PyPI releases. |

---

## 3. The Recommended Architecture: Four-Layer Merge Discipline

Rather than adding a slow, cloud-based GitHub PR queue, SASE should implement a cohesive, deterministic, host-owned landing architecture:

```
                  [Agent Completes Turn]
                            │
                            ▼
           [Layer 1: Host-Owned Pre-Push Landing Lane]
         ┌──────────────────────────────────────────────┐
         │ 1. Acquire per-repo host landing lease       │
         │ 2. Fetch and rebase onto origin/master       │
         │ 3. Run fast local verification (just check)  │
         │ 4. Evaluate Ratchet:                         │
         │    - New failures? -> REFUSE PUSH            │
         │    - Clean pass? -> PROCEED                  │
         │ 5. Push to origin/master                     │
         │ 6. Verify remote SHA (push proof)            │
         └──────────────────────────────────────────────┘
                            │
                            ▼ (Pushed to master)
         ┌──────────────────────────────────────────────┐
         │ [Layer 2: Environment Parity Enforced]       │
         │ - Python 3.12 pinned locally & in CI         │
         │ - Linked sase-core checked against pin       │
         └──────────────────────────────────────────────┘
                            │
                            ▼
         ┌──────────────────────────────────────────────┐
         │ [Layer 3: Stop-The-Line Enforcement]         │
         │ If CI Master Gate fails on HEAD:             │
         │ - Commit finalizer refuses non-repair pushes │
         │ - Only 'ci'/'flake' task beads can land      │
         └──────────────────────────────────────────────┘
                            │
                            ▼
         ┌──────────────────────────────────────────────┐
         │ [Layer 4: Decoupled Stable Release Train]    │
         │ - Master Gate + Full CI passes on SHA X      │
         │ - Fast-forward 'stable' branch to SHA X      │
         │ - release-please & publish.yml cut PyPI from │
         │   'stable' continuously                      │
         └──────────────────────────────────────────────┘
```

### Layer 1: Host-Owned Pre-Push Landing Lane (`builtin@commit` Ratchet)
Borrowing the core verification lesson from Gas Town's Refinery and Bors, executed locally:
1. **Per-Repo Landing Lease:** The host commit finalizer (`src/sase/finalizers/commit_execution.py`) acquires a local lock per repository before committing, serializing concurrent agent pushes on that host.
2. **Rebase First:** Rebase the agent's work onto the fresh tip of `origin/master`.
3. **Verify the Rebased Tree:** Before `_git_commit_dispatch.py` executes `git push`, it runs `just check` locally against the rebased tree.
4. **Enforce the Regression Ratchet:**
   - If master was green: any failure is a regression $\rightarrow$ refuse the push and fail the landing.
   - If master was red: the commit must introduce zero *new* failure signatures outside the baseline.
   - Fits SASE's `decisions:receipts-prove-before-they-skip`: receipts serve as proof for completion, not an unverified skip.
5. **Prove the Push:** Following Gas Town's `verifyMQPostMergeProof`, confirm that `origin/master` contains the expected SHA before marking bead dependencies resolved.

### Layer 2: Strict Environment & Boundary Parity
1. **Commit `.python-version` = `3.12`:** Enforce Python 3.12 locally via `just install`. This closes the gap where Python 3.14 locally masked `argparse` formatting failures in CI.
2. **Pin Validation:** Verify linked `sase-core` checkouts against `sase-core-revision.txt` prior to test runs.
3. **Selector Blind Spots:** Track test facade and inter-test import edges in `tools/select_tests`.

### Layer 3: Stop-The-Line Mode on Red HEADs
- If `origin/master` HEAD is red on GitHub Actions, `_git_commit_dispatch.py` refuses all pushes unless the task bead or commit is tagged as `fix:`, `ci:`, or `flake:`.
- This halts the accumulation of hundreds of commits on top of broken states.

### Layer 4: Decoupled `stable` Release Train for Frequent PyPI Publishing
- Establish a `stable` branch in `sase-org/sase`.
- Have `ci_watch` automatically fast-forward `stable` to the latest `master` commit where both `Master Gate` and `Full CI` have passed.
- Retarget `release-please` and `.github/workflows/publish.yml` to run against `stable`.
- **Outcome:** PyPI releases happen automatically, frequently, and without risk, completely unblocked by normal feature iteration on `master`.

---

## 4. Implementation Roadmap

1. **Phase 1 (Immediate / Stop-The-Line):**
   - Perform a clean repair pass on the currently failing tests on master (`test_launch_approval_tui.py`, etc.).
   - Pin Python 3.12 locally via `.python-version`.
   - Merge Release PR #299 and publish SASE 0.18.0 to PyPI.
2. **Phase 2 (Week 1):**
   - Add pre-push local verification in `_git_commit_dispatch.py` behind a feature flag.
   - Wire push refusal into `builtin@commit` for failing rebased trees.
3. **Phase 3 (Week 2):**
   - Configure the `stable` branch and update `ci_watch` to advance it on proven-green commits.
   - Point `release-please` at `stable` to enable continuous PyPI releases.
4. **Phase 4 (Month 1):**
   - Migrate host landing lease and regression ratchet to `sase_core` (Rust backend) under `decisions:rust-core-required`.
   - Author decision record: `decisions:host-landing-lane-and-stable-release`.

---
*The complete report with detailed line-by-line code traces, empirical gate statistics, and mathematical modeling is saved in [`sase_merge_discipline_and_green_master_architecture__gem.md`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/sase/repos/research/202610/sase_merge_discipline_and_green_master_architecture__gem.md) and registered under artifact ID `explicit:e1d5ef46b84412c99e264901`.*
