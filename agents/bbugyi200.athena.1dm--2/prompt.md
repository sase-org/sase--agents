%queue(weight=1)
#fork:1dm--1
%model:grok-4.6
%effort:medium

%macros_enabled:false
# Monitored command finished

**Command:**

```text
just check
```

**Directory:**

```text
/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_27
```

| | |
| --- | --- |
| **Outcome** | FAILED — exit 1 |
| **Started** | 2026-11-17T21:38:05.094212+00:00 |
| **Finished** | 2026-11-17T21:45:03.170902Z |
| **Elapsed** | 5m 8s of a 1h 0m 0s budget |
| **Output** | 2 KiB · evidence refs: `file:monitor-diagnostic-manifest:qrjckdkvxa4p`, `file:monitor-retained-log:qrjckdkvxa4p`, `file:monitor-stage:lint-symvision-2080274-1794951900989049587-eca0ba39` · raw output omitted: `failed_diagnostics` · full log: `sase monitor show qrjckdkvxa4p --all-lines` |
| **Tool run** | sase tool show a3d7324facea41cfa2bfbc8cdb0961e7 |

**Why this was monitored:** Verify gate-fit teardown crash fix and import-budget deferral before host completion

## Failure triage

verdict: new_failures — 1 NEW, 1 KNOWN; exit 1

NEW lint (symvision): MemoryAuditRow in src/sase/memory/_read_log_query_facade.py — recorded evidence; no owner
KNOWN 1; FLAKY 0

sase tool show a3d7324facea41cfa2bfbc8cdb0961e7 -j

## Selected diagnostics

<!--sase:budget-span:open:kind=newest_diagnostics;id=1-->
**Diagnostics (untrusted program output):**

```text
== lint (symvision) (failed exit 1) ==
[counts: output_bytes=1289, output_lines=8, retained_bytes=1289]
.venv/bin/python tools/setup_required_plugins
[setup] Installing required plugin sase-github>=0.2.5.
[setup] Installing required plugin sase-research-artifacts>=0.2.0.
SASE_SYMVISION_BEAD_STATUS_ONLY=1 BD_COMMAND=tools/sase_bead .venv/bin/symvision src/sase --exclude-decorator gate_command_entrypoint --exclude-decorator builtin_chop --epic-symbol "sase-1tb.5(FrameExtractResult)" --epic-symbol "sase-1tb.5(ScrubTrack)" --epic-symbol "sase-1tb.5(StoryboardResult)" --epic-symbol "sase-1tb.5(artifact_video_cache_dir)" --epic-symbol "sase-1tb.5(build_storyboard)" --epic-symbol "sase-1tb.5(content_digest_for_path)" --epic-symbol "sase-1tb.5(enforce_cache_budget)" --epic-symbol "sase-1tb.5(extract_frame)" --epic-symbol "sase-1tb.5(format_video_metadata_summary)" --epic-symbol "sase-1tb.5(metadata_for_frame_service)" --epic-symbol "sase-1tb.5(scrub_fps_for_duration)" --epic-symbol "sase-1tb.5(start_scrub_track)" 
Unused public functions/classes. Make these private if they are used only within the file they are defined. If the functions/classes are completely unused, you should delete them:
  MemoryAuditRow in src/sase/memory/_read_log_query_facade.py
  PreprocessResult in src/sase/llm_provider/preprocessing.py
error: recipe `_lint-symvision` failed on line 562 with exit code 1

```

<!--sase:budget-span:close:1-->

## Host completion

Verification FAILED — exit 1, but host completion did not land the change.

- `no_new_verdict_insufficient:new_failures`

## Your next action

Diagnose failures or stale verification, then finish the requested change.
%macros_enabled:true