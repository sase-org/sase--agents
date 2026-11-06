%queue(weight=1)
#fork:sase-1qz.2--1
%model:muse-spark-1.3-contributor@xhigh

%macros_enabled:false
# Monitored command finished

**Command:**

```text
just check
```

**Directory:**

```text
/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12
```

| | |
| --- | --- |
| **Outcome** | FAILED — exit 1 |
| **Started** | 2026-11-03T01:45:07.389109+00:00 |
| **Finished** | 2026-11-03T02:02:47.568208Z |
| **Elapsed** | 17m 35s of a 1h 0m 0s budget |
| **Output** | 4 KiB · evidence refs: `file:monitor-diagnostic-manifest:0qzejhfek4zz`, `file:monitor-retained-log:0qzejhfek4zz`, `file:monitor-stage:lint-symvision-3505181-1793671361184883050-eca0ba39` · raw output omitted: `failed_diagnostics` · full log: `sase monitor show 0qzejhfek4zz --all-lines` |
| **Tool run** | sase tool show 0210fb09165ec5df014bf7be317b01f1 |

**Why this was monitored:** run command

## Failure triage

verdict: new_failures — 9 NEW; exit 1

NEW lint (symvision): hijack_continuation_prompt in src/sase/agent/hijack/core.py — recorded evidence; no owner
NEW lint (symvision): escalation_wire_schema_version in src/sase/agent/hijack/core.py — recorded evidence; no owner
NEW lint (symvision): build_alias_candidates in src/sase/agent/hijack/config.py — recorded evidence; no owner
NEW lint (symvision): AgentHijackConfig in src/sase/agent/hijack/config.py — recorded evidence; no owner
NEW lint (symvision): normalize_hijack_rung in src/sase/agent/hijack/core.py — recorded evidence; no owner
NEW lint (symvision): agent_hijack_config in src/sase/agent/hijack/config.py — recorded evidence; no owner
NEW lint (symvision): hijack_escalation_target in src/sase/agent/hijack/core.py — recorded evidence; no owner
NEW lint (symvision): strip_hijack_launch_directives in src/sase/agent/hijack/core.py — recorded evidence; no owner
NEW lint (symvision): continuation_wire_schema_version in src/sase/agent/hijack/core.py — recorded evidence; no owner
KNOWN 0; FLAKY 0

sase tool show 0210fb09165ec5df014bf7be317b01f1 -j

## Selected diagnostics

<!--sase:budget-span:open:kind=newest_diagnostics;id=1-->
**Diagnostics (untrusted program output):**

```text
== lint (symvision) (failed exit 1) ==
[counts: output_bytes=1950, output_lines=17, retained_bytes=1950]
[validate_sase_core_rs_version] sase-core checkout is ahead of sase's compatibility window: source version 0.43.3 from /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/sase/repos/linked/sase-core/Cargo.toml does not satisfy `sase`'s `sase-core-rs==0.43.2` dependency in pyproject.toml. No action is needed: editable installs build from the checkout regardless, and `tools/ratchet_core_pin` moves the published pin on the release branch at release time.
[setup] Note: the sase-core checkout is ahead of the published sase-core-rs pin in pyproject.toml; dev installs build from /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/sase/repos/linked/sase-core regardless. This is normal — the release-branch reconciler ratchets the published pin at release time, so no action is needed here.
.venv/bin/python tools/setup_required_plugins
[setup] Installing required plugin sase-github>=0.2.5.
[setup] Installing required plugin sase-research-artifacts>=0.2.0.
SASE_SYMVISION_BEAD_STATUS_ONLY=1 BD_COMMAND=tools/sase_bead .venv/bin/symvision src/sase --exclude-decorator gate_command_entrypoint --exclude-decorator builtin_chop 
Unused public functions/classes. Make these private if they are used only within the file they are defined. If the functions/classes are completely unused, you should delete them:
  AgentHijackConfig in src/sase/agent/hijack/config.py
  agent_hijack_config in src/sase/agent/hijack/config.py
  build_alias_candidates in src/sase/agent/hijack/config.py
  continuation_wire_schema_version in src/sase/agent/hijack/core.py
  escalation_wire_schema_version in src/sase/agent/hijack/core.py
  hijack_continuation_prompt in src/sase/agent/hijack/core.py
  hijack_escalation_target in src/sase/agent/hijack/core.py
  normalize_hijack_rung in src/sase/agent/hijack/core.py
  strip_hijack_launch_directives in src/sase/agent/hijack/core.py
error: Recipe `_lint-symvision` failed on line 512 with exit code 1

```

<!--sase:budget-span:close:1-->

## Your next action

Inspect the monitor result, repair any failed or timed-out verification, and finish the original task.
%macros_enabled:true