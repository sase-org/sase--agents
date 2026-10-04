# Chat History - ace-run (research.02.gem)

- **TIMESTAMP:** 2026-10-02 11:10:56 EDT
- **MODEL:** agy/gemini-3.8-flash-high
- **AGENT:** research.02.gem
- **PROMPT:** `~/.sase/multi_prompts/202610/gh_sase_org__sase-multiprompt-261002_110156.md`

## Prompt

%id(gem, clan=research.02)
%m:agy/gemini-3.8-flash-high %q(1.5x, w=0.25)
#gh:gh_sase-org__sase 
You are researcher gem in a 5-researcher swarm.
The other researchers, `research.02.cdx`, `research.02.cld`, `research.02.grk`, `research.02.mus`, are independently investigating the same request and will write their own self-named reports ending in `__cdx.md` and `__cld.md` and `__grk.md` and `__mus.md`. Your report will end in `__gem.md`.

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
would love to be able to reduce this project's agent instruction files down to <=100
lines. Sase has pretty good support for progressive disclosure with memory files
already.

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
(for example `research:202609/topic__a.md`), including any subdirectory the steps above
put it in. Do not derive the label from the current month, the clock, or a guessed name.
Do not pass `--move`; the source stays in the research repo for later reorganization. If
registration itself fails, report that failure — do not report the research task as
fully complete.

## Response

# Independent Research Report: Reducing Agent Instruction Files to <=100 Lines

**Researcher:** `research.02.gem`  
**Report Artifact Reference:** [`file:explicit:3b64959897a926c257d1f106`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_22/sase/repos/research/202610/reducing_agent_instructions_under_100_lines__gem.md)  
**Artifact Label:** `research:202610/reducing_agent_instructions_under_100_lines__gem.md`  
**Absolute Path:** `/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_22/sase/repos/research/202610/reducing_agent_instructions_under_100_lines__gem.md`  

---

## Executive Summary & Verdict

The proposal to reduce SASE agent instruction files down to **<=100 lines** is **both feasible and strategically beneficial**, but **only if the objective is framed as maximizing token and signal density rather than syntactic line-golfing**.

The current root [`AGENTS.md`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_22/AGENTS.md) (and its byte-for-byte provider shims [`CLAUDE.md`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_22/CLAUDE.md), [`GEMINI.md`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_22/GEMINI.md), etc.) stands at **283 lines (~4,316 tokens)**. Furthermore, in environments such as Antigravity/Gemini CLI that discover both `AGENTS.md` and `GEMINI.md`, the model suffers a **dual-loading penalty of 566 lines (~8.6k tokens)** on Turn 0 before any user instructions are processed.

Our audit shows that **over 51% of the file (145 lines)** consists of automatically inlined Memory Web strand rosters (24 decisions taking 90 lines, 66 glossary terms taking 27 lines, and task bead types taking 22 lines). Core Memory accounts for another **103 lines (36.4%)**, largely consisting of tutorial-style explanations that duplicate existing skill documentation.

By reopening ADR `webs-render-in-their-own-section`, suppressing strand rosters in agent instructions, and refactoring Core Memory templates, the file can be reduced to **78–84 lines (~1,180 tokens)**—a **~70% reduction** in lines and token cost—while preserving 100% of the project's critical operational invariants.

---

## 1. The Baseline: Why `AGENTS.md` is 283 Lines Today

Running `sase memory list` reveals the exact composition of the current file:

| Section | Current Lines | Share | Current Content & Cause of Bloat |
| :--- | :---: | :---: | :--- |
| **Section 1: Core Memory** | **103** | 36.4% | `sase.md` (76 lines: workspace boundaries, 5 linked repos, `/sase_repo`, `/sase_final`), `gotchas.md` (6 lines), `rust_core_backend_boundary.md` (17 lines). |
| **Section 2: Reference Memory** | **33** | 11.7% | 10 reference notes with multi-line wrapped descriptions. |
| **Section 3: Memory Webs** | **145** | 51.2% | `decisions.md` (90 lines: 24 decision summaries in full roster), `glossary.md` (27 lines: 66 terms), `task_types.md` (22 lines: 5 types + body). |
| **Headers & Dividers** | **2** | 0.7% | Title and structural formatting. |
| **Total** | **283** | **100%** | **~4,316 tokens** |

### The Mathematical Bottleneck
- Core Memory alone is **103 lines**.
- Memory Webs alone is **145 lines**.

This proves that **no simple trim can hit <=100 lines**. You cannot reach <=100 lines without restructuring both Memory Web rendering and Core Memory template generation.

---

## 2. Critique of the Plan

### Why it IS a good idea:
1. **Turn Economics in Swarms and Long Trajectories:** Every turn of every agent spends ~4.3k input tokens on instruction overhead (or 8.6k tokens when dual-shim loading occurs). In multi-agent swarms or multi-turn epic runs, this accumulates to hundreds of thousands of redundant tokens.
2. **Mitigating Attention Diffusion ("Lost in the Middle"):** LLMs adhere to 5–10 sharp, high-priority rules far more reliably than 50 mixed rules. Listing 24 historical decisions (e.g. how legacy v1 import was retired) dilutes attention away from critical guardrails like workspace confinement and repository gating.
3. **Prompt Cache Stability:** Under prefix caching (Claude prompt caching, Gemini context caching), any change to an ADR or glossary term currently mutates `AGENTS.md`, invalidating the cache across the entire team and agent fleet. Moving volatile strand rosters out of `AGENTS.md` keeps the system prompt byte-stable.

### The Risks & Traps:
1. **The Progressive Disclosure Tax (Retrieval Failure):** If an invariant constraint is pushed to reference memory, an agent will violate it *before* it realizes a rule exists. For example, if the workspace jail or `/sase_repo` gating is moved to reference memory, an agent will run commands outside the workspace or fetch repos over the web before ever calling `sase memory read`.
2. **Tool-Call Inflation:** If instructions are pruned too aggressively, agents will waste turns and latency running multiple `sase memory read` calls on routine tasks, increasing wall-clock time and adding more tokens to the conversation history than were saved from `AGENTS.md`.
3. **Line-Golfing Distortion:** Forcing `<=100 lines` without token or column guidelines incentivizes ugly formatting tricks (e.g. stripping blank lines, joining multiple concepts into 300-column run-on paragraphs) that degrade LLM comprehension.

---

## 3. Recommended Adjustments to Requirements

1. **Adjust Metric to Dual Budget:**
   - **Line Budget:** `<=100 lines` at standard Markdown wrap width (80–88 columns) with standard markdown paragraph spacing.
   - **Token Budget:** `<=1,500 tokens` total instruction footprint.
2. **Establish the "Hard Invariant" Boundary:**
   - Keep in Core Memory *only* rules where violation is **unrecoverable, catastrophic, or invisible to host finalizers**: workspace confinement (`sase_<N>`), cross-repo access gating (`/sase_repo`), host completion (`/sase_final`), and the Rust backend litmus test.
   - All catalogs, step-by-step procedures, and domain references must live in progressive disclosure.
3. **Reopen ADR `webs-render-in-their-own-section`:**
   - The decision record explicitly contains the reopen condition: *"Reopens when. A project accumulates enough memory webs that unconditionally inlining every descriptor becomes a real token-budget problem."*
   - That condition is met today. Memory web descriptors in `AGENTS.md` should render as concise catalog pointers, not expand full strand rosters.
4. **Eliminate Provider Shim Redundancy:**
   - Ensure providers that inspect both `AGENTS.md` and proprietary names (`GEMINI.md`) do not duplicate the instruction payload in context.

---

## 4. Reconstructed Target Design (~78 Lines / ~1,180 Tokens)

Applying this architecture yields the following concrete ~78-line structure:

