# Chat History - ace-run (toobig-3l.split_file.tests.monitor.test_monitor_supervise.0)

- **TIMESTAMP:** 2026-08-23 12:32:00 EDT
- **MODEL:** grok/grok-4.6
- **AGENT:** toobig-3l.split_file.tests.monitor.test_monitor_supervise.0
- **PROMPT:** `~/.sase/multi_prompts/202608/sase_org_sase-multiprompt-260823_120159.md`

## Prompt

#gh:sase-org/sase
%id(split_file.tests.monitor.test_monitor_supervise.0, clan=toobig-3l)
%model:@medium
%wait:toobig-3l.split_file.tests.ace.tui.test_statistics_pane_interactions.0
%wait(runners=3)
%auto %wait(priority=20) Can you help me split the `tests/monitor/test_monitor_supervise.py` file up into multiple files? Use your best
judgement, but let's aim to keep all files <=500 lines of code.

## Response

I'll start by inspecting the test file's size and structure so I can split it into focused modules that stay under 500 lines.

The file is 752 lines. Next I’ll map its test classes and compare with how other monitor tests were already split.

I’ll extract shared helpers, then split the tests into core settlement, follow-up claims, and timeout/process-tree files.

I'll switch the test modules to `pytest_plugins` so the shared autouse fixtures load without dummy imports.

`pytest_plugins` would register those autouse fixtures globally, so I’ll import them in each test module instead.

`just check` failed on an unrelated mypy error. I’ll confirm it isn’t from this split before deciding how to handle it.

Split `tests/monitor/test_monitor_supervise.py` (752 lines, 25 tests) along the same sibling-module pattern as the start/store tests. Shared setup lives in a helper; each test file stays well under 500 lines.

| File | Role | Lines | Tests |
|---|---|---|---|
| `tests/monitor/_supervise.py` | Shared member factory, supervisor subprocess driver, autouse fixtures | 178 | — |
| `tests/monitor/test_monitor_supervise.py` | Spawn, completion, settlement, launch barrier, env scrub | 215 | 8 |
| `tests/monitor/test_monitor_supervise_followup.py` | Follow-up launch and workspace-claim behavior | 126 | 4 |
| `tests/monitor/test_monitor_supervise_timeout.py` | Timeouts, idle, process-group kill, SIGTERM, pgid | 299 | 13 |

All 25 original tests are preserved. The live flake-baseline node for `test_run_supervisor_kills_the_whole_process_group_on_timeout` now points at the timeout module; historical `# fixed-at:` comments keep the old node IDs so prior evidence still retires.

Verification: ruff, keep-sorted, test-wait helpers, and toobig passed; `just test-scoped` passed 595 tests, including all 25 supervise tests. `just check` still fails at mypy on an unrelated `wait_watch` export mismatch (`is_terminal_state` vs `_is_terminal_state`). That is already tracked as ready task **sase-sg**; I added an independent +1 rather than changing that code.
