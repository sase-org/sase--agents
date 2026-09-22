# Chat History - ace-run (toobig-5r.test_launch_admission_dispatch.0)

- **TIMESTAMP:** 2026-09-22 02:02:35 EDT
- **MODEL:** muse/muse-spark-1.3-contributor
- **AGENT:** toobig-5r.test_launch_admission_dispatch.0

## Prompt

%id(test_launch_admission_dispatch.0, clan=toobig-5r)
%model:@medium
%auto
%queue(capacity=3)
#gh:gh_sase-org__sase Can you help me split the `tests/test_launch_admission_dispatch.py` file up into multiple files? Use your best
%wait:toobig-5r.test_finalizers_protocol_harness_multi_repo.0
judgement, but let's aim to keep all files <=500 lines of code.

## Response

Done. Split `tests/test_launch_admission_dispatch.py` (914 lines) into three files, each under 500 lines:

- [test_launch_admission_dispatch_core.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_25/tests/test_launch_admission_dispatch_core.py) (217 lines) — basic dispatch: engine dispatch after empty wait, partial success, cancel behavior, proc queue capacity, authored proc weight.
- [test_launch_admission_dispatch_proc_holds.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_25/tests/test_launch_admission_dispatch_proc_holds.py) (340 lines) — proc hold gating and typed hold pre-arm: named/future holds, idempotency, field recording, flag override, empty-ID rejection, rollback cases.
- [test_launch_admission_dispatch_hold_lifecycle.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_25/tests/test_launch_admission_dispatch_hold_lifecycle.py) (396 lines) — hold lifecycle around dispatch: hold-key carry/re-anchor, best-effort re-anchor failures, hold release paths, self-hold, proc priority.

Test bodies are byte-identical to the original (verified by diff; 23 tests preserved), with imports trimmed per file and the `_write_launch_request` helper moved to the one file that uses it. Verification: all 26 test cases pass, and `just check` is green across every lint gate including `toobig`.
