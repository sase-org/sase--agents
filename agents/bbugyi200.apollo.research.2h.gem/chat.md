# Chat History - ace-run (research.2h.gem)

- **TIMESTAMP:** 2026-10-25 13:21:05 EDT
- **MODEL:** agy/gemini-3.8-flash-high
- **AGENT:** research.2h.gem
- **PROMPT:** `~/.sase/multi_prompts/202610/gh_sase_org__sase-multiprompt-261025_130846.md`

## Prompt

%id(gem, clan=research.2h)
%m:agy/gemini-3.8-flash-high %q(1.5x, w=0.25)
#gh:gh_sase-org__sase 
You are researcher gem in a 5-researcher swarm.
The other researchers, `research.2h.cdx`, `research.2h.cld`, `research.2h.grk`, `research.2h.mus`, are independently investigating the same request and will write their own self-named reports ending in `__cdx.md` and `__cld.md` and `__grk.md` and `__mus.md`. Your report will end in `__gem.md`.

Conduct your research independently and form your own conclusions. Do NOT attempt to
locate, open, read, or otherwise consult the other researcher's report from this swarm,
even if it becomes available before you finish. Do not obtain that peer's findings
indirectly through its chat transcript, summaries, or requests to the peer. You may
independently use the same external sources, shared input material, and unrelated prior
research. You may check filenames or file existence to avoid overwriting your own
output, but do not inspect the peer's report contents. If you encounter its filename,
leave the report alone. The lead researcher will read every report and synthesize their
findings after you have all finished.

I've been thinking about how sase integrates with my task managment system (see the
bob-cli project and related GitHub repos in the bobs-org organization for more context)
currently and I think I have myself convinced that there is a deeper connection between
sase (and agent orchestration in general) and task management systems. I am at the very
beginning stages of thinking about this / designing this integration. Can you do some
research with the goal of helping me determine if this is a good idea and, if so, what
types of use-cases would be unlocked by a deeper, task-management system agnostic sase
integration? Some notes related to other use-cases I've been considering for this
functionality can be found below:

- It would be useful to be able to tag an Obsidian task as ready to be worked and have a
  sase agent automatically launched at some point to work it. Evidence of completion
  could then be added to that Obsidian task by the integration and the task would be
  marked as pending (i.e. `[/]`).
- For tasks that I have not tagged to be worked on by sase agents but for which agents
  are confident they understand, it would be useful if an agent could propose
  adjustments to that task to further clarify the requirements. If accepted this would
  then add the appropriate tag, which automatically triggers a sase agent launch. This
  sase launch proposal might correspond with a prompt that asks an agent to plan out and
  implement the work or it could be, for example, a research swarm proposal (using the
  `#research_swarm` macro swarm).
- I sometimes leave questions about a reference PDF I am reading in the Highlights app
  via a note on a highlight which gets saved to a markdown file in the ~/bob/ref/
  directory. It would be useful for agents to be able to answer those questions
  automatically (maybe when tagged with `#q`?) and then write those answers to the same
  note that asked the question.
- These are just a few things that I have thought up off the top of my head. You should
  think hard about what others might exist. 
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

# Research Report: Deep, Task-Management-System-Agnostic SASE Integration

**Researcher:** `research.2h.gem` (`gem`)  
**Report File:** [`sase_task_management_integration_architecture_and_use_cases__gem.md`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/sase/repos/research/202610/sase_task_management_integration_architecture_and_use_cases__gem.md)  
**Registered Artifact:** `explicit:cdc2a004c4f24cef074ee23e` (`research:202610/sase_task_management_integration_architecture_and_use_cases__gem.md`)

---

## 1. Executive Verdict: Is This a Good Idea?

**Yes—unambiguously.** Deepening the integration between SASE (and agent orchestration in general) and task management systems is not just a convenient feature; it represents the necessary paradigm shift from **episodic prompt engineering** to **continuous ambient delegation**.

