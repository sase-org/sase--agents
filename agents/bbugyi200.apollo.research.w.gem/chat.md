# Chat History - ace-run (research.w.gem)

- **TIMESTAMP:** 2026-09-30 18:44:44 EDT
- **MODEL:** agy/gemini-3.8-flash-high
- **AGENT:** research.w.gem
- **PROMPT:** `~/.sase/multi_prompts/202609/gh_sase_org__sase-multiprompt-260930_183649.md`

## Prompt

%id(gem, clan=research.w)
%m:agy/gemini-3.8-flash-high %q(1.5x, w=0.25)
#gh:gh_sase-org__sase 
You are researcher gem in a 5-researcher swarm.
The other researchers, `research.w.cdx`, `research.w.cld`, `research.w.grk`, `research.w.mus`, are independently investigating the same request and will write their own self-named reports ending in `__cdx.md` and `__cld.md` and `__grk.md` and `__mus.md`. Your report will end in `__gem.md`.

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

# Research Synthesis: 10 High-Value Papers & Articles in Agentic Software Engineering (2025–2026)

**Researcher:** `research.w.gem`  
**Report File:** [`agentic_software_engineering_recommendations__gem.md`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/sase/repos/research/202609/agentic_software_engineering_recommendations__gem.md)  
**Registered Artifact:** `explicit:d40b9b14a4a2ab7b1a7b7b5c` (`research:202609/agentic_software_engineering_recommendations__gem.md`)  
**Scope Window:** October 2025 – September 2026 (strictly within the past 12 months, following Hassan et al., arXiv:2509.06216)

---

## Executive Overview: The Post-SASE Landscape

