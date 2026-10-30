# Chat History - ace-run (toobig-8v.migration.0)

- **TIMESTAMP:** 2026-10-30 09:02:21 EDT
- **MODEL:** muse/muse-spark-1.3-contributor
- **AGENT:** toobig-8v.migration.0

## Prompt

Your previous attempt hit a model context limit or transient provider failure. Any file edits, new tests, and other on-disk changes you made are preserved. Before making additional changes, run `git status` and `git diff` to see what is already in place, then continue implementing the plan from wherever you left off. Do not re-apply edits that are already present.

%id:toobig-8v.migration.0
%clan(toobig-8v, tribe=chop, summary=[[[bold #D75FFF]◆ TOOBIG SPLIT · 8 FILES[/bold #D75FFF]
[bold #87D7FF]MISSION[/bold #87D7FF]
[dim #D7D7FF]Decompose oversized Python modules into focused, reviewable units[/dim #D7D7FF]
[dim #D7D7FF]without changing behavior.[/dim #D7D7FF]

[bold #87D7FF]TARGETS[/bold #87D7FF]
[#87D7FF]• 824  src/sase/axe/run_agent_exec_staged.py[/#87D7FF]
[#87D7FF]• 774  src/sase/finalizers/declaration.py[/#87D7FF]
[#87D7FF]• 773  src/sase/main/workspace_handler_maintenance.py[/#87D7FF]
[#87D7FF]• 763  src/sase/agents_sync/prompt_archive/migration.py[/#87D7FF]
[#87D7FF]• 756  src/sase/gate_turn/reclaim.py[/#87D7FF]
[#87D7FF]• 739  src/sase/core/tool_run.py[/#87D7FF]
[#87D7FF]• 707  src/sase/ace/tui/widgets/_agent_list_render_rail.py[/#87D7FF]
[#87D7FF]• 707  tests/ace/tui/util/test_gc_policy.py[/#87D7FF]

[dim #A8A8A8]2 scan roots · limits 1,000 / 850 / 700 lines · sequential queue[/dim #A8A8A8]]])
%model:@medium
%auto
%queue(capacity=5)
#gh:gh_sase-org__sase Can you help me split the `src/sase/agents_sync/prompt_archive/migration.py` file into multiple files? Use your best
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

Done. Split `src/sase/agents_sync/prompt_archive/migration.py` (763 lines) into a `migration/` package, largest file 267 lines.

New layout, in [migration/](src/sase/agents_sync/prompt_archive/migration/):

- [`__init__.py`](src/sase/agents_sync/prompt_archive/migration/__init__.py) — facade re-exporting only `migrate_prompt_archive`, so the public import path is unchanged.
- [`_common.py`](src/sase/agents_sync/prompt_archive/migration/_common.py) — private module holding the shared public names: `PromptMigrationSkip`, `PromptMigrationReport`, `MigrationItem`, `relpath`.
- [`planning.py`](src/sase/agents_sync/prompt_archive/migration/planning.py) — public `plan_items`, `filter_publishable_migration_items`; single-use helpers stayed private in-file.
- [`apply.py`](src/sase/agents_sync/prompt_archive/migration/apply.py) — public `apply_month`; `_commit_paths` and `_atomic_write` stayed private in-file.
- [`publishing.py`](src/sase/agents_sync/prompt_archive/migration/publishing.py) — public `publish_migration_sidecars`; recovery helpers stayed private in-file.
- [`orchestration.py`](src/sase/agents_sync/prompt_archive/migration/orchestration.py) — public `migrate_prompt_archive`; repository/retargeted-test entry `_migrate_prompt_archive_repositories` stayed private in-file.

No `_`-prefixed name is imported across modules. Retargeted the two test imports to the new homes ([migration tests](tests/agents_sync/test_prompt_archive_migration.py), [push-paths test](tests/agents_sync/test_publication_recovery/test_push_paths.py)); `cli_prompts.py` keeps using the facade unchanged.

Verification, all observed:

- `just _lint-symvision` — pass.
- `just _lint-mypy` — no issues in 6237 files.
- `just _lint-toobig` — no migration file flagged (all ≤267 lines). The single ERROR is `publication_state_repair.py` (1784 lines), untouched by this change and pre-existing.
- Targeted tests: 14 passed across the two migration test files.
- `sase tool run check` (run `6cb1b628…`) — every stage ✓ including `test (scoped)`, overall `succeeded exit=0`.

Declared commit for the migration split; host will preserve it after this turn.
