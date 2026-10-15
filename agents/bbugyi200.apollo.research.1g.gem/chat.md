# Chat History - ace-run (research.1g.gem)

- **TIMESTAMP:** 2026-10-15 09:30:07 EDT
- **MODEL:** agy/gemini-3.8-flash-high
- **AGENT:** research.1g.gem
- **PROMPT:** `~/.sase/multi_prompts/202610/gh_sase_org__sase-multiprompt-261015_091709.md`

## Prompt

%id(gem, clan=research.1g)
%m:agy/gemini-3.8-flash-high %q(1.5x, w=0.25)
#gh:gh_sase-org__sase 
You are researcher gem in a 4-researcher swarm.
The other researchers, `research.1g.cdx`, `research.1g.cld`, `research.1g.grk`, are independently investigating the same request and will write their own self-named reports ending in `__cdx.md` and `__cld.md` and `__grk.md`. Your report will end in `__gem.md`.

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
have been thinking that some of sase's memories should be migrated to documentation in
markdown files in the docs/ directory (the sase/memory/macros.md memory file, for
example), that I should consider making project documentation a first-class
representation of memory (we should manage it in a similar way, for example), and that I
should do a better job of structuring my documentation so its maintainance is more
intuitive and scriptable (via agents).

Can you do some research with the goal of finding some articles/papers that will help
inspire me on this front? End your analysis with a ranked list of articles/papers that
you think I should consider reading. 
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

### Research Report Completed & Registered

I have completed the independent research investigation on **migrating agent memory to project documentation, elevating documentation to a first-class memory representation, and structuring documentation for intuitive, scriptable agentic maintenance**.

The research report has been written and registered as a durable SASE artifact:

- **Absolute Path:** [`/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/sase/repos/research/202610/migrating_memory_to_documentation_and_agentic_maintenance__gem.md`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/sase/repos/research/202610/migrating_memory_to_documentation_and_agentic_maintenance__gem.md)
- **Artifact Label:** `research:202610/migrating_memory_to_documentation_and_agentic_maintenance__gem.md`
- **Artifact ID:** `explicit:ecb8f2523f928722f3ee77c3`
- **Artifact Ref:** `file:explicit:ecb8f2523f928722f3ee77c3`

---

### Core Theoretical & Architectural Insights

1. **The Dual Knowledge Dilemma (Shadow Documentation):**
   - Notes like `sase/memory/macros.md` (14+ KB of directive syntax tables, inputs, and launch rules) currently duplicate content from `docs/macros.md` (240+ KB). This results in a "triple-update tax" (`src/`, `docs/`, `memory/`), semantic drift, and unnecessary context window consumption.
2. **Documentation as External Semantic Memory (CoALA Taxonomy):**
   - Grounded in cognitive architectures (Sumers et al., 2023), documentation is the externalized **Semantic Memory** of the software system. Agent memory and project documentation should share a unified control plane rather than operating in disconnected silos.
3. **The Diátaxis Separation of Concerns:**
   - Monolithic documentation files mix tutorials, how-to recipes, architecture explanations, and reference manuals. Adopting the **Diátaxis framework** (Procida) separates content into four distinct quadrants:
     - **Reference:** Factual, deterministic syntax tables and schemas (ideal for automated generation, verification, and surgical agent edits).
     - **How-To:** Goal-oriented workflow recipes (ideal for agent procedural guidance).
     - **Explanation:** Architectural rationale and design trade-offs (tethered to immutable ADRs).
     - **Tutorials:** Beginner learning journeys (human-oriented).
4. **Topological Code-Doc Synchronization (RepoAgent / DocAgent):**
   - Modern agentic doc maintenance uses Abstract Syntax Tree (AST) parsing to build an inter-object dependency Directed Acyclic Graph (DAG) and traces `git diff`s. Documentation nodes are regenerated in **bottom-up topological order**, ensuring high-precision, automated doc updates without context sprawl.
