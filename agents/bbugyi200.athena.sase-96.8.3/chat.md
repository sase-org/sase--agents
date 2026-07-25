# Chat History - ace-run (sase-96.8.3)

- **TIMESTAMP:** 2026-07-25 15:59:05 EDT
- **MODEL:** claude/opus
- **AGENT:** sase-96.8.3

## Prompt

#gh:gh_sase-org__sase
%id(3, clan=sase-96.8, bead=sase-96.8.3)
%model:@medium_phase_worker
%auto
Can you complete the work for bead sase-96.8.3? The bead is already reserved for you and assigned to your agent
name: it was set to status=claimed while your agent was waiting, and the runtime promoted it to
status=in_progress before you started reading this. Do not set either status by hand. Read its description and
design file, do the work, and close the bead. Do NOT close the parent epic. Do NOT create new beads.

## Response

I'll start by reading the bead.

Now let me look at the relevant source files.

Now let me implement. First the guard helper:

Now the sandbox-aware `get_sase_managed_tmpdir`:

Now extend the leak guard:

Now update the affected existing tests and add new coverage:

Now add coverage for the new guard helper itself:

Now run the targeted tests:

Now the plan's verification experiment:

Lint is clean. Now the full `just check`:

I'll wait for the background `just check` to finish.

The full `just check` is running in the background; I'll report when it completes.

The `just check` suite is still running. I'll report as soon as it finishes.

Implementation is complete and the targeted verification passes. The full `just check` is still running in the background — I'll report its result and close the bead when it lands.

Summary of what's in place so far:

- **`src/sase/core/state_write_guard.py`** — new `require_pytest_sandbox_root(purpose=...)`: returns `None` outside pytest, the resolved `SASE_PYTEST_SANDBOX_DIR` inside it, and raises (fail closed) when a pytest process published no sandbox — same shape/wording as `assert_bead_store_write_sandboxed()`.
- **`src/sase/core/paths.py`** — `get_sase_managed_tmpdir()` now routes through that guard, landing under `<sandbox>/managed-tmp/<parts…>` under pytest. Production behavior is untouched (`$SASE_TMPDIR`, else `~/.sase/tmp`), now factored into `_unsandboxed_managed_tmpdir_root()`.
- **`tests/_tmp_leak_guard.py`** — `watched_temp_directories()` returns the `tempfile` root *and* the developer's real managed root (deduped). Top level only: the category children (`handoff/`, `wrappers/`, …) get continuous writes from other live sase processes on this host, so diffing them would report their scratch — the same reason shared `/tmp` isn't watched. `ace_profile_*`/`sase_ace_prompt_*` are allowlisted for the same reason (concurrent agent launches; the `prompt_leak` phase retires both).

The plan's reproduction now shows a zero delta — the same 31-test run that added `workflow-artifacts=+6` before adds nothing:

```
before: workflow-artifacts=402 handoff=330 wrappers=134
31 passed, 4 warnings in 2.57s
after:  workflow-artifacts=402 handoff=330 wrappers=134
```

`just lint` is clean (ruff, mypy over 2372 files, symvision).

One thing worth flagging: `sase repo open plans` was failing on entry because the plans repo was stuck mid-rebase with a conflict in `beads/events/streams/sase-96.8.jsonl` (two agents both took event index `000023`), which broke every bead command. `sase bead resolve-conflicts` fixed it, and the subsequent `sase repo open` recovered the clone to `origin/main` — which reset sase-96.8.3 from `in_progress` back to `open` and dropped its assignee, retaining the claim commit at `refs/sase/recovery/20260725T184614Z-main-0882755d1f`. I did not set any status by hand; I'll still close the bead as instructed.

No `just check` is running in my workspace anymore and its output is gone, so I'll re-run it while I handle the bead.

Changes are intact. Waiting on `just check`.

`just check` is re-running in the background (ID `b5hv5h13s`). I'll close the bead and commit once it passes — I want a green check before finalizing, since the earlier run's output was lost.

Bead closed. Now committing.

Now finalizing the sase commit bookkeeping.

Done. sase-96.8.3 is closed and the work is committed and pushed as `bd16432c9`.

## What changed

**`src/sase/core/state_write_guard.py`** — new `require_pytest_sandbox_root(purpose=...)`: `None` outside pytest, the resolved `SASE_PYTEST_SANDBOX_DIR` inside it, and it raises when a pytest process published no sandbox. Fails closed, because silently falling back to the production target is the leak the guard exists to prevent — same shape and wording as `assert_bead_store_write_sandboxed()`.

**`src/sase/core/paths.py`** — `get_sase_managed_tmpdir()` routes through that guard and lands under `<sandbox>/managed-tmp/<parts…>` under pytest. Production behavior is unchanged (`$SASE_TMPDIR`, else `~/.sase/tmp`), factored into `_unsandboxed_managed_tmpdir_root()`, which never creates the directory so the leak guard can still name the developer's real root from inside a pytest process.

**`tests/_tmp_leak_guard.py`** — now watches that real root alongside the `tempfile` root, deduped when they coincide. Top level only: the category children (`handoff/`, `wrappers/`, …) take continuous writes from other live sase processes sharing the root, so diffing them would report their scratch — the same reason shared `/tmp` isn't watched.

Plus new coverage in `tests/test_managed_tmpdir_sandbox.py`, and updates to `test_tmp_leak_guard.py`, `test_state_write_guard.py`, `test_multi_prompt_launcher_serialization.py`, and `test_xprompt_catalog_render_build.py` (it asserted the catalog PDF landed under `~/.sase/tmp`; it now asserts it routes through the managed helper, which is the property it was after).

## Verification

The guard immediately paid for itself: the first full run after wiring it up reported a new `launch-prompts/` entry in the real root. That turned out to be a **sibling** phase's producer — `sase-96.8.2`, which landed upstream mid-run and routes agent-launch prompts and ACE profiles through the managed helper. Since other live sase processes on this host write those names into the same shared root, `launch-prompts`, `ace-profiles`, `ace_profile_*`, and `sase_ace_prompt_*` are allowlisted rather than treated as suite leaks.

Post-rebase `just check`: lint clean, **22193 passed, 2 failed**, no leak-guard report.

Both failures are unrelated to this change and I left them alone:
- `tests/ace/tui/widgets/file_panel/test_diff_cache.py::test_get_agent_diff_invalidates_when_index_changes` — **pre-existing on `origin/master`**. Confirmed by reproducing it with my source changes stashed; the file_panel and `running_field` sources are byte-identical to upstream.
- `tests/test_suite_gate_integration.py::test_scaled_suite_runs_share_capacity_and_release_after_sigkill` — contention-flaky; passes in isolation (re-ran it just now, 1 passed).

Two process notes: the rebase onto `origin/master` conflicted in `paths.py` because `sase-96.8.2` deleted `get_sase_tmpdir()` and rewrote the same docstring; I took upstream's deletion and merged both docstring paragraphs. And the resume printed a warning that agent-hood publication for `sase-99` will retry automatically — the primary commit succeeded and the branch is in sync with upstream.
