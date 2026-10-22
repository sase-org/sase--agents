# Chat History - ace-run (research.4l.gem)

- **TIMESTAMP:** 2026-10-15 16:29:50 EDT
- **MODEL:** agy/gemini-3.8-flash-high
- **AGENT:** research.4l.gem
- **PROMPT:** `~/.sase/multi_prompts/202610/gh_sase_org__sase-multiprompt-261015_161657.md`

## Prompt

%id(gem, clan=research.4l)
%m:agy/gemini-3.8-flash-high %q(1.5x, w=0.25)
#gh:gh_sase-org__sase 
You are researcher gem in a 5-researcher swarm.
The other researchers, `research.4l.cdx`, `research.4l.cld`, `research.4l.grk`, `research.4l.mus`, are independently investigating the same request and will write their own self-named reports ending in `__cdx.md` and `__cld.md` and `__grk.md` and `__mus.md`. Your report will end in `__gem.md`.

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
want to drastically simplify sase's documentation on sase.sh by making it simpler and
more intuitive while, at the same time, adding more structure to sase's documentation
process.

- Try to use the system described by https://diataxis.fr for inspiration if possible.
- Long-term agentic management (using sase agents) of this documenttion should be
  considered, but should not be the key focus of your research report.
- Instead, this report should focus on deciding the best possible documentation solution
  and structure. This report should also focus on the (related) sase.sh site, its UX,
  and how the proposed changes make the site more intuitive for user's looking to learn
  more about sase.

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

# SASE Documentation Simplification & Diátaxis Architecture Research Report

**Researcher:** `research.4l.gem`  
**Report Location:** [`sase/repos/research/202610/sase_documentation_simplification_and_diataxis_architecture__gem.md`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_17/sase/repos/research/202610/sase_documentation_simplification_and_diataxis_architecture__gem.md)  
**Registered Artifact:** `research:202610/sase_documentation_simplification_and_diataxis_architecture__gem.md` (`ref: file:explicit:1c3f8ddac048230afe6a357e`)

---

## Key Findings & Strategic Summary

### 1. Diagnosis: The "Kitchen Sink" Monolith Problem on `sase.sh`
A forensic audit of SASE's current public documentation reveals that while SASE possesses an advanced, world-class agentic platform, its documentation on `sase.sh` suffers from extreme cognitive and structural bloat:
- **4.1+ MB of raw Markdown text** is concentrated across ~50 files.
- Flagship files are massive monoliths that mix incompatible modes of writing:
  - [`docs/ace.md`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_17/docs/ace.md): **9,771 lines** (740 KB)
  - [`docs/configuration.md`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_17/docs/configuration.md): **7,768 lines** (668 KB)
  - [`docs/llms.md`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_17/docs/llms.md): **3,582 lines** (237 KB)
  - [`docs/beads.md`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_17/docs/beads.md): **3,047 lines** (201 KB)
- The existing navigation uses arbitrary cognitive tiers (*"The Basics"*, *"Beyond the Basics"*, *"The Nitty Gritty"*) that obscure user intent.
- The homepage presents 17 competing cards, creating choice paralysis for newcomers evaluating SASE.

---

### 2. The Diátaxis Solution
The [Diátaxis framework](https://diataxis.fr) maps directly to the needs of SASE's users by separating content into four distinct, unpolluted quadrants:
1. **Tutorials (Learning-Oriented):** Welcoming, end-to-end guided learning for newcomers (e.g., *Your First 15 Minutes*, *Running Your First Parallel Swarm*). Zero options, guaranteed success.
2. **How-To Guides (Problem-Oriented):** Task-driven, practical recipes for active developers (e.g., *How to Configure Claude Code as Provider*, *How to Set Up GitHub PR Workflows*, *How to Triage Follow-Up Beads*).
3. **Reference (Information-Oriented):** Austere, authoritative, complete specifications (e.g., CLI flag tables, `default_config.yml` schema, TUI keymap lookup, Macro grammar).
4. **Explanation (Understanding-Oriented):** Illuminating conceptual essays (e.g., *The Single-Turn Agent Contract*, *Why Completion Is Host-Owned*, *The Rust Core Boundary*, *Memory Webs Architecture*).

---

### 3. Plan Critique & Justified Adjustments

#### Is this a good idea?
**Yes, unequivocally.** SASE's primary adoption bottleneck is documentation accessibility, not feature maturity. Adopting Diátaxis brings the same contract-driven rigor to documentation that SASE brings to software engineering.

#### Where the raw plan risks failure (and the required adjustments):
1. **The "Four-Door" Fragmentation Trap:**
   - *Risk:* Scattering every subsystem into four disjoint folders causes "folder disorientation" when an engineer wants to understand a feature holistically.
   - *Adjustment:* Implement **Subsystem Portals with a Diátaxis Compass** (e.g., a *Beads Hub* that links to the Beads Tutorial, How-Tos, CLI Reference, and Event-Log Architecture).
2. **The Hand-Maintained Reference Burden:**
   - *Risk:* Manually authoring reference tables in Markdown guarantees drift and maintenance rot.
   - *Adjustment:* Mandate **Single Source of Truth (SSOT) Auto-Generation**. Extend the proven pattern of `tools/render_model_docs` to generate CLI flags from the parser, config options from `default_config.yml`, and keybindings from Textual configuration.
3. **PDF Handbook Disruption:**
   - *Risk:* SASE's downloadable offline PDF handbook (`mkdocs-pdf.yml`) requires a linear narrative, which naive Diátaxis directory structures break.
   - *Adjustment:* Decouple the web navigation manifest (`mkdocs.yml`) from the linear PDF compilation manifest (`mkdocs-pdf.yml`).
4. **Agentic Documentation Governance:**
   - *Leverage:* SASE agents thrive when given single-turn, bounded tasks. By giving each doc page a single Diátaxis archetype, SASE agents can reliably write, audit, and verify documentation without prompt dilution. Enforce this via `just docs-lint` with a strict page line-budget rule (warning at 1,500 lines, error at 2,500 lines).

---

### 4. Proposed `sase.sh` UX & Architecture

- **Top Navigation Tabs:** Enable MkDocs Material `navigation.tabs` to surface:
  `[Tutorials]` `[How-To Guides]` `[Reference]` `[Explanation]` `[Blog]`
- **Redesigned 3-Path Homepage:** Replace the 17-card grid with three distinct user pathways:
  1. *New to SASE:* Zero-to-one 15-minute tutorial.
  2. *Daily Operator:* Task-oriented recipes & interactive keybinding cheatsheet.
  3. *Systems Architect:* Deep conceptual dives and engine specifications.
- **Visual Quadrant Badges:** Subtle header chips (`TUTORIAL`, `HOW-TO`, `REFERENCE`, `CONCEPT`) setting immediate reading expectations.

---

### 5. Implementation Roadmap
- **Phase 1: Tooling & Navigation Foundation:** Enable navigation tabs, implement `tools/lint_docs_diataxis` with line budgets, build SSOT reference generators, and redesign the homepage.
- **Phase 2: Core Reference Extraction:** Decompose `configuration.md` and `cli.md` into auto-generated reference tables.
- **Phase 3: Monolith Deconstruction:** Decompose `ace.md` (9,771 lines) and `beads.md` (3,047 lines) into bounded quadrant pages with `mkdocs-redirects`.
- **Phase 4: PDF & Quality Verification:** Realign `mkdocs-pdf.yml` into a 4-book linear handbook and enforce CI passing gates (`just docs-check`, `just docs-pdf-check`).

---

*The full research report with all technical diagrams, decomposition tables, and archetype templates has been committed and registered as an artifact.*
