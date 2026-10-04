# Chat History - ace-run (research.02.mus)

- **TIMESTAMP:** 2026-10-02 11:08:05 EDT
- **MODEL:** muse/muse-spark-1.3-contributor
- **AGENT:** research.02.mus
- **PROMPT:** `~/.sase/multi_prompts/202610/gh_sase_org__sase-multiprompt-261002_110156.md`

## Prompt

%id(mus, clan=research.02)
%m:muse/muse-spark-1.3-contributor@xhigh %q(1.5x, w=0.25)
#gh:gh_sase-org__sase 
You are researcher mus in a 5-researcher swarm.
The other researchers, `research.02.cdx`, `research.02.cld`, `research.02.grk`, `research.02.gem`, are independently investigating the same request and will write their own self-named reports ending in `__cdx.md` and `__cld.md` and `__grk.md` and `__gem.md`. Your report will end in `__mus.md`.

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
would love to be able to reduce this project's agent instruction files down to <=100
lines. Sase has pretty good support for progressive disclosure with memory files
already.

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

Done. Report written and registered as a durable snapshot.

- Report: `sase/repos/research/202610/agent_instruction_line_budget__mus.md` (~9KB), artifact ref `file:explicit:582e4b0c7fe09cb370f49088`.
- Top finding: ≤100 lines is feasible (~87-line sketch budget) but lines are a proxy — restate as ≤100 lines / ~1,600 tokens **plus** reference-read compliance from the existing memory audit log staying at baseline. The waste is entirely in the always-loaded index surface (decisions roster ~90 lines, cross-repo policy ~33, glossary enumeration ~18); reference-note bodies are already pay-per-read and should not be touched.
- Key adjustments: measure full-turn context share first (AGENTS.md's ~4.3k tokens may be dwarfed by harness/skill-schema context); replace the decisions roster with top-5-inline plus a list-view read mode rather than a dead pointer; implement the cut in the `src/sase/amd/` generator (noting `AGENTS.minimal.template.md` already exists); add a CI size-gate test since none exists today.

Declaration submitted for the research report commit.