### Why the Connection is Deep and Inevitable
- **The Cognitive Impedance Mismatch:** Today's agents possess high parallel throughput, zero fatigue, and strict test verification capabilities, but they sit completely idle until a human manually formats a prompt in a terminal. Meanwhile, human cognitive management happens asynchronously in task management systems (`bob-cli` / Obsidian GTD, Linear, GitHub Issues) via mobile captures, PDF reading marginalia, and morning planning. The human is currently an exhausted, rate-limiting router between the task system and the agent CLI.
- **The Task Manager as the Ambient Control Interface:** Integrating SASE with the task system elevates the task manager into the **Human-Agent Collaboration Boundary (HACB)**. Tasks become living, bidirectional execution contracts.
- **Two-Phase Completion Protects Human Agency:** Naive AI agents attempt to mark human tasks as completed (`[x]`), which breeds distrust. In SASE's architecture, agents mechanically verify changes (e.g., `just check`), commit via stitches, and transition tasks to **Pending Review (`[/]`)** with an attached, verifiable **Evidence Card**. Only the human settles and closes the task.

---

## 2. Core Architectural Model: The System-Agnostic `TaskProvider` SPI

To ensure SASE does not become tightly coupled to Obsidian markdown formatting or specific cloud SaaS APIs, SASE must introduce a provider-neutral abstraction analogous to `vcs_provider`:

1. **Clear Domain Boundaries:**
   - **External Tasks:** Declarations of *human intent* and backlog priority (in Obsidian, Linear, GitHub).
   - **SASE Goals (`⌖`):** The host-bound contract linking an LLM turn to an audited objective.
   - **SASE Beads:** The internal engineering *execution DAG* (epics, phases, typed tasks like `bug`, `ci`, `feature`). External tools never manage bead internals directly.
   - **Durable Artifacts & Evidence Cards:** Cryptographic receipts, test verdicts, and links to research/diff snapshots attached back to the external task.

2. **The `TaskProvider` Interface:**
   - `list_candidates(filter)`: Scans for tasks with execution tags (`#sase`, `#q`, `#research_swarm`).
   - `get_task(task_ref)`: Normalizes tasks into a uniform `TaskWire` record.
   - `propose_clarification(task_ref, proposal)`: Appends non-invasive, collapsible proposals (`> [!PROPOSAL]-`) for human review.
   - `transition_status(task_ref, status, reason)`: Maps lifecycle transitions (`[ ]` $\rightarrow$ `[*]` $\rightarrow$ `[/]`).
   - `append_evidence(task_ref, evidence_card)`: Attaches verifiable execution receipts.
   - `answer_marginalia(marker_ref, answer)`: Formats and injects answers directly beneath PDF annotation comments.

---

## 3. Comprehensive Taxonomy of Unlocked Use-Cases

The report details **16 concrete use-cases** categorized across 5 functional domains:

### Category 1: Autonomous Execution & Smart Delegation ("Tag and Forget")
- **Tag-Triggered Single-Turn Execution:** Marking `- [ ] Add JSON export to tool list #sase ^task-1` automatically launches an isolated SASE workspace worker, runs `just check`, creates a commit stitch, transitions the task to `[/]`, and writes an Evidence Card with diffs and test results.
- **Tiered Model & Swarm Routing:** Tag modifiers route tasks to appropriate compute tiers:
  - `#sase/fast` $\rightarrow$ Fast, lightweight models for mechanical fixes, typos, and docstrings.
  - `#sase/deep` $\rightarrow$ Frontier reasoning models with extended thinking for algorithmic bugs.
  - `#sase/swarm` $\rightarrow$ Dispatches a multi-agent macro swarm (`#research_swarm`) across model families.
  - `#sase/epic` $\rightarrow$ Launches a planning agent to draft and compile an Epic Plan DAG (`./epic_plan.md`).
