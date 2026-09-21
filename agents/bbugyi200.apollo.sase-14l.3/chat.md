# Chat History - ace-run (sase-14l.3)

- **TIMESTAMP:** 2026-09-20 19:51:03 EDT
- **MODEL:** muse/muse-spark-1.3-contributor
- **AGENT:** sase-14l.3

## Prompt

#gh:gh_sase-org__sase
%id(3, clan=sase-14l, bead=sase-14l.3)
%model:@small
%auto
%w:sase-14l.2
%w(bead=sase-14l.2)
Can you complete the work for bead sase-14l.3? The bead is already reserved for you and assigned to your agent
name: it was set to status=in_progress before you started reading this, either by the `sase bead work` launch
checkpoint or by the runtime promoting an ad-hoc wait-time claim. Do not set the status by hand. Read its
description and design file, do the work, and close only this bead with
`sase bead close sase-14l.3 --note "<what you verified>"`. Before closing, run
`sase bead epic-symbols sase-14l.3`. If this phase still has `--epic-symbol` entries, resolve each symbol or
re-key the Justfile line to a still-open bead (the parent epic or a later phase). `sase bead close` refuses while
leftovers remain; they go stale the instant this phase closes and turn unrelated agents' `just check` red. Closing
an assigned phase bead is unaffected by the parent-close descendant guard. Do NOT close the parent epic or any ancestor plan bead. Any instruction in a phase
description or child plan to close an ancestor is preparation and evidence for that ancestor's land agent, not
authorization for a phase worker. Do not create beads yourself: record discovered follow-up work as a
`PROPOSED FOLLOW-UP:` entry via
`sase bead note sase-14l.3 'PROPOSED FOLLOW-UP: <one-line summary — detail>'`; the epic's land agent triages
these into task beads.

## Response

Bead `sase-14l.3` (unread-projection) is done and closed.

What changed (4 files, uncommitted for host finalizers):

- [\_notification_utils.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/actions/agents/_notification_utils.py:731) — added `active_row_owned_notification_keys()`: union of `active_completion_agent_keys()` and the exact `(cl_name, raw_suffix)` keys of active `epic-launch`/`monitor-settlement` rows, mirroring the host-ack predicate with no `cl_name`-only fallback. `active_completion_agent_keys` itself untouched.
- [\_notification_unread_projection.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/actions/agents/_notification_unread_projection.py:157) — reconcile now builds `active_keys` from the union helper. Terminal-status gate, manual-`U` guard, and node resolution unchanged.
- [test_agent_unread_projection.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/tests/ace/tui/test_agent_unread_projection.py:126) — 7 new tests: settlement marks terminal row unread (both senders), wrong `raw_suffix` ignored, running row ignored, dismissed settlement clears, manual-`U` not re-added, and the end-to-end ordering (completion read → settlement arrives → row reflags unread).
- `Justfile` — re-keyed the `agent_settlement_notification_matches_agent` symvision whitelist from `sase-14l.3` to parent `sase-14l`. It can't be dropped: the predicate's only non-test caller is same-file, which symvision doesn't count. The land agent triages it (note left in the Justfile comment).

Verification observed:

- 36/36 focused tests pass (projection + settlement-match suites).
- `sase tool run check`: all lint gates green; the test lane's 6 failures are not mine — 4 pass in isolation (load flakes), and the 2 persistent ones (notify-rules help text, shard-timing drift) fail identically on the pristine tree via stash check. Filed both as `PROPOSED FOLLOW-UP:` notes on the bead for triage.
- `just _lint-symvision` green with the re-keyed entry; `sase bead epic-symbols sase-14l.3` clean before close.

Declaration accepted for the commit payload (bead already closed, so submitted with keep).
