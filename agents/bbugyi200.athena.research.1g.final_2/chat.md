# Chat History - ace-run (research.1g.final_2)

- **TIMESTAMP:** 2026-09-05 19:33:28 EDT
- **MODEL:** claude/claude-fable-5
- **AGENT:** research.1g.final_2

## Prompt

%id(final_2, clan=research.1g) %m:@xlarge
%wait:research.1g.cdx %wait:research.1g.cld 
#gh:gh_sase-org__sase 
You are the lead researcher: two independent researchers have reported on the request
below, and you will add your own research and merge all three perspectives into one
consolidated report.

SASE derives your plan's links from the artifacts you read this turn; use
`sase artifact read` for context you actually used.

Research request:

I've been thinking about ways we could allow sase to dispatch
to other known machines so the user can open up one TUI on one machine and manage all of
their agents across all machines.

- In practice, I plan to use this to manage all (e.g. launch, view, kill, etc...) sase
  agents that are running on any of my Tailscale devices from the `sase ace` TUI on my
  MacBook.
- Some lag is to be expected across network devices. But, once fully synced, I should be
  able to view and manage (e.g. from the "Agents" tab in the TUI) sase agents running on
  different machines in all of the same ways I can view and manage sase agents that are
  running on the local machine (i.e. the same machine as the TUI).
- I already did some research on this (see the tailnet_agent_fleet.md file in the
  research sidecar repo), but have since decided to remove the `agent_sync` import leg
  (see the sase-ws epic bead and the sase_collaboration_architecture.md file in the
  research sidecar repo for context). Review the tailnet_agent_fleet.md file for context
  and inspiration before performing your own (much improved I would expect, since you
  have more up-to-date information and a better starting point) research.

Can you do some research with the goal of helping me decide the best way to implement
this? End your analysis with a recommended solution. Make sure that the solution you
recommend is reliable, robust, and beautiful.

The researchers' chat transcripts:

{{ wait_chats }}

Month directory (create it if missing):

$(sase repo path research --ensure)/$(date +%Y%m)

Steps:

1. Read both transcripts to learn which report file each researcher wrote
   (`research.1g.cdx` -> `__a`, `research.1g.cld` -> `__b`), then read both reports.
   Never assign `__a`/`__b` from filesystem order.
2. Research the request yourself, prioritizing gaps, weak evidence, and disagreements
   between the two reports.
3. Pick a descriptive stem `<name>` that collides with nothing in the month directory
   (do NOT end the name with `_consolidated` or `_<YYYYmmdd>` or anything similar unless
   it relates to the research topic), create `<month-dir>/<name>/`, and move the two
   reports to `<name>__a.md` and `<name>__b.md` inside it. Preserve both files and never
   overwrite: on any collision, pick a different stem first.
4. Write the consolidated report to `<name>/<name>.md`: merge the strongest findings
   from both reports and your own research, resolve conflicts, cut duplication, and add
   missing critical context without unnecessary length.

Final layout:

```text
<month-dir>/<name>/
├── <name>__a.md
├── <name>__b.md
└── <name>.md
```

## Response

I'll start by reading the two researcher transcripts to find which report each wrote, then dig into the reports and prior research myself.

I'll verify these claims systematically. Let me start by exploring the repo structure.

I'll verify these claims systematically. Let me start with parallel searches.

Claim 1 shows no direct FS calls. Let me check its imports and helper calls.

Findings, claim by claim. All paths relative to `/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_24/sase/repos/linked/sase-core`.

**1. Unauthenticated pairing-start that returns the code — VERIFIED**
- `crates/sase_gateway/src/routes.rs:562-593` — `pair_start` takes only `State` + `Json<PairStartRequestWire>`; no `HeaderMap`, no `authenticate(...)` call (contrast every other handler, e.g. `session` at :654 which calls `authenticate`). It generates `let code = generate_pairing_code();` and returns it verbatim in `PairStartResponseWire { pairing_id, code, ... }` at :585-592.
- `crates/sase_gateway/src/routes.rs:594-651` — `pair_finish` is likewise unauthenticated and only checks `challenge.code != payload.code`, then mints a bearer token via `token_store.pair_device`. So start→finish is a self-service loop with no out-of-band/local confirmation.
- Router at :500-548 applies only `TraceLayer::new_for_http()`; there is no auth middleware layer, confirming auth is purely per-handler.
- Mitigating nuance (PARTIAL on "remote caller"): default bind is loopback and non-loopback binds are refused unless opted in — `crates/sase_gateway/src/server.rs:26` (`SocketAddr::from(([127,0,0,1], 7629))`), `:28` (`allow_non_loopback: false`), `:70-77` (`validate_bind_policy` errors with `NonLoopbackBind` otherwise). So the attack requires the operator to have passed `--allow-non-loopback`/`-L` (or the attacker to be local). Also no rate limit / pairing-count cap on `pair_start`.

