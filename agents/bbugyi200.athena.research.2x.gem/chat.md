# Chat History - ace-run (research.2x.gem)

- **TIMESTAMP:** 2026-09-30 06:22:35 EDT
- **MODEL:** agy/gemini-3.8-flash-high
- **AGENT:** research.2x.gem
- **PROMPT:** `~/.sase/multi_prompts/202609/gh_sase_org__sase-multiprompt-260930_060703.md`

## Prompt

%id(gem, clan=research.2x)
%m:agy/gemini-3.8-flash-high %q(1.5x, w=0.25)
#gh:gh_sase-org__sase 
You are researcher gem in a 5-researcher swarm.
The other researchers, `research.2x.cdx`, `research.2x.cld`, `research.2x.grk`, `research.2x.mus`, are independently investigating the same request and will write their own self-named reports ending in `__cdx.md` and `__cld.md` and `__grk.md` and `__mus.md`. Your report will end in `__gem.md`.

Conduct your research independently and form your own conclusions. Do NOT attempt to
locate, open, read, or otherwise consult the other researcher's report from this swarm,
even if it becomes available before you finish. Do not obtain that peer's findings
indirectly through its chat transcript, summaries, or requests to the peer. You may
independently use the same external sources, shared input material, and unrelated prior
research. You may check filenames or file existence to avoid overwriting your own
output, but do not inspect the peer's report contents. If you encounter its filename,
leave the report alone. The lead researcher will read every report and synthesize their
findings after you have all finished.

I just used the `,u`
keymap on the "Agents" tab to mark all unread nodes as read, but it didn't seem to work
(see the ~/tmp/screenshots/20260930_060248.png screenshot for context). The unread
indicators have been a bit flakey in general and always very slow (when using the `,j`
keymap, for example). I would like to make the TUI much more responsive when working
with these indicators. I'm not sure how to implement this, but my first thought was that
we could use a proc to run any expensive work (anything that causes a delay in the TUI)
in the background.

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

Marking command launch and waiting for background execution to complete.
Waiting for background load and unread reconcile simulation task to complete.
Waiting for background reconcile test task to finish.
Waiting for task-230 to finish.
# Research Report Summary: Agents Tab Unread Responsiveness & Architecture Critique

**Report Artifact:** [`research:202609/agents_tab_unread_indicators_performance__gem.md`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_48/sase/repos/research/202609/agents_tab_unread_indicators_performance__gem.md)  
**Registered Artifact Reference:** `file:explicit:a36e8f1ae8ca633991c26cab`  
**Researcher:** `research.2x.gem` (Swarm Member `__gem`)

---

### 1. Visual Evidence & Root Causes from Screenshot (`20260930_060248.png`)

In screenshot `20260930_060248.png`, the top banner shows `204 [3 running · 28 waiting · 5 failed · 27 unread · 146 done]`. The user cursor is positioned on `0u0` inside `@default`, which itself has **0 unread nodes**. 

All **27 unread indicators** are located outside the focused node, nested inside **collapsed clan containers and collapsed tribes**:
- **Tribe `@epic` [W26 F5 U21 D127]** (21 unread):
  - Under `Failed`: `sase-1d5` (U2), `sase-1cx` (U2), `sase-1cj.12` (U2), `sase-1co` (U1), `sase-1ck` (U5) — *12 unread nodes*.
  - Under `Done`: `sase-1cu` (U4), `sase-1ck.5.1` (U3), `sase-1cq` (U1), `sase-1cp` (U1) — *9 unread nodes*.
- **Tribe `@job` [R1 U6 D2]** (6 unread):
  - Collapsed tribe banner containing 6 unread nodes.

#### Why `,u` (`mark_all_unread_done_agents_read`) Failed:
1. **Collapsed Clan & Hierarchy Blindspot:** `_toggle_all_unread_done_agents_read` filters over `roster = self._agents_with_children or self._agents` with `is_agents_tab_agent_node(agent)`. Clan containers explicitly return `False` for `is_agents_tab_agent_node`. Unlike `,j` (which calls `_collapsed_clan_jump_candidates`), `,u` does not inspect members hidden inside collapsed clan containers or collapsed tribe panels.
2. **Terminal Status Predicate Mismatch:** 12 of the 21 unreads in `@epic` are under `Failed`. The check `is_unread_completed_status(agent.status)` requires exact membership in `DISMISSABLE_STATUSES`. Decorated failure statuses (e.g., `FAILED (RETRIED)`) or intermediate session-waiting turns fail this exact equality check and are ignored by `,u`.
3. **The Hidden Undo Toggle Trap:** `,u` is implemented as an unannounced toggle. If previous unreads were acknowledged, or if the user presses `,u` multiple times due to UI lag, `_toggle_all_unread_done_agents_read()` immediately invokes `_restore_bulk_read_undo()`, restoring all unreads.
4. **Background Notification Polling Race Condition:** Periodic polling (`_notification_polling.py`, every 9s) re-syncs unread IDs against the on-disk `notifications.jsonl`. When `,u` schedules off-thread dismissal, the file I/O latency or key matching gaps permit the poller to re-populate `_unread_completed_agent_ids` from disk before the write commits.

