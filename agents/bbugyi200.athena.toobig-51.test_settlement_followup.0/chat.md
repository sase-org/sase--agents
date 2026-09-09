# Chat History - ace-run (toobig-51.test_settlement_followup.0)

- **TIMESTAMP:** 2026-09-09 03:54:52 EDT
- **MODEL:** grok/grok-4.6
- **AGENT:** toobig-51.test_settlement_followup.0

## Prompt

%wait:toobig-51.test_dispatch.0
%id(test_settlement_followup.0, clan=toobig-51)
%model:@medium
%auto
%wait(runners=3)
%wait(priority=20)
#gh:gh_sase-org__sase
Can you help me split the `tests/gate_shell/test_settlement_followup.py` file up into multiple files? Use your best
judgement, but let's aim to keep all files <=500 lines of code.

## Response

I'll start by inspecting the settlement follow-up test file and how nearby gate-shell tests are split, then break it into files of 500 lines or fewer.

The file is large, so I’ll map its tests and helpers next, then split along those boundaries.

The file is 715 lines; next I’ll read it in full and check how nearby tests share fixtures.

I’ll check how other test suites share fixtures so the split matches existing conventions.

I’ll extract shared builders, then split launch/follow-up tests from workspace-claim tests so each file stays under 500 lines.

Next I’ll confirm line counts and run the split tests.

I'll run the split tests first, then `just check` as the required verification lane.

`just check` is still running; I’ll wait for it to finish.

Verification passed. Next I’ll submit the finalizer declaration so this turn can close.

Split `tests/gate_shell/test_settlement_followup.py` (715 lines) along the two concerns in that file:

| File | Lines | Contents |
|---|---|---|
| `tests/gate_shell/_settlement_followup_helpers.py` | 124 | Shared gate spec/member builders and the `SASE_HOME` sandbox fixture |
| `tests/gate_shell/test_settlement_followup.py` | 370 | Launch ordering, timeout branches, unparseable shell, tale coder follow-up, `creator_live` suppression, done-marker outcome |
| `tests/gate_shell/test_settlement_followup_claims.py` | 268 | Workspace-claim hold, restore when the creator is live, and release when it is dead |

Behavior is unchanged: the 12 original tests still pass. `just check` is green.