**2. SSE replays buffer then heartbeats only — VERIFIED**
- `crates/sase_gateway/src/routes.rs:764-788` — `events()` yields `initial_events` first, then enters `loop { interval.tick().await; ... EventPayloadWire::Heartbeat { sequence } ... }`. The loop body constructs only heartbeats; there is no receiver/subscription (`tokio::sync::broadcast` is not used anywhere — `EventHub` is `Arc<Mutex<EventHubInner>>` with a `VecDeque` ring, :296-307, :408-440). An already-connected client learns of new `agents_changed` events only by reconnecting with `Last-Event-ID` (`initial_events_for_stream` :1777-1803, `replay_after` :441+).
- `publish_agents_changed` definition: `routes.rs:1729-1746`. Call sites (all inside gateway mutation handlers, none from any external/host watcher):
  - `routes.rs:854` — `agent_launch`, reason `"launch"`
  - `routes.rs:889` — `agent_launch_image`, reason `"launch_image"`
  - `routes.rs:925` — `agent_kill`
  - `routes.rs:967` — `agent_retry`, reason `"retry"`
  - `routes.rs:3961` — inside `#[cfg(test)]` code, not production
- Corroborating test: `crates/sase_gateway/src/server.rs:305-306` asserts the first two SSE frames are `session` then `heartbeat`.

**3. `request_id` accepted but never deduplicated — VERIFIED**
- `crates/sase_gateway/src/wire.rs:488, 503, 562` declare `pub request_id: Option<String>` on the text-launch, image-launch, and retry/update wire types.
- `crates/sase_gateway/src/routes.rs:835-867` (`agent_launch`) sets only `payload.device_id` and immediately calls `state.agent_bridge.launch_text(&payload)` — no lookup keyed on `request_id` before dispatch. Same shape in `agent_launch_image` (:869-902) and `update_start` (:1129-1153, which builds `request_id: payload.request_id` and dispatches).
- `crates/sase_gateway/src/host_bridge.rs:325` merely forwards `"request_id": request.request_id.clone()` into the subprocess JSON.
- Repo-wide grep for `dedup|idempot|journal|already_seen|seen_request` across `crates/sase_gateway/src/` returns zero hits. `request_id` is a pure correlation passthrough.

**4. tower-http `trace` only, no compression — VERIFIED**
- `Cargo.toml:30` (workspace root) — `tower-http = { version = "0.5", features = ["trace"] }`; `crates/sase_gateway/Cargo.toml:33` inherits it with `{ workspace = true }`. No `compression-gzip`/`compression-full` feature, and only `TraceLayer` is layered (`routes.rs:546`).

**5. `DaemonConfig` models a socket path that is never bound — VERIFIED**
- `crates/sase_gateway/src/daemon.rs:23` `const DAEMON_SOCKET_NAME: &str = "sase-daemon.sock"`; `:26-31` `DaemonRuntimePaths { socket_path: PathBuf }`; `:197-205` `default_run_root` = `sase_home/run/<sanitized host>` and `default_socket_path` = `run_root/sase-daemon.sock`. Test at `:276-279` asserts `/tmp/sase-home/run/workstation.local/sase-daemon.sock`.
- `run_daemon` (`daemon.rs:163-186`) binds only `TcpListener::bind(mobile_gateway.bind)`, else awaits `ctrl_c`. Grep for `UnixListener`/`UnixStream` across `crates/sase_gateway/src/` returns zero hits; `socket_path` is referenced outside daemon.rs only as a re-export (`crates/sase_gateway/src/lib.rs:19`).

