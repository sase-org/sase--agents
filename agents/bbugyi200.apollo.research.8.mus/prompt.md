%id(mus, clan=research.8)
%m:muse/muse-spark-1.3-contributor@xhigh %q(w=0.25)
#gh:gh_sase-org__sase 
You are researcher mus in a 4-researcher swarm.
The other researchers, `research.8.cdx`, `research.8.cld`, `research.8.gem`, are independently investigating the same request and will write their own self-named reports ending in `__cdx.md` and `__cld.md` and `__gem.md`. Your report will end in `__mus.md`.

Conduct your research independently and form your own conclusions. Do NOT attempt to
locate, open, read, or otherwise consult the other researcher's report from this swarm,
even if it becomes available before you finish. Do not obtain that peer's findings
indirectly through its chat transcript, summaries, or requests to the peer. You may
independently use the same external sources, shared input material, and unrelated prior
research. You may check filenames or file existence to avoid overwriting your own
output, but do not inspect the peer's report contents. If you encounter its filename,
leave the report alone. The lead researcher will read every report and synthesize their
findings after you have all finished.

I want to add a new `"` keymap
to the "Agents" tab that opens a new panel which makes it very easy to navigate to any
node, regardless of whether or not it is show. We should be able to jump to hidden agent
session shells and hidden agent clan members, for example. Don't include agent shell
Bash/Python steps.

- This panel should have similar (but more powerful) functionality to the panel that is
  triggered by the backtick keymap in that hints will always be rendered next to nodes
  that the user can jump to by pressing the corresponding keys.
- This functionality will be more powerful in that we will support filtering the list
  (by node name) via a query input bar at the top of the panel.
- By default, the query input bar should not be selected (so the user can press hint
  keys). The `<tab>` keymap should be able to be used to focus the query input bar and
  then unfocus it again to press hint keys.
- The user should also be able to use the `<enter>` keymap to select (and jump to) the
  currently selected node.
- This panel should be large so we can show a good (but fast) preview of the currently
  selected node
- The user should be able to cycle through the nodes listed in the panel using the
  `<ctrl+n/p>` keymaps.
- #beau

Can you do some research with the goal of helping me decide the best way to implement
this? Also, critique this plan in general. Is this a good idea? Would you take a
different approach? Make any adjustments to the requirements that you think are
justified but clearly call these out. End your analysis with a recommended solution. #research(suffix=mus)