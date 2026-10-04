# Chat History - ace-run (research.w.cld)

- **TIMESTAMP:** 2026-09-30 18:58:56 EDT
- **MODEL:** claude/opus
- **AGENT:** research.w.cld
- **PROMPT:** `~/.sase/multi_prompts/202609/gh_sase_org__sase-multiprompt-260930_183649.md`

## Prompt

%id(cld, clan=research.w)
%m:claude/opus@xhigh %q(1.5x, w=0.25)
#gh:gh_sase-org__sase 
You are researcher cld in a 5-researcher swarm.
The other researchers, `research.w.cdx`, `research.w.grk`, `research.w.mus`, `research.w.gem`, are independently investigating the same request and will write their own self-named reports ending in `__cdx.md` and `__grk.md` and `__mus.md` and `__gem.md`. Your report will end in `__cld.md`.

Conduct your research independently and form your own conclusions. Do NOT attempt to
locate, open, read, or otherwise consult the other researcher's report from this swarm,
even if it becomes available before you finish. Do not obtain that peer's findings
indirectly through its chat transcript, summaries, or requests to the peer. You may
independently use the same external sources, shared input material, and unrelated prior
research. You may check filenames or file existence to avoid overwriting your own
output, but do not inspect the peer's report contents. If you encounter its filename,
leave the report alone. The lead researcher will read every report and synthesize their
findings after you have all finished.

One
of the best reads I've ever had related to sase was actually the SASE paper
(2509.06216). It has been a while since I've delved into relevant literature (e.g.
papers, articles) and I am curious as to what related progress has been made in the
industry over the last 6-12 monthes.

Can you do some research with the goal of recommending 10 high-value, recent papers
and/or articles on similar topics that I am likely to understand, appreciate, and learn
from? Prioritize quality over recency but do not recommend any papers or articles that
were published more than a year ago. 
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

Still gathering candidates. I've confirmed the SASE paper's framing (v3 was revised in June 2026) and am now checking recent papers and industry articles for fit and publication dates.

I've shortlisted about 40 recent candidates and checked the dates and key numbers for the top picks. Next I'll check a few more sources, then choose the final 10 and write the report.

The report is written. Before registering it, I'm checking two links I haven't confirmed yet.

The report is saved and registered. I'm submitting the commit declaration for the research repo now.

I've written the reading list and registered it as an artifact (`file:explicit:5c9552a0cae0fb30c76e8cce`). The host will commit the research repo after this turn.

**Report:** `sase/repos/research/202609/agentic_se_reading_list_since_sase_paper__cld.md`

Everything on the main list was first published between 2025-09-30 and 2026-09-30. I checked each pick's date and main numbers on the arXiv page or the original post. The one exception is the OpenAI post: openai.com blocked direct fetches, so its date and author come from secondary sources that agree with each other. Only #7 and #10 are confirmed peer-reviewed; the others are preprints or first-hand engineering write-ups.

**The 10 picks:**
1. **[OpenAI, *Harness engineering*](https://openai.com/index/harness-engineering/)** (Lopopolo, Feb 2026): about 1M lines of code with no hand-written lines. AGENTS.md is kept as a short "map, not a manual", rules are enforced by linters, and background agents clean up drift. Read this one if you read only one.
2. **[Davis et al., *MAGE*](https://arxiv.org/abs/2608.25174)** (Aug 2026): the paper most like the SASE paper. It's a framework built from constraints, sensors, validators and gates, backed by a 540k-line build with 6–8 parallel agents and six company case reports. It doesn't cite Hassan et al.
3. **[Anthropic, *Harness design for long-running apps*](https://www.anthropic.com/engineering/harness-design-long-running-apps)** (Mar 2026): separate planner, generator and evaluator agents, with acceptance criteria agreed before each round of work, and fresh contexts plus handoff files beating summarised ones. Read it with the shorter Nov 2025 post *Effective harnesses for long-running agents*.
4. **[Cursor, *Towards self-driving codebases*](https://cursor.com/blog/self-driving-codebases)** (Feb 2026): thousands of agents, with a frank record of what failed (shared locks, a central merge gate, one agent doing every role). Read it with Carlini's Feb 2026 post on building a C compiler with 16 parallel Claudes.
5. **[Tang et al., *How Coding Agents Fail Their Users*](https://arxiv.org/abs/2605.29442)** (May 2026): 20,574 real sessions. The top failures are agents breaking the developer's constraints (38%) and misreporting their own progress (23%), and both are growing.
6. **[Kim et al. (Google), *Scaling Agent Systems*](https://arxiv.org/abs/2512.08296)** (Dec 2025): once a single agent passes about 45% on a task, adding agents makes results worse. On SWE-bench Verified every multi-agent setup did worse than one agent. Independent agents multiplied errors 17.2×, versus 4.4× when one coordinator checked the work.
7. **[He et al. (CMU), *Speed at the Cost of Quality*](https://arxiv.org/abs/2511.04427)** (MSR '26): adopting Cursor gave a short-lived speed boost but lasting rises in code complexity (+42%) and warnings (+30%). A companion paper finds repos that commit their AI configuration roughly halve that quality cost.
8. **[METR, *Many SWE-bench-Passing PRs Would Not Be Merged*](https://metr.org/notes/2026-03-10-many-swe-bench-passing-prs-would-not-be-merged-into-main/)** (Mar 2026): maintainers approved about 24 points fewer PRs than the automated tests passed. Read it with *ImpossibleBench* (Oct 2025), which shows agents editing tests to make them pass.
9. **[Huang et al., *Professional Developers Don't Vibe, They Control*](https://arxiv.org/abs/2512.14012)** (Dec 2025): experienced developers steer agents with plan files, small steps and careful diff review. Read it with *ParallelPilot* (published 27 Sep 2026), the closest study yet of a command-centre tool for supervising parallel agents.
10. **[Edwards & Schuster, *Ask or Assume?*](https://arxiv.org/abs/2603.26233)** (EMNLP '26): the best evidence yet on when an agent should ask a human. A separate agent that spots missing information and asks early recovers almost all the accuracy lost to vague tasks. Read it with *HiL-Bench*.

**Also in the report:**
- A short summary of how the field changed over the year.
- A suggested reading order.
- What the SASE paper's authors published next, including a harness-evolution study, a benchmark-profiling paper and a Claude Code plugins study.
- About 15 honourable mentions.
- The papers I left out, and why: some predate the window, and some already appear in earlier sase research reports (e.g., *Evaluating AGENTS.md*, *Codified Context*).

The SASE paper itself was revised to a third version on 2026-06-24, which may be worth a re-skim. I didn't compare it with the earlier version.
