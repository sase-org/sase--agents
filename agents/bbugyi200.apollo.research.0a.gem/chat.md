# Chat History - ace-run (research.0a.gem)

- **TIMESTAMP:** 2026-10-04 16:58:21 EDT
- **MODEL:** agy/gemini-3.8-flash-high
- **AGENT:** research.0a.gem
- **PROMPT:** `~/.sase/multi_prompts/202610/gh_sase_org__sase-multiprompt-261004_164941.md`

## Prompt

%id(gem, clan=research.0a)
%m:agy/gemini-3.8-flash-high %q(1.5x, w=0.25)
#gh:gh_sase-org__sase 
You are researcher gem in a 4-researcher swarm.
The other researchers, `research.0a.cdx`, `research.0a.cld`, `research.0a.grk`, are independently investigating the same request and will write their own self-named reports ending in `__cdx.md` and `__cld.md` and `__grk.md`. Your report will end in `__gem.md`.

Conduct your research independently and form your own conclusions. Do NOT attempt to
locate, open, read, or otherwise consult the other researcher's report from this swarm,
even if it becomes available before you finish. Do not obtain that peer's findings
indirectly through its chat transcript, summaries, or requests to the peer. You may
independently use the same external sources, shared input material, and unrelated prior
research. You may check filenames or file existence to avoid overwriting your own
output, but do not inspect the peer's report contents. If you encounter its filename,
leave the report alone. The lead researcher will read every report and synthesize their
findings after you have all finished.

I would like to add support for a new `enum` macro input type in order to, for example,
add customizable completion for macro inputs in the prompt input widget and external
editors (via LSP support).

- Every input that has an enum type will need to specify the set of values that are
  allowed to be used for that enum. These values are just single-word strings, so enums
  are sort of like a sub-type of the existig `word` macro input type.
- We need to support re-using enum values so plugin providers and sase itself can share
  enum value sets. For example, this functionality will be required in order to allow
  users to specify that a macro they are defining has an input that only accepts a valid
  model string that is accepted by the `%model` directive. I'm imagining that we can use
  something like `builtin@model_enum_values` to specify that a macro input uses this type
  but you should think hard about the best way to do this.
- I want you to lead the design on this one. Make sure you design this feature so it is intuitive, reliable, and (last but not least) beautiful!

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

# Research Report Completed: First-Class `enum` Macro Input Types, Cross-Plugin Reusability, and Dual-Speed Completion Architecture

The independent research report for agent `gem` (`research.0a.gem`) has been written and registered as a durable artifact snapshot.

- **Report Path:** [`/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/sase/repos/research/202610/macro_enum_input_type_architecture__gem.md`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/sase/repos/research/202610/macro_enum_input_type_architecture__gem.md)
- **Artifact Ref:** `file:explicit:c4654a4659f5b2d7eb057f14`
- **Artifact Label:** `research:202610/macro_enum_input_type_architecture__gem.md`

---

## Key Findings & Strategic Critique

