# Chat History - ace-run (sase-1tz.1--plan)

- **TIMESTAMP:** 2026-11-19 07:28:35 EST
- **MODEL:** claude/opus
- **AGENT:** sase-1tz.1--plan

**Plan:** /home/bryan/.sase/plans/202611/outage_disk_attribution_and_held_workspaces.md


## Proposed Plan Preview

*Plan submitted for review.*

**Plan file:** `/home/bryan/.sase/plans/202611/outage_disk_attribution_and_held_workspaces.md`

> - **PARENT:**
>   [202611/notification_log_audit_fixes.md](202611/notification_log_audit_fixes.md)
> # Plan: Honest disk attribution and the held-workspace re-settlement loop
> This child epic implements phase `outage` (**sase-1tz.1**) of parent epic **sase-1tz**,
> `plan:202611/notification_log_audit_fixes.md`. It covers items 1 and 2: audit findings
> F2 (disk attribution blindness and the Nov 16 apollo ENOSPC outage) and F1 (the
> held-workspace +1 loop).
> ## Read first (every phase)
> - **Audit.** The source of truth is
>   `research:202611/apollo_athena_sase_notification_and_log_audit/apollo_athena_sase_notification_and_log_audit.md`.

*See full plan file for details.*

## Prompt

#gh:gh_sase-org__sase
%id(sase-1tz.1, bead=sase-1tz.1)
%clan(sase-1tz, tribe=epic, summary_script=sase_clan_summary_epic)
%model:@xlarge
%auto
Can you complete the work for bead sase-1tz.1? The bead is already reserved for you and assigned to your agent
name: it was set to status=in_progress before you started reading this, either by the `sase bead work` launch
checkpoint or by the runtime promoting an ad-hoc wait-time claim. Do not set the status by hand. If the host
notice says the bead was already closed when this run started, the run is attached to the closed bead. Only the
host notice tells you that; if `sase bead read` shows a closed bead and no host notice said so, you copied the
wrong ID — re-copy `sase-1tz.1` from this prompt before concluding anything. Check
whether the earlier work landed before redoing anything. Only when the host notice said the bead was already
closed and the work is genuinely unfinished, run `sase bead open sase-1tz.1` first. Otherwise never run
`sase bead open` on your own bead: it demotes an `in_progress` bead back to `open`. To view a bead, run
`sase bead read sase-1tz.1 -r "<why you need this bead>"`. Read its
description and design file with `sase bead read sase-1tz.1 -r "Need the phase scope and design file"`, do the work, and close only this bead with
`sase bead close sase-1tz.1 --note "<what you verified>"`. Honor the epic's DECISIONS shown by
`sase bead read`; they are final, and only memory notes they authorize may be edited. Before closing, run
`sase bead epic-symbols sase-1tz.1`. If this phase still has `--epic-symbol` entries, resolve each symbol or
re-key the Justfile line to a still-open bead (the parent epic or a later phase). `sase bead close` refuses while
leftovers remain; they go stale the instant this phase closes and turn unrelated agents' `just check` red. Closing
an assigned phase bead is unaffected by the parent-close descendant guard. Do NOT close the parent epic or any ancestor plan bead. Any instruction in a phase
description or child plan to close an ancestor is preparation and evidence for that ancestor's land agent, not
authorization for a phase worker. Do not create beads yourself: record discovered follow-up work as a
`PROPOSED FOLLOW-UP:` entry via
`sase bead note sase-1tz.1 'PROPOSED FOLLOW-UP: <one-line summary — detail>'`; the epic's land agent triages
these into task beads. A check failure that reproduces identically on the clean base tree does not keep this bead
open: record it as a `PROPOSED FOLLOW-UP:` entry (citing any task bead that already tracks it) and close anyway;
nothing relaunches a phase left open. Before planning, check the phase's notes: if an earlier agent already
worked this phase and left it open with recorded remaining work, that remainder did not fit one agent, so author
a child epic whose phases each fit one coding agent and whose land agent closes this phase instead of another
single-agent tale unless one coder can clearly finish everything left.
Think this through thoroughly and create a plan using your `/sase_plan` skill. Choose and author the appropriate
tier, validate and revalidate until it passes, then submit it with `sase plan propose` (as the skill instructs)
before making any file changes.


## Response

I'm reading the phase scope and size guidance so I can write the child epic plan for sase-1tz.1.

Opened the research sidecar; now reading the audit's F1/F2 evidence.

Reviewing the overlapping disk-retention epic (sase-zw.8.7.8) to see what's landed before I design.

Still mapping the disk inventory code; next the classifier, models, pressure job, and reaper.

Reading code for both items in parallel: I'll take the held-workspace path myself and send two helpers to map the sase-core notification store and the disk pressure/reaper chain.

Both helper reports are in. Now reading the held-workspace settlement path myself.

Now checking the two prior beads the phase must confirm or refute (sase-1rg.3, sase-1bf.4).

Checking one more overlapping epic (sase-11h) before drafting the child plan.

Checking the raw swarm evidence for what actually blocked apollo's recovery, since the reaper never reads the inventory.

Plan validates cleanly. Submitting it.

sase-1tz.1 is too big for one agent, so instead of coding it I wrote a child epic plan for it and submitted it for review. It passed validation with 0 warnings and is now waiting for approval. No code has changed yet. The bead stays in progress; the child epic's land agent will close it once all phases land. Nothing needed committing this turn.

**What the code review found**
- **Disk recovery:** the reaper never reads the disk inventory. Apollo's Nov 16 recovery missed its target because most of the full disk sat with owners that pressure recovery doesn't touch (workspaces, artifact runs, the rust-prebuild cache). Fixing the inventory alone would not have saved it, so the plan adds a clear escalation that names the blockers.
- **The disk_pressure job** collects the inventory before it reaps, with no error guard. A failing or slow inventory can therefore abort or delay recovery.
- **Every pressure notice is a new row** because it has no dedup key, which is why apollo has 119 of them.
- **sase-1bf.4 looks like an unmet requirement, not a regression.** The scan order that measures workspaces last dates from `028c5137be`, and sase-1bf.4 never changed it. The plan has a phase verify this before recording it on that bead.
- **The held-workspace loop:** each cleanup pass re-runs settlement for every held workspace. That means git probes, diff snapshots and decision-sheet publishing, then an identical +1 that rewrites the whole notification store, even when the row is dismissed.

**The child epic's seven phases**

| Phase | Size | Depends on | What it does |
|---|---|---|---|
| `store_guard` | medium | — | In sase-core, a +1 on a dismissed row does nothing unless the caller opts in, and identical +1s within a window are merged. Neither rewrites the store. Moves the core pin. |
| `held_settle` | medium | `store_guard` | Settles a held workspace once per evidence fingerprint. Re-checks git only when a cheap file check changes or 30 minutes pass. Sends a +1 only when evidence changes, plus the hourly "still held" heartbeat on undismissed rows (your `held_heartbeat = yes` decision). Stops +1s once the row is dismissed, so archived dismissed rows never come back. |
| `starter_scope` | small | — | Checks whether sase-1rg.3 covers repo lists inherited from a monitor's starter; fixes and tests it if not. |
| `unknown_sizes` | medium | — | Disk rows report a size as measured, a lower bound, or unmeasured, never `0 B` complete. The inventory format moves to v2, and the leftover space is no longer all called "unattributed". Moves the core pin. |
| `owner_first` | medium | `unknown_sizes` | Measures workspace and owner folders first, on their own time budget, before the general scan. Records `du` comparisons and a tolerance on apollo and athena. |
| `pressure_recovery` | medium | `unknown_sizes`, `store_guard` | Reaps first, then collects the inventory without letting it block recovery. Gives each pressure episode one notice row. Adds a separate escalation when recovery misses its target. |
| `standing_skips` | small | — | The temp-file reaper still refuses entries it can't fully inspect, but warns once instead of every pass. |

The plan leaves the open disk-retention epic's work alone (sase-zw.8.7.8, which owns scan limits and the rules for whether a temp folder is still in use). The relevant phases note where they overlap on sase-zw.8 and sase-11h. Live-host steps on apollo and athena are read-only measurements, recorded with the command to repeat after you install.
