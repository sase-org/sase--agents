# Chat History - ace-run (toobig-9p.test_repo_init_plan.0)

- **TIMESTAMP:** 2026-11-08 15:34:26 EST
- **MODEL:** muse/muse-spark-1.3-contributor
- **AGENT:** toobig-9p.test_repo_init_plan.0

## Prompt

%id:toobig-9p.test_repo_init_plan.0
%clan(toobig-9p, tribe=chop, summary=[[[bold #D75FFF]◆ TOOBIG SPLIT · 1 FILE[/bold #D75FFF]
[bold #87D7FF]MISSION[/bold #87D7FF]
[dim #D7D7FF]Decompose oversized Python modules into focused, reviewable units[/dim #D7D7FF]
[dim #D7D7FF]without changing behavior.[/dim #D7D7FF]

[bold #87D7FF]TARGETS[/bold #87D7FF]
[#87D7FF]• 702  tests/main/test_repo_init_plan.py[/#87D7FF]

[dim #A8A8A8]2 scan roots · limits 1,000 / 850 / 700 lines · sequential queue[/dim #A8A8A8]]])
%model:@medium
%auto
%queue(capacity=5)
#gh:gh_sase-org__sase Can you help me split the `tests/main/test_repo_init_plan.py` file into multiple files? Use your best
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

Split done. All files under 500 lines and all gates pass.

- [test_repo_init_plan.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_13/tests/main/test_repo_init_plan.py): 47-line facade re-exporting 19 public tests.
- [_test_repo_init_plan_sidecars.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_13/tests/main/_test_repo_init_plan_sidecars.py): 366 lines, 7 sidecar planning tests.
- [_test_repo_init_plan_management.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_13/tests/main/_test_repo_init_plan_management.py): 334 lines, 12 management/run tests.
- [_test_repo_init_plan_helpers.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_13/tests/main/_test_repo_init_plan_helpers.py): 26 lines, public `make_plan_args` and `mark_plan_project`.

Retargeted private imports to public names: direct spec calls use `configured_sidecar_specs`, and the attachments test uses `plan_sidecar_actions` with a string monkeypatch target. `just _lint-symvision`, `just _lint-mypy`, `just _lint-toobig` pass. `sase tool run check` succeeded.