**6. Dependency split — VERIFIED**
- `crates/sase_core/Cargo.toml:14-27` — serde, serde_json, serde_yaml, thiserror, regex, chrono, fs2, rusqlite, hex, sha2, libc, tempfile, unicode-width. No tokio, no reqwest, no async runtime.
- `crates/sase_gateway/Cargo.toml:19-33` — `axum = { workspace = true }` (:20), `tokio = { workspace = true }` (:32), `reqwest = { version = "0.11", ... features = ["json","rustls-tls"] }` (:25), `sase_core = { workspace = true }` (:26). Also async-stream, jsonwebtoken, tower-http.
- `crates/sase_core_py/Cargo.toml` — `crate-type = ["cdylib", "rlib"]` (:29), `sase_core = { workspace = true }` (:36), `pyo3 = { version = "0.22", features = ["abi3-py312"] }` (:37), `extension-module` feature (:33). Confirmed as the PyO3 wheel crate.

**7. agent_scan module and exports — VERIFIED, with one sub-claim REFUTED**
- Module files exist: `crates/sase_core/src/agent_scan/{context.rs, index.rs, layout.rs, mod.rs, scanner.rs, selector.rs, wire.rs}`.
- All four named functions are re-exported: `crates/sase_core/src/agent_scan/mod.rs:24, 26, 28, 30` and again from `crates/sase_core/src/lib.rs:226, 229, 231, 235`.
- `record_shape` discriminator: `crates/sase_core/src/agent_scan/wire.rs:905-921` defines `enum AgentArtifactRecordShapeWire { #[default] Full, List }` with `#[serde(rename_all = "snake_case")]`; `wire.rs:952-957` puts `pub record_shape: AgentArtifactRecordShapeWire` on `AgentArtifactRecordWire` with `skip_serializing_if = "AgentArtifactRecordShapeWire::is_full"`. The List shape is live, not vestigial: `index.rs:1147` (`if query.record_shape == ...::List`) and `index.rs:1186` (`record.record_shape = ...::List`).
- `meta` table holds versioned state — VERIFIED: `index.rs:2202-2205` `CREATE TABLE IF NOT EXISTS meta (key TEXT PRIMARY KEY, value TEXT NOT NULL)`; read/write at `:2339` and `:2435` (`INSERT OR REPLACE INTO meta(key, value) VALUES ('schema_version', ?1)`), plus generic accessors `read_agent_artifact_index_meta` / `write_agent_artifact_index_meta` at `:871-895`. Other keys are used in practice (e.g. `dismissed_projection`, `crates/sase_core/tests/agent_scan_parity.rs:1646-1657`).
- Monotonic `revision` counter — REFUTED (none exists yet): grep for `revision` across `crates/sase_core/src/` hits only unrelated concepts — `prompt_artifact.rs:45 vcs_revision`, `artifact_ref/expansion.rs:22 "captured_revision"`, `bead/history.rs` note revisions. No revision key in the `meta` table and no counter in `agent_scan`.

**8. devices.json fully rewritten on every authenticated request — VERIFIED**
- `crates/sase_gateway/src/storage.rs:66-88` — `authenticate_token` reads the whole file (`read_devices_unlocked`), sets `record.last_seen_at = Some(format_time(now));` (:84), then calls `self.write_devices_unlocked(&file)?` (:86), which rewrites the entire `devices.json` via a temp-file + rename (`:231-240`, `DEVICES_FILE` const at `:20`).
- `crates/sase_gateway/src/routes.rs:1617-1619` — every authenticated handler routes through `authenticate()`, which calls `authenticate_token(token, Utc::now())`. So one full-file read+rewrite per poll, plus an `append_audit` fsync per request (`storage.rs:206-221`, `file.sync_all()`).

**9. machine_hood module — VERIFIED as existing, PARTIAL on "already used for agent identity"**
- `crates/sase_core/src/machine_hood.rs` exists; module doc at `:1-9` describes qualifying agent names with `<machine_name>.` "so agent names become globally unique across machines". API: `validate_machine_name` (:25, enforces `^[a-z_]+$`), `qualify_machine_agent_name` (:49), `strip_machine_agent_name` (:61), `machine_hood_of` (:71). Exported at `crates/sase_core/src/lib.rs:694-696`.
- Caveat on shape: names are machine-qualified as `<machine>.<agent>` (single leading hood segment), not the four-part `owner.machine.clan.agent` in your claim — there is no owner segment in this module.
- Caveat on "already used": within the Rust workspace these functions have no internal callers. The only consumers are the PyO3 bindings (`crates/sase_core_py/src/lib.rs:851-854, 1241-1263`), i.e. the capability is exposed to Python but nothing in `sase_core`'s own `agent_identity`/`agent_scan` code paths calls it.

