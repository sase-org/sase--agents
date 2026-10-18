- **AGENTS:**
  - [bbugyi200.apollo.research.21.gem](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.research.21.gem/README.md)

%id(gem, clan=research.21) %m:agy/gemini-3.8-flash-high %q(1.5x, w=0.25)
#gh:gh_sase-org__sase You are researcher gem in a 4-researcher swarm. The other
researchers, `research.21.cdx`, `research.21.cld`, `research.21.grk`, are independently
investigating the same request and will write their own self-named reports ending in
`__cdx.md` and `__cld.md` and `__grk.md`. Your report will end in `__gem.md`.

Conduct your research independently and form your own conclusions. Do NOT attempt to
locate, open, read, or otherwise consult the other researcher's report from this swarm,
even if it becomes available before you finish. Do not obtain that peer's findings
indirectly through its chat transcript, summaries, or requests to the peer. You may
independently use the same external sources, shared input material, and unrelated prior
research. You may check filenames or file existence to avoid overwriting your own
output, but do not inspect the peer's report contents. If you encounter its filename,
leave the report alone. The lead researcher will read every report and synthesize their
findings after you have all finished.

I would like to start instructing the `#research_swarm` macro swarm's image agent to
consider whether or not the research file would benefit from one or more mermaid
diagrams to visually illustrate certain concepts.

- If so, it should not modify the lead researcher's report or create its own report.
- Instead, we need a way for the image agent to create the appropriate mermaid diagrams
  and specify which parts of the research file they correspond with. Think hard about
  the best way to do this.
- The linker agent should then be responsible for integrating these mermaid diagrams (if
  the image agent chose to create any) into the final document.

Can you do some research with the goal of helping me decide the best way to implement
this? Also, critique this plan in general. Is this a good idea? Would you take a
different approach? Make any adjustments to the requirements that you think are
justified but clearly call these out. End your analysis with a recommended solution.
#research(suffix=gem)
