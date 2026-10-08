# Chat History - ace-run (sase-1h7.6)

- **TIMESTAMP:** 2026-10-07 17:06:49 EDT
- **MODEL:** muse/muse-spark-1.3-contributor
- **AGENT:** sase-1h7.6

## Prompt

#gh:gh_sase-org__sase
%id(6, clan=sase-1h7, bead=sase-1h7.6)
%model:@medium
%auto
%w:sase-1h7.5
%w(bead=sase-1h7.5)
Can you complete the work for bead sase-1h7.6? The bead is already reserved for you and assigned to your agent
name: it was set to status=in_progress before you started reading this, either by the `sase bead work` launch
checkpoint or by the runtime promoting an ad-hoc wait-time claim. Do not set the status by hand. Read its
description and design file with `sase bead read sase-1h7.6 -r "Need the phase scope and design file"`, do the work, and close only this bead with
`sase bead close sase-1h7.6 --note "<what you verified>"`. Before closing, run
`sase bead epic-symbols sase-1h7.6`. If this phase still has `--epic-symbol` entries, resolve each symbol or
re-key the Justfile line to a still-open bead (the parent epic or a later phase). `sase bead close` refuses while
leftovers remain; they go stale the instant this phase closes and turn unrelated agents' `just check` red. Closing
an assigned phase bead is unaffected by the parent-close descendant guard. Do NOT close the parent epic or any ancestor plan bead. Any instruction in a phase
description or child plan to close an ancestor is preparation and evidence for that ancestor's land agent, not
authorization for a phase worker. Do not create beads yourself: record discovered follow-up work as a
`PROPOSED FOLLOW-UP:` entry via
`sase bead note sase-1h7.6 'PROPOSED FOLLOW-UP: <one-line summary — detail>'`; the epic's land agent triages
these into task beads. A check failure that reproduces identically on the clean base tree does not keep this bead
open: record it as a `PROPOSED FOLLOW-UP:` entry (citing any task bead that already tracks it) and close anyway;
nothing relaunches a phase left open.

## Response

Bead sase-1h7.6 is closed.

What landed:
- New `src/sase/core/wait_epic_follow_view.py`: `EpicFollowView` per target, coercion from Agent/marker/wire shapes, `armed_follow_targets`, `authored_wait_beads` (derived `added_bead_ids` excluded, user-authored kept), `epic_follow_state_token`, and `describe_epic_follow` with the plan's three phrasings (verified reason literals against the sase-core reducer).
- Agent model gained `wait_for_epics_of` + `wait_epic_follows`, loaded by both the wire and filesystem enrichment twins with `waiting.json` taking precedence, plus dedup merges.
- `wait_dependency_status_counts` gained a `follows` segment: FOLLOWING targets leave agent counts, their epics count from the cached bead snapshot, derived beads leave authored counts. `wait_dependencies_satisfied` parks on launching/blocked; resolved-but-stageless targets behave exactly as today. `agent_render_key` covers both new fields.
- Tests: `tests/test_wait_epic_follow_view.py` and `tests/ace/tui/test_agent_wait_epic_follow_model.py` (loaders, precedence, key change, every state, no-I/O spy guard). 296 tests across affected files pass; ruff and mypy clean.
- `describe_epic_follow` has no in-phase consumer by design (tui/surfaces phases render it), so the Justfile carries `--epic-symbol 'sase-1h7.8(describe_epic_follow)'`; `epic-symbols sase-1h7.6` is empty and close succeeded.

Two failures reproduce identically on the clean base and were recorded as `PROPOSED FOLLOW-UP` notes instead of blocking: the KNOWN symvision `_runs` private-import errors and the `init repo --check` sidecar README drift.

Declaration submitted: commit for bead sase-1h7.6 with `bead_action: close` accepted.
