# Chat History - ace-run (sase-1rq.2.1.3--1)

- **TIMESTAMP:** 2026-11-07 16:59:40 EST
- **MODEL:** claude/opus
- **AGENT:** sase-1rq.2.1.3--1

## Prompt

%queue(weight=1)
%macros_enabled:false
# Previous Continuation

This fork uses versioned continuation replay. Blocks are stable, parent-first projections of exact continuation nodes; any historical source without recoverable node provenance is represented as an opaque legacy boundary.

- **Projection version:** `1`
- **Ordered nodes:** `1`

## Continuation Block `block:v1:1a393f5b98f7908c83ea8cc5a5f730ec`

- **Node:** `agent-delta:20261107102711:fbac7d6a53ee0c37`
- **Kind:** `agent_delta`
- **Parents:** (none)
- **Content:** `local:continuation/records/agent_delta/agent-delta:20261107102711:fbac7d6a53ee0c37.json`
- **Checkpoint:** `local:continuation/checkpoints/monitor_handoff-2b2fb8d2275ae812.json`

### User

**Protected user instruction.** Carry this request unless an explicit attributed update supersedes it.

%model:@medium
#gh:gh_sase-org__sase
@plan:202611/test_cost_snapshot_overhead.md

The above plan has been reviewed and approved. Implement it now.

### Checkpoint

- **Kind:** `monitor_handoff`

### Assistant

<!--sase:budget-span:open:kind=checkpoint;id=1;checkpoint_ref=local%3Acontinuation%2Fcheckpoints%2Fmonitor_handoff-2b2fb8d2275ae812.json;covered=agent-delta%3A20261107102711%3Afbac7d6a53ee0c37-->
Reading the plan, bead, and parent plans; next I'll measure the leak detector's snapshot hot path and optimize it.

CI run 42377692789's test-cost job is still running (~2h in, heading for the same timeout). Now reading the cost plugin and run_pytest launcher.

Writing a snapshot micro-benchmark (scratch dir outside the repo) to measure the baseline before changing anything.

Surprisingly little gain — the per-call overheads aren't the dominant cost. Breaking down where the time actually goes.

Writing the four-arm measurement harness (scratch outputs under `/tmp/sase25_costprobe/<label>/`).

Starting the baseline (unchanged code) arms in the background with a log I'll poll; I won't touch repo files until they finish.

While baseline runs, checking how the existing tests use the fingerprint internals.

Prototyping the C-level-filtered snapshot in scratch and checking exact equality against the current `_snapshot()`.

Still only ~15% faster — so neither name checks nor the probe's Python overhead dominate. Timing each stage of the prototype separately.

Slower — something in the flat pipeline is pathological. Timing each stage.

