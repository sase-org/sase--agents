- **AGENTS:**
  - [bbugyi200.athena.toobig-78.test_axe_chop_sidecar_auto_sync.0](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.toobig-78.test_axe_chop_sidecar_auto_sync.0/README.md)

%id:toobig-78.test_axe_chop_sidecar_auto_sync.0 %clan(toobig-78, tribe=chop,
summary=[[[bold #D75FFF]◆ TOOBIG SPLIT · 2 FILES[/bold #D75FFF] [bold
#87D7FF]MISSION[/bold #87D7FF] [dim #D7D7FF]Decompose oversized Python modules into
focused, reviewable units[/dim #D7D7FF] [dim #D7D7FF]without changing behavior.[/dim
#D7D7FF]

[bold #87D7FF]TARGETS[/bold #87D7FF] [bold #FF5F87]▲ 1,011
tests/test_commit_revision_pin_dispatch.py[/bold #FF5F87] [#87D7FF]• 728
tests/test_axe_chop_sidecar_auto_sync.py[/#87D7FF]

[dim #A8A8A8]2 scan roots · limits 1,000 / 850 / 700 lines · sequential queue[/dim
#A8A8A8]]]) %model:@medium %auto %queue(capacity=5) #gh:gh_sase-org__sase Can you help
me split the `tests/test_axe_chop_sidecar_auto_sync.py` file into multiple files? Use
your best judgment, but keep every resulting file at 500 lines of code or fewer.

Preserve behavior and the original module's public import path. A facade may re-export
public names, but never `_private` names. Never import a `_`-prefixed name across the
new modules. If more than one new module needs a helper, give it a public name inside an
already-private (`_`-prefixed) module; move a helper used by only one other module into
that module instead. Keep test monkeypatch targets working, or retarget the tests.

Before finishing, run `just _lint-symvision`, `just _lint-mypy`, and `just _lint-toobig`
individually. Fix every issue in a file the split touched, even if an earlier
`just check` stage is already red. Then run `sase tool run check`.
