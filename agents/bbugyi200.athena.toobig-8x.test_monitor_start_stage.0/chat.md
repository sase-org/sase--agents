# Chat History - ace-run (toobig-8x.test_monitor_start_stage.0)

- **TIMESTAMP:** 2026-10-31 03:36:06 EDT
- **MODEL:** grok/grok-4.6
- **AGENT:** toobig-8x.test_monitor_start_stage.0

## Prompt

%id(test_monitor_start_stage.0, clan=toobig-8x)
%model:@medium
%auto
%queue(capacity=5)
#gh:gh_sase-org__sase Can you help me split the `tests/monitor/test_monitor_start_stage.py` file into multiple files? Use your best
%wait:toobig-8x.agent_loader_artifacts.0
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

I'll split `tests/monitor/test_monitor_start_stage.py` into modules of 500 lines or fewer while preserving behavior and public imports. First I'll read the file, lint notes, and the split conventions.

I'll read the lint notes and look at how nearby test files were split so this one follows the same pattern.

I'll scan the rest of the test file and nearby split patterns so the new modules match the project's conventions.

I have the split: shared public helpers in `_start_stage.py`, three themed test modules, and a facade that keeps the original import path. Next I’ll write those files.

The helper rename collided with `identical_request`. I'll redo the extraction with word-boundary replacements.

All three lints and `sase tool run check` passed. I'll gather the finalizer context and submit the declaration.

Split `tests/monitor/test_monitor_start_stage.py` (1163 lines) into modules of 500 lines or fewer, with the original import path kept as a facade.

**Layout**
- `tests/monitor/_start_stage.py` (237) — shared builders with public names (`stage_env`, `stage_request`, `sandbox_home`, …)
- `tests/monitor/test_monitor_start_stage_adopt.py` (401) — checkpoint freeze, adoption, persist/replay, workspace pinning
- `tests/monitor/test_monitor_start_stage_prepared.py` (339) — prepared-completion bind/rollback and finalizer wait
- `tests/monitor/test_monitor_start_stage_cleanup.py` (318) — held cleanup, join consume, ack rollback, launch
- `tests/monitor/test_monitor_start_stage.py` (68) — facade that re-exports public test names and `SANDBOX_CATALOG` (`__test__ = False` so pytest collects each test once)

Helpers used by more than one module live as public names in the already-private `_start_stage.py`. No `_`-prefixed names are imported across the new modules. Monkeypatch targets stay on production modules.

**Verification**
- `just _lint-symvision` — pass
- `just _lint-mypy` — pass
- `just _lint-toobig` — pass
- `sase tool run check` — succeeded (`74b77c87ecbb1d044007a63cb17b13e0`)
