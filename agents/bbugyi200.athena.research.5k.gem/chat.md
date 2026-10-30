# Chat History - ace-run (research.5k.gem)

- **TIMESTAMP:** 2026-10-30 17:06:17 EDT
- **MODEL:** agy/gemini-3.8-flash-high
- **AGENT:** research.5k.gem
- **PROMPT:** `~/.sase/multi_prompts/202610/gh_sase_org__sase-multiprompt-261030_164448.md`

## Prompt

%id(gem, clan=research.5k)
%m:agy/gemini-3.8-flash-high %q(1.5x, w=0.25)
#gh:gh_sase-org__sase 
You are researcher gem in a 5-researcher swarm.
The other researchers, `research.5k.cdx`, `research.5k.cld`, `research.5k.grk`, `research.5k.mus`, are independently investigating the same request and will write their own self-named reports ending in `__cdx.md` and `__cld.md` and `__grk.md` and `__mus.md`. Your report will end in `__gem.md`.

Conduct your research independently and form your own conclusions. Do NOT attempt to
locate, open, read, or otherwise consult the other researcher's report from this swarm,
even if it becomes available before you finish. Do not obtain that peer's findings
indirectly through its chat transcript, summaries, or requests to the peer. You may
independently use the same external sources, shared input material, and unrelated prior
research. You may check filenames or file existence to avoid overwriting your own
output, but do not inspect the peer's report contents. If you encounter its filename,
leave the report alone. The lead researcher will read every report and synthesize their
findings after you have all finished.

