%queue(weight=1)
#fork:1dm--code
%model:grok-4.6@medium

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
| **Started** | 2026-11-17T20:49:52.625981+00:00 |
| **Finished** | 2026-11-17T21:20:27.207837Z |
| **Elapsed** | 29m 28s of a 1h 0m 0s budget |
| **Output** | 139 KiB · evidence refs: `file:monitor-diagnostic-manifest:378dgkngbzm0`, `file:monitor-retained-log:378dgkngbzm0`, `file:monitor-stage:lint-symvision-248557-1794949321330979318-eca0ba39`, `file:monitor-stage:test-scoped-1002488-1794950421492024219-8949acab` · raw output omitted: `failed_diagnostics` · full log: `sase monitor show 378dgkngbzm0 --all-lines` |
| **Tool run** | sase tool show a2f3a08dde3c1d15e7e0b0f4b7333b1b |

**Why this was monitored:** Verify gate fit-callback teardown crash fix before host completion

## Failure triage

verdict: new_failures — 1 NEW, 2 KNOWN; exit 1

NEW test (scoped): FAILED tests/ace/tui/test_app_import_budget.py::test_tui_app_import_stays_under_startup_budget — recorded evidence; no owner
KNOWN 2; FLAKY 0

sase tool show a2f3a08dde3c1d15e7e0b0f4b7333b1b -j

## Selected diagnostics

<!--sase:budget-span:open:kind=newest_diagnostics;id=1-->
**Diagnostics (untrusted program output):**

```text
== lint (symvision) (failed exit 1) ==
[counts: output_bytes=1228, output_lines=7, retained_bytes=1228]
.venv/bin/python tools/setup_required_plugins
[setup] Installing required plugin sase-github>=0.2.5.
[setup] Installing required plugin sase-research-artifacts>=0.2.0.
SASE_SYMVISION_BEAD_STATUS_ONLY=1 BD_COMMAND=tools/sase_bead .venv/bin/symvision src/sase --exclude-decorator gate_command_entrypoint --exclude-decorator builtin_chop --epic-symbol "sase-1tb.5(FrameExtractResult)" --epic-symbol "sase-1tb.5(ScrubTrack)" --epic-symbol "sase-1tb.5(StoryboardResult)" --epic-symbol "sase-1tb.5(artifact_video_cache_dir)" --epic-symbol "sase-1tb.5(build_storyboard)" --epic-symbol "sase-1tb.5(content_digest_for_path)" --epic-symbol "sase-1tb.5(enforce_cache_budget)" --epic-symbol "sase-1tb.5(extract_frame)" --epic-symbol "sase-1tb.5(format_video_metadata_summary)" --epic-symbol "sase-1tb.5(metadata_for_frame_service)" --epic-symbol "sase-1tb.5(scrub_fps_for_duration)" --epic-symbol "sase-1tb.5(start_scrub_track)" 
Unused public functions/classes. Make these private if they are used only within the file they are defined. If the functions/classes are completely unused, you should delete them:
  MemoryAuditRow in src/sase/memory/_read_log_query_facade.py
error: recipe `_lint-symvision` failed on line 562 with exit code 1
== test (scoped) (failed exit 1) ==
[counts: output_bytes=122685, output_lines=1384, retained_bytes=122685]
.venv/bin/python tools/setup_required_plugins
[setup] Installing required plugin sase-github>=0.2.5.
[setup] Installing required plugin sase-research-artifacts>=0.2.0.

┌───────────────────────────────────────────────────────┐
│                RUNNING: just test-scoped              │
└───────────────────────────────────────────────────────┘

---------- Running diff-scoped pytest selection... ----------
test selection escalated to the full suite (rules: core-identity-changed); 5769 test files in scope
coverage contexts: not consulted — the run escalates to the full suite, so ground truth had nothing to add
escalating to the governed full test lane (rules: core-identity-changed)
============================= test session starts ==============================
platform linux -- Python 3.14.7, pytest-9.1.1, pluggy-1.6.0
rootdir: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_27
configfile: pyproject.toml
testpaths: tests
plugins: hypothesis-6.168.0, cov-7.1.0, asyncio-1.4.0, inline-snapshot-0.35.4, xdist-3.8.0, mock-3.15.1
asyncio: mode=Mode.AUTO, debug=False, asyncio_default_fixture_loop_scope=None, asyncio_default_test_loop_scope=function
created: 14/14 workers
14 workers [61703 items]

........................................................................ [  0%]
........................................................................ [  0%]
........................................................................ [  0%]
........................................................................ [  0%]
........................................................................ [  0%]
........................................................................ [  0%]
........................................................................ [  0%]
........................................................................ [  0%]
........................................................................ [  1%]
........................................................................ [  1%]
........................................................................ [  1%]
........................................................................ [  1%]
........................................................................ [  1%]
........................................................................ [  1%]
........................................................................ [  1%]
........................................................................ [  1%]
........................................................................ [  1%]
........................................................................ [  2%]
........................................................................ [  2%]
........................................................................ [  2%]
........................................................................ [  2%]
........................................................................ [  2%]
........................................................................ [  2%]
........................................................................ [  2%]
........................................................................ [  2%]
........................................................................ [  3%]
........................................................................ [  3%]
........................................................................ [  3%]
........................................................................ [  3%]
........................................................................ [  3%]
........................................................................ [  3%]
........................................................................ [  3%]
........................................................................ [  3%]
....................................s................................... [  3%]
........................................................................ [  4%]
........................................................................ [  4%]
........................................................................ [  4%]
........................................................................ [  4%]
........................................................................ [  4%]
........................................................................ [  4%]
........................................................................ [  4%]
........................................................................ [  4%]
........................................................................ [  5%]
........................................................................ [  5%]
........................................................................ [  5%]
........................................................................ [  5%]
........................................................................ [  5%]
........................................................................ [  5%]
........................................................................ [  5%]
........................................................................ [  5%]
........................................................................ [  5%]
........................................................................ [  6%]
........................................................................ [  6%]
........................................................................ [  6%]
........................................................................ [  6%]
........................................................................ [  6%]
........................................................................ [  6%]
........................................................................ [  6%]
........................................................................ [  6%]
........................................................................ [  7%]
........................................................................ [  7%]
........................................................................ [  7%]
........................................................................ [  7%]
........................................................................ [  7%]
........................................................................ [  7%]
........................................................................ [  7%]
......................

```

<!--sase:budget-span:close:1-->

## Your next action

Inspect the monitor result, repair any failed or timed-out verification, and finish the original task.
%macros_enabled:true