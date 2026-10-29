%queue(weight=1)
#fork:sase-1pm.2--2
%model:grok-4.6@medium

%macros_enabled:false
# Monitored command finished

**Command:**

```text
just check
```

**Directory:**

```text
/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_25
```

| | |
| --- | --- |
| **Outcome** | FAILED — exit 1 |
| **Started** | 2026-10-29T09:19:40.511461+00:00 |
| **Finished** | 2026-10-29T09:23:32.634156Z |
| **Elapsed** | 3m 50s of a 6h 0m 0s budget |
| **Output** | 8 KiB · evidence refs: `file:monitor-diagnostic-manifest:kyxm01g3r11k`, `file:monitor-retained-log:kyxm01g3r11k`, `file:monitor-stage:lint-symvision-135161-1793265808688696719-eca0ba39` · raw output omitted: `failed_diagnostics` · full log: `sase monitor show kyxm01g3r11k --all-lines` |
| **Tool run** | sase tool show 0eb6ba91bd5e57ce1930d72f531a3ac6 |

**Why this was monitored:** Verify TERM pin before host completion of sase-1pm.2; previous 1h/2h monitors timed out because root-conftest escalates just check to the full suite

## Failure triage

verdict: new_failures — 5 NEW; exit 1

NEW lint (symvision): Error: --epic-symbol 'sase-1pj.1.1.4(release_staging_reservation)': bead 'sase-1pj.1.1.4' is closed. Remove this stale --epic-symbol entry and clean up the symbol. — recorded evidence; no owner
NEW lint (symvision): Error: --epic-symbol 'sase-1pj.1.1.4(write_staged_handoff)': bead 'sase-1pj.1.1.4' is closed. Remove this stale --epic-symbol entry and clean up the symbol. — recorded evidence; no owner
NEW lint (symvision): Error: --epic-symbol 'sase-1pj.1.1.4(build_plan_staged_record)': bead 'sase-1pj.1.1.4' is closed. Remove this stale --epic-symbol entry and clean up the symbol. — recorded evidence; no owner
NEW lint (symvision): Error: --epic-symbol 'sase-1pj.1.1.4(acquire_staging_reservation)': bead 'sase-1pj.1.1.4' is closed. Remove this stale --epic-symbol entry and clean up the symbol. — recorded evidence; no owner
NEW lint (symvision): Error: --epic-symbol 'sase-1pj.1.1.4(staged_handoffs_enabled)': bead 'sase-1pj.1.1.4' is closed. Remove this stale --epic-symbol entry and clean up the symbol. — recorded evidence; no owner
KNOWN 0; FLAKY 0

sase tool show 0eb6ba91bd5e57ce1930d72f531a3ac6 -j

## Selected diagnostics

<!--sase:budget-span:open:kind=newest_diagnostics;id=1-->
**Diagnostics (untrusted program output):**

```text
== lint (symvision) (failed exit 1) ==
[counts: output_bytes=2311, output_lines=12, retained_bytes=2311]
[validate_sase_core_rs_version] sase-core checkout is ahead of sase's compatibility window: source version 0.43.0 from /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_25/sase/repos/linked/sase-core/Cargo.toml does not satisfy `sase`'s `sase-core-rs==0.42.7` dependency in pyproject.toml. No action is needed: editable installs build from the checkout regardless, and `tools/ratchet_core_pin` moves the published pin on the release branch at release time.
[setup] Note: the sase-core checkout is ahead of the published sase-core-rs pin in pyproject.toml; dev installs build from /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_25/sase/repos/linked/sase-core regardless. This is normal — the release-branch reconciler ratchets the published pin at release time, so no action is needed here.
.venv/bin/python tools/setup_required_plugins
[setup] Installing required plugin sase-github>=0.2.5.
[setup] Installing required plugin sase-research-artifacts>=0.2.0.
SASE_SYMVISION_BEAD_STATUS_ONLY=1 BD_COMMAND=tools/sase_bead .venv/bin/symvision src/sase --exclude-decorator gate_command_entrypoint --exclude-decorator builtin_chop --epic-symbol 'sase-1pj.1.1.4(acquire_staging_reservation)' --epic-symbol 'sase-1pj.1.1.4(build_plan_staged_record)' --epic-symbol 'sase-1pj.1.1.4(release_staging_reservation)' --epic-symbol 'sase-1pj.1.1.4(staged_handoffs_enabled)' --epic-symbol 'sase-1pj.1.1.4(write_staged_handoff)' 
Error: --epic-symbol 'sase-1pj.1.1.4(acquire_staging_reservation)': bead 'sase-1pj.1.1.4' is closed. Remove this stale --epic-symbol entry and clean up the symbol.
Error: --epic-symbol 'sase-1pj.1.1.4(build_plan_staged_record)': bead 'sase-1pj.1.1.4' is closed. Remove this stale --epic-symbol entry and clean up the symbol.
Error: --epic-symbol 'sase-1pj.1.1.4(release_staging_reservation)': bead 'sase-1pj.1.1.4' is closed. Remove this stale --epic-symbol entry and clean up the symbol.
Error: --epic-symbol 'sase-1pj.1.1.4(staged_handoffs_enabled)': bead 'sase-1pj.1.1.4' is closed. Remove this stale --epic-symbol entry and clean up the symbol.
Error: --epic-symbol 'sase-1pj.1.1.4(write_staged_handoff)': bead 'sase-1pj.1.1.4' is closed. Remove this stale --epic-symbol entry and clean up the symbol.
error: recipe `_lint-symvision` failed on line 493 with exit code 1

```

<!--sase:budget-span:close:1-->

## Your next action

Inspect the monitor result, repair any failed or timed-out verification, and finish the original task.
%macros_enabled:true