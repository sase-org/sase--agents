# Chat History - ace-run (sase-za.4)

- **TIMESTAMP:** 2026-09-10 14:57:07 EDT
- **MODEL:** claude/sonnet
- **AGENT:** sase-za.4

## Prompt

#gh:gh_sase-org__sase
%id(4, clan=sase-za, bead=sase-za.4)
%model:@small
%auto
%w(bead=sase-za.2)
%w(bead=sase-za.3)
Can you complete the work for bead sase-za.4? The bead is already reserved for you and assigned to your agent
name: it was set to status=in_progress before you started reading this, either by the `sase bead work` launch
checkpoint or by the runtime promoting an ad-hoc wait-time claim. Do not set the status by hand. Read its
description and design file, do the work, and close only this bead with
`sase bead close sase-za.4 --note "<what you verified>"`. Before closing, run
`sase bead epic-symbols sase-za.4`. If this phase still has `--epic-symbol` entries, resolve each symbol or
re-key the Justfile line to a still-open bead (the parent epic or a later phase). `sase bead close` refuses while
leftovers remain; they go stale the instant this phase closes and turn unrelated agents' `just check` red. Closing
an assigned phase bead is unaffected by the parent-close descendant guard. Do NOT close the parent epic or any ancestor plan bead. Any instruction in a phase
description or child plan to close an ancestor is preparation and evidence for that ancestor's land agent, not
authorization for a phase worker. Do not create beads yourself: record discovered follow-up work as a
`PROPOSED FOLLOW-UP:` entry via
`sase bead note sase-za.4 'PROPOSED FOLLOW-UP: <one-line summary — detail>'`; the epic's land agent triages
these into task beads.

## Response

Good, no epic-symbol leftovers to worry about at close time. Now let me explore the relevant code to understand what exists already.

sase-core is indeed a linked repo and already cloned for this workspace. Let me open it to inspect the notification compaction implementation.

Good, Rust extension is available. Now let's implement the code changes, starting with the fixture generator.

Now let's update `bench_notification_store.py` to add the mostly-dismissed workload.

Now add the timing helper and wire it into `run_phase7_floor_payload`.

Now update the shape test to reflect the new workload.

Now let's add a smoke test for `synthetic_rows` dismissed_fraction and check the fixtures test file to see if there is an existing test file for the generator.

Good, unaffected. Now let's add the capacity-mode scan scenario to `bench_agent_scan.py`.

Now update the smoke test that asserts scenario presence, and wire the new scenario into the phase7b adaptor.

Now update the phase7b adaptor to expose the new candidate scenario.

Now let's run the benches to capture real baseline numbers for the two new anchors.

Now add the two anchor entries to the `anchors` array.

Now let's validate the JSON is well-formed and run the actual phase7 checker (smoke mode) to confirm the new anchors are picked up correctly end-to-end.

Now let's run `just check` per the agent-default verification requirement.

`just check` passed cleanly. Now let's verify the specific new/changed test files explicitly (including the slow-marked bench tests, which the scoped run may have skipped).

All 29 tests pass. Now let's do the live-host measurement part of the phase. Let's check current live process stats to capture "after" numbers.

Now let's record the live measurements and residual hotspots on the epic bead, and add the discovered follow-up on the phase bead.

Now let's re-check epic symbols one more time (should still be clean since I haven't touched the Justfile) and confirm `just check` is still green after all edits.

All clear. Now let's close the phase bead with a note summarizing what was verified.

Phase sase-za.4 is complete and closed.

Summary:
- Added a capacity-only scan perf floor (`scan_agent_artifacts.synthetic_6p_200pp.capacity_scan_facade`) and a mostly-dismissed notification snapshot-read perf floor (`notification_store.mostly_dismissed_900.notification_store_mostly_dismissed_load_snapshot`), both wired into `tests/perf/baselines/phase7_regression_floor.json` and passing under `just phase7-perf-check` and `just check`.
- Captured live before/after evidence on athena: ACE's `read_notification_snapshot` share of py-spy samples dropped from ~38% to ~11.7%; host load average dropped from 31-46 to 21-26.
- Discovered that capacity-only scanning is much less effective on this host's real artifact tree (~25% faster, ~33% less RSS) than on a clean synthetic one (~8-12x), because ~74% of ace-run dirs here predate reliable `done.json` writing — recorded this as a `PROPOSED FOLLOW-UP` on the phase bead and full measurement details as a note on the epic bead (`sase-za`) for the land agent to triage.
- Closed `sase-za.4` with a verification note; did not touch the parent epic or any ancestor bead.
