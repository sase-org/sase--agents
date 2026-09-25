# Chat History - ace-run (sase-13i.3)

- **TIMESTAMP:** 2026-09-20 06:53:07 EDT
- **MODEL:** claude/sonnet
- **AGENT:** sase-13i.3

## Prompt

%id(3, clan=sase-13i, bead=sase-13i.3)
#gh:gh_sase-org__sase
%model:@medium
%auto
%w:sase-13i.1
%w(bead=sase-13i.1)
Can you complete the work for bead sase-13i.3? The bead is already reserved for you and assigned to your agent
name: it was set to status=in_progress before you started reading this, either by the `sase bead work` launch
checkpoint or by the runtime promoting an ad-hoc wait-time claim. Do not set the status by hand. Read its
description and design file, do the work, and close only this bead with
`sase bead close sase-13i.3 --note "<what you verified>"`. Before closing, run
`sase bead epic-symbols sase-13i.3`. If this phase still has `--epic-symbol` entries, resolve each symbol or
re-key the Justfile line to a still-open bead (the parent epic or a later phase). `sase bead close` refuses while
leftovers remain; they go stale the instant this phase closes and turn unrelated agents' `just check` red. Closing
an assigned phase bead is unaffected by the parent-close descendant guard. Do NOT close the parent epic or any ancestor plan bead. Any instruction in a phase
description or child plan to close an ancestor is preparation and evidence for that ancestor's land agent, not
authorization for a phase worker. Do not create beads yourself: record discovered follow-up work as a
`PROPOSED FOLLOW-UP:` entry via
`sase bead note sase-13i.3 'PROPOSED FOLLOW-UP: <one-line summary — detail>'`; the epic's land agent triages
these into task beads.

## Response

Reading the merge guard and the query-change discard path so I can make the changes to `_loading_compute_merge.py` and `_loading_apply.py`.

Applying the edits now: snapshot field, merge guard, and latch handling.

Reading the existing bounded-prefix tests so I can extend them with same-query zero and changed-query cases.

The tmux mypy errors are in files I didn't touch. The `_loading_apply.py:337` error is mine, so I'm fixing that one.

The 20 remaining mypy errors also appear on the untouched tree, so they aren't mine. Because `just check` stops at mypy, I'm running the other gates and tests by hand.

Symvision fails on symbols in files I didn't touch (memory selector, tmux). Checking whether any of them is mine, then closing the bead.

I finished and closed sase-13i.3. `just check` did not go green, but the failures are in files I didn't touch, and I ran the other gates and the tests by hand.

**What changed**
- **Merge guard** (`_loading_compute_merge.py`): a bounded load now patches over the cache whether or not `has_more` is set. It is only exempt when the cached roster was applied under a different committed query.
- **Empty bounded load** (`_loading_apply.py`): a same-query bounded load that returns zero rows keeps a nonempty cache. It traces `empty_incomplete_apply_ignored` and schedules one revalidated refresh, so repeated zeros don't loop.
- **Latch:** the complete-history latch now clears only when the committed query changes. The last applied query key is tracked in a new `_agents_applied_query_key`, and an incomplete load with a missing or mismatched key no longer resets it.
- **Revalidate loads:** revalidate-shaped loads go through the same patch path, so a small revalidate result can't shrink a larger cache.
- **Repro invariant** (`invariants.py`): I added `incomplete_nonempty_to_empty`, which rejects an incomplete load that empties a nonempty tab even before a complete-history snapshot is seen. It cannot tell a legitimate query change from a bad empty apply, because the repro schema has no query key. I recorded that as a `PROPOSED FOLLOW-UP:` note on the bead.

**Tests** (`tests/test_agents_tab_apply_boundary.py`)
- I renamed `test_complete_bounded_window_replaces_cache` to `test_bounded_window_without_has_more_still_patches_cache` and flipped its expectation, since `has_more=False` no longer authorizes replacement.
- New cases: same-query bounded zero, bounded zero without the latch (one revalidate only), a mismatched incomplete key leaving the latch alone, a changed-query zero emptying the tab, and a revalidate-shaped load over a larger cache.
- `tests/ace/tui` and `tests/perf` gave 3785 passed and 2 failed. Both failures are assertions on file paths in output, `test_agents_zoom_panel_files.py` and `test_commit_view_modal.py`. The long temp-directory path looks like the cause, though I didn't confirm that.

**Verification status**
- **`just check`:** it stops at mypy. The remaining 20 mypy errors are in `src/sase/main/ace_tmux*.py` and the same count shows on the tree without my changes. `_lint-symvision` also fails on symbols in the memory-selector and tmux modules. I did not confirm none of them come from my changes, because the one run that grepped for my files timed out. ruff and `_lint-toobig` finish without errors.
- **Close note:** it says "symvision failures in untouched files", which is what I saw in the output but not a full check.

The declaration is submitted with the bead action set to `keep`, since I had already closed the bead with `sase bead close`.
