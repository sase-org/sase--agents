# Chat History - ace-run (research.w.grk)

- **TIMESTAMP:** 2026-09-30 18:44:18 EDT
- **MODEL:** grok/grok-4.6
- **AGENT:** research.w.grk
- **PROMPT:** `~/.sase/multi_prompts/202609/gh_sase_org__sase-multiprompt-260930_183649.md`

## Prompt

%id(grk, clan=research.w)
%m:grok/grok-4.6@xhigh %q(1.5x, w=0.25)
#gh:gh_sase-org__sase 
You are researcher grk in a 5-researcher swarm.
The other researchers, `research.w.cdx`, `research.w.cld`, `research.w.mus`, `research.w.gem`, are independently investigating the same request and will write their own self-named reports ending in `__cdx.md` and `__cld.md` and `__mus.md` and `__gem.md`. Your report will end in `__grk.md`.

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

I'll start by reading the SASE paper and the research-repo conventions so the recommendations stay on-topic and the report lands in the right place.

Next I’ll open the research repo, read the SASE paper, and check existing report conventions so this write stays independent and in the right place.

The research repo is open. I’ll read its conventions and the SASE paper next, then scan 202609 so I don’t collide with an existing `__grk` report.

I have the paper’s pillars. Next I’ll look at report format and pull citing work plus recent agentic-SE literature from the last year.

I’ll now read the strongest candidates in enough depth to rank them, then write the `__grk` report.

I have enough to write the report. I’ll confirm the filename is free, then write it and register the artifact.

I’ll write the literature report into the research repo, then register it as a durable snapshot.

The report is in the research sidecar as `research:202609/agentic_se_related_literature_2025_2026__grk.md`. It is registered as a durable snapshot (`explicit:5aeb7ad70ce11bed7e13da26`); the source file stays in the research repo.

The SASE paper (Hassan et al., [arXiv:2509.06216](https://arxiv.org/abs/2509.06216), v3 June 2026) is still the conceptual scaffold. What moved in the last year is that it now has companions, an empirical substrate, and a harness literature that treats the workbench as the product.

**Read these ten, in this order.** Cutoff is 30 September 2025 through 30 September 2026. Quality ranked above recency.

1. **Hoda, *Toward Agentic Software Engineering Beyond Code*** ([arXiv:2510.19692](https://arxiv.org/abs/2510.19692), Oct 2025 / ICSE Companion 2026). Direct conversation with Hassan et al.: keep the vocabulary, widen the object of study past code.
2. **Feldt et al., *The Semi-Executable Stack*** ([arXiv:2604.15468](https://arxiv.org/abs/2604.15468), Apr 2026). The scope companion. Prompts, workflows, and gates are engineered artifacts on a spectrum of executability.
3. **Aleti, Ray, Hoda, Chen, *Trustworthy AI Software Engineers*** ([arXiv:2602.06310](https://arxiv.org/abs/2602.06310), Feb 2026). Evidence-centric inspection rather than reading diffs — Merge-Readiness Packs in all but name.
4. **Li, Zhang, Hassan, *AIDev*** ([arXiv:2602.09185](https://arxiv.org/abs/2602.09185), MSR 2026). The map of agent-authored PRs that the vision paper could only gesture at.
5. **Chatlatanagulchai et al., *Agent READMEs*** ([arXiv:2511.12884](https://arxiv.org/abs/2511.12884), Nov 2025). What MentorScripts look like in the wild: lots of how-to-run, almost no security or performance.
6. **Gloaguen et al., *Evaluating AGENTS.md*** ([arXiv:2602.11988](https://arxiv.org/abs/2602.11988), Feb 2026, v3 Sep 2026). The ablation: context files do not raise SWE-bench success and cost ~20% more tokens.
7. **Ben Sghaier, Li, Adams, Hassan, *Don't Blame the Large Language Model*** ([arXiv:2607.03691](https://arxiv.org/abs/2607.03691), Jul 2026). Fix the model, vary the harness: quality swings that look like model regressions are harness PRs.
8. **Davis et al., *Model-Based Agentic Software Engineering*** ([arXiv:2608.25174](https://arxiv.org/abs/2608.25174), Aug 2026). Freeze settled obligations; leave uncertain intent open. Closest 2026 theory paper to ACE as a governed environment.
9. **Gorinova et al., *Coding Benchmarks Are Misaligned with Agentic Software Engineering*** ([arXiv:2606.17799](https://arxiv.org/abs/2606.17799), Jun 2026). SWE-bench collapses model, harness, and environment into one score. That is the wrong instrument for SASE-like systems.
10. **Anthropic, *Effective harnesses for long-running agents*** ([Nov 2025](https://www.anthropic.com/engineering/effective-harnesses-for-long-running-agents)). Field-tested LoopScript: initializer, feature list, progress file, leave the tree mergeable.

The report also lists honorable mentions (Rio A2SE agenda, METR Time Horizon 1.1, agent-PR rejection and follow-up-fix studies, Anthropic’s April 2026 managed-agents post) and explicitly excludes the 2024 SE 3.0 prequel and other out-of-window classics.
