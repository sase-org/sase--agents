# Chat History - ace-run (research.4f.gem)

- **TIMESTAMP:** 2026-10-13 17:43:50 EDT
- **MODEL:** agy/gemini-3.8-flash-high
- **AGENT:** research.4f.gem
- **PROMPT:** `~/.sase/multi_prompts/202610/gh_sase_org__sase-multiprompt-261013_172545.md`

## Prompt

%id(gem, clan=research.4f)
%m:agy/gemini-3.8-flash-high %q(1.5x, w=0.25)
#gh:gh_sase-org__sase 
You are researcher gem in a 5-researcher swarm.
The other researchers, `research.4f.cdx`, `research.4f.cld`, `research.4f.grk`, `research.4f.mus`, are independently investigating the same request and will write their own self-named reports ending in `__cdx.md` and `__cld.md` and `__grk.md` and `__mus.md`. Your report will end in `__gem.md`.

Conduct your research independently and form your own conclusions. Do NOT attempt to
locate, open, read, or otherwise consult the other researcher's report from this swarm,
even if it becomes available before you finish. Do not obtain that peer's findings
indirectly through its chat transcript, summaries, or requests to the peer. You may
independently use the same external sources, shared input material, and unrelated prior
research. You may check filenames or file existence to avoid overwriting your own
output, but do not inspect the peer's report contents. If you encounter its filename,
leave the report alone. The lead researcher will read every report and synthesize their
findings after you have all finished.

I
am thinking about implementing some form of evals for sase.

- See the related research files (I think one of the Databricks research files were the
  ones to first suggest this) in the research sidecar repo and in the private
  bbugyi200/job--research GitHub repo for context.
- I think I am going to implement evals using goals somehow, which do not exist yet
  (review recent related research--note that I've done some thrashing on the
  requirements for this one, so favor more recent research files related to goals).
- Also, see my annotations in the
  ~/bob/ref/papers/2026_goals_as_first_class_abstractions_in_human_ai_collaboration_automationxp26.md
  file (and the corresponding research file) for some ideas (that I mostly agree with)
  on what goals should be.

I'm new to evals and am still thinking through goals. Can you do some research with the
goal of finding some articles or papers that inspire me / help me think through all of
this? End your analysis with a ranked list of articles/papers that you think I should
consider reading. 
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

# Research Report: SASE Evals via Goals — Foundational Readings & Architectural Blueprint

The research report has been written to the research sidecar repository and registered as a durable SASE artifact:
* **Absolute File Path:** [`/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/sase/repos/research/202610/sase_evals_via_goals_reading_list__gem.md`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/sase/repos/research/202610/sase_evals_via_goals_reading_list__gem.md)
* **Registered Artifact Reference:** `file:explicit:523136e1322de096cde2345c` (`research:202610/sase_evals_via_goals_reading_list__gem.md`)

---

## 1. Executive Summary & Core Insight: The Duality of Evals and Goals

The key conceptual breakthrough when synthesizing evaluations ("evals") and goals is recognizing that **they are the exact same abstraction viewed through two different operational lenses**:

$$\text{Offline Eval} = \text{A curated Goal executed against a frozen workspace to measure capability \& regression}.$$
$$\text{Online Goal} = \text{A live user Goal executed by an agent, evaluated against host-enforced assertions \& human review}.$$

In conventional software testing, test suites verify deterministic code paths against static inputs. But coding agents operate with multi-turn autonomy across entire codebases. Evaluating an agent cannot be reduced to syntactic diff matching or brittle unit tests (the exact failure mode that led frontier labs to abandon SWE-bench Verified in 2026). Instead, evaluation requires **assessing whether an intended outcome was achieved within acceptable behavioral boundaries**.

A **Goal** provides the missing structural backbone:
1. **The Contract:** Articulates the target outcome, scope constraints, and verification assertions *before* work starts.
2. **The Execution:** An agent runs inside an isolated, single-turn workspace under host supervision.
3. **The Graders:** The host evaluates the claim using deterministic code-based graders (`ToolRun` receipts, linters), behavioral process graders (trajectory rules), and human settlement.

