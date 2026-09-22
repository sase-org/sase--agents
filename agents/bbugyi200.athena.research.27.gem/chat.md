# Chat History - ace-run (research.27.gem)

- **TIMESTAMP:** 2026-09-22 08:31:57 EDT
- **MODEL:** agy/gemini-3.8-flash-high
- **AGENT:** research.27.gem
- **PROMPT:** `~/.sase/multi_prompts/202609/gh_sase_org__sase-multiprompt-260922_081822.md`

## Prompt

%id(gem, clan=research.27)
%m:agy/gemini-3.8-flash-high %q(w=0.25)
#gh:gh_sase-org__sase 
You are researcher gem in a 3-researcher swarm.
The other researchers, `research.27.cld`, `research.27.mus`, are independently investigating the same request and will write their own self-named reports ending in `__cld.md` and `__mus.md`. Your report will end in `__gem.md`.

Conduct your research independently and form your own conclusions. Do NOT attempt to
locate, open, read, or otherwise consult the other researcher's report from this swarm,
even if it becomes available before you finish. Do not obtain that peer's findings
indirectly through its chat transcript, summaries, or requests to the peer. You may
independently use the same external sources, shared input material, and unrelated prior
research. You may check filenames or file existence to avoid overwriting your own
output, but do not inspect the peer's report contents. If you encounter its filename,
leave the report alone. The lead researcher will read every report and synthesize their
findings after you have all finished.

Can you do some research with the
goal of improving the recently added "sase services" feature (see the sase-11y epic bead
for context)? Look for any bugs that should be fixed, objective improvements that
should be made, or larger extensions that you think I should consider making. End your
analysis with a recommended set of changes you think I should definitely make and (if
you could think of any that deserve to be mentioned) any larger extensions that you
think I should consider making. 
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

# Research Report: Improving the SASE Services Feature

**Author**: `research.27.gem`  
**Report File**: [`sase_services_enhancements_and_roadmap__gem.md`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_32/sase/repos/research/202609/sase_services_enhancements_and_roadmap__gem.md)  
**Registered Artifact**: `ref: file:explicit:244d4aadebdc4a82be28b037` (`research:202609/sase_services_enhancements_and_roadmap__gem.md`)

---

## Executive Summary

An independent, end-to-end investigation of the newly introduced **SASE Services** feature (spanning epic `sase-11y` and child landing `sase-11y.11`) was conducted across `src/sase/service/`, `src/sase/main/`, `src/sase/ace/tui/`, `src/sase/procs/`, and the Rust core backend `crates/sase_core/src/service/`.

While the foundational architecture—combining native supervisor integration (`systemd` user units on Linux, `launchd` on macOS), Rust-owned config composition and state validation, and cgroup isolation via [`detach_scope`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_32/src/sase/detach_scope.py)—is clean and solid, the analysis uncovered **11 distinct defects (including a live, confirmed no-op bug in `sase scheduler restart`)**, several **operational blind spots**, and substantial opportunities for **operational improvements and larger architectural extensions**.

---

## 1. Confirmed Defects & Bugs Found

