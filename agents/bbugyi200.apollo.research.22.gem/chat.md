# Chat History - ace-run (research.22.gem)

- **TIMESTAMP:** 2026-10-18 11:39:36 EDT
- **MODEL:** agy/gemini-3.8-flash-high
- **AGENT:** research.22.gem
- **PROMPT:** `~/.sase/multi_prompts/202610/gh_sase_org__sase-multiprompt-261018_111719.md`

## Prompt

%id(gem, clan=research.22)
%m:agy/gemini-3.8-flash-high %wait:8y %q(1.5x, w=0.25)
#gh:gh_sase-org__sase 
You are researcher gem in a 4-researcher swarm.
The other researchers, `research.22.cdx`, `research.22.cld`, `research.22.grk`, are independently investigating the same request and will write their own self-named reports ending in `__cdx.md` and `__cld.md` and `__grk.md`. Your report will end in `__gem.md`.

Conduct your research independently and form your own conclusions. Do NOT attempt to
locate, open, read, or otherwise consult the other researcher's report from this swarm,
even if it becomes available before you finish. Do not obtain that peer's findings
indirectly through its chat transcript, summaries, or requests to the peer. You may
independently use the same external sources, shared input material, and unrelated prior
research. You may check filenames or file existence to avoid overwriting your own
output, but do not inspect the peer's report contents. If you encounter its filename,
leave the report alone. The lead researcher will read every report and synthesize their
findings after you have all finished.

Can you help me review all of the files that the previous agent just tagged in the
research sidecar repo, which are related to our efforts to make sase's PyPI releases
much more reliable? Once you've done that, you should think hard about what the best
possible solution is and how the work should be split up. It's fine if your
recommendation steals a lot from those other research files (i.e. no need to be
original). Converging on the best design/architecture is our main priority. 
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

The command is running synchronously to read `merge_queue_fence_reassessment_and_epic_split.md`. Waiting for output.
The command is reading the original proposal `merge_queue_fenced_master_and_exact_sha_releases.md`. Waiting for output.
The command is reading `google_release_engineering_vs_sase_release_plan.md`. Waiting for output.
The command is reading `github_native_merge_queue_primer.md`. Waiting for output.
The command is reading `gastown_vs_sase_lessons_to_borrow.md`. Waiting for output.
The command is reading `gascity_advantages_over_sase_and_what_to_borrow.md`. Waiting for output.
The command is reading `agent_factory_merge_discipline_reading_list.md`. Waiting for output.
The command is reading `sase_sh_docs_redesign.md`. Waiting for output.
The command `sase artifact show` is finishing. Waiting for output.
# Research Report: PyPI Release Reliability Architecture and Epic Delivery Plan

**Researcher:** `gem` (Independent Researcher 4 of 4, Swarm 22)  
**Report File:** [`pypi_release_reliability_architecture_and_epic_plan__gem.md`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_17/sase/repos/research/202610/pypi_release_reliability_architecture_and_epic_plan__gem.md)  
**Registered Artifact:** `research:202610/pypi_release_reliability_architecture_and_epic_plan__gem.md` (`file:explicit:f9443fc5500c0cc80832d357`)

---

## 1. Overview and Synthesis of Reviewed Research

All 12 tagged research files in the research sidecar repository were audited and analyzed. Together, they explain both why SASE's PyPI release cadence broke down for 49 days and how to fix it permanently:

### 1.1 The Release Crisis & Immediate Context
* **`sase_v0_18_0_pypi_release_status.md`**: Unpacks why release PR #299 (v0.18.0) sat unmerged since late August. `ci_watch` required a completed Full CI run on `master` that was $\le 6$ hours old. However, Full CI had failed for 49 consecutive days due to visual golden timeouts and test flakes. Crucially, PyPI's existing v0.17.1 package broke (`sase-16p`) because retention in `sase-core` wiped out older `sase-core-rs` versions, causing `pip install sase` to resolve to v0.1.0 or error out.
* **`master_ruleset_step0_setup_steps.md`**: Provides exact steps for **Step 0**: creating a repository ruleset on `sase-org/sase` (`master-integrity`) to block branch deletion and force-pushes (`non_fast_forward`) with an empty bypass list, completely decoupled from any feature epic.

