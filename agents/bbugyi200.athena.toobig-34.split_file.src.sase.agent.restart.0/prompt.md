#gh:sase-org/sase
%id:toobig-34.split_file.src.sase.agent.restart.0
%clan(toobig-34, tribe=chop, summary=[[[bold #D75FFF]◆ TOOBIG SPLIT · 8 FILES[/bold #D75FFF]
[bold #87D7FF]MISSION[/bold #87D7FF]
[dim #D7D7FF]Decompose oversized Python modules into focused, reviewable units[/dim #D7D7FF]
[dim #D7D7FF]without changing behavior.[/dim #D7D7FF]

[bold #87D7FF]TARGETS[/bold #87D7FF]
[#87D7FF]• 825  src/sase/agent/restart.py[/#87D7FF]
[#87D7FF]• 797  src/sase/running_field/_operations.py[/#87D7FF]
[#87D7FF]• 778  tests/test_vcs_xprompt_mru.py[/#87D7FF]
[#87D7FF]• 733  tests/test_config_schema.py[/#87D7FF]
[#87D7FF]• 730  tests/test_running_field_operations.py[/#87D7FF]
[#87D7FF]• 728  src/sase/bead/snooze_gate.py[/#87D7FF]
[#87D7FF]• 720  tests/ace/tui/test_retry_edit_agent_name.py[/#87D7FF]
[#87D7FF]• 713  tests/ace/tui/test_custom_gate_modal.py[/#87D7FF]

[dim #A8A8A8]2 scan roots · limits 1,000 / 850 / 700 lines · sequential queue[/dim #A8A8A8]]])
%wait(runners=3)
%auto %wait(priority=20) #split_file:src/sase/agent/restart.py