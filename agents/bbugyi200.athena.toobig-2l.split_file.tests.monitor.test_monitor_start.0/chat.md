# Chat History - ace-run (toobig-2l.split_file.tests.monitor.test_monitor_start.0)

- **TIMESTAMP:** 2026-08-13 17:14:28 EDT
- **MODEL:** claude/opus
- **AGENT:** toobig-2l.split_file.tests.monitor.test_monitor_start.0
- **PROMPT:** `~/.sase/multi_prompts/202608/sase_org_sase-multiprompt-260813_135756.md`

## Prompt

#gh:sase-org/sase
%id:toobig-2l.split_file.tests.monitor.test_monitor_start.0
%clan(toobig-2l, tribe=chop, summary=[[[bold #D75FFF]◆ TOOBIG SPLIT · 2 FILES[/bold #D75FFF]
[bold #87D7FF]MISSION[/bold #87D7FF]
[dim #D7D7FF]Decompose oversized Python modules into focused, reviewable units[/dim #D7D7FF]
[dim #D7D7FF]without changing behavior.[/dim #D7D7FF]

[bold #87D7FF]TARGETS[/bold #87D7FF]
[#87D7FF]• 798  tests/monitor/test_monitor_store.py[/#87D7FF]
[#87D7FF]• 734  tests/monitor/test_monitor_start.py[/#87D7FF]

[dim #A8A8A8]2 scan roots · limits 1,000 / 850 / 700 lines · sequential queue[/dim #A8A8A8]]])
%wait(runners=3)
%auto %wait(priority=20) Can you help me split the `tests/monitor/test_monitor_start.py` file up into multiple files? Use your best
judgement, but let's aim to keep all files <=500 lines of code.

## Response

I'll start by looking at the file to understand its structure.

Now I'll add the shared polling helpers to the existing fixtures module:

Now the four new split files:

Now rewrite the original file to keep just the lifecycle tests:

All 17 tests preserved. Now let me install and run the suite:

All 119 monitor tests pass. Now the repo gate:

Done. `tests/monitor/test_monitor_start.py` (968 lines) is now five files, split by concern:

| File | Lines | Contents |
|---|---|---|
| `test_monitor_start.py` | 173 | Happy-path lifecycle: bare-lane promotion → completion, concurrent starts serialized in one lane |
| `test_monitor_start_supervisor.py` | 391 | Supervisor env scrubbing, diagnostics log, persisted identity, reparenting, ppid-walk survival, SIGHUP |
| `test_monitor_start_conflicts.py` | 221 | Duplicate-start handling: idempotent replay vs. the four rejection cases |
| `test_monitor_start_teardown.py` | 132 | Failure teardown: supervisor spawn failure, workspace-claim failure |
| `test_monitor_start_handoff.py` | 126 | Pending-marker write + `maybe_handoff_monitor_from_agent` |

Supporting changes:

- Moved the two polling helpers into `tests/monitor/_fixtures.py` as public `wait_for_done` / `wait_for_path` (plus `POLL_TIMEOUT`/`POLL_INTERVAL`), since they were needed by two of the new files. Bodies are verbatim, including the `sase-test-wait` pragma.
- The `/proc` ancestry helpers and `_python_command` stayed local to `test_monitor_start_supervisor.py` — only that file uses them.
- Each file carries its own `_sandbox_home` autouse fixture, matching what every other module in `tests/monitor/` already does.

Verification: all 17 original test functions are present, names unchanged (diffed against `HEAD`); `pytest tests/monitor/` is 119 passed. `just check` passed every lint gate — including `toobig` and the test-wait-helper gate — and the scoped test lane failed only on two pre-existing failures in `tests/ace/tui/widgets/test_prompt_panel_header.py`.

Those two failures reproduce on a clean stashed tree, so they aren't from this change. I didn't file a bead for them: this workspace is 3 commits behind `origin/master`, and pending commit `932277b26 refactor(ace): split detail-header summary into per-lane resolution and caching` rewrites the exact SASE CONTEXT lane code those tests assert on — so they're very likely already resolved upstream. Worth a `git pull` to confirm.

I made these changes — committing now.

The changes are mine. Writing the commit message:

Clean and pushed, and the stitch rebased onto the 3 upstream commits. Re-verifying the suite post-rebase:

Upstream introduced a broken import while I was rebasing. Verifying my own change first:

Confirmed: upstream commit `4d36d6d3d` re-added an import of a symbol that `c1970b5a0` had made private, so `import sase.llm_provider` now fails at master HEAD — every one of those 119 errors is that collection failure, not my change. Temporarily patching it locally so I can verify my split this turn:

119 passed. Reverting the temporary patch so the tree stays clean:

Working tree is clean and in sync with `origin/master`. Filing the upstream breakage as a task bead:

No duplicate and no causally linked epic. Creating the task:

Committed as `93e6df7ba` and pushed; working tree clean and in sync with `origin/master`.

**The split** — `tests/monitor/test_monitor_start.py` (968 lines) became five files, each well under 500 lines, with all 17 test functions preserved under their original names:

| File | Lines | Concern |
|---|---|---|
| `test_monitor_start.py` | 173 | Happy-path lifecycle: bare-lane promotion → completion, concurrent starts serialized into one lane |
| `test_monitor_start_supervisor.py` | 391 | Supervisor env scrubbing, diagnostics log, persisted identity, reparenting, ppid-walk survival, SIGHUP |
| `test_monitor_start_conflicts.py` | 221 | Duplicate-start handling: idempotent replay plus the four rejection cases |
| `test_monitor_start_teardown.py` | 132 | Failure teardown for supervisor spawn and workspace claim |
| `test_monitor_start_handoff.py` | 126 | Pending-marker write and `maybe_handoff_monitor_from_agent` |

The two polling helpers moved to `tests/monitor/_fixtures.py` as `wait_for_done`/`wait_for_path` (two modules need them); the `/proc` ancestry helpers stayed local to the supervisor module, their only caller.

**Verification** — `tests/monitor/` is 119 passed post-rebase. That required a workaround worth knowing about: the commit rebased onto 3 upstream commits, and one of them broke master. `import sase.llm_provider` now raises `ImportError` because `4d36d6d3d` ("normalize Grok tool-call stream artifacts") re-added `from ._subprocess_claude import stream_and_parse_messages_json_output` at `src/sase/llm_provider/_subprocess.py:12`, a symbol that `c1970b5a0` had renamed private. Neither commit is wrong alone — the merge is. It kills pytest collection repo-wide. I confirmed my 119 passed by temporarily aliasing the private name locally, then reverted that edit; it is not in the commit and the tree is clean.

Filed as ready task **`sase-lg`** with the repro, the blame evidence, and the fix options, plus a `RELATED:` note pointing at closed task `sase-ld` (whose fix is the other half of the collision — don't revert it, its symvision finding would return). The two `test_prompt_panel_header.py` failures I saw earlier are already tracked as `sase-le`, so I didn't duplicate them.
