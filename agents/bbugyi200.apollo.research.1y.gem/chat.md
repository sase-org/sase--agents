# Chat History - ace-run (research.1y.gem)

- **TIMESTAMP:** 2026-10-17 15:20:07 EDT
- **MODEL:** agy/gemini-3.8-flash-high
- **AGENT:** research.1y.gem
- **PROMPT:** `~/.sase/multi_prompts/202610/gh_sase_org__sase-multiprompt-261017_150918.md`

## Prompt

%id(gem, clan=research.1y)
%m:agy/gemini-3.8-flash-high %q(1.5x, w=0.25)
#gh:gh_sase-org__sase 
You are researcher gem in a 4-researcher swarm.
The other researchers, `research.1y.cdx`, `research.1y.cld`, `research.1y.grk`, are independently investigating the same request and will write their own self-named reports ending in `__cdx.md` and `__cld.md` and `__grk.md`. Your report will end in `__gem.md`.

Conduct your research independently and form your own conclusions. Do NOT attempt to
locate, open, read, or otherwise consult the other researcher's report from this swarm,
even if it becomes available before you finish. Do not obtain that peer's findings
indirectly through its chat transcript, summaries, or requests to the peer. You may
independently use the same external sources, shared input material, and unrelated prior
research. You may check filenames or file existence to avoid overwriting your own
output, but do not inspect the peer's report contents. If you encounter its filename,
leave the report alone. The lead researcher will read every report and synthesize their
findings after you have all finished.

Can you do some research with the goal of helping me understand how GitHub's native
merge queues work? See the merge_queue_fenced_master_and_exact_sha_releases.md file in
the research sidecar repo for context. Make sure your report is concise and easy to
understand. 
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

# Research Report: How GitHub's Native Merge Queues Work

The research report has been completed independently and registered in durable artifact storage:
* **Report Path:** [`how_github_merge_queues_work__gem.md`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_17/sase/repos/research/202610/how_github_merge_queues_work__gem.md)
* **Artifact Reference:** `file:explicit:706d37888e486460b7892431` (`research:202610/how_github_merge_queues_work__gem.md`)

Below is a concise summary of how GitHub native merge queues operate, their architecture, key levers, and automation gotchas.

---

## 1. What Problem Merge Queues Solve

In active repositories, pull requests (PRs) that pass CI in isolation often break the target branch (`main`/`master`) when merged sequentially due to **semantic merge conflicts** (e.g., PR #1 renames a method that PR #2 calls).

* **Why standard PR protections fail:** PR tests validate against a stale base commit, not the future integrated state.
* **Why "Require branches to be up to date" causes churn:** Forcing authors to manually rebase whenever `main` advances causes exponential CI churn and starvation on active repositories (at 40+ landings/day, PRs enter a constant re-test loop).
* **The Merge Queue solution:** GitHub automates the integration and testing of PRs in First-In, First-Out (FIFO) order against the latest cumulative state on transient staging branches (`gh-readonly-queue/<base>/...`), merging only verified trees.

---

## 2. Core Mechanics

### The Queue Flow
1. **Enrollment:** Once branch protection checks and approvals pass, a PR is added to the queue (via UI *"Merge when ready"* or CLI `gh pr merge --auto`).
2. **Transient Integration Branches:** GitHub creates a temporary branch (e.g., `gh-readonly-queue/main/pr-123-...`) combining `main` + changes from all PRs ahead in the queue + this PR.
3. **Speculative Parallel Execution:** If **Build Concurrency** $> 1$, GitHub builds and tests stacked PRs in parallel rather than waiting for each to finish serially:
   * `Group 1`: `main + PR #1`
   * `Group 2`: `main + PR #1 + PR #2`
4. **Landing / Ejection:**
   * If both pass: both merge sequentially into `main` without waiting for two full CI durations.
   * If PR #1 fails: GitHub immediately ejects PR #1, invalidates Group 2, and restacks PR #2 directly on `main` to re-test.

---

## 3. GitHub Actions CI Integration (`merge_group`)

Workflows triggered by `on: pull_request` **do not run** on merge queue branches.

```yaml
on:
  pull_request:
    branches: [ "master" ]
  merge_group:
    types: [ checks_requested ]
```

### Critical Gotchas
* **Exact Check Matching:** Any status check marked "required" in branch protection rulesets must be reported by the `merge_group` workflow. If a check only runs on `pull_request`, the queue hangs until the status check timeout.
* **No Top-Level Path Filters:** Using `paths:` filters on required workflows causes GitHub to report `Pending` indefinitely when filtered out. Use job-level `if:` conditions or an aggregate gate job instead.
* **Scoped Concurrency Keys:** Concurrency blocks using `group: ${{ github.workflow }}-${{ github.ref }}` must preserve the transient queue ref. If grouped by target branch alone (`master`), incoming queue runs cancel earlier ones.

---

## 4. Key Configuration Levers

| Parameter | Recommended Setting | Rationale |
| :--- | :--- | :--- |
| **Merge method** | `merge` | Preserves commit history, author provenance, and commit trailers/footers. Avoids base-resolution bugs seen in historical squash/rebase incidents. |
| **Build concurrency** | `2` to `4` | Enables speculative parallel execution to minimize queue wait latency while preventing CI runner starvation. |
| **Only merge non-failing PRs** | `Enabled` | Enforces that each individual PR satisfies required checks before merging. |
| **Status check timeout** | `60 min` | Bounds maximum execution time before an unresponsive CI run is ejected. |
| **Merge limits** | Min: `1`, Max: `5` | Controls batching to the base branch. *(Note: Per GitHub docs, limits govern merges to the base branch, not CI build grouping).* |

---

## 5. Automation & Agentic Considerations

1. **Zero Human Approvals for Bots:** GitHub prohibits self-approvals. Automated agent pipelines must configure branch rulesets with `0` required reviews to prevent deadlock.
2. **`gh pr merge` Semantics:** On a queue-protected branch, `gh pr merge` exits `0` as soon as the PR is **queued**, not merged. Automated finalizers must not treat exit `0` as proof of landing.
3. **Flake Sensitivity:** A 10–15%+ test flake rate severely degrades speculative queues, as a single false failure cancels all trailing speculative builds. In-job retries and quarantine mechanisms are essential prerequisites.
