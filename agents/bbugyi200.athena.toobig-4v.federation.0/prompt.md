%id:toobig-4v.federation.0
%clan(toobig-4v, tribe=chop, summary=[[[bold #D75FFF]◆ TOOBIG SPLIT · 5 FILES[/bold #D75FFF]
[bold #87D7FF]MISSION[/bold #87D7FF]
[dim #D7D7FF]Decompose oversized Python modules into focused, reviewable units[/dim #D7D7FF]
[dim #D7D7FF]without changing behavior.[/dim #D7D7FF]

[bold #87D7FF]TARGETS[/bold #87D7FF]
[#87D7FF]• 814  tests/test_running_agents_snapshot.py[/#87D7FF]
[#87D7FF]• 790  src/sase/dispatch/federation.py[/#87D7FF]
[#87D7FF]• 782  tests/test_fleet_contract_sase_core_rs.py[/#87D7FF]
[#87D7FF]• 775  tests/test_runner_slots.py[/#87D7FF]
[#87D7FF]• 736  tests/test_agent_loader.py[/#87D7FF]

[dim #A8A8A8]2 scan roots · limits 1,000 / 850 / 700 lines · sequential queue[/dim #A8A8A8]]])
%model:@medium
%auto
%wait(runners=3)
%wait(priority=20)
#gh:gh_sase-org__sase
Can you help me split the `src/sase/dispatch/federation.py` file up into multiple files? Use your best
judgement, but let's aim to keep all files <=500 lines of code.