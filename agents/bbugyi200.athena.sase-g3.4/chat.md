# Chat History - ace-run (sase-g3.4)

- **TIMESTAMP:** 2026-08-06 09:42:55 EDT
- **MODEL:** claude/opus
- **AGENT:** sase-g3.4

## Prompt

#gh:gh_sase-org__sase
%id(4, clan=sase-g3, bead=sase-g3.4)
%model:@medium_phase_worker
%auto
Can you complete the work for bead sase-g3.4? The bead is already reserved for you and assigned to your agent
name: it was set to status=in_progress before you started reading this, either by the `sase bead work` launch
checkpoint or by the runtime promoting an ad-hoc wait-time claim. Do not set the status by hand. Read its
description and design file, do the work, and close the bead with
`sase bead close sase-g3.4 --note "<what you verified>"`. Closing an assigned phase bead is unaffected by the
parent-close descendant guard. Do NOT close the parent epic. Do not create beads yourself: record discovered
follow-up work as a `PROPOSED FOLLOW-UP:` entry via
`sase bead note sase-g3.4 'PROPOSED FOLLOW-UP: <one-line summary — detail>'`; the epic's land agent triages
these into task beads.

## Response

I'll start by reading the bead.

Now let me add the shared prune helper to the contexts library.

Now wire it into the Justfile.

Now let me test the tool's behavior quickly with a real small contexts run.

Now the tests. Let me look at how the contexts tests build fixtures.

Now the docs.

Now a test for that, following the existing run_pytest command tests.

Now re-record the full baseline with the pinned core and verify parity with CI.

The background run will notify me when it finishes. Meanwhile, a quick status recap of what's done so far:

- `tools/install_coverage_contexts` (new local baseline producer) + `just test-contexts` wiring
- Shared `prune_baselines` in `tests/_test_selection_contexts.py`, reused by both producers
- `COVERAGE_CORE=ctrace` pinned for `cov-contexts` — measured fix for lossy per-test attribution on Python 3.14
- Tests: 12 tool tests, 3 coverage-core tests, 1 Justfile-wiring test; `just lint` clean

Still queued behind other agents' suite-gate leases. Waiting for it.

Mechanism confirmed already: a separate checkout resolved the locally installed baseline and fired `context-selection`. Waiting on the `ctrace` re-run to confirm ground-truth parity with CI.

I'll wait for the monitor rather than poll.

The `ctrace` re-run is queued behind other agents' suite-gate leases. I'll continue when it completes — the monitor will wake me.

Waiting on the suite gate. I'll resume when the monitor reports the run finished.

The instrumented re-run is queued behind other agents holding suite-gate worker tokens. I'll pick this back up when it lands.

I have the monitor armed; I'll wait for its event rather than polling.

Still gated. Waiting on the monitor event.

I'll stop polling and wait for the monitor to report completion.

The instrumented re-run is still waiting for suite-gate worker tokens (another agent holds 28). The monitor I armed will notify me the moment it finishes, and I'll complete the parity check and the cross-checkout verification then.

Waiting on the gated run; the monitor will wake me when it exits.

I'm waiting on the monitor event for the gated instrumented run — no further action until it fires.

The `just test-contexts` re-run (with the `ctrace` fix) is still queued on the suite gate. Everything else for the phase is in place; I'll finish the two remaining verifications — CI-parity of the locally recorded database, and the cross-checkout baseline resolution — as soon as that run completes.

Still gated. I'll wait for the monitor notification.

Waiting on the monitor.

Bead closed and published cleanly (no unpublished diagnostic). Now committing.

Clean tree, in sync with `origin/master`. Bead `sase-g3.4` closed and published.

## What shipped

**`tools/install_coverage_contexts`** — the local baseline producer. Before this, `tools/fetch_coverage_contexts` was the only route to a selection baseline, so ground truth reached a host solely via the CI artifact (master pushes, 14-day retention). A host that never fetched, or fetched too long ago, ran the diff-scoped lane on the static import closure alone — while `just test-contexts` was recording exactly the database that would have answered the question and then throwing it away. The tool files a recorded `.coverage` under HEAD in the host-local cache; `just test-contexts` calls it on success via `--if-enabled` (opt out with `SASE_TEST_SELECTION_INSTALL_CONTEXTS=0`, and a rejected database warns rather than failing the recipe).

Two guards, because a baseline that resolves but contributes nothing is worse than none — it silences `context-baseline-missing` while adding no tests. A dirty `src/` tree is refused (the database is keyed by its commit's line numbers); a run covering under half the suite's test files is refused (baselines rank by mtime, so a partial run would displace a complete one). Both overridable.

**`COVERAGE_CORE=ctrace` pinned for the `cov-contexts` lane.** On Python 3.14 coverage defaults to `sysmon`, which stops monitoring a code location once seen — so every test after the first to execute a line goes unattributed. At `6b0976bcb`, `tests/test_agent_lanes.py` recorded 6 contexts against `agent_lanes.py` under `sysmon` versus 32 under `ctrace`, the latter matching CI's Python 3.12 default.

**Shared `prune_baselines`** in `tests/_test_selection_contexts.py`, so one cache bound holds however a baseline arrived.

## Verification

`just lint` clean (ruff, mypy, symvision, toobig). 12 tool tests, 3 coverage-core tests, 1 Justfile-wiring test pass. Against a real `ctrace`-recorded database, the partial-run guard fired correctly and the dirty-`src` guard correctly ignored this branch's non-`src` changes.

`just check`'s scoped lane passed except two tests that fail only under full parallel load and pass in isolation — `test_stall_watchdog` and `test_cli_work_contention_regressions`; neither touches selection or coverage. Recorded as a `PROPOSED FOLLOW-UP:` on the bead for the epic's land agent.

**Left unverified:** a full-suite instrumented re-record under `ctrace` compared wholesale against the CI artifact. The suite gate was saturated by other agents throughout, and that run does not fit this turn. The per-file `sysmon`-vs-`ctrace` measurement above is the evidence the core pin rests on.
