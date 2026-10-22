# Chat History - ace-run (research.3z.cld)

- **TIMESTAMP:** 2026-10-07 12:52:33 EDT
- **MODEL:** claude/opus
- **AGENT:** research.3z.cld
- **PROMPT:** `~/.sase/multi_prompts/202610/gh_sase_org__sase-multiprompt-261007_122939.md`

## Prompt

%id(cld, clan=research.3z)
%m:claude/opus@xhigh %q(1.5x, w=0.25)
#gh:gh_sase-org__sase 
You are researcher cld in a 5-researcher swarm.
The other researchers, `research.3z.cdx`, `research.3z.grk`, `research.3z.mus`, `research.3z.gem`, are independently investigating the same request and will write their own self-named reports ending in `__cdx.md` and `__grk.md` and `__mus.md` and `__gem.md`. Your report will end in `__cld.md`.

Conduct your research independently and form your own conclusions. Do NOT attempt to
locate, open, read, or otherwise consult the other researcher's report from this swarm,
even if it becomes available before you finish. Do not obtain that peer's findings
indirectly through its chat transcript, summaries, or requests to the peer. You may
independently use the same external sources, shared input material, and unrelated prior
research. You may check filenames or file existence to avoid overwriting your own
output, but do not inspect the peer's report contents. If you encounter its filename,
leave the report alone. The lead researcher will read every report and synthesize their
findings after you have all finished.

Can you do some web research with the goal of finding some recent articles/papers that
are likely to inspire the current and future direction of this project? See the
sase_related_reading_history.md file in the research sidecar repo for an idea of some of
the things I've already read related to sase. End your analysis with a ranked list of
articles/papers that you think I should consider reading (make sure to clearly call out
why I should read each article/paper). 
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

I've read your reading-history file. Next I'll get a picture of SASE's current direction from the repo, then run web searches.

I've noted what SASE is working on now and which papers earlier reading lists already recommended. Next I'll load web search and run searches by theme.

I have about 35 candidates. Next I'll check them against the original pages, using parallel fetch agents grouped by theme.

Now I'll check every candidate against your Bob library.

I have enough verified material. I'll write the report now, ranking 15 primary picks plus a second tier.

The report is written. Next I'll register it as an artifact.

Registration succeeded. Last step: the final declaration.

I wrote the report, registered it as artifact `file:explicit:ea79dc2fa2c7c72560bfb7a5` under the label `research:202610/sase_next_moves_recent_reading_list__cld.md`, and declared it for commit; the host commits it after this turn ends. The file is at `sase/repos/research/202610/sase_next_moves_recent_reading_list__cld.md`.

**What I found:** most recent work (June–October 2026) lands on threads SASE already has open:
- **Replay:** you asked for it in two annotations, and no bead tracks it yet. *Chronicle* gives a design you can copy for "replay from workflow step *k*".
- **Gates:** *Loopjacking* shows shipping agent frameworks running a different operation from the one the human approved. That makes it an audit checklist for the new sudo gates, plan approvals and Telegram approvals.
- **Completion evidence:** *Proof-or-Stop* is close to your fingerprint-bound receipts. Its additions are a hash of the check command set, a witness that must come from a different host, session and signing key, and an explicit degraded mode that is never upgraded.
- **CI and host capacity:** Anthropic reports CI jobs up 25× in six months. Separately, AgentCgroup finds memory, not CPU, limits how many agents a host can run.
- **Harnesses and size aliases:** model rankings flip from one harness to another, and the same effort label means different things to different CLIs. Size aliases should be tables built from measurements, not fixed vendor pairings.
- **Research swarms:** sixteen models produced about 1.7 independent voices. Synthesis should compare claim by claim rather than count votes.