If SASE builds Goals as first-class objects with structured validation assertions, **SASE gets an enterprise-grade evaluation engine for free**. An eval suite is simply a collection of benchmark Goals run across models and harnesses.

---

## 2. Context Synthesis: Databricks, Genie Agents, and Bryan's Annotations

### The Databricks Context
In the Databricks role preparation research (`databricks_nyc_cv_and_role_pitches.md`), a gap in SASE was highlighted:
> *"SASE has strong harness-reliability signals but no task-success evaluation of real agents... A small eval over SASE runs (1–2 weekends) helps both roles."*

SASE currently has elite **harness reliability** (the `fakey` deterministic fake provider, single-turn isolation in `sase_<N>`, normalized `ToolRun` failure signatures, and host-owned completion). However, it has **no task-success evaluation**. You cannot currently measure:
* When Claude 3.5 Sonnet updates to Sonnet 4 or Opus 4.5, does task completion improve or regress on real refactorings?
* What is the $pass@k$ (capability) vs. $pass^k$ (reliability) of each of SASE's seven supported harnesses?

Databricks' AI Research team is tackling this exact challenge for Genie Agents via MLflow GenAI evaluation (`mlflow.genai.evaluate`), trace capture, and guideline-based evaluators.

### Bryan's Annotations on Goals
Bryan's annotations in `~/bob/ref/papers/2026_goals_as_first_class_abstractions_in_human_ai_collaboration_automationxp26.md` (Tankelevitch & Rintel, Microsoft Research, CHI / AutomationXP 2026) establish:
- **Goals at any altitude:** Ranging from task-level assertions ("Fix race condition in supervisor bootstrap") to strategic initiatives.
- **Bidirectional Evaluation:** *"Goals enable evaluation: they provide benchmarks for success and iterative improvement... goals let humans assess AI outputs against intended outcomes and let AI provide goal-referenced feedback."* $\rightarrow$ **Bryan's Note:** `Use goals to drive evals that databricks research recommended!`
- **Outcomes vs. Outputs:** Decoupling the intended outcome from the specific diff or prompt output.
- **Prompt Provenance:** Tracking who created or changed a goal, when, and why (`Goals should always link back to a user prompt!`).
- **Interoperability:** Beads, agents, and artifacts link to goals (`Beads should support an optional goal field!`).

---

## 3. Ranked Reading List for Bryan

The 12 articles and papers below are ranked by their ability to inspire and guide the design of **Evals via Goals** in SASE.

```
                                  READING MAP
                                  
       Eval Foundations              Goal Architecture            Safety & Oversight
  ┌─────────────────────────┐   ┌─────────────────────────┐   ┌─────────────────────────┐
  │ #1 Demystifying Evals   │   │ #2 Goals as First-Class │   │ #6 Why SWE-bench Failed │
  │    (Anthropic)          │   │    Abstractions (MSR)   │   │    (OpenAI Audit)       │
  │ #4 Eval is a Smell      │   │ #3 How Missions Work    │   │ #8 Overseeing Agents    │
  │    (Hamel Husain)       │   │    (Factory)            │   │    (UW / MSR)           │
  │ #10 Product Evals       │   │ #5 Behavior Specs       │   │ #11 Governance Decay    │
  │     (Eugene Yan)        │   │    (Braintrust / Basis) │   │     (Shiyang Chen)      │
  └─────────────────────────┘   └─────────────────────────┘   └─────────────────────────┘
                                             │
                                             ▼
                                Industrial Practice & Proofs
                                ┌─────────────────────────┐
                                │ #7 Proven to Work       │
                                │    (Simon Willison)     │
                                │ #9 Agentic Systems Eval │
                                │    (Databricks MLflow)  │
                                │ #12 Cybernetic Claims   │
                                │     (Jérémie Lumbroso)  │
                                └─────────────────────────┘
```

