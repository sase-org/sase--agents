# Chat History - ace-run (sase-vs.3)

- **TIMESTAMP:** 2026-08-30 08:42:36 EDT
- **MODEL:** claude/sonnet
- **AGENT:** sase-vs.3

## Prompt

#gh:gh_sase-org__sase
%id(3, clan=sase-vs, bead=sase-vs.3)
%model:@small
%auto
%w:sase-vs.1
%w(bead=sase-vs.1)
Can you complete the work for bead sase-vs.3? The bead is already reserved for you and assigned to your agent
name: it was set to status=in_progress before you started reading this, either by the `sase bead work` launch
checkpoint or by the runtime promoting an ad-hoc wait-time claim. Do not set the status by hand. Read its
description and design file, do the work, and close only this bead with
`sase bead close sase-vs.3 --note "<what you verified>"`. Before closing, run
`sase bead epic-symbols sase-vs.3`. If this phase still has `--epic-symbol` entries, resolve each symbol or
re-key the Justfile line to a still-open bead (the parent epic or a later phase). `sase bead close` refuses while
leftovers remain; they go stale the instant this phase closes and turn unrelated agents' `just check` red. Closing
an assigned phase bead is unaffected by the parent-close descendant guard. Do NOT close the parent epic or any ancestor plan bead. Any instruction in a phase
description or child plan to close an ancestor is preparation and evidence for that ancestor's land agent, not
authorization for a phase worker. Do not create beads yourself: record discovered follow-up work as a
`PROPOSED FOLLOW-UP:` entry via
`sase bead note sase-vs.3 'PROPOSED FOLLOW-UP: <one-line summary — detail>'`; the epic's land agent triages
these into task beads.

## Response

I'll start by reading the bead details for sase-vs.3.

Good, the parser exists already (from phase 1). Now let's look at the epic launch files.

Now `start_epic_launch_monitor`:

Now the `_submit_epic_launch_task` call within `start_epic_launch_monitor`, and the function itself:

Now `_epic_launch_command_pair`:

Good, those remaining diagnostics are pre-existing. Now let's update `finish_epic_launch`:

Now update `_raise_unclaimable_epic_launch`:

Now let's write tests. First check existing test structure and imports for `PromptWaitDirective`.

Good, that's the phase-1 test pattern for `render_multi_prompt`. Now let's add tests to `test_epic_launch.py` for `build_epic_launch_argv` with `wait_spec`:

Now let's add a test to `test_epic_launch_monitor.py` verifying `start_epic_launch_monitor` forwards `wait_spec`, and a dedup test confirming the matching still works with a wait-carrying argv.

Now add a dedup test showing a wait-carrying argv still matches an in-flight launch for the same plan:

Now let's add tests to `test_epic_launch_finish.py` for `finish_epic_launch` carrying the wait spec into the resume hint:

Confirmed those `.lane` warnings pre-exist (just shifted line numbers due to my new test insertion). Now let's add the actual test using `PromptWaitDirective` to `test_epic_launch_finish.py`.

Now let's add the direct `prepare_epic_launch` wait-spec tests. I'll insert them after `epic_launch_project` tests, before `test_headless_epic_submit_failure_keeps_durable_host_claim`.

Now insert the tests after `test_epic_launch_project_returns_none_without_project_identity`:

I'll wait for `just install` to finish in the background before re-running tests.

Now `format_wait_spec` has a real consumer (`build_epic_launch_argv`), so I should remove the stale `--epic-symbol "sase-vs.3(format_wait_spec)"` entry from the Justfile.

Now let's check on the `just install` background task and then run the full test/lint suite.

Now let me review the full diff so far before running tests.

This all looks correct and matches the plan precisely. Those diagnostics are pre-existing (confirmed earlier). Let me check if `just install` finished.

Rust build is still in progress (release build, can take a while). I'll wait for the background notification rather than poll.

I'll use `TaskOutput` with blocking to wait for the `just install` background task to finish.

`just install` finished successfully (exit 0). Now let's run the relevant tests.

All 61 tests pass. Now let's run `just check`.

I'll wait for this background `just check` run to finish (it escalates to the full test suite since the Justfile changed, so it may take a while).

`just check` passed with exit code 0 (full escalated suite included, since the Justfile changed). Let's peek at the log tail to confirm the full-suite summary line.

No leftover epic symbols. Let's do a final review of the full diff before closing.

This matches the phase scope exactly: `build_epic_launch_argv`, `start_epic_launch_monitor`, `prepare_epic_launch`, and every resume-hint call site now thread an optional `wait_spec`, with the stale symvision whitelist entry resolved and full test coverage. `just check` passed (including the escalated full suite). Now closing the bead.

Bead **sase-vs.3** is complete and closed.

Summary:
- Added `wait_spec: PromptWaitDirective | None = None` to `build_epic_launch_argv`, `start_epic_launch_monitor`, `_epic_launch_command_pair`, `_submit_epic_launch_task`, `prepare_epic_launch`, `_raise_unclaimable_epic_launch`, and `finish_epic_launch`, so a wait spec threads from `prepare_epic_launch` through the monitor into the `sase bead work --wait` argv, with every resume hint (unusable-store, monitor-start failure, unclaimable-project, and the CLI failure/success resume) reproducing it.
- Confirmed `_active_epic_launch_for_plan`/`_logical_epic_launch_argv` still dedupe a wait-carrying argv (they only inspect `argv[:4]`) and added a regression test.
- Resolved the stale `sase-vs.3(format_wait_spec)` symvision `--epic-symbol` whitelist entry in the Justfile now that `format_wait_spec` has a real caller.
- Added tests across `test_epic_launch.py`, `test_epic_launch_monitor.py`, `test_epic_launch_finish.py`, and `test_plan_approval_actions.py`.
- No existing caller passes a real spec yet (that's phase `gate_wait_input`/sase-vs.4); every new parameter defaults to `None`, keeping existing callers byte-identical.
- `just check` passed, including the full-suite escalation triggered by the Justfile change.
- Work committed via the SASE final declaration.
