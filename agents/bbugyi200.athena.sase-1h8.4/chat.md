# Chat History - ace-run (sase-1h8.4)

- **TIMESTAMP:** 2026-10-06 19:44:39 EDT
- **MODEL:** muse/muse-spark-1.3-contributor
- **AGENT:** sase-1h8.4

## Prompt

#gh:gh_sase-org__sase
%id(4, clan=sase-1h8, bead=sase-1h8.4)
%model:@medium
%auto
Can you complete the work for bead sase-1h8.4? The bead is already reserved for you and assigned to your agent
name: it was set to status=in_progress before you started reading this, either by the `sase bead work` launch
checkpoint or by the runtime promoting an ad-hoc wait-time claim. Do not set the status by hand. Read its
description and design file with `sase bead read sase-1h8.4 -r "Need the phase scope and design file"`, do the work, and close only this bead with
`sase bead close sase-1h8.4 --note "<what you verified>"`. Before closing, run
`sase bead epic-symbols sase-1h8.4`. If this phase still has `--epic-symbol` entries, resolve each symbol or
re-key the Justfile line to a still-open bead (the parent epic or a later phase). `sase bead close` refuses while
leftovers remain; they go stale the instant this phase closes and turn unrelated agents' `just check` red. Closing
an assigned phase bead is unaffected by the parent-close descendant guard. Do NOT close the parent epic or any ancestor plan bead. Any instruction in a phase
description or child plan to close an ancestor is preparation and evidence for that ancestor's land agent, not
authorization for a phase worker. Do not create beads yourself: record discovered follow-up work as a
`PROPOSED FOLLOW-UP:` entry via
`sase bead note sase-1h8.4 'PROPOSED FOLLOW-UP: <one-line summary — detail>'`; the epic's land agent triages
these into task beads. A check failure that reproduces identically on the clean base tree does not keep this bead
open: record it as a `PROPOSED FOLLOW-UP:` entry (citing any task bead that already tracks it) and close anyway;
nothing relaunches a phase left open.

## Response

Bead sase-1h8.4 (parse-once) is complete and closed.

What changed, all in the linked sase-core checkout (`crates/sase_core/src/bead/`):

- `jsonl.rs`: `read_event_store` no longer prunes, deletes, or rewrites the manifest. Removed-flag tombstones are skipped in memory (counted in the `stream_count` check), live-flag streams still error with today's message, other parse failures surface unchanged, and the streams directory is listed once. Each event is validated exactly once at parse time in `parse_event_stream_bytes`.
- `events/reduction.rs`: removed the deep stream clone and all per-event `IssueWire::validate` calls. New `reduce_parsed_event_streams` entry points skip re-validation for parse-validated input; the untrusted `bead_reduce_event_streams` binding path keeps full validation. Issues are validated once each in the post-pass; a finally-invalid store still fails with kind `validation`.
- `wire.rs`: `validate_unique_external_refs` is O(n) via `HashMap` with a byte-identical error.
- `mutation/store.rs`: `MutableStore::load` prunes under the mutation lock; the redundant load-level ext-ref check is gone. `read.rs`, `history.rs`, `attachments.rs` use the parsed paths.

Verification observed this turn: 5 new tests green (skip-without-delete with byte-identical store, live-flag read error, locked-load prune, repaired-intermediate loads, finally-invalid still fails); parity suites green (bead_event 35, bead_storage 15, bead_read 8; 426 bead unit tests); `sase tool run check` succeeded (run 243c48a2011e70b2de50e9290083b24e, 46 suites ok). Timing on a /tmp copy of the live-shape store (2,112 streams, 7,062 issues, debug build): `read_event_store_issues` went from ~3.0s to ~1.2s per replay (~60% reduction).

Notes: `sase bead epic-symbols` showed no leftovers. The sanctioned intermediate-state relaxation and numbers are recorded in the bead notes. sase-core tree is uncommitted for the host finalizer (final declaration accepted); the land agent still needs to ratchet `sase-core-revision.txt` — no sase code changes were needed since no bindings changed.
