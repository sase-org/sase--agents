# Chat History - ace-run (research.0t.gem)

- **TIMESTAMP:** 2026-10-10 16:50:58 EDT
- **MODEL:** agy/gemini-3.8-flash-high
- **AGENT:** research.0t.gem
- **PROMPT:** `~/.sase/multi_prompts/202610/gh_sase_org__sase-multiprompt-261010_163712.md`

## Prompt

%id(gem, clan=research.0t)
%m:agy/gemini-3.8-flash-high %q(1.5x, w=0.25)
#gh:gh_sase-org__sase 
You are researcher gem in a 5-researcher swarm.
The other researchers, `research.0t.cdx`, `research.0t.cld`, `research.0t.grk`, `research.0t.mus`, are independently investigating the same request and will write their own self-named reports ending in `__cdx.md` and `__cld.md` and `__grk.md` and `__mus.md`. Your report will end in `__gem.md`.

Conduct your research independently and form your own conclusions. Do NOT attempt to
locate, open, read, or otherwise consult the other researcher's report from this swarm,
even if it becomes available before you finish. Do not obtain that peer's findings
indirectly through its chat transcript, summaries, or requests to the peer. You may
independently use the same external sources, shared input material, and unrelated prior
research. You may check filenames or file existence to avoid overwriting your own
output, but do not inspect the peer's report contents. If you encounter its filename,
leave the report alone. The lead researcher will read every report and synthesize their
findings after you have all finished.

Can you do some research with the goal of finding the best, recent (<=1 year old)
articles related to agentic Software Engineering? Use your /bob_ref skill to make sure I
haven't already read any of the articles that you recommend. End your analysis with a
ranked list of articles that you think I should consider reading. 
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

# Research Report: Recent Breakthroughs in Agentic Software Engineering (2025–2026)

**Researcher ID:** `research.0t.gem` (`gem`)  
**Report File:** [`recent_agentic_software_engineering_articles__gem.md`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/sase/repos/research/202610/recent_agentic_software_engineering_articles__gem.md)  
**Artifact ID:** `explicit:310f727c3fd5bd4a339265dc` (`research:202610/recent_agentic_software_engineering_articles__gem.md`)  
**Time Horizon:** October 2025 – October 2026 (≤ 1 year old)

---

## Executive Summary & Landscape Synthesis

Over the past twelve months (late 2025 through late 2026), the discipline of software engineering with AI underwent a fundamental paradigm shift away from prompt-centric "vibe coding" toward **Structured Agentic Software Engineering (SASE)** and **Harness Engineering**. 

The emerging consensus across academic and industry research centers on four pillars:
1. **The Primacy of the Harness (`Agent = Model + Harness`):** Raw model reasoning is only one component. The surrounding environment—execution sandboxes, deterministic sensors (linters, static analyzers, test suites), memory persistence ledgers, and outer loops—governs real-world reliability.
2. **From Code Generation to Verification & Specification:** When syntax generation is cheap and abundant, human engineering value concentrates in **specification inference** (formalizing intent into executable specifications) and **verification & validation (V&V)** (evaluating conflicting signals across tests, diffs, and execution traces).
3. **Beyond Isolated Bug-Fixing to Long-Horizon Evolution:** Benchmarks like SWE-bench saturated or faced contamination issues, catalyzing new evaluation frameworks (such as SWE-EVO) that test multi-file software evolution and long-horizon refactorings across mature codebases.
4. **Preservation of the Software Engineering Discipline:** Far from rendering software engineering obsolete, coding agents create an acute need for engineers to serve as **methodologists, mediators, and custodians** of durable knowledge levers and system invariants.

---

## Bob Reference Library Audit (`/bob_ref`)

Before finalizing recommendations, all candidate papers and articles were audited against Bryan's reading vault (`~/bob/ref`) via `bob ref find - -f json`:

