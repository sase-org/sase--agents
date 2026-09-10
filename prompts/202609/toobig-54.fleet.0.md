- **AGENTS:**
  - [bbugyi200.athena.toobig-54.fleet.0](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.toobig-54.fleet.0/README.md)

%id:toobig-54.fleet.0 %clan(toobig-54, tribe=chop, summary=[[[bold #D75FFF]◆ TOOBIG
SPLIT · 9 FILES[/bold #D75FFF] [bold #87D7FF]MISSION[/bold #87D7FF] [dim
#D7D7FF]Decompose oversized Python modules into focused, reviewable units[/dim #D7D7FF]
[dim #D7D7FF]without changing behavior.[/dim #D7D7FF]

[bold #87D7FF]TARGETS[/bold #87D7FF] [bold #FFAF5F]◆ 875
tests/ace/tui/fleet_fixture.py[/bold #FFAF5F] [#87D7FF]• 838
src/sase/ace/tui/actions/agents/_fleet.py[/#87D7FF] [#87D7FF]• 828
src/sase/ace/tui/modals/machines_pane.py[/#87D7FF] [#87D7FF]• 801
tests/test_run_agent_runner_slot_capacity.py[/#87D7FF] [#87D7FF]• 755
tests/test_bead/test_cli_work_from_plan_publication.py[/#87D7FF] [#87D7FF]• 728
tests/doctor/test_checks_providers.py[/#87D7FF] [#87D7FF]• 724
tests/ace/tui/test_agent_display_diff.py[/#87D7FF] [#87D7FF]• 721
tests/test_core_agent_launch_wire.py[/#87D7FF] [#87D7FF]• 708
src/sase/ace/tui/widgets/_agent_list_build.py[/#87D7FF]

[dim #A8A8A8]2 scan roots · limits 1,000 / 850 / 700 lines · sequential queue[/dim
#A8A8A8]]]) %model:@medium %auto %queue(runners=3) #gh:gh_sase-org__sase Can you help
me split the `src/sase/ace/tui/actions/agents/_fleet.py` file up into multiple files?
Use your best judgement, but let's aim to keep all files <=500 lines of code.
