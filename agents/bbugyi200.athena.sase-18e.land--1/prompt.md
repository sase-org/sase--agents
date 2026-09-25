%queue(weight=1)
%auto
#fork:sase-18e.land--code
%model:muse-spark-1.3-contributor@high

%xprompts_enabled:false
# Monitored command finished

**Command:**

```text
just check
```

**Directory:**

```text
/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_40
```

| | |
| --- | --- |
| **Outcome** | FAILED — exit 1 |
| **Started** | 2026-09-24T23:33:18.609953+00:00 |
| **Finished** | 2026-09-24T23:36:39.233491+00:00 |
| **Elapsed** | 3m 19s of a 1h 0m 0s budget |
| **Output** | 1 KiB · evidence refs: `file:monitor-diagnostic-manifest:v3h5n9pz7qr1`, `file:monitor-retained-log:v3h5n9pz7qr1`, `file:monitor-stage:lint-symvision-945663-1790292998229647619-eca0ba39` · raw output omitted: `failed_diagnostics` · full log: `sase monitor show v3h5n9pz7qr1 --all-lines` |
| **Tool run** | sase tool show c920e5b35735f3af7e5d7fcbb2a8de70 |

**Why this was monitored:** Verify monitor lane core pin before host completion

## Selected diagnostics

<!--sase:budget-span:open:kind=newest_diagnostics;id=1-->
**Diagnostics (untrusted program output):**

```text
== lint (symvision) (failed exit 1) ==
[counts: output_bytes=788, output_lines=9, retained_bytes=788]
.venv/bin/python tools/setup_required_plugins
[setup] Installing required plugin sase-github>=0.2.5.
[setup] Installing required plugin sase-research-artifacts>=0.2.0.
SASE_SYMVISION_BEAD_STATUS_ONLY=1 BD_COMMAND=tools/sase_bead .venv/bin/symvision src/sase --exclude-decorator gate_command_entrypoint --exclude-decorator builtin_chop 
Unused public functions/classes. Make these private if they are used only within the file they are defined. If the functions/classes are completely unused, you should delete them:
  AgentSurvivorsError in src/sase/ace/tui/actions/agents/_kill_termination.py
  Survivor in src/sase/ace/tui/actions/agents/_kill_termination.py
  environ_has_launch_key in src/sase/agent/process_tree.py
error: recipe `_lint-symvision` failed on line 370 with exit code 1

```

<!--sase:budget-span:close:1-->

## Your next action

Inspect the monitor result, repair any failed or timed-out verification, and finish the original task.
%xprompts_enabled:true