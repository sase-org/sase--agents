- **AGENTS:**
  - [bbugyi200.athena.research.3b.mus](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.research.3b.mus/README.md)

%id(mus, clan=research.3b) %m:muse/muse-spark-1.3-contributor@xhigh %q(1.5x, w=0.25)
#gh:gh_sase-org__sase You are researcher mus in a 5-researcher swarm. The other
researchers, `research.3b.cdx`, `research.3b.cld`, `research.3b.grk`, `research.3b.gem`,
are independently investigating the same request and will write their own self-named
reports ending in `__cdx.md` and `__cld.md` and `__grk.md` and `__gem.md`. Your report
will end in `__mus.md`.

Conduct your research independently and form your own conclusions. Do NOT attempt to
locate, open, read, or otherwise consult the other researcher's report from this swarm,
even if it becomes available before you finish. Do not obtain that peer's findings
indirectly through its chat transcript, summaries, or requests to the peer. You may
independently use the same external sources, shared input material, and unrelated prior
research. You may check filenames or file existence to avoid overwriting your own
output, but do not inspect the peer's report contents. If you encounter its filename,
leave the report alone. The lead researcher will read every report and synthesize their
findings after you have all finished.

I would like to improve the "Agents" tab deck panel and the sase pager's split view
support (see the sase-1eg epic bead for context on the latter).

- We currently only support two views, each of which support just two panes: horizontal
  and vertical.
- I want to add a support for two additional views that each use three panes. Namely:
  - A horizontal split 3-pane view should be triggered when the `|` keymap is used if a
    horizontal split is already shown by splitting the currently focused pane
    vertically. Pressing `|` again should switch to the 3-pane view described in the
    bullet below. Alternatively, pressing `\` closes the larger horizontal pane which
    switches us to the 2-pane vertical view.
  - A vertical split 3-pane view should be triggered when the `\` keymap is used if a
    vertical split is already shown by splitting the currently focused pane
    horizontally. Pressing `\` again should switch to the 3-pane view described in the
    bullet above. Alternatively, pressing `|` closes the larger vertical pane which
    switches us to the 2-pane horizontal view.
- The `<ctrl+b>` keymap should be added that worked like the `<ctrl+f>` keymap (i.e.
  changes which pane is focused) but in the reverse direction.
- The new `<ctrl+shift+b/f>` keymaps should be added to give the user the ability to
  swap the current pane with the previous/next pane.
- A new `<ctrl+shift+d>` keymap should be added that deletes the current pane. This
  keymap should only be active when at least two panes are visible. We should still
  support switching back to a single-pane view when the `\` keymap is used but the
  2-pane horizontal view is already active or when the `|` keymap is used but the 2-pane
  vertical view is already active.
- #beau

Can you do some research with the goal of helping me decide the best way to implement
this? Also, critique this plan in general. Is this a good idea? Would you take a
different approach? Make any adjustments to the requirements that you think are
justified but clearly call these out. End your analysis with a recommended solution.
#research(suffix=mus)
