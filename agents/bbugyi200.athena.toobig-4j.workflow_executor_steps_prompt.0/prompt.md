%id:toobig-4j.workflow_executor_steps_prompt.0
%clan(toobig-4j, tribe=chop, summary=[[[bold #D75FFF]◆ TOOBIG SPLIT · 3 FILES[/bold #D75FFF]
[bold #87D7FF]MISSION[/bold #87D7FF]
[dim #D7D7FF]Decompose oversized Python modules into focused, reviewable units[/dim #D7D7FF]
[dim #D7D7FF]without changing behavior.[/dim #D7D7FF]

[bold #87D7FF]TARGETS[/bold #87D7FF]
[#87D7FF]• 734  src/sase/xprompt/workflow_executor_steps_prompt.py[/#87D7FF]
[#87D7FF]• 729  tests/ace/tui/test_lazy_tier2_reconcile.py[/#87D7FF]
[#87D7FF]• 703  tests/test_workflow_executor.py[/#87D7FF]

[dim #A8A8A8]2 scan roots · limits 1,000 / 850 / 700 lines · sequential queue[/dim #A8A8A8]]])
%model:@medium
%auto
%wait(runners=3)
%wait(priority=20)
#gh:gh_sase-org__sase
Can you help me split the `src/sase/xprompt/workflow_executor_steps_prompt.py` file up into multiple files? Use your best
judgement, but let's aim to keep all files <=500 lines of code.