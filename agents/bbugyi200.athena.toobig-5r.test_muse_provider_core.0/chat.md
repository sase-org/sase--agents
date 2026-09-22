# Chat History - ace-run (toobig-5r.test_muse_provider_core.0)

- **TIMESTAMP:** 2026-09-21 23:13:49 EDT
- **MODEL:** muse/muse-spark-1.3-contributor
- **AGENT:** toobig-5r.test_muse_provider_core.0

## Prompt

%id(test_muse_provider_core.0, clan=toobig-5r)
%model:@medium
%auto
%queue(capacity=3)
#gh:gh_sase-org__sase Can you help me split the `tests/llm_provider/test_muse_provider_core.py` file up into multiple files? Use your best
%wait:toobig-5r.test_v2_io.0
judgement, but let's aim to keep all files <=500 lines of code.

## Response

Done. Split the 795-line `tests/llm_provider/test_muse_provider_core.py` into three focused test files plus one shared helpers module, following the repo's existing `_helpers` convention:

- [test_muse_provider_identity.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_25/tests/llm_provider/test_muse_provider_identity.py) (112 lines) — registration, metadata hooks, model mapping, install metadata.
- [test_muse_provider_invocation.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_25/tests/llm_provider/test_muse_provider_invocation.py) (261 lines) — command construction, effort flags, extra args, error paths, interrupt continuation.
- [test_muse_provider_stream.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_25/tests/llm_provider/test_muse_provider_stream.py) (338 lines) — JSONL stream-parser tests, keeps the original release-keyed fixture docstring.
- [_muse_provider_helpers.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_25/tests/llm_provider/_muse_provider_helpers.py) (108 lines) — shared fixtures and builders (`_run_fixture_stream`, `_envelope`, `_invoke_and_capture`, `_delta`, `_terminal`, `_read_timestamps`, fixture paths, `_MUSE_MODELS`).

The split follows the section banners already in the original file, and all test bodies are unchanged. Verification: all 48 tests (same IDs as baseline) pass, and `sase tool run check` succeeded — every lint gate (ruff, mypy, symvision, toobig, etc.) plus the diff-scoped test lane.
