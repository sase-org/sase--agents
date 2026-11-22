# Chat History - ace-run (toobig-ai.auto_refresh.0)

- **TIMESTAMP:** 2026-11-22 11:40:54 EST
- **MODEL:** grok/grok-4.6
- **AGENT:** toobig-ai.auto_refresh.0

## Prompt

%id:toobig-ai.auto_refresh.0
%clan(toobig-ai, tribe=chop, summary=[[[bold #D75FFF]◆ TOOBIG SPLIT · 3 FILES[/bold #D75FFF]
[bold #87D7FF]MISSION[/bold #87D7FF]
[dim #D7D7FF]Decompose oversized Python modules into focused, reviewable units[/dim #D7D7FF]
[dim #D7D7FF]without changing behavior.[/dim #D7D7FF]

[bold #87D7FF]TARGETS[/bold #87D7FF]
[#87D7FF]• 841  tests/tool/test_admission.py[/#87D7FF]
[#87D7FF]• 751  tests/ace/tui/test_machine_capacity_report_feed.py[/#87D7FF]
[#87D7FF]• 736  src/sase/ace/tui/actions/event_refresh/_auto_refresh.py[/#87D7FF]

[dim #A8A8A8]2 scan roots · limits 1,000 / 850 / 700 lines · sequential queue[/dim #A8A8A8]]])
%model:@medium
%auto
%queue(capacity=5)
#gh:gh_sase-org__sase Can you help me split the `src/sase/ace/tui/actions/event_refresh/_auto_refresh.py` file into multiple files? Use your best
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

I'll start by reading the ACE and lint memory, then inspect the auto-refresh module and its tests so the split keeps public imports and monkeypatch targets working.

The auto-refresh module is 736 lines; I’ll read it and the existing split siblings to match that package’s import pattern.

I'll split capacity signatures, probe, and install into private modules, then keep `_auto_refresh.py` as a facade so public imports and monkeypatch targets stay intact.

Probe currently calls install methods, which will fail mypy. I’ll move the feed timer onto the install mixin and share the poll interval as a public name.

The split is in place and all cross-module imports use public names. Next I’ll run the three requested lints.

Symvision, mypy, and toobig all passed. I’ll run `sase tool run check` next.

Docs-lint failed on an unrelated word-budget error in `notification-gates.md`. I’ll run the auto-refresh tests the split actually affects.

The scoped suite escalated and reported several failures. I’ll inspect the ones that could come from the split, especially audit and timezone guards.

The remaining test failures are outside the split. I’ll collect git status and the finalizer context so we can declare.

Split `_auto_refresh.py` (736 lines) into four modules, all under 500 lines.

**Layout**
- `_auto_refresh.py` (108) — facade: `EventAutoRefreshMixin` plus `_CapacityReportFeedMixin` for the original import path
- `_auto_refresh_capacity_signatures.py` (76) — shared public helpers (`freeze_capacity_value`, `capacity_override_fingerprint`, `CAPACITY_REPORT_POLL_SECONDS`)
- `_auto_refresh_capacity_probe.py` (209) — token/hold/liveness revalidation
- `_auto_refresh_capacity.py` (385) — coalesced refresh, install, telemetry

Public imports stay on `sase.ace.tui.actions.event_refresh._auto_refresh`. Tests still import `_CapacityReportFeedMixin` and `EventAutoRefreshMixin` from that module. Cross-module imports use public names only.

**Verification**
- `just _lint-symvision`, `just _lint-mypy`, and `just _lint-toobig` passed
- Capacity-feed tests passed (20/20 in `test_machine_capacity_report_feed.py`)
- `sase tool run check` failed on an unrelated docs-contract word-budget error in `docs/reference/automation/notification-gates.md`

`just test-scoped` escalated to the full suite (`core-identity-changed` from a sase-core rebuild) and showed other failures outside this split, including a pre-existing `AttributeError` in `test_settled_monitor_replay_converges_after_index_upsert` (`_PreparedApplyHarness` missing `_agents_token_reload_kind`).