**Ranked reading list (top 15):**
1. **Chronicle: Cut-Point Replay** – the most direct answer to your replay annotations.
2. **Loopjacking** – a checklist of how approval gates fail, to run against the new sudo and plan gates before they harden.
3. **Anthropic: "Agentic coding is straining CI"** – your Master Gate is red; a 10-minute read on why each patch buys less time and what fixed it.
4. **Proof-or-Stop** – what comes after the receipts work: command-set hashes, independent witnesses, freshness rules.
5. **Harness Engineering: eleven systems**, with Databricks' **Omnigent** post – how each CLI finds instruction files, plus the closest peer to SASE's adapter layer.
6. **Oversight Has a Capacity** – sending every gate to your phone is less safe than routing by your current load.
7. **Finding the Right Fit**, with **What Does a Harness Buy?** – both published this month; they test your size-alias and adapter decisions directly.
8. **AgentCgroup**, with **HiveMind** – bears on the Apollo OOMs and on `sase tool` admission.
9. **The Work Behind Delegation** – supervision is mostly time spent away; supports designing ACE for coming back, not watching.
10. **Engineering Reliable Coding Agents**, chapters 9–10 only – replay, recovery and crash-safety mechanics.
11. **Mo' Models, Mo' Problems**, with **Sixteen Models** – what to change in the research swarm itself.
12. **Beads vs br** and **Restoring Beads Classic** – the failure list Beads hit before leaving SQLite and JSONL; use it as acceptance tests for the bead-store epic `sase-1h8`.
13. **Is Agent Code Less Maintainable?** – changes to validation and error handling, not size or complexity, are what hurt; relevant to the `toobig` splits.
14. **AI Agent PRs: merge-conflict rates** – different agents conflict about twice as often as one agent with itself; suggests a cheap pre-landing conflict check.
15. **Hassan et al. v3** – the paper SASE is named after; already queued in your library, and v3 adds worked examples in Appendix A.

The report also has a second tier of 12 papers, a 13-item list of ideas mapped to SASE threads, and proposed `bob ref create` commands (not run).

**Library check:** 1 of 40 candidates is already in your library (0 finished). That one is the Hassan paper.

**Caveats:**
- I read papers through fetch agents, not cover to cover. Two are partly read (*Engineering Reliable Coding Agents*, *Harness Engineering*), and *Sixteen Models* is abstract-only.
- I left out CodeRescue because it was withdrawn.
- *Oversight Has a Capacity* is a simulation, and *Loopjacking* is one researcher's chosen sample; the report labels both.
- I didn't read the other swarm members' reports. I did read the ranked lists of earlier, finished reading-list reports so I wouldn't repeat their picks.

Key sources:
- [Chronicle](https://arxiv.org/abs/2609.20625)
- [Loopjacking](https://arxiv.org/abs/2609.21081)
- [Anthropic CI post](https://claude.com/blog/agentic-coding-is-straining-ci-heres-how-we-scaled-test-impact-analysis-at-anthropic)
- [Proof-or-Stop](https://arxiv.org/abs/2607.14890)
- [Harness Engineering](https://arxiv.org/abs/2609.00006)
- [Omnigent](https://www.databricks.com/blog/introducing-omnigent-meta-harness-combine-control-and-share-your-agents)
- [Oversight Has a Capacity](https://arxiv.org/abs/2606.08919)
- [Finding the Right Fit](https://arxiv.org/abs/2610.00917)
- [What Does a Harness Buy?](https://arxiv.org/abs/2610.04433)
- [AgentCgroup](https://arxiv.org/abs/2602.09345)
- [HiveMind](https://arxiv.org/abs/2604.17111)
- [The Work Behind Delegation](https://arxiv.org/abs/2609.24234)
- [Engineering Reliable Coding Agents](https://arxiv.org/abs/2608.13867)
- [Mo' Models](https://arxiv.org/abs/2609.17306)
- [Sixteen Models](https://arxiv.org/abs/2608.00285)
- [Beads vs br](https://gascity.com/guide/beads-vs-br/)
- [Restoring Beads Classic](https://www.dolthub.com/blog/2026-04-02-restoring-beads-classic/)
- [Is Agent Code Less Maintainable?](https://arxiv.org/abs/2606.21804)
- [AI Agent PR merge conflicts](https://arxiv.org/abs/2607.04697)
- [Hassan et al.](https://arxiv.org/abs/2509.06216)
