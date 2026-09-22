%id:toobig-5u.visual_maintenance_salvage.0
%clan(toobig-5u, tribe=chop, summary=[[[bold #D75FFF]◆ TOOBIG SPLIT · 3 FILES[/bold #D75FFF]
[bold #87D7FF]MISSION[/bold #87D7FF]
[dim #D7D7FF]Decompose oversized Python modules into focused, reviewable units[/dim #D7D7FF]
[dim #D7D7FF]without changing behavior.[/dim #D7D7FF]

[bold #87D7FF]TARGETS[/bold #87D7FF]
[#87D7FF]• 734  tests/test_fix_tui_screenshots_apply.py[/#87D7FF]
[#87D7FF]• 732  tests/test_render_visual_snapshot_failure_report.py[/#87D7FF]
[#87D7FF]• 706  tests/ace/tui/visual/_visual_maintenance_salvage.py[/#87D7FF]

[dim #A8A8A8]2 scan roots · limits 1,000 / 850 / 700 lines · sequential queue[/dim #A8A8A8]]])
%model:@medium
%auto
%queue(capacity=3)
#gh:gh_sase-org__sase Can you help me split the `tests/ace/tui/visual/_visual_maintenance_salvage.py` file up into multiple files? Use your best
judgement, but let's aim to keep all files <=500 lines of code.