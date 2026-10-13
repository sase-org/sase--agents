# Chat History - ace-run (research.4c.gem)

- **TIMESTAMP:** 2026-10-13 09:28:09 EDT
- **MODEL:** agy/gemini-3.8-flash-high
- **AGENT:** research.4c.gem
- **PROMPT:** `~/.sase/multi_prompts/202610/gh_sase_org__sase-multiprompt-261013_090356.md`

## Prompt

%id(gem, clan=research.4c)
%m:agy/gemini-3.8-flash-high %q(1.5x, w=0.25)
#gh:gh_sase-org__sase 
You are researcher gem in a 5-researcher swarm.
The other researchers, `research.4c.cdx`, `research.4c.cld`, `research.4c.grk`, `research.4c.mus`, are independently investigating the same request and will write their own self-named reports ending in `__cdx.md` and `__cld.md` and `__grk.md` and `__mus.md`. Your report will end in `__gem.md`.

Conduct your research independently and form your own conclusions. Do NOT attempt to
locate, open, read, or otherwise consult the other researcher's report from this swarm,
even if it becomes available before you finish. Do not obtain that peer's findings
indirectly through its chat transcript, summaries, or requests to the peer. You may
independently use the same external sources, shared input material, and unrelated prior
research. You may check filenames or file existence to avoid overwriting your own
output, but do not inspect the peer's report contents. If you encounter its filename,
leave the report alone. The lead researcher will read every report and synthesize their
findings after you have all finished.

It
is taking a very long time to startup sase's TUI on my apollo machine. Can you do help
me profile that machine and sase's startup? End your analysis with a ranked list of
changes you think I should consider making in order to improve the TUI's startup on that
machine (or in general). 
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

# Research Report: Profiling SASE TUI Startup on Apollo and Optimization Roadmap

**Researcher:** `research.4c.gem`  
**Report File:** [`apollo_tui_startup_profiling_and_optimization__gem.md`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/sase/repos/research/202610/apollo_tui_startup_profiling_and_optimization__gem.md)  
**Artifact Registration:** `research:202610/apollo_tui_startup_profiling_and_optimization__gem.md` (`file:explicit:1c0c97383f85b8798e8c7461`)

---

## Executive Summary

An empirical investigation of the slow startup of SASE's TUI on `apollo` was conducted via remote profiling, telemetry logs (`~/.sase/logs/tui_startup.jsonl`, `tui_agent_loads.jsonl`, `tui_stalls.jsonl`), runtime thread stack traces, and scoped `pyinstrument` profiling.

### Key Discoveries

1. **Massive Latency Degradation (4.6s → 78.9s):**
   - Telemetry from `tui_startup.jsonl` shows `agents_ready_seconds` on `apollo` was **~4.6s** in late August 2026.
   - It rose to **15.2s** on Oct 12, **55.5s** earlier today, and peaked at **78.95 seconds** (`visible_ready_seconds: 75.79s`) on the current session.
   - In contrast, on `athena` (bare-metal Threadripper), `agents_ready_seconds` is consistently **4.1s–4.9s**.

2. **Severe Machine & I/O Disparity:**
   - **CPU:** `apollo` is a 16-vCPU KVM guest running 2.70 GHz Intel Xeon Platinum 8168 processors (Skylake-SP, 2017) with lower clock speed and IPC than `athena`'s 32-core / 64-thread 4.55 GHz Threadripper 3970X.
   - **Disk I/O:** `apollo`'s virtual disk (`/dev/vda1`, ext4 over virtio) has a synchronous write throughput of **84.3 MB/s** versus `athena`'s NVMe at **1.2 GB/s** (**14.2× slower disk write throughput**).
   - **Host Workload Sched-Delay:** `apollo`'s 1-minute load average was **10.50 to 12.60** out of 16 vCPUs, saturated by two long-running `mypy` processes (each burning 100% of a core in workspaces `sase_16` and `sase_12`), `sase tool wait`, background AXE routine runners, `codex`, and `muse`.

