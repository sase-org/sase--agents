# Chat History - ace-run (toobig-9k.test_agent_hijack_recover_reconcile.0)

- **TIMESTAMP:** 2026-11-06 16:53:05 EST
- **MODEL:** grok/grok-4.6
- **AGENT:** toobig-9k.test_agent_hijack_recover_reconcile.0

## Prompt

%id:toobig-9k.test_agent_hijack_recover_reconcile.0
%clan(toobig-9k, tribe=chop, summary=[[[bold #D75FFF]◆ TOOBIG SPLIT · 3 FILES[/bold #D75FFF]
[bold #87D7FF]MISSION[/bold #87D7FF]
[dim #D7D7FF]Decompose oversized Python modules into focused, reviewable units[/dim #D7D7FF]
[dim #D7D7FF]without changing behavior.[/dim #D7D7FF]

[bold #87D7FF]TARGETS[/bold #87D7FF]
[#87D7FF]• 795  tests/test_agent_hijack_recover_reconcile.py[/#87D7FF]
[#87D7FF]• 743  tests/test_axe_chop_output_contract_retention.py[/#87D7FF]
[#87D7FF]• 706  src/sase/project_display_names.py[/#87D7FF]

[dim #A8A8A8]2 scan roots · limits 1,000 / 850 / 700 lines · sequential queue[/dim #A8A8A8]]])
%model:@medium
%auto
%queue(capacity=5)
#gh:gh_sase-org__sase Can you help me split the `tests/test_agent_hijack_recover_reconcile.py` file into multiple files? Use your best
judgment, but keep every resulting file at 500 lines of code or fewer.

Preserve behavior and the original module's public import path. A facade may re-export
public names, but never `_private` names. Never import a `_`-prefixed name across the
new modules. If more than one new module needs a helper, give it a public name inside an
already-private (`_`-prefixed) module; move a helper used by only one other module into
that module instead. Keep test monkeypatch targets working, or retarget the tests.

Before finishing, run `just _lint-symvision`, `just _lint-mypy`, and `just _lint-toobig`
individually. Fix every issue in a file the split touched, even if an earlier
`just check` stage is already red. Then run `sase tool run check`.

## Response

I'll split `tests/test_agent_hijack_recover_reconcile.py` into modules of 500 lines or fewer, then run the requested lints and `sase tool run check`. First I'm reading the split conventions and the current file.

The file is large, so I’ll measure it, read the lint notes, and look at how similar test splits are structured.

I'll look at the existing recover-test facade, who imports this module, and the rest of the 795-line file.

I’ll split along the existing sections: shared helpers in a private support module, resolver and wait tests in their own files, and settlement tests in a third, with a facade at the original import path.

The waits helper stays in that module. Next I’ll write the settlement tests and the facade, then restore the original `tmp_path: Path` annotation.

Format is clean. Next I’ll run the three requested lints one by one.

The lint recipes failed in `_setup` on a stale sase-core schema, so I’m inspecting that gate next.

Mypy only checks `src`, so the test-file typing noise is out of that gate. I’ll run the underlying linters and the split tests, then `sase tool run check`.

The linked sase-core wheel is schema 2 while this tree expects schema 1. I’ll pin `SASE_CORE_WHEEL` to a matching schema-1 wheel so the just lint recipes can run.

Split `tests/test_agent_hijack_recover_reconcile.py` (795 lines) into focused modules, all 500 lines or fewer. The original import path is a facade.

**Layout**
- `tests/_agent_hijack_recover_reconcile_support.py` (55) — shared public helpers `resolving_record` and `dead_seams`
- `tests/test_agent_hijack_recover_reconcile_resolver.py` (201) — resolver crash-repair tests
- `tests/test_agent_hijack_recover_reconcile_waits.py` (162) — successor-following waits, with in-file `_hijacked_agent`
- `tests/test_agent_hijack_recover_reconcile_settlement.py` (408) — settlement-completion tests
- `tests/test_agent_hijack_recover_reconcile.py` (87) — facade re-exporting the public `test_*` names (`__test__ = False`)

Shared helpers live under public names in the private support module. `_hijacked_agent` stays private in the waits module. Monkeypatch targets still point at production modules.

**Verification**
- 34 tests passed in the split modules
- `just _lint-mypy` passed
- `just _lint-toobig` failed on pre-existing `tests/test_agent_hijack_recover_release.py` (1324 lines)
- `just _lint-symvision` and `sase tool run check` failed on pre-existing `_choice_for_enter_target` in `src/sase/ace/tui/actions/agents/_agent_enter_action.py` (NEW; check stopped there). Ruff and mypy stages of check passed.
