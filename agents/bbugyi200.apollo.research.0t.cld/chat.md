# Chat History - ace-run (research.0t.cld)

- **TIMESTAMP:** 2026-10-10 16:52:39 EDT
- **MODEL:** claude/opus
- **AGENT:** research.0t.cld
- **PROMPT:** `~/.sase/multi_prompts/202610/gh_sase_org__sase-multiprompt-261010_163712.md`

## Prompt

%id(cld, clan=research.0t)
%m:claude/opus@xhigh %q(1.5x, w=0.25)
#gh:gh_sase-org__sase 
You are researcher cld in a 5-researcher swarm.
The other researchers, `research.0t.cdx`, `research.0t.grk`, `research.0t.mus`, `research.0t.gem`, are independently investigating the same request and will write their own self-named reports ending in `__cdx.md` and `__grk.md` and `__mus.md` and `__gem.md`. Your report will end in `__cld.md`.

Conduct your research independently and form your own conclusions. Do NOT attempt to
locate, open, read, or otherwise consult the other researcher's report from this swarm,
even if it becomes available before you finish. Do not obtain that peer's findings
indirectly through its chat transcript, summaries, or requests to the peer. You may
independently use the same external sources, shared input material, and unrelated prior
research. You may check filenames or file existence to avoid overwriting your own
output, but do not inspect the peer's report contents. If you encounter its filename,
leave the report alone. The lead researcher will read every report and synthesize their
findings after you have all finished.

Can you do some research with the goal of finding the best, recent (<=1 year old)
articles related to agentic Software Engineering? Use your /bob_ref skill to make sure I
haven't already read any of the articles that you recommend. End your analysis with a
ranked list of articles that you think I should consider reading. 
Write this research to a new markdown file under the $(sase repo path research --ensure)/$(date +%Y%m)/ directory.
Choose a descriptive filename stem yourself, but the filename MUST end with the
`__cld` suffix, i.e. `<stem>__cld.md` (double underscore before the
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

Checked your reading library (~960 refs; heavy on harness engineering, context engineering, Claude Code, memory, and SDD). Now searching the web for agentic SE articles from Oct 2025 to Oct 2026.

Building the candidate pool (~40 so far, many July–Oct 2026). A few more targeted searches, then I'll batch-check them against your library and read the top ones in full.

Library check on 49 candidates: none are in your library yet (2 "possible" title hits turned out to be unrelated). Now reading the strongest candidates in parallel to confirm dates and content.

Content is now confirmed for about 45 finalists. Running the final library check against their exact URLs.

Report written. Now registering it as a durable artifact.

I wrote the report and registered it as an artifact. The host will commit it to the research repo when this turn ends.

**Report:** `sase/repos/research/202610/agentic_se_recent_reading_list__cld.md`
**Artifact:** `file:explicit:d7ab6ceb037b7ecdfee3a97e`, label `research:202610/agentic_se_recent_reading_list__cld.md`

Your library already has most of the well-known 2025–early-2026 material (the Anthropic and OpenAI harness posts, context engineering, Claude Code, spec-driven development, beads/Gas Town, memory papers). So the list leans toward mid/late-2026 sources you haven't saved. I opened and read every ranked item, or for papers the abstract plus intro, to confirm its URL, date and content.

**Top 10 of the 25 ranked picks:**
1. Armin Ronacher, "The Coming Loop" (Jun 2026). He separates the agent's own loop from an outer loop that decides when work continues, which maps directly onto SASE's single-turn agents.
2. Berkeley (Zaharia, Stoica et al.), "Reality Is the Final Verifier" (Sep 2026). It names two gaps no automated check can close: written requirements vs. what people actually want, and the test environment vs. the real world.
3. Birgitta Böckeler, "Harness engineering for coding agent users" (Apr 2026), plus her follow-up on "sensors" (automated feedback such as linters and tests).
4. Wang & Liu, "Software Engineering in the Agent Era" (Sep 2026). Agents produce changes and evidence but never gain the authority to accept them, close to SASE's host-owned completion.
5. Cursor, "Towards self-driving codebases" (Feb 2026). The most detailed public account of running hundreds of agents with planners and workers.
6. ETH Zürich, "Evaluating AGENTS.md" (v3 Sep 2026). Context files didn't raise task success and added more than 20% cost. This is the most decision-relevant paper for SASE's memory files.
7. Zalando, "Agentic Engineering at Zalando: a snapshot" (Aug 2026). Data from 250+ teams; a risk-based bot auto-approves 33% of PRs.
8. Annie Vella, "Verification Without Inspection" (Jul 2026).
9. Margaret-Anne Storey, "From Technical Debt to Cognitive and Intent Debt" (Mar 2026). "Intent debt" is what SASE's decision records pay down.
10. Nicholas Carlini, "Building a C compiler with a team of parallel Claudes" (Feb 2026).

Three picks you might not expect:
- **#15, Böckeler's "TDD inside the agent loop":** telling agents to write tests first cost 3–8× the tokens with no quality gain.
- **#19, three short papers on parallel agents:** they measure merge conflicts between agents and test ways to schedule around them, relevant to how SASE assigns workspaces.
- **#20, Ronacher's "Agent Psychosis":** includes a pointed critique of Beads, which SASE adopted.

**Gaps:**
- The OpenAI Codex agent-loop post blocked my fetcher, so I list it as unverified.
- I couldn't find the original Anthropic post on scaling CI for agents (only secondhand coverage), so I left it out.
- The Böckeler TDD piece shows no date; I placed it around August 2026 from its position in the series.

The report also lists seven on-topic items that are already queued in your library and worth moving up, led by Geoffrey Litt's "Understanding is the new bottleneck". It ends with ready-to-run `bob ref create` lines for the top 10.

Library check: 8 of 69 candidates already in your library (0 finished).
