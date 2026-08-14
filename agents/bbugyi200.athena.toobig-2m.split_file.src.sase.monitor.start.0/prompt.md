#gh:sase-org/sase
%id:toobig-2m.split_file.src.sase.monitor.start.0
%clan(toobig-2m, tribe=chop, summary=[[[bold #D75FFF]◆ TOOBIG SPLIT · 2 FILES[/bold #D75FFF]
[bold #87D7FF]MISSION[/bold #87D7FF]
[dim #D7D7FF]Decompose oversized Python modules into focused, reviewable units[/dim #D7D7FF]
[dim #D7D7FF]without changing behavior.[/dim #D7D7FF]

[bold #87D7FF]TARGETS[/bold #87D7FF]
[#87D7FF]• 794  src/sase/monitor/start.py[/#87D7FF]
[#87D7FF]• 739  tests/ace/tui/test_memory_reads_loader.py[/#87D7FF]

[dim #A8A8A8]2 scan roots · limits 1,000 / 850 / 700 lines · sequential queue[/dim #A8A8A8]]])
%wait(runners=3)
%auto %wait(priority=20) #split_file:src/sase/monitor/start.py