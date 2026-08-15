# Chat History - ace-run (sase-m6.6.1.4)

- **TIMESTAMP:** 2026-08-15 07:58:33 EDT
- **MODEL:** claude/sonnet
- **AGENT:** sase-m6.6.1.4

## Prompt

#gh:gh_sase-org__sase
%id(4, clan=sase-m6.6.1, bead=sase-m6.6.1.4)
%model:@medium_worker
%auto
%w:sase-m6.6.1.1
%w(bead=sase-m6.6.1.1)
Can you complete the work for bead sase-m6.6.1.4? The bead is already reserved for you and assigned to your agent
name: it was set to status=in_progress before you started reading this, either by the `sase bead work` launch
checkpoint or by the runtime promoting an ad-hoc wait-time claim. Do not set the status by hand. Read its
description and design file, do the work, and close the bead with
`sase bead close sase-m6.6.1.4 --note "<what you verified>"`. Closing an assigned phase bead is unaffected by the
parent-close descendant guard. Do NOT close the parent epic. Do not create beads yourself: record discovered
follow-up work as a `PROPOSED FOLLOW-UP:` entry via
`sase bead note sase-m6.6.1.4 'PROPOSED FOLLOW-UP: <one-line summary — detail>'`; the epic's land agent triages
these into task beads.

## Response

I'll start by reading the bead's description and design file.

This is a large surface. Let me delegate deep exploration to an Explore agent while I read the three core store files myself in parallel.

This is a substantial task spanning persistence layers, TUI actions, modals, and startup logic. Let me delegate a thorough exploration to map out the full picture before designing the implementation.

Now let me look at the remaining files for item 2.

Now let's look at `_query.py`, `_startup_loads.py`, `startup.py`, `_state_init_late.py`, `_app_watchers.py`.

Now let's check the harness.py and test_conformance.py for the pattern this phase should extend, plus look at the contract compiler for pane_id conventions.

Good, `descriptor.id` == pane_id, matching the query_profile pane_id values ("patches", "stitches", "beads", "ref:plan", "files"). Let me check that this matches exactly.

Confirms pane ids match query_profile's pane_id conventions exactly. Now let's wait for the exploration agent's report to finish before designing the implementation.

Good — `app.current_artifacts_subtab` is the active-pane reactive. Now let's check on the background exploration agent's progress; meanwhile let's look at how `saved_queries`/`query_history`/`query_selection` functions are called in the action files most central to this task.

I'll wait for the exploration agent's comprehensive report rather than manually crawling all 18 files myself.

Now let's check the remaining item-2 files and item 5/6 (CLI, migration idiom).

Still running. Let me continue examining directly-relevant files while it works — starting with `patch/_query.py` and `patch/_core.py` in full.

I now have a complete picture. Here is the structured research report.

Let me look at the remaining state-init and startup files while the agent continues.

Still running. Let me check the `find_slot_for_query` caller context and how `current_artifacts_subtab`/pane_id is generally retrieved as a helper, plus `parser_ace.py` CLI surface, to round out my own understanding before the report lands.

# Research Report: sase-m6.6.1.4 — Namespace durable query state by pane

Repo root used below: `/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14`

## 1. Call sites of the public API

### `saved_queries.py` (`load_saved_queries`, `find_slot_for_query`, `save_query`, `delete_query`, `get_next_available_slot`, `load_first_saved_query`, `load_last_query`, `save_last_query`)

