# Chat History - ace-run (research.3e.image)

- **TIMESTAMP:** 2026-10-02 15:49:43 EDT
- **MODEL:** agy/gemini-3.8-flash-high
- **AGENT:** research.3e.image
- **PROMPT:** `~/.sase/multi_prompts/202610/gh_sase_org__sase-multiprompt-261002_141852.md`

## Prompt

%id(image, clan=research.3e) %m:@image
%wait:research.3e.final %q(1.5x, w=0.25) #gh:gh_sase-org__sase 
%xprompts_enabled:false
# Previous Continuation

This fork uses versioned continuation replay. Blocks are stable, parent-first projections of exact continuation nodes; any historical source without recoverable node provenance is represented as an opaque legacy boundary.

- **Projection version:** `1`
- **Ordered nodes:** `1`

## Continuation Block `block:v1:c89dc88d2349fd5cb9ec1b5a79260405`

- **Node:** `agent-delta:20261002141857:232aa000da2ae23d`
- **Kind:** `agent_delta`
- **Parents:** (none)
- **Content:** `local:continuation/records/agent_delta/agent-delta:20261002141857:232aa000da2ae23d.json`

### User

**Protected user instruction.** Carry this request unless an explicit attributed update supersedes it.

%clan(research.3e, tribe=research, summary=[[[bold]RESEARCH PROMPT:[/bold] The
prompt_space_and_project_cycle_latency.md file in the research sidecar repo is reporting
that the TUI is frozen 10% of the time?! Can you dig into the logs / profiling data we
have available and do some research with the goal of helping me fix this issue? End your
analysis with a recommended solution.]]) %id:research.3e.final %m:@xlarge
%wait:research.3e.cdx %wait:research.3e.cld %wait:research.3e.grk %wait:research.3e.mus %wait:research.3e.gem %q(1.5x, w=0.25)
#gh:gh_sase-org__sase 
You are the lead researcher: 5 independent researchers have reported on the request
below, and you will add your own research and merge every perspective into one
consolidated report.

SASE derives your plan's links from the artifacts you read this turn; use
`sase artifact read` for context you actually used.

Research request:

The
prompt_space_and_project_cycle_latency.md file in the research sidecar repo is reporting
that the TUI is frozen 10% of the time?! Can you dig into the logs / profiling data we
have available and do some research with the goal of helping me fix this issue? End your
analysis with a recommended solution.

The researchers' registered reports:

{% for a in wait.artifacts if a.kind == "markdown" and a.label and a.label.startswith("research:") %}
- wait_name={{ a.wait_name }} label={{ a.label }} source_path={{ a.source_path }} path={{ a.path }} ref={{ a.ref }}
{% endfor %}

Month directory (create it if missing):

$(sase repo path research --ensure)/$(date +%Y%m)

Steps:

1. From the registered reports above, identify exactly one report per expected suffix
   in cdx, cld, grk, mus, gem, belonging to this
   dispatch's `research.3e.cdx`, `research.3e.cld`, `research.3e.grk`, `research.3e.mus`, `research.3e.gem` dependencies, matching by `wait_name` and the canonical research
   label's existing `__<suffix>.md` suffix. Never reassign suffixes from list order.
   Open the research repo with `/sase_repo`, then read each report through its canonical
   research reference (or the `ref` field's `file:<id>` reference if the original has
   moved) using `sase artifact read`. Do not read predecessor chat transcripts. If the
   records above do not identify exactly one report per expected suffix, stop and report
   the missing or ambiguous input instead of guessing.
2. Research the request yourself, prioritizing gaps, weak evidence, and disagreements
   between the reports.
3. Pick a descriptive stem `<name>` that collides with nothing in the month directory
   (do NOT end the name with `_consolidated` or `_<YYYYmmdd>` or anything similar unless
   it relates to the research topic), create `<month-dir>/<name>/`, and move each report
   inside it as `<name>__<suffix>.md`, preserving its existing suffix. Each report's
   `source_path` is provenance for where it lives in your own opened research checkout;
   resolve its canonical repo-relative path there before moving it. Never modify the
   other agents' checkouts or the stored snapshot recorded at `ref` — only the copy in
   your own checkout moves. Preserve every file and never overwrite: on any collision,
   pick a different stem first.
