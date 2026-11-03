# Chat History - ace-run (toobig-95.test_workspace_retention.0)

- **TIMESTAMP:** 2026-11-03 10:38:35 EST
- **MODEL:** grok/grok-4.6
- **AGENT:** toobig-95.test_workspace_retention.0

## Prompt

%auto
%id(test_workspace_retention.0, clan=toobig-95)
%model:@medium
%queue(capacity=5)
#gh:gh_sase-org__sase Can you help me split the `tests/turns/test_workspace_retention.py` file into multiple files? Use your best
%wait:toobig-95.test_monitor_handler_start_launch.0
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

I'll split `tests/turns/test_workspace_retention.py` into modules of 500 lines or fewer, then run the requested lints and `sase tool run check`. First I'll read the split constraints and the current test file.

I'll read the rest of the test file and the lint/split conventions next so the split matches existing patterns.

The file is 744 lines, and another test already imports `_init_repo` from it. I'll check how similar splits are done and read the lint notes next.

I'll look at how earlier toobig splits were structured so this one follows the same facade and helper rules.

I have the facade pattern. Next I’ll read the full test file and map helpers, tests, and monkeypatch targets.

I'll split into a private helpers module plus two themed test modules, and keep the original path as a public-name facade.

I'll add the helpers module and the two test modules, then turn the original file into a facade.

There's a second `_init_repo` call in the staged-recovery test; I'll retarget that next.

The split is in place. Next I’ll run `_lint-symvision`, `_lint-mypy`, and `_lint-toobig` one at a time.

The three lints passed. Next I’ll run `sase tool run check`.

Check finished with one FLAKY scoped-test failure. I’ll inspect it to confirm it isn’t from the split.

Scoped check escalated to the full suite: 59,822 passed, one unrelated FLAKY. I’ll gather the finalizer context and submit.

Split `tests/turns/test_workspace_retention.py` (744 lines) into four modules, all under 500 lines:

- `tests/turns/_workspace_retention_helpers.py` — shared builders with public names (`init_repo`, `owner`, `claim`, …)
- `tests/turns/test_workspace_retention_policy.py` — retain vs release
- `tests/turns/test_workspace_retention_records.py` — dismissal, occupancy, records
- `tests/turns/test_workspace_retention.py` — facade that re-exports public test names (`__test__ = False`)

`tests/test_staged_recovery_retention.py` now imports `init_repo` from the helpers module instead of `_init_repo` from the original path.

`just _lint-symvision`, `just _lint-mypy`, and `just _lint-toobig` all passed. `sase tool run check` finished `no_new_failures`: 59,822 passed, 1 FLAKY in `tests/test_agent_artifact_marker_path_passing_audit.py` (untouched, already in the flake baseline).
