- **AGENTS:**
  - [bbugyi200.athena.toobig-5j.disk_footprint_reap.0](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.toobig-5j.disk_footprint_reap.0/README.md)

%id:toobig-5j.disk_footprint_reap.0 %clan(toobig-5j, tribe=chop, summary=[[[bold
#D75FFF]◆ TOOBIG SPLIT · 4 FILES[/bold #D75FFF] [bold #87D7FF]MISSION[/bold #87D7FF]
[dim #D7D7FF]Decompose oversized Python modules into focused, reviewable units[/dim
#D7D7FF] [dim #D7D7FF]without changing behavior.[/dim #D7D7FF]

[bold #87D7FF]TARGETS[/bold #87D7FF] [#87D7FF]• 741
src/sase/core/disk_footprint_reap.py[/#87D7FF] [#87D7FF]• 730
tests/ace/tui/widgets/test_xprompt_arg_value_completion.py[/#87D7FF] [#87D7FF]• 729
src/sase/workspace_provider/git_objects.py[/#87D7FF] [#87D7FF]• 717
tests/core/test_disk_footprint.py[/#87D7FF]

[dim #A8A8A8]2 scan roots · limits 1,000 / 850 / 700 lines · sequential queue[/dim
#A8A8A8]]]) %model:@medium %auto %queue(capacity=3) #gh:gh_sase-org__sase Can you help
me split the `src/sase/core/disk_footprint_reap.py` file up into multiple files? Use
your best judgement, but let's aim to keep all files <=500 lines of code.
