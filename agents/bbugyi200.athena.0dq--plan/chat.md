# Chat History - ace-run (0dq--plan)

- **TIMESTAMP:** 2026-08-25 15:07:11 EDT
- **MODEL:** claude/opus
- **AGENT:** 0dq--plan

## Linked Chats

- **1. --plan** — `~/.sase/chats/202608/gh_sase_org__sase-ace_run-0dq__plan-260825_144810.md`
- 2. --code — `~/.sase/chats/202608/gh_sase_org__sase-ace_run-0dq__code-260825_144810.md`

**Plan:** /home/bryan/.sase/plans/202608/lazy_beads_sidecar.md


## Prompt

#gh:gh_sase-org__sase We currently auto-clone the beads sidecar repo by default. This is no longer necessary, however, since we should now do this automatically when a `sase bead` command is run that requires the beads repo (which is likely most of them), right? Can you help me verify my claims and then make sase workspace initialization faster by (if I'm right and this won't break anything) no longer auto-cloning the beads sidecar repo?

Think this through thoroughly and create a plan using your `/sase_plan` skill. Choose and author the appropriate
tier, validate and revalidate until it passes, then submit it with `sase plan propose` (as the skill instructs)
before making any file changes.
 %model:opus

## Response

*Plan submitted for review.*

**Plan file:** `/home/bryan/.sase/plans/202608/lazy_beads_sidecar.md`

> # Plan
> ## Problem
> Every launched agent in a numbered workspace currently pays for a full clone of the
> `<project>--beads` sidecar during workspace preparation, whether or not that agent ever
> touches a bead. The clone is unconditional because managed projects mark the `beads`
> sidecar `auto_clone: true`.
> That auto-clone predates on-demand materialization. It is no longer needed: the bead
> CLI, the agent-launch bead claim, and the artifact/plan surfaces all materialize the
> beads sidecar themselves when they need it.
> Measured on `sase-org/sase` at the time of writing:

*See full plan file for details.*

