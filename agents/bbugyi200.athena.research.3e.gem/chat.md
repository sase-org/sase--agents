# Chat History - ace-run (research.3e.gem)

- **TIMESTAMP:** 2026-10-02 14:33:04 EDT
- **MODEL:** agy/gemini-3.8-flash-high
- **AGENT:** research.3e.gem
- **PROMPT:** `~/.sase/multi_prompts/202610/gh_sase_org__sase-multiprompt-261002_141852.md`

## Prompt

%id(gem, clan=research.3e)
%m:agy/gemini-3.8-flash-high %q(1.5x, w=0.25)
#gh:gh_sase-org__sase 
You are researcher gem in a 5-researcher swarm.
The other researchers, `research.3e.cdx`, `research.3e.cld`, `research.3e.grk`, `research.3e.mus`, are independently investigating the same request and will write their own self-named reports ending in `__cdx.md` and `__cld.md` and `__grk.md` and `__mus.md`. Your report will end in `__gem.md`.

Conduct your research independently and form your own conclusions. Do NOT attempt to
locate, open, read, or otherwise consult the other researcher's report from this swarm,
even if it becomes available before you finish. Do not obtain that peer's findings
indirectly through its chat transcript, summaries, or requests to the peer. You may
independently use the same external sources, shared input material, and unrelated prior
research. You may check filenames or file existence to avoid overwriting your own
output, but do not inspect the peer's report contents. If you encounter its filename,
leave the report alone. The lead researcher will read every report and synthesize their
findings after you have all finished.

The
prompt_space_and_project_cycle_latency.md file in the research sidecar repo is reporting
that the TUI is frozen 10% of the time?! Can you dig into the logs / profiling data we
have available and do some research with the goal of helping me fix this issue? End your
analysis with a recommended solution. 
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

### Research Summary: TUI Event-Loop Stall Budget & Memory Growth Forensics

A forensic analysis of the live ACE TUI process (PID 872820, running `sase tui` for >26 hours) and historical telemetry logs (`~/.sase/logs/tui_stalls.jsonl*`, `tui_agent_loads.jsonl*`, and `tui.log`) confirms that the TUI has been spending **between 11.2% and 13.5% of total wall-clock time completely frozen** in multi-second event-loop hitches.

---

### Key Quantitative Findings

From the 3.93-hour telemetry window (10:27 to 14:24 today):
- **413 event-loop hitches** ($\ge 1.5$ s) were recorded, totaling **1,590.3 seconds (26.5 minutes)** of frozen UI time (**11.23% of total wall time**).
- When including message pump stalls and recovery transitions, total frozen time reaches **1,912.4 seconds (13.54% of wall time)**.
- **Hitch Duration Profile:** Median (p50) duration is **3.85 s**, 90th percentile (p90) is **5.05 s**, and the single maximum freeze reached **10.06 s**. During active periods, freezes recur every 1 to 2 minutes.
- **Process Memory Growth:** Process RSS has grown from the ~2.5 GB reported in August 2026 (epic `sase-v2` / bead `sase-v3`) to **6.08 GB RSS** (~9.68 GB VSZ) across 16–26 active threads, of which **97.1% is private anonymous heap**.

---

### Root Causes

The freezes are driven by two interacting mechanisms:

#### 1. 6 GB Heap Bloat and Stop-the-World Generation-2 Garbage Collection (64.2% of stall time)
- **Heap Bloat Drivers:** In Textual 8.2.8 (`textual/strip.py`), each `Strip` instance instantiates **seven `FIFOCache` objects**, each containing a dictionary (15 Python objects per strip). Repainting lists with 400+ agents and multiple card blocks churns tens of thousands of `Strip` instances per minute. In addition, module-level caches (`_artifact_state` with 65k entries, `normalized_dirs` with 16k entries, `_aggregate_wires_cache`, and unbounded `_CLEANED_ARTIFACT_DIRS`) retain millions of objects across a long session.
- **Stop-the-World Pauses:** In CPython, when gen-1 collections exceed the threshold, **generation 2 executes a full collection** that must traverse every cyclic object across the entire 6 GB heap. Benchmarked pauses scale from ~50 ms at 1M simple objects to **445–600 ms** at 1M rich objects, and reach **2.5–5.0 seconds** across a 6 GB heap.
- **GIL Starvation:** In 57.9% of recovery events (1,116 s), the main thread was trapped sleeping in `selectors.poll` / `_read_from_self`. When background worker threads (`asyncio_0` ... `asyncio_12`) allocate memory and trigger GC while parsing agent artifact deltas, the worker holds the GIL during the multi-second collection, starving the main UI thread. In another 19.7% of mid-stall captures, the main thread was paused at trivial allocation sites (`cache.__init__`, `enum.__hash__`, `Text.__init__`).

