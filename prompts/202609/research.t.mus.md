- **AGENTS:**
  - [bbugyi200.apollo.research.t.mus](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.research.t.mus/README.md)

%id(mus, clan=research.t) %m:muse/muse-spark-1.3-contributor@xhigh %q(1.5x, w=0.25)
#gh:gh_sase-org**sase You are researcher mus in a 5-researcher swarm. The other
researchers, `research.t.cdx`, `research.t.cld`, `research.t.grk`, `research.t.gem`, are
independently investigating the same request and will write their own self-named reports
ending in
`**cdx.md`and`**cld.md`and`**grk.md`and`**gem.md`. Your report will end in `**mus.md`.

Conduct your research independently and form your own conclusions. Do NOT attempt to
locate, open, read, or otherwise consult the other researcher's report from this swarm,
even if it becomes available before you finish. Do not obtain that peer's findings
indirectly through its chat transcript, summaries, or requests to the peer. You may
independently use the same external sources, shared input material, and unrelated prior
research. You may check filenames or file existence to avoid overwriting your own
output, but do not inspect the peer's report contents. If you encounter its filename,
leave the report alone. The lead researcher will read every report and synthesize their
findings after you have all finished.

It is important that memory file changes are tracked, versioned, and easy to navigate /
understand. I would like to add support for this to sase.

- All agent instruction file changes and all memory file changes should be tracked. It's
  fine if we use git history for this to get this version-control data for free, but we
  need to be able to navigate between the different versions for each supported file
  very quickly (so we might need to create an index or something--think hard about the
  best way to solve this).
- I was thinking that we could add some sort of special support to sase's pager for
  memory files / agent instruction files and make that the main interface for navigating
  / viewing memory change history. Think hard about what the best UX for this looks
  like.
- #beau

Can you do some research with the goal of helping me decide the best way to implement
this? Also, critique this plan in general. Is this a good idea? Would you take a
different approach? Make any adjustments to the requirements that you think are
justified but clearly call these out. End your analysis with a recommended solution.
#research(suffix=mus)
