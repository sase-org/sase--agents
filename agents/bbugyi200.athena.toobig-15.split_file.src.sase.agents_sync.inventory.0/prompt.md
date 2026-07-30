#gh:sase-org/sase
%id:toobig-15.split_file.src.sase.agents_sync.inventory.0
%clan(toobig-15, tribe=chop, summary=[[[bold #D75FFF]◆ TOOBIG SPLIT · 4 FILES[/bold #D75FFF]
[bold #87D7FF]MISSION[/bold #87D7FF]
[dim #D7D7FF]Decompose oversized Python modules into focused, reviewable units[/dim #D7D7FF]
[dim #D7D7FF]without changing behavior.[/dim #D7D7FF]

[bold #87D7FF]TARGETS[/bold #87D7FF]
[#87D7FF]• 783  src/sase/agents_sync/inventory.py[/#87D7FF]
[#87D7FF]• 766  tests/agents_sync/test_inventory.py[/#87D7FF]
[#87D7FF]• 723  tests/main/test_artifact_cli_references.py[/#87D7FF]
[#87D7FF]• 710  tests/agents_sync/test_commit_publication.py[/#87D7FF]

[dim #A8A8A8]2 scan roots · limits 1,000 / 850 / 700 lines · sequential queue[/dim #A8A8A8]]])
%wait(runners=3)
%auto %wait(priority=20) #split_file:src/sase/agents_sync/inventory.py