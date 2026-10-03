- **AGENTS:**
  - [bbugyi200.athena.research.3g.cld](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.research.3g.cld/README.md)

%id(cld, clan=research.3g) %m:claude/opus@xhigh %q(1.5x, w=0.25) #gh:gh_sase-org__sase
You are researcher cld in a 5-researcher swarm. The other researchers,
`research.3g.cdx`, `research.3g.grk`, `research.3g.mus`, `research.3g.gem`, are
independently investigating the same request and will write their own self-named reports
ending in `__cdx.md` and `__grk.md` and `__mus.md` and `__gem.md`. Your report will end
in `__cld.md`.

Conduct your research independently and form your own conclusions. Do NOT attempt to
locate, open, read, or otherwise consult the other researcher's report from this swarm,
even if it becomes available before you finish. Do not obtain that peer's findings
indirectly through its chat transcript, summaries, or requests to the peer. You may
independently use the same external sources, shared input material, and unrelated prior
research. You may check filenames or file existence to avoid overwriting your own
output, but do not inspect the peer's report contents. If you encounter its filename,
leave the report alone. The lead researcher will read every report and synthesize their
findings after you have all finished.

I would like to add support to the Muse LLM provider for streaming its output.

- I'm pretty sure we used to support this but then fixed a related bug which caused Muse
  agent replies to be chunked poorly.
- Unfortunately, I don't think that reply streaming has worked for the Muse provider
  ever since.

Can you do some research with the goal of helping me decide the best way to implement
this? End your analysis with a recommended solution. #research(suffix=cld)
