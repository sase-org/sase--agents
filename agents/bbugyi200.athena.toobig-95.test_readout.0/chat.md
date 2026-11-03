# Chat History - ace-run (toobig-95.test_readout.0)

- **TIMESTAMP:** 2026-11-03 09:17:25 EST
- **MODEL:** muse/muse-spark-1.3-contributor
- **AGENT:** toobig-95.test_readout.0

## Prompt

%id(test_readout.0, clan=toobig-95)
%model:@medium
%auto
%queue(capacity=5)
#gh:gh_sase-org__sase Can you help me split the `tests/instructions/test_readout.py` file into multiple files? Use your best
%wait:toobig-95.readout.0
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

Split done. All 32 tests pass in their new homes.

New files, each under 500 lines:
- [test_readout.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/tests/instructions/test_readout.py) (98 lines): facade with `__test__ = False`, re-exports `RUN_START`, `RUN_END` and all 32 `test_*` names.
- [_readout_support.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/tests/instructions/_readout_support.py) (68 lines): public `HANDOFF_PHASE`, `RUN_START`, `RUN_END`, `write_meta`, `write_done`, `passthrough_manifest_normalize`.
- [test_readout_cli.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/tests/instructions/test_readout_cli.py), [test_readout_classify.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/tests/instructions/test_readout_classify.py), [test_readout_build.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/tests/instructions/test_readout_build.py), [test_readout_staged.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/tests/instructions/test_readout_staged.py), [test_readout_adapter.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/tests/instructions/test_readout_adapter.py).

No `_`-prefixed imports across the new modules. Shared helpers live as public names in the private support module. Single-use helpers (`_make_run`, staged writers) live in their home module.

Verification:
- `just _lint-symvision`: pass.
- `just _lint-mypy`: pass, 6363 files clean.
- `just _lint-toobig`: pass, split files all ≤226 lines.
- `sase tool run check`: succeeded.
