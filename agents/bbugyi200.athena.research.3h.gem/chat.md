# Chat History - ace-run (research.3h.gem)

- **TIMESTAMP:** 2026-10-03 13:49:54 EDT
- **MODEL:** agy/gemini-3.8-flash-high
- **AGENT:** research.3h.gem
- **PROMPT:** `~/.sase/multi_prompts/202610/gh_sase_org__sase-multiprompt-261003_133508.md`

## Prompt

%id(gem, clan=research.3h)
%m:agy/gemini-3.8-flash-high %q(1.5x, w=0.25)
#gh:gh_sase-org__sase 
You are researcher gem in a 5-researcher swarm.
The other researchers, `research.3h.cdx`, `research.3h.cld`, `research.3h.grk`, `research.3h.mus`, are independently investigating the same request and will write their own self-named reports ending in `__cdx.md` and `__cld.md` and `__grk.md` and `__mus.md`. Your report will end in `__gem.md`.

Conduct your research independently and form your own conclusions. Do NOT attempt to
locate, open, read, or otherwise consult the other researcher's report from this swarm,
even if it becomes available before you finish. Do not obtain that peer's findings
indirectly through its chat transcript, summaries, or requests to the peer. You may
independently use the same external sources, shared input material, and unrelated prior
research. You may check filenames or file existence to avoid overwriting your own
output, but do not inspect the peer's report contents. If you encounter its filename,
leave the report alone. The lead researcher will read every report and synthesize their
findings after you have all finished.

My
apollo machine keeps killing all of its sase agents due to OOM errors I believe. Can you
dig into this / do some research with the goal of helping me figure out what is causing
this and fix it? End your analysis with a recommended solution. 
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

# Investigation & Research Report: Cascading SASE Agent OOM Terminations on Apollo

The investigation into host **`apollo`** (`apollo.tail297af1.ts.net`, Linux 6.8.0-138-generic, Ubuntu 24.04 LTS, 16 CPUs, 31 GiB RAM, 0B Swap) has concluded. 

The durable research report has been written and registered as a durable snapshot:
- **Report Path:** [`apollo_agent_oom_cascading_kills_investigation__gem.md`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_44/sase/repos/research/202610/apollo_agent_oom_cascading_kills_investigation__gem.md)
- **Artifact Ref:** `file:explicit:904ba18537f570f5baef732c` (`research:202610/apollo_agent_oom_cascading_kills_investigation__gem.md`)

---

## 1. Executive Summary & Core Diagnosis

Your suspicion that OOM is killing agents is correct, but the reason **all** agents die simultaneously (along with the SASE TUI) is a **fate-sharing cgroup cascade** caused by three intersecting factors:

1. **The Physical Trigger (Zero Swap on Apollo):**
   Apollo has 31 GiB of physical RAM but **0 bytes of swap**. When concurrent agent tasks (e.g., Rust compilation via `cargo`, test suites with `pytest`, AST analysis with `symvision`, or active LLM harness sessions) generate spikes in anonymous memory, the kernel has no paging fallback. It aggressively evicts file pagecache (which plummeted from ~17.5 GiB down to 2.7 GiB during the incidents). When clean pagecache can no longer be reclaimed fast enough, direct memory reclaim fails, and the kernel OOM killer triggers.

2. **The Blast Radius (Ubuntu 24.04 Tmux Scopes with `OOMPolicy=stop`):**
   On modern Ubuntu 24.04 (systemd 255), `tmux` places each child pane into a transient systemd scope: `tmux-spawn-<uuid>.scope`. By default, systemd scopes enforce:
   - `OOMPolicy=stop`
   - `KillMode=control-group`
   Under `OOMPolicy=stop`, if **any single process** in the scope is killed by the OOM killer, systemd considers the unit to have failed and sends **SIGTERM (exit code 143)** followed by SIGKILL to **every process in that cgroup**.

3. **The Architectural Bug (`src/sase/detach_scope.py`):**
   SASE's process launcher calls `detach_scope()` to isolate background agents into their own `systemd-run --user --scope`. However, `detach_scope.py` contained an overly restrictive guard: it only escaped if the parent process was already a SASE-owned unit (`sase.service` or starting with `sase-`). When `sase -p tui` is launched inside tmux, the parent scope is `tmux-spawn-<uuid>.scope` (which is not SASE-owned). Consequently, `detach_scope()` **silently skipped escaping**, leaving every agent launched by the TUI running inside the TUI's single `tmux-spawn-*.scope`.

When any single test, compiler, or sub-process in that tmux scope gets OOM-killed, systemd terminates the whole scope, killing the SASE TUI and every agent running under it at the exact same instant.

