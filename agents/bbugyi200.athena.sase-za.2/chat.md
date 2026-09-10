# Chat History - ace-run (sase-za.2)

- **TIMESTAMP:** 2026-09-10 13:53:04 EDT
- **MODEL:** grok/grok-4.6
- **AGENT:** sase-za.2

## Prompt

#gh:gh_sase-org__sase
%id(2, clan=sase-za, bead=sase-za.2)
%model:@medium
%auto
%w:sase-za.1
%w(bead=sase-za.1)
Can you complete the work for bead sase-za.2? The bead is already reserved for you and assigned to your agent
name: it was set to status=in_progress before you started reading this, either by the `sase bead work` launch
checkpoint or by the runtime promoting an ad-hoc wait-time claim. Do not set the status by hand. Read its
description and design file, do the work, and close only this bead with
`sase bead close sase-za.2 --note "<what you verified>"`. Before closing, run
`sase bead epic-symbols sase-za.2`. If this phase still has `--epic-symbol` entries, resolve each symbol or
re-key the Justfile line to a still-open bead (the parent epic or a later phase). `sase bead close` refuses while
leftovers remain; they go stale the instant this phase closes and turn unrelated agents' `just check` red. Closing
an assigned phase bead is unaffected by the parent-close descendant guard. Do NOT close the parent epic or any ancestor plan bead. Any instruction in a phase
description or child plan to close an ancestor is preparation and evidence for that ancestor's land agent, not
authorization for a phase worker. Do not create beads yourself: record discovered follow-up work as a
`PROPOSED FOLLOW-UP:` entry via
`sase bead note sase-za.2 'PROPOSED FOLLOW-UP: <one-line summary — detail>'`; the epic's land agent triages
these into task beads.

## Response

I'll start by reading the bead, its design, and the SASE procedures so I can finish `sase-za.2` without touching the parent epic.

Next I’ll load the bead, its design, and the SASE memory that applies so the work stays inside this phase.

Phase 1 already added `capacity_only`; I’ll inspect the wait-slot tests and marker-mutation path so the poll diet can reuse that scan.

I’ll add the host-wide slot signal and shared scan cache first, then wire the wait loop onto them.

Path helpers are only used in-file, so I’ll make them private to keep Symvision from treating them as unused public API.

The workspace venv is missing the Rust extension, so I’ll install that and then rerun the tests.

`run_agent_wait_slots.py` is just over the 700-line warning, so I’ll pull the backoff step into the poll helper.

Symvision flagged those poll helpers as unused public API, so I’ll make them private and keep only `advance_runner_slot_poll` exported.

`just check` passed, including the escalated full suite. Next I’ll check epic-symbols and close only this phase bead.

Closed **sase-za.2** (`slot-poll-diet`). Parked runners no longer rescan full artifact history every 2s.

What landed:

- **Capacity-only scans.** `_scan_runner_slot_records()` now sets `capacity_only=True`, so admission walks live running/waiting dirs instead of done history.
- **One scan per poll window.** Under `runner_slots.lock`, waiters reuse a host-wide cache keyed by the slot-state token and poll-interval freshness. A claim still runs only against lock-validated state.
- **Jittered backoff + wake signal.** After parking, polling starts near 2s and backs off toward 10× that interval (20s by default). Marker mutations, deletes, and successful claims bump `~/.sase/runner_slots.token`, which resets backoff so a freed slot is seen on the fast cadence instead of at the cap. The fakey e2e still works because the cap scales with the patched poll interval.

Admission behavior is unchanged: queue weights, wait priorities, deference windows, serial-family claim reuse, fail-closed limit handling, and kill cleanup.

Verified with the new reuse/backoff tests, existing slot-admission tests, and `just check` (lint plus the full suite after core-identity escalation). No leftover `--epic-symbol` entries for this phase. Parent epic **sase-za** is still open.
