%queue(weight=1)
#fork:sase-1tc.3.1.2--2
%model:gpt-6-luna@xhigh

%macros_enabled:false
# Monitored command finished

**Command:**

```text
just check
```

**Directory:**

```text
/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_22
```

| | |
| --- | --- |
| **Outcome** | FAILED — exit 1 |
| **Started** | 2026-11-18T04:01:11.517341+00:00 |
| **Finished** | 2026-11-18T04:09:11.238786Z |
| **Elapsed** | 5m 18s of a 1h 0m 0s budget |
| **Output** | 4 KiB · evidence refs: `file:monitor-diagnostic-manifest:b2z6nwjk3m9z`, `file:monitor-retained-log:b2z6nwjk3m9z`, `file:monitor-stage:lint-symvision-4072716-1794974948581553448-eca0ba39` · raw output omitted: `failed_diagnostics` · full log: `sase monitor show b2z6nwjk3m9z --all-lines` |
| **Tool run** | sase tool show bcc5c2af6aa006ec093ca71a1a4d3760 |

**Why this was monitored:** Verify ordinary chop launch journal before host completion

## Failure triage

verdict: new_failures — 4 NEW; exit 1

NEW lint (symvision): Error: --epic-symbol 'sase-1tc.3.1(update_chop_batch)': symbol 'update_chop_batch' is already properly used. Remove this unnecessary --epic-symbol entry. — recorded evidence; no owner
NEW lint (symvision): Error: --epic-symbol 'sase-1tc.3.1(create_chop_batch)': symbol 'create_chop_batch' is already properly used. Remove this unnecessary --epic-symbol entry. — recorded evidence; no owner
NEW lint (symvision): Error: --epic-symbol 'sase-1tc.3.1(load_chop_batch)': symbol 'load_chop_batch' is already properly used. Remove this unnecessary --epic-symbol entry. — recorded evidence; no owner
NEW lint (symvision): Error: --epic-symbol 'sase-1tc.3.1(apply_chop_batch_event)': symbol 'apply_chop_batch_event' is already properly used. Remove this unnecessary --epic-symbol entry. — recorded evidence; no owner
KNOWN 0; FLAKY 0

sase tool show bcc5c2af6aa006ec093ca71a1a4d3760 -j

## Selected diagnostics

<!--sase:budget-span:open:kind=newest_diagnostics;id=1-->
**Diagnostics (untrusted program output):**

```text
== lint (symvision) (failed exit 1) ==
[counts: output_bytes=2124, output_lines=9, retained_bytes=2124]
.venv/bin/python tools/setup_required_plugins
[setup] Installing required plugin sase-github>=0.2.5.
[setup] Installing required plugin sase-research-artifacts>=0.2.0.
SASE_SYMVISION_BEAD_STATUS_ONLY=1 BD_COMMAND=tools/sase_bead .venv/bin/symvision src/sase --exclude-decorator gate_command_entrypoint --exclude-decorator builtin_chop --epic-symbol "sase-1t3.10.1(query_agent_artifact_index_list)" --epic-symbol "sase-1t3.10.1(scan_agent_artifact_dir_list)" --epic-symbol "sase-1tc.3.1(ChopBatchCorruptError)" --epic-symbol "sase-1tc.3.1(ChopBatchError)" --epic-symbol "sase-1tc.3.1(ChopBatchExistsError)" --epic-symbol "sase-1tc.3.1(ChopBatchNotFoundError)" --epic-symbol "sase-1tc.3.1(acquire_chop_batch_ownership)" --epic-symbol "sase-1tc.3.1(apply_chop_batch_event)" --epic-symbol "sase-1tc.3.1(chop_batch_owner_path)" --epic-symbol "sase-1tc.3.1(chop_batch_path)" --epic-symbol "sase-1tc.3.1(chop_batches_dir)" --epic-symbol "sase-1tc.3.1(create_chop_batch)" --epic-symbol "sase-1tc.3.1(delete_chop_batch)" --epic-symbol "sase-1tc.3.1(ensure_chop_batches_dir)" --epic-symbol "sase-1tc.3.1(list_pending_chop_batches)" --epic-symbol "sase-1tc.3.1(load_chop_batch)" --epic-symbol "sase-1tc.3.1(read_chop_batch_owner)" --epic-symbol "sase-1tc.3.1(reconcile_stored_batch)" --epic-symbol "sase-1tc.3.1(release_chop_batch_ownership)" --epic-symbol "sase-1tc.3.1(summarize_stored_batch)" --epic-symbol "sase-1tc.3.1(update_chop_batch)" 
Error: --epic-symbol 'sase-1tc.3.1(apply_chop_batch_event)': symbol 'apply_chop_batch_event' is already properly used. Remove this unnecessary --epic-symbol entry.
Error: --epic-symbol 'sase-1tc.3.1(create_chop_batch)': symbol 'create_chop_batch' is already properly used. Remove this unnecessary --epic-symbol entry.
Error: --epic-symbol 'sase-1tc.3.1(load_chop_batch)': symbol 'load_chop_batch' is already properly used. Remove this unnecessary --epic-symbol entry.
Error: --epic-symbol 'sase-1tc.3.1(update_chop_batch)': symbol 'update_chop_batch' is already properly used. Remove this unnecessary --epic-symbol entry.
error: recipe `_lint-symvision` failed on line 574 with exit code 1

```

<!--sase:budget-span:close:1-->

## Your next action

Inspect the monitor result, repair any failed or timed-out verification, and finish the original task.
%macros_enabled:true