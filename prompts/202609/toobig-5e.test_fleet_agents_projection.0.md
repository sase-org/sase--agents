- **AGENTS:**
  - [bbugyi200.athena.toobig-5e.test_fleet_agents_projection.0](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.toobig-5e.test_fleet_agents_projection.0/README.md)

%id:toobig-5e.test_fleet_agents_projection.0 %clan(toobig-5e, tribe=chop,
summary=[[[bold #D75FFF]◆ TOOBIG SPLIT · 12 FILES[/bold #D75FFF] [bold
#87D7FF]MISSION[/bold #87D7FF] [dim #D7D7FF]Decompose oversized Python modules into
focused, reviewable units[/dim #D7D7FF] [dim #D7D7FF]without changing behavior.[/dim
#D7D7FF]

[bold #87D7FF]TARGETS[/bold #87D7FF] [bold #FFAF5F]◆ 992
tests/test_core_facade/test_notification_store.py[/bold #FFAF5F] [#87D7FF]• 842
tests/perf/agent_load_tiering_fixture.py[/#87D7FF] [#87D7FF]• 827
tests/ace/tui/test_fleet_agents_projection.py[/#87D7FF] [#87D7FF]• 803
tests/test_axe_chop_agents.py[/#87D7FF] [#87D7FF]• 786
tests/test_pooled_alias_single_consumption.py[/#87D7FF] [#87D7FF]• 784
tests/test_bare_git_workspace.py[/#87D7FF] [#87D7FF]• 781
tests/test_gate_wait_dependency.py[/#87D7FF] [#87D7FF]• 769
tests/perf/agent_load_tiering_harness.py[/#87D7FF] [#87D7FF]• 750
tests/test_managed_tmp_reaper.py[/#87D7FF] [#87D7FF]• 731
tests/test_enrich_agent_waiting.py[/#87D7FF] [dim #A8A8A8]…and 2 more[/dim #A8A8A8]

[dim #A8A8A8]2 scan roots · limits 1,000 / 850 / 700 lines · sequential queue[/dim
#A8A8A8]]]) %model:@medium %auto %queue(capacity=3) #gh:gh_sase-org__sase Can you help
me split the `tests/ace/tui/test_fleet_agents_projection.py` file up into multiple
files? Use your best judgement, but let's aim to keep all files <=500 lines of code.
