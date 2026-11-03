%id:toobig-95.stop.0
%clan(toobig-95, tribe=chop, summary=[[[bold #D75FFF]◆ TOOBIG SPLIT · 6 FILES[/bold #D75FFF]
[bold #87D7FF]MISSION[/bold #87D7FF]
[dim #D7D7FF]Decompose oversized Python modules into focused, reviewable units[/dim #D7D7FF]
[dim #D7D7FF]without changing behavior.[/dim #D7D7FF]

[bold #87D7FF]TARGETS[/bold #87D7FF]
[bold #FF5F87]▲ 1,033  src/sase/agent/hijack/stop.py[/bold #FF5F87]
[#87D7FF]•   806  src/sase/instructions/readout.py[/#87D7FF]
[#87D7FF]•   775  tests/instructions/test_readout.py[/#87D7FF]
[#87D7FF]•   744  tests/turns/test_workspace_retention.py[/#87D7FF]
[#87D7FF]•   732  tests/main/test_monitor_handler_start_launch.py[/#87D7FF]
[#87D7FF]•   706  src/sase/axe/run_agent_runner_lifecycle.py[/#87D7FF]

[dim #A8A8A8]2 scan roots · limits 1,000 / 850 / 700 lines · sequential queue[/dim #A8A8A8]]])
%model:@medium
%auto
%queue(capacity=5)
#gh:gh_sase-org__sase Can you help me split the `src/sase/agent/hijack/stop.py` file into multiple files? Use your best
judgment, but keep every resulting file at 500 lines of code or fewer.

Preserve behavior and the original module's public import path. A facade may re-export
public names, but never `_private` names. Never import a `_`-prefixed name across the
new modules. If more than one new module needs a helper, give it a public name inside an
already-private (`_`-prefixed) module; move a helper used by only one other module into
that module instead. Keep test monkeypatch targets working, or retarget the tests.

Before finishing, run `just _lint-symvision`, `just _lint-mypy`, and `just _lint-toobig`
individually. Fix every issue in a file the split touched, even if an earlier
`just check` stage is already red. Then run `sase tool run check`.