### Already in Library
* **OpenAI Engineering:** *"Harness engineering: leveraging Codex in an agent-first world"* (February 11, 2026)  
  * *Library Note:* [`ref/blogs/harness_engineering.md`](file:///home/bryan/bob/ref/blogs/harness_engineering.md) (`reading_state: finished`).
  * *Verdict:* Already read. Serves as foundational context for the 2026 harness engineering movement, but excluded from the unread recommendations.
* **Rashina Hoda:** *"Toward Agentic Software Engineering Beyond Code: Framing Vision, Values, and Vocabulary"* (October 22, 2025; arXiv:2510.19692)  
  * *Library Note:* [`ref/ai/agent_ref/toward_agent_swe.md`](file:///home/bryan/bob/ref/ai/agent_ref/toward_agent_swe.md) (`reading_state: started` since 2025-11-15).
  * *Verdict:* Already in your library (started since 2025-11-15). Highlighted as an active reading to complete.

### Fresh Discoveries (`not_found`)
Nine high-impact articles and papers were verified absent from the library and are detailed below.

---

## Ranked Reading Recommendations

| Rank | Title & Link | Author(s) & Venue | Date | Why Read It | Proposed Bob Capture Command |
| :---: | :--- | :--- | :---: | :--- | :--- |
| **1** | [**Why Software Engineering Is Indispensable in the Age of Coding Agents**](https://arxiv.org/abs/2610.10226) | Alfonso Fuggetta (*CACM* / arXiv:2610.10226) | Oct 2026 | Theoretical proof for why LLMs suffer from probabilistic generation, agnosticism, and semantic statelessness, requiring human engineers to maintain durable "knowledge levers." | `bob ref create https://arxiv.org/abs/2610.10226 -L` |
| **2** | [**Harness engineering for coding agent users**](https://martinfowler.com/articles/exploring-gen-ai/harness-engineering.html) | Birgitta Böckeler (*Martin Fowler*) | Apr 2026 | Practical taxonomy of controls: Guides (feedforward steering) vs. Sensors (feedback checks), separating deterministic computational checks from inferential LLM checks. | `bob ref create https://martinfowler.com/articles/exploring-gen-ai/harness-engineering.html -L` |
| **3** | [**Agent Harness Engineering**](https://addyosmani.com/blog/agent-harness-engineering/) | Addy Osmani (*addyosmani.com*) | Apr 2026 | Production systems perspective on the "Agent Stack," treating scaffolding as versioned infrastructure and urging teams to "own the outer loop." | `bob ref create https://addyosmani.com/blog/agent-harness-engineering/ -L` |
| **4** | [**Skills for the future software profession: beyond agentic AI!**](https://arxiv.org/abs/2606.21894) | S. Kang, B. Ray, A. Roychoudhury (arXiv:2606.21894) | Jun 2026 | Expert roundtables from NYC and Singapore outlining why specification inference and V&V become the primary engineering skills when agents write code. | `bob ref create https://arxiv.org/abs/2606.21894 -L` |
| **5** | [**Agentic Engineering Patterns**](https://simonwillison.net/guides/agentic-engineering-patterns/) | Simon Willison (*simonwillison.net*) | Feb 2026 | Practical design patterns for coding agents: Red/Green TDD for agents, agentic manual testing, and subagent specialization to protect context limits. | `bob ref create https://simonwillison.net/guides/agentic-engineering-patterns/ -L` |
| **6** | [**SWE-EVO: Benchmarking Coding Agents in Long-Horizon Software Evolution**](https://arxiv.org/abs/2512.18470) | M. V. T. Thai et al. (arXiv:2512.18470) | Dec 2025 | Realistic benchmark demonstrating performance cliffs when agents move from single-bug fixes to multi-file software evolution across mature repositories. | `bob ref create https://arxiv.org/abs/2512.18470 -L` |
| **7** | [**From Vibe Coding to Agentic Engineering**](https://simmering.dev/blog/agentic-engineering/) | Paul Simmering (*simmering.dev*) | Feb 2026 | Deep dive into the five coding styles and the hidden cost of "cognitive debt" (codebase opacity) when over-delegating to AI. | `bob ref create https://simmering.dev/blog/agentic-engineering/ -L` |
| **8** | [**Agentic Software: How AI Agents Are Restructuring the Software Paradigm**](https://arxiv.org/abs/2606.05608) | Zhenfeng Cao (arXiv:2606.05608) | Jun 2026 | Macroeconomic framework tracing the shift from SaaS to AaaS and analyzing ephemeral runtime code vs. persistent intent architecture. | `bob ref create https://arxiv.org/abs/2606.05608 -L` |
| **9** | [**Methods and Techniques of Agentic Software Engineering: A Systematic Literature Review**](https://doi.org/10.1109/ACCESS.2026.3528498) | N. A. Otoum & N. Elkhalili (*IEEE Access*) | Jan 2026 | Comprehensive academic survey mapping agentic SE architectures, tooling protocols (MCP), and maturity across the full SDLC. | `bob ref create https://doi.org/10.1109/ACCESS.2026.3528498 -L` |

---

## Artifact Registration & SASE Finalization

* **Report Source:** [`/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/sase/repos/research/202610/recent_agentic_software_engineering_articles__gem.md`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/sase/repos/research/202610/recent_agentic_software_engineering_articles__gem.md)
* **Registration Command Executed:**  
  `sase artifact create -p "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/sase/repos/research/202610/recent_agentic_software_engineering_articles__gem.md" -l "research:202610/recent_agentic_software_engineering_articles__gem.md"`
* **Registration Result:**
  * **Artifact ID:** `explicit:310f727c3fd5bd4a339265dc`
  * **Durable Path:** `/home/bryan/.sase/artifacts/agents/gh_sase-org__sase/20261010163726/recent_agentic_software_engineering_articles__gem-7f4a1936b678.md`
  * **Reference:** `file:explicit:310f727c3fd5bd4a339265dc`
* **Final Declaration:** Submitted and accepted for repository `sdd:research` (`repo-9bf900ad4f21`).

---

Library check: 2 of 11 candidates already in your library (1 finished).
