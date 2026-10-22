# Chat History - ace-run (research.3q.cld)

- **TIMESTAMP:** 2026-10-06 11:07:40 EDT
- **MODEL:** claude/opus
- **AGENT:** research.3q.cld
- **PROMPT:** `~/.sase/multi_prompts/202610/gh_sase_org__sase-multiprompt-261006_104840.md`

## Prompt

%id(cld, clan=research.3q)
%m:claude/opus@xhigh %q(1.5x, w=0.25)
#gh:gh_sase-org__sase 
You are researcher cld in a 5-researcher swarm.
The other researchers, `research.3q.cdx`, `research.3q.grk`, `research.3q.mus`, `research.3q.gem`, are independently investigating the same request and will write their own self-named reports ending in `__cdx.md` and `__grk.md` and `__mus.md` and `__gem.md`. Your report will end in `__cld.md`.

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
`__cld` suffix, i.e. `<stem>__cld.md` (double underscore before the
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

I've read about 35 sources in full or in part. Now I'm measuring a couple of facts about sase's own instruction files to ground the recommendations, then I'll write the report.

Registration succeeded. Now the final declaration.

I've written the report, registered it as an artifact, and submitted the final declaration so the host commits it to the research repo.

- **Report:** `sase/repos/research/202610/memory_and_instruction_files_reading_list__cld.md`
- **Artifact:** created with label `research:202610/memory_and_instruction_files_reading_list__cld.md` (ref `file:explicit:bd3164d4dc1164ce1ea1f511`)

It ranks 30 pieces published between Oct 2025 and Oct 2026, mostly 2026 papers and engineering posts.

**What the research says, in short:**
- **Always-loaded instruction files rarely change whether tasks succeed, but they do change cost and behavior.** Context files added about 20% to cost with no significant success gain. What helps is information the agent can't find in the repo: hazards, prohibitions and conventions.
- **Prohibitions help and positive "do X" directives can hurt.** One large study found every individually helpful rule was a "don't", and every harmful one was a "do". Vercel found that "You MUST invoke the skill" made agents anchor on the skill and miss project context, which is close to sase's "MUST use `/skill_x` before Y" pattern.
- **Instruction files keep growing because nobody records why each rule exists, so nobody dares delete one.** Short hidden comments recording the failure that prompted each rule kept prompts near minimal size. sase's `decisions` web already does this for architecture; core directives and skill rules don't.
- **Out-of-date memory is the main way memory goes wrong.** The fixes being tried are mechanical: mapping notes to code paths, code citations checked before use, and marking facts invalid instead of deleting them.
- **Learning loops are settling on "propose, review, apply"** (Gemini CLI's memory inbox, Letta, Anthropic's memory consolidation, TRACE). Memory that agents write without a human gate tended to hurt.

**What I measured in sase today:**
- The generated `AGENTS.md` is 290 lines and about 2,550 words. The `decisions` index is about 35% of it and still lists 4 superseded records.
- For Claude agents in workspaces under `$HOME`, 543 of the 614 words in `~/CLAUDE.md` duplicate the project `CLAUDE.md`, so that text loads twice every turn.

**Read these first:**
1. [Why Does CLAUDE.md Keep Growing?](https://arxiv.org/html/2608.11095v1) — Chakrabarti, Aug 2026
2. [Evaluating AGENTS.md](https://arxiv.org/abs/2602.11988) — ETH Zürich, Feb 2026
3. [Guardrails Beat Guidance](https://arxiv.org/html/2604.11088v2) — AWS and HSBC, Apr–May 2026
4. [Coding Agents Love Decision Records](https://www.oreilly.com/radar/coding-agents-love-decision-records/) — Davidson, Oct 2026
5. [Skill Blocks](https://arxiv.org/html/2608.14943) — Microsoft, Aug 2026; when to load always vs on demand, accounting for prompt caching
6. [Codified Context](https://arxiv.org/html/2602.20478v1) — Feb 2026
7. [TRACE: compiling user corrections into enforcement](https://arxiv.org/html/2606.13174v1) — Jun 2026
8. [GitHub Copilot agentic memory](https://github.blog/ai-and-ml/github-copilot/building-an-agentic-memory-system-for-github-copilot/) — Jan 2026

The report also has a table of 14 improvement ideas, each linked to its sources.

**Caveats:**
- **Partly read sources:**
  - McMillan's factorial study: abstract only.
  - OpenAI's "Harness engineering" post: blocked my fetch, so it's summarized from search results.
  - Anthropic's "dreaming" feature: known only from news coverage.
- **Benchmarks:** most quantitative results come from coding benchmarks with one or two models, so they don't cover sase's orchestration rules (final declarations, gates, beads).
- **Emphasis:** no study directly tested MUST/NEVER capitalization, so that recommendation rests on Anthropic's guidance and practitioner evidence.
