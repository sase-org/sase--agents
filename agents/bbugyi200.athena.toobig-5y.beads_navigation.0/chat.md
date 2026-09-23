# Chat History - ace-run (toobig-5y.beads_navigation.0)

- **TIMESTAMP:** 2026-09-23 19:03:24 EDT
- **MODEL:** muse/muse-spark-1.3-contributor
- **AGENT:** toobig-5y.beads_navigation.0

## Prompt

%id(beads_navigation.0, clan=toobig-5y)
%model:@medium
%auto
%queue(capacity=3)
#gh:gh_sase-org__sase Can you help me split the `src/sase/ace/tui/widgets/artifacts/beads_navigation.py` file up into multiple files? Use your best
%wait:toobig-5y.plugins_browser_install.0
judgement, but let's aim to keep all files <=500 lines of code.

## Response

Done. The 805-line `beads_navigation.py` is now four files, all ≤500 lines, with no behavior change.

**Split** (in `src/sase/ace/tui/widgets/artifacts/`):

- [beads_navigation.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/src/sase/ace/tui/widgets/artifacts/beads_navigation.py:1) (347 lines) — core `BeadsNavigationMixin`: selection, stable entry targets, epic-fold expansion, option-list accessors. It now inherits the two mixins below and re-exports them plus `BeadsOptionList`, so existing imports in `beads_pane.py` / `beads_options.py` keep working.
- [beads_option_list.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/src/sase/ace/tui/widgets/artifacts/beads_option_list.py:1) (55 lines) — `BeadsOptionList`.
- [beads_navigation_hydration.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/src/sase/ace/tui/widgets/artifacts/beads_navigation_hydration.py:1) (260 lines) — `BeadsNavigationHydrationMixin` (reveal context, query row, hydrate/install/reindex) with its private helpers `_bead_row_kind` / `_merge_bead_into_snapshot` moved alongside their only callers.
- [beads_navigation_detail.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/src/sase/ace/tui/widgets/artifacts/beads_navigation_detail.py:1) (231 lines) — `BeadsNavigationDetailMixin` (detail/preview, conditional footer) with `_can_launch_bead_row` / `_bead_row_is_snoozable` alongside.

Each helper moved with its sole caller, so no new private cross-file imports. Explicit `DetailMixin._conditional_footer_entries(self, …)` dispatch preserves the duck-typed fake-host contract the snooze test relies on (my first version used `self.` dispatch and broke it; fixed).

**Also updated:** `tests/ace/tui/test_artifacts_beads_navigation.py` patches the hydration module's `_resolve_projects` / `_project_beads_dir` aliases (the actual lookup site now), following the file's documented patch-alias pattern.

**Verification:** `just fmt` clean; ruff, mypy (4847 files), keep-sorted, toobig all pass; 27/27 tests pass in `test_artifacts_beads_navigation.py` + `test_bead_snooze_modal.py`.

**Findings (pre-existing, not caused by this change):** `just check` stops at `lint (pyscripts)` (Rule 2 closer-dir errors for visual-maintenance tool refs) and `just _lint-symvision` flags 4 private imports in the `plugins_browser` split. Both reproduce byte-identically on the clean tree (verified via `git stash`). Filed as ready triage beads `sase-17b` (pyscripts) and `sase-17c` (symvision), with `sase-17b` related-linked to the earlier distinct instance `sase-12n`.

Declaration accepted for `commit`.
