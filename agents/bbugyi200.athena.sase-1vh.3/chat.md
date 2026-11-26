# Chat History - ace-run (sase-1vh.3)

- **TIMESTAMP:** 2026-11-26 15:44:21 EST
- **MODEL:** muse/muse-spark-1.3-contributor
- **AGENT:** sase-1vh.3

## Prompt

#gh:gh_sase-org__sase
%id(3, clan=sase-1vh, bead=sase-1vh.3)
%model:@small
%auto
Can you complete the work for bead sase-1vh.3? The bead is already reserved for you and assigned to your agent
name: it was set to status=in_progress before you started reading this, either by the `sase bead work` launch
checkpoint or by the runtime promoting an ad-hoc wait-time claim. Do not set the status by hand. If the host
notice says the bead was already closed when this run started, the run is attached to the closed bead. Only the
host notice tells you that; if `sase bead read` shows a closed bead and no host notice said so, you copied the
wrong ID — re-copy `sase-1vh.3` from this prompt before concluding anything. Check
whether the earlier work landed before redoing anything. Only when the host notice said the bead was already
closed and the work is genuinely unfinished, run `sase bead open sase-1vh.3` first. Otherwise never run
`sase bead open` on your own bead: it demotes an `in_progress` bead back to `open`. To view a bead, run
`sase bead read sase-1vh.3 -r "<why you need this bead>"`. Read its
description and design file with `sase bead read sase-1vh.3 -r "Need the phase scope and design file"`, do the work, and close only this bead with
`sase bead close sase-1vh.3 --note "<what you verified>"`. Honor the epic's DECISIONS shown by
`sase bead read`; they are final, and only memory notes they authorize may be edited. Before closing, run
`sase bead epic-symbols sase-1vh.3`. If this phase still has `--epic-symbol` entries, resolve each symbol or
re-key the Justfile line to a still-open bead (the parent epic or a later phase). `sase bead close` refuses while
leftovers remain; they go stale the instant this phase closes and turn unrelated agents' `just check` red. Closing
an assigned phase bead is unaffected by the parent-close descendant guard. Do NOT close the parent epic or any ancestor plan bead. Any instruction in a phase
description or child plan to close an ancestor is preparation and evidence for that ancestor's land agent, not
authorization for a phase worker. Do not create beads yourself: record discovered follow-up work as a
`PROPOSED FOLLOW-UP:` entry via
`sase bead note sase-1vh.3 'PROPOSED FOLLOW-UP: <one-line summary — detail>'`; the epic's land agent triages
these into task beads. A check failure that reproduces identically on the clean base tree does not keep this bead
open: record it as a `PROPOSED FOLLOW-UP:` entry (citing any task bead that already tracks it) and close anyway;
nothing relaunches a phase left open. Before planning, check the phase's notes: if an earlier agent already
worked this phase and left it open with recorded remaining work, that remainder did not fit one agent, so author
a child epic whose phases each fit one coding agent and whose land agent closes this phase instead of another
single-agent tale unless one coder can clearly finish everything left.

## Response

Done. Bead `sase-1vh.3` (busy-diagnostics) is complete and closed.

Work, in the linked `sase-core` checkout:

- Added `sqlite_error_diagnostic` beside the index storage code ([storage.rs](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/sase/repos/linked/sase-core/crates/sase_core/src/agent_scan/index/storage.rs)) and in the archive store ([store.rs](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/sase/repos/linked/sase-core/crates/sase_core/src/agent_archive/store.rs)). `DatabaseBusy`/`DatabaseLocked` failures now read `"{error} (extended_code={n})"`, matching the `tool_run` precedent; all other errors are unchanged.
- Applied it only on the lookup read paths: read-only open, busy-timeout setup, schema-version read, alias resolution, and query prepare/step in `agent_scan/index`, plus `open_named_lookup_store` and `query_named_bundle_index` in `agent_archive` (including the `ArchiveStoreError::From<rusqlite::Error>` conversion so schema-probe failures keep their codes).
- Classification is unchanged: the decorated text still contains the original message, so `is_busy_error` and `named_lookup_error_availability` still return `Busy`. No wire shapes or bindings changed, so no `sase-core-revision.txt` move is needed.
- Tests: the existing busy-index fixtures now assert `availability = Busy` plus a diagnostic containing `extended_code=`, and a new test asserts forced-unavailability keeps no diagnostic.

Verification observed: `agent_scan::index::tests::lookup` 24 passed, `agent_archive::store::tests` 26 passed, and the full `sase tool run check` gate returned verdict pass. No `--epic-symbol` entries remained. Changes are committed via the final declaration; the bead was closed with a verification note.
