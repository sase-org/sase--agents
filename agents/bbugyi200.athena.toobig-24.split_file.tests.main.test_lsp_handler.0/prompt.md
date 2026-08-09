#gh:sase-org/sase
%id:toobig-24.split_file.tests.main.test_lsp_handler.0
%clan(toobig-24, tribe=chop, summary=[[[bold #D75FFF]◆ TOOBIG SPLIT · 6 FILES[/bold #D75FFF]
[bold #87D7FF]MISSION[/bold #87D7FF]
[dim #D7D7FF]Decompose oversized Python modules into focused, reviewable units[/dim #D7D7FF]
[dim #D7D7FF]without changing behavior.[/dim #D7D7FF]

[bold #87D7FF]TARGETS[/bold #87D7FF]
[bold #FFAF5F]◆ 977  src/sase/artifact_ref_prompt.py[/bold #FFAF5F]
[bold #FFAF5F]◆ 861  tests/test_artifact_ref_preprocessing.py[/bold #FFAF5F]
[#87D7FF]• 784  src/sase/ace/tui/widgets/_prompt_input_bar_stack_rendering.py[/#87D7FF]
[#87D7FF]• 732  tests/main/test_lsp_handler.py[/#87D7FF]
[#87D7FF]• 713  tests/test_bead/test_project.py[/#87D7FF]
[#87D7FF]• 708  src/sase/xprompt/workflow_loader.py[/#87D7FF]

[dim #A8A8A8]2 scan roots · limits 1,000 / 850 / 700 lines · sequential queue[/dim #A8A8A8]]])
%wait(runners=3)
%auto %wait(priority=20) #split_file:tests/main/test_lsp_handler.py