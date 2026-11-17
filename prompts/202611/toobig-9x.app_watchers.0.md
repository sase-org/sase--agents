- **AGENTS:**
  - [bbugyi200.athena.toobig-9x.app_watchers.0](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.toobig-9x.app_watchers.0/README.md)

%id:toobig-9x.app_watchers.0 %clan(toobig-9x, tribe=chop, summary=[[[bold #D75FFF]◆
TOOBIG SPLIT · 11 FILES[/bold #D75FFF] [bold #87D7FF]MISSION[/bold #87D7FF] [dim
#D7D7FF]Decompose oversized Python modules into focused, reviewable units[/dim #D7D7FF]
[dim #D7D7FF]without changing behavior.[/dim #D7D7FF]

[bold #87D7FF]TARGETS[/bold #87D7FF] [bold #FF5F87]▲ 1,201
tests/ace/tui/test_artifacts_post_paint_publication.py[/bold #FF5F87] [bold #FF5F87]▲
1,092 tests/ace/tui/test_agent_hijack_action.py[/bold #FF5F87] [#87D7FF]• 816
tests/test_agent_hijack_stop.py[/#87D7FF] [#87D7FF]• 775
src/sase/agent/hijack/_stop_orchestrator_main.py[/#87D7FF] [#87D7FF]• 733
src/sase/vcs_provider/plugins/_git_commit_dispatch.py[/#87D7FF] [#87D7FF]• 713
src/sase/monitor/supervise.py[/#87D7FF] [#87D7FF]• 711
tests/test_agent_hijack_latch.py[/#87D7FF] [#87D7FF]• 709
src/sase/gate_turn/settlement.py[/#87D7FF] [#87D7FF]• 708
src/sase/ace/tui/models/agent_loader.py[/#87D7FF] [#87D7FF]• 704
src/sase/ace/tui/_app_watchers.py[/#87D7FF] [dim #A8A8A8]…and 1 more[/dim #A8A8A8]

[dim #A8A8A8]2 scan roots · limits 1,000 / 850 / 700 lines · sequential queue[/dim
#A8A8A8]]]) %model:@medium %auto %queue(capacity=5) #gh:gh_sase-org__sase Can you help
me split the `src/sase/ace/tui/_app_watchers.py` file into multiple files? Use your best
judgment, but keep every resulting file at 500 lines of code or fewer.

Preserve behavior and the original module's public import path. A facade may re-export
public names, but never `_private` names. Never import a `_`-prefixed name across the
new modules. If more than one new module needs a helper, give it a public name inside an
already-private (`_`-prefixed) module; move a helper used by only one other module into
that module instead. Keep test monkeypatch targets working, or retarget the tests.

Before finishing, run `just _lint-symvision`, `just _lint-mypy`, and `just _lint-toobig`
individually. Fix every issue in a file the split touched, even if an earlier
`just check` stage is already red. Then run `sase tool run check`.
