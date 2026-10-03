- **AGENTS:**
  - [bbugyi200.athena.toobig-6y.memory_panel_rendering.0](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.toobig-6y.memory_panel_rendering.0/README.md)

%id:toobig-6y.memory_panel_rendering.0 %clan(toobig-6y, tribe=chop, summary=[[[bold
#D75FFF]◆ TOOBIG SPLIT · 9 FILES[/bold #D75FFF] [bold #87D7FF]MISSION[/bold #87D7FF]
[dim #D7D7FF]Decompose oversized Python modules into focused, reviewable units[/dim
#D7D7FF] [dim #D7D7FF]without changing behavior.[/dim #D7D7FF]

[bold #87D7FF]TARGETS[/bold #87D7FF] [bold #FF5F87]▲ 1,087
…/tui/visual/test_ace_png_snapshots_memory_pane_history_states.py[/bold #FF5F87] [bold
#FFAF5F]◆ 924 tests/test_macro_terminology.py[/bold #FFAF5F] [bold #FFAF5F]◆ 859
tests/test_detach_scope.py[/bold #FFAF5F] [#87D7FF]• 806
…/ace/tui/widgets/prompt_panel/_agent_display_header_summary.py[/#87D7FF] [#87D7FF]• 802
tests/ace/tui/test_prompt_catalog.py[/#87D7FF] [#87D7FF]• 781
tests/ace/tui/widgets/test_xprompt_completion_spacer.py[/#87D7FF] [#87D7FF]• 773
tests/ace/tui/modals/test_memory_panel_history.py[/#87D7FF] [#87D7FF]• 706
tests/_macro_terminology_string_pairs_b.py[/#87D7FF] [#87D7FF]• 702
src/sase/ace/tui/modals/memory_panel_rendering.py[/#87D7FF]

[dim #A8A8A8]2 scan roots · limits 1,000 / 850 / 700 lines · sequential queue[/dim
#A8A8A8]]]) %model:@medium %auto %queue(capacity=5) #gh:gh_sase-org__sase Can you help
me split the `src/sase/ace/tui/modals/memory_panel_rendering.py` file into multiple
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
