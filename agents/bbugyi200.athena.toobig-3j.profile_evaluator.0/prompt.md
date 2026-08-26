%id:toobig-3j.profile_evaluator.0
%clan(toobig-3j, tribe=chop, summary=[[[bold #D75FFF]◆ TOOBIG SPLIT · 8 FILES[/bold #D75FFF]
[bold #87D7FF]MISSION[/bold #87D7FF]
[dim #D7D7FF]Decompose oversized Python modules into focused, reviewable units[/dim #D7D7FF]
[dim #D7D7FF]without changing behavior.[/dim #D7D7FF]

[bold #87D7FF]TARGETS[/bold #87D7FF]
[bold #FFAF5F]◆ 940  tests/ace/tui/widgets/test_prompt_panel_section_navigation.py[/bold #FFAF5F]
[bold #FFAF5F]◆ 911  tests/test_launch_condition_workspace.py[/bold #FFAF5F]
[#87D7FF]• 841  src/sase/sdd/_artifact_link_store_impl.py[/#87D7FF]
[#87D7FF]• 808  tests/test_axe_chop_proposal_launch_clan_dispatch.py[/#87D7FF]
[#87D7FF]• 743  tests/sdd/test_artifact_link_store.py[/#87D7FF]
[#87D7FF]• 723  src/sase/workspace_provider/lease.py[/#87D7FF]
[#87D7FF]• 716  src/sase/ace/query/profile_evaluator.py[/#87D7FF]
[#87D7FF]• 716  src/sase/ace/tui/commands/availability.py[/#87D7FF]

[dim #A8A8A8]2 scan roots · limits 1,000 / 850 / 700 lines · sequential queue[/dim #A8A8A8]]])
%model:@medium
%auto
%wait(runners=3)
%wait(priority=20)
#gh:gh_sase-org__sase
Can you help me split the `src/sase/ace/query/profile_evaluator.py` file up into multiple files? Use your best
judgement, but let's aim to keep all files <=500 lines of code.