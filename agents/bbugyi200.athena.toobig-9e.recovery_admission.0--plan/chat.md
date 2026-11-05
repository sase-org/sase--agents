# Chat History - ace-run (toobig-9e.recovery_admission.0--plan)

- **TIMESTAMP:** 2026-11-05 18:36:29 EST
- **MODEL:** muse/muse-spark-1.3-contributor
- **AGENT:** toobig-9e.recovery_admission.0--plan

# Monitor handoff

This agent delegated the remaining work to a monitor turn.
Monitor ID: 29qzabt8tna9
Inspect with: sase monitor show 29qzabt8tna9
Monitor turn: toobig-9e.recovery_admission.0--mon
Directory: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_28

Command:

```sh
sase tool run check
```

Reason:

finish check (joined run)

Next action:

Read the joined check run result with sase tool show, fix any NEW failures in the split files, run the hijack recovery tests, then reply to the user.


## Prompt

%id(recovery_admission.0, clan=toobig-9e)
%model:@medium
%auto
%queue(capacity=5)
#gh:gh_sase-org__sase Can you help me split the `src/sase/agent/hijack/recovery_admission.py` file into multiple files? Use your best
%wait:toobig-9e.recover.0
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

Split `recovery_admission.py` (983 lines) into 6 files, all ≤500 lines:

- [recovery_admission.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_28/src/sase/agent/hijack/recovery_admission.py) (53 lines) — facade re-exporting original public API and `__all__`, plus `RECOVERY_REQUESTS_SUBDIR`, `TYPED_LAUNCHES_SUBDIR`, `LOGICAL_ID` for compat. No `_private` re-exports.
- [_recovery_admission_common.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_28/src/sase/agent/hijack/_recovery_admission_common.py) (198) — constants + shared public helpers (`required_string`, `string_or_none`, `positive_int`, `validate_request_id`, `canonical_json`, `descriptor_digest`, `split_model_effort`, `validate_descriptor_fields`, `descriptor_from_data`, `record_owns_descriptor`, `bundle_dir_for_request`, `read_prepared_recovery_descriptor`, `is_hijack_recovery_typed_request`).
- [_recovery_admission_prepare.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_28/src/sase/agent/hijack/_recovery_admission_prepare.py) (165) — `prepare/persist/remove`.
- [_recovery_admission_dispatch.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_28/src/sase/agent/hijack/_recovery_admission_dispatch.py) (121) — `dispatch_recovery_admission` + private `_typed_request_payload`.
- [_recovery_admission_dispatcher.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_28/src/sase/agent/hijack/_recovery_admission_dispatcher.py) (425) — `make_hijack_recovery_agent_dispatcher` + private validation/spawn helpers including `_target_available`.
- [_recovery_admission_observe.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_28/src/sase/agent/hijack/_recovery_admission_observe.py) (201) — `observe/resume/cancel/cancel_for_rollback` + private `_ledgerless_admission_states`.

No cross-module `_private` imports; single-use helpers stay private in their owner module.

Retargeted test monkeypatch in `tests/_agent_hijack_recover_helpers.py` from `recovery_admission._target_available` to `_recovery_admission_dispatcher._target_available`.

Verification:
- `just _lint-symvision`: pass
- `just _lint-mypy`: pass (6388 files)
- `just _lint-toobig`: fails only on pre-existing `recovery_successor.py` (1305 lines); all touched files pass
- `sase tool run check` (run `bb7701623f611bc3fbbbc695afd553ef`) handed to monitor `29qzab` via `sase monitor start -J`; follow-up will read the result, run hijack recovery tests, and fix any NEW failures.
Split complete. `src/sase/agent/hijack/recovery_admission.py` (983 lines) is now 6 files, each ≤500 lines:

- [recovery_admission.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_28/src/sase/agent/hijack/recovery_admission.py) (53 lines) — facade re-exporting the original public API with the identical `__all__` (3 constants + 10 functions), plus `RECOVERY_REQUESTS_SUBDIR`, `TYPED_LAUNCHES_SUBDIR`, `LOGICAL_ID` for attribute compat. No `_private` re-exports.
- [_recovery_admission_common.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_28/src/sase/agent/hijack/_recovery_admission_common.py) (198) — constants plus shared helpers with public names (`required_string`, `string_or_none`, `positive_int`, `validate_request_id`, `canonical_json`, `descriptor_digest`, `split_model_effort`, `validate_descriptor_fields`, `descriptor_from_data`, `record_owns_descriptor`, `bundle_dir_for_request`, `read_prepared_recovery_descriptor`, `is_hijack_recovery_typed_request`).
- [_recovery_admission_prepare.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_28/src/sase/agent/hijack/_recovery_admission_prepare.py) (165) — `prepare/persist/remove`.
- [_recovery_admission_dispatch.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_28/src/sase/agent/hijack/_recovery_admission_dispatch.py) (121) — `dispatch_recovery_admission` + private `_typed_request_payload`.
- [_recovery_admission_dispatcher.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_28/src/sase/agent/hijack/_recovery_admission_dispatcher.py) (425) — `make_hijack_recovery_agent_dispatcher` + private validation/spawn helpers.
- [_recovery_admission_observe.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_28/src/sase/agent/hijack/_recovery_admission_observe.py) (201) — `observe/resume/cancel/cancel_for_rollback`.

No cross-module `_private` imports; single-use helpers stay private in their owner module. Existing callers (`_recover_dispatch`, `recover`, `launch_admission`, `recover_confirm`, `__init__`) import public names from the facade and needed no changes. The one private monkeypatch target was retargeted: `tests/_agent_hijack_recover_helpers.py` now patches `_recovery_admission_dispatcher._target_available`.

Verification, each run individually as required:
- `just _lint-symvision`: pass (`All public/private classes/functions are used properly!`)
- `just _lint-mypy`: pass (`Success: no issues found in 6388 source files`)
- `just _lint-toobig`: our files pass; the single violation is pre-existing `recovery_successor.py` (1305 lines), untouched by this split
- `sase tool run check` (`bb7701623f611bc3fbbbc695afd553ef`): settled EXIT 1. Every failure proven pre-existing by re-running on an untouched HEAD worktree with identical results — the same 9 `test_agent_hijack_recovery_transaction.py` failures (root cause `replace()` on a `SimpleNamespace` plan, present in the original code), the same 2 `test_pytest_isolation_guards.py` failures (offender `tests/ace/tui/test_log_panel_keymap.py:331`, unrelated), and the toobig violation above. The 8 hijack recovery admission/launch tests covering the split all pass, including through the retargeted patch target.
