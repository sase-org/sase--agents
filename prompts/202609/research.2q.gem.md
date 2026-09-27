- **AGENTS:**
  - [bbugyi200.athena.research.2q.gem](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.research.2q.gem/README.md)

%id(gem, clan=research.2q) %m:agy/gemini-3.8-flash-high %q(1.5x, w=0.25)
#gh:gh_sase-org**sase You are researcher gem in a 5-researcher swarm. The other
researchers, `research.2q.cdx`, `research.2q.cld`, `research.2q.grk`, `research.2q.mus`,
are independently investigating the same request and will write their own self-named
reports ending in
`**cdx.md`and`**cld.md`and`**grk.md`and`**mus.md`. Your report will end in `**gem.md`.

Conduct your research independently and form your own conclusions. Do NOT attempt to
locate, open, read, or otherwise consult the other researcher's report from this swarm,
even if it becomes available before you finish. Do not obtain that peer's findings
indirectly through its chat transcript, summaries, or requests to the peer. You may
independently use the same external sources, shared input material, and unrelated prior
research. You may check filenames or file existence to avoid overwriting your own
output, but do not inspect the peer's report contents. If you encounter its filename,
leave the report alone. The lead researcher will read every report and synthesize their
findings after you have all finished.

I want to add support for dynamic sub-tabs to the "Agents" tab.

- We should add the `%tab:<tab_name>` directive to support this.
- If the `%tab` directive is not used explicitly in the prompt used to launch a sase
  agent, then we should default to launching that agent on a special "main" tab.
- If there is only one tab that has agents on it, then we should not show any tabs at
  all (i.e. keep the current behavior).
- Machine Tabs
  - We should add a new "machine tabs" glossary memory web term that describes this
    concept.
  - When remote machines are configured on the current machine, we should automatically
    show `local` instead of `main` for the main tab for agents that were launched on the
    current machine. For remote agents, we should automatically replace `main` with
    `<machine_name>` where `<machine_name>` is that machine's configured name.
  - A good icon should be rendered next to the machine tabs in the sub-tab title bar on
    the "Agents" tab (this includes "local").
  - Any agents that are launched with the `%tab:<tab_name>` directive should always use
    `<tab_name>` as their tab (on all machines). This will allow us to, for example,
    group all agents related to a particular project on a single tab regardless of which
    machine each agent ran on.
- We should not support an "ALL" sub-tab that shows all agents. Instead, we should
  modify the `o` option in the panel that is shown when the `o` keymap is used on the
  "Agents" tab. Namely, we should add support for a 3rd view that merges all tribes and
  all tabs (instead of just all tribes) into a single panel. This option should also
  support its current behavior (merge all tribes--but do not merge tabs) by cycling
  through the 3 views. We should also add a new `O` option that does the same thing as
  the `o` option but in the opposite direction.
- Some previous research can be found in the agent_machine_tabs_and_cluster_semantics.md
  file in the research sidecar repo. This research file should be reviewed before
  performing your own research. Note, however, that this research file focuses too much
  on the specific case of machine tabs, does not prioritize dynamic tabs, and is not
  ambitious enough overall.
- #beau

Can you do some research with the goal of helping me decide the best way to implement
this? Also, critique this plan in general. Is this a good idea? Would you take a
different approach? Make any adjustments to the requirements that you think are
justified but clearly call these out. End your analysis with a recommended solution.
#research(suffix=gem)
