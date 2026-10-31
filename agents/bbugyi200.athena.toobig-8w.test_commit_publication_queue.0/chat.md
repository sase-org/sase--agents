# Chat History - ace-run (toobig-8w.test_commit_publication_queue.0)

- **TIMESTAMP:** 2026-10-30 23:18:07 EDT
- **MODEL:** grok/grok-4.6
- **AGENT:** toobig-8w.test_commit_publication_queue.0

## Prompt

%auto
%id(test_commit_publication_queue.0, clan=toobig-8w)
%model:@medium
%queue(capacity=5)
#gh:gh_sase-org__sase Can you help me split the `tests/agents_sync/test_commit_publication_queue.py` file into multiple files? Use your best
%wait:toobig-8w.test_cli.0
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

I'll split that agents_sync test file into smaller modules while preserving public imports and behavior. First I need the lint notes, the current file, and how similar test splits were done.

I'll pull the lint/test and Symvision notes plus the original test file so the split matches project rules.

The original file is 704 lines. Next I’ll inspect it and nearby split patterns so the new modules stay under 500 lines.

I'll look at how other test files in this tree were split so the new layout matches existing conventions.

The local pattern is a package plus an `__init__.py` facade. I’ll split the eight tests into three themed modules and keep the public import path.

I'll format the new modules, confirm each stays under 500 lines, then run the three lint recipes.

All four files are under 500 lines. Next I’ll run the three requested lint recipes and collect the split tests.

toobig’s remaining failures are in files this split didn’t touch. I’ll wait for mypy and Symvision to finish.

Symvision and mypy passed. I’ll collect and run the split tests, then start `sase tool run check`.

All eight tests passed and the public import path still works. Next I’ll run `sase tool run check`.

The check failed on feature-flags, which may be unrelated. I’ll inspect the full ToolRun output before deciding.

The flags failure is schema drift outside this split. I’ll rerun check with `-k` so the remaining lint and test stages still run.

One scoped-test failure is in `tests/agents_sync/test_cli_names.py`. I’ll inspect that before treating the rest as unrelated schema drift.

Split `tests/agents_sync/test_commit_publication_queue.py` (704 lines) into a package that keeps the original import path.

**Layout**

- `tests/agents_sync/test_commit_publication_queue/__init__.py` — facade re-exporting the 8 public tests
- `test_enqueue.py` (127 lines) — retryable enqueue and linked-repo scope
- `test_drain.py` (270 lines) — bounded drain, stranded-payload cleanup, large-backlog inventory reuse
- `test_failures.py` (348 lines) — mixed-queue quarantine, retire, doctor drop

The facade re-exports only public test names. `_fail_git` stays private in `test_enqueue.py`. Monkeypatch targets still point at production modules.

**Verification**

- `just _lint-symvision` — pass
- `just _lint-mypy` — pass
- `just _lint-toobig` — the new files are all under 500; the remaining error is the untouched `tests/monitor/test_monitor_start_stage.py` (1163 lines)
- Direct pytest of the split package — 8 passed
- `sase tool run check` then `sase tool run -k check` — 59241 passed; 4 failures are outside this split:
  - 3 in `tests/test_macro_input_schemas.py` (`wait_target` catalog drift; same as `_lint-flags`)
  - 1 in `tests/agents_sync/test_cli_names.py` (`handle_agents_sync` used without an import, from the earlier CLI test split)
