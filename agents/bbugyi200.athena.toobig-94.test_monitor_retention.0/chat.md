# Chat History - ace-run (toobig-94.test_monitor_retention.0)

- **TIMESTAMP:** 2026-11-02 20:28:34 EST
- **MODEL:** muse/muse-spark-1.3-contributor
- **AGENT:** toobig-94.test_monitor_retention.0

## Prompt

%id(test_monitor_retention.0, clan=toobig-94)
%model:@medium
%auto
%queue(capacity=5)
#gh:gh_sase-org__sase Can you help me split the `tests/monitor/test_monitor_retention.py` file into multiple files? Use your best
%wait:toobig-94.workspace_retention.0
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

Split done. All gates pass.

Files:
- [test_monitor_retention.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/tests/monitor/test_monitor_retention.py) is now a 58-line facade (`__test__ = False`, re-exports 19 public tests).
- [test_monitor_retention_settlement.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/tests/monitor/test_monitor_retention_settlement.py) (359 lines): stopped/lost/failed/degraded/blocked/successor cases.
- [test_monitor_retention_lifecycle.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/tests/monitor/test_monitor_retention_lifecycle.py) (368 lines): completion, idempotency, resume, stale/proc/baseline/uncertainty/binding cases.
- [_retention_fixtures.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/tests/monitor/_retention_fixtures.py) (126 lines): shared public helpers (`RETENTION_CLAIM_WORKFLOW`, `init_retention_repo`, `make_retention_monitor`, `read_retention_meta`, `write_retention_meta`, `retention_record`, `no_launch_followup`).

No `_`-prefixed imports cross test modules. Single-use helpers stayed private in-file (`_failed_launch`/`_degraded_launch` in settlement, `_write_monitor_baselines` in lifecycle). Monkeypatch targets unchanged (production paths only).

Verification: `just _lint-symvision`, `just _lint-mypy`, `just _lint-toobig` each exit 0; retention tests 21 passed; `sase tool run check` succeeded.

Declaration submitted for the monitor retention split; host will commit after this turn.
