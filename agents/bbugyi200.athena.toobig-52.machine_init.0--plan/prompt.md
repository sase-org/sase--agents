%id:toobig-52.machine_init.0
%clan(toobig-52, tribe=chop, summary=[[[bold #D75FFF]◆ TOOBIG SPLIT · 3 FILES[/bold #D75FFF]
[bold #87D7FF]MISSION[/bold #87D7FF]
[dim #D7D7FF]Decompose oversized Python modules into focused, reviewable units[/dim #D7D7FF]
[dim #D7D7FF]without changing behavior.[/dim #D7D7FF]

[bold #87D7FF]TARGETS[/bold #87D7FF]
[bold #FFAF5F]◆ 866  tests/dispatch/test_machine_init.py[/bold #FFAF5F]
[#87D7FF]• 817  src/sase/sdd/_artifact_link_publication_retry.py[/#87D7FF]
[#87D7FF]• 709  src/sase/dispatch/machine_init.py[/#87D7FF]

[dim #A8A8A8]2 scan roots · limits 1,000 / 850 / 700 lines · sequential queue[/dim #A8A8A8]]])
%model:@medium
%auto
%queue(runners=3, priority=20)
#gh:gh_sase-org__sase
Can you help me split the `src/sase/dispatch/machine_init.py` file up into multiple files? Use your best
judgement, but let's aim to keep all files <=500 lines of code.