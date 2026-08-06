# Chat History - ace-run (sase-gi.4)

- **TIMESTAMP:** 2026-08-06 16:40:13 EDT
- **MODEL:** claude/opus
- **AGENT:** sase-gi.4

## Prompt

#gh:gh_sase-org__sase
%id(4, clan=sase-gi, bead=sase-gi.4)
%model:@medium_phase_worker
%auto
%w:sase-gi.1
%w(bead=sase-gi.1)
Can you complete the work for bead sase-gi.4? The bead is already reserved for you and assigned to your agent
name: it was set to status=in_progress before you started reading this, either by the `sase bead work` launch
checkpoint or by the runtime promoting an ad-hoc wait-time claim. Do not set the status by hand. Read its
description and design file, do the work, and close the bead with
`sase bead close sase-gi.4 --note "<what you verified>"`. Closing an assigned phase bead is unaffected by the
parent-close descendant guard. Do NOT close the parent epic. Do not create beads yourself: record discovered
follow-up work as a `PROPOSED FOLLOW-UP:` entry via
`sase bead note sase-gi.4 'PROPOSED FOLLOW-UP: <one-line summary — detail>'`; the epic's land agent triages
these into task beads.

## Response

I'll start by reading the bead.

Now I'll write the ordered nest/unnest planner.

Truthy dataclass, good. Now add the import and update the comment:

Now let me sanity-check the planner behavior with a quick script before writing tests.

Now the test file:

Install finished. Running the new tests:

The dot-capture remap collapses when the plan replaces a range rather than inserting. Let me fix that mapping:

I'll wait for `just check` to finish.

`just check` is still running; I'll report when it completes.

I'll check the current state of the work.

All 32 new tests pass. Now the full `just check`:

Lint gates pass now. The one failure is in an unrelated timing test — let me check if it's flaky:

The work is complete and verified. Now closing the bead:

The close published cleanly (no unpublished-state error). Now committing:

Committed and pushed; working tree clean and in sync with `origin/master`.

## What I did (bead sase-gi.4)

**New module** `src/sase/ace/tui/widgets/_prompt_ordered_shift_editing.py` — `plan_prompt_ordered_shift()` plans one INSERT-mode nest/unnest of the ordered item under the cursor:

- **Tab** moves the item to its parent's *content column* (not a fixed two-space unit — an ordered item indented two spaces under `1. ` is still a CommonMark sibling). Starting a new nested list numbers it `1`; landing under an existing nested run continues that run.
- **Shift+Tab** moves the item out to its parent's indent and takes the next number of the enclosing run.
- Both carry the item's owned block along and renumber *both* the source and destination runs in a single `TextEdit`, so one keypress is one undo checkpoint.

**Wiring** in `_prompt_text_area_key_handling.py`: the ordered planner runs ahead of `plan_prompt_bullet_shift`, with queued snippet tabstops still winning. Also fixed the dot-insert capture remap — it assumed plans insert at a point, so a range-replacing plan collapsed the capture to the end of the replacement; it now follows the cursor by the same delta.

**Justfile**: removed the `sase-gi.2(plan_ordered_list_edit)` and `sase-gi.4(find_ordered_run)` symvision epic-symbol entries, which this change made unnecessary (symvision errors on stale whitelist entries).

## Verification

- 32 new tests in `tests/ace/tui/widgets/test_prompt_ordered_shift_editing.py` pass — marker/delimiter variants, owned-block movement, formatter fixed-point, single-undo, snippet-tabstop precedence, and no-op cases.
- `just check`: all lint gates green (fmt, keep-sorted, ruff, mypy, pyscripts, changelog, symvision).
- Scoped test lane: 26226 passed, 1 failure — `test_stall_watchdog.py::test_watchdog_keeps_hitch_and_stall_state_machines_independent`, a load-sensitive timing test unrelated to this change that passes in isolation. Recorded as a `PROPOSED FOLLOW-UP:` note on the bead.

Bead `sase-gi.4` is closed with a verification note; the parent epic is untouched.

One thing to flag: the commit reported a pre-existing quarantined agent-hood publication request (`sase agent sync --retry-quarantined`), so the agent link on this commit may not resolve until that outbox is cleared. I left it alone since it predates this work.
