# Chat History - ace-run (research.36.mus)

- **TIMESTAMP:** 2026-10-01 12:20:32 EDT
- **MODEL:** muse/muse-spark-1.3-contributor
- **AGENT:** research.36.mus
- **PROMPT:** `~/.sase/multi_prompts/202610/gh_sase_org__sase-multiprompt-261001_120547.md`

## Prompt

%id(mus, clan=research.36)
%m:muse/muse-spark-1.3-contributor@xhigh %q(1.5x, w=0.25)
#gh:gh_sase-org__sase 
You are researcher mus in a 5-researcher swarm.
The other researchers, `research.36.cdx`, `research.36.cld`, `research.36.grk`, `research.36.gem`, are independently investigating the same request and will write their own self-named reports ending in `__cdx.md` and `__cld.md` and `__grk.md` and `__gem.md`. Your report will end in `__mus.md`.

Conduct your research independently and form your own conclusions. Do NOT attempt to
locate, open, read, or otherwise consult the other researcher's report from this swarm,
even if it becomes available before you finish. Do not obtain that peer's findings
indirectly through its chat transcript, summaries, or requests to the peer. You may
independently use the same external sources, shared input material, and unrelated prior
research. You may check filenames or file existence to avoid overwriting your own
output, but do not inspect the peer's report contents. If you encounter its filename,
leave the report alone. The lead researcher will read every report and synthesize their
findings after you have all finished.

: 
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

Done. The top finding: the swarm's researchers are five identical prompts, not a team — and the fix is mostly delegation, contracts, and evaluation, not new machinery.

I independently researched how to improve `#research_swarm` and wrote `202610/research_swarm_improvement_ideas__mus.md` (registered as `research:202610/research_swarm_improvement_ideas__mus.md`, snapshot ref `file:explicit:26f913956e7339f68fdebd03`). Evidence was gathered firsthand: the full 461-line template source, the swarm-expansion host code, reference memory, git history, prior swarm outputs (sizes/layout only), and Anthropic's multi-agent research system article as primary external grounding.

Key findings in the report:

- Researchers get the identical prompt with no division of labor, no method guidance, and no output contract; the lead absorbs all variance in one fat pass and fails closed if any report is missing.
- Verifiable history: the opt-in critique agent (commit `59fdf94`) was dropped accidentally in the `bf8deb9` re-scaffold, not deliberately retired.
- Ranked 10 improvements, topped by: assign distinct research angles per member, add a shared researcher charter plus output contract, restore the critique agent with lead disposition, degrade gracefully on missing reports, and build an LLM-judge eval loop so the rest can be measured.

Final declaration accepted for the research-repo commit; the turn ends here.