4. Write the consolidated report to `<name>/<name>__final.md`: merge the strongest findings
   from every report above and your own research, resolve conflicts, cut duplication,
   and add missing critical context without unnecessary length.

   Do not create `<name>/<name>.md`, not even as a placeholder, because the linker
   agent `research.3e.linker` publishes it from your report.

5. After the write succeeds, register the consolidated report as a durable snapshot so
   the linker agent, `research.3e.linker`, can find it:

   sase artifact create -p "<absolute-report-path>" -l "research:<repo-relative-report-path>"

   Use the consolidated report's actual absolute path and its path relative to the
   research repo root, for example `research:202609/<name>/<name>__final.md`. Register
   only the consolidated report, and do not pass `--move`. If registration fails,
   report that failure; do not report the task as fully complete.

Final layout:

```text
<month-dir>/<name>/
├── <name>__cdx.md
├── <name>__cld.md
├── <name>__grk.md
├── <name>__mus.md
├── <name>__gem.md
└── <name>__final.md
```

### Assistant

The TUI really is frozen about 10% of the time, and the logs actually understate it. Most of the frozen time is Python's full garbage collection, which stops every thread at once. It is made worse by a cache bug that keeps old copies of large files in memory, so the heap keeps growing.

**What the evidence shows:**
- **It comes back soon after a restart.** All five researchers reproduced the figure from the stall log: about 11.2% of the time between 10:28 and 14:24. The TUI restarted at 14:24:47 and logged no freezes for 18 minutes. It was back at 12.9% frozen by 15:02–15:20.
- **Full garbage collection is the cause.** I timed collections inside the running TUI from 15:24 to 15:27, about an hour after the restart:
  - 13 full collections, one every 11–18 s, each lasting 1.8–3.1 s (median 2.16 s).
  - That is 16.7% of the time in full collections alone, and 25.5% in all garbage collection.
  - Every freeze the log recorded with a late detection overlapped one of these collections.
  - 8 of the 13 ran on background threads. A collection on any thread blocks the UI, so moving more work off the UI thread won't help.
- **The freeze log misses most of these.** 7 of the 13 collections, each about 2–3 s, left no freeze record. Only 2 of those were counted as dropped by the log's 4-per-minute cap.
- **Memory grows fast.** The TUI went from 1.48 GB at 14:31 to 4.66 GB plus 1.46 GB in swap by 15:20. Each collection takes longer as the heap grows, and much longer once part of it is in swap.
- **The cache bug is confirmed.** The artifact-index and artifact-links caches key entries on file modification time and size, and keep up to 32 or 64 old versions instead of one. Agents append to these files constantly, so each append adds another full copy. At 15:28 the TUI held 22 copies of the 26.8k-row artifact index and 10 copies of the 35k-row links snapshot. Other things are growing too, so this bug is not the whole story.
- **The rest is genuine UI work, about 1.5–3% of the time.** The worst offenders are the 1-second countdown tick, fleet projection, the prompt-panel digest, and the config check that starts a new thread every 5 s. The `<space>` and `<ctrl+n/p>` keys from the original report account for only 1.6%.

**Recommended solution**, as one small epic:
1. **Log every collection's length and the memory size**, and make the freeze log notice when its own thread was blocked. Without this, no later fix can be checked.
2. **Fix the caches** to keep one current copy per file or scope, and add a test that enforces it.
3. **Change when full collections run:**
   - freeze the startup objects once, so later collections skip them;
   - raise the setting that triggers automatic full collections so they become rare (`gc.set_threshold(2000, 10, 10_000)`);
   - run full collections only after about 3 s with no key or mouse input, with a backstop after 5 minutes or 500 MB of growth.

   Each collection today frees only 50k–80k objects, so waiting for idle time costs little memory.
4. **Then reduce how many short-lived objects pile up:** stop copying every notification on each read, and make the slow agent reloads cheaper.
5. **Then trim the per-second UI-thread work** listed above.

