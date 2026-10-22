# Chat History - ace-run (research.3d.gem)

- **TIMESTAMP:** 2026-10-02 13:06:57 EDT
- **MODEL:** agy/gemini-3.8-flash-high
- **AGENT:** research.3d.gem
- **PROMPT:** `~/.sase/multi_prompts/202610/gh_sase_org__sase-multiprompt-261002_124445.md`

## Prompt

%id(gem, clan=research.3d)
%m:agy/gemini-3.8-flash-high %q(1.5x, w=0.25)
#gh:gh_sase-org__sase 
You are researcher gem in a 5-researcher swarm.
The other researchers, `research.3d.cdx`, `research.3d.cld`, `research.3d.grk`, `research.3d.mus`, are independently investigating the same request and will write their own self-named reports ending in `__cdx.md` and `__cld.md` and `__grk.md` and `__mus.md`. Your report will end in `__gem.md`.

Conduct your research independently and form your own conclusions. Do NOT attempt to
locate, open, read, or otherwise consult the other researcher's report from this swarm,
even if it becomes available before you finish. Do not obtain that peer's findings
indirectly through its chat transcript, summaries, or requests to the peer. You may
independently use the same external sources, shared input material, and unrelated prior
research. You may check filenames or file existence to avoid overwriting your own
output, but do not inspect the peer's report contents. If you encounter its filename,
leave the report alone. The lead researcher will read every report and synthesize their
findings after you have all finished.

Traversing through
the "current project" stack using the `<ctrl+n/p>` keymaps can be painfully slow in the
prompt input widget. Also, activating the prompt input widget using the `<space>` keymap
can be pretty slow sometimes too. It is very important that both of these operations are
very fast.

Can you do some research with the goal of helping me decide the best way to make these
keymaps work much faster? End your analysis with a recommended solution. 
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

# Research Summary: Optimizing Prompt Input Widget Activation and Project Stack Traversal Keymaps

**Researcher:** `research.3d.gem`  
**Report Artifact:** `file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_48/sase/repos/research/202610/prompt_input_keymap_performance_optimization__gem.md`  
**Artifact Reference:** `file:explicit:bb39d88961df7aa74464dcc7` (`research:202610/prompt_input_keymap_performance_optimization__gem.md`)

---

## 1. Root Cause Analysis

