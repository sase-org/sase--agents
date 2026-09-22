- **AGENTS:**
  - [bbugyi200.athena.research.28.gem](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.research.28.gem/README.md)

%id(gem, clan=research.28) %m:agy/gemini-3.8-flash-high %q(w=0.25) #gh:gh_sase-org**sase
You are researcher gem in a 3-researcher swarm. The other researchers,
`research.28.cld`, `research.28.mus`, are independently investigating the same request
and will write their own self-named reports ending in
`**cld.md`and`**mus.md`. Your report will end in `**gem.md`.

Conduct your research independently and form your own conclusions. Do NOT attempt to
locate, open, read, or otherwise consult the other researcher's report from this swarm,
even if it becomes available before you finish. Do not obtain that peer's findings
indirectly through its chat transcript, summaries, or requests to the peer. You may
independently use the same external sources, shared input material, and unrelated prior
research. You may check filenames or file existence to avoid overwriting your own
output, but do not inspect the peer's report contents. If you encounter its filename,
leave the report alone. The lead researcher will read every report and synthesize their
findings after you have all finished.

We recently implemented the `sase tool` command, which is just the first part of a
larger plan (see the sase_tool_epic_roadmap.md file in the research sidecar repo and the
sase-135 epic bead for context). I'm thinking about taking the next steps on this.
Here's what I'm thinking that those next steps should be:

- Add support for smoe way of enforcing that sase agents always use the `sase tool`
  command for certain commands. I want you to lead the design on this one, but one
  possible solution would be to implement a new `sase tool ensure-not-agent` command
  that commands (like the `just check` command, for example) could call at the start of
  their logic. This command could then fail if it detects a sase agent. Whatever
  solution we go with, make sure that sase agents are able to override this somehow (in
  case, for example, the `sase tool` command is broken).
- We should start making sase monitors wrap the command they run with the `sase tool`
  command. This should be possible since the `sase tool` command should be able to run
  any arbitrary command (you might need to implement this).

Can you do some research with the goal of helping me decide the best way to implement
this? Also, critique this plan in general. Is this a good idea? Would you take a
different approach? Make any adjustments to the requirements that you think are
justified but clearly call these out. End your analysis with a recommended solution.
#research(suffix=gem)