| Call site | What it does | "Active pane" in scope? |
|---|---|---|
| `src/sase/ace/tui/actions/base.py:9-15,530-552` (`action_edit_query`'s `on_dismiss`, `#<N>` save/delete syntax) | `find_slot_for_query`, `load_saved_queries`, `save_query`, `delete_query`, `get_next_available_slot` — the `#`-prefix save/delete UX inside the free-text query modal | Yes — this whole branch is already gated to Patches: `action_edit_query` only reaches the query-modal path when not stitches/document-provider/beads/files (`base.py:455-494`); `self.current_artifacts_pane_key` / `self.current_artifacts_subtab` is directly on `self` (the app) |
| `src/sase/ace/tui/actions/_startup_loads.py:15-24` (`_invalidate_saved_queries_cache`) | Reloads `self._saved_queries` from disk after any save/delete | No pane param; always assumes Patches. Called from `base.py` after save/delete |
| `src/sase/ace/tui/actions/_state_init_late.py:112-115` (`init_late_startup_state`) | Initial load of `self._saved_queries` at app startup | No pane context (startup, before any pane is "active") |
| `src/sase/ace/tui/actions/patch/_query.py:31-33` (`_save_current_query`), `:49-95` (`_load_saved_query`), `:97-154` (`action_open_saved_query_picker`, slot actions 0-9) | Core save-last-query / load-a-slot / open-picker logic | Yes — `_load_saved_query` explicitly forces `switch_to_artifacts_subtab(self, "patches")` first (lines 55-67); everything here is Patches-only by construction |
| `src/sase/ace/tui/widgets/patch_detail.py:81-95` (`SearchQueryPanel._resolve_saved_queries`) | Hot render path reads `app._saved_queries` cache, falls back to `load_saved_queries()` disk read only outside a full app | `self.app` available; this widget itself lives in the Patches pane only |
| `src/sase/ace/tui/widgets/_keybinding_modes.py:437-449` (`update_saved_query_bindings`) | Footer bindings for saved-query slot mode | Has `self.app`, only invoked for Patches slot-mode |
| `src/sase/ace/tui/modals/help_modal/query_sections.py:8,35` (`add_saved_queries_section`) | Renders the "Saved Queries" help-modal section; defaults to `load_saved_queries()` if no `queries=` override passed | No pane param directly, but caller (`modal.py`) is tab-aware |
| `src/sase/ace/tui/modals/help_modal/modal.py:109-128,235-238,336-346` | Passes `dict(self._saved_queries)` (app cache) into `HelpModal`, refreshed per-tab via `refresh_for_tab` | Yes, `_current_tab` tracked on modal; but query sections are only rendered when tab == "artifacts" (`modal.py` `_append_query_panels`, query-history section explicitly gated `if self._current_tab == "artifacts"`) |
| `src/sase/ace/tui/modals/saved_query_picker.py:16,21` (`SAVED_QUERY_SLOT_ORDER = KEY_ORDER`) | Only imports the `KEY_ORDER` constant, not persistence functions | N/A |
| `src/sase/ace/tui/actions/navigation/_modals.py:74` (`action_show_help`) | Passes `dict(self._saved_queries)` into `HelpModal(...)` | `self.current_tab` available on the mixin |
| `src/sase/ace/tui/_app_watchers.py:144` (`watch_current_tab`) | Refreshes an open `HelpModal` with `dict(self._saved_queries)` on tab switch | `new_tab` is the param; `self.current_artifacts_subtab` also available |
| `src/sase/main/parser_ace.py:5,18` | **Non-TUI / CLI**: `load_first_saved_query() or load_last_query() or "!!!"` used as the default value for the `ace` positional `query` CLI arg, evaluated at parser-registration/import time | No pane context — implicitly "patches" since it seeds the initial query for the Patches pane on TUI cold start |
| `src/sase/ace/tui/actions/startup.py:117`, `navigation/_types.py:108`, `patch/_query.py:27` | Type-only annotations for `_saved_queries: dict[str, str]` | — |
| `src/sase/ace/tui/_artifact_tab_contract_rules.py:286-309`, `_artifact_tab_model.py:85` | `PaneCapability.SAVED_QUERIES` verdict rule — **already pane-aware and already ON for every built-in pane with `has_inventory+has_fields`** (patches/stitches/beads/files/`ref:plan`), even though no non-Patches pane wires it up yet | Fully pane-scoped already at the contract layer |

### `query_history.py` (`load_query_history`, `save_query_history`, `push_to_prev_stack`, `navigate_prev`, `navigate_next`)

| Call site | What it does | Pane context |
|---|---|---|
| `src/sase/ace/tui/actions/_state_init_late.py:99-102` | Initial `self._query_history = load_query_history()` at startup | No pane context |
| `src/sase/ace/tui/actions/patch/_query.py:70,86-87` (`_load_saved_query`), `:203-221` (`action_prev_query`), `:228-246` (`action_next_query`) | Push/pop the history stacks when loading a slot or navigating `^`/`_` | `action_prev_query`/`action_next_query` both early-return `if self.current_tab != "artifacts"` — implicitly Patches only (no further pane check, but nothing else in Artifacts currently drives these) |
| `src/sase/ace/tui/actions/base.py:555-565` (`action_edit_query`'s normal-query branch) | Pushes old query before applying a new free-text query | Same Patches-only gating as saved_queries above |
| `src/sase/ace/tui/actions/agents/_notification_navigation.py:221,251-255` (`navigate_to_patch_tab`) | Pushes current query before switching to `project:<name>` query when a notification's target Patch isn't in the current filtered list; explicitly calls `switch_to_artifacts_subtab(app, "patches")` first | Yes, forces Patches pane before touching history |
| `src/sase/ace/tui/actions/navigation/_tree.py:308-309,332-333` (`_change_query_for_navigation`) | Pushes history when ancestor/child/sibling navigation changes the query | Implicit Patches (`_is_patch_tree_tab()` gates callers to `{"artifacts","patches","changespecs"}`) |
| `src/sase/ace/tui/actions/patch/_core.py:15,62` and `navigation/_types.py:17,107` | Type-only `_query_history: QueryHistoryStacks` annotations | — |
| `src/sase/ace/tui/modals/help_modal/query_sections.py:7,121` (`add_query_history_section`) | Renders "Query History" section from `load_query_history()` directly (no cache/override param, unlike saved queries) | Caller gates on tab == "artifacts" only, not sub-pane |
| `src/sase/ace/tui/_artifact_tab_contract_rules.py:260-283`, `_artifact_tab_model.py:84` | `PaneCapability.QUERY_HISTORY` rule — same as saved queries, already ON for all 4 built-in panes + plan provider | Contract layer already pane-scoped |

### `query_selection.py` (`load_query_selections`, `save_query_selections`)

| Call site | What it does | Pane context |
|---|---|---|
| `src/sase/ace/tui/actions/_state_init_late.py:104-107` | Initial `self._query_selections = load_query_selections()` at startup | No pane context |
| `src/sase/ace/tui/actions/patch/_core.py:476-498` (`_save_selection_for_current_query`, `_restore_selection_for_current_query`) | Only two mutation points in the whole codebase: pop+reinsert to mark MRU, then `save_query_selections(self._query_selections)`; restore looks up `self._query_selections.get(canonical)` then scans `self.patches` by name | These operate on `self.patches` directly — hard-wired to Patches; would need a Patch-specific `ArtifactEntryTarget` (pane_id="patches") once migrated |
| `src/sase/ace/tui/actions/patch/_query.py:26,72,85,209,234` | Callers of the above two helpers (`_load_saved_query`, `action_prev_query`, `action_next_query`) | Same Patches-only gating |
| `src/sase/ace/tui/actions/navigation/_modals.py` / `agents/_notification_navigation.py` | `_save_selection_for_current_query()` also invoked before `navigate_to_patch_tab`'s query change (`_notification_navigation.py:250-255` calls it implicitly via the same flow — actually it's `base.py`/`_query.py` callers) | — |

No `query_selection` import exists anywhere outside `patch/_core.py` and `patch/_query.py`/`navigation/_types.py`'s type hints — it is the most narrowly-scoped of the three.

## 2. Per-file role summary (requested files)

- **`tui/actions/agents/_notification_navigation.py`** (`navigate_to_agent_tab`, `navigate_to_patch_tab`) — Jumps from a notification to the matching Patch. If not found in the current filtered list, it explicitly forces Patches (`switch_to_artifacts_subtab(app, "patches")`, line 224) before mutating `app._query_history` (lines 221, 251-255) and calling `push_to_prev_stack`/`save_query_history`. Pure Patches consumer.
- **`tui/actions/base.py`** — Home of `action_edit_query` (the `/` query-edit modal), which is the single richest consumer: it dispatches to per-pane `show_filters()` for stitches/beads/files/document-provider panes (lines 455-494, none of which touch the three stores) and only reaches the `saved_queries`/`query_history` code (lines 502-576) when on the Patches pane. This file is the primary integration point for `#<N>` save/delete syntax and normal query-edit history pushes.
- **`tui/actions/navigation/_modals.py`** — `action_jump_to_all_entries` (cross-tab jump, unrelated to these stores) and `action_show_help`, which passes `dict(self._saved_queries)` into `HelpModal`. No direct persistence calls.
- **`tui/actions/navigation/_tree.py`** — Ancestor/child/sibling Patch-tree navigation (`<`, `>`, `~` keys). `_change_query_for_navigation` (lines 293-346) pushes to `_query_history` when the derived `ancestor:`/`sibling:` query differs from current. Gated to `_is_patch_tree_tab()` (patches/artifacts/changespecs).
- **`tui/actions/navigation/_types.py`** — `NavigationMixinBase`, pure type-hint base class declaring `_query_history: QueryHistoryStacks`, `_saved_queries: dict[str, str]`, `_artifacts_jump_history: dict[ArtifactsPaneKey, ArtifactEntryTarget]` (note: this last one is *already* pane-keyed by `ArtifactsPaneKey`, a useful precedent).
- **`tui/actions/patch/_core.py`** — `PatchMixin`, home of `_save_selection_for_current_query`/`_restore_selection_for_current_query` (the only `query_selection` mutation site), plus a large block of `changespec`-legacy-alias properties (unrelated noise).
- **`tui/actions/patch/_query.py`** — `PatchQueryMixin`, the densest consumer: `_save_current_query` (saved_queries), `_load_saved_query` (all three stores), `action_open_saved_query_picker`, slot actions 0-9, `action_prev_query`/`action_next_query` (query_history + query_selection). This is effectively "the Patches query-persistence controller" and is where most new pane-aware branching would concentrate if this phase widens beyond Patches.
- **`tui/actions/_startup_loads.py`** — `_invalidate_saved_queries_cache()`, the sole cache-refill point after a save/delete mutation; called from `base.py`.
- **`tui/actions/startup.py`** — `StartupMixin` composition root; just declares `_saved_queries: dict[str, str]` as a type hint (line 117).
- **`tui/actions/_state_init_late.py`** — `init_late_startup_state()`, the single startup site that calls all three loaders (`load_query_history` line 100-102, `load_query_selections` line 105-107, `load_saved_queries` line 113-115) to seed `self._query_history`/`self._query_selections`/`self._saved_queries`.
- **`tui/_app_watchers.py`** — `watch_current_tab` refreshes an open `HelpModal` with `dict(self._saved_queries)` whenever the top-level tab changes (not sub-pane changes — `watch_current_artifacts_subtab` in the same file does NOT touch these stores at all today).
- **`tui/_artifact_tab_contract_rules.py`** — Declares `_rule_query_history` (lines 260-283) and `_rule_saved_queries` (lines 286-309): both ON whenever `facts.has_inventory and facts.has_fields`, which is true for **all** built-in panes (`stitches`, `patches`, `beads`, `files`) and the `ref:plan` provider adapter per `_artifact_tab_contract_adapters.py`. The contract layer already asserts these capabilities are pane-general; only the storage/actions layer is Patches-only today.
- **`tui/_artifact_tab_model.py`** — Defines `PaneCapability.QUERY_HISTORY`/`SAVED_QUERIES` enum members (lines 84-85) and `ArtifactsPaneContract` (the immutable per-pane contract with `.id` = pane_id string).
- **`tui/modals/help_modal/modal.py`** — `HelpModal.__init__`/`refresh_for_tab` accept `saved_queries: Mapping[str,str] | None`; `_append_query_panels` renders the Saved-Queries section unconditionally but the Query-History section only `if self._current_tab == "artifacts"` (not sub-pane-aware).
- **`tui/modals/help_modal/query_sections.py`** — `add_saved_queries_section` (accepts an optional `queries` override so it doesn't have to hit disk) and `add_query_history_section` (always calls `load_query_history()` directly, no override param — an inconsistency worth normalizing during the redesign).
- **`tui/modals/saved_query_picker.py`** — `SavedQueryPickerModal`; only imports `KEY_ORDER` (not the load/save functions) — it's fed an immutable snapshot dict by its caller (`patch/_query.py:148-153`).
- **`tui/widgets/_keybinding_modes.py:435-449`** — `update_saved_query_bindings()`, footer text for saved-query slot mode; reads `self.app._saved_queries` cache directly.
- **`tui/widgets/patch_detail.py`** — `SearchQueryPanel` (lines 64-heirs), the hot per-keystroke render widget; `_resolve_saved_queries()` prefers `app._saved_queries` cache, falls back to `load_saved_queries()` only for bare-widget tests (see `tests/ace/tui/widgets/test_search_query_panel_cache.py`, which asserts the disk loader is **never** called from a mounted app — important constraint to preserve).
- **`main/parser_ace.py`** — CLI-only consumer; see item 5 below.

## 3. Active-pane tracking (how to get a `pane_id`)

- **`app.py:163-165`** — `current_artifacts_subtab: reactive[ArtifactsSubTab]` (default `"stitches"`), the raw reactive Textual state.
- **`app.py:341-344`** — `AceApp.current_artifacts_pane_key` **property**: `return artifacts_pane_key(self.current_artifacts_subtab)` — this is the normalized, canonical pane id. Also duplicated as a plain property on `ArtifactsNavigationActionsMixin` (`actions/artifacts_navigation.py:39-43`) for lightweight test harnesses, and stubbed via `getattr(self, "current_artifacts_pane_key", "patches")` in many action mixins that don't inherit the full app (`base.py`, `marking.py`, `clipboard/*`, `axe_display/_render.py`, `commands/context.py`, etc.).
- **`artifact_tabs.py:221-236`** (`artifacts_pane_key`) — normalizes `subtab` (+legacy `files_subtab`) into the canonical `ArtifactsPaneKey` string via `normalize_artifacts_subtab`, which maps legacy ids (`"prs"→"patches"`, `"bugs"→"beads"`, `"plans"→"ref:plan"`, `"other"/"chats"→...`) and falls back to `DEFAULT_ARTIFACTS_SUBTAB` for anything not in the currently configured pane set.
- **`ArtifactsPaneKey`** (`_artifact_tab_model.py:21`) is just `str` — no closed enum, matching a fully dynamic pane set (built-ins + per-project document providers).
- **The exact pane_id vocabulary** is confirmed identical across every subsystem: `"patches"`, `"stitches"`, `"beads"`, `"files"`, and `"ref:<kind>"` (e.g. `"ref:plan"`) for document providers. Verified in:
  - `_artifact_tab_contract_adapters.py` (`BUILTIN_ADAPTERS` dict keys + `PLAN_ADAPTER.pane_id = "ref:plan"`)
  - `entry_navigation.py`'s `_LEGACY_KIND_TO_PANE_ID` (`"commit"→"stitches"`, `"bead"→"beads"`, `"file"→"files"`, `"patch"→"patches"`, else `f"ref:{kind}"`)
  - `query_profile/profiles.py` (`pane_id="patches"` line 91, `"stitches"` line 164, `"beads"` line 242, `"ref:plan"` line 275, `"files"` line 327, `f"ref:{kind}"` line 378)
- **`ArtifactsPaneContract.id`** (`_artifact_tab_model.py:201`, resolved via `artifacts_pane_contract(pane_id)` in `artifact_tabs.py:130-134`) is the compiled, capability-bearing record keyed by this exact same pane_id string — use `app.current_artifacts_pane_key` (or `app.active_artifacts_contract.id`, see `artifacts_navigation.py:45-56`) as the namespacing key for the new stores.
- Existing precedent for a pane-keyed persistence-shaped dict already exists in the same mixin: `_artifacts_marked_targets: dict[ArtifactsPaneKey, set[ArtifactEntryTarget]]` and `_artifacts_jump_history: dict[ArtifactsPaneKey, ArtifactEntryTarget]` (`navigation/_types.py:100`, `artifacts_navigation.py:36-37`) — both are in-memory-only today, but they are exactly the "one dict keyed by pane_id" shape the redesigned stores should mirror.

## `ArtifactEntryTarget` token format (from `tui/widgets/artifacts/entry_navigation.py`)

- `ArtifactEntryTarget(pane_id: str, parts: tuple[str, ...])` — frozen dataclass, `__post_init__` rejects empty `pane_id` and any part/pane_id containing the delimiter.
- **Delimiter**: `_TOKEN_DELIMITER = "\x1f"` (ASCII Unit Separator, line 16) — chosen because it can't appear in real identifier content (shas, paths, titles, unicode).
- **Version marker**: `_TOKEN_VERSION = "v1"` (line 13) — bump this when the encoding shape changes; comment says old tokens become invalid (no automatic migration inside this module).
- **`to_token()`** (line 59-61): `"\x1f".join((VERSION, pane_id, *parts))` → e.g. `"v1\x1fpatches\x1fmy-patch-name"`.
- **`from_token(token)`** (line 63-73): splits on the delimiter; raises `ValueError` if fewer than 2 segments, wrong version, or empty pane_id. Everything after the 2nd segment becomes `parts`.
- **`from_legacy(value: tuple[str,...])`** (line 75-87): converts old `(kind, *rest)` tuples via `_LEGACY_KIND_TO_PANE_ID`, explicitly scoped to "staged migration and tests" — production code should construct `ArtifactEntryTarget` directly.
- This is exactly the token format the new persisted records must store for selections (replacing raw Patch-name strings in `query_selection.py`) — `target.to_token()` for storage, `ArtifactEntryTarget.from_token(s)` for reads.

## Query profile digest (from `query_profile/compiler.py` + `types.py` + `profiles.py`)

- `CompiledQueryProfile` (`compiler.py:33-72`) is a frozen dataclass with a `digest: str` field — a `hashlib.sha256(...).hexdigest()` over a canonical JSON payload (`json.dumps(payload, sort_keys=True, separators=(",", ":"))`, see `compile_query_profile` lines 75-110). The digest changes whenever the pane's dialect (fields/sigils/predicates/macros/free_text_hint/boolean/pane_id) changes — exactly the "detect a changed dialect, invalidate a cached saved query" use case called out in the module docstring (`compiler.py:1-11`).
- **There is no existing `pane_id -> CompiledQueryProfile` registry/cache yet** (confirmed — the package docstring explicitly defers "wiring the compiled profile into live pane filtering... to later phases of the sase-m6.6.1 epic"). To get a digest for a given pane_id today you must call the matching schema builder in `query_profile/profiles.py` and then `compile_query_profile(schema)`:
  - `patches_query_schema()` → pane_id `"patches"`
  - `stitches_query_schema()` → `"stitches"`
  - `beads_query_schema()` → `"beads"`
  - `plans_query_schema()` → `"ref:plan"` (note: function name doesn't match pane_id string)
  - `files_query_schema()` → `"files"`
  - `provider_query_schema(kind: str, spec: Mapping[str, Any] | None)` → `f"ref:{kind}"` (needs the provider's `spec`, e.g. from `ArtifactsTabDescriptor.provider_spec`)
  - All six take no `pane_id` parameter of their own except `provider_query_schema`'s `kind`; there's no single `schema_for_pane_id(pane_id: str)` dispatcher yet — this phase will likely need to add one (or inline a small `pane_id -> schema` map) since persisted records need `compile_query_profile(...).digest` per pane.

## 4. Existing tests

- **`tests/test_saved_queries.py`** — unit tests against `sase.ace.saved_queries` using `unittest.mock.patch` on `_SAVED_QUERIES_FILE`/`_LAST_QUERY_FILE`: `KEY_ORDER`, delete/save/move-between-slots, corrupt-JSON handling, `find_slot_for_query`, `get_next_available_slot` (partial/full), `load_last_query` missing-file case.
- **`tests/test_query_history.py`** — unit tests against `sase.ace.query_history`: empty-load, `navigate_prev`/`navigate_next` (including duplicate-removal semantics), `MAX_STACK_SIZE` enforcement on push, corrupt-JSON handling, bare `QueryHistoryStacks` dataclass construction.
- **`tests/test_query_selection.py`** — unit tests against `sase.ace.query_selection`: empty-load, MRU trimming past `MAX_SELECTIONS`, corrupt-JSON and non-dict-JSON handling.
- **`tests/ace/tui/artifacts_contract/test_persistence_goldens.py`** (+ `tests/ace/tui/artifacts_contract/goldens/persistence/{saved_queries,query_history,query_selections}.json`) — **the most important test for this phase**: it freezes the *current flat, non-namespaced* on-disk JSON shapes as golden fixtures and asserts `load_saved_queries()`/`load_query_history()`/`load_query_selections()` parse them exactly as today. Any redesign must either (a) keep these loaders backward-compatible with the pre-existing flat format (auto-upgrading it on read), or (b) this test file will need to be deliberately updated as part of documenting the migration contract — likely (a), given the docstring "Frozen Patch persistence files for saved queries, history, and selections."
- **`tests/ace/tui/test_saved_query_slot_keys.py`** — behavioral `AcePage` TUI tests for the `0`-prefixed slot-loading keybinding (`0` then digit), including cross-pane behavior ("from commits lands on PRs" — i.e., today pressing the saved-query key from the Stitches pane always redirects to Patches).
- **`tests/ace/tui/modals/test_saved_query_picker.py`**, **`tests/ace/tui/visual/test_ace_png_snapshots_saved_query_picker.py`** — modal behavior + a PNG visual snapshot (`snapshots/png/saved_query_picker_100x32.png`) of `SavedQueryPickerModal`; any change to slot data shape flowing into this modal risks snapshot invalidation (would need `just test-visual` with `--sase-update-visual-snapshots` if rendering changes).
- **`tests/ace/tui/widgets/test_search_query_panel_cache.py`** — asserts `SearchQueryPanel.render()` **never** calls `load_saved_queries()` when mounted in a real app (must keep reading `app._saved_queries` cache only) — a hard perf constraint to preserve through the redesign.
- **`tests/ace/tui/modals/test_help_modal.py`**, **`tests/test_keymaps_app_bindings.py`**, **`tests/ace/tui/test_agents_jump_to_patches_subtab.py`**, **`tests/ace/tui/test_changespecs_onboarding.py`**, **`tests/ace/tui/test_jump_to_changespec.py`** — matched the grep but only touch these modules incidentally (help modal construction, keymap binding names, or Patch-tab-switch behavior), not persistence format directly.
- **`tests/ace/tui/artifacts_contract/test_contract_compiler.py`** and **`test_query_goldens.py`** matched the grep only because of unrelated identifiers (`PaneCapability.QUERY_HISTORY`/`SAVED_QUERIES` capability names, and a test literally named `test_query_selection_results_match_frozen_patch_oracle` that's about query *filtering* semantics, not the `query_selection.py` persistence module) — not relevant to this phase's storage redesign.

## 5. CLI surface

- **`src/sase/main/parser_ace.py:5,18`** is the only non-TUI consumer: `from sase.ace.saved_queries import load_first_saved_query, load_last_query`, used as `default=load_last_query() or load_first_saved_query() or "!!!"` for the `ace` subcommand's positional `query` argument (evaluated once at argparse-registration time, i.e. at `sase ace` invocation, before the TUI app even constructs). No CLI flags directly expose `query_history`/`query_selection`. Whatever pane_id these new APIs require, this call site needs a default (almost certainly `"patches"`, since it seeds the app's *initial* query and the app always boots into the Patches query system for this string) — or the function signatures need a `pane_id: str = "patches"` default so this call site doesn't have to change its call shape.

## 6. Existing migration idiom to reuse

Two established patterns exist in this codebase; the first is the closer match for small single-file JSON stores like these three:

- **`src/sase/ace/dismissed_agents_migrations.py`** — the cleanest precedent. `maybe_migrate_bundles(ctx)` (lines 12-39): checks whether an *old-format* file exists (`ctx._old_bundles_file()`); if so, loads it, validates shape defensively (`if not isinstance(data, list): file.unlink(); return`), transforms each entry into the new per-agent-file representation via `Agent.from_bundle_dict(entry)`, writes the new files, then `old_bundles_file.unlink()` — all wrapped in a broad `except (OSError, json.JSONDecodeError): pass` so migration failure is silent/non-fatal (matches the existing `load_*` functions' own defensive-degrade style in `saved_queries.py`/`query_history.py`/`query_selection.py`). `maybe_shard_root_bundles`/`maybe_fix_child_collisions` in the same file show the sibling "marker-file-guarded one-shot" variant (`bundles_dir / ".root_bundles_sharded"` existence check) for migrations that need idempotency tracking beyond "does the old shape still exist." These are invoked from `src/sase/ace/dismissed_agents.py:413-414` (`_run_dismissed_archive_maintenance`), itself called at multiple points in `dismissed_agents_bundles.py` (lines 85, 167, 324) — i.e., safe to call opportunistically/repeatedly, not just once at startup.
- **`src/sase/ace/patch/project_spec_migration.py`** — a heavier, explicitly-invoked (CLI/startup-probe) migration with `MigrationReport`, per-file locking (`patch_lock`), and conflict detection between legacy/canonical *file paths* (`.gp`→`.sase` rename). This is overkill for the query-persistence stores (single small JSON blobs, not a directory of many files with concurrent writers), but its `MigrationReport`-with-counts convention could be reused if CLI-visible migration diagnostics are ever wanted here.
- **Recommendation given the golden-test constraint in item 4**: the natural idiom is closer to `maybe_migrate_bundles`'s "detect old shape → transform in memory → treat as already-migrated" but *without* needing a separate old-file/new-file split, since it's the same JSON file just reshaped — i.e., `load_saved_queries()`/`load_query_history()`/`load_query_selections()` should detect "flat legacy shape" (e.g. `saved_queries.json` values are all plain strings, `query_history.json` has top-level `"prev"/"next"` lists of strings, `query_selections.json` values are all plain strings) vs. "namespaced shape" (e.g. a `"panes"` or per-pane-id top-level key), and when legacy, lift the entire flat structure under the `"patches"` pane_id (the sole historical consumer) rather than raising or dropping data — this is what keeps `test_persistence_goldens.py`'s frozen fixtures passing unchanged.

I'll keep examining independently while waiting — checking `_startup_loads.py`, `startup.py`, and `navigation/_modals.py`.

Now let's look at `_notification_navigation.py`, `_app_watchers.py`, `navigation/_modals.py`, `startup.py`, and `widgets/_keybinding_modes.py` relevant sections.

This confirms this call site always operates on the "patches" pane (explicitly switched first). Now `_app_watchers.py` around the HelpModal refresh and `navigation/_modals.py`.

Now I have a clear design. Let me start implementing — first the shared I/O helper and the profile digest resolver.

Now update the `query_profile/__init__.py` exports:

That resolves once added to `__all__`.

Now the shared `QueryRecord` type:

Now rewrite `saved_queries.py`:

Now `query_history.py`:

Likely just LSP indexing lag since I just created that file. Let's continue with `query_selection.py`.

Let's verify the modules actually import correctly in Python (LSP lag check):

Good, installed. Now let's verify the modules with the venv's python.

Modules import fine. Now let's run the existing legacy test files to see what breaks (expected — I'll rewrite them next).

Expected. Now let's rewrite the three unit test files plus the golden test file.

Now let's rewrite `tests/test_query_history.py`:

Now let's run these three test files to check correctness:

All pass. Now let's update the golden persistence test.

Confirm the checked-in golden fixture files themselves are untouched by git status:

Clean. Now let's move to updating the CLI parser and the TUI action call sites.

Now `_state_init_late.py`:

Now `_startup_loads.py`:

Pre-existing/unrelated diagnostics. Now let's rewrite `patch/_query.py`:

Let me fix the tab-switching semantics to distinguish top-level tab switch (legitimate, still needed for cross-tab invocation) from sub-pane switch (removed per the epic):

Now let's fix `action_open_saved_query_picker`, `action_prev_query`, and `action_next_query`:

Let's continue to `patch/_core.py` for the selection save/restore using `ArtifactEntryTarget`:

Now `base.py`'s `#`-save/delete and normal-update flow:

Found it — these type hints need updating too:

Now update `navigation/_types.py`:

Now `navigation/_tree.py`:

Now `agents/_notification_navigation.py`:

Good. Now `base.py`'s save/delete and normal-query-update flow:

Good, no missing type hints in base.py. Now let's move to `_app_watchers.py` and `navigation/_modals.py`:

Now let's implement the `pane_id` threading in `HelpModal`:

Now update `_append_query_panels`:

Now update `query_sections.py`:

Now let's update `navigation/_modals.py`'s `action_show_help`:

That's fine — the diagnostic is stale/cached. Now let's update `widgets/_keybinding_modes.py`:

Now `widgets/patch_detail.py`'s `_resolve_saved_queries`:

Pre-existing noise unrelated to my edit. Now let's run the search query panel cache test:

Now let's update `tests/ace/tui/test_saved_query_slot_keys.py`:

Now let's update the saved-query-picker test file:

Now fix this section:

Now the other `_saved_queries` assignment:

Now the PNG snapshot test's direct assignment:

Now let's check `test_agents_jump_to_patches_subtab.py` and `test_jump_to_changespec.py`:

Now let's fix the test's assignment:

Now let's check `test_jump_to_changespec.py`:

No assertions directly inspect `_query_history`'s content shape, so just the initial construction needs updating:

Now let's fix the `test_changespecs_onboarding.py`'s `save_query(...)` calls (old 2-arg signature):

Excellent, all 101 tests pass. Now let's check the remaining files I haven't verified: `_app_watchers.py` full context, `navigation/_modals.py`, and run a broader search for any leftover `_saved_queries`/`_query_history`/`_query_selections` references I might have missed.

Let's run formatting and linting now to clean up the long import lines:

`just fmt` (ruff format) reformatted the long import lines nicely. Now let's run `just lint`:

Simplest fix: convert to canonical strings right after loading the stacks.

Now let's re-run mypy:

Let's re-run ruff and the whole affected test battery to confirm everything's still green after formatting.

All green. Now let's run the full `just check` scoped test lane and lint gates to catch anything else across the broader repo.

Given the scoped run escalated to the full suite (due to a core-identity change unrelated to my edits), I'll run it through the monitor per project convention rather than blocking inline.

The monitor's family-promotion has an unrelated bug. I'll run `just check` via the Bash tool's background mode instead, which doesn't need that machinery.

While `just check` runs in the background, let me record the monitor bug I hit as a follow-up note on the bead, and continue reviewing the diff for completeness.

Let's add a test for stale-record handling at the end of this file:

All passing, including the new stale-digest test. Let's clean up the unused `_saved` helper (already used) and check ruff again for this file, then wait for the background `just check` to finish.

While `just check` runs in the background, let's review the full set of changes so far.

This matches my design plan exactly. Now let's wait for the background `just check` run to complete.

That tool wasn't the right fit here — I'm not in a `/loop` context. I'll simply wait for the background `just check` task notification, which will resume this conversation automatically when it completes.

I'll verify the current repo state and confirm this is the work from the in-progress session before proceeding to verification and commit.

Install succeeded. Now let's run `just check` in the background and block on it within this turn.

`just check` passed cleanly — all lint gates green (fmt, ruff, mypy, pyscripts, symvision, etc.) and the scoped test lane (634 of 2654 files) passed. Now closing the bead.

The close published successfully (no "NOT published" error). Now committing via the git commit skill.

Working tree is clean and in sync with `origin/master`.

## Summary

Completed bead **sase-m6.6.1.4** — namespaced saved-query, query-history, and query-selection persistence by pane, keyed on the active pane's compiled query-profile digest with `ArtifactEntryTarget` tokens for selections. Added safe read-time migration of legacy flat-format files and write-then-read validation, and rewired slot actions, the saved-query picker, history navigation, help-modal sections, startup, and selection restore to route through the active pane without switching tabs.

Verified: `just check` passed clean (all lint gates + scoped test lane, 634/2654 files, exit 0), plus the full set of unit/behavioral/golden/visual-snapshot tests for this subsystem passed explicitly. Bead closed and published with a verification note; changes committed and pushed to `master`.