The TUI has slowed down again lately. Can you do some research with the goal of helping
me speed things up again? Make sure you prioritize good architecture choices and
reliability (don't break anything). End your analysis with a recommended solution. 
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

# Research Report: SASE TUI Slowdown Root-Cause Analysis and Architectural Remedies

**Author:** Researcher `gem` (`research.5k.gem`)  
**Report File:** [`tui_slowdown_root_cause_and_architecture_fixes__gem.md`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_13/sase/repos/research/202610/tui_slowdown_root_cause_and_architecture_fixes__gem.md)  
**Registered Artifact Ref:** [`file:explicit:b4ab2b7898738e828fb75480`](file:///home/bryan/.sase/artifacts/agents/gh_sase-org__sase/20261030164453/tui_slowdown_root_cause_and_architecture_fixes__gem-275916cacbf9.md)  
**Artifact Label:** `research:202610/tui_slowdown_root_cause_and_architecture_fixes__gem.md`

---

## 1. Executive Summary

A forensic investigation of the live SASE Textual TUI (`athena`, PID `2704211`, instance [`f8c86c23`](file:///home/bryan/.sase/logs/tui_stalls.jsonl)) reveals that recent user-visible slowness, $j$/$k$ navigation lag, and multi-second UI freezes are **not** caused by layout calculations or rendering algorithms. 

Instead, the slowness is driven by a **catastrophic feedback loop between unbounded heap bloat, Linux kernel swap thrashing, and stop-the-world Python cyclic garbage collection**:

- **Massive Memory Footprint:** The active TUI process has expanded to **29.1 GB virtual memory**, **15.6 GB RSS**, and **7.85 GB of anonymous memory pushed to swap**.
- **Stop-the-World Freeze Amplification:** In CPython, cyclic GC ([`gc.collect`](file:///home/bryan/.local/share/uv/tools/sase/lib/python3.14/site-packages/textual/app.py)) must traverse all container objects in Generation 2. Because 7.85 GB of heap structures reside in swap, cyclic GC triggers bursts of major page faults (`major_faults_delta > 140` per GC pause). Pauses that should take <50 ms escalate into **5 to 32-second complete freezes**. Because the Python GIL is held throughout cyclic collection, the main Textual event loop and all background worker threads are completely locked.
- **`tools/tui_freeze_report` Failure:** Over an observed 6,651-second window, the TUI was frozen for **847.88 seconds (12.75% of wall time)**, with GC alone consuming **710.43 seconds (10.68% of wall time)**. The idle full-generation GC $p95$ reached **5.47 seconds** (limit $\le 500$ ms), and peak loop hitches reached **23.98 seconds**.

---

## 2. Subsystem Root Causes

### A. Monolithic Unbounded JSON Registries
- **[`agent_name_registry.json`](file:///home/bryan/.sase/agent_name_registry.json) (37 MB, 28,258 entries):** Deserializing this 37 MB JSON file creates over 28,000 top-level dicts, consuming ~350–500 MB of Python heap. During staleness checks in [`_registry_file_is_stale`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_13/src/sase/agent/names/_registry_store.py#L152-L167), [`entry_owner_missing`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_13/src/sase/agent/names/_registry_entries.py#L84-L107) executes over **28,000 filesystem `stat()` calls** on disk. Detail panel renders also query this registry via [`_snapshot_agent_name_registry`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_13/src/sase/ace/tui/models/agent_page_url.py#L85-L118).
- **[`dismissed_agents.json`](file:///home/bryan/.sase/dismissed_agents.json) (4.7 MB, 83,592 entries):** On every full agent disk load, the TUI parses 4.7 MB of JSON into a set of 83,592 Python tuples, passing it across asynchronous thread boundaries. Although already mirrored in SQLite (83,592 rows in [`agent_artifact_index.sqlite`](file:///home/bryan/.sase/agent_artifact_index.sqlite)), the Python layer continues to load and pass the monolithic JSON in memory.
- *Prior Debt Note:* Linked `sase-core` commit messages specifically cite this unresolved debt: *"JSON-registry retention gap (agent_name_registry.json/dismissed_agents.json) left for a dedicated follow-up."*

### B. Full-Load Refresh Stampedes
- In [`tui_agent_loads.jsonl`](file:///home/bryan/.sase/logs/tui_agent_loads.jsonl), the TUI recorded **298 slow agent loads** in a 2-hour span, including **175+ full-history loads** (averaging one full load every 40 seconds).
- A full load takes **25 to 71 seconds** (`index` taking up to 64.3s scanning the 323 MB SQLite database, `decode` taking 23.8s, and `prep` taking 4–6.5s).
- Because a full load exceeds the periodic tick interval, subsequent triggers ([`auto_refresh`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_13/src/sase/ace/tui/actions/event_refresh/_watcher.py), [`roster_completion_retry`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_13/src/sase/ace/tui/actions/agents/_loading_filter.py), [`input_quiet_tier2_reconcile`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_13/src/sase/ace/tui/actions/agents/_loading_filter.py)) trigger overlapping disk loads, saturating the 16-worker thread pool and contending on [`agent_artifact_index_operation_lock`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_13/src/sase/core/agent_artifact_index_lock.py#L17-L21).

### C. Textual `Strip` Self-Cycles & Option Prompt Churn
- In Textual 8.2.8, every [`Strip`](file:///home/bryan/.local/share/uv/tools/sase/lib/python3.14/site-packages/textual/strip.py) instance allocates **seven separate `FIFOCache` instances**.
- In [`Strip.crop`](file:///home/bryan/.local/share/uv/tools/sase/lib/python3.14/site-packages/textual/strip.py), cropped child strips are stored inside the parent's `_crop_cache`, generating self-referencing and cross-referencing cycles.
- Because Python's reference counting cannot collect cyclic garbage, discarded strips survive until Generation 2 GC runs.
- In [`_agent_list_build_patch_single.py`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_13/src/sase/ace/tui/widgets/_agent_list_build_patch_single.py#L39-L198), calling [`replace_option_prompt_at_index`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_13/src/sase/ace/tui/widgets/_agent_list_build_patch_single.py#L192) without a content equality guard continuously drops and rebuilds lines, generating millions of cyclic `Strip` instances that accumulate in Gen 2.

### D. Flaws in Prior GC Policy (`sase-1ez` / `sase-1nf.14.1`)
- Calling `gc.freeze()` at startup only protected startup objects; 99.9% of objects are allocated during runtime.
- Raising `threshold2 = 10,000` worsened the problem: by delaying Generation 2 collection, garbage accumulated unchecked until memory exceeded physical RAM and spilled into swap (7.85 GB), converting what would have been 50 ms pauses into 32-second system freezes.

---

## 3. Recommended Architectural Solution

A four-pillar architectural action plan is detailed in the report:

```
+---------------------------------------------------------------------------------------------------+
|                                   THE FOUR-PILLAR ARCHITECTURAL FIX                               |
|                                                                                                   |
|  +--------------------------------+                  +-----------------------------------------+  |
|  | Pillar 1: Native SQLite Stores |                  | Pillar 2: Single-Flight Refresh Coalesce |  |
|  | • Move name & dismissal checks |                  | • Hard single-flight mutex on loads     |  |
|  |   into sase-core SQLite        |                  | • Deduplicate concurrent full refreshes |  |
|  | • 30-day retention pruning     |                  | • Exponential backoff on retries        |  |
|  | • Eliminate 37MB JSON parse    |                  | • Relax revalidation cadence (15 min)   |  |
|  +--------------------------------+                  +-----------------------------------------+  |
|                 |                                                          |                      |
|                 +----------------------------+-----------------------------+                      |
|                                              |                                                    |
|                                              v                                                    |
|  +-------------------------------------------+-------------------------------------------------+  |
|  | Pillar 3: Explicit Cycle Breaking         | Pillar 4: Proactive Memory Pressure Watchdog    |  |
|  | • Weak references for Agent graphs        | • Cap RSS at 2.0 GB; proactive malloc_trim      |  |
|  | • Invalidate Textual Strip FIFOCaches     | • Re-tune threshold2 to 2,000 (frequent, fast)  |  |
|  | • Equality guard on Option replacement    | • Zero-tolerance for VmSwap > 50 MB             |  |
|  +-------------------------------------------+-------------------------------------------------+  |
+---------------------------------------------------------------------------------------------------+
```

1. **Pillar 1: Migrate Monolithic Registries to Native SQLite in `sase-core`**
   - Query `dismissed_agents` (83,592 rows already in [`agent_artifact_index.sqlite`](file:///home/bryan/.sase/agent_artifact_index.sqlite)) via a fast indexed Rust binding (`is_agent_dismissed()`), eliminating the 4.7 MB JSON parse.
   - Migrate `agent_name_registry` schema to SQLite, replacing the 37 MB JSON file and 28,000 Python `stat()` calls with an indexed database query.
   - Implement `sase agent registry prune --older-than 30d` to archive stale records.

2. **Pillar 2: Single-Flight Refresh Coalescing & Rate Limiting**
   - Introduce a `SingleFlightCoordinator` in [`_loading_disk_full.py`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_13/src/sase/ace/tui/actions/agents/_loading_disk_full.py) so concurrent triggers share the single in-flight disk load rather than queueing up to 16 redundant worker threads.
   - Relax `tier1_index_revalidate` cadence to 15 minutes and apply exponential backoff (1s, 2s, 4s, 8s, up to 60s) to `roster_completion_retry`.

3. **Pillar 3: Explicit Cycle Breaking & Render Strip Decoupling**
   - In [`_agent_list_build_patch_single.py`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_13/src/sase/ace/tui/widgets/_agent_list_build_patch_single.py#L39-L198), compare `current_option.prompt == new_option.prompt` before calling `replace_option_prompt_at_index`, preventing redundant `Strip` churn.
   - Explicitly clear `_crop_cache` and `_divide_cache` on discarded `Strip` instances upon row removal/unmount.
   - Decouple bidirectional strong references in [`Agent`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_13/src/sase/ace/tui/models/agent.py) hierarchies using `weakref`.

4. **Pillar 4: Proactive Memory Pressure Management in `GCPolicy`**
   - Re-tune `threshold2` down from 10,000 to **2,000**: small, frequent Gen-2 collections take <100 ms and keep the heap compact.
   - In [`gc_policy.py`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_13/src/sase/ace/tui/util/gc_policy.py), enforce a hard RSS soft ceiling (2.0 GB) and swap alert (50 MB). When exceeded, trigger an idle collection and invoke `malloc_trim(0)` off-thread to return memory to the OS before paging begins.

---

## 4. Verification and Artifact Registration

- **Research Markdown File:** [`sase/repos/research/202610/tui_slowdown_root_cause_and_architecture_fixes__gem.md`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_13/sase/repos/research/202610/tui_slowdown_root_cause_and_architecture_fixes__gem.md)
- **Artifact Creation Command:**
  ```bash
  sase artifact create \
    -p "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_13/sase/repos/research/202610/tui_slowdown_root_cause_and_architecture_fixes__gem.md" \
    -l "research:202610/tui_slowdown_root_cause_and_architecture_fixes__gem.md"
  ```
- **Result:** Snapshot successfully created (`id: explicit:b4ab2b7898738e828fb75480`).
- **SASE Finalizer:** Turn finalized and declaration submitted via `/sase_final` (`repo-a9361c74969c` commit staged for host completion).
