# Chat History - ace-run (0px--code)

- **TIMESTAMP:** 2026-09-23 10:13:21 EDT
- **MODEL:** muse/muse-spark-1.3-contributor
- **AGENT:** 0px--code

## Prompt

%model:@small
#gh:gh_sase-org__sase @plan:202609/ctrl_k_project_tag_history_seed.md

The above plan has been reviewed and approved. Implement it now.


## Response

Implemented the approved Ctrl+K `+<project>` seed plan.

Changed files:
- [prompt_history_project_filter.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_37/src/sase/history/prompt_history_project_filter.py): `build_prompt_history_seed_from_draft` now also scans `find_project_tags`, skips literal zones, applies D3 (anchored always counts, unanchored only if `catalog.resolve_ref` resolves), and picks the earliest VCS/tag span.
- [test_prompt_history_project_filter.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_37/tests/history/test_prompt_history_project_filter.py): added 11 cases from the plan (anchored, case-insensitive, directive, unanchored resolvable, literal-zone, unknown anchored/unanchored, both mixed orders).
- [test_prompt_history_modal_project_filter.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_37/tests/ace/tui/modals/test_prompt_history_modal_project_filter.py): added real-flow Ctrl+K test asserting `+sase fix parser` settles on `project:sase fix parser`.

Verification:
- `tests/history/test_prompt_history_project_filter.py`: 25 passed.
- `tests/ace/tui/modals/test_prompt_history_modal_project_filter.py`: 14 passed.
- Spot check `build_prompt_history_seed_from_draft("+sase fix the bug", real catalog)` returns `project:sase fix the bug`.
- `sase tool run check` fails only on the known master-red `symvision: ExpandedLaunchSegments` in `src/sase/agent/launch_cwd_segments.py` (task sase-16u), unrelated to this change.

Docs: `docs/ace.md` already describes `+sase` becoming `project:<name>`; no change needed.
