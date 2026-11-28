# Chat History - ace-run (sase-1vn.3.1.2)

- **TIMESTAMP:** 2026-11-27 19:16:16 EST
- **MODEL:** muse/muse-spark-1.3-contributor
- **AGENT:** sase-1vn.3.1.2

## Prompt

%auto
#gh:gh_sase-org__sase
%id(2, clan=sase-1vn.3.1, bead=sase-1vn.3.1.2)
%model:@medium
%w(sase-1vn.3.1.1, for_epic=false)
%w(bead=sase-1vn.3.1.1)
Can you complete the work for bead sase-1vn.3.1.2? The bead is already reserved for you and assigned to your agent
name: it was set to status=in_progress before you started reading this, either by the `sase bead work` launch
checkpoint or by the runtime promoting an ad-hoc wait-time claim. Do not set the status by hand. If the host
notice says the bead was already closed when this run started, the run is attached to the closed bead. Only the
host notice tells you that; if `sase bead read` shows a closed bead and no host notice said so, you copied the
wrong ID — re-copy `sase-1vn.3.1.2` from this prompt before concluding anything. Check
whether the earlier work landed before redoing anything. Only when the host notice said the bead was already
closed and the work is genuinely unfinished, run `sase bead open sase-1vn.3.1.2` first. Otherwise never run
`sase bead open` on your own bead: it demotes an `in_progress` bead back to `open`. To view a bead, run
`sase bead read sase-1vn.3.1.2 -r "<why you need this bead>"`. Read its
description and design file with `sase bead read sase-1vn.3.1.2 -r "Need the phase scope and design file"`, do the work, and close only this bead with
`sase bead close sase-1vn.3.1.2 --note "<what you verified>"`. Honor the epic's DECISIONS shown by
`sase bead read`; they are final, and only memory notes they authorize may be edited. Before closing, run
`sase bead epic-symbols sase-1vn.3.1.2`. If this phase still has `--epic-symbol` entries, resolve each symbol or
re-key the Justfile line to a still-open bead (the parent epic or a later phase). `sase bead close` refuses while
leftovers remain; they go stale the instant this phase closes and turn unrelated agents' `just check` red. Closing
an assigned phase bead is unaffected by the parent-close descendant guard. Do NOT close the parent epic or any ancestor plan bead. Any instruction in a phase
description or child plan to close an ancestor is preparation and evidence for that ancestor's land agent, not
authorization for a phase worker. Do not create beads yourself: record discovered follow-up work as a
`PROPOSED FOLLOW-UP:` entry via
`sase bead note sase-1vn.3.1.2 'PROPOSED FOLLOW-UP: <one-line summary — detail>'`; the epic's land agent triages
these into task beads. A check failure that reproduces identically on the clean base tree does not keep this bead
open: record it as a `PROPOSED FOLLOW-UP:` entry (citing any task bead that already tracks it) and close anyway;
nothing relaunches a phase left open. Before planning, check the phase's notes: if an earlier agent already
worked this phase and left it open with recorded remaining work, that remainder did not fit one agent, so author
a child epic whose phases each fit one coding agent and whose land agent closes this phase instead of another
single-agent tale unless one coder can clearly finish everything left.

## Response

Phase bead `sase-1vn.3.1.2` is closed. The failed-origin ownership defect is fixed on the host side.

**What changed** (all in the sase checkout; sase-core policy from `sase-1vn.3.1.1` was already pushed at `34461b7f`):
- [New host module](src/sase/agent/_staged_handoff_inactive.py): builds the typed Rust inactive-stage request from persisted facts (stage/receipt validity, origin terminal evidence, proc/successor execution with unknown-vs-absent separation, recovery state), plus the identity-scoped `.sase_handoff_settled_inactive.json` marker.
- [Settlement applier](src/sase/axe/run_agent_exec_staged_inactive.py): idempotent, re-observes policy under the adoption lock, reuses held staged cleanup (reserved ToolRun settles as never-executed, staged join/prepared released, owner index cleared), never touches submitted procs. Runs nonblocking on the recovery automatic-hold path and the failed-dispatch boundary.
- Collector, admission, lane, ToolRun-owner, and runner-capacity paths honor inactive stages; adoption atomically invalidates the marker. Unstarted monitors are no longer `process_live` merely by being listed. Pin ratcheted to `34461b7f`.

**Verification (all observed, not inferred):** 25 new tests in [tests/test_staged_inactive_host.py](tests/test_staged_inactive_host.py) pass; neighbor suites (stranded, staged recovery, reconcile, monitor cleanup) pass; `sase tool run check` passed on run `07116f5e…` (full-suite escalation, triage `pass`/`exited_zero`); `epic-symbols` clean. One real find along the way: the first reconcile wiring blocked the sweep on a busy adoption lock (caught by `test_busy_adoption_lock_does_not_block_the_sweep`), fixed with nonblocking attempts plus a regression test.

The close note leaves the land agent a `sase-1sh` resolution recommendation (reconcile once, confirm `stranded/failed` + marker, then close it) and records `sase-1r4`/`sase-1si`/`sase-1sj` as untouched. No PROPOSED FOLLOW-UP items.

Declaration accepted for bead `sase-1vn.3.1.2` (commit, close).
