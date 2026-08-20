# Chat History - ace-run (sase-r6.4)

- **TIMESTAMP:** 2026-08-19 21:08:08 EDT
- **MODEL:** grok/grok-4.6
- **AGENT:** sase-r6.4

## Prompt

#gh:gh_sase-org__sase
%id(4, clan=sase-r6, bead=sase-r6.4)
%model:@medium
%auto
%w:sase-r6.3
%w(bead=sase-r6.3)
Can you complete the work for bead sase-r6.4? The bead is already reserved for you and assigned to your agent
name: it was set to status=in_progress before you started reading this, either by the `sase bead work` launch
checkpoint or by the runtime promoting an ad-hoc wait-time claim. Do not set the status by hand. Read its
description and design file, do the work, and close only this bead with
`sase bead close sase-r6.4 --note "<what you verified>"`. Before closing, run
`sase bead epic-symbols sase-r6.4`. If this phase still has `--epic-symbol` entries, resolve each symbol or
re-key the Justfile line to a still-open bead (the parent epic or a later phase). `sase bead close` refuses while
leftovers remain; they go stale the instant this phase closes and turn unrelated agents' `just check` red. Closing
an assigned phase bead is unaffected by the parent-close descendant guard. Do NOT close the parent epic or any ancestor plan bead. Any instruction in a phase
description or child plan to close an ancestor is preparation and evidence for that ancestor's land agent, not
authorization for a phase worker. Do not create beads yourself: record discovered follow-up work as a
`PROPOSED FOLLOW-UP:` entry via
`sase bead note sase-r6.4 'PROPOSED FOLLOW-UP: <one-line summary — detail>'`; the epic's land agent triages
these into task beads.

## Response

I'll start by reading the bead, its design, and the beads memory so I can finish only `sase-r6.4` without touching the parent epic.

I'll load beads memory and inspect `sase-r6.4` next so the phase work is grounded in the official description.

The phase is keybindings for Artifacts Ctrl+J/K. I’ll read the epic plan and prior phases next.

This phase adds Artifacts Ctrl+J/K, so I’ll read TUI performance notes and map the current keymap and pane query paths.

I’ll inspect the keymap and artifacts-query plumbing next so the new chords can reuse the existing commit path.

I’ll fan out across query-commit, keymaps, and snapshot-growth so the new actions can reuse those seams.

I'll search the codebase for artifacts snapshot loading, query limits, and the related tests.

I'll

 search the TUI

 for how Art

ifacts panes commit queries

, including filter sessions, history, and selection restore.

I'll map the keymap wiring end-to-end, starting with config, AppKeymaps, command catalog, and the existing metadata-section bindings.

Next I’ll read the snapshot

 loaders,

 query

-commit path

, and limit-

growth

 helpers.

Query-commit is enough for Stitches, Beads, Patches, and provider re-slices. Files need the existing `full=True` worker when the cap exceeds an incomplete first page. Plans must not load archive on the UI thread.

## 1. Files first page / `full=True` / `complete` / worker

**Constants and loader** — `/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/src/sase/ace/tui/widgets/artifacts/files_data.py`

- `FILES_FIRST_PAGE_LIMIT = 500`
- `load_files_snapshot(project, limit)` queries `query_artifact_files(..., limit=limit)`, merges ref versions, then `_merge_rows` slices `rows[:limit]`.
- `FilesSnapshot.complete = (limit is None or len(rows) < limit)` (so exactly 500 rows with limit 500 is incomplete).

**Worker path** — `/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/src/sase/

ace/tui

/widgets/artifacts

/snapshot_pane

.py`



- `Artifacts

SnapshotPane._request_snapshot(force, full=False

)` runs

 `_

build_snapshot`

 on

 a **thread** worker (`thread=True`). Never on the event loop (`_collects_snapshots_on_event_loop = False`).
- `SnapshotRequest.full` is the grow flag. In-flight requests coalesce via `_full_pending`.

**Files pane** — `/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/src/sase/ace/tui/widgets/artifacts/files_pane.py`

| Function | Behavior |
|---|---|
| `_request_load(force, full)` | Forwards to `_request_snapshot` |
| `_build_snapshot` | `load_files_snapshot(project, None if request.full else FILES_FIRST_PAGE_LIMIT)` |
| `_apply_snapshot` | If `not request.full and not snapshot.complete and no load_error` → `_schedule_full_extension` |
| `_schedule_full_extension` | `asyncio.sleep(0)`, then `_request_load(force=False, full=True)` |

First activate / scope / refresh always start with `full=False` (the 500-row page). Incomplete first pages **always** schedule unbounded extension, **independent of `values.limit`**.

**Slice after load** — `FilesOptionsMixin._filtered_snapshot` in `files_options.py`:

```230:253:/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/src/

sase/ace

/tui/widgets/artifacts/files_options.py
    def _filtered_snapshot(...):
        ...
        rows, truncated = apply_limit(rows, values.limit)
```

It does **not** look at `snapshot.complete`. If 500 rows are loaded and the cap is 600, `apply_limit` reports `truncated=False`, so the bar can look exact while more files exist.

**Grow when cap exceeds the loaded page:** reuse `_request_load(force=False, full=True)` (same path as `_schedule_full_extension`), then slice. There is no separate grow API.

---

## 2. Stitches collection

 and

 `values.limit

`

`/

home/bryan/.

local/state/

sase/workspaces

/sase-org/sase

/sase_

15/src/sase/ace

/tui/

widgets/artifacts/

commits_collection.py

`

- `_collect

` → `_backend

_collection_limit

(spec.filters

)` → `self

._collector(..., limit=collection_limit, ...)`.
- `_backend_collection_limit`: `0` (unlimited git log) if `values.text` or excluded authors/text exist; otherwise **`values.limit`**.
- Authoritative cache key is `(scope_key, filters)` including limit. Different limit ⇒ cache miss.
- `snapshot_covers` treats `potentially_truncated` as not covering; backend constraints ignore limit, so a non-truncated smaller collection can cover a larger cap (then UI slices).

Display slice: `CommitsFilteringMixin._filtered_result` (`commits_filtering.py`) does `commits[: values.limit]` and sets `aggregate_truncated` when clipped.

Commit path: `CommitsFilteringMixin._commit_filter_values` always `_schedule_collection()` unless an in-flight worker already matches that exact `values`. Live pause path `_reconcile_live_filter` does the same.

**Query-commit is sufficient for Stitches.** Collection already follows `values.limit`.

---

## 3. Plans deep-archive worker

Preview snapshot (`load_plans_snapshot` in `plans_data.py`) is **not** driven by query limit:

- `_ARCHIVE_PER_PROJECT_LIMIT = 50`
- `_ARCHIVE_MERGED_LIMIT = 100`
- `archive_truncated` is the lower-bound flag

Deep archive (`plans_deep_archive.py` + `plans_filter_session.py`):

