# Chat History - ace-run (research.62.gem)

- **TIMESTAMP:** 2026-11-16 06:41:10 EST
- **MODEL:** agy/gemini-4-hydrogen-xhigh
- **AGENT:** research.62.gem
- **PROMPT:** `~/.sase/multi_prompts/202611/gh_sase_org__sase-multiprompt-261116_061336.md`

## Prompt

%id(gem, clan=research.62)
%m:agy/gemini-4-hydrogen-xhigh %q(1.5x, w=0.25)
#gh:gh_sase-org__sase 
You are researcher gem in a 5-researcher swarm.
The other researchers, `research.62.cdx`, `research.62.cld`, `research.62.grk`, `research.62.mus`, are independently investigating the same request and will write their own self-named reports ending in `__cdx.md` and `__cld.md` and `__grk.md` and `__mus.md`. Your report will end in `__gem.md`.

Conduct your research independently and form your own conclusions. Do NOT attempt to
locate, open, read, or otherwise consult the other researcher's report from this swarm,
even if it becomes available before you finish. Do not obtain that peer's findings
indirectly through its chat transcript, summaries, or requests to the peer. You may
independently use the same external sources, shared input material, and unrelated prior
research. You may check filenames or file existence to avoid overwriting your own
output, but do not inspect the peer's report contents. If you encounter its filename,
leave the report alone. The lead researcher will read every report and synthesize their
findings after you have all finished.

The TUI has slowed down quite a bit lately (including startup). I would like to dig into
this and speed up sase's TUI significantly.

Can you do some research with the goal of helping me decide the best/safest way to
optimize sase's TUI? Feel free to recommend extra instrumentation but only if truly
necessary to diagnose the TUI's performance. End your analysis with a recommended
solution. 
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

Research complete. I wrote the full analysis to [sase_tui_performance_optimization__gem.md](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_30/sase/repos/research/202611/sase_tui_performance_optimization__gem.md) and registered the snapshot as `explicit:36641fd25ac14d1c35253c36` (`research:202611/sase_tui_performance_optimization__gem.md`). I also submitted the `sase final submit` commit declaration for the `sdd:research` sidecar repo.

### Key Findings

