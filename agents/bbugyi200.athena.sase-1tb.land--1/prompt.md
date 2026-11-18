%queue(weight=1)
#fork:sase-1tb.land--code
%model:muse-spark-1.3-contributor@xhigh

%macros_enabled:false
# Monitored command finished

**Command:**

```text
sase tool run check
```

**Directory:**

```text
/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_30
```

| | |
| --- | --- |
| **Outcome** | FAILED — exit 1 |
| **Started** | 2026-11-18T02:22:59.647362+00:00 |
| **Finished** | 2026-11-18T04:51:02.069565Z |
| **Elapsed** | 9m 22s of a 1h 0m 0s budget |
| **Output** | 17 KiB · evidence refs: `file:monitor-diagnostic-manifest:t0bwrqvbmnnq`, `file:monitor-retained-log:t0bwrqvbmnnq`, `file:monitor-stage:lint-symvision-2860757-1794977213491614544-eca0ba39` · raw output omitted: `failed_diagnostics` · full log: `sase monitor show t0bwrqvbmnnq --all-lines` |
| **Tool run** | sase tool show 10524016847ca8c29097c7e572ce188a |

**Why this was monitored:** Verify fast video pane landing fixes before epic close

## Failure triage

verdict: no_new_failures — 3 KNOWN; exit 1

KNOWN 3; FLAKY 0

sase tool show 10524016847ca8c29097c7e572ce188a -j

## Selected diagnostics

<!--sase:budget-span:open:kind=newest_diagnostics;id=1-->
**Diagnostics (untrusted program output):**

```text
== lint (symvision) (failed exit 1) ==
[counts: output_bytes=1855, output_lines=9, retained_bytes=1855]
.venv/bin/python tools/setup_required_plugins
[setup] Installing required plugin sase-github>=0.2.5.
[setup] Installing required plugin sase-research-artifacts>=0.2.0.
SASE_SYMVISION_BEAD_STATUS_ONLY=1 BD_COMMAND=tools/sase_bead .venv/bin/symvision src/sase --exclude-decorator gate_command_entrypoint --exclude-decorator builtin_chop --epic-symbol "sase-1t3.10.1(query_agent_artifact_index_list)" --epic-symbol "sase-1t3.10.1(scan_agent_artifact_dir_list)" --epic-symbol "sase-1tc.3.1(ChopBatchCorruptError)" --epic-symbol "sase-1tc.3.1(ChopBatchError)" --epic-symbol "sase-1tc.3.1(ChopBatchExistsError)" --epic-symbol "sase-1tc.3.1(ChopBatchNotFoundError)" --epic-symbol "sase-1tc.3.1(acquire_chop_batch_ownership)" --epic-symbol "sase-1tc.3.1(apply_chop_batch_event)" --epic-symbol "sase-1tc.3.1(chop_batch_owner_path)" --epic-symbol "sase-1tc.3.1(chop_batch_path)" --epic-symbol "sase-1tc.3.1(chop_batches_dir)" --epic-symbol "sase-1tc.3.1(create_chop_batch)" --epic-symbol "sase-1tc.3.1(delete_chop_batch)" --epic-symbol "sase-1tc.3.1(ensure_chop_batches_dir)" --epic-symbol "sase-1tc.3.1(list_pending_chop_batches)" --epic-symbol "sase-1tc.3.1(load_chop_batch)" --epic-symbol "sase-1tc.3.1(read_chop_batch_owner)" --epic-symbol "sase-1tc.3.1(reconcile_stored_batch)" --epic-symbol "sase-1tc.3.1(release_chop_batch_ownership)" --epic-symbol "sase-1tc.3.1(summarize_stored_batch)" --epic-symbol "sase-1tc.3.1(update_chop_batch)" 
Error: Private functions/classes should not be imported. Make these public if they need to be imported by non-test files!:
  _assemble_inspect_key in src/sase/ace/tui/graphics/_viewer_video_input.py
  _completed_inspect_escape in src/sase/ace/tui/graphics/_viewer_video_input.py
  _decode_inspect_key in src/sase/ace/tui/graphics/_viewer_video_input.py
error: recipe `_lint-symvision` failed on line 574 with exit code 1

```

<!--sase:budget-span:close:1-->

## Continuation checkpoint

- **Ref:** `local:continuation/checkpoints/monitor_start-2e1098bf86d17abc.json`

**Checkpoint (JSON):**

```text
{
  "kind": "monitor_start",
  "payload": {
    "command": "sase tool run check",
    "cwd": "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_30",
    "member_agent_name": "sase-1tb.land--mon-0",
    "monitor_id": "t0bwrqvbmnnq",
    "next_output": "auto",
    "parent_node_ids": [
      "agent-delta:20261117111750:f79082880259fde0"
    ],
    "project_name": "gh_sase-org__sase",
    "request_fingerprint": "sha256:e6ec6c443aae340cee0616cb232e96cbc410d99e00b84e97e5ee5628e18836e3",
    "starter_agent": "sase-1tb.land--code",
    "starter_artifacts_dir": "/home/bryan/.sase/projects/gh_sase-org__sase/artifacts/ace-run/202611/17/20261117195948"
  },
  "recorded_at_epoch": 1794976899.9615571,
  "schema_version": 1
}
```


## Your next action

Check run finished. Read result with sase tool show <run> or sase tool wait. If green (only KNOWN/FLAKY, no NEW/UNKNOWN): run just symvision (must be clean), confirm import footprint below 11924777 via budget test, then close epic sase-1tb with land verification note (7 phases closed, source f28da33a13 reviewed, follow-up triage per land note, defects 1-8 fixed; measured probe header->first APC 223.4ms l->APC 9.1ms client bytes 395431 APCs 3 burst 00:05.0, footprint 11922010 vs cap 11924777; checks: sase tool run check id + result, symvision clean). Then set status done in plans sidecar plan 202611/fast_video_artifact_pane.md frontmatter via sase repo open plans. If NEW/UNKNOWN failures: fix them (likely test issues, not product), do not close epic.
%macros_enabled:true