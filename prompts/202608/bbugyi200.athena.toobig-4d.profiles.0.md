- **AGENTS:**
  - [bbugyi200.athena.toobig-4d.profiles.0](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.toobig-4d.profiles.0/README.md)

%id:toobig-4d.profiles.0 %clan(toobig-4d, tribe=chop, summary=[[[bold #D75FFF]◆ TOOBIG
SPLIT · 6 FILES[/bold #D75FFF] [bold #87D7FF]MISSION[/bold #87D7FF] [dim
#D7D7FF]Decompose oversized Python modules into focused, reviewable units[/dim #D7D7FF]
[dim #D7D7FF]without changing behavior.[/dim #D7D7FF]

[bold #87D7FF]TARGETS[/bold #87D7FF] [#87D7FF]• 808
tests/test_axe_chop_proposal_launch_clan_dispatch.py[/#87D7FF] [#87D7FF]• 787
tests/test_launch_condition_workspace.py[/#87D7FF] [#87D7FF]• 784
src/sase/ace/query_profile/profiles.py[/#87D7FF] [#87D7FF]• 742
src/sase/ace/tui/copy_targets.py[/#87D7FF] [#87D7FF]• 723
src/sase/workspace_provider/lease.py[/#87D7FF] [#87D7FF]• 720
src/sase/llm_provider/commit_finalizer_state.py[/#87D7FF]

[dim #A8A8A8]2 scan roots · limits 1,000 / 850 / 700 lines · sequential queue[/dim
#A8A8A8]]]) %model:@medium %auto %wait(runners=3) %wait(priority=20)
#gh:gh_sase-org__sase Can you help me split the
`src/sase/ace/query_profile/profiles.py` file up into multiple files? Use your best
judgement, but let's aim to keep all files <=500 lines of code.
