# Chat History - ace-run (sase-16z.4)

- **TIMESTAMP:** 2026-09-23 14:03:55 EDT
- **MODEL:** muse/muse-spark-1.3-contributor
- **AGENT:** sase-16z.4

## Prompt

#gh:gh_sase-org__sase
%id(4, clan=sase-16z, bead=sase-16z.4)
%model:@medium
%auto
%w:sase-16z.1,sase-16z.3
%w(bead=sase-16z.1)
%w(bead=sase-16z.3)
Can you complete the work for bead sase-16z.4? The bead is already reserved for you and assigned to your agent
name: it was set to status=in_progress before you started reading this, either by the `sase bead work` launch
checkpoint or by the runtime promoting an ad-hoc wait-time claim. Do not set the status by hand. Read its
description and design file with `sase bead read sase-16z.4 -r "Need the phase scope and design file"`, do the work, and close only this bead with
`sase bead close sase-16z.4 --note "<what you verified>"`. Before closing, run
`sase bead epic-symbols sase-16z.4`. If this phase still has `--epic-symbol` entries, resolve each symbol or
re-key the Justfile line to a still-open bead (the parent epic or a later phase). `sase bead close` refuses while
leftovers remain; they go stale the instant this phase closes and turn unrelated agents' `just check` red. Closing
an assigned phase bead is unaffected by the parent-close descendant guard. Do NOT close the parent epic or any ancestor plan bead. Any instruction in a phase
description or child plan to close an ancestor is preparation and evidence for that ancestor's land agent, not
authorization for a phase worker. Do not create beads yourself: record discovered follow-up work as a
`PROPOSED FOLLOW-UP:` entry via
`sase bead note sase-16z.4 'PROPOSED FOLLOW-UP: <one-line summary — detail>'`; the epic's land agent triages
these into task beads.

## Response

Bead sase-16z.4 is done and closed.

What landed:
- Core pin moved to `cfe1902a` (contains the attempt-policy commit); bindings gate passes and the new attempt fields were probed live against the built core.
- New shared `detect_rate_limit` classifier in [\_strategy.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_37/src/sase/llm_provider/usage/_strategy.py) covering 429 / rate-limit phrasings / too-many-requests plus Retry-After extraction from headers, prose, and error fields. All five collectors consult it first on their evidence-bearing failure paths; agy now captures stderr so non-JSON output classifies instead of falling through to `parse_error`.
- `not_installed` normalized to outcome `unsupported` for muse, agy, and grok (claude/codex already did this).
- Runner passes each observation's reason code and Retry-After plus `adaptive=True` into every attempt; deadline/crash paths record `deadline_exceeded`/`probe_failed`. Facade extended with the new attempt fields.
- `sase usage list -v` (plain `retry=` field, new rich Retry column) and the Models-panel detail line render `last_failure_reason` + `retry_at` (e.g. `rate limited · retry in 52m`); JSON passes the snapshot through unchanged.
- Docs updated (`llms.md` classifier contract for plugin authors, error-class table in `configuration.md`) and committed tests added for every item above.

Verification: all touched-area test files pass in full (strategy, presentation, models rendering, all five probe suites, refresh runner, refresh, store bindings, probe). `just check` is green on every gate except one pre-existing symvision flag (`ClanSummaryDigest` in an untouched ACE file, failing at HEAD independent of this diff) — recorded as a `PROPOSED FOLLOW-UP` note on the bead for the land agent. No epic-symbol leftovers; final declaration accepted.
