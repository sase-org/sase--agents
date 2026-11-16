%queue(weight=1)
#fork:sase-1t3.4--plan
%model:grok-4.6@high

%macros_enabled:false
# Monitored command finished

**Command:**

```text
just check
```

**Directory:**

```text
/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11
```

| | |
| --- | --- |
| **Outcome** | FAILED — exit 1 |
| **Started** | 2026-11-16T13:52:07.071824+00:00 |
| **Finished** | 2026-11-16T14:49:45.098218Z |
| **Elapsed** | 55m 46s of a 1h 0m 0s budget |
| **Output** | 8 KiB · evidence refs: `file:monitor-diagnostic-manifest:zxrtawmv86j1`, `file:monitor-retained-log:zxrtawmv86j1`, `file:monitor-stage:lint-symvision-3164716-1794837480008958090-eca0ba39` · raw output omitted: `failed_diagnostics` · full log: `sase monitor show zxrtawmv86j1 --all-lines` |
| **Tool run** | sase tool show 7e02efcde40176ad8c05d4429cd5b726 |

**Why this was monitored:** Verify trust-root before host completion

## Failure triage

verdict: no_new_failures — 2 KNOWN; exit 1

KNOWN 2; FLAKY 0

sase tool show 7e02efcde40176ad8c05d4429cd5b726 -j

## Selected diagnostics

<!--sase:budget-span:open:kind=newest_diagnostics;id=1-->
**Diagnostics (untrusted program output):**

```text
== lint (symvision) (failed exit 1) ==
[counts: output_bytes=734, output_lines=8, retained_bytes=734]
.venv/bin/python tools/setup_required_plugins
[setup] Installing required plugin sase-github>=0.2.5.
[setup] Installing required plugin sase-research-artifacts>=0.2.0.
SASE_SYMVISION_BEAD_STATUS_ONLY=1 BD_COMMAND=tools/sase_bead .venv/bin/symvision src/sase --exclude-decorator gate_command_entrypoint --exclude-decorator builtin_chop 
Unused public functions/classes. Make these private if they are used only within the file they are defined. If the functions/classes are completely unused, you should delete them:
  reset_lower_macros_cache in src/sase/config/local_trust_enforcement.py
  reset_project_identity_caches in src/sase/config/local_trust_management.py
error: recipe `_lint-symvision` failed on line 534 with exit code 1

```

<!--sase:budget-span:close:1-->

## Your next action

Inspect the monitor result, repair any failed or timed-out verification, and finish the original task.
%macros_enabled:true