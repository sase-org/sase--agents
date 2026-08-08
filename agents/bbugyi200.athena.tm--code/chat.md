# Chat History - ace-run (tm--code)

- **TIMESTAMP:** 2026-08-05 19:43:17 EDT
- **MODEL:** claude/sonnet
- **AGENT:** tm--code

## Linked Chats

- 1. --plan — `~/.sase/chats/202608/gh_sase_org__sase-ace_run-tm__plan-260805_190136.md`
- **2. --code** — `~/.sase/chats/202608/gh_sase_org__sase-ace_run-tm__code-260805_190136.md`

## Prompt

%model:@claude_coder
#gh:gh_sase-org__sase @sase/repos/plans/202608/test_suite_tier0.md

The above plan has been reviewed and approved. Implement it now.


## Response

I'll implement this plan directly since it's a single cohesive commit. Let me start by reading all the files that need changes.

Now let's look at the other relevant files.

Now let's look at the CI workflow file and docs/development.md and the dismissed bundle test file.

Let's start implementing. First, Change 1 and 4 in `_suite_gate.py`.

Now let's implement Change 2 in `tools/run_pytest`.

Let's verify no other references to the deleted names remain in `tools/run_pytest`.

Clean. Now let's update `tests/test_run_pytest_tool.py` for Change 2.

Now replace the two cov-mode visual tests with a single test.

Let's check for any other references to `EXCLUDE_VISUAL_ENV` or `FAST_NON_VISUAL_MARKER_EXPRESSION` across the repo.

Now let's edit `.github/workflows/ci.yml` for Change 2 (remove env blocks) and Change 3 (add slow test step to perf-floors).

Now let's apply the ci.yml edits: remove both env blocks (Change 2), and add the "Run slow tests" step to perf-floors (Change 3).

Now add the "Run slow tests" step to the perf-floors job (Change 3), placed alongside the other floor steps.

Now let's find and mark the three dismissed-bundle tests as `slow`.

Let me check if `pytest` is already imported in this file (needed for `@pytest.mark.slow`).

`pytest` is already imported. Now add the marks.

Now let's update `tests/test_github_actions_ci.py`: rewrite `test_visual_suite_runs_only_in_dedicated_job` and add a new regression test for the slow-lane CI step.

Now let's update `docs/development.md`.

Now let's look at line 270 area to update it.

Let's check for any other stale references in docs/development.md or elsewhere to `SASE_PYTEST_EXCLUDE_VISUAL` or the old memory calibration figures.

Those remaining hits are all in research/plan/bead history docs, which are out of scope. The actual code and docs are updated. Now let's mark task 8 complete and move to verification.

Install succeeded (the sase-core version warning is pre-existing and unrelated). Now let's run `just check`.

This is the known pre-existing symvision failure (`progress_fingerprint`, tracked as sase-fj). Since `just check` stopped there, let me check whether it runs tests after lint or if I need to run them separately.

Both pass. Now let's run `validate-committed-plans` and then the full `just test`.

Now let's run the full test suite.

The test run is still going in the background. I'll wait for it to complete.

The background `just test` run finished successfully. Let's check its output.

`just test` passed: 25545 passed, 7 skipped. Now let's verify the collection counts and targeted files per the plan's verification steps 3-6.

Both match the plan exactly: fast lane 16/19, slow lane 3/19. Now let's run the targeted test files and the full slow lane to confirm everything passes.

All 109 targeted tests pass. Now let's run `just test-slow` to confirm the slow lane (with the 3 relocated tests) passes and is non-fatal.

The plan flagged exactly this risk — the "system temp leakage" report might not be non-fatal. Let me check what's actually failing at Justfile line 338.

This matches the exact risk flagged in the plan — the temp-leak guard turns the "informational" leak report into an actual `TESTS_FAILED` exit code. Let me check if this is deterministic by re-running.

This confirms the leak is deterministic — `just test-slow` will fail every time in CI's perf-floors job, even though all tests pass. The plan is explicit here: file a task bead for the `uv_tool` harness rather than deleting the CI step or disabling the guard. Let me do that now.

Now let's check for existing duplicate tasks and any related active epics before creating a new bead.

No matches — not a duplicate. Let's check active in-progress epics for a credible causal link.

No causal link — that's the only in-progress epic, and it's unrelated (bead creation time display, not test infra). Let's create the new task bead now.

The bead is filed. Let's clean up the remaining stale comment in the Justfile that still claims `just test` includes visual snapshots.

These comments are stale now — the default lane no longer runs visual tests but still depends on `_setup-visual` for collection (per the plan's explicit "Do NOT change the `_setup-visual` dependency" note). Let me fix them to be accurate.

No justfile-specific lint recipe exists, so this is safe. Let's do a final sanity check of the full diff before wrapping up.

This matches the plan's expected scope. Let's do one final full `git diff` review to make sure everything is coherent.

This all matches the plan precisely. Let's mark verification complete.

## Summary

Implemented all four Tier 0 changes from the plan in `sase/repos/plans/202608/test_suite_tier0.md`:

1. **Proportional CPU reserve** — `tests/_suite_gate.py` now reserves `max(1, cpu_count // 8)` CPUs instead of a flat 4, fixing the 4-vCPU CI runner collapsing to 1 worker.
2. **Right-sized memory reserve** — `_MEMORY_KIB_PER_WORKER` dropped from 1.2 GiB to 950 MiB, matching measured worker RSS.
3. **Visual excluded from default `just test`** — `tools/run_pytest`'s `FAST_MARKER_EXPRESSION` is now `"not slow and not visual"`; removed the now-dead `SASE_PYTEST_EXCLUDE_VISUAL` env var, its CI wiring, and the helper function.
4. **Three dismissed-bundle scale tests moved to `slow`** — and a `just test-slow` step was added to CI's `perf-floors` job so they stay covered.

All test files, `ci.yml`, and `docs/development.md` were updated per the plan, plus two stale Justfile comments I found along the way. Verification: `just install`, `just lint`/`validate`/`toobig` all pass (symvision's pre-existing `progress_fingerprint` failure is the only lint red, as the plan anticipated); full `just test` passed 25545/7 skipped with exactly 418 tests deselected (visual); collect-only counts match the plan exactly (fast lane 16/19, slow lane 3/19 for the dismissed-bundle file).

One thing the plan flagged as a risk did occur: `just test-slow` deterministically fails via the temp-leak guard because `tests/uv_tool/test_real_uv_harness.py` leaves `uv-setuptools-*.lock` files behind — all tests pass but the guard flips the exit code. Per the plan's explicit instruction, I didn't delete the new CI step or disable the guard; I filed task bead **sase-fo** (ready) for the `uv_tool` harness fix instead.

Nothing is committed — let me know if you'd like me to commit this.

These are the changes from my prior implementation of the Tier 0 plan. Let me verify the diff looks complete and correct before committing.

This matches the scope described in the prior session's summary. I'll now invoke the commit skill for these files.

The commit succeeded (the archive-publication warning is unrelated bookkeeping, not a failure). Let me verify the working tree is clean and pushed.

Working tree is clean and in sync with `origin/master`. The Tier 0 test suite changes are committed and pushed.
