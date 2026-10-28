# Chat History - ace-run (toobig-8q.snapshot_capture.0)

- **TIMESTAMP:** 2026-10-28 11:07:53 EDT
- **MODEL:** muse/muse-spark-1.3-contributor
- **AGENT:** toobig-8q.snapshot_capture.0

## Prompt

%auto
%id(snapshot_capture.0, clan=toobig-8q)
%model:@medium
%queue(capacity=5)
#gh:gh_sase-org__sase Can you help me split the `src/sase/workspace_provider/_snapshot_capture.py` file into multiple files? Use your best
%wait:toobig-8q.artifact_link_event_publish.0
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

Done. Split the 777-line `_snapshot_capture.py` into four files, each under 500 lines.

New layout in `src/sase/workspace_provider/`:

- [`_snapshot_capture.py`](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_13/src/sase/workspace_provider/_snapshot_capture.py) (24 lines) — facade re-exporting only the four public names.
- [`_snapshot_capture_source.py`](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_13/src/sase/workspace_provider/_snapshot_capture_source.py) (298 lines) — entry points, orchestration, and source-state reading.
- [`_snapshot_capture_payload.py`](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_13/src/sase/workspace_provider/_snapshot_capture_payload.py) (493 lines) — tree/pack/manifest capture with public `capture_into` and `publish_manifest`.
- [`_snapshot_capture_common.py`](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_13/src/sase/workspace_provider/_snapshot_capture_common.py) (13 lines) — shared `is_managed_sidecar_rel` used by both modules.

Also added public `DIR/FILE_OPERATION_MARKERS` aliases in [`_snapshot_model.py`](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_13/src/sase/workspace_provider/_snapshot_model.py) so the new modules never import `_`-prefixed names, and retargeted the five monkeypatch sites in `test_snapshot.py` to the module where each patched name is now looked up. Facade identity confirmed: `snapshot.py` and `_snapshot_nested.py` resolve to the same function objects.

Verification: `just _lint-mypy` clean; `just _lint-symvision` and `just _lint-toobig` report only pre-existing issues in untouched files (`_failed_close_recovery_assess.py`, `test_reset_replay.py`); the 16 snapshot tests pass; `sase tool run check` passes every stage except that same KNOWN symvision item (verdict `no_new_failures`).
