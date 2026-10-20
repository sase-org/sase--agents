# Chat History - ace-run (sase-1nd.2)

- **TIMESTAMP:** 2026-10-20 13:16:29 EDT
- **MODEL:** muse/muse-spark-1.3-contributor
- **AGENT:** sase-1nd.2

## Prompt

%auto
#gh:gh_sase-org__sase
%id(2, clan=sase-1nd, bead=sase-1nd.2)
%model:@medium
%w(sase-1nd.1, for_epic=false)
%w(bead=sase-1nd.1)
Can you complete the work for bead sase-1nd.2? The bead is already reserved for you and assigned to your agent
name: it was set to status=in_progress before you started reading this, either by the `sase bead work` launch
checkpoint or by the runtime promoting an ad-hoc wait-time claim. Do not set the status by hand. If the host
notice says the bead was already closed when this run started, the run is attached to the closed bead. Check
whether the earlier work landed before redoing anything, and run `sase bead open sase-1nd.2` only if the work
is genuinely unfinished. Read its
description and design file with `sase bead read sase-1nd.2 -r "Need the phase scope and design file"`, do the work, and close only this bead with
`sase bead close sase-1nd.2 --note "<what you verified>"`. Honor the epic's DECISIONS shown by
`sase bead read`; they are final, and only memory notes they authorize may be edited. Before closing, run
`sase bead epic-symbols sase-1nd.2`. If this phase still has `--epic-symbol` entries, resolve each symbol or
re-key the Justfile line to a still-open bead (the parent epic or a later phase). `sase bead close` refuses while
leftovers remain; they go stale the instant this phase closes and turn unrelated agents' `just check` red. Closing
an assigned phase bead is unaffected by the parent-close descendant guard. Do NOT close the parent epic or any ancestor plan bead. Any instruction in a phase
description or child plan to close an ancestor is preparation and evidence for that ancestor's land agent, not
authorization for a phase worker. Do not create beads yourself: record discovered follow-up work as a
`PROPOSED FOLLOW-UP:` entry via
`sase bead note sase-1nd.2 'PROPOSED FOLLOW-UP: <one-line summary — detail>'`; the epic's land agent triages
these into task beads. A check failure that reproduces identically on the clean base tree does not keep this bead
open: record it as a `PROPOSED FOLLOW-UP:` entry (citing any task bead that already tracks it) and close anyway;
nothing relaunches a phase left open. Before planning, check the phase's notes: if an earlier agent already
worked this phase and left it open with recorded remaining work, that remainder did not fit one agent, so author
a child epic whose phases each fit one coding agent and whose land agent closes this phase instead of another
single-agent tale unless one coder can clearly finish everything left.

## Response

Bead sase-1nd.2 is done and closed.

Rewired `#research/diagrams` around named reader questions with the skill guide inlined exactly once: retargeted candidate selection and ranking, replaced the drawing bans with the guide, swapped the max-width grep for fit-scale validation under the PDF-mirroring config, redrew the manifest example, and added `question`/`review` fields. Also added the linker's audit-note clause, and updated tests and docs.

Verified: `sase tool run check` green (147 passed, lint and mypy clean), wheel lane 4 passed, redrawn example renders 383×438 px at fit 100% under pinned mmdc 12.0.0 (1 round), expanded diagrams-on prompt inlines the guide exactly once with no raw tags, linker clause present only when diagrams run, and epic-symbols clean. One caveat: this runtime cannot view PNGs, so the look step relied on measured and source checks per the skill. Three follow-ups recorded on the bead; the plugin-repo commit was declared for the host to land.
