%id:toobig-5o.auto_refresh.0
%clan(toobig-5o, tribe=chop, summary=[[[bold #D75FFF]◆ TOOBIG SPLIT · 13 FILES[/bold #D75FFF]
[bold #87D7FF]MISSION[/bold #87D7FF]
[dim #D7D7FF]Decompose oversized Python modules into focused, reviewable units[/dim #D7D7FF]
[dim #D7D7FF]without changing behavior.[/dim #D7D7FF]

[bold #87D7FF]TARGETS[/bold #87D7FF]
[bold #FFAF5F]◆ 999  src/sase/memory/selector.py[/bold #FFAF5F]
[bold #FFAF5F]◆ 987  tests/ace/tui/modals/test_prompt_history_modal.py[/bold #FFAF5F]
[bold #FFAF5F]◆ 912  tests/test_launch_admission_dispatch.py[/bold #FFAF5F]
[bold #FFAF5F]◆ 875  tests/memory/test_memory_selector_render.py[/bold #FFAF5F]
[#87D7FF]• 822  tests/test_run_agent_runner_slot_capacity.py[/#87D7FF]
[#87D7FF]• 759  tests/test_sudo_gate.py[/#87D7FF]
[#87D7FF]• 752  tests/main/test_screenshot_remote_command.py[/#87D7FF]
[#87D7FF]• 742  src/sase/ace/tui/actions/event_refresh/_auto_refresh.py[/#87D7FF]
[#87D7FF]• 721  tests/test_agent_loader_query_window.py[/#87D7FF]
[#87D7FF]• 712  tests/main/test_repo_handler_open_configured.py[/#87D7FF]
[dim #A8A8A8]…and 3 more[/dim #A8A8A8]

[dim #A8A8A8]2 scan roots · limits 1,000 / 850 / 700 lines · sequential queue[/dim #A8A8A8]]])
%model:@medium
%auto
%queue(capacity=3)
#gh:gh_sase-org__sase Can you help me split the `src/sase/ace/tui/actions/event_refresh/_auto_refresh.py` file up into multiple files? Use your best
judgement, but let's aim to keep all files <=500 lines of code.