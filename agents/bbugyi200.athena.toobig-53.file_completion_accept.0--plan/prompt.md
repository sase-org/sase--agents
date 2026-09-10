%id:toobig-53.file_completion_accept.0
%clan(toobig-53, tribe=chop, summary=[[[bold #D75FFF]◆ TOOBIG SPLIT · 8 FILES[/bold #D75FFF]
[bold #87D7FF]MISSION[/bold #87D7FF]
[dim #D7D7FF]Decompose oversized Python modules into focused, reviewable units[/dim #D7D7FF]
[dim #D7D7FF]without changing behavior.[/dim #D7D7FF]

[bold #87D7FF]TARGETS[/bold #87D7FF]
[bold #FFAF5F]◆ 973  src/sase/pager/_trail_chrome.py[/bold #FFAF5F]
[bold #FFAF5F]◆ 949  src/sase/sdd/artifact_link_outbox.py[/bold #FFAF5F]
[bold #FFAF5F]◆ 918  src/sase/sdd/artifact_link_event_publisher.py[/bold #FFAF5F]
[bold #FFAF5F]◆ 866  tests/dispatch/test_machine_init.py[/bold #FFAF5F]
[#87D7FF]• 817  src/sase/sdd/_artifact_link_publication_retry.py[/#87D7FF]
[#87D7FF]• 730  tests/ace/tui/visual/test_ace_png_snapshots_model_completion.py[/#87D7FF]
[#87D7FF]• 728  tests/doctor/test_checks_providers.py[/#87D7FF]
[#87D7FF]• 717  src/sase/ace/tui/widgets/_file_completion_accept.py[/#87D7FF]

[dim #A8A8A8]2 scan roots · limits 1,000 / 850 / 700 lines · sequential queue[/dim #A8A8A8]]])
%model:@medium
%auto
%queue(runners=3)
#gh:gh_sase-org__sase
Can you help me split the `src/sase/ace/tui/widgets/_file_completion_accept.py` file up into multiple files? Use your best
judgement, but let's aim to keep all files <=500 lines of code.