---

### 2. Why `,j` (`jump_to_next_unread_done_agent`) is Sluggish & Stuttering

1. **O(N) Full-Tree Reconstruction on Every Step:**
   Each `,j` jump marks one agent read, changing `_unread_completed_agent_ids`. This invalidates the candidate cache on 100% of consecutive jumps. To resolve candidates hidden in collapsed clans, it calls `prospective_clan_members`, which expands all clan folds, runs fold filtering across all workspace agents, re-runs panel grouping, and rebuilds the Textual tree from scratch on the synchronous UI thread.
2. **Heavy Disk I/O on an 18.6 MB JSONL Store:**
   `~/.sase/notifications/notifications.jsonl` has grown to **18.6 MB** (3,873+ rows). Acknowledging a single agent completion triggers an exclusive lock and a full read, JSON parse, mutation, and rewrite of the entire 18.6 MB file (~131ms pure I/O). Rapid `,j` presses saturate the thread pool and lock file.
3. **Full List Rebuilding on Step:**
   Crossing panel boundaries or expanding folds triggers `_refresh_agents_display(list_changed=True)`, forcing Textual to destroy and rebuild widget DOM elements rather than patching rows in place.

---

### 3. Critique of the Proposed "Background Proc"

The idea of offloading this expensive work to a background "proc" is **strongly discouraged**:
- **Architectural Mismatch:** In SASE, a "proc" is an independent OS subprocess (e.g. `sase proc`, AXE routine, service proc). TUI responsiveness is an in-memory interactivity problem, not a long-running batch job.
- **IPC & Serialization Latency:** Serializing agent trees and UI states across process boundaries to a child proc would add tens to hundreds of milliseconds of IPC delay, compounding UI lag.
- **Split-Brain State Hazards:** UI state (folds, cursor focus, search text, manual unread marks) mutates synchronously with user keystrokes. An external proc holding an asynchronous view of this state causes race conditions and stale jump suggestions.
- **Boundary Violation:** SASE design records (`rust-core-required`) mandate that core domain logic and persistence optimizations belong in the compiled Rust crate (`sase_core` / `sase_core_rs`), not ad-hoc Python subprocs.

---

### 4. Adjustments to Requirements

1. **Idempotent Bulk Read:** `,u` must be an idempotent "Mark All Unread as Read" action across all tribes, collapsed clans, and tabs, with undo separated or requiring explicit confirmation.
2. **Inclusive Status Matching:** Unread dismissal must match all terminal and failed states (e.g., prefix match on `FAILED*`), not just strict `DISMISSABLE_STATUSES`.
3. **Sub-10ms UI SLA for `,j`:** Candidate selection must run in O(1) / O(log N) without prospective tree building on the UI thread.
4. **Append-Only / Compacted Persistence:** Notification persistence must not perform full-file 18.6 MB rewrites on single-key interactions.

---

### 5. Recommended Multi-Phase Solution

- **Phase 1: Fix `,u` Logic & Badges (Immediate)**
  - Make `,u` operate directly on `_unread_completed_agent_ids` across the global catalog rather than filtering the visible `self._agents` list.
  - Broaden status matching to include all `FAILED*` variants via `is_failed_agent_status`.
  - Invalidate clan aggregate badges (`[W7 F1 U2]`, `[U4]`) and trigger headline repaint upon acknowledgment.
- **Phase 2: High-Performance Candidate Discovery for `,j` (UI Layer)**
  - Maintain an in-memory list of unread agent references sorted by timestamp. On `,j`, pick the next unread candidate in O(1).
  - Lazily expand *only* the specific clan fold of the selected target agent, completely eliminating the expensive `prospective_clan_members` tree reconstruction.
  - Use `_try_patch_agent_row` for surgical in-place updates.
- **Phase 3: Store Compaction & Append-Only Persistence (Core / Rust Backend)**
  - Run `sase_job_notification_store_compact` to archive dismissed notifications older than 14 days, shrinking `notifications.jsonl` from 18.6 MB down to active records (< 500 KB) and cutting I/O time by >95%.
  - Add an in-flight acknowledgment TTL cache in `_unread_state.py` to prevent periodic polling from restoring cleared unreads while background writes process.
  - Implement append-only mutation records or SQLite-backed storage in `sase_core` so individual dismissals are O(1) writes.
