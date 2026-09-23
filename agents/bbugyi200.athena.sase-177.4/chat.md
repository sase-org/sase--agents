# Chat History - ace-run (sase-177.4)

- **TIMESTAMP:** 2026-09-23 18:40:36 EDT
- **MODEL:** muse/muse-spark-1.3-contributor
- **AGENT:** sase-177.4

## Prompt

#gh:gh_sase-org__sase
%id(4, clan=sase-177, bead=sase-177.4)
%model:@medium
%auto
Can you complete the work for bead sase-177.4? The bead is already reserved for you and assigned to your agent
name: it was set to status=in_progress before you started reading this, either by the `sase bead work` launch
checkpoint or by the runtime promoting an ad-hoc wait-time claim. Do not set the status by hand. Read its
description and design file with `sase bead read sase-177.4 -r "Need the phase scope and design file"`, do the work, and close only this bead with
`sase bead close sase-177.4 --note "<what you verified>"`. Before closing, run
`sase bead epic-symbols sase-177.4`. If this phase still has `--epic-symbol` entries, resolve each symbol or
re-key the Justfile line to a still-open bead (the parent epic or a later phase). `sase bead close` refuses while
leftovers remain; they go stale the instant this phase closes and turn unrelated agents' `just check` red. Closing
an assigned phase bead is unaffected by the parent-close descendant guard. Do NOT close the parent epic or any ancestor plan bead. Any instruction in a phase
description or child plan to close an ancestor is preparation and evidence for that ancestor's land agent, not
authorization for a phase worker. Do not create beads yourself: record discovered follow-up work as a
`PROPOSED FOLLOW-UP:` entry via
`sase bead note sase-177.4 'PROPOSED FOLLOW-UP: <one-line summary — detail>'`; the epic's land agent triages
these into task beads.

## Response

Bead sase-177.4 is complete and closed.

What was done (wait-guidance phase):
- [sase_monitor.md](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_36/src/sase/xprompts/skills/sase_monitor.md): added "Decide Before You Start" — route before starting, never cancel/rerun an in-flight command to move it to a monitor.
- [sase_final.md](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_36/src/sase/xprompts/skills/sase_final.md): declaration is mandatory for final answers and incomplete-status responses, never for waiting; added the two never-wait / never-declare-while-running rules; expanded Prepared Monitor Completion into the full `just fix` → wrapper → `prepare -j` → `monitor start -f` recipe with green/red outcomes.
- Core-memory Final Declaration template plus its test markers rewritten to the never-wait wording; [lint_and_test.md](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_36/sase/memory/lint_and_test.md) now states the up-front rule, names this repo's known-long commands, and folds in the sase-16q fix.
- New decision record `adapters-normalize-harnesses.md` linking `single-turn-agents`; memory regenerated with the workspace venv binary (the system `sase` is a stale install and silently skipped the template change) plus `just fmt`.
- One existing test asserted the old resume-later sentence this phase was required to delete, so its assertions were updated to the new contract.
- All 5 plan follow-ups recorded as `PROPOSED FOLLOW-UP:` notes; `epic-symbols` clean; bead closed; final declaration submitted for the host commit.

Verification: 65 affected-area tests pass. Full `sase tool run check` gave 45904 passed with 3 failures that fail identically on the clean tree (pre-existing TUI/import-budget issues, unrelated to this change); the other transient failures passed on re-run under host load.
