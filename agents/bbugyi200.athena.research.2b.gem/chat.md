# Chat History - ace-run (research.2b.gem)

- **TIMESTAMP:** 2026-09-23 09:37:20 EDT
- **MODEL:** agy/gemini-3.8-flash-high
- **AGENT:** research.2b.gem
- **PROMPT:** `~/.sase/multi_prompts/202609/gh_sase_org__sase-multiprompt-260923_092418.md`

## Prompt

%id(gem, clan=research.2b)
%m:agy/gemini-3.8-flash-high %q(w=0.25)
#gh:gh_sase-org__sase 
You are researcher gem in a 3-researcher swarm.
The other researchers, `research.2b.cld`, `research.2b.mus`, are independently investigating the same request and will write their own self-named reports ending in `__cld.md` and `__mus.md`. Your report will end in `__gem.md`.

Conduct your research independently and form your own conclusions. Do NOT attempt to
locate, open, read, or otherwise consult the other researcher's report from this swarm,
even if it becomes available before you finish. Do not obtain that peer's findings
indirectly through its chat transcript, summaries, or requests to the peer. You may
independently use the same external sources, shared input material, and unrelated prior
research. You may check filenames or file existence to avoid overwriting your own
output, but do not inspect the peer's report contents. If you encounter its filename,
leave the report alone. The lead researcher will read every report and synthesize their
findings after you have all finished.

I think I want to migrate the usage
window collector, which seems to run as a background proc periodically (and when
triggered by the user by pressing `u` on the "Refresh" panel) to a service proc.

- This seems more appropriate since background procs should generally be triggered by
  some user action I'm thinking (instead of, for example, some periodic process which
  might make the user why a proc is running when they shouldn't need to worry about / be
  disturbed by this).
- I also think this will allow us to start refreshing the usage windows a bit more
  frequently.
- Make sure we don't overwhelm providers and that we handle usage collection errors from
  individual providers in a graceful, robust, and reliable way.

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
(for example `research:202609/topic__a.md`), including any subdirectory the steps above
put it in. Do not derive the label from the current month, the clock, or a guessed name.
Do not pass `--move`; the source stays in the research repo for later reorganization. If
registration itself fails, report that failure — do not report the research task as
fully complete.

## Response

# Research Complete: Migrating the Usage Window Collector to a Service Proc

- **Author:** Researcher `gem` (`research.2b.gem`)
- **Report Location:** [`usage_window_collector_service_proc_migration__gem.md`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_29/sase/repos/research/202609/usage_window_collector_service_proc_migration__gem.md)
- **Durable Artifact Snapshot:** Registered via `sase artifact create` as `research:202609/usage_window_collector_service_proc_migration__gem.md` (`ref: file:explicit:5b004c2d343e0a91f975b633`).

---

## 1. Executive Summary & Verdict

### Is migrating to a service proc a good idea?
**Yes, with critical architectural caveats.**