| Function | Role |
|---|---|
| `make_deep_archive_request` | Built only if `archive_truncated`, query can reach archive, and **session open or `not values.is_empty`** |
| `PlansFilterSessionMixin._schedule_deep_archive` | Cache / debounce / launch |
| `_launch_deep_archive` | `run_worker(load_deep_archive_result, thread=True, group="artifacts-plans-deep-archive")` |
| `load_deep_archive_result` | `load_deep_plan_archive` at `DEEP_ARCHIVE_PER_PROJECT_LIMIT = 500` per project, then index/

eval off-thread |

`PlanFilterValues.is_empty` **ignores `limit`**. Default/limit-only queries are empty.

Submit (`on_plan_filter_bar_submitted`) **closes the session first**, then `_schedule_deep_archive(values)`. For a limit-only rewrite that means `filter_session_open=False` and `is_empty=True` → request is `None` → worker is invalidated.

`plans_options._refresh_options` `apply_limit`s the in-memory index, then if a deep result exists, fills remaining slots:

`remaining = max(0, values.limit - len(non_archive_records))`.

Coverage stays a lower bound (`newest 500 searched` when `DeepArchiveResult.capped`).

**Do not load archive on the UI thread.** Let `_schedule_deep_archive` / `_launch_deep_archive` extend. Do not grow the main snapshot for a higher cap.

---

## 4. How a higher-limit commit reloads today

There is no host `Ctrl+J` / `adjust_limit` action on Artifacts yet. `adjust_limit` / `replace_limit` live in `limit_token.py`; only Patches uses `replace_limit` (canonicalization). Growth today is “rewrite `limit:` and submit the filter bar.”

| Pane | Submit handler | Reload? |
|---|---|---|
| Files | `FilesFilterSessionMixin.on_file_filter_bar_submitted` | Sets `self.filters`,

 `_refresh_options

` only. **

No** `_request

_load`. |


| Beads

 | `

BeadsFilterSessionMixin

.on_bead

_filter_bar

_submitted` |

 Same:

 `_refresh_options` only. |
| Plans | `PlansFilterSessionMixin.on_plan_filter_bar_submitted` | `_refresh_options` + `_schedule_deep_archive`. No `_request_load`. |
| Stitches | `on_commit_filter_bar_submitted` → `_commit_filter_values` | `_schedule_collection` on cache miss. |
| Patches | `PatchesFilterSessionMixin.on_patch_filter_bar_submitted` → `PatchFilterSessionActionsMixin._commit_patch_query` | `_load_patches()` then `_filter_patches_impl` + `apply_limit`. |

---

## 5. Is query-commit enough? Extra grow calls?

**No new grow function exists or is needed.** Reuse existing workers.

| Pane | Commit alone? | Extra call |
|---|---|---|
| **Files** | **Not if cap > loaded rows and `complete is False`.** Submit only re-slices. Auto-extension already does `full=True` after an incomplete first page, even for `limit:100`. If you grow *on cap* (or extension was cancelled), call `_request_load(force=False, full=True)` then `apply_limit`. |
| **Stitches** | **Yes.** `_commit_filter_values` collects with `values.limit`. |
| **Plans** | **Do not grow the preview snapshot.** If `archive_truncated`, schedule the existing worker; never `load_deep_

plan_archive`

 on the UI thread

. Limit

-only commit

 after close currently **does not** keep the worker (`is_empty`). Membership queries do. |
| **Beads** | **Yes.** `load_beads_snapshot` is

 the full in-memory corpus; `_refresh_options` + `apply_limit`. |
| **Patches

** | **Yes.** `_all_patches` / `_load_patches` then `apply_limit`. |
| **Providers** | Same as Plans (`plans_pane._build_snapshot` / `load_plans_snapshot` with `provider_kind`). Re-slice in-memory rows; archive via the same worker. |

---

## 6. `apply_limit` / `extract_limit` after r6.3

Host helpers: `/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/src/sase/ace/query/limit_token.py`

- `extract_limit` / `extract_limit_as` — strip `limit:` before dialect parse / Rust eval.
- `apply_limit(items, cap)` — `(sliced, truncated)`; `cap is None` is unlimited.
- `ensure_limit` — default `limit:<page_size>` when absent.
- `replace_limit` / `adjust_limit` — rewrite / ± page_size (Patches canonicalization; tests only for `adjust_limit` so far).

**Extract (membership remainder):**

- Beads: `parse_bead_filter_query` → `extract_limit_as`
- Plans: `parse_plan_filter_query` → `extract_limit_as`
- Files: `parse_files_filter_

query` → `extract_limit_as`
- Patches: `_parse_patch_query` / `_canonical_patch_query` / `_filter_patches_impl

` → `extract_limit`
- Rust eval: `evaluate_artifact_query_many` in `query_profile_corpus_facade.py` strips limit again (`remainder, _cap = extract_limit(query)`).
- Also: `profile_reference.py`, `query_facade.py`, `_state_init_runtime.py`.

**Apply (presentation slice):**

- `files_options._filtered_snapshot`
- `plans_options._refresh_options` (plus remaining archive slots)
- `beads_options._refresh_options`
- `patch/_loading._

filter_patches_impl`
- Stitches uses `commits[: values.limit]` instead of `apply_limit` (same idea; `limit:0` / `all` is unlimited).

`is_empty` on Files/Plans/Beads **does not include limit**, so `limit:N` still uses the filter index and `apply_limit`.

---

## 7. Tests

| File | What it

 covers

 |
|---|---|
| `/home/bryan/.local

/state/sase/workspaces/sase-org/sase/sase_15/tests/ace/tui/test_artifacts_query_limit.py` | Default `limit:<page_size>`; dialect parse; `limit:all`; `ensure_limit` leaves user tokens; `

apply_limit` truncation; Patches strips limit before boolean eval; Files `limit` is not a membership field |
| `/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/tests/ace/test_limit_token.py` | `extract_limit` / `extract_limit_as` / `apply_limit` / `replace_limit` / `adjust_limit` |
| `/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/tests/ace/tui/test_artifacts_files_loading.py` | Loader `limit=500`; `complete`; first page paints then full extension (`requested_limits == [500, None]`) |
| `/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/tests/ace/tui/test_commits_pane_collection.py` |

 Collection

 `

limit`

 from query

; `limit:

all`;

 `snapshot_covers

`

 vs truncation |
|

 `/home/bryan

/.local/state

/s

ase/workspaces/

sase-org

/sase/sase_15/tests/ace/tui/test_commits_config.py` | Default `values.limit` |
| `/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/tests/ace/tui/test_artifacts_plans_filtering.py` | Deep-archive coverage label / `DEEP_ARCHIVE_PER_PROJECT_LIMIT` |

There is **no** test that committing a larger `limit:` requests Files `full=True` or grows Plans archive.

**Implementation takeaway:** committing a rewritten query is enough for Stitches (recollect), Beads/Patches/providers (re-slice). Files must additionally hit the existing `full=True` worker when `limit > len(snapshot.rows

)` and `not

 snapshot.complete`. Plans should only kick `_schedule_deep_archive`, never archive I/O on the UI thread.

