# Chat History - ace-run (research.0c.cld)

- **TIMESTAMP:** 2026-10-05 12:22:57 EDT
- **MODEL:** claude/opus
- **AGENT:** research.0c.cld
- **PROMPT:** `~/.sase/multi_prompts/202610/gh_sase_org__sase-multiprompt-261005_120824.md`

## Prompt

%id(cld, clan=research.0c)
%m:claude/opus@xhigh %q(1.5x, w=0.25)
#gh:gh_sase-org__sase 
You are researcher cld in a 5-researcher swarm.
The other researchers, `research.0c.cdx`, `research.0c.grk`, `research.0c.mus`, `research.0c.gem`, are independently investigating the same request and will write their own self-named reports ending in `__cdx.md` and `__grk.md` and `__mus.md` and `__gem.md`. Your report will end in `__cld.md`.

Conduct your research independently and form your own conclusions. Do NOT attempt to
locate, open, read, or otherwise consult the other researcher's report from this swarm,
even if it becomes available before you finish. Do not obtain that peer's findings
indirectly through its chat transcript, summaries, or requests to the peer. You may
independently use the same external sources, shared input material, and unrelated prior
research. You may check filenames or file existence to avoid overwriting your own
output, but do not inspect the peer's report contents. If you encounter its filename,
leave the report alone. The lead researcher will read every report and synthesize their
findings after you have all finished.

I'm thinking about adding / completing a major new faeature named "goals", which is
partially completed already (but that part may need modifications). My latest thinkng on
this subject can be found in the incomplete research prompt that I've stored in the
~/tmp/incomplete_goals_prompt.md file.

But I don't want you to design or research this feature. Instead, can you do some
research with the goal of finding some recent (<=1 year old) articles that you think are
likely to improve / inspire my thinking on this topic? End your analysis with a ranked
list of ten articles you think I should consider reading, with justification for each. 
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

Quick update: I've read your incomplete goals prompt and the goals epic roadmap. Next I'll skim the rest of the design context, then search the web for recent articles.

Still searching: I've found strong candidates (Claude Code and Codex `/goal`, Gas Town, Anthropic harness posts, oversight studies). Now I'm checking a few more angles before verifying the shortlist.

Shortlist assembled. Verifying publication dates and details for the top candidates in parallel.

Verification is done. Writing the report now.

The reading list is written and registered as an artifact. The host will commit it to the research repo after this turn.

**Report:** `sase/repos/research/202610/goals_recent_reading_list__cld.md`
**Artifact:** `sase artifact create` succeeded with label `research:202610/goals_recent_reading_list__cld.md` (ref `file:explicit:0bb0e518fb8f84d2e4d7e0db`).

**The ranked ten** (all published on or after 2025-10-05; nine are from 2026):

