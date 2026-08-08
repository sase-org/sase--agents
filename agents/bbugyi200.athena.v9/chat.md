# Chat History - ace-run (v9)

- **TIMESTAMP:** 2026-08-07 20:21:05 EDT
- **MODEL:** claude/opus
- **AGENT:** v9

## Prompt

#gh:gh_sase-org__sase @~/.sase/plans/202608/suite_gate_bypass.md

The above plan has been reviewed and approved. Implement it now.

## Response

I'll start by reading the two files this plan changes.

Now implementing. First `tests/_suite_gate.py`:

Now the exemption helpers and the exported budget fit:

Now `tools/run_pytest`:

Now `tests/test_run_pytest_workers.py`:

Now the end-to-end regression in the integration suite:

The implementation is verified. Now filing the pre-existing test failures I found:

Implementation complete and verified.

## What changed

**`tests/_suite_gate.py`** — every held lease now marks its descendants with both `SASE_TEST_GATE_DISABLED=1` and `SASE_TEST_GATE_GOVERNED=1`. The `governed` constructor parameter and its branch are gone, since `configure_suite_gate()` was the only caller that wanted the ungoverned form and that was the gap. New public `descendant_exemption()` reports whether an ancestor's lease already paid for this demand (`SASE_TEST_GATE_GOVERNED` or `PYTEST_XDIST_WORKER` — deliberately *not* the bare disable flag); `_is_gate_exempt()` is re-expressed in terms of it and still honours the bare flag, because it is the in-pytest safety net. `_fit_request_to_budget` is now public `fit_request_to_budget`.

**`tools/run_pytest`** — `_parallel_worker_grant()` splits the two meanings. A corroborated exemption gets its width untouched with no tokens taken. An uncorroborated `SASE_TEST_GATE_DISABLED=1` still never waits and never takes tokens, but goes through `_bypass_worker_grant()`, which clamps to the host budget and prints one stderr line naming the width, the pool, and the `SASE_TEST_GATE_SLOTS` remedy. An exact over-budget ask raises the existing `UsageError`.

**Fixtures** — `isolate_run_pytest_environment` now clears `PYTEST_XDIST_WORKER` and `SASE_TEST_GATE_GOVERNED`. Without this every `tools/run_pytest` test would silently exercise the descendant-exemption shortcut, since the suite itself runs under a governed xdist lease.

## Verification

- All lint gates green (`fmt`, keep-sorted, ruff, mypy, pyscripts, changelog, symvision, toobig, SASE validation, committed plans).
- The test stage escalated to the governed full lane (`root-conftest`, `selection-tooling`), so the full suite ran: **27,278 passed, 25 skipped, 6 failed**. Those 6 are pre-existing on master — I confirmed by stashing the diff and re-running at `7bbd82a47`. `just check-full` would re-run exactly this same full lane plus the same lint gates, so I did not repeat it.
- By hand: the incident's own command now refuses — `SASE_TEST_GATE_DISABLED=1 SASE_PYTEST_WORKERS=64` → *"Requested 64 pytest worker tokens, but the computed host budget permits only 32."* A within-budget bypass prints the banner and runs. `pool.lock` reports `{"capacity": 32, "explicit": false}` after the governed full lane.

## The 6 pre-existing failures

Deterministic, not the flake class: `sase-h7.5`'s new fail-closed validator (`_validate_option_answerability`, `ff0b765a4`) rejects `sase-h7.9`'s own fixtures (`cce9e9e22`), which mark `input_schema` properties required without declaring them under `inputs`. Both phases belong to in-progress epic **sase-h7**, so per the bead policy I recorded it there as a `DISCOVERED ISSUE:` note rather than filing a duplicate task.

I also noted on epic **sase-h8** that its in-progress contention harness (`sase-h8.1`) is the caller this change breaks — it was the `-n 64` controller in the incident and must move to `SASE_TEST_GATE_SLOTS`. That is the plan's own stated risk, and h8.1 is being worked right now.

The changes from this session's implementation are all present. Committing them now.

Committed as `522c728d7`, working tree clean and level with `origin/master`.

## What landed

**`tests/_suite_gate.py`** — every held lease now marks descendants with both `SASE_TEST_GATE_DISABLED=1` and `SASE_TEST_GATE_GOVERNED=1`. `configure_suite_gate()` was the one caller building an ungoverned lease, and that was the gap; with no live second value, the `governed` parameter and its branch are gone. New public `descendant_exemption()` reports whether an ancestor's lease already paid for this demand (`SASE_TEST_GATE_GOVERNED` or `PYTEST_XDIST_WORKER` — deliberately not the bare disable flag). `_is_gate_exempt()` is re-expressed in terms of it and still honours the bare flag, since the in-pytest gate is a safety net. `_fit_request_to_budget` is now public `fit_request_to_budget`.

**`tools/run_pytest`** — `_parallel_worker_grant()` splits the two meanings of the disable flag. A corroborated exemption keeps its width untouched with no tokens taken. An uncorroborated bypass still never waits and never takes tokens, but goes through `_bypass_worker_grant()`, which clamps to the host budget and prints one stderr line naming the width, the pool, and the `SASE_TEST_GATE_SLOTS` remedy. An exact over-budget ask raises the existing `UsageError`.

**Fixtures** — `isolate_run_pytest_environment` clears `PYTEST_XDIST_WORKER` and `SASE_TEST_GATE_GOVERNED`, without which every `tools/run_pytest` test would silently take the descendant-exemption shortcut, because the suite itself runs under a governed xdist lease.

Docs for both variables in `docs/configuration.md` and `docs/development.md` were updated to describe bounded-bypass behaviour and the `SASE_TEST_GATE_SLOTS` route.

## Verification

Verified before this commit pass: all lint gates green; the test stage escalated to the governed full lane and ran the full suite (27,278 passed, 25 skipped, 6 failed). Those 6 failures are pre-existing on master — confirmed by stashing the diff and re-running at `7bbd82a47`. They are `sase-h7.5`'s fail-closed validator rejecting `sase-h7.9`'s fixtures; both phases belong to in-progress epic **sase-h7**, so it was recorded there as a `DISCOVERED ISSUE:` note. The incident's own command now refuses by hand: `SASE_TEST_GATE_DISABLED=1 SASE_PYTEST_WORKERS=64` against a 32-token budget raises the `UsageError`. The commit's own `just fix` hook ran clean.

## One flag

The commit carries a `BREAKING CHANGE:` footer. `sase-h8.1`'s in-progress contention harness was the `-n 64` controller in the incident and relies on the unbounded form — it must move to `SASE_TEST_GATE_SLOTS`. That is the plan's stated risk, and it is noted on epic **sase-h8**.

Prompt-archive publication was deferred (`agents sync lock is busy`) and one quarantined publication request already existed for this project; the primary commit and push both succeeded. Clearing it needs `sase agent sync --retry-quarantined`, which I did not run.
