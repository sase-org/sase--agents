# Chat History - ace-run (research.1f.gem)

- **TIMESTAMP:** 2026-10-15 09:35:02 EDT
- **MODEL:** agy/gemini-3.8-flash-high
- **AGENT:** research.1f.gem
- **PROMPT:** `~/.sase/multi_prompts/202610/gh_sase_org__sase-multiprompt-261015_091655.md`

## Prompt

%id(gem, clan=research.1f)
%m:agy/gemini-3.8-flash-high %q(1.5x, w=0.25)
#gh:gh_sase-org__sase 
You are researcher gem in a 4-researcher swarm.
The other researchers, `research.1f.cdx`, `research.1f.cld`, `research.1f.grk`, are independently investigating the same request and will write their own self-named reports ending in `__cdx.md` and `__cld.md` and `__grk.md`. Your report will end in `__gem.md`.

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

# Research Summary: Docs as Memory, First-Class Knowledge Representation, and Agent-Scriptable Documentation

I have completed the independent research investigation as **`research.1f.gem`** and published the full analysis to [`docs_as_memory_migration_and_structure__gem.md`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_17/sase/repos/research/202610/docs_as_memory_migration_and_structure__gem.md).

The report has also been registered as a durable SASE artifact snapshot:
- **Artifact ID:** `explicit:f08a35823f53585bfdd4d018`
- **Label:** `research:202610/docs_as_memory_migration_and_structure__gem.md`
- **Stored Snapshot:** `/home/bryan/.sase/artifacts/agents/gh_sase-org__sase/20261015091659/docs_as_memory_migration_and_structure__gem-ec8c592932ab.md`
- **Ref:** `file:explicit:f08a35823f53585bfdd4d018`

---

## Key Findings & Strategic Critique

### 1. Migrating Memories to `docs/` (The `sase/memory/macros.md` Case Study)
- **Verdict: A literal file migration or pointer replacement is fatal.**
- **The Divergence Reality:**
  - `sase/memory/macros.md`: **167 lines | 14.8 KB | ~3,700 tokens** (high-density operational constraints, directives table, finalizer invariants).
  - `docs/macros.md`: **4,082 lines | 243.8 KB | ~61,000 tokens** (human-facing didactic narrative, CLI tutorials, ASCII infographics, edge-case prose).
- **The Failure Mode:** Pointing agents directly to `docs/macros.md` introduces a **16x token explosion** per read, consuming 30–60% of an agent’s single-turn context window before reading codebase files, causing context dilution ("lost in the middle") and higher hallucination rates. Conversely, stripping `docs/macros.md` down to a telegraphic cheat-sheet destroys the documentation for human users on `https://sase.sh/`.
- **The Real Problem:** Dual-maintenance divergence. The solution is **single-source generation from code definitions**, not merging two fundamentally distinct rhetorical artifacts.

### 2. Making Project Documentation a "First-Class Representation of Memory"
- **Verdict: Excellent as a parallel tier with shared governance, but dangerous if merged into prompt compilation.**
- **What to Adopt:** Extend SASE Memory’s best governance mechanisms to `docs/`:
  - **Audited Reads:** Introduce `sase doc read <topic> [--section <name>] -r "<why>"` with token caps (<2,500 tokens), capturing agent ID, reason, and git blob OIDs in the audit log.
  - **Frontmatter Schemas:** Require YAML frontmatter (`title`, `description`, `doc_type`, `domain`, `related_code`, `status`) on all doc pages.
  - **Drift Testing:** Implement CI checks verifying that CLI options and config keys in docs match code parsers and schemas.
- **What to Avoid:** Do not add the 90 doc files (4.4 MB / 1.1M tokens) into `sase memory list` or the preloaded instruction bundle compiler. Keep prompt budgets hermetic.

### 3. Structuring Documentation for Intuitive and Scriptable Agent Maintenance
- **Verdict: Highly recommended — this is the most critical reform.**
- **The Root Cause:** SASE documentation currently suffers from **monolithic monster files**:
  - `docs/ace.md`: 739.7 KB (~185k tokens)
  - `docs/configuration.md`: 667.8 KB (~167k tokens)
  - `docs/macros.md`: 243.8 KB (~61k tokens)
  - `docs/cli.md`: 210.6 KB (~53k tokens)
- **The Solution:**
  1. **De-monolithize into Topic Subtrees (<400 lines per file):** Split `docs/macros.md` into `docs/macros/` (`index.md`, `syntax.md`, `directives/`, `workflows.md`, `swarms.md`, `vcs.md`). Small files allow agents to view and edit surgical chunks in a single tool call without offset paging or regex truncation.
  2. **Code-Driven Single-Source Codegen:** SASE already proved this pattern with `tools/render_model_docs` (rendering `models.yml` into `docs/llms.md` and checked by `just fmt-docs-check`). Extend this to macro directives and CLI commands: a shared registry in `src/sase/macro/` generates both the exhaustive reference pages in `docs/macros/directives/` and the compact reference table in `sase/memory/macros.md`.

---

## Recommended 3-Tier Knowledge Architecture

```
┌───────────────────────────────────────────────────────────────────────────────────────┐
│ TIER 1: CORE PROMPT MEMORY (`sase/memory/*.md`, type: core)                           │
│ - Audience: Root agents during prompt assembly                                        │
│ - Scope: Workspace invariants, linked repos, /sase_final contract, key gotchas        │
│ - Delivery: Inlined into AGENTS.md and explicit provider bundles                      │
│ - Budget: Hard cap <6,000 tokens total (Current: ~5,750 tokens)                       │
├───────────────────────────────────────────────────────────────────────────────────────┤
│ TIER 2: AGENT REFERENCE MEMORY (`sase/memory/*.md`, type: reference & webs)          │
│ - Audience: Active agents executing specialized tasks                                 │
│ - Scope: Dense operational cheat-sheets, task schemas, ADRs, glossary strands         │
│ - Delivery: On-demand, audited via `sase memory read <selector> -r "<why>"`           │
│ - Budget: 500 – 3,500 tokens per note/strand                                          │
├───────────────────────────────────────────────────────────────────────────────────────┤
│ TIER 3: MODULAR PROJECT DOCUMENTATION (`docs/**/*.md`)                                │
│ - Audience: Humans (reading sase.sh) & Agents (performing deep research/refactors)    │
│ - Scope: Conceptual guides, tutorials, architectural runbooks, full API references    │
│ - Delivery: Human web browsing & Audited agent access via `sase doc read`             │
│ - Budget: Unconstrained globally; section-capped (<2,500 tokens) per agent read       │
│ - Structure: De-monolithized into modular topic trees (<400 lines per file)           │
└───────────────────────────────────────────────────────────────────────────────────────┘
```

The full research report detailing the Diátaxis modularization structure, schema definitions, and phased 4-stage implementation plan is available in the artifact.