1. **P0 Memory, Thread & Swap Catastrophe (2026-11-16 commit `d26b581253`):**
   - [\_display_detail_footer.py](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_30/src/sase/ace/tui/actions/agents/_display_detail_footer.py#L173-L217) schedules `_schedule_hijack_decision()` in [\_hijack_decision_cache.py](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_30/src/sase/ace/tui/actions/agents/_hijack_decision_cache.py#L89-L141) with no concurrency bound and keys it on `roster_generation`.
   - When `row` lacks `artifacts_dir`, `resolve_hijack_subject()` in [facts.py](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_30/src/sase/agent/hijack/facts.py#L70-L125) calls `find_named_agent()`, which runs an unindexed full-tree `scan_agent_artifacts()` in [\_lookup_named.py](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_30/src/sase/agent/names/_lookup_named.py#L100-L245) (`15.378s`, `23,107` `AgentArtifactRecordWire`, `2.16 GiB` RSS per standalone call) and falls back to `bundles_dir.rglob("*.json")` across `65,875` files in `~/.sase/dismissed_bundles`. Even with `artifacts_dir`, it walks all artifact dirs via `_iter_agent_session_members()` in [\_lookup_groups.py](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_30/src/sase/agent/names/_lookup_groups.py#L126-L180).
   - Live heartbeats/census (`9976747c`) showed `207,837` `AgentArtifactRecordWire` (`9 × ~23.1k`), `5.19–5.43 GiB` RSS within `16–20s`, `20.85–35.14 GiB` RSS (`48.99 GiB` RSS+swap) within ~5–20 minutes, and `14` lingering `asyncio_*` worker threads on exit.

2. **P0 Startup Regression `+4.3s` in `AceApp.__init__` (2026-11-12 commit `ea4121387b`):**
   - `app_construct_seconds` jumped from `1.034s` (`671ff5bd`) to `6.205s` (`ea412138`), with `process_start_to_on_mount_seconds` rising from `1.979s` (`Nov 7–12` median) to `6.086s` (`Nov 13–16` median) and `agents_ready_seconds` to `11.969s` median (`53.93s` max).
   - `build_app_bindings()` ([_state_init_late.py](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_30/src/sase/ace/tui/actions/_state_init_late.py#L373)) calls `resolve_artifacts_subtabs()`, triggering explicit per-project config loads across enabled projects. In `_checkout_root_for_local_path()` ([local_trust_enforcement.py](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_30/src/sase/config/local_trust_enforcement.py#L86-L109)), `discover_project_root(local_path.parent)` resolves `.../proj/sase` instead of `.../proj`, failing `str(primary) == root_key` in `_project_identity()` ([local_trust_management.py](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_30/src/sase/config/local_trust_management.py#L165-L205)) and triggering an $O(N^2)$ scan across all registered projects (also hit cold in `AgentIdentitySnapshot.current()`).

3. **Full-Log In-Memory Caches, Import Closure, AXE Startup & Delta/UI Stalls:**
   - **Pre-hijack multi-GB baseline (`3.06–5.57 GiB` on `8c4f728d`):** `build_detail_header_summary()` ([_agent_display_header_summary.py](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_30/src/sase/ace/tui/widgets/prompt_panel/_agent_display_header_summary.py#L244-L340); `3.394s` on first cold agent, `p50=1.25s`, `max=18.62s` in traces) loads and caches entire project logs into Python RAM: `artifacts/index.jsonl` (`46,930` `ArtifactFile`, `93,824` alive in census via [artifact_file_explicit.py](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_30/src/sase/core/artifact_file_explicit.py#L50-L255)), `artifact_reads.jsonl` (`27,005–27,011`), `memory_reads.jsonl` (`23,037–23,051`), and `agent_bead_touches.json` (`16,005`), plus `3.42s` `links.index_build` and `gc.freeze()` ([gc_policy.py](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_30/src/sase/ace/tui/util/gc_policy.py#L396)) freezing `513k–1,002k` startup objects.
   - **Imports & AXE:** Importing `AceApp` takes `2,123.7 ms` (`65.5%` inside `sase.ace.tui.actions.agents._core` importing `gate_turn`, `notification_gates`, `macro.models`, and `agent_detail`); `axe.load_status` takes `4.10s` median reading chop/tail files (`1,349` file reads across `63` chops in [\_data.py](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_30/src/sase/ace/tui/actions/axe_display/_data.py#L340-L520)).
   - **Warmup, Delta Prep & UI Hitches:** `agents.bead_confirmation_warmup` hit `p50=141.1s, max=161.1s` in traces; `artifact_delta` `prep` copies the whole `Agent` graph via `own_required_apply_snapshot` (`0.288s` / `860k` calls for `166` agents, scaling to `2.5–12.8s`); `,j` (`p50=588.5 ms`, `p95=1,548.4 ms`) and UI-thread ticks (`aggregate_clan_runtime` `33` hitches, `.stat()`/locks, `Textual` stylesheet/caches) drive interactive latency spikes.

### Instrumentation Assessment

No new heavy instrumentation is needed upfront—existing logs (`tui_startup.jsonl`, `tui_stalls.jsonl`, `tui_agent_loads.jsonl`, `SASE_TUI_PERF=1`, `SASE_TUI_TRACE=1`, `SASE_TUI_GC_CENSUS=1`) already capture every bottleneck. Only after landing fixes would optional worker-pool depth in heartbeats or trace spans inside `prepare_loaded_agents_worker_boundary` / `decode` be worth adding if needed.

### Recommended Solution

1. **Immediate Hotfix (Today):**
   - Debounce and serialize `_schedule_hijack_decision` (`max_concurrency=1`), switch its cache key from `roster_generation` to a row-local hijack fingerprint, pass loaded TUI rows into `facts.resolve_and_decide`, and ban `scan_agent_artifacts()` / `dismissed_bundles.rglob("*.json")` from `facts.py` / interactive TUI lookups (use `query_agent_artifact_index` with `candidate_filter`).
   - Fix `_checkout_root_for_local_path()` in `local_trust_enforcement.py` to unwrap `.../sase/sase.yml` to the checkout root *before* `discover_project_root` / `_project_identity()`, memoize `_project_identity()`, and defer `axe.collect(include_full_snapshots=True)` until the Services/AXE tab opens.
2. **Short-Term Architecture Fix (This Week, `sase-core` + `sase`):**
   - Replace full-file Python caches for `artifacts/index.jsonl`, `artifact_reads.jsonl`, `memory_reads.jsonl`, `agent_bead_touches.json`, and `issues.jsonl` with per-agent/per-bead filtered Rust/SQLite lookups, lazy-load heavy action/modal imports out of `sase.ace.tui.actions.agents._core`, and relocate `gc.freeze()` right after imports (or remove it once live survivors fall below `<200k`).
3. **Follow-Up Responsiveness Pass:**
   - Replace whole-graph `copy_agent_graph` on `artifact_delta` with per-row copy-on-write updates and move UI-thread `aggregate_clan_runtime`, `.stat()`/lock checks, and `,j` notification/panel work off the UI loop.
