# Chat History - ace-run (sase-1if.9)

- **TIMESTAMP:** 2026-10-08 16:37:28 EDT
- **MODEL:** muse/muse-spark-1.3-contributor
- **AGENT:** sase-1if.9

## Prompt

#gh:gh_sase-org__sase
%id(9, clan=sase-1if, bead=sase-1if.9)
%model:@small
%auto
%w(sase-1if.2, for_epic=false)
%w(bead=sase-1if.2)
Can you complete the work for bead sase-1if.9? The bead is already reserved for you and assigned to your agent
name: it was set to status=in_progress before you started reading this, either by the `sase bead work` launch
checkpoint or by the runtime promoting an ad-hoc wait-time claim. Do not set the status by hand. Read its
description and design file with `sase bead read sase-1if.9 -r "Need the phase scope and design file"`, do the work, and close only this bead with
`sase bead close sase-1if.9 --note "<what you verified>"`. Honor the epic's DECISIONS shown by
`sase bead read`; they are final, and only memory notes they authorize may be edited. Before closing, run
`sase bead epic-symbols sase-1if.9`. If this phase still has `--epic-symbol` entries, resolve each symbol or
re-key the Justfile line to a still-open bead (the parent epic or a later phase). `sase bead close` refuses while
leftovers remain; they go stale the instant this phase closes and turn unrelated agents' `just check` red. Closing
an assigned phase bead is unaffected by the parent-close descendant guard. Do NOT close the parent epic or any ancestor plan bead. Any instruction in a phase
description or child plan to close an ancestor is preparation and evidence for that ancestor's land agent, not
authorization for a phase worker. Do not create beads yourself: record discovered follow-up work as a
`PROPOSED FOLLOW-UP:` entry via
`sase bead note sase-1if.9 'PROPOSED FOLLOW-UP: <one-line summary — detail>'`; the epic's land agent triages
these into task beads. A check failure that reproduces identically on the clean base tree does not keep this bead
open: record it as a `PROPOSED FOLLOW-UP:` entry (citing any task bead that already tracks it) and close anyway;
nothing relaunches a phase left open.

## Response

Bead sase-1if.9 is closed.

What was done, all in the linked `sase-research-artifacts` checkout:

- `research_audio.md`: the "Choose the CLI" step now selects `sase listen` first (probing `sase listen render --help` for `--generated-cover`), then `sase-listen`, then `uvx sase-listen`. All later steps use the `<listen>` placeholder, rendering via `sase tool run -- <listen> render …`. The "do not silently drop the option" and `audio.ok=false` rules are unchanged.
- `research_swarm.md`: the linker recovery hint now reads `sase listen ls <episode_id> --json` (or `sase-listen ls …`, or `uvx sase-listen ls …`).
- `docs/macros.md` and `README.md`: recommend `sase plugin install listen`, with `uv tool install sase-listen` as the alternative.
- `tests/test_macro_loading.py`: updated the pinned strings to the `<listen>` placeholder and three-tier `ls` hint, and added a test asserting the `sase listen` → `sase-listen` → `uvx` selection order.

Verification: `just lint` is clean and all 74 tests in `test_macro_loading.py` pass via `sase tool run`. An earlier full `check` run showed 112 passed with 1 failure caused by my own line wrap splitting a pinned string; I unwrapped that sentence and re-ran the file green. A `PROPOSED FOLLOW-UP` note records that the `ls` recovery hint is unproven since `ls` is still a stub in sase-listen. `sase bead epic-symbols` shows no leftovers, and no memory notes were edited.

Declaration accepted for the `sase-research-artifacts` commit (bead already closed, so `bead_action: keep`).
