- **AGENTS:**
  - [bbugyi200.apollo.research.1q.gem](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.research.1q.gem/README.md)

%id(gem, clan=research.1q) %m:agy/gemini-3.8-flash-high %q(1.5x, w=0.25)
#gh:gh_sase-org__sase You are researcher gem in a 5-researcher swarm. The other
researchers, `research.1q.cdx`, `research.1q.cld`, `research.1q.grk`, `research.1q.mus`,
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

I would like to add a new `sase project stats <project_name>` command, where
`<project_name>` is an optional sase project name, that produces useful stats about a
specific (or all if `<project_name>` is not specified) sase project.

- These numbers should include, but not be limited to (think hard about what stats would
  be genuinely useful to users): commit counts, line counts (for code files and docs),
  file counts (for code files and docs), length of time the project has been active.
- We should show numbers for all repos linked to the targeted project(s), but the stats
  should be separated by repo.
- We should support various formats that are useful to humans, agents, and scripts.
  Think hard about which formats to support and what the `sase project stats` command's
  output should look like for each format.
- This will be useful, for example, when gathering the numbers I plan on listing in
  sase's launch post (see the sase_launch_post_outline.md file in the research sidecar
  repo for context).
- #beau

Can you do some research with the goal of helping me decide the best way to implement
this? Also, critique this plan in general. Is this a good idea? Would you take a
different approach? Make any adjustments to the requirements that you think are
justified but clearly call these out. End your analysis with a recommended solution.
#research(suffix=gem)
