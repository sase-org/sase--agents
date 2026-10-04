# Chat History - ace-run (research.c.image)

- **TIMESTAMP:** 2026-09-25 20:12:30 EDT
- **MODEL:** agy/gemini-3.8-flash-high
- **AGENT:** research.c.image
- **PROMPT:** `~/.sase/multi_prompts/202609/gh_sase_org__sase-multiprompt-260925_193845.md`

## Prompt

%id(image, clan=research.c) %model:@image
%wait:research.c.final %q(w=0.25) #gh:gh_sase-org__sase 
%xprompts_enabled:false
# Previous Continuation

This fork uses versioned continuation replay. Blocks are stable, parent-first projections of exact continuation nodes; any historical source without recoverable node provenance is represented as an opaque legacy boundary.

- **Projection version:** `1`
- **Ordered nodes:** `1`

## Continuation Block `block:v1:316ad61b9050c31bdbcc808b65132345`

- **Node:** `agent-delta:20260925193850:ecbc54a553fffe23`
- **Kind:** `agent_delta`
- **Parents:** (none)
- **Content:** `local:continuation/records/agent_delta/agent-delta:20260925193850:ecbc54a553fffe23.json`

### User

**Protected user instruction.** Carry this request unless an explicit attributed update supersedes it.

%clan(research.c, tribe=research, summary=[[[bold]RESEARCH PROMPT:[/bold] Updating
the default values used for sase's size model alias pools (`@medium`, for example) and
models supported by completion in the prompt input widget and external editors (via LSP
support) is painful considering how often we need to do it. I would like to make this
much easier so maintainers can update both of these by updating as few files as
possible/desirable.

Can you do some research with the goal of helping me decide the best way to implement
this? Also, critique this plan in general. Is this a good idea? Would you take a
different approach? Make any adjustments to the requirements that you think are
justified but clearly call these out. End your analysis with a recommended solution.]]) %id:research.c.final %m:@xlarge
%wait:research.c.cld %wait:research.c.grk %wait:research.c.mus %wait:research.c.gem %q(w=0.25)
#gh:gh_sase-org__sase 
You are the lead researcher: 4 independent researchers have reported on the request
below, and you will add your own research and merge every perspective into one
consolidated report.

SASE derives your plan's links from the artifacts you read this turn; use
`sase artifact read` for context you actually used.

Research request:

Updating
the default values used for sase's size model alias pools (`@medium`, for example) and
models supported by completion in the prompt input widget and external editors (via LSP
support) is painful considering how often we need to do it. I would like to make this
much easier so maintainers can update both of these by updating as few files as
possible/desirable.

Can you do some research with the goal of helping me decide the best way to implement
this? Also, critique this plan in general. Is this a good idea? Would you take a
different approach? Make any adjustments to the requirements that you think are
justified but clearly call these out. End your analysis with a recommended solution.

The researchers' registered reports:

{% for a in wait.artifacts if a.kind == "markdown" and a.label and a.label.startswith("research:") %}
- wait_name={{ a.wait_name }} label={{ a.label }} source_path={{ a.source_path }} path={{ a.path }} ref={{ a.ref }}
{% endfor %}

Month directory (create it if missing):

$(sase repo path research --ensure)/$(date +%Y%m)

Steps:

1. From the registered reports above, identify exactly one report per expected suffix
   in cld, grk, mus, gem, belonging to this
   dispatch's `research.c.cld`, `research.c.grk`, `research.c.mus`, `research.c.gem` dependencies, matching by `wait_name` and the canonical research
   label's existing `__<suffix>.md` suffix. Never reassign suffixes from list order.
   Open the research repo with `/sase_repo`, then read each report through its canonical
   research reference (or the `ref` field's `file:<id>` reference if the original has
   moved) using `sase artifact read`. Do not read predecessor chat transcripts. If the
   records above do not identify exactly one report per expected suffix, stop and report
   the missing or ambiguous input instead of guessing.
2. Research the request yourself, prioritizing gaps, weak evidence, and disagreements
   between the reports.
3. Pick a descriptive stem `<name>` that collides with nothing in the month directory
   (do NOT end the name with `_consolidated` or `_<YYYYmmdd>` or anything similar unless
   it relates to the research topic), create `<month-dir>/<name>/`, and move each report
   inside it as `<name>__<suffix>.md`, preserving its existing suffix. Each report's
   `source_path` is provenance for where it lives in your own opened research checkout;
   resolve its canonical repo-relative path there before moving it. Never modify the
   other agents' checkouts or the stored snapshot recorded at `ref` — only the copy in
   your own checkout moves. Preserve every file and never overwrite: on any collision,
   pick a different stem first.
