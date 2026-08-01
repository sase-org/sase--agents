# Chat History - ace-run (sase-da.4)

- **TIMESTAMP:** 2026-08-01 10:26:11 EDT
- **MODEL:** codex/gpt-5.5
- **AGENT:** sase-da.4

## Prompt

#gh:gh_sase-org__sase
%id(4, clan=sase-da, bead=sase-da.4)
%model:@small_phase_worker
%auto
%w:sase-da.1
%w(bead=sase-da.1)
Can you complete the work for bead sase-da.4? The bead is already reserved for you and assigned to your agent
name: it was set to status=in_progress before you started reading this, either by the `sase bead work` launch
checkpoint or by the runtime promoting an ad-hoc wait-time claim. Do not set the status by hand. Read its
description and design file, do the work, and close the bead with
`sase bead close sase-da.4 --note "<what you verified>"`. Closing an assigned phase bead is unaffected by the
parent-close descendant guard. Do NOT close the parent epic. Do not create beads yourself: record discovered
follow-up work as a `PROPOSED FOLLOW-UP:` entry via
`sase bead note sase-da.4 'PROPOSED FOLLOW-UP: <one-line summary — detail>'`; the epic's land agent triages
these into task beads.

## Response

I'll start by reading the bead.

Now let me examine the target files.

Now wire it into the task launch path.

Now the epic path:

All five pass. Now the full check:

Pre-existing on clean master. Running the remaining check stages:

Now the full test suite plus the remaining lint/format stages:

Phase `sase-da.4` (launch_retry) is complete and the bead is closed.

**What landed**

- **`src/sase/bead/_store_contention.py`** (new) — treats a core `lock_timeout` as its own retryable condition. Because the Rust core takes the mutation lock *before* it touches the store, an expiry means the mutation never ran, so retrying the whole call is safe; every other failure propagates untouched. It retries within a small budget (3 attempts, jittered backoff), prints a wait naming the holder read from `<beads_dir>/.bead-mutation-lock.holder` (the file phase `store_lock` added), and on exhaustion raises `BeadStoreContentionError` naming the holder plus the exact `sase bead work <id>` resume command instead of an opaque exit 1.
- **`cli_work_task.py`** — task preclaim (`proj.update`) goes through the retry. A contended preclaim never reaches the store, so an exhausted budget leaves the task exactly as found; nothing to roll back.
- **`cli_work_handler.py`** — epic `mark_ready_to_work` and `preclaim_epic_work` go through the retry; `BeadStoreContentionError` joins the existing `except` clauses so the preclaim path still runs `rollback_work_launch` and restores `is_ready_to_work`.
- **`claims.py`** — dropped its private duplicate classifier in favor of the shared one.
- **`tests/test_bead/test_cli_work_store_contention.py`** (7 tests) — retry succeeds after one simulated expiry; exhausted task budget leaves `status=ready`/unassigned and reports holder + resume command with no checkpoint or spawn; exhausted epic budget rolls back the ready flag with phases untouched; non-lock failures aren't retried; unreadable/malformed holder metadata degrades gracefully.

**Verification:** `just fmt`, ruff, mypy, keep-sorted, and symvision are clean. `just test`: 25242 passed, 7 skipped, with one failure — `tests/ace/tui/test_agent_metadata_search.py::test_inline_metadata_search_commit_repeat_q_and_passthrough`, which passes in isolation and is unrelated to these files. `just check` also can't complete because `_lint-pyscripts` fails identically on clean master (`tools/sase_bead` Rule 2 violation). Both are recorded as `PROPOSED FOLLOW-UP:` notes on the bead rather than filed as beads.

Bead is closed. Committing now.

Committed and pushed.

- **Bead `sase-da.4`** was already closed (2026-08-01T14:24:32Z, resolution `done`) — the commit run confirmed it as "Already closed".
- **Commit:** `feat(bead): retry bead-work preclaims on store-lock contention`, staging exactly the five listed files (including the two untracked ones). The `just fix` pre-commit hook ran and `create_commit` succeeded.
- **`git status --short --branch`** shows `## master...origin/master` — working tree clean, not ahead of upstream.

One non-blocking note from the commit output: agent-hood publication was deferred because the agents sync lock was busy; it's queued and retries automatically. The primary commit and push were unaffected.
