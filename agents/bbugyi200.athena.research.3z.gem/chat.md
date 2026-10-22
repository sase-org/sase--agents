# Chat History - ace-run (research.3z.gem)

- **TIMESTAMP:** 2026-10-07 12:43:21 EDT
- **MODEL:** agy/gemini-3.8-flash-high
- **AGENT:** research.3z.gem
- **PROMPT:** `~/.sase/multi_prompts/202610/gh_sase_org__sase-multiprompt-261007_122939.md`

## Prompt

%id(gem, clan=research.3z)
%m:agy/gemini-3.8-flash-high %q(1.5x, w=0.25)
#gh:gh_sase-org__sase 
You are researcher gem in a 5-researcher swarm.
The other researchers, `research.3z.cdx`, `research.3z.cld`, `research.3z.grk`, `research.3z.mus`, are independently investigating the same request and will write their own self-named reports ending in `__cdx.md` and `__cld.md` and `__grk.md` and `__mus.md`. Your report will end in `__gem.md`.

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
`__gem` suffix, i.e. `<stem>__gem.md` (double underscore before the
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

# Independent Research Report: Recent Agentic Software Engineering Literature & Future Directions for SASE

**Researcher:** `research.3z.gem`  
**Report File:** [`recent_agentic_se_papers_and_future_directions__gem.md`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_34/sase/repos/research/202610/recent_agentic_se_papers_and_future_directions__gem.md)  
**Registered Artifact:** `research:202610/recent_agentic_se_papers_and_future_directions__gem.md` (`file:explicit:9d0dcd262a3733bf8c10a8b1`)

---

## Executive Overview & Contextual Fit

An audit of the reading history ([`sase_related_reading_history.md`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_34/sase/repos/research/202610/sase_related_reading_history.md)) indicates three clear signals:
1. **Explicit Need for Replay:** Two separate annotations explicitly demanded tool call and workflow step replay:
   - On *The Log is the Agent*: *"Support sase tool call replay?"*
   - On Gas Town's molecules: *"Materialize steps in workflow to enable replay starting at certain xprompt workflow steps? @sase"*
   - Reading history synthesis note: *"Replay is the clearest design idea your reading keeps returning to."*
2. **The Foundational Gap:** Hassan et al.'s seminal paper introducing the concept and name **"Structured Agentic Software Engineering (SASE)"** and the **Agent Command Environment (ACE)** remains queued/unread in the library.
3. **Core Themes in Progress:** Memory evolution, multi-agent fleet governance, spec-driven development, and the tension between prompt persuasion versus host-enforced constraints.

The literature from 2025 and 2026 directly speaks to these exact problems. Below is the synthesized analysis and ranked reading list.

---

## Ranked Reading List

### 1. *Chronicle: Cut-Point Replay for Regression Testing of LLM Agents*
- **Authors:** Tisha Chawla, Susheem Koul
- **Publication:** arXiv:2609.20625 (September 2026) | [arXiv:2609.20625](https://arxiv.org/abs/2609.20625) | [GitHub: theagentplane/chronicle](https://github.com/theagentplane/chronicle)
- **Primary Domain:** Deterministic Replay, Tool-Call Infrastructure, Regression Testing
- **Why You Should Read It:**
  This directly solves your explicit question about tool-call replay and workflow step materialization. *Chronicle* records agent execution at typed "boundaries" (model inference, tool invocations, routing choices) as immutable envelopes. Through **cut-point replay**, you can freeze steps $1 \dots k-1$ from recorded envelopes (avoiding LLM costs and re-executing stateful tools) and execute step $k$ and downstream live. Because SASE already records ToolRun entries, Goal Ledgers, and transcripts, Chronicle provides the exact formal semantics and boundary model needed to implement `sase repro replay` and macro step resumption.

---

### 2. *Agentic Software Engineering: Foundational Pillars and a Research Roadmap*
- **Authors:** Ahmed E. Hassan et al.
- **Publication:** arXiv:2509.06216 (September 2025) | [arXiv:2509.06216](https://arxiv.org/abs/2509.06216)
- **Primary Domain:** SASE Manifesto, Conceptual Architecture
- **Why You Should Read It:**
  This paper is the academic touchstone of the entire SASE project—it literally coined the terms **"Structured Agentic Software Engineering" (SASE)** and the **Agent Command Environment (ACE)**. It is currently sitting unread/queued in your reference library (`ref/ai/agent_ref/agent_swe.md`). It articulates the fundamental duality (*Software Engineering for AI Agents* vs. *AI Agents for Software Engineering*) and grounds the architectural necessity of separating the human command plane from ephemeral execution environments (`sase_<N>`). Reading it aligns SASE's roadmap and terminology with the field's founding academic charter.

---

### 3. *When May an Agent Stop? Evidence-Carrying Termination for Tool-Using LLMs*
- **Authors:** Hsu et al.
- **Publication:** arXiv:2608.23623 (August 2026) | [arXiv:2608.23623](https://arxiv.org/abs/2608.23623)
- **Primary Domain:** Host-Owned Completion, Verification Receipts, Proof-of-Execution
- **Why You Should Read It:**
  Agents notoriously hallucinate completion or stop prematurely when encountering ambiguous state. **Evidence-Carrying Termination (ECT)** introduces a formal verification system where an agent cannot signal completion via text; it must produce a **typed certificate** binding all post-condition claims to valid, in-scope trace evidence (test exit codes, AST diffs, receipt signatures) that the host validates via closed replay. This is the exact theoretical counterpart to SASE's core architectural decisions: *Completion Is Host-Owned* (Decision 7), *Receipts Prove Before They Skip* (Decision 21), and the `/sase_final` declaration manifest.

---

### 4. *Model-Based Agentic Software Engineering (MAGE)*
- **Authors:** James C. Davis, Kelechi Kalu, Huiyun Peng, Parth V. Patil
- **Publication:** arXiv:2608.25174 (August 2026) | [arXiv:2608.25174](https://arxiv.org/abs/2608.25174)
- **Primary Domain:** Spec-Driven Development, Intent Modeling, System Invariants
- **Why You Should Read It:**
  Framed around the reality of **"Cheap Code, Costly Judgment,"** MAGE explains why stuffing larger prompts or relying on unguided RAG fails as systems scale. It proposes two foundational pillars:
  1. *Modeling:* Externalizing minimal purposeful representations of intent, structure, and constraints.
  2. *Alignment:* Giving obligations operational force through non-bypassable sensors, validators, and gates.
  MAGE provides formal rigor for SASE's bead taxonomy, planar memory webs, and spec-driven planning (`sase plan`).

---

### 5. *AI Agent Pull Requests on GitHub: Frequency, Structure, and Merge Conflict Rates*
- **Authors:** George Xu, Arjun Subramanian, N. Karthik
- **Publication:** arXiv:2607.04697 (July 2026) | [arXiv:2607.04697](https://arxiv.org/abs/2607.04697)
- **Primary Domain:** Multi-Agent Concurrency, Integration Bottlenecks, Swarm Logistics
- **Why You Should Read It:**
  Analyzing 33,596 agent PRs across 2,807 repositories, this paper provides the first large-scale empirical measurement of the **"Integration Bottleneck."** The authors found that concurrent cross-agent PRs suffer a staggering **41.7% textual merge conflict rate** (compared to 19.8% for sequential PRs). This hard data proves why SASE's ephemeral workspace isolation (`sase_<N>`) and AXE scheduler hold admission are essential, and highlights the urgent necessity of building a bisecting merge queue (like Gas Town's Refinery) into `sase stitch` to prevent concurrent swarms from thrashing master CI.

---

### 6. *Introducing Consort: A Spec-First Agent Framework for Enforced, Test-Driven Development on Live Database Branches*
- **Authors:** Databricks Field Engineering
- **Publication:** Databricks Technical Report & arXiv (September 2026)
- **Primary Domain:** Enforced TDD, Immutable Controls, Sandbox Branching
- **Why You Should Read It:**
  Consort critiques existing spec frameworks (GitHub Spec Kit, obra/superpowers) for relying on "prompt persuasion," which agents easily ignore or bypass by weakening test assertions. Consort enforces discipline via **immutable controls that the agent cannot edit**: deterministic orchestrators separating design and build lanes, read-only test suites, and copy-on-write live environment branching. It offers concrete architectural patterns for enforcing strict red-green-refactor TDD loops in SASE without allowing agents to tamper with verification baselines.

---

### 7. *From Agent Behaviour to Agent-Friendly Documentation: An Empirical Study of How Coding Agents Discover, Read, and Write Technical Documentation*
- **Authors:** Zhijun Gao, Jing Chen
- **Publication:** arXiv:2608.20195 (August 2026) | [arXiv:2608.20195](https://arxiv.org/abs/2608.20195)
- **Primary Domain:** Context Engineering, Instruction Files (`AGENTS.md`), Working Notes
- **Why You Should Read It:**
  Analyzing 557 real agent coding sessions and 33k PRs, this study revealed that **60.5% of agent documentation interactions are with instruction files (`AGENTS.md`) and working notes**, while only 10.6% touch classic technical docs and 1.3% touch API references. Furthermore, it proved that agents struggle with redundant conceptual prose and thrive on minimal procedural rules. This gives empirical justification to your own revisions of `sase AGENTS v1/v2/v3` (pruning core notes, prioritizing machine-actionable skills) and provides guidance on optimizing SASE's memory token consumption.

---

### 8. *SWE-Router: Routing in Multi-turn Agentic Software Engineering Tasks*
- **Authors:** Seongho Son, Sangwoong Yoon, Jiahua Tang, Shuhan Wang, Lorenz Wolf, Ilija Bogunovic
- **Publication:** arXiv:2607.00053 / ICML 2026 DL4Code Workshop (June/July 2026) | [arXiv:2607.00053](https://arxiv.org/abs/2607.00053)
- **Primary Domain:** Multi-Turn Routing, Capacity Allocation, Cost Optimization
- **Why You Should Read It:**
  Identifies the "Bayes-error floor" of prompt-only routing: an initial issue description cannot tell you whether a task is a 1-line typo fix or a complex multi-file bug. *SWE-Router* uses **value-based temporal routing**: a cheap model performs the first 1–3 exploratory turns, after which a learned value head inspects the partial trajectory (command outputs, errors, file reads) to predict success. If below threshold, the task escalates to a frontier model. This directly connects to SASE's *Size Aliases Descend The Effort Ladder* (Decision 22) and offers a formal mechanism for dynamic model escalation in the AXE scheduler.

---

### 9. *Agentic Software: How AI Agents Are Restructuring the Software Paradigm*
- **Authors:** Zhenfeng Cao
- **Publication:** arXiv:2606.05608 (June 2026; originally *The End of Software Engineering*) | [arXiv:2606.05608](https://arxiv.org/abs/2606.05608)
- **Primary Domain:** Macro Paradigm Shift, Ephemeral Code, Evolutionary Benchmarks
- **Why You Should Read It:**
  A high-level philosophical analysis examining why coding agents excel at point-in-time benchmark tasks (SWE-bench Verified) but experience severe friction in continuous repository evolution (EvoClaw). Cao argues that code is becoming ephemeral and that the enduring engineering asset is the governance harness that specifies intent and validates system invariants.

---

## High-Leverage SASE Implementation Roadmap

| Subsystem | Academic Inspiration | Concrete Opportunity for SASE |
| :--- | :--- | :--- |
| **Tool & Macro Replay** | *Chronicle* (Chawla & Koul, 2026) | Implement cut-point boundary recording in `sase tool` and macro workflows to freeze upstream tool executions and resume live execution from an arbitrary failure step. |
| **Completion Proofs** | *ECT* (Hsu et al., 2026) | Require typed, verifiable execution certificates in `sase final submit` before host finalizers run `sase stitch` or close beads. |
| **Merge Queue (Refinery)** | *Xu et al.* (2026) / Gas Town | Add an automated bisecting merge queue to serialize concurrent agent PRs and avoid the measured 41.7% cross-agent merge conflict rate. |

---

### Artifact Details
- **Report Location:** [`/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_34/sase/repos/research/202610/recent_agentic_se_papers_and_future_directions__gem.md`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_34/sase/repos/research/202610/recent_agentic_se_papers_and_future_directions__gem.md)
- **Artifact Ref:** `file:explicit:9d0dcd262a3733bf8c10a8b1` (`research:202610/recent_agentic_se_papers_and_future_directions__gem.md`)
- **Finalizer Declaration:** Submitted and accepted (`builtin@commit`).
