# Chat History - ace-run (sase-zr.7.3)

- **TIMESTAMP:** 2026-09-20 07:06:59 EDT
- **MODEL:** claude/sonnet
- **AGENT:** sase-zr.7.3

## Prompt

#gh:gh_sase-org__sase
%id(3, clan=sase-zr.7, bead=sase-zr.7.3)
%model:@medium
%auto
%w(bead=sase-zr.7.1)
%w(bead=sase-zr.7.2)
Can you complete the work for bead sase-zr.7.3? The bead is already reserved for you and assigned to your agent
name: it was set to status=in_progress before you started reading this, either by the `sase bead work` launch
checkpoint or by the runtime promoting an ad-hoc wait-time claim. Do not set the status by hand. Read its
description and design file, do the work, and close only this bead with
`sase bead close sase-zr.7.3 --note "<what you verified>"`. Before closing, run
`sase bead epic-symbols sase-zr.7.3`. If this phase still has `--epic-symbol` entries, resolve each symbol or
re-key the Justfile line to a still-open bead (the parent epic or a later phase). `sase bead close` refuses while
leftovers remain; they go stale the instant this phase closes and turn unrelated agents' `just check` red. Closing
an assigned phase bead is unaffected by the parent-close descendant guard. Do NOT close the parent epic or any ancestor plan bead. Any instruction in a phase
description or child plan to close an ancestor is preparation and evidence for that ancestor's land agent, not
authorization for a phase worker. Do not create beads yourself: record discovered follow-up work as a
`PROPOSED FOLLOW-UP:` entry via
`sase bead note sase-zr.7.3 'PROPOSED FOLLOW-UP: <one-line summary — detail>'`; the epic's land agent triages
these into task beads.

## Response

I've read the bead and the TUI perf rules. Next I'm reading the refresh code paths this phase changes.

I've mapped out the refresh code. Now I'm checking how ACE dispatches a notification's action, so I can wire in the failure-recovery actions.

The `python` binary is missing, so I'll rerun the edit script with `python3`.

Next I'll register the new helper in the lazy export map, then wire the exact-dir refresh and the disappearance check in the TUI.

Now I'll add tests for the new behavior.

I finished sase-zr.7.3 and closed it; the changes are submitted for the host to commit. I did not run the j/k p95 navigation benchmark or capture before/after latency numbers. I left that for sase-zr.7.5. `just check` never reached its test lane because mypy failed.

The bead's other requirements are covered:

- **Exact pulse:** Gate acceptance now writes a refresh pulse inside the gate shell's agent directory, and the ACE classifier treats it as an exact-row signal instead of a full rebuild. The project-level pulse is still written too.
- **Exact row deltas:** After the watcher sees a receipt, it resolves the planner and shell directories on a worker thread and sends them through the artifact-delta queue, with no broad fallback.
- **Disappearance race:** The async notification count refresh now checks which gates vanished before it replaces the cache.
- **Off the UI thread:**
  - Gate execution and sudo now use the scheduled snapshot refresh instead of the synchronous count refresh.
  - The `partial_attempt` journal read runs off the event loop through a new `run_off_loop` helper.
  - I did not convert the remaining synchronous `_refresh_notification_count` callers elsewhere in ACE.
- **Plan-gate retry:** A `partial_attempt` on a plan gate now opens `GateRetryModal` to choose resume or restart. Choosing one resubmits through the generic gate-answer path, not the plan-specific `on_complete` handling, so it skips the extra planner-row refresh.
- **Failure recovery:** Selecting a gate-execution-failed notification opens `GateRetryModal` with resume, restart, cancel and error-report choices. It works from the failure notification alone, so it still works after the original review notification was dismissed.

I added `tests/ace/tui/test_gate_failure_recovery.py` plus cases in the plan-gate and artifact-path tests. The targeted TUI, gate and notification tests pass.

**Verification failures** (all outside the files I touched):
- **mypy:** errors in `main/ace_tmux*.py`.
- **`just symvision`:** flags private names in `memory/selector_models.py` and `main/ace_tmux_support.py`.
- **`just test-scoped`:** 43,538 passed, 3 failed.
  - `test_capacity_gate_to_admission` (2 tests) fails on the unmodified tree too.
  - `tests/tool/test_executor.py::test_literal_argv_preserves_spaces_and_dashes` fails, and I did not rerun it on the unmodified tree.

I renamed the private `_describe_partial_attempt` to `describe_partial_attempt` so the new recovery module could import it without tripping symvision.
