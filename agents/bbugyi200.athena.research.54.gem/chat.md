# Chat History - ace-run (research.54.gem)

- **TIMESTAMP:** 2026-10-20 09:23:52 EDT
- **MODEL:** agy/gemini-3.8-flash-high
- **AGENT:** research.54.gem
- **PROMPT:** `~/.sase/multi_prompts/202610/gh_sase_org__sase-multiprompt-261020_090613.md`

## Prompt

%id(gem, clan=research.54)
%m:agy/gemini-3.8-flash-high %q(1.5x, w=0.25)
#gh:gh_sase-org__sase 
You are researcher gem in a 5-researcher swarm.
The other researchers, `research.54.cdx`, `research.54.cld`, `research.54.grk`, `research.54.mus`, are independently investigating the same request and will write their own self-named reports ending in `__cdx.md` and `__cld.md` and `__grk.md` and `__mus.md`. Your report will end in `__gem.md`.

Conduct your research independently and form your own conclusions. Do NOT attempt to
locate, open, read, or otherwise consult the other researcher's report from this swarm,
even if it becomes available before you finish. Do not obtain that peer's findings
indirectly through its chat transcript, summaries, or requests to the peer. You may
independently use the same external sources, shared input material, and unrelated prior
research. You may check filenames or file existence to avoid overwriting your own
output, but do not inspect the peer's report contents. If you encounter its filename,
leave the report alone. The lead researcher will read every report and synthesize their
findings after you have all finished.

The mermaid diagrams that the image agent in the `#research_swarm` macro swarm
recommends are difficult to understand in isolation, not very useful, and not very
visually appealing. I would like to improve this agent's instructions (using some
mermaid diagram advice that is factored out to its own macro maybe?) so it produces much
more useful, easy to understand, and beautiful mermaid diagrams.

Can you do some research with the goal of helping me decide the best way to implement
this? Also, critique this plan in general. Is this a good idea? Would you take a
different approach? Make any adjustments to the requirements that you think are
justified but clearly call these out. End your analysis with a recommended solution. 
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

# Research Report Summary: Improving Mermaid Diagrams in the Research Swarm

**Report Path**: `/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/sase/repos/research/202610/improving_research_swarm_mermaid_diagrams__gem.md`  
**Durable Artifact Snapshot**: `research:202610/improving_research_swarm_mermaid_diagrams__gem.md` (`file:explicit:4cdcb57ad6f10f6512b67006`)  
**Researcher**: `gem` (`research.54.gem`)

---

### Key Findings & Plan Critique

#### 1. Why Current Diagrams Fail
The Mermaid diagrams produced by the `#research_swarm` image agent suffer from three distinct defects:
- **Incomprehensible in Isolation**: Diagrams lack high-level architectural framing, subsystem boundaries, entry/exit points, and contextual labels. Nodes like `A["Child's #prj"] --> B["Child task"]` give no indication of *who* acts, *what* system executes the logic, or *where* execution begins.
- **Low Utility**: The agent defaults almost exclusively to basic `flowchart TD` trees that merely restate simple bullet points without illustrating decision complexity, temporal exchanges, or lifecycle states.
- **Visually Unappealing**: The diagrams are monotonous collections of unstyled gray rectangles with no visual rhythm, shape language, or hierarchy.

**Root Cause**: The current instructions in `src/sase_research_artifacts/xprompts/research_diagrams.md` were written *defensively* to prevent breaking downstream rendering (specifically pandoc/XeLaTeX PDF pipelines and the `mmdc` CLI). However, the rules over-corrected into harmful micro-constraints:
- Banning decision diamonds (*"avoid decision diamonds and put the condition on a labelled edge instead"*) eliminated the single most recognizable visual indicator of branching logic.
- Restricting labels to *"about four words or fewer"* forced cryptic, telegraphic shorthand lacking verbs and system context.
- Banning all styling (*"No init directives, click, style, classDef, HTML, or icons"*) stripped away visual hierarchy and themes.

#### 2. Critique of the Proposed Macro Factoring Plan
- **Is factoring Mermaid advice into its own macro a good idea?**  
  **Yes, strongly endorsed.** It cleanly separates **tactical orchestration** (candidate scanning, panel drill-down identification, verbatim text anchoring, CLI smoke-testing, manifest authoring, status variable reporting) from **visual & structural craftsmanship** (diagram type selection, shape semantics, self-containment rules, layout, and styling).
- **Cross-System Reusability**: Factoring out `#mermaid/advice` makes publication-grade diagram guidance available across the entire SASE ecosystem (architecture plans, bead documentation, system design documents, and ad-hoc agent queries) rather than trapping it inside the research plugin.

---

### Adjustments to Requirements

1. **Mandate Structural Enclosure (Understanding in Isolation)**:
   - Flowcharts MUST use `subgraph` blocks to visually demarcate subsystems, actors, or lifecycle phases (e.g. `subgraph Intake`, `subgraph Execution Engine`).
   - Every diagram MUST include identifiable entry and exit points using stadium shapes `([Trigger / Start])` and `([Terminal / Result])`.
   - Relax the label restriction from "≤ 4 words" to "3–8 words", specifying the action verb and domain object.
2. **Restore Visual Hierarchy & Shape Semantics**:
   - Restore decision diamonds `{Condition?}` for branching logic.
   - Enforce shape semantics: `([Stadium])` for terminals, `[...]` for operational steps, `{Rhombus}` for decisions, `[(Cylinder)]` for databases/caches/durable state, and `[[Subroutine]]` for external tools or CLI subprocesses.
   - Enforce line semantics: solid `-->` for standard progression, thick `==>` for primary/happy paths, and dashed `-.->` for fallback/error/async flows.
3. **Diversify Diagram Types (Maximizing Utility)**:
   - Provide an explicit decision heuristic: use `sequenceDiagram` (with `autonumber`) for temporal multi-actor exchanges; use `stateDiagram-v2` for lifecycles and modes; reserve `flowchart TD` for workflows and algorithms.
4. **Enable Safe Built-in Styling**:
   - Standardize on `%%{init: {'theme': 'neutral'}}%%`. Empirical testing confirms `mmdc 11.4.2` compiles this cleanly without SVG or contrast bugs across light/dark themes and Pandoc PDF rendering.
   - Retain strict prohibitions on raw HTML tags (`<br>`, `<div>`), `click` callbacks, and arbitrary inline hex styling.
5. **Technical CLI Host Guard**:
   - In SASE agent environments, Chromium's singleton socket path fails if `$TMPDIR` exceeds 108 characters (`FATAL: Socket path too long`). Validation instructions must prepend `TMPDIR=/tmp` when invoking `mmdc`.

---

### Recommended Solution & Implementation

1. **Create `#mermaid/advice`** in `src/sase_research_artifacts/xprompts/mermaid_advice.md` defining:
   - Standalone comprehension rules (subgraphs, terminals, 3–8 word verb+object labels, decision diamonds).
   - Diagram type decision tree (`sequenceDiagram` vs `stateDiagram-v2` vs `flowchart TD`).
   - Shape and line hierarchy semantics.
   - Safe neutral styling and hard prohibitions.
2. **Refactor `#research/diagrams`** in `src/sase_research_artifacts/xprompts/research_diagrams.md`:
   - Replace the legacy "Draw" micro-constraints with a reference to `#mermaid/advice`.
   - Update `mmdc` validation instructions to include `TMPDIR=/tmp`.
   - Retain the orchestration harness (candidate filtering, anchor verification, manifest writing, and status reporting).
