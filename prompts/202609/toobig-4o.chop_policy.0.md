- **AGENTS:**
  - [bbugyi200.athena.toobig-4o.chop_policy.0](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.toobig-4o.chop_policy.0/README.md)

%id:toobig-4o.chop_policy.0 %clan(toobig-4o, tribe=chop, summary=[[[bold #D75FFF]◆
TOOBIG SPLIT · 9 FILES[/bold #D75FFF] [bold #87D7FF]MISSION[/bold #87D7FF] [dim
#D7D7FF]Decompose oversized Python modules into focused, reviewable units[/dim #D7D7FF]
[dim #D7D7FF]without changing behavior.[/dim #D7D7FF]

[bold #87D7FF]TARGETS[/bold #87D7FF] [bold #FFAF5F]◆ 948
tests/ace/tui/test_kill_and_edit_last_launch.py[/bold #FFAF5F] [#87D7FF]• 798
src/sase/main/parser.py[/#87D7FF] [#87D7FF]• 748
tests/test_bead/test_conflict_resolver.py[/#87D7FF] [#87D7FF]• 745
src/sase/bead/conflict_resolver.py[/#87D7FF] [#87D7FF]• 735
tests/ace/tui/test_artifacts_relation_sources.py[/#87D7FF] [#87D7FF]• 728
src/sase/main/init_onboarding.py[/#87D7FF] [#87D7FF]• 727
src/sase/finalizers/commit_dispatch.py[/#87D7FF] [#87D7FF]• 719
tests/ace/tui/test_projects_pane_init_flow.py[/#87D7FF] [#87D7FF]• 718
src/sase/axe/chop_policy.py[/#87D7FF]

[dim #A8A8A8]2 scan roots · limits 1,000 / 850 / 700 lines · sequential queue[/dim
#A8A8A8]]]) %model:@medium %auto %wait(runners=3) %wait(priority=20)
#gh:gh_sase-org__sase Can you help me split the `src/sase/axe/chop_policy.py` file up
into multiple files? Use your best judgement, but let's aim to keep all files <=500
lines of code.
