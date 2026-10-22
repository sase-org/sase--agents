# Chat History - ace-run (research.3q.grk)

- **TIMESTAMP:** 2026-10-06 10:59:59 EDT
- **MODEL:** grok/grok-4.6
- **AGENT:** research.3q.grk
- **PROMPT:** `~/.sase/multi_prompts/202610/gh_sase_org__sase-multiprompt-261006_104840.md`

## Prompt

%id(grk, clan=research.3q)
%m:grok/grok-4.6@xhigh %q(1.5x, w=0.25)
#gh:gh_sase-org__sase 
You are researcher grk in a 5-researcher swarm.
The other researchers, `research.3q.cdx`, `research.3q.cld`, `research.3q.mus`, `research.3q.gem`, are independently investigating the same request and will write their own self-named reports ending in `__cdx.md` and `__cld.md` and `__mus.md` and `__gem.md`. Your report will end in `__grk.md`.

Conduct your research independently and form your own conclusions. Do NOT attempt to
locate, open, read, or otherwise consult the other researcher's report from this swarm,
even if it becomes available before you finish. Do not obtain that peer's findings
indirectly through its chat transcript, summaries, or requests to the peer. You may
independently use the same external sources, shared input material, and unrelated prior
research. You may check filenames or file existence to avoid overwriting your own
output, but do not inspect the peer's report contents. If you encounter its filename,
leave the report alone. The lead researcher will read every report and synthesize their
findings after you have all finished.

I'm looking for some recent (published within the last year) articles that will inspire
me to improve sase's memory files and agent instruction files. Can you do some research
with the goal of finding the articles that are most likely to do that? End your analysis
with a ranked list of articles that you think I should consider reading. 
Write this research to a new markdown file under the $(sase repo path research --ensure)/$(date +%Y%m)/ directory.
Choose a descriptive filename stem yourself, but the filename MUST end with the
`__grk` suffix, i.e. `<stem>__grk.md` (double underscore before the
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

I'll research recent work on agent memory and instruction files independently, then write a `__grk` report and register it. First I'm loading the research, artifact, and memory skills plus the current SASE memory/instruction design so the recommendations actually fit this codebase.

I'm opening the research sidecar, reading SASE memory/artifact conventions, and checking how existing reports are structured so this one matches.

Research repo is open. Next I’ll inspect existing report format and current SASE memory/instruction files, then search 2025–2026 literature that maps onto those designs.

I’ll sample existing report style, scan 202610 for colliding `__grk` names, and start literature search on agent memory and instruction files.

I have the SASE memory model and report conventions. Next I’ll pull the primary papers and 2025–2026 industry writeups that actually speak to core vs reference memory, generated `AGENTS.md`, and authored links.

Primary sources next: I’ll read the AGENTS.md evaluation, ACE, Anthropic’s context-engineering notes, and the 2026 agent-memory survey so rankings rest on the papers themselves.

I’ll pull the remaining high-signal papers and the rest of the AGENTS.md evaluation so the ranking is based on primary findings, not summaries.

I have enough primary sources and a clear map onto SASE’s core/reference/web split. Next I’ll write the `__grk` report, then register it as a durable artifact.

The report is on disk. I’ll register it as a durable snapshot, then submit the final declaration.

Independent report is in `research:202610/sase_memory_instruction_file_inspiration__grk.md` (artifact `file:explicit:6c5089e0b7a11d511f37dfab`). I did not read the other swarm reports.

SASE already has the right shape: core vs reference vs webs vs generated skills vs authored `[[links]]` vs immutable decisions. The last year’s literature pushes on **budget, placement, and evolution**. Generated `AGENTS.md` is 290 lines; Anthropic’s 2026 CLAUDE.md heuristic is under 200. The expensive always-on pieces are the decisions roster and the glossary dump, not the small core notes.

Read these first:

1. **Gloaguen et al., Evaluating AGENTS.md** (arXiv:2602.11988, Feb–Sep 2026) — instruction files are followed, so extra lines raise cost ~20% and often do not raise success. Skip LLM-generated files and repository overviews; keep only non-standard practices.
2. **Anthropic, Steering Claude Code** (18 Jun 2026) — facts in a small always-on file, procedures in skills, “never” in hooks. CLAUDE.md under 200 lines, with an owner.
3. **Shihipar, New rules of context engineering for Claude 5** (24 Jul 2026) — they deleted 80% of Claude Code’s system prompt with no eval loss. Judgement over rules; progressive disclosure over encyclopedias; gotchas over filesystem tours.
4. **Zhang/Hu et al., ACE** (arXiv:2510.04618, ICLR 2026) — grow memory by incremental bullets; full rewrites collapse. Keep SASE decisions immutable; put learned tactics in a separate delta-updated playbook.

Then: Anthropic’s Sep 2025 context-engineering essay, the MSR 2026 OSS `AGENTS.md` taxonomy, the Aug 2026 agent-memory survey, Git Context Controller, Context-as-a-Tool, the Agent Skills spec, Memory-as-Action, and Coding Agent Memory Post-training.

The full ranked list, SASE mappings, and skip list are in the report.