There is **no shared “set this pane’s query” helper**. Each pane owns committed state, a live-session overlay, and a different commit function. Load-more/unload should be **string-level** (`extract_limit` → `adjust_limit` → `replace_limit`) on the **source query**, then dispatched into the pane’s existing commit path **without closing** an open session.

---

## Shared limit helpers (use these, do not reimplement)

`/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/src/sase/ace/query/limit_token.py`

```33:43:src/sase/ace/query/limit_token.py
def extract_limit(query: str) -> tuple[str, int | None]:
    """Return ``(remainder, cap)`` after removing a host ``limit:`` token.
    ``None`` means unlimited: the token is absent, ``limit:all``, or
    ``limit:0``.
```

```96:133:src/sase/ace/query/limit_token.py
def replace_limit(query: str, n: int) -> str:
    """Write a numeric ``limit:n``, preserving the rest of the query."""

def adjust_limit(
    current: int | None,
    page_size: int,
    direction: Literal["load_more", "unload"],
) -> int | None:
    """... Load-more on an unlimited cap is a no-op. Unload of unlimited
    introduces ``page_size``. Unload never rises a user-typed cap below
    ``page_size`` up to that floor...
```

Page size: `get_ace_page_size() -> int` in `src/sase/ace/config.py` (default `100`).

**No-op rule (already encoded):**

| direction | current cap | `adjust_limit` | rewrite? |
|---|---|---|---|
| `load_more` | `None` (unlimited / `limit:all` / `limit:0`) | `None` | **no-op** |
| `load_more` | `N` | `N + page_size` | rewrite |
| `unload` | `None` | `page_size` | **writes** `limit:page_size` |
| `unload` | `N >= page_size` | `max(page_size, N - page_size)` | rewrite unless already at floor |
| `unload` | `N < page_size` | `N` | **no-op** |

`replace_limit` cannot emit `limit:all`. Compare `old_cap == new_cap` **before** rewriting.

Tests: `tests/ace/test_limit_token.py` (`test_adjust_limit_floor_and_plus_minus_rules`, `test_replace_limit_overwrites_existing_token_in_place`).

---

## How each pane stores committed vs live query

### 1. Patches — **app-owned source string** (only pane with history/selections)

| | |
|---|---|
| Committed source | `AceApp.query_string` |
| Committed AST | `AceApp.parsed_query` |
| Canonical (includes `limit:`) | `AceApp.canonical_query_string` → `_canonical_patch_query` |
| Live (session open) | `AceApp._live_patch_query: tuple[str, QueryExpr] \| None` |
| Session flag | `ArtifactsPatchesPane._patch_filter_session_open` |
| Display helper | `_display_patch_query()` / `_display_patch_parsed_query()` |

```67:77:src/sase/ace/tui/actions/patch/_filter_session.py
def _display_patch_query(self) -> str:
    live = getattr(self, "_live_patch_query", None)
    return live[0] if live is not None else self.query_string

def _set_patch_live_query(self, source: str, parsed: QueryExpr) -> None:
    self._live_patch_query = (source, parsed)
    self._refilter_current_patch_snapshot()
```

Startup always injects a cap: `self.query_string = ensure_limit(query, get_ace_page_size())` in `src/sase/ace/tui/actions/_state_init_runtime.py`.

### 2. Beads — **typed values on the pane**

`BeadsFilterSessionMixin` in `src/sase/ace/tui/widgets/artifacts/beads_filter_session.py`

- `filters: BeadFilterValues` (committed; `.limit: int | None`)
- `_live_filter_values` / `_filter_session_open` / `_filter_restore_values` / `_filter_restore_selection`
- `_display_filter_values()` → live if session open else `filters`
- Source string is **not stored**; only `to_query_string(values)` (canonical token order)
- Default: `ensure_limit("-status:closed", page_size)` via `default_bead_filter_values()` in `src/sase/bead/filter_query.py`

### 3. Files — same shape as beads

`FilesFilterSessionMixin` in `src/sase/ace/tui/widgets/artifacts/files_filter_session.py`

- `filters: FilesFilterValues` (`.limit`)
- `_display_filter_values()`
- Default: `parse_files_filter_query(ensure_limit("", page_size))`
- Parse/render: `src/sase/ace/tui/widgets/artifacts/files_filtering.py`  
  `parse_files_filter_query(text) -> FilesFilterValues`  
  `to_query_string(values) -> str`

### 4. Plans **and document providers** — same mixin

`PlansFilterSessionMixin` in `src/sase/ace/tui/widgets/artifacts/plans_filter_session.py`

- Used by `ArtifactsDocumentsPane` (`pane_key` = contract id, e.g. `ref:plan` or a provider pane)
- `filters: PlanFilterValues` (`.limit`)
- Default: `parse_plan_filter_query(ensure_limit("", page_size))`
- Parse/render: `src/sase/plan_search/filter_query.py`
- Extra: deep-archive worker on filter change (`_schedule_deep_archive`)

App accessor: `ArtifactsPlansActionsMixin._active_documents_pane()` in `src/sase/ace/tui/actions/artifacts_plans.py` (not just `#artifacts-plans-pane`).

### 5. Stitches/commits — typed values + **`limit: 0` = unlimited**

`CommitsFilteringMixin` in `src/sase/ace/tui/widgets/artifacts/commits_filtering.py`

- `filters: CommitLogFilterValues`
- `UNLIMITED_COMMIT_LOG_LIMIT = 0` in `src/sase/vcs_log/filter_query.py`
- `to_query_string` **omits** `limit:` when `limit <= 0`
- Default query: `resolve_commits_default_query()` → `ensure_limit("sidecar:false merges:hide since:24h", page_size)` (`src/sase/ace/tui/widgets/artifacts/commit_config.py`)
- “Chips” here are **query tokens**, not a separate chip widget:

```167:171:src/sase/ace/tui/widgets/artifacts/commits_rendering.py
def commit_filter_chips(filters: CommitLogFilterValues) -> tuple[str, ...]:
    """Return active filters in the same vocabulary as the query language."""
    return to_query_tokens(filters)
```

Closed persistent bars on **every** pane are syntax-highlighted query text (`FilterBar._closed_display_text` → `highlight_query`), not clickable chips.

### 6. Chats

No live `chats_filter_session.py` source in this tree. Do not invent a chats path.

---

## Commit / apply path (user submit)

### FilterBar contract (`src/sase/ace/tui/widgets/filter_bar.py`)

```208:258:src/sase/ace/tui/widgets/filter_bar.py
def open(self, prefill: str) -> None: ...
def close(self) -> None: ...
def set_query(self, text: str) -> None:
    """Replace displayed text without emitting a user-edit message."""
    self._last_query_text = text
    # then editor.load_text(text)
```

`set_query` sets `_last_query_text` **before** `load_text`, so it does **not** emit `QueryChanged`. That is how you update an open editor.

All Artifacts bars are `PERSISTENT = True` (`patch_filter_bar.py`, `bead_filter_bar.py`, `file_filter_bar.py`, `plan_filter_bar.py`, `commit_filter_bar.py`).

### Patches

`PatchesFilterSessionMixin` — `src/sase/ace/tui/widgets/artifacts/patches_filter_session.py`

