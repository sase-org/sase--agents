# Chat History - ace-run (toobig-9v.run_agent_exec_staged_dispatch.0)

- **TIMESTAMP:** 2026-11-16 16:06:21 EST
- **MODEL:** grok/grok-4.6
- **AGENT:** toobig-9v.run_agent_exec_staged_dispatch.0

## Prompt

%auto
%id(run_agent_exec_staged_dispatch.0, clan=toobig-9v)
%model:@medium
%queue(capacity=5)
#gh:gh_sase-org__sase Can you help me split the `src/sase/axe/run_agent_exec_staged_dispatch.py` file into multiple files? Use your best
%wait:toobig-9v.latch.0
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

I'll split `run_agent_exec_staged_dispatch.py` into smaller modules while preserving the public import path. First I'll read the file, the lint notes, and the split conventions.

I'll read the source, nearby split facades, and the lint notes so the new modules match existing conventions.

The source is 739 lines, so I’ll map its functions, public surface, and test monkeypatches before choosing the split.

I'll inspect related modules, the toobig limit, and a recent split so the new layout matches the rest of this package.

I'll keep dispatch on the original module so monkeypatches still work, move retention into `run_agent_exec_staged_retention.py`, and extract already-adopted replay plus the shared dispatch type.

I'll add the shared type, extract replay and retention, and slim the original dispatch module.

Imports load cleanly and every file is under 500 lines. Next I’ll run the three requested lints on the split.

Symvision and mypy passed. The toobig failure is in an unrelated test file the split did not touch. I’ll format, then run the full check.

The check is still running after 20 minutes. I’ll inspect progress and keep waiting.

The check reported no new failures: 10 KNOWN and 1 FLAKY, all outside the split. I’ll confirm the staged-dispatch tests passed.

Split `src/sase/axe/run_agent_exec_staged_dispatch.py` (739 lines) into focused modules, all under 500 lines. The original import path still works.

**Layout**
- `run_agent_exec_staged_dispatch.py` (402) — still owns `dispatch_completed_staged_handoff` and re-exports `retain_failed_adoption_workspace`, so existing monkeypatches keep working
- `run_agent_exec_staged_dispatch_replay.py` (106) — `already_adopted_dispatch`
- `run_agent_exec_staged_retention.py` (341) — `retain_failed_adoption_workspace` now lives with dead-origin settlement
- `_run_agent_exec_staged_shared.py` (103) — shared public `StagedHandoffDispatch`

No `_`-prefixed names are imported across modules.

**Verification**
- `just _lint-symvision` — pass
- `just _lint-mypy` — pass
- `just _lint-toobig` — our files are fine; the gate still fails on unrelated `tests/ace/tui/test_agent_hijack_action.py` (1092 lines)
- `sase tool run check` — `no_new_failures` (10 KNOWN, 1 FLAKY archive/corpus tests, none from this split)
