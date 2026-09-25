#gh:gh_sase-org__sase Can you help me close as many obsolete open sase task beads as you can find?

- Make sure you close out each bead with an excellent reason note.
- Once you're done, produce an analysis of the beads that you closed and why and why it
  was inappropriate to close all of the other beads.
- Finally, use you /sase_pipe skill to launch a new agent that is instructed to:
  - Verify and improve this analysis.
  - Use their /sase_plan skill to design and implement solutions for the remaining open
    sase task beads. Make sure this agent explicitly lists which beads the agent(s)
    implementing the plan should close once their work is complete.
  - If any remaining sase task beads remain open, this agent should launch a new agent
    using their /sase_pipe skill that is instructed to:
    - Produce a short report on the remaining beads that answers the following
      questions:
      - Why are these task beads still open?
      - What was done, if anything, to attempt to close these task beads?
      - What needs to be done to resolve the issues corresponding with those beads and
        close them?
    - Write this research to a new markdown file under the 202608/ directory in the
      research sidecar repo.