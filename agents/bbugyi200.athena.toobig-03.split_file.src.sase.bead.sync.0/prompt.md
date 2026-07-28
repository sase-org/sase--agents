#gh:sase-org/sase
%id:toobig-03.split_file.src.sase.bead.sync.0
%clan(toobig-03, tribe=chop, summary=[[[bold #D75FFF]◆ TOOBIG SPLIT · 5 FILES[/bold #D75FFF]
[bold #87D7FF]MISSION[/bold #87D7FF]
[dim #D7D7FF]Decompose oversized Python modules into focused, reviewable units[/dim #D7D7FF]
[dim #D7D7FF]without changing behavior.[/dim #D7D7FF]

[bold #87D7FF]TARGETS[/bold #87D7FF]
[bold #FFAF5F]◆ 949  tests/sdd_store/test_repository_transaction.py[/bold #FFAF5F]
[bold #FFAF5F]◆ 910  tests/agents_sync/test_v2_importer.py[/bold #FFAF5F]
[#87D7FF]• 792  src/sase/bead/sync.py[/#87D7FF]
[#87D7FF]• 761  tests/main/test_task_handler.py[/#87D7FF]
[#87D7FF]• 721  tests/ace/tui/actions/test_prompt_save_xprompt.py[/#87D7FF]

[dim #A8A8A8]2 scan roots · limits 1,000 / 850 / 700 lines · sequential queue[/dim #A8A8A8]]])
%auto %wait(priority=20) #split_file:src/sase/bead/sync.py