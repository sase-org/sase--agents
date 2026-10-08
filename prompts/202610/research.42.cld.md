- **AGENTS:**
  - [bbugyi200.athena.research.42.cld](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.research.42.cld/README.md)

%id(cld, clan=research.42) %m:claude/opus@xhigh %q(1.5x, w=0.25) #gh:gh_sase-org__sase
You are researcher cld in a 5-researcher swarm. The other researchers,
`research.42.cdx`, `research.42.grk`, `research.42.mus`, `research.42.gem`, are
independently investigating the same request and will write their own self-named reports
ending in `__cdx.md` and `__grk.md` and `__mus.md` and `__gem.md`. Your report will end
in `__cld.md`.

Conduct your research independently and form your own conclusions. Do NOT attempt to
locate, open, read, or otherwise consult the other researcher's report from this swarm,
even if it becomes available before you finish. Do not obtain that peer's findings
indirectly through its chat transcript, summaries, or requests to the peer. You may
independently use the same external sources, shared input material, and unrelated prior
research. You may check filenames or file existence to avoid overwriting your own
output, but do not inspect the peer's report contents. If you encounter its filename,
leave the report alone. The lead researcher will read every report and synthesize their
findings after you have all finished.

I need a way to reliably install sase from PyPI (i.e. prod) and from a dev/editable
install (which needs to include the appropriate sase-core checkout for that dev version)
using the `just` command.

- The `just install` command and other related `just install-*` commands are already
  used to install sase into a local virtual environment.
- These commands are necessary but their names are not intuitive. Can we rename them to
  `just install-venv` / `just install-venv-*`? This will likely require updating some
  memory files.
- This will allow us to add new `just install` and `just install-dev` commands to serve
  these roles.
- #beau

Can you do some research with the goal of helping me decide the best way to implement
this? Also, critique this plan in general. Is this a good idea? Would you take a
different approach? Make any adjustments to the requirements that you think are
justified but clearly call these out. End your analysis with a recommended solution.
#research(suffix=cld)
