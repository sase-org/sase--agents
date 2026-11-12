# Chat History - ace-run (toobig-9t.healer_relaunch.0)

- **TIMESTAMP:** 2026-11-12 11:56:17 EST
- **MODEL:** muse/muse-spark-1.3-contributor
- **AGENT:** toobig-9t.healer_relaunch.0

## Prompt

%id:toobig-9t.healer_relaunch.0
%clan(toobig-9t, tribe=chop, summary=[[[bold #D75FFF]◆ TOOBIG SPLIT · 2 FILES[/bold #D75FFF]
[bold #87D7FF]MISSION[/bold #87D7FF]
[dim #D7D7FF]Decompose oversized Python modules into focused, reviewable units[/dim #D7D7FF]
[dim #D7D7FF]without changing behavior.[/dim #D7D7FF]

[bold #87D7FF]TARGETS[/bold #87D7FF]
[#87D7FF]• 791  src/sase/agent/auto_restart/healer_relaunch.py[/#87D7FF]
[#87D7FF]• 764  tests/test_bead/test_db_migrations.py[/#87D7FF]

[dim #A8A8A8]2 scan roots · limits 1,000 / 850 / 700 lines · sequential queue[/dim #A8A8A8]]])
%model:@medium
%auto
%queue(capacity=5)
#gh:gh_sase-org__sase Can you help me split the `src/sase/agent/auto_restart/healer_relaunch.py` file into multiple files? Use your best
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

Split complete. `healer_relaunch.py` (791 lines) is now a 16-line facade re-exporting `relaunch_claimed`; implementation moved to four modules, all ≤500 lines:

- [healer_relaunch_claim.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/src/sase/agent/auto_restart/healer_relaunch_claim.py) (408 lines): `relaunch_claimed` plus private plan/execute/digest/wipe helpers used only there.
- [_healer_relaunch_launcher.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/src/sase/agent/auto_restart/_healer_relaunch_launcher.py) (207 lines): public `is_launcher_row`, `launcher_intended_names`, `launcher_has_force_reuse`, `launcher_project_cwd`, `prepare_launcher_reservation`, `launch_launcher_prompt`; private `_launcher_explicit_directives` and `_launcher_owned_planned_names` stay in-file.
- [_healer_relaunch_provenance.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/src/sase/agent/auto_restart/_healer_relaunch_provenance.py) (138 lines): public `attach_provenance`, `provenance_env`; private `_identity_revision` stays in-file.
- [_healer_relaunch_evidence.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/src/sase/agent/auto_restart/_healer_relaunch_evidence.py) (109 lines): public `write_evidence`; private `_runner_log_tail` stays in-file.

No `_`-prefixed name is imported across the new modules; shared helpers are public names inside already-private modules. The facade exposes only `relaunch_claimed`, so `healer_flow.py` needed no change.

Retargeted tests: `healer_relaunch_claim.launcher_project_cwd` in the launcher-reservation and healer-flow tests, `attach_provenance` from `_healer_relaunch_provenance` in the guards test, and marker mutation/path-passing audits to the new `write_evidence` / `_runner_log_tail` / `relaunch_claimed` locations.

Verification: `just _lint-symvision`, `just _lint-mypy`, and `just _lint-toobig` all pass; `sase tool run check` passes (verdict pass). The 40 healer/audit tests pass.