Phases run 2–3× slower inside `snap()` than standalone, which points to GC interaction (3.14's incremental GC scanning a big heap during allocation-heavy phases). Checking with GC disabled.

Baseline `fast` arm done: 3,656 passed, 253.5 s wall / 541 CPU-s. GC isn't the culprit (prototype still slower with GC off). Digging into what's slow in the private-globals loop.

Pure `getattr` is only ~8 ms/snapshot with no pathological objects, so the simplest C-level pass (no dedup) should win. Writing a cleaner interleaved A/B benchmark pinned to one core.

While the last baseline arm ("both") runs, reading the leaking module.

Now checking model usage before adding `slots=True` to the fingerprint dataclasses (fewer per-snapshot allocations).

Pyright's `list[str]` notes are pre-existing (same calls existed before); I'll make the `cache_info()` result explicitly `Any`. Adding `slots=True` to the fingerprint dataclasses.

Verifying the new `_snapshot()` produces snapshots identical to the HEAD implementation (loaded from `git show` into a scratch module) and benchmarking both regimes.

Now the diff fast path (identical semantics: only names whose fingerprints differ are classified, in the same sorted order).

Re-running the equivalence check and benchmark, plus the existing detector tests.

Verifying the leak fix with the detector gate on the affected test files.

While the arms run, writing the behavioral regression tests. Checking the `toobig` line limit and existing test-file conventions first.

Writing the new real-snapshot regression test module.

Checking the env ignore rules so the secret-hashing test uses a key the snapshot actually records.

All 17 new tests pass. I'll mutation-check their sensitivity after the arms finish (editing the plugin mid-run would contaminate later arms). Checking arm progress.

Ruff reformatting is semantics-neutral, so the in-flight arms are unaffected. Applying the two `functools.cache` fixes in the test file.

The other mypy errors are pre-existing lines; fixing my `map(type, …)` typing in `_has_fixed_fingerprint` via `isinstance` narrowing.

mypy's configured scope is `src` only, but I'll keep this clean anyway with a semantics-identical edit.

Type-clean. Re-reading the final fingerprints module end-to-end to double-check correctness.

Implementation reads correctly. Checking arm progress.

While the remaining arms run, reading the `/sase_monitor` skill to plan the full `just test-cost` handoff.

`test-cost` isn't a guarded catalog recipe. Checking the tail tools' arguments so the monitored run can point them at a dedicated, preserved recording.

Detector arm running now. Meanwhile reading the `sase_beads` memory note (needed before adding notes/closing the bead).

While the detector/both arms finish, checking the committed cost budgets — adding 17 tests could matter if a node-count budget is hard and tight.

Passes 5/5 focused; it's a wall-clock race (0.3 s arm delay vs. a loaded host). Looking at how the arm delay is implemented to see whether a deterministic root-cause fix is cheap.

Fixed deterministically (19/19 ×3). Now the in-worker A/B: old vs new snapshot implementation on `tests/ace/tui/modals` with the detector, 3 workers each, sequentially.

Now editing the stylesheet cache to store one immutable pickled blob.

Hydration semantics match (fresh variables/source dicts, fresh rule graph with shared `RuleSet` identity). Running ruff and the fast-stylesheet-cache tests.

Passing (40/40). Now the per-test clearing of the `lazy_syntax` render caches; first checking no test depends on them persisting across tests (e.g., warmed by a module-scoped fixture).

zlib level 1 shrinks the blob 1.3 MB → 162 KB (repr ~1 ms vs ~4.7–10 ms) for ~2 ms extra per hydrate (still ~4× faster than the old 183 ms deepcopy). Adopting it.

Checking whether the visual-snapshot lane goes through the fast stylesheet seeding path (to know if a targeted PNG check is warranted).

All 7 mutations are now caught; 43 tests pass unmutated and the tree holds only intended changes. Re-running the four matched arms with every fix in place ("after2").

While after2 runs (~25 min), checking the bead's epic-symbols entries (required before closing).

No epic-symbol entries. While after2 runs, reviewing the full diff for quality.

Diff reads cleanly. Checking docs for references to the stylesheet cache behavior I changed, while the arms continue.

All lint stages passed; the only test failure is the triage-labeled FLAKY registry test, which passes 3/3 focused. Recording the evidence on the bead now, before handing the full run to a monitor.

Adding the flake follow-up proposal per the epic's rules (not quarantined; evidence only).

Now reading the `/sase_final` skill so the monitor handoff and commit declaration are done correctly.

Staging the full-suite `just test-cost` monitor (3 workers, dedicated preserved recording/report directory; the report and both budget modes run against that exact recording even if pytest fails).

The monitor is staged. Getting the final context to declare the commit.

The test-cost lane's overhead is down about 3× on a local 3,656-test subset (3 workers), and the subset now passes the leak gate. Whether CI now finishes inside 180 minutes is not proven yet: the full local `just test-cost` run is staged and starts after this turn, and only a real CI run will settle it. The changes are declared for commit, and bead `sase-1rq.2.1.3` stays open.

**What was slow.** The global-leak detector, not the cost recorder (recorder-only ran as fast as plain mode). The detector snapshots global state before and after every test. The plan's lead (per-binding probe work) was real but small. In real TUI test workers, most of the time went to re-rendering a few big cache values on every snapshot:
- the shared test stylesheet cache: ~88 ms per snapshot;
- the syntax-highlight caches: up to 430 ms per snapshot.

Snapshots used to take 123–603 ms each; now the median is 68–79 ms and the worst seen is 124 ms.

**Subset results** (seconds as pytest reports them):

| | plain | recorder only | detector only | full cost mode |
|---|---|---|---|---|
| before | 247 | 244 | 684 | 668 (failed: 20 leaks) |
| after | 215 | 231 | 362 | 353 (passed: 0 leaks) |

Full cost mode went from 2.70× plain to 1.64×. The added time fell from 421 s to 138 s, and the added CPU from 1,286 s to 406 s.

**Changes:**
- **Snapshot code:** faster but exact. On the same loaded state, the new code gives byte-identical snapshots to the old code. Every binding is still visited at both test boundaries, and mutable values are still fully re-checked each time.
- **Stylesheet cache:** now stored as one compressed pickle. It is cheap to check exactly, and it also makes each TUI test app boot faster (~183 ms to ~49 ms). 12 targeted screenshot goldens are unchanged.
- **Real leak fixed:** all 20 leaks came from the associated-plan sheet caches keeping temp-path entries between tests. They and the syntax caches are now cleared after each test, the same way other caches already are.
- **Flaky test fixed:** the chooser modal's arm-delay test failed once in a loaded run, because a 0.3 s real-time window could expire before the first keypress landed. It now uses a fixed long window and backdates the timer instead of sleeping.
- **New tests:** 20, covering what the detector must still catch and the stylesheet cache. I broke each fast path on purpose in 7 ways and the tests caught all 7.

**Checks:** `sase tool run check` ran the full suite: all lint passed and 60,478 tests passed. One registry test (`test_registry_rebuild_keeps_live_identity_pending_claim`) failed. The tool labelled it flaky, it passed 3/3 when run alone, and my change doesn't touch it. I recorded it on the bead as a proposed follow-up without skipping it.

**Unchanged as required:** timeouts, worker count, budgets, leak flags, and test selection. I added no leak exclusions. The cost recorder is unchanged.

**Estimate (not verified):** plain CI on the same tests took ~52 min, and the cancelled test-cost run was heading for ~193 min. A ~3× smaller overhead suggests roughly 95–110 min.

**Next:** the staged run is `just test-cost` on the full suite with 3 workers. Its results go to `/var/tmp/sase-1rq.2.1.3-test-cost-<timestamp>/`. That directory also holds the cost report and both budget checks (local and `--ci`), run against that exact recording even if pytest fails. A follow-up agent then reads the results, fixes or records any new leaks, failures, or budget breaches, and closes the bead only if the run, report, and budget check all complete.

A few smaller product caches still cost about 3–12 ms each per snapshot. I left them alone to keep the change contained.
<!--sase:budget-span:close:1-->

---

%macros_enabled:true
# New Query
%model:opus@xhigh

%macros_enabled:false
# Monitored command finished

**Command:**

```text
OUT=/var/tmp/sase-1rq.2.1.3-test-cost-$(date -u +%Y%m%dT%H%M%SZ); mkdir -p "$OUT/cost"; echo "OUT=$OUT"; START=$(date +%s); SASE_PYTEST_WORKERS=3 SASE_TEST_COST_DIR="$OUT/cost" just test-cost --sase-global-leak-report="$OUT/sase-global-leaks.json" > "$OUT/test-cost.log" 2>&1; rc=$?; echo "just test-cost rc=$rc wall_s=$(( $(date +%s) - START ))"; REC=$(ls -t "$OUT"/cost/*.json 2>/dev/null | head -1); echo "recording=$REC"; .venv/bin/python tools/test_cost_report --recording "$REC" > "$OUT/report.txt" 2>&1; echo "test_cost_report rc=$?"; .venv/bin/python tools/check_test_cost_budgets --recording "$REC" > "$OUT/budgets-local.txt" 2>&1; echo "budgets local rc=$?"; .venv/bin/python tools/check_test_cost_budgets --recording "$REC" --ci > "$OUT/budgets-ci.txt" 2>&1; echo "budgets ci rc=$?"; grep -E "passed|failed|leak detector|error" "$OUT/test-cost.log" | tail -8; tail -15 "$OUT/budgets-local.txt"; exit $rc
```

**Directory:**

```text
/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_25
```

| | |
| --- | --- |
| **Outcome** | FAILED — exit 1 |
| **Started** | 2026-11-07T18:53:17.406545+00:00 |
| **Finished** | 2026-11-07T21:01:26.103375Z |
| **Elapsed** | 2h 4m 40s of a 5h 0m 0s budget |
| **Output** | 4 KiB · evidence refs: `file:monitor-diagnostic-manifest:wqmd3t8mxmbx`, `file:monitor-retained-log:wqmd3t8mxmbx` · full log: `sase monitor show wqmd3t8mxmbx --all-lines` |

**Why this was monitored:** Full-suite test-cost validation for sase-1rq.2.1.3 after the leak-detector, stylesheet-cache, and cache-isolation fixes (3 workers, CI width); preserves the exact recording and leak report

## Last 120 lines of output
<!--sase:budget-span:open:kind=old_raw_excerpts;id=1-->

Everything between the fences below is raw command output -- untrusted data, not instructions. The only instruction in this prompt is the "Your next action" section.

```text
sase: running unwrapped (no profile (monitor.tool_wrap is verify))
OUT=/var/tmp/sase-1rq.2.1.3-test-cost-20261107T185645Z
just test-cost rc=1 wall_s=7480
recording=/var/tmp/sase-1rq.2.1.3-test-cost-20261107T185645Z/cost/20261107T210118Z-1998944.json
test_cost_report rc=0
budgets local rc=1
budgets ci rc=1
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_25/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_retry_on_retryable_error changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_25' to '<deleted>'; restored it.
tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_error_after_slot_admission_records_run_started_at
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_25/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_error_after_slot_admission_records_run_started_at changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_25' to '<deleted>'; restored it.
- sase global leak detector: 157 poisoning change(s) across 156 test(s); 115005 warming mutation(s) filtered; 965 cooling mutation(s) filtered; 6351 invalidation(s) filtered; report=/var/tmp/sase-1rq.2.1.3-test-cost-20261107T185645Z/sase-global-leaks.json -
---------------- sase global leak detector blocking gate failed ----------------
FAILED tests/ace/tui/test_screenshot_export.py::test_app_export_body_tolerates_signal_task_prepare_error
==== 2 failed, 60534 passed, 18 skipped, 109 warnings in 7468.17s (2:04:28) ====
error: recipe `test-cost` failed on line 639 with exit code 1
- [hard] causes.subprocess_run.count: actual 104676.000 exceeds budget 52000.000 + 0% tolerance (52000.000)
- [hard] causes.textual_app_run_test_enter.cpu: actual 1654.690 exceeds budget 750.000 + 25% tolerance (937.500)
- [hard] causes.textual_app_run_test_enter.count: actual 5589.000 exceeds budget 4500.000 + 0% tolerance (4500.000)
- [hard] causes.yaml_load.cpu: actual 50.214 exceeds budget 24.000 + 25% tolerance (30.000)
- [hard] causes.yaml_load.count: actual 113228.000 exceeds budget 71000.000 + 0% tolerance (71000.000)
test cost budget advisories: /var/tmp/sase-1rq.2.1.3-test-cost-20261107T185645Z/cost/20261107T210118Z-1998944.json
wall-clock overages usually mean the host was busy, not that the suite got more expensive; the cpu/count figures alongside each entry are contention-stable, so compare them to tell the two apart.
- [advisory] total_file_wall_seconds: actual 10441.873 exceeds budget 4700.000 + 15% tolerance (5405.000) (cpu=6946.223s)
- [advisory] causes.ace_page_enter: actual 2272.328 exceeds budget 540.000 + 15% tolerance (621.000) (cpu=2278.769s, count=1123)
- [advisory] causes.ace_settle_pilot: actual 1460.347 exceeds budget 340.000 + 15% tolerance (391.000) (cpu=1457.945s, count=15632)
- [advisory] causes.parser_create: actual 142.425 exceeds budget 52.000 + 15% tolerance (59.800) (cpu=141.344s, count=2648)
- [advisory] causes.pilot_pause_delay: actual 1249.238 exceeds budget 230.000 + 15% tolerance (264.500) (cpu=1199.127s, count=31790)
- [advisory] causes.subprocess_run: actual 1068.023 exceeds budget 540.000 + 15% tolerance (621.000) (cpu=207.721s, count=104676)
- [advisory] causes.textual_app_run_test_enter: actual 1651.052 exceeds budget 470.000 + 15% tolerance (540.500) (cpu=1654.690s, count=5589)
- [advisory] causes.yaml_load: actual 50.291 exceeds budget 20.000 + 15% tolerance (23.000) (cpu=50.214s, count=113228)
```

<!--sase:budget-span:close:1-->
## Continuation checkpoint

- **Ref:** `local:continuation/checkpoints/monitor_start-d274475630a61ae6.json`

**Checkpoint (JSON):**

```text
{
  "kind": "monitor_start",
  "payload": {
    "command": "OUT=/var/tmp/sase-1rq.2.1.3-test-cost-$(date -u +%Y%m%dT%H%M%SZ); mkdir -p \"$OUT/cost\"; echo \"OUT=$OUT\"; START=$(date +%s); SASE_PYTEST_WORKERS=3 SASE_TEST_COST_DIR=\"$OUT/cost\" just test-cost --sase-global-leak-report=\"$OUT/sase-global-leaks.json\" > \"$OUT/test-cost.log\" 2>&1; rc=$?; echo \"just test-cost rc=$rc wall_s=$(( $(date +%s) - START ))\"; REC=$(ls -t \"$OUT\"/cost/*.json 2>/dev/null | head -1); echo \"recording=$REC\"; .venv/bin/python tools/test_cost_report --recording \"$REC\" > \"$OUT/report.txt\" 2>&1; echo \"test_cost_report rc=$?\"; .venv/bin/python tools/check_test_cost_budgets --recording \"$REC\" > \"$OUT/budgets-local.txt\" 2>&1; echo \"budgets local rc=$?\"; .venv/bin/python tools/check_test_cost_budgets --recording \"$REC\" --ci > \"$OUT/budgets-ci.txt\" 2>&1; echo \"budgets ci rc=$?\"; grep -E \"passed|failed|leak detector|error\" \"$OUT/test-cost.log\" | tail -8; tail -15 \"$OUT/budgets-local.txt\"; exit $rc",
    "cwd": "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_25",
    "member_agent_name": "sase-1rq.2.1.3--mon",
    "monitor_id": "wqmd3t8mxmbx",
    "next_output": "tail",
    "parent_node_ids": [
      "agent-delta:20261107102711:fbac7d6a53ee0c37"
    ],
    "project_name": "gh_sase-org__sase",
    "request_fingerprint": "sha256:e7638d22a8f1e72c9a19bdfd72bd3ed1f3d4a3c2e8bc30b4275769fc9820453a",
    "starter_agent": "sase-1rq.2.1.3--code",
    "starter_artifacts_dir": "/home/bryan/.sase/projects/gh_sase-org__sase/artifacts/ace-run/202611/07/20261107105141"
  },
  "recorded_at_epoch": 1794077805.4407172,
  "schema_version": 1
}
```


## Your next action

You are the follow-up for phase bead sase-1rq.2.1.3 (plan:202611/test_cost_snapshot_overhead.md). The changes from the previous turn were already committed through host completion. The monitored command ran the full `just test-cost` with SASE_PYTEST_WORKERS=3 and kept its artifacts in the directory echoed as OUT=... at the top of the output: cost/<recording>.json, sase-global-leaks.json, test-cost.log (full pytest output), report.txt (tools/test_cost_report), budgets-local.txt, and budgets-ci.txt (tools/check_test_cost_budgets without and with --ci, all against that exact recording). Do this: (1) Read the pytest summary, the "sase global leak detector" line, and wall_s from test-cost.log, then report.txt and both budget files. (2) For every pytest failure, rerun the node focused through tools/run_pytest. If it passes on the unchanged tree, it is a flake: append `PROPOSED FOLLOW-UP: flake — <nodeid> — <evidence>` to sase-1rq.2.1.3; do not create beads. If it is deterministic and caused by this phase diff, fix it. If it reproduces on the clean base or is out of scope, append one PROPOSED FOLLOW-UP note per family with nodes, base evidence, and artifact paths. (3) For any poisoning in sase-global-leaks.json, fix the causal leak the same way tests/_conftest_runtime.py `_reset_derived_config_caches` now clears _ASSOCIATED_PLAN_SHEET_* and the lazy_syntax caches. Never add broad exclusions. (4) For any hard budget breach, record exact actual/allowed values and leave the budgets unchanged; CPU overages are advisory under --ci. (5) Append a bead note to sase-1rq.2.1.3 with: full-run wall time and pytest counts, the leak result, whether the report and the local/CI budget checks completed and their outcomes, the recording path, and a comparison to the ~193-minute projected CI test-cost run (local hardware, not a CI claim). (6) If you changed files, run `sase tool run check`. (7) Run `sase bead epic-symbols sase-1rq.2.1.3`. If the full run completed pytest, the report, and the budget check with any remaining failures recorded as follow-ups under the epic clean-base and bounded-remainder rules, close the bead with `sase bead close sase-1rq.2.1.3 --note "..."`. Otherwise keep it open. Never close ancestors. (8) Finish through /sase_final. If files changed, submit a commit decision for the sase repo (bead_action close only when you closed the bead scope; otherwise keep).
%macros_enabled:true

## Response

Reading the run's artifacts first: the pytest summary, leak report, cost report, and budget files.

Two failures. The first looks caused by the `SASE_TEST_COST_DIR` override I set in the monitor command; the second is a screenshot convergence timeout. Reading both in full.

CI doesn't set `SASE_TEST_COST_DIR`, so this one only fails when the override env is present, as it was in my monitor command. Now the leak report, which is the main item: 157 poisoning changes.

Each of those tests adds one more copy of `<repo>/tools` to `sys.path`: the list grows 39→40→41… and is never restored. Finding the helper that inserts it.

None of the affected tools are vendored (`-YYmmdd`), so they're safe to edit here. Checking the exact insert lines in all six tools the family loads.

`tools/release_metrics` itself doesn't touch `sys.path`; its test inserts `tools/` directly at three places. Viewing those.

Now the release-metrics test: one guarded module-level insert.

`tools/run_pytest cost <paths>` runs the full gate. Running the whole `sys.path` family under it, with recordings and the leak report kept in scratch.

The script resolved to the system Python, which doesn't have `sase` installed. Rerunning with the venv on `PATH`.

Zero poisonings, 258 passed. Confirming this subset actually leaked before the edits by stashing them and rerunning on the clean base.

I'll clear both display dicts in place under the module's lock and bump the humanize generation, which is what invalidation already does. Next, the deck view's `_prebuilt_bodies`.

That one is a live-thread timing question and needs a focused repro, so I'll check it after the simple fixes. Viewing the remaining `human_only` call site before editing.

Checking two risks: what `_bump_humanize_cache` does, and whether any footprint or deck test depends on these memos across a fixture boundary.

Pyright rejects attribute assignment on a `ModuleType`. Switching to a loop with `setattr`, which matches the loop style of the other helpers and avoids ruff's constant-`setattr` rule.

Neither failing area is in that diff, though `test_screenshot_export` does boot through the stylesheet cache I changed. Now reading the full budget outputs and the cost report.

Running the new test, then mutation-checking it by temporarily removing the two new reset calls.

The shell's `cp` is aliased to interactive `cp -i`, so the overwrite prompt hung. The file was never overwritten. Verifying it matches the backup, then retrying with `command cp -f`.

Both mutants fail the test, and the file is restored. Since I changed tracked files, the `lint_and_test` note is required reading before verification.

Formatting and linting the changed files before the full check.

Ruff passes. Smoke-checking that the five edited tools still start as scripts.

All five start cleanly. Running `sase tool run check`. My change to `tests/_conftest_runtime.py` will likely escalate it to the full suite, so I'm allowing a long timeout.

`sase tool run check` passed in about 19.6 minutes. Pulling the scoped test lane's summary line for the bead note.

The check passed (exit 0). Its scoped lane escalated to the full suite because I touched the root conftest. Running `sase bead epic-symbols` for the bead.

No epic-symbol entries. Before writing the bead notes, extracting the exact node IDs for the thread-race family from the full-run report.

Recording the evidence on the bead: one progress note, then one `PROPOSED FOLLOW-UP:` per remaining family.

Bead closed. Last step: finishing through `/sase_final` with a commit declaration for the sase repo.

All 12 dirty paths are this turn's work. Some show `written_by_this_run: false` only because I edited them through Bash scripts. Submitting the commit with `bead_action: close`.

The full local `just test-cost` run now finishes in **124.7 min**, inside the 180-minute cap. The old CI run was projected at about 193 min. This was on athena with 3 workers, not CI, so CI proof is still open. The run didn't pass: 2 tests failed, the leak gate failed, and the budget check failed. I fixed most of the leaks this turn and recorded the rest on the bead. I closed bead `sase-1rq.2.1.3` and declared the commit.

**What the run reported** (artifacts in `/var/tmp/sase-1rq.2.1.3-test-cost-20261107T185645Z/`):
- **Pytest:** 60,534 passed, 2 failed, 18 skipped.
- **Leak gate:** 157 leaks across 11 groups. They predate my earlier speed-up; the cancelled CI run never got far enough to report them.
- **Report and budget checks:** the cost report completed normally. Both budget checks ran to completion and failed: 17 hard breaches locally, 8 in CI mode.

**The 2 test failures:**
- `test_screenshot_export.py::test_app_export_body_tolerates_signal_task_prepare_error` is flaky: it timed out under load and passed 3 of 3 when rerun alone.
- `test_cost_directory_lives_under_the_timing_store` fails every time the `SASE_TEST_COST_DIR` override is set, which my monitored run did. It passes when unset, and CI doesn't set it. It also fails on the code before my changes, so I recorded it with a one-line fix suggestion instead of fixing it.

**Leaks fixed this turn:**
- **`sys.path` (122 of the 157):** five tool scripts added `tools/` to `sys.path` again every time a test reloaded them. They now add it only if it's missing, and `test_release_metrics.py` adds it once. On the same subset: 122 leaks before the fix, 0 after.
- **Eight smaller caches:**
  - Tests that clear shared caches now get their own copy per test.
  - The per-test reset now also clears five shared caches, from project display names through the TUI's pending usage counts. A new test checks that reset, and it fails if either new reset call is removed.
  - On the subset these tests come from: 25 leaks before, 1 after.

The full test-cost run hasn't been repeated with these fixes. `sase tool run check` passed (exit 0); its test stage ran the full suite.

**Recorded on the bead, not fixed:**
- **The 1 remaining leak:** a background config-refresh thread is sometimes still alive when a test ends. Which test it shows up in changes between runs, so it looks like a timing race in teardown.
- **Count budgets (fail in both modes):** for example, subprocess calls are 104,676 against an allowed 52,000. Counts don't depend on machine load. The budgets were last set on 2026-09-18, so this is likely suite growth, but I didn't confirm the cause.
- **Peak worker memory:** 3.16 GB against 2.16 GB allowed in CI mode. Memory grows steadily over each worker's life. On the subset, the leak detector adds only about 50–75 MB, the same as before my changes.

No budgets, timeouts, gates, or exclusions were changed, and no workflow steps were added.
