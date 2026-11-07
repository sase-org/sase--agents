# Chat History - ace-run (toobig-9m.agent_artifact_run_trash.0)

- **TIMESTAMP:** 2026-11-07 04:57:56 EST
- **MODEL:** grok/grok-4.6
- **AGENT:** toobig-9m.agent_artifact_run_trash.0

## Prompt

%id(agent_artifact_run_trash.0, clan=toobig-9m)
%model:@medium
%auto
%queue(capacity=5)
#gh:gh_sase-org__sase Can you help me split the `src/sase/core/agent_artifact_run_trash.py` file into multiple files? Use your best
%wait:toobig-9m.hijack_recovery_panel.0
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

I'll start by reading the split target, the lint/test notes, and the current module structure so the new files stay under 500 lines without changing behavior.

The file is large, so I'll read the rest of it in chunks and pull the lint notes at the same time.

I'll look at similar package splits and at tests that import or monkeypatch this module so the public path stays intact.

I have a split plan: models, quarantine, list/restore/purge ops, a private shared helpers module, and a public facade. Next I’ll add those files and keep the original import path.

All new modules are under 500 lines. Next I’ll inspect the formatter change, then run the three linters.

Symvision passed. Next I’ll run mypy, then the toobig line-count gate.

The three linters passed. I’ll glance at the formatted helpers, then run `sase tool run check`.

Check failed on a test-waits lint in a file I didn’t split. I’ll inspect that failure and confirm whether it’s pre-existing.

The red check is an unrelated test-waits lint. I’ll file that as a task bead and run the split’s tests so the refactor is still verified.

The missing pragma is in the live Agent Hijack epic’s new e2e test, so I’ll record it there instead of opening a new task.

Split `src/sase/core/agent_artifact_run_trash.py` (807 lines) into five modules, each under 500 lines. The original public import path still works.

- `agent_artifact_run_trash.py` — facade that re-exports public names only
- `agent_artifact_run_trash_models.py` — wire dataclasses and schema version
- `agent_artifact_run_trash_quarantine.py` — `quarantine_ace_runs`
- `agent_artifact_run_trash_ops.py` — list, restore, and purge
- `_agent_artifact_run_trash_shared.py` — shared helpers with public names (`run_trash_root`, `call_run_trash_binding`, `require_run_trash_wire_schema`, `normalized_dir`)

Helpers used by only one module stayed private in that module. No `_`-prefixed names are imported across files. Tests still import public names from the facade; no monkeypatch retargets were needed.

Verification:
- `just _lint-symvision`, `just _lint-mypy`, and `just _lint-toobig` all passed
- 36 tests covering the trash module, prune-runs CLI, and core-rs validator passed
- `sase tool run check` stopped at an unrelated `lint (test waits)` failure: `tests/fakey/test_agent_hijack_e2e.py:105` is missing a `# sase-test-wait:` pragma. That file is from the Agent Hijack e2e coverage, not this split. I recorded it as a discovered issue on epic `sase-1qz`.
