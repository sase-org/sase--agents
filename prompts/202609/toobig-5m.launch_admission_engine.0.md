- **AGENTS:**
  - [bbugyi200.athena.toobig-5m.launch_admission_engine.0](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.toobig-5m.launch_admission_engine.0/README.md)

%id:toobig-5m.launch_admission_engine.0 %clan(toobig-5m, tribe=chop, summary=[[[bold
#D75FFF]◆ TOOBIG SPLIT · 8 FILES[/bold #D75FFF] [bold #87D7FF]MISSION[/bold #87D7FF]
[dim #D7D7FF]Decompose oversized Python modules into focused, reviewable units[/dim
#D7D7FF] [dim #D7D7FF]without changing behavior.[/dim #D7D7FF]

[bold #87D7FF]TARGETS[/bold #87D7FF] [bold #FFAF5F]◆ 938 tests/test_axe_cli.py[/bold
#FFAF5F] [bold #FFAF5F]◆ 864 src/sase/core/agent_hold_facade.py[/bold #FFAF5F]
[#87D7FF]• 788 src/sase/continuation_capture/monitor.py[/#87D7FF] [#87D7FF]• 774
tests/agents_sync/test_publication.py[/#87D7FF] [#87D7FF]• 722
tests/test_config.py[/#87D7FF] [#87D7FF]• 719
src/sase/agent/launch_admission_engine.py[/#87D7FF] [#87D7FF]• 707
tests/test_llm_provider_codex_parser.py[/#87D7FF] [#87D7FF]• 706
tests/continuation/test_capture.py[/#87D7FF]

[dim #A8A8A8]2 scan roots · limits 1,000 / 850 / 700 lines · sequential queue[/dim
#A8A8A8]]]) %model:@medium %auto %queue(capacity=3) #gh:gh_sase-org__sase Can you help
me split the `src/sase/agent/launch_admission_engine.py` file up into multiple files?
Use your best judgement, but let's aim to keep all files <=500 lines of code.
