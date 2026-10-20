# Chat History - ace-run (toobig-89.test_ace_png_snapshots_agents_deck_views.0)

- **TIMESTAMP:** 2026-10-20 06:49:15 EDT
- **MODEL:** grok/grok-4.6
- **AGENT:** toobig-89.test_ace_png_snapshots_agents_deck_views.0

## Prompt

%id:toobig-89.test_ace_png_snapshots_agents_deck_views.0
%clan(toobig-89, tribe=chop, summary=[[[bold #D75FFF]◆ TOOBIG SPLIT · 6 FILES[/bold #D75FFF]
[bold #87D7FF]MISSION[/bold #87D7FF]
[dim #D7D7FF]Decompose oversized Python modules into focused, reviewable units[/dim #D7D7FF]
[dim #D7D7FF]without changing behavior.[/dim #D7D7FF]

[bold #87D7FF]TARGETS[/bold #87D7FF]
[bold #FF5F87]▲ 1,253  tests/test_release_watch_health.py[/bold #FF5F87]
[bold #FFAF5F]◆   910  tests/test_qualification_transport_integration.py[/bold #FFAF5F]
[#87D7FF]•   842  tests/test_collect_qualification_jobs.py[/#87D7FF]
[#87D7FF]•   826  tests/test_release_candidate.py[/#87D7FF]
[#87D7FF]•   796  tests/test_github_actions_ci_workflow.py[/#87D7FF]
[#87D7FF]•   704  tests/ace/tui/visual/test_ace_png_snapshots_agents_deck_views.py[/#87D7FF]

[dim #A8A8A8]2 scan roots · limits 1,000 / 850 / 700 lines · sequential queue[/dim #A8A8A8]]])
%model:@medium
%auto
%queue(capacity=5)
#gh:gh_sase-org__sase Can you help me split the `tests/ace/tui/visual/test_ace_png_snapshots_agents_deck_views.py` file into multiple files? Use your best
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

I'll split that visual snapshot test module into files of 500 lines or fewer while preserving public imports and test behavior. First I'm reading the split rules, lint notes, and the current file.

I'll read the lint and split-related memory notes next, then inspect the snapshot test file and any existing split patterns.

I'll inspect the snapshot test file, nearby split patterns, and any toobig or monkeypatch constraints next.

The original file is 704 lines, so I’ll study similar splits and the file’s structure before cutting it.

I'll look at a completed split and any monkeypatch targets so the new modules keep the same public path.

I'll split along Main vs Files: shared public helpers in a private module, tests in two modules, and a facade that keeps the original import path.

All split files are under 500 lines. Next I’ll format, then run the three requested lints.

Format is clean. I'll run the three requested lints as separate commands next.

Symvision and mypy passed. The toobig failure is in an unrelated file; every file this split touched is under 500 lines. Next I’ll run `sase tool run check`.

Split `tests/ace/tui/visual/test_ace_png_snapshots_agents_deck_views.py` (704 lines) into four modules, each under 500 lines, with the original import path kept as a facade.

**Layout**
- `test_ace_png_snapshots_agents_deck_views.py` — facade (`__test__ = False`) that re-exports the public test names
- `_ace_agents_deck_views_png_snapshot_shared.py` — private module with public helpers used by more than one test file (`view_turn`, `title_plain`, `goto_agents`)
- `test_ace_png_snapshots_agents_deck_views_main.py` — Main-deck view tests, plus file-local `_view_session` and `_press_view`
- `test_ace_png_snapshots_agents_deck_views_files.py` — Files-deck view tests, plus file-local `_files_agent`, `_bundle_files_agent`, and `_media_agent`

No `_`-prefixed names are imported across modules. The facade re-exports only the public test functions.

**Verification**
- `just _lint-symvision` — pass
- `just _lint-mypy` — pass
- `just _lint-toobig` — split files are clean (75 / 50 / 467 / 200). The gate still fails on unrelated `tests/test_release_watch_health.py` (1253 lines)
- `sase tool run check` — succeeded
