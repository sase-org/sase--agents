- **AGENTS:**
  - [bbugyi200.athena.research.3n.gem](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.research.3n.gem/README.md)

%id(gem, clan=research.3n) %m:agy/gemini-3.8-flash-high %q(1.5x, w=0.25)
#gh:gh_sase-org__sase You are researcher gem in a 5-researcher swarm. The other
researchers, `research.3n.cdx`, `research.3n.cld`, `research.3n.grk`, `research.3n.mus`,
are independently investigating the same request and will write their own self-named
reports ending in `__cdx.md` and `__cld.md` and `__grk.md` and `__mus.md`. Your report
will end in `__gem.md`.

Conduct your research independently and form your own conclusions. Do NOT attempt to
locate, open, read, or otherwise consult the other researcher's report from this swarm,
even if it becomes available before you finish. Do not obtain that peer's findings
indirectly through its chat transcript, summaries, or requests to the peer. You may
independently use the same external sources, shared input material, and unrelated prior
research. You may check filenames or file existence to avoid overwriting your own
output, but do not inspect the peer's report contents. If you encounter its filename,
leave the report alone. The lead researcher will read every report and synthesize their
findings after you have all finished.

I would like to migrate all existing agent instruction files to a single SASE.md file
that defines a spec for the agent instruction file that gets used to contruct the
appropirate agent instruction file dynamically in ephemeral workspaces before launching
sase agents in those workspaces.

- I think that this architecture change will allow us to fix a few bugs identified in
  the agent_instructions_budgeted_router.md file in the research sidecar repo (e.g. Grok
  reads both AGENTS.md and CLAUDE.md and codex doesn't read the ~/AGENTS.md file at
  all).
- Also, this would unlock the ability to specify that parts of the agent instruction
  file should only be rendered for certain agents. I'm not sure how we should identify
  these agents, but my first thought would be to use a new `%tag` directive to tag
  certain agents and then only render some parts of the agent instruction file for
  agents with certain tags. This is just my first instinct though. You should think hard
  about the best way to implement this.
- I think I'm probably forgetting a few other high-value use-cases (see if you can
  identify any that I missed).

Can you do some research with the goal of helping me decide the best way to implement
this? Also, critique this plan in general. Is this a good idea? Would you take a
different approach? Make any adjustments to the requirements that you think are
justified but clearly call these out. End your analysis with a recommended solution.
#research(suffix=gem)
