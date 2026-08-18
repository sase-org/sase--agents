# Chat History - ace-run (05e--plan)

- **TIMESTAMP:** 2026-08-17 18:52:24 EDT
- **MODEL:** claude/opus
- **AGENT:** 05e--plan

**Plan:** /home/bryan/.sase/plans/202608/epic_resume_gate.md


## Prompt

#gh:gh_sase-org__sase When an agent fails that is working a phase of an epic fails, it is often for a transient reason and the next agent will succeed. Also sometimes the agent actually completed its work so we just need to get the epic rolling again. See #sshot for an example of this. What I normally do to fix this is run the `sase bead work <epic_bead_id> -Y` command. Can you help me start sending a sase gate when this happens that offers the user a single option which runs that command, with `<epic_bead_id>` replaced with the appropriate epic bead's ID?

Think this through thoroughly and create a plan using your `/sase_plan` skill. Choose and author the appropriate
tier, validate and revalidate until it passes, then submit it with `sase plan propose` (as the skill instructs)
before making any file changes.


## Response

*Plan submitted for review.*

**Plan file:** `/home/bryan/.sase/plans/202608/epic_resume_gate.md`

> # Plan: Raise an EpicResume gate when a failed phase agent stalls an epic
> ## Why
> An epic launched by `sase bead work` runs its phases as one agent clan
> (`%clan(<epic_id>, tribe=epic)`). Every later phase waits on its predecessor by agent
> name (`%w:<agent>`) and by phase bead (`%w(bead=<id>)`), and the land agent waits on all
> of them. A phase agent that reaches outcome `failed` therefore never satisfies those
> waits: its siblings sit in `WAITING` forever and the epic makes no further progress.
> `sase_chop_wait_checks` already observes this exact condition — it logs
> `Terminal dependency still blocks waiter` — but nothing acts on it.
> Today the owner notices the stall by eye in ACE (a clan row like

*See full plan file for details.*