| Event | Method | Effect |
|---|---|---|
| `/` / click | `show_filters()` | snapshots `app.query_string` + selection; `bar.open(app.query_string)` |
| type | `on_patch_filter_bar_query_changed` | `app._set_patch_live_query(text, parsed)` (in-memory refilter) |
| Enter | `on_patch_filter_bar_submitted` | `app._commit_patch_query(event.text)` then **close session** |
| Esc | `on_patch_filter_bar_dismissed` | `app._clear_patch_live_query()`; restore selection |

**Commit seam (do not close session yourself):**

```96:132:src/sase/ace/tui/actions/patch/_filter_session.py
def _commit_patch_query(self, source: str, *, notify: bool = True) -> None:
    new_parsed = self._parse_patch_query(source)
    new_canonical = self._canonical_patch_query(source, new_parsed)
    current_canonical = self.canonical_query_string
    self._live_patch_query = None
    if new_canonical == current_canonical:
        ...
        return
    self._save_selection_for_current_query()
    push_to_prev_stack(...)          # history
    save_query_history("patches", stacks)
    self.query_string = source
    self.parsed_query = new_parsed
    self._load_patches()             # sync disk I/O
    self._restore_selection_for_current_query()
    self._save_current_query()       # last_query.txt
    if notify:
        self.notify("Query updated")
```

Signatures:

```python
def _parse_patch_query(self, source: str) -> QueryExpr
def _canonical_patch_query(self, source: str, parsed: QueryExpr) -> str
def _commit_patch_query(self, source: str, *, notify: bool = True) -> None
```

`#N query` save-slot grammar is patches-only; load-more must not look like `#…`.

### Beads / Files / Plans (same pattern, no history)

Submit handlers (beads shown; files/plans are clones):

```101:120:src/sase/ace/tui/widgets/artifacts/beads_filter_session.py
def on_bead_filter_bar_submitted(self, event: BeadFilterBar.Submitted) -> None:
    values = parse_bead_

filter_query(event.text

)
    self.filters =

 values
    self._live

_filter_values = values


    preferred_id =

 self._selected_option_

id()
    self._

close_filter_session()


    self._refresh_

options(preferred_id=

preferred_id)
    self

.focus_list()
```



There is **no** `_commit_*_query` helper. Programmatic apply = parse → assign `filters` → `_refresh_options(preferred_*)` and **do not** call `_close_filter_session()`.

Idle bar text is written only when the session is **closed**:

```258:260:src/sase/ace/tui/widgets/artifacts/beads_options.py
        if not self._filter_session_open:
            bar.set_query(to_query_string(self.filters))
```

If the editor is open you **must** call `bar.set_query(...)` yourself.

### Stitches — the only other real commit helper

```384:442:src/sase/ace/tui/widgets/artifacts/commits_filtering.py
def _commit_filter_values(
    self,
    values: CommitLogFilterValues,
    *,
    close_session: bool,
) -> None:
    ...
    self._live_filter_values = values
    self.filters = values
    self.query_one(CommitFilterBar).set_query(to_query_string(values))
    if close_session:
        self._close_filter_session()
        ...
    # then cache / preview / _schedule_collection()
```

Submit uses `close_session=True`. Programmatic facet toggles already use `close_session=False` — **this is the load-more pattern**:

```345:349:src/sase/

ace/tui/widgets

/artifacts/commits_pane

.py
def toggle_sdd(self) -> None:
    self._commit_filter_values(
        replace(self.filters, sidecar=not self.filters.sidecar),
        close_session=False,
    )
```

Same for `cycle_merges`, `toggle_all_projects`, `set_project_scope`.

---

## History (`prev_query` / `next_query`) — **patches only**

`PatchQueryMixin` in `src/sase/ace/tui/actions/patch/_query.py`

```239:273:src/sase/ace/tui/actions/patch/_query.py
def action_prev_query(self) -> None:
    pane_id = getattr(self, "current_artifacts_pane_key", "patches")
    if self.current_tab != "artifacts" or pane_id != "patches":
        return
    ...
    prev_record = navigate_prev(current_record, stacks)
    self.parsed_query = self._parse_patch_query(prev_record.source)
    self.query_string = prev_record.source
    self._load_query_patches()
    self._restore_selection_for_current_query()
    self._save_current_query()
    save_query_history(pane_id, stacks)
```

`action_next_query` is the same with `navigate_next`.

Storage: `src/sase/ace/query_history.py`

```

python
@dataclass
class QueryHistoryStacks:
    prev: list[QueryRecord]
    next: list[QueryRecord]

def push_to_prev_stack(current: QueryRecord, stacks: QueryHistoryStacks) -> None
def navigate_prev(current: QueryRecord, stacks: QueryHistoryStacks) -> QueryRecord | None
def navigate_next(...) -> QueryRecord | None
def save_query_history(pane_id: str, stacks: QueryHistoryStacks) -> bool  # JSON I/O
```

`_commit_patch_query` **does** push history when canonical changes. Other panes have **no** history stacks in

 `_

query_history` (only `"patches

"` is

 loaded

 in

 `_

state_

init_late.py

`).

`

QUERY_HISTORY` capability

 in `_artifact_

tab_actions.py` currently maps to `("edit_query",)` — not a shared prev/next API.

---

## Reveal-lens restoration (patches only, implicit)

`src/sase/ace/relation_reveal.py`

The lens is **not** a flag. It stays live iff `reveal.revealed_canonical == current_canonical`.

```110:126:src/sase/ace/relation_reveal.py
def is_relation_reveal_active(reveal, *, pane_id, current_canonical) -> bool:
    ...
    if reveal.revealed_canonical != current_canonical:
        return False
```

Relation jump (`_change_query_for_navigation` in `src/sase/ace/tui/actions/navigation/_tree.py`):

1. `push_to_prev_stack` of the composed query
2. set `query_string` to `ancestor:` / `sibling:` …
3. `_load_patches()` + select target
4. store `self._relation_reveals["patches"]`

`revealed_canonical` is `to_canonical_string(parsed)` — **no `limit:`**. Composed queries usually have `limit:100`. So:

- `prev_query` (`^`) restores the composed source → lens goes inactive because canonical moved. That is the advertised “return” path (`build_reveal_chip` in `src/sase/ace/tui/widgets/artifacts/shell.py`).
- **Load-more on a reveal query adds `limit:N` → canonical ≠ `revealed_canonical` → the ↩ chip vanishes.** `_commit_patch_query` does not touch `_relation_reveals`. If you need the lens to survive a cap change, update `revealed_canonical` or exclude `limit:` from the equality.

---

## Selection restore

### Patches (persistent, keyed by **canonical** query)

`src/sase/ace/tui/actions/patch/_core.py`

```478:511:src/sase/ace/tui/actions/patch/_core.py
def _save_selection_for_current_query(self) -> None:
    # _query_selections["patches"][canonical] = ArtifactEntryTarget.to_token()
    save_query_selections

(pane_id, selections)

def _

restore_selection_for_current_query(self)

 -> None:
    # lookup token for new canonical; set current_idx if still

 in list
```

