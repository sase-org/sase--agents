# Chat History - ace-run (sase-sq.1--plan)

- **TIMESTAMP:** 2026-08-24 09:45:42 EDT
- **MODEL:** claude/opus
- **AGENT:** sase-sq.1--plan

**Plan:** /home/bryan/.sase/plans/202608/core_reference_memory.md


## Prompt

#gh:gh_sase-org__sase
%id(sase-sq.1, bead=sase-sq.1)
%clan(sase-sq, tribe=epic, summary_script=sase_clan_summary_epic)
%model:@large
%auto
Can you complete the work for bead sase-sq.1? The bead is already reserved for you and assigned to your agent
name: it was set to status=in_progress before you started reading this, either by the `sase bead work` launch
checkpoint or by the runtime promoting an ad-hoc wait-time claim. Do not set the status by hand. Read its
description and design file, do the work, and close only this bead with
`sase bead close sase-sq.1 --note "<what you verified>"`. Before closing, run
`sase bead epic-symbols sase-sq.1`. If this phase still has `--epic-symbol` entries, resolve each symbol or
re-key the Justfile line to a still-open bead (the parent epic or a later phase). `sase bead close` refuses while
leftovers remain; they go stale the instant this phase closes and turn unrelated agents' `just check` red. Closing
an assigned phase bead is unaffected by the parent-close descendant guard. Do NOT close the parent epic or any ancestor plan bead. Any instruction in a phase
description or child plan to close an ancestor is preparation and evidence for that ancestor's land agent, not
authorization for a phase worker. Do not create beads yourself: record discovered follow-up work as a
`PROPOSED FOLLOW-UP:` entry via
`sase bead note sase-sq.1 'PROPOSED FOLLOW-UP: <one-line summary — detail>'`; the epic's land agent triages
these into task beads.
Think this through thoroughly and create a plan using your `/sase_plan` skill. Choose and author the appropriate
tier, validate and revalidate until it passes, then submit it with `sase plan propose` (as the skill instructs)
before making any file changes.


## Response

*Plan submitted for review.*

**Plan file:** `/home/bryan/.sase/plans/202608/core_reference_memory.md`

> - **PARENT:** [202608/memory_webs.md](202608/memory_webs.md)
> - **BEAD:** sase-sq.1
> # Plan: Core and reference memory vocabulary
> Implements phase `tiers` of epic bead `sase-sq` (phase bead `sase-sq.1`,
> `plan:202608/memory_webs.md`). This is the first phase and has no dependencies.
> ## Goal
> "Short-term memory" becomes **core memory** and "long-term memory" becomes **reference
> memory** everywhere: the Rust tier wire, `type:` frontmatter, the `AGENTS.md` H2
> anchors, templates, the `/sase_memory_read` skill, CLI help, docstrings, and docs.
> Two properties are non-negotiable:

*See full plan file for details.*

