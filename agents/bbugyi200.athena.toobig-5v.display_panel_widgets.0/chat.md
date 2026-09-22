# Chat History - ace-run (toobig-5v.display_panel_widgets.0)

- **TIMESTAMP:** 2026-09-22 18:41:15 EDT
- **MODEL:** muse/muse-spark-1.3-contributor
- **AGENT:** toobig-5v.display_panel_widgets.0

## Prompt

%id(display_panel_widgets.0, clan=toobig-5v)
%model:@medium
%auto
%queue(capacity=3)
#gh:gh_sase-org__sase Can you help me split the `src/sase/ace/tui/actions/agents/_display_panel_widgets.py` file up into multiple files? Use your best
%wait:toobig-5v.agent_enter_targets.0
judgement, but let's aim to keep all files <=500 lines of code.

## Response

Done. The 738-line `_display_panel_widgets.py` is now five files, all well under 500 lines, with no behavior change (verbatim move plus two linter-driven adjustments noted below).

New layout in `src/sase/ace/tui/actions/agents/`:

- [_display_panel_widgets.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_32/src/sase/ace/tui/actions/agents/_display_panel_widgets.py) (43 lines) — compatibility facade. Re-exports `PanelWidgetRefreshMixin` and aggregates the three sub-mixins, following the existing `_display_detail.py` / `_display_panels.py` facade pattern.
- [_display_panel_widgets_keys.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_32/src/sase/ace/tui/actions/agents/_display_panel_widgets_keys.py) (110 lines) — pure row-identity/paint-key helpers.
- [_display_panel_widgets_mount.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_32/src/sase/ace/tui/actions/agents/_display_panel_widgets_mount.py) (205 lines) — `PanelWidgetMountMixin`: mount, unmount, reorder, sync.
- [_display_panel_widgets_paint.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_32/src/sase/ace/tui/actions/agents/_display_panel_widgets_paint.py) (251 lines) — `PanelWidgetPaintMixin`: collapse/content-staleness checks and single-panel repaint.
- [_display_panel_widgets_refresh.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_32/src/sase/ace/tui/actions/agents/_display_panel_widgets_refresh.py) (219 lines) — `PanelWidgetRefreshOrchestrationMixin`: shared paint context plus full/selective refresh entry points.

Two adjustments the linters required:

- Cross-mixin `self` calls in the refresh module use `# type: ignore[attr-defined]`, matching the existing `_try_insert_panel_rows` precedent.
- The four helpers shared across files (`panel_row_signature`, `panel_agents_match`, `panel_fold_inputs`, `panel_paint_key`) are now public, per the symvision rule against cross-file private imports — the same convention as `agent_panel_counts` / `agent_panel_border_title`. The test import `from _display_panel_widgets import _panel_fold_inputs` keeps working via a facade alias.

Verification: the 78 tests across the seven panel-display test files pass, and ruff plus mypy are clean on all five files. `just check` passes every gate except symvision, which fails on `delete_paths_in_background` in `src/sase/_linked_repo_workspaces.py` — I confirmed via stash that this failure exists identically on clean master, so it is pre-existing and unrelated. Same for one `test_pr_unmirrored_counts_cache` failure, also reproduced on clean master. The remaining tail of the full non-visual `tests/ace/tui` suite is still running; if it surfaces anything beyond those two known failures I will follow up.
