# Chat History - ace-run (toobig-ae.test_artifact_protection_scan.0)

- **TIMESTAMP:** 2026-11-20 21:34:45 EST
- **MODEL:** muse/muse-spark-1.3-contributor
- **AGENT:** toobig-ae.test_artifact_protection_scan.0

## Prompt

%id(test_artifact_protection_scan.0, clan=toobig-ae)
%model:@medium
%auto
%queue(capacity=5)
#gh:gh_sase-org__sase Can you help me split the `tests/test_artifact_protection_scan.py` file into multiple files? Use your best
%wait:toobig-ae.agent_artifact_run_retention.0
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

Done. Split the 737-line test module into 4 focused modules plus a shared helper, with the original kept as a re-export facade.

New and rewritten files (all ≤500 lines, max 243):

- [shared helpers](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_17/tests/_artifact_protection_scan_helpers.py) (37 lines): public `make_repo_record()` for the formerly private `_record()`.
- [bead tests](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_17/tests/test_artifact_protection_scan_beads.py) (243 lines): collection plus 3 bead-projection tests.
- [sidecar tests](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_17/tests/test_artifact_protection_scan_sidecars.py) (216 lines): 5 availability and managed/unmanaged tests.
- [consumption tests](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_17/tests/test_artifact_protection_scan_consumption.py) (222 lines): 3 ledger tests plus the link-aggregate test.
- [scanning tests](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_17/tests/test_artifact_protection_scan_scanning.py) (108 lines): `_scan_root` and `_extract_artifact_ids` unit tests.
- [facade](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_17/tests/test_artifact_protection_scan.py) (55 lines): re-exports all 17 `test_*` names with `__test__ = False` and sorted `__all__`; no `_private` re-exports.

Rules followed: new modules share only the public `make_repo_record` from the already-private helpers file; nothing imports a `_`-prefixed name defined in another new module; `_mark_managed_project` stays imported only by the one module that needs it; monkeypatch target strings were left unchanged.

Verified: `just _lint-symvision`, `just _lint-mypy`, and `just _lint-toobig` each exit 0 (toobig no longer flags the file); fixed one `ruff format` issue in the sidecars module; `pytest` on the 4 split modules passes 17 tests with no double-collection through the facade; `sase tool run check` succeeds (run `13e701a4`, ~409s).

Declared the test split for host commit.
