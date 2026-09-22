# Chat History - ace-run (toobig-5r.test_agents_tab_apply_boundary.0)

- **TIMESTAMP:** 2026-09-22 01:16:26 EDT
- **MODEL:** muse/muse-spark-1.3-contributor
- **AGENT:** toobig-5r.test_agents_tab_apply_boundary.0

## Prompt

%id(test_agents_tab_apply_boundary.0, clan=toobig-5r)
%model:@medium
%auto
%queue(capacity=3)
#gh:gh_sase-org__sase Can you help me split the `tests/test_agents_tab_apply_boundary.py` file up into multiple files? Use your best
%wait:toobig-5r.test_agent_loader_query_window.0
judgement, but let's aim to keep all files <=500 lines of code.

## Response

Done. Split `tests/test_agents_tab_apply_boundary.py` (782 lines) into three files, all under 500 lines:

- [test_agents_tab_apply_compute.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_25/tests/test_agents_tab_apply_compute.py) (136 lines) — compute/projection tests plus the fold-projection match test.
- [test_agents_tab_apply_bounded.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_25/tests/test_agents_tab_apply_bounded.py) (392 lines) — bounded-prefix, bounded-zero, and revalidate cache tests with their helpers.
- [test_agents_tab_apply_capacity.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_25/tests/test_agents_tab_apply_capacity.py) (296 lines) — fold-recompute, runner-capacity, worker-boundary, and proc-shell tests.

Every test body is byte-identical to the original, imports were trimmed per file, and the shared legacy-dialect fixture was kept in each. Verified: 20 passed via the project venv, `just fmt` clean, and `sase tool run check` succeeded (all lint gates + scoped tests).