1. **[Claude Code Projects docs](https://code.claude.com/docs/en/claude-projects)** (launched 2026-09-17). This is the closest shipped analog to your Goals tab. Its overview groups work as Ready for review / Waiting on you / Working / Landing / Idle / Resolved. Recurring work sits on a separate Routines tab. Threads resolve themselves after a week of no activity, which is a shipped answer to your purge question.
2. **[Claude Code `/goal` docs](https://code.claude.com/docs/en/goal)** (May 2026). A goal is one sentence. A separate model judges after each turn whether it is met, not yet met, or impossible. Idle check-ins back off from 30 minutes to every 2 hours, which bears on your heartbeat design.
3. **[OpenAI Cookbook: Using Goals in Codex](https://developers.openai.com/cookbook/examples/codex/using_goals_in_codex)** (around May 2026; the page is undated). It sets a clear split between what the agent may change and what the user may change. It includes a six-part template for writing a goal and treats running out of budget as a soft stop.
4. **[Overseeing Agents Without Constant Oversight](https://arxiv.org/abs/2602.16844)** (Microsoft Research, Feb 2026). This is the best evidence I found on verification-card design. Outcome-shaped views found the most errors. But faster review didn't mean more accurate review, and people were more confident when they missed an error.
5. **[Anthropic: Harness design for long-running apps](https://www.anthropic.com/engineering/harness-design-long-running-apps)** (Mar 2026). Before each chunk of work, the builder agent and a reviewer agent agree in writing on what "done" means. That is relevant to putting plan approval and verification together in "Needs Review". It also argues for machinery you can delete later.
6. **[Maggie Appleton on Gas Town](https://maggieappleton.com/gastown)** (around Feb 2026), plus Yegge's own posts. It covers Gas Town's hooks (an agent must run whatever work is on its hook), durable versus throwaway work records, and patrol agents. It also warns that Gas Town has too many overlapping concepts, which is worth comparing against SASE's growing vocabulary.
7. **[AI Agents Push Humans Out of the Loop](https://arxiv.org/abs/2608.23642)** (Aug 2026). This is the strongest counterweight to `<enter><enter>` approval. It argues for deliberate friction and for watching your own review behaviour, for example review time falling while the approval rate stays flat.
8. **[Human oversight of agentic systems in practice](https://arxiv.org/abs/2606.05391)** (Microsoft, Jun 2026). It identifies four kinds of oversight work, and they map almost one-to-one onto your four tab sections.
9. **[Levels, Ticks and Cascaded Intelligence](https://arxiv.org/abs/2609.19519)** (Salesforce, Sep 2026), with [OpenClaw's heartbeat docs](https://docs.openclaw.ai/gateway/heartbeat) as a companion. Both are directly relevant to heartbeats and standing goals: a heartbeat stays silent unless something matters, and a cheap check skips the wake-up when nothing is due.
10. **[Intelligent AI Delegation](https://arxiv.org/abs/2602.11865)** (DeepMind, Feb 2026). Its sorting of tasks by how easy they are to verify and undo suggests which goals need you to verify them. It also gives a reason for launching `%clan(goal=…)` as its own unit.

The report also maps each of your TODOs to these readings and lists seven honorable mentions (Kief Morris, Cursor, Anthropic's autonomy study, Linear, the Codex app, Arjmandi, Böckeler).

**Verification gaps:**
- Medium blocked both of Yegge's Gas Town posts and OpenAI blocked the Codex app announcement page, so for those I relied on secondary sources.
- A few pages were only partly readable, and three key docs pages show no date. The report notes which claims are affected.

I did not look at any other researcher's report from this swarm.

Sources:
- [Claude Code Projects docs](https://code.claude.com/docs/en/claude-projects) · [VentureBeat on Projects](https://venturebeat.com/orchestration/anthropic-launches-claude-code-projects-an-always-on-conversation-that-remembers-and-delegates-your-long-running-dev-work)
- [Claude Code /goal docs](https://code.claude.com/docs/en/goal) · [VentureBeat on /goal](https://venturebeat.com/orchestration/claude-codes-goals-separates-the-agent-that-works-from-the-one-that-decides-its-done)
- [Codex goals cookbook](https://developers.openai.com/cookbook/examples/codex/using_goals_in_codex) · [Vaughan on Codex goal mode](https://codex.danielvaughan.com/2026/05/03/codex-cli-goal-mode-persistent-objectives-token-budgets-agentic-loops/)
- [arXiv 2602.16844](https://arxiv.org/abs/2602.16844) · [arXiv 2608.23642](https://arxiv.org/abs/2608.23642) · [arXiv 2606.05391](https://arxiv.org/abs/2606.05391) · [arXiv 2609.19519](https://arxiv.org/abs/2609.19519) · [arXiv 2602.11865](https://arxiv.org/abs/2602.11865) · [arXiv 2608.04066](https://arxiv.org/abs/2608.04066)
- [Anthropic harness design](https://www.anthropic.com/engineering/harness-design-long-running-apps) · [Anthropic effective harnesses](https://www.anthropic.com/engineering/effective-harnesses-for-long-running-agents) · [Anthropic autonomy study](https://www.anthropic.com/research/measuring-agent-autonomy)
- [Maggie Appleton: Gas Town](https://maggieappleton.com/gastown) · [Welcome to Gas Town](https://steve-yegge.medium.com/welcome-to-gas-town-4f25ee16dd04) · [Gas Town v1.0](https://steve-yegge.medium.com/gas-town-from-clown-show-to-v1-0-c239d9a407ec) · [Vaughan on Gas Town](https://codex.danielvaughan.com/2026/04/08/gas-town-multi-agent-factory/) · [Leo Simons on Gas Town](https://leosimons.com/2026/01/02/understanding-yegges-gas-town/)
- [OpenClaw heartbeat docs](https://docs.openclaw.ai/gateway/heartbeat) · [Cursor: scaling agents](https://cursor.com/blog/scaling-agents) · [Kief Morris](https://martinfowler.com/articles/exploring-gen-ai/humans-and-agents.html) · [Böckeler SDD](https://martinfowler.com/articles/exploring-gen-ai/sdd-3-tools.html) · [Linear coding sessions](https://linear.app/now/coding-sessions-for-linear-agent) · [Introducing the Codex app](https://openai.com/index/introducing-the-codex-app/) · [SmartScope Codex automation guide](https://smartscope.blog/en/generative-ai/chatgpt/codex-app-automation-guide/)
