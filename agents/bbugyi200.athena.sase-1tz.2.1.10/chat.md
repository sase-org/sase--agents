# Chat History - ace-run (sase-1tz.2.1.10)

- **TIMESTAMP:** 2026-11-19 17:35:54 EST
- **MODEL:** muse/muse-spark-1.3-contributor
- **AGENT:** sase-1tz.2.1.10

## Prompt

%auto
#gh:gh_sase-org__sase
%id(10, clan=sase-1tz.2.1, bead=sase-1tz.2.1.10)
%model:@medium
%w(sase-1tz.2.1.9, for_epic=false)
%w(bead=sase-1tz.2.1.9)
Can you complete the work for bead sase-1tz.2.1.10? The bead is already reserved for you and assigned to your agent
name: it was set to status=in_progress before you started reading this, either by the `sase bead work` launch
checkpoint or by the runtime promoting an ad-hoc wait-time claim. Do not set the status by hand. If the host
notice says the bead was already closed when this run started, the run is attached to the closed bead. Only the
host notice tells you that; if `sase bead read` shows a closed bead and no host notice said so, you copied the
wrong ID — re-copy `sase-1tz.2.1.10` from this prompt before concluding anything. Check
whether the earlier work landed before redoing anything. Only when the host notice said the bead was already
closed and the work is genuinely unfinished, run `sase bead open sase-1tz.2.1.10` first. Otherwise never run
`sase bead open` on your own bead: it demotes an `in_progress` bead back to `open`. To view a bead, run
`sase bead read sase-1tz.2.1.10 -r "<why you need this bead>"`. Read its
description and design file with `sase bead read sase-1tz.2.1.10 -r "Need the phase scope and design file"`, do the work, and close only this bead with
`sase bead close sase-1tz.2.1.10 --note "<what you verified>"`. Honor the epic's DECISIONS shown by
`sase bead read`; they are final, and only memory notes they authorize may be edited. Before closing, run
`sase bead epic-symbols sase-1tz.2.1.10`. If this phase still has `--epic-symbol` entries, resolve each symbol or
re-key the Justfile line to a still-open bead (the parent epic or a later phase). `sase bead close` refuses while
leftovers remain; they go stale the instant this phase closes and turn unrelated agents' `just check` red. Closing
an assigned phase bead is unaffected by the parent-close descendant guard. Do NOT close the parent epic or any ancestor plan bead. Any instruction in a phase
description or child plan to close an ancestor is preparation and evidence for that ancestor's land agent, not
authorization for a phase worker. Do not create beads yourself: record discovered follow-up work as a
`PROPOSED FOLLOW-UP:` entry via
`sase bead note sase-1tz.2.1.10 'PROPOSED FOLLOW-UP: <one-line summary — detail>'`; the epic's land agent triages
these into task beads. A check failure that reproduces identically on the clean base tree does not keep this bead
open: record it as a `PROPOSED FOLLOW-UP:` entry (citing any task bead that already tracks it) and close anyway;
nothing relaunches a phase left open. Before planning, check the phase's notes: if an earlier agent already
worked this phase and left it open with recorded remaining work, that remainder did not fit one agent, so author
a child epic whose phases each fit one coding agent and whose land agent closes this phase instead of another
single-agent tale unless one coder can clearly finish everything left.

## Response

Bead `sase-1tz.2.1.10` (heap_retainers) is done, verified, and submitted for host commit/close.

**Census (controlled, live athena data):** retained-types census via the repo's own tooling ranks the TUI-owned retainers as `NotificationPlusOne` 12,052 live, `SkillUseEvent` 11,365 live (whole-file snapshot cache), `Notification` 5,234 live. Production `tui_stalls.jsonl.1` gives the freed scale: idle gen-2 n=2021, max 7.2M collected, p50 320k. A churn probe (30 loader cycles, gc disabled, one `DEBUG_SAVEALL` full collect) freed 0 cycles — the loader paths are retainers, not cyclic-garbage producers.

**Fixes (2 of up to 3):**
- Deleted the whole-file `_skill_uses_snapshot_cache` ([skill_uses.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/src/sase/ace/tui/skill_uses.py)); per-agent/context loaders now use a new targeted newest-first scan ([`query_skill_use_events`](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/src/sase/skills/use_log.py)) keeping ≤50 events/agent. Matching semantics unchanged. Cold miss on the live 11,365-line log: 0.268s → 0.075s, retained 11,360 → 0. This demonstrates `sase-1tw` resolution (left for the land agent to close). New regression tests: retention, scan budget, revalidation, query units.
- Added `SkillUseEvent` to `CENSUS_WATCHLIST` and removed the dead snapshot-cache probe, so the next census soak tracks the fixed type.

**Verification:** 104 focused tests pass; ruff and mypy clean; `sase tool run check` passes every gate except one symvision NEW on `LaunchPromptContext`, which I verified reproduces identically on a clean HEAD worktree (pre-existing, recorded as follow-up). `epic-symbols` is clean.

**Notes:** before/after numbers, repeat commands, and 4 `PROPOSED FOLLOW-UP:` entries (sase-1tw closure, sase-1tx TUI +1 compaction design, pre-existing symvision item, missing per-type freed census) are on the bead; evidence noted on [sase-1nc](https://github.com/sase-org/sase--beads/blob/main/pages/sase-1tz/sase-1nc.md), summary on `sase-1tz.2`.
