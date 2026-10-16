- **PLAN:**
  [202610/closed_bead_launch_attach.md](https://github.com/sase-org/sase--plans/blob/main/202610/closed_bead_launch_attach.md)
- **AGENTS:**
  - [bbugyi200.athena.research.4n.linker.w0--plan](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.research.4n.linker.w0.md)

I would like to start making it fine for an agent to be launched using the `%id`
directive's `bead=<bead>` input even when `<bead>` is already closed. Can you help me
implement this?

- Currently, the sase agent just fails when this is the case which is annoying since I
  often restart sase agents using the `,x` keymap on the "Agents" tab after, for
  example, an error occurs that causes the agent to fail for some reason (sometimes the
  agent or the finalizer has already closed the bead at this point).
- We should make sure to add some kind of recognizable, timestamped note or annotation
  of some sort to the bead so there is a clear audit trail when we do this though.
- Review the closed_bead_agent_relaunch.md file in the research sidecar repo for context
  and inspiration before planning. I agree with all of the requirements recommended in
  that research file (but keep in mind that you are responsible for planning and
  splitting up this work appropriately).

Think this through thoroughly and create a plan using your `/sase_plan` skill. Choose
and author the appropriate tier, validate and revalidate until it passes, then submit it
with `sase plan propose` (as the skill instructs) before making any file changes.
