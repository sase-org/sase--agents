- **AGENTS:**
  - [bbugyi200.apollo.research.g.mus](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.research.g.mus/README.md)

%id(mus, clan=research.g) %m:muse/muse-spark-1.3-contributor@xhigh %q(1.5x, w=0.25)
#gh:gh_sase-org**sase You are researcher mus in a 4-researcher swarm. The other
researchers, `research.g.cdx`, `research.g.grk`, `research.g.gem`, are independently
investigating the same request and will write their own self-named reports ending in
`**cdx.md`and`**grk.md`and`**gem.md`. Your report will end in `__mus.md`.

Conduct your research independently and form your own conclusions. Do NOT attempt to
locate, open, read, or otherwise consult the other researcher's report from this swarm,
even if it becomes available before you finish. Do not obtain that peer's findings
indirectly through its chat transcript, summaries, or requests to the peer. You may
independently use the same external sources, shared input material, and unrelated prior
research. You may check filenames or file existence to avoid overwriting your own
output, but do not inspect the peer's report contents. If you encounter its filename,
leave the report alone. The lead researcher will read every report and synthesize their
findings after you have all finished.

I want to make it easier to set file hooks for artifact files by using a more robust and
reliable approach to matching artifact files.

- I was thinking that we could maybe achieve this by having the `#research` xprompt set
  an environment variable by default.
- We would need to support an override for this as well (e.g. by adding a new input
  argument to the `#research` xprompt) to not set this environment variable in some
  cases (we will need to set this override for all of the researcher agents that run
  before the lead researcher agent in the `#research_swarm` xprompt swarm, for example).

Can you do some research with the goal of helping me decide the best way to implement
this? Also, critique this plan in general. Is this a good idea? Would you take a
different approach? Make any adjustments to the requirements that you think are
justified but clearly call these out. End your analysis with a recommended solution.
#research(suffix=mus)
