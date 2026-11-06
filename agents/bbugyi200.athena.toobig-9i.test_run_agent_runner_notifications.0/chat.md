# Chat History - ace-run (toobig-9i.test_run_agent_runner_notifications.0)

- **TIMESTAMP:** 2026-11-06 12:47:55 EST
- **MODEL:** grok/grok-4.6
- **AGENT:** toobig-9i.test_run_agent_runner_notifications.0

## Prompt

%id(test_run_agent_runner_notifications.0, clan=toobig-9i)
%model:@medium
%auto
%queue(capacity=5)
#gh:gh_sase-org__sase Can you help me split the `tests/test_run_agent_runner_notifications.py` file into multiple files? Use your best
%wait:toobig-9i.test_agent_publication_recovery.0
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

I'll split `tests/test_run_agent_runner_notifications.py` into files of 500 lines or fewer while preserving public imports and test behavior. First I'll read the lint/test rules and the current module.

The file is 706 lines, so I’ll look at recent test splits and the toobig gate to match existing conventions.

I'll split the module into three focused test files plus a facade that re-exports the public names. Helpers stay private in the file that uses them.

All public tests are re-exported and each file is under 500 lines. Next I’ll format, then run the three linters individually.

The three linters passed. Next I’ll run `sase tool run check`.

`sase tool run check` succeeded. I’ll load the finalizer context and submit the declaration.

Split `tests/test_run_agent_runner_notifications.py` into three focused modules plus a facade that keeps the original import path.

**Layout**
- `tests/test_run_agent_runner_notifications.py` (93 lines) — facade; re-exports public tests, `__test__ = False`
- `tests/test_run_agent_runner_notifications_flags.py` (338) — silent/tags/outcomes, payload, SDD notes
- `tests/test_run_agent_runner_notifications_identity.py` (215) — bead display and agent-session identity
- `tests/test_run_agent_runner_notifications_handoff.py` (179) — held staged-handoff notes

Helpers stay private in the file that uses them. The facade re-exports only public `test_*` names. Monkeypatch targets still point at production modules.

**Verification**
- `just _lint-symvision` — pass
- `just _lint-mypy` — pass
- `just _lint-toobig` — pass
- `sase tool run check` — succeeded
