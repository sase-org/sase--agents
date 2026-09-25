# Chat History - ace-run (sase-zn.9.3)

- **TIMESTAMP:** 2026-09-13 11:35:15 EDT
- **MODEL:** claude/sonnet
- **AGENT:** sase-zn.9.3

## Prompt

%id(3, clan=sase-zn.9, bead=sase-zn.9.3)
#gh:gh_sase-org__sase
%model:@medium
%auto
%w(bead=sase-zn.9.1)
%w(bead=sase-zn.9.2)
Can you complete the work for bead sase-zn.9.3? The bead is already reserved for you and assigned to your agent
name: it was set to status=in_progress before you started reading this, either by the `sase bead work` launch
checkpoint or by the runtime promoting an ad-hoc wait-time claim. Do not set the status by hand. Read its
description and design file, do the work, and close only this bead with
`sase bead close sase-zn.9.3 --note "<what you verified>"`. Before closing, run
`sase bead epic-symbols sase-zn.9.3`. If this phase still has `--epic-symbol` entries, resolve each symbol or
re-key the Justfile line to a still-open bead (the parent epic or a later phase). `sase bead close` refuses while
leftovers remain; they go stale the instant this phase closes and turn unrelated agents' `just check` red. Closing
an assigned phase bead is unaffected by the parent-close descendant guard. Do NOT close the parent epic or any ancestor plan bead. Any instruction in a phase
description or child plan to close an ancestor is preparation and evidence for that ancestor's land agent, not
authorization for a phase worker. Do not create beads yourself: record discovered follow-up work as a
`PROPOSED FOLLOW-UP:` entry via
`sase bead note sase-zn.9.3 'PROPOSED FOLLOW-UP: <one-line summary — detail>'`; the epic's land agent triages
these into task beads.

## Response

I'll start by reading the bead's details.

Good, dependencies are done. Let me look at the existing heap sampler infrastructure and related test/doc files.

While that explores, let me check how AceApp is tested/driven in existing test harnesses so I can build a representative sustained-session test.

Good, sampler lifecycle is wired correctly. Let me check `lifecycle.py`'s shutdown to confirm pending tasks are cancelled cleanly.

This is exactly the reusable harness I need. Let me read the existing diff-cache test and its helpers.

Now let me check the exact `Any` import status in `_linked_deltas.py` and implement the fixes.

Now let me apply the fix to `_diff.py`:

Now `_linked_deltas.py`:

Now update all insertion sites to call the eviction helper:

Now the `_selected_agent_linked_delta_cache` / `_selected_agent_cache_monotonic` site:

## Summary

I read through the perf-runbook-listed refresh/render modules plus the caches they call into, and traced every module-level and class-level mutable collection I found back to its write site and (attempted) eviction site. The clearest, highest-confidence bugs are all in **`src/sase/ace/tui/widgets/file_panel/_diff.py`** and **`_linked_deltas.py`**, which are wired directly into the periodic "live hint" refresh that the perf runbook's listed modules (`_loading_live_hints.py`, `_display.py`) drive on every agents-tab refresh cycle. I also found several slower-growing but still-unbounded module-level caches elsewhere. For each I read the *entire* removal/eviction path (not just the write site) before calling it unbounded — where I found bounded LRU/TTL caps I say so explicitly as a negative result.

Ranked by confidence that this is a genuine, unbounded, per-refresh-cycle leak (not bounded-but-large):

### Tier 1 — confirmed unbounded, grows every refresh cycle (multiplies with session length × active-agent count)

