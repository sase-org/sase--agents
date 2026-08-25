%id:toobig-49.index_queries.0
%clan(toobig-49, tribe=chop, summary=[[[bold #D75FFF]◆ TOOBIG SPLIT · 2 FILES[/bold #D75FFF]
[bold #87D7FF]MISSION[/bold #87D7FF]
[dim #D7D7FF]Decompose oversized Python modules into focused, reviewable units[/dim #D7D7FF]
[dim #D7D7FF]without changing behavior.[/dim #D7D7FF]

[bold #87D7FF]TARGETS[/bold #87D7FF]
[#87D7FF]• 805  tests/test_axe_chop_proposal_launch_clan_dispatch.py[/#87D7FF]
[#87D7FF]• 740  src/sase/core/wait_dependency_resolution/_index_queries.py[/#87D7FF]

[dim #A8A8A8]2 scan roots · limits 1,000 / 850 / 700 lines · sequential queue[/dim #A8A8A8]]])
%model:@medium
%auto
%wait(runners=3)
%wait(priority=20)
#gh:gh_sase-org__sase
Can you help me split the `src/sase/core/wait_dependency_resolution/_index_queries.py` file up into multiple files? Use your best
judgement, but let's aim to keep all files <=500 lines of code.