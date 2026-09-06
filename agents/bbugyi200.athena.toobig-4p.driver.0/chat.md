# Chat History - ace-run (toobig-4p.driver.0)

- **TIMESTAMP:** 2026-09-06 08:06:41 EDT
- **MODEL:** claude/sonnet
- **AGENT:** toobig-4p.driver.0

## Prompt

%id:toobig-4p.driver.0
%clan(toobig-4p, tribe=chop, summary=[[[bold #D75FFF]◆ TOOBIG SPLIT · 2 FILES[/bold #D75FFF]
[bold #87D7FF]MISSION[/bold #87D7FF]
[dim #D7D7FF]Decompose oversized Python modules into focused, reviewable units[/dim #D7D7FF]
[dim #D7D7FF]without changing behavior.[/dim #D7D7FF]

[bold #87D7FF]TARGETS[/bold #87D7FF]
[bold #FFAF5F]◆ 916  tests/perf/bench_prompt_search.py[/bold #FFAF5F]
[bold #FFAF5F]◆ 855  src/sase/migration_kit/driver.py[/bold #FFAF5F]

[dim #A8A8A8]2 scan roots · limits 1,000 / 850 / 700 lines · sequential queue[/dim #A8A8A8]]])
%model:@medium
%auto
%wait(runners=3)
%wait(priority=20)
#gh:gh_sase-org__sase
Can you help me split the `src/sase/migration_kit/driver.py` file up into multiple files? Use your best
judgement, but let's aim to keep all files <=500 lines of code.

## Response

No monkeypatching of private driver internals — good, that gives freedom to relocate helpers freely. Let me check the `sase/memory/lint_and_test.md` note since I've changed files, and also check how other migration_kit modules are organized (e.g., `operations/` package) for naming conventions to follow.

Those are expected transient warnings since `driver.py` hasn't been updated to import from these new modules yet. Continuing with the remaining files.

Expected until driver.py wires them up. Now the preflight module and the rewritten driver.py.

Now rewriting `driver.py` to keep just the public API and constants, wired to the new helper modules.

Now let's check line counts and run diagnostics/lint/tests.

Ruff is clean. Let me confirm pyright resolves fine too (likely just a stale-cache diagnostic from the editor since the files were just created).

Imports resolve correctly. Now let's run the actual test suite for migration_kit driver.

All tests pass. Let's also run the migrate_handler tests (its consumer) and a broader migration_kit test pass, plus check for other files referencing driver internals I might've missed.

All relevant tests pass. Now let's check the `lint_and_test.md` reference memory since I've modified files in this repo, per the project's CLAUDE.md requirement.

I need to run `just check` (agent default). Let's run it inline since it's typically quick, but I'll monitor if it takes long.

Symvision flags cross-module imports of underscore-prefixed names. Let me check the symvision reference memory for the correct fix pattern.

The symvision lint gate forbids importing underscore-prefixed (private) names across files — the sanctioned fix is to make the cross-module helpers public (drop the leading underscore), keeping single-file-only helpers private. Let me apply that.

The renames applied correctly, matching my plan exactly. Now update `driver.py`'s imports and call sites to use the new public names.

We're already inside that directory from the earlier `cd`. Let me just run the rename directly here.

Now let's return to the repo root and run formatting/lint fixups to resort the import blocks.

Now let's rerun `just check`.

`just check` passes cleanly (exit 0) — all lint gates green including symvision, and the scoped test lane passed. The file split is complete and verified.

Split `src/sase/migration_kit/driver.py` (855 lines) into six files, all well under 500 lines, organized by responsibility:

- **`driver.py`** (478 lines) — the public API: `MigrationCommandOutcome` re-export and the six command entry points (`list_operations`, `plan_operation`, `run_manifest`, `resume_run`, `status_runs`, `verify_run`)
- **`driver_outcome.py`** (37) — the `MigrationCommandOutcome` dataclass
- **`driver_context.py`** (69) — operation resolution and per-run `OperationContext` building
- **`driver_manifest.py`** (158) — manifest construction, loading/parsing, and host/repo identity
- **`driver_backup.py`** (82) — backup-record construction and checksum verification
- **`driver_preflight.py`** (110) — preflight validation and journal-state bookkeeping (plus the `ABORT_AFTER_ARCHIVES_ENV_VAR` constant)

Helpers used only within their own file kept their `_` prefix; ones consumed by `driver.py` across module boundaries had the leading underscore dropped, since this repo's symvision lint gate forbids importing private names cross-file. `just check` now passes clean (all lint gates including symvision, plus the escalated full test suite), and the existing external consumers (`migrate_handler.py`, the driver/synthetic-matrix tests) needed no changes since they only ever imported the public names from `sase.migration_kit.driver`.

All paths are this run's own new files, so this is a straightforward commit. Building the manifest now.

Declaration submitted successfully — the host finalizer will commit the six-file `driver.py` split.
