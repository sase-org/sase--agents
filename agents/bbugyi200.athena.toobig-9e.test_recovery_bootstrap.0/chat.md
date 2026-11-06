# Chat History - ace-run (toobig-9e.test_recovery_bootstrap.0)

- **TIMESTAMP:** 2026-11-05 23:06:41 EST
- **MODEL:** muse/muse-spark-1.3-contributor
- **AGENT:** toobig-9e.test_recovery_bootstrap.0

## Prompt

%auto
%id(test_recovery_bootstrap.0, clan=toobig-9e)
%model:@medium
%queue(capacity=5)
#gh:gh_sase-org__sase Can you help me split the `tests/agent/test_recovery_bootstrap.py` file into multiple files? Use your best
%wait:toobig-9e.recovery_successor.0
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

Split complete.

- New [shared fixtures](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_23/tests/agent/_recovery_bootstrap_shared.py) with public `lineage`, `descriptor`, `write_meta`, `write_baseline`.
- New [enforce tests](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_23/tests/agent/test_recovery_bootstrap_enforce.py) (417 lines): `TestDescriptorRoundTrip`, `TestEnforceSuccess`, `TestEnforceFailures`.
- New [gather tests](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_23/tests/agent/test_recovery_bootstrap_gather.py) (320 lines): `TestCollectObservation`, `TestParentSideProof`, `TestVersionedAck`, `TestLineageKeys`, `TestStrictBootstrapEntry`.
- [Facade](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_23/tests/agent/test_recovery_bootstrap.py) (41 lines) re-exports all 8 test classes with `__test__ = False`.

Verified: 39 split tests pass, facade imports but collects 0. `just _lint-symvision`, `just _lint-mypy`, `just _lint-toobig` all exit 0. `sase tool run check` run `c057e535f5dd945a64e7086eea470cab` verdict pass.
