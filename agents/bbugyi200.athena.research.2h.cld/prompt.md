#gh:gh_sase-org__sase %id(cld, clan=research.2h)
%m:claude/opus@xhigh %q(w=0.25)

You are researcher cld in a 3-researcher swarm.
The other researchers, `research.2h.mus`, `research.2h.gem`, are independently investigating the same request and will write their own self-named reports ending in `__mus.md` and `__gem.md`. Your report will end in `__cld.md`.

Conduct your research independently and form your own conclusions. Do NOT attempt to
locate, open, read, or otherwise consult the other researcher's report from this swarm,
even if it becomes available before you finish. Do not obtain that peer's findings
indirectly through its chat transcript, summaries, or requests to the peer. You may
independently use the same external sources, shared input material, and unrelated prior
research. You may check filenames or file existence to avoid overwriting your own
output, but do not inspect the peer's report contents. If you encounter its filename,
leave the report alone. The lead researcher will read every report and synthesize their
findings after you have all finished.

I think I want to make the command
pallette trigger via the `;` keymap only and use the `:` keymap to trigger a new
"command-mode" panel that allows users to run `sase` commands directly from the TUI.

- The goal would be to give the user much better completion than the command-line ever
  could without ever needing to leave the TUI.
- We should default to showing the output of the command inline in the command-mode
  panel, but the user should also be able to leave the command-mode panel since the
  command should be run as a proc (which can be viewed on the "Procs" tab of the "SASE
  Admin Center" panel).
- #beau

Can you do some research with the goal of helping me decide the best way to implement
this? Also, critique this plan in general. Is this a good idea? Would you take a
different approach? Make any adjustments to the requirements that you think are
justified but clearly call these out. End your analysis with a recommended solution. #research(suffix=cld)