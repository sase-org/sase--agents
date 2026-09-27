- **AGENTS:**
  - [bbugyi200.apollo.research.h.cdx](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.research.h.cdx/README.md)

#gh:gh_sase-org__sase %id(cdx, clan=research.h) %m:codex/gpt-5.6-sol@xhigh %q(1.5x,
w=0.25)

You are researcher cdx in a 5-researcher swarm. The other researchers, `research.h.cld`,
`research.h.grk`, `research.h.mus`, `research.h.gem`, are independently investigating
the same request and will write their own self-named reports ending in `__cld.md` and
`__grk.md` and `__mus.md` and `__gem.md`. Your report will end in `__cdx.md`.

Conduct your research independently and form your own conclusions. Do NOT attempt to
locate, open, read, or otherwise consult the other researcher's report from this swarm,
even if it becomes available before you finish. Do not obtain that peer's findings
indirectly through its chat transcript, summaries, or requests to the peer. You may
independently use the same external sources, shared input material, and unrelated prior
research. You may check filenames or file existence to avoid overwriting your own
output, but do not inspect the peer's report contents. If you encounter its filename,
leave the report alone. The lead researcher will read every report and synthesize their
findings after you have all finished.

We currently support collapsing the nav sidebar on the "Agents" tab via the `<ctrl+s>`
keymap.

- We also support zooming in on a single deck using the `Z` keymap, in which case the
  sidebar is also collapsed.
- When the sidebar is collapsed, it is completely invisible currently.
- This is the correct behavior when zoomed, but should not be the default format used
  when collapsing the sidebar using the `<ctrl+s>` keymap.
- Instead, every tribe, agent group (e.g. "Running"), and node should be represented
  still, just in a collapsed, fixed width state.
- I'm thinking we can use some of the icons we already support (and maybe add a few more
  if needed--for example, I'm not sure if every type of agent group has a corresponding
  icon) to accomplish this, but you should decide. Think hard about what the best UX for
  this is.
- As a part of this change, let's make it clearer (in a visually appealing way) when a
  deck is zoomed (so the user can't mistakenly think the sidebar is just collapsed).
- #beau

Can you do some research with the goal of helping me decide the best way to implement
this? Also, critique this plan in general. Is this a good idea? Would you take a
different approach? Make any adjustments to the requirements that you think are
justified but clearly call these out. End your analysis with a recommended solution.
#research(suffix=cdx)