Your intuition is spot-on:
1. **Semantic Isolation:** Background procs (`ProcSubmitRequest`) are meant for user tasks (agent runs, tests, monitors, explicit `!` commands). Having internal maintenance routines surface in `sase proc list` and the TUI Procs tab every 5 minutes violates user expectations and causes false alarms.
2. **Immediate Root Cause Identified:** The usage collector is *already* triggered by the AXE scheduler's `checks` routine (`sase_chop_usage_refresh.py`). However, its underlying invocation (`submit_usage_refresh` in [`refresh.py`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_29/src/sase/llm_provider/usage/refresh.py)) submits a `ProcSubmitRequest` that **omits the `service` metadata block** (`ProcServiceBlock`) and uses `shell_kind="proc"`. Consequently, [`is_service_row()`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_29/src/sase/ace/tui/_proc_observer_models.py#L112) evaluates to `False`, forcing the CLI and TUI to treat it as an ordinary unattributed user background command.
3. **The High-Frequency Polling Trap:** Lowering the refresh cadence to a static 60s (or 30s) across all providers 24/7 is an anti-pattern. Polling 5 providers (`agy`, `claude`, `codex`, `grok`, `muse`) every 60s while idle generates **7,200 external CLI/network calls per day**, risking Anthropic third-party OAuth compliance flags and HTTP 429 rate limits for data that does not change when no agents are running.
4. **The Cadence Floor:** The Rust backend (`crates/sase_core/src/provider_usage/mod.rs:69`) enforces a hard limit: `MIN_USAGE_CADENCE_SECONDS = 60.0`. Any cadence below 60s is strictly rejected by [`validate_refresh_cadence()`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_29/sase/repos/linked/sase-core/crates/sase_core/src/provider_usage/refresh.rs#L161).

---

## 2. Key Findings & Codebase Analysis

### 2.1 The Current Execution Pipeline
* **Trigger Sources:**
  1. **AXE Scheduler:** Runs `sase_job_usage_refresh` every 300s (5m) on the `checks` routine ([`default_config.yml:1240`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_29/src/sase/default_config.yml#L1240)).
  2. **ACE TUI Fallback:** [`_usage_refresh_fallback.py`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_29/src/sase/ace/tui/actions/_usage_refresh_fallback.py) runs an async loop submitting work every 300s when AXE is absent.
  3. **Refresh Panel `u` Key:** [`refresh_panel.py:153`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_29/src/sase/ace/tui/actions/refresh_panel.py#L153) dispatches `submit_usage_refresh(explicit=True)` in a thread worker.
* **Coordination:** Passes through Rust core's `admit_provider_usage_refresh()`, which manages atomic CAS leases (TTL 75s), preventing duplicate concurrent probes.
* **Execution:** Spawns a detached background proc running [`refresh_runner.py`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_29/src/sase/llm_provider/usage/refresh_runner.py), which launches worker subprocesses ([`worker.py`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_29/src/sase/llm_provider/usage/worker.py)) for each provider via `ThreadPoolExecutor(max_workers=3)`.
* **Failure:** Because no `service` block is attached to the `ProcSubmitRequest`, each run writes an unattributed row to `~/.sase/procs/procs.jsonl`.

### 2.2 Provider Probing Cost & Latency Profile
* **Claude:** `claude -p /usage` (~1.7s) + passive `rate_limit_event` streaming. *Warning:* High-frequency polling risks Anthropic OAuth compliance scrutiny.
* **Codex:** `codex app-server` JSON-RPC stdio (~1.0s).
* **Grok:** `grok agent stdio` ACP `_x.ai/billing` (~0.4s).
* **Antigravity (`agy`):** `agy -p /usage` (~1.8s). Hardcoded 2.0s version check easily times out under load.
* **Muse:** `muse serve` + echo session minting (~2.8s). Spawns an MSP server and waits 2.5s for credential minting on every probe.

---

## 3. Resilience & Error Handling Audit

### 3.1 Existing Strengths in the Rust Core
* **Exponential Backoff:** `refresh_backoff_seconds()` scales failed providers exponentially up to 1,800s (30m).
* **Per-Provider Isolation:** Each provider's schedule is tracked independently. A timeout in `agy` or `muse` never impedes `claude` or `codex`.
* **5.0s Cooldown:** [`USAGE_REFRESH_EXPLICIT_COOLDOWN_SECONDS`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_29/sase/repos/linked/sase-core/crates/sase_core/src/provider_usage/refresh.rs#L17) prevents rapid mashing of the `u` key.
* **Stale Preservation:** On error, the store marks cached windows as `stale` with an error diagnostic rather than wiping them to 0%.

### 3.2 Gaps Discovered
1. **Discarded `Retry-After`:** [`refresh_runner.py:198`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_29/src/sase/llm_provider/usage/refresh_runner.py#L198) fails to pass `retry_after_seconds` to `record_provider_usage_refresh_attempt()`, ignoring vendor 429 backoff headers.
2. **Rigid Version Check Timeouts:** `agy.py` and `grok.py` hardcode a 2.0s timeout for `--version`. Under system load, this causes false-positive probe failures.

---

## 4. Recommended Solution: The Hybrid Service Architecture

We recommend a **Tiered & Hybrid Architecture**:

```
+-------------------------------------------------------------------------------------------------+
|                                    RECOMMENDED ARCHITECTURE                                     |
+-------------------------------------------------------------------------------------------------+
|                                                                                                 |
|   +-----------------------------------------------------------------------------------------+   |
|   | sase service Host (systemd / launchd)                                                   |   |
|   |   -> service: scheduler (owns background automation)                                    |   |
|   |   -> service: usage_collector (daemon service proc)                                     |   |
|   |        - Async event loop (bypasses ProcSubmitRequest -> 0 procs.jsonl writes)          |   |
|   |        - Writes live status to ~/.sase/service/procs/usage_collector/status.json        |   |
|   |        - Listens on IPC trigger socket: ~/.sase/run/usage_collector.sock                |   |
|   +-----------------------------------------------------------------------------------------+   |
|                                         ^                                                       |
|                                         | 1. IPC Trigger (Immediate)                            |
|                                         |                                                       |
|   +-----------------------+             |               +-----------------------------------+   |
|   | Interactive Clients   |-------------+               | Fallback Path (Offline/No-Service)|   |
|   | - ACE 'u' Key Press   |                             | If daemon socket is unreachable:  |   |
|   | - CLI: usage refresh  |---------------------------->| Run direct in-process worker      |   |
|   | - 429 Rate Limit Event|                             | thread without error or delay     |   |
|   +-----------------------+                             +-----------------------------------+   |
|                                                                                                 |
+-------------------------------------------------------------------------------------------------+
```

### 4.1 Adaptive 3-Tier Cadence
Instead of static high-frequency polling:
* **Active Tier (60s):** Active while coding agents are running, ran within the last 15 minutes, or when any provider window is critical (< 20% remaining).
* **Passive Harvest (Instant, 0 Cost):** Capture Claude's `rate_limit_event` directly from active agent execution streams.
* **Idle Tier (300s–600s):** Backs off when the system has been idle for > 15 minutes, cutting idle calls by 80–90%.
* **Event-Driven Wakeup:** Triggers immediately when a window's `resets_at` timestamp is crossed (`reset_passed` in Rust store) or on user `u` key press.

---

## 5. Phased Implementation Plan

1. **Phase 1: Immediate Hygiene Fix (Quick Win, Zero Risk)**
   * In [`refresh.py:_submit_started_proc`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_29/src/sase/llm_provider/usage/refresh.py#L378), add:
     ```python
     service=ProcServiceBlock(name="usage-refresh", mode="oneshot", source="builtin"),
     shell_kind="service",
     origin=SERVICE_ONESHOT_ORIGIN,
     ```
   * *Outcome:* Immediately removes `usage-refresh` procs from `sase proc list` and the TUI Procs tab.
2. **Phase 2: Dedicated Daemon Service Proc**
   * Implement `sase usage daemon` in `src/sase/llm_provider/usage/daemon.py`.
   * Register `usage_collector` in [`default_config.yml`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_29/src/sase/default_config.yml) under `service.procs`.
   * Expose a lightweight Unix domain socket at `~/.sase/run/usage_collector.sock` for instant triggers from ACE (`u`) and CLI.
   * Add graceful in-process worker fallback in ACE when the service host is down.
3. **Phase 3: Cadence & Error Hardening**
   * Wire `retry_after_seconds` through to `record_provider_usage_refresh_attempt()`.
   * Increase `--version` check timeouts in `agy.py` and `grok.py` to 4.0s with memoization.
   * Implement the Active vs Idle adaptive cadence engine.

---

The complete research report with full comparative matrices and architectural diagrams is available in the research repository at [`usage_window_collector_service_proc_migration__gem.md`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_29/sase/repos/research/202609/usage_window_collector_service_proc_migration__gem.md).
