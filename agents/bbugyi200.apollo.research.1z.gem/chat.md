# Chat History - ace-run (research.1z.gem)

- **TIMESTAMP:** 2026-10-17 16:45:41 EDT
- **MODEL:** agy/gemini-3.8-flash-high
- **AGENT:** research.1z.gem
- **PROMPT:** `~/.sase/multi_prompts/202610/gh_sase_org__sase-multiprompt-261017_163112.md`

## Prompt

%id(gem, clan=research.1z)
%m:agy/gemini-3.8-flash-high %q(1.5x, w=0.25)
#gh:gh_sase-org__sase 
You are researcher gem in a 4-researcher swarm.
The other researchers, `research.1z.cdx`, `research.1z.cld`, `research.1z.grk`, are independently investigating the same request and will write their own self-named reports ending in `__cdx.md` and `__cld.md` and `__grk.md`. Your report will end in `__gem.md`.

Conduct your research independently and form your own conclusions. Do NOT attempt to
locate, open, read, or otherwise consult the other researcher's report from this swarm,
even if it becomes available before you finish. Do not obtain that peer's findings
indirectly through its chat transcript, summaries, or requests to the peer. You may
independently use the same external sources, shared input material, and unrelated prior
research. You may check filenames or file existence to avoid overwriting your own
output, but do not inspect the peer's report contents. If you encounter its filename,
leave the report alone. The lead researcher will read every report and synthesize their
findings after you have all finished.

I've been thinking about the best way to handle merging for an agent software factory
like sase. See the merge_queue_fenced_master_and_exact_sha_releases.md file in the
research sidecar repo for context. Can you do some research with the goal of finding
some recent (<1 year old) articles/papers that will help inspire me / point me in the
right direction? End your analysis with a ranked list of articles/papers that you think
I should consider reading. 
Write this research to a new markdown file under the $(sase repo path research --ensure)/$(date +%Y%m)/ directory.
Choose a descriptive filename stem yourself, but the filename MUST end with the
`__gem` suffix, i.e. `<stem>__gem.md` (double underscore before the
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

# Research Report: Merging in the Agent Software Factory (Recent Literature & Ranked Reading List)

**Researcher:** `research.1z.gem`  
**Report File:** [`agent_software_factory_merging_reading_list__gem.md`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/sase/repos/research/202610/agent_software_factory_merging_reading_list__gem.md)  
**Registered Artifact:** `research:202610/agent_software_factory_merging_reading_list__gem.md` (`file:explicit:2f6e7ca7825545f5027cd082`)

---

## Executive Summary & Key Insights

Operating an autonomous software factory like SASE—where swarms of agents continuously generate, test, and attempt to land changes onto trunk across multiple hosts (`athena`, `apollo`)—breaks conventional trunk-based workflows. Replaying uncoordinated direct pushes or relying on conversational human review rapidly leads to trunk decay and blocked releases.

Recent research published over the past year (late 2025 to late 2026) converges on five core realities:

1. **Agent Conflicts Are Severe and Asymmetric:** Uncoordinated concurrent agent PRs produce conflict rates of **27% to 42%**, driven by large, multi-file diffs and shared configuration/entrypoint collisions (*Xu et al., 2026*; *Ogenrwot & Businge, 2026*). Cross-agent collisions happen at more than double the rate of single-agent sequential work.
2. **Merge Queues Are Mandatory Fences, but Fragile Under Flakes:** Speculative execution merge queues isolate semantic "green-green" breakage. However, speculative parallel branches suffer severe cascade aborts when test suites exhibit flaky failure rates above 3% (*Jungwirth et al., 2025*).
3. **LLM Conflict Auto-Resolution Is Insufficient:** Frontier LLMs (even when trained with GRPO reinforcement learning) resolve **fewer than 60%** of real-world merge conflicts correctly (*Schesch & Ernst, 2026*). Structural avoidance and queue ejection beat inline LLM merge attempts.
4. **Autonomous Self-Healing Loops Work ("Who Finishes the Job"):** While merged agent PRs require follow-up patches at 1.62× the rate of human PRs, **69.6% of those follow-up fixes can be written and merged autonomously by the agents themselves** (*Takerngsaksiri et al., 2026*). Host-driven automated "build-cop" and repair turns are empirically validated.
5. **Decouple Merge Gating from Release Qualification:** Passing a merge queue proves that code did not break the trunk, but it does not guarantee release quality or absence of architectural code smells (*Cynthia et al., 2026*). Fast admission gating must be paired with scheduled, exact-SHA qualification off the critical landing path.

---

## Ranked Reading List (< 1 Year Old)

### Tier 1: Essential / Must-Read Foundations

#### 1. AI Agent Pull Requests on GitHub: Frequency, Structure, and Merge Conflict Rates
* **Authors:** George Xu, Arjun Subramanian, Nitin Karthik
* **Identifier:** [arXiv:2607.04697](https://arxiv.org/abs/2607.04697) (`cs.SE`) — July 2026
* **Why Read It:** Provides the first empirical measurement of merge conflicts caused specifically by autonomous coding agents (Devin, Cursor, Copilot, Codex, Claude Code) working concurrently. Replaying 3-way `git merge` on co-active agent PR pairs showed a **41.7% cross-agent conflict rate**. Proves that uncoordinated agent swarms must have an admission fence.

#### 2. Who Finishes the Job? A Study of Follow-Up Fixes and Commit Authorship on AI Coding Agent Pull Requests
* **Authors:** Wannita Takerngsaksiri, Nhat Duong, Scott Barnett (Applied AI Initiatives, Deakin Univ.)
* **Identifier:** [arXiv:2609.26847](https://arxiv.org/abs/2609.26847) (`cs.SE`) — September 2026
* **Why Read It:** Explores post-merge stability across 6,774 merged agent PRs. Demonstrates that while agent merges attract follow-up fixes at 1.62× the odds of human PRs, **69.6% of follow-up fixes are authored autonomously by the same agent**. Confirms that host-initiated post-merge self-healing turns ("build cop") are a sound architecture.

#### 3. Improving Merge Pipeline Throughput in Continuous Integration via Pull Request Prioritization
* **Authors:** Maximilian Jungwirth, Martin Gruber, Gordon Fraser
* **Venue:** *IEEE International Conference on Software Maintenance and Evolution (ICSME 2025)*, pp. 565–575 — October 2025
* **Why Read It:** Analyzes throughput bottlenecks in speculative merge queues (GitHub Merge Queue, GitLab Merge Trains). Proposes dynamic flow-control scheduling and PR prioritization to eliminate head-of-line blocking by slow/flaky PRs, reducing P95 wait times and cutting wasted CI minutes by >30%.

#### 4. AgenticFlict: A Large-Scale Dataset of Merge Conflicts in AI Coding Agent Pull Requests on GitHub
* **Authors:** Daniel Ogenrwot, John Businge
* **Identifier:** [arXiv:2604.03551](https://arxiv.org/abs/2604.03551) (`cs.SE`) — April 2026
* **Why Read It:** Benchmark of 142,000+ AI coding agent PRs across 59,000 repositories. Found that **27.67% of agent PRs hit textual merge conflicts** across 336,000 conflict regions, identifying dependency manifests, shared interfaces, and central routing tables as high-risk collision zones.

---

### Tier 2: Post-Merge Code Quality & Workflow Failure Taxonomies

#### 5. Beyond Bug Fixes: An Empirical Investigation of Post-Merge Code Quality Issues in Agent-Generated Pull Requests
* **Authors:** Shamse Tasnim Cynthia, Al Muttakin, Banani Roy (Univ. of Saskatchewan)
* **Identifier:** [arXiv:2601.20109](https://arxiv.org/abs/2601.20109) (`cs.SE`) — January 2026
* **Why Read It:** Documents that passing green CI does not prevent critical post-merge code smells or architectural drift. Directly reinforces the requirement for SASE's two-speed verification: fast gating at admission, heavy full matrix qualification for releases.

#### 6. Why Are Agentic Pull Requests Merged or Rejected? An Empirical Study
* **Authors:** Sien Reeve O. Peralta et al. (Waseda, Osaka, Ritsumeikan, NAIST)
* **Venue:** *IEEE/ACM International Conference on Mining Software Repositories (MSR 2026)* / [arXiv:2605.22534](https://arxiv.org/abs/2605.22534) — May 2026
* **Why Read It:** Reveals that 33.1% of rejected agent PRs suffer from reviewer abandonment, and highlights the **Review Comment Sign-Flip**: each review cycle drastically increases the likelihood of agent rejection. Confirms SASE's policy of zero human review approvals for routine agent merges.

#### 7. Where Do AI Coding Agents Fail? An Empirical Study of Failed Agentic Pull Requests in GitHub
* **Authors:** Ramtin Ehsani et al.
* **Identifier:** [arXiv:2601.15195](https://arxiv.org/abs/2601.15195) (`cs.SE`) — January 2026
* **Why Read It:** Forensic analysis of 33,000+ agent PRs showing that changes modifying >3 files fail CI at a 4× higher rate. Validates SASE's `toobig` agent splitting and phased task scoping.

---

### Tier 3: Automated Conflict Resolution Limits & Operational Case Studies

#### 8. Merge-Bench: Resolve Merge Conflicts with Large Language Models
* **Authors:** Benedikt Schesch, Michael D. Ernst (Univ. of Washington)
* **Identifier:** [arXiv:2605.25890](https://arxiv.org/abs/2605.25890) (`cs.SE`) — May 2026
* **Why Read It:** Evaluates commercial and RL-trained models on 7,938 real merge conflict hunks. Even frontier models resolve <60% of real conflicts. Warns against relying on inline LLM conflict auto-mergers on the critical landing path.

#### 9. Can Large Language Models Resolve Real Java Merge Conflicts? An Evaluation with a Calibrated LLM-as-Judge
* **Authors:** Bowen Shen
* **Identifier:** [arXiv:2607.27674](https://arxiv.org/abs/2607.27674) (`cs.SE`) — July 2026
* **Why Read It:** Shows that zero-shot LLM conflict resolution creates subtle semantic bugs and duplicate definitions, but adding deterministic compiler and AST test validation loops dramatically improves repair fidelity.

#### 10. Operational Retrospective: The April 2026 GitHub Merge Queue Incident
* **Source:** GitHub Engineering Blog & Availability Updates — April 2026
* **Why Read It:** Analyzes the incident where squash-merge queues built on inverted bases, silently reverting commits across 2,092 PRs. Repositories using standard **merge commits** were unaffected. Validates SASE's decision to enforce merge commits and require cryptographic tree-equality proofs (`master^{tree} == queue_commit^{tree}`).

---

### Foundational Reference: Industrial CI at Scale

* **CI at Scale: Lean, Green, and Fast** (Dhruva Juloori, Zhongpeng Lin, Matthew Williams, Eddy Shin, Sonal Mahajan — Uber Technologies; [arXiv:2501.03440](https://arxiv.org/abs/2501.03440), January 2025).  
  *The* reference for scaling speculative merge queues (*SubmitQueue*). Introduces **speculation thresholding** (only speculating when historical pass probability is >85%), reducing CI usage by 53% and P95 wait times by 37%.

---

## Artifact Registration Details

- **Report Source:** [`/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/sase/repos/research/202610/agent_software_factory_merging_reading_list__gem.md`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/sase/repos/research/202610/agent_software_factory_merging_reading_list__gem.md)
- **Artifact Label:** `research:202610/agent_software_factory_merging_reading_list__gem.md`
- **Artifact ID:** `explicit:2f6e7ca7825545f5027cd082`
- **Stored Snapshot:** `/home/bryan/.sase/artifacts/agents/gh_sase-org__sase/20261017163116/agent_software_factory_merging_reading_list__gem-e8473295b32e.md`
- **Finalizer Declaration:** Submitted and accepted for repository `sdd:research` commit declaration.
