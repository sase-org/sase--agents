# Chat History - ace-run

- **TIMESTAMP:** 2026-07-08 17:38:16 EDT
- **MODEL:** claude/opus
- **AGENT:** research.3.cld
- **PROMPT:** `~/.sase/multi_prompts/202607/gh_sase_org__sase-multiprompt-260708_173045.md`

## Prompt

%name:research.@.cld %m:@research_assist %g:research #gh:gh_sase-org__sase I am seriously thinking about renaming sase xprompt to sase plang. Can you do some research to help me critique this idea? End your analysis with a recommendation for whether or not I should move forward with this rename. Keep in mind that the cost of implementation is not a factor. I want to make sure that we have the best naming conventions in place possible. After concluding with your research, express a summary of your answer via SASE variables. Write this research to a new markdown file under the sdd/research/$(date +%Y%m)/ directory.


## Response

I'll research this thoroughly. Let me start by understanding what "xprompt" actually is in the codebase, how widely the term is used, and then analyze the rename proposal.

"xprompt" is deeply embedded (836 files, 10,513 raw matches) and "plang" has zero existing conflicts. Let me understand the concept deeply and map the user-facing surfaces before analyzing the rename.

I'll investigate the SASE codebase thoroughly. Let me start with parallel exploration of the key areas.

Key finding already: the plain word "prompt" is heavily used as its own concept (`prompt_part`, `prompt_panel`, `PromptDirectives`), and xprompt replaced a "legacy snippet system." Let me map the user-facing CLI/config surfaces and the term's history while the explorer works.

The term is heavily used. Let me read the core definition sources: the module docstring, glossary, docs intro, and config.

Excellent, the glossary is very informative. Let me read the docs intro, config files, and CLI definitions.

There's a full `sase xprompt` CLI command (5 subcommands), an xprompt LSP ("language server"), config keys (`xprompts`, `xprompt_aliases`), and permission scopes. Let me get the canonical definition and check what the "x" connotes.

Let me examine the CLI parser, default config, the prompt.md doc, and the "prompt" collision concept.

Let me read the default config sections and search for other coined short names and the trigger syntax.

Let me investigate the "x" prefix meaning, other coined terms, the prompt_part step, and TUI modal labels.

Let me look at the reference syntax docs, TUI modal labels, and search for any explicit "x" expansion.

I have strong evidence. One notable collision: there's already an "xprompt **language server**" — so "plang" (prompt-language) would produce "prompt-language language server." Let me verify one external factual claim — whether "Plang" already exists as a product/language in the AI space — before I assert it.

Let me check the user-created xprompts/ directory, generated skills, and do a repo-wide search for any expansion of the "x".

Strong finding: **"Plang" is already an established name in this exact domain** — a published LLM prompt-engineering DSL (ScienceDirect / Expert Systems with Applications) *and* a separate natural-language programming language (plang.is). Let me grab the last config-surface details and let the explorer finish.

Key finding: blog posts call xprompt "the prompt language." Let me read those and confirm the naming culture and skill sources.

Let me confirm the discovery/directory conventions and the config schema field, plus check for any dedicated file extension.

I have comprehensive coverage. Let me do one final check on how the term is described in the agent instructions and confirm the "x" is never expanded.

I now have comprehensive, well-grounded evidence across all dimensions. Let me write the research document. (I'll fold in the explorer's synthesis if it adds anything material.)

I now have a thorough picture. Here is my report.

---

# "xprompt" in the SASE codebase — findings for the "plang" rename

## 1. Definition / semantics — what an xprompt is, and what "x" means

The clearest authoritative definitions:

- Module docstring, `src/sase/xprompt/__init__.py:1`:
  > "XPrompt system for typed prompt templates with argument validation. This module provides a replacement for the legacy snippet system, adding: Markdown files with YAML front matter for defining input arguments … Type validation … Backward compatibility with existing `#name(args)` syntax … YAML workflow support for multi-step agent workflows."

- Docs intro, `docs/xprompt.md:3`:
  > "XPrompts are reusable prompt templates with optional typed inputs and Jinja2 support. They let you define a prompt fragment once and reference it by name anywhere a prompt is composed … Inline prompt fragments use `#name`; standalone workflows use `#!name`."

- Glossary, `memory/glossary.md:42` (also copied verbatim into `CLAUDE.md`/`AGENTS.md`/etc.):
  > "**xprompt** — Triggered with `#foo` in agent prompts. Defined in an `xprompts/` directory (.md or .yml file) or in `~/.config/sase/sase.yml` (`xprompts` field)."

