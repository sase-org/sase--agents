- **AGENTS:**
  - [bbugyi200.athena.toobig-63.bead_touches.0](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.toobig-63.bead_touches.0/README.md)

%id:toobig-63.bead_touches.0 %clan(toobig-63, tribe=chop, summary=[[[bold #D75FFF]◆
TOOBIG SPLIT · 36 FILES[/bold #D75FFF] [bold #87D7FF]MISSION[/bold #87D7FF] [dim
#D7D7FF]Decompose oversized Python modules into focused, reviewable units[/dim #D7D7FF]
[dim #D7D7FF]without changing behavior.[/dim #D7D7FF]

[bold #87D7FF]TARGETS[/bold #87D7FF] [bold #FF5F87]▲ 1,168
src/sase/tool/executor.py[/bold #FF5F87] [bold #FF5F87]▲ 1,048
tests/tool/test_settlement.py[/bold #FF5F87] [bold #FF5F87]▲ 1,023
tests/ace/tui/widgets/test_agent_bead_touch_rows.py[/bold #FF5F87] [bold #FFAF5F]◆ 999
tests/ace/tui/command_line/test_transcript_blocks.py[/bold #FFAF5F] [bold #FFAF5F]◆ 960
src/sase/main/plan_direct_approval.py[/bold #FFAF5F] [bold #FFAF5F]◆ 900
tests/test_plan_direct_approval_recovery.py[/bold #FFAF5F] [bold #FFAF5F]◆ 886
tests/test_agent_name_registry_rebuild.py[/bold #FFAF5F] [bold #FFAF5F]◆ 881
tests/ace/tui/command_line/test_panel_shell.py[/bold #FFAF5F] [bold #FFAF5F]◆ 866
tests/ace/tui/visual/test_ace_png_snapshots_agents_sase_context.py[/bold #FFAF5F] [bold
#FFAF5F]◆ 860 tests/ace/tui/widgets/test_agent_header_panel.py[/bold #FFAF5F] [dim
#A8A8A8]…and 26 more[/dim #A8A8A8]

[dim #A8A8A8]2 scan roots · limits 1,000 / 850 / 700 lines · sequential queue[/dim
#A8A8A8]]]) %model:@medium %auto %queue(capacity=3) #gh:gh_sase-org__sase Can you help
me split the `src/sase/ace/tui/bead_touches.py` file into multiple files? Use your best
judgment, but keep every resulting file at 500 lines of code or fewer.

Preserve behavior and the original module's public import path. A facade may re-export
public names, but never `_private` names. Never import a `_`-prefixed name across the
new modules. If more than one new module needs a helper, give it a public name inside an
already-private (`_`-prefixed) module; move a helper used by only one other module into
that module instead. Keep test monkeypatch targets working, or retarget the tests.

Before finishing, run `just _lint-symvision`, `just _lint-mypy`, and `just _lint-toobig`
individually. Fix every issue in a file the split touched, even if an earlier
`just check` stage is already red. Then run `sase tool run check`.
