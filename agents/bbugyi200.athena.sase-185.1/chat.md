# Chat History - ace-run (sase-185.1)

- **TIMESTAMP:** 2026-09-24 16:02:51 EDT
- **MODEL:** claude/sonnet
- **AGENT:** sase-185.1

## Prompt

#gh:gh_sase-org__sase
%id(sase-185.1, bead=sase-185.1)
%clan(sase-185, tribe=epic, summary_script=sase_clan_summary_epic)
%model:@medium
%auto
Can you complete the work for bead sase-185.1? The bead is already reserved for you and assigned to your agent
name: it was set to status=in_progress before you started reading this, either by the `sase bead work` launch
checkpoint or by the runtime promoting an ad-hoc wait-time claim. Do not set the status by hand. Read its
description and design file with `sase bead read sase-185.1 -r "Need the phase scope and design file"`, do the work, and close only this bead with
`sase bead close sase-185.1 --note "<what you verified>"`. Before closing, run
`sase bead epic-symbols sase-185.1`. If this phase still has `--epic-symbol` entries, resolve each symbol or
re-key the Justfile line to a still-open bead (the parent epic or a later phase). `sase bead close` refuses while
leftovers remain; they go stale the instant this phase closes and turn unrelated agents' `just check` red. Closing
an assigned phase bead is unaffected by the parent-close descendant guard. Do NOT close the parent epic or any ancestor plan bead. Any instruction in a phase
description or child plan to close an ancestor is preparation and evidence for that ancestor's land agent, not
authorization for a phase worker. Do not create beads yourself: record discovered follow-up work as a
`PROPOSED FOLLOW-UP:` entry via
`sase bead note sase-185.1 'PROPOSED FOLLOW-UP: <one-line summary — detail>'`; the epic's land agent triages
these into task beads.

## Response

Read the plan and the TUI perf/lint notes. Next I'm reading the launch-submission code that this phase changes.

Still mapping the code: I've read the submission, barrier, record, and mount paths. Next are the proc observer's pending-row API and `agent_durable`.

Still reading the code. I'm confirming the pending status counts as active, then checking the quit flush and prompt recovery hooks.

Almost done reading the source files. The last thing to read is the existing barrier test file, since I'll be updating and extending it.

Now I'll write the new `_pending_launch.py` module.

Making steady progress: records, barrier, pending-launch module, and `,X` are done. Now the submission rewrite.

Both rewritten tests fail, so I'm looking at the actual errors.

Docs next: I'll add the pending-launch paragraph to the `,X` section of `docs/ace.md`.

Bead closed. The last step is the SASE final declaration.

Bead sase-185.1 is done and closed. Submitting from the prompt bar now removes the bar right away, and the launch carries on as a visible, cancellable pending launch. `just check` still can't go green here because the gates fail on a clean tree too (details below).

I ran `just test-scoped`, which escalated to the full suite: 46,592 passed and 33 failed. All 33 fail identically on a clean checkout, so none come from this change.

The lint gates for this change pass: ruff, formatting, feature flags, test waits, changelog, patch/stitch terminology, `just validate`, and committed-plan validation. Symvision reports no unused-symbol errors for the new code. `just check` stops at mypy on a clean tree, and symvision, toobig and pyscripts also fail there for reasons unrelated to this change. I recorded that as a `PROPOSED FOLLOW-UP` note on the bead.

- **Acceptance point:** `_submit_resolved_launch` snapshots the prompt into a new `PendingLaunch` (`_pending_launch.py`), unmounts the bar, and only then checks the relaunch-cleanup hold. The guards (`%hold`, provider) still run before it, as this phase specified.
- **Visibility:** the launch shows as a `launch <name>` proc row whose message names the wait. It also gets a new `PREPARING` launch record.
- **Hand-off:** at submit, the durable `sase run` proc replaces the row and the record picks up its proc ids.
- **Parked launches:** waiters are keyed by launch id instead of prompt session, so a parked launch replays from its own snapshot and never reads the prompt context.
- **`,X` on a pending launch:** it cancels the launch, drops the waiter, row and record, and restores the prompt in a bar under the same relaunch operation. A re-submit stays behind any open barrier.
- **Abort and quit:**
  - A rejected durable submit, or a bulk launch that resolves no Patch, restores the prompt into a bar or stashes it if a bar or modal is open.
  - Quitting stashes every still-pending prompt off the event loop, so `@` recovers it.
- **Off the UI thread:**
  - The submit-time MRU write now runs as a pump-free task.
  - Bulk Patch resolution runs in a non-exclusive thread worker and returns a typed per-Patch plan, with the UI thread submitting the procs.
  - Timestamp reservation stays on the UI thread, since it measures about 0.09 ms warm.
- **Trace and docs:** `launch.accepted` and `launch.submitted` trace events (with `accept_to_submit_ms` and the stages visited) are documented in `docs/perf_runbook.md`, and the `,X` behavior is in `docs/ace.md`.
- **Removed:** the `accepted_whole_bar_submit` flag, which the immediate unmount made dead.
- **Tests:** the new `tests/ace/tui/test_pending_launch.py` has 17 tests, and I rewrote the two barrier tests around `,X` and updated the records and observer tests.

I did not commit anything myself. The `sase_final` finalizer accepted the commit declaration and the host does the commit, with the bead action set to `keep` because I had already closed the bead.