### Rank 1 — Demystifying Evals for AI Agents
* **Author & Date:** Prithvi Rajasekaran & Anthropic Engineering Team (January 9, 2026)
* **Link:** [https://www.anthropic.com/engineering/demystifying-evals-for-ai-agents](https://www.anthropic.com/engineering/demystifying-evals-for-ai-agents)
* **Core Insight:** The definitive guide to agent evaluations. Introduces the agent eval equation $\text{Eval} = \text{Task} + \text{Graders} + \text{Outcome}$. Details the Three Graders Toolbox (code-based, model-based, and human), capability vs. regression evals, handling non-determinism via $pass@k$ vs. $pass^k$ (measuring consistency across all $k$ consecutive runs), and Evaluation-Driven Development (EDD).
* **Why It Matters for SASE:** The operational blueprint for building `sase eval run`. SASE's `ToolRun` failure signatures and receipts map directly to code-based graders, and $pass^k$ provides the exact metric to benchmark SASE's seven supported harnesses.
* **Question to Bring:** *How can SASE's `ToolRun` receipts and triage verdicts serve as the automated code-based graders for an agent eval runner?*

### Rank 2 — Goals as First-Class Abstractions in Human-AI Collaboration
* **Authors & Date:** Lev Tankelevitch & Sean Rintel, Microsoft Research (April 14, 2026, CHI / AutomationXP 2026)
* **Link:** [https://www.microsoft.com/en-us/research/publication/goals-as-first-class-abstractions-in-human-ai-collaboration/](https://www.microsoft.com/en-us/research/publication/goals-as-first-class-abstractions-in-human-ai-collaboration/)
* **Core Insight:** Argues goals must be first-class computational abstractions across six dimensions: goal articulation, persistent representations, alignment surfacing, provenance history, outcome simulation, and situated workflow support. Demonstrates that goals serve as the bidirectional bridge for evaluation.
* **Why It Matters for SASE:** Directly validates Bryan's annotations. Justifies making Goals a dedicated Rust-backed domain in `sase-core` rather than overloading Beads, and shows why every agent turn must bind to a goal (`decisions:goals-host-binds`).
* **Question to Bring:** *What minimal schema in `sase-core` allows a goal to represent user intent while doubling as an automated evaluation specification?*

### Rank 3 — How Missions Work: Contract Before Plan
* **Author & Date:** Theo Luan, Factory (April 10, 2026)
* **Link:** [https://factory.com/news/missions-architecture](https://factory.com/news/missions-architecture)
* **Core Insight:** Architecture for long-running autonomous coding "Missions." Crucially, **the validation contract of testable assertions is authored before the plan** to avoid implementation bias. Uses independent, read-only validator agents that never fix bugs, reporting that **37.2% of total execution time in production is spent on validation**.
* **Why It Matters for SASE:** Demonstrates the necessity of separating the actor from the validator. In SASE, an agent cannot self-certify its goal completion; the host must execute the validation contract upon claim.
* **Question to Bring:** *Should SASE enforce an upfront validation contract of machine-executable assertions before an agent is permitted to execute implementation steps?*

### Rank 4 — "It's Hard to Eval" Is a Product Smell
* **Author & Date:** Hamel Husain (June 29, 2026)
* **Link:** [https://hamel.dev/blog/posts/eval-smell/index.html](https://hamel.dev/blog/posts/eval-smell/index.html)
* **Core Insight:** When an agent's work is hard to evaluate, it is a symptom that the task abstraction is poorly shaped. Advocates for progressive disclosure, sharp binary assertions instead of fuzzy 1–5 scales, and treating LLM evaluators like production code benchmarked against human ground truth.
* **Why It Matters for SASE:** Prevents over-complicating SASE evals with subjective metrics. If a SASE goal cannot be verified with crisp binary assertions, the goal prompt needs better decomposition.
* **Question to Bring:** *What binary assertions must SASE evaluate upon goal claim to eliminate ambiguous evaluations?*

### Rank 5 — Behavior Specs: An Open Standard for Supervising Long-Horizon Agents
* **Authors & Date:** Ankur Goyal (Braintrust) & Mitchell Troyanovsky (Basis) (July 29, 2026)
* **Link:** [https://www.braintrust.dev/blog/behavior-specs](https://www.braintrust.dev/blog/behavior-specs) (Standard: [https://agentbehavior.dev](https://agentbehavior.dev))
* **Core Insight:** Process supervision over pure outcome evals. Uses declarative markdown specs (`.agents/behaviors/<name>/BEHAVIOR.md`) defining target goals, required evidence, decision steps, and prohibited anti-patterns, evaluating entire multi-step traces.
* **Why It Matters for SASE:** SASE already captures execution traces via `ToolRun`. Behavior specs provide a clean markdown format for evaluating whether agents adhered to workspace boundaries and architectural invariants.
* **Question to Bring:** *Can SASE adopt lightweight markdown behavior specs to evaluate trajectory compliance across turns?*

### Rank 6 — Why SWE-bench Verified Fails to Track Frontier Capabilities
* **Authors & Date:** OpenAI Evaluation & Research Team (February 2026; companion: Jimenez et al., ICLR 2024)
* **Link:** [https://openai.com/research/evaluating-coding-benchmarks](https://openai.com/research/evaluating-coding-benchmarks)
* **Core Insight:** Postmortem on SWE-bench Verified: over 50% of audited benchmark failures stemmed from tests asserting private implementation details (internal helper names, formatting) rather than functional correctness, while public PRs suffered severe pretraining data contamination.
* **Why It Matters for SASE:** A cautionary lesson: SASE eval tasks must evaluate goal fulfillment at the functional contract level (CLI exit codes, integration tests, API contracts) rather than overfitting to specific code diff shapes.
* **Question to Bring:** *How can SASE eval tasks define success at the interface/behavior level rather than overfitting to syntactic diffs?*

### Rank 7 — Proven to Work: Captured Evidence and Replayable Proofs
* **Author & Date:** Simon Willison (December 18, 2025 & February 10, 2026)
* **Link:** [https://simonwillison.net/2025/Dec/18/code-proven-to-work/](https://simonwillison.net/2025/Dec/18/code-proven-to-work/)
* **Core Insight:** Introduces *Showboat* to combat agent hallucination and cheating. Distinguishes "narrated claims" (what the LLM says happened) from "captured evidence" (tool-intercepted stdout/stderr and exit codes) that can be replayed by a human with one command.
* **Why It Matters for SASE:** Aligns 1:1 with `decisions:receipts-prove-before-they-skip`. When an agent claims a goal in SASE, the claim must attach host-captured receipts rather than agent-narrated promises.
* **Question to Bring:** *How can SASE's goal-claiming finalizer enforce that every claim carries host-captured receipts rather than agent-narrated assertions?*

### Rank 8 — Overseeing Agents Without Constant Oversight
* **Authors & Date:** Grunde-McLaughlin, Mozannar, Murad, Chen, Amershi, Fourney (UW & MSR, February 18, 2026)
* **Link:** [https://arxiv.org/abs/2602.16844](https://arxiv.org/abs/2602.16844)
* **Core Insight:** Empirical study on human oversight of agents. Demonstrates that reviewing step-by-step action logs blinds developers, leading to skimming and missed bugs. Conversely, an **Outcome/Specification View** allows humans to catch significantly more errors in half the time.
* **Why It Matters for SASE:** Guides the layout of the Goals TUI tab. When a goal moves to "Needs Review", Bryan should not be forced to read raw transcripts; SASE should render a concise Goal Settlement Card summarizing target outcomes, passed assertions, modified files, and open assumptions.
* **Question to Bring:** *What visual components on SASE's Goals TUI card will enable rapid human settlement without skimming over consequential errors?*

### Rank 9 — Evaluating Agentic Systems with MLflow GenAI Evaluation
* **Authors & Date:** Databricks AI Research & MLflow Team (Mid-2026)
* **Link:** [https://docs.databricks.com/aws/en/mlflow/genai-eval-agent](https://docs.databricks.com/aws/en/mlflow/genai-eval-agent)
* **Core Insight:** Databricks' production playbook for evaluating Genie Agents: converting multi-turn agent interactions into MLflow traces, evaluating traces with guideline-based evaluators, and feeding failure clusters into an improvement flywheel.
* **Why It Matters for SASE:** Directly targets the Databricks Agent Quality interview prep. Provides the architecture for exporting SASE traces and goal rejections into an eval dataset.
* **Question to Bring:** *How can SASE's human goal rejections ("Reject and reopen") seamlessly export into an offline eval dataset to feed an improvement flywheel?*

### Rank 10 — Product Evals in Three Simple Steps
* **Author & Date:** Eugene Yan (Updated 2026)
* **Link:** [https://eugeneyan.com/writing/evals/](https://eugeneyan.com/writing/evals/)
* **Core Insight:** Pragmatic, non-academic setup: (1) curate 20–50 golden tasks, (2) align automated evaluators to human preferences, (3) run evals continuously in development loops.
* **Why It Matters for SASE:** The ideal starting point for SASE's first eval pilot: 8–12 representative tasks, frozen commits, and a simple test runner.
* **Question to Bring:** *What are the first 10 canonical SASE tasks that should form SASE's initial golden eval set?*

### Rank 11 — Governance Decay: How Context Compaction Silently Erases Goal Constraints
* **Author & Date:** Shiyang Chen (June 21, 2026, arXiv:2606.22528)
* **Link:** [https://arxiv.org/abs/2606.22528](https://arxiv.org/abs/2606.22528)
* **Core Insight:** Across 1,323 agent episodes, context compaction caused policy violations to surge to **30–59%**, with soft domain rules decaying 8.3x faster than hard rules. Re-injecting a pinned 47-token constraint outside context restored violations to 0%.
* **Why It Matters for SASE:** Proves that Goals cannot live solely in chat context. The host must pin the active Goal contract outside LLM context and evaluate it at turn boundaries.
* **Question to Bring:** *How should SASE's host harness pin the active Goal specification across turns to ensure immunity from context compaction decay?*

### Rank 12 — Cybernetic and Epistemic: A Missing Vocabulary for Trustworthy Agentic Delegation
* **Author & Date:** Jérémie Lumbroso (October 1, 2026, arXiv:2610.00961)
* **Link:** [https://arxiv.org/abs/2610.00961](https://arxiv.org/abs/2610.00961)
* **Core Insight:** Introduces the **falsifier requirement**: an agent claim is unverified unless it specifies the exact condition under which the goal would *not* have been satisfied.
* **Why It Matters for SASE:** Provides the standard for SASE's goal-claiming protocol: agents must submit verifiable falsifier conditions along with their claims.
* **Question to Bring:** *Can SASE require goal claims to provide an explicit falsifier condition that the host's goal finalizer automatically verifies?*

---

## 4. SASE Architectural Blueprint: Implementing Evals via Goals

```
Phase 1: Goal Schema with Verifiable Assertions
  Goal in sase-core:
    - id: goal_<ulid>
    - target_outcome: "Add --json flag to sase bead list"
    - provenance: prompt_<hash>
    - assertions:
        - command: "just check" (exit 0)
        - command: "sase bead list --json" (valid JSON schema)
        - diff_scope: ["src/sase/**"]

Phase 2: Automated Verification on Claim
  Agent executes -> calls `sase goal claim <id>`
  Host intercepts via `builtin@goal` finalizer:
    - Runs code-based assertions in workspace
    - Fails assertions? -> Agent kept open with diagnostics
    - Passes assertions? -> Transitions to `needs_review`

Phase 3: The Offline SASE Eval Suite (`sase eval run`)
  Benchmark tasks (sase-bench-01 .. 12) across frozen repo checkouts:
    - Matrix: Claude, Codex, Antigravity, Muse
    - Measures pass@k (capability) and pass^k (reliability)
    - Generates MLflow-compatible traces

Phase 4: The Closed-Loop Flywheel
  User rejects claim via `sase goal reject <id>`:
    - Host exports failed goal and execution trace to eval benchmark
    - Creates permanent regression test to prevent recurrence
```

---

## 5. Suggested Next Steps

If reviewing this week, read the top three in order:
1. **Anthropic's *Demystifying evals for AI agents*** (#1): For the operational eval formula, grader taxonomy, and $pass^k$ metrics.
2. **Theo Luan's *How Missions Work*** (#3): For structuring upfront validation contracts and independent validation.
3. **Grunde-McLaughlin et al.'s *Overseeing Agents Without Constant Oversight*** (#8): For designing the TUI Goals card to enable rapid human verification without oversight fatigue.
