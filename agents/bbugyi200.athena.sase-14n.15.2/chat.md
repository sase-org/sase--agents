# Chat History - ace-run (sase-14n.15.2)

- **TIMESTAMP:** 2026-09-21 19:18:37 EDT
- **MODEL:** muse/muse-spark-1.3-contributor
- **AGENT:** sase-14n.15.2

## Prompt

#gh:gh_sase-org__sase
%id(2, clan=sase-14n.15, bead=sase-14n.15.2)
%model:@medium
%auto
%w:sase-14n.15.1
%w(bead=sase-14n.15.1)
Can you complete the work for bead sase-14n.15.2? The bead is already reserved for you and assigned to your agent
name: it was set to status=in_progress before you started reading this, either by the `sase bead work` launch
checkpoint or by the runtime promoting an ad-hoc wait-time claim. Do not set the status by hand. Read its
description and design file with `sase bead read sase-14n.15.2 -r "Need the phase scope and design file"`, do the work, and close only this bead with
`sase bead close sase-14n.15.2 --note "<what you verified>"`. Before closing, run
`sase bead epic-symbols sase-14n.15.2`. If this phase still has `--epic-symbol` entries, resolve each symbol or
re-key the Justfile line to a still-open bead (the parent epic or a later phase). `sase bead close` refuses while
leftovers remain; they go stale the instant this phase closes and turn unrelated agents' `just check` red. Closing
an assigned phase bead is unaffected by the parent-close descendant guard. Do NOT close the parent epic or any ancestor plan bead. Any instruction in a phase
description or child plan to close an ancestor is preparation and evidence for that ancestor's land agent, not
authorization for a phase worker. Do not create beads yourself: record discovered follow-up work as a
`PROPOSED FOLLOW-UP:` entry via
`sase bead note sase-14n.15.2 'PROPOSED FOLLOW-UP: <one-line summary — detail>'`; the epic's land agent triages
these into task beads.

## Response

Bead sase-14n.15.2 is done and closed.

What shipped: `T` toggles the notification modal between the unread inbox and a dismissed-rows view (title shows `Notifications (dismissed)`), reloading through the provider with `include_dismissed=True`; `u` restores the highlighted or marked rows. Both keys were added to all three footer fragment lists at the tag-tabs rung, so every variant renders them at 120 columns (84/108 cells, `q`/`+1` intact). `u` on a dismissed live CustomGate restores it unread, and Enter then reaches the gate handler without marking it read.

Key decisions recorded on the bead: `T` has no twin in use (`t` is free, unlike `d`/`D` or `x`/`X`); rows that are both read and dismissed stay out of both views since the inbox is unread-scoped and Rust undismiss clears only the dismissed flag — pending bundles remain reachable via `sase gate list`/`show`.

Verification: 8/8 new production-path tests pass (seed dismissed live gate → real app flow → `T` → `u` → store undismissed → `T` back → listed → Enter dispatches); `sase tool run check` lints all green with 44614 passed. Its 18 failures were each reproduced on clean master (15 pre-existing, including the question-footer MagicMock bug and shard-table drift I filed as follow-ups) or pass in isolation (3 parallel-load flakes). No screenshot goldens moved; no `default_config.yml` change (modal keys aren't configurable there).

Declaration accepted for commit (bead_action keep, since bead status unreadable). No other work done.
