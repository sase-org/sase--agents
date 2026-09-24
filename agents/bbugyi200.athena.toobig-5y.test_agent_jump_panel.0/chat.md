# Chat History - ace-run (toobig-5y.test_agent_jump_panel.0)

- **TIMESTAMP:** 2026-09-23 21:38:52 EDT
- **MODEL:** muse/muse-spark-1.3-contributor
- **AGENT:** toobig-5y.test_agent_jump_panel.0

## Prompt

%id(test_agent_jump_panel.0, clan=toobig-5y)
%model:@medium
%auto
%queue(capacity=3)
#gh:gh_sase-org__sase Can you help me split the `tests/ace/tui/widgets/test_agent_jump_panel.py` file up into multiple files? Use your best
%wait:toobig-5y.test_ace_png_snapshots_prompt_highlighting.0
judgement, but let's aim to keep all files <=500 lines of code.

## Response

Done. Split `tests/ace/tui/widgets/test_agent_jump_panel.py` (843 lines) into 4 topical test files plus a shared helper, and removed the original. All new files are well under 500 lines:

- [\_agent_jump_panel_helpers.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/tests/ace/tui/widgets/_agent_jump_panel_helpers.py) (117 lines) — shared harness: `_solo`, `_DetailApp`, `_show_agent`, `_jump_panel`, `_jump_text`, `_labeled_map`, `_labeled_map_and_roster`
- [test_agent_jump_panel_visibility.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/tests/ace/tui/widgets/test_agent_jump_panel_visibility.py) (197 lines) — 9 tests: hide/show, clan/tribe, layout positioning, search overlay, hint docs
- [test_agent_jump_panel_expansion.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/tests/ace/tui/widgets/test_agent_jump_panel_expansion.py) (166 lines) — 6 tests: toggle expand/collapse, roster repaint, state persistence, scroll reset, bottom pinning
- [test_agent_jump_panel_prefix.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/tests/ace/tui/widgets/test_agent_jump_panel_prefix.py) (203 lines) — 6 tests: prefix narrowing, dismissed/revive cells, empty narrow, subtitle, toggle availability, digit hooks
- [test_agent_jump_panel_numbers.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/tests/ace/tui/widgets/test_agent_jump_panel_numbers.py) (235 lines) — 4 tests: number presses through the real jump path (family, neighbor, dismissed, clan/tribe)

Verification performed:
- AST-compared every test/helper body old-vs-new: all 25 tests present exactly once, 0 mismatches — pure move, no behavior change.
- Targeted pytest on the 4 new files: 25/25 passed.
- `just fmt` / `just fix`: clean. `sase tool run check`: ruff, mypy, and all other gates passed except `lint (symvision)`.

Finding (not caused by this change): the symvision gate fails on private-import complaints across `src/sase/...` files, which this change does not touch — symvision only scans `src/sase`, and `git status` shows only the 6 test paths dirty, so the failure is pre-existing at HEAD. Also, `sase final prepare` was ineligible due to a protected path in an unrelated sidecar repo, so I verified inline and submitted the final declaration directly, which was accepted.