- **Dependency-Chained DAG Waves:** Automatically monitors `dependsOn:: ^block-id` relationships; as upstream tasks land in `[/]`, downstream prerequisite tasks are unlocked and scheduled in waves.
- **Off-Peak / Nightly Batch Execution:** Runs queued `#sase/backlog` tasks overnight under strict weighted capacity limits during idle compute hours.

### Category 2: Proactive Clarification, Sizing & Triage ("Agent as Senior Partner")
- **Interactive Clarification Proposals:** When an ambiguous task is captured (e.g. `- [ ] fix timeout race`), an agent analyzes the codebase and attaches a collapsible callout (`> [!PROPOSAL]-`) with suggested scope, acceptance criteria, and an approval checkbox (`- [ ] Approve & Launch`).
- **Automated Task Sizing & Decomposition Guidance:** Evaluates tasks against `sase_sizes.md`. If a task exceeds a single turn, the agent alerts the user and recommends decomposing it via an Epic Plan.
- **Semantic Duplicate & Precedent Matching:** Cross-references newly captured tasks against existing open tasks across all project notes, closed SASE beads, and historical research reports.

### Category 3: Marginalia, Active Reading & Knowledge Integration ("Ambient Scholar")
- **Marginalia Q&A on PDF Reading Notes (`~/bob/ref/`):** When reading in Highlights on iPad, typing a note like `Comment: #q How does our token budgeter handle this?` syncs to Obsidian. The agent discovers `#q`, researches the codebase/literature, and writes a cited answer directly beneath the comment in the note.
- **Pre-Reading Executive Briefings:** When an arXiv paper or article is queued (`bob ref create`), an agent synthesizes an architectural impact summary and attaches it to the reference note before the user opens the PDF.
- **Dynamic Literature-to-Code Tracing:** Extracts key theoretical decisions from reading notes directly into SASE memory webs (`sase/memory/decisions/`).

### Category 4: GTD Workflow Augmentation (Daily Planning & Review)
- **Morning Plan Budget Feasibility Check (`bob plan`):** SASE analyzes scheduled tasks against the user's daily Pomodoro budget and recommends which specific items can be safely delegated to agents to balance workload.
- **Nightly Reconciliation & Journal Ledger (`bob nightly`):** Compiles an executive summary of completed agent runs and test verdicts into the daily journal note (`journals/YYYY-MM-DD.md`).
- **Freshness Review Copilot (`bob freshness`):** Audits stale project notes (like `sase.md`), identifying completed tasks whose code already merged, flagging broken references, and proposing archiving.

### Category 5: Reverse-Flow: Agent Discoveries to Human Backlog
- **Surfacing Discovered Work into the Human GTD Inbox:** When agents discover bugs, test flakes, or tech debt during epic execution, SASE projects them directly into the human's Obsidian inbox under `### Discovered by Agents` for prioritization.
- **CI Failure Action Items:** Diagnostic failures on master runs generate structured, actionable follow-up tasks in the appropriate project note.

---

## 4. Phased Implementation Roadmap

1. **Phase 1 (Non-Invasive Observation & Q&A):** Deploy marginalia `#q` Q&A in `~/bob/ref/` and background clarification proposals (`> [!PROPOSAL]-`). Completely read-only with zero risk to code or task state.
2. **Phase 2 (Tag-Driven Execution & Proof Cards):** Implement `BobObsidianProvider` with `#sase` tag detection, single-turn execution, mandatory `just check` verification, and two-phase completion (`[ ]` $\rightarrow$ `[/]`).
3. **Phase 3 (GTD Deep Integration):** Integrate with `bob plan` (delegation budgeting), `bob nightly` (daily journal summaries), and `bob freshness` (backlog hygiene).
4. **Phase 4 (Multi-Provider Platform):** Extract `TaskProvider` into `sase-core` and implement providers for Linear and GitHub Issues.

*Full architectural specifications, data models, sequence diagrams, and markdown syntax examples are available in the linked research report.*
