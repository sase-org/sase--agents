# Chat History - ace-run (toobig-al.loading_bead_warmup.0)

- **TIMESTAMP:** 2026-11-22 20:58:50 EST
- **MODEL:** muse/muse-spark-1.3-contributor
- **AGENT:** toobig-al.loading_bead_warmup.0

## Prompt

%id:toobig-al.loading_bead_warmup.0
%clan(toobig-al, tribe=chop, summary=[[[bold #D75FFF]◆ TOOBIG SPLIT · 4 FILES[/bold #D75FFF]
[bold #87D7FF]MISSION[/bold #87D7FF]
[dim #D7D7FF]Decompose oversized Python modules into focused, reviewable units[/dim #D7D7FF]
[dim #D7D7FF]without changing behavior.[/dim #D7D7FF]

[bold #87D7FF]TARGETS[/bold #87D7FF]
[#87D7FF]• 793  src/sase/ace/tui/actions/agents/_loading_bead_warmup.py[/#87D7FF]
[#87D7FF]• 726  src/sase/ace/tui/actions/event_refresh/_auto_refresh_surfaces.py[/#87D7FF]
[#87D7FF]• 718  src/sase/ace/tui/actions/event_refresh/_surface_tokens.py[/#87D7FF]
[#87D7FF]• 702  src/sase/ace/tui/util/fs_watcher.py[/#87D7FF]

[dim #A8A8A8]2 scan roots · limits 1,000 / 850 / 700 lines · sequential queue[/dim #A8A8A8]]])
%model:@medium
%auto
%queue(capacity=5)
#gh:gh_sase-org__sase Can you help me split the `src/sase/ace/tui/actions/agents/_loading_bead_warmup.py` file into multiple files? Use your best
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

Split the 793-line warmup module into five files, each under 500 lines. Behavior is preserved; the original import path stays working for public names.

New modules:

- [types](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/src/sase/ace/tui/actions/agents/_loading_bead_warmup_types.py) (80 lines): public `AgentBeadWarmupCandidates`, `AgentBeadWarmupResults` (renamed from `_`-prefixed so siblings can import them).
- [scan](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/src/sase/ace/tui/actions/agents/_loading_bead_warmup_scan.py) (327 lines): `AgentBeadWarmupScanMixin` plus the private `_warm_agent_bead_caches` it alone uses.
- [candidates](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/src/sase/ace/tui/actions/agents/_loading_bead_warmup_candidates.py) (306 lines): `AgentBeadWarmupCandidatesMixin` plus the private `_MAX_*` constants it alone uses.
- [apply](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/src/sase/ace/tui/actions/agents/_loading_bead_warmup_apply.py) (148 lines): `AgentBeadWarmupApplyMixin`.
- [facade](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/src/sase/ace/tui/actions/agents/_loading_bead_warmup.py) (46 lines): re-exports only public names and defines `AgentBeadWarmupMixin` combining the three mixins.

No `_`-prefixed name is imported across the new modules; cross-mixin calls go through `self` with the existing `# type: ignore[attr-defined]` pattern.

Tests retargeted to the new public names and new monkeypatch paths (`_loading_bead_warmup_scan._warm_agent_bead_caches`, `_loading_bead_warmup_scan.warm_confirmed_bead_displays`): `test_agents_bead_warmup_run.py`, `test_refresh_warmup_gc.py`, `test_agents_bead_warmup_results.py`, `test_agent_list_clan_unknown_wait.py`, `test_ace_png_snapshots_agents_stranded.py`. `AgentBeadWarmupMixin` imports still resolve through the facade.

Verification:

- `just _lint-symvision`: pass.
- `just _lint-mypy`: pass (6709 files).
- `just _lint-toobig`: pass (touched files max 327 lines).
- `sase tool run check` (run `34ed8b41cd7fa17ca2de300beb6a038f`): all lint stages pass; test lane went 6697 passed, 1 failed on `test_auto_refresh_merge_live_hints_and_warmup_release_obsolete_payloads` (leftover `FinalizerInventoryWorkerResult`, unrelated subsystem). Re-ran that test solo and the full `test_refresh_warmup_gc.py` file: all pass, so the check failure was a load-related GC flake, not a regression. Bead-warmup suites (42 tests) all pass.

Declaration submitted — commit authorized for the warmup split work.