```markdown
# Structured Agentic Software Engineering (SASE) - Agent Instructions

## 1. Core Memory
The following memories contain core (always loaded) context:

### 1.1 SASE Operating Contracts (sase)
- **Memory Architecture:** Core memory is inlined here. Read reference memory on demand: `sase memory read <path> -r "<why>"`. Read web strands: `sase memory read <web>:<keyword> -r "<why>"`. Modifying memory requires `/sase_memory_write`.
- **Ephemeral Workspaces:** You run in an ephemeral workspace (`sase_<N>`). Never run commands outside it; never hardcode workspace paths in plans or generated artifacts.
- **Repositories & Boundaries:** Linked repos: `sase-github`, `sase-telegram`, `sase-nvim`, `sase-research-artifacts`, `sase--research`. You MUST use `/sase_repo` before reading or modifying any repo other than your workspace checkout (including web/gh fetches). Read sidecar artifacts ONLY via `sase artifact read <ref> "<reason>"`.
- **Host Completion:** End every turn with `/sase_final` to commit work. Never pause/wait for background commands; hand long commands to `/sase_monitor`. Mechanical handoffs (`/sase_plan`, `/sase_monitor`, `/sase_questions`) are exempt.

### 1.2 Code Conventions and Gotchas (gotchas)
- **Keymaps:** When updating keymaps or leader keys, sync `src/sase/default_config.yml`.

### 1.3 Rust Core Backend Boundary (rust_core_backend_boundary)
Shared backend and domain behavior belongs in the `sase_core` crate (`sase repo open sase-core`). Python/TUI code must call through `sase_core_rs` bindings.
- **Litmus Test:** If a CLI, web app, or editor needs identical behavior to the TUI, implement it in Rust.
- **Pin:** Bumping bindings requires advancing `sase-core-revision.txt` past the sase-core commit.

## 2. Reference Memory
Read these on demand with `/sase_memory_read` (`sase memory read <path> -r "<why>"`):
1. `sase/memory/cli_rules.md` — Read when adding/modifying CLI subcommands or arguments.
2. `sase/memory/dispatch.md` — Read before remote agent dispatch with `%dispatch`.
3. `sase/memory/generated_skills.md` — Read when working with xprompt skill templates.
4. `sase/memory/lint_and_test.md` — Read before finishing your turn if you modified git-tracked files.
5. `sase/memory/sase_artifacts.md` — Read when creating, resolving, or managing SASE artifacts.
6. `sase/memory/sase_beads.md` — Read before creating, updating, or closing task/phase beads.
7. `sase/memory/sase_flags.md` — Read when adding, deferring, or removing feature flags.
8. `sase/memory/symvision.md` — Read before resolving Symvision symbol/pragma linter failures.
9. `sase/memory/tui.md` — Read before modifying TUI layouts, screenshots, or visual snapshots.
10. `sase/memory/xprompts.md` — Read before authoring xprompts, workflows, or prompt directives.

## 3. Memory Webs
Keyed collections read on demand via `sase memory read <web>:<keyword> -r "<why>"`.

### 3.1 Decisions (`decisions`)
Architectural decision records covering immutability, gates, single-turn execution, tool admission, and verification contracts.
- Browse: `sase memory web show decisions`
- Query: `sase memory read decisions:<slug> -r "<why>"`

### 3.2 Glossary Terms (`glossary`)
Domain terminology and entity concepts (Beads, Stitches, Decks, Hooks, Procs, Hoods).
- Query: `sase memory read glossary:<term> -r "<why>"` (batched queries supported).

### 3.3 Task Bead Types (`task_types`)
Catalog of allowed task types (`bug`, `ci`, `feature`, `flake`, `memory`).
- Query: `sase memory read task_types:<slug> -r "<why>"`
- **Discovered Work:** File out-of-scope follow-ups as beads using `/sase_new_task`.
```

---

## 5. Implementation Roadmap

1. **Phase 1: Memory Web Rendering (`src/sase/amd/_memory.py` & `src/sase/memory/web/roster.py`)**
   - Update `_render_web_sections` so that `sase memory init` suppresses the full `<!-- sase:strands -->` roster when assembling `AGENTS.md`. Full rosters remain accessible via `sase memory web show <web>`.
   - *Result:* Immediate reduction from 283 to ~160 lines.
2. **Phase 2: Core Memory Template Refactoring (`src/sase/main/init_memory/templates/`)**
   - Refactor `memory-sase.template.md`, `rust_core_backend_boundary.md`, and `gotchas.md` to adopt high-density operational wording.
   - *Result:* File drops from ~160 to ~80 lines.
3. **Phase 3: Automated Guardrail (`sase doctor` & CI)**
   - Add a structural budget check in `sase doctor` and `sase memory init`:
     `MAX_AGENTS_LINES = 100`, `MAX_AGENTS_TOKENS = 1500`.
4. **Phase 4: Provider Shim Deduplication**
   - Resolve dual-loading in CLI tools so `AGENTS.md` and `GEMINI.md` do not both get injected into context.

---

## 6. Durable Snapshot Registration & Completion Status

The full research report has been written and permanently registered in the SASE durable artifact index:

- **Local Path:** `/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_22/sase/repos/research/202610/reducing_agent_instructions_under_100_lines__gem.md`
- **Artifact Reference:** `file:explicit:3b64959897a926c257d1f106`
- **Artifact Label:** `research:202610/reducing_agent_instructions_under_100_lines__gem.md`
- **Stored Snapshot Path:** `/home/bryan/.sase/artifacts/agents/gh_sase-org__sase/20261002110200/reducing_agent_instructions_under_100_lines__gem-c73a9da849dc.md`
- **Final Declaration:** Submitted and accepted (`Accepted final declaration for: commit` on repository `sdd:research`).
