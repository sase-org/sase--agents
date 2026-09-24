# Chat History - ace-run (toobig-5y.presentation.0)

- **TIMESTAMP:** 2026-09-23 20:09:52 EDT
- **MODEL:** muse/muse-spark-1.3-contributor
- **AGENT:** toobig-5y.presentation.0

## Prompt

%id(presentation.0, clan=toobig-5y)
%model:@medium
%auto
%queue(capacity=3)
#gh:gh_sase-org__sase Can you help me split the `src/sase/llm_provider/usage/presentation.py` file up into multiple files? Use your best
%wait:toobig-5y.claude.0
judgement, but let's aim to keep all files <=500 lines of code.

## Response

Done. Split the 767-line `presentation.py` into 5 files, all ≤500 lines, following the `claude.py` → `_claude_*` facade precedent already used in the same directory:

- [presentation.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/src/sase/llm_provider/usage/presentation.py:1) (55 lines) — thin facade; `__all__` is byte-identical, so all existing imports keep working.
- [_presentation_snapshot.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/src/sase/llm_provider/usage/_presentation_snapshot.py:1) (101 lines) — JSON payload, snapshot filtering, display rows.
- [_presentation_labels.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/src/sase/llm_provider/usage/_presentation_labels.py:1) (273 lines) — status/retry/reset/age/timestamp labels plus Rich styles.
- [_presentation_render.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/src/sase/llm_provider/usage/_presentation_render.py:1) (343 lines) — plain/Rich/toast/receipt renderers and plain-record encoders.
- [_presentation_shared.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/src/sase/llm_provider/usage/_presentation_shared.py:1) (102 lines) — constants, coercion helpers, row accessors.

One judgment call worth knowing: the test suite monkeypatches `presentation.provider_usage_format_remaining_text` and accesses private `_collector_health_label` / `_collector_health_style`. The facade re-exports all three, and the moved call sites resolve the formatter through the facade at call time (documented in `_format_remaining_text`), so that seam keeps working with no test changes.

Verified: 18/18 presentation tests pass, plus `test_usage_command`, `test_refresh_panel_modal`, and `test_grok_usage_probe` (65 passed); `ruff check`, `ruff format --check`, and `mypy` are all clean on the touched files.

Declaration submitted: commit accepted for the presentation split.
