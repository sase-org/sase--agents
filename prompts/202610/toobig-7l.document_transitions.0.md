- **AGENTS:**
  - [bbugyi200.athena.toobig-7l.document_transitions.0](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.toobig-7l.document_transitions.0/README.md)

%id:toobig-7l.document_transitions.0 %clan(toobig-7l, tribe=chop, summary=[[[bold
#D75FFF]◆ TOOBIG SPLIT · 5 FILES[/bold #D75FFF] [bold #87D7FF]MISSION[/bold #87D7FF]
[dim #D7D7FF]Decompose oversized Python modules into focused, reviewable units[/dim
#D7D7FF] [dim #D7D7FF]without changing behavior.[/dim #D7D7FF]

[bold #87D7FF]TARGETS[/bold #87D7FF] [bold #FF5F87]▲ 1,368
src/sase/agent/auto_restart/healer.py[/bold #FF5F87] [bold #FF5F87]▲ 1,015
tests/test_agent_auto_restart_scan.py[/bold #FF5F87] [#87D7FF]• 849
tests/ace/tui/test_live_reply_follow_mounted.py[/#87D7FF] [#87D7FF]• 729
src/sase/agent/auto_restart/notify.py[/#87D7FF] [#87D7FF]• 705
src/sase/ace/tui/widgets/decks/document_transitions.py[/#87D7FF]

[dim #A8A8A8]2 scan roots · limits 1,000 / 850 / 700 lines · sequential queue[/dim
#A8A8A8]]]) %model:@medium %auto %queue(capacity=5) #gh:gh_sase-org__sase Can you help
me split the `src/sase/ace/tui/widgets/decks/document_transitions.py` file into multiple
files? Use your best judgment, but keep every resulting file at 500 lines of code or
fewer.

Preserve behavior and the original module's public import path. A facade may re-export
public names, but never `_private` names. Never import a `_`-prefixed name across the
new modules. If more than one new module needs a helper, give it a public name inside an
already-private (`_`-prefixed) module; move a helper used by only one other module into
that module instead. Keep test monkeypatch targets working, or retarget the tests.

Before finishing, run `just _lint-symvision`, `just _lint-mypy`, and `just _lint-toobig`
individually. Fix every issue in a file the split touched, even if an earlier
`just check` stage is already red. Then run `sase tool run check`.