**1. `src/sase/ace/tui/widgets/file_panel/_diff.py:62` — `_diff_cache`**
```python
_diff_cache: dict[DiffCacheKey, str | None] = {}
```
`DiffCacheKey` (line 53-59) includes a `ttl_bucket = int(time.time() // DIFF_CACHE_TTL_SECONDS)` (line 267, `DIFF_CACHE_TTL_SECONDS = 1.0` at line 51). The TTL bucket is documented (lines 12-18) as the *intended* invalidation mechanism — but invalidation only means "the old key stops being looked up," not "the old entry is removed." Writes happen at lines 383-384 inside `_get_agent_diff`, which is called from `get_agent_diff()` (detail-panel render) and from `live_agent_file_change_hint()` (line 288). I grepped the whole repo for `_diff_cache.clear(` / `.pop(` — the **only** hits are in test fixtures (`tests/ace/tui/widgets/file_panel/test_diff_cache.py`), never in production code. Since the key changes every second for every active agent, this dict grows by roughly one entry per active agent per second it is probed, forever.
- **Trigger**: `_loading_live_hints.py:AgentLiveHintMixin._run_live_hint_refresh` → `_compute_live_hints` (line 218-230) → `classify_live_file_change_hint` (`models/_agent_status_diff.py:55`) → `live_agent_file_change_hint` (`_diff.py:271`) → `_get_agent_diff`. This scan is scheduled via `self._schedule_live_hint_refresh(source="apply")` at `actions/agents/_loading_apply.py:533`, which fires on **every** agents-tab load/apply cycle (auto-refresh, file-watcher reload, launch fan-out — confirmed by reading `_loading_apply.py:516-533`).
- **What removes entries**: nothing.

**2. `src/sase/ace/tui/widgets/file_panel/_linked_deltas.py:52-53` — `_linked_diff_text_cache`, `_linked_delta_cache`**
Same TTL-bucket-in-key pattern (`LinkedDeltaCacheKey` at lines 42-50 includes a `ttl_bucket`). Written at lines 276, 298, 317, 326, 330 inside `_fetch_repo_diff_text`/`_compute_repo_group`, invoked from `linked_agent_file_change_hint` — called by the **same** per-refresh live-hint scan as #1. No `.pop()`/`.clear()` anywhere in the file or repo.

**3. `src/sase/ace/tui/widgets/file_panel/_linked_deltas.py:54-58` — `_selected_agent_linked_delta_cache`, `_selected_agent_cache_monotonic`**
Keyed by `agent.identity` (not time-bucketed), written at lines 385-386 in `compute_linked_delta_groups`, read at line 228. Grows one entry per distinct agent identity ever selected/scanned; never pops an identity when that agent is dismissed/archived/disappears from the list. Slower growth than #1/#2 (bounded by distinct-agent count, not by elapsed time), but still strictly monotonic for the life of the process.

### Tier 2 — confirmed unbounded, grows per distinct entity or per content-change (not per-second, but still never pruned)

**4. `src/sase/ace/tui/relations/artifact_links.py:81` — `_CACHE`**
```python
_CACHE: dict[tuple[tuple[str, object, object], ...], ArtifactLinksSnapshot] = {}
```
Keyed by a `(project_key, mtime_ns, size)` signature of each project's artifact-link aggregate file (built at line 99, `load_artifact_links_snapshot`). Every time any project's aggregate file changes — i.e. routinely whenever an agent/patch/bead link is created — a new signature produces a new entry (lines 128-132); the previous entry becomes permanently unreachable but is never removed. Called from the hot refresh path: `actions/patch/_loading.py:_build_patch_relation_index` → `load_artifact_links_snapshot(None)` (line 657), invoked on every `_apply_patches`/`_reload_and_reposition`/`_apply_reloaded_patches`. No `.pop()`/`.clear()` in the file.

**5. `src/sase/ace/tui/relations/link_index.py:74` — `_INDEX_CACHE`**
```python
_INDEX_CACHE: dict[tuple[object, ...], LinkIndex] = {}
```
Keyed by `snapshot.source_key` — exactly the signature from #4 — so it grows in lockstep with `_CACHE` (`link_index_for_snapshot`, lines 76-93). No eviction.

