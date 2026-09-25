# Chat History - ace-run (sase-18d.1)

- **TIMESTAMP:** 2026-09-24 17:31:47 EDT
- **MODEL:** muse/muse-spark-1.3-contributor
- **AGENT:** sase-18d.1

## Prompt

#gh:gh_sase-org__sase
%id(sase-18d.1, bead=sase-18d.1)
%clan(sase-18d, tribe=epic, summary_script=sase_clan_summary_epic)
%model:@medium
%auto
Can you complete the work for bead sase-18d.1? The bead is already reserved for you and assigned to your agent
name: it was set to status=in_progress before you started reading this, either by the `sase bead work` launch
checkpoint or by the runtime promoting an ad-hoc wait-time claim. Do not set the status by hand. Read its
description and design file with `sase bead read sase-18d.1 -r "Need the phase scope and design file"`, do the work, and close only this bead with
`sase bead close sase-18d.1 --note "<what you verified>"`. Before closing, run
`sase bead epic-symbols sase-18d.1`. If this phase still has `--epic-symbol` entries, resolve each symbol or
re-key the Justfile line to a still-open bead (the parent epic or a later phase). `sase bead close` refuses while
leftovers remain; they go stale the instant this phase closes and turn unrelated agents' `just check` red. Closing
an assigned phase bead is unaffected by the parent-close descendant guard. Do NOT close the parent epic or any ancestor plan bead. Any instruction in a phase
description or child plan to close an ancestor is preparation and evidence for that ancestor's land agent, not
authorization for a phase worker. Do not create beads yourself: record discovered follow-up work as a
`PROPOSED FOLLOW-UP:` entry via
`sase bead note sase-18d.1 'PROPOSED FOLLOW-UP: <one-line summary — detail>'`; the epic's land agent triages
these into task beads.

## Response

Bead `sase-18d.1` (core-wire) is done and closed.

What landed:

- **sase-core**: `runner_is_live` on the cleanup target wire with schema bumped 4→5; FAILED+pid+live rows are now kill items (kill-and-dismiss, incl. parallel-member cascade) and `not_dismissable/runner_live` skips in dismiss-completed, while DONE+live still dismisses. `save_dismissed_agents_index` is atomic (temp+fsync+rename), and new locked merge-on-write `update_dismissed_agents_index` handles missing/corrupt files and both triple/dict shapes. Exposed through `sase_core_py` as `update_dismissed_agents_index`.
- **sase**: wire v5 + field carried through `cleanup_targets_for_core`/coerce, `runner_is_live` projected from agents, exact mirror of the FAILED+live rule in the reference planner, `try_update_dismissed_agents_index` wrapper, and `add/remove_dismissed_agents` in `dismissed_agents` + `dismissed_agents_state`. Callers unchanged for the later additive-dismissals phase.

Verification (all observed this turn): new Rust tests pass (planner kill/dismiss/cascade/schema-4-rejection, concurrent-update/compose/corrupt/shapes); Rust↔Python parity suites pass against a freshly built schema-5 extension; new additive-API tests pass; ruff/keep-sorted clean. Two pre-existing issues reported, not introduced: `just check` mypy/symvision findings confined to untouched files, and a sase-core gateway load flake that passes in isolation.

One open item, recorded on the bead for the land agent: the sase-core change sits uncommitted in the linked checkout, so `sase-core-revision.txt` stays at `6d0d0e6` — the pin can only move past a landed sase-core commit, which a phase worker can't create.

Declaration accepted for `commit` (main: close bead `sase-18d.1`; sibling `sase-core`: keep). No further work performed this turn.
