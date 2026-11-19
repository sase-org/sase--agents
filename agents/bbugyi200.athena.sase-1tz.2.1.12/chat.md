# Chat History - ace-run (sase-1tz.2.1.12)

- **TIMESTAMP:** 2026-11-19 12:49:03 EST
- **MODEL:** muse/muse-spark-1.3-contributor
- **AGENT:** sase-1tz.2.1.12

## Prompt

#gh:gh_sase-org__sase
%id(12, clan=sase-1tz.2.1, bead=sase-1tz.2.1.12)
%model:@small
%auto
Can you complete the work for bead sase-1tz.2.1.12? The bead is already reserved for you and assigned to your agent
name: it was set to status=in_progress before you started reading this, either by the `sase bead work` launch
checkpoint or by the runtime promoting an ad-hoc wait-time claim. Do not set the status by hand. If the host
notice says the bead was already closed when this run started, the run is attached to the closed bead. Only the
host notice tells you that; if `sase bead read` shows a closed bead and no host notice said so, you copied the
wrong ID — re-copy `sase-1tz.2.1.12` from this prompt before concluding anything. Check
whether the earlier work landed before redoing anything. Only when the host notice said the bead was already
closed and the work is genuinely unfinished, run `sase bead open sase-1tz.2.1.12` first. Otherwise never run
`sase bead open` on your own bead: it demotes an `in_progress` bead back to `open`. To view a bead, run
`sase bead read sase-1tz.2.1.12 -r "<why you need this bead>"`. Read its
description and design file with `sase bead read sase-1tz.2.1.12 -r "Need the phase scope and design file"`, do the work, and close only this bead with
`sase bead close sase-1tz.2.1.12 --note "<what you verified>"`. Honor the epic's DECISIONS shown by
`sase bead read`; they are final, and only memory notes they authorize may be edited. Before closing, run
`sase bead epic-symbols sase-1tz.2.1.12`. If this phase still has `--epic-symbol` entries, resolve each symbol or
re-key the Justfile line to a still-open bead (the parent epic or a later phase). `sase bead close` refuses while
leftovers remain; they go stale the instant this phase closes and turn unrelated agents' `just check` red. Closing
an assigned phase bead is unaffected by the parent-close descendant guard. Do NOT close the parent epic or any ancestor plan bead. Any instruction in a phase
description or child plan to close an ancestor is preparation and evidence for that ancestor's land agent, not
authorization for a phase worker. Do not create beads yourself: record discovered follow-up work as a
`PROPOSED FOLLOW-UP:` entry via
`sase bead note sase-1tz.2.1.12 'PROPOSED FOLLOW-UP: <one-line summary — detail>'`; the epic's land agent triages
these into task beads. A check failure that reproduces identically on the clean base tree does not keep this bead
open: record it as a `PROPOSED FOLLOW-UP:` entry (citing any task bead that already tracks it) and close anyway;
nothing relaunches a phase left open. Before planning, check the phase's notes: if an earlier agent already
worked this phase and left it open with recorded remaining work, that remainder did not fit one agent, so author
a child epic whose phases each fit one coding agent and whose land agent closes this phase instead of another
single-agent tale unless one coder can clearly finish everything left.

## Response

Bead `sase-1tz.2.1.12` (ui_cpu_caches) is done and the final declaration is accepted.

What landed:

- **Memoized built-in query profiles** — [`pane_registry.py`](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_29/src/sase/ace/query_profile/pane_registry.py) now caches compiled profiles keyed by pane id (builders are static, profiles are frozen dataclasses, so sharing is safe); exported `clear_compiled_builtin_pane_cache` through the package `__init__` for tests. Profile lookup went from ~177 µs/call to ~0.1–0.2 µs.
- **Facade wire cache** — [`agent_runtime_facade.py`](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_29/src/sase/core/agent_runtime_facade.py) caches `asdict()` payloads keyed by wire object identity (with an `is`-check plus strong refs against id reuse; verified the Rust binding doesn't mutate inputs). Steady-tick cost for a 12-member clan dropped from ~115 µs to ~67–73 µs; the Rust aggregation itself still runs per tick for the now-dependent suffix. No sase-core changes, so no pin move.
- **`agent_share_fingerprint` confirmed dead** — zero callers in `src/`, `tests/`, `docs/`; the audit's stall samples (Nov 16–17, `_agent_graph.py:288,306`) predate removal commit `d152f200b2` (Nov 18).
- **Tests** — new `tests/test_query_profile_pane_registry.py` (6 tests: memoization identity, all panes, fresh-compile parity, unknown-pane passthrough, clear/rebuild, immutability) and `tests/test_core_agent_runtime_cache.py` (3 tests: payload reuse, changed-member reserialization with uncached parity, bounded eviction). Existing `test_runtime_tick_caches` and query-profile suites pass.
- **Verification** — `sase tool run check`: all lint gates pass including symvision (which caught and I fixed a test-only helper); scoped lane 62,125 passed with 3 unrelated load flakes (git lock-retry, artifact volume-budget, pager trail) that import none of the touched modules and pass in isolation.
