# Chat History - ace-run (sase-1tz.2--plan)

- **TIMESTAMP:** 2026-11-19 11:13:21 EST
- **MODEL:** claude/opus
- **AGENT:** sase-1tz.2--plan

**Plan:** /home/bryan/.sase/plans/202611/noise_publication_digests_tui_stalls.md


## Proposed Plan Preview

*Plan submitted for review.*

**Plan file:** `/home/bryan/.sase/plans/202611/noise_publication_digests_tui_stalls.md`

> - **PARENT:**
>   [202611/notification_log_audit_fixes.md](202611/notification_log_audit_fixes.md)
> # Plan: Publication de-flap, truthful error digests, and TUI stall reduction
> This child epic implements phase `noise` (**sase-1tz.2**) of parent epic **sase-1tz**,
> `plan:202611/notification_log_audit_fixes.md`. It covers items 3, 4, and 5: audit
> findings F3 (agent_publication's chronic error state), F4 (the error digest hides storms
> and loses counts), and F5 (TUI memory growth, GC pauses, and main-thread stalls).
> ## Read first (every phase)
> - **Audit.** The source of truth is
>   `research:202611/apollo_athena_sase_notification_and_log_audit/apollo_athena_sase_notification_and_log_audit.md`.

*See full plan file for details.*

## Prompt

%auto
#gh:gh_sase-org__sase
%id(2, clan=sase-1tz, bead=sase-1tz.2)
%model:@xlarge
%w(sase-1tz.1, for_epic=false)
%w(bead=sase-1tz.1)
Can you complete the work for bead sase-1tz.2? The bead is already reserved for you and assigned to your agent
name: it was set to status=in_progress before you started reading this, either by the `sase bead work` launch
checkpoint or by the runtime promoting an ad-hoc wait-time claim. Do not set the status by hand. If the host
notice says the bead was already closed when this run started, the run is attached to the closed bead. Only the
host notice tells you that; if `sase bead read` shows a closed bead and no host notice said so, you copied the
wrong ID — re-copy `sase-1tz.2` from this prompt before concluding anything. Check
whether the earlier work landed before redoing anything. Only when the host notice said the bead was already
closed and the work is genuinely unfinished, run `sase bead open sase-1tz.2` first. Otherwise never run
`sase bead open` on your own bead: it demotes an `in_progress` bead back to `open`. To view a bead, run
`sase bead read sase-1tz.2 -r "<why you need this bead>"`. Read its
description and design file with `sase bead read sase-1tz.2 -r "Need the phase scope and design file"`, do the work, and close only this bead with
`sase bead close sase-1tz.2 --note "<what you verified>"`. Honor the epic's DECISIONS shown by
`sase bead read`; they are final, and only memory notes they authorize may be edited. Before closing, run
`sase bead epic-symbols sase-1tz.2`. If this phase still has `--epic-symbol` entries, resolve each symbol or
re-key the Justfile line to a still-open bead (the parent epic or a later phase). `sase bead close` refuses while
leftovers remain; they go stale the instant this phase closes and turn unrelated agents' `just check` red. Closing
an assigned phase bead is unaffected by the parent-close descendant guard. Do NOT close the parent epic or any ancestor plan bead. Any instruction in a phase
description or child plan to close an ancestor is preparation and evidence for that ancestor's land agent, not
authorization for a phase worker. Do not create beads yourself: record discovered follow-up work as a
`PROPOSED FOLLOW-UP:` entry via
`sase bead note sase-1tz.2 'PROPOSED FOLLOW-UP: <one-line summary — detail>'`; the epic's land agent triages
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

Reading the phase bead and its context before drafting the child epic plan for items 3–5.

The audit artifact resolves as missing locally, so I'm opening the research sidecar first, then reading the F3–F5 evidence.

Audit read. Now I'll fan out three read-only code explorations (publication, error digests, TUI stalls) while I read the overlapping beads myself.

Sibling phases have no child plans yet, so no overlap to reconcile. Now I'll spot-check the key code paths myself and take a few read-only baseline numbers on this host (athena).

Still in exploration: checking the outbox row model and the publication job's error counting before I write the plan.

Found a likely second root cause for the "sdd:agents prompt archive" holds (leftover `.sase-v2-backup-*` scratch); checking the code that creates it.

Note: this host's Python 3.14.7 still uses the classic three-generation collector, so I won't plan around incremental GC. Checking the drain's timeout/cleanup path next.

I have enough context. Checking the rest of the sibling child plan's structure (phase sections, land guidance) so this one matches, then I'll write the plan.

Plan drafted. Before validating, I'm replacing a convoluted one-liner in the `stall_telemetry` measurement with a clean one.

Three decision fields exceed the 100-character limit (the fourth error cascades from them). Shortening them.

Validation passes. Quick existence check on the file paths the plan cites, before proposing.

All cited paths exist. One small precision fix: naming the exact doc page for the doctor check.

The proposal is staged. Finishing the turn through `/sase_final`.

I've written and staged a child epic plan for sase-1tz.2 (items 3–5: publication, error digests, TUI stalls). Nothing is implemented yet: the plan's phases do the code work, and its land agent closes sase-1tz.2. The plan was auto-approved because it has one decision and that decision takes its default. No files are committed this turn (the host reported no commit was required), and the bead stays in progress.

**The 13 phases:**
- **Error digest (item 4):**
  - `error_groups`: a sase-core normalizer turns error text into a stable signature. The scheduler keeps a durable count per signature, and a failed write is counted and logged instead of silently dropped.
  - `digest_render`: the hourly digest prints one line per cause, a true total, and the real time span covered. It no longer loses errors after downtime, and digest files older than 30 days are deleted.
- **agent_publication (item 3):**
  - `pub_standing`: a repeated failure becomes one standing alert per project and cause, with backoff and a true attempt count. It notifies only when the alert opens, changes, escalates or clears.
  - `pub_cleanup`: the drain timeout keeps time in reserve so cleanup can finish, and leftover scratch directories are removed.
  - `pub_inventory`: the slowest drain stage is built once per tick, reads primary history incrementally, and only queries the agents being published.
  - `prompt_terminal`: prompt archives that genuinely can't be rebuilt get a recorded terminal state, and the cause of their missing source files gets fixed.
  - `pub_doctor`: doctor's publication issue count stops growing every tick. It also applies fix (a) from sase-1rb.
- **TUI (item 5):**
  - `stall_telemetry`: `tui_stalls.jsonl` rotates by size, every reader skips broken lines, and `tui_faults.log` only gets an entry when a fault actually happens.
  - `gc_policy`: stops the TUI's own scheduled full garbage collections from freezing it.
  - `heap_retainers`: finds and fixes what creates the millions of collectable objects.
  - `ui_io_offload` and `ui_cpu_caches`: move the sampled slow file and CPU work off the main thread or behind caches.
  - `tui_acceptance`: compares the TUI numbers before and after, then decides whether sase-1nc, sase-1gf and sase-lx can close.

**What I measured on athena (read-only) that shaped the plan:**
- **Workspace holds:** the 28 "Workspace held … sdd:agents prompt archive" notices come from two leftover scratch folders dated Nov 3 in the shared agents checkout (`~/.sase/projects/gh_sase-org__sase/repos/agents/.sase-v2-backup-*` and `.sase-v2-stage-*`). They were not caused by the prompt archives that can't be rebuilt, so `pub_cleanup` owns releasing those holds.
- **Unbuildable prompt archives:** these don't retry forever. Each is charged three times and then stays quarantined, but it never becomes terminal, so doctor keeps counting it.
- **TUI freezes:** every multi-second GC pause comes from the TUI's own scheduled full collections. The "idle" ones have a median of 1.9 s and a worst case of 73 s; the 5-minute "backstop" reached 324 s while the process was swapping. Both hosts use Python's standard collector, so the plan doesn't rely on any newer one.
- **Log size and error ring:** `tui_stalls.jsonl` is 36 MB. Every publication entry in the error ring carries the same summary line, so the real cause is hidden.

**Decision for you:** the parent plan says to rotate `tui_stalls.jsonl` at the same 2 MiB as its sibling logs, but at athena's current rate that holds only about 4 hours. Since that file is how the TUI fixes get measured, the plan defaults to a cap that keeps 48 hours of rows, with smaller per-pause entries. The other option is to rotate at 2 MiB as the parent plan says. Long test runs would then have to copy the log out as they go.

The plan file is `sase_plan_noise_publication_digests_tui_stalls.md`.
