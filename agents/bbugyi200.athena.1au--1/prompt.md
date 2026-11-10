%queue(weight=1)
#fork:1au--code
%model:grok-4.6@high

%macros_enabled:false
# Monitored command finished

**Command:**

```text
just check
```

**Directory:**

```text
/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10
```

| | |
| --- | --- |
| **Outcome** | FAILED — exit 1 |
| **Started** | 2026-11-10T13:13:37.871743+00:00 |
| **Finished** | 2026-11-10T13:18:51.008899Z |
| **Elapsed** | 3m 47s of a 1h 0m 0s budget |
| **Output** | 3 KiB · evidence refs: `file:monitor-diagnostic-manifest:nxwv189vmnj2`, `file:monitor-retained-log:nxwv189vmnj2`, `file:monitor-stage:lint-symvision-1931326-1794316728490525252-eca0ba39` · raw output omitted: `failed_diagnostics` · full log: `sase monitor show nxwv189vmnj2 --all-lines` |
| **Tool run** | sase tool show 00453d0ec8f0fecb1ed80305b78425b5 |

**Why this was monitored:** Verify sudo remote snapshot and macOS TCC work before host completion

## Failure triage

verdict: new_failures — 2 NEW; exit 1

NEW lint (symvision): _probe_contract in src/sase/sudo/ssh_exec.py — recorded evidence; no owner
NEW lint (symvision): _probe_contract in src/sase/screenshot/remote.py — recorded evidence; no owner
KNOWN 0; FLAKY 0

sase tool show 00453d0ec8f0fecb1ed80305b78425b5 -j

## Selected diagnostics

<!--sase:budget-span:open:kind=newest_diagnostics;id=1-->
**Diagnostics (untrusted program output):**

```text
== lint (symvision) (failed exit 1) ==
[counts: output_bytes=1440, output_lines=10, retained_bytes=1440]
[validate_sase_core_rs_version] sase-core checkout is ahead of sase's compatibility window: source version 0.44.2 from /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/sase/repos/linked/sase-core/Cargo.toml does not satisfy `sase`'s `sase-core-rs==0.43.2` dependency in pyproject.toml. No action is needed: editable installs build from the checkout regardless, and `tools/ratchet_core_pin` moves the published pin on the release branch at release time.
[setup] Note: the sase-core checkout is ahead of the published sase-core-rs pin in pyproject.toml; dev installs build from /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/sase/repos/linked/sase-core regardless. This is normal — the release-branch reconciler ratchets the published pin at release time, so no action is needed here.
.venv/bin/python tools/setup_required_plugins
[setup] Installing required plugin sase-github>=0.2.5.
[setup] Installing required plugin sase-research-artifacts>=0.2.0.
SASE_SYMVISION_BEAD_STATUS_ONLY=1 BD_COMMAND=tools/sase_bead .venv/bin/symvision src/sase --exclude-decorator gate_command_entrypoint --exclude-decorator builtin_chop 
Error: Private functions/classes should not be imported. Make these public if they need to be imported by non-test files!:
  _probe_contract in src/sase/sudo/ssh_exec.py
  _probe_contract in src/sase/screenshot/remote.py
error: recipe `_lint-symvision` failed on line 534 with exit code 1

```

<!--sase:budget-span:close:1-->

## Your next action

Inspect the monitor result, repair any failed or timed-out verification, and finish the original task.
%macros_enabled:true