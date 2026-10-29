# Chat History - ace-run (research.5h.gem)

- **TIMESTAMP:** 2026-10-29 01:26:39 EDT
- **MODEL:** agy/gemini-3.8-flash-high
- **AGENT:** research.5h.gem
- **PROMPT:** `~/.sase/multi_prompts/202610/gh_sase_org__sase-multiprompt-261029_010613.md`

## Prompt

%id(gem, clan=research.5h)
%m:agy/gemini-3.8-flash-high %q(1.5x, w=0.25)
#gh:gh_sase-org__sase 
You are researcher gem in a 5-researcher swarm.
The other researchers, `research.5h.cdx`, `research.5h.cld`, `research.5h.grk`, `research.5h.mus`, are independently investigating the same request and will write their own self-named reports ending in `__cdx.md` and `__cld.md` and `__grk.md` and `__mus.md`. Your report will end in `__gem.md`.

Conduct your research independently and form your own conclusions. Do NOT attempt to
locate, open, read, or otherwise consult the other researcher's report from this swarm,
even if it becomes available before you finish. Do not obtain that peer's findings
indirectly through its chat transcript, summaries, or requests to the peer. You may
independently use the same external sources, shared input material, and unrelated prior
research. You may check filenames or file existence to avoid overwriting your own
output, but do not inspect the peer's report contents. If you encounter its filename,
leave the report alone. The lead researcher will read every report and synthesize their
findings after you have all finished.

I suspect that it takes a very long time for sase agents to complete their commit
stages, but I'm not sure why that is. Can you do some research with the goal of helping
me figure this out? End your analysis with a recommended solution. 
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

# Investigation: SASE Agent Commit Stage Latency and Publication Drain Bottlenecks

**Researcher:** `research.5h.gem`  
**Report Artifact:** `file:explicit:07dc9741f708557e00b12388`  
**Report File:** [commit_stage_latency_and_publication_drain_root_cause__gem.md](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_28/sase/repos/research/202610/commit_stage_latency_and_publication_drain_root_cause__gem.md)  
**Artifact Registration:** `research:202610/commit_stage_latency_and_publication_drain_root_cause__gem.md`

---

## 1. Executive Summary & Findings

Your suspicion that SASE agents spend an excessive amount of time completing their commit stages is **fully confirmed**. Telemetry from recent agent runs demonstrates that commit stages frequently stall for **3.5 to 7.5 minutes (210s to 450s+)**.

