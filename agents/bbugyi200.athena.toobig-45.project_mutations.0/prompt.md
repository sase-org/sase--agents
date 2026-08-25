%id:toobig-45.project_mutations.0
%clan(toobig-45, tribe=chop, summary=[[[bold #D75FFF]◆ TOOBIG SPLIT · 11 FILES[/bold #D75FFF]
[bold #87D7FF]MISSION[/bold #87D7FF]
[dim #D7D7FF]Decompose oversized Python modules into focused, reviewable units[/dim #D7D7FF]
[dim #D7D7FF]without changing behavior.[/dim #D7D7FF]

[bold #87D7FF]TARGETS[/bold #87D7FF]
[bold #FFAF5F]◆ 999  src/sase/scripts/agent_chat_from_name.py[/bold #FFAF5F]
[bold #FFAF5F]◆ 960  tests/test_ratchet_core_window_tool.py[/bold #FFAF5F]
[bold #FFAF5F]◆ 911  src/sase/history/chat_fork.py[/bold #FFAF5F]
[bold #FFAF5F]◆ 888  tests/test_test_cost.py[/bold #FFAF5F]
[bold #FFAF5F]◆ 876  tests/test_models_panel_provider_modal.py[/bold #FFAF5F]
[#87D7FF]• 786  tests/test_query_profile.py[/#87D7FF]
[#87D7FF]• 779  tests/main/test_init_memory_managed_agents.py[/#87D7FF]
[#87D7FF]• 747  src/sase/bead/_project_mutations.py[/#87D7FF]
[#87D7FF]• 736  tests/test_launch_admission.py[/#87D7FF]
[#87D7FF]• 722  tests/ace/tui/test_agent_marking.py[/#87D7FF]
[dim #A8A8A8]…and 1 more[/dim #A8A8A8]

[dim #A8A8A8]2 scan roots · limits 1,000 / 850 / 700 lines · sequential queue[/dim #A8A8A8]]])
%model:@medium
%auto
%wait(runners=3)
%wait(priority=20)
#gh:gh_sase-org__sase
Can you help me split the `src/sase/bead/_project_mutations.py` file up into multiple files? Use your best
judgement, but let's aim to keep all files <=500 lines of code.