# Chat History - ace-run (sase-16z.7)

- **TIMESTAMP:** 2026-09-23 15:49:19 EDT
- **MODEL:** muse/muse-spark-1.3-contributor
- **AGENT:** sase-16z.7

## Prompt

#gh:gh_sase-org__sase
%id(7, clan=sase-16z, bead=sase-16z.7)
%model:@medium
%auto
%w:sase-16z.6
%w(bead=sase-16z.6)
Can you complete the work for bead sase-16z.7? The bead is already reserved for you and assigned to your agent
name: it was set to status=in_progress before you started reading this, either by the `sase bead work` launch
checkpoint or by the runtime promoting an ad-hoc wait-time claim. Do not set the status by hand. Read its
description and design file with `sase bead read sase-16z.7 -r "Need the phase scope and design file"`, do the work, and close only this bead with
`sase bead close sase-16z.7 --note "<what you verified>"`. Before closing, run
`sase bead epic-symbols sase-16z.7`. If this phase still has `--epic-symbol` entries, resolve each symbol or
re-key the Justfile line to a still-open bead (the parent epic or a later phase). `sase bead close` refuses while
leftovers remain; they go stale the instant this phase closes and turn unrelated agents' `just check` red. Closing
an assigned phase bead is unaffected by the parent-close descendant guard. Do NOT close the parent epic or any ancestor plan bead. Any instruction in a phase
description or child plan to close an ancestor is preparation and evidence for that ancestor's land agent, not
authorization for a phase worker. Do not create beads yourself: record discovered follow-up work as a
`PROPOSED FOLLOW-UP:` entry via
`sase bead note sase-16z.7 'PROPOSED FOLLOW-UP: <one-line summary — detail>'`; the epic's land agent triages
these into task beads.

## Response

Bead sase-16z.7 (hot cadence) is done and closed.

What landed:
- `llm_provider.usage_metrics.active_refresh_seconds` (default 120, min 60, capped at `refresh_seconds`) in `UsageMetricsSettings`, `default_config.yml`, `sase.schema.json`, and the `docs/configuration.md` table.
- `_admit_one` passes the active cadence and `warn_percent` into due/admit; new best-effort `mark_provider_usage_hot` facade with `ProviderUsageMarkHotOutcome` wire type, exported through store and package.
- 15-minute hot hints from the agent launch path (gated on collection + probe capability, never raises) and from limit events.
- Hot rules documented in `configuration.md` / `llms.md`.
- New `tests/llm_provider/test_usage_hot_cadence.py` (15 tests: settings clamping, admission passthrough, hint gating/failure-swallowing, e2e hot codex due at ~120s while hot claude waits on its 300s floor); updated the `test_usage_refresh.py` admit fake for the new kwargs.

Verification: new suite 15 passed; 98 passed across neighboring usage/config/schema suites. `just check` is red only on pre-existing debt I confirmed at HEAD in untouched files (5 symvision unused symbols) plus `test_chop_emits_nothing_due_summary` failing on the clean tree — recorded as a `PROPOSED FOLLOW-UP` note for the land agent (no duplicate task beads found). `epic-symbols` clean, bead closed, final declaration accepted for commit.
