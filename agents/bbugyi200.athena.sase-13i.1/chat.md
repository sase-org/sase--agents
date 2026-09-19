# Chat History - ace-run (sase-13i.1)

- **TIMESTAMP:** 2026-09-19 12:26:39 EDT
- **MODEL:** grok/grok-4.6
- **AGENT:** sase-13i.1

## Prompt

#gh:gh_sase-org__sase
%id(sase-13i.1, bead=sase-13i.1)
%clan(sase-13i, tribe=epic, summary_script=sase_clan_summary_epic)
%model:@medium
%auto
Can you complete the work for bead sase-13i.1? The bead is already reserved for you and assigned to your agent
name: it was set to status=in_progress before you started reading this, either by the `sase bead work` launch
checkpoint or by the runtime promoting an ad-hoc wait-time claim. Do not set the status by hand. Read its
description and design file, do the work, and close only this bead with
`sase bead close sase-13i.1 --note "<what you verified>"`. Before closing, run
`sase bead epic-symbols sase-13i.1`. If this phase still has `--epic-symbol` entries, resolve each symbol or
re-key the Justfile line to a still-open bead (the parent epic or a later phase). `sase bead close` refuses while
leftovers remain; they go stale the instant this phase closes and turn unrelated agents' `just check` red. Closing
an assigned phase bead is unaffected by the parent-close descendant guard. Do NOT close the parent epic or any ancestor plan bead. Any instruction in a phase
description or child plan to close an ancestor is preparation and evidence for that ancestor's land agent, not
authorization for a phase worker. Do not create beads yourself: record discovered follow-up work as a
`PROPOSED FOLLOW-UP:` entry via
`sase bead note sase-13i.1 'PROPOSED FOLLOW-UP: <one-line summary — detail>'`; the epic's land agent triages
these into task beads.

## Response

I'll start by reading the bead, its design file, and the project instructions so the work stays scoped to `sase-13i.1`.

The bead is a phase to publish one aggregate roster per disk apply. Next I’ll read the design, related memory, and current roster code.

I’ve got the design; next I’ll read the apply/snapshot code and the existing proc-shell tests so the first failing case matches the real path.

I have the apply path mapped. Next I’ll add the failing tests, then make roster publication merge the live proc projection once before finalize.

Cached proc shells should still carry when a snapshot never captured a projection. I’ll treat a missing projection as “use the cache,” and an explicit empty projection as the source of truth.

`just check` passed. Next I’ll check leftover epic symbols, then close only `sase-13i.1`.

Closed **sase-13i.1**. A disk apply now publishes one aggregate Agents roster: the live proc-observer projection is merged in before the single finalize, so an empty disk load with a live `@epic` proc shell no longer flashes empty.

What changed:

- `PreparedApplySnapshot` now carries the proc projection, a monotonic `proc_generation`, and dismissed proc-shell ids. That generation is on the finalize stale token, so a moved projection drops a stale worker plan.
- `prepare_loaded_agents_apply_boundary` merges shells from the captured projection, not only from the cached roster.
- UI commit rebases the prepared roster onto `_effective_proc_projection()` if the generation moved during the worker, then calls `_finalize_agent_list()` once. The post-finalize `_sync_proc_shell_agents_from_projection()` call is gone from the disk-apply path.
- While `_agents_loading` is true, observer snapshots only replace `_proc_projection` and bump generation; they do not finalize.

Verified:

- Empty-disk + live epic proc-shell: first and only finalize includes the epic shell and `"epic"` in `panel_keys_for`.
- Generation move between worker prep and UI commit publishes the latest projection.
- Observer snapshot during a disk apply does not finalize.
- Unchanged-projection single-finalize test still passes.
- `just check` is green. No leftover `--epic-symbol` entries for this phase. Parent epic **sase-13i** is still open.