5. **Living, Executable Documentation:**
   - Adopting Martraire’s *Living Documentation* principles: extracting reference specs directly from code/schemas (CLI parsers, dataclasses) and executing doc code snippets in CI (`just check`) to prevent documentation drift at the pre-commit boundary.

---

### Ranked Reading List

| Rank | Title | Authors / Source | Key Focus |
| :---: | :--- | :--- | :--- |
| **1** | [**RepoAgent: An LLM-Powered Open-Source Framework for Repository-level Code Documentation Generation**](https://arxiv.org/abs/2402.16667) | Q. Luo et al. (Tsinghua / OpenBMB, 2024 · ASE/EMNLP) | AST dependency DAGs, Git-diff tracking, and bottom-up topological generation for automated repo documentation maintenance. |
| **2** | [**Cognitive Architectures for Language Agents (CoALA)**](https://arxiv.org/abs/2309.02427) | T. R. Sumers, S. Yao, K. Narasimhan, T. L. Griffiths (Princeton, 2023) | Formalizes agent memory: Working Memory vs. Long-Term Memory (Semantic, Episodic, Procedural). Documents as semantic memory. |
| **3** | [**Diátaxis: A Systematic Approach to Technical Documentation Authoring**](https://diataxis.fr/) | Daniele Procida (Divio / Canonical, 2020–present) | The 4-quadrant architecture (Tutorials, How-To, Reference, Explanation) that solves prompt confusion and enables surgical doc updates. |
| **4** | **Living Documentation: Continuous Knowledge Sharing by Design** | Cyrille Martraire (Addison-Wesley, 2019) | Foundations of single-source-of-truth documentation extracted from code, executable specifications, and ubiquitous language. |
| **5** | [**ReadMe.LLM: A Framework to Help LLMs Understand Your Library**](https://arxiv.org/abs/2504.09798) | S. Wijaya et al. (UC Berkeley, 2025) | Design principles for "LLM-oriented documentation" optimized for agent context ingestion and accurate tool use. |
| **6** | [**DocAgent: A Multi-Agent System for Automated Code Documentation Generation**](https://arxiv.org/abs/2504.08725) | D. Yang et al. (2025) | Multi-agent collaboration (Reader, Writer, Verifier) coordinated through code dependency DAGs. |
| **7** | **Documenting Architecture Decisions (ADRs)** | Michael Nygard (Cognitect, 2011) / O. Zimmermann et al. (IEEE Software) | Distinguishing immutable, chronological decision memory (`decisions/`) from living, evolving system documentation (`docs/`). |
| **8** | [**CODESYNC: Synchronizing Large Language Models with Dynamic Code Evolution at Scale**](https://arxiv.org/abs/2502.16645) | Research Consortium (2025) | Empirical benchmarks on API drift and methods to synchronize models with rapidly evolving codebases. |
| **9** | **Docs Like Code: Modern Approaches to Software Documentation** | Anne Gentle (2017) | Treating documentation with code rigor: version control, issue tracking, linters (Vale/markdownlint), and CI testing. |
| **10** | **Cascade: Detecting Code-Documentation Inconsistencies via Automated Test Generation** | Academic SE Group (2026 Pre-print) | Synthesizing automated verification tests directly from documentation prose to catch subtle code-documentation decay. |

---

### Migration Roadmap for SASE

1. **Carve out `sase/memory/macros.md` via Diátaxis:** Move syntax tables to `docs/reference/macros.md` and workflow recipes to `docs/how-to/authoring_macros.md`. Retire the heavy reference note from `sase/memory/`.
2. **First-Class `docs:` Memory Resolution:** Allow `sase memory read docs:reference/macros -r "<why>"` with section anchor filtering and audit logging.
3. **CI Doc Verification:** Add markdown linting, internal link checking, and code snippet execution into `just check`.
4. **Git-Diff Doc-Sync Hook:** Implement an automated agent workflow (e.g. `#doc-sync`) to inspect staged diffs and update mapped documentation nodes before turn completion.
