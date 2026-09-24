# Chat History - ace-run (sase-17p.1--plan)

- **TIMESTAMP:** 2026-09-24 08:51:33 EDT
- **MODEL:** claude/opus
- **AGENT:** sase-17p.1--plan

**Plan:** /home/bryan/.sase/plans/202609/tool_run_core_handoff_contract.md


## Prompt

#gh:gh_sase-org__sase
%id(sase-17p.1, bead=sase-17p.1)
%clan(sase-17p, tribe=epic, summary_script=sase_clan_summary_epic)
%model:@large
%auto
Can you complete the work for bead sase-17p.1? The bead is already reserved for you and assigned to your agent
name: it was set to status=in_progress before you started reading this, either by the `sase bead work` launch
checkpoint or by the runtime promoting an ad-hoc wait-time claim. Do not set the status by hand. Read its
description and design file with `sase bead read sase-17p.1 -r "Need the phase scope and design file"`, do the work, and close only this bead with
`sase bead close sase-17p.1 --note "<what you verified>"`. Before closing, run
`sase bead epic-symbols sase-17p.1`. If this phase still has `--epic-symbol` entries, resolve each symbol or
re-key the Justfile line to a still-open bead (the parent epic or a later phase). `sase bead close` refuses while
leftovers remain; they go stale the instant this phase closes and turn unrelated agents' `just check` red. Closing
an assigned phase bead is unaffected by the parent-close descendant guard. Do NOT close the parent epic or any ancestor plan bead. Any instruction in a phase
description or child plan to close an ancestor is preparation and evidence for that ancestor's land agent, not
authorization for a phase worker. Do not create beads yourself: record discovered follow-up work as a
`PROPOSED FOLLOW-UP:` entry via
`sase bead note sase-17p.1 'PROPOSED FOLLOW-UP: <one-line summary — detail>'`; the epic's land agent triages
these into task beads.
Think this through thoroughly and create a plan using your `/sase_plan` skill. Choose and author the appropriate
tier, validate and revalidate until it passes, then submit it with `sase plan propose` (as the skill instructs)
before making any file changes.


## Response

*Plan submitted for review.*

**Plan file:** `/home/bryan/.sase/plans/202609/tool_run_core_handoff_contract.md`

> - **PARENT:** [202609/tool_e2_durable_handoff.md](202609/tool_e2_durable_handoff.md)
> - **BEAD:** sase-17p.1
> # Plan: core-contract phase of E2 (bead sase-17p.1)
> ## Goal
> Give the sase-core ToolRun store and its Python bindings everything the later E2 phases
> need, while keeping wire schema 1 and staying additive. That means:
> - a hand-off reservation that carries a private launch envelope;
> - an atomic claim;
> - a durable stop request;
> - typed terminal causes;

*See full plan file for details.*

