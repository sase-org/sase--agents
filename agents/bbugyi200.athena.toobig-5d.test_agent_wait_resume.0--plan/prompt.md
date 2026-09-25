%id:toobig-5d.test_agent_wait_resume.0
%clan(toobig-5d, tribe=chop, summary=[[[bold #D75FFF]◆ TOOBIG SPLIT · 26 FILES[/bold #D75FFF]
[bold #87D7FF]MISSION[/bold #87D7FF]
[dim #D7D7FF]Decompose oversized Python modules into focused, reviewable units[/dim #D7D7FF]
[dim #D7D7FF]without changing behavior.[/dim #D7D7FF]

[bold #87D7FF]TARGETS[/bold #87D7FF]
[bold #FFAF5F]◆ 992  tests/test_core_facade/test_notification_store.py[/bold #FFAF5F]
[bold #FFAF5F]◆ 947  src/sase/monitor/resume.py[/bold #FFAF5F]
[#87D7FF]• 848  src/sase/finalizers/commit_repair.py[/#87D7FF]
[#87D7FF]• 842  tests/perf/agent_load_tiering_fixture.py[/#87D7FF]
[#87D7FF]• 826  src/sase/monitor/start.py[/#87D7FF]
[#87D7FF]• 823  tests/monitor/test_monitor_followup.py[/#87D7FF]
[#87D7FF]• 805  tests/pager/_rendered_link_corpus.py[/#87D7FF]
[#87D7FF]• 803  tests/test_axe_chop_agents.py[/#87D7FF]
[#87D7FF]• 786  tests/test_pooled_alias_single_consumption.py[/#87D7FF]
[#87D7FF]• 784  tests/test_bare_git_workspace.py[/#87D7FF]
[dim #A8A8A8]…and 16 more[/dim #A8A8A8]

[dim #A8A8A8]2 scan roots · limits 1,000 / 850 / 700 lines · sequential queue[/dim #A8A8A8]]])
%model:@medium
%auto
%queue(capacity=3)
#gh:gh_sase-org__sase Can you help me split the `tests/ace/tui/test_agent_wait_resume.py` file up into multiple files? Use your best
judgement, but let's aim to keep all files <=500 lines of code.