# Chat History - ace-run (research.42.mus)

- **TIMESTAMP:** 2026-10-08 16:43:29 EDT
- **MODEL:** muse/muse-spark-1.3-contributor
- **AGENT:** research.42.mus
- **PROMPT:** `~/.sase/multi_prompts/202610/gh_sase_org__sase-multiprompt-261008_163448.md`

## Prompt

%id(mus, clan=research.42)
%m:muse/muse-spark-1.3-contributor@xhigh %q(1.5x, w=0.25)
#gh:gh_sase-org__sase 
You are researcher mus in a 5-researcher swarm.
The other researchers, `research.42.cdx`, `research.42.cld`, `research.42.grk`, `research.42.gem`, are independently investigating the same request and will write their own self-named reports ending in `__cdx.md` and `__cld.md` and `__grk.md` and `__gem.md`. Your report will end in `__mus.md`.

Conduct your research independently and form your own conclusions. Do NOT attempt to
locate, open, read, or otherwise consult the other researcher's report from this swarm,
even if it becomes available before you finish. Do not obtain that peer's findings
indirectly through its chat transcript, summaries, or requests to the peer. You may
independently use the same external sources, shared input material, and unrelated prior
research. You may check filenames or file existence to avoid overwriting your own
output, but do not inspect the peer's report contents. If you encounter its filename,
leave the report alone. The lead researcher will read every report and synthesize their
findings after you have all finished.

I
need a way to reliably install sase from PyPI (i.e. prod) and from a dev/editable
install (which needs to include the appropriate sase-core checkout for that dev version)
using the `just` command.

- The `just install` command and other related `just install-*` commands are already
  used to install sase into a local virtual environment.
- These commands are necessary but their names are not intuitive. Can we rename them to
  `just install-venv` / `just install-venv-*`? This will likely require updating some
  memory files.
- This will allow us to add new `just install` and `just install-dev` commands to serve
  these roles.
- I want you to lead the design on this one. Make sure you design this feature so it is intuitive, reliable, and (last but not least) beautiful!

Can you do some research with the goal of helping me decide the best way to implement
this? Also, critique this plan in general. Is this a good idea? Would you take a
different approach? Make any adjustments to the requirements that you think are
justified but clearly call these out. End your analysis with a recommended solution. 
Write this research to a new markdown file under the $(sase repo path research --ensure)/$(date +%Y%m)/ directory.
Choose a descriptive filename stem yourself, but the filename MUST end with the
`__mus` suffix, i.e. `<stem>__mus.md` (double underscore before the
suffix). Create the report without overwrite: if the exact file already exists, pick a
different stem instead of replacing it.


After the write succeeds, register the report as a durable snapshot:

sase artifact create -p "<absolute-report-path>" -l "research:<repo-relative-report-path>"

Use the report's actual absolute path and its path relative to the research repo root
(for example `research:202609/topic__a.md`), including any subdirectory the steps above
put it in. Do not derive the label from the current month, the clock, or a guessed name.
Do not pass `--move`; the source stays in the research repo for later reorganization. If
registration itself fails, report that failure — do not report the research task as
fully complete.

## Response

Research complete.

**Top finding: the rename plan is a good idea and should be approved with four adjustments — the most important being that the new prod `just install` must target the uv tool environment, never the repo `.venv`, or the venv will stop reflecting its checkout.**

Report written to [just_install_prod_and_dev_design__mus.md](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/sase/repos/research/202610/just_install_prod_and_dev_design__mus.md) and registered as durable snapshot `file:explicit:842d60d78d61e657d0dba98a` (`research:202610/just_install_prod_and_dev_design__mus.md`).

Key points from the analysis (all verified against the Justfile, INSTALL.md, docs, and memory files):

- Rename surface is exactly three recipes (`install`, `install-visual`, `install-terminal-smoke`); private `_setup` edges are untouched, so `check`/`test`/`lint` keep working.
- Bare `install` is a **flag day** — no alias can bridge old and new meanings — so docs, memory files (`lint_and_test.md`, `symvision.md`, `guarded-recipes.md`), and Justfile-internal "rerun `just install`" strings must move atomically in one commit. The variant renames, unlike bare `install`, can keep deprecation wrappers.
- `just install-dev`'s "matching sase-core checkout" has a well-defined answer: the `sase-core-revision.txt` content at the requested sase ref; and it should delegate to the existing `sase update --to dev` mode-switch machinery rather than reimplementing it.
- New recipes stay outside the tool-run guard (per the guarded-recipes decision), and CI stays on `smoke/pypi`, never the new `just install`.

The report ends with a concrete five-step recommended solution.

Declaration submitted. Research report commit authorized for `sdd:research`; host will commit after this turn.
