# Chat History - ace-run (research.4c.mus)

- **TIMESTAMP:** 2026-10-13 09:13:16 EDT
- **MODEL:** muse/muse-spark-1.3-contributor
- **AGENT:** research.4c.mus
- **PROMPT:** `~/.sase/multi_prompts/202610/gh_sase_org__sase-multiprompt-261013_090356.md`

## Prompt

%id(mus, clan=research.4c)
%m:muse/muse-spark-1.3-contributor@xhigh %q(1.5x, w=0.25)
#gh:gh_sase-org__sase 
You are researcher mus in a 5-researcher swarm.
The other researchers, `research.4c.cdx`, `research.4c.cld`, `research.4c.grk`, `research.4c.gem`, are independently investigating the same request and will write their own self-named reports ending in `__cdx.md` and `__cld.md` and `__grk.md` and `__gem.md`. Your report will end in `__mus.md`.

Conduct your research independently and form your own conclusions. Do NOT attempt to
locate, open, read, or otherwise consult the other researcher's report from this swarm,
even if it becomes available before you finish. Do not obtain that peer's findings
indirectly through its chat transcript, summaries, or requests to the peer. You may
independently use the same external sources, shared input material, and unrelated prior
research. You may check filenames or file existence to avoid overwriting your own
output, but do not inspect the peer's report contents. If you encounter its filename,
leave the report alone. The lead researcher will read every report and synthesize their
findings after you have all finished.

It
is taking a very long time to startup sase's TUI on my apollo machine. Can you do help
me profile that machine and sase's startup? End your analysis with a ranked list of
changes you think I should consider making in order to improve the TUI's startup on that
machine (or in general). 
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

Top finding: your slow startup is host pressure plus data-scaled work, not first paint — fix the apollo gateway stampede first, then the startup data path.

I wrote [tui_startup_apollo_profile__mus.md](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_13/sase/repos/research/202610/tui_startup_apollo_profile__mus.md) and registered it as `research:202610/tui_startup_apollo_profile__mus.md` (artifact `explicit:d86ab6e4bb74b4590587b973`).

Measured on athena (same code): import ~2.5s with 3,517 modules, agents-ready 4–5s, axe-ready 8–9s, and 2.4–3.1s Python `prep` even for 3–6 rows. Apollo adds a 16-vCPU/no-swap host recently at load 13–560 with the gateway eating 6–11 cores. Full report has the profiling recipe and ten ranked fixes; the top ones are containing the gateway single-flight defect and its federation polling, guaranteeing bounded Tier-1 first paint, cutting per-row Python decode, trimming the import closure, and revalidating off the critical path.

Declaration accepted for commit. Report stands as filed.
