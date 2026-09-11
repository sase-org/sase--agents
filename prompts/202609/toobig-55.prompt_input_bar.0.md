- **AGENTS:**
  - [bbugyi200.athena.toobig-55.prompt_input_bar.0](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.toobig-55.prompt_input_bar.0/README.md)

%id:toobig-55.prompt_input_bar.0 %clan(toobig-55, tribe=chop, summary=[[[bold #D75FFF]◆
TOOBIG SPLIT · 20 FILES[/bold #D75FFF] [bold #87D7FF]MISSION[/bold #87D7FF] [dim
#D7D7FF]Decompose oversized Python modules into focused, reviewable units[/dim #D7D7FF]
[dim #D7D7FF]without changing behavior.[/dim #D7D7FF]

[bold #87D7FF]TARGETS[/bold #87D7FF] [bold #FFAF5F]◆ 938
tests/sdd/test_artifact_link_event_acceptance.py[/bold #FFAF5F] [bold #FFAF5F]◆ 919
tests/test_run_agent_runner_slot_capacity.py[/bold #FFAF5F] [bold #FFAF5F]◆ 889
tests/ace/tui/fleet_fixture.py[/bold #FFAF5F] [#87D7FF]• 848
src/sase/completion/install.py[/#87D7FF] [#87D7FF]• 836
src/sase/artifact_cli/link_health.py[/#87D7FF] [#87D7FF]• 811
tests/ace/tui/test_agent_runner_slots.py[/#87D7FF] [#87D7FF]• 799
tests/sdd_store/test_sidecar_clone.py[/#87D7FF] [#87D7FF]• 792
tests/test_provider_disables_indicator.py[/#87D7FF] [#87D7FF]• 771
tests/test_validate_sase_core_rs_contracts_tool.py[/#87D7FF] [#87D7FF]• 761
tests/ace/tui/test_fleet_agents.py[/#87D7FF] [dim #A8A8A8]…and 10 more[/dim #A8A8A8]

[dim #A8A8A8]2 scan roots · limits 1,000 / 850 / 700 lines · sequential queue[/dim
#A8A8A8]]]) %model:@medium %auto %queue(runners=3) #gh:gh_sase-org__sase Can you help
me split the `src/sase/ace/tui/widgets/prompt_input_bar.py` file up into multiple files?
Use your best judgement, but let's aim to keep all files <=500 lines of code.
