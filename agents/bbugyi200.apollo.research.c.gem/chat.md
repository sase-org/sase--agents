# Chat History - ace-run (research.c.gem)

- **TIMESTAMP:** 2026-09-25 19:45:00 EDT
- **MODEL:** agy/gemini-3.8-flash-high
- **AGENT:** research.c.gem
- **PROMPT:** `~/.sase/multi_prompts/202609/gh_sase_org__sase-multiprompt-260925_193845.md`

## Prompt

%id(gem, clan=research.c)
%m:agy/gemini-3.8-flash-high %q(w=0.25)
#gh:gh_sase-org__sase 
You are researcher gem in a 4-researcher swarm.
The other researchers, `research.c.cld`, `research.c.grk`, `research.c.mus`, are independently investigating the same request and will write their own self-named reports ending in `__cld.md` and `__grk.md` and `__mus.md`. Your report will end in `__gem.md`.

Conduct your research independently and form your own conclusions. Do NOT attempt to
locate, open, read, or otherwise consult the other researcher's report from this swarm,
even if it becomes available before you finish. Do not obtain that peer's findings
indirectly through its chat transcript, summaries, or requests to the peer. You may
independently use the same external sources, shared input material, and unrelated prior
research. You may check filenames or file existence to avoid overwriting your own
output, but do not inspect the peer's report contents. If you encounter its filename,
leave the report alone. The lead researcher will read every report and synthesize their
findings after you have all finished.

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

# Research Summary: Streamlining SASE Size Model Alias Pools and Completion Catalog Maintenance

**Researcher**: `gem` (`research.c.gem`)  
**Report Artifact**: [`file:explicit:45bb4a2afb6ca889bfdb2caf`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_22/sase/repos/research/202609/size_model_aliases_and_completion_catalog_maintenance__gem.md)  
**Registered Label**: `research:202609/size_model_aliases_and_completion_catalog_maintenance__gem.md`  
**Absolute Path**: `/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_22/sase/repos/research/202609/size_model_aliases_and_completion_catalog_maintenance__gem.md`

---

## 1. Critique of the Plan

### Is Making This Easier a Good Idea?
**Yes, emphatically.** In an ecosystem where LLM frontier and mid-tier models update on a 4-to-8 week cadence, the current maintenance friction is severe and directly measurable from repository history:
- **Grok 4.7 Support (`1cea18e00f`)**: **19 files** changed.
- **GPT-6 Sol Selection (`682089c845`)**: **28 files** changed.
- **Retune Size Aliases to Effort Ladder (`65c8169f9d`)**: **16 files** changed.

Maintainers currently have to touch Python provider classes, default alias YAML, example configurations in `default_config.yml`, Markdown tables in `docs/llms.md`, modal placeholders, and multiple unit test suites. This friction discourages routine upgrades, leads to partial updates, and wastes time recalculating effort ladder rungs.

### Risks and Pitfalls of "Updating as Few Files as Possible"
A naive consolidation ("put everything into one file") introduces several hidden failure modes:
1. **Conflation Hazard**: The *universe of completable models* (e.g. mini models, legacy models, testing models like `fakey`) is significantly larger than the *curated, effort-laddered subset* in size aliases (`@xsmall`..`@xlarge`). If completion is restricted solely to what is in size aliases, users lose completion for 80% of valid models.
2. **The "Test Tax" Trap**: Over 70% of historical diffs were in **brittle unit tests** asserting exact string literals (e.g., `assert "gpt-6-sol" in model_entries` or parametrized checks asserting `codex/gpt-5.6-terra`). Merging code and config into 1 file while leaving tests untouched would still cause CI to fail across 5–10 test files on every model bump.
3. **Dynamic Discovery Anti-Pattern**: Attempting to dynamically query provider CLIs (e.g., `codex models`) or APIs fails SASE's offline/CI invariant, introduces unacceptable startup and completion latency, and clutters completions with non-coding models (embeddings, moderation, etc.).

---

## 2. Adjustments to the Requirements

