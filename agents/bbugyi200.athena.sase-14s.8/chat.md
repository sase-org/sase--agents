# Chat History - ace-run (sase-14s.8)

- **TIMESTAMP:** 2026-09-21 09:35:20 EDT
- **MODEL:** muse/muse-spark-1.3-contributor
- **AGENT:** sase-14s.8

## Prompt

#gh:gh_sase-org__sase
%id(8, clan=sase-14s, bead=sase-14s.8)
%model:@medium
%auto
%w:sase-14s.7
%w(bead=sase-14s.7)
Can you complete the work for bead sase-14s.8? The bead is already reserved for you and assigned to your agent
name: it was set to status=in_progress before you started reading this, either by the `sase bead work` launch
checkpoint or by the runtime promoting an ad-hoc wait-time claim. Do not set the status by hand. Read its
description and design file, do the work, and close only this bead with
`sase bead close sase-14s.8 --note "<what you verified>"`. Before closing, run
`sase bead epic-symbols sase-14s.8`. If this phase still has `--epic-symbol` entries, resolve each symbol or
re-key the Justfile line to a still-open bead (the parent epic or a later phase). `sase bead close` refuses while
leftovers remain; they go stale the instant this phase closes and turn unrelated agents' `just check` red. Closing
an assigned phase bead is unaffected by the parent-close descendant guard. Do NOT close the parent epic or any ancestor plan bead. Any instruction in a phase
description or child plan to close an ancestor is preparation and evidence for that ancestor's land agent, not
authorization for a phase worker. Do not create beads yourself: record discovered follow-up work as a
`PROPOSED FOLLOW-UP:` entry via
`sase bead note sase-14s.8 'PROPOSED FOLLOW-UP: <one-line summary — detail>'`; the epic's land agent triages
these into task beads.

## Response

Bead sase-14s.8 is done and closed.

Split `crates/sase_core/src/editor/completion.rs` (7,260 lines) into `editor/completion/` — `mod.rs` facade plus 5 source-keyed modules, with tests split along the same seams into `completion/tests/`. Pure move: only `use` lines, `pub(crate)` visibility, and `super::` → `crate::editor::` paths changed.

Chosen decomposition (by completion source): `artifact_ref` (997), `assist_candidates` — xprompt/agent/wait/hold/queue/identity/hood/snippet plus shared rendering helpers (706), `directive_candidates` (589), `vcs_candidates` (879), `trigger_context` — classify dispatcher plus xprompt-arg trigger analysis (436). Rejected the pipeline-stage split (trigger/collection/ranking/rendering): each source's detect/build/apply triple (e.g. `detect_vcs_repo` + `build_vcs_repo` + `apply_vcs_repo`) and its ranking helpers are tightly coupled per source, so staging would have cut cohesive clusters apart and multiplied cross-module visibility. Also avoided `xprompt_args` as a module name — it would collide confusingly with the existing `editor/xprompt_args.rs`.

Tests: 6 files, largest `tests/artifact_ref.rs` (1,248); every file ≤1,500 lines. Test count 81 before → 81 after, none modified beyond the move. Public surface unchanged: all 32 `pub` items re-exported through the facade, so `editor::completion::X`, `editor::X`, and `editor_X` paths all still resolve; `hover.rs` and the `directive.rs` test needed no changes. No `--epic-symbol` entries left.

`just check` passes (fmt, clippy, full workspace incl. `sase_core_py` bindings). One unrelated failure on the first run — `provider_priority` concurrent lock-timeout test — passed solo and passed in the re-run gate; recorded as a `PROPOSED FOLLOW-UP` on the bead for flake triage. Remaining >1,500-line files are other phases' targets (`xprompt_catalog.rs`, `sudo_runner.rs`) or untargeted files, as expected.

Work is committed via the accepted final declaration; parent epic left open for its land agent.
