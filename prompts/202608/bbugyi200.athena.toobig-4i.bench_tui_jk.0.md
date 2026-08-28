- **AGENTS:**
  - [bbugyi200.athena.toobig-4i.bench_tui_jk.0](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.toobig-4i.bench_tui_jk.0/README.md)

%id:toobig-4i.bench_tui_jk.0 %clan(toobig-4i, tribe=chop, summary=[[[bold #D75FFF]◆
TOOBIG SPLIT · 8 FILES[/bold #D75FFF] [bold #87D7FF]MISSION[/bold #87D7FF] [dim
#D7D7FF]Decompose oversized Python modules into focused, reviewable units[/dim #D7D7FF]
[dim #D7D7FF]without changing behavior.[/dim #D7D7FF]

[bold #87D7FF]TARGETS[/bold #87D7FF] [bold #FFAF5F]◆ 912 src/sase/pager/screen.py[/bold
#FFAF5F] [#87D7FF]• 810 tests/test_github_actions_ci.py[/#87D7FF] [#87D7FF]• 759
tests/ace/tui/visual/test_ace_png_snapshots_agents_family_panel.py[/#87D7FF] [#87D7FF]•
738 tests/ace/tui/bench_tui_jk.py[/#87D7FF] [#87D7FF]• 714
src/sase/ace/tui/widgets/prompt_panel/_agent_display_hint_render.py[/#87D7FF]
[#87D7FF]• 710 src/sase/ace/tui/models/_loaders/_done_loaders.py[/#87D7FF] [#87D7FF]•
706 tests/test_suite_gate_integration.py[/#87D7FF] [#87D7FF]• 701
tests/ace/tui/test_artifacts_relation_collapse.py[/#87D7FF]

[dim #A8A8A8]2 scan roots · limits 1,000 / 850 / 700 lines · sequential queue[/dim
#A8A8A8]]]) %model:@medium %auto %wait(runners=3) %wait(priority=20)
#gh:gh_sase-org__sase Can you help me split the `tests/ace/tui/bench_tui_jk.py` file
up into multiple files? Use your best judgement, but let's aim to keep all files <=500
lines of code.
