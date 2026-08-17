# Chat History - ace-run (sase-ng.1.2)

- **TIMESTAMP:** 2026-08-17 15:43:07 EDT
- **MODEL:** grok/grok-4.6
- **AGENT:** sase-ng.1.2

## Prompt

#gh:gh_sase-org__sase
%id(2, clan=sase-ng.1, bead=sase-ng.1.2)
%model:@small
%auto
Can you complete the work for bead sase-ng.1.2? The bead is already reserved for you and assigned to your agent
name: it was set to status=in_progress before you started reading this, either by the `sase bead work` launch
checkpoint or by the runtime promoting an ad-hoc wait-time claim. Do not set the status by hand. Read its
description and design file, do the work, and close only this bead with
`sase bead close sase-ng.1.2 --note "<what you verified>"`. Before closing, run
`sase bead epic-symbols sase-ng.1.2`. If this phase still has `--epic-symbol` entries, resolve each symbol or
re-key the Justfile line to a still-open bead (the parent epic or a later phase). `sase bead close` refuses while
leftovers remain; they go stale the instant this phase closes and turn unrelated agents' `just check` red. Closing
an assigned phase bead is unaffected by the parent-close descendant guard. Do NOT close the parent epic or any ancestor plan bead. Any instruction in a phase
description or child plan to close an ancestor is preparation and evidence for that ancestor's land agent, not
authorization for a phase worker. Do not create beads yourself: record discovered follow-up work as a
`PROPOSED FOLLOW-UP:` entry via
`sase bead note sase-ng.1.2 'PROPOSED FOLLOW-UP: <one-line summary — detail>'`; the epic's land agent triages
these into task beads.

## Response

I'll start by reading the bead description, the beads memory, and the skills I need to complete `sase-ng.1.2` without touching parent status.

The bead is the MRU and unresolved-reference feedback move. Next I’ll read the plan, parent epic, and current launch-path code.

The plan is truncated at the feedback section. I'll read that part of the design and locate the current MRU and toast code.

The feedback phase is two durable-path moves: record VCS-xprompt MRU after a successful launch, and put unresolved-reference warnings into the launch result payload. I'll inspect the current launch and toast code next.

I have the implementation path. Next I’ll check epic-symbol wiring and a few test helpers, then start the code changes.

I'll implement the durable-path MRU recording and the unresolved-reference toast payload next, then add tests at that seam.

Next I’ll install the workspace and run `just check` to verify the durable-path changes.

Install finished. I’ll run the new tests first, then the full `just check` gate.

The prefix helper follows the orphaned path: first matching pattern, not first tag in the query. I’ll correct that test.

Targeted tests passed. Next I’ll run `just check` for the whole-repo lint gates and scoped tests.

Mypy is flagging a `payload` redefinition. I’ll rename the result payload so it doesn’t collide.

Those two force-reuse failures may be pre-existing. I’ll confirm against the original `launch_query` before deciding whether to touch them.

Those two force-reuse tests fail on the pre-change tree as well. I’ll record that as a proposed follow-up, then check epic-symbols and close this phase.

`sase-ng.1.2` is closed. VCS-xprompt MRU recording and the unresolved-`#ref` warning toast now live on the durable `sase run` path, so `<ctrl+p>` cycling and ACE’s unknown-ref toast keep working after the orphaned in-process launch body is deleted.

**MRU.** After a successful `launch_query()`, the leading `get_ref_patterns()` match is handed to `record_vcs_xprompt_usage()`. A plain prompt records nothing, `#git:home` is not persisted, an explicit `#gh:sase` is recorded once, and a failed spawn records nothing.

**Toast.** `scan_query_for_unresolved_references()` still prints each warning to the proc log. On success, `format_unresolved_references_toast()` is also placed on the `emit_run_launch_result()` payload as `warning_messages`. `_launch_outcome_from_completion()` reads that key into `LaunchProcOutcome`, and `_on_launch_proc_complete()` still surfaces those as warning toasts.

**Verified.** Lint (fmt, ruff, mypy, symvision) passed. New coverage is in `tests/test_launch_query_feedback.py` plus payload-fed toast tests in `tests/ace/tui/test_agent_launch_non_blocking.py`. Scoped `just check` ran 1663 passing tests.

**Not closed:** parent epic `sase-ng.1`. No `--epic-symbol` leftovers.

**Proposed follow-up** (on this bead for the land agent): two unauthorized-path tests in `tests/test_force_reuse_launch_seam.py` over-specify `launch_agents_from_cwd(..., segment_extra_env=None)`. Production only passes that kwarg when a force-reuse plan produced envs. Those two failures reproduce with this phase stashed; `sase-ng.1.1` likely owns the assertion.

I'll close the bead (that publish step is the verification), then commit the uncommitted launch-feedback changes with the git-commit skill. First I'm reading the close/commit workflow and checking the current tree.

The bead is closed locally; I’ll publish that close, then inspect the diffs and commit the launch-feedback work.

The close command is still running; I’ll wait for it to finish so I can confirm the publish before committing.

The close published (already closed, note added). I’ll write the commit message and commit the durable-path MRU and toast changes.

The commit is still running; I’ll wait for it to finish.

Commit succeeded. Next I’ll confirm the tree is clean and the branch is not ahead of upstream.

Published the `sase-ng.1.2` close and committed the durable-path launch feedback.

**Bead.** `sase bead close sase-ng.1.2` exited 0 as already closed and appended the verification note. No unpublished-close diagnostic.

**Commit.** `97f5b6f03` — `feat(launch): record VCS xprompt MRU and unresolved-ref toasts on durable sase run`

- After a successful `launch_query()`, record the leading VCS xprompt prefix for `<ctrl+p>` cycling.
- Put unresolved `#ref` warnings on the `RUN_LAUNCH` result payload so ACE still toasts them from the child process.
- Tests in `tests/test_launch_query_feedback.py` and `tests/ace/tui/test_agent_launch_non_blocking.py`.

Working tree is clean and `master` matches `origin/master`. Parent epic `sase-ng.1` was not closed. The stitch warning about 19 quarantined agent-hood publication requests is unrelated to this commit.
