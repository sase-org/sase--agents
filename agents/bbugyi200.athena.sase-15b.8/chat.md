# Chat History - ace-run (sase-15b.8)

- **TIMESTAMP:** 2026-09-21 17:23:35 EDT
- **MODEL:** muse/muse-spark-1.3-contributor
- **AGENT:** sase-15b.8

## Prompt

#gh:gh_sase-org__sase
%id(8, clan=sase-15b, bead=sase-15b.8)
%model:@medium
%auto
%w:sase-15b.7
%w(bead=sase-15b.7)
Can you complete the work for bead sase-15b.8? The bead is already reserved for you and assigned to your agent
name: it was set to status=in_progress before you started reading this, either by the `sase bead work` launch
checkpoint or by the runtime promoting an ad-hoc wait-time claim. Do not set the status by hand. Read its
description and design file with `sase bead read sase-15b.8 -r "Need the phase scope and design file"`, do the work, and close only this bead with
`sase bead close sase-15b.8 --note "<what you verified>"`. Before closing, run
`sase bead epic-symbols sase-15b.8`. If this phase still has `--epic-symbol` entries, resolve each symbol or
re-key the Justfile line to a still-open bead (the parent epic or a later phase). `sase bead close` refuses while
leftovers remain; they go stale the instant this phase closes and turn unrelated agents' `just check` red. Closing
an assigned phase bead is unaffected by the parent-close descendant guard. Do NOT close the parent epic or any ancestor plan bead. Any instruction in a phase
description or child plan to close an ancestor is preparation and evidence for that ancestor's land agent, not
authorization for a phase worker. Do not create beads yourself: record discovered follow-up work as a
`PROPOSED FOLLOW-UP:` entry via
`sase bead note sase-15b.8 'PROPOSED FOLLOW-UP: <one-line summary — detail>'`; the epic's land agent triages
these into task beads.

## Response

Done. Bead sase-15b.8 is closed; the split is committed via the host finalizer.

**Chosen decomposition** (`crates/sase_core/src/editor/directive/`): four domain submodules following the plan's seams, each keeping its private helpers with their callers:

- [metadata.rs](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_29/sase/repos/linked/sase-core/crates/sase_core/src/editor/directive/metadata.rs) — 791 lines: all static tables, `DIRECTIVES`, hidden list, limits
- [candidate_lists.rs](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_29/sase/repos/linked/sase-core/crates/sase_core/src/editor/directive/candidate_lists.rs) — 371 lines: name/keyword/value/bead candidate builders
- [context.rs](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_29/sase/repos/linked/sase-core/crates/sase_core/src/editor/directive/context.rs) — 481 lines: token detection, clause parsing, `QuoteState`
- [contract.rs](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_29/sase/repos/linked/sase-core/crates/sase_core/src/editor/directive/contract.rs) — 212 lines: lookup API plus the `pub(crate)` colon/double-colon helpers
- [tests.rs](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_29/sase/repos/linked/sase-core/crates/sase_core/src/editor/directive/tests.rs) — 1103 lines, single file (under ceiling, so no `tests/` dir needed); [mod.rs](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_29/sase/repos/linked/sase-core/crates/sase_core/src/editor/directive/mod.rs) — 30 lines, thin re-exports

**Rejected alternatives:** a 2-file tables-plus-logic split (mixes three concepts, lower cohesion); a per-directive-family split (would scatter the shared keyword/conflict machinery and flag-aware `_with_flags` pairs). Naming avoids `editor/completion/directive_candidates.rs` confusion (`candidate_lists`, not `candidates`).

**Visibility diff (minimal):** six private table consts → `pub(super)`; `wait_queue_keyword_retired` → `pub(in crate::editor)` (used by `completion/directive_candidates.rs`, matching the `bead/events` precedent); `mixes_positional_and_keyword_clauses` → `pub(super)` (used by `context.rs`). Public surface is byte-identical — all crate-external paths (`editor/mod.rs` re-exports, `super::directive::` users, `directive_scan.rs`) resolve unchanged.

**Verification:** 29/29 directive tests pass (matches the 29-test baseline); `just check` green (fmt, clippy with zero warnings, full workspace tests including 56 `sase_core_py` binding tests). Size audit confirms the target is gone and every new file is ≤1500. Remaining >1500 files are other phases' targets (`runner_capacity.rs`, `notification_store_parity.rs`) or explicitly out of scope (`frontmatter.rs`). `epic-symbols` was clean; only this bead was closed.
