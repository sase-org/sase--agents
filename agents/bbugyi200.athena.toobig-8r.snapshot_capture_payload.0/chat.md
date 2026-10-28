# Chat History - ace-run (toobig-8r.snapshot_capture_payload.0)

- **TIMESTAMP:** 2026-10-28 14:47:13 EDT
- **MODEL:** muse/muse-spark-1.3-contributor
- **AGENT:** toobig-8r.snapshot_capture_payload.0

## Prompt

%id:toobig-8r.snapshot_capture_payload.0
%clan(toobig-8r, tribe=chop, summary=[[[bold #D75FFF]◆ TOOBIG SPLIT · 3 FILES[/bold #D75FFF]
[bold #87D7FF]MISSION[/bold #87D7FF]
[dim #D7D7FF]Decompose oversized Python modules into focused, reviewable units[/dim #D7D7FF]
[dim #D7D7FF]without changing behavior.[/dim #D7D7FF]

[bold #87D7FF]TARGETS[/bold #87D7FF]
[bold #FF5F87]▲ 1,079  tests/workspace_provider/test_reset_replay.py[/bold #FF5F87]
[#87D7FF]•   738  tests/workspace_provider/test_rescue/test_snapshot.py[/#87D7FF]
[#87D7FF]•   724  src/sase/workspace_provider/_snapshot_capture_payload.py[/#87D7FF]

[dim #A8A8A8]2 scan roots · limits 1,000 / 850 / 700 lines · sequential queue[/dim #A8A8A8]]])
%model:@medium
%auto
%queue(capacity=5)
#gh:gh_sase-org__sase Can you help me split the `src/sase/workspace_provider/_snapshot_capture_payload.py` file into multiple files? Use your best
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

Split `src/sase/workspace_provider/_snapshot_capture_payload.py` (724 lines) into three files under 500 lines:

- [facade](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_13/src/sase/workspace_provider/_snapshot_capture_payload.py) (203 lines): keeps `capture_into`, `publish_manifest`, and private filesystem helpers `_copy_operation_markers`, `_cleanup_capture_temps`, `_payload_names`.
- [trees](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_13/src/sase/workspace_provider/_snapshot_capture_payload_trees.py) (167 lines): public `collect_worktree_entries`, `write_tree`, `build_index_tree` plus private `_hash_blob`.
- [objects](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_13/src/sase/workspace_provider/_snapshot_capture_payload_objects.py) (409 lines): public `validate_index_objects`, `base_commit_objects`, `object_shas`, `account_pack_objects`, `write_pack`, `verify_pack` plus private remote/object/pack helpers.

No `_`-prefixed name is imported across new modules. Shared git/model helpers stay public in existing `_`-prefixed modules. Tests retargeted: `SNAPSHOT_MAX_BYTES` to objects module, `run_git_bytes` to trees module, `_write_pack` to facade `write_pack`; `publish_manifest` still patched on facade.

Verification:

- `just _lint-mypy` passes after adding missing `SNAPSHOT_PACK_NAME` import.
- `just _lint-toobig` passes; src files all under info limit.
- `just _lint-symvision` reports only pre-existing `_RecoveryAssessment` in untouched `src/sase/finalizers/_failed_close_recovery_assess.py`; no payload mentions.
- `pytest test_snapshot.py` 23 passed, `test_nested_preservation.py` 12 passed.
- `sase tool run check` fails only on that same pre-existing symvision item.
