# Chat History - ace-run (ci_fix.sase.g)

- **TIMESTAMP:** 2026-08-07 03:04:45 EDT
- **MODEL:** claude/opus
- **AGENT:** ci_fix.sase.g

## Prompt

#gh:sase-org/sase
%id(ci_fix.sase.@, tribe=chop)
%wait(runners=0)
#pr(ci_fix_sase_1e35588, status=ready)

GitHub Actions is failing for the sase-org/sase repo. Can you run the `actstat` command to get more information about
the failing jobs, diagnose the root cause of these failures, and then fix them?

Repair the current default-branch CI failure in sase-org/sase.

Pinned failing run: https://github.com/sase-org/sase/actions/runs/31152049889
Pinned failing commit: 1e355887f664dd0015e0036723e991ab473eb7e5
Failed jobs from the sweep:
- coverage-contexts
- test (3.12)
- test (3.13)


First re-verify that this failure and commit are still current on the default branch.
If it was superseded or already fixed, leave the worktree unchanged and report that
outcome. Keep any fix narrowly scoped and run the relevant checks.

## Response

I'll start by verifying the failure is still current on the default branch.

`1e355887f` is still the tip of `origin/master`. Now let me pull the CI failure details.

Failure is current at HEAD. Let me pull the failing job logs.

The pinned run ID was actually the (successful) Publish workflow; the real failure is CI run `31152049642`. Two of the three failures are the same test file. Let me look.

Both failures are the same assertion (`current_selection is not None` right after typing `/needle`). Let me investigate the corpus/refresh race.

Let me set up the workspace and try to reproduce while I read the refresh path.

Passes locally (fast machine). Let me reproduce under CPU contention, and read the controller's corpus capture in parallel.

Passes under load too. Let me instrument to catch the actual mechanism rather than guess.

Let me instrument to confirm which background writer clobbers the injected text.

Let me check the selection logic — `current_selection` could also be None from an unlaid-out overlay viewport.

Let me verify empirically that background workers are still in flight when the test injects text.

Let me examine the third failure, which has a concrete timeout.

Let me confirm all prompt-panel repaints funnel through a single choke point.

Let me force the race locally by widening the window, and capture who repaints.

No repaints at all locally. Let me check the key-dispatch path for a double-start race.

Found a strong lead: the initial `/` is handled by a Textual *binding action*, not by `on_key`. Let me check how `page.press` delivers keys.

Let me instrument the actual ordering of the binding action vs. the typed letters.

Let me test whether a not-yet-settled startup repaint can clobber the injection.

Root cause confirmed. Let me look at the header-enrichment message path.

Root cause is confirmed and reproducible. Let me clean up the probe and implement the fix.

Now the third failure — the stash-pump timeout:

Now let me verify both fixes, including that the metadata fix actually defends against the race I reproduced.

Now let me prove the fix actually defends against the reproduced race by simulating the slow CI worker.

First let me confirm this simulation reproduces the CI failure against the *original* helper:

Exact CI failure reproduced — same tests, same lines (77, 258), same assertion. Now against the fix:

The fix defends against the reproduced race. Let me clean up and run the full check.

Lint gates passed. One test failure — let me check whether it's mine or pre-existing.

My two files aren't in the contract manifest, so they can't affect that measurement. Let me re-run to confirm it's an independent load-sensitive flake.

`just check` passes cleanly. Let me run the full gate since this lands on master CI.

`just check-full` passes — every lint gate plus the full suite. Let me file a bead for the unrelated flaky test I hit.

An existing bead `sase-go` covers exactly this defect. Let me check in-progress epics, then corroborate rather than duplicate.

The epic has no causal link to this test. Corroborating the existing bead instead of duplicating:

Done. The failure was still current on `origin/master` at `1e355887f`, and I fixed it.

## Diagnosis

The pinned run `31152049889` was actually the **Publish** workflow, which *succeeded*. The real failing run is CI `31152049642`. Two distinct root causes, both timing flakes exposed by CI load — not regressions from the release commit (which only bumps a version string).

**`test (3.13)` + `coverage-contexts` — `tests/ace/tui/test_agent_metadata_search.py`** (lines 77 and 258, `assert None is not None`)

`current_selection` is `None` only when the frozen search corpus has no match. The tests inject a fixture document into the live prompt panel, then press `/`, which freezes that text as the corpus. `wait_for_startup` only proves the *detail debouncer* is idle — but startup also spawns **thread workers** (detail-header enrichment, clan/tribe sections) whose completion messages repaint the panel. On a loaded runner those land after the injection, replacing the fixture with real agent metadata, so the corpus never contains `needle`.

I confirmed this by tracing `AgentPromptPanel.update` — the clobber comes through `on_agent_detail_header_enriched` → `refresh_detail_header_from_cache`. I then built a repro that gates that worker until just after the startup barrier: against unmodified code it fails on **exactly the two CI tests, at exactly lines 77 and 258**; with the fix it passes.

**`test (3.12)` coverage leg — `test_prompt_stash_pump_nonblocking.py`** (`TimeoutError` at line 36)

`asyncio.wait_for(asyncio.to_thread(entered.wait), timeout=0.5)` is *setup* — it just sequences the blocking read onto a pool thread — but it was held to a budget as tight as the actual non-blocking assertions. Under xdist plus coverage tracing, merely scheduling that thread can exceed 500 ms, failing the test for the wrong reason.

## Fixes (test-only, both files)

- Added `_settle_agent_detail()`, which waits for `_pending_visual_work` (debouncer, running workers, short one-shot timers, animations) to report clear across 3 consecutive drained pauses before injecting — the pause between samples delivers any already-queued repaint while the panel is still disposable. Plus a post-injection assertion so a future clobber fails with a clear message instead of a cryptic `assert None is not None`.
- Named the stash-pump budgets and raised only the sequencing barrier to 10 s, keeping the 50 ms handler-return and heartbeat budgets that are the actual property under test. The `_slow_read` release timeout was raised in step so the store is still genuinely blocked when the heartbeat samples the loop.

## Verification

`just check-full` passes — every lint gate plus the full suite. Both target files also pass 5 consecutive runs.

One unrelated failure surfaced: `test_contract_set_serial_runtime_stays_within_budget` failed once during a parallel `just check`, then passed standalone (26.77 s against a 30 s budget) and on rerun. It can't be mine — neither changed file is in `tests/contract_manifest.txt`. Bead `sase-go` already tracks this exact defect, so I recorded a `+1` with the independent reproduction rather than filing a duplicate; notably the *uncontended* measurement is already at 26.8 s, so the budget constant looks as suspect as the probe model.

I made no commit, branch, or PR — the two modified files are staged in the working tree for your review.

Committed and pushed as a PR branch.

**Commit:** `f84d119d9` on `sase_ci_fix_sase_1e35588_1` (tracking origin, tree clean) — ChangeSpec `sase_ci_fix_sase_1e35588_1`.

**What it fixes** — both CI failures at `1e355887f` are test-side timing races, not regressions from the release commit:

- **`test (3.13)` + `coverage-contexts`** — `tests/ace/tui/test_agent_metadata_search.py` injected its fixture document once the detail debouncer went idle, but startup thread workers (detail-header enrichment, clan/tribe sections) repaint the same panel on completion. On loaded runners those landed after the injection, so the corpus frozen at `/` held real agent metadata and `current_selection` stayed `None`. Added `_settle_agent_detail()`, requiring `_pending_visual_work` to be clear across 3 consecutive drained pauses, plus a post-injection assertion that names the clobber instead of surfacing `assert None is not None`.
- **`test (3.12)`** — `test_prompt_stash_pump_nonblocking.py` held the `asyncio.to_thread(entered.wait)` *setup* step to the same 0.5 s budget as the real assertions; under xdist + coverage tracing, scheduling that thread alone can exceed it. Named the budgets and raised only the sequencing barrier to 10 s, keeping the 50 ms handler-return and heartbeat budgets that are the actual property under test.

Verification from the prior pass stands: `just check-full` passed (all lint gates + full suite), and a gated repro reproduced the exact CI failure (same two tests, lines 77 and 258) against unmodified code while passing with the fix.

One caveat worth your attention: `test_contract_set_serial_runtime_stays_within_budget` failed once under parallel load and passed standalone at 26.8 s against a 30 s budget. It's unrelated to these files (neither is in `tests/contract_manifest.txt`); bead `sase-go` already tracks it and I recorded a corroboration there rather than filing a duplicate.