#### 2. Heavy Synchronous Work on the UI Event Loop (35.8% of stall time)
- **Countdown Tick Aggregation (19.5% of hitches):** `_on_countdown_tick` fires every 1.0 s without an idle activity gate. Every second, `_patch_agent_runtime_rows` invokes `aggregate_clan_runtime`, which executes `[asdict(member) for member in members]` across all clan members, serializing dataclasses to dicts and bridging to Rust. Concurrently, `_update_agents_info_panel_impl` executes `compiled_profile_for_builtin_pane`, running `json.dumps()` and blake2b hashing every second.
- **Fleet Refresh & Clan Tree Projection (14.6% of hitches):** While `_run_agents_fleet_refresh` awaits network I/O asynchronously, `project_fleet_agents(...)` runs synchronously on the main thread. It normalizes remote host nodes, executes `sort_and_reorder`, `project_clan_tree`, and `resolve_clan_tribe` for all remote agents, blocking the loop for 2 to 4 seconds.
- **Agent Detail Debouncer & Content Digest (12.7% of hitches):** `renderable_content_digest` recursively walks every node in the Rich renderable tree and computes digests, formatting strings for every single Rich `Span` and `Style` (`f"{span.start}:{span.end}:{_style_digest_token(span.style)}"`). This caused 62 mid-stall hitches and 230 seconds of freeze time.
- **UI-Thread Thread Creation (4.5% of hitches):** `current_config_token()` polls every 5 seconds. When the deadline expires, it calls `Thread.start()`. In Python 3.14 on Linux, `Thread.start()` blocks synchronously on `self._started.wait()`, taking up to 5–7 seconds under thread/GIL contention.

---

### Recommended Solution Architecture

1. **Track 1: Memory & GC Pause Elimination (Target: −64% Freeze Time)**
   - Call `gc.collect(); gc.freeze()` immediately after initial agent load completion (`_mark_startup_agents_ready`). Moving existing objects to the permanent generation reduces full GC traversal pauses from 500+ ms down to $<10$ ms.
   - Re-freeze during extended idle windows ($>60$ s without keypresses).
   - Adjust collection thresholds via `gc.set_threshold(5000, 20, 25)` to prevent aggressive gen-2 triggers under high ephemeral allocation churn.
   - Bound long-lived accumulators (`_CLEANED_ARTIFACT_DIRS`, `_aggregate_wires_cache`).
2. **Track 2: Offload CPU-Bound Operations from the Main Thread (Target: −27% Freeze Time)**
   - Run `project_fleet_agents` in a worker thread (`await asyncio.to_thread(...)`) inside `_run_agents_fleet_refresh`.
   - Replace the per-tick `aggregate_clan_runtime` + `asdict()` bridge with in-memory timestamp math (`elapsed = base_elapsed + (now - last_sync)`), re-evaluating in Rust only on status or roster changes.
   - Optimize `renderable_content_digest` by replacing string formatting for spans with packed integer bytes (`struct.pack("<qqq", span.start, span.end, hash(style))`).
3. **Track 3: Remove Thread Creation from the UI Loop (Target: −5% Freeze Time)**
   - In `current_config_token()`, delegate background config refreshes to the shared thread pool rather than instantiating and starting a new OS thread on the UI thread.
4. **Track 4: Throttle Idle Countdown Ticks (Target: −4% Freeze Time)**
   - Memoize query profile compilation in `_update_agents_info_panel_impl`.
   - Throttle runtime suffix row patching from 1.0 s to 5.0 s when no agents are in active states.

---

### Artifacts & Deliverables

1. **Research Report:**
   - Absolute Path: `/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_40/sase/repos/research/202610/tui_stall_budget_and_event_loop_freezes__gem.md`
   - Repo-Relative Path: `202610/tui_stall_budget_and_event_loop_freezes__gem.md`
2. **Registered Artifact Snapshot:**
   - Reference: `file:explicit:72448e1fb467b98322321877`
   - Label: `research:202610/tui_stall_budget_and_event_loop_freezes__gem.md`
3. **Turn Finalization:**
   - SASE finalizer manifest submitted and accepted (`Accepted final declaration for: commit`).
