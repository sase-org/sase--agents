# Chat History - ace-run (sase-qd.1)

- **TIMESTAMP:** 2026-08-18 18:52:57 EDT
- **MODEL:** grok/grok-4.6
- **AGENT:** sase-qd.1

## Prompt

#gh:gh_sase-org__sase
%id(sase-qd.1, bead=sase-qd.1)
%clan(sase-qd, tribe=epic, summary_script=sase_clan_summary_epic)
%model:@medium
%auto
Can you complete the work for bead sase-qd.1? The bead is already reserved for you and assigned to your agent
name: it was set to status=in_progress before you started reading this, either by the `sase bead work` launch
checkpoint or by the runtime promoting an ad-hoc wait-time claim. Do not set the status by hand. Read its
description and design file, do the work, and close only this bead with
`sase bead close sase-qd.1 --note "<what you verified>"`. Before closing, run
`sase bead epic-symbols sase-qd.1`. If this phase still has `--epic-symbol` entries, resolve each symbol or
re-key the Justfile line to a still-open bead (the parent epic or a later phase). `sase bead close` refuses while
leftovers remain; they go stale the instant this phase closes and turn unrelated agents' `just check` red. Closing
an assigned phase bead is unaffected by the parent-close descendant guard. Do NOT close the parent epic or any ancestor plan bead. Any instruction in a phase
description or child plan to close an ancestor is preparation and evidence for that ancestor's land agent, not
authorization for a phase worker. Do not create beads yourself: record discovered follow-up work as a
`PROPOSED FOLLOW-UP:` entry via
`sase bead note sase-qd.1 'PROPOSED FOLLOW-UP: <one-line summary — detail>'`; the epic's land agent triages
these into task beads.

## Response

I'll start by reading the bead and beads memory so I can follow the assigned phase work without changing status by hand.

The phase is `core-set`: add `set_current_project()` and land `sase project set-current`. I'll read the plan and current-project code next.

The plan file was truncated before the core-set write-path details. I'll pull that section and inspect the existing current-project code.

I have the write-path design. Next I’ll inspect CLI parser/help tests, project-record fields, and how existing tests isolate the MRU.

I have the write-path design. Next I’ll add `set_current_project()`, the `set-current` CLI, tests, and the docs that still claim no set command exists.

Next I’ll install the workspace env, run the new tests, and regenerate the completion spec.

The new tests passed. I'll regenerate the completion snapshot and run the full `just check` gate.

The flag lint failure is about missing beads I didn’t touch. I’ll confirm it’s pre-existing and finish the rest of the check stages.

The escalated full suite passed. Next I’ll check leftover epic symbols and close only this phase bead.

`sase-qd.1` is closed. The current project now has a verified write path, and `sase project set-current` is its first consumer. The parent epic `sase-qd` is still open.

### Write path
`set_current_project()` in `sase.current_project` returns a `SetCurrentProjectOutcome` (`set` / `unchanged` / `ineligible` / `unverified`) and runs the five planned steps:

1. Resolve the target through the same alias map as the resolver (display name, alias, or directory key).
2. Require enabled + launchable, and take the workflow tag from `detect_workflow_type` on the ProjectSpec — not `vcs_kind` — so a mismatched prefix cannot be silently dropped.
3. If that project is already current, write nothing (MRU `st_mtime_ns` stays put).
4. Promote with one `record_vcs_xprompt_usage(f"#{workflow_type}:{project_key}")`.
5. Re-resolve and only claim success when the resolver agrees.

### CLI
`sase project set-current <project> [-j|--json]`:

- Exit 0 for `set` / `unchanged`, 1 for `ineligible` / `unverified`
- Human output prints `outcome.message`, then the same accented detail as `sase project current`
- `--json` is `{status, message, project}`

The old “there is no set command” claim is gone from parser help, `docs/cli.md`, `docs/ace.md`, and `docs/configuration.md`. The `sase_project` skill now documents `set-current`.

### Verified
- Unit tests for all four outcomes, including the provider-mismatch regression and the already-current mtime guard
- CLI help / parser / handler tests
- `sase bead epic-symbols sase-qd.1` — no leftovers
- Symvision clean (both new public symbols have real CLI consumers)
- `just test-scoped` escalated (`core-identity-changed`); full suite **33772 passed**, 13 skipped

`just check` as a whole still fails on two pre-existing gates I did not touch: `_lint-flags` (flags name missing beads `sase-nw` / `sase-om` / `sase-pa` / `sase-nx`) and `_lint-toobig` (`tests/_suite_gate.py` is 1197 lines). Those are on the bead as `PROPOSED FOLLOW-UP` for the land agent.

The finalizer needs the phase closed and then committed. I'll read the commit skill, confirm the bead and working tree, and close `sase-qd.1` before committing.

The phase is already closed locally. I’ll confirm the unpublished-close diagnostic, then inspect the diff and commit.

Closing the phase bead to publish the close, then committing.

The close command is still running. I’ll wait for it to finish in this turn.

The close is published (already closed; verification note attached). Writing the commit message and committing.

Closed `sase-qd.1` and committed the set-current write path.

**Bead.** `sase bead close sase-qd.1` published successfully. The phase was already closed (`done` at 2026-08-18T22:48:15Z); the close added the verification note. `sase bead epic-symbols sase-qd.1` reported no leftovers. Parent epic `sase-qd` is still open.

**Commit.** `ce534441f` — `feat(project): add set_current_project and sase project set-current` — is on `master` and matches `origin/master` (clean working tree, 0 ahead / 0 behind).

The commit lands `set_current_project()`, `sase project set-current`, the CLI/docs/skill updates, and the new tests. Agent-hood publication for this commit is still queued behind 40 quarantined requests; that does not affect the git push.
