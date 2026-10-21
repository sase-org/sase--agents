# Chat History - ace-run (toobig-8d.test_git_sync_outbox.0)

- **TIMESTAMP:** 2026-10-21 08:55:06 EDT
- **MODEL:** muse/muse-spark-1.3-contributor
- **AGENT:** toobig-8d.test_git_sync_outbox.0

## Prompt

%auto
%id(test_git_sync_outbox.0, clan=toobig-8d)
%model:@medium
%queue(capacity=5)
#gh:gh_sase-org__sase Can you help me split the `tests/agents_sync/test_git_sync_outbox.py` file into multiple files? Use your best
%wait:toobig-8d.grok.0
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

Done. Split the 867-line `tests/agents_sync/test_git_sync_outbox.py` into a 5-file package, all files ≤500 lines:

- [test_sync.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/tests/agents_sync/test_git_sync_outbox/test_sync.py) (300 lines) — full-sync isolation, acknowledgement, and drop-retired tests (5 tests)
- [test_retry_retired.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/tests/agents_sync/test_git_sync_outbox/test_retry_retired.py) (364 lines) — retry-retired tests (7 tests), with the single-use `_stub_mocked_sync` moved into it
- [test_bounded_retry.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/tests/agents_sync/test_git_sync_outbox/test_bounded_retry.py) (237 lines) — bounded-retry tests (2 tests)
- [_helpers.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/tests/agents_sync/test_git_sync_outbox/_helpers.py) (23 lines) — shared helper as public `retire_publication` (was `_retire`)
- [__init__.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/tests/agents_sync/test_git_sync_outbox/__init__.py) (46 lines) — facade re-exporting all 14 public tests, preserving the original import path

No `_`-prefixed name is imported across modules, and the facade re-exports only public names. Monkeypatch targets are unchanged, so no retargeting was needed.

Verification: all 14 tests pass in the new layout, `just _lint-symvision`, `just _lint-mypy`, and `just _lint-toobig` each pass with no touched-file issues, and `sase tool run check` succeeded (run `ea97bc122fc6015a9313ca4e8ef7507a`).

Declaration submitted: commit for the `test_git_sync_outbox` split package.
