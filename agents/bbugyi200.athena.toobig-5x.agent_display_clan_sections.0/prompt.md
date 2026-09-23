%id:toobig-5x.agent_display_clan_sections.0
%clan(toobig-5x, tribe=chop, summary=[[[bold #D75FFF]◆ TOOBIG SPLIT · 5 FILES[/bold #D75FFF]
[bold #87D7FF]MISSION[/bold #87D7FF]
[dim #D7D7FF]Decompose oversized Python modules into focused, reviewable units[/dim #D7D7FF]
[dim #D7D7FF]without changing behavior.[/dim #D7D7FF]

[bold #87D7FF]TARGETS[/bold #87D7FF]
[#87D7FF]• 837  tests/test_project_alias_services.py[/#87D7FF]
[#87D7FF]• 736  tests/ace/tui/widgets/test_agent_display_xprompt.py[/#87D7FF]
[#87D7FF]• 710  src/sase/agent/launch_cwd_agents.py[/#87D7FF]
[#87D7FF]• 710  src/sase/bead/work.py[/#87D7FF]
[#87D7FF]• 706  src/sase/ace/tui/widgets/prompt_panel/_agent_display_clan_sections.py[/#87D7FF]

[dim #A8A8A8]2 scan roots · limits 1,000 / 850 / 700 lines · sequential queue[/dim #A8A8A8]]])
%model:@medium
%auto
%queue(capacity=3)
#gh:gh_sase-org__sase Can you help me split the `src/sase/ace/tui/widgets/prompt_panel/_agent_display_clan_sections.py` file up into multiple files? Use your best
judgement, but let's aim to keep all files <=500 lines of code.