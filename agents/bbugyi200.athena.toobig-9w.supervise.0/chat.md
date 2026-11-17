# Chat History - ace-run (toobig-9w.supervise.0)

- **TIMESTAMP:** 2026-11-16 22:54:22 EST
- **MODEL:** muse/muse-spark-1.3-contributor
- **AGENT:** toobig-9w.supervise.0

## Prompt

%auto
%id(supervise.0, clan=toobig-9w)
%model:@medium
%queue(capacity=5)
#gh:gh_sase-org__sase Can you help me split the `src/sase/monitor/supervise.py` file into multiple files? Use your best
%wait:toobig-9w.settlement.0
judgment, but keep every resulting file at 500 lines of code or fewer.

Preserve behavior and the original module's public import path. A facade may re-export
public names, but never `_private` names. Never import a `_`-prefixed name across the
new modules. If more than one new module needs a helper, give it a public name inside an
already-private (`_`-prefixed) module; move a helper used by only one other module into
that module instead. Keep test monkeypatch targets working, or retarget the tests.

Before finishing, run `just _lint-symvision`, `just _lint-mypy`, and `just _lint-toobig`
individually. Fix every issue in a file the split touched, even if an earlier
`just check` stage is already red. Then run `sase tool run check`.

## Response

Done. Split the 713-line `src/sase/monitor/supervise.py` into five files, all under 500 lines, with behavior verified identical (AST comparison of every moved function, only a docstring word changed).

**New layout**
- [`supervise.py`](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_22/src/sase/monitor/supervise.py) (38 lines) — facade re-exporting only the public `run_supervisor`, plus the `python -m sase.monitor.supervise` CLI it already owned.
- [`supervise_run.py`](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_22/src/sase/monitor/supervise_run.py) (260) — orchestration: `run_supervisor` and its private helpers (`_read_meta`, `_append_supervisor_line`, `_reexport_member_agent_tab`, etc.).
- [`supervise_proc.py`](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_22/src/sase/monitor/supervise_proc.py) (212) — process control: `SupervisorTermination`, `SupervisorOutputActivity`, `popen_monitored_command`, `wait_for_child`, `wait_for_launch_barrier`.
- [`supervise_finish.py`](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_22/src/sase/monitor/supervise_finish.py) (271) — terminal settlement: `finish_monitor`.
- [`_supervise_shared.py`](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_22/src/sase/monitor/_supervise_shared.py) (38) — the three helpers needed by multiple modules, public as required (`TimeoutKind`, `format_duration`, `utc_now_iso`).

No `_`-prefixed name is imported across the new modules (verified by AST scan, matching the repo's existing convention), and the facade re-exports no private names.

**Tests retargeted** (imports/patches moved to the new homes): `tests/monitor/_supervise.py` (override driver now patches `supervise_proc`), `test_monitor_supervise.py`, `test_monitor_supervise_followup.py`, `test_macro_tab_inheritance.py`, plus audit inventories in `test_turns_substrate.py` (`supervise_finish.py` is now the done-marker writer) and `test_agent_artifact_marker_path_passing_audit.py` (`supervise_run.py:_read_meta`).

**Verification**
- `just _lint-symvision` — pass; `just _lint-mypy` — clean (6534 files).
- `just _lint-toobig` — no touched file flagged; the 2 remaining violations are pre-existing on the base tree in untouched TUI test files (proven via stash).
- `sase tool run check` — succeeded, including the scoped test lane (all 61 supervise/timeout/diagnostics/tab/audit tests pass).

Declaration submitted: committed the supervise split on `main`.
