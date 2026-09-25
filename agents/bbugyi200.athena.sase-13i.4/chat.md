# Chat History - ace-run (sase-13i.4)

- **TIMESTAMP:** 2026-09-20 07:35:32 EDT
- **MODEL:** claude/sonnet
- **AGENT:** sase-13i.4

## Prompt

%id(4, clan=sase-13i, bead=sase-13i.4)
#gh:gh_sase-org__sase
%model:@medium
%auto
%w:sase-13i.1,sase-13i.2,sase-13i.3
%w(bead=sase-13i.1)
%w(bead=sase-13i.2)
%w(bead=sase-13i.3)
Can you complete the work for bead sase-13i.4? The bead is already reserved for you and assigned to your agent
name: it was set to status=in_progress before you started reading this, either by the `sase bead work` launch
checkpoint or by the runtime promoting an ad-hoc wait-time claim. Do not set the status by hand. Read its
description and design file, do the work, and close only this bead with
`sase bead close sase-13i.4 --note "<what you verified>"`. Before closing, run
`sase bead epic-symbols sase-13i.4`. If this phase still has `--epic-symbol` entries, resolve each symbol or
re-key the Justfile line to a still-open bead (the parent epic or a later phase). `sase bead close` refuses while
leftovers remain; they go stale the instant this phase closes and turn unrelated agents' `just check` red. Closing
an assigned phase bead is unaffected by the parent-close descendant guard. Do NOT close the parent epic or any ancestor plan bead. Any instruction in a phase
description or child plan to close an ancestor is preparation and evidence for that ancestor's land agent, not
authorization for a phase worker. Do not create beads yourself: record discovered follow-up work as a
`PROPOSED FOLLOW-UP:` entry via
`sase bead note sase-13i.4 'PROPOSED FOLLOW-UP: <one-line summary — detail>'`; the epic's land agent triages
these into task beads.

## Response

Adding a sticky-tribe guard test and running it.

TUI is up on the landed SHA with tracing. Soaking for 30 minutes.

All four notes landed. Now the final declaration.

I did not close sase-13i.4. The 30-minute traced soak on the landed tree still showed the panel dipping, so the "no 2→1→2" check fails.

**Soak**
- I ran my own traced TUI at v0.17.1+945.g9231c9352 with the `NOT machine:apollo` filter.
- I left your live TUI (PID 1880150) alone. It started Sep 15, before the fixes, so it is stale.
- The trace has about 81k records, at `~/.sase/perf/sase-13i.4-soak-tui_trace.jsonl`.

**What held**
- There were zero `active_search` fallbacks.
- The refresh path was mostly incremental: 200 `refresh_display_incremental` spans against 31 `refresh_panel_widgets`.

**What failed**
- **Panel dip:** Three times (once at startup, twice mid-run) the display went from 2 panels / 13–16 agents to 1 panel / 3–6 agents, then back to 2 / 16 about 0.4s later.
- **Cause:** An incomplete `inflight_poll` or `auto_refresh` apply took the full-rebuild path with `status_membership_change`. It published 3–6 rows although the query filter had left about 30. The next `fleet_refresh` restored them.
- **Widget identity:** `agents.refresh_panel_widgets` spans carry no widget id, so `@epic` widget identity can't be checked from traces.

**Tests**
- I added a guard test in `tests/perf/test_agents_display_rebuild_guard.py` (committed). It checks that an emptied roster doesn't unmount an already-mounted `@epic` tribe. That file's 7 tests pass. The other three guards the bead asked for were already in the file or in `tests/test_agents_tab_apply_boundary.py`.
- `just check` fails on 20 mypy errors in `src/sase/main/ace_tmux*.py`, which I didn't touch.

I recorded the verification failure and three `PROPOSED FOLLOW-UP:` notes on the bead: the residual dip, widget ids in the trace spans, and the docs/Rust-core items from the plan.
