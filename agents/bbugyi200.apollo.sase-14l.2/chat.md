# Chat History - ace-run (sase-14l.2)

- **TIMESTAMP:** 2026-09-20 18:44:57 EDT
- **MODEL:** muse/muse-spark-1.3-contributor
- **AGENT:** sase-14l.2

## Prompt

#gh:gh_sase-org__sase
%id(2, clan=sase-14l, bead=sase-14l.2)
%model:@medium
%auto
%w:sase-14l.1
%w(bead=sase-14l.1)
Can you complete the work for bead sase-14l.2? The bead is already reserved for you and assigned to your agent
name: it was set to status=in_progress before you started reading this, either by the `sase bead work` launch
checkpoint or by the runtime promoting an ad-hoc wait-time claim. Do not set the status by hand. Read its
description and design file, do the work, and close only this bead with
`sase bead close sase-14l.2 --note "<what you verified>"`. Before closing, run
`sase bead epic-symbols sase-14l.2`. If this phase still has `--epic-symbol` entries, resolve each symbol or
re-key the Justfile line to a still-open bead (the parent epic or a later phase). `sase bead close` refuses while
leftovers remain; they go stale the instant this phase closes and turn unrelated agents' `just check` red. Closing
an assigned phase bead is unaffected by the parent-close descendant guard. Do NOT close the parent epic or any ancestor plan bead. Any instruction in a phase
description or child plan to close an ancestor is preparation and evidence for that ancestor's land agent, not
authorization for a phase worker. Do not create beads yourself: record discovered follow-up work as a
`PROPOSED FOLLOW-UP:` entry via
`sase bead note sase-14l.2 'PROPOSED FOLLOW-UP: <one-line summary — detail>'`; the epic's land agent triages
these into task beads.

## Response

Bead sase-14l.2 (host-ack) is done and closed.

What landed:
- Pin ratcheted to the core-match commit (`1655a12`) via `tools/ratchet_core_revision`; bindings check passes (678 bindings).
- New `agent_settlement_notification_matches_agent` (exact `(cl_name, raw_suffix)`, no `cl_name`-only fallback, mirrors the Rust matcher) plus the combined `agent_row_notification_matches_agent`, wired into `_remove_agent_completion_notifications_from_cache`. Polling/provider verified to hold no parallel copy — no change needed there.
- Pre-existing `agent_completion_notification_matches_agent` privatized (it lost its only cross-file consumer); the settlement predicate is whitelisted via `--epic-symbol sase-14l.3(...)` since the open unread-projection phase consumes it next.
- Tests: 1 selection, 2 toggle, and 9 focused predicate cases — 46/46 pass in the three touched modules; ruff and mypy clean.
- Docs updated (`notifications.md` dismissal contract + exact-match rationale; `rust_backend.md` boundary note). Row-identity assumption confirmed against live `epic-launch` rows and the agent list.
- `sase bead epic-symbols sase-14l.2` is clean; bead closed with the verification note; final declaration accepted.

One caveat, stated in the close note: `just check` still fails at the symvision gate on 26 violations in untouched `sdd`/`service`/`completion`/`models` files. A pristine-tree baseline run shows the identical 26, so they pre-date this phase and belong to sibling in-flight work — I left them alone.
