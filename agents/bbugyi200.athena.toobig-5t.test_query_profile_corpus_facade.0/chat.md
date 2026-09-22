# Chat History - ace-run (toobig-5t.test_query_profile_corpus_facade.0)

- **TIMESTAMP:** 2026-09-22 09:02:14 EDT
- **MODEL:** muse/muse-spark-1.3-contributor
- **AGENT:** toobig-5t.test_query_profile_corpus_facade.0

## Prompt

%id(test_query_profile_corpus_facade.0, clan=toobig-5t)
%model:@medium
%auto
%queue(capacity=3)
#gh:gh_sase-org__sase Can you help me split the `tests/test_query_profile_corpus_facade.py` file up into multiple files? Use your best
%wait:toobig-5t.test_service_effective_env.0
judgement, but let's aim to keep all files <=500 lines of code.

## Response

Done. The 703-line `tests/test_query_profile_corpus_facade.py` is now four files, all well under 500 lines:

- [helpers](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_25/tests/_query_profile_corpus_facade_helpers.py) (85 lines) — shared `_BEADS_ROWS` fixture plus the `_flags`/`_bounds`/`_boolean_value` schema builders, following the existing `tests/_query_profile_helpers.py` convention.
- [index](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_25/tests/test_query_profile_corpus_facade_index.py) (125 lines) — index lifecycle: compile/evaluate, facets, wire shape, cache-key sensitivity, stale-index validation.
- [parity](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_25/tests/test_query_profile_corpus_facade_parity.py) (407 lines) — Rust-vs-Python evaluation parity, including the large bare-flags/bound-keys test.
- [parse](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_25/tests/test_query_profile_corpus_facade_parse.py) (130 lines) — parse/canonicalize parity.

No test was added, removed, or altered — the split is a pure move (44 tests collected after, matching the original's 5 + 27 + 12). Verified with the targeted pytest run (44 passed) and the recorded `sase tool run check`, which passed all lint gates (ruff, mypy, symvision, toobig) plus the diff-scoped test lane.
