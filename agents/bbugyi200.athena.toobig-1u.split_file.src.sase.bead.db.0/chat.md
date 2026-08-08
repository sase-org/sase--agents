# Chat History - ace-run (toobig-1u.split_file.src.sase.bead.db.0)

- **TIMESTAMP:** 2026-08-06 21:23:35 EDT
- **MODEL:** claude/opus
- **AGENT:** toobig-1u.split_file.src.sase.bead.db.0

## Prompt

#gh:sase-org/sase
%id:toobig-1u.split_file.src.sase.bead.db.0
%clan(toobig-1u, tribe=chop, summary=[[[bold #D75FFF]◆ TOOBIG SPLIT · 1 FILE[/bold #D75FFF]
[bold #87D7FF]MISSION[/bold #87D7FF]
[dim #D7D7FF]Decompose oversized Python modules into focused, reviewable units[/dim #D7D7FF]
[dim #D7D7FF]without changing behavior.[/dim #D7D7FF]

[bold #87D7FF]TARGETS[/bold #87D7FF]
[#87D7FF]• 709  src/sase/bead/db.py[/#87D7FF]

[dim #A8A8A8]2 scan roots · limits 1,000 / 850 / 700 lines · sequential queue[/dim #A8A8A8]]])
%wait(runners=3)
%auto %wait(priority=20) Can you help me split the `src/sase/bead/db.py` file up into multiple files? Use your best judgement, but let's aim to keep
all files <=500 lines of code.

## Response

I'll start by looking at the file.

Now I'll create the split modules.

Now the migrations module:

Now update the tests that referenced `_SCHEMA`:

All gates pass. Here's the split:

| File | Lines | Contents |
|---|---|---|
| `src/sase/bead/db.py` | 248 | Public API: `init_db`, `create_issue`, `get_issue`, `list_issues`, `update_issue`, `add_dependency`, `delete_dependencies_not_in`, `get_epic_children`, `stats` |
| `src/sase/bead/_db_migrations.py` | 240 | All `_migrate_*` functions behind one public `run_migrations(conn)`, which owns the order-sensitive call sequence and its comments |
| `src/sase/bead/_db_schema.py` | 88 | `SCHEMA_SQL` DDL + `connect()` |
| `src/sase/bead/_db_codec.py` | 84 | JSON column encoders/decoders (`plus_one_evidence_json`, `close_history_json`, `snooze_json`, and their `*_from_json` inverses) |
| `src/sase/bead/_db_rows.py` | 78 | `row_to_issue`, `load_dependencies`, plus `rows_to_issues` |

Notes on the choices:

- Private module names (`_db_*`) match the package's existing convention (`_project_store.py`, `_sync_git.py`). Symbols crossing module boundaries had to become public to satisfy symvision's "private symbols must not be imported across files" rule — hence `_SCHEMA` → `_db_schema.SCHEMA_SQL`, `_connect` → `connect`, `_row_to_issue` → `row_to_issue`, etc. Each has a real non-test consumer.
- The three `list_issues`/`get_epic_children`-style row loops were identical, so they collapsed into `rows_to_issues`. Each `_migrate_*` also repeated the same `PRAGMA table_info` / `sqlite_master` lookups; those are now `_columns()` and `_create_table_sql()` helpers inside the migrations module.
- `jsonl.py` now imports the three JSON encoders directly from `_db_codec` rather than reaching through `db_mod`, avoiding a re-export that ruff would flag as unused.
- Tests referencing `_SCHEMA` (`test_db_migrations.py`, `test_close_history_storage.py`, `test_snooze_storage.py`) were updated to `SCHEMA_SQL` from `sase.bead._db_schema`.

`just check` is green end to end (fmt, ruff, mypy, symvision, toobig, scoped tests — 365 files selected).

Gates are green. Committing now.

Committed and pushed; working tree is clean and level with `origin/master`.

**What the split looks like:**

| File | Lines | Contents |
|---|---|---|
| `src/sase/bead/db.py` | 248 | Public API: `init_db`, `create_issue`, `get_issue`, `list_issues`, `update_issue`, `add_dependency`, `delete_dependencies_not_in`, `get_epic_children`, `stats` |
| `src/sase/bead/_db_migrations.py` | 240 | All `_migrate_*` steps behind one `run_migrations(conn)` that owns the order-sensitive sequence |
| `src/sase/bead/_db_schema.py` | 88 | `SCHEMA_SQL` DDL + `connect()` |
| `src/sase/bead/_db_codec.py` | 84 | JSON column encoders/decoders (plus-one evidence, close history, snooze) |
| `src/sase/bead/_db_rows.py` | 78 | `row_to_issue`, `rows_to_issues`, `load_dependencies` |

Notes:
- `_db_*` naming matches the package's existing convention (`_project_store.py`, `_sync_git.py`). Symbols crossing module boundaries became public to satisfy symvision's cross-file private-import rule — `_SCHEMA` → `SCHEMA_SQL`, `_connect` → `connect`, `_row_to_issue` → `row_to_issue`.
- Three identical row-hydration loops collapsed into `rows_to_issues`; repeated `PRAGMA table_info` / `sqlite_master` lookups in the migrations became local `_columns()` / `_create_table_sql()` helpers.
- `jsonl.py` now imports the encoders from `_db_codec` directly rather than through `db`.
- Tests referencing `_SCHEMA` were updated to import `SCHEMA_SQL` from `sase.bead._db_schema`.

`just check` was green end to end before the commit (fmt, ruff, mypy, symvision, toobig, scoped tests — 365 files selected).
