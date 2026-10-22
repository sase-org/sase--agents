# Chat History - ace-run (research.40.gem)

- **TIMESTAMP:** 2026-10-07 13:19:46 EDT
- **MODEL:** agy/gemini-3.8-flash-high
- **AGENT:** research.40.gem
- **PROMPT:** `~/.sase/multi_prompts/202610/gh_sase_org__sase-multiprompt-261007_130213.md`

## Prompt

%id(gem, clan=research.40)
%m:agy/gemini-3.8-flash-high %q(1.5x, w=0.25)
#gh:gh_sase-org__sase 
You are researcher gem in a 5-researcher swarm.
The other researchers, `research.40.cdx`, `research.40.cld`, `research.40.grk`, `research.40.mus`, are independently investigating the same request and will write their own self-named reports ending in `__cdx.md` and `__cld.md` and `__grk.md` and `__mus.md`. Your report will end in `__gem.md`.

Conduct your research independently and form your own conclusions. Do NOT attempt to
locate, open, read, or otherwise consult the other researcher's report from this swarm,
even if it becomes available before you finish. Do not obtain that peer's findings
indirectly through its chat transcript, summaries, or requests to the peer. You may
independently use the same external sources, shared input material, and unrelated prior
research. You may check filenames or file existence to avoid overwriting your own
output, but do not inspect the peer's report contents. If you encounter its filename,
leave the report alone. The lead researcher will read every report and synthesize their
findings after you have all finished.

I've been thinking that some of the builtin routines and/or jobs that exist currently
might be better suited as service procs. For example, wouldn't it be better if the
`wait_checks` job was instead a service proc that could wake up agents that are ready
sooner?

Can you do some research with the goal of recommending which jobs (if any) I should
migrate to service procs? Also, critique this plan in general. Is this a good idea?
Would you take a different approach? Make any adjustments to the requirements that you
think are justified but clearly call these out. End your analysis with a recommended
solution. 
Write this research to a new markdown file under the $(sase repo path research --ensure)/$(date +%Y%m)/ directory.
Choose a descriptive filename stem yourself, but the filename MUST end with the
`__gem` suffix, i.e. `<stem>__gem.md` (double underscore before the
suffix). Create the report without overwrite: if the exact file already exists, pick a
different stem instead of replacing it.


After the write succeeds, register the report as a durable snapshot:

sase artifact create -p "<absolute-report-path>" -l "research:<repo-relative-report-path>"

Use the report's actual absolute path and its path relative to the research repo root
(for example `research:202609/topic__a.md`), including any subdirectory the steps above
put it in. Do not derive the label from the current month, the clock, or a guessed name.
Do not pass `--move`; the source stays in the research repo for later reorganization. If
registration itself fails, report that failure — do not report the research task as
fully complete.

## Response

# Research Report Summary: Evaluating Job and Routine Migration to Service Procs

**Researcher:** `research.40.gem`  
**Report File:** [`migrating_jobs_to_service_procs_evaluation__gem.md`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_23/sase/repos/research/202610/migrating_jobs_to_service_procs_evaluation__gem.md)  
**Registered Artifact:** `ref: file:explicit:1f5ab01315b5fa560ac4e5dd` (`research:202610/migrating_jobs_to_service_procs_evaluation__gem.md`)

---

## 1. Executive Verdict & Core Critique

### Is migrating builtin jobs/routines to service procs a good idea?
**No. Migrating periodic or triggered background automation jobs into `service.procs` is an architectural antipattern and a category error.**

1. **Subsystem Hierarchy Inversion:** In SASE, `service.procs` is reserved for **machine-level host daemons** (specifically the `scheduler` orchestrator and the `gateway` HTTP server). The `scheduler` service proc was created explicitly so background automation would *not* require ad-hoc, uncoordinated host daemons.
2. **Loss of Operational Governance:** Service procs are supervised directly by the host process (`sase service run`) via systemd/launchd. They bypass:
   - **AXE Maintenance Mode:** `sase axe maintenance enter` pauses routine ticks during upgrades, migrations, and plugin installs. Service procs are completely blind to maintenance mode.
   - **Unified Metrics & Observability:** AXE tracks cycle duration metrics (`AXE_CYCLE_DURATION`), tick frequencies (`AXE_CYCLES`), and errors (`AXE_ERRORS`). Service procs only log process exits.
   - **Concurrency & Runner Pool Limits:** AXE coordinates global agent execution via `SharedRunnerPool` (`max_agent_runners`, `max_hook_runners`). Service procs operate outside runner limits.
   - **TUI Services Presentation:** The Services tab cleanly separates "Service Procs" (infrastructure daemons) from "Scheduled Routines" (lifecycle jobs with cycle history, status chips, and next-run timers).
3. **Audit Result (0 of 29 Jobs):** An exhaustive audit of all 29 builtin jobs across SASE's 7 routines (`hooks`, `waits`, `checks`, `usage`, `comments`, `external_mirror`, `housekeeping`) reveals that **zero jobs** qualify for migration to service procs.

---

## 2. Deconstructing the `wait_checks` Latency Fallacy

The user noted: *"Wouldn't it be better if the `wait_checks` job was instead a service proc that could wake up agents that are ready sooner?"*

While the desire for faster wake-up latency is valid, turning `wait_checks` into a service proc does not solve the problem:

1. **Service Procs Do Not Provide Inherent Event-Driven Reactivity:** A service proc is simply a standalone OS process. If implemented as a polling loop (`while True: check(); sleep(1)`), it wastes CPU scanning dozens of project directories outside AXE. If fast polling were acceptable, one could simply configure the existing `waits` routine interval from 10s to 2s without changing any code or architecture.
2. **Technical Pitfalls of an inotify/Watcher Daemon:**
   - **OS Watch Limits:** SASE workspaces hold thousands of run directories under `projects/<proj>/artifacts/ace-run/<YYYYMM>/<DD>/<run_id>/`. Recursive inotify watchers risk exhausting `/proc/sys/fs/inotify/max_user_watches`.
   - **Event Storms:** Running agents continuously write log chunks, token counters, and tool calls into their artifact directory. An inotify daemon would suffer dozens of false-alarm wakeups per second.
   - **Non-Filesystem Dependencies:** Waiting markers also wait on **closed beads** (`wait_for_beads`), which live in project stores (`beads.jsonl`) or git sidecar repositories. An inotify watcher on `ace-run` would be blind to bead closures.
   - **Partial Write Races:** When an agent finishes, writing `done.json` is not instantaneous with updating metadata, indexes, or successor markers. This is why `wait_checks` includes a two-phase `confirm_dependency_resolution` check. Immediate triggering increases race conditions.
3. **Disproportionate ROI:** SASE agent turns involve LLM reasoning, code edits, and test runs taking **30 to 180 seconds**. Shaving 4 to 6 seconds off an occasional 10-second wait barrier represents <5% of total workflow duration—a poor return on investment for introducing daemon complexity and process fragmentation.

---

## 3. The Litmus Test: What Actually Belongs in `service.procs`?

A background task belongs in `service.procs` if and only if it satisfies at least one of these criteria:
1. **Persistent Socket/Network Listener:** Binds a network port, Unix socket, or IPC FIFO (e.g., `gateway` HTTP API, future LSP or WebSocket servers).
2. **Real-time Push Stream Consumer:** Keeps a persistent connection open to an external service (e.g., `sase-telegram`'s `telegram_receiver` long-polling the Telegram API).
3. **Top-Level Process Supervisor:** Supervises a hierarchy of child worker processes (e.g., the `scheduler` orchestrator).
4. **Stateful In-Memory Engine:** Holds heavy, persistent in-memory models, indexes, or caches that cannot be reloaded from disk on each tick.

Every current job in SASE is a **batch reconciler or poller** (reads disk/API state, diffs, acts, and exits)—which is the textbook definition of an AXE job (chop).

---

## 4. Requirements Reframing & Adjustments

- **Original Request:** Migrate builtin jobs/routines to service procs to wake agents faster.
- **Adjusted Requirement:** **Minimize agent `%wait` resolution latency from ~10s to ~2s while preserving single-tree supervision, resource frugality, and transactional safety.**

---

## 5. Recommended Solution: Four-Tier Evolutionary Roadmap

### Tier 1: Cadence Tuning & Lane Rebalancing (Immediate / Zero Code Risk)
- **Option A (Move to `hooks`):** Move `wait_checks` from the `waits` routine (10s interval) to the `hooks` routine (5s interval).
  - Because `wait_checks` already has an `fs` trigger on `projects/*/artifacts/ace-run/*`, idle ticks cost only a handful of fast `stat()` calls.
  - Immediately cuts average wakeup latency from ~6s to ~2.5s.
- **Option B (Tune `waits`):** Reduce `axe.routines.waits.interval` in `src/sase/default_config.yml` from `10` to `3` or `5`. All other jobs in `waits` are either trigger-guarded or throttled via `run_every: "30s"`.

### Tier 2: Waiting Runner Optimization (Minor Code Change)
- In `src/sase/axe/run_agent_wait.py`, the waiting runner already polls for `ready.json` every 2s (`_WAIT_POLL_INTERVAL = 2`), but its direct resolution fallback interval is throttled to 60s (`_WAIT_DEPENDENCY_FALLBACK_INTERVAL = 60.0`).
- Reduce this fallback interval to **5.0s–10.0s** for lightweight dependency checks. When waiting on a single predecessor agent, the parked runner can directly verify `done.json` inline and self-wake without waiting for AXE.

### Tier 3: Producer-Side Completion Signaling (Event-Driven Without Daemons)
- When an agent finishes in `run_agent_exec_finalize.py`, or when a bead closes in `sase bead close`:
  - Touch a lightweight trigger hint file (extending the existing `mark_bead_wait_sync_hint` pattern).
  - The `waits` routine watches this hint file and executes immediately upon predecessor completion, achieving sub-second resolution without continuous polling.

### Tier 4: Event-Aware Scheduler Orchestrator (Long-Term Architecture)
- If SASE eventually needs broad sub-second reactivity across background automation, **modernize the `scheduler` service proc itself**.
- Add an inotify/event-loop thread to the Orchestrator that signals specific routine processes to trigger early when watched paths change.
- This delivers instant event-driven responsiveness while preserving unified supervision, maintenance mode, and error telemetry.

---

## 6. Durable Snapshot Registration

The full research report has been saved and registered as requested:
- **Report Path:** `/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_23/sase/repos/research/202610/migrating_jobs_to_service_procs_evaluation__gem.md`
- **Registration Command:**
  ```bash
  sase artifact create -p "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_23/sase/repos/research/202610/migrating_jobs_to_service_procs_evaluation__gem.md" -l "research:202610/migrating_jobs_to_service_procs_evaluation__gem.md"
  ```
- **Created Artifact Reference:** `file:explicit:1f5ab01315b5fa560ac4e5dd`

The finalizer declaration has been submitted and accepted for the `commit` payload (`repo-e029ea166d96` / `sdd:research`). The host finalizer will commit the work after this turn ends.
