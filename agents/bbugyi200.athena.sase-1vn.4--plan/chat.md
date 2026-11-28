# Chat History - ace-run (sase-1vn.4--plan)

- **TIMESTAMP:** 2026-11-27 20:17:36 EST
- **MODEL:** codex/gpt-6-astra
- **AGENT:** sase-1vn.4--plan

**Plan:** /home/bryan/.sase/plans/202611/zombie_epic_liveness.md


## Proposed Plan Preview

*Plan submitted for review.*

**Plan file:** `/home/bryan/.sase/plans/202611/zombie_epic_liveness.md`

> - **PARENT:** [202611/backlog_epic_1.md](202611/backlog_epic_1.md)
> # Host-owned recovery for zombie epics
> ## Scope and authority
> This child epic implements phase `sase-1vn.4` of `plan:202611/backlog_epic_1.md`,
> addressing the defect recorded in `sase-12u`. The parent reviewer selected
> **zombie_recovery = relaunch**. That decision is final: report existing zombies, and
> recover eligible future cases by relaunching the land agent. Never automatically close a
> plan bead. No memory changes are authorized or needed. The parent's test-cost decision
> is outside this child epic.
> The assigned phase had no prior-work notes when inspected on 2026-11-27. The inspected

*See full plan file for details.*

## Prompt

%auto
#gh:gh_sase-org__sase
%id(4, clan=sase-1vn, bead=sase-1vn.4)
%model:@large
%w(sase-1vn.3, for_epic=false)
%w(bead=sase-1vn.3)
Can you complete the work for bead sase-1vn.4? The bead is already reserved for you and assigned to your agent
name: it was set to status=in_progress before you started reading this, either by the `sase bead work` launch
checkpoint or by the runtime promoting an ad-hoc wait-time claim. Do not set the status by hand. If the host
notice says the bead was already closed when this run started, the run is attached to the closed bead. Only the
host notice tells you that; if `sase bead read` shows a closed bead and no host notice said so, you copied the
wrong ID — re-copy `sase-1vn.4` from this prompt before concluding anything. Check
whether the earlier work landed before redoing anything. Only when the host notice said the bead was already
closed and the work is genuinely unfinished, run `sase bead open sase-1vn.4` first. Otherwise never run
`sase bead open` on your own bead: it demotes an `in_progress` bead back to `open`. To view a bead, run
`sase bead read sase-1vn.4 -r "<why you need this bead>"`. Read its
description and design file with `sase bead read sase-1vn.4 -r "Need the phase scope and design file"`, do the work, and close only this bead with
`sase bead close sase-1vn.4 --note "<what you verified>"`. Honor the epic's DECISIONS shown by
`sase bead read`; they are final, and only memory notes they authorize may be edited. Before closing, run
`sase bead epic-symbols sase-1vn.4`. If this phase still has `--epic-symbol` entries, resolve each symbol or
re-key the Justfile line to a still-open bead (the parent epic or a later phase). `sase bead close` refuses while
leftovers remain; they go stale the instant this phase closes and turn unrelated agents' `just check` red. Closing
an assigned phase bead is unaffected by the parent-close descendant guard. Do NOT close the parent epic or any ancestor plan bead. Any instruction in a phase
description or child plan to close an ancestor is preparation and evidence for that ancestor's land agent, not
authorization for a phase worker. Do not create beads yourself: record discovered follow-up work as a
`PROPOSED FOLLOW-UP:` entry via
`sase bead note sase-1vn.4 'PROPOSED FOLLOW-UP: <one-line summary — detail>'`; the epic's land agent triages
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

I’ll use the `sase_memory_read` and `sase_plan` skills to review the bead, check earlier work, and submit the required plan before changing files.


The bead has no earlier-work notes. Its approved decision calls for automatic land-agent relaunch when all child work is closed and no land agent is live. I’m checking the existing recovery code to identify what still needs to be built.


The current code can relaunch just an epic’s land agent, but it has no automatic zombie-epic check. I’m using `sase_repo` to inspect the Rust core, where the shared detection logic belongs. The plan must also preserve the approved cutoff: existing zombies are reported, while only new child-close events can trigger recovery.


I’m sizing this as a child epic. The remaining work spans shared detection, a read-only report, durable relaunch deduplication, and the scheduled host job. Separate phases will make the launch guarantees easier to verify, especially around crashes and overlapping scheduler runs.


The key gaps are confirmed: the current stranded-work snapshot lacks the full descendant tree, and launch deduplication only covers active processes. I’m writing a four-phase plan that adds complete detection and a durable close-event claim, then connects them to the report and scheduled recovery job.


The plan passes validation with zero warnings. It now has five phases: detection, reporting, durable claims, guarded launch submission, and scheduler integration.

I’ll submit it for review now. The required [`sase_plan` workflow](/home/bryan/.codex/skills/sase_plan/SKILL.md) says, “Nothing starts until your turn ends”; after staging, I must finish through `sase_final`. Implementation and bead closure will follow that review.


The proposal is staged. I’m using `sase_final` to complete the planning handoff; `sase-1vn.4` remains in progress.


Validated and staged a five-phase child epic for `sase-1vn.4`, with zero validation warnings. Implementation awaits review; the bead remains in progress.

The required [`sase_plan` workflow](/home/bryan/.codex/skills/sase_plan/SKILL.md) says to “finish through `/sase_final`” after staging. That handoff is complete.
