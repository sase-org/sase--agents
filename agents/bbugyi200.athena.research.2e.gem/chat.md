# Chat History - ace-run (research.2e.gem)

- **TIMESTAMP:** 2026-09-24 08:32:10 EDT
- **MODEL:** agy/gemini-3.8-flash-high
- **AGENT:** research.2e.gem
- **PROMPT:** `~/.sase/multi_prompts/202609/gh_sase_org__sase-multiprompt-260924_081856.md`

## Prompt

%id(gem, clan=research.2e)
%m:agy/gemini-3.8-flash-high %q(w=0.25)
#gh:gh_sase-org__sase 
You are researcher gem in a 3-researcher swarm.
The other researchers, `research.2e.cld`, `research.2e.mus`, are independently investigating the same request and will write their own self-named reports ending in `__cld.md` and `__mus.md`. Your report will end in `__gem.md`.

Conduct your research independently and form your own conclusions. Do NOT attempt to
locate, open, read, or otherwise consult the other researcher's report from this swarm,
even if it becomes available before you finish. Do not obtain that peer's findings
indirectly through its chat transcript, summaries, or requests to the peer. You may
independently use the same external sources, shared input material, and unrelated prior
research. You may check filenames or file existence to avoid overwriting your own
output, but do not inspect the peer's report contents. If you encounter its filename,
leave the report alone. The lead researcher will read every report and synthesize their
findings after you have all finished.

I've been thinking about implementing a
new service proc that serves as an optional daemon that makes reading and, ideally
(though this might be harder), writing sase beads much faster when it is running. I'm
not really sure if/how this will work though.

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

# Research Summary: SASE Bead Acceleration & Service Proc Daemon Architecture

**Researcher**: `gem` (Swarm Member)  
**Report File**: [`202609/bead_service_proc_daemon_performance__gem.md`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_36/sase/repos/research/202609/bead_service_proc_daemon_performance__gem.md)  
**Artifact Snapshot**: `file:explicit:8f456bfed07a2c8e77e92aec` (Label: `research:202609/bead_service_proc_daemon_performance__gem.md`)

---

## 1. Empirical Profiling & Root Cause Analysis

Profiling the production store (5,968 total beads, 1,712 stream JSONL files, 16 MB `issues.jsonl`) revealed distinct bottlenecks across the read and write paths:

| Operation | Current Latency | Dominant Bottleneck |
| :--- | :--- | :--- |
| `sase bead list` | **2.69 s** | Excluded from Rust fast-path in `bead_fast_path.py`; pays Python startup, argparse, and FFI object hydration costs. |
| `sase bead show` | **2.67 s** | Excluded from Rust fast-path; full event stream reduction in Python layer. |
| `sase bead stats` (Rust fast-path) | **0.83 s** | Re-opens and re-parses all 1,712 stream JSONL files in `crates/sase_core/src/bead/read.rs` on every single invocation. |
| `sase bead search` (Rust fast-path) | **0.93 s** | Deserializes every event stream into memory via `serde_json`. |
| TUI `load_project_beads` | **~2.5 s** | Calls `list_issues`, `ready`, and `blocked` sequentially, repeating the 1,712-file scan 3 times back-to-back. |
| TUI `store_mtime_key` | **~25 ms / poll** | Executes `rglob("*")` on `events/`, triggering ~1,700 `stat` syscalls every polling tick. |
| Mutating commands (`update`, `close`, `note`) | **1.8–4.5 s** | Serializes full 16MB `issues.jsonl`, runs `git commit`, and executes synchronous network `git push` to GitHub under lock contention. |
| Cold workspace start | **10–30+ s** | Initializing an agent in a fresh ephemeral workspace (`sase_<N>`) clones the sidecar repo via `git pack-objects`. |

---

## 2. Critique of the "Optional Service Proc Daemon"

### For Reads: An Over-Engineered Mismatch
A daemon serving queries over a Unix Domain Socket (UDS) can achieve <5ms queries, but SASE already links native Rust via `sase_core_rs`. An **in-process SQLite database (`beads.db`) in WAL mode** delivers **1–3ms reads** directly inside the CLI process—with zero daemon lifecycle management, zero IPC serialization, zero port/socket contention, and zero dual-stack maintenance. If direct reads can run in 2ms via embedded SQLite, a daemon adds operational complexity with no latency benefit.

### For Writes: Fundamentally Hazardous in SASE
Attempting to accelerate writes by having a daemon act as an asynchronous write-behind buffer (returning immediately while pushing Git in the background) introduces severe architectural failure modes:
1. **Breaks the SASE Single-Turn Agent Contract**: SASE agents run a single provider turn and exit immediately after declaring completion (*Decision 3: Agents Are Single-Turn*; *Decision 7: Completion Is Host-Owned*). If a daemon buffers a write that later fails to push (merge conflict, network disconnect, GitHub rate limit), the failure happens after the agent has terminated, leading to split-brain states across machines and lost task updates.
2. **Multi-Workspace Git Topology**: Agents run in isolated checkouts (`sase_<N>`), each with its own nested beads sidecar. A daemon cannot safely arbitrate Git commits across isolated workspace working trees without risking silent data destruction during AXE workspace eviction (`runner_workspace_beads.py`).
3. **Write Contention**: Centralizing asynchronous Git writes from concurrent agent swarms onto a single Git branch generates frequent rebase conflicts that cannot be reliably resolved without human intervention.

---

## 3. Recommended Adjustments to Requirements

1. **Decouple Read Performance from Daemon Uptime**: Read operations must be sub-15ms *unconditionally*, even when no daemon is active.
2. **Disallow Uncoordinated Write-Behind Buffering**: Retain the synchronous local commit and remote publication guarantee for agent milestones, while offering an explicit `--async` flag only for interactive human CLI commands.
3. **Repurpose the Service Proc**: Reframe the daemon from an RPC data server into a **Proactive Sync and Maintenance Supervisor** (`bead-syncd`).
4. **Decouple the 16MB Projection from the Write Path**: Stop regenerating `issues.jsonl` on every single mutation.

---

## 4. Recommended Solution: The Hybrid "Fast-Local, Safe-Remote" Architecture

### Layer 1: In-Process SQLite WAL Read Model (`beads.db`) in `sase_core`
- Activate the existing dormant `beads.db` file in the bead store directory using SQLite in WAL mode.
- Use watermarked synchronization: check `events/manifest.json` mtime (~0.1ms). If unchanged, query `beads.db` directly (lookups in **<1ms**, filtered listings in **2–4ms**).
- If modified, perform an incremental catch-up: read and reduce *only* the modified stream `.jsonl` files (using file mtime/size signatures, matching `bead_touch_index.rs`), and upsert into SQLite.

### Layer 2: Close the Python Fast-Path Bypass
- Remove `list`, `read`, and `show` from the bypass filter in `src/sase/main/bead_fast_path.py`.
- Implement native terminal rendering in `crates/sase_core/src/bead/cli/`, reducing `sase bead list` and `show` from **2,700ms to <15ms**.

### Layer 3: Streamlined Mutation Pipeline
- Append mutation event to `events/streams/<id>.jsonl` + upsert SQLite `beads.db` (<3ms).
- Commit local Git repository (<15ms).
- Defer monolithic 16MB `issues.jsonl` serialization to Git pre-push or background maintenance.

### Layer 4: The Optional `bead-syncd` Service Proc (Supervisor Role)
Implemented as a native service proc supervised by `sase service`:
- **Proactive Git Fetch/Rebase**: Periodically fetches remote changes in the background so local Git HEAD is constantly aligned with upstream, allowing write pushes to complete in **~300ms** (fast-forward) without rebase contention.
- **Filesystem Watcher**: Listens for file changes using `notify` to keep `beads.db` warm.
- **TUI Real-Time Push**: Emits change notifications directly to the SASE TUI, eliminating the 1,700-stat `rglob("*")` polling cycle.

---

## 5. Implementation Roadmap

- **Phase 1 (1–2 weeks, 100x Read Speedup)**: Implement the incremental SQLite WAL engine in `sase_core` and route `list`, `read`, and `show` to `bead_cli_execute`.
- **Phase 2 (1 week, 10x Write Speedup)**: Decouple 16MB `issues.jsonl` generation from the mutation hot path and streamline local Git commits.
- **Phase 3 (1–2 weeks)**: Implement the `bead-syncd` service proc under `sase service` for proactive remote fetching and TUI event streaming.