### 1. The Dormant Baseline
A deep dive into the codebase revealed that `enum` is **not absent**, but exists in a **dormant, half-implemented state**:
- **Python Models:** [`src/sase/macro/models.py`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/macro/models.py#L35) already defines `InputType.ENUM` and `InputChoice(value, label)`.
- **Parsing & Validation:** Frontmatter YAML parsing in [`loader_parsing.py`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/macro/loader_parsing.py#L109) and Rust [`sase-core`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/sase/repos/linked/sase-core/crates/sase_core/src/editor/frontmatter.rs#L883) already validate `choices: [...]` for `type: enum`.
- **The Severed Leg:** `choices` are stripped in `MacroInputHint` across both Python and Rust wire models, `sase-macro-lsp` hardcodes argument value completion to `bool_completion_list()`, the TUI prompt bar assist categorizes `enum` as non-completable, and [`workflow.schema.json`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/macros/workflow.schema.json#L27) omits `enum` entirely.

### 2. Critique of "Enums as a Sub-Type of `word`"
- **Token Constraints:** Bare colon macro invocations (`#macro:arg1,arg2`) split on whitespace and commas. Therefore, the machine **value** of an enum must be a single-word token (`[a-zA-Z0-9_\-\.:@]+`).
- **Token vs. Label Separation:** Machine tokens should not limit human display. The architecture must strictly separate the machine **value** (e.g. `sonnet` or `gemini-1.5-pro`) from human-friendly **labels** and **descriptions** (e.g. `Claude 3.5 Sonnet (Anthropic)`) rendered in completion menus, hover docs, and TUI argument hints.

### 3. Critique of `builtin@model_enum_values` & The `%model` Dichotomy
- **Naming:** `builtin@model_enum_values` is redundant and verbose. Following SASE conventions (`<source>@<slug>` like `builtin@commit`), it should be standardized as `builtin@models` (with alias `builtin@model`).
- **Static vs. Dynamic Value Sets:** Models, machines (`%dispatch`), and VCS projects (`+project`) are **dynamic runtime entities**, not static enums. Treating `%model` as a rigid, static allowlist would cause false-positive validation rejections whenever new models, user aliases, or provider overrides are introduced.
- **Dual-Speed Resolution:** Static enums (e.g. `[draft, ready, closed]`) must validate as closed sets at YAML load time. Dynamic catalogs (`builtin@models`, `builtin@machines`, `builtin@projects`) must resolve through live provider registries (`resolve_model_provider_with_effort()`), with graceful degradation if a provider is temporarily offline.

---

## Recommended Architectural Solution

```
┌────────────────────────────────────────────────────────────────────────┐
│                        ENUM RESOLUTION LAYERS                          │
├────────────────────────────────────────────────────────────────────────┤
│ 1. Builtin Dynamic Catalogs:                                           │
│    builtin@models   --> sase.macro.model_completion (LLM Registry)     │
│    builtin@machines --> sase.dispatch.machine_catalog (Dispatch hosts) │
│    builtin@projects --> sase.macro.vcs_projects (VCS catalog)          │
│    builtin@tribes   --> sase.config (Agent tribes)                     │
├────────────────────────────────────────────────────────────────────────┤
│ 2. Plugin Enums (via Entry Points or Plugin Config):                   │
│    sase_github@pr_status, sase_listen@voices, etc.                    │
├────────────────────────────────────────────────────────────────────────┤
│ 3. Project-Defined Enums:                                              │
│    sase/config.yml (enums:) or sase/enums/*.yml                        │
│    e.g. project@environments, @environments                            │
├────────────────────────────────────────────────────────────────────────┤
│ 4. Inline Enums:                                                       │
│    choices: [fast, slow] or [{value: fast, label: "Fast Mode"}]        │
└────────────────────────────────────────────────────────────────────────┘
```

### 1. Authoring Syntax
- **Inline Enums:**
  ```yaml
  input:
    mode:
      type: enum
      choices: [fast, slow, dry_run]
      default: fast
  ```
- **Shared / Reusable Enums:**
  ```yaml
  input:
    target_model:
      type: enum
      enum: builtin@models
      default: sonnet

    pr_status:
      type: enum
      enum: github@pr_status
  ```
- **Shortform Syntax:**
  ```yaml
  input:
    mode: enum(fast, slow, dry_run)
    target_model: enum(builtin@models)
    # Or direct type alias:
    target_model: builtin@models
  ```

### 2. Tiered Discovery & Enum Registry
- **Built-in:** `builtin@models`, `builtin@machines`, `builtin@projects`, `builtin@tribes`.
- **Plugins:** Discovered via `pyproject.toml` entry points `[project.entry-points.sase_enums]` or packaged plugin config.
- **Projects:** Configured in `sase/config.yml` under `enums:` or dedicated `sase/enums/<name>.yml` files, addressable as `project@<name>` or local `@<name>`.

### 3. Editor & LSP Completion Integration
- **Rust Core & Wire:** Thread `choices: Vec<MobileInputChoiceWire>` and `enum_ref: Option<String>` through `MacroInputHint` in [`crates/sase_core/src/editor/wire.rs`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/sase/repos/linked/sase-core/crates/sase_core/src/editor/wire.rs).
- **Macro LSP:** In `crates/sase_xprompt_lsp/src/server/completion.rs`, emit `CompletionItemKind::EnumMember` for macro inputs with declared choices or `enum_ref`. When `enum_ref == "builtin@models"`, reuse the existing LSP `model_completion_list()`.
- **TUI Prompt Bar Assist:** Connect `_macro_arg_assist_detection.py` and `_file_completion_macro_args.py` to present popup completions on `Ctrl+T`/`Tab` with styled badges (`#D7AF87`) and inline argument hints (`▸ mode: [fast|slow]`).

---

## Phased Implementation Roadmap

1. **Phase 1: Wire & Model Alignment** — Add `choices` and `enum_ref` to Python and Rust `MacroInputHint`; update `workflow.schema.json`.
2. **Phase 2: Inline Enum Autocomplete** — Enable TUI and LSP completion for inline `choices`.
3. **Phase 3: Shared Enum Registry** — Build `sase.macro.enums`, plugin entry point discovery, and project `enums:` loading.
4. **Phase 4: Dynamic Built-in Providers** — Connect `builtin@models`, `builtin@machines`, and `builtin@projects` to live catalogs in Python and LSP.
5. **Phase 5: TUI Aesthetics & Schema Polish** — Render rich argument hint overlays and searchable picker modals.

*Full details, code diff specifications, and comparative analysis are available in the linked research report.*
