#gh:gh_sase-org__sase I would like to start instructing the `#research_swarm` macro swarm's image agent
to consider whether or not the research file would benefit from one or more mermaid
diagrams to visually illustrate certain concepts. Can you help me implement this?

- If so, it should not modify the lead researcher's report or create its own report.
- Instead, we need a way for the image agent to create the appropriate mermaid diagrams
  and specify which parts of the research file they correspond with. Think hard about
  the best way to do this.
- The linker agent should then be responsible for integrating these mermaid diagrams (if
  the image agent chose to create any) into the final document.
- Review the research_swarm_mermaid_handoff_to_linker.md file in the research sidecar repo for context and inspiration
  before planning. I agree with all of the requirements recommended in that research
  file (but keep in mind that you are responsible for planning and splitting up this
  work appropriately).

#plan %m:@xlarge %auto %w:research.21.linker