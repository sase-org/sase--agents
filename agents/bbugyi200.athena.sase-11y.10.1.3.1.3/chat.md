# Chat History - ace-run (sase-11y.10.1.3.1.3)

- **TIMESTAMP:** 2026-09-20 22:28:08 EDT
- **MODEL:** muse/muse-spark-1.3-contributor
- **AGENT:** sase-11y.10.1.3.1.3

## Prompt

#gh:gh_sase-org__sase
%id(3, clan=sase-11y.10.1.3.1, bead=sase-11y.10.1.3.1.3)
%model:@medium
%auto
Can you complete the work for bead sase-11y.10.1.3.1.3? The bead is already reserved for you and assigned to your agent
name: it was set to status=in_progress before you started reading this, either by the `sase bead work` launch
checkpoint or by the runtime promoting an ad-hoc wait-time claim. Do not set the status by hand. Read its
description and design file, do the work, and close only this bead with
`sase bead close sase-11y.10.1.3.1.3 --note "<what you verified>"`. Before closing, run
`sase bead epic-symbols sase-11y.10.1.3.1.3`. If this phase still has `--epic-symbol` entries, resolve each symbol or
re-key the Justfile line to a still-open bead (the parent epic or a later phase). `sase bead close` refuses while
leftovers remain; they go stale the instant this phase closes and turn unrelated agents' `just check` red. Closing
an assigned phase bead is unaffected by the parent-close descendant guard. Do NOT close the parent epic or any ancestor plan bead. Any instruction in a phase
description or child plan to close an ancestor is preparation and evidence for that ancestor's land agent, not
authorization for a phase worker. Do not create beads yourself: record discovered follow-up work as a
`PROPOSED FOLLOW-UP:` entry via
`sase bead note sase-11y.10.1.3.1.3 'PROPOSED FOLLOW-UP: <one-line summary — detail>'`; the epic's land agent triages
these into task beads.

## Response

Bead sase-11y.10.1.3.1.3 (update-restart) is done and closed.

What changed:
- Seam: `restart_after_update` now restarts via `restart_service_proc("scheduler", actor="cli", reason=source)` through a default adapter. `ServiceProcActionError`/`ServiceConfigError` map to `status="failed"` with the exception text; success is `status="restarted"` carrying the outcome message. The `_call_restart_axe` introspection probe is deleted; the injected function is called directly with `reason=`.
- Types ([update_types.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_41/src/sase/main/update_types.py)): `AxeRunningFn`→`SchedulerRunningFn`, `RestartAxeFn`→`RestartSchedulerFn` (typed against the renamed `ServiceProcActionOutcome`, now public and exported). `RestartInfo` dropped `pid`/`attempts`/`verified`; schema version bumped 3→4. The old `RestartAxeFn` name is kept as a legacy alias only because `sase axe restart` still uses it — the axe-alias phase spec expects that import to exist when it deletes it.
- Callers rewired with scheduler wording: update handler (live + mode-switch), `sase flag`, plugin install/uninstall/update, shared plugin-restart helper, and the PluginsRequired gate (including its docstring). JSON and journal restart payloads dropped the removed fields.
- Tests: all fakes updated to the `reason=` signature returning service-proc outcomes, assertions updated, plus a new case proving a successful `sase update` requests a `scheduler` service-proc restart and never calls `restart_axe_daemon_result`.

Verification: `sase tool run check` is green for fmt, ruff, and mypy; every affected test file passes (in isolated runs); `epic-symbols` reports no entries for this phase. Three failures in the wider run are pre-existing on clean HEAD, confirmed by stash-and-rerun: the stale `sase-14l` epic-symbol entry blocking symvision, two completion-snapshot drifts, and an order-dependent `sase_core_rs` import flake. No follow-up beads were created and no ancestor beads touched.

Declaration accepted for bead sase-11y.10.1.3.1.3 (already closed); commit authorized for the update-restart work.
