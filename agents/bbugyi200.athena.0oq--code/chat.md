# Chat History - ace-run (0oq--code)

- **TIMESTAMP:** 2026-09-21 15:23:11 EDT
- **MODEL:** muse/muse-spark-1.3-contributor
- **AGENT:** 0oq--code

## Prompt

%model:@medium
#gh:gh_sase-org__sase @plan:202609/agents_panel_focus_follows_selection.md

The above plan has been reviewed and approved. Implement it now.


## Response

Implemented the approved `202609/agents_panel_focus_follows_selection.md` plan.

**What changed** (presentation-only, no `sase-core` touch):
- [ `_display_panel_collection.py`](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_31/src/sase/ace/tui/actions/agents/_display_panel_collection.py:204) — `_sync_panel_group` now lets panel focus follow a renderable selection instead of snapping the cursor to the focused panel. Focus is treated as deliberately parked (old snap preserved) for whole-panel focus, banner focus, collapsed/empty focused strips, and a cursor stranded in a collapsed panel.
- [ `_loading_state.py`](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_31/src/sase/ace/tui/actions/agents/_loading_state.py:241) — new `_capture_agents_apply_selection()` helper holding the existing capture logic.
- [ `_loading_disk_full.py`](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_31/src/sase/ace/tui/actions/agents/_loading_disk_full.py:272) and [ `_loading_disk_delta.py`](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_31/src/sase/ace/tui/actions/agents/_loading_disk_delta.py:98) — re-capture the live selection synchronously at the apply seam, so navigation during worker awaits discards the stale finalize plan via the existing token check. No token change.
- [ `_loading_apply.py`](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_31/src/sase/ace/tui/actions/agents/_loading_apply.py:120) — captures `prior_pos` before the roster swap and forwards it to `_finalize_agent_list`, giving removed selections the same-panel neighbor fallback as kill/dismiss. Identity-found case unaffected.
- New [ `test_agents_panel_focus_follows_selection.py`](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_31/tests/ace/tui/test_agents_panel_focus_follows_selection.py:1) — 12 tests covering M1b, M1a, parked (a)/(b)/(c) plus collapsed-focus and cursor-in-collapsed branches, both async apply seams, off-tab capture, and both `prior_pos` wirings. No AceApp boot, so no host-leak risk. Existing arrival-frame expectations untouched (56 passed).

**One judgment call to flag:** the plan's parked predicate as literally written (slice-empty check) missed collapsed strips, which broke 3 existing collapse tests. I refined it per the plan's own "refine the parked predicate" instruction and its §4(b) spec ("focus on a collapsed or empty panel strip"): collapsed focus stays parked, and a cursor stranded in a collapsed panel snaps back out rather than dragging focus onto a hidden row. All previously-failing collapse tests pass unmodified.

**Verification:** 12/12 new tests pass; neighbors pass (panel index + apply boundary 34, collapse/dead-end/kill-focus 62, arrival frames 56). `just fix` clean; every `just check` gate passes except `symvision`, which I proved fails identically on pristine master (dead notification-modal symbols, untouched by this change), as do 8 scoped-lane failures in import-budget/bead-hooks/usage-config — all pre-existing.

**Deliberately skipped per plan:** sticky `live_keys` (§7.2), `ProgrammaticSelectionGuard` (refuted), daemon remediation (other plan's). Filed follow-up bead `sase-15n` (ready, large) for the stable container-row `selection_key` (§5.3).
