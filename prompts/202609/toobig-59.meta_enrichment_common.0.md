- **AGENTS:**
  - [bbugyi200.athena.toobig-59.meta_enrichment_common.0](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.toobig-59.meta_enrichment_common.0/README.md)

%id:toobig-59.meta_enrichment_common.0 %clan(toobig-59, tribe=chop, summary=[[[bold
#D75FFF]◆ TOOBIG SPLIT · 10 FILES[/bold #D75FFF] [bold #87D7FF]MISSION[/bold #87D7FF]
[dim #D7D7FF]Decompose oversized Python modules into focused, reviewable units[/dim
#D7D7FF] [dim #D7D7FF]without changing behavior.[/dim #D7D7FF]

[bold #87D7FF]TARGETS[/bold #87D7FF] [bold #FFAF5F]◆ 864
tests/test_core_facade/test_notification_store.py[/bold #FFAF5F] [#87D7FF]• 786
tests/test_pooled_alias_single_consumption.py[/#87D7FF] [#87D7FF]• 778
src/sase/monitor/resume.py[/#87D7FF] [#87D7FF]• 769
src/sase/main/monitor_handler.py[/#87D7FF] [#87D7FF]• 761
src/sase/monitor/start.py[/#87D7FF] [#87D7FF]• 755
src/sase/ace/tui/models/_loaders/_meta_enrichment_common.py[/#87D7FF] [#87D7FF]• 726
tests/monitor/test_monitor_followup_prompt.py[/#87D7FF] [#87D7FF]• 716
src/sase/monitor/store.py[/#87D7FF] [#87D7FF]• 714
tests/main/test_artifact_cli_link_health.py[/#87D7FF] [#87D7FF]• 701
src/sase/ops/commands/agent.py[/#87D7FF]

[dim #A8A8A8]2 scan roots · limits 1,000 / 850 / 700 lines · sequential queue[/dim
#A8A8A8]]]) %model:@medium %auto %queue(capacity=3) #gh:gh_sase-org__sase Can you help
me split the `src/sase/ace/tui/models/_loaders/_meta_enrichment_common.py` file up into
multiple files? Use your best judgement, but let's aim to keep all files <=500 lines of
code.
