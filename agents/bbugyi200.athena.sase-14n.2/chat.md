# Chat History - ace-run (sase-14n.2)

- **TIMESTAMP:** 2026-09-20 17:32:45 EDT
- **MODEL:** muse/muse-spark-1.3-contributor
- **AGENT:** sase-14n.2

## Prompt

#gh:gh_sase-org__sase
%id(2, clan=sase-14n, bead=sase-14n.2)
%model:@medium
%auto
Can you complete the work for bead sase-14n.2? The bead is already reserved for you and assigned to your agent
name: it was set to status=in_progress before you started reading this, either by the `sase bead work` launch
checkpoint or by the runtime promoting an ad-hoc wait-time claim. Do not set the status by hand. Read its
description and design file, do the work, and close only this bead with
`sase bead close sase-14n.2 --note "<what you verified>"`. Before closing, run
`sase bead epic-symbols sase-14n.2`. If this phase still has `--epic-symbol` entries, resolve each symbol or
re-key the Justfile line to a still-open bead (the parent epic or a later phase). `sase bead close` refuses while
leftovers remain; they go stale the instant this phase closes and turn unrelated agents' `just check` red. Closing
an assigned phase bead is unaffected by the parent-close descendant guard. Do NOT close the parent epic or any ancestor plan bead. Any instruction in a phase
description or child plan to close an ancestor is preparation and evidence for that ancestor's land agent, not
authorization for a phase worker. Do not create beads yourself: record discovered follow-up work as a
`PROPOSED FOLLOW-UP:` entry via
`sase bead note sase-14n.2 'PROPOSED FOLLOW-UP: <one-line summary — detail>'`; the epic's land agent triages
these into task beads.

## Response

Done. Bead sase-14n.2 (and its owned task bead sase-13n) are closed; the final declaration was accepted.

Decision: the keep-the-larger-cache change was wrong, the test expectation was right. Commit `9231c9352` had swapped the complete-history latch gate in [src/sase/ace/tui/actions/agents/_loading_apply.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_34/src/sase/ace/tui/actions/agents/_loading_apply.py) from a latch-key mismatch to an applied-roster-key mismatch, so a changed-query incomplete load kept a stale latch whenever the applied key was unset or matching. I restored the latch-key gate; the merge/applied-key tracking from that commit is untouched, and the reconcile-arming check (which already used the latch-key comparison) agrees with it again.

Verification: `test_lazy_tier2_reconcile_apply.py` 11/11 (was 10/11 with `assert True is False` at line 210), `test_agents_tab_apply_boundary.py` 20/20 including the missing-key-keeps-latch and changed-query-clears cases, plus the view-picker file — 42 passed total, ruff clean. `sase tool run check` still aborts at the symvision gate, which fails identically on a clean tree and belongs to sibling phase sase-14n.1. `epic-symbols` was clean, and the parent epic was left open.