**6. `src/sase/ace/tui/util/axe_log_renderer.py:76` — `_render_cache`**
```python
_render_cache: dict[tuple[str, str], tuple[int, int, Text]] = {}
```
`source_id` is built per-entity: `f"gate:{agent.gate_id or agent.identity}"` (`prompt_panel/_agent_gate_section.py:90`), `f"monitor:{agent.monitor_id or agent.identity}"` (`prompt_panel/_agent_monitor_section.py:81`), `f"proc-shell:{agent.proc_id or agent.identity}"` (`prompt_panel/_agent_proc_shell_section.py:61`), `f"bgcmd:{info.pid}"` (`widgets/axe_dashboard.py:209`), `f"proc:{task.proc_id}"` (`modals/procs_pane_render.py:307`). Write is unconditional at line 133 on every miss; a "hit" only happens when size+tail-hash are byte-identical to the last render, so a still-changing (running) row keeps rewriting its own slot, but a completed/dismissed agent's slot is simply abandoned — never popped. No cap, no `.clear()`/`.pop()` anywhere in the module.

**7. `src/sase/ace/tui/models/_diff_badge.py:13` — `_diff_badge_cache`**
Keyed by `(expanded_diff_path, mtime_ns, size)` of each agent's persisted diff file (`diff_has_real_edits`, lines 50-76). Since a terminal agent's `diff_path` file never changes again, this grows by exactly one permanent entry per unique diff artifact ever classified (called from the loader's status-override pass on essentially every agents load). No eviction.

**8. `src/sase/ace/tui/tools/cache.py:39` — `_tools_cache`**
Keyed by `get_cache_key(agent)` (≈ `cl_name:agent_type:workspace_num:raw_suffix`, i.e. per-agent). `invalidate_cached_tool_calls` (lines 146-151) only mutates the *existing* entry's fields (forces a re-fetch) — it never calls `_tools_cache.pop(...)`. So the key set only ever grows; one slot per distinct agent ever viewed with the Tools panel, for process lifetime.

**9. `src/sase/ace/tui/actions/agents/_snapshot_cache.py` — module-level singleton `_GLOBAL_CACHE` (line 180)**
`AgentSnapshotCache._attempt_history` and `._retry_state` (lines 42-47) are keyed by `artifacts_dir` (per-agent). The class defines working `invalidate()` / `invalidate_dismissed_bundles()` methods (lines 160-177) that *would* prune a slot — but a full-repo grep (`grep -rn "get_global_snapshot_cache\|\.invalidate("`) shows these are **never called from any production code path**, only referenced inside the class itself and in the module's own docstring. `retry_state_for` is populated for every RUNNING/live agent on every agents load (`_loading_helpers.py:401`), and `attempt_history_for` is populated whenever a detail pane hydrates history (`hydrate_agent_attempt_history`, `_loading_helpers.py:350-371`). Net effect: a dead-code eviction API sitting on top of a strictly monotonically growing per-process dict.

### Checked and ruled out (bounded, not leaks)

- `widgets/_agent_list_render_cache.py` (`AgentRenderCache`, instance-level, `_AGENT_CACHE_MAX=512`/`_BANNER_CACHE_MAX=128`, real `OrderedDict` LRU eviction in `_bounded_lru_put`) — correctly bounded.
- `PatchList`/`AgentList` per-instance row dicts (`_row_render_ctx`, `_option_idx_by_patch_name`, etc., `widgets/patch_list.py`, `widgets/agent_list.py`) — fully reset (`= {}`) on every full `update_list`/`render_collapsed`, bounded to current visible rows.
- `actions/patch/_loading.py:_patch_query_result_cache` — `OrderedDict` capped at 32 (`_patch_query_result`, lines 356-383).
- `actions/patch/_loading.py:_pr_unmirrored_cache_key/_value` — single-slot cache (one key at a time), not accumulating.
- `models/agent_page_url.py:_AGENT_PAGE_REGISTRY_SNAPSHOTS` — capped at 32 with a 30s TTL.
- `proc_observer.py:_LIVE_OBSERVERS` — `weakref.ref` registry with a GC finalizer callback (`_drop`, line 339-341) that self-prunes, plus a defensive stale-sweep in `_live_observers()` (lines 352-364). Correctly self-cleaning.
- `widgets/artifacts/commits_detail.py:_diff_cache` — instance-level (`self._diff_cache = {}`), scoped to widget lifetime.
- `util/trace.py:_context` — small, fixed set of fields (`current_tab`, `current_idx`, etc.), overwritten not accumulated.

### Not fully verified (flagged, not claimed)

I did not trace the removal logic for `widgets/_artifact_ref_completion_menu.py:_SNAPSHOT_PAYLOAD_MEMOS`, `widgets/_artifact_ref_entity_catalogs.py:_BEAD_CACHE`, or `widgets/_artifact_ref_completion_catalog.py:_ARTIFACT_INDEX_CACHE` in depth — they're keyed by `Path`, which in most sessions is bounded to a handful of workspace roots, so I'd guess bounded, but I did not confirm an eviction path exists, so treat that as unconfirmed rather than cleared.

If you want, I can go deeper on the exact write/read call counts (e.g. instrumenting `len(_diff_cache)` growth over a synthetic multi-hour session) to quantify magnitude before you pick which of these to fix first.

Good — the exploration confirms my Tier-1 fixes and surfaces additional Tier-2 unbounded caches. Let me look at those to apply the same bounded-eviction fix where it's a simple, low-risk cap.

Both are simple single-write-site caches — same fix pattern applies cleanly. Let me apply the FIFO cap.

Pre-existing unused import, unrelated to my change. Now let me finish wiring the eviction call in `link_index.py`:

Now let's look at `axe_log_renderer.py` and `_diff_badge.py`.

Now update the read/write sites to use LRU semantics:

Pre-existing (just shifted line numbers). Now let me fix the get/put logic for real LRU behavior:

Good, `.clear()` works identically on `OrderedDict`. Now let's look at `_diff_badge.py` and `tools/cache.py`.

Now `tools/cache.py`:

I need to reconsider — `_selected_agent_linked_delta_cache` is rewritten on every refresh for actively-selected agents, so plain FIFO eviction would unfairly evict the hottest entries first, same issue as the axe_log_renderer case. Let me fix that properly with LRU semantics.

Let me update the read sites (lines 260, 271) and the write site (433-438).

Now the write site:

Good, both are wired — that diagnostic was just stale/out-of-order from the tool. Let's run the existing test suites for these modules now to confirm nothing broke.

All 46 pass. Now let's check `artifact_links.py`/`link_index.py` and `_diff_badge.py` tests too.

Good, straightforward defaults. Now let's write the combined regression test file for both caches:

Now let's add regression tests to `test_diff_cache.py` and `test_linked_deltas.py` for the Tier-1 caches, and `test_axe_log_renderer.py` for the LRU correctness.

All pass, including the LRU-vs-FIFO correctness proof. Now let's add the diff-cache and linked-delta-cache bound tests.

Now let's add the linked-delta cache bound + LRU-correctness tests.

Now let's add a bounded-cache test for `_diff_badge.py`.

Fast enough (0.43s). Now let's run the full relevant test suite to confirm nothing regressed.

Now remove the unused `time` import:

Good, provider resolves now. Let's re-run the smoke test loop.

Let's smoke-test this simplified version with small parameters before committing to the full run.

Found it — asyncio's child watcher racing with plain `subprocess.run()` calls inside the event loop. Since nothing here actually needs async, let me rewrite as a plain synchronous script.

Let's smoke-test this synchronous version thoroughly before the real run.

Real git subprocesses are unreliable in this sandbox regardless of async/sync. Since the actual bug is pure Python caching (not git behavior), let me switch to a stub VCS provider — the same pattern the unit tests already use — to eliminate subprocess flakiness entirely while still exercising the real production cache code.

Let me try one more diagnostic — running the same test as a truly backgrounded process rather than through a synchronous foreground `timeout` wrapper, in case the hang is specific to how the tool manages foreground/timeout processes.

While the evidence run proceeds in the background, let me check the required lint/test memory note since I've modified tracked files.

Good, matches expectations. Now let's check the background evidence run's progress and then run `just check`.

Phase 1 shows clean unbounded growth (exactly 10 entries/tick, no eviction) — strong live evidence for the bug. Phase 2 (capped) is now running. Let me check epic-symbols while that continues.

No epic-symbol leftovers to resolve. Let's check the evidence run again.

This looks clean and well-scoped. Let's do a final review of the full diff for correctness before closing.

This diff looks correct and well-documented. Let's check the evidence run again.

Let me check on the scoped-test background task while waiting.

Good, confirmed. Now let's check on both background tasks.

While the scoped test run finishes, let me draft the close note and verify the diff for the remaining files once more.

All correct and clean. Let me check the test-scoped task status.

Clean and scoped. Now let's wait for the test-scoped run to finish.

The scoped test run is still in progress alongside other agents' runs on this host. I'll wait for it to complete before finalizing verification.

I've done what I can proactively — the scoped test suite is running in the background (shared with other agents on this host) and I'm waiting for it to complete before closing out. I won't poll further; I'll act on the next notification.

I'll stop polling now and wait for the scoped test run's completion notification (via the Monitor I already started) before finalizing.

The scoped verification suite (`just test-scoped`) is still running in the background — it's a shared lane on this host with other agents' runs queued alongside it. I have a monitor watching for it to finish, and I'll pick back up as soon as it completes: reviewing results, then closing out bead `sase-zn.9.3`.

In the meantime, here's where things stand:

**Root cause found:** Live evidence (a real `TUIHeapSampler`-driven session I just ran) confirmed `_diff_cache` in `_diff.py` grows without bound — every second, for every active agent, because its cache key includes a TTL bucket that's never reused and nothing ever evicts a stale entry. Pre-fix: 900 entries and climbing linearly after 90 ticks. Post-fix: pinned at the 128-entry cap from tick 15 onward, flat for the rest of the run.

**Fixed 6 unbounded caches** across `_diff.py`, `_linked_deltas.py`, `axe_log_renderer.py`, `_diff_badge.py`, `artifact_links.py`, and `link_index.py` — bounded FIFO eviction where a key is written once, LRU (via `OrderedDict.move_to_end`) where a live entity keeps rewriting its own slot (so a naive FIFO cap would've evicted the busiest agent first).

**Added regression tests** for each fix, including two that specifically prove LRU-correctness (a hot, repeatedly-touched entry survives while cold ones cycle out).

Two more unbounded caches I found (`tools/cache.py`, `_snapshot_cache.py`) are lower-severity (user-interaction-gated, not automatic per-refresh growth) and need more careful surgery than a quick cap — I'll record those as a proposed follow-up rather than rushing a fix.

I'll stop checking manually now and wait for the monitor notification when the scoped suite finishes.

I'll pause here and resume once the scoped test run completes.

I'll wait for that notification now rather than polling.

The scoped test run finished successfully. Let's check the results.

None of the 22 failures touch files I changed. Let me spot-check a few in isolation to confirm they're pre-existing/unrelated, not caused by my diff.

All 22 scoped-test failures are confirmed unrelated to my change — they trace to two other already-committed changes (a stale `sase_core_rs` Rust binding missing `continuation_decide_resume_adoption`, and queue_capacity schema fallout), not to the ACE TUI cache fixes. Let me record the discovered follow-ups and close the bead.

Now let's re-verify epic-symbols one final time and close the bead with a thorough note.

I'll wait for that to complete rather than poll further — this pre-close verification (full-suite escalation) may take a while given only 4 workers were available.

The close command completed successfully. Let me verify the bead is actually closed.

Bead `sase-zn.9.3` is confirmed **CLOSED**.

The final declaration was accepted. Bead `sase-zn.9.3` is closed and the code changes are committed.

**Summary:** Attributed and fixed residual ACE TUI heap retention (bead `sase-zn.9.3`). Live `TUIHeapSampler`-driven evidence traced the growth to `_diff_cache` in `_diff.py` — its key embeds a per-second TTL bucket that's never reused, so every active-agent probe left a permanent entry. Fixed that plus five more caches with the identical structural bug (`_linked_deltas.py`, `axe_log_renderer.py`, `_diff_badge.py`, `artifact_links.py`, `link_index.py`), using LRU eviction rather than FIFO wherever a live entity keeps rewriting its own cache slot. Added deterministic regression tests proving each cache stays bounded. Scoped/full test suites pass aside from 22 confirmed-unrelated pre-existing failures (traced to other commits), which I recorded as follow-ups on the bead along with two lower-severity caches left for a future pass.
