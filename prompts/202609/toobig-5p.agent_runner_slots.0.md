- **AGENTS:**
  - [bbugyi200.athena.toobig-5p.agent_runner_slots.0](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.toobig-5p.agent_runner_slots.0/README.md)

%id:toobig-5p.agent_runner_slots.0 %clan(toobig-5p, tribe=chop, summary=[[[bold
#D75FFF]◆ TOOBIG SPLIT · 34 FILES[/bold #D75FFF] [bold #87D7FF]MISSION[/bold #87D7FF]
[dim #D7D7FF]Decompose oversized Python modules into focused, reviewable units[/dim
#D7D7FF] [dim #D7D7FF]without changing behavior.[/dim #D7D7FF]

[bold #87D7FF]TARGETS[/bold #87D7FF] [bold #FFAF5F]◆ 999
src/sase/memory/selector.py[/bold #FFAF5F] [bold #FFAF5F]◆ 987
tests/ace/tui/modals/test_prompt_history_modal.py[/bold #FFAF5F] [bold #FFAF5F]◆ 986
tests/test_sudo_acceptance.py[/bold #FFAF5F] [bold #FFAF5F]◆ 959
tests/memory/test_memory_selector_render.py[/bold #FFAF5F] [bold #FFAF5F]◆ 952
src/sase/sudo/ssh.py[/bold #FFAF5F] [bold #FFAF5F]◆ 923
tests/ace/tui/visual/_visual_maintenance_run.py[/bold #FFAF5F] [bold #FFAF5F]◆ 914
tests/test_launch_admission_dispatch.py[/bold #FFAF5F] [bold #FFAF5F]◆ 901
tests/sdd_store/test_sidecar_clone_retry.py[/bold #FFAF5F] [bold #FFAF5F]◆ 871
src/sase/service/platform.py[/bold #FFAF5F] [bold #FFAF5F]◆ 864
tests/test_visual_capture.py[/bold #FFAF5F] [dim #A8A8A8]…and 24 more[/dim #A8A8A8]

[dim #A8A8A8]2 scan roots · limits 1,000 / 850 / 700 lines · sequential queue[/dim
#A8A8A8]]]) %model:@medium %auto %queue(capacity=3) #gh:gh_sase-org__sase Can you help
me split the `src/sase/ace/tui/models/agent_runner_slots.py` file up into multiple
files? Use your best judgement, but let's aim to keep all files <=500 lines of code.