However, the delay is **not** caused by Git operations:
1. **The actual Git commit & push takes only ~2.5 seconds (<1% of commit time)**: Adding files, creating the commit, syncing upstream (`git fetch` + `git rebase`), and pushing to origin consistently completes in 2.0 to 3.5 seconds.
2. **Pre-commit formatting overhead accounts for ~25 seconds (5%–10%)**: The configured `commit_hooks.before` runs `just fix` (Ruff, Prettier across all markdown, Keep-Sorted across all YAML, documentation renderers), scanning the entire 12,800+ file tree before any commit can occur.
3. **Post-commit publication and outbox draining accounts for 85% to 95% of the total elapsed time (~180s to 415s)**:
   - When an agent commits, [`CommitWorkflow`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_28/src/sase/workflows/commit/workflow.py#L132) calls [`run_agent_publication_step()`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_28/src/sase/workflows/commit/workflow_publication.py#L18), which executes three heavy synchronous operations: [`publish_bead_pages()`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_28/src/sase/workflows/commit/workflow_publication.py#L112), [`publish_prompt_archive()`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_28/src/sase/workflows/commit/workflow_publication.py#L144), and [`publish_committed_agent_hood()`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_28/src/sase/workflows/commit/workflow_publication.py#L198) (which calls [`drain_agent_publications()`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_28/src/sase/agents_sync/_commit_publication_drain.py#L112)).
   - In [`drain_agent_publications()`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_28/src/sase/agents_sync/_commit_publication_drain.py#L112), a full publication drain builds a project-wide hood inventory (scanning 1,190+ runs and ~10,000 Git subprocesses, taking ~35s) and plans/renders Markdown and chat logs across hoods (taking 75s to 145s+).
   - Drains consistently exceed the 120.0s `SIGALRM` bound (`DEFAULT_PUBLICATION_DRAIN_TIMEOUT_SECONDS`), raising `PublicationDrainTimedOut` (`alarm_fired: true`, `error_class: timeout`).
4. **Lock serialization and concurrency stampede on `sase-agents-sync.lock`**:
   - Both `publish_prompt_archive` and `drain_agent_publications` serialize on a single repository file lock (`sase-agents-sync.lock`).
   - When parallel agents (such as 5-researcher swarms) commit at approximately the same time, the first agent acquires the lock and holds it for 120s to 220s during its slow drain. Subsequent agents block on the lock until their timeout expires, or queue in a serialized cascade.
5. **Backlog feedback loop**:
   - Athena has accumulated **3,501 quarantined publication requests** and **10,393 artifact link outbox records**.
   - [`_drain_artifact_link_outbox_for_agent()`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_28/src/sase/workflows/commit/workflow_publication.py#L297) reads and partitions this entire 10,000+ item outbox, taking between **10 and 125 seconds** per commit even when the committing agent has zero qualifying link events.

---

## 2. Telemetry Evidence Summary

Production timing extracted from `attempt-1.main.steps.jsonl` across recent runs:

| Run ID | `just fix` (Before Hook) | Git Commit & Push | Post-Commit Publication Pipeline | Total Commit Stage |
|:---|:---:|:---:|:---:|:---:|
| `20261028170604` | 21.3s | 2.5s | **414.4s** | **438.3s (7.3 min)** |
| `20261028181409` | 32.0s | 2.8s | **288.4s** | **323.4s (5.4 min)** |
| `20261028200510` | 24.4s | 2.4s | **318.1s** | **345.0s (5.8 min)** |
| `20261028200849` | 28.0s | 2.6s | **184.2s** | **214.9s (3.6 min)** |
| `20261028204919` | 23.5s | 2.6s | **198.9s** | **225.0s (3.8 min)** |
| `20261028221057` | 22.1s | 2.5s | **196.9s** | **221.6s (3.7 min)** |

`sase doctor -C state.agent_publication_outbox -j` confirms:
- **Quarantined requests**: 3,767 (3,501 in `sase`, 266 in `bob-cli`)
- **Error classification histogram**: `timeout: 2,910`, `lock_busy: 439`, `other: 396`, `index_lock: 19`, `unstaged_changes: 6`

---

## 3. Recommended Solution

To reduce the commit stage duration from **~4 minutes to under 10 seconds** (a ~98% latency reduction):

1. **Decouple Publication Draining from the Synchronous Commit Path (Critical)**:
   - Modify [`publish_committed_agent_hood()`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_28/src/sase/agents_sync/_commit_publication_queue.py#L42) to **enqueue only**. It should write its entry to `agents-publication-outbox.json` (<5ms file append) and return immediately with `queued=True`, rather than executing `drain_agent_publications()`.
   - Modify [`_drain_artifact_link_outbox_for_agent()`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_28/src/sase/workflows/commit/workflow_publication.py#L297) to append pending events and defer outbox replay off the commit path.
2. **Handle Drains Asynchronously via Background Workers / Lumberjack**:
   - Schedule periodic background runs of `sase agent sync --project <project>` (e.g. every 5–10 minutes via a Lumberjack routine or daemon service).
   - This amortizes drain overhead across all agent commits and eliminates lock contention in agent workspaces.
3. **Reclaim Outbox Backlog & Clear Quarantined Entries**:
   - Run `sase agent sync --drop-retired` to drop permanently unpublishable entries.
   - Run bounded recovery for the 3,501 quarantined timeout entries (`sase agent sync --retry-quarantined --retry-limit 50 --retry-error-class timeout`).
   - Prune/compact the 10,393-item artifact link outbox.
4. **Scope Pre-Commit Hooks to Staged Files**:
   - Scope `commit_hooks.before` (`just fix`) to only format files modified in the commit (`git diff --cached --name-only`) rather than scanning all 12,800+ files in the repository. This drops pre-commit hook time from ~28s to <2s.

---

## 4. Deliverable

The complete, unabridged research report has been saved to:
- **Repository Path**: `/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_28/sase/repos/research/202610/commit_stage_latency_and_publication_drain_root_cause__gem.md`
- **Artifact Ref**: `file:explicit:07dc9741f708557e00b12388` (`research:202610/commit_stage_latency_and_publication_drain_root_cause__gem.md`)
