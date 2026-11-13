# Chat History - ace-run (research.4k.gem)

- **TIMESTAMP:** 2026-11-13 17:54:12 EST
- **MODEL:** agy/gemini-3.8-flash-high
- **AGENT:** research.4k.gem
- **PROMPT:** `~/.sase/multi_prompts/202611/gh_sase_org__sase-multiprompt-261113_174022.md`

## Prompt

%id(gem, clan=research.4k)
%m:agy/gemini-3.8-flash-high %q(1.5x, w=0.25)
#gh:gh_sase-org__sase 
You are researcher gem in a 5-researcher swarm.
The other researchers, `research.4k.cdx`, `research.4k.cld`, `research.4k.grk`, `research.4k.mus`, are independently investigating the same request and will write their own self-named reports ending in `__cdx.md` and `__cld.md` and `__grk.md` and `__mus.md`. Your report will end in `__gem.md`.

Conduct your research independently and form your own conclusions. Do NOT attempt to
locate, open, read, or otherwise consult the other researcher's report from this swarm,
even if it becomes available before you finish. Do not obtain that peer's findings
indirectly through its chat transcript, summaries, or requests to the peer. You may
independently use the same external sources, shared input material, and unrelated prior
research. You may check filenames or file existence to avoid overwriting your own
output, but do not inspect the peer's report contents. If you encounter its filename,
leave the report alone. The lead researcher will read every report and synthesize their
findings after you have all finished.

I would like to add support to sase for Google's new Argon and Hydrogen models.

- We should update all model completion surfaces to include these models.
- As a part of this change, we should update the `#research_swarm` macro to use the new
  Hydrogen model instead of the current Gemini model that we use for that macro swarm.

Can you do some research with the goal of helping me decide the best way to implement
this? End your analysis with a recommended solution. 
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

# Research Summary: Adding Support for Google Argon and Hydrogen Models & Modernizing `#research_swarm`

**Researcher:** gem (`research.4k.gem`)  
**Report Artifact:** `research:202611/google_argon_hydrogen_model_support__gem.md`  
**Absolute Path:** `/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/sase/repos/research/202611/google_argon_hydrogen_model_support__gem.md`  
**Artifact ID:** `explicit:c1fc0d4b7e14d44da50131d8`

---

### Executive Findings

1. **Model Landscape & Capabilities**:
   - **Gemini 4 Argon** (released October 2026): Google's frontier deep-reasoning model. Served in Antigravity (`agy`) as `gemini-4-argon-{high,medium,low}`. Gated to Google AI Ultra and Gemini Enterprise; SASE requires an entitlement advisory (`needs Google AI Ultra`) and excludes Argon from shipped size aliases and tier defaults so non-Ultra accounts do not fail.
   - **Gemini 4 Hydrogen** (released November 12, 2026): Google's high-efficiency workhorse model succeeding Flash. Served in Antigravity (`agy`) across four thinking depth levels:
     - `gemini-4-hydrogen-xhigh`
     - `gemini-4-hydrogen-high`
     - `gemini-4-hydrogen-medium`
     - `gemini-4-hydrogen-low`
     Hydrogen carries general availability (no Ultra requirement), requires no advisory, and is eligible for `agy` tier defaults and shipped size-alias pools.

2. **Model Completion Surfaces in SASE**:
   - SASE's completion architecture centers on `src/sase/llm_provider/models.yml`. Updating this manifest automatically propagates across nearly all completion surfaces without Python code changes:
     - **ACE TUI Prompt Input Directives** (`%model:`, `%m:` via `sase.macro.model_completion`)
     - **ACE TUI Model Picker Modal** (`ModelPickerModal` via `sase.llm_provider.registry`)
     - **ACE TUI Macro Argument Model Completion** (`#macro(model=...)` via `_file_completion_macro_args.py`)
     - **Model Alias (`@`) and Explicit Shortcut (`=`) Completion**
     - **Editor Macro LSP Server** (`sase-macro-lsp`)
     - **CLI Shell Option Completion** (`sase completion`)
     - **Generated Documentation Tables** (`docs/reference/providers/models.md` via `tools/render_model_docs`)
   - **Required Code Change**: `src/sase/ace/tui/widgets/_agent_list_helpers.py` (`short_model_name`) contains an explicit keyword matching list. Adding `"hydrogen"` ensures agent badges render as `hydrogen` rather than falling back to `gemini`.

3. **Updating `#research_swarm` to Hydrogen**:
   - Macro definition: `sase/repos/linked/sase-research-artifacts/src/sase_research_artifacts/xprompts/research_swarm.md`.
   - **Recommended Default**: `agy/gemini-4-hydrogen-xhigh`.
     - *Rationale*: All other swarm researchers run at maximum reasoning effort (`codex/gpt-6.1-sol@xhigh`, `claude/opus@xhigh`, `grok/grok-4.6@xhigh`, `muse/muse-spark-1.3-contributor@xhigh`). Antigravity rejects explicit `@effort` suffixes and relies on the model slug; Hydrogen introduces Google's first `-xhigh` slug for workhorse/Flash-class models, achieving parity with the rest of the swarm.
   - **Input Parameter**: Retain `gemini_model` for 100% backward compatibility (the model family remains Gemini: `Gemini 4 Hydrogen`), keeping `.gem` and `__gem.md`. Update description to document the `-xhigh` slug.
   - **Companion Updates**: Update `@image` pool in `sase-research-artifacts/src/sase_research_artifacts/default_config.yml` to use `agy/gemini-4-hydrogen-xhigh`.

---

### Recommended Implementation Steps

#### Phase 1: Primary `sase` Repository
1. **`src/sase/llm_provider/models.yml`**:
   - Add `gemini-4-hydrogen-xhigh`, `gemini-4-hydrogen-high`, `gemini-4-hydrogen-medium`, and `gemini-4-hydrogen-low` to `providers.agy.models`.
   - Add short aliases: `hydro4x`, `hydro4h`, `hydro4m`, `hydro4l`.
   - Update `providers.agy.tiers` to `large: gemini-4-hydrogen-high`, `small: gemini-4-hydrogen-low`.
   - Update shipped `@xsmall` size alias to `agy/gemini-4-hydrogen-high`.
2. **`src/sase/ace/tui/widgets/_agent_list_helpers.py`**:
   - Add `"hydrogen"` to the `short_model_name()` keyword loop.
3. **Tests & Docs**:
   - Add tests for `short_model_name` and update `tests/llm_provider/` test suites.
   - Run `just fix` to regenerate documentation tables in `docs/reference/providers/models.md` and check model policy via `just check`.

#### Phase 2: Linked `sase-research-artifacts` Repository
1. Open the repository via `sase repo open sase-research-artifacts`.
2. In `src/sase_research_artifacts/xprompts/research_swarm.md`, update `gemini_model` default to `"agy/gemini-4-hydrogen-xhigh"`.
3. In `src/sase_research_artifacts/default_config.yml`, update the `@image` pool to reference `agy/gemini-4-hydrogen-xhigh`.
4. Update tests in `tests/test_macro_loading.py` and `tests/test_default_config.py`.
5. Run `just check` within `sase-research-artifacts`.
