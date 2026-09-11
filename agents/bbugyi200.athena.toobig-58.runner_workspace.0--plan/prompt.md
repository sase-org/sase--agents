%id:toobig-58.runner_workspace.0
%clan(toobig-58, tribe=chop, summary=[[[bold #D75FFF]◆ TOOBIG SPLIT · 7 FILES[/bold #D75FFF]
[bold #87D7FF]MISSION[/bold #87D7FF]
[dim #D7D7FF]Decompose oversized Python modules into focused, reviewable units[/dim #D7D7FF]
[dim #D7D7FF]without changing behavior.[/dim #D7D7FF]

[bold #87D7FF]TARGETS[/bold #87D7FF]
[bold #FF5F87]▲ 1,471  src/sase/continuation_capture.py[/bold #FF5F87]
[bold #FF5F87]▲ 1,108  tests/test_provider_usage_indicator_presentation.py[/bold #FF5F87]
[bold #FFAF5F]◆   894  src/sase/history/chat_fork/continuation.py[/bold #FFAF5F]
[#87D7FF]•   847  tests/main/test_repo_handler_open.py[/#87D7FF]
[#87D7FF]•   846  src/sase/axe/runner_workspace.py[/#87D7FF]
[#87D7FF]•   765  tests/test_llm_provider_invoke.py[/#87D7FF]
[#87D7FF]•   744  src/sase/core/agent_launch_wire.py[/#87D7FF]

[dim #A8A8A8]2 scan roots · limits 1,000 / 850 / 700 lines · sequential queue[/dim #A8A8A8]]])
%model:@medium
%auto
%queue(runners=3)
#gh:gh_sase-org__sase Can you help me split the `src/sase/axe/runner_workspace.py` file up into multiple files? Use your best
judgement, but let's aim to keep all files <=500 lines of code.