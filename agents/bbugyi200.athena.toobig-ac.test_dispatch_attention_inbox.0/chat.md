# Chat History - ace-run (toobig-ac.test_dispatch_attention_inbox.0)

- **TIMESTAMP:** 2026-11-20 19:54:15 EST
- **MODEL:** grok/grok-4.6
- **AGENT:** toobig-ac.test_dispatch_attention_inbox.0

## Prompt

%auto
%id(test_dispatch_attention_inbox.0, clan=toobig-ac)
%model:@medium
%queue(capacity=5)
#gh:gh_sase-org__sase Can you help me split the `tests/test_dispatch_attention_inbox.py` file into multiple files? Use your best
%wait:toobig-ac.sase_chop_bead_task_triage.0
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

I'll start by reading the split constraints and the current test file so the modules stay under 500 lines without changing behavior.

I'll load the lint/split notes through the memory skill and inspect the test file plus any existing split patterns.

The file is 823 lines, so I'll look at prior splits and the rest of the module before choosing the cut points.

I'll look at recent test splits and how pytest fixtures are shared so the new modules match this repo.

I'll check how facades avoid double collection and how ruff treats helper-module naming.

I’ll split along lifecycle, reconcile, and legacy, put shared helpers in a private module with public names, and keep the original file as a facade.

I'll format the new modules, then run the three requested lints.

Format passed; next I’ll inspect import order and run the three lints.

I'll put the imports in the repo's usual order, then run the three lints.

The three lints passed. I’ll run the split tests, then `sase tool run check`.

All 21 tests passed. Next I’ll run the full `sase tool run check` gate.

Check succeeded. I’ll load the finalizer context and submit the declaration.

Split `tests/test_dispatch_attention_inbox.py` (823 lines) into five files, all under 500 lines. The original import path still re-exports the public names.

**Layout**
- `tests/test_dispatch_attention_inbox.py` — facade (`__test__ = False`) re-exporting the fixture and 21 tests
- `tests/_dispatch_attention_inbox_helpers.py` — shared builders and the `notification_store_file` fixture, under public names
- `tests/test_dispatch_attention_inbox_lifecycle.py` — create / dismiss / revision tests
- `tests/test_dispatch_attention_inbox_reconcile.py` — absence, concurrency, fetch, and payload tests
- `tests/test_dispatch_attention_inbox_legacy.py` — legacy-row migration tests (helpers stay private in this file)

**Verification**
- `just _lint-symvision`, `just _lint-mypy`, and `just _lint-toobig` all passed
- 21 split tests passed
- `sase tool run check` succeeded