### 1.2 Core Reassessments & Queue Mechanics
* **`merge_queue_fenced_master_and_exact_sha_releases.md`**: Established that runner capacity is **not** the bottleneck ($K=2$ concurrency comfortably handles 43 landings/day at ~13 min p50 and ~28 min p95). Flakiness ($>10\%$) is the true bottleneck. Proved host-side landing lanes (Gas Town R1) fail because local checks pass only 3.6% of the time and cannot coordinate multi-host pushes (apollo vs. athena).
* **`merge_queue_fence_reassessment_and_epic_split.md`**: Consolidated prior research into a four-epic roadmap and reversed the merge method from merge commits to **rebase** after uncovering release-please changelog duplication and drops in SASE's real history. Established the N1 three-tier check inventory and extracted v0.18.0 into Track 0.
* **`merge_queue_fence_reassessment_explained.md`**: Clarified the boundary separations: why merging Epics C and D into 3 epics would compromise sandbox verification and leave cutover unowned.
* **`github_native_merge_queue_primer.md`**: Verified that GitHub advances `master` to the exact tested group commit SHA on `gh-readonly-queue/master/...`. Highlighted that `gh pr merge` exits 0 on *armed/queued*, requiring asynchronous reconcilers, and documented why skipping checks on `merge_group` causes untested code to land, requiring an event-aware aggregate check (`integration-ready`).

### 1.3 External Best Practices & Cross-Ecosystem Inputs
* **`google_release_engineering_vs_sase_release_plan.md`**: Compared the plan against Google release engineering (Piper, TAP, Rapid, MPM, BAB). Identified critical post-merge gaps:
  1. *Flake-aware qualification:* 3 of 6 runs on unchanged commit `ae9f044bb3` failed due to 1–2 flakes out of ~56k tests. Bounded 1-shot reruns are essential.
  2. *Post-submit discipline:* 2-hour continuous Full CI with deterministic culprit finding and auto-revert-first.
  3. *Multi-OS behavioral exercise:* Clean-environment testing of wheels/sdist on Linux and macOS before uploading.
  4. *Quarantine time-bomb fix:* Expired quarantine entries must escalate hygiene and bead priority, never break the required admission gate.
  5. *Provenance hardening:* Trusted Publishing attestations must certify the release candidate SHA, not the trigger commit.
* **`merge_queue_impact_on_testing_agent_fixes.md`**: Addressed the edit-test loop under asynchronous queue landing, mandating landed notifications and `sase preview` (isolated worktree at the PR head).
* **`agent_factory_merge_discipline_reading_list.md`**: Synthesized modern agent VC literature (Anthropic, Uber SubmitQueue/Stovepipe, Mergify, Snyk LiteLLM poisoned scanner), warning against unchecked queue retry loops and confirming zero approvals remains safe with automated post-merge verification.
* **`gastown_vs_sase_lessons_to_borrow.md` & `gascity_advantages_over_sase_and_what_to_borrow.md`**: Reinforced that "fences beat promises", confirmed that git alternates eliminate workspace disk bloat, and validated mechanical release invariants.
* **`sase_sh_docs_redesign.md`**: Emphasized that "Step 1 must be true": the documented first-run install (`uv tool install sase`) must match shipped PyPI reality.

---

## 2. Converged Architectural Solution

1. **Admission Control & Protected Master:**
   - **GitHub Ruleset:** Enforce required pull requests with **0 approvals**, block force pushes/deletions, and require merge queue with `merge_method: REBASE`, concurrency $K=2$, `ALLGREEN` grouping, and an empty bypass list.
   - **Event-Aware Aggregate (`integration-ready`):** Fast formatting/lint checks on `pull_request`; full Master Gate suite on `merge_group`.
   - **Drift Protection:** Base-red witness on ejection; 3-strike circuit breaker with durable hold; queue-jump for repair turns; nightly +30-day shifted-clock canary.
2. **Exact-Candidate Qualification & Publishing:**
   - **Draft Versioning:** `release-please` configured with `draft: true` and `force-tag-creation: true`. Release is published/un-drafted only upon PyPI confirmation.
   - **Build-Once Binary Pipeline:** Wheel and sdist built once from the candidate SHA, recording sha256 digests. Trusted Publishing attestations strictly bound to candidate SHA.
   - **Flake-Aware Qualification:** Bounded 1-shot in-job rerun for $\le 3$ failing test nodes in `ci.yml` release-blocking jobs.
   - **Pre-Publish Behavioral Exercise:** Clean virtual environment installation and validation (`sase --version`, `sase core health`, headless TUI frame rendering, real CLI workflow) on both `ubuntu-latest` and `macos-latest`.
   - **Public Install Canary & Recovery:** Daily clean-room canary testing `uv tool install sase` against public PyPI; automated yanking tool (`sase release yank`) and release-branch hotfixes.
