%queue(weight=1)
#fork:19b--code
%model:grok-4.6@high

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
| **Started** | 2026-11-07T12:08:44.723091+00:00 |
| **Finished** | 2026-11-07T12:14:05.035421Z |
| **Elapsed** | 4m 19s of a 1h 0m 0s budget |
| **Output** | 3 KiB · evidence refs: `file:monitor-diagnostic-manifest:d82ahapgejc3`, `file:monitor-retained-log:d82ahapgejc3`, `file:monitor-stage:lint-symvision-738321-1794053641771800496-eca0ba39` · raw output omitted: `failed_diagnostics` · full log: `sase monitor show d82ahapgejc3 --all-lines` |
| **Tool run** | sase tool show def310fa5d11f7dd39db682a110a7a25 |

**Why this was monitored:** Verify sidecar terminal-handoff init before host completion

## Failure triage

verdict: new_failures — 1 NEW; exit 1

NEW lint (symvision): sidecar_missing_is_drift in src/sase/main/_repo_init_sidecars.py — recorded evidence; no owner
KNOWN 0; FLAKY 0

sase tool show def310fa5d11f7dd39db682a110a7a25 -j

## Selected diagnostics

<!--sase:budget-span:open:kind=newest_diagnostics;id=1-->
**Diagnostics (untrusted program output):**

```text
== lint (symvision) (failed exit 1) ==
[counts: output_bytes=1466, output_lines=9, retained_bytes=1466]
[validate_sase_core_rs_version] sase-core checkout is ahead of sase's compatibility window: source version 0.43.3 from /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/sase/repos/linked/sase-core/Cargo.toml does not satisfy `sase`'s `sase-core-rs==0.43.2` dependency in pyproject.toml. No action is needed: editable installs build from the checkout regardless, and `tools/ratchet_core_pin` moves the published pin on the release branch at release time.
[setup] Note: the sase-core checkout is ahead of the published sase-core-rs pin in pyproject.toml; dev installs build from /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/sase/repos/linked/sase-core regardless. This is normal — the release-branch reconciler ratchets the published pin at release time, so no action is needed here.
.venv/bin/python tools/setup_required_plugins
[setup] Installing required plugin sase-github>=0.2.5.
[setup] Installing required plugin sase-research-artifacts>=0.2.0.
SASE_SYMVISION_BEAD_STATUS_ONLY=1 BD_COMMAND=tools/sase_bead .venv/bin/symvision src/sase --exclude-decorator gate_command_entrypoint --exclude-decorator builtin_chop 
Unused public functions/classes. Make these private if they are used only within the file they are defined. If the functions/classes are completely unused, you should delete them:
  sidecar_missing_is_drift in src/sase/main/_repo_init_sidecars.py
error: recipe `_lint-symvision` failed on line 534 with exit code 1

```

<!--sase:budget-span:close:1-->

## Your next action

Inspect the monitor result, repair any failed or timed-out verification, and finish the original task.
%macros_enabled:true