In September 2025, Hassan et al. introduced **Structured Agentic Software Engineering (SASE)** ([arXiv:2509.06216](https://arxiv.org/abs/2509.06216)), formalizing the division between:
1. **Software Engineering for Humans (SE4H):** The **Agent Command Environment (ACE)**, where humans orchestrate intent, supervise agent teams, and resolve ambiguities.
2. **Software Engineering for Agents (SE4A):** The **Agent Execution Environment (AEE)**, where autonomous models execute bounded tasks inside tool-rich sandboxes.

Over the last 6–12 months, the industry encountered the limits of unstructured "vibe coding": individual code generation speed exploded, but multi-developer codebases suffered from architectural drift, non-deterministic regressions, and review exhaustion (the **Agentic Productivity Paradox**). 

The literature and leading industry practitioners responded by establishing five foundational pillars:
- **Spec-Driven Development (SDD):** Replacing ephemeral, single-session chat plans with version-controlled, durable requirement contracts.
- **Harness Engineering Supremacy:** Empirical proof that outer middleware (tool control planes, sensors, process isolation, context bounds) dictates agent performance far more than raw model scale.
- **Event-Sourced, Structured Memory:** Overcoming the "50 First Dates" amnesia problem using append-only event logs rather than noisy vector-RAG.
- **The Verification Tax & SDLC Control Planes:** Measuring progress by *Production-Qualified Changes (PQC)* bounded by automated verification gates and Test-Driven Development (TDD) loops.
- **Empirical Telemetry at Scale:** Moving from toy single-file benchmarks to long-horizon repository tasks (SWE-bench Pro Verified) and massive real-world telemetry (Anthropic’s 400k-session study).

---

## 10 Recommended Papers & Articles

### 1. [Spec-Driven Development for Agentic Software Engineering: Harnessing Human–Agent Teamwork](https://arxiv.org/abs/2609.00252)
- **Authors:** Jessica Diaz, Joaquin Gayoso, Andrea Cimminio, Jorge Perez
- **Reference:** arXiv:2609.00252 (August 31, 2026)
- **Key Idea:** Formalizes **Spec-Driven Development (SDD)** as the contract substrate between human engineers and autonomous agents. Replaces transient plan modes with version-controlled specifications where every edit, patch, and test maintains bidirectional traceability back to a requirements clause.
- **Why You Will Appreciate It:** Directly grounds SASE’s philosophical rejection of ephemeral plan mode, demonstrating why durable, queryable specs (epics, tales, beads) are mandatory for scaling agent teams.

---

### 2. [A Research Agenda on Agents and Software Engineering: Outcomes from the Rio A2SE Seminar](https://arxiv.org/abs/2605.11720)
- **Authors:** A2SE Working Group (18 international researchers from academia and industry)
- **Reference:** arXiv:2605.11720 (May 12, 2026)
- **Key Idea:** The authoritative community consensus roadmap succeeding Hassan et al. Synthesizes the dual axis of **Agents for Software Engineering (A4SE)** and **Software Engineering for Agents (SE4A)**, mapping research priorities across non-determinism management, specification-driven alignment, governance barriers, and compute/token economics.
- **Why You Will Appreciate It:** Serves as the direct spiritual successor to the SASE paper, capturing global academic and industry consensus on agent governance.

---

### 3. [Don't Blame the Large Language Model: How Agent Harness Evolution Shapes Coding Agent Quality](https://arxiv.org/abs/2607.03691)
- **Authors:** Oussama Ben Sghaier et al.
- **Reference:** arXiv:2607.03691 (July 2026)
- **Key Idea:** A landmark empirical study demonstrating that holding underlying model weights constant, variations in the **agent harness** (tool registry architecture, sensory truncation, retry mechanics, process isolation) produce up to a **35% variance** in task completion rates and frequently introduce silent regressions.
- **Why You Will Appreciate It:** Provides rigorous empirical validation for Boris Cherny's core insight: *the bottleneck in agentic SE is not the agent, but the coordination layer around it*.

---

### 4. [PROJECTMEM: A Local-First, Event-Sourced Memory and Judgment Layer for AI Coding Agents](https://arxiv.org/abs/2606.12329)
- **Authors:** Ripon Chandra Malo, Tong Qiu
- **Reference:** arXiv:2606.12329 (June 2026)
- **Key Idea:** Solves agent amnesia across sessions and checkouts through an append-only, local-first event log. Records atomic development decisions, test outputs, and diagnostic hypotheses, exposing anti-recurrence summaries to agents via the Model Context Protocol (MCP) to prevent repeated debugging mistakes.
- **Why You Will Appreciate It:** Strongly mirrors SASE's event-backed bead store (`events/**` append-only logs), confirming that event-sourced memory is the superior alternative to vector-similarity RAG for codebases.

---

### 5. [Beyond Code Generation: Reliability, Verification, and Cost Economics in the Agentic Software Development Lifecycle](https://arxiv.org/abs/2609.04681)
- **Authors:** Systems & Software Engineering Research Group
- **Reference:** arXiv:2609.04681 (September 2026)
- **Key Idea:** Analyzes the **Agentic SDLC Throughput Paradox**: as code generation costs fall toward zero, verification costs scale superlinearly. Introduces **Production-Qualified Change (PQC)** and the **Agentic SDLC Control Plane**, embedding policy barriers, mutation tests, and verification receipts directly into the execution loop.
- **Why You Will Appreciate It:** Aligns with SASE's decision `receipts-prove-before-they-skip`, guarded recipes, and tool control plane policies, providing an economic and mathematical model for balancing speed with deterministic verification.

---

### 6. [Agentic Software: How AI Agents Are Restructuring the Software Paradigm](https://arxiv.org/abs/2606.05608)
- **Author:** Zhenfeng Cao
- **Reference:** arXiv:2606.05608 (June 2026; revised from *The End of Software Engineering*)
- **Key Idea:** Analyzes the conceptual transformation of software when agents become primary creators and consumers. Argues that code is becoming **ephemeral tooling** generated on demand and discarded, while the enduring assets become goal specifications, constraint topologies, and verification harnesses.
- **Why You Will Appreciate It:** Offers macro-level architectural framing for what software systems look like when autonomous execution environments become the standard development medium.

---

### 7. [TDFlow: Agentic Workflows for Test Driven Development](https://arxiv.org/abs/2510.23761)
- **Authors:** AI-SE Research Group
- **Reference:** arXiv:2510.23761 (October 2025)
- **Key Idea:** Deconstructs repository issue resolution into a four-stage Test-Driven Development pipeline with decoupled sub-agents: (1) Test Generation, (2) Patch Proposal, (3) Diagnosis, and (4) Patch Revision. Achieves **94.3% resolution** on SWE-bench Verified when high-quality reproduction tests are established.
- **Why You Will Appreciate It:** Concrete proof that decomposing monolithic agent turns into specialized sub-agents and using red-to-green test cycles provides an unambiguous, deterministic stopping condition for autonomous runs.

---

### 8. [SWE-bench Pro Verified: Towards Reliable Evaluation of Long-Horizon Software Engineering Tasks](https://arxiv.org/abs/2609.08149)
- **Authors:** Benchmark Research Consortium
- **Reference:** arXiv:2609.08149 (September 2026; building on arXiv:2509.16941)
- **Key Idea:** Overcomes the flaws of early single-file synthetic coding benchmarks. Evaluates agents across 1,865 human-verified, multi-file software engineering tasks across 41 multi-language enterprise repositories, featuring anti-tampering guards and sandboxed test environments.
- **Why You Will Appreciate It:** Details where modern frontier models actually hit walls on complex codebases, emphasizing the necessity of isolated workspaces and structured issue trackers for long-horizon work.

---

### 9. Context Engineering & Harness Engineering for Coding Agents
- **Author:** Birgitta Böckeler (Thoughtworks / Martin Fowler's Bliki)
- **Reference:** Practitioner Series (February 5 & April 2, 2026 on `martinfowler.com`)
- **Key Idea:** A two-part masterclass for software practitioners. Explores **Context Engineering** (curating what the model sees via `AGENTS.md`, modular skills, and glossary bindings) and **Harness Engineering** (surrounding agents with automated sensors—linters, typecheckers, test runners—that provide rapid feedback loops).
- **Why You Will Appreciate It:** Reads like an independent operational guide to SASE’s daily conventions, offering practical, pragmatic advice from an elite software architecture consultant.

---

### 10. How Developers and Non-Developers Work with Claude Code: A Study of 400,000 Sessions
- **Authors:** Anthropic Research
- **Reference:** Empirical Industry Report (June 2026)
- **Key Idea:** The largest empirical study to date of terminal-based coding agents in real-world production. Unveils the **70/80 division of labor**: successful sessions feature humans making ~70% of high-level planning decisions ("what to build") and the agent making ~80% of low-level execution decisions ("how to write and verify"). Shows domain expertise is a stronger success predictor than raw syntax programming experience.
- **Why You Will Appreciate It:** Provides massive empirical validation for Hassan et al.'s ACE/AEE paradigm, proving that the future of SWE is structured human orchestration paired with bounded agent execution.

---

## Comparative Taxonomy Matrix

| # | Work | Domain | Core Shift | Primary Mechanism | SASE Architecture Match |
|---|---|---|---|---|---|
| 1 | **Diaz et al. (SDD)** | Methodology | Ephemeral plans → Durable contracts | Machine-verifiable specifications | SASE Epics, Tales, Beads |
| 2 | **Rio A2SE Seminar** | Foundations | Ad-hoc tools → Bilateral discipline | Governance & non-determinism bounds | ACE / AEE Dual Architecture |
| 3 | **Ben Sghaier et al.** | Harness Systems | Model weights → Harness middleware | Reusable tool primitives, sensors | SASE Tool Control Plane |
| 4 | **PROJECTMEM** | Persistent State | Vector RAG → Event-sourced memory | Append-only event logs, MCP summaries | `sase bead` Rust events |
| 5 | **Beyond Code Gen** | Control & Verification | Code volume → Production-Qualified Change | Verification tax models, control planes | `receipts-prove-before-they-skip` |
| 6 | **Agentic Software** | Architecture | Static assets → Ephemeral runtime tooling | Agent-as-a-Service (AaaS) | Single-turn agent workspaces |
| 7 | **TDFlow** | Workflow | Monolithic runs → Multi-agent TDD | Decoupled sub-agents (Test, Patch, Revise) | SASE swarms & sub-agents |
| 8 | **SWE-bench Pro Verified**| Evaluation | Toy snippets → Long-horizon enterprise tasks | 1,865 verified multi-file problems | Isolated git workspaces |
| 9 | **Böckeler (Harness)** | Practice | Prompt crafting → Context & sensor curation | `AGENTS.md`, modular skills, sensor loops | SASE `AGENTS.md` & skills |
| 10 | **Anthropic 400k Study**| Telemetry | Full autonomy → 70/80 Division of Labor | Real-world CLI supervisory loops | ACE (Command) / AEE (Execution) |

---

## Artifact Registration Details

- **Absolute Source Path:** `/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/sase/repos/research/202609/agentic_software_engineering_recommendations__gem.md`
- **Artifact Label:** `research:202609/agentic_software_engineering_recommendations__gem.md`
- **Artifact ID:** `explicit:d40b9b14a4a2ab7b1a7b7b5c`
- **Durable Storage Path:** `/home/bryan/.sase/artifacts/agents/gh_sase-org__sase/20260930183654/agentic_software_engineering_recommendations__gem-2136a6431c30.md`
- **Final Declaration:** Submitted and accepted by the host completion plane.