1. **Two-Tier Declarative Manifest**: The configuration must explicitly separate:
   - *Provider Model Catalogs*: All supported models per provider, short display aliases, supported reasoning effort levels, and advisories.
   - *Size Alias Routing*: The mapping of `@xsmall`..`@xlarge` to load-balanced pools, fallback chains, and explicit effort levels.
   Both will live in a single unified YAML file (`src/sase/llm_provider/catalog.yml`).
2. **Preserve Third-Party Pluggy Extensibility**: Built-in providers will delegate their `llm_known_model_names()` and `llm_model_short_aliases()` hooks to the central catalog, but the hook specifications remain untouched so external third-party plugins remain fully compatible.
3. **Decouple Test Assertions into Property Invariants**: Shipped-alias tests must test *invariants* (valid selector parsing, target resolvability, multi-provider redundancy, and Decision 15 effort ladder descent) rather than hardcoded model strings. Mechanical tests (routing, round-robin, error recovery) must run against frozen synthetic fixtures (`tests/_model_alias_defaults_fixture.py`).
4. **Automated Documentation Synchronization**: The Markdown tables in `docs/llms.md` must be generated or linted directly against the catalog via `just check`.
5. **Zero-Touch Editor & LSP Wire Parity**: The existing `MODEL_COMPLETION_CATALOG_SCHEMA_VERSION = 1` JSON wire payload generated by `model_completion_catalog_payload()` remains identical. Neither the Rust `sase-xprompt-lsp` binary nor the ACE Textual UI widgets require code changes.

---

## 3. Recommended Solution: Unified Declarative Manifest (`catalog.yml`)

### Architecture Overview

```
                        src/sase/llm_provider/catalog.yml
                       [ Unified Manifest (schema_version: 2) ]
                       ├─ providers: (known models, shorthands, effort, tiers)
                       └─ size_aliases: (@xsmall .. @xlarge pools/fallbacks)
                                       │
                ┌──────────────────────┴──────────────────────┐
                ▼                                             ▼
  [ Built-in LLMProvider Plugins ]              [ Model Alias Policy Loader ]
    codex.py, claude.py, grok.py...               sase.llm_provider.catalog
    (1-line hook delegations)                     - Validates Decision 15 ladder
                │                                 - Enforces provider redundancy
                ▼                                             │
  [ LLM Registry Metadata ]                                   │
    get_llm_metadata_payload()                                │
                │                                             │
                └──────────────────────┬──────────────────────┘
                                       ▼
                       [ Completion Catalog Builder ]
                      sase.xprompt.model_completion
                       - build_model_completion_catalog()
                       - model_completion_catalog_payload()
                                       │
                    ┌──────────────────┴──────────────────┐
                    ▼                                     ▼
         [ ACE Prompt Input Bar ]              [ External Editors (LSP) ]
           Textual TUI completion                xprompt_lsp writes model_catalog.json
           Rust filter binding                   Consumed by sase-xprompt-lsp (Rust)
```

### Maintainer Experience: Before vs. After
When adding a new model (e.g., `gpt-6.5-turbo`) and promoting it to `@medium`:
- **Current State**: Maintainer edits **11+ files** (`codex.py`, `model_alias_defaults.yml`, 4 test files, 2 documentation tables in `docs/llms.md`, `default_config.yml`), manually re-computes effort ladder rungs, and fixes broken test assertions.
- **Recommended Solution**: Maintainer edits **exactly 1 file** (`catalog.yml`):
  1. Adds `gpt-6.5-turbo: { short: gpt65t }` under `providers.codex.models`.
  2. Updates `size_aliases.medium` to use `codex/gpt-6.5-turbo@xhigh`.
  Running `just check` automatically validates Decision 15 effort ladder compliance and updates documentation tables. **Zero test failures. Zero LSP changes.**

---

## 4. Snapshot Registration & Artifact Status

The complete research report has been written and registered in durable artifact storage:
- **Source File**: `/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_22/sase/repos/research/202609/size_model_aliases_and_completion_catalog_maintenance__gem.md`
- **Artifact ID**: `explicit:45bb4a2afb6ca889bfdb2caf`
- **Artifact Ref**: `file:explicit:45bb4a2afb6ca889bfdb2caf`
- **Finalizer Declaration**: Sealed and submitted via `sase final submit` for host commit.
