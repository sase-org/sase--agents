# Chat History - ace-run (sase-1qh.5)

- **TIMESTAMP:** 2026-10-31 13:38:24 EDT
- **MODEL:** muse/muse-spark-1.3-contributor
- **AGENT:** sase-1qh.5

## Prompt

#gh:gh_sase-org__sase
%id(5, clan=sase-1qh, bead=sase-1qh.5)
%model:@small
%auto
Can you complete the work for bead sase-1qh.5? The bead is already reserved for you and assigned to your agent
name: it was set to status=in_progress before you started reading this, either by the `sase bead work` launch
checkpoint or by the runtime promoting an ad-hoc wait-time claim. Do not set the status by hand. If the host
notice says the bead was already closed when this run started, the run is attached to the closed bead. Only the
host notice tells you that; if `sase bead read` shows a closed bead and no host notice said so, you copied the
wrong ID — re-copy `sase-1qh.5` from this prompt before concluding anything. Check
whether the earlier work landed before redoing anything, and run `sase bead open sase-1qh.5` only if the work
is genuinely unfinished. Read its
description and design file with `sase bead read sase-1qh.5 -r "Need the phase scope and design file"`, do the work, and close only this bead with
`sase bead close sase-1qh.5 --note "<what you verified>"`. Honor the epic's DECISIONS shown by
`sase bead read`; they are final, and only memory notes they authorize may be edited. Before closing, run
`sase bead epic-symbols sase-1qh.5`. If this phase still has `--epic-symbol` entries, resolve each symbol or
re-key the Justfile line to a still-open bead (the parent epic or a later phase). `sase bead close` refuses while
leftovers remain; they go stale the instant this phase closes and turn unrelated agents' `just check` red. Closing
an assigned phase bead is unaffected by the parent-close descendant guard. Do NOT close the parent epic or any ancestor plan bead. Any instruction in a phase
description or child plan to close an ancestor is preparation and evidence for that ancestor's land agent, not
authorization for a phase worker. Do not create beads yourself: record discovered follow-up work as a
`PROPOSED FOLLOW-UP:` entry via
`sase bead note sase-1qh.5 'PROPOSED FOLLOW-UP: <one-line summary — detail>'`; the epic's land agent triages
these into task beads. A check failure that reproduces identically on the clean base tree does not keep this bead
open: record it as a `PROPOSED FOLLOW-UP:` entry (citing any task bead that already tracks it) and close anyway;
nothing relaunches a phase left open. Before planning, check the phase's notes: if an earlier agent already
worked this phase and left it open with recorded remaining work, that remainder did not fit one agent, so author
a child epic whose phases each fit one coding agent and whose land agent closes this phase instead of another
single-agent tale unless one coder can clearly finish everything left.

## Response

Done. Bead `sase-1qh.5` (footer-brackets) is closed.

What landed:

- **sase-core parser** (`crates/sase_core/src/commit_footer.rs`): values of the exact form `[label]`, and `[label][id]` whose `id` has no reference definition, now project as the bare `label` with no destination. `raw_value` is untouched, and retained unlinked tags re-render from `raw_value`, so `update_commit_footer` round-trips stay byte-identical. Added 3 tests (shortcut form, undefined-id form with a defined link beside it, round-trip).
- **sase cache** (`src/sase/artifact_links/projection/_stitch_rules.py`): rule-level `_STITCH_RULES_CACHE_VERSION = 2` folded into the cache signature, so the cached `bead:[...]` rows rebuild once. Document-wide `_CACHE_SCHEMA_VERSION` untouched.
- **Tests**: replaced the old-behavior stitch test with one asserting `SASE_BEAD=[sase-xx]` projects `bead:sase-xx` end to end, plus a test seeding a pre-version bare-sha cache and proving it's ignored, rewritten versioned, then hit. Verified against the real `8c8c47f720` trailer shape: bead unwraps correctly, the defined `SASE_AGENT=...[1]` link still resolves, round-trip identical.

Verification observed: sase_core full suite 5737+405 pass, `sase_core_py` binding tests 18 pass, sase `sase tool run check` — all lint gates green, full suite 59387 pass with one failure in `test_tui_app_import_stays_under_startup_budget` that I proved reproduces identically on the clean base tree (triage already marks it KNOWN) and recorded as a `PROPOSED FOLLOW-UP`. The 12 remaining sase-core fmt diffs are pre-existing `staged_handoff` drift in a sibling epic's area; my files are fmt-clean.

Two deliberate non-actions, both noted on the bead: no `sase-core-revision.txt` ratchet (remote HEAD doesn't contain the uncommitted fix, so ratcheting now would pin a fix-less HEAD — it's a land-time step after the sase-core commit), and no installs (global install is human-only; the local venv rebuild was verification-only).

Declaration accepted. Bead `sase-1qh.5` work committed (main: close, sase-core: keep).