**10. Route count — VERIFIED as 27, far closer to 27 than 6**
- `crates/sase_gateway/src/routes.rs:500-548` registers exactly 27 distinct paths (28 method-path handlers, since `/api/v1/session/push-subscriptions` is `get(...).post(...)` at :505-508), plus a `.fallback(unknown_route)`.
- All five named feature areas exist:
  - notifications — `:526` list, `:527` detail, `:528-531` mark-read, `:532-535` dismiss
  - gate approval — `:537` `POST /api/v1/actions/gate/:prefix`
  - question answering — `:538-541` `.../question/:prefix/answer`, `:542-545` `.../question/:prefix/custom`
  - beads — `:522` list, `:523` `/api/v1/beads/:id`
  - xprompts catalog — `:521` `GET /api/v1/xprompts/catalog`
- Full list also covers health, pair start/finish, session, push-subscriptions (+delete by id), events, agents (list/resume-options/launch/launch-image/kill/retry), changespec-tags, update start/status, and attachment download.

Findings:

**1. VERIFIED (with one caveat).** `/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_24/src/sase/ace/tui/models/_loaders/_done_snapshot_loaders.py` (250 lines) has zero `.exists()/open()/iterdir()/glob()/read_text()/listdir/stat` calls; imports are all wire types (`AgentArtifactScanWire`, `AgentArtifactRecordWire` from `sase.core.agent_scan_wire`), docstring at line 241 says "instead of re-walking the filesystem". Caveat: one transitive FS touch is reachable — `enrich_agent_from_meta_wire` → `_meta_enrichment_wire.py:251` → `_meta_enrichment_common.py:453` `response_path.exists()`. It is gated by `agent.status in ACTIVE_ENRICHMENT_STATUSES = {"STARTING","RUNNING"}` (`_meta_enrichment_common.py:37`), so done rows never hit it in practice. The `_wire` prompt-markers variant is clean (the `glob` at `_meta_enrichment_prompt_markers.py:23` is in the non-wire `enrich_agent_from_prompt_markers`).

**2. VERIFIED.** `provider_contract.py`: `AceProviderCapabilities(pages/deltas/lazy_details/counts)` L19-25; `AceRowHandle.daemon_handle` L55-61; `AcePage` with `cursor` L70, `next_cursor` L71, `bounded` L76, `truncated` L77; `AceSnapshot.snapshot_id` L86 / `generation_id` L87; `AceDeltaBatch.row_patches` L128, `count_patches` L129, `invalidation_reason` L131, `resync_hint` L132. `data_providers/_types.py`: `AgentsProviderSnapshot` L14 with `used_daemon` L21, `fallback_reason` L22, `snapshot_id` L24; `AgentEventApplyResult` L28; `AgentsViewport` L37.

**3. VERIFIED.** `data_providers/_settings.py:6-8` — `agents_daemon_reads_enabled()` body is literally `return False`. `data_providers/_factory.py:9-11` returns `DirectAgentsDataProvider()`; `_direct.py:12` is the only concrete provider class in the package (no daemon provider module exists).

**4. VERIFIED.** `_running_loaders.py:252-257` — `if pid is None or not is_process_running(pid)` → `running_file.unlink(missing_ok=True)` (L256) → `update_agent_artifact_index_for_marker_mutation(artifact_dir)` (L257). The `~/.sase/projects/home/artifacts/ace-run` walk is at L305-314 (`sase_projects_dir()` / `"home"`, `iter_agent_artifact_dirs("home", "ace-run", ...)`), with the same unlink/index-update pair repeated at L327-328.

**5. PARTIAL / one REFUTED.**
- `is_process_running|is_process_alive` in `src/sase/ace/`: 41 total line matches (33 excluding import lines), across 14 files — ~41 VERIFIED.
- Loader path: 8 call sites under `src/sase/ace/tui/models/` — VERIFIED at that scope; only 6 under `models/_loaders/` specifically.
- `update_agent_artifact_index_for_marker_mutation`: REFUTED — 103 line matches / 39 non-import call sites across 38 files in `src/`. Only 6 call sites fall inside `src/sase/ace/`, so "~10" is wrong at repo scope and low even at ACE scope.
- `src/sase/ace/tui/actions/agents/`: 161 `.py` files (claim ~162) — VERIFIED.
- Files referencing `artifacts_dir` there: exactly 28 — VERIFIED.

