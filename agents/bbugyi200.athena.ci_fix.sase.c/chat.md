# Chat History - ace-run (ci_fix.sase.c)

- **TIMESTAMP:** 2026-08-06 22:10:56 EDT
- **MODEL:** claude/opus
- **AGENT:** ci_fix.sase.c

## Prompt

#gh:sase-org/sase
%id(ci_fix.sase.@, tribe=chop)
%wait(runners=0)
#pr(ci_fix_sase_b5872ca, status=ready)

GitHub Actions is failing for the sase-org/sase repo. Can you run the `actstat` command to get more information about
the failing jobs, diagnose the root cause of these failures, and then fix them?

Repair the current default-branch CI failure in sase-org/sase.

Pinned failing run: https://github.com/sase-org/sase/actions/runs/31130782239
Pinned failing commit: b5872ca
Failed jobs from the sweep:
- coverage-contexts
- test (3.13)

The pinned failure is on a settled commit older than the current unsettled HEAD
(5e6a94a3890d192dca6091d2165783381c8348e3). Re-verify these job failures against current state
before changing code.


First re-verify that this failure and commit are still current on the default branch.
If it was superseded or already fixed, leave the worktree unchanged and report that
outcome. Keep any fix narrowly scoped and run the relevant checks.

## Response

I'll start by re-verifying the pinned failure against current state.

CI is still failing on much newer commits. Let me look at the most recent settled failure.

Several distinct failures. Let me gather the failure signatures across the recent failed runs to see which are persistent.

The one deterministic failure across **all** runs is `test_notification_custom_gate.py::test_tracked_executor_reports_terminal_and_extra_commands_live` in `coverage-contexts` (broken pipe). Let me investigate.

The `commands/audit` script (`#!/bin/sh` + `printf`) never reads stdin and exits immediately — so the parent's stdin write gets EPIPE. Let me confirm the exact mechanism.

Confirmed: the buffered writer retains the unflushed bytes, so `close()` retries and raises `BrokenPipeError` a second time — uncaught, and `_run_owned_command`'s `except OSError` misreports it as `command_start_failed`. Let me check the other persistent failing job while I fix this.

`published-core-minimum-smoke` is a separate, out-of-scope issue (the published `sase_core_rs` 0.18.4 lags the new bindings — needs a sase-core release). Let me fix the in-scope root cause.

Now let me verify the fix reproduces/passes the failing test.

Passes locally — the race needs the child to exit first. Let me add a regression test that makes it deterministic, and confirm it catches the bug.

Now let me add the regression test.

Now verify the test actually catches the bug — run it against the reverted fix, then with the fix.

The regression test fails without the fix and passes with it. Now running the full check gate.

Pre-existing at HEAD, unrelated to my change (stale `--epic-symbol` entries for beads closed after those CI runs). Let me run the remaining test lane.

## Re-verification

The pinned failure was **not** superseded — CI is still failing on the default branch, on commits much newer than `b5872ca`. Every settled commit since is red, including current `HEAD` (`09bb443ea`).

## Root cause

Across all four recent failed runs, exactly one failure is **deterministic** — `coverage-contexts` fails it every time:

```
FAILED tests/ace/tui/test_notification_custom_gate.py::test_tracked_executor_reports_terminal_and_extra_commands_live
  _GateTaskOutcome(message='cannot start command: [Errno 32] Broken pipe', success=False)
```

