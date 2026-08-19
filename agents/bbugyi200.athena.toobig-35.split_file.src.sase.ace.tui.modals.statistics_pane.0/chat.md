# Chat History - ace-run (toobig-35.split_file.src.sase.ace.tui.modals.statistics_pane.0)

- **TIMESTAMP:** 2026-08-18 23:36:17 EDT
- **MODEL:** claude/opus
- **AGENT:** toobig-35.split_file.src.sase.ace.tui.modals.statistics_pane.0
- **PROMPT:** `~/.sase/multi_prompts/202608/sase_org_sase-multiprompt-260818_225904.md`

## Prompt

#gh:sase-org/sase
%id:toobig-35.split_file.src.sase.ace.tui.modals.statistics_pane.0
%clan(toobig-35, tribe=chop, summary=[[[bold #D75FFF]◆ TOOBIG SPLIT · 12 FILES[/bold #D75FFF]
[bold #87D7FF]MISSION[/bold #87D7FF]
[dim #D7D7FF]Decompose oversized Python modules into focused, reviewable units[/dim #D7D7FF]
[dim #D7D7FF]without changing behavior.[/dim #D7D7FF]

[bold #87D7FF]TARGETS[/bold #87D7FF]
[#87D7FF]• 828  tests/test_suite_gate.py[/#87D7FF]
[#87D7FF]• 815  tests/ace/tui/test_agent_panel_titles.py[/#87D7FF]
[#87D7FF]• 769  tests/test_axe_run_agent_exec_retry.py[/#87D7FF]
[#87D7FF]• 755  src/sase/plugins/github_source.py[/#87D7FF]
[#87D7FF]• 753  tests/test_run_agent_runner_lifecycle.py[/#87D7FF]
[#87D7FF]• 751  tests/ace/tui/test_retry_edit_agent_name.py[/#87D7FF]
[#87D7FF]• 745  src/sase/ace/tui/modals/statistics_pane.py[/#87D7FF]
[#87D7FF]• 736  tests/test_config_schema.py[/#87D7FF]
[#87D7FF]• 730  tests/test_running_field_operations.py[/#87D7FF]
[#87D7FF]• 705  src/sase/main/project_handler.py[/#87D7FF]
[dim #A8A8A8]…and 2 more[/dim #A8A8A8]

[dim #A8A8A8]2 scan roots · limits 1,000 / 850 / 700 lines · sequential queue[/dim #A8A8A8]]])
%wait(runners=3)
%auto %wait(priority=20) Can you help me split the `src/sase/ace/tui/modals/statistics_pane.py` file up into multiple files? Use your best
judgement, but let's aim to keep all files <=500 lines of code.

## Response

I'll start by looking at the file.

Now I have the full picture. Let me build the split — extracting exact bodies with `sed` to avoid transcription drift.

Now the trimmed main module:

Now the two tests that read module-level tab constants via `sp.`:

Now install and run the lint/type gates:

Split is complete and verified. Now let me file the pre-existing failures I hit during verification.

`src/sase/ace/tui/modals/statistics_pane.py` is split from 745 lines into three modules, following the mixin-chain pattern the rest of the `statistics_pane_*` family already uses.

## The split

| File | Lines | Contents |
|---|---|---|
| `statistics_pane_layout.py` (new) | 155 | Tab/tile constants (`_VIEW_TABS`, `_VIEWS_*_BELOW_WIDTH`, `OVERVIEW_TILE_TARGETS`), the `_StatTile` / `_CustomRangeInput` widgets, and `StatisticsPaneLayoutMixin` with `compose()` + `_close_custom_range()` |
| `statistics_pane_actions.py` (new) | 357 | `StatisticsPaneActionsMixin` — `on_key`, every `action_*`, the range/group/project/xprompt cycles, scroll, click and `Input.Submitted` handlers, `_set_view`, `_selection_changed` |
| `statistics_pane.py` | 291 | `StatisticsPane` — state in `__init__`, mount/unmount/resize/visibility lifecycle, and the range-resolution + worker load path |

MRO is now `StatisticsPane → ActionsMixin → LayoutMixin → StatisticsPanePresentationBase` (each mixin is a Widget subclass, so Textual's `@on` handler discovery keeps working).

Two decisions worth knowing about:

- **The load path stayed in `statistics_pane.py` on purpose.** Tests monkeypatch `load_statistics_view`, `resolve_preset`, `resolve_current_project`, and `_REFRESH_INTERVAL_SECONDS` on that module's namespace, so everything reading those globals had to stay there. The actions mixin declares `_resolve_current_range` / `_schedule_load` as hooks the pane implements, and `_cycle_range` now goes through `self._resolve_current_range()` instead of calling `resolve_preset` directly — same result, single resolve path.
- **Four test files updated** to import `_StatTile`, `OVERVIEW_TILE_TARGETS`, and the tab-width constants from `statistics_pane_layout` rather than re-exporting private names across modules (symvision forbids cross-file private imports from non-test code, and re-exports would have been the thing it flags).

## Verification

`just lint` passes clean (ruff, mypy, symvision, toobig). 205 statistics/config-center tests pass, plus all 16 Statistics PNG snapshots — pixel-identical, so the rendering is unchanged.

`just check` surfaced 3 failures, all pre-existing and unrelated; I confirmed each and recorded them:
- `test_plugins_pane_lazy_fetches_highlighted_latest_when_flag_on` — reproduces on a clean stashed master tree; already root-caused on in-progress epic `sase-qn`, added a corroboration note.
- `test_candidates_fast_path_wall_clock_budget[agent]` — `+1` on existing task `sase-pg` (a third affected parametrization).
- `test_facade_try_disable_one_winner_under_process_contention` — provider-disable lock acquire times out under a 14-worker lane; noted on epic `sase-n4.5`, which owns that lock.

One thing outside what you asked: three siblings in this family were already over 500 lines before this change — `statistics_pane_rendering.py` (571), `statistics_pane_perf.py` (538), `statistics_pane_xprompts.py` (525). Happy to split those too if you want the whole family under the limit.

These are my changes from the split. Committing them now.

Committed and pushed as `e395acd4c`; the working tree is clean and `master` is level with `origin/master`.

**What landed:** `src/sase/ace/tui/modals/statistics_pane.py` split from 745 lines into three modules under the 500-line target, using the mixin-chain pattern the rest of the `statistics_pane_*` family already follows:

| File | Lines | Contents |
|---|---|---|
| `statistics_pane_layout.py` (new) | 155 | Tab/tile constants, `_StatTile` / `_CustomRangeInput`, `StatisticsPaneLayoutMixin` (`compose`, `_close_custom_range`) |
| `statistics_pane_actions.py` (new) | 357 | `StatisticsPaneActionsMixin` — `on_key`, all `action_*`, range/group/project/xprompt cycles, scroll/click/`Input.Submitted` handlers, `_set_view`, `_selection_changed` |
| `statistics_pane.py` | 291 | `StatisticsPane` state, mount/unmount/resize/visibility lifecycle, range resolution + worker load path |

Four test files were updated to import the moved names from `statistics_pane_layout` directly rather than through re-exports.

Two things to flag:

- The commit printed a warning: this project has **15 quarantined agent-hood publication requests**, so the agent link written into this commit may not resolve until you run `sase agent sync --retry-quarantined`. The commit and push themselves succeeded.
- Three siblings in this family were already over 500 lines before this change and I left them alone: `statistics_pane_rendering.py` (571), `statistics_pane_perf.py` (538), `statistics_pane_xprompts.py` (525). Say the word if you want the whole family brought under the limit.
