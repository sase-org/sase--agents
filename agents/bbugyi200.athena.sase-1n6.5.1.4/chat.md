# Chat History - ace-run (sase-1n6.5.1.4)

- **TIMESTAMP:** 2026-10-20 00:11:39 EDT
- **MODEL:** muse/muse-spark-1.3-contributor
- **AGENT:** sase-1n6.5.1.4

## Prompt

#gh:gh_sase-org__sase
%id(4, clan=sase-1n6.5.1, bead=sase-1n6.5.1.4)
%model:@medium
%auto
%w(sase-1n6.5.1.3, for_epic=false)
%w(bead=sase-1n6.5.1.3)
Can you complete the work for bead sase-1n6.5.1.4? The bead is already reserved for you and assigned to your agent
name: it was set to status=in_progress before you started reading this, either by the `sase bead work` launch
checkpoint or by the runtime promoting an ad-hoc wait-time claim. Do not set the status by hand. If the host
notice says the bead was already closed when this run started, the run is attached to the closed bead. Check
whether the earlier work landed before redoing anything, and run `sase bead open sase-1n6.5.1.4` only if the work
is genuinely unfinished. Read its
description and design file with `sase bead read sase-1n6.5.1.4 -r "Need the phase scope and design file"`, do the work, and close only this bead with
`sase bead close sase-1n6.5.1.4 --note "<what you verified>"`. Honor the epic's DECISIONS shown by
`sase bead read`; they are final, and only memory notes they authorize may be edited. Before closing, run
`sase bead epic-symbols sase-1n6.5.1.4`. If this phase still has `--epic-symbol` entries, resolve each symbol or
re-key the Justfile line to a still-open bead (the parent epic or a later phase). `sase bead close` refuses while
leftovers remain; they go stale the instant this phase closes and turn unrelated agents' `just check` red. Closing
an assigned phase bead is unaffected by the parent-close descendant guard. Do NOT close the parent epic or any ancestor plan bead. Any instruction in a phase
description or child plan to close an ancestor is preparation and evidence for that ancestor's land agent, not
authorization for a phase worker. Do not create beads yourself: record discovered follow-up work as a
`PROPOSED FOLLOW-UP:` entry via
`sase bead note sase-1n6.5.1.4 'PROPOSED FOLLOW-UP: <one-line summary — detail>'`; the epic's land agent triages
these into task beads. A check failure that reproduces identically on the clean base tree does not keep this bead
open: record it as a `PROPOSED FOLLOW-UP:` entry (citing any task bead that already tracks it) and close anyway;
nothing relaunches a phase left open. Before planning, check the phase's notes: if an earlier agent already
worked this phase and left it open with recorded remaining work, that remainder did not fit one agent, so author
a child epic whose phases each fit one coding agent and whose land agent closes this phase instead of another
single-agent tale unless one coder can clearly finish everything left.

## Response

Bead sase-1n6.5.1.4 is complete and closed.

What landed: `release.yml` gained `qualify-prepare` (binds the same-run sealed manifest, refuses probes outside rehearse), `qualify-ci` (reusable CI at the identity SHA against the published core), and `qualify` (paginated scoped job/artifact reads, shared evaluator, red observations persisted before the final verdict fails; probes always stay red with intended/tested cores recorded). New stdlib `tools/collect_qualification_jobs` normalizes scoped attempt snapshots with carry-forward, plus 9 helper tests and expanded release workflow contract tests, a Qualify docs section, and the publish seam noted on sase-1n6.5.

Verified: `sase tool run check` green (exit 0, run 677aabb6), all 34 focused tests pass, `epic-symbols` clean. Final declaration accepted; host commits after the turn.