4. Write the consolidated report to `<name>/<name>.md`: merge the strongest findings
   from every report above and your own research, resolve conflicts, cut duplication,
   and add missing critical context without unnecessary length.

Final layout:

```text
<month-dir>/<name>/
├── <name>__cld.md
├── <name>__grk.md
├── <name>__mus.md
├── <name>__gem.md
└── <name>.md
```

### Assistant

Opened the research repo; now reading the four reports through audited artifact reads.

Read all four reports (one per suffix: cld, grk, mus, gem). Now verifying the points where they disagree against the code and git history.

Checking the provider modules for per-model behavior (this decides whether model lists can move into YAML cleanly).

Git history confirms the file counts, but the per-category split in two reports is off. Tests are the biggest bucket. Now reading the effort-ladder decision record and the ladder test.

Still mapping which commits change the model catalog vs. the pools (the key data for the one-file-vs-two question); switching to a direct diff scan.

Still verifying the remaining claims: where the alias file is referenced and which checks already exist.

Confirmed cld's claim that the user's own `sase.yml` pins superseded models. Quick look at a related earlier research report in the same month directory, then I'll write up.

I have enough evidence. Next I'll check the research repo's conventions, then move the reports and write the consolidated report.

Moving the four reports into the new topic directory (no collisions for the stem `model_catalog_and_size_alias_maintenance`).

Reports moved. One quick check on how `just check` and CI are wired, so the drift-check recommendation names the right recipe.

Writing the consolidated report now.

Fixing a few numbers in the report that I want to double-check (known-model count, the per-commit before/after table).

The layout is final and chezmoi is unchanged (I only read it). Submitting the final declaration.

I've written the consolidated report and submitted the research repo for commit. My recommendation: do it, but aim at the tests and docs rather than at the TUI or the LSP.

**Your plan, critiqued.** Making updates cheaper is worth it: the alias file has changed 29 times in 8 weeks. But part of the plan targets a problem that's already solved:
- The prompt input widget and the LSP already read one Python-built catalog. The Rust LSP re-reads a JSON copy of it and has no model list of its own, so there's nothing to unify there.
- The cost is in hand-maintained copies. I recounted the last 10 model updates (145 files in total): tests were 42% of the files touched, docs 37%, source 19%. Six test files changed in at least half of those updates.
- Only moving the values into one file saves almost nothing. The Grok 4.7 commit would go from 19 files to 18.

**Where the researchers disagreed, and what the code shows:**
- **One file or two:** half the recent updates changed both the model catalog and the pools. That favours one file, though this matters less than the test and docs work. The model lists are plain data, so moving them doesn't split data from the code that uses it (that was mus's main objection).
- **Drift check:** there isn't one. The existing renderer test compares output in memory and never reads `docs/llms.md`, so if someone skips `just fix` the docs go stale silently.
- **Existing checks:** the "every pool member is a known model" test and the effort-ladder test already exist. The ladder test hardcodes which Grok model continues from which.
- **gem's example config has wrong values** (Claude's small tier, Antigravity's tier, short aliases), so don't copy it.

**Requirement changes I'd make:**
- Measure success as one file edited by hand per update, plus one regeneration command, with CI catching everything else. Regenerated docs showing up in the diff is fine.
- Drop "unify the TUI and LSP" from scope.
- Add rules that make that single edit safe: known models only, supported effort levels, the effort ladder, and at least two providers per alias.
- Add a docs drift check to `just check` and CI.
- Stop updating placeholders, help text and config comments to name the newest model. They only need to name a model that still exists.
- Put each provider's large/small default model in the manifest too. Antigravity's is still on Gemini 3.7 while 3.8 is in `@xsmall`, and nothing flags it.
- Stop editing the effort-ladder decision record on every retune.
- Not doing: moving the catalog into sase-core, asking provider CLIs for their model lists at runtime, or computing efforts automatically.

**Recommended solution:** one hand-edited `src/sase/llm_provider/models.yml` with two sections: the built-in model catalog (ids, short aliases, large/small defaults, which model a new one `supersedes`, optional `status: legacy`) and the size-alias pools. The built-in providers read from it. The plugin hooks, the data the completion surfaces receive, and the Rust LSP stay exactly as they are.

The order matters:
1. Make tests take their expected values from the data, add the drift check, and neutralize the examples. This needs no runtime change.
2. Build the manifest, with a check that providers publish exactly the same data before and after the move.
3. Add the rules module and generate every model table in the docs.

After that, a Grok 4.7-style update is: edit `models.yml`, run `just fix`, run `just check`. That's one file edited by hand, one regenerated, and no test edits.