**6. VERIFIED.** `src/sase/agent/running.py:45` — `def kill_named_agent(name: str, *, exact_name: bool = False) -> _KillResult`; re-resolves via `find_named_agent(name)` (L60), returns `reason/status="not_found"` (L62-67, L70-75) and `"already_completed"` (L90-91).

**7. VERIFIED.** `src/sase/ace/agent_query/pushdown.py:26` `compile_agent_query_pushdown()`; `CandidateFilterWire = dict[str, object]` (L12) — JSON-able. Serialized at `src/sase/core/agent_scan_wire_conversion.py:107` and consumed by Rust at `sase/repos/linked/sase-core/crates/sase_core/src/agent_scan/index.rs:260` (`pub candidate_filter: Option<AgentArtifactCandidateFilterWire>`) and `index.rs:3716,3733` (`candidate_matches_query_filter`). Caller: `src/sase/ace/tui/models/agent_loader.py:500-520`.

**8. PARTIAL — `_submit_tracked_proc()` does NOT exist in production code.** It appears only in `tests/_agent_cleanup_proc_helpers.py:114` (a fake app harness) and is asserted to live in `src/sase/ace/tui/actions/proc_actions.py` by the memory note `sase/memory/tui_perf.md:31` — that note is stale: `proc_actions.py` is 45 lines and defines only `ProcActionsMixin` (L24); neither `_submit_tracked_proc` nor `_submit_proc` is defined anywhere in `src/`. The real production analogs are `_submit_launch_proc` (`src/sase/ace/tui/actions/agent_workflow/_launch_procs.py:57`, `LaunchProcMixin` L54) and `_submit_cleanup_proc` (`src/sase/ace/tui/actions/agents/_cleanup_procs.py:34`, `CleanupProcMixin` L31), delegating to `submit_agent_launch` / `submit_agent_cleanup` in `..agent_durable`.
The pump-free helpers are VERIFIED: `src/sase/ace/tui/util/pump_tasks.py:64` `spawn_pump_free_task`, L111 `cancel_pump_free_tasks` (~20+ call sites across `ace/tui/modals`, `widgets`, `src/sase/pager/`).

**9. VERIFIED.** `src/sase/axe/_ensure_timer.py:29` `install_ensure_timer()` writes `sase-axe-ensure.service` / `sase-axe-ensure.timer` (L16-17) into `~/.config/systemd/user` (`_systemd_user_unit_dir` L161-164) and activates via `systemctl`. Wired to the CLI at `src/sase/main/axe_handler.py:95-118` (`ensure_sub == "install"` → L108), re-exported via `src/sase/axe/ensure.py:25`.

**10. VERIFIED.** `src/sase/integrations/mobile_gateway.py:285-297` — `_resolve_gateway_command()` tries `shutil.which("sase_gateway")` (L286), else sibling `sase-core/target/{debug,release}/sase_gateway` (L290-296), returning `()` when neither exists. No wheel-packaged binary path.

**11. VERIFIED.** `src/sase/default_config.yml:38` `max_running_agents: 10`, preceded by a comment (L30-37) describing it as a host-wide runner-slot cap. No `machines:` config section exists — only per-machine identity fields (`id.machine_name`, `src/sase/config/layers.py:35`, `src/sase/config/sase.schema.json:1067`); "machines" appears in schema only inside description prose.

**12. VERIFIED.** `src/sase/ace/tui/util/fs_watcher.py:9-11` docstring states inotify via `ctypes` and silent decline on non-inotify platforms; enforced at L201 `if not sys.platform.startswith("linux"): return None` inside `_libc()` (L196).

**13. VERIFIED.** `5a65fa4fc "feat: revert sase-3e daemon rollout"` (Bryan Bugyi, 2026-05-14; parent `c512db755`). It removed the local daemon plus projection, provider-host, scheduler, rollout-control and their ACE read/write surfaces introduced by the sase-3e legend, along with the associated docs (`docs/local_daemon.md`, `docs/rust_backend.md`, `docs/troubleshooting/daemon-operations.md`), SDD artifacts, fixtures, tests, config schema defaults and CLI references, returning the tree to direct execution paths (PLAN=`sdd/tales/202605/revert_sase_3e_legend.md`).

