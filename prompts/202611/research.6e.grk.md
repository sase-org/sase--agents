- **AGENTS:**
  - [bbugyi200.apollo.research.6e.grk](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.research.6e.grk/README.md)

%id(grk, clan=research.6e) %m:grok/grok-4.6@xhigh %q(1.5x, w=0.25) #gh:gh_sase-org__sase
You are researcher grk in a 5-researcher swarm. The other researchers,
`research.6e.cdx`, `research.6e.cld`, `research.6e.mus`, `research.6e.gem`, are
independently investigating the same request and will write their own self-named reports
ending in `__cdx.md` and `__cld.md` and `__mus.md` and `__gem.md`. Your report will end
in `__grk.md`.

Conduct your research independently and form your own conclusions. Do NOT attempt to
locate, open, read, or otherwise consult the other researcher's report from this swarm,
even if it becomes available before you finish. Do not obtain that peer's findings
indirectly through its chat transcript, summaries, or requests to the peer. You may
independently use the same external sources, shared input material, and unrelated prior
research. You may check filenames or file existence to avoid overwriting your own
output, but do not inspect the peer's report contents. If you encounter its filename,
leave the report alone. The lead researcher will read every report and synthesize their
findings after you have all finished.

The decisions memory web for this project and the bob-cli project is taking up way too
much context for each sase agent. I would like to mitigate this somehow.

- These decisions should probably only be read by planner agents (i.e. agents that use
  the /sase_plan skill). Note, however, that we can not modify the /sase_plan skill
  directly with these instructions since it is used by all sase projects (most of which
  will not have this custom decisions memory web).
- It follows that we should stop rendering the full decisions roster in agent
  instruction bundles.
- The decisions memory is just a specific memory web though, which we should not add
  custom support for, so we need to be able to handle memory webs like this generically
  (i.e. for any memory web we want).
- The best solution I can think of is to configure the decisions memory so it stops
  rendering the roster and instead renders instructions that state that any agent that
  is writing a SASE plan (i.e. invoked the /sase_plan skill) MUST read the decisions
  memory roster. This "decisions memory roster" should be retrievable by running a
  `sase memory` command and should look a lot like the roster that is currently in the
  AGENTS.md file. I'm not sure if we have an appropriate `sase memory` command for this
  yet (if not, you should add one).
- We will need to make sure that we audit this memory web roster read and display it in
  the TUI in the appropriate place.
- As a part of this change, we should update the decisions memories appropriately for
  both of these projects (sase and bob-cli).
- #beau

Can you do some research with the goal of helping me decide the best way to implement
this? Also, critique this plan in general. Is this a good idea? Would you take a
different approach? Make any adjustments to the requirements that you think are
justified but clearly call these out. End your analysis with a recommended solution.
#research(suffix=grk)
