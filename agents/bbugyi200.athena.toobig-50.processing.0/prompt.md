%id:toobig-50.processing.0
%clan(toobig-50, tribe=chop, summary=[[[bold #D75FFF]◆ TOOBIG SPLIT · 9 FILES[/bold #D75FFF]
[bold #87D7FF]MISSION[/bold #87D7FF]
[dim #D7D7FF]Decompose oversized Python modules into focused, reviewable units[/dim #D7D7FF]
[dim #D7D7FF]without changing behavior.[/dim #D7D7FF]

[bold #87D7FF]TARGETS[/bold #87D7FF]
[bold #FFAF5F]◆ 985  src/sase/pager/resolve.py[/bold #FFAF5F]
[bold #FFAF5F]◆ 975  tests/main/test_notify_handler.py[/bold #FFAF5F]
[bold #FFAF5F]◆ 932  tests/pager/test_app.py[/bold #FFAF5F]
[bold #FFAF5F]◆ 915  tests/pager/test_resolve.py[/bold #FFAF5F]
[bold #FFAF5F]◆ 900  tests/ace/tui/actions/test_view_files_pager.py[/bold #FFAF5F]
[#87D7FF]• 801  src/sase/artifact_ref_models.py[/#87D7FF]
[#87D7FF]• 778  src/sase/llm_provider/usage/store.py[/#87D7FF]
[#87D7FF]• 728  tests/test_command_availability_agents.py[/#87D7FF]
[#87D7FF]• 702  src/sase/ace/tui/actions/hints/_processing.py[/#87D7FF]

[dim #A8A8A8]2 scan roots · limits 1,000 / 850 / 700 lines · sequential queue[/dim #A8A8A8]]])
%model:@medium
%auto
%wait(runners=3)
%wait(priority=20)
#gh:gh_sase-org__sase
Can you help me split the `src/sase/ace/tui/actions/hints/_processing.py` file up into multiple files? Use your best
judgement, but let's aim to keep all files <=500 lines of code.