# Chat History - ace-run (sase-ng.1.4)

- **TIMESTAMP:** 2026-08-17 17:08:08 EDT
- **MODEL:** grok/grok-4.6
- **AGENT:** sase-ng.1.4

## Prompt

#gh:gh_sase-org__sase
%id(4, clan=sase-ng.1, bead=sase-ng.1.4)
%model:@medium
%auto
%w:sase-ng.1.1,sase-ng.1.2
%w(bead=sase-ng.1.1)
%w(bead=sase-ng.1.2)
Can you complete the work for bead sase-ng.1.4? The bead is already reserved for you and assigned to your agent
name: it was set to status=in_progress before you started reading this, either by the `sase bead work` launch
checkpoint or by the runtime promoting an ad-hoc wait-time claim. Do not set the status by hand. Read its
description and design file, do the work, and close only this bead with
`sase bead close sase-ng.1.4 --note "<what you verified>"`. Before closing, run
`sase bead epic-symbols sase-ng.1.4`. If this phase still has `--epic-symbol` entries, resolve each symbol or
re-key the Justfile line to a still-open bead (the parent epic or a later phase). `sase bead close` refuses while
leftovers remain; they go stale the instant this phase closes and turn unrelated agents' `just check` red. Closing
an assigned phase bead is unaffected by the parent-close descendant guard. Do NOT close the parent epic or any ancestor plan bead. Any instruction in a phase
description or child plan to close an ancestor is preparation and evidence for that ancestor's land agent, not
authorization for a phase worker. Do not create beads yourself: record discovered follow-up work as a
`PROPOSED FOLLOW-UP:` entry via
`sase bead note sase-ng.1.4 'PROPOSED FOLLOW-UP: <one-line summary — detail>'`; the epic's land agent triages
these into task beads.

## Response

I'll start by reading the bead, its design, and the relevant SASE skills so I can complete only `sase-ng.1.4`.

The bead is in progress. Next I’ll read the plan, bead memory, and the code this phase is supposed to delete.

I have the phase scope: delete the in-process launch body and fan-out dispatchers, then re-point tests at the durable path. Exploring the current code next.

I'll map every production and test reference to the launch body, fan-out mixins, and `proc_callable` before deleting anything.

The deletion set is clear. Next I’ll read the launch modules and the tests that need to be trimmed rather than deleted.

I need the force-reuse replacement tests and the submit-handler files that still invoke the discarded callable.

I’ll check remaining production callers of the fan-out mixins and how other tests record launch submissions.

I have the replacement coverage and the deletion list. Implementing the source deletions and test re-points next.

Install finished. Next I’ll run the launch-path tests and the unused-symbol lint so leftover orphans can be re-keyed before `just check`.

Targeted tests passed. Symvision flagged expected second-order orphans; I’ll inspect each and re-key the ones this phase is supposed to leave for `support_retire`.

I’ll privatize the launch-outcome helpers that now live only in one file, and whitelist the support-module orphans on `sase-ng.1.5`.

Unused-symbol lint is clean. Next I’ll run `just check` for the whole-repo gates and the scoped test lane.

`just check` passed, but the scoped lane escalated. I’ll inspect that report and then decide whether `just check-full` still needs a monitor.

`just check` passed after escalating to the full suite. I’ll confirm this phase has no leftover `--epic-symbol` entries, then close the bead.

Closed **sase-ng.1.4**. ACE launch now has only the durable `sase run` path: the in-process launch body, fan-out dispatchers, and `proc_callable` seam are gone.

**Production**
- Deleted `_launch_body.py`, `_launch_body_impl.py`, `_launch_body_single.py`, `_launch_bulk.py`, `_launch_multi_prompt.py`, `_launch_multi_model.py`, and `_launch_repeat.py`.
- Dropped those mixins from `AgentLaunchMixin`.
- Removed `proc_callable` from `_submit_launch_proc` and from `_launch_resolved_prompt`.
- Privatized `_LaunchProcOutcome` / `_launch_results_tuple` and deleted unused `with_warning_messages`. Completion tests now assert on the dict result payload.

**Tests**
- Deleted files that only exercised the discarded callable (dispatch, fan-out, repeat, stack-body integration, and `agent_launch_vcs/`).
- Moved the live `resolve_ref_from_prompt()` unit test to `tests/ace/tui/test_resolve_ref_from_prompt.py`.
- Re-pointed prompt-submit / input-collection tests at the recorded `prompt` and `extra_payload`.
- Deleted the seven in-process force-reuse tests only after confirming the same behavior on `tests/agent/test_force_reuse_launch.py` and `tests/test_force_reuse_launch_seam.py`. Kept the raw-prompt submit test.

**Handoff to sase-ng.1.5**
Re-keyed leftover support-module orphans on that still-open phase: `_launch_history` recorders, `strip_all_vcs_refs`, and `strip_known_project_vcs_refs`. This phase has no `--epic-symbol` leftovers.

**Verified**
`just install`, targeted launch/submit tests, `just _lint-symvision`, and `just check` (scoped lane escalated to the full suite and passed). Parent epic `sase-ng.1` was left open.

The prior pass already implemented the phase; this turn is the commit finalizer. I'll verify the working tree, re-close the bead so the close is published, then commit.

The phase work is already on disk and the bead is closed locally. Next I’ll check leftover epic symbols, re-run close so the publish is verified, then commit.

The close command is still running; I’ll wait for it to finish before committing.

Close published successfully. Writing the commit message and committing the launch-body retirement.

The commit hit a rebase conflict in `Justfile`. I’ll resolve it, continue the rebase, then resume the stitch.

Upstream dropped the glossary exemptions; I’ll keep our `sase-ng.1.5` leftovers and not restore the retired `sase-op` symbols.

Rebase is clean. Resuming the stitch so the commit is pushed and recorded.

Closed **sase-ng.1.4** and committed the launch-body retirement.

**Close.** `sase bead epic-symbols` reported no leftovers. `sase bead close` published the already-closed bead (exit 0) and attached the verification note.

**Commit.** `0f7d86a66` — `refactor(tui): retire in-process launch body and fan-out dispatchers` — is on `origin/master`. The working tree is clean and in sync.

The stitch rebase conflicted on `Justfile` with the upstream glossary exemption retirement. Resolution kept the `sase-ng.1.5` leftover symbols and did not restore the retired `sase-op` exemptions.

Parent epic `sase-ng.1` was left open.
