# Chat History - ace-run (sase-1h8.1)

- **TIMESTAMP:** 2026-10-06 21:14:14 EDT
- **MODEL:** muse/muse-spark-1.3-contributor
- **AGENT:** sase-1h8.1

## Prompt

#gh:gh_sase-org__sase
%id(sase-1h8.1, bead=sase-1h8.1)
%clan(sase-1h8, tribe=epic, summary_script=sase_clan_summary_epic)
%model:@medium
%auto
Can you complete the work for bead sase-1h8.1? The bead is already reserved for you and assigned to your agent
name: it was set to status=in_progress before you started reading this, either by the `sase bead work` launch
checkpoint or by the runtime promoting an ad-hoc wait-time claim. Do not set the status by hand. Read its
description and design file with `sase bead read sase-1h8.1 -r "Need the phase scope and design file"`, do the work, and close only this bead with
`sase bead close sase-1h8.1 --note "<what you verified>"`. Before closing, run
`sase bead epic-symbols sase-1h8.1`. If this phase still has `--epic-symbol` entries, resolve each symbol or
re-key the Justfile line to a still-open bead (the parent epic or a later phase). `sase bead close` refuses while
leftovers remain; they go stale the instant this phase closes and turn unrelated agents' `just check` red. Closing
an assigned phase bead is unaffected by the parent-close descendant guard. Do NOT close the parent epic or any ancestor plan bead. Any instruction in a phase
description or child plan to close an ancestor is preparation and evidence for that ancestor's land agent, not
authorization for a phase worker. Do not create beads yourself: record discovered follow-up work as a
`PROPOSED FOLLOW-UP:` entry via
`sase bead note sase-1h8.1 'PROPOSED FOLLOW-UP: <one-line summary — detail>'`; the epic's land agent triages
these into task beads. A check failure that reproduces identically on the clean base tree does not keep this bead
open: record it as a `PROPOSED FOLLOW-UP:` entry (citing any task bead that already tracks it) and close anyway;
nothing relaunches a phase left open.

## Response

Bead sase-1h8.1 is closed. The scaled-corpus benchmark harness is landed and verified.

What was built:
- [tests/perf/_bead_corpus.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/tests/perf/_bead_corpus.py) — deterministic, seedable synthetic corpus. Event IDs minted exactly as core's `mint_bead_event_id` (proved byte-equal against core-minted events, including the `external_ref` serialization order).
- [tests/perf/_bead_scale_copy.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/tests/perf/_bead_scale_copy.py) + [tools/bead_scale_corpus](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/tools/bead_scale_corpus) — read-only copy tool with length-preserving prefix-renamed k× copies (re-minted), refusing sidecar-clone destinations.
- [tests/perf/bench_bead_scale.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/tests/perf/bench_bead_scale.py) — 16 ops (binding reads, binding mutations, CLI incl. note against a local bare remote, TUI loader cold + no-change), JSON with p50/p95/max, shape, and core revision. Record-only, no thresholds.
- [tests/perf/test_bead_corpus.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/tests/perf/test_bead_corpus.py) — 6 tests (mint-exactness, validity + doctor-clean, determinism, shape, 2× copy, refusals); all pass.
- `Justfile`: `bead-perf-scale` (1/2/4/8), `bead-perf-scale-record`, `bead-scale-copy`. CI `perf-floors` runs the record-only 4× with trimmed binding ops and uploads the JSON.

Key results (in the bead notes): 1× gives 6899 beads / 2000 streams / 44744 events at 91.9% closed with `bead_doctor` clean, replaying at ~0.5s — matching the research's 0.48–0.52s. `show_detail` scales 495/984/2127/4628ms across 1×→8× (roughly linear); the TUI snapshot goes 3.0s→11.6s for 2× data, confirming the superlinear grouping loop the tui-board phase will remove.

One finding, not mine: `just check` fails at `lint (symvision)` on `_runs` private-imports in two `src/sase` files I never touched — it reproduces identically with my files removed. Recorded as a `PROPOSED FOLLOW-UP` on the bead for the land agent; everything else in `check` (ruff, mypy, pyscripts, toobig, fmt, extensionless-tools check) passes.

Declaration accepted. Bead sase-1h8.1 work committed with `bead_action: close`; host finalizer will land the commit and close the bead.
