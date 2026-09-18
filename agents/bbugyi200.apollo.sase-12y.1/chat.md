# Chat History - ace-run (sase-12y.1)

- **TIMESTAMP:** 2026-09-18 10:31:54 EDT
- **MODEL:** grok/grok-4.6
- **AGENT:** sase-12y.1

## Prompt

#gh:gh_sase-org__sase
%id(sase-12y.1, bead=sase-12y.1)
%clan(sase-12y, tribe=epic, summary_script=sase_clan_summary_epic)
%model:@medium
%auto
Can you complete the work for bead sase-12y.1? The bead is already reserved for you and assigned to your agent
name: it was set to status=in_progress before you started reading this, either by the `sase bead work` launch
checkpoint or by the runtime promoting an ad-hoc wait-time claim. Do not set the status by hand. Read its
description and design file, do the work, and close only this bead with
`sase bead close sase-12y.1 --note "<what you verified>"`. Before closing, run
`sase bead epic-symbols sase-12y.1`. If this phase still has `--epic-symbol` entries, resolve each symbol or
re-key the Justfile line to a still-open bead (the parent epic or a later phase). `sase bead close` refuses while
leftovers remain; they go stale the instant this phase closes and turn unrelated agents' `just check` red. Closing
an assigned phase bead is unaffected by the parent-close descendant guard. Do NOT close the parent epic or any ancestor plan bead. Any instruction in a phase
description or child plan to close an ancestor is preparation and evidence for that ancestor's land agent, not
authorization for a phase worker. Do not create beads yourself: record discovered follow-up work as a
`PROPOSED FOLLOW-UP:` entry via
`sase bead note sase-12y.1 'PROPOSED FOLLOW-UP: <one-line summary — detail>'`; the epic's land agent triages
these into task beads.

## Response

I'll start by reading the bead, its design file, and the beads skill so I can complete only `sase-12y.1`.

I'll record skill use and pull the bead details plus its design file.

Phase 1 is a core API change. I'll open `sase-core` and inspect the current projection path.

I'll open `sase-core` and inspect the existing bead-projection APIs.

I have the contract: one lock, one load, one save, and the singleton API going through the same apply path. Next I’ll implement that in `sase-core`.

Next I’ll add the core tests that lock in rollback, replay, byte-equivalence, and the scaled load/save bound.

I'll format the core repo and run the new projection tests before the full gate.

Core tests passed. Next I’ll run the PyO3 binding tests, then the full `just check` gate.

The binding conversion test was too strict about the serde error text. I’ll match the actual message and rerun it.

Clippy is clean. Next I’ll run the full sase-core `just check` gate.

`just check` passed. I’ll inspect leftover epic-symbols, then close only this phase bead.

Completed **sase-12y.1** (`projection_batch_core`) in `sase-core` and closed the phase bead.

`set_bead_link_projection` now shares one apply path with a new bulk API, `set_bead_link_projections`. A batch takes one bead mutation lock, loads the store once, applies every request in input order with the same validation, canonicalization, undirected-holder selection, receipt, and event payload as the singleton, and saves once only if something actually changed. An invalid request in the middle leaves the event stream and `issues.jsonl` untouched.

The PyO3 binding is `bead_set_link_projections(beads_dir, requests)` (list of dicts). The existing singleton binding is unchanged.

Verified:
- Mixed present/absent, directed and undirected holders, and already-canonical aliases are byte-equivalent to the singleton contract
- Invalid middle request rolls back (store bytes unchanged)
- A seen receipt can still repair changed reduced state; stable replay is 1 load / 0 saves
- 32-request batch is 1 load / 1 save versus 32/32 for singleton calls
- Binding conversion and core validation errors
- `just check` in sase-core (fmt, clippy, workspace tests)

No `--epic-symbol` leftovers. Parent epic `sase-12y` was left open. Phase 2 (`sase-12y.2`) can pin the published `sase-core-rs` that contains this binding; this phase does not claim SASE integration from a local wheel.
