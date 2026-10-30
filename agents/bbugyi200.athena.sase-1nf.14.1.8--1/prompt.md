%queue(weight=1)
#fork:sase-1nf.14.1.8--plan
%model:grok-4.6@medium

%macros_enabled:false
# Monitored command finished

**Command:**

```text
python3 /home/bryan/.cache/sase/tui-gc-soak-sase-1nf.14.1.8/soak_wait.py
```

**Directory:**

```text
/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_13
```

| | |
| --- | --- |
| **Outcome** | COMPLETED — exit 0 |
| **Started** | 2026-10-28T23:05:03.721732+00:00 |
| **Finished** | 2026-10-29T21:20:10.312302Z |
| **Elapsed** | 22h 15m 5s of a 24h 0m 0s budget |
| **Output** | 139 KiB · log file: `diagnostics/retained_logs` · evidence refs: `file:monitor-diagnostic-manifest:zfxaj9fatwzd`, `file:monitor-retained-log:zfxaj9fatwzd` · raw output omitted: `file_refs` · full log: `sase monitor show zfxaj9fatwzd --all-lines` |

**Why this was monitored:** Wait for 24 post-warmup hours on retained Athena and Apollo TUI instances

## Continuation checkpoint

- **Ref:** `local:continuation/checkpoints/authored-29899109d4618e42.json`

**Checkpoint (JSON):**

```text
{
  "author": {
    "actor_id": "sase-1nf.14.1.8",
    "actor_kind": "user"
  },
  "constraints": [
    "Do not restart the capture TUIs merely to begin this phase.",
    "Never pool instances. If a process restarted, keep the interrupted segment, report it, and require user-confirmed preflight for a new complete interval.",
    "Do not close parent epic sase-1nf.14.1 or any ancestor.",
    "Do not create beads; use PROPOSED FOLLOW-UP notes on sase-1nf.14.1.8.",
    "Missing duration is a monitor continuation, not a completion claim.",
    "Honor DECISIONS; only memory notes they authorize may be edited.",
    "Run sase bead epic-symbols sase-1nf.14.1.8 before close; resolve leftovers.",
    "A complete honest FAIL/INCOMPLETE matrix may close this measurement phase."
  ],
  "coverage": [],
  "findings": [
    "Capture instances still live at soak start (2026-10-28T23:01Z).",
    "Athena app_instance_id 8b65de59 PID 4045198 start_ticks 114069905 boot 2e013859-5e29-418c-bf6d-035a5eeff435 source 196690f6cb4f3ddc89f0cfa18817688fd2675fed flags PERF=1 CENSUS=1 startup 2026-10-28T20:45:20.175219Z.",
    "Apollo app_instance_id 7e973b00 PID 1562336 start_ticks 166947655 boot 1e87418e-2b01-47ab-ad0d-eb23a80d5f96 same source and flags startup 2026-10-28T20:45:21.698951Z.",
    "Prior fixed-capture report research:202610/tui_gc_fixed_capture_20261028.md and bundle file:explicit:8ce7eae6df0b33fe4d6aae99 already FAIL GC/hitch/swap with incomplete four-hour and busy-hour evidence."
  ],
  "kind": "authored_checkpoint",
  "objective": "Complete sase-1nf.14.1.8 same-instance 24-hour TUI GC soak on Athena and Apollo.",
  "remaining_work": [
    "After deadline, confirm same PID/start_ticks/boot/instance IDs.",
    "Merge retained logs, run tools/tui_freeze_report --acceptance per host with explicit instance, raw boundaries, perf input, busy hour, required tabs.",
    "Verify coverage, hourly latency/GC/hitch summaries, full-window pause quantiles, swap history, four-hour RSS including final four hours.",
    "Publish research report and artifact refs, then close only sase-1nf.14.1.8."
  ],
  "schema_version": 1,
  "source_refs": [
    "plan:202610/measured_tui_gc_fixes.md",
    "research:202610/tui_gc_fixed_capture_20261028.md",
    "research:202610/tui_gc_measurement_20261023.md",
    "file:explicit:8ce7eae6df0b33fe4d6aae99",
    "bead:sase-1nf.14.1.8"
  ],
  "unresolved_decisions": []
}
```


## Your next action

Complete phase sase-1nf.14.1.8 (fixed-soak). Do not close parent epic sase-1nf.14.1 or any ancestor. Do not create beads; record follow-ups as PROPOSED FOLLOW-UP notes on sase-1nf.14.1.8.

Read `sase bead read sase-1nf.14.1.8 -r "Need soak scope, notes, and decisions"`, plan:202610/measured_tui_gc_fixes.md phase fixed-soak, and `/home/bryan/.cache/sase/tui-gc-soak-sase-1nf.14.1.8/{checkpoint.yaml,wait-state.json}`. Open `sase--research` with `sase repo open`. Read `lint_and_test.md`, `tui.md`, `tui_perf.md`, `tailnet.md`, and `sase_artifacts.md` through `sase memory read`. Read prior capture `research:202610/tui_gc_fixed_capture_20261028.md` and `file:explicit:8ce7eae6df0b33fe4d6aae99` plus r5 baseline `research:202610/tui_gc_measurement_20261023.md` through `sase artifact read`.

1. Confirm the same instances are still alive with matching PID/start_ticks/boot/flags: Athena 8b65de59 PID 4045198 start_ticks 114069905 boot 2e013859-5e29-418c-bf6d-035a5eeff435; Apollo 7e973b00 PID 1562336 start_ticks 166947655 boot 1e87418e-2b01-47ab-ad0d-eb23a80d5f96; both SASE_TUI_PERF=1 SASE_TUI_GC_CENSUS=1 source 196690f6cb4f3ddc89f0cfa18817688fd2675fed. If either restarted, keep the interrupted segment as evidence, report the interruption, and use /sase_questions for user-confirmed preflight of a new complete interval. Never pool instances. A correctness fix needs a fresh warmup/capture.

2. Use retained logs under /home/bryan/.cache/sase/tui-gc-soak-sase-1nf.14.1.8/retained and the wait-end snapshots. Preserve files outside rotating logs.

3. Run `tools/tui_freeze_report --acceptance` per host with explicit --instance, raw --since/--until covering at least 24 post-warmup hours (Athena warmup end 2026-10-28T21:05:20.175219Z, Apollo 2026-10-28T21:05:21.698951Z), --perf-path, selected busy hour, and required tabs (-t Agents plus any other evidenced usual tabs). Retain text, JSON, exit status, and coverage diagnostics. Cross-check full-collection counts against heartbeat totals. Do not subtract census collectors to force a pass.

4. Verify coverage, hourly latency/GC/hitch summaries, full-window pause quantiles, swap history, and four-hour RSS windows including the final four hours. Report long-term peaks/growth and any additional busy-hour samples. Carry forward fixed-capture workload and prompt evidence only for these same instances. Record interruptions, unknown evidence, and misses as such.

5. Publish the final research report in the opened research sidecar and `sase artifact create` the raw bundle; attach refs to sase-1nf.14.1.8. Then `sase bead epic-symbols sase-1nf.14.1.8` and resolve or re-key leftovers. Close only sase-1nf.14.1.8 with `--note` of what was verified. A complete honest FAIL/INCOMPLETE matrix may close this measurement phase. Missing duration requires another monitor continuation, not a completion claim. Run `sase tool run check` only if you changed tracked sase-repo files.
%macros_enabled:true