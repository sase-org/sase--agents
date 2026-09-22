# Chat History - ace-run (toobig-5r.test_workspace_lease.0)

- **TIMESTAMP:** 2026-09-22 03:25:43 EDT
- **MODEL:** muse/muse-spark-1.3-contributor
- **AGENT:** toobig-5r.test_workspace_lease.0

## Prompt

%id(test_workspace_lease.0, clan=toobig-5r)
%model:@medium
%auto
%queue(capacity=3)
#gh:gh_sase-org__sase Can you help me split the `tests/workspace_provider/test_workspace_lease.py` file up into multiple files? Use your best
%wait:toobig-5r.test_visual_capture.0
judgement, but let's aim to keep all files <=500 lines of code.

## Response

Done. Split the 794-line `tests/workspace_provider/test_workspace_lease.py` into three focused files, all under 500 lines:

- [test_workspace_lease_acquire.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_25/tests/workspace_provider/test_workspace_lease_acquire.py) (380 lines) — `TestAuthorizeOperationalLeaseWorkspace` + `TestAcquireAndContextManager`
- [test_workspace_lease_submit.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_25/tests/workspace_provider/test_workspace_lease_submit.py) (253 lines) — `TestDurableSubmission` + `TestSettlement`
- [test_workspace_lease_prepare.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_25/tests/workspace_provider/test_workspace_lease_prepare.py) (226 lines) — `TestPrepareFromRemote` + `_init_git`

Each file is self-contained with only the fixture helpers it needs (matching the existing `test_utils_*` split convention — no shared helper module). Also updated the stale ``test_workspace_lease.py`` docstring reference in `test_ownership_invariant_audit.py`.

Verification: all 27 tests preserved verbatim (confirmed identical test-name sets), 29 passed via direct pytest run, and `sase tool run check` succeeded (all lint gates including toobig, plus the scoped test lane).
