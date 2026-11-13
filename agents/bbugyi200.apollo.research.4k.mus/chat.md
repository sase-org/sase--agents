# Chat History - ace-run (research.4k.mus)

- **TIMESTAMP:** 2026-11-13 17:52:36 EST
- **MODEL:** muse/muse-spark-1.3-contributor
- **AGENT:** research.4k.mus
- **PROMPT:** `~/.sase/multi_prompts/202611/gh_sase_org__sase-multiprompt-261113_174022.md`

## Prompt

%id(mus, clan=research.4k)
%m:muse/muse-spark-1.3-contributor@xhigh %q(1.5x, w=0.25)
#gh:gh_sase-org__sase 
You are researcher mus in a 5-researcher swarm.
The other researchers, `research.4k.cdx`, `research.4k.cld`, `research.4k.grk`, `research.4k.gem`, are independently investigating the same request and will write their own self-named reports ending in `__cdx.md` and `__cld.md` and `__grk.md` and `__gem.md`. Your report will end in `__mus.md`.

Conduct your research independently and form your own conclusions. Do NOT attempt to
locate, open, read, or otherwise consult the other researcher's report from this swarm,
even if it becomes available before you finish. Do not obtain that peer's findings
indirectly through its chat transcript, summaries, or requests to the peer. You may
independently use the same external sources, shared input material, and unrelated prior
research. You may check filenames or file existence to avoid overwriting your own
output, but do not inspect the peer's report contents. If you encounter its filename,
leave the report alone. The lead researcher will read every report and synthesize their
findings after you have all finished.

I would like to add support to sase for Google's new Argon and Hydrogen models.

- We should update all model completion surfaces to include these models.
- As a part of this change, we should update the `#research_swarm` macro to use the new
  Hydrogen model instead of the current Gemini model that we use for that macro swarm.

Can you do some research with the goal of helping me decide the best way to implement
this? End your analysis with a recommended solution. 
Write this research to a new markdown file under the $(sase repo path research --ensure)/$(date +%Y%m)/ directory.
Choose a descriptive filename stem yourself, but the filename MUST end with the
`__mus` suffix, i.e. `<stem>__mus.md` (double underscore before the
suffix). Create the report without overwrite: if the exact file already exists, pick a
different stem instead of replacing it.


After the write succeeds, register the report as a durable snapshot:

sase artifact create -p "<absolute-report-path>" -l "research:<repo-relative-report-path>"

Use the report's actual absolute path and its path relative to the research repo root
(for example
`research:202609/topic__a.md`),
including any subdirectory the steps above put it in. Do not derive the label from
the current month, the clock, or a guessed name.
Do not pass `--move`; the source stays in the research repo for later reorganization. If
registration itself fails, report that failure — do not report the research task as
fully complete.

## Response

Research complete and declared. Report written and registered:

- Report: [argon_hydrogen_model_support__mus.md](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/sase/repos/research/202611/argon_hydrogen_model_support__mus.md)
- Snapshot: `file:explicit:e21aafd0dba21a5b916e17c3` (`research:202611/argon_hydrogen_model_support__mus.md`)
- Final declaration accepted for the research sidecar commit.

Key findings: Argon already shipped (commit `4d8940d4b7`, the template to mirror); live `agy models` confirms four new Hydrogen slugs (`gemini-4-hydrogen-{high,xhigh,medium,low}` — note the `xhigh` variant Argon lacks). Recommended solution: add the four slugs + `hydrogen4*` aliases + Ultra-gating advisory to `models.yml`, add `"hydrogen"` to `short_model_name`, regenerate docs via `just fix`, switch the swarm's `gemini_model` default to `agy/gemini-4-hydrogen-high` in the sidecar, update pinned test expectations, verify with `just check`. Open questions flagged: Hydrogen entitlement on non-Ultra accounts, `-high` vs `-xhigh` swarm default, and a possible stale chezmoi copy of the xprompt.
