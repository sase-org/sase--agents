# Chat History - ace-run (sase-on.4)

- **TIMESTAMP:** 2026-08-17 13:51:32 EDT
- **MODEL:** grok/grok-4.6
- **AGENT:** sase-on.4

## Prompt

#gh:gh_sase-org__sase
%id(4, clan=sase-on, bead=sase-on.4)
%model:@medium
%auto
%w:sase-on.1,sase-on.3
%w(bead=sase-on.1)
%w(bead=sase-on.3)
Can you complete the work for bead sase-on.4? The bead is already reserved for you and assigned to your agent
name: it was set to status=in_progress before you started reading this, either by the `sase bead work` launch
checkpoint or by the runtime promoting an ad-hoc wait-time claim. Do not set the status by hand. Read its
description and design file, do the work, and close only this bead with
`sase bead close sase-on.4 --note "<what you verified>"`. Before closing, run
`sase bead epic-symbols sase-on.4`. If this phase still has `--epic-symbol` entries, resolve each symbol or
re-key the Justfile line to a still-open bead (the parent epic or a later phase). `sase bead close` refuses while
leftovers remain; they go stale the instant this phase closes and turn unrelated agents' `just check` red. Closing
an assigned phase bead is unaffected by the parent-close descendant guard. Do NOT close the parent epic or any ancestor plan bead. Any instruction in a phase
description or child plan to close an ancestor is preparation and evidence for that ancestor's land agent, not
authorization for a phase worker. Do not create beads yourself: record discovered follow-up work as a
`PROPOSED FOLLOW-UP:` entry via
`sase bead note sase-on.4 'PROPOSED FOLLOW-UP: <one-line summary — detail>'`; the epic's land agent triages
these into task beads.

## Response

I'll start by reading the bead, its design file, and the bead-workflow memory so the phase work stays aligned with SASE rules.

The phase is the stale-cleanup chop. Next I’ll read the epic plan and the earlier phases so I can implement it against the existing design.

The plan is clear: extract the shared project inventory, add the hourly cleanup chop, then register it and drop the temporary epic symbols. I’ll inspect the earlier-phase code next.

I have the triage chop as a template. Next I’ll read the gate facade, lumberjack config, and existing tests so the new chop matches those contracts.

`local_now()` is naive while `stale_task_bead` compares against aware timestamps — I need to check how the existing tests handle that.

I have the contracts and the earlier-phase seams. Next I’ll extract the shared inventory and implement the new chop against them.

The inventory is shared. Next I’ll add the stale-cleanup chop and its lane-state reconciliation.

Docs and registration are in. Next I’ll write the chop tests and extend the lumberjack coverage.

That inventory warning test is messier than it needs to be. I’ll clean up the imports and keep the assertion.

The implementation is in place. Next I’ll install the workspace and run the new tests.

The helper was snapshotting the bead list, so later mutations never reached the second pass. I’ll keep a live reference instead.

The new tests passed. I’ll format, then run the full `just check` gate.

Closed **sase-on.4** (`bead_stale_cleanup chop`). The parent epic is still open.

### What landed

**Shared inventory.** `enabled_project_stores`, `coerce_project_inventory`, `ProjectInventory`, and `project_display_name` now live in `src/sase/scripts/_bead_gate_projects.py`. `enabled_project_stores` takes a required `chop=` keyword so each chop labels its own warnings. The old module does not re-export them. `bead_task_triage` still exposes a log-only `_enabled_project_stores` wrapper so existing test doubles keep working.

**Hourly chop.** `sase_chop_bead_stale_cleanup` scans ready task beads, keeps those `stale_task_bead` accepts, and:

- creates nothing below `stale_cleanup_min_beads`
- offers at most 50, oldest first, with a `(project, bead_id)` tie-break
- logs a non-zero omitted count
- fingerprints the offered roster plus the three thresholds (`stale_as_of` is excluded)
- leaves an unchanged pending gate alone
- cancels and recreates on a roster change
- cancels and clears state when the backlog drops below the bar
- never cancels a healthy gate if a project store read failed or inventory is unavailable

Lane state is `bead_stale_cleanup.json` under the lumberjack state dir, locked for the whole pass.

**Registration.** The chop is on the `housekeeping` lumberjack (`timeout: 2m`) and in `[project.scripts]`. The four `sase-on(...)` `--epic-symbol` entries are gone.

**Docs.** `docs/axe.md`, `docs/notifications.md`, `docs/beads.md`, and the `configuration.md` axe sample now describe the cleanup chop, the 50-bead cap, and the single-gate invariant.

### Verified

- `just check` passed. The scoped lane escalated to the full suite (Justfile, packaging config, default config) and that run was green.
- `sase bead epic-symbols sase-on.4` reports no leftovers.
- Chop tests cover below/at-threshold, non-stale exclusion, the cap and omitted log, unchanged roster, `stale_as_of` excluded from the fingerprint, generation bump on roster change, below-bar cancel, failed-project no-cancel, inventory failure, dry-run, and two-project oldest-first order.

I'll close the assigned phase bead after checking leftover epic symbols, then commit the uncommitted stale-cleanup work with the git-commit skill.

The bead is already closed locally with no leftover epic symbols. I’ll publish that close, then review the diff and commit.

Publishing the bead close next, then writing the commit message from the reviewed diff.

The close command is still running; I’ll wait on it in this turn rather than ending early.

The close published (already closed, note recorded). Next I’ll write the commit message and create the stitch.

The commit succeeded. I’ll confirm the branch is clean and in sync with upstream.

Published the close for **sase-on.4** (`bead_stale_cleanup chop`) and committed the phase work. The parent epic is still open.

**Bead.** `sase bead epic-symbols sase-on.4` had no leftovers. `sase bead close sase-on.4` published (already closed; verification note recorded) with no unpublished-store diagnostic.

**Commit.** `9f5147be3` — `feat(axe): add hourly bead_stale_cleanup chop`

- Shared project inventory in `_bead_gate_projects.py`
- Hourly `bead_stale_cleanup` chop (50-bead cap, fingerprint reconciliation, single-gate invariant)
- Housekeeping lumberjack + `[project.scripts]` registration
- Dropped the four `sase-on` `--epic-symbol` entries
- Docs and tests for the new chop

Working tree is clean and `master` matches `origin/master`. Agent-hood publication for this commit is still queued behind 13 quarantined requests (`sase agent sync --retry-quarantined`); that does not affect the git commit.