3. **Core Dependency Invariant & Retention Guard:**
   - `sase-core`'s `pypi_retention.py` enforces an inviolable rule: never delete any `sase-core-rs` version required by the last $N \ge 2$ published `sase` releases; fails closed on error.
   - Automatic `CORE_LAG` detector cuts required `sase-core` releases before promoting SASE releases.
4. **Developer Experience & Velocity:**
   - Turn ends at **armed** submission (`gh pr merge --auto`).
   - Host reconciler tracks `armed` $\to$ `queued` $\to$ `landed` / `ejected` and emits a landed notification.
   - `sase preview` runs isolated worktrees at the PR head for immediate local testing before landing.

---

## 3. Four-Epic Delivery Roadmap

```
[Today]  Step 0: Human Admin Ruleset (Force-push & deletion protection on master)
[Now]    Track 0: Restore PyPI Installability (sase-16p / sase-10d / PR #299 / v0.18.0)

               ┌──────────────────────────────────────────────┐
               │         Parallel Engineering Phase            │
               ├──────────────────────┬───────────────────────┤
               ▼                      ▼                       ▼
      [Epic A: Releases]      [Epic B: Gate]          [Epic C: Queue]
      - Build-once SHA        - Bounded rerun         - Landing state machine
      - Flake-aware qual      - Expiring quarantine   - Rebase adapter
      - Linux/macOS exercise  - Parity (.python-ver)  - Preview & notify
      - Retention invariant   - Shifted-clock canary  - Sandbox verification
      - Install canary        - False-red digest      
               │                      │                       │
               │                      ▼                       ▼
               │              [Mechanisms Live]       [Sandbox Suite Passed]
               │                      │                       │
               └──────────────────────┼───────────────────────┘
                                      ▼
                        [Epic D: Production Cutover]
                        - Production merge_group & integration-ready
                        - Low-risk pilot (docs, toobig, ratchets)
                        - Culprit finder & auto-revert
                        - 7-day soak (<3% false reds)
                        - Enforce queue default (bypass empty)
                        - Nightly release train active
```

* **Step 0 (Today, Admin):** Create `master-integrity` branch ruleset on `sase-org/sase` blocking deletions and non-fast-forward pushes.
* **Track 0 (Immediate, Parallel):** Restore PyPI installability. Cut `sase-core-rs` for `916d5e3a`, ratchet PR #299, and publish v0.18.0.
* **Epic A (Parallel Start):** Exact-Candidate Releases, Install Guards, and Core Invariants (Build-once candidate record, flake-aware qualification, multi-OS exercise, core retention invariant, daily public install canary).
* **Epic B (Parallel Start):** Trustworthy Merge Gate & Drift Protection (Bounded rerun, non-blocking quarantine with hygiene escalation, test parity, +30-day shifted-clock drift canary).
* **Epic C (Parallel Start):** Queue-Aware Landing Protocol & Developer Experience (Landing state machine in `sase_core`, rebase adapter in `sase-github`, `sase preview` worktree command, landed notifications, proven on `sase-org/sase-sandbox`).
* **Epic D (Sequenced Cutover):** Production Cutover, Post-Submit Discipline, and Release Train (Requires Epic B live and Epic C sandbox passed; low-risk pilot, 7-day soak with $<3\%$ false reds, post-submit culprit finder and auto-revert, and nightly release train).

---

## 4. Execution and Artifact Registration

1. **Research Report Created:**
   - **Absolute Path:** `/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_17/sase/repos/research/202610/pypi_release_reliability_architecture_and_epic_plan__gem.md`
   - **Relative Path:** `202610/pypi_release_reliability_architecture_and_epic_plan__gem.md`
2. **Artifact Registered:**
   - **Command:** `sase artifact create -p "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_17/sase/repos/research/202610/pypi_release_reliability_architecture_and_epic_plan__gem.md" -l "research:202610/pypi_release_reliability_architecture_and_epic_plan__gem.md"`
   - **Artifact ID:** `explicit:f9443fc5500c0cc80832d357`
   - **Status:** Verified live and stored cleanly in SASE artifact storage.
3. **Turn Finalization:**
   - Finalizer declaration submitted and accepted via `sase final submit`.
