%queue(weight=1)
#fork:15d--code
%model:grok-4.6@high

%macros_enabled:false
# Monitored command finished

**Command:**

```text
just check
```

**Directory:**

```text
/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_13
```

| | |
| --- | --- |
| **Outcome** | FAILED — exit 1 |
| **Started** | 2026-10-28T20:14:53.396912+00:00 |
| **Finished** | 2026-10-28T20:19:14.175107Z |
| **Elapsed** | 4m 19s of a 1h 0m 0s budget |
| **Output** | 5 KiB · evidence refs: `file:monitor-diagnostic-manifest:1ep69fpvp064`, `file:monitor-retained-log:1ep69fpvp064`, `file:monitor-stage:lint-symvision-1543666-1793218752435229291-eca0ba39` · raw output omitted: `failed_diagnostics` · full log: `sase monitor show 1ep69fpvp064 --all-lines` |
| **Tool run** | sase tool show 9e04a76d13c4daed2b75a61367f4d292 |

**Why this was monitored:** Verify before host completion

## Failure triage

verdict: new_failures — 9 NEW; exit 1

NEW lint (symvision): ArtifactLinkCollisionPartition in src/sase/sdd/_artifact_link_event_collision.py — recorded evidence; no owner
NEW lint (symvision): SnapshotEvidence in src/sase/finalizers/_failed_close_recovery_snapshots.py — recorded evidence; no owner
NEW lint (symvision): FinderFeature in src/sase/ace/tui/modals/statistics_footprint_finder_modal.py — recorded evidence; no owner
NEW lint (symvision): discover_nested_git_repos in src/sase/workspace_provider/_snapshot_nested.py — recorded evidence; no owner
NEW lint (symvision): reduce_events in src/sase/sdd/_artifact_link_event_canonical.py — recorded evidence; no owner
NEW lint (symvision): admission_sequence_for in src/sase/sdd/_artifact_link_event_quarantine.py — recorded evidence; no owner
NEW lint (symvision): candidates_from_tier in src/sase/sdd/_artifact_link_event_store.py — recorded evidence; no owner
NEW lint (symvision): overlay_payload in src/sase/footprint/query.py — recorded evidence; no owner
NEW lint (symvision): review_settings in src/sase/footprint/query.py — recorded evidence; no owner
KNOWN 0; FLAKY 0

sase tool show 9e04a76d13c4daed2b75a61367f4d292 -j

## Selected diagnostics

<!--sase:budget-span:open:kind=newest_diagnostics;id=1-->
**Diagnostics (untrusted program output):**

```text
== lint (symvision) (failed exit 1) ==
[counts: output_bytes=2028, output_lines=17, retained_bytes=2028]
[validate_sase_core_rs_version] sase-core checkout is ahead of sase's compatibility window: source version 0.43.0 from /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_13/sase/repos/linked/sase-core/Cargo.toml does not satisfy `sase`'s `sase-core-rs==0.42.7` dependency in pyproject.toml. No action is needed: editable installs build from the checkout regardless, and `tools/ratchet_core_pin` moves the published pin on the release branch at release time.
[setup] Note: the sase-core checkout is ahead of the published sase-core-rs pin in pyproject.toml; dev installs build from /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_13/sase/repos/linked/sase-core regardless. This is normal — the release-branch reconciler ratchets the published pin at release time, so no action is needed here.
.venv/bin/python tools/setup_required_plugins
[setup] Installing required plugin sase-github>=0.2.5.
[setup] Installing required plugin sase-research-artifacts>=0.2.0.
SASE_SYMVISION_BEAD_STATUS_ONLY=1 BD_COMMAND=tools/sase_bead .venv/bin/symvision src/sase --exclude-decorator gate_command_entrypoint --exclude-decorator builtin_chop 
Unused public functions/classes. Make these private if they are used only within the file they are defined. If the functions/classes are completely unused, you should delete them:
  ArtifactLinkCollisionPartition in src/sase/sdd/_artifact_link_event_collision.py
  FinderFeature in src/sase/ace/tui/modals/statistics_footprint_finder_modal.py
  SnapshotEvidence in src/sase/finalizers/_failed_close_recovery_snapshots.py
  admission_sequence_for in src/sase/sdd/_artifact_link_event_quarantine.py
  candidates_from_tier in src/sase/sdd/_artifact_link_event_store.py
  discover_nested_git_repos in src/sase/workspace_provider/_snapshot_nested.py
  overlay_payload in src/sase/footprint/query.py
  reduce_events in src/sase/sdd/_artifact_link_event_canonical.py
  review_settings in src/sase/footprint/query.py
error: recipe `_lint-symvision` failed on line 486 with exit code 1

```

<!--sase:budget-span:close:1-->

## Your next action

Inspect the monitor result, repair any failed or timed-out verification, and finish the original task.
%macros_enabled:true