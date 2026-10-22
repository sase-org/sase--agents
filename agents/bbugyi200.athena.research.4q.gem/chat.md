# Chat History - ace-run (research.4q.gem)

- **TIMESTAMP:** 2026-10-17 16:04:54 EDT
- **MODEL:** agy/gemini-3.8-flash-high
- **AGENT:** research.4q.gem
- **PROMPT:** `~/.sase/multi_prompts/202610/gh_sase_org__sase-multiprompt-261017_154710.md`

## Prompt

%id(gem, clan=research.4q)
%m:agy/gemini-3.8-flash-high %q(1.5x, w=0.25)
#gh:gh_sase-org__sase 
You are researcher gem in a 4-researcher swarm.
The other researchers, `research.4q.cdx`, `research.4q.cld`, `research.4q.grk`, are independently investigating the same request and will write their own self-named reports ending in `__cdx.md` and `__cld.md` and `__grk.md`. Your report will end in `__gem.md`.

Conduct your research independently and form your own conclusions. Do NOT attempt to
locate, open, read, or otherwise consult the other researcher's report from this swarm,
even if it becomes available before you finish. Do not obtain that peer's findings
indirectly through its chat transcript, summaries, or requests to the peer. You may
independently use the same external sources, shared input material, and unrelated prior
research. You may check filenames or file existence to avoid overwriting your own
output, but do not inspect the peer's report contents. If you encounter its filename,
leave the report alone. The lead researcher will read every report and synthesize their
findings after you have all finished.

Can you reassess the solution proposed by the
merge_queue_fenced_master_and_exact_sha_releases.md file in the research sidecar repo,
make any changes to its requirements (in the new report your create) that you think are
warranted (but clearly call these out), and then recommend whether or not this work
should be a single epic or multiple epics with justification and indepent epic
verification steps if you think that multiple are warranted? 
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

# Research Reassessment: Merge-Queue-Fenced `master`, Exact-SHA PyPI Releases, and Epic Decomposition

**Author:** Researcher `gem` (`research.4q.gem`)  
**Artifact Ref:** `file:explicit:c759a26c3ae1f2bab8b6358d` (`artifacts[0]`)  
**Report Path:** [`merge_queue_reassessment_and_epic_structure__gem.md`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/sase/repos/research/202610/merge_queue_reassessment_and_epic_structure__gem.md)  
**Registered Label:** `research:202610/merge_queue_reassessment_and_epic_structure__gem.md`

---

## 1. Executive Summary & Verdict

The solution proposed in [`merge_queue_fenced_master_and_exact_sha_releases.md`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/sase/repos/research/202610/merge_queue_fenced_master_and_exact_sha_releases/merge_queue_fenced_master_and_exact_sha_releases.md) is architecturally sound in its core thesis:
1. **GitHub Native Merge Queue over Host Locks:** Host-side locking (`flock`) fails because SASE landings originate from multiple machines (`athena` and `apollo`), local checks take 12–59 minutes and fail 96% of the time, and local validation cannot enforce server-side push rejection.
2. **Decoupled Qualification & Exact-SHA Releases:** Green HEAD is an illusory release gate. The root cause of the 49-day PyPI release stall since August 29 is not merely Master Gate volatility, but rather Full CI drift, core-floor blockers, and a silent defect in `.github/workflows/publish.yml` where `actions/checkout@v4` checks out the default branch tip instead of the qualified release commit.
3. **Flake Quarantine Precedes Queue Enforcement:** Enforcing a merge queue on a test suite with a 30–40% false-red rate turns the queue into a random-rejection engine that thrashes speculative batches and starves agent workflows.

However, the proposed requirements have **critical gaps** that must be resolved, and the work **must be partitioned into multiple epics (specifically, three sequenced epics)** rather than a single monolithic epic.

---

## 2. Warranted Requirement Adjustments

The following six adjustments modify or extend the requirements specified in the baseline report:

| # | Requirement Area | Baseline Stance | Warranted Adjustment | Rationale |
| :--- | :--- | :--- | :--- | :--- |
| **R1** | **Release Publishing Atomicity** | Release-please tags on GitHub; `publish.yml` builds, qualifies, and pushes to PyPI. If qualify fails, "fix forward". | **Tag-After-Qualify via Draft Releases:** A permanent public git tag or release must *not* be created until the `qualify` workflow passes. Keep release-please releases as `draft: true` until qualification succeeds. | Under protected tag rulesets, a failed qualification run leaves an orphaned, unremovable public git tag that does not exist on PyPI, breaking downstream tooling and version resolvers. |
| **R2** | **Visual Test Gating Precondition** | Fold `visual-test` (check mode, sharded) into Master Gate during Phase 1. | **Shadow Mode Precondition for Visual Tests:** `visual-test` MUST NOT be a required status check until it achieves a false-red rate of < 1% over 14 consecutive days. Run in shadow/advisory mode only. | The baseline data shows `visual-test` failed in 270 of 271 runs. Mandating an actively broken suite in the merge gate will instantly paralyze all 43 daily landings. |
| **R3** | **Cross-Repo Landing Order** | Handled implicitly under single-repo landing rules. | **Coordinated Landing Dependency (`sase` + `sase-core`):** The landing state machine in `sase_core` and `sase-github` must enforce that `sase-core` merges and publishes upstream *before* the dependent `sase` PR enters the merge queue. | `master-gate.yml`'s `core-wheel` job fetches Rust core directly from `sase-core-revision.txt` at `sase-org/sase-core`. An unmerged core SHA causes deterministic compilation failures. |
| **R4** | **Epic Wave Latency SLA** | "Each phase starts once the previous one has merged." | **Phase Parallelism & Epic Integration Branches:** Bound wave latency by prioritizing horizontal clan waves and supporting optional epic integration branches for epics with > 3 sequential phases; enforce a queue p50 SLA < 25 min. | Waiting 20–30 minutes for merge confirmation on a 5-phase sequential epic adds 100–150 minutes of idle queue latency. |
| **R5** | **Speculative Batch Attribution** | When head fails, all speculative builds restart. | **Isolated Retesting of Queued Dependents:** When speculative batch (PR1 + PR2) fails, PR1 is ejected and PR2 is immediately re-tested standalone without receiving a failure penalty or burning a retry. | Prevents healthy PRs speculative stacked behind a broken PR from being misclassified as defective or trapped in redundant repair cycles. |
| **R6** | **Host Gate Lease Retirement** | Replaces host landing lane with GitHub merge queue. | **Full Deprecation of Host-Local Locks:** Formally remove all local `flock` serial locks and demote local `just check` to lightweight pre-commit linting (< 2 min). Full verification belongs solely on GitHub Actions. | Local `just check` takes 12–59 min and fails 96% of the time on `apollo`, while `athena` cannot synchronize local locks across hosts. |

---

## 3. Epic Decomposition Recommendation: Multiple Epics (3 Epics)

**Executing this work as a single epic is strongly rejected.** It must be structured as **three strictly sequenced epics**:

```
[ EPIC 1: Phase 0 ]
Exact-SHA Releases & Master Protection Fences
- Fix publish.yml (exact SHA checkout)
- Add master force-push/delete ruleset
- Reconcile release metadata & ship 0.18.0
(Duration: 2-3 Days | Risk: Low | Verification: 0.18.0 on PyPI)
       |
       v
[ EPIC 2: Phase 1 ]
CI Gate Trustworthiness & Flake Quarantine
- Inline single-node test retry (<= 3 nodes)
- Expiring quarantine manifest (quarantine.yml)
- Python 3.12 & Rust core revision parity
- Reschedule Full CI to nightly; visual tests in shadow mode
(Duration: 1-2 Weeks | Risk: Medium | Verification: False-reds < 3% over 7 days)
       |
       v
[ EPIC 3: Phases 2 & 3 ]
Native Merge Queue & Host Landing Orchestration
- Rust landing record state machine (sase_core)
- GitHub PR landing adapter & submit.py fix (sase-github)
- Deterministic landing watcher daemon
- Actions merge_group workflow & integration-ready check
- Scratch repo rehearsal -> Low-risk pilot -> Full enforcement
(Duration: 2-3 Weeks | Risk: High | Verification: Zero direct pushes, p50 < 30m, 100% via queue)
```

### Justification Against a Single Monolithic Epic

