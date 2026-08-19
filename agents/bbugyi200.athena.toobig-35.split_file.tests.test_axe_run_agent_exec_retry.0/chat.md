# Chat History - ace-run (toobig-35.split_file.tests.test_axe_run_agent_exec_retry.0)

- **TIMESTAMP:** 2026-08-19 02:20:52 EDT
- **MODEL:** claude/opus
- **AGENT:** toobig-35.split_file.tests.test_axe_run_agent_exec_retry.0
- **PROMPT:** `~/.sase/multi_prompts/202608/sase_org_sase-multiprompt-260818_225904.md`

## Prompt

#gh:sase-org/sase
%id(split_file.tests.test_axe_run_agent_exec_retry.0, clan=toobig-35)
%wait:toobig-35.split_file.tests.main.test_init_skills_sources.0
%wait(runners=3)
%auto %wait(priority=20) Can you help me split the `tests/test_axe_run_agent_exec_retry.py` file up into multiple files? Use your best
judgement, but let's aim to keep all files <=500 lines of code.

## Response

I'll start by looking at the file.

Now I'll create the shared helpers module:

Now the three focused test modules:

Now the usage-limit module:

All 23 tests pass (same count as before the split). Now the repo gate:

Done. The 769-line file is now four modules, split by what each group actually exercises:

| File | Lines | Covers |
|---|---|---|
| `tests/test_axe_run_agent_exec_retry.py` | 249 | Continuation-nudge behavior: `_maybe_prepend_continuation`, nudge injection/idempotence on retry, max-retries exhaustion, no-nudge config, post-plan-approval coder retries |
| `tests/test_axe_run_agent_exec_retry_workspace.py` | 183 | `preserve_workspace` gating of `prepare_workspace` (retry + fallback paths) and the occupancy guard that refuses to clobber a live occupant |
| `tests/test_axe_run_agent_exec_retry_usage_limits.py` | 297 | Usage-limit precedence over retry classification, fallback provider allow/skip, `_detect_usage_limit_for_error` |
| `tests/_axe_run_agent_exec_retry_helpers.py` | 77 | Shared `make_ctx`, `make_ctx_with_update_target`, `make_state`, `config_with_nudge`, `CLAUDE_WEEKLY_LIMIT`, and the autouse `SASE_MODEL_OVERRIDE` restore fixture |

Notes on the mechanics:
- Helpers follow the existing `tests/_*_helpers.py` convention with public names; the autouse env fixture is imported into all three modules with `# noqa: F401`, matching the precedent in `tests/_axe_chop_bead_task_triage_helpers.py`, so every test keeps the exact fixture coverage it had before.
- Test bodies are unchanged apart from helper renames; the only substantive tidy-ups are hoisting function-local imports (`dataclasses`, `get_retry_config`, occupancy-guard imports) to module level, and using `make_ctx_with_update_target` in `test_prepends_nudge_on_zero_wait_retry` where it previously inlined the same `dataclasses.replace`.
- `_preserve_cfg` / `_fallback_preserve_cfg` stayed file-local since only the workspace module uses them.

Verification: 23 tests before, 23 passing after. `just check` is green across all lint gates and the scoped test lane (which escalated to the full suite on this change and passed).

These are the split changes from this session. Committing them now.

Committed as `f799c3b73`. Working tree is clean and `master` is level with `origin/master` (pushed).

The split, as landed:

| File | Lines | Covers |
|---|---|---|
| `tests/test_axe_run_agent_exec_retry.py` | 249 | Continuation-nudge behavior: injection, idempotence across retries, max-retries exhaustion, no-nudge config, post-plan-approval coder retries |
| `tests/test_axe_run_agent_exec_retry_workspace.py` | 183 | `preserve_workspace` gating of `prepare_workspace` plus the live-occupant guard |
| `tests/test_axe_run_agent_exec_retry_usage_limits.py` | 297 | Usage-limit precedence over retry classification, fallback provider allow/skip, `_detect_usage_limit_for_error` |
| `tests/_axe_run_agent_exec_retry_helpers.py` | 77 | Shared fixtures/factories, following the existing `tests/_*_helpers.py` convention |

One note from the commit hook: the project has 15 quarantined agent-hood publication requests, so the agent link written to this commit may be unavailable until you run `sase agent sync --retry-quarantined`. That's pre-existing and unrelated to this change — the commit itself succeeded.