**Your own config is affected too.** Your custom aliases `sol_or_grok` and `opus_or_grok` in `sase.yml` still target `gpt-5.6-sol` and `grok-4.6`, and your `codex` and `m_agy` prompt snippets pin older models too. Once the manifest records which model supersedes which, a `sase doctor` warning for this is cheap. I've listed it as a follow-up.

The report ends with five questions for you, including one file versus two, what "retired" should mean, and whether the Gemini 3.7 default is intentional.

Everything is in `202609/model_catalog_and_size_alias_maintenance/` in the research repo:
- `model_catalog_and_size_alias_maintenance.md` (the consolidated report)
- `model_catalog_and_size_alias_maintenance__cld.md`
- `model_catalog_and_size_alias_maintenance__grk.md`
- `model_catalog_and_size_alias_maintenance__mus.md`
- `model_catalog_and_size_alias_maintenance__gem.md`

---

%xprompts_enabled:true
# New Query

 Generate an infographic that illustrates the main points made in this research markdown
file. Write the image to `<source-stem>_infographic.png` in the same directory.


## Response

An infographic illustrating the main findings and architectural recommendations from [model_catalog_and_size_alias_maintenance.md](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/sase/repos/research/202609/model_catalog_and_size_alias_maintenance/model_catalog_and_size_alias_maintenance.md) has been generated and written to:

**[model_catalog_and_size_alias_maintenance_infographic.png](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/sase/repos/research/202609/model_catalog_and_size_alias_maintenance/model_catalog_and_size_alias_maintenance_infographic.png)**

---

### Key Points Illustrated in the Infographic

1. **Top Audit Metrics & Problem Statement:**
   - **29 Commits / 8 Weeks:** Size alias defaults and model configurations churn constantly; frequent pool retunes are structural, not transient.
   - **42% Tests · 37% Docs (79% Hidden Maintenance Tax):** In the last 10 value-only updates (145 files touched), tests and documentation accounted for the vast majority of churn; source code changes were only 19%.
   - **6 Test Files with High Churn:** Over half of all test edits were concentrated in just 6 files due to hardcoded model slugs and literal member tuples.
   - **19 ➔ 1 Hand-Edited File:** Updating a model (such as Grok 4.7) currently touches 19 files across the repo; the target architecture collapses this to a single hand-edited file.

2. **Core Architectural Insights (The Three Pillars):**
   - **1 · The Audit & Reality:**
     - Runtime is *already* single-sourced: the TUI prompt input widget and the Rust LSP already consume the same Python-assembled `model_catalog.json`. There is no TUI vs. LSP divergence to solve.
     - Merely moving values into YAML without fixing tests and docs saves almost nothing (19 files ➔ 18 files). The real fix is addressing the "test tax" and documentation generation.
   - **2 · The Unified Manifest (`src/sase/llm_provider/models.yml`):**
     - Single hand-edited YAML manifest replacing `model_alias_defaults.yml` and provider code literals.
     - Section 1: `providers:` (built-in models, display order, short aliases, tier defaults, `supersedes:` tracking, and optional `status: legacy`).
     - Section 2: `size_aliases:` (alias pools `@xsmall` through `@xlarge`).
     - Built-in provider hooks become thin readers; plugin hook contracts and Rust wire schemas stay unchanged.
   - **3 · Policy Rules as Code (R1–R5):**
     - `R1 Membership`: Pool ⊆ Catalog (warns on legacy models).
     - `R2 Capability`: Member effort levels validated against provider capability.
     - `R3 Effort Ladder`: Automated descent rule enforcement via `supersedes:` lineage tracking (with optional `--fix` flag).
     - `R4 Redundancy`: Every size alias guaranteed to reach ≥2 distinct providers.
     - `R5 Shape`: Frozen graph-shape contract preserved.

3. **New Maintainer Workflow (1 Edit, 1 Regen, Zero Test Churn):**
   - **Step 1:** Edit `models.yml` (add new model or swap alias pool).
   - **Step 2:** Run `just fix` (automatically regenerates all doc tables: `known-models`, `short-aliases`, `tier-defaults`, `model-alias-defaults`).
   - **Step 3:** Run `just check` (executes R1–R5 rules and the CI docs drift check).
   - **Step 4:** Commit (1 hand-edited file + 1 regenerated doc, 0 test edits).

4. **Key Decisions & Guardrails:**
   - **Tests Assert Rules, Not Slugs:** Tests derive expectations from registry metadata and assert behavioral invariants.
   - **Strict CI Docs Drift Check:** `tools/render_model_docs --check` wired into `fmt-check`, `just check`, and GitHub Actions.
   - **Examples Illustrative, Not Fresh:** Help text and placeholders only need to name an existing model, eliminating arbitrary sample updates.
   - **No Data in `sase-core`:** Keeps Python plugin hook extensibility and avoids multi-repo release friction for simple model bumps.
