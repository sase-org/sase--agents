- **AGENTS:**
  - [bbugyi200.athena.toobig-7r.agent_display_render.0](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.toobig-7r.agent_display_render.0/README.md)

%id:toobig-7r.agent_display_render.0 %clan(toobig-7r, tribe=chop, summary=[[[bold
#D75FFF]◆ TOOBIG SPLIT · 5 FILES[/bold #D75FFF] [bold #87D7FF]MISSION[/bold #87D7FF]
[dim #D7D7FF]Decompose oversized Python modules into focused, reviewable units[/dim
#D7D7FF] [dim #D7D7FF]without changing behavior.[/dim #D7D7FF]

[bold #87D7FF]TARGETS[/bold #87D7FF] [bold #FFAF5F]◆ 913
tests/test_project_display_presentation_audit.py[/bold #FFAF5F] [#87D7FF]• 805
tests/main/test_repo_init_handler_creation.py[/#87D7FF] [#87D7FF]• 778
src/sase/scripts/_chop_wait_checks_run.py[/#87D7FF] [#87D7FF]• 709
src/sase/ace/tui/widgets/prompt_panel/_agent_display_render.py[/#87D7FF] [#87D7FF]• 708
tests/ace/tui/test_tool_runs_deck_cards.py[/#87D7FF]

[dim #A8A8A8]2 scan roots · limits 1,000 / 850 / 700 lines · sequential queue[/dim
#A8A8A8]]]) %model:@medium %auto %queue(capacity=5) #gh:gh_sase-org__sase Can you help
me split the `src/sase/ace/tui/widgets/prompt_panel/_agent_display_render.py` file into
multiple files? Use your best judgment, but keep every resulting file at 500 lines of
code or fewer.

Preserve behavior and the original module's public import path. A facade may re-export
public names, but never `_private` names. Never import a `_`-prefixed name across the
new modules. If more than one new module needs a helper, give it a public name inside an
already-private (`_`-prefixed) module; move a helper used by only one other module into
that module instead. Keep test monkeypatch targets working, or retarget the tests.

Before finishing, run `just _lint-symvision`, `just _lint-mypy`, and `just _lint-toobig`
individually. Fix every issue in a file the split touched, even if an earlier
`just check` stage is already red. Then run `sase tool run check`.
