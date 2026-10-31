# Chat History - ace-run (research.5l.gem)

- **TIMESTAMP:** 2026-10-31 10:34:00 EDT
- **MODEL:** agy/gemini-3.8-flash-high
- **AGENT:** research.5l.gem
- **PROMPT:** `~/.sase/multi_prompts/202610/gh_sase_org__sase-multiprompt-261031_100834.md`

## Prompt

%id(gem, clan=research.5l)
%m:agy/gemini-3.8-flash-high %q(1.5x, w=0.25)
#gh:gh_sase-org__sase 
You are researcher gem in a 5-researcher swarm.
The other researchers, `research.5l.cdx`, `research.5l.cld`, `research.5l.grk`, `research.5l.mus`, are independently investigating the same request and will write their own self-named reports ending in `__cdx.md` and `__cld.md` and `__grk.md` and `__mus.md`. Your report will end in `__gem.md`.

Conduct your research independently and form your own conclusions. Do NOT attempt to
locate, open, read, or otherwise consult the other researcher's report from this swarm,
even if it becomes available before you finish. Do not obtain that peer's findings
indirectly through its chat transcript, summaries, or requests to the peer. You may
independently use the same external sources, shared input material, and unrelated prior
research. You may check filenames or file existence to avoid overwriting your own
output, but do not inspect the peer's report contents. If you encounter its filename,
leave the report alone. The lead researcher will read every report and synthesize their
findings after you have all finished.

I'm getting consistent sase error notifications regarding agent publication. See the
errors shown in the ~/.sase/axe/error_digests/digest_20261031_100432.txt file, for
example. Can you do some research with the goal of helping me determine the best way to
fix this? End your analysis with a recommended solution. 
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

# Research Report: Agent Publication Drain Failure Root Cause Analysis & Remediation

