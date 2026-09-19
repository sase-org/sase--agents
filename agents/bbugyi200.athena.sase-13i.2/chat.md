# Chat History - ace-run (sase-13i.2)

- **TIMESTAMP:** 2026-09-19 12:57:42 EDT
- **MODEL:** grok/grok-4.6
- **AGENT:** sase-13i.2

## Prompt

#gh:gh_sase-org__sase
%id(2, clan=sase-13i, bead=sase-13i.2)
%model:@medium
%auto
Can you complete the work for bead sase-13i.2? The bead is already reserved for you and assigned to your agent
name: it was set to status=in_progress before you started reading this, either by the `sase bead work` launch
checkpoint or by the runtime promoting an ad-hoc wait-time claim. Do not set the status by hand. Read its
description and design file, do the work, and close only this bead with
`sase bead close sase-13i.2 --note "<what you verified>"`. Before closing, run
`sase bead epic-symbols sase-13i.2`. If this phase still has `--epic-symbol` entries, resolve each symbol or
re-key the Justfile line to a still-open bead (the parent epic or a later phase). `sase bead close` refuses while
leftovers remain; they go stale the instant this phase closes and turn unrelated agents' `just check` red. Closing
an assigned phase bead is unaffected by the parent-close descendant guard. Do NOT close the parent epic or any ancestor plan bead. Any instruction in a phase
description or child plan to close an ancestor is preparation and evidence for that ancestor's land agent, not
authorization for a phase worker. Do not create beads yourself: record discovered follow-up work as a
`PROPOSED FOLLOW-UP:` entry via
`sase bead note sase-13i.2 'PROPOSED FOLLOW-UP: <one-line summary — detail>'`; the epic's land agent triages
these into task beads.

## Response

I'll start by reading the bead, its design file, and the SASE skills this phase needs.

The phase is tribe-stable widgets: I'll inspect the current display/widget code and tests before changing IDs or rebuild behavior.

I have a clear picture of the tribe-keyed IDs and incremental insert/remove path. Next I’ll add the failing tests, then implement the widget-layer changes.

Sticky occupancy should stay on the widget layer, not in `_panel_group`, so focus still drops when a tribe leaves occupancy.

Closed **sase-13i.2**. Agents-tab tribe panels are now tribe-keyed widgets, so adding or removing a sibling no longer remounts or blanks `@epic`.

What landed:

- Widget ids are `agent-list-panel` for `@default` and `agent-list-panel-{public_tribe_name}` for named tribes (`chop` → `agent-list-panel-job`). Index slots are gone.
- Occupancy growth/shrink mounts or removes only the affected `AgentList`, then reorders. Untouched panels skip `update_list` / `clear_options`.
- A tribe that has appeared this session stays mounted under the same committed query as a collapsed title strip at 0 rows; a query change may unmount it. Fold intents for those sticky keys are kept.
- `_try_remove_agent_rows` no longer bails on a standing search query. Whole-panel occupancy loss collapses that widget instead of rebuilding siblings.

Verified: targeted widget/diff/kill tests; `just check` lint/mypy; scoped suite 43464 passed. One unrelated `test_run_ace_app_does_not_join_default_executor_worker` timing flake failed in the full scoped run and passed 5/5 in isolation. No leftover `--epic-symbol` entries for this phase. Visual snapshot tests were updated to tribe-stable selectors; `just check` does not run them, and PNG goldens were not regenerated because widget ids are not painted.
