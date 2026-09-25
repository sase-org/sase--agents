# Chat History - ace-run (sase-17z.3)

- **TIMESTAMP:** 2026-09-24 13:53:18 EDT
- **MODEL:** muse/muse-spark-1.3-contributor
- **AGENT:** sase-17z.3

## Prompt

#gh:gh_sase-org__sase
%id(3, clan=sase-17z, bead=sase-17z.3)
%model:@small
%auto
%w:sase-17z.1
%w(bead=sase-17z.1)
Can you complete the work for bead sase-17z.3? The bead is already reserved for you and assigned to your agent
name: it was set to status=in_progress before you started reading this, either by the `sase bead work` launch
checkpoint or by the runtime promoting an ad-hoc wait-time claim. Do not set the status by hand. Read its
description and design file with `sase bead read sase-17z.3 -r "Need the phase scope and design file"`, do the work, and close only this bead with
`sase bead close sase-17z.3 --note "<what you verified>"`. Before closing, run
`sase bead epic-symbols sase-17z.3`. If this phase still has `--epic-symbol` entries, resolve each symbol or
re-key the Justfile line to a still-open bead (the parent epic or a later phase). `sase bead close` refuses while
leftovers remain; they go stale the instant this phase closes and turn unrelated agents' `just check` red. Closing
an assigned phase bead is unaffected by the parent-close descendant guard. Do NOT close the parent epic or any ancestor plan bead. Any instruction in a phase
description or child plan to close an ancestor is preparation and evidence for that ancestor's land agent, not
authorization for a phase worker. Do not create beads yourself: record discovered follow-up work as a
`PROPOSED FOLLOW-UP:` entry via
`sase bead note sase-17z.3 'PROPOSED FOLLOW-UP: <one-line summary — detail>'`; the epic's land agent triages
these into task beads.

## Response

Done. Bead sase-17z.3 (surfaces phase) is implemented, closed, and the final declaration was accepted.

What changed (14 files):

- `sase plan list` Proposed table now leads with a `Name` column: the plan name in bold cyan (shortest-unique form, so collisions render as `<shard>/<name>`), folded never ellipsized, with the dim 8-char ID prefix on a second line. A dim hint line under the section shows ready-to-paste `approve:` / `reject:` commands for the first name plus `TAB completes names`.
- `ProposedPlan` gained a `name` field (populated via `plan_names.plan_name`), emitted in `--json` rows; `id_prefix` stays.
- `sase plan show`: the proposal hint now prints `approve <name>` / `reject <name>`, `PlanShowProposal` carries `name` (wired through `_proposal_context`), and the JSON envelope includes it automatically.
- Docs: `docs/cli.md` Proposed-row description is name-first, the `proposal` rung description matches the resolver, and `docs/configuration.md` documents the `name` field and hint line.

Verification:

- `sase bead epic-symbols sase-17z.3`: clean, no leftovers.
- Focused suites green: 81 passed (inventory, rendering, proposals, scanning, show render/handler/resolve) + 45 passed (pending-selector, approve CLI), including a new collision-display/hint test.
- `sase tool run check`: every gate passes except `symvision`, which fails with 74 private-import violations in files I never touched. I proved it pre-existing by stashing my diff and re-running symvision on the pristine tree (identical failure, zero mentions of plan files). Recorded as `PROPOSED FOLLOW-UP` on the bead for the epic land agent.

Two environment notes: the prepared-monitor completion path was ineligible because another agent has an uncommitted object file in the `agents` sidecar (foreign work, left alone), so verification ran inline; and tests must run under `.venv/bin/python` (3.14), not the system 3.11.
