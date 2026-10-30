%id:toobig-8v.migration.0
%clan(toobig-8v, tribe=chop, summary=[[[bold #D75FFF]◆ TOOBIG SPLIT · 8 FILES[/bold #D75FFF]
[bold #87D7FF]MISSION[/bold #87D7FF]
[dim #D7D7FF]Decompose oversized Python modules into focused, reviewable units[/dim #D7D7FF]
[dim #D7D7FF]without changing behavior.[/dim #D7D7FF]

[bold #87D7FF]TARGETS[/bold #87D7FF]
[#87D7FF]• 824  src/sase/axe/run_agent_exec_staged.py[/#87D7FF]
[#87D7FF]• 774  src/sase/finalizers/declaration.py[/#87D7FF]
[#87D7FF]• 773  src/sase/main/workspace_handler_maintenance.py[/#87D7FF]
[#87D7FF]• 763  src/sase/agents_sync/prompt_archive/migration.py[/#87D7FF]
[#87D7FF]• 756  src/sase/gate_turn/reclaim.py[/#87D7FF]
[#87D7FF]• 739  src/sase/core/tool_run.py[/#87D7FF]
[#87D7FF]• 707  src/sase/ace/tui/widgets/_agent_list_render_rail.py[/#87D7FF]
[#87D7FF]• 707  tests/ace/tui/util/test_gc_policy.py[/#87D7FF]

[dim #A8A8A8]2 scan roots · limits 1,000 / 850 / 700 lines · sequential queue[/dim #A8A8A8]]])
%model:@medium
%auto
%queue(capacity=5)
#gh:gh_sase-org__sase Can you help me split the `src/sase/agents_sync/prompt_archive/migration.py` file into multiple files? Use your best
judgment, but keep every resulting file at 500 lines of code or fewer.

Preserve behavior and the original module's public import path. A facade may re-export
public names, but never `_private` names. Never import a `_`-prefixed name across the
new modules. If more than one new module needs a helper, give it a public name inside an
already-private (`_`-prefixed) module; move a helper used by only one other module into
that module instead. Keep test monkeypatch targets working, or retarget the tests.

Before finishing, run `just _lint-symvision`, `just _lint-mypy`, and `just _lint-toobig`
individually. Fix every issue in a file the split touched, even if an earlier
`just check` stage is already red. Then run `sase tool run check`.