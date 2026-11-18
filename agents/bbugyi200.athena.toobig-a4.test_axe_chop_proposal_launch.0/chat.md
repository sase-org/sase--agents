# Chat History - ace-run (toobig-a4.test_axe_chop_proposal_launch.0)

- **TIMESTAMP:** 2026-11-18 13:28:14 EST
- **MODEL:** muse/muse-spark-1.3-contributor
- **AGENT:** toobig-a4.test_axe_chop_proposal_launch.0

## Prompt

%id:toobig-a4.test_axe_chop_proposal_launch.0
%clan(toobig-a4, tribe=chop, summary=[[[bold #D75FFF]◆ TOOBIG SPLIT · 1 FILE[/bold #D75FFF]
[bold #87D7FF]MISSION[/bold #87D7FF]
[dim #D7D7FF]Decompose oversized Python modules into focused, reviewable units[/dim #D7D7FF]
[dim #D7D7FF]without changing behavior.[/dim #D7D7FF]

[bold #87D7FF]TARGETS[/bold #87D7FF]
[#87D7FF]• 727  tests/test_axe_chop_proposal_launch.py[/#87D7FF]

[dim #A8A8A8]2 scan roots · limits 1,000 / 850 / 700 lines · sequential queue[/dim #A8A8A8]]])
%model:@medium
%auto
%queue(capacity=5)
#gh:gh_sase-org__sase Can you help me split the `tests/test_axe_chop_proposal_launch.py` file into multiple files? Use your best
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

Split [tests/test_axe_chop_proposal_launch.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_27/tests/test_axe_chop_proposal_launch.py) (727 lines) into a facade plus three focused modules, each under 500 lines:

- [tests/test_axe_chop_proposal_launch_ordinary.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_27/tests/test_axe_chop_proposal_launch_ordinary.py): 192 lines, ordinary first-run ownership and clan-kill tests.
- [tests/test_axe_chop_proposal_launch_typed_admission.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_27/tests/test_axe_chop_proposal_launch_typed_admission.py): 419 lines, durable admission, pause/reopen, and interrupted-write recovery.
- [tests/test_axe_chop_proposal_launch_typed_dispatch.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_27/tests/test_axe_chop_proposal_launch_typed_dispatch.py): 175 lines, typed dispatch fails-closed, hold key, and all-skipped runner.
- Facade re-exports all 8 public `test_` names with `__test__ = False` and `__all__`, so `tests.test_axe_chop_proposal_launch` still imports but pytest collects only the new modules. No `_`-prefixed names are imported across new modules; shared helpers stay as public names in [tests/_axe_chop_proposal_launch_helpers.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_27/tests/_axe_chop_proposal_launch_helpers.py). Monkeypatch string targets were unchanged.

Verification observed:

- `just _lint-symvision`: pass.
- `just _lint-mypy`: pass, no issues in 6614 files.
- `just _lint-toobig`: pass, all files within info limit.
- New-module pytest: 8 passed.
- `sase tool run check`: succeeded.
