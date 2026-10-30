%id:toobig-8w.staged_handoff.0
%clan(toobig-8w, tribe=chop, summary=[[[bold #D75FFF]◆ TOOBIG SPLIT · 13 FILES[/bold #D75FFF]
[bold #87D7FF]MISSION[/bold #87D7FF]
[dim #D7D7FF]Decompose oversized Python modules into focused, reviewable units[/dim #D7D7FF]
[dim #D7D7FF]without changing behavior.[/dim #D7D7FF]

[bold #87D7FF]TARGETS[/bold #87D7FF]
[bold #FF5F87]▲ 1,784  src/sase/agents_sync/publication_state_repair.py[/bold #FF5F87]
[bold #FFAF5F]◆   936  src/sase/monitor/start_stage.py[/bold #FFAF5F]
[bold #FFAF5F]◆   904  tests/test_workflow_completion.py[/bold #FFAF5F]
[#87D7FF]•   815  src/sase/agents_sync/publication_snapshot.py[/#87D7FF]
[#87D7FF]•   794  tests/test_agents_tab_graph_isolation.py[/#87D7FF]
[#87D7FF]•   774  tests/agents_sync/test_publication_state_repair.py[/#87D7FF]
[#87D7FF]•   758  src/sase/agent/staged_handoff.py[/#87D7FF]
[#87D7FF]•   750  tests/agents_sync/test_cli.py[/#87D7FF]
[#87D7FF]•   739  src/sase/core/tool_run.py[/#87D7FF]
[#87D7FF]•   718  src/sase/core/prompt_artifact_staging.py[/#87D7FF]
[dim #A8A8A8]…and 3 more[/dim #A8A8A8]

[dim #A8A8A8]2 scan roots · limits 1,000 / 850 / 700 lines · sequential queue[/dim #A8A8A8]]])
%model:@medium
%auto
%queue(capacity=5)
#gh:gh_sase-org__sase Can you help me split the `src/sase/agent/staged_handoff.py` file into multiple files? Use your best
judgment, but keep every resulting file at 500 lines of code or fewer.

Preserve behavior and the original module's public import path. A facade may re-export
public names, but never `_private` names. Never import a `_`-prefixed name across the
new modules. If more than one new module needs a helper, give it a public name inside an
already-private (`_`-prefixed) module; move a helper used by only one other module into
that module instead. Keep test monkeypatch targets working, or retarget the tests.

Before finishing, run `just _lint-symvision`, `just _lint-mypy`, and `just _lint-toobig`
individually. Fix every issue in a file the split touched, even if an earlier
`just check` stage is already red. Then run `sase tool run check`.