In `src/sase/notification_gates/executor.py:489`, `_run_command_streaming` writes the gate's JSON input to the child's stdin. A gate command may legitimately exit without draining stdin (the test's `commands/audit` is `#!/bin/sh` + `printf`). The code already catches `BrokenPipeError` around `write`/`flush` — but the failed write stays in the `BufferedWriter`, so `process.stdin.close()` in the `finally` **retries it and raises EPIPE a second time**, uncaught. That propagates to `_run_owned_command`'s `except OSError`, which misreports a successful command as `command_start_failed`. I reproduced this exact double-raise in isolation.

It's a race — the child must exit before the parent writes — which is why it's deterministic under `coverage-contexts` (coverage slows the parent) and only occasional in the plain `test` jobs. The non-streaming path is unaffected because `subprocess.run` uses `communicate()`, which handles EPIPE internally.

## Fix

Made `close()` EPIPE-safe, matching what `communicate()` does, plus a regression test that forces the child to exit first via `on_process_state`. Verified the test **fails without the fix and passes with it**.

`just check`: fmt, keep-sorted, ruff, mypy, pyscripts, changelog all pass; `just test-scoped` — 2600 passed.

## Out of scope — two things I did not fix

1. **`just check`'s symvision gate fails at `HEAD` independently of my change** (confirmed by stashing). Beads `sase-gn.3` and `sase-gn.7` were closed after those CI runs, leaving stale `--epic-symbol` entries in the justfile that now demand symbol cleanup. This lint passed in CI at the pinned commit, so it is a new, separate breakage.

2. **`published-core-minimum-smoke`** fails because published `sase_core_rs` 0.18.4 is missing 6 bindings added recently in the sibling repo (`bead_snooze`, `classify_notification_tabs`, etc.). It needs a `sase-core` release plus a version bump — not fixable in this repo, and it wasn't in the pinned job list.

The remaining red tests (`test_contract_manifest` budget at 30.1/30.6s vs a 30s ceiling, `test_residual_freeze_soak`, `test_tasks_pane_selection`, `test_agent_metadata_search`) each appeared in only one run and differ run-to-run — flaky/borderline, not the persistent cause. I left them alone per the narrow-scope instruction; say the word if you'd like beads filed for those, the symvision drift, or the core release.

I made file changes only — no commit, branch, or PR.

All 27 tests pass. Committing now.

Committed and pushed. Working tree clean, branch in sync with upstream.

## What was wrong

The pinned failure was **not superseded** — CI was still red on the default branch at commits far newer than `b5872ca`, including `HEAD` (`09bb443ea`). Across the recent failed runs exactly one failure was deterministic, and `coverage-contexts` hit it every time:

```
FAILED tests/ace/tui/test_notification_custom_gate.py::test_tracked_executor_reports_terminal_and_extra_commands_live
  _GateTaskOutcome(message='cannot start command: [Errno 32] Broken pipe', success=False)
```

In `src/sase/notification_gates/executor.py:493`, `_run_command_streaming` writes the gate's JSON input to the child's stdin. A gate command may legitimately exit without draining stdin (the test's `commands/audit` is just `#!/bin/sh` + `printf`). The code already caught `BrokenPipeError` around the write — but the failed write stays buffered in the `BufferedWriter`, so `process.stdin.close()` in the `finally` retries it and raises EPIPE a **second** time, uncaught. That propagated to `_run_owned_command`'s `except OSError`, which misreported a command that had actually succeeded as `command_start_failed`.

It's a race requiring the child to exit before the parent writes — which is why coverage instrumentation (slower parent) made it deterministic while the plain `test` jobs only saw it occasionally. The non-streaming path is unaffected because `subprocess.run` uses `communicate()`, which swallows EPIPE internally.

## Fix

Made `close()` EPIPE-safe, matching `communicate()`'s behavior, plus a regression test that forces the ordering via `on_process_state`. Verified it fails without the fix and passes with it. 27 tests in the two gate suites pass.

## Left alone, deliberately

- **`published-core-minimum-smoke`** — published `sase_core_rs` 0.18.4 lacks 6 bindings added recently in the sibling repo (`bead_snooze`, `classify_notification_tabs`, …). Needs a `sase-core` release + version bump; not fixable here, and not in the pinned job list.
- **`just check`'s symvision gate fails at `HEAD` independently of this change** (confirmed by stashing). Beads `sase-gn.3` and `sase-gn.7` were closed after those CI runs, leaving stale `--epic-symbol` entries in the justfile. Separate, newer breakage.
- Four one-off red tests (`test_contract_manifest` at 30.1s vs a 30s ceiling, `test_residual_freeze_soak`, `test_tasks_pane_selection`, `test_agent_metadata_search`) each appeared in a single run and varied run-to-run — flaky, not the persistent cause.

Say the word if you want beads filed for the symvision drift, the core release, or the flaky tests.