**Researcher:** `gem` (5-Researcher Swarm)  
**Report Artifact Location:** [`202610/agent_publication_drain_failure_root_cause__gem.md`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_24/sase/repos/research/202610/agent_publication_drain_failure_root_cause__gem.md)  
**Durable Snapshot Ref:** `research:202610/agent_publication_drain_failure_root_cause__gem.md` (`file:explicit:b403f187793b76ccee1d0be3`)  
**Examined Incident Digest:** [`~/.sase/axe/error_digests/digest_20261031_100432.txt`](file:///home/bryan/.sase/axe/error_digests/digest_20261031_100432.txt)

---

## 1. Executive Summary & Core Finding

The recurring errors from the scheduler job `agent_publication` (e.g., `[agent_publication] gh_sase-org__sase: published agent page for 'bbugyi200.athena.sase-1pj.6' did not materialize during commit drain`) are caused by an **unfulfillable revision-association contract** between Python's prompt-archive publication and Rust's completion verification logic, **compounded by a misleading error diagnostic**.

Crucially:
1. **The published agent page did in fact materialize on disk.** In the sidecar clone (`~/.sase/projects/gh_sase-org__sase/repos/agents/`), both `sessions/bbugyi200.athena.sase-1pj.6.md` and `agents/bbugyi200.athena.sase-1pj.6/README.md` are present and valid.
2. The real failure reason returned by the Rust core backend ([`crates/sase_core/src/agent_publication_recovery/complete.rs`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_24/sase/repos/linked/sase-core/crates/sase_core/src/agent_publication_recovery/complete.rs)) is:
   `reason: "required page exists without the requested primary revision"`
3. Python ([`src/sase/agents_sync/_commit_publication_transaction_steps.py`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_24/src/sase/agents_sync/_commit_publication_transaction_steps.py#L311-L325)) discarded Rust's specific reason and hardcoded the misleading error message `"did not materialize during commit drain"`.
4. Over **3,540 historical items have accumulated in the outbox** (`gh_sase-org__sase`), with 3,542 currently quarantined. Each time a new agent finishes planning or runs without a primary commit, it encounters this bug, fails 3 times, triggers error notifications, and joins the quarantine backlog.

---

## 2. Deep Root Cause Analysis

### 2.1 The Producer Defect: Scope Mismatch on Non-Committing Runs
- In [`src/sase/axe/run_agent_exec_plan_accept_sdd.py`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_24/src/sase/axe/run_agent_exec_plan_accept_sdd.py#L33-L54), when an agent authors or accepts a plan (e.g., `sase-1pj.6`), `publish_planner_prompt_archive()` executes `git rev-parse HEAD` on the workspace clone and passes it as `primary_revision` to `publish_prompt_archive()`, setting `commit_cwd = ctx.workspace_dir`.
- In [`src/sase/agents_sync/prompt_archive/publish.py`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_24/src/sase/agents_sync/prompt_archive/publish.py#L150-L163), `fulfillment_scope_for_commit_cwd(commit_cwd)` inspects the workspace directory. Because the workspace directory is a clone of the primary repository, it assigns:
  `scope = PUBLICATION_SCOPE_REVISION` (`"revision"`).
- **The flaw:** A planner agent **never makes a commit in the primary repository** (`commits: []`). It publishes its prompt and plan to sidecar repositories (`sase--agents`, `sase--plans`). Tagging this request as `scope = "revision"` binds it to a non-existent commit obligation.

### 2.2 The Pre-Commit Revision Ghost in Multi-Turn Sessions
- For sessions that plan first and commit later (e.g. `sase-1q4.land`, `sase-1q5.land`):
  1. The planning turn (`--plan`) enqueues an outbox row with `primary_revision = <pre-commit-HEAD>`.
  2. The subsequent coding turn (`--code`) makes a commit and enqueues a row with the *new* commit SHA.
  3. Because the outbox key is `(global_agent, primary_revision)`, the second row does not overwrite the first. The actual commit fulfills and drains row 2, leaving row 1 stranded forever with the pre-commit parent revision.

### 2.3 The Verification Block in Rust
- In [`crates/sase_core/src/agent_publication_recovery/complete.rs`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_24/sase/repos/linked/sase-core/crates/sase_core/src/agent_publication_recovery/complete.rs#L48-L86):
  - When `scope == "linked"`, Rust fulfills the request as long as the page exists.
  - When `scope == "revision"`, Rust demands `revision_associated(...)`.
  - For zero-commit agents, `run.commit_shas` and `container.commit_shas` are empty.
  - For pre-commit ghost rows, the requested revision is not among the agent's commits.
  - Result: `fulfilled: false`, with `reason: "required page exists without the requested primary revision"`.

### 2.4 The Repair Block
- [`sase agent sync --repair-revisions`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_24/src/sase/agents_sync/publication_revision_repair.py) was built to repair stale pre-commit revisions by matching ancestor commits.
- However, in [`crates/sase_core/src/agent_publication_recovery/stale.rs`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_24/sase/repos/linked/sase-core/crates/sase_core/src/agent_publication_recovery/stale.rs#L77-L83):
  ```rust
  if request.run_commit_shas.is_empty() {
      return Ok(response(
          STALE_REPAIR_ACTION_UNRESOLVED,
          None,
          "no recorded run commits for this agent",
      ));
  }
  ```
  Zero-commit agents are marked `UNRESOLVED` and left untouched, making `--repair-revisions` incapable of clearing them. Furthermore, scanning 3,500+ items against git history causes the repair pass itself to time out.

---

## 3. Recommended Solution

### Phase 1: Operational Cleanup (Immediate)
1. **Reconcile and Prune Outbox Backlog:**
   - Run a reconciliation script on `~/.sase/projects/gh_sase-org__sase/agents-publication-outbox.json` to inspect quarantined items:
     - For items whose canonical sidecar page (`sessions/<agent>.md` or `agents/<agent>/README.md`) already exists, mark them acknowledged and remove them.
     - Prune historical rows older than 30 days to bring the outbox back to a lightweight, O(1) state. This will immediately resolve scheduler timeouts and restore fast sync operations.

### Phase 2: Producer Scope Assignment (Python)
1. In [`src/sase/axe/run_agent_exec_plan_accept_sdd.py`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_24/src/sase/axe/run_agent_exec_plan_accept_sdd.py) and [`src/sase/agents_sync/prompt_archive/publish.py`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_24/src/sase/agents_sync/prompt_archive/publish.py):
   - Enqueue prompt archive publication items originating from planning turns or non-committing runs with `scope = PUBLICATION_SCOPE_LINKED` (`"linked"`).
   - Because plans and prompt archives reside in sidecar repositories, `linked` scope correctly reflects their lifecycle: once the page is generated in the sidecar, the publication contract is satisfied.

### Phase 3: Rust Core Completion & Stale Classification Resilience (`sase-core`)
1. In [`crates/sase_core/src/agent_publication_recovery/stale.rs`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_24/sase/repos/linked/sase-core/crates/sase_core/src/agent_publication_recovery/stale.rs):
   - Map `run_commit_shas.is_empty()` to `STALE_REPAIR_ACTION_LINKED` instead of `STALE_REPAIR_ACTION_UNRESOLVED`. This allows `sase agent sync --repair-revisions --apply` to automatically convert stranded non-committing rows to linked scope.
2. In [`crates/sase_core/src/agent_publication_recovery/complete.rs`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_24/sase/repos/linked/sase-core/crates/sase_core/src/agent_publication_recovery/complete.rs):
   - When the page exists and the agent's recorded commit list is empty (`commit_shas.is_empty()`), recognize that the agent has no primary commit obligations and fulfill the request.

### Phase 4: Diagnostic Accuracy (Python)
1. In [`src/sase/agents_sync/_commit_publication_transaction_steps.py`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_24/src/sase/agents_sync/_commit_publication_transaction_steps.py#L311-L325):
   - Do not discard `decision.reason`. Use the returned reason directly in the logged diagnostic and error record:
     ```python
     error = f"agent publication for {item.global_agent!r} unfulfilled: {decision.reason}"
     ```
   - This eliminates false assertions about missing files and provides immediate visibility into the exact reason for any unfulfilled request.

---

The full research report has been saved to [`202610/agent_publication_drain_failure_root_cause__gem.md`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_24/sase/repos/research/202610/agent_publication_drain_failure_root_cause__gem.md), registered as a durable artifact snapshot (`file:explicit:b403f187793b76ccee1d0be3`), and submitted via the SASE finalizer declaration.
