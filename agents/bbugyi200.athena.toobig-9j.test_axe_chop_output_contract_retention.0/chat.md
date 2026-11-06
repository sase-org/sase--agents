# Chat History - ace-run (toobig-9j.test_axe_chop_output_contract_retention.0)

- **TIMESTAMP:** 2026-11-06 15:21:16 EST
- **MODEL:** muse/muse-spark-1.3-contributor
- **AGENT:** toobig-9j.test_axe_chop_output_contract_retention.0

## Prompt

%auto
%id(test_axe_chop_output_contract_retention.0, clan=toobig-9j)
%model:@medium
%queue(capacity=5)
#gh:gh_sase-org__sase Can you help me split the `tests/test_axe_chop_output_contract_retention.py` file into multiple files? Use your best
%wait:toobig-9j.project_display_names.0
judgment, but keep every resulting file at 500 lines of code or fewer.

Preserve behavior and the original module's public import path. A facade may re-export
public names, but never `_private` names. Never import a `_`-prefixed name across the
new modules. If more than one new module needs a helper, give it a public name inside an
already-private (`_`-prefixed) module; move a helper used by only one other module into
that module instead. Keep test monkeypatch targets working, or retarget the tests.

Before finishing, run `just _lint-symvision`, `just _lint-mypy`, and `just _lint-toobig`
individually. Fix every issue in a file the split touched, even if an earlier
`just check` stage is already red. Then run `sase tool run check`.

## Response

Done. The 743-line `tests/test_axe_chop_output_contract_retention.py` is now four files, each under 500 lines, with the original path kept as a re-export facade.

What changed:
- [tests/test_axe_chop_output_contract_retention.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_13/tests/test_axe_chop_output_contract_retention.py): facade, 50 lines, re-exports all 15 public `test_*` names with `__test__ = False`, no `_private` re-exports.
- [tests/test_axe_chop_output_contract_retention_prune.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_13/tests/test_axe_chop_output_contract_retention_prune.py): 6 mocked prune tests, 364 lines.
- [tests/test_axe_chop_output_contract_retention_prune_real_store.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_13/tests/test_axe_chop_output_contract_retention_prune_real_store.py): 5 real-store tests plus the single-use `_stub_retention_plan`/`_run_artifact_prune` moved in-file, 234 lines.
- [tests/test_axe_chop_output_contract_retention_flush_compact.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_13/tests/test_axe_chop_output_contract_retention_flush_compact.py): epic-flush and compact tests, 181 lines.
- [tests/_axe_chop_output_contract_helpers.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_13/tests/_axe_chop_output_contract_helpers.py): new public builders (`retention_plan`, `retention_selected_item`, `retention_empty_shard`, `retention_purge_result`, `assert_configured_aware_timestamp`, `write_output_contract_context`, `isolate_chop_result_file`) for helpers shared by two or more new modules; no new module imports a `_`-prefixed name. Old `_` aliases kept for the other existing importers.

One real issue found and fixed: two tests failed only when run after the TUI prune-modal test, because that suite's conftest patches the display-snapshot loader and the chop module captures it at first import. Both tests now stub `load_project_ref_display_snapshot` like their neighbors, so they pass in any order. Per the durable-test guidance I kept no extra test file: the two fixed tests are themselves the regression coverage, proven by the polluted-order repro (16 passed).

Verification observed: `just _lint-mypy` clean, `just _lint-toobig` clean, `just fmt` clean, symvision scan clean ("All public/private classes/functions are used properly!"). `just test-scoped` passed fully: 1183 passed. `sase tool run check` could not go green for an unrelated reason: its epic-symbol freshness preflight refuses because this checkout's HEAD predates an upstream revision that already removed the stale `sase-1qz.7` whitelist rows. That needs the normal workspace update flow, not a test edit, so I left it untouched.
