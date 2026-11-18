# Chat History - ace-run (toobig-a2.chop_proposal_launch_impl.0)

- **TIMESTAMP:** 2026-11-18 09:07:55 EST
- **MODEL:** muse/muse-spark-1.3-contributor
- **AGENT:** toobig-a2.chop_proposal_launch_impl.0

## Prompt

%id(chop_proposal_launch_impl.0, clan=toobig-a2)
%model:@medium
%auto
%queue(capacity=5)
#gh:gh_sase-org__sase Can you help me split the `src/sase/axe/chop_proposal_launch_impl.py` file into multiple files? Use your best
%wait:toobig-a2.chop_batch_recovery.0
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

Done. Split the 1,170-line `src/sase/axe/chop_proposal_launch_impl.py` into five private modules plus a thin facade, every file at 500 lines or fewer.

New modules (all under `src/sase/axe/`):

- [`_chop_proposal_launch_shared.py`](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_22/src/sase/axe/_chop_proposal_launch_shared.py) (131 lines) — public `ordinary_batch_manifest`, `query_for_plans`, `wait_names_by_proposal_index`, each needed by two consumers.
- [`_chop_proposal_launch_typed_metadata.py`](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_22/src/sase/axe/_chop_proposal_launch_typed_metadata.py) (187 lines) — public `unit_dispatch_metadata`, `unit_dispatch_metadata_from_payload`, `typed_admission_record`; single-file-private helpers stayed private.
- [`_chop_proposal_launch_typed_dispatch.py`](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_22/src/sase/axe/_chop_proposal_launch_typed_dispatch.py) (353 lines) — public `maybe_dispatch_typed_chop_proposals`; typed-only helpers moved into it.
- [`_chop_proposal_launch_journal.py`](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_22/src/sase/axe/_chop_proposal_launch_journal.py) (372 lines) — public `OrdinaryLaunchJournal` class holding the batch-journal closures' state; `_launch_descriptor` stayed private inside it.
- [`_chop_proposal_launch_runner.py`](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_22/src/sase/axe/_chop_proposal_launch_runner.py) (262 lines) — public `launch_chop_proposals`, unchanged signature and behavior.
- [`chop_proposal_launch_impl.py`](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_22/src/sase/axe/chop_proposal_launch_impl.py) (12 lines) — facade re-exporting only the public `launch_chop_proposals`, so the original import path and all monkeypatch targets keep working; no test retargeting needed.

Constraints honored: no `_`-prefixed name is imported across the new modules, and the facade re-exports no private names.

Verification, all observed this session: `just _lint-symvision` passed, `just _lint-mypy` passed (no issues in 6598 files), `just _lint-toobig` passed (remaining warnings are in pre-existing untouched files), ruff format applied to one file, the 18 tests in the four chop-launch test files passed, and `sase tool run check` finished with STATE succeeded, exit 0.

Declaration submitted. Split work committed via host finalizer.