- README one-liner, `README.md:85`:
  > "**XPrompt** — Prompt templates and YAML workflows with reference expansion, typed inputs, output-variable handoffs, and workflow visualization."

**What does "x" stand for? Nothing documented.** I searched docs/, README, CLAUDE.md, and the whole `src/` tree for any expansion (extended / executable / extensible / expansion / experimental / cross). There is **no** definition of the "x" anywhere. The `x` functions purely as a disambiguating prefix that separates the concept from the plain word "prompt." Notably, the system's own text expands the abbreviation the *opposite* way from "plang": the CamelCase form is always written **"XPrompt"** (capital P), i.e. "X-Prompt," never "eXtended-prompt." So "x" is a bare prefix, not an initialism for a word.

## 2. User-facing surfaces where "xprompt" appears

This term is pervasive on user-facing surfaces — a rename touches all of these:

- **CLI command group** `sase xprompt` with 5 subcommands — `expand`, `explain`, `list`, `graph`, `catalog` (`docs/xprompt.md:62-133`; parser at `src/sase/main/parser_xprompt.py`, help text: `help="Expand and visualize xprompt workflows"`). Handler: `src/sase/main/xprompt_handler.py`.
- **Config keys** (all in `src/sase/default_config.yml` and validated in `src/sase/config/sase.schema.json`):
  - `xprompts:` — the map of config-defined xprompts (`default_config.yml:415`, `sase.yml:27`)
  - `xprompt_aliases:` — `default_config.yml:412`, schema `sase.schema.json:1062`
  - `auto_xprompt_menu: true` — `default_config.yml:61` ("automatically open the xprompt/skill completion menu")
  - keymap `start_last_vcs_xprompt_in_editor: "ctrl+g"` — `default_config.yml:121`
  - chop config field `xprompt:` — "XPrompt reference to run instead of a chop script" (`sase.schema.json:467`, `671`)
- **User-created directory names**: `xprompts/` and hidden `.xprompts/` at CWD and home (`docs/xprompt.md:178-193` discovery-order table). No dedicated file extension — xprompts are plain `.md` / `.yml` / `.yaml` files (confirmed: no `.xprompt` extension exists).
- **Trigger syntax**: confirmed `#foo` triggers an inline xprompt; `#name(args)`, `#name:arg`, `#name+`, `#ns/name`; standalone workflows use `#!name` (`docs/xprompt.md:255-271` reference-syntax table; glossary line 42-43).
- **TUI labels / modals**:
  - Modal title `Label("Select XPrompt", …)` and IDs `xprompt-list`, `xprompt-filter-input`, `xprompt-modal-container`, `xprompt-panels` (`src/sase/ace/tui/modals/xprompt_select_modal.py:218`)
  - `src/sase/ace/tui/modals/xprompt_browser_preview.py:1` "Preview and metadata formatting for the XPrompt browser pane."
  - ACE Admin Center has an **"XPrompts"** tab: `README.md:105` "press # for the Admin Center (Config / Logs / Projects / Tasks / Updates / XPrompts)".
- **LSP / editor**: `sase lsp` is "the SASE xprompt language server"; env override `SASE_XPROMPT_LSP_CMD` (`docs/xprompt.md:137`, `docs/editor.md:12`, `docs/cli.md:173`, `src/sase/integrations/xprompt_lsp.py`). Plugin entry-point group is `sase_xprompts` (`docs/xprompt.md:191`).
- **Skills**: agent skills are described as "aka xprompt skills," generated from source templates in `src/sase/xprompts/skills/` via `sase skill init` (`memory/generated_skills.md:5,21`). The bundled skill sources are `.md` files in `src/sase/xprompts/skills/` (sase_plan.md, sase_run.md, etc.).

Note there are **three** similarly named directories that would all be implicated:
- `src/sase/xprompt/` — the Python code module
- `src/sase/xprompts/` — bundled/built-in xprompt library (`workflow.schema.json`, `skills/`, `examples/`, `steps/`, and many `.md`/`.yml` templates)
- `xprompts/` (repo root) — this project's own project-local xprompts (e.g. `sync.md`, `pylimit_split.yml`)

## 3. Related terminology — composition

From `memory/glossary.md:34-50` (verbatim):
- **"Multi-agent xprompt"** — "An xprompt whose body contains `---` segment separators (outside fenced blocks)."
- **"xprompt Part"** — ".md file → single `prompt_part` step with the file's content."
- **"xprompt Workflow"** — ".yml file → multiple steps (`prompt_part`, `python`, `bash`, etc.)."

