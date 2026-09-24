# Chat History - ace-run (toobig-5y.refresh.0)

- **TIMESTAMP:** 2026-09-23 20:32:44 EDT
- **MODEL:** muse/muse-spark-1.3-contributor
- **AGENT:** toobig-5y.refresh.0

## Prompt

%id(refresh.0, clan=toobig-5y)
%model:@medium
%auto
%queue(capacity=3)
#gh:gh_sase-org__sase Can you help me split the `src/sase/llm_provider/usage/refresh.py` file up into multiple files? Use your best
%wait:toobig-5y.presentation.0
judgement, but let's aim to keep all files <=500 lines of code.

## Response

Done. `refresh.py` (814 lines) is now a thin facade plus five focused modules, all well under 500 lines:

| File | Lines | Contents |
|---|---|---|
| [refresh.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_25/src/sase/llm_provider/usage/refresh.py:1) | 103 | Facade: re-exports + unchanged `__all__` |
| [_refresh_model.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_25/src/sase/llm_provider/usage/_refresh_model.py:1) | 79 | Constants, `UsageRefreshReceipt`, `_UsageRefreshProviderResult`, `is_inline_usage_operation` |
| [_refresh_eligibility.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_25/src/sase/llm_provider/usage/_refresh_eligibility.py:1) | 130 | `eligible_usage_providers`, `_referenced_provider_ids`, `_provider_cli_ready`, `_resolve_requested_providers`, `_provider_has_probe_capability` |
| [_refresh_triggers.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_25/src/sase/llm_provider/usage/_refresh_triggers.py:1) | 115 | `_mark_usage_refresh_due`, `mark_provider_usage_hot_hint`, `trigger_usage_refresh_after_limit_event` |
| [_refresh_execution.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_25/src/sase/llm_provider/usage/_refresh_execution.py:1) | 259 | `wait_for_usage_refresh_operations`, inline/proc runners, payload, release helpers |
| [_refresh_submit.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_25/src/sase/llm_provider/usage/_refresh_submit.py:1) | 324 | `submit_usage_refresh`, `request_due_usage_refresh`, `_admit_one`, normalize/disabled helpers |

Compatibility was the main constraint and is fully preserved: same `__all__` (verified byte-identical), same import paths for all 13 in-repo consumers, and every private test seam (`_admit_one`, `_referenced_provider_ids`, `_mark_usage_refresh_due`, …) still resolvable from `sase.llm_provider.usage.refresh`. Function bodies are verbatim moves. The one deliberate mechanism: names the test suite monkeypatches on the `refresh` namespace (store functions, `usage_probe_floor`, `eligible_usage_providers`, …) are resolved via late imports so the facade stays the single patch point — each site has a one-line note saying so. This mirrors yesterday's `presentation.py` split (d7faebddf) exactly.

Verification observed: 1212 passed across `tests/llm_provider` plus drain/exec-retry tests, 83 passed across usage-command/modal/refresh-panel/doctor tests, all importers load, and ruff, mypy, fmt, keep-sorted, and toobig are clean.

One pre-existing finding, not caused by this change: `just check` stops at the symvision gate. I confirmed via `git stash` that pristine HEAD fails it two ways — a stale `--epic-symbol 'sase-17a.2(…)'` entry for a closed bead, and 56 private-import findings (the installed symvision 0.1.0 flags the same facade pattern the repo already uses in `_presentation_*`). My split adds 17 entries of that same already-failing kind; making them public would break the test seams and still leave the gate red, so I kept the precedent-consistent design. Worth a maintainer decision on whether to clean up the gate or pin symvision differently.

Declaration submitted: commit of the `refresh.py` split for host finalizer to preserve.
