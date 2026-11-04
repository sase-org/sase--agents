# Chat History - ace-run (toobig-9a.test_workspace_lease_prepare.0)

- **TIMESTAMP:** 2026-11-04 11:36:11 EST
- **MODEL:** muse/muse-spark-1.3-contributor
- **AGENT:** toobig-9a.test_workspace_lease_prepare.0

## Prompt

%id:toobig-9a.test_workspace_lease_prepare.0
%clan(toobig-9a, tribe=chop, summary=[[[bold #D75FFF]◆ TOOBIG SPLIT · 1 FILE[/bold #D75FFF]
[bold #87D7FF]MISSION[/bold #87D7FF]
[dim #D7D7FF]Decompose oversized Python modules into focused, reviewable units[/dim #D7D7FF]
[dim #D7D7FF]without changing behavior.[/dim #D7D7FF]

[bold #87D7FF]TARGETS[/bold #87D7FF]
[#87D7FF]• 722  tests/workspace_provider/test_workspace_lease_prepare.py[/#87D7FF]

[dim #A8A8A8]2 scan roots · limits 1,000 / 850 / 700 lines · sequential queue[/dim #A8A8A8]]])
%model:@medium
%auto
%queue(capacity=5)
#gh:gh_sase-org__sase Can you help me split the `tests/workspace_provider/test_workspace_lease_prepare.py` file into multiple files? Use your best
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

Split complete. The 722-line module is now a 29-line facade plus four private modules, all under 500 lines:

- [test_workspace_lease_prepare.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_13/tests/workspace_provider/test_workspace_lease_prepare.py) (29 lines): facade re-exporting `TestPrepareFromRemote`, `TestPrepareFromRemoteTransport`, `TestLeasePrepareRescue`, and the public `OperationalLeaseError` alias.
- [_workspace_lease_prepare_helpers.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_13/tests/workspace_provider/_workspace_lease_prepare_helpers.py) (150 lines): public shared builders `make_fake_git`, `prepared_lease_checkout`, `plant_index_lock`, `init_git` plus `PUBLICKEY_DENIAL` / `CONNECTION_RESET` constants.
- [_workspace_lease_prepare_credential.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_13/tests/workspace_provider/_workspace_lease_prepare_credential.py) (243 lines): `TestPrepareFromRemote` with the missing-git-dir and credential-remediation tests.
- [_workspace_lease_prepare_transport.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_13/tests/workspace_provider/_workspace_lease_prepare_transport.py) (224 lines): new `TestPrepareFromRemoteTransport` with transport/timeout/fast-forward/lock tests.
- [_workspace_lease_prepare_rescue.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_13/tests/workspace_provider/_workspace_lease_prepare_rescue.py) (157 lines): `TestLeasePrepareRescue` unchanged apart from the helper import.

No `_private` name crosses the new modules; monkeypatch string targets on `sase.*` are untouched.

Verification: `just _lint-symvision`, `just _lint-mypy`, and `just _lint-toobig` each exit 0; targeted pytest runs 27 passed; `sase tool run check` (run `8d4c49a8ccb6b659fa583790be885a46`) succeeded.

Declaration accepted for `commit`.
