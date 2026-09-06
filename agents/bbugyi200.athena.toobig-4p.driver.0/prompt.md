%id:toobig-4p.driver.0
%clan(toobig-4p, tribe=chop, summary=[[[bold #D75FFF]◆ TOOBIG SPLIT · 2 FILES[/bold #D75FFF]
[bold #87D7FF]MISSION[/bold #87D7FF]
[dim #D7D7FF]Decompose oversized Python modules into focused, reviewable units[/dim #D7D7FF]
[dim #D7D7FF]without changing behavior.[/dim #D7D7FF]

[bold #87D7FF]TARGETS[/bold #87D7FF]
[bold #FFAF5F]◆ 916  tests/perf/bench_prompt_search.py[/bold #FFAF5F]
[bold #FFAF5F]◆ 855  src/sase/migration_kit/driver.py[/bold #FFAF5F]

[dim #A8A8A8]2 scan roots · limits 1,000 / 850 / 700 lines · sequential queue[/dim #A8A8A8]]])
%model:@medium
%auto
%wait(runners=3)
%wait(priority=20)
#gh:gh_sase-org__sase
Can you help me split the `src/sase/migration_kit/driver.py` file up into multiple files? Use your best
judgement, but let's aim to keep all files <=500 lines of code.