# Chat History - ace-run (toobig-8t.test_monitor_host_completion.0)

- **TIMESTAMP:** 2026-10-29 17:43:54 EDT
- **MODEL:** grok/grok-4.6
- **AGENT:** toobig-8t.test_monitor_host_completion.0

## Prompt

%auto
%id(test_monitor_host_completion.0, clan=toobig-8t)
%model:@medium
%queue(capacity=5)
#gh:gh_sase-org__sase Can you help me split the `tests/monitor/test_monitor_host_completion.py` file into multiple files? Use your best
%wait:toobig-8t.workflow.0
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

I'll split `tests/monitor/test_monitor_host_completion.py` into files of 500 lines or fewer, keep public imports working, and run the requested lints. First I'm reading the split rules and the current test file.

The original file is 740 lines, so I'll look at how similar monitor tests were split and then map this module's public names and helpers.

I'll look at how other monitor tests were split and what the toobig gate expects so the facade and helper layout match the repo.

I have a split plan: a private helper module with public names, themed test modules under 500 lines, and a facade that keeps the original import path.

I left `InvokeResult` out of the helper imports; adding it next, then writing the split test modules.

Nine tests passed with no double collection. Next I’ll run the three requested lints.

The three lints passed and the nine tests stayed green. Next I’ll run `sase tool run check`.

`sase tool run check` failed on a stale contract manifest. I’ll inspect whether the split caused that and refresh it if it did.

Split `tests/monitor/test_monitor_host_completion.py` (740 lines) into focused modules, each under 500 lines. The original import path still re-exports the public test names.

**Layout**
- `tests/monitor/_host_completion.py` — shared public helpers (`make_meta`, `make_intent`, `patch_mod`, `patch_success_path`, `production_recovery`, `settle`, `sandbox_home`)
- `test_monitor_host_completion_eligibility.py` — sidecar archive eligibility
- `test_monitor_host_completion_settle.py` — success, ineligible recovery, policy fall-through
- `test_monitor_host_completion_receipts.py` — commit-receipt matching (private `_production_commit_markers` stays in this file)
- `test_monitor_host_completion_no_model.py` — missing-declaration controller refusal
- `test_monitor_host_completion.py` — facade with `__test__ = False` so pytest collects each test once

Private names are not imported across modules. Helpers used by more than one module have public names in the `_`-prefixed helper module.

**Verification**
- 9 host-completion tests passed (same count as before, no double collection)
- `just _lint-symvision`, `just _lint-mypy`, and `just _lint-toobig` all passed
- `sase tool run check` finished `no_new_failures` with one FLAKY: `tests/test_contract_manifest.py::test_contract_manifest_matches_marker_selection` (stale `tests/contract_manifest.txt`). That file is outside this split.
