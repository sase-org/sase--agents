# Chat History - ace-run (toobig-9f.test_agent_hijack_recovery_transaction.0)

- **TIMESTAMP:** 2026-11-05 23:50:23 EST
- **MODEL:** muse/muse-spark-1.3-contributor
- **AGENT:** toobig-9f.test_agent_hijack_recovery_transaction.0

## Prompt

%id(test_agent_hijack_recovery_transaction.0, clan=toobig-9f)
%model:@medium
%auto
%queue(capacity=5)
#gh:gh_sase-org__sase Can you help me split the `tests/test_agent_hijack_recovery_transaction.py` file into multiple files? Use your best
%wait:toobig-9f.recover_confirm.0
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

Split done. The 844-line `tests/test_agent_hijack_recovery_transaction.py` is now four files, each under 500 lines:

- [facade](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_23/tests/test_agent_hijack_recovery_transaction.py) (39 lines) — re-exports all 11 public `test_*` functions with `__test__ = False`, so the original import path works with no double collection.
- [support](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_23/tests/_agent_hijack_recovery_transaction_support.py) (423 lines) — public `Transaction` fixture plus public `parent_done`, needed by both test modules.
- [launch tests](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_23/tests/test_agent_hijack_recovery_transaction_launch.py) (123 lines) — continue, escalate, instruct, with private `_ack_for`.
- [resilience tests](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_23/tests/test_agent_hijack_recovery_transaction_resilience.py) (303 lines) — races, crash resume, uncertain dispatch, refusals, settlement replay, with private `_disable_provider`.

No `_`-prefixed name is imported across the new modules. Monkeypatch targets are unchanged (same `src` module objects patched).

Verification: 11 passed via pytest; `just _lint-symvision`, `just _lint-mypy`, and `just _lint-toobig` all pass; `sase tool run check` passed with verdict `pass` (exit 0).