Persistence: `src/sase/ace/query_selection.py` (`load_query_selections` / `save_query_selections`). Disk I/O on the UI thread.

Live refilter (`_refilter_current_patch_snapshot`) keeps `(project, name)` if

 still visible

.

### Beads

 / files / plans



In-session only

: `_refresh

_options(preferred_id=...)

` / `preferred_target

=...`.

 No

 `query_selections` map.

### Stitches

`CommitsTimeline.update_result` keeps `selected_entry_target` (repo + full SHA) across rebuilds (`commits_timeline.py:140-151`). No query-keyed persistence.

---

## How to read the “current” query for load-more

Prefer **source spelling** so `replace_limit` can rewrite the token in place.

```
if filter session open:
    source = bar._last_query_text   # raw editor; survives invalid mid-edit
    # patches also: app._display_patch_query()
    # others also:  to_query_string(pane._display_filter_values())  #

 CANONICALIZED
else:
    patches: app.query_string
    others: 

 to_query_string(pane.filters)
```

Then:

```python
old_cap = extract_limit(source)[1]          # may raise LimitTokenError
new_cap = adjust_limit(old_cap, get_ace_page_size(), direction)


if new_cap is None or new_cap == old_cap:
    return  # no rewrite
rewritten = replace_limit(source, new_cap)
# commit rewritten through the pane path below
```

**Do not** use `CommitLogFilterValues.limit` directly (`0` vs `None`). Always go through `extract_limit` on a query string.

---

## Best shared seam for load-more / unload

Put app actions on `ArtifactsMixin` (`src/sase/ace/tui/actions/artifacts.py`) and dispatch by `current_artifacts_pane_key`. Pane accessors already exist:

| Pane | Getter | Commit call |
|---|---|---|
| patches | `_artifacts_entry_navigator("patches")` + app | `_commit_patch_query(rewritten, notify=False)` then `PatchFilterBar.set_query(rewritten)` if `_patch_filter_session_open` |
| stitches | `_commits_pane()` | `parse_commit_filter_query(rewritten)` → `_commit_filter_values(values, close_session=False)` then **overwrite** `CommitFilterBar.set_query(rewritten)` (helper canonicalizes) |
| beads | `_beads_pane()` (browse mixin) | `parse_bead_filter_query` → `filters = values`; if session: `_live_filter_values

 = values`; `_refresh_

options(preferred_id=

…)`; if session: `Bead

FilterBar.set_query(rewritten)` |
| files | `_files_pane()`

 | same with `parse_files_filter_query` / `preferred_target` |
| plans + providers | `_active_documents_pane()` | same with `parse_plan_filter_query`; also

 `_schedule_deep_archive(values)` |

There is no protocol on `ArtifactEntryNavigator` for this. A thin per-pane `apply_query_string(source

, *, keep_session: bool)` would be new.

**Keep the session open.** Submit handlers close it; load-more should not. After commit, `set_query(rewritten)` so the editor matches.

Optional: after patches commit, re-set `_live_patch_query` if the bar is still open — `_commit_patch_query` **clears** `_live_patch_query`.

---

## Updating an open filter editor

```python
bar = pane.query_one(XxxFilterBar)
bar.set_query(rewritten)   # no QueryChanged
```

If you only assign `filters` and `_refresh_options`, an open session **will not** update the editor (`_sync_query_bar` skips `set_query` while `_filter_session_open`).

`_last_query_text` is the live editor source even mid-keystroke.

---

## Pitfalls

1. **No uniform commit API.** Patches = app `_commit_patch_query`. Stitches = `_commit_filter_values`. Others = assign `filters` + refresh.

2. **Stitches `limit: 0` vs host `None`.** String-level `extract_limit` is the only consistent view.

3. **Canonicalize vs in-place.** `

to_query_string` / `_commit_filter_values` reorder tokens (always emit `sidecar:` / `merges:`). If you care about original spelling, `set_query(rewritten)` after that helper.

4. **Patches history + last_query.** `_commit_patch_query` pushes prev

 stack, writes

 `query_history.json` and `last_query.txt`, and calls `_load_patches()` (sync disk). Other panes do none of that.

5. **Reveal lens dies if you change `limit:`** on a reveal query (canonical includes limit; `revealed_canonical` does not).

6. **Async workers (not UI-thread IO except patches):**
   - Beads/files/plans: `ArtifactQuerySession` thread worker; first `_refresh_options` may early-return (`pending_query`) and repaint when the worker finishes. Keep `preferred_id` from current selection.
   - Plans: extra deep-archive worker.
   - Stitches: `_schedule_collection` thread worker; raising `limit` may re-run `run_vcs_log`. `_backend_collection_limit` is `0` (unlimited collect) when text/exclusions exist, else `values.limit`.
   - **Do not** do git/snapshot I/O on the UI thread; collection/query already use workers. Patches `_load_patches` **is** UI-thread disk — existing debt.

7. **Live parse errors.** Open session + invalid text: patches keep last valid `_live_patch_query`; stitches roll the list back (`_show_filter_query_error`) but leave the editor. Prefer `_last_query_text`; `extract_limit` can raise — treat as no-op.

8. **`_commit_patch_query(notify=True)` toasts** `"Query updated"`. Load-more should pass `notify=False`.

9. **Document providers** share the plans filter session. Always use `_active_documents_pane()`, not `#artifacts-plans-pane`.

10. **`cycle_kind` (files)** closes an open session. Do not copy that for load-more.

11. **Jump-to-entry filter clear** (`_clear_filter_for_entry_jump`) wipes `filters` to empty (including limit) and closes the session.

 Unrelated,

 but don’t reuse it.

---

## Tests / patterns to copy

| File | What to steal |
|---|---|
| `tests/ace/test_limit_token.py` | `adjust_limit` / `replace_limit` / no-op table |
| `tests/ace/tui/test_patch_filter_bar.py` | `AcePage`, open bar, `Submitted`/`Dismissed`, history + `last_query.txt`; `_capped()` helper |
| `tests/ace/tui/test_artifacts_beads_filtering.py` | `test_committing_bead_query_updates_idle_bar` — submit + idle display

 |
| `tests/ace/tui/test_artifacts_files_filtering.py` | session-open click + `Submitted` |
| `tests/ace/tui/test_artifacts_plans_filtering.py` | plans session + submit |
| `tests/ace/tui/test_commits_pane_filters.py` | live vs dismiss restore; `_commit_filter_values` via typing |
| `tests/ace/tui/test_artifacts_scaffold.py` | `_commit_filter_values(..., close_session=False)` |
| `tests/ace/tui/test_relation_reveal_navigation.py` | `action_prev_query` restores composed query / lens |
| `tests/ace/tui/visual/test_ace_png_snapshots_commits.py` | `_commit_filter_query` helper |
| `tests/ace/tui/visual/test_ace_png_snapshots_artifacts_plans.py` | `_commit_plan_filter_query` |

Typical commit-from-test pattern:

```python
bar = pane.query_one(BeadFilterBar)
await page.press("/")
bar.set_query("tier:epic")
bar.post_message(BeadFilterBar.Submitted("tier:epic"))
await page.wait_for(lambda _state: not bar._editing)
```

For load-more tests: start from a capped default (`limit:100`), invoke the action, assert `filters.limit` / `query_string` / editor text, assert no-op at floor and at `limit:all`, and (patches) assert history only if you choose to go through `_commit_patch_query`.

Adding two app keys that share `ctrl+j`/`ctrl+k` with Agents metadata is a **tab-disjoint duplicate-key** pattern (`edit_query`/`search_forward` on `/`, `show_diff`/`toggle_axe_description` on `d`). Wire the fields, then gate them to Artifacts the same way metadata is gated to Agents. `loader.py` and `defaults.py` do **not** list field names.

---

### 1. `default_config.yml` (source of truth)

**File:** `/home/bryan/.local

/state/sase/workspaces/sase-org/sase/sase_15/src/sase/default_

config.yml`

Insert under

 `

ace.keymaps.app` **

Navigation**, immediately after the metadata pair (lines 409–412). Putting them in the **Artifacts split** block (418–423) is also fine; field order does not have to match `AppKeymaps`.

```409:423:/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/src/sase/default_config.yml
      next_agent_metadata_section: "ctrl+j"
      prev_agent_metadata_section: "ctrl+k"
      next_agent_file: "ctrl+n"
      prev_agent_file: "ctrl+p"
      # Tab switching
      next_tab: "tab"
      prev_tab: "shift+tab"
      cycle_artifacts_subtab: "right_square_bracket"
      cycle_artifacts_subtab_reverse: "left_square_bracket"
      # Artifacts split
      cycle_artifacts_split: "right_curly_bracket"
      cycle_artifacts_split_reverse: "left_curly_bracket"
      files_next_version: "right_parenthesis"
      files_prev_version: "left_parenthesis"
      pick_artifacts_project: "p"
```

**Minimal-drift snippet:**

```yaml
      artifacts_load_more: "ctrl+j"
      artifacts_unload: "ctrl+k"


```

Startup fails with `ValueError: default_config.yml missing app keymaps` if the YAML is omitted (`registry.py` 285–291). Shared defaults are allowed; conflict checks only fire on **user overrides**.

---

### 2. `AppKeymaps`, `_BINDING_META`, `DEFAULT_BINDINGS`

**`AppKeymaps`** — `/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/src/sase/ace/tui/keymaps/app_keymaps.py`  
Add fields next to the other Artifacts split keys (after

 `pick_artifacts_project` at line 40

),

 not next to metadata

 (26–27).

 No dataclass

 defaults.

```python
    artifacts_load_more: str
    artifacts_unload: str
```

**`_BINDING_META`** — `/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/src/sase/ace/tui/keymaps/metadata.py`  
Must cover **exactly** `AppKeymaps` fields (`types.py` 79–91 raises `RuntimeError` on mismatch). Place with other Artifacts rows (~59–65):

```python
    ("artifacts_load_more", "Load More Artifacts", False),
    ("artifacts_unload", "Unload Artifacts", False),
```

**`DEFAULT_BINDINGS`** — `/home/bryan/.local/state/sase/

workspaces/sase

-org/sase/sase_15/src/sase/ace/tui/bindings.py` 66–75  
Static fallback; tests compare it. Duplicate the metadata Binding shape:

```python
    Binding("ctrl+j", "artifacts_load_more", "Load More Artifacts", show=False),
    Binding("ctrl+k", "artifacts_unload", "Unload Artifacts", show=False),
```

**`keymaps/bindings.py` `build_app_bindings()`** (46–59) walks `_BINDING_META`; no extra list.

Action names **are** the Textual action ids: `action_artifacts_load_more` / `action_artifacts_unload`.

---

### 3. `loader.py` / `registry.py` / `

defaults.py`

| File | What to change |
| --- | --- |
| `src/sase/ace/tui/keymaps/defaults.py` | Nothing. `load_builtin_app_defaults()` reads `ace.keymaps.app` dynamically. |
| `src/sase/ace/tui/keymaps/loader.py` | Re-export shim only. |
| `src/sase/ace/tui/keymaps/registry.py` | **Do** add contextual-duplicate pairs (88–101). Field iteration is already `fields(AppKeymaps)`. |

**Required** so a user can

 remap both shared

 keys together without silent revert:

```87:101:/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/src/sase/ace/tui/keymaps/registry.py
# These app actions intentionally share a key because their tab applicability
# is disjoint: metadata search is Agents-only, while query editing excludes
# Agents. Preserve duplicate validation for every other app-action pairing.
_CONTEXTUAL_APP_DUPLICATES: frozenset[frozenset[str]] = frozenset(
    {
        frozenset({"edit_query", "search_forward"}),
        ...
        frozenset({"open_agent_cleanup_panel", "patches_toggle_reverted"}),
    }
)
```

Add:

```python
frozenset({"artifacts_load_more", "next_agent_metadata_section"}),
frozenset({"artifacts_unload", "prev_agent_metadata_section"}),
```

`types.py` 79–91 is an import-time `_BINDING_META` ↔ `AppKeymaps` guard; no extra names.

---

### 4. Command catalog / palette

**Metadata table** — `src/sase/ace/tui/commands/_app_metadata.py`  
Mirror `cycle_artifacts_subtab` (`CL_ONLY`) next to other Artifacts split entries (73–109), **not** the Agents metadata rows (39–51):

```python
    (
        "artifacts_load_more

",
        "

Artifacts: load more",
        "Navigation",
        CL_ONLY,
        ("load more", "page", "ctrl+j"),
    ),
    (
        "artifacts_unload",
        "Artifacts: unload",
        "Navigation",
        CL_ONLY,
        ("unload", "page", "ctrl+k"),
    ),
```

`CL_ONLY = ("artifacts",)` in `src/sase/ace/tui/commands/_tabs.py` line

 8

.  
`ensure_

metadata_covers_

app_keymaps()` (618–

638

) and

 `catalog.py` import

-time call (46–55) fail if omitted.

**Palette runtime filter** — `src/sase/ace/tui/commands/availability.py`

1. `spec.tabs` already hides them off Artifacts (`is_command_available` 633–634).
2. **Must** add to `_NON_PRS_ARTIFACT_COMMANDS` (84–112). Non-Patches panes only keep `artifacts.*` ids or that allowlist (295–296). Pattern: `app.artifacts_copy_reference` at 107.

```

python
       

 "app.artifacts

_load_more",
        "app.artifacts_unload",
```

**Coverage tests (auto if metadata exists):**

- `tests/test_command_catalog.py` 35–40 (`fields(AppKeymaps)`)
- `tests/test_command_catalog_guards.py` 53–67
- `tests/test_command_catalog_build.py` 29–35, 343–353

**Hand assertions to add** (same files as metadata):

- `tests/test_command_catalog.py` 74–

75 — add

 `.