1. **Urgency Mismatch (Emergency Unblock vs. Infrastructure Overhaul):** PyPI 0.18.0 has been stalled for 49 days. Phase 0 is an emergency YAML and workflow repair taking 2–3 days. Coupling it to a multi-week cross-repo Rust/GitHub merge queue rollout needlessly delays releasing 0.18.0 by another month.
2. **Technical Domain Decoupling:** Phase 0 is GitHub Actions workflow configuration; Phase 1 is pytest and test harness stabilization; Phase 2/3 is distributed systems engineering across `sase_core` (Rust), `sase-github` (Python API client), and GitHub repository rulesets.
3. **Hard Prerequisite Gate:** A merge queue cannot be safely turned on until gate stability is proven. If combined into one epic, the epic would enter an ambiguous limbo state where queue code is ready but cannot be enabled because tests are still flaking at 15–20%.
4. **SASE Agent & Bead Lifecycle Rules:** SASE epics cannot sit idle for weeks monitoring flake rates or running canary pilots without violating single-turn and bead lifecycle constraints.

---

## 4. Independent Epic Verification Plans

### Epic 1: Exact-SHA Release Pipeline & Master Protection Fences (Phase 0)
- **Scope:** `.github/workflows/publish.yml`, `tools/_release_watch_api.py`, GitHub branch rulesets, unblocking 0.18.0.
- **Independent Verification Protocol:**
  1. *Ruleset Protection:* Attempt `git push origin :master` using a test token; confirm server rejects with HTTP 403 / protected branch error.
  2. *Ref Resolution in CI:* Trigger a dry-run `publish.yml` on a test tag; verify the checkout step logs the exact requested SHA rather than `master` HEAD.
  3. *Digest Parity:* Verify that sha256 checksums of built wheels in `build` match those tested in `qualify` and `install-smoke` byte-for-byte.
  4. *Qualify Gating:* Simulate a failed `qualify` job; confirm downstream `publish` job is skipped and no upload occurs.
  5. *Production Release:* Merge PR #299; confirm PyPI returns HTTP 200 for `sase 0.18.0` and `uv pip install sase==0.18.0` succeeds in a clean virtualenv.

### Epic 2: CI Gate Trustworthiness & Expiring Flake Quarantine (Phase 1)
- **Scope:** `.github/workflows/master-gate.yml`, test runner configuration, `tests/quarantine.yml`.
- **Independent Verification Protocol:**
  1. *Inline Flake Retry:* Commit a test that fails attempt 1 and passes attempt 2; verify the job passes with a `FLAKY: <node_id>` annotation.
  2. *Retry Bound:* Commit 4 failing tests; verify retry logic is bypassed and the job fails fast without burning extra time.
  3. *Quarantine Isolation:* Add a test to `tests/quarantine.yml`; verify it is excluded from gate shards and executed in a non-blocking lane.
  4. *Quarantine Expiry Lint:* Add an entry with an expired date to `tests/quarantine.yml`; verify `just lint` fails with an expired quarantine error.
  5. *7-Day Gate Stability SLA:* Query GitHub Actions API over 7 consecutive days; confirm Master Gate false-red rate is strictly < 3%.

### Epic 3: Native Merge Queue & Host Landing Orchestration (Phases 2 & 3)
- **Scope:** `sase_core` (Rust state machine), `sase-github` (`submit.py`), `master-gate.yml` (`merge_group`), GitHub rulesets.
- **Independent Verification Protocol:**
  1. *Scratch Repo Rehearsal:* Execute an end-to-end queued PR merge on a test repository; confirm `merge_group` runs and auto-merges successfully.
  2. *Proof-of-Merge Bead State:* Complete an agent turn; verify the assigned bead remains `in_progress`/`claimed` while queued, and transitions to `closed` *only* after the landing watcher confirms SHA and tree equality on `master`.
  3. *Mutual Incompatibility Rejection:* Submit two PRs that pass independently but conflict when integrated; confirm the queue admits PR A and cleanly ejects PR B without corrupting `master`.
  4. *Direct Push Rejection:* Attempt a direct push to `master` as both agent and maintainer; verify server-side rejection by the GitHub ruleset.
  5. *Nightly Release Train:* Verify unattended nightly release-please execution enqueues the release PR, qualifies the candidate commit, and publishes without manual human intervention.

---

## 5. Report Artifact Snapshot

The full research report has been written without overwrite and registered in durable artifact storage:
- **File:** `/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/sase/repos/research/202610/merge_queue_reassessment_and_epic_structure__gem.md`
- **Registration Command:** `sase artifact create -p "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/sase/repos/research/202610/merge_queue_reassessment_and_epic_structure__gem.md" -l "research:202610/merge_queue_reassessment_and_epic_structure__gem.md"`
- **Artifact ID:** `explicit:c759a26c3ae1f2bab8b6358d`
- **Final Declaration:** Submitted via `/sase_final` (`sase final submit -`) and accepted by the host.
