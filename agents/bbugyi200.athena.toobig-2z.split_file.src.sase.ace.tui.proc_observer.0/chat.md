# Chat History - ace-run (toobig-2z.split_file.src.sase.ace.tui.proc_observer.0)

- **TIMESTAMP:** 2026-08-17 15:59:48 EDT
- **MODEL:** claude/opus
- **AGENT:** toobig-2z.split_file.src.sase.ace.tui.proc_observer.0
- **PROMPT:** `~/.sase/multi_prompts/202608/sase_org_sase-multiprompt-260817_152710.md`

## Prompt

#gh:sase-org/sase
%id:toobig-2z.split_file.src.sase.ace.tui.proc_observer.0
%clan(toobig-2z, tribe=chop, summary=[[[bold #D75FFF]◆ TOOBIG SPLIT · 4 FILES[/bold #D75FFF]
[bold #87D7FF]MISSION[/bold #87D7FF]
[dim #D7D7FF]Decompose oversized Python modules into focused, reviewable units[/dim #D7D7FF]
[dim #D7D7FF]without changing behavior.[/dim #D7D7FF]

[bold #87D7FF]TARGETS[/bold #87D7FF]
[#87D7FF]• 783  tests/test_llm_provider_usage_limit_config.py[/#87D7FF]
[#87D7FF]• 766  src/sase/ace/tui/proc_observer.py[/#87D7FF]
[#87D7FF]• 732  tests/test_axe_chop_bead_task_triage.py[/#87D7FF]
[#87D7FF]• 724  tests/ace/tui/test_proc_observer.py[/#87D7FF]

[dim #A8A8A8]2 scan roots · limits 1,000 / 850 / 700 lines · sequential queue[/dim #A8A8A8]]])
%wait(runners=3)
%auto %wait(priority=20) Can you help me split the `src/sase/ace/tui/proc_observer.py` file up into multiple files? Use your best
judgement, but let's aim to keep all files <=500 lines of code.

## Response

I'll start by looking at the file to understand its structure.

Now I'll create the split modules.

Now updating the tests that reference the moved private symbols.

Now let me apply the test updates.

Now the timezone test:

Now the tests:

Confirmed: the symvision failure is a pre-existing stale epic-symbol entry (`sase-oc.8`, a closed bead) in the Justfile — untouched by this change. Let me run the test lane, which `check` skipped.

While the scoped test lane runs, let me file a bead for the pre-existing symvision failure per repo policy.

Both a duplicate and an active-epic link apply here, so I'll record both rather than create a new task.

The scoped lane passed except two failures in an unrelated launch-seam test. Let me verify those are pre-existing.

Done. `src/sase/ace/tui/proc_observer.py` is split into four modules, all well under 500 lines:

| File | Lines | Contents |
|---|---|---|
| `proc_observer.py` | 356 | `ProcObserver` thread, `_snapshot_signature`, live-observer registry, `stop_orphaned_proc_observers`, re-exports |
| `_proc_observer_models.py` | 229 | `ObservedProc`, `ProcProjection`, `ProcCompletionRecord`, `ProcObserverSnapshot`, `compose_proc_projection`, monitor-row helpers |
| `_proc_observer_store.py` | 203 | durable-store reads: `store_proc_row`, `decode_completion`, `load_observer_context`, `live_session_ids`, log tails |
| `_proc_observer_log.py` | 102 | bounded presentation log: `ProcLogLine`, `ObservedProcLog` |

Design notes:

- **Import site unchanged.** Every existing `from ..proc_observer import X` in `src/` keeps working — `proc_observer.py` re-exports the full public surface. No src callers were touched.
- **Helper modules are `_`-prefixed siblings**, matching the existing `_agent_completion_*.py` / `_proc_action_*.py` convention in this tree.
- **Symbols shared across the new files had to go public** (symvision forbids cross-file private imports): `_ObservedProcLog`→`ObservedProcLog`, `_Watch`→`ProcWatch`, `_ObserverContext`→`ObserverContext`, `_store_proc_row`→`store_proc_row`, `_load_context`→`load_observer_context`, `_live_session_ids`→`live_session_ids`, `_is_relevant`→`proc_is_relevant`, `_decode_completion`→`decode_completion`. Symbols still used only within one file (`_ProcLogSnapshot`, `_read_log_tail`, `_local_datetime`, `_attribute_session_row`, `_snapshot_signature`) stayed private.
- Replaced the duplicated `_ACTIVE_STATUSES` membership checks with `proc_status_is_active()`, and the repeated `replace(projection, active_count=…, active_monitor_count=…)` with `recount_projection()`.
- Two test files were updated for the renames and for monkeypatch targets that moved modules (`_read_log_tail`, `read_operation_result`, and `local_now` now live in the store/log modules).

Verification: ruff, mypy, symvision (symbol analysis), toobig, keep-sorted, `sase validate`, and plan validation all pass. The scoped test lane ran 3236 tests — everything green except two failures I confirmed are pre-existing.

Two pre-existing failures found, neither caused by this change; both recorded per repo policy:

- **symvision gate is red on master** — stale `--epic-symbol "sase-oc.8(set_completion_summary)"` in the Justfile. Recorded as a `DISCOVERED ISSUE:` on in-progress epic `sase-oc` (its phase left it behind) and as a post-close `+1` on `sase-o7`. Worth flagging: `sase-oc.8`'s own landing commit contains `sase-o7`'s close-time refusal fix, yet it closed 5.5h later with the entry intact — so either the close took a path the refusal doesn't cover, or the worker's workspace venv had a pre-fix `sase` installed.
- **`tests/test_force_reuse_launch_seam.py`** — 2 tests assert `launch_agents_from_cwd(prompt, segment_extra_env=None)` but `_launch.py:112` only passes that kwarg when it is non-`None`. Filed as `sase-ot` (small, ready), reproduced on a stashed clean tree.

I'll commit the changes I made in this session.

These are the changes from this session's file split. Committing now.

Committed as `6ac274be5`; working tree is clean and `master` is in sync with `origin/master`.

**What landed:** `src/sase/ace/tui/proc_observer.py` split from ~870 lines into four modules, all under 500:

| File | Lines | Contents |
|---|---|---|
| `proc_observer.py` | 356 | `ProcObserver` thread, live-observer registry, `stop_orphaned_proc_observers`, re-exports |
| `_proc_observer_models.py` | 229 | `ObservedProc`, `ProcProjection`, `ProcCompletionRecord`, `ProcObserverSnapshot`, projection helpers |
| `_proc_observer_store.py` | 203 | durable-store reads and log tails |
| `_proc_observer_log.py` | 102 | bounded presentation log |

Every existing `from ..proc_observer import X` still resolves — the entry module re-exports the full public surface, and no `src/` callers changed. Two test files were updated for renames and relocated monkeypatch targets.

The `just fix` pre-commit hook ran clean. One note on the commit output: publication of the prompt archive link was deferred because the agents sync lock was busy, and this project already has 19 quarantined agent-hood publication requests. That is a pre-existing outbox backlog unrelated to this change — clearing it needs `sase agent sync --retry-quarantined`, which I did not run since it touches shared project state beyond this commit's scope.
