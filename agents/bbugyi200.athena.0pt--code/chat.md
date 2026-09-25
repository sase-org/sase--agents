# Chat History - ace-run (0pt--code)

- **TIMESTAMP:** 2026-09-23 09:59:19 EDT
- **MODEL:** muse/muse-spark-1.3-contributor
- **AGENT:** 0pt--code

## Prompt

%model:@small
#gh:gh_sase-org__sase @plan:202609/hide_idle_dispatch_context_line.md

The above plan has been reviewed and approved. Implement it now.


## Response

Plan implemented. The idle `Target here local Source <project>` line no longer renders on ordinary local prompts, even with remote targets enrolled.

Changed files:
- [src/sase/ace/tui/widgets/_prompt_input_bar_dispatch.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_38/src/sase/ace/tui/widgets/_prompt_input_bar_dispatch.py) — `_dispatch_context_text` returns `(Text(), "ok", False)` immediately when there is no `%dispatch` selector (parse errors still return visible/error), and the visibility rule is now `visible = scan is not None`. Docstring updated. No changes to the picker, preflight, height accounting, or styles.
- [tests/ace/tui/widgets/test_prompt_dispatch_context_line.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_38/tests/ace/tui/widgets/test_prompt_dispatch_context_line.py) — new sibling module with 5 tests: idle prompt hidden with seeded targets, idle prompt hidden with a catalog-unavailable override, `%dispatch:apollo` visible with Target/apollo/Source text, duplicate directive visible with `error` class and `Target error`, and a direct `_dispatch_context_text` unit check.
- [docs/ace.md](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_38/docs/ace.md) and [docs/remote_dispatch.md](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_38/docs/remote_dispatch.md) — short notes that the line appears only with a `%dispatch` selector (or an invalid one).

Verification observed:
- New tests: 5 passed. With the fix stashed, the 3 idle-path tests fail and the 2 `%dispatch`-path tests pass, confirming the regression coverage is genuine.
- Existing `test_dispatch_target_picker_focus.py` plus all `test_prompt_input_bar_*.py` modules: 88 passed.
- Prompt-bar PNG goldens (stack, inputs, editing): 22 clean. The `prompt_search_highlight` golden drifts, but I proved it pre-existing by reproducing the identical drift on the pristine tree with my changes stashed (diff is a tiny pill-background raster region, no dispatch line involved), so per the plan I left it unregenerated and filed it as [sase-16w](ci, small, ready, linked to sibling sase-16o).
- `sase tool run check` is blocked by a pre-existing symvision failure (`ExpandedLaunchSegments` unused-public in `launch_cwd_segments.py`, untouched by this change, introduced by cfac28d15). Exact duplicate [sase-16u](already tracked) corroborated with a +1 and independent reproduction.
