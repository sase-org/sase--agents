# Chat History - ace-run (toobig-5r.test_repo_handler_open_configured.0)

- **TIMESTAMP:** 2026-09-21 23:49:55 EDT
- **MODEL:** muse/muse-spark-1.3-contributor
- **AGENT:** toobig-5r.test_repo_handler_open_configured.0

## Prompt

%id(test_repo_handler_open_configured.0, clan=toobig-5r)
%model:@medium
%auto
%queue(capacity=3)
#gh:gh_sase-org__sase Can you help me split the `tests/main/test_repo_handler_open_configured.py` file up into multiple files? Use your best
%wait:toobig-5r.test_init_onboarding_all.0
judgement, but let's aim to keep all files <=500 lines of code.

## Response

Done. Split `tests/main/test_repo_handler_open_configured.py` (712 lines) into two files, with all 8 tests preserved verbatim:

- [test_repo_handler_open_configured_linked.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_25/tests/main/test_repo_handler_open_configured_linked.py) (404 lines) — linked-checkout resolution: direct linked name, provider alias using the configured checkout, and the two external-duplicate preservation/warning tests. Keeps the `_evaluate_sase_core_dir` helper, which only these tests need.
- [test_repo_handler_open_configured_aliases.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_25/tests/main/test_repo_handler_open_configured_aliases.py) (326 lines) — sidecar slug acceptance, the two registered-project-alias redirects (by path, by remote identity), and the hidden-agents machine-scoping test.

Verification: an AST comparison confirmed every test body is byte-identical to the original; all 8 tests pass under the project venv; `sase tool run check` (all lint gates + scoped tests) succeeded. The original file was removed and the change submitted via the finalizer declaration.
