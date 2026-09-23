%id:toobig-5y.startup_loads.0
%clan(toobig-5y, tribe=chop, summary=[[[bold #D75FFF]◆ TOOBIG SPLIT · 16 FILES[/bold #D75FFF]
[bold #87D7FF]MISSION[/bold #87D7FF]
[dim #D7D7FF]Decompose oversized Python modules into focused, reviewable units[/dim #D7D7FF]
[dim #D7D7FF]without changing behavior.[/dim #D7D7FF]

[bold #87D7FF]TARGETS[/bold #87D7FF]
[bold #FF5F87]▲ 1,145  tests/ace/tui/test_plugins_browser_pane_agent_clis_install.py[/bold #FF5F87]
[bold #FFAF5F]◆   910  tests/test_project_alias_services.py[/bold #FFAF5F]
[bold #FFAF5F]◆   902  src/sase/ace/tui/modals/plugins_browser_install.py[/bold #FFAF5F]
[#87D7FF]•   849  tests/ace/tui/test_agent_tribe_assignment.py[/#87D7FF]
[#87D7FF]•   843  tests/ace/tui/widgets/test_agent_jump_panel.py[/#87D7FF]
[#87D7FF]•   805  src/sase/ace/tui/widgets/artifacts/beads_navigation.py[/#87D7FF]
[#87D7FF]•   798  src/sase/llm_provider/usage/refresh.py[/#87D7FF]
[#87D7FF]•   794  tests/ace/tui/test_plugins_browser_rows.py[/#87D7FF]
[#87D7FF]•   794  tests/agent_clis/test_install.py[/#87D7FF]
[#87D7FF]•   782  src/sase/llm_provider/usage/claude.py[/#87D7FF]
[dim #A8A8A8]…and 6 more[/dim #A8A8A8]

[dim #A8A8A8]2 scan roots · limits 1,000 / 850 / 700 lines · sequential queue[/dim #A8A8A8]]])
%model:@medium
%auto
%queue(capacity=3)
#gh:gh_sase-org__sase Can you help me split the `src/sase/ace/tui/actions/_startup_loads.py` file up into multiple files? Use your best
judgement, but let's aim to keep all files <=500 lines of code.