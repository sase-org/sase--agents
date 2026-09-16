%id(cld, clan=research.1z) %m:@opus_or_grok %q(w=0.25)
#gh:gh_sase-org__sase You are researcher B in a two-researcher swarm. The other researcher,
`research.1z.cdx`, is independently investigating the same request and will write its
own self-named report ending in `__a.md`. Your report will end in `__b.md`.

Conduct your research independently and form your own conclusions. Do NOT attempt to
locate, open, read, or otherwise consult the other researcher's report from this swarm,
even if it becomes available before you finish. Do not obtain that peer's findings
indirectly through its chat transcript, summaries, or requests to the peer. You may
independently use the same external sources, shared input material, and unrelated prior
research. You may check filenames or file existence to avoid overwriting your own
output, but do not inspect the peer's report contents. If you encounter its filename,
leave the report alone. The lead researcher will read both reports and synthesize their
findings after you have both finished.

I want to add a new `%sink`
directive that acts like the `%wait` directive, but in reverse (i.e. the target agents
wait for the agent that specified the `%sink` directive in its prompt).

- This directive should have inputs that allow for a robust selection of agents that
  should wait for the agent we are launching with corresponding completion in the prompt
  input widget and external editors (via LSP support).
  - We need to have the ability to target all currently waiting agents.
  - We need to have the ability to target all agents in a particular agent hood.
  - We need to have the ability to target specific sase agents by name.
  - We need a way to specify that any agents that matches the specified selection
    criteria (by the other inputs described above) which are launched after this agent
    should also wait for this agent to complete.
- This directive also needs to work with stand-alone procs (i.e. prompts that are
  submitted that just contain the `%proc` directive and a VCS xprompt workflow) in both
  directions (i.e. the `%sink` directive should be able to be used in stand-alone proc
  prompts to have other waitingg/queued agents and/or stand-alone procs to wait for it).
  This will be useful, for example, when I want to run some command in an ephemeral
  workspace for some sase project but need to wait until no sase agents are running /
  for a certain set of sase agents to finish running before running the command.
- Notably, no agent that is running (e.g. not WAITING or QUEUED) should be effected by
  (i.e. need to wait for or stop for) the agent/proc that specified the `%sink`
  directive in its prompt.

Can you do some research with the goal of helping me decide the best way to implement
this? As a part of your research you should critique the idea itself. Make any
modifications to the design/proposal that you think are objectively beneficial but
clearly call these out. End your analysis with a recommended solution. #research(suffix=b)