3. **The 3.0-Second Deferred Startup Fallback Stampede:**
   - In [`src/sase/ace/tui/actions/_startup_loads_core.py`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/src/sase/ace/tui/actions/_startup_loads_core.py#L10), `_STARTUP_DEFERRED_FALLBACK_SECONDS` is hardcoded to **3.0 seconds**.
   - On `apollo`, loading the visible Agents tab takes longer than 3.0 seconds under load. At $t = 3.0\text{s}$, the fallback timer triggers unconditionally, unleashing an avalanche of 15+ concurrent background workers (macro catalog rebuilding, link graph indexing, axe status collection, bead checks) into the asyncio event loop and thread pool while the visible surface is still reading disk.

4. **Quadratic Entry-Point Re-discovery in Prompt & Macro Loading (Critical Bug):**
   - Direct Pyinstrument profiling of `build_prompt_catalog_snapshot()` on `apollo` revealed that it takes **20.6 seconds** of CPU time.
   - **Over 17.1 seconds (83%)** is spent inside `_discovery_snapshot` calling `importlib.metadata.entry_points(group=group)`.
   - In [`src/sase/macro/_loader_parsing_inputs.py`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/src/sase/macro/_loader_parsing_inputs.py#L30), `_plugin_registry_snapshot()` calls `get_plugin_input_type_registry()` without memoized files, causing Python to repeatedly scan `entry_points.txt` across all installed packages on disk for *every single input field of every macro and workflow*.

5. **Relation Graph Explosion (44,321 Links):**
   - `load_artifact_links_snapshot(None)` on `apollo` contains **44,321 link rows**.
   - [`link_index_for_snapshot()`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/src/sase/ace/tui/relations/link_index.py#L136) takes **7.39 seconds** of pure Python computation to index these links, running Rust FFI label queries, string canonicalizations, and alias lookups. Scheduled right after the 3-second fallback, it monopolizes the CPython Global Interpreter Lock (GIL).

6. **Agent Dataset Scale (965 Agents):**
   - `apollo` tracks **965 agents** in its loader pool (vs **23** on `athena`).
   - The UI thread `apply` phase alone takes **5.2 seconds** on `apollo`, computing DOM node hierarchies, resolving clan summaries via FFI, and re-evaluating Textual CSS stylesheet rules across hundreds of widgets.

7. **GIL Starvation & Event Loop Freezes:**
   - Because all background workers run in Python threads (`asyncio.to_thread`), they fiercely contend for the CPython 3.12 GIL.
   - The stall watchdog recorded message pump stalls of **5.4s to 7.5s** and event loop stalls of **5.2s to 6.4s**, completely freezing the user interface during startup.

---

## Machine & Hardware Comparison

| Attribute | Apollo | Athena | Comparison |
| :--- | :--- | :--- | :--- |
| **Environment** | KVM Guest (VM) | Bare Metal | Virtualized vs Bare Metal |
| **CPU Model** | Intel Xeon Platinum 8168 @ 2.70GHz | AMD Ryzen Threadripper 3970X | Skylake-SP (2017) vs Zen 2 (2019) |
| **Core Count** | 16 vCPUs | 64 threads (32 cores / 64 threads) | 4× parallel capacity on Athena |
| **L3 Cache** | 64 MiB | 128 MiB | 2× cache on Athena |
| **Root Disk** | `/dev/vda1` (virtio ext4) | `/dev/nvme0n1p2` (PCIe NVMe ext4) | Virtual disk vs direct NVMe |
| **Sync Write Throughput** | **84.3 MB/s** (100MB dsync: 1.24s) | **1.2 GB/s** (100MB dsync: 0.09s) | **14.2× slower disk write on Apollo** |
| **Active Load Average** | **10.50 – 12.60** (70–80% CPU utilized) | **0.85 – 1.10** (idle) | Severe CPU overcommit on Apollo |

---

## Ranked List of Recommended Optimizations

### Rank 1: Memoize Plugin Entry Points in Macro Input Parsing (Critical Bugfix)
- **Impact:** **−17.1 seconds** on `apollo` startup; eliminates 83% of `build_prompt_catalog_snapshot()` CPU time.
- **Target Files:** [`src/sase/macro/plugin_input_types.py`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/src/sase/macro/plugin_input_types.py) & [`src/sase/main/plugin_discovery.py`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/src/sase/main/plugin_discovery.py)
- **Proposed Change:**
  - Cache `discover_macro_plugin_distributions()` and `discover_macro_plugin_input_type_files()` at module level with an `@functools.cache` or process-lifetime memo.
  - In `get_plugin_input_type_registry()`, reuse the cached entry-point list instead of repeatedly hitting `importlib.metadata.entry_points()` and reading `.dist-info/entry_points.txt` from disk for every single input field.
- **Effort / Risk:** Low effort (<20 lines of code), zero behavioral risk.

---

### Rank 2: Extend or Dynamically Gate the Deferred Startup Fallback Timer (High Impact)
- **Impact:** **−20 to −30 seconds** on `apollo`; eliminates GIL and disk contention during initial visible paint.
- **Target File:** [`src/sase/ace/tui/actions/_startup_loads_core.py`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/src/sase/ace/tui/actions/_startup_loads_core.py#L10)
- **Proposed Change:**
  - Increase `_STARTUP_DEFERRED_FALLBACK_SECONDS` from 3.0s to at least **15.0s**, or make it dynamically scale with system load.
  - Better yet: gate deferred maintenance (`prompt_catalog`, `link_index_refresh`, `update_attempts`) on `_agents_first_load_done == True` rather than an arbitrary wall-clock timer, ensuring the visible surface completes its load with exclusive CPU/disk priority.
- **Effort / Risk:** Low effort (adjusting timer constant and gating condition), very low risk.

---

### Rank 3: Optimize Link Index Generation via Rust Core or Prefiltering (High Impact)
- **Impact:** **−5.5 to −6.5 seconds** on `apollo`; prevents a 7.4s GIL freeze.
- **Target Subsystem:** [`src/sase/ace/tui/relations/link_index.py`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/src/sase/ace/tui/relations/link_index.py) & `sase_core` crate
- **Proposed Change:**
  - **Move `_build_link_index` to Rust Core:** In accordance with the Rust Core Backend Boundary rule, heavy graph and index logic belongs in `sase_core`. Rust can build the 44k-row indexed map in <20ms and expose a zero-copy lookup interface to Python.
  - **Short-Term Python Optimization:** Filter links to only currently visible entities (the active project or currently displayed agents) rather than constructing a whole-world index of 44,321 historic rows on startup.
- **Effort / Risk:** Medium effort; high return.

---

### Rank 4: Viewport-Cap Initial Agent Roster Ingestion on Startup (High Impact)
- **Impact:** **−4 to −6 seconds** on `apollo`; cuts initial `stages_seconds["disk"]` and UI-thread `apply` latency.
- **Target Files:** [`src/sase/ace/tui/models/agent_loader.py`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/src/sase/ace/tui/models/agent_loader.py) & [`src/sase/ace/tui/actions/agents/_loading_disk_full.py`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/src/sase/ace/tui/actions/agents/_loading_disk_full.py)
- **Proposed Change:**
  - For the initial startup refresh (`source == "startup"`), enforce a bounded viewport limit (e.g. top 50 or 100 most recent agents) via `query_agent_artifact_index_bounded`.
  - Ingest the remaining 850+ older historical rows in the background only after `visible_ready` has fired and the UI is interactive.
- **Effort / Risk:** Medium effort; high UX impact.

---

### Rank 5: Pre-import `repro.capture` and Hot Modules off the UI Thread (Medium Impact)
- **Impact:** **−2 to −4 seconds**; eliminates stall watchdog hitches during initial render.
- **Target Files:** [`src/sase/ace/tui/actions/agents/_loading_disk_full.py`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/src/sase/ace/tui/actions/agents/_loading_disk_full.py#L271) & [`src/sase/ace/tui/actions/_startup_mount.py`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/src/sase/ace/tui/actions/_startup_mount.py)
- **Proposed Change:**
  - Add `sase.ace.tui.repro.capture` and related runtime modules to early warmup lists (`PROMPT_BAR_FIRST_MOUNT_MODULES` or early startup imports) so module discovery and compilation do not stall the UI event loop thread.
- **Effort / Risk:** Low effort; zero risk.

---

### Rank 6: Throttle Background AXE Routines & Mypy Contention on Apollo (Machine Level)
- **Impact:** Immediate reduction of Apollo load average from 12.0 to ~2.0, giving SASE full CPU slice allocation.
- **Target:** Machine-level background process management on `apollo`.
- **Proposed Actions:**
  - Check why two background `mypy` processes were running indefinitely at 100% CPU in workspaces `sase_16` and `sase_12`. Kill or renice them with `nice -n 19 ionice -c 3`.
  - When launching the TUI interactively on `apollo`, consider using `sase tui --no-axe` (`-x`) if service procs and background git syncs are not immediately needed, or configure AXE routine intervals to be less aggressive during user-present sessions.
- **Effort / Risk:** Operational fix; immediate benefit.

---

## Projected Startup Impact

| Optimization | Estimated Time Saved on Apollo |
| :--- | :--- |
| **Rank 1: Macro Entry-Point Memoization** | **~17 seconds** |
| **Rank 2: Defer Maintenance until Agents Ready** | **~25 seconds** (contention eliminated) |
| **Rank 3: Rust Core Link Index / Bounded Links** | **~6 seconds** |
| **Rank 4: Viewport-Capped Startup Agent Load** | **~4 seconds** |
| **Rank 5: Pre-import Module Warmup** | **~3 seconds** |
| **Rank 6: Apollo Background Load Mitigation** | **~10–15 seconds** |
| **Total Projected Startup Time on Apollo** | **Reduced from ~78s to ~5–8s (~90% improvement)** |

---

## Artifact Registration Confirmation

The full technical research document has been written and registered:
- **Local Path:** `/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/sase/repos/research/202610/apollo_tui_startup_profiling_and_optimization__gem.md`
- **Artifact Ref:** `file:explicit:1c0c97383f85b8798e8c7461`
- **Registered Label:** `research:202610/apollo_tui_startup_profiling_and_optimization__gem.md`
- **Output Variable:** `artifacts[0]`

Finalizer declaration successfully submitted and accepted for `commit` (`sdd:research`). Work will be committed by the host finalizer upon turn completion.
