# Chat History - ace-run (research.3t.cld)

- **TIMESTAMP:** 2026-10-06 16:02:26 EDT
- **MODEL:** claude/opus
- **AGENT:** research.3t.cld
- **PROMPT:** `~/.sase/multi_prompts/202610/gh_sase_org__sase-multiprompt-261006_153844.md`

## Prompt

%id(cld, clan=research.3t)
%m:claude/opus@xhigh %q(1.5x, w=0.25)
#gh:gh_sase-org__sase 
You are researcher cld in a 5-researcher swarm.
The other researchers, `research.3t.cdx`, `research.3t.grk`, `research.3t.mus`, `research.3t.gem`, are independently investigating the same request and will write their own self-named reports ending in `__cdx.md` and `__grk.md` and `__mus.md` and `__gem.md`. Your report will end in `__cld.md`.

Conduct your research independently and form your own conclusions. Do NOT attempt to
locate, open, read, or otherwise consult the other researcher's report from this swarm,
even if it becomes available before you finish. Do not obtain that peer's findings
indirectly through its chat transcript, summaries, or requests to the peer. You may
independently use the same external sources, shared input material, and unrelated prior
research. You may check filenames or file existence to avoid overwriting your own
output, but do not inspect the peer's report contents. If you encounter its filename,
leave the report alone. The lead researcher will read every report and synthesize their
findings after you have all finished.

I'm looking for some recent (published within the last year) articles that will further
inspire my work on goals. We've done some related research to find good articles (and
papers, which I'm fine with this round too but I will preference articles) that help
with this (find this research file in the research sidecar repo), but I'm looking for
more that will inspire me.

Can you do some research with the goal of finding the articles that are most likely to
do that? End your analysis with a ranked list of articles that you think I should
consider reading. 
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

I found the earlier goals reading list (2026-10-05) and I'm reading it so the new list doesn't repeat it.

I have the prior reading list and the September goals design. Next I'll check how much of Goals is built today, then start searching the web.

Status: I've checked about 20 candidates so far. Next I'm looking into review-fatigue studies, spec-as-shared-goal tools, and agent-team task lists.

Status: I have about 30 candidates that weren't in the prior list. I'm filling in a few missing dates, then I'll have helpers open the pages and check each claim before ranking.

I've checked 30+ sources. Next I'll look at the research repo's conventions, then write the report.

Report written. Now registering it as an artifact.

Registration worked. Now I'll submit the final declaration.

I wrote the report and registered it as an artifact (`file:explicit:2c1c3162b4dcc0d3d3210750`, label `research:202610/goals_further_inspiration_reading_list__cld.md`). The research repo commit will happen when this turn ends.

**Report:** `sase/repos/research/202610/goals_further_inspiration_reading_list__cld.md`

I started from the earlier reading list (`202610/goals_redesign_recent_reading_list/`) and the September goals design. None of the twelve picks below was in that list's top ten or its honorable mentions. For every pick I opened the page and checked the date, author and the figures I quote.

**Ranked list:**
1. **Factory, "How Missions Work"** (2026-04-10). Before any planning, it writes a "validation contract": a short list of testable checks that define done. Separate validator agents, not the workers, decide when work is done. When blocked, it stops and hands control back to you.
2. **Mollick, "The Dot and the Swarm"** (2026-10-01), read with **Project Vend phase two**. Mollick argues agents can now organize themselves; what stays human is deciding "where to point them." Project Vend is the counterweight: a manager agent running on the same model approved far too much.
3. **Simon Willison, "Your job is to deliver code you have proven to work"** plus **Showboat**. What a "done" claim's evidence should be: a demo that can be re-run. Agents were caught hand-editing those demo files.
4. **Spotify, background coding agents part 3** (with Imbue's **Vet**). An LLM judge compares the diff to the original prompt and rejects about a quarter of sessions before a person sees them.
5. **Ramp, "How we made Ramp Sheets self-maintaining."** The best example of a permanent goal: monitors fire triggers, and a link left on the monitor tells the next agent to stand down. Their rule is "detect everything, notify selectively."
6. **OpenAI Symphony** (read Alex Kotliarskyi's "Building Symphony"). "The task board is the control plane," with agents handing back "proof of work" packets and a "Rework" state for sending work back.
7. **Carlini, "Building a C compiler with a team of parallel Claudes"** (with Anthropic's "Long-running Claude for scientific computing"). Sixteen agents claimed tasks with plain lock files. The test suite effectively decided what "done" meant.
8. **ImpossibleBench** (paper; with Anthropic's reward-hacking post). Giving agents an explicit "flag for a human" exit cut GPT-5's cheating from 54% to 9%.
9. **Google Antigravity's "Verify with Artifacts, not logs"** (with GitHub **Agent HQ**). Shipped examples of what a review card can show, and of commenting on an agent's output while it keeps working.
10. **GitHub Agentic Workflows.** Recurring goals written in Markdown, with the trigger, permissions and allowed outputs declared at the top. A direct template for goal hooks.
11. **"Ask or Assume?"** (paper). A separate agent watching the run for missing intent nearly closes the gap to a fully specified task (69.4% vs 70.8%). That supports making goals lighter to create.
12. **Smashing Magazine, "Designing For Agentic AI."** UX patterns paired with numbers you could track per goal type, such as how often you override or undo the agent.

The report also maps each Goals item to these readings and lists six questions to carry into them. Nine honorable mentions follow, including Stripe Minions, HBR's "brain fry" study, Wang & Liu's "Trustworthy Change" paper and the Claude Code agent-teams docs.

Four sources I couldn't fully read:
- **Symphony:** OpenAI's own page returned HTTP 403, so #6 relies on the builder's post and DevOps.com coverage.
- **HBR:** paywalled. Its headline numbers come from secondary coverage and are labeled that way.
- **Wang & Liu:** I read only the abstract.
- **Factory:** the launch post is dated 2025, almost certainly a typo, so #1 is dated by its April 2026 companion post.
