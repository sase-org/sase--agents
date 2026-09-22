%id:toobig-5v.agent_enter_targets.0
%clan(toobig-5v, tribe=chop, summary=[[[bold #D75FFF]◆ TOOBIG SPLIT · 12 FILES[/bold #D75FFF]
[bold #87D7FF]MISSION[/bold #87D7FF]
[dim #D7D7FF]Decompose oversized Python modules into focused, reviewable units[/dim #D7D7FF]
[dim #D7D7FF]without changing behavior.[/dim #D7D7FF]

[bold #87D7FF]TARGETS[/bold #87D7FF]
[bold #FF5F87]▲ 1,242  tests/service/test_service_host_scenarios.py[/bold #FF5F87]
[bold #FFAF5F]◆   869  tests/test_bead/test_workspace_sidecar_bead_eviction.py[/bold #FFAF5F]
[bold #FFAF5F]◆   859  src/sase/ace/tui/actions/agents/_agent_enter_targets.py[/bold #FFAF5F]
[#87D7FF]•   828  tests/ace/tui/test_agent_enter_targets.py[/#87D7FF]
[#87D7FF]•   799  src/sase/service/host.py[/#87D7FF]
[#87D7FF]•   791  src/sase/axe/run_agent_runner_setup.py[/#87D7FF]
[#87D7FF]•   778  src/sase/axe/runner_workspace_prepare.py[/#87D7FF]
[#87D7FF]•   738  src/sase/ace/tui/actions/agents/_display_panel_widgets.py[/#87D7FF]
[#87D7FF]•   736  tests/test_agent_loader_dedup_merge.py[/#87D7FF]
[#87D7FF]•   732  tests/test_render_visual_snapshot_failure_report.py[/#87D7FF]
[dim #A8A8A8]…and 2 more[/dim #A8A8A8]

[dim #A8A8A8]2 scan roots · limits 1,000 / 850 / 700 lines · sequential queue[/dim #A8A8A8]]])
%model:@medium
%auto
%queue(capacity=3)
#gh:gh_sase-org__sase Can you help me split the `src/sase/ace/tui/actions/agents/_agent_enter_targets.py` file up into multiple files? Use your best
judgement, but let's aim to keep all files <=500 lines of code.