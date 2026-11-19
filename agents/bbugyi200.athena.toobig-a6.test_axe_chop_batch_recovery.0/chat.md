# Chat History - ace-run (toobig-a6.test_axe_chop_batch_recovery.0)

- **TIMESTAMP:** 2026-11-18 21:48:28 EST
- **MODEL:** muse/muse-spark-1.3-contributor
- **AGENT:** toobig-a6.test_axe_chop_batch_recovery.0

## Prompt

%id(test_axe_chop_batch_recovery.0, clan=toobig-a6)
%model:@medium
%auto
%queue(capacity=5)
#gh:gh_sase-org__sase Can you help me split the `tests/axe/test_axe_chop_batch_recovery.py` file into multiple files? Use your best
%wait:toobig-a6.test_agents_bead_warmup.0
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

Split `tests/axe/test_axe_chop_batch_recovery.py` (1203 lines) into 5 files, all under 500 lines:

* [facade](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/tests/axe/test_axe_chop_batch_recovery.py:1) (81 lines) – re-exports 29 tests + `isolated_home`, sets `__test__ = False`, `__all__` lists public names only, no `_private` re-exports.
* [cancel](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/tests/axe/test_axe_chop_batch_recovery_cancel.py:1) (442 lines) – stop signal, pending, clan cancel, generation gating, typed cancel, dead-executor, rust matching.
* [notices](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/tests/axe/test_axe_chop_batch_recovery_notices.py:1) (358 lines) – holds, notice delivery, claims, bounded failure, dry-run.
* [observations](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/tests/axe/test_axe_chop_batch_recovery_observations.py:1) (368 lines) – spawn observations, strict holds, replay.
* [shared](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/tests/axe/_test_axe_chop_batch_recovery_shared.py:1) (144 lines) – private module with public helpers `manifest`, `record_spawn`, `replay_manifest`, and `recovery_isolated_home` fixture (`@pytest.fixture(name="isolated_home")` to avoid F811).

No `_`-prefixed imports across new modules; `src` private imports (`_chop_batch_recovery_*`) kept verbatim to preserve monkeypatch targets. Local `manifest` variables renamed to `batch` to avoid shadowing.

Verification observed:

* `just _lint-symvision` – pass.
* `just _lint-mypy` – pass (6624 files).
* `just _lint-toobig` – pass.
* Fixed `ruff` F811 (`isolated_home` redefinition, `CHOP_BATCH_SCHEMA_VERSION` unused top-level) in split files.
* `pytest` on 3 new modules + facade: 29 passed.
* `sase tool run check` (run `2c8038916cf1044576738432ebac83d4`) – verdict `pass`, 20/20 stages exit 0.

Declaration accepted; test split committed by host finalizer.