**14. VERIFIED.** `src/sase/ace/tui/models/_agent_state.py` is 532 lines; `class AgentState` at L22 with 210 annotated field lines (claim ~209 — within rounding; the count includes any nested annotations).

Report written. Now let me verify the final layout and check for whitespace issues (the research repo has a trailing-whitespace gate that caught researcher A).

Layout is correct and clean. Now I'll add the supersedes link so the consolidated report is the canonical successor of the original fleet research.

One epic (`sase-lh`, the Procs rename) is topically adjacent. Let me check whether it actually caused the symbol drift before deciding where to record this.

The symbol was removed by closed work (`sase-m9.3.1.4`), not an in-progress epic, and no duplicate exists — so a new `memory` task bead is warranted. Let me check the type's required fields.

The consolidation is complete. The final layout is in place at `202609/tailnet_fleet_federation/` in the research sidecar — `tailnet_fleet_federation__a.md` (research.1g.cdx's `tailnet_agent_fleet_v2.md`), `tailnet_fleet_federation__b.md` (research.1g.cld's `cross_machine_agent_control_plane.md`), and the consolidated `tailnet_fleet_federation.md` — with the host finalizer committing the sidecar and the new report linked as superseding the original `tailnet_agent_fleet` research.

**The consolidated recommendation** (all three reports — both researchers plus the earlier consolidated proposal — independently converged on the transport, and my verification confirms it): extend `sase_gateway` into one supervised per-user binary with a `serve` role (each machine is sole authority for its own agents: resident Rust reads, a liveness-resolution pass, a revision feed, loopback bind published per-device via Tailscale Serve) and a `federate` role beside the viewer (per-peer caches, cursors, circuit breakers, an operation journal, a Unix-socket API for ACE). The fleet wire is the `AgentArtifactScanWire` contract Rust and Python already share, wrapped in a small envelope of machine identity, freshness, resolved liveness, and opaque content handles; ACE consumes it through the provider seam that already exists. No new messaging framework, row model, or identity space. Read-only fleet visibility ships first; mutations only behind a durable idempotency journal, host-side name resolution, revision fencing, and fault-injection gates.

**How I resolved the reports' disagreements:**

- **Client placement** — B's federate daemon wins over A's federate-in-ACE and the predecessor's `sase_core` placement. I verified the crate graph: `sase_core` has no tokio/reqwest and is deliberately PyO3-free, the gateway already has both, and Python has 13 deps with no HTTP client. The federate role also gives the one payoff nothing else offers: `sase mobile` sees the whole tailnet through one pairing.
- **Identity** — B and the predecessor win: machine-qualified names plus a pinned gateway identity, no new UUID space. But A's idea of reserving run identity durably *before* spawn is kept inside the launch journal. One correction to B: `machine_hood` exists but has zero internal Rust callers — the plumbing is real work, not a citation.
- **Wire** — B wins: the scan wire plus envelope, with A's envelope requirements folded in. A's actual objection was to freezing the mobile DTO, which nobody proposes.
- **Event cursor** — B's durable index revision subsumes A's boot-epoch design entirely, since the store becomes the log and cursors survive daemon restarts.

**What my own verification added:** A's security findings all confirmed and promoted to Phase 0 blockers — `pair_start` is unauthenticated and hands back the pairing code (`routes.rs:562-651`), which becomes tailnet-reachable exactly when you publish via Serve; `devices.json` is fully rewritten and an audit line fsynced on *every* authenticated request. B's SSE finding confirmed (replay then heartbeats only; `publish_agents_changed` fires from just the gateway's own four mutation handlers). The phantom-liveness finding reproduced: 1,871 active-status index rows vs 27 actually-alive agents on athena right now, with the same SQLite queries answering in 12–15 ms against the 195 MB index. I also caught two errors in B that the report corrects: `_done_snapshot_loaders.py` is not perfectly filesystem-free (one enrichment `.exists()` is reachable for RUNNING rows — the rows a fleet view cares most about), and B cited `_submit_tracked_proc()`, a symbol that now exists only in a test harness because the durable-proc-observer migration removed it.

That stale symbol traces to a line in your `tui_perf.md` memory note, so I filed **`sase-x9`** (small `memory` task, READY) with the corrected citation. The report also ends with five open questions for you, the sharpest being whether the MacBook should run a supervised daemon or just an ACE-lifetime federate child — the answer decides whether launchd work is in scope at all.
