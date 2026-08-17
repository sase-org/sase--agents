# Chat History - ace-run (toobig-2w.split_file.tests.test_notification_toast_polling.0)

- **TIMESTAMP:** 2026-08-16 22:53:19 EDT
- **MODEL:** claude/opus
- **AGENT:** toobig-2w.split_file.tests.test_notification_toast_polling.0
- **PROMPT:** `~/.sase/multi_prompts/202608/sase_org_sase-multiprompt-260816_201801.md`

## Prompt

#gh:sase-org/sase
%id(split_file.tests.test_notification_toast_polling.0, clan=toobig-2w)
%wait:toobig-2w.split_file.tests.test_bead.test_sync.0
%wait(runners=3)
%auto %wait(priority=20) Can you help me split the `tests/test_notification_toast_polling.py` file up into multiple files? Use your best
judgement, but let's aim to keep all files <=500 lines of code.

## Response

I'll start by looking at the file to understand its structure.

Let me check how recent test splits were done in this repo to match the convention.

Now I'll create the split modules. Starting with the snooze and concurrency ones:

Now the agent-refresh module, which gathers the notification→agent resolution tests:

Now the trimmed original module:

Test set matches exactly (32 tests, side-by-side diff shows no differences). Now installing and running the checks:

All 33 tests pass (32 functions, one parametrized ×2). Now the full lint + scoped test gate:

`just check` is green. Here's the split:

| File | Lines | Concern |
|---|---|---|
| `tests/test_notification_toast_polling.py` | 296 | `TestPollingDelta` (toast/bell/indicator delta), `TestRefreshNotificationCount`, `TestCompletionRaceOrder` — all unread/indicator projection from a store read |
| `tests/test_notification_toast_polling_agent_refresh.py` | 290 | `TestDisappearedReviewRefresh` (moved out of `TestPollingDelta`) + `TestNotificationAgentTargeting` — resolving a notification to an agent row and scheduling exact vs. broad refreshes |
| `tests/test_notification_toast_polling_snooze.py` | 176 | `TestSnoozeExpiry` |
| `tests/test_notification_toast_polling_concurrency.py` | 123 | `TestRingTmuxBellNonBlocking` + `TestNotificationSnapshotSingleFlight` — the poll must not block the event loop or double-parse the store |

Names follow the sibling `test_notification_toast*.py` convention already in `tests/`.

All 32 test functions carry over unchanged — none added, removed, or renamed; only their containing module changed, plus one new class name (`TestDisappearedReviewRefresh`) for the three disappeared-review tests that moved out of `TestPollingDelta`. Three cleanups came with the move, matching the precedent in the recent split commits: the function-local `from datetime import timedelta`, `find_agent_for_notification`, and `request_notification_agents_refresh` imports are now module-level, and each module imports only what it uses.

Verification: the four modules run 33 tests (one parametrized ×2) and all pass; `just check` passes every lint gate including symvision and toobig.

I did not commit — let me know if you want that.

The four split files are mine from this session. Committing now.

Committed as `fd60739c5`; the working tree is clean and `master` is level with `origin/master`.

**The split** — `tests/test_notification_toast_polling.py` went from 848 lines to four modules, all well under 500:

| File | Lines | Concern |
|---|---|---|
| `tests/test_notification_toast_polling.py` | 296 | `TestPollingDelta`, `TestRefreshNotificationCount`, `TestCompletionRaceOrder` — unread/indicator projection from a store read |
| `tests/test_notification_toast_polling_agent_refresh.py` | 290 | `TestDisappearedReviewRefresh` + `TestNotificationAgentTargeting` — resolving a notification to an agent row and scheduling exact vs. broad refreshes |
| `tests/test_notification_toast_polling_snooze.py` | 176 | `TestSnoozeExpiry` |
| `tests/test_notification_toast_polling_concurrency.py` | 123 | `TestRingTmuxBellNonBlocking` + `TestNotificationSnapshotSingleFlight` |

All 32 test functions carried over unchanged — none added, removed, or renamed. The one new class name, `TestDisappearedReviewRefresh`, holds the three disappeared-review tests that moved out of `TestPollingDelta`. Function-local imports (`timedelta`, `find_agent_for_notification`, `request_notification_agents_refresh`) were hoisted to module level, matching the recent split commits.

Verified before committing: the four modules run 33 tests (one is parametrized ×2) and all pass, and `just check` was green across every lint gate. The commit's `just fix` pre-hook made no further changes.

One note that isn't about this commit: the push warned that the project has 7 quarantined agent-hood publication requests, so the link recorded on this commit may not resolve until someone runs `sase agent sync --retry-quarantined`. I left that alone since it predates this work.