Steps 2 and 3 need to ship together. The cache fix alone makes each collection shorter but more frequent, so about 15% of the time would still be lost. The new collection timing alone lets memory keep growing between the forced backstop collections. Until they land, restarting the TUI buys about 18 freeze-free minutes.

Running the timing probe meant briefly injecting a small script into your live TUI. I tested it on a dummy process first and removed it afterwards. It barely affects the TUI, so the 15:24–15:28 rows in your stall log are still usable.

The final report is `research:202610/tui_freeze_gc_heap_bloat/tui_freeze_gc_heap_bloat__final.md`, registered as `file:explicit:794d7cea81907ca122112af5`. The five researcher reports are in the same folder, and the host commits the folder once this turn ends.

---

%xprompts_enabled:true
# New Query

 Generate an infographic that illustrates the main points made in this research markdown
file. Write the image to `<stem>_infographic.png` in the same directory, where
`<stem>` is the source file's stem with any trailing `__final` removed (so
`topic__final.md` becomes `topic_infographic.png`; other stems are unchanged).
Create it without overwrite. If it already exists, stop and report the collision.


## Response

An infographic illustrating the core findings, telemetry models, and recommendations from the consolidated research report has been generated and written without collision or overwrite:

- **Source Report:** [`tui_freeze_gc_heap_bloat__final.md`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/sase/repos/research/202610/tui_freeze_gc_heap_bloat/tui_freeze_gc_heap_bloat__final.md)
- **Target File:** [`tui_freeze_gc_heap_bloat_infographic.png`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/sase/repos/research/202610/tui_freeze_gc_heap_bloat/tui_freeze_gc_heap_bloat_infographic.png) (848×1264 PNG)

### Main Points Illustrated in the Infographic

1. **The 10% Figure & Watchdog Undercount:**
   - 11.2% wall time inside ≥1.5 s hitches in the stall log.
   - Clean restart exhibits 0% freezes for 18 minutes, returning to 12.9% within 40 minutes.
   - Watchdog missed 7 of 13 full collections due to rate limits and GIL wake races; real frozen duration is 16–25%.

2. **Direct Measurement — Stop-The-World Gen-2 GC:**
   - Generation-2 (Full) GC constitutes 16.7% of wall time (25.5% of all GC time).
   - 13 full collections observed across 179 s (every 11–18 s), each lasting 1.8–3.1 s (p50: 2.16 s).
   - 8 of 13 collections triggered on background worker threads, stopping all threads via the GIL and freezing the UI.

3. **Heap Bloat & Swap Cascade:**
   - Rapid heap growth of ~100 MB/min (1.5 GB to 4.7 GB RSS + 1.5 GB swap).
   - Snapshot cache keying bug: keys on `(mtime_ns, size)` and retains 32–64 superseded copies of the 26.8k-row artifact index (~0.9 GB).
   - Sweeping swap-backed memory blocks spikes major page faults up to 2,764/s, transforming 1 s pauses into 3–10 s stalls.

4. **Mathematical GC Model:**
   - $\text{Pause} \approx c \cdot L$ (where $L$ is old-gen size, $c$ spikes in swap).
   - $\text{Interval} \approx 0.25 \cdot L / r$ (where $r$ is the medium-lived object promotion rate).
   - $\text{Frozen Share} = \frac{\text{Pause}}{\text{Interval}} \approx 4 \cdot c \cdot r$ (independent of heap size).

5. **5-Step Recommended Epic:**
   - **Step 1:** Telemetry & instrumentation (`gc.callbacks` timing, RSS/swap heartbeat, watchdog self-lateness).
   - **Step 2:** Snapshot caches bound by logical path/scope with tail parsing on appends.
   - **Step 3:** Idle-time Gen-2 GC policy (single startup freeze, `threshold2 = 10,000`, idle collections after 3 s inactivity).
   - **Step 4:** Reduce promotion rate (stop deep copying notifications, migrate `LinkIndex` to `sase_core`).
   - **Step 5:** UI-thread optimization (compare-then-skip on 1 s countdown tick, off-loop fleet projection).