tabs == ("artifacts

",)`


- `tests/test_command_

availability_scope.py` 32–47 — positive `tab="artifacts"`, negative `"agents"` / `"axe"`. Existing metadata test uses legacy `tab="changespecs"` which is **not** in `spec.tabs`.

---

### 5. Footer / help / docs

**Help modal (do this):** `src/sase/ace/tui/modals/help_modal/patches_artifact_bindings.py` **Artifact Views** section (40–63), next to split/project rows:

```python
(
    f"{d(a.artifacts_load_more)} / {d(a.artifacts_unload)}",
    "Load more / unload page (limit:)",
),
```

**Agents help (do not steal):** `help_modal/agents_bindings.py` 58–61 is metadata only.

**Prompt

 help:**

 `help

_modal/binding_common.py` `PROMPT_INPUT_SECTION` (17–63) does **not** currently list Ctrl+J/K; no change required for keymap wiring.

**Pane hint bars** (optional but matches other shared verbs like `refresh`):

- `src/sase/ace/tui/widgets/artifacts/commits_rendering.py` 149–163
- `.../beads_rendering.py` 166–174
- `.../plans_rendering.py` 131–139
- `.../files_rendering.py` 171–185

`KeybindingFooter` (`widgets/keybinding_footer.py`) is **conditional** Agents/Patches/Axe chips only — do not put paging there.

**Docs

:**

|

 Location | Why

 |
| --- |

 --- |
| `docs/ace.md

` 134

–148 **

Navigation in Stitches

, Beads, Provider Documents

, and Files**

 | Shared Artifacts nav

 table — best home |


| `docs/ace.md` 317–326 `limit:N` | Semantic home for load-more |
| `docs/ace.md` 571–586 File pane table | If you document Files keys |
| `docs/ace.md` 652–666 Artifacts/Patches Navigation | Patches shares the same host `limit:` |
| `docs/ace.md` 3092–3093, 5820–5821 | **Leave.**

 Modal-local Ctrl+J/K (alias history / prompt history), not app keymaps |
| `docs/artifacts_pane_contract.md` 31–51 | Only if you add a capability; `refresh` is the analog |

Do **not** put these in Global Keybindings (`docs/ace.md` 2486).

---

### 6. Tests (keymap-specific)

| File | What |
| --- | --- |
| `tests/test_keymaps_defaults.py` 433–438, 597–601 | Auto via `fields(AppKeymaps)` |
| `tests/test_keymaps_app_bindings.py` 12–25 | Count auto |
| **Same file 54–61** | Copy `test_search_

and_contextual_

app_query_share_slash`:

 both new

 actions +

 both metadata actions on

 `ctrl+j`/`ctrl+

k` |
| **Same file 

175–194** | **Will

 fail

.** Today

 `ctrl+k` must be **only** `prev_agent_metadata_section`. Change to a two-action list (order = `_BINDING_META` / `DEFAULT_BINDINGS` order) |
| `tests/test_keymaps_registry_loading.py` 44–45 | Add `reg.app.artifacts_load_more == "ctrl+j"` etc. |
| `tests/test_keymaps_validation.py` 172–185 | Optional: independent remap of the new fields |
| `tests/test_keymaps_e2e.py` 259–281 | Keep; proves prompt still wins. Optionally clone on `initial_tab="artifacts"` |
| `tests/ace/tui/test_agents_zoom_panel_action.py` 135–147 | Mirror: available on Artifacts, **False** on agents/axe |
| `tests/_keymaps_helpers.py` | No change (`load_builtin_app_defaults()`) |

`test_keybinding_footer_core.py` constructs `AppKeymaps(**load_builtin_app_defaults())` — auto.

---

### 7. How metadata is gated — mirror for Artifacts

**Binding availability (the key one):** `src/sase/ace/tui/_app_action_availability.py` 216–221:

```216:221:/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/src/s

ase/ace/tui/_app_action_availability.py
    if action in {
        "next_agent_metadata_section",
        "prev_agent_metadata_section",
    }:
        if app.current_tab != "agents":
            return False
```

Mirror with `ARTIFACTS_TAB` (already imported line 8):

```python
    if action in {"artifacts_load_more", "artifacts_unload"}:
        if app.current_tab != ARTIFACTS_TAB:
            return False
```

**Also required** — same file 

124

–129

: on Art

ifacts **

non-Patches**

 panes, anything **not** in `NON_PRS_ARTIFACT_ACTIONS` is disabled.

Add both names to `NON_PRS_ARTIFACT_ACTIONS` in `src/sase/ace/tui/actions/artifacts.py` 45–103 (next to `"artifacts_copy_reference"` at 100). Same set is imported into `check_app_action`.

Optional extra gate like `cycle_artifacts_*` (135–142) is redundant if the pair above is in the allowlist **and** you early-return False off Artifacts.

Wired from `AceApp.check_action` → `check_app_action` (`app.py` 355–357). Textual uses this when two app bindings share a key.

**Action body:** `action_next_agent_metadata_section` lives in `actions/navigation/_basic.py` 297–313 and no-ops if `current_tab != "agents"`. Put `action_artifacts_load_more` / `action_artifacts_unload` on `ArtifactsNavigationActionsMixin` (`actions/artifacts_navigation.py`) or `ArtifactsMixin` (`actions/artifacts.py` 253), with `current_tab != ARTIFACTS_TAB: return`. Defense in depth, same as `action_artifacts_copy_reference` (`actions/clipboard/_artifacts.py` 96–106).

---

### 8. Prompt Ctrl+J / Ctrl+K priority — **not** `check_app_action`

`check_app_action` only gates **tab**. On Agents, metadata stays **enabled** while the prompt is focused; the widget still wins.

**Ctrl+J (newline):** widget binding on `PromptTextArea` — `src/sase/ace/tui/widgets/prompt_text_area.py` 123–126:

```python
    BINDINGS = [
        ("enter", "submit_prompt", "Submit"),
        ("ctrl+j", "insert_newline", "New line"),
        ...
    ]
```

Focused widget bindings beat app bindings. Implementation: `_prompt_text_area_list_editing.py` `action_insert_newline` (149+). Single-line subclass **swallows** Ctrl+J (`single_line_vim_text_area

.py` ~118–120).

**Ctrl+K (history):** **not** a widget Binding. `PromptTextAreaKeyHandlingMixin` stops the event before it bubbles:

```281:285:/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/src/sase/ace/tui/widgets/_prompt_text_area_key_handling.py
        if event.key == "ctrl+k":
            event.stop()
            event.prevent_default()
            self.action_open_prompt_history()
            return
```

Hardcoded `"ctrl+k"`, not `registry.app.prev_agent_metadata_section`. `VimTextArea` comment (line 50) notes Textual `TextArea` also binds `ctrl+k` (kill-to-end); this handler overrides it.

**E2E lock:** `tests/test_keymaps_e2e.py` 259–281 (`test

_agents_prompt

_input_ctrl_j_keeps_local_newline_priority`, `..._ctrl_k_keeps_local_history_priority`). No `check_app_action` prompt-focus branch for these keys.

Modals (`prompt_history_modal.py` 86–87, `alias_history_modal.py`, `revive_agent_modal.py`) bind the same chords with `priority=True` — leave them; they are not `ace.keymaps.app`.



---

### 9. Schema



`src/

sase/config

/sase.schema.json` **

1828–1834**:



```json
"app": {
 

 "type": "object",
  "description": "

Top-level application keybindings (action name to key string)",
  "additionalProperties": { "type": "string" }
}
```

No per-action properties. `tests/test_config_schema_keymaps.py` does not enumerate `app` fields. **No schema edit.**

---

### 10. CHANGELOG

Confirmed. `CONTRIBUTING.md` 31–36:

> `CHANGELOG.md` is generated by release-please from conventional commit messages and must never be hand-edited. There is no `Unreleased` section; `just lint` enforces this. Add changelog entries with a proper `feat:` or `fix:` commit subject and a `BREAKING CHANGE:` footer where applicable.

Do **not** edit `CHANGELOG.md`. Land with e.g. `

feat(ace-tui): add configurable Artifacts load-more/unload keys`.

---

### Action implementation (not keymap, but the keys are dead without it)

Textual will call `AceApp.action_artifacts_load_more` / `action_artifacts_unload`. Those methods do not exist yet. Closest mixin: `ArtifactsNavigationActionsMixin`. Also add names to `_artifact_tab_actions.py` `CAPABILITY_HOST_ACTIONS` **only** if you invent a capability; host-always verbs

 like `refresh`

 sit on `Pane

Capability.REFRESH`.

 Load-more is closer

 to `refresh`

 (every pane) than to

 pane

-specific `files

_*`.

---

### Minimal ordered checklist

1. YAML defaults (`default_config.yml`)
2. `AppKeymaps` fields
3. `_BINDING_META` + `DEFAULT_BINDINGS`
4. `_CONTEXTUAL_APP_DUPLICATES` two pairs
5. `_APP_COMMAND_META` with `CL_ONLY`
6. `_NON_PRS_ARTIFACT_COMMANDS` + `NON_PRS_ARTIFACT_ACTIONS`
7. `check_app_action` Artifacts-only gate
8. `action_*` methods on Artifacts mixin
9. Help **Artifact Views** row + `docs/ace.md` shared nav table
10. Tests: shared-key assertion, availability/check_action, fix uniqueness test 175–194
11. **Do not** touch schema, `loader.py`, `defaults.py`, `CHANGELOG.md`, or prompt widget intercepts

Import-time guards that will fail if you skip a layer: `types.py` (`_BINDING_META`), `_app_metadata.py` / `catalog.py` (command meta), `load_keymap_registry` (YAML).

I have the seams mapped. Next I’ll add the keymaps and the load-more/unload actions, then wire them through each Artifacts pane.

I'll install the package next, then run the new paging tests and the keymap/catalog checks.

Install is still compiling the Rust bindings. I’ll review the new action paths while that finishes.

Install finished. I’ll run the new paging tests and the keymap/catalog suite next.

Patches paging no-ops when the tab still uses the legacy `patches` id. I’ll treat that as the Artifacts tab and re-run the failing tests.

Ruff is clean. Next I’ll run `just check` on this tree.

Two tests failed. I’ll update the Stitches footer expectation and check whether the agent-header failure is ours or unrelated.

`sase-r6.4` is closed. On the Artifacts tab, **Ctrl+J** now loads another `ace.page_size` rows and **Ctrl+K** unloads that page by rewriting the host-owned `limit:` token. The parent epic `sase-r6` is still open.

### What landed

Configurable app keys `artifacts_load_more` / `artifacts_unload` (defaults `ctrl+j` / `ctrl+k`) are wired through `AppKeymaps`, `default_config.yml`, bindings, the command palette, help, and pane footers.

One pair of app actions:

- reads the active pane’s committed query, or the live editor text if the filter session is open
- runs `extract_limit` → `adjust_limit` → `replace_limit`
- commits through each pane’s existing query path (chips, history, selection)
- no-ops at the floor (unload) or when already unlimited (load more)
- unload of `limit:all` introduces `limit:<page_size>`
- keeps the selected row when it is still visible; otherwise selects the new last row
- grows data off-thread: Files requests `full=True` when the cap outruns an incomplete snapshot; Plans extends the existing archive worker

Filter-bar editors intercept the chords so they still work while you are typing a query. Prompt newline / history and Agents metadata `Ctrl+J`/`Ctrl+K` stay as they were.

### Verified

Targeted tests cover default `limit:<page_size>` on every built-in pane, Beads paging, `limit:all` then unload, custom `ace.page_size: 25`, Patches query history back to the pre-Ctrl+J query, an open filter editor, prompt-bar `Ctrl+K` still opening history, and Agents-tab metadata still owning those keys.

`just check` lint passed, including symvision. `sase bead epic-symbols sase-r6.4` reported no leftovers. The scoped test lane escalated to the full suite because the Justfile and a data asset changed: **34,930 passed**. Two failures are unrelated and recorded as `PROPOSED FOLLOW-UP` on this bead:

- `test_workflow_step_has_no_kind_heading[parallel]` — production only emits `Step:` for bash/python
- `test_ace_page_fast_startup_is_structurally_quiet` — same flake r6.3 already noted; isolated rerun passed

Also noted for the land agent: Artifacts PNG goldens may need a refresh for the new footer text and r6.3’s default `limit:` chips.

I'll start from the full request and current repo state so I can close `sase-r6.4` and commit only the work that belongs to this phase.

The phase work looks already in the tree. I’ll check bead status, leftover epic symbols, and the uncommitted diff next so close and commit stay in the right order.

The bead is already closed with no leftover epic symbols. Next I’ll review the diff and write the commit for the Artifacts Ctrl+J/K work.

The leftover commit message is from r6.3, so I’ll inspect this phase’s actual diff and write a new one before committing.

I’ll close the already-finished bead if the close command still publishes, then write a r6.4 commit message and stitch the changes.

The close published as already-closed with a note. I’ll write the r6.4 commit message and stitch the changes next.

`sase-r6.4` is done, closed, and committed.

**Bead:** `sase-r6.4` is closed (`done`). `sase bead epic-symbols sase-r6.4` reports no leftovers. The parent epic was not closed.

**Commit:** `ed20ccdb8` — `feat(ace): page Artifacts lists with Ctrl+J and Ctrl+K`  
`master` is clean and in sync with `origin/master`.

**What landed:**
- `artifacts_load_more` / `artifacts_unload` on Ctrl+J / Ctrl+K, Artifacts-only so Agents keep the same chords for metadata
- Limit rewrite via `extract_limit` → `adjust_limit` → `replace_limit`, committed through each pane path without closing an open filter session
- Load-more no-ops at `limit:all`; unload floors at `page_size`
- Files grow an incomplete first page with the existing `full=True` worker; Plans/docs schedule the deep-archive worker off the UI thread
- Filter bars keep the chords live while editing; help, palette, and pane footers advertise them

Follow-ups already on the bead (PNG goldens, an unrelated workflow-step header, and an AcePage startup flake) stay for the land agent.
