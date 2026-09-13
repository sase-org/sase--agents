- **AGENTS:**
  - [bbugyi200.athena.toobig-5a.admission.0](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.toobig-5a.admission.0/README.md)

%id:toobig-5a.admission.0 %clan(toobig-5a, tribe=chop, summary=[[[bold #D75FFF]◆ TOOBIG
SPLIT · 15 FILES[/bold #D75FFF] [bold #87D7FF]MISSION[/bold #87D7FF] [dim
#D7D7FF]Decompose oversized Python modules into focused, reviewable units[/dim #D7D7FF]
[dim #D7D7FF]without changing behavior.[/dim #D7D7FF]

[bold #87D7FF]TARGETS[/bold #87D7FF] [bold #FFAF5F]◆ 992
tests/test_core_facade/test_notification_store.py[/bold #FFAF5F] [#87D7FF]• 848
src/sase/finalizers/commit_repair.py[/#87D7FF] [#87D7FF]• 815
src/sase/llm_provider/continuation_budget.py[/#87D7FF] [#87D7FF]• 791
src/sase/monitor/start.py[/#87D7FF] [#87D7FF]• 786
tests/test_pooled_alias_single_consumption.py[/#87D7FF] [#87D7FF]• 784
tests/test_bare_git_workspace.py[/#87D7FF] [#87D7FF]• 778
src/sase/monitor/resume.py[/#87D7FF] [#87D7FF]• 768
src/sase/core/runner_slots/_admission.py[/#87D7FF] [#87D7FF]• 726
tests/monitor/test_monitor_followup_prompt.py[/#87D7FF] [#87D7FF]• 721
src/sase/finalizers/commit.py[/#87D7FF] [dim #A8A8A8]…and 5 more[/dim #A8A8A8]

[dim #A8A8A8]2 scan roots · limits 1,000 / 850 / 700 lines · sequential queue[/dim
#A8A8A8]]]) %model:@medium %auto %queue(capacity=3) #gh:gh_sase-org__sase Can you help
me split the `src/sase/core/runner_slots/_admission.py` file up into multiple files? Use
your best judgement, but let's aim to keep all files <=500 lines of code.