These compose as noun phrases: "multi-agent xprompt," "xprompt part," "xprompt workflow." Test file names mirror this: `tests/test_multi_agent_xprompt_parsing.py`, `test_multi_prompt_launcher_xprompt_groups.py`, `test_bead_xprompt_tags.py`. A "plang" rename would have to read as "plang part," "plang workflow," "multi-agent plang" — where "plang workflow" is arguably redundant (a plang IS partly about workflows) and "multi-agent plang" loses the "prompt" cue that explains what is being split.

## 4. The "prompt" collision — this is the strongest evidence for your critique

The plain word **"prompt"** is already a heavily loaded, *distinct* first-class concept, separate from xprompt:

- **`sase prompt` is an entire separate command group** — prompt *history* (list/show/search/run/edit/select/delete/prune/save/export), documented in its own `docs/prompt.md`. Its intro: "The `sase prompt` command group is the first-class way to inspect, search, reuse, curate, and clean up that history" (`docs/prompt.md:9`). This sits right next to `sase xprompt`. A "plang = prompt language" rename collides directly with `sase prompt` (history) vs a hypothetical `sase plang`.
  - Interesting overlap: `sase prompt save` already "Save a prompt as a reusable **xprompt** markdown file" (`docs/prompt.md:48`) — so both "prompt" and "xprompt" appear on the same table row.
- **`prompt_part`** is the workflow step type for prompt text (`src/sase/xprompt/workflow_models.py:70,95,125`).
- **`PromptDirectives` / `extract_prompt_directives`** (`src/sase/xprompt/directives.py`, exported from `__init__.py:34`).
- **TUI widgets** carry the bare "prompt" name: `prompt_panel/` widget package, `prompt_input_bar.py`, `_prompt_input_bar_completion.py`, `_prompt_preview_target.py`, `_prompt_bar_stash.py`, etc. — 46 Python files reference `prompt_panel`/`prompt_input_bar`/`PromptDirectives`.
- **The docstrings/docs literally already call the xprompt system "the prompt language."** This is the crux:
  - `docs/editor.md:44`: "The xprompt language server is focused on prompt and xprompt editing" — note it distinguishes "prompt" editing from "xprompt" editing in the same sentence.
  - Blog `docs/blog/posts/prompt-widget-and-nvim.md:117`: heading "sase-nvim: The Neovim Side Of **The Prompt Language**"; line 149: "the prompt language is the contract."
  - Blog `docs/blog/posts/why-coding-agents-need-orchestration.md:465`: "SASE exposes an **XPrompt language server**."

So "plang" (prompt-language) would formalize a name (prompt language) that the project currently uses *informally and interchangeably* for the whole xprompt surface — while the bare word "prompt" simultaneously denotes (a) the literal text a user types, (b) the `sase prompt` history feature, (c) `prompt_part` steps, and (d) the `prompt_panel`/`prompt_input_bar` UI. Adopting "plang" risks blurring the currently-crisp `prompt` (the text/history) vs `xprompt` (the template/language) distinction, since "plang" re-injects "prompt" as its root.

## 5. Naming culture / precedents for coined short names

SASE strongly favors short, punchy, often 3-4 letter coined names, mostly **not** documented as acronyms:

- **ACE** — the interactive TUI ("The interactive TUI for ChangeSpecs, live agents…", `README.md:83`). No expansion is given anywhere; used as a bare name (`sase ace`).
- **AXE** — the background automation daemon (`README.md:84`; `docs/axe.md`). Only ever expanded loosely as "automation daemon," never as a true acronym.
- **bead(s)** — git-portable issue tracking (`docs/beads.md`, `sase bead`). A coined common-noun term.
- **`.gp`** — ChangeSpec storage files (`memory/glossary.md:24`).
- **SDD** — spec-driven development/planning (`docs/sdd.md`).
- **ChangeSpec** — CamelCase coined term for a PR-sized unit.
- **gp / cd / gh / git / hg** — short reference prefixes.

So a short coined name like "plang" is *stylistically* consistent with SASE's culture (ace/axe/bead). The stylistic fit is fine. The substantive risks are the two points above: (a) the "x" carries no meaning to preserve, but "XPrompt" is written X-Prompt everywhere, and (b) "plang"'s "prompt" root collides with an already-busy `prompt` namespace (`sase prompt` history, `prompt_part`, `prompt_panel`, and the informal "the prompt language" already meaning xprompt).

