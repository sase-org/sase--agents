# Chat History - ace-run (sase-ay.4)

- **TIMESTAMP:** 2026-07-29 18:50:47 EDT
- **MODEL:** claude/opus
- **AGENT:** sase-ay.4

## Prompt

#gh:gh_sase-org__sase
%id(4, clan=sase-ay, bead=sase-ay.4)
%model:@small_phase_worker
%auto
Can you complete the work for bead sase-ay.4? The bead is already reserved for you and assigned to your agent
name: it was set to status=in_progress before you started reading this, either by the `sase bead work` launch
checkpoint or by the runtime promoting an ad-hoc wait-time claim. Do not set the status by hand. Read its
description and design file, do the work, and close the bead with
`sase bead close sase-ay.4 --note "<what you verified>"`. Closing an assigned phase bead is unaffected by the
parent-close descendant guard. Do NOT close the parent epic. Do NOT create new beads.

## Response

I'll start by reading the bead.

Now implementing. First the shared helper in the pure-logic module:

Now the panel:

Now the caller that computes the scroll offset:

Now the tests:

Now the full check plus the visual suite:

Waiting on `just check`.

`just check` is running in the background (its output is buffered through `tail`, so nothing shows until it exits). I'll report as soon as it lands.

Implementation so far:

- `file_completion.py`: new `COMPLETION_PANEL_MAX_HEIGHT`/`COMPLETION_PANEL_BORDER_ROWS`/`COMPLETION_PANEL_CONTENT_ROWS` mirrors plus `completion_visible_rows()` and `completion_scroll_offset()`, which reserve a line for `↓ N more…` on overflow and another when a group rule is drawn.
- `_prompt_input_bar_completion_panel.py`: slices with the shared budget, takes a `group_rule` flag, and sources its height mirrors from the same constants.
- `_file_completion_base.py`: scroll offset now comes from `completion_scroll_offset`, with a `_completion_group_rule_reserved()` seam for the grouped `@` menu.
- Dropped the now-unreferenced `MAX_VISIBLE` (the plan asked to keep it exported, but nothing in or out of `src/` imports it anymore, and a dead public constant would be misleading — the row budget is no longer 10).
- `docs/ace.md`: the "up to 10 candidates" sentence now states the real budget.

Symvision failures are pre-existing (identical on a clean tree, all from the unrelated `sase-ax` epic whitelist). Running the test suites:

All good. Closing the bead:

Bead `sase-ay.4` is closed. What landed:

**`src/sase/ace/tui/widgets/file_completion.py`**
- `COMPLETION_PANEL_MAX_HEIGHT` (10), `COMPLETION_PANEL_BORDER_ROWS` (2), `COMPLETION_PANEL_CONTENT_ROWS` (8) — the CSS mirrors now live next to the logic that consumes them.
- `completion_visible_rows(total, *, group_rule=False)` — the real content capacity, minus one line for `↓ N more…` when candidates overflow, minus one more when a group rule is drawn.
- `completion_scroll_offset(total, selected_index, *, group_rule=False)` — same budget, so the window and the highlight can't disagree.

**Callers** — `_file_completion_base.py` derives its offset from the shared helper and passes a new `group_rule` flag through to `show_file_completions`, which slices with the same budget. `_completion_group_rule_reserved()` is the seam the grouped `@` menu (sase-ay.7) overrides. `_prompt_input_bar_completion_panel.py`'s height reservation now reads the shared constants instead of its own copies.

Verification: new tests cover the D7 defect directly (15 candidates, last row selected → highlight is in the rendered lines, content ≤ 8 lines, panel height still ≤ the CSS cap of 10), plus the budget arithmetic and an exhaustive selection-index sweep with and without a group rule. `just test`: 23877 passed. No PNG golden churn — no existing snapshot menu renders more than eight rows, so the visual suite passed untouched.

Two things to flag:

- **`just check` fails on symvision, pre-existing.** Ten stale `sase-ax(...)` `--epic-symbol` entries in the Justfile. Identical failure on a clean stashed tree; it belongs to that epic, so I left the whitelist alone rather than collide with its in-flight work. Everything else in `just check` is green.
- **One flaky test**, `test_input_collection_modal.py::test_growing_last_field_keeps_cursor_visible_in_fields_scroll` — failed under the parallel/random-order run, passes in isolation, unrelated to completion.

I deviated from the plan on one point: it asked to keep `MAX_VISIBLE` exported for compatibility, but after the refactor nothing in `src/` or `tests/` imported it and 10 is no longer the row budget, so I deleted it instead of leaving a misleading dead constant. I also fixed the "up to 10 candidates" sentence in `docs/ace.md`, which my change invalidated — the rest of the doc updates stay with the `docs` phase. Nothing is committed.

Bead is closed. Committing now.

Committed and pushed — working tree clean, branch level with `origin/master`.

**Commit** `53b34965f fix(ace): keep completion panel rows within budget`

The bead `sase-ay.4` was already closed before the commit (the wrapper's close step was idempotent). What landed:

- **`file_completion.py`** — `COMPLETION_PANEL_MAX_HEIGHT` / `_BORDER_ROWS` / `_CONTENT_ROWS` mirrors, plus `completion_visible_rows()` and `completion_scroll_offset()`, which reserve a content line for `↓ N more…` on overflow and another when a group rule is drawn. `MAX_VISIBLE` removed (no consumers left, and 10 is no longer the row budget).
- **`_file_completion_base.py`** — scroll offset comes from the shared helper; new `_completion_group_rule_reserved()` seam for the grouped `@` menu (sase-ay.7).
- **`_prompt_input_bar_completion_panel.py`** — slices with the shared budget, takes a `group_rule` flag, reads the shared height constants.
- **`docs/ace.md`** — the stale "up to 10 candidates" sentence now states the real budget.
- **Tests** — the D7 defect case (15 candidates, last row selected → highlight is inside the rendered window, content ≤ 8 lines, panel height ≤ CSS cap), budget arithmetic, and an exhaustive selection-index sweep with and without a group rule.

Two carryovers I flagged earlier and did not change: `just check`'s symvision step fails identically on a clean tree (10 stale `sase-ax` `--epic-symbol` entries, that epic's territory), and `test_input_collection_modal.py::test_growing_last_field_keeps_cursor_visible_in_fields_scroll` is flaky under parallel/random order but passes in isolation — unrelated to completion.
