# Chat History - ace-run (sase-16n.11.2)

- **TIMESTAMP:** 2026-09-23 10:29:24 EDT
- **MODEL:** muse/muse-spark-1.3-contributor
- **AGENT:** sase-16n.11.2

## Prompt

#gh:gh_sase-org__sase
%id(2, clan=sase-16n.11, bead=sase-16n.11.2)
%model:@medium
%auto
%w:sase-16n.11.1
%w(bead=sase-16n.11.1)
Can you complete the work for bead sase-16n.11.2? The bead is already reserved for you and assigned to your agent
name: it was set to status=in_progress before you started reading this, either by the `sase bead work` launch
checkpoint or by the runtime promoting an ad-hoc wait-time claim. Do not set the status by hand. Read its
description and design file with `sase bead read sase-16n.11.2 -r "Need the phase scope and design file"`, do the work, and close only this bead with
`sase bead close sase-16n.11.2 --note "<what you verified>"`. Before closing, run
`sase bead epic-symbols sase-16n.11.2`. If this phase still has `--epic-symbol` entries, resolve each symbol or
re-key the Justfile line to a still-open bead (the parent epic or a later phase). `sase bead close` refuses while
leftovers remain; they go stale the instant this phase closes and turn unrelated agents' `just check` red. Closing
an assigned phase bead is unaffected by the parent-close descendant guard. Do NOT close the parent epic or any ancestor plan bead. Any instruction in a phase
description or child plan to close an ancestor is preparation and evidence for that ancestor's land agent, not
authorization for a phase worker. Do not create beads yourself: record discovered follow-up work as a
`PROPOSED FOLLOW-UP:` entry via
`sase bead note sase-16n.11.2 'PROPOSED FOLLOW-UP: <one-line summary — detail>'`; the epic's land agent triages
these into task beads.

## Response

Bead sase-16n.11.2 work is implemented; declaration submitted with `keep` while two verifications finish.

Done this turn:
- `+home` synthetic system target (`[catalog.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_34/src/sase/project_tags/catalog.py)`), verified on an empty dir: expands to `#git:home`.
- `project_tag_for` returns unknown names unchanged; callers (`_vcs_launch_prefix`, mismatch hint, frozen prefix) verified to degrade gracefully.
- `to_wire()` sends `state`/`workspace_dir`; payload test updated; `validate_sase_core_rs` needs no change (symbol list only).
- Completion cache keys on the MRU store plus spec signature.
- Doctor reports case-only directory keys and `Home`-folded keys, with kind-aware wording.
- Dead `catalog_cache_signature` removed; `use_cache=False` leaves the cache alone.
- New `tests/test_project_tag_launch.py`: 16 step-8 tests (ordering, verbatim dispatch, canonical MRU, guard matrix, alt/swarm, preview errors, `#git:Sase` refusal with `+sase` hint).
- Core pin ratcheted to `4300166` (core-fixes).

Still pending: scoped test lane and followup/monitor suite results. `sase tool run check` passes everything except the known master red `symvision: ExpandedLaunchSegments` (task sase-16u, untouched file). I will close the bead once the pending runs land.