---

## 2. Incident Evidence from Apollo

Analysis of the journal, SAR metrics, and agent artifacts on `apollo` revealed two major cascading teardowns today (2026-10-03):

### Incident 1: 16:24:28 UTC (12:24:28 EDT)
- **Scope:** `tmux-spawn-1a05ddb8-e19b-4439-9e24-e3e8a3367627.scope`
- **Memory Peak:** **29.0 GiB** (out of 31 GiB physical RAM)
- **Killed Agents:** All three active agents—`4s.f0` (codex), `4r.f0` (codex), and `bob-cli-3u.land` (claude)—died at 12:24:30–12:24:38 with exit code 143 (SIGTERM).
- **Journal Log:**
  ```text
  Oct 03 16:24:28 apollo systemd[1162]: tmux-spawn-1a05ddb8-….scope: A process of this unit has been killed by the OOM killer.
  Oct 03 16:25:58 apollo systemd[1162]: tmux-spawn-1a05ddb8-….scope: Failed with result 'oom-kill'.
  Oct 03 16:25:58 apollo systemd[1162]: tmux-spawn-1a05ddb8-….scope: Consumed … 29.0G memory peak.
  ```

### Incident 2: 17:32:39 UTC (13:32:39 EDT)
- **Scope:** `tmux-spawn-d263949a-07c1-42bd-b1b8-457137a334ea.scope`
- **Killed Agents:** `sase-1fs.1--1` (muse) and `4r.f1.f0` (codex) both died simultaneously.
- **Journal Log:**
  ```text
  Oct 03 17:32:39 apollo systemd[1162]: tmux-spawn-d263949a-….scope: A process of this unit has been killed by the OOM killer.
  Oct 03 17:33:03 apollo systemd[1162]: tmux-spawn-d263949a-….scope: Failed with result 'oom-kill'.
  ```
- **SAR Data:** Shows direct reclaim (`pgscand/s = 936.58`, `pgscank/s = 16091.04`) and 14 GiB of cached memory dumped right before the kill.

---

## 3. Recommended Solution

A multi-tiered solution is required to fix both the **memory trigger** (running out of RAM) and the **blast radius** (cascading kills across all agents).

### Tier 1: Host-Level Operational Fix (Immediate Action on Apollo)
Apollo has 51 GiB of available storage on `/dev/vda1`. Provision a **16 GiB swap file** and tune swappiness so the kernel has headroom to absorb memory spikes without thrashing:

```bash
# 1. Allocate and activate a 16 GiB swap file
sudo fallocate -l 16G /swapfile
sudo chmod 600 /swapfile
sudo mkswap /swapfile
sudo swapon /swapfile

# 2. Persist in /etc/fstab
if ! grep -q '/swapfile' /etc/fstab; then
    echo '/swapfile none swap sw 0 0' | sudo tee -a /etc/fstab
fi

# 3. Configure sysctl to prefer RAM while allowing paging under pressure
sudo tee /etc/sysctl.d/99-sase-memory.conf << 'EOF'
vm.swappiness = 15
vm.vfs_cache_pressure = 50
EOF

sudo sysctl --system
```

### Tier 2: Land the SASE Cgroup Isolation Patch (Software Architecture Fix)
A plan addressing the software flaw has already been designed and is actively being authored in workspace 10 (`sase_10`) on Apollo under `plans/202610/detach_scope_user_manager_escape.md`:
1. **Expand `detach_scope.py`:** Escape into a dedicated transient scope `sase-agent-<uniquifier>.scope` whenever the user systemd manager is reachable (`_user_manager_reachable()`), specifically covering tmux pane scopes (`tmux-spawn-*.scope`).
2. **Set `OOMPolicy=continue`:** Pass `--property=OOMPolicy=continue` on all transient scopes created by `systemd-run`. If an individual compiler or test process exceeds memory and gets killed, systemd will **not** terminate the agent runner or sibling processes.
3. **Set `OOMPolicy=continue` on `sase.service`:** Update `src/sase/service/platform_units.py` so the SASE service host does not terminate on child OOMs.
4. **Kill Provenance Telemetry:** Record `kill_source: "external"` and cgroup OOM deltas in `done.json` so external terminations are clearly reported in telemetry instead of being masked as user kills.

### Tier 3: Workload & Concurrency Governance (Future Guardrails)
- Once agents run in isolated scopes, set per-agent memory quotas (e.g. `--property=MemoryHigh=16G --property=MemoryMax=24G`).
- Bound build concurrency (e.g. `CARGO_BUILD_JOBS=8` instead of 16) to avoid saturating 31 GiB when multiple agents run compilations simultaneously.