### Related design/plan docs already in-repo (useful background for your proposal)
`sase_plan_save_draft_as_xprompt.md`, `sase_plan_lsp_local_xprompts.md`, `sase_plan_xprompt_effort.md`, `sase_plan_vcs_xprompt_mru_all_launch_paths.md`, `sase_plan_xprompt_completion_skip_space_before_punctuation.md`, and `sase_plan_snippet_reference_syntax.md` (xprompt as the successor to the "snippet" system).

The explorer surfaced two findings that materially sharpen the analysis — I'll fold them in. Most important: **`sase prompt` is already a separate top-level command group** (prompt history), and the project *already informally calls xprompt "the prompt language"* in its own blog/docs. Both change the strength of key arguments.

The research doc is complete and refined. Now let me express the summary via SASE variables as requested.

Done. Research written to `sdd/research/202607/xprompt_to_plang_rename_analysis.md`, and the summary is published as SASE output variables (`recommendation`, `verdict`, `top_reason`, `cheaper_fix`, `report_path`). Since the only file change is a markdown file under `sdd/research/`, `just check` is not required per the repo rules.

## Recommendation: **Do not rename `xprompt` → `plang`. Keep `xprompt`.**

I stipulated implementation cost aside and judged purely on naming quality. `plang` loses on the substantive criteria and only wins on cosmetics.

**The four decisive problems with `plang`:**

1. **It fails as a count noun.** `xprompt` names both the system *and* each artifact — "write an xprompt," "three xprompts," the `xprompts:` config dict. A "language" has no instances: `plangs:` (a dict of many "languages") is nonsensical, yet that's the term's most common usage.

2. **It collides with an already-busy `prompt` namespace — including a whole sibling CLI.** `sase prompt` is its own top-level command group (prompt *history*: list/search/save/…). `plang` re-injects "prompt" as its root, so `sase plang` would sit next to `sase prompt` as a near-homophone. Today's `sase prompt` vs `sase xprompt` is far more distinguishable — that's exactly what the `x` prefix buys you.

3. **"language server" tautology.** There's already an *xprompt language server* (`sase lsp`). Rename → "prompt-language language server."

4. **External brand collision in the exact same domain.** "Plang" is already an established LLM prompt-engineering DSL (published in *Expert Systems with Applications*) *and* a natural-language programming language (plang.is). Adopting it makes the feature non-distinctive and un-Googleable. `xprompt` has zero external collisions and is trivially greppable (~10,500 in-repo hits, 0 for `plang`).

**The honest steel-man** (why the idea is tempting): the system really has matured into a DSL, the `x` is undocumented/opaque, and the project *already informally calls it "The Prompt Language"* in its own blog. But that framing works precisely *as prose*, not as a proper noun competing with `prompt` — and the opacity of `x` is fixable by documenting it, not renaming.

**Cheaper fix that addresses the real itch:** document `x` as an intentional namespace marker ("X-Prompt": a prompt-derived artifact, distinct from a raw `prompt`), and keep the "prompt-templating language" framing in prose. You get the DSL-honest framing without breaking the count noun, without the `sase prompt` collision, and without the external clash.

Sources for the external-collision claim:
- [Plang: Efficient prompt engineering language… (ScienceDirect)](https://www.sciencedirect.com/science/article/pii/S0957417425037339)
- [Plang — natural-language programming language](https://plang.is)

I made this change — I created the research document in this session. I'll commit it using the commit skill.

I'll record skill usage, then examine the changes before committing.

The change is a new research markdown doc — `docs` tag is appropriate. Let me write the commit message and commit.

The commit succeeded and the working tree is clean, with `master` in sync with `origin/master` (nothing ahead/behind).

## Summary

I committed the research document I created in this session:

- **File:** `sdd/research/202607/xprompt_to_plang_rename_analysis.md`
- **Commit:** `docs: research xprompt-to-plang rename critique`
- **Method:** `create_commit` (committed and pushed via the `sase_git_commit` skill; `just fix` precommit ran clean)

No `just check` was required — the only change is a markdown file under `sdd/research/`, which is an explicit exception in the repo rules.

The research itself stands as delivered: my recommendation is **do not rename `xprompt` → `plang`** (it fails as a count noun, collides with the busy `prompt` namespace and the sibling `sase prompt` command, creates a "language server" tautology, and clashes with an existing external "Plang" brand in the same domain), with a cheaper fix being to simply document the `x` prefix as an intentional namespace marker.
