# Chat History - ace-run (toobig-9i.stale_running_cleanup.0)

- **TIMESTAMP:** 2026-11-06 11:52:57 EST
- **MODEL:** muse/muse-spark-1.3-contributor
- **AGENT:** toobig-9i.stale_running_cleanup.0

## Prompt

%id:toobig-9i.stale_running_cleanup.0
%clan(toobig-9i, tribe=chop, summary=[[[bold #D75FFF]◆ TOOBIG SPLIT · 5 FILES[/bold #D75FFF]
[bold #87D7FF]MISSION[/bold #87D7FF]
[dim #D7D7FF]Decompose oversized Python modules into focused, reviewable units[/dim #D7D7FF]
[dim #D7D7FF]without changing behavior.[/dim #D7D7FF]

[bold #87D7FF]TARGETS[/bold #87D7FF]
[bold #FFAF5F]◆ 947  src/sase/ace/scheduler/stale_running_cleanup.py[/bold #FFAF5F]
[#87D7FF]• 806  tests/monitor/test_monitor_retention_lifecycle.py[/#87D7FF]
[#87D7FF]• 754  tests/tool/test_detach.py[/#87D7FF]
[#87D7FF]• 706  tests/test_run_agent_runner_notifications.py[/#87D7FF]
[#87D7FF]• 705  tests/core/test_agent_publication_recovery.py[/#87D7FF]

[dim #A8A8A8]2 scan roots · limits 1,000 / 850 / 700 lines · sequential queue[/dim #A8A8A8]]])
%model:@medium
%auto
%queue(capacity=5)
#gh:gh_sase-org__sase Can you help me split the `src/sase/ace/scheduler/stale_running_cleanup.py` file into multiple files? Use your best
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

Split done. The 947-line module is now four files, each under 500 lines.

New layout in `src/sase/ace/scheduler/`:

- [stale_running_cleanup.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/src/sase/ace/scheduler/stale_running_cleanup.py) (5 lines): facade. Re-exports only `cleanup_stale_running_entries`.
- [stale_running_sweep.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/src/sase/ace/scheduler/stale_running_sweep.py) (456 lines): sweep, hijack custody, held-claim/TTL, monitor/gate checks, project-file scan.
- [stale_running_leak.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/src/sase/ace/scheduler/stale_running_leak.py) (407 lines): leaked-monitor repair, stray-sheet publishing, SDD helpers. Exports public `repair_leaked_monitor_claim`.
- [_stale_running_shared.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/src/sase/ace/scheduler/_stale_running_shared.py) (116 lines): shared custody helpers with public names (`staged_origin_retains_claim`, `pending_retention_retains_claim`, `settle_stale_retention_record`, `clear_stale_occupant_record`).

No `_`-prefixed name is imported across the new modules. Singly-used helpers stayed file-local.

Tests retargeted to the new lookup locations (7 files). Public imports still use the facade path.

Verification observed:

- `just _lint-symvision`: pass.
- `just _lint-mypy`: pass, no issues in 6409 files.
- `just _lint-toobig`: pass.
- Fixed one ruff format nit in the shared module.
- Targeted pytest: 41 + 11 + 20 + 1 passed across stale-cleanup, held, hijack, monitor, staged-recovery, gate-origin, and monitor-start suites.
- `sase tool run check` (run `a725610d07ba7edce09e75b7febbe05e`): TRIAGE VERDICT pass, all stages green including scoped tests.
