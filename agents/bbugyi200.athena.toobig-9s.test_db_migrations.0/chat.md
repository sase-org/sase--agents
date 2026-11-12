# Chat History - ace-run (toobig-9s.test_db_migrations.0)

- **TIMESTAMP:** 2026-11-12 11:30:37 EST
- **MODEL:** muse/muse-spark-1.3-contributor
- **AGENT:** toobig-9s.test_db_migrations.0

## Prompt

%auto
%id(test_db_migrations.0, clan=toobig-9s)
%model:@medium
%queue(capacity=5)
#gh:gh_sase-org__sase Can you help me split the `tests/test_bead/test_db_migrations.py` file into multiple files? Use your best
%wait:toobig-9s.processor.0
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

Done. Split the 764-line module into two focused modules plus a facade, each under 500 lines.

- [Migration facade](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/tests/test_bead/test_db_migrations.py:1) (23 lines): re-exports `TestMigrationAddsColumn`, `TestSizeConstraintMigration`, `TestStatusConstraintMigration`, `TestIssueTypeRebuildRestartability` with `__test__ = False` and `__all__`, so the original import path keeps working.
- [Adds-column tests](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/tests/test_bead/test_db_migrations_adds_column.py:1) (369 lines): `TestMigrationAddsColumn` with its local `_`-private column constants and `_flag_era_schema`.
- [Rebuild tests](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/tests/test_bead/test_db_migrations_rebuild.py:1) (423 lines): size, status, and restartability classes with local `_SIZE_COLUMN_DEFINITION` and `_assert_columns_survive_rebuild`. No `_`-prefixed imports cross between the new modules; the size/status helper stays in-file since both consumers moved together.

Monkeypatch targets unchanged: the rebuild module still patches `sase.bead.db.connect` and `run_migrations` via the same `bead_db` import.

Verification observed: `just _lint-symvision`, `just _lint-mypy`, and `just _lint-toobig` each exit 0; targeted pytest shows 14 passed with no duplicate collection via the facade; `ruff check` and `ruff format --check` pass after one `just fmt` fix; `sase tool run check` succeeded (run `a85db41e`, scoped tests green).
