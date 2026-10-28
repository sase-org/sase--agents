# Chat History - ace-run (toobig-8p.catalog_gen.0)

- **TIMESTAMP:** 2026-10-27 20:14:05 EDT
- **MODEL:** grok/grok-4.6
- **AGENT:** toobig-8p.catalog_gen.0

## Prompt

%id:toobig-8p.catalog_gen.0
%clan(toobig-8p, tribe=chop, summary=[[[bold #D75FFF]◆ TOOBIG SPLIT · 3 FILES[/bold #D75FFF]
[bold #87D7FF]MISSION[/bold #87D7FF]
[dim #D7D7FF]Decompose oversized Python modules into focused, reviewable units[/dim #D7D7FF]
[dim #D7D7FF]without changing behavior.[/dim #D7D7FF]

[bold #87D7FF]TARGETS[/bold #87D7FF]
[#87D7FF]• 736  src/sase/ace/tui/widgets/decks/panel_spread.py[/#87D7FF]
[#87D7FF]• 707  tests/core/test_tool_run_store.py[/#87D7FF]
[#87D7FF]• 702  src/sase/footprint/catalog_gen.py[/#87D7FF]

[dim #A8A8A8]2 scan roots · limits 1,000 / 850 / 700 lines · sequential queue[/dim #A8A8A8]]])
%model:@medium
%auto
%queue(capacity=5)
#gh:gh_sase-org__sase Can you help me split the `src/sase/footprint/catalog_gen.py` file into multiple files? Use your best
judgment, but keep every resulting file at 500 lines of code or fewer.

Preserve behavior and the original module's public import path. A facade may re-export
public names, but never `_private` names. Never import a `_`-prefixed name across the
new modules. If more than one new module needs a helper, give it a public name inside an
already-private (`_`-prefixed) module; move a helper used by only one other module into
that module instead. Keep test monkeypatch targets working, or retarget the tests.

Before finishing, run `just _lint-symvision`, `just _lint-mypy`, and `just _lint-toobig`
individually. Fix every issue in a file the split touched, even if an earlier
`just check` stage is already red. Then run `sase tool run check`.

## Response

I'll split `catalog_gen.py` into modules of 500 lines or fewer, keep the public import path, and then run the requested lints. First I'll read the source, tests, and the lint/size rules.

I'll inspect the tests and similar package splits so the facade and private helpers match existing conventions.

I have a four-file layout: a shared private helper module, CLI/TUI generation, the remaining generators, and a public facade. Next I’ll write those files and retarget the tests.

I'll write the split modules and retarget the tests that reach into private helpers.

I'll wire `ENTRY_KEYS` through the shared helper so the facade still exports it and it isn't a dead name.

Symvision failed on stale epic-symbol flags in the Justfile, so I’ll inspect the recipe and scan the split files directly.

Split `src/sase/footprint/catalog_gen.py` into four modules, each well under 500 lines. `sase.footprint.catalog_gen` is still the public import path.

| File | Role | Lines |
|---|---|---|
| `catalog_gen.py` | Facade: `generate_entries`, `render_catalog`, `ENTRY_KEYS` | 99 |
| `_catalog_gen_shared.py` | Shared `Entry` type and helpers | 45 |
| `_catalog_gen_commands.py` | CLI parser tree and TUI keymap generation | 282 |
| `_catalog_gen_content.py` | Views, modals, macros, skills, config, AXE, plugins | 292 |

Cross-module helpers use public names inside the private `_catalog_gen_*` modules. Tests that called `catalog_gen._load_bundled_config`, `_package_resource`, `_flatten_mode_keys`, and `_gen_tui` now import from those modules.

Verification:
- `just _lint-mypy` and `just _lint-toobig` passed
- `tests/footprint/test_catalog.py`: 20 passed
- `just _lint-symvision` and `sase tool run check` failed on stale `--epic-symbol` entries in the Justfile for closed beads `sase-1p1.2` and `sase-1p1.3`. Those are outside the split files; scanning the split itself reported no unused or misused symbols.
