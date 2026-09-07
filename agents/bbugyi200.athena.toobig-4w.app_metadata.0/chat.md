# Chat History - ace-run (toobig-4w.app_metadata.0)

- **TIMESTAMP:** 2026-09-07 07:41:04 EDT
- **MODEL:** grok/grok-4.6
- **AGENT:** toobig-4w.app_metadata.0

## Prompt

%id:toobig-4w.app_metadata.0
%clan(toobig-4w, tribe=chop, summary=[[[bold #D75FFF]◆ TOOBIG SPLIT · 4 FILES[/bold #D75FFF]
[bold #87D7FF]MISSION[/bold #87D7FF]
[dim #D7D7FF]Decompose oversized Python modules into focused, reviewable units[/dim #D7D7FF]
[dim #D7D7FF]without changing behavior.[/dim #D7D7FF]

[bold #87D7FF]TARGETS[/bold #87D7FF]
[#87D7FF]• 808  tests/ace/tui/visual/test_ace_png_snapshots_models_panel_modals.py[/#87D7FF]
[#87D7FF]• 777  src/sase/llm_provider/provider_priority.py[/#87D7FF]
[#87D7FF]• 719  src/sase/ace/tui/commands/_app_metadata.py[/#87D7FF]
[#87D7FF]• 711  src/sase/agent/names/_wipe.py[/#87D7FF]

[dim #A8A8A8]2 scan roots · limits 1,000 / 850 / 700 lines · sequential queue[/dim #A8A8A8]]])
%model:@medium
%auto
%wait(runners=3)
%wait(priority=20)
#gh:gh_sase-org__sase
Can you help me split the `src/sase/ace/tui/commands/_app_metadata.py` file up into multiple files? Use your best
judgement, but let's aim to keep all files <=500 lines of code.

## Response

I'll start by inspecting `_app_metadata.py` and how it's imported so we can split it cleanly while keeping each file under 500 lines.

The file is already a metadata catalog; next I’ll measure its size, map its public API, and see how neighboring command modules are split.

The catalog is 719 lines; I’ll read the rest of it plus tests so the split preserves the public API and snapshot coverage.

I’ll check whether a line-length or file-size lint already exists, and how similar command modules were split.

The repo already uses a 500-line split pattern. I’ll match that and check how sibling modules were named.

There's a size-cap memory note I should read before splitting, plus the lint rules I'll need for verification.

I’ll split along the existing section comments into three domain modules plus a thin facade, then generate the files so the tuple order stays exact.

I’ll generate the three domain modules from the current table so the catalog order stays identical, then replace `_app_metadata.py` with a concatenating facade.

The generated modules look right; I’ll tighten the type aliases and replace the original file with a facade that concatenates them.

I’ll put the shared row type in `types.py`, point the new modules at it, and turn `_app_metadata.py` into the concatenating facade.

Verification passed. I’ll collect the SASE finalizer context and submit the commit declaration.

Split `src/sase/ace/tui/commands/_app_metadata.py` (719 lines) along the existing section comments so each file stays well under 500 lines.

`_app_metadata.py` is now a thin facade. It still exports `APP_COMMAND_META` and `ensure_metadata_covers_app_keymaps()`, so `catalog.py` and the coverage tests did not need to change. The 157 catalog rows are concatenated in the original order from three domain tables:

| File | Contents | Lines |
|---|---|---|
| `_app_metadata.py` | Concatenation + AppKeymaps coverage guard | 55 |
| `_app_metadata_nav.py` | Navigation, tabs, artifact-pane commands | 260 |
| `_app_metadata_actions.py` | Patch, agent, axe, folding, and marking commands | 301 |
| `_app_metadata_display.py` | Grouping, queries, display, workspace, and mode commands | 164 |

The shared `AppCommandMeta` row type now lives in `types.py` next to `CommandCategory` / `CommandTab`, so the three tables do not each redeclare it.

I checked that the concatenated table matches the original 157 rows exactly. `just check` passed (lint including toobig/symvision, plus the scoped test lane).
