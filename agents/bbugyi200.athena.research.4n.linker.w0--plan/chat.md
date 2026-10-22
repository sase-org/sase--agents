# Chat History - ace-run (research.4n.linker.w0--plan)

- **TIMESTAMP:** 2026-10-16 12:34:26 EDT
- **MODEL:** claude/opus
- **AGENT:** research.4n.linker.w0--plan

**Plan:** /home/bryan/.sase/plans/202610/closed_bead_launch_attach.md


## Prompt

%auto
#gh:gh_sase-org__sase I would like to start making it fine for an agent to be launched using the `%id`
directive's `bead=<bead>` input even when `<bead>` is already closed. Can you help me
implement this?

- Currently, the sase agent just fails when this is the case which is annoying since I
  often restart sase agents using the `,x` keymap on the "Agents" tab after, for
  example, an error occurs that causes the agent to fail for some reason (sometimes the
  agent or the finalizer has already closed the bead at this point).
- We should make sure to add some kind of recognizable, timestamped note or annotation
  of some sort to the bead so there is a clear audit trail when we do this though.
- Review the closed_bead_agent_relaunch.md file in the research sidecar repo for context and inspiration
  before planning. I agree with all of the requirements recommended in that research
  file (but keep in mind that you are responsible for planning and splitting up this
  work appropriately).

Think this through thoroughly and create a plan using your `/sase_plan` skill. Choose and author the appropriate
tier, validate and revalidate until it passes, then submit it with `sase plan propose` (as the skill instructs)
before making any file changes.
 %m:@xlarge %w:research.4n.linker

## Response

*Plan submitted for review.*

**Plan file:** `/home/bryan/.sase/plans/202610/closed_bead_launch_attach.md`

> # Plan: Attach agent launches to beads that were already closed
> ## Background
> Today an agent launched with `%id(<name>, bead=<id>)` fails when `<id>` is closed. The
> only fatal check is sase-core's launch claim: `run_claim_launch` in
> `crates/sase_core/src/bead/mutation/claims.rs` returns
> `closed: cannot claim closed bead for agent launch: <id>`. It runs at the runner's
> single promotion checkpoint (`_promote_bead_claim` in
> `src/sase/axe/run_agent_runner_launch.py` → `claim_bead_for_agent_launch` in
> `src/sase/axe/run_agent_runner_bead.py` → `BeadProject.claim_for_agent_launch` →
> `bead_mutation_facade.claim_for_agent_launch` → the `bead_claim_for_agent_launch`

*See full plan file for details.*

