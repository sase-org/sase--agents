%queue(weight=1)
#fork:sase-1t3.14--plan
%model:muse-spark-1.3-contributor@xhigh

%macros_enabled:false
# Monitored command finished

**Command:**

```text
/tmp/sase-1t3.14-soak.sh
```

**Directory:**

```text
/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_22
```

| | |
| --- | --- |
| **Outcome** | COMPLETED — exit 0 |
| **Started** | 2026-11-19T01:08:18.041304+00:00 |
| **Finished** | 2026-11-19T02:42:24.015158Z |
| **Elapsed** | 1h 20m 11s of a 2h 30m 0s budget |
| **Output** | 182 bytes · evidence refs: `file:monitor-diagnostic-manifest:z66x83kvrf2k`, `file:monitor-retained-log:z66x83kvrf2k` · raw output omitted: `facts_only` · full log: `sase monitor show z66x83kvrf2k --all-lines` |

**Why this was monitored:** sase-1t3.14 separate-instance 1h soak of the whole epic under real load

## Continuation checkpoint

- **Ref:** `local:continuation/checkpoints/monitor_start-3d9d96d4bbde93d2.json`

**Checkpoint (JSON):**

```text
{
  "kind": "monitor_start",
  "payload": {
    "command": "/tmp/sase-1t3.14-soak.sh",
    "cwd": "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_22",
    "member_agent_name": "sase-1t3.14--mon",
    "monitor_id": "z66x83kvrf2k",
    "next_output": "auto",
    "parent_node_ids": [
      "agent-delta:20261117060253:98dff81f9eefa7ed"
    ],
    "project_name": "gh_sase-org__sase",
    "request_fingerprint": "sha256:46d084a3f4d94a0c3c0fc78a043ae6728c62f45e19e96fe0fb5f5ba898d4eaf4",
    "starter_agent": "sase-1t3.14--plan",
    "starter_artifacts_dir": "/home/bryan/.sase/projects/gh_sase-org__sase/artifacts/ace-run/202611/17/20261117060253"
  },
  "recorded_at_epoch": 1795051332.917178,
  "schema_version": 1
}
```


## Your next action

Finish sase-1t3.14 soak-verify. 1) Find the soak dir: newest ~/.sase/perf/sase-1t3.14-soak-*/; read SOAK_SUMMARY.md and soak.log. The soak TUI is already quit; do NOT relaunch it. 2) Build the stage-by-stage table from the epic plan (sase/repos/plans/202611/tui_storm_trust_heap_recovery.md, soak-verify section: Storm / Construction / Provider substage / Loads / Startup / Heap / Interaction / Overall) with research baseline, target, and measured values from the soak dir (startup row, stalls heartbeats incl. default_executor gauge fields, agent_loads disk substages, jk samples, trace summary, proc_timeline.tsv, py-spy dumps, freeze reports). Supplement j/k only with the sase-1t3.13.1.5 bench numbers already on bead sase-1t3.13 if the soak has too few key samples; say which source each number came from. 3) Record the table as a note on the EPIC bead with: sase bead note sase-1t3. 4) Read the docs_writing memory first (sase memory read docs_writing.md --reason ...), then update docs/contribute/perf-runbook.md with the recovered baselines and the new executor-saturation gauge fields (tui_perf.md must NOT be edited: epic decision tui_perf_memory=no). 5) For every missed target record: sase bead note sase-1t3.14 PROPOSED FOLLOW-UP: <one line plus evidence>. Also record a clean-base check failure identically instead of holding the bead open. 6) Run sase tool run check for the runbook edit (the soak script rebuilt .venv via just install-venv; if the tool escalates, join the printed run with sase monitor start -J, do not rerun). 7) Run sase bead epic-symbols sase-1t3.14 (must be empty), then close ONLY sase-1t3.14 with sase bead close sase-1t3.14 --note <what you verified>. Never close the parent epic sase-1t3. 8) Finish through /sase_final.
%macros_enabled:true