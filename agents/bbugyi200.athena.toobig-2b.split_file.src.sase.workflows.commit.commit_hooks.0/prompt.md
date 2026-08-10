#gh:sase-org/sase
%id:toobig-2b.split_file.src.sase.workflows.commit.commit_hooks.0
%clan(toobig-2b, tribe=chop, summary=[[[bold #D75FFF]◆ TOOBIG SPLIT · 3 FILES[/bold #D75FFF]
[bold #87D7FF]MISSION[/bold #87D7FF]
[dim #D7D7FF]Decompose oversized Python modules into focused, reviewable units[/dim #D7D7FF]
[dim #D7D7FF]without changing behavior.[/dim #D7D7FF]

[bold #87D7FF]TARGETS[/bold #87D7FF]
[#87D7FF]• 833  tests/test_commit_hooks_artifacts.py[/#87D7FF]
[#87D7FF]• 777  src/sase/workflows/commit/commit_hooks.py[/#87D7FF]
[#87D7FF]• 772  tests/test_agent_list_entries.py[/#87D7FF]

[dim #A8A8A8]2 scan roots · limits 1,000 / 850 / 700 lines · sequential queue[/dim #A8A8A8]]])
%wait(runners=3)
%auto %wait(priority=20) #split_file:src/sase/workflows/commit/commit_hooks.py