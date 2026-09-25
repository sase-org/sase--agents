# Chat History - ace-run (sase-17y.2)

- **TIMESTAMP:** 2026-09-24 12:40:34 EDT
- **MODEL:** muse/muse-spark-1.3-contributor
- **AGENT:** sase-17y.2

## Prompt

#gh:gh_sase-org__sase
%id(2, clan=sase-17y, bead=sase-17y.2)
%model:@medium
%auto
Can you complete the work for bead sase-17y.2? The bead is already reserved for you and assigned to your agent
name: it was set to status=in_progress before you started reading this, either by the `sase bead work` launch
checkpoint or by the runtime promoting an ad-hoc wait-time claim. Do not set the status by hand. Read its
description and design file with `sase bead read sase-17y.2 -r "Need the phase scope and design file"`, do the work, and close only this bead with
`sase bead close sase-17y.2 --note "<what you verified>"`. Before closing, run
`sase bead epic-symbols sase-17y.2`. If this phase still has `--epic-symbol` entries, resolve each symbol or
re-key the Justfile line to a still-open bead (the parent epic or a later phase). `sase bead close` refuses while
leftovers remain; they go stale the instant this phase closes and turn unrelated agents' `just check` red. Closing
an assigned phase bead is unaffected by the parent-close descendant guard. Do NOT close the parent epic or any ancestor plan bead. Any instruction in a phase
description or child plan to close an ancestor is preparation and evidence for that ancestor's land agent, not
authorization for a phase worker. Do not create beads yourself: record discovered follow-up work as a
`PROPOSED FOLLOW-UP:` entry via
`sase bead note sase-17y.2 'PROPOSED FOLLOW-UP: <one-line summary — detail>'`; the epic's land agent triages
these into task beads.

## Response

Done. Bead `sase-17y.2` (launch-guard) is implemented and closed.

What changed:

- [relocation.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_41/src/sase/bead/relocation.py): added `relocations_for_subtree` (scopes records to the launch's own ID subtree), `resolve_own_bead_id` (proves a move by matching creation identity `issue_type/title/created_at/created_by` in the post-publication store; foreign moves return the original ID, unlocatable raises `BeadRelocationIdentityError`), and made `rewrite_text_for_bead_relocations` token-safe (single regex pass, ID-boundary guards so `sase-17v.3` rewrites but `sase-17v1` doesn't, no chained `a→b→c` rewrites).
- [cli_work_handler.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_41/src/sase/bead/cli_work_handler.py): `launch_epic_bead_work` no longer rewrites prompt/env text. Unchanged ID launches as before; a proven move of its own graph rolls back preclaims mapped through the moved IDs and raises the new `EpicGraphRelocatedError` (`epic <old> was renumbered to <new>… Resume with: sase bead work <new>`). Unlocatable moves roll back only if the original ID still holds our bead, then raise `BeadWorkError` with a `sase doctor -v` hint.
- [cli_work_from_plan_resume.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_41/src/sase/bead/cli_work_from_plan_resume.py): `publish_resumed_graph` now returns the checkpoint result so resumed launches see relocations.
- [cli_work_commit.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_41/src/sase/bead/cli_work_commit.py) + [cli_work_task.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_41/src/sase/bead/cli_work_task.py): `checkpoint_task_work_launch` returns `LaunchCheckpointResult` (still truthy on push); `launch_task_bead_work` verifies the task after publication and rolls back on the moved ID with `task <old> was renumbered to <new>…`.
- Tests: replaced the old rewrite test with foreign-move (launches original IDs) and own-move (`EpicGraphRelocatedError`, rollback on moved IDs) tests whose fake launcher enforces the real `%name == expected_names` invariant; added unit tests for the new helpers plus a moved-task test.

Verification: 18 relocation/epic-checkpoint, 25 task, 54 launch/cleanup/resume/from-plan, and 20 contention/validation tests all pass; ruff and mypy clean on every touched file; `just fmt` clean with no collateral edits. `sase bead epic-symbols` showed no leftovers. One caveat: full `just check` could not finish in-turn — its setup rebuilds `sase_core_rs` from the linked sase-core checkout, which alone exceeds the 10-minute shell limit (two attempts, both killed during the Rust compile; no check failures observed).

Declaration accepted for `commit`. Recovery turn complete — no new edits made.
