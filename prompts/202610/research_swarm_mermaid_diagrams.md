- **PLAN:**
  [202610/research_swarm_mermaid_diagrams.md](https://github.com/sase-org/sase--plans/blob/main/202610/research_swarm_mermaid_diagrams.md)
- **AGENTS:**
  - [bbugyi200.apollo.research.21.linker.w0--plan](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.research.21.linker.w0.md)

I would like to start instructing the `#research_swarm` macro swarm's image agent to
consider whether or not the research file would benefit from one or more mermaid
diagrams to visually illustrate certain concepts. Can you help me implement this?

- If so, it should not modify the lead researcher's report or create its own report.
- Instead, we need a way for the image agent to create the appropriate mermaid diagrams
  and specify which parts of the research file they correspond with. Think hard about
  the best way to do this.
- The linker agent should then be responsible for integrating these mermaid diagrams (if
  the image agent chose to create any) into the final document.
- Review the research_swarm_mermaid_handoff_to_linker.md file in the research sidecar
  repo for context and inspiration before planning. I agree with all of the requirements
  recommended in that research file (but keep in mind that you are responsible for
  planning and splitting up this work appropriately).

Think this through thoroughly and create a plan using your `/sase_plan` skill. Choose
and author the appropriate tier, validate and revalidate until it passes, then submit it
with `sase plan propose` (as the skill instructs) before making any file changes.