### 1.1 Live Bug: `sase scheduler restart` is a Broken No-Op
- **Location**: [`src/sase/main/scheduler_handler.py#L72-L79`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_32/src/sase/main/scheduler_handler.py#L72-L79)
- **Root Cause**: `handle_scheduler_command()` invokes [`restart_service_proc("scheduler", delay=0.0)`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_32/src/sase/service/actions.py#L82-L105). With `delay=0.0`, the stop marker is recorded and cleared in microseconds. The asynchronous background service host never observes the stop marker during its reconcile loop.
- **Verification**: Verified live on this machine. Running `sase scheduler restart` printed `"requested service proc scheduler restart"`, but `sase scheduler status` confirmed the PID remained identical (`pid 1964543`).

### 1.2 Architectural Race: The Stop/Clear Restart Anti-Pattern
- **Location**: [`src/sase/service/actions.py#L82-L105`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_32/src/sase/service/actions.py#L82-L105)
- **Root Cause**: `restart_service_proc()` simulates an edge-triggered command using level-triggered state by writing a stop marker, sleeping an arbitrary duration (`delay=0.5`), and immediately clearing the stop marker. If the host is under load or the child process takes >0.5s to shut down, the restart is either dropped or the stop marker is cleared before the previous process finishes terminating.

### 1.3 Invisible Orphan Service Procs in CLI & TUI
- **Location**: [`src/sase/main/service_handler.py#L103, L227`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_32/src/sase/main/service_handler.py#L103) and [`src/sase/ace/tui/actions/axe_display/_loader_items.py#L130-L142`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_32/src/sase/ace/tui/actions/axe_display/_loader_items.py#L130-L142)
- **Root Cause**: While `sase-core` derives orphan procs into `ServiceStatusSnapshot.orphans`, `sase service status`, `sase service proc list`, and the TUI Services sidebar iterate exclusively over `snapshot.procs`. Orphan processes (e.g. running services that were renamed or unconfigured) are completely invisible in all standard interfaces.

### 1.4 `enable_service_proc` Fails to Clear Boot Stop Markers
- **Location**: [`src/sase/service/actions.py#L107-L123`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_32/src/sase/service/actions.py#L107-L123)
- **Root Cause**: If a service was stopped via `sase service proc stop <name>`, enabling it later via `sase service proc enable <name>` sets `enablement = True` but does not clear `state.stops[name]`. The host sees the stop marker and leaves the proc stopped.

### 1.5 `start_service_proc` Reports False Success on Disabled Procs
- **Location**: [`src/sase/service/actions.py#L41-L61, L153-L160`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_32/src/sase/service/actions.py#L41-L61)
- **Root Cause**: [`_require_startable()`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_32/src/sase/service/actions.py#L153-L160) validates only `available`, completely ignoring whether the proc is enabled. Running `sase service proc start` on a disabled proc outputs `"requested service proc <name> start"`, but the host refuses to launch it.

### 1.6 Stale `status.json` Reports Persist Across Crashes & Restarts
- **Location**: [`src/sase/service/host_support.py#L97-L117`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_32/src/sase/service/host_support.py#L97-L117)
- **Root Cause**: `status.json` in `~/.sase/service/procs/<name>/` is never unlinked on process exit or launch. When a service restarts, [`read_reported_status()`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_32/src/sase/service/host_support.py#L97-L117) immediately displays the old report from the prior run—even when `updated_at < started_at`.

### 1.7 `entry.after` Dependency Ordering is Unconsumed at Runtime
- **Location**: [`src/sase/service/host.py#L252-L257`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_32/src/sase/service/host.py#L252-L257)
- **Root Cause**: `after: [...]` is validated for cycles in `sase-core` and hashed in `entry_signature`, but [`_reconcile_desired()`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_32/src/sase/service/host.py#L215-L257) launches procs concurrently in dictionary order without checking whether dependencies are running or ready.

### 1.8 Catastrophic O(N*M) Log Rewriting in `append_bounded_log`
- **Location**: [`src/sase/service/host_support.py#L124-L141`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_32/src/sase/service/host_support.py#L124-L141)
- **Root Cause**: Once a service log reaches `log_max_bytes` (2 MB default), every read chunk (<4 KB) triggers: write chunk -> seek -> read entire 2 MB into memory -> open in `"wb"` (truncating to 0 bytes) -> rewrite entire 2 MB. This causes extreme disk I/O thrashing (GBs of writes), tears multi-byte UTF-8 boundaries, and causes concurrent readers (TUI) to see 0-byte truncations.

### 1.9 Duplicate Instance Spawn on Stuck Children
- **Location**: [`src/sase/service/host.py#L228-L231, L252-L257`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_32/src/sase/service/host.py#L228-L231)
- **Root Cause**: If a child ignores `SIGKILL` and times out during [`_stop_child()`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_32/src/sase/service/host.py#L467-L504), the host pops it from `self._children` anyway, and immediately launches a second instance in the same loop pass.

### 1.10 `apply_service_init` Leaves Active Services on Stale Config
- **Location**: [`src/sase/service/platform.py#L183-L191`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_32/src/sase/service/platform.py#L183-L191)
- **Root Cause**: Running `sase service init --yes` applies unit file and `service.env` updates and reloads systemd, but does not restart active units (`start=not already_active`). The running host remains on the old binary and environment with no warning given.

### 1.11 Serial Child Termination During Host Shutdown
- **Location**: [`src/sase/service/host.py#L505-L510`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_32/src/sase/service/host.py#L505-L510)
- **Root Cause**: `_stop_all_children()` stops children sequentially. If each child takes up to 5–10s to gracefully terminate, shutdown takes $\sum T_i$, risking ungraceful `SIGKILL` from systemd.

---

## 2. Objective Improvements (Usability & Observability)

1. **CLI Log Streaming (`-f` / `--follow`)**: Add real-time tailing to `sase service logs` and `sase service proc logs <name>`.
2. **Enriched `sase service proc show`**: Surface restart counts, last exit details (code/signal/time), crash-loop backoff status, reported status, uptime, and description.
3. **Enhanced CLI Status Tables**: Add `PID`, `Restarts`, and `Uptime` columns to `sase service status` and `sase service proc list`.
4. **Dedicated `sase service proc kill <name>`**: Provide direct CLI signal delivery to running procs without needing raw proc ID lookups.
5. **Runtime Service Health in `sase doctor`**: Check host running state, heartbeat freshness, and crash-looping procs rather than just static unit files on disk.
6. **Configurable Host Environment Passthrough**: Support configuring `service.capture_env_names` in `sase.yml` for proxy variables (`HTTP_PROXY`, `HTTPS_PROXY`, `NO_PROXY`), custom CA certs (`SSL_CERT_FILE`), and locales.
7. **Robust Dual-File Log Rotation**: Replace the rewrite loop in `append_bounded_log` with standard dual-file rotation (`.log` and `.log.1`).
8. **TUI Services Tab Polish**: Document `r` (restart) in the help modal, surface orphan procs in the sidebar, and expose service procs in `ProcessSelectModal` (`!x`).

---

## 3. Recommended Larger Extensions (Future Epics)

1. **Declarative Health Checks & Dependency Readiness Gating**:
   - Add `healthcheck:` specs (`http_get`, `tcp_socket`, `exec_cmd`, `heartbeat_ttl`) to `service.procs`.
   - Automatically restart deadlocked daemons and delay starting procs with `after: [dep]` until `dep` transitions to `healthy`.
2. **Configured (Non-Transient) Oneshots & Boot Hooks**:
   - Allow declaring one-off initialization tasks (`mode: oneshot`) in `service.procs` (e.g. database/state migrations, workspace cleanup) that run before daemons start.
3. **Resource Limits & Sandboxing (Systemd Slices / Cgroups)**:
   - Allow service procs to specify `memory_max` and `cpu_quota`, launching via systemd transient scopes (`systemd-run --slice`) to prevent memory leaks from destabilizing the host.
4. **Cross-Machine Service Control via Mobile Gateway / Tailnet**:
   - Expose service inspection and restart endpoints on the gateway API, enabling `sase machine service <alias> status|restart|logs` across Athena, Apollo, etc.
5. **Unix Domain Socket Control Plane (UDS / RPC)**:
   - Replace file-based state polling and `SIGUSR1` signals with a lightweight UDS RPC server (`~/.sase/service/host.sock`), providing synchronous restart responses, instant error reporting, and live log streaming.

---

## 4. Definitive Action Plan

### Phase 1: Defect Remediation (Immediate Priority)
- [x] Fix `sase scheduler restart` by removing `delay=0.0`.
- [x] Introduce explicit restart generation tokens in `ServiceState` (Rust + Python).
- [x] Render `snapshot.orphans` in CLI status/list and TUI sidebar.
- [x] Clear boot stop markers in `enable_service_proc`.
- [x] Validate enablement in `start_service_proc`.
- [x] Invalidate stale `status.json` on proc launch/exit.
- [x] Implement dual-file rotation in `append_bounded_log`.
- [x] Prevent duplicate launches of hung children in `_stop_child`.
- [x] Parallelize child termination in `_stop_all_children`.
- [x] Enforce `entry.after` ordering at launch.

### Phase 2: Usability & Observability
- [x] Add `-f/--follow` to `service logs` and `proc logs`.
- [x] Enrich `sase service proc show` with restart count, exit details, backoff, and uptime.
- [x] Add `PID`, `Restarts`, and `Uptime` columns to CLI status tables.
- [x] Add runtime service checks to `sase doctor`.
- [x] Add `service.capture_env_names` for proxy and custom env vars.

### Phase 3: Architectural Extensions
- Plan standalone epics for: (1) Declarative Health Checks, (2) Configured Oneshots, (3) UDS Control Plane, and (4) Fleet Service Control.

---

*The full, unabridged research document has been committed to the research repository and registered as a durable artifact at:*  
[`sase_services_enhancements_and_roadmap__gem.md`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_32/sase/repos/research/202609/sase_services_enhancements_and_roadmap__gem.md)  
*Artifact Reference*: `ref: file:explicit:244d4aadebdc4a82be28b037`
