- **AGENTS:**
  - [bbugyi200.athena.research.2y.cld](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.research.2y.cld/README.md)

%id(cld, clan=research.2y) %m:claude/opus@xhigh %q(1.5x, w=0.25) #gh:gh_sase-org**sase
You are researcher cld in a 5-researcher swarm. The other researchers,
`research.2y.cdx`, `research.2y.grk`, `research.2y.mus`, `research.2y.gem`, are
independently investigating the same request and will write their own self-named reports
ending in
`**cdx.md`and`**grk.md`and`**mus.md`and`**gem.md`. Your report will end in `**cld.md`.

Conduct your research independently and form your own conclusions. Do NOT attempt to
locate, open, read, or otherwise consult the other researcher's report from this swarm,
even if it becomes available before you finish. Do not obtain that peer's findings
indirectly through its chat transcript, summaries, or requests to the peer. You may
independently use the same external sources, shared input material, and unrelated prior
research. You may check filenames or file existence to avoid overwriting your own
output, but do not inspect the peer's report contents. If you encounter its filename,
leave the report alone. The lead researcher will read every report and synthesize their
findings after you have all finished.

We currently store too many prompts in prompt history (see the
~/tmp/screenshots/20260930_062115.png screenshot for an example of a prompt that likely
shouldn't have been stored).

- Namely, prompt history is meant to be used to store user prompts, each of which is
  supposed to correlate with a specific request made by a human being (by using the
  prompt input widget in the TUI or the `sase run` command to launch a sase agent, for
  example).
- Any prompt used to launch agents that belong to an xprompt swarm should not be saved
  to prompt history, but the prompt containing the xprompt swarm invokation
  (`#research_swarm`, for example) which was used by the user to launch the swarm should
  be saved to prompt history.
- Any prompt used to launch agents from routines should not be saved to prompt history.

Can you do some research with the goal of helping me decide the best way to implement
this? Also, critique this plan in general. Is this a good idea? Would you take a
different approach? Make any adjustments to the requirements that you think are
justified but clearly call these out. End your analysis with a recommended solution.
#research(suffix=cld)
