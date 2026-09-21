# Chat History - ace-run (sase-15b.9)

- **TIMESTAMP:** 2026-09-21 17:55:56 EDT
- **MODEL:** muse/muse-spark-1.3-contributor
- **AGENT:** sase-15b.9

## Prompt

#gh:gh_sase-org__sase
%id(9, clan=sase-15b, bead=sase-15b.9)
%model:@medium
%auto
%w:sase-15b.8
%w(bead=sase-15b.8)
Can you complete the work for bead sase-15b.9? The bead is already reserved for you and assigned to your agent
name: it was set to status=in_progress before you started reading this, either by the `sase bead work` launch
checkpoint or by the runtime promoting an ad-hoc wait-time claim. Do not set the status by hand. Read its
description and design file with `sase bead read sase-15b.9 -r "Need the phase scope and design file"`, do the work, and close only this bead with
`sase bead close sase-15b.9 --note "<what you verified>"`. Before closing, run
`sase bead epic-symbols sase-15b.9`. If this phase still has `--epic-symbol` entries, resolve each symbol or
re-key the Justfile line to a still-open bead (the parent epic or a later phase). `sase bead close` refuses while
leftovers remain; they go stale the instant this phase closes and turn unrelated agents' `just check` red. Closing
an assigned phase bead is unaffected by the parent-close descendant guard. Do NOT close the parent epic or any ancestor plan bead. Any instruction in a phase
description or child plan to close an ancestor is preparation and evidence for that ancestor's land agent, not
authorization for a phase worker. Do not create beads yourself: record discovered follow-up work as a
`PROPOSED FOLLOW-UP:` entry via
`sase bead note sase-15b.9 'PROPOSED FOLLOW-UP: <one-line summary — detail>'`; the epic's land agent triages
these into task beads.

## Response

Bead sase-15b.9 is done and closed.

Result: `crates/sase_core/src/runner_capacity.rs` (2,938 lines) is now a `runner_capacity/` module tree. Every file is under 470 lines, all 43 tests moved whole with count parity (43 before → 43 after, all passing), and `just check` exits 0 with 33 ok suites and no failures.

Chosen decomposition (domain seams from the plan, 8 production files): `wire.rs` (wire types, schema consts, alias normalization, diagnostic/blocker builders), `snapshot.rs` (entry point), `claims.rs` (claim building and lineage), `records.rs` (record predicates, weights, record index), `waiters.rs` (waiter evaluation, blockers, ordering/priority/deference), `candidate.rs` (candidate decision), `holds.rs` (hold barriers), `capacity_math.rs` (float math plus shortfalls, moved byte-for-byte). Tests mirror the seams in `tests/` (`support.rs` holds the shared builders per the accepted `support.rs` exception; `capacity_math.rs` also imports `capacity_math::capacity_fits`, which one test calls directly). Rejected: a layer split (scatters domain concepts), merging holds/candidate/records into neighbors (blurs the hold-barrier concept, bloats waiters), and splitting claims-vs-lineage further (would cut the tightly coupled build_claims↔lineage↔inherited-weight cluster). No file remains over 1500 lines; `lib.rs` is untouched and the public API is preserved through `mod.rs` re-exports. `sase bead epic-symbols` showed no leftovers.

Commit decision: changes are uncommitted in the linked sase-core checkout (deleted `runner_capacity.rs`, new `runner_capacity/` tree) for the host-owned finalizer to land; I created no beads and filed no follow-ups.

Declaration accepted for commit (sibling:sase-core, bead_action keep; close rejected since this linked repo is not the bead's primary owner, and the bead was already closed).
