- **AGENTS:**
  - [bbugyi200.athena.research.3l.gem](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.research.3l.gem/README.md)

%id(gem, clan=research.3l) %m:agy/gemini-3.8-flash-high %q(1.5x, w=0.25)
#gh:gh_sase-org__sase You are researcher gem in a 4-researcher swarm. The other
researchers, `research.3l.cdx`, `research.3l.cld`, `research.3l.grk`, are independently
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

Can you help me dig into the research sidecar repo for all research swarms that Gemini
models contributed to (the files they produced end with `__gem.md`) and find ones (if
any) where Gemini provided unique insights that the other models in the swarm did not
that were actually included in the final research report? End your analysis with a list
of those research files and a summary of what unique contributions Gemini made to them.
#research(suffix=gem)
