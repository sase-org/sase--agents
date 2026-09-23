# Chat History - ace-run (sase-16z.2)

- **TIMESTAMP:** 2026-09-23 12:41:13 EDT
- **MODEL:** muse/muse-spark-1.3-contributor
- **AGENT:** sase-16z.2

## Prompt

#gh:gh_sase-org__sase
%id(2, clan=sase-16z, bead=sase-16z.2)
%model:@medium
%auto
%w:sase-16z.1
%w(bead=sase-16z.1)
Can you complete the work for bead sase-16z.2? The bead is already reserved for you and assigned to your agent
name: it was set to status=in_progress before you started reading this, either by the `sase bead work` launch
checkpoint or by the runtime promoting an ad-hoc wait-time claim. Do not set the status by hand. Read its
description and design file with `sase bead read sase-16z.2 -r "Need the phase scope and design file"`, do the work, and close only this bead with
`sase bead close sase-16z.2 --note "<what you verified>"`. Before closing, run
`sase bead epic-symbols sase-16z.2`. If this phase still has `--epic-symbol` entries, resolve each symbol or
re-key the Justfile line to a still-open bead (the parent epic or a later phase). `sase bead close` refuses while
leftovers remain; they go stale the instant this phase closes and turn unrelated agents' `just check` red. Closing
an assigned phase bead is unaffected by the parent-close descendant guard. Do NOT close the parent epic or any ancestor plan bead. Any instruction in a phase
description or child plan to close an ancestor is preparation and evidence for that ancestor's land agent, not
authorization for a phase worker. Do not create beads yourself: record discovered follow-up work as a
`PROPOSED FOLLOW-UP:` entry via
`sase bead note sase-16z.2 'PROPOSED FOLLOW-UP: <one-line summary — detail>'`; the epic's land agent triages
these into task beads.

## Response

Bead sase-16z.2 complete and closed.

Implemented the core-admission-policy phase in the linked sase-core checkout: adaptive due/admit evaluation (retry_after → cooldown → explicit → parked/cli_changed → backoff → floor → marked_due → reset_passed → never_observed → jittered cadence), deterministic FNV jitter in [0.9, 1.1] on cadence intervals and adaptive backoffs, hot cadence with hints/warn windows/passive suppression, `mark_provider_usage_hot` (1 h cap, 60 s coalescing), read-only reservation listing, and floor-aware reads — all with Python bindings (`provider_usage_mark_hot`, `provider_usage_list_refresh_reservations`, `provider_min_intervals` on load) and golden legacy-compat tests.

Verified: 129 provider-usage core tests, 10 provider-policy binding tests, and `sase tool run check` green. One transient fleet-gateway failure appeared under the full parallel lane and passed on retry plus 221/221 in isolation (no dependency on this change); recorded as a `PROPOSED FOLLOW-UP` note for the land agent. No epic-symbol entries remained.
