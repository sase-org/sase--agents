%queue(weight=1)
#fork:sase-1tc.3.1.3--1
%model:gpt-6-luna@xhigh

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
| **Started** | 2026-11-18T08:39:55.736399+00:00 |
| **Finished** | 2026-11-18T09:03:37.789228Z |
| **Elapsed** | 22m 38s of a 1h 0m 0s budget |
| **Output** | 20 KiB · evidence refs: `file:monitor-diagnostic-manifest:dhrx6789hnt6`, `file:monitor-retained-log:dhrx6789hnt6`, `file:monitor-stage:lint-symvision-2035329-1794992615133933715-eca0ba39` · raw output omitted: `failed_diagnostics` · full log: `sase monitor show dhrx6789hnt6 --all-lines` |
| **Tool run** | sase tool show 7feea4159792681359cfd81eff6157e1 |

**Why this was monitored:** Verify typed chop admission before host completion

## Failure triage

verdict: new_failures — 1 NEW; exit 1

NEW lint (symvision): TypedChopBatchResume in src/sase/axe/chop_typed_admission.py — recorded evidence; no owner
KNOWN 0; FLAKY 0

sase tool show 7feea4159792681359cfd81eff6157e1 -j

## Selected diagnostics

<!--sase:budget-span:open:kind=newest_diagnostics;id=1-->
**Diagnostics (untrusted program output):**

```text
== lint (symvision) (failed exit 1) ==
[counts: output_bytes=1710, output_lines=7, retained_bytes=1710]
.venv/bin/python tools/setup_required_plugins
[setup] Installing required plugin sase-github>=0.2.5.
[setup] Installing required plugin sase-research-artifacts>=0.2.0.
SASE_SYMVISION_BEAD_STATUS_ONLY=1 BD_COMMAND=tools/sase_bead .venv/bin/symvision src/sase --exclude-decorator gate_command_entrypoint --exclude-decorator builtin_chop --epic-symbol "sase-1t3.10.1(query_agent_artifact_index_list)" --epic-symbol "sase-1t3.10.1(scan_agent_artifact_dir_list)" --epic-symbol "sase-1tc.3.1(ChopBatchCorruptError)" --epic-symbol "sase-1tc.3.1(ChopBatchError)" --epic-symbol "sase-1tc.3.1(ChopBatchExistsError)" --epic-symbol "sase-1tc.3.1(ChopBatchNotFoundError)" --epic-symbol "sase-1tc.3.1(ChopBatchReplayError)" --epic-symbol "sase-1tc.3.1(ChopBatchReplayResult)" --epic-symbol "sase-1tc.3.1(acquire_chop_batch_ownership)" --epic-symbol "sase-1tc.3.1(chop_batch_owner_path)" --epic-symbol "sase-1tc.3.1(chop_batch_path)" --epic-symbol "sase-1tc.3.1(chop_batches_dir)" --epic-symbol "sase-1tc.3.1(delete_chop_batch)" --epic-symbol "sase-1tc.3.1(ensure_chop_batches_dir)" --epic-symbol "sase-1tc.3.1(list_pending_chop_batches)" --epic-symbol "sase-1tc.3.1(read_chop_batch_owner)" --epic-symbol "sase-1tc.3.1(reconcile_stored_batch)" --epic-symbol "sase-1tc.3.1(replay_ordinary_chop_batch)" --epic-symbol "sase-1tc.3.1(release_chop_batch_ownership)" --epic-symbol "sase-1tc.3.1(summarize_stored_batch)" 
Unused public functions/classes. Make these private if they are used only within the file they are defined. If the functions/classes are completely unused, you should delete them:
  TypedChopBatchResume in src/sase/axe/chop_typed_admission.py
error: recipe `_lint-symvision` failed on line 573 with exit code 1

```

<!--sase:budget-span:close:1-->

## Your next action

Inspect the monitor result, repair any failed or timed-out verification, and finish the original task.
%macros_enabled:true