# Chat History - ace-run (sase-uv.8--plan)

- **TIMESTAMP:** 2026-08-27 17:20:09 EDT
- **MODEL:** codex/gpt-5.6-sol
- **AGENT:** sase-uv.8--plan

**Plan:** /home/bryan/.sase/plans/202608/agents_viewport_1.md


## Prompt

%id(8, clan=sase-uv, bead=sase-uv.8)
#gh:gh_sase-org__sase
%model:@large
%auto
%w:sase-uv.4,sase-uv.5,sase-uv.7
%w(bead=sase-uv.4)
%w(bead=sase-uv.5)
%w(bead=sase-uv.7)
Can you complete the work for bead sase-uv.8? The bead is already reserved for you and assigned to your agent
name: it was set to status=in_progress before you started reading this, either by the `sase bead work` launch
checkpoint or by the runtime promoting an ad-hoc wait-time claim. Do not set the status by hand. Read its
description and design file, do the work, and close only this bead with
`sase bead close sase-uv.8 --note "<what you verified>"`. Before closing, run
`sase bead epic-symbols sase-uv.8`. If this phase still has `--epic-symbol` entries, resolve each symbol or
re-key the Justfile line to a still-open bead (the parent epic or a later phase). `sase bead close` refuses while
leftovers remain; they go stale the instant this phase closes and turn unrelated agents' `just check` red. Closing
an assigned phase bead is unaffected by the parent-close descendant guard. Do NOT close the parent epic or any ancestor plan bead. Any instruction in a phase
description or child plan to close an ancestor is preparation and evidence for that ancestor's land agent, not
authorization for a phase worker. Do not create beads yourself: record discovered follow-up work as a
`PROPOSED FOLLOW-UP:` entry via
`sase bead note sase-uv.8 'PROPOSED FOLLOW-UP: <one-line summary — detail>'`; the epic's land agent triages
these into task beads.
Think this through thoroughly and create a plan using your `/sase_plan` skill. Choose and author the appropriate
tier, validate and revalidate until it passes, then submit it with `sase plan propose` (as the skill instructs)
before making any file changes.


## Response

*Plan submitted for review.*

**Plan file:** `/home/bryan/.sase/plans/202608/agents_viewport_1.md`

> - **BEAD:** sase-uv.8
> # Plan: Honour the AgentsViewport contract on the direct ACE read path
> ## Scope and provenance
> Complete phase `viewport` of epic `sase-uv`, bead `sase-uv.8`. The governing design is
> `plan:202608/ace_tui_responsiveness.md`; its evidence base is the research report
> `research:202608/ace_refresh_loop_and_link_rail_regression/ace_refresh_loop_and_link_rail_regression.md`.
> The phase is measurement-gated and crosses the Rust core boundary. Open `sase-core` with
> `/sase_repo` and use only the path it prints.
> The current tree has two load-bearing facts that the implementation must address:
> - `AgentsViewport` already defines a prefix window

*See full plan file for details.*

