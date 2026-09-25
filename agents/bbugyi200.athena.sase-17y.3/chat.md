# Chat History - ace-run (sase-17y.3)

- **TIMESTAMP:** 2026-09-24 13:18:55 EDT
- **MODEL:** muse/muse-spark-1.3-contributor
- **AGENT:** sase-17y.3

## Prompt

#gh:gh_sase-org__sase
%id(3, clan=sase-17y, bead=sase-17y.3)
%model:@medium
%auto
%w:sase-17y.2
%w(bead=sase-17y.2)
Can you complete the work for bead sase-17y.3? The bead is already reserved for you and assigned to your agent
name: it was set to status=in_progress before you started reading this, either by the `sase bead work` launch
checkpoint or by the runtime promoting an ad-hoc wait-time claim. Do not set the status by hand. Read its
description and design file with `sase bead read sase-17y.3 -r "Need the phase scope and design file"`, do the work, and close only this bead with
`sase bead close sase-17y.3 --note "<what you verified>"`. Before closing, run
`sase bead epic-symbols sase-17y.3`. If this phase still has `--epic-symbol` entries, resolve each symbol or
re-key the Justfile line to a still-open bead (the parent epic or a later phase). `sase bead close` refuses while
leftovers remain; they go stale the instant this phase closes and turn unrelated agents' `just check` red. Closing
an assigned phase bead is unaffected by the parent-close descendant guard. Do NOT close the parent epic or any ancestor plan bead. Any instruction in a phase
description or child plan to close an ancestor is preparation and evidence for that ancestor's land agent, not
authorization for a phase worker. Do not create beads yourself: record discovered follow-up work as a
`PROPOSED FOLLOW-UP:` entry via
`sase bead note sase-17y.3 'PROPOSED FOLLOW-UP: <one-line summary — detail>'`; the epic's land agent triages
these into task beads.

## Response

Bead sase-17y.3 (plan-retry) is done and closed.

What was implemented, per the phase spec:

- [epic_from_plan.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_39/src/sase/bead/epic_from_plan.py): `EpicFromPlanError` carries `relocated_epic_id`; when the launch raises `EpicGraphRelocatedError`, rollback removes the moved epic ID (cascading to phases) and never the original ID, keeping `graph_published`/`rollback_performed`.
- [cli_work_from_plan_launch.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_39/src/sase/bead/cli_work_from_plan_launch.py): fresh-creation branch retries up to 3 total attempts (`_EPIC_CREATION_MAX_ATTEMPTS`) only when the failure carries a relocated ID, the rollback was clean, and `publish_epic_rollback` succeeds; renders the `↻ Epic ID <old> collided… retrying (attempt 2/3)` line, resets per-attempt state, keeps `stale_epic_id`, uses the launched epic's verified ID (dropped the `published_relocations` plumbing), and records `relocation_retries` timing.
- [cli_work_from_plan_resume.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_39/src/sase/bead/cli_work_from_plan_resume.py): on relocation, the archived plan's `bead_id` is rewritten to the moved ID via `set_frontmatter_fields` + the plan-commit hook, then the existing rollback-publish branch runs and the error states re-running the plan resumes the moved epic. No auto-retry.

Verified: 4 new tests pass (moved-ID rollback preserving original + foreign bead, retry succeeding on attempt 2, exhaustion stopping at 3 with plan restored, resume relinking); all 28 tests in the two touched test files pass, plus 43 in checkpoint/relocation/task suites; `ruff check`, `ruff format --check`, and `mypy` clean. `epic-symbols` is empty.

Two environment notes: `sase final prepare` is blocked by a pre-existing protected file in the agents sidecar (dated 2026-08-29, untouched by this session), so the final declaration went through `sase final submit` (accepted) instead; and I left a `PROPOSED FOLLOW-UP` note suggesting the land agent run the full `just check` gate, since this turn ran scoped verification only.
