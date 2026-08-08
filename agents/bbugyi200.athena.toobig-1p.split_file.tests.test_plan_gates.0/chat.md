# Chat History - ace-run (toobig-1p.split_file.tests.test_plan_gates.0)

- **TIMESTAMP:** 2026-08-06 12:21:17 EDT
- **MODEL:** claude/opus
- **AGENT:** toobig-1p.split_file.tests.test_plan_gates.0
- **PROMPT:** `~/.sase/multi_prompts/202608/sase_org_sase-multiprompt-260806_115812.md`

## Prompt

#gh:sase-org/sase
%id(split_file.tests.test_plan_gates.0, clan=toobig-1p)
%wait:toobig-1p.split_file.tests.agents_sync.test_rendering.0
%wait(runners=3)
%auto %wait(priority=20) Can you help me split the `tests/test_plan_gates.py` file up into multiple files? Use your best judgement, but let's aim to keep
all files <=500 lines of code.

## Response

I'll start by looking at the file.

Now I'll create the shared fixtures module and the split test files.

Now rewriting the original file to keep only the request-envelope structure tests:

All four files are well under 500 lines. Waiting for `just install` to finish before running the tests.

Same 33 tests before and after. Now the repo gates:

`just check` is fully green. Split done:

| File | Lines | Covers |
|---|---|---|
| `tests/test_plan_gates.py` | 168 | Request envelope structure: tier→typed-action routing, project-dir env contract, tier-aware option icons, plan-context recovery from old bundles |
| `tests/test_plan_gates_validation.py` | 178 | Edit revalidation + hash refresh, malformed header rejection, TOCTOU/unregistered-command rejection, forged query and stale group-label rejection |
| `tests/test_plan_gates_execution.py` | 246 | Epic host launch (durable path, unresolvable-launch hint), auto-resolution and its argument rejection, feedback/reject/race executor behavior, tale selection → runner protocol |
| `tests/test_plan_gates_action_api.py` | 156 | `execute_plan_approval_response` presets and option filtering, local action aliases, legacy plan-approval responses |
| `tests/_plan_gate_fixtures.py` | 46 | Shared `gate_home` fixture + `write_plan` helper |

Notes on the approach:

- The `gate_home` fixture in the original file shadowed a **narrower** same-named fixture in `tests/conftest.py` (the local one also clears `CLAUDE_PROJECT_DIR`/`SASE_ARTIFACTS_DIR`). To preserve that exactly, the shared version lives in `tests/_plan_gate_fixtures.py` as `plan_gate_home` with `@pytest.fixture(name="gate_home")`, and each module imports it — a module-level binding outranks conftest, which a `pytest_plugins` registration would not have. This follows the existing `_commit_workflow_fixtures.py` convention.
- `_write_plan` was renamed to `write_plan` since it's now imported across modules (symvision private-misuse rule).
- Test bodies are otherwise unchanged; 33 tests collected before and after, all passing, plus `test_gate_e2e_smoke.py` (which has its own near-duplicate `gate_home`) still green.

I did not commit — let me know if you want that.

I'll commit the split now.

Committed and pushed as `4186ceea9`; working tree is clean and level with `origin/master`.

The split (all files well under 500 lines):

| File | Lines | Covers |
|---|---|---|
| `tests/test_plan_gates.py` | 168 | Request envelope structure: tier→typed-action routing, project-dir env contract, tier-aware option icons, plan-context recovery from old bundles |
| `tests/test_plan_gates_validation.py` | 178 | Edit revalidation + hash refresh, malformed header rejection, TOCTOU/unregistered-command rejection, forged query and stale group-label rejection |
| `tests/test_plan_gates_execution.py` | 246 | Epic host launch, auto-resolution and its argument rejection, feedback/reject/race executor behavior, tale selection → runner protocol |
| `tests/test_plan_gates_action_api.py` | 156 | `execute_plan_approval_response` presets and option filtering, local action aliases, legacy plan-approval responses |
| `tests/_plan_gate_fixtures.py` | 46 | Shared `gate_home` fixture + `write_plan` helper |

Two details worth keeping in mind: the shared fixture is defined as `plan_gate_home` with `@pytest.fixture(name="gate_home")` and imported per-module so the module-level binding still outranks the narrower same-named fixture in `tests/conftest.py`, and `_write_plan` became `write_plan` now that it crosses module boundaries. Test bodies are unchanged — same 33 tests collected and passing before and after, and `just check` was green before the commit.
