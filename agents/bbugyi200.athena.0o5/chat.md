# Chat History - ace-run (0o5)

- **TIMESTAMP:** 2026-09-20 13:03:28 EDT
- **MODEL:** claude/sonnet
- **AGENT:** 0o5

## Prompt

#gh:gh_sase-org__sase The 202609/provider_teardown_stall_watchdog.md plan file has been reviewed and approved. Implement
it now. %m:@medium

## Response

I'll start by locating the plan file.

Found the plan at `~/.sase/plans/202609/provider_teardown_stall_watchdog.md`. I'm reading the provider subprocess code it touches before I write anything.

Status: I've read the stream loop, the muse call path and the claude/codex wrappers. Next I'm checking the agent and monitor registries that the reaper's exclusion logic has to consult.

Status: the watchdog and the bounded drain are in place. I'm now refactoring `stream_process_output` to share its per-line handlers between the main loop and the drain.

Status: source changes are done. Now I'm writing the tests — reaper unit tests first, then the watchdog and stream-level regression tests.

Status: all new tests pass. I'm running a quick mutation check to confirm the muse end-to-end test fails if the return-code normalization is removed.

The mutation check confirmed both tests catch the regression, but the restore `cp` prompted and didn't overwrite. Restoring the file now and verifying.

The restore is verified: `return 0` is back at line 190 and the diff shows identical files. Next come formatting, lint and the existing suites.

Status: ruff and mypy are clean. I'm reading the required `lint_and_test` memory note before running the remaining checks.

Formatting is normalized with no stray changes. Now the full `just check` gate through `sase tool run`.

`just check` failed at line 699, the symvision gate. I'm pulling the failure output.

Status: all 43 new tests pass with the private API. I'm re-running symvision alone to see whether only unrelated failures remain.

My symbols are gone from the list. The 26 remaining entries are in files I haven't touched. I'll confirm they also fail on a clean checkout of `HEAD`, without disturbing my working tree.

All lint and validation stages pass. Next is the diff-scoped test lane (`just test-scoped`), which is what `just check` finishes with.

The test lane ran 43,840 tests and 4 failed, none in areas I touched. I'm checking whether they're related to my change.

The same 4 tests fail with my changes stashed, so they're pre-existing on master. I've restored the working tree (14 files back). A final sanity run over the provider tests and the new tests:

There's a "Subprocess Streaming" section and an "Environment Variable Reference" section in `docs/llms.md`. I'm looking at both to add a short watchdog note.

The work is complete and verified. Per the project rules, I need to submit the SASE final declaration as the last action before my summary.

I implemented the watchdog and the reaper, and the final declaration is accepted. It passes its own tests and every lint stage. `just check` itself still stops at symvision, which already fails on master.

If a provider outlives the grace period after `final_submission.json` is accepted, it is now terminated and its leaked descendants reaped. The grace period is 120 s, set by `SASE_PROVIDER_TEARDOWN_GRACE_SECONDS`, and `0` disables it. The watchdog is wired into `agy`, `claude`, `codex`, `grok`, `muse`, `opencode` and `qwen`. The reaper lives in `src/sase/llm_provider/_subprocess_reap.py`. A stall is written to `provider_teardown_stall.json` and to stderr. The turn is reported as a clean exit with its reply intact, so muse no longer raises `CalledProcessError`. I also added a section to `docs/llms.md`.

## Deviations from the plan

- **Snapshot before the kill.** The plan says kill the provider, then walk descendants. Once the provider dies, its children reparent to init and a `ppid` walk finds nothing. The reaper now snapshots the tree first.
- **Pid-reuse guard.** After the provider is dead, every orphan has already reparented, so re-reading `ppid` can't guard against pid reuse. Each target records `process_identity_token` at snapshot time and is signalled only while that still matches.
- **Stale declarations.** A `final_submission.json` already present when the watchdog starts is ignored. Otherwise a resumed run would be killed 120 s after starting. A newer acceptance restarts the grace timer.
- **Bounded drain.** If a shielded process still holds the provider's stdout, the post-kill drain now gives up after a short settle period instead of hanging.
- **Fail-safe sweep.** If the live agent registry can't be read, no descendants are signalled, only the provider.

## Verification

- **New tests:** 43 pass, including exclusion of a registered monitor and everything under it, a leaked process in its own session, and a muse end-to-end run against a fake wedged `muse`. Removing the return-code normalization makes two of them fail with `-15` and `CalledProcessError`.
- **Existing suites:** `tests/llm_provider` and `tests/test_llm_provider_subprocess.py` pass (1013 tests).
- **Lint:** ruff, mypy, formatting, toobig, validate and the other stages all pass.
- **`just check`:** it stops at the symvision stage, which fails on clean master HEAD (307872298) with 26 unused symbols in `sdd`, `ace/tui`, `service` and `completion`.
- **Scoped tests:** the full scoped lane had 4 failures. The same 4 fail with my changes stashed:
  - two in `test_capacity_gate_to_admission`
  - `test_contract_manifest_matches_marker_selection`
  - `test_changed_query_incomplete_load_after_reconcile_rearms`
- **Existing beads:** sase-13s, 13q/13o, 13n and 13m already track these. I added one +1 to sase-13s, noting that `coherent` in `src/sase/completion/runtime_cache_generation.py` is flagged too.
- **Not run:** I didn't replay the `research.a.cdx` incident itself, and the still-wedged agent needs the manual cleanup from the plan's operator-action section.

A leaked process that had already reparented away from the provider before the watchdog fired is out of reach of the `ppid` walk.
