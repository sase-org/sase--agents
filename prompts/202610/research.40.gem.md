- **AGENTS:**
  - [bbugyi200.athena.research.40.gem](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.research.40.gem/README.md)

%id(gem, clan=research.40) %m:agy/gemini-3.8-flash-high %q(1.5x, w=0.25)
#gh:gh_sase-org__sase You are researcher gem in a 5-researcher swarm. The other
researchers, `research.40.cdx`, `research.40.cld`, `research.40.grk`, `research.40.mus`,
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

I've been thinking that some of the builtin routines and/or jobs that exist currently
might be better suited as service procs. For example, wouldn't it be better if the
`wait_checks` job was instead a service proc that could wake up agents that are ready
sooner?

Can you do some research with the goal of recommending which jobs (if any) I should
migrate to service procs? Also, critique this plan in general. Is this a good idea?
Would you take a different approach? Make any adjustments to the requirements that you
think are justified but clearly call these out. End your analysis with a recommended
solution. #research(suffix=gem)