### A. `<ctrl+n>` and `<ctrl+p>` Project Stack Traversal in `PromptTextArea`
When cycling through the "current project" MRU ring using `<ctrl+n>` or `<ctrl+p>`, [`_handle_vcs_mru_cycle_key`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_48/src/sase/ace/tui/widgets/_vcs_mru_cycling.py#L385-L424) executes on **every single keystroke**. Profiling identified the following critical bottlenecks:

1. **Uncached Synchronous Disk & FFI Scans:**
   - [`load_launchable_vcs_xprompt_mru()`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_48/src/sase/history/vcs_xprompt_mru.py#L46-L65) possesses **zero caching**. Every keypress reads `~/.sase/vcs_xprompt_mru.json` from disk.
   - It invokes [`_resolvable_vcs_ref_index()`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_48/src/sase/history/vcs_xprompt_mru.py#L300-L323), which calls the Rust core [`list_project_records`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_48/src/sase/core/project_lifecycle_facade.py#L49-L70), runs `os.path.isdir()` on every project workspace, scans all patch files via [`find_all_patches_cached()`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_48/src/sase/ace/patch/cache.py#L102-L107), and builds project alias maps.
2. **$O(N \times M)$ Redundant Project File Parsing:**
   - For every entry in the MRU ring, [`_is_stale_known_project_prefix`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_48/src/sase/history/vcs_xprompt_mru.py#L263-L293) calls [`is_launchable_project`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_48/src/sase/ace/tui/modals/project_discovery.py#L64-L89), which re-invokes Rust core `list_project_records` **again**, re-reads and parses the project YAML spec on disk (`parse_workspace_dir`), checks `workspace_dir.exists()`, and dispatches pluggy hooks via [`detect_workflow_type()`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_48/src/sase/workspace_provider/_registry.py#L179-L194).
   - In addition, [`_vcs_prefix_provider_mismatched`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_48/src/sase/history/vcs_xprompt_mru.py#L388-L439) opens the project spec and calls `detect_workflow_type()` a second time.
3. **Synchronous Disk Writes on Keypresses:**
   - If an MRU entry is pruned during evaluation, [`_save_vcs_xprompt_mru()`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_48/src/sase/history/vcs_xprompt_mru.py#L174-L182) synchronously writes JSON back to disk on the main UI thread, directly violating Rule 11 of `sase/memory/tui_perf.md` (*"Keystroke paths are read-only and prompt-free"*).
4. **Triple Event Cascade:**
   - Applying `_replace_via_keyboard` fires `TextArea.Changed`, then `move_cursor` fires `TextArea.SelectionChanged`, and finally `_handle_vcs_mru_cycle_key` calls [`_on_prompt_completion_context_changed()`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_48/src/sase/ace/tui/widgets/_prompt_soft_completion.py#L138-L143) a third time in the exact same event cycle.
5. **Measured Latency:**
   - Cold run (first keypress): **~628 ms**.
   - Warm run (with only 7 entries): **~20.4 ms** per keypress.
   - Projected with 30–50 entries: **150–350 ms** per keypress (target frame budget is **< 16.6 ms**).

---

### B. `<space>` Prompt Widget Activation
When pressing `<space>` (`start_agent_from_patch`) from the main TUI window:
1. **Unnecessary Eager Evaluation of All 100 Entries:**
   - [`_resolve_vcs_xprompt_mru_head()`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_48/src/sase/ace/tui/actions/agent_workflow/_entry_custom.py#L14-L43) calls `load_launchable_vcs_xprompt_mru_pairs()`, which runs the full pruning, YAML-parsing, and humanization pipeline on all 100 entries just to obtain `pairs[0]`.
2. **Cold Import Penalties:**
   - On the first `<space>` press in a session, importing `sase.xprompt`, `sase-github`, `sase.ace.patch.cache`, etc., blocks the event loop for **400–650 ms**.
3. **Synchronous Teardown I/O:**
   - If an existing prompt bar contains unsubmitted text, [`_unmount_prompt_bar()`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_48/src/sase/ace/tui/actions/agent_workflow/_prompt_bar_mount.py#L201-L223) executes regex reference extraction and writes prompt history to disk synchronously.
4. **DOM Reconstruction & Layout Recalculation:**
   - A brand-new [`PromptInputBar`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_48/src/sase/ace/tui/widgets/prompt_input_bar.py#L84-L100) hierarchy (6 widgets) is constructed, mounted, and styled dynamically on every invocation.
5. **Worker Burst (GIL Contention) on Mount:**
   - In [`PromptInputBarLifecycleMixin.on_mount()`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_48/src/sase/ace/tui/widgets/_prompt_input_bar_lifecycle.py#L75-L110), **eight (8) concurrent background worker threads** are spawned simultaneously:
     - `prompt-vcs-project-catalog`
     - `artifact-ref-worker-group:0`
     - `model-completion-catalog`
     - `prompt-path-inventory`
     - `history-word-completion`
     - `prompt-prediction`
     - `dispatch-target-catalog`
     - `xprompt-target-stale-check`
   - Spawning 8 threads causes immediate GIL contention and thread-scheduling latency while Textual computes layout geometries.
   - Synchronous module imports inside `_refresh_dispatch_context_line()` add another **~27 ms** on the first mount.

---

## 2. Quantitative Benchmarks

| Component / Function | Uncached / Cold | Measured Warm Cache | Target Budget |
| :--- | :--- | :--- | :--- |
| `load_launchable_vcs_xprompt_mru()` | **628.13 ms** | **20.41 ms** (7 entries) | **< 1.0 ms** |
| `_resolvable_vcs_ref_index()` | 357.22 ms | 29.07 ms | N/A (cached) |
| `_is_stale_known_project_prefix()` (single entry) | 397.32 ms | 4.80–8.20 ms | **< 0.05 ms** |
| `detect_workflow_type()` (Pluggy hook dispatch) | 67.70 ms | 4.41 ms | **0.002 ms** (memoized) |
| `_resolve_vcs_xprompt_mru_head()` | **59.78–650 ms** | **23.35 ms** | **< 0.1 ms** |
| `os.stat()` on `vcs_xprompt_mru.json` | 0.015 ms | **0.0023 ms** (2.3 µs) | **< 0.01 ms** |
| `_refresh_dispatch_context_line()` | 26.85 ms | 0.059 ms | **< 0.1 ms** |

---

## 3. Recommended Solution Architecture

To make both operations fast without breaking existing semantics or tests, we recommend a cohesive **4-Tier Optimization Architecture**:

```
+-----------------------------------------------------------------------------------+
|                            ACE TUI Event Loop (Main Thread)                       |
+-----------------------------------------------------------------------------------+
       │                                                          │
       │ User presses <ctrl+n/p>                                  │ User presses <space>
       ▼                                                          ▼
+----------------------------------------+     +------------------------------------+
| VcsMruCyclingMixin                     |     | action_start_agent_from_patch      |
| - In-widget cached `_cached_vcs_mru`   |     | - Calls `resolve_vcs_xprompt_mru_  |
| - Batches cursor/change events         |     |   head()` (lazy evaluation)        |
+----------------------------------------+     +------------------------------------+
       │ (0.001 ms)                                               │ (0.002 ms)
       ▼                                                          ▼
+-----------------------------------------------------------------------------------+
| `sase.history.vcs_xprompt_mru` Memoization Layer                                  |
| - Fast `os.stat` token check on `vcs_xprompt_mru.json` (~2.3 µs)                  |
| - Returns cached `(canonical, display)` tuples directly                           |
| - Invalidation generation on `record_vcs_xprompt_usage()`                         |
| - Keystroke cycling uses `prune=False` (Strictly read-only, Rule 11)              |
+-----------------------------------------------------------------------------------+
       │ (On cache miss only)
       ▼
+-----------------------------------------------------------------------------------+
| Optimized Resolution Pipeline                                                     |
| - `detect_workflow_type` cached with `@lru_cache(maxsize=128)` (0.002 ms)         |
| - `_is_stale_known_project_prefix` reuses prebuilt `known_projects` map           |
| - Lazy evaluation terminates on index 0 when only head is required                |
+-----------------------------------------------------------------------------------+
```

### Tier 1: Stat-Token Memoization for `load_launchable_vcs_xprompt_mru_pairs`
- **File:** [`src/sase/history/vcs_xprompt_mru.py`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_48/src/sase/history/vcs_xprompt_mru.py)
- **Design:** Cache the filtered, launchable `(canonical_prefix, display_prefix)` pairs in memory keyed by `(st.st_mtime_ns, st.st_size)` of `vcs_xprompt_mru.json`.
- **Validation:** `os.stat` takes **2.3 microseconds**. If unchanged, return the cached list immediately.
- **Invalidation:** Add [`invalidate_vcs_xprompt_mru_cache()`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_48/src/sase/history/vcs_xprompt_mru.py), called automatically by [`record_vcs_xprompt_usage()`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_48/src/sase/history/vcs_xprompt_mru.py#L131-L172) and test fixtures.
- **Speedup:** Reduces execution time from **20–600 ms** to **0.002 ms** (10,000× speedup).

### Tier 2: In-Widget Session Ring & Read-Only Cycling
- **File:** [`src/sase/ace/tui/widgets/_vcs_mru_cycling.py`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_48/src/sase/ace/tui/widgets/_vcs_mru_cycling.py)
- **Design:**
  1. Cache `self._cached_vcs_mru` on [`PromptTextArea`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_48/src/sase/ace/tui/widgets/prompt_text_area.py#L82-L113) while active. Traversal keypresses read directly from memory (0.001 ms).
  2. Pass `prune=False` during keymap cycling so cycling never triggers synchronous disk writes.
  3. Add a batching flag (`self._cycling_vcs_mru = True`) around text replacement to suppress the redundant 2nd and 3rd calls to `_on_prompt_completion_context_changed()`.

### Tier 3: Lazy Head Resolution for `<space>` Activation
- **File:** [`src/sase/history/vcs_xprompt_mru.py`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_48/src/sase/history/vcs_xprompt_mru.py) & [`src/sase/ace/tui/actions/agent_workflow/_entry_custom.py`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_48/src/sase/ace/tui/actions/agent_workflow/_entry_custom.py)
- **Design:** Add `resolve_vcs_xprompt_mru_head()`. If the cache is warm, return `cached_pairs[0]`. If cold, lazily test entries starting at index 0 and return immediately upon the first valid entry.
- **Benefit:** Avoids evaluating 99 unused entries when opening the prompt bar.

### Tier 4: Pluggy Hook Caching & Mount Worker Staggering
- **Files:** [`src/sase/workspace_provider/_registry.py`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_48/src/sase/workspace_provider/_registry.py) & [`src/sase/ace/tui/widgets/_prompt_input_bar_lifecycle.py`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_48/src/sase/ace/tui/widgets/_prompt_input_bar_lifecycle.py)
- **Design:**
  1. Decorate `detect_workflow_type` with `@lru_cache(maxsize=128)` (cleared in `reset_workflow_metadata_caches`). Reduces detection from **67 ms** to **0.002 ms**.
  2. In `_is_stale_known_project_prefix`, reuse the `known_projects` map from `_resolvable_vcs_ref_index` instead of re-scanning all project records.
  3. Stagger non-essential background completion warmers in `on_mount()` (e.g. model completion, prediction, history word catalogs) by 50 ms via `self.set_timer(0.05, ...)`. This eliminates the 8-thread GIL burst on the mount frame.
  4. Hoist lazy imports in `_refresh_dispatch_context_line()` to module scope to eliminate the 27 ms first-mount delay.

---

## 4. Verification and Artifact Registration

The complete, unabridged research report has been written and durably registered:
- **Report Path:** `/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_48/sase/repos/research/202610/prompt_input_keymap_performance_optimization__gem.md`
- **Registration Command:** `sase artifact create -p "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_48/sase/repos/research/202610/prompt_input_keymap_performance_optimization__gem.md" -l "research:202610/prompt_input_keymap_performance_optimization__gem.md"`
- **Artifact ID:** `explicit:bb39d88961df7aa74464dcc7`
- **Final Declaration:** Submitted and accepted (`builtin@commit`).
