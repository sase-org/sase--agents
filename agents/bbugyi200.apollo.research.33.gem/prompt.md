%id(gem, clan=research.33)
%m:agy/gemini-3.8-flash-high %q(1.5x, w=0.25)
#gh:gh_sase-org__sase 
You are researcher gem in a 5-researcher swarm.
The other researchers, `research.33.cdx`, `research.33.cld`, `research.33.grk`, `research.33.mus`, are independently investigating the same request and will write their own self-named reports ending in `__cdx.md` and `__cld.md` and `__grk.md` and `__mus.md`. Your report will end in `__gem.md`.

Conduct your research independently and form your own conclusions. Do NOT attempt to
locate, open, read, or otherwise consult the other researcher's report from this swarm,
even if it becomes available before you finish. Do not obtain that peer's findings
indirectly through its chat transcript, summaries, or requests to the peer. You may
independently use the same external sources, shared input material, and unrelated prior
research. You may check filenames or file existence to avoid overwriting your own
output, but do not inspect the peer's report contents. If you encounter its filename,
leave the report alone. The lead researcher will read every report and synthesize their
findings after you have all finished.

I would like to add support for "hijacking" a stalled sase agent.

- An "agent hijack" (aka "hijack"--we should add a good new glossary term for this) is
  meant to describe the process of killing a sase agent without releasing its workspace
  or dismissing it.
- The agent node should then be rendered with the new "HIJACKED" status on the "Agents"
  tab.
- If the `<enter>` keymap is used when a "HIJACKED" agent is selected a new panel should
  be triggered that allows the user to select (with a single keypress) between one of
  the following options. Think hard about what other options (if any) this panel should
  support:
  - Restart the agent by dismissing it (and releasing its workspace) and relaunching it
    using the exact same prompt.
  - Dismiss (and release the workspace) and edit the agent prompt (similar to what the
    `,x` keymap does).
  - Escalate to a smarter model. We should use the `@xlarge` model alias if the `@large`
    model alias was used for the previous prompt; otherwise, we should use the `@large`
    model alias. We should NOT release the workspace in this case since the smarter
    model needs to have access to all of the previous agent's file changes.
- We may want to add support for one or more new sase config fields to support this new
  functionality, but I'll let you decide.
- #beau

Can you do some research with the goal of helping me decide the best way to implement
this? Also, critique this plan in general. Is this a good idea? Would you take a
different approach? Make any adjustments to the requirements that you think are
justified but clearly call these out. End your analysis with a recommended solution. #research(suffix=gem)