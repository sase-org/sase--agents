%queue(weight=1)
#fork:sase-1p1.12--b
%model:grok-4.6
%effort:high

%macros_enabled:false
# Monitored command finished

**Command:**

```text
just check
```

**Directory:**

```text
/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14
```

| | |
| --- | --- |
| **Outcome** | FAILED — exit 1 |
| **Started** | 2026-10-28T12:59:36.098884+00:00 |
| **Finished** | 2026-10-28T13:15:43.640769Z |
| **Elapsed** | 16m 6s of a 1h 0m 0s budget |
| **Output** | 15 KiB · evidence refs: `file:monitor-diagnostic-manifest:ys65f2j65gym`, `file:monitor-retained-log:ys65f2j65gym`, `file:monitor-stage:lint-symvision-1102757-1793192599900725665-eca0ba39` · raw output omitted: `failed_diagnostics` · full log: `sase monitor show ys65f2j65gym --all-lines` |
| **Tool run** | sase tool show 51eb8af7794ab1f98dba8da46ba44d94 |

**Why this was monitored:** Verify Footprint export/import before host completion

## Failure triage

verdict: no_new_failures — 1 KNOWN; exit 1

KNOWN 1; FLAKY 0

sase tool show 51eb8af7794ab1f98dba8da46ba44d94 -j

## Selected diagnostics

<!--sase:budget-span:open:kind=newest_diagnostics;id=1-->
**Diagnostics (untrusted program output):**

```text
== lint (symvision) (failed exit 1) ==
[counts: output_bytes=1529, output_lines=9, retained_bytes=1529]
[validate_sase_core_rs_version] sase-core checkout is ahead of sase's compatibility window: source version 0.43.0 from /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/sase/repos/linked/sase-core/Cargo.toml does not satisfy `sase`'s `sase-core-rs==0.42.7` dependency in pyproject.toml. No action is needed: editable installs build from the checkout regardless, and `tools/ratchet_core_pin` moves the published pin on the release branch at release time.
[setup] Note: the sase-core checkout is ahead of the published sase-core-rs pin in pyproject.toml; dev installs build from /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/sase/repos/linked/sase-core regardless. This is normal — the release-branch reconciler ratchets the published pin at release time, so no action is needed here.
.venv/bin/python tools/setup_required_plugins
[setup] Installing required plugin sase-github>=0.2.5.
[setup] Installing required plugin sase-research-artifacts>=0.2.0.
SASE_SYMVISION_BEAD_STATUS_ONLY=1 BD_COMMAND=tools/sase_bead .venv/bin/symvision src/sase --exclude-decorator gate_command_entrypoint --exclude-decorator builtin_chop --epic-symbol 'sase-1p1(footprint_wire_schema_version)' --epic-symbol 'sase-1p1(footprint_validate_overlay)' 
Error: Private functions/classes should not be imported. Make these public if they need to be imported by non-test files!:
  _RecoveryAssessment in src/sase/finalizers/_failed_close_recovery_assess.py
error: recipe `_lint-symvision` failed on line 491 with exit code 1

```

<!--sase:budget-span:close:1-->

## Host completion

Verification FAILED — exit 1, but host completion did not land the change.

- `no_new_receipt_fingerprint_changed:fingerprint changed`

## Your next action

Diagnose failures or stale verification, then finish the requested change.
%macros_enabled:true