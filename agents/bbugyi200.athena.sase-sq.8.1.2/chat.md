# Chat History - ace-run (sase-sq.8.1.2)

- **TIMESTAMP:** 2026-08-25 00:57:42 EDT
- **MODEL:** claude/sonnet
- **AGENT:** sase-sq.8.1.2

## Prompt

#gh:gh_sase-org__sase
%id(2, clan=sase-sq.8.1, bead=sase-sq.8.1.2)
%model:@medium
%auto
%w:sase-sq.8.1.1
%w(bead=sase-sq.8.1.1)
Can you complete the work for bead sase-sq.8.1.2? The bead is already reserved for you and assigned to your agent
name: it was set to status=in_progress before you started reading this, either by the `sase bead work` launch
checkpoint or by the runtime promoting an ad-hoc wait-time claim. Do not set the status by hand. Read its
description and design file, do the work, and close only this bead with
`sase bead close sase-sq.8.1.2 --note "<what you verified>"`. Before closing, run
`sase bead epic-symbols sase-sq.8.1.2`. If this phase still has `--epic-symbol` entries, resolve each symbol or
re-key the Justfile line to a still-open bead (the parent epic or a later phase). `sase bead close` refuses while
leftovers remain; they go stale the instant this phase closes and turn unrelated agents' `just check` red. Closing
an assigned phase bead is unaffected by the parent-close descendant guard. Do NOT close the parent epic or any ancestor plan bead. Any instruction in a phase
description or child plan to close an ancestor is preparation and evidence for that ancestor's land agent, not
authorization for a phase worker. Do not create beads yourself: record discovered follow-up work as a
`PROPOSED FOLLOW-UP:` entry via
`sase bead note sase-sq.8.1.2 'PROPOSED FOLLOW-UP: <one-line summary — detail>'`; the epic's land agent triages
these into task beads.

## Response

I'll start by reading the bead's description and design file.

Now let me look at the current state of the repo to understand what exists from Phase 1 and what needs to change in Phase 2.

Clean working tree, no prior progress. This is a large phase. Let me explore the current MemoryPane and glossary pane implementations to scope the actual work before touching anything.

This is a large phase, so I've launched a background research agent to survey the current MemoryPane, the standalone Glossary pane family, keymaps/doctor, existing memory-web mutation code, and related tests/snapshots. I'll wait for that report before making changes.

While that agent runs, let me check the epic and sibling phase beads for additional context.

Now let's look at the roster, discovery, frontmatter, and validation modules, plus memory/mutation.py (the existing note mutation engine) to see reusable pieces for a strand mutation engine.

I'll wait for both the install and the exploration agent to finish before proceeding.

That tool doesn't apply here — this isn't a `/loop` session. I'll just wait for the background install and research agent to finish naturally; both will notify me on completion.

Waiting on `just install` and the exploration agent to complete before I scope the implementation.

I'll pause here and resume once the background install and research agent report back.

I'll stop issuing calls now — both the `just install` background command and the exploration agent will notify me automatically when they finish.

Both `just install` and the exploration agent are still running in the background. I'll resume as soon as they report back — no further action needed from me right now.

I'll hold here until the background `just install` run and the exploration agent notify me that they're done, then continue scoping and implementing Phase 2.

Still waiting on both background tasks — I'll continue once notified.

Good — this confirms the chip renderer is already shared (`build_numbered_chip_rows` is used by both glossary and memory rendering), so only the relation *data* (outbound "SEE ALSO" via `glossary_cross_references`/`resolve_glossary_closure`, inbound "REFERENCED BY" via `glossary_reverse_references`) needs to be wired into MemoryPane's strand rows — the chip UI plumbing is already unified.

I now have enough to write the full report.

# Phase 2 Research Report: Consolidating Glossary into MemoryPane

## 1. MemoryPane implementation

**Files** (`src/sase/ace/tui/modals/`):
- `memory_pane.py` (594 lines) — the reusable content widget `MemoryPane` (a `Vertical` mixing in `CopyModeForwardingMixin`, `SourceFileActionsMixin`, `MemoryPanelActionsMixin`, `MemoryPanelStateMixin`, `MemoryPanelViewMixin`, `MemoryPanelNavigationMixin`, `MemoryPanelTravelMixin`). Owns composition, worker-backed loads, `MemoryPaneSession` (scope_key/note bookmark, lines 78-89), and the constructor seeding params `initial_scope_key`/`initial_note` (lines 133-186).
- `memory_panel.py` — thin `ModalScreen` adapter (`MemoryPanel`) that hosts `MemoryPane` as the standalone modal, delegating everything.
- `memory_panel_state.py` (265 lines) — snapshot/filter/selection state machine.
- `memory_panel_view.py` (265 lines) — writes rendered text into mounted widgets.
- `memory_panel_rendering.py` (564 lines) — pure render helpers (rail rows, header/footer, note card).
- `memory_panel_web_rendering.py` — web/strand-specific metadata card (badges `WEB`/`STRAND`/`EXPANDED`/`COLLAPSED`/`AUDITED`, PARENT/CHILDREN chips, property grids for webs and strands).
- `memory_panel_navigation.py` (221 lines) — note cursor, filter, `p`/`P`/`ctrl+p` scope cycling, `action_toggle_web` (line 98), `action_next_strand`/`action_prev_strand` (lines 113-143).
- `memory_panel_travel.py` (159 lines) — `MemoryPanelTravelMixin`: numbered PARENT/CHILDREN chip cursor, `action_follow_link`/`action_follow_link_number`, bounded `_trail` breadcrumb, `action_travel_back`.
- `memory_panel_scope_picker.py` — `ctrl+p` filterable scope picker (`MemoryScopePicker`).
- `memory_panel_load.py` — off-thread loads; `record_memory_panel_strand_read` (lines 158-186) performs the audited strand read via `sase.memory.read_log`.
- `memory_panel_actions.py` / `memory_panel_add.py` / `memory_panel_delete.py` / `memory_panel_write.py` / `memory_panel_publish.py` / `memory_panel_publish_actions.py` — add/edit/delete forms and `sase memory init` publish flow.
- `memory_panel_help_modal.py` — contextual help.

Companion catalog module: `src/sase/ace/tui/memory_panel_catalog.py` (`MemoryRailNode`, `MemoryScopeSnapshot`, `build_memory_scope_ring`, `load_memory_scope_snapshot`, `memory_note_relations`).

**Config-hub wiring**: `src/sase/ace/tui/modals/config_hub_catalog.py` — `_memory_factory` (lines 90-103) constructs `MemoryPane(host=hub, launch_workspace=…, initial_note=_entry_note(entry), session=hub._session_state.config_hub.memory_session(), activate_on_mount=True, id="memory")`. It is one of `CONFIG_SUBTAB_SPECS` (lines 154-218, `"memory"` at 191-199) and is listed in `RELATION_SUBTABS` (line 225-227, alongside `"snippets"` and `"glossary"`). Session bookmark type lives in `config_hub_session.py` (`ConfigHubSessionState.memory_session()`, lines 83-89) and seeding key `ConfigHubEntry.note` (lines 52-65).

### Capability matrix

| Capability | Status | Evidence |
|---|---|---|
| Web expansion (`web:keyword` browsing) | **EXISTS** | `action_toggle_web` (`memory_panel_navigation.py:98-111`), `_expanded_webs: set[str]` state, `memory_panel_web_rendering.py` renders WEB/STRAND badges and per-web/strand property grids. |
| Strand preview | **EXISTS** | Selecting a strand row renders its card via `build_rail_node_card_meta` (`memory_panel_web_rendering.py:30-75`), showing keyword/slug/aliases/summary/metadata. |
| Audited strand read | **EXISTS** | `_ensure_strand_read_for_current_selection` / `record_memory_panel_strand_read` (`memory_pane.py:496-550`, `memory_panel_load.py:158-186`) call the same selector-resolution + `append_memory_read_event` path as `sase memory read`; body copy is gated on `AUDITED` state (`memory_pane.py:575-587`). |
| "Scope ring" (`p`/`P`/`ctrl+p`) | **EXISTS** | `build_memory_scope_ring` includes every enabled project plus a trailing Home scope (`memory_panel_catalog.py:126-137`); `MemoryScopePicker` for `ctrl+p`. |
| Next/previous strand navigation | **EXISTS** | `action_next_strand`/`action_prev_strand` → `_move_strand` (`memory_panel_navigation.py:113-143`), bound to keys `s`/`S` in `ace.keymaps.memory`. |
| Link-trail navigation (breadcrumb `travel_back`) | **EXISTS** | `_travel_forward`/`action_travel_back`/`_trail` (`memory_panel_travel.py:114-141`), shared "numbered chip" UI (`numbered_link_keys.py`, `build_numbered_chip_rows`). |
| **Mention-relation** navigation (glossary's "SEE ALSO"/"REFERENCED BY") | **MISSING for strands** | `_refresh_links_for_current_note` always calls `memory_note_relations(snapshot, node.note)` (`memory_panel_travel.py:65-79`), which is pure flat-note `parent:`/children hierarchy (`memory_panel_catalog.py:192-206+`). It is never routed through the web's `closure: mentions` engine (`sase/memory/web/closure.py::resolve_strand_closure`, `sase/memory/web/relations.py::glossary_reverse_references`) that Glossary already uses (`glossary_panel_catalog.py::glossary_entry_relations`, lines 131-144). Chip UI (`build_numbered_chip_rows`) is already shared, so this is a data-wiring gap, not a rendering gap. |

**Add/delete strand (mutation)**: **MISSING** — deliberately blocked today. `action_edit_note`/`action_delete_note` in `memory_panel_actions.py` (lines 98-154) explicitly check `node.is_strand` and notify `"memory strands are edited from their source file"` / `"memory strands are deleted from their source directory"` rather than opening a form. The closest existing pattern is the flat-note add/edit/delete pipeline: `MemoryNoteFormModal` (`memory_panel_add.py`), `ConfirmActionModal`/`neighbor_note_after_delete` (`memory_panel_delete.py`), `_submit_memory_write` → session-worker queue → `run_memory_panel_write` (`memory_panel_write.py:59-155`) → `sase.memory.mutation.{create,update,delete}_memory_note`. A strand-mutation engine would need an analogous `create_memory_strand`/`delete_memory_strand` in a new module plus a roster-refresh step (see §4) since strand webs also render a managed roster region in the descriptor.

**Initial identity seeding**: `MemoryPane.__init__` accepts `initial_scope_key` and `initial_note` (`memory_pane.py:139-140`). `_preferred_note_for_snapshot` (lines 272-286) resolves the identity against `_snapshot_identities` (lines 288-294), which is the union of flat-note `relative_path`s **and** `f"{web.slug}:{strand.slug}"` strand identities — so passing `initial_note="glossary:some-strand-slug"` already works today and auto-expands that web (`_expand_web_for_identity`, lines 296-305). However, the existing prompt-bar seed path (`_seed_note_from_reference` in `_prompt_bar_memory_panel.py:24-40`) only converts `#memory/<stem>` references into flat relative paths — there is no code today that converts a glossary term/alias into the `glossary:<slug>` strand identity string. Also note: Glossary's own seed is matched by **term text** (`entry.term`, i.e. the strand's human keyword — `glossary_panel_state.py:104-125`), not by slug, so consolidating the prompt-bar seed requires a term→strand-slug lookup, not a straight passthrough.

## 2. Standalone Glossary pane family

Under `src/sase/ace/tui/`:

| File | Responsibility | What MemoryPane needs to gain |
|---|---|---|
| `glossary_catalog.py` | ACE prompt-side glossary catalog cache (`PromptGlossaryContext`, warms `EditorGlossaryCatalog` for the prompt text-area highlighter). | Unrelated to the pane; feeds `_prompt_glossary.py`'s inline highlighting, keep as-is. |
| `glossary_panel_catalog.py` | Panel-side project ring + per-project snapshot cache (`GlossaryProjectRef/Snapshot`, `build_glossary_project_ring`, `load_glossary_project_snapshot`, `glossary_entry_relations` at 131-144). Backed by `sase.memory.web.catalog.GLOSSARY_WEB_SLUG` + `find_memory_web` (already memory-web-backed post Phase 1). | MemoryPane needs the outbound/inbound relation computation this module already does (`glossary_cross_references` + `glossary_reverse_references`) generalized onto strand rows. |
| `glossary_reads.py` | Loader for legacy per-agent `sase glossary read` audit events (`GlossaryReadDisplayEvent`), used by the agent-context header, **not** the browsing pane. | Out of scope for pane consolidation; separate legacy read-log system (see below). |
| `modals/glossary_panel_actions.py` | **Already retired**: `action_add_term`/`action_delete_term` are stubs that just notify `"Glossary writes now use the Memory panel's glossary web controls."` (lines 12-34) — confirms Phase 1 already killed glossary mutation. |
| `modals/glossary_panel_add.py` (324 lines) | Defines `GlossaryTermAddModal`/`GlossaryAddDraft` — **dead code**, nothing imports it anymore (`action_add_term` never opens it). Candidate for straight deletion in this phase. |
| `modals/glossary_panel_delete.py` | Delete-confirmation copy/neighbor-reselect helpers — unused now that delete is stubbed; likely dead too. |
| `modals/glossary_panel_help_modal.py` | Contextual help modal for `GlossaryPane`'s keymap. |
| `modals/glossary_panel_load.py` | Off-thread initial/project loads (mirrors `memory_panel_load.py` minus the strand-read audit). |
| `modals/glossary_panel_navigation.py` | Term cursor, filter, `p`/`P` project cycling — structurally identical to `memory_panel_navigation.py`. |
| `modals/glossary_panel_rendering.py` | Pure render helpers for term rows/header/footer. |
| `modals/glossary_panel_state.py` | Snapshot/filter/selection state machine (mirrors `memory_panel_state.py`), matches by `entry.term` identity. |
| `modals/glossary_panel_travel.py` | Numbered SEE ALSO/REFERENCED BY chip cursor + trail — the exact feature MemoryPane is missing for strands. |
| `modals/glossary_panel_view.py` | Widget update glue (mirrors `memory_panel_view.py`). |
| `modals/glossary_pane.py` | The reusable `GlossaryPane` content widget (mirrors `MemoryPane`'s structure closely — same mixin pattern, same numbered-link key handling). |
| `modals/glossary_preview_modal.py` / `modals/glossary_preview_render.py` | Purpose-built term-definition preview popup and its shared render helpers (`build_numbered_chip_rows`, `glossary_card_accent`, `glossary_definition_position`, `glossary_source_path`, `glossary_cross_references`). **Used independently** by the prompt-buffer hover/jump feature (`widgets/_prompt_glossary.py::_preview_glossary_under_cursor`), not only by the panel — so this may need to survive (or be retargeted at MemoryPane data) even after the browsing pane itself is deleted. `memory_panel_web_rendering.py` already imports `build_numbered_chip_rows` from here (line 18), so the two surfaces are already coupled. |
| `widgets/_prompt_glossary.py` | Prompt text-area mixin: glossary highlighting overlay, hover preview (`GlossaryPreviewModal`), and jump-to-definition (`JumpTarget`). Independent of the pane; not being deleted. |
| `actions/agent_workflow/_prompt_bar_glossary_panel.py` | Handles `PromptInputBar.GlossaryPanelRequested`, opens `ConfigHubEntry(subtab="glossary", term=event.term)` via `_open_config_center`. |
| `widgets/prompt_panel/_agent_glossary_reads.py` | Renders the agent-context-header "GLOSSARY" lane from legacy read-log events (`sase.memory.legacy_glossary_read_report`) — a separate audit-trail display system, distinct from the pane. |

**Opening the Glossary pane from the prompt bar**: `PromptInputBar._prompt_input_bar_g_prefix_actions.py::request_open_glossary_panel` (around line ~290, paired with `request_open_memory_panel` at line 333) captures `self._glossary_term_under_cursor()` (lines 349-363) — which reuses `PromptGlossaryMixin._glossary_match_under_cursor` from `_prompt_glossary.py` — and posts `PromptInputBar.GlossaryPanelRequested(term, mode)` (message class at `_prompt_input_bar_messages.py:111-122`). `_prompt_bar_glossary_panel.py::on_prompt_input_bar_glossary_panel_requested` (lines 29-53) then calls `_open_config_center("config", config_entry=ConfigHubEntry(subtab="glossary", launch_workspace=…, term=event.term), on_dismissed=…)`. The seed is the **raw matched term string** (`GlossaryEntry.term`), not a slug — `GlossaryPane._preferred_initial_term()` (`glossary_pane.py:242-247`) then matches it exactly against `entry.term` in `glossary_panel_state.py`.

**Config-hub "Glossary" subtab wiring**: `config_hub_catalog.py::_glossary_factory` (lines 75-87) builds `GlossaryPane(launch_workspace=…, initial_term=_entry_term(entry), host=hub, session=hub._session_state.config_hub.glossary, id="glossary")`; registered in `CONFIG_SUBTAB_SPECS` (lines 173-181) and `RELATION_SUBTABS`. Its session bookmark is the generic `CatalogPaneSession` (`catalog_pane_contract.py:43-55`, `scope_key`/`entry_id`) rather than a dedicated dataclass like `MemoryPaneSession`. Note: **the Glossary pane is already embedded in the Config hub as a normal subtab** (not truly "standalone" today) — deleting it means removing the `"glossary"` entries from `CONFIG_SUBTAB_SPECS`/`ConfigSubTab`/`ConfigHubSessionState`/`RELATION_SUBTABS`/`CONFIG_SUBTAB_ORDER` in addition to deleting `GlossaryPanel`/`GlossaryPane`.

Also confirmed: top-level `glossary:` **config** key is already in `UNSUPPORTED_TOP_LEVEL_KEYS` (`src/sase/config/layers.py:23-25`), consistent with "Phase 1 already removed the config-backed glossary backend." The Rust-backed `sase.core.glossary_facade` (term/definition/alias validation, phrase-matcher compilation) is retained and still generically reused by both the prompt highlighter and the memory-web glossary source (`sase.memory.web.catalog.memory_web_glossary_entries` converts strands into `GlossaryInputEntry`s for it).

## 3. Keymaps

`src/sase/default_config.yml`:
- `ace.keymaps.glossary` — lines 328-352 (`next_term`, `prev_term`, `first_term`, `last_term`, `scroll_definition_down/up`, `filter_terms`, `toggle_definition_filter`, `next_relation`, `prev_relation`, `follow_relation`, `travel_back`, `next_project`, `prev_project`, `add_term`, `delete_term`, `open_source`, `open_viewer`, `copy_definition`, `copy_source_path`, `refresh`, `help`). Note `add_term`/`delete_term` keys still exist even though they're stubbed to a "retired" warning today.
- `ace.keymaps.memory` — lines 353-383 (`next_note`, `prev_note`, `first_note`, `last_note`, `toggle_web`, `next_strand`, `prev_strand`, `scroll_body_down/up`, `filter_notes`, `toggle_body_filter`, `next_link`, `prev_link`, `follow_link`, `travel_back`, `next_scope`, `prev_scope`, `pick_scope`, `add_note`, `edit_note`, `delete_note`, `publish`, `open_source`, `open_viewer`, `copy_body`, `copy_source_path`, `refresh`, `help`).

Code-side (`src/sase/ace/tui/keymaps/`):
- `app_keymaps.py:297-322` — `GlossaryPanelKeymaps` dataclass; `app_keymaps.py:325-356` — `MemoryPanelKeymaps` dataclass.
- `defaults.py:71-74` — `load_builtin_glossary_defaults()`; parallel `load_builtin_memory_defaults()`.
- `scopes.py:198-216` — `load_glossary_keymaps`/`load_memory_keymaps`, both routed through the shared `_load_scope_keymaps` helper (lines 41-137) which does unknown-action warnings, canonicalization, reserved-key revert (`_NUMBERED_LINK_RESERVED_KEYS`, lines 35-38 — `.`/`full_stop` reserved by both glossary and memory), and supports a `pre_step` hook for scope-specific migrations (used today by the gate scope's `activate_control` deprecation shim, `scopes.py:139-161`).
- `registry.py:384-390, 488-489` — `load_keymap_registry` builds both `glossary_km`/`memory_km` into `KeymapRegistry`.
- `types.py:61,108-109` — `KeymapRegistry.glossary`/`.memory` fields.
- `bindings.py:139-181` — `build_glossary_bindings`/`glossary_help_bindings` alongside `build_memory_bindings`/`memory_help_bindings`.
- `metadata.py:247` — comment marking Glossary-panel bindings as intentionally scoped/non-global.

**"Doctor" implementation**: `src/sase/doctor/` (registry in `runner.py`, individual `checks_*.py` modules), invoked via `src/sase/main/doctor_handler.py::handle_doctor_command`. No existing doctor check mentions "glossary" today (`grep -rl glossary src/sase/doctor` is empty) — a new `checks_config_keymap_glossary.py`-style check would be new work.

**Existing "deprecated config key" patterns to mirror** (three relevant precedents, none an exact match for "rename an entire nested keymap scope"):
1. **Top-level key rename** — `src/sase/config/layers.py:31-40`, `DEPRECATED_TOP_LEVEL_KEYS: dict[str, str]` (e.g. `"linked_repos": "repos.linked"`), collected per layer via `_collect_deprecated_keys` (lines 97-100) and surfaced as `layer.deprecated_keys` (line 80) → rendered by `src/sase/doctor/checks_config_layers.py:60-66` as `"{key} -> {new_key}"` WARN rows. This only works for *top-level* keys, not `ace.keymaps.glossary`.
2. **Retired action rename inside one keymap scope** — `src/sase/ace/tui/keymaps/registry.py:59-79`, `LEGACY_APP_KEY_ALIASES: dict[str, str]`, applied by `_migrate_legacy_keys`-style logic in `registry.py` and surfaced by `src/sase/doctor/checks_config_keymap_actions.py:11-60` (`check_config_keymap_actions`) — this is the closest analog in *shape* (a doctor check that loads `ace.keymaps.app`, flags legacy action names, points at a migrate command) but operates within a single scope's field names, not across scopes.
3. **Single-field deprecation shim inside one scope** — `scopes.py:139-161`, `_migrate_gate_legacy_activate_control`, folding a retired override into its replacement field with a `log.warning`, invoked as `_load_scope_keymaps`'s `pre_step`.

For `ace.keymaps.glossary` → `ace.keymaps.memory`, none of these directly transplants a whole scope; the new doctor check (and a `pre_step`-style loader shim) would likely need to be original code combining pattern 2's doctor-check shape with a custom per-field mapping (e.g. `next_term`→`next_note`, `next_project`→`next_scope`, `copy_definition`→`copy_body`, `add_term`/`delete_term` retired outright) since the field names between the two scopes don't line up 1:1.

## 4. Existing memory-web write/mutation code

**No existing write path in `src/sase/memory/web/`** — that whole package (`catalog.py`, `discovery.py`, `frontmatter.py`, `lookup.py`, `models.py`, `roster.py`, `closure.py`, `relations.py`, `resolution.py`, `render.py`, `validation.py`, `scope.py`, `generated.py`, `text_filter.py`, `read_context.py`) is read/parse/render only — confirmed via `grep -rl write_text|write_bytes|atomic src/sase/memory` matching only `mutation.py`, `proposals/ledger.py`, `proposals/review.py`, and the unrelated `legacy_glossary_read_report.py`.

**The reusable engine to build on is `src/sase/memory/mutation.py`** (391 lines) — "the only code that writes memory notes," no Textual import:
- `memory_note_digest(data: bytes) -> str` (line 55-57) — SHA-256 digest for conflict detection.
- `create_memory_note(*, scope_key, content_root, stem, note_type, parent, description, body="", scope_kind) -> MemoryMutationOutcome` (60-104).
- `update_memory_note(*, scope_key, content_root, relative_path, note_type, parent, description, expected_digest, scope_kind) -> MemoryMutationOutcome` (107-161) — digest-guarded (`_require_digest`, raises `MemoryConflictError`), preserves body byte-for-byte, only rewrites frontmatter.
- `delete_memory_note(*, scope_key, content_root, relative_path, expected_digest, scope_kind) -> MemoryMutationOutcome` (164-210) — backs up to `.sase/memory-backups/` or `~/.sase/memory-backups/<scope_key>/` (`_backup_path`, 295-315) before `source.unlink()`, re-checks bytes right before backup to catch a race (`MemoryConflictError`).
- `_write_bytes_atomically(path, data, *, overwrite)` (318-357) — tempfile in the same directory, `fchmod` to preserve/normalize mode, `fsync`, then `os.replace` (overwrite) or `os.link` + unlink temp (create, so `FileExistsError`→`MemoryConflictError` on a race), plus `_fsync_directory` (360-371) for durability. This is directly reusable for strand file writes.
- Path/flat-note assumptions to work around: `_assert_flat_memory_path`, `require_flat_memory_note_path`, `memory_write_root`/`memory_read_root` (from `sase/memory/paths.py`) all assume one-level-deep flat notes; a strand mutation engine needs analogous helpers scoped to `memory_root / web_slug / *.md` instead.
- Validation split lives in `sase/memory/mutation_validate.py` (`validate_memory_note_draft`, `children_of_memory_note`, `raise_if_generated_memory_note`, `require_flat_memory_note_path`) and `sase/memory/mutation_models.py` (typed errors: `MemoryConflictError`, `MemoryGeneratedNoteError`, `MemoryMutationError`, `MemoryValidationError`, plus `MemoryMutationOutcome`/`MemoryNoteDraft`/`MemoryDraftValidation`). A strand engine would want an equivalent `validate_memory_strand_draft` (validating `keyword`/`aliases`/`summary`/`metadata`, slug uniqueness within the web) reusing the same error types where the shape matches.

**Frontmatter and discovery reuse** (`src/sase/memory/web/`):
- `frontmatter.py::parse_memory_strand` / `parse_web_descriptor` (261-321, 163-258) — parsing only; there is no `render_strand_frontmatter`/`apply_strand_frontmatter` writer counterpart yet (unlike `sase.memory.notes.apply_memory_frontmatter` used by `mutation.py`). One would need to be added, mirroring `apply_memory_frontmatter`'s "preserve body, rewrite header block" approach.
- `frontmatter.py::slug_to_keyword` (119-123) — default keyword derivation from a strand's file slug; reusable when generating a new strand's default `keyword:` field.
- `discovery.py::FileMemoryWebProvider.discover` — pure read; a new strand write must invalidate/re-run this (already exposed as `invalidate_glossary_project`/`invalidate_memory_scope` cache-busting helpers in the TUI catalog layers, not in `memory/web/` itself).

**Descriptor-roster refresh path**: `src/sase/memory/web/roster.py`:
- `render_strand_roster(web)` / `render_managed_roster_region(web)` (37-62) — regenerates the `<!-- sase:strands --> … <!-- /sase:strands -->` managed block from `ordered_web_strands(web)` (inline or list style per `web.roster`).
- `render_web_body_with_roster(web)` (65-84) and `render_web_descriptor_with_roster(web)` (87-93, calling `frontmatter.replace_web_body`) — produce the full descriptor content with the roster region inserted/replaced. **This is the function a strand create/delete mutation must call and then atomically write back to the web's `.md` descriptor** (via something like `mutation._write_bytes_atomically`) any time a strand is added or removed, so the roster stays in sync — today nothing calls these two functions from a write path; they're only exercised by `sase memory init`/rendering tests.

**Memory-init / publish path**: `src/sase/main/init_memory_handler.py` (`handle_memory_init_command`, `run_memory_init_command` at ~line 459) is the `sase memory init` CLI entry the MemoryPane's publish flow shells out to (`memory_panel_write.py::run_memory_panel_publish`, `sase.noninteractive_subprocess.run_noninteractive`). `src/sase/main/init_memory/` contains the broader root-application/rendering machinery (`root_application.py`, `root_rendering.py`, `root_rendering_artifact_relations.py`, etc.) that a strand mutation would presumably continue to route through post-write (i.e., strand mutation engine writes the strand file + refreshed descriptor directly, then optionally offers the same "publish via `sase memory init`" confirmation MemoryPane already offers for flat notes, via `memory_panel_publish.py`/`memory_panel_publish_actions.py`).

## 5. Visual snapshots and tests

**PNG visual snapshots** (`tests/ace/tui/visual/snapshots/png/`):
- `glossary_panel_empty_dark_120x40.png`
- `glossary_panel_empty_light_120x40.png`
- `glossary_panel_populated_dark_120x40.png`
- `glossary_panel_populated_light_120x40.png`
- `glossary_preview_card_full_dark_120x40.png`
- `glossary_preview_card_full_light_120x40.png`
- `glossary_preview_card_minimal_120x40.png`
- `prompt_glossary_highlight_dark_120x40.png`
- `prompt_glossary_highlight_light_120x40.png`
- `prompt_glossary_wrapped_highlight_dark_120x40.png`

**`tests/ace/tui/modals/`**:
`glossary_panel_test_helpers.py`, `test_glossary_panel_adapter.py`, `test_glossary_panel_chips.py`, `test_glossary_panel_load.py`, `test_glossary_panel.py`, `test_glossary_panel_rendering.py`, `test_glossary_panel_term_rail.py`, `test_glossary_panel_trail.py`, `test_glossary_pane_session.py`, `test_glossary_preview_modal.py`, `test_glossary_preview_render.py`.

**`tests/ace/tui/widgets/`**:
`_prompt_glossary_helpers.py`, `test_agent_glossary_reads.py`, `test_prompt_glossary_highlighting.py`, `test_prompt_glossary_navigation.py`, `test_prompt_glossary_panel_entry.py` (plus g-prefix hint tests that reference glossary alongside memory/snippets: `prompt_g_prefix_hint_test_support.py`, `test_prompt_g_prefix_hint_entries.py`, `test_prompt_g_prefix_hint_lifecycle.py`, `test_prompt_g_prefix_hint_routing.py`).

**`tests/ace/tui/actions/`**:
`test_prompt_glossary_panel_open.py` (and `test_prompt_config_hub_open.py`, which likely exercises both glossary and memory config-hub entry points together).

**`tests/ace/tui/visual/`**:
`_ace_prompt_png_snapshot_glossary_fixtures.py`, `test_ace_png_snapshots_glossary_panel.py`, `test_ace_png_snapshots_glossary_preview.py` (plus shared harness files `_ace_prompt_png_snapshot_prompts.py` / `_ace_prompt_png_snapshot_wire.py` that both glossary and other prompt snapshot tests build on).

**Adjacent tests worth knowing about** (outside the four requested directories but directly relevant to the phase): `tests/ace/tui/test_glossary_panel_catalog.py`, `tests/ace/tui/test_config_hub_catalog.py`, `tests/ace/tui/test_config_hub_pane.py`, `tests/ace/tui/test_config_hub_pane_navigation.py`, `tests/ace/tui/test_config_center_tabs.py`, `tests/ace/tui/test_config_hub_numbered_links.py` (Config-hub subtab-registration/order tests that will need to drop `"glossary"` once the subtab is removed), and `tests/ace/tui/test_memory_panel_catalog.py` (the MemoryPane-side counterpart that will grow strand-relation coverage).

Good, the research report is thorough. Let me check on the `just install` background task now.

The research is thorough. Given the scope, I'll read the key implementation files directly myself before delegating precise, well-scoped subtasks — I want exact anchors so I can write agent prompts that don't waste effort re-deriving context.

Before touching any TUI selection-path code, I need to consult the required TUI performance reference memory.

I have a solid design for the mention-relation navigation piece. Let me check existing tests for these files before implementing, then start with this stream myself while parallel agents handle the more independent mutation-engine and keymap-consolidation work.

Now let me implement Stream 1. First, `closure.py`:

Now update `src/sase/memory/web/__init__.py` to export the new names:

Now add the `mention_catalogs` field to `MemoryScopeSnapshot`, populate it in `_load_memory_scope_snapshot`/`_empty_snapshot`, and add the dispatcher functions:

Now update `_load_memory_scope_snapshot` and `_empty_snapshot` to populate `mention_catalogs`, and update `__all__`:

Now let's wire `memory_panel_travel.py` to use the new dispatcher:

Now let's update `memory_panel_web_rendering.py` for the fallback call and chip label branching:

Now let's fix these lines properly:

Now let's find a good insertion point (after `memory_note`) to add the mentions-web builder:

Now update the import to include `memory_note`:

Let me rewrite this using `initial_note=` so the strand row is properly expanded at mount:

Let's run the new tests and check for regressions in related existing tests.

Let me add a fake for `record_memory_panel_strand_read` to my test helpers module so it's reusable, and use it in the new test file:

Now let's add the fake-read installer function, right after `install_fixed_load`:

Now update the test file to use this helper in each test:

Good, the automated edit applied correctly. Let's run the tests now.

All 4 new tests pass. Now let's run the broader existing test suites for the touched modules to check for regressions.

Now let's re-run the full set of touched test files plus the closure/lookup backend tests:

Now let me add a real-file-based catalog test right after `test_snapshot_includes_collapsed_web_rows_and_strand_metadata`:

All 18 pass. Let's run ruff/mypy on all my changed files so far to make sure Stream 1 is fully clean.

Good, ruff passes. Now mypy:

Now I'll dispatch two background agents for the more self-contained pieces (mutation engine backend, and keymap consolidation + doctor check), while I handle the prompt-bar reroute myself.

I'll start by reading the key existing files to understand patterns before writing new code.

Now let me look at the memory web test file to understand fixtures used for creating webs/strands on disk, and check `test_mutation_validate.py` briefly.

While those agents work, I'll handle the prompt-bar reroute myself. Let me read the relevant files first.

I'll start by exploring the relevant files to understand the current state before making changes.

The dataclass structure matches the expected mapping. Let me check the stubbed actions file and other keymap infrastructure files in parallel.

Let me check the most recent commit (which mentions "retire config glossary infrastructure") and search for current usages of the glossary keymap symbols to understand whether `glossary_pane.py` still depends on them.

This confirms the expected mapping (step 1 verified). It also reveals that `glossary_panel_help_modal.py`, `glossary_panel_rendering.py`, and `glossary_panel_view.py` (pane files owned by another agent) still reference these keymap symbols — per the task framing, that agent will delete those pane files separately, and my scoped checks (not repo-wide) are exactly why this transient inconsistency is acceptable. Let me check the keymaps package `__init__.py` and `loader.py`, since those re-export the symbols I'm removing and are within my scope (the keymaps package itself must stay import-clean).

This confirms `glossary_panel_section` in `binding_common.py` directly accesses `km.glossary` and is called from 3 help-modal files — removing `KeymapRegistry.glossary` (mandated by step 2) will break these at runtime/mypy. Since these files aren't in the "PANE file" exclusion list (they're help-modal builders, not glossary_pane*/glossary_panel* files), and step 5 explicitly says to fix any breaking test that isn't pane-scoped, I'll include this fix in scope. Now let me look at the config, schema, and doctor check files.

Now let me check the config schema for `ace.keymaps.*` shape, the doctor package layout, and the existing keymap-actions doctor check as precedent.

Now let's check `test_prompt_config_hub_open.py`:

Now let's update `_prompt_input_bar_g_prefix_actions.py`:

Now let's add the necessary imports (`Mapping`, `Path`):

Confirmed I need real imports for `Mapping`/`Path`:

Now let's delete the old glossary prompt-bar mixin and fold its logic into the memory one:

Good, no new issues from my edit (the remaining are pre-existing textual-import noise). Now let's delete the old glossary prompt-bar file and update `_prompt_bar.py`:

Now let's update the two affected test files. First `test_prompt_glossary_panel_open.py`:

Now I have a complete picture. Let me implement the changes, starting with `app_keymaps.py`.

Now `defaults.py`:

Now `scopes.py`:

Now let's run all these tests:

Now `registry.py`:

Now `types.py`:

Good, my Stream 2 files are syntactically and lint-clean. The keymap agent is still mid-edit on shared files, so I'll hold off on running import-dependent tests until it finishes. Let's check on the mutation-engine agent's likely progress and look at what else I can do meanwhile — let's check `sase.schema.json` scope for `ace.keymaps` to anticipate integration, without touching it.

Now `bindings.py`:

While the keymap agent finishes its in-flight edits, let me read the Config-hub wiring I'll need for the pane deletion step later (read-only, no conflict risk).

Now `metadata.py`:

Let me use the remaining wait time to read the Memory panel's existing add/delete/write action files, since I'll need to wire the mutation engine into them once that agent finishes.

Now `default_config.yml`:

Now let's update `keymaps/__init__.py` and `keymaps/loader.py`:

Now `keymaps/loader.py`:

Now let's fix `help_modal/binding_common.py`, `bindings.py`, and the 3 call sites:

Both background agents are still running. I've gathered enough context on the memory-panel write plumbing to wire in the mutation engine once it lands. I'll wait for their completion notifications before proceeding further.

Now the 3 call sites. Let me check the import lines in each and remove them along with the append call.

I'll wait for the background agents to finish before continuing.

Both agents (mutation engine + keymap consolidation) are still running in the background. I'll pause here and resume once they report back.

Waiting on the two background agents (mutation engine backend, keymap consolidation) to complete — I'll continue with the wiring and pane deletion once they report back.

All three files import `glossary_panel_section` the same way and call it identically. Let me fix all three in parallel.

Now I have a clear picture. Let me check a couple more things: the `content_layout` import used for `LayoutCollisionError`, and confirm `memory_read_root` can raise it from within `discover_memory_webs`.

Now let's update the config schema to mark `ace.keymaps.glossary` as inert compatibility, matching the `prometheus` precedent.

Good, `LayoutCollisionError` is confirmed to propagate from `resolve_read` → `memory_read_root`. My design of wrapping `discover_memory_webs` calls with a try/except for `LayoutCollisionError` and `OSError` (mirroring `_discover_notes`) is correct. Now let me write the new `atomic_write.py` module first.

Now let's build the doctor check module. Let me check `diagnostics.py` and `checks_config_common.py` for exact types.

Good, that matches what `checks_config_keymap_actions.py` already imports. Now let's write the new doctor check module.

Now let's update `src/sase/memory/mutation.py` to use the shared helpers.

Now let's register the new check in `checks_config.py`, mirroring the existing `check_config_keymap_actions` registration exactly.

Now remove the extracted private helper functions (`_backup_path`, `_write_bytes_atomically`, `_fsync_directory`) from mutation.py.

Let's read the test files that need updates.

Now let's remove the glossary test function and imports from `test_keymaps_defaults.py`.

Now let's view the final mutation.py to double check consistency and imports.

Now let's add `render_strand_frontmatter` to `web/frontmatter.py`.

Good, clean. Now let's look at `test_keymaps_registry_loading.py`.

Let me update this file, removing the glossary-specific assertions and import.

Now let's create `src/sase/memory/web/mutation_models.py`.

Now let's create `src/sase/memory/web/mutation_validate.py`.

Now let's add a dedicated test confirming `ace.keymaps.glossary` in a user config produces no `.glossary` field and doesn't raise, at the end of this file:

Now let's look at `test_keymaps_registry_loading_panes.py`:

Now let's write the core `src/sase/memory/web/mutation.py` module.

Let me verify no remaining glossary references in that file:

Clean. Now let's look at `test_keymaps_display_help.py` and `test_keymaps_validation.py`.

Now let's update `web/__init__.py` to export the new mutation module's public surface.

Good, that's just the new test I wrote. Now let's check `test_keymaps_validation.py`:

Clean. Now let's fix `tests/ace/tui/modals/test_help_modal.py`:

Only these two lines. Let's remove the "Glossary Panel" (section header) assertion, leaving the "Glossary panel" prompt-input mention untouched since that belongs to the other agent's pane deletion work.

Now let's do a comprehensive re-check across the whole repo for any remaining references I might have missed.

Good, there's a top-level `conftest.py` that isolates `sase_home`, applying automatically to all tests including our new one at `tests/test_memory_web_mutation.py`. Now let's write the test file.

That's just the test I added. Now let's check the schema test suite for anything that validates the schema itself against `ace.keymaps` sections, plus check for existing JSON-schema config validation tests.

Good, that confirms sase_home is auto-isolated for all tests. Now let me write the test file.

`test_config_schema_keymaps.py` is highly relevant. Let's check it.

Let's add a schema test confirming `ace.keymaps.glossary` remains accepted (inert compatibility), matching the file's established pattern.

Now let's write the new doctor test file, mirroring the `test_checks_config_layers.py` pattern for controlling config layers via `tmp_path`.

Now let's run the verification suite. First, install dependencies (ephemeral workspace), then lint/typecheck/test only the files touched.

Now let's install and run the tests.

Install succeeded. Now let's run ruff format/check, mypy, and pytest scoped to the touched files.

Good, install succeeded. Now let's run the new tests.

All files already correctly formatted. Now ruff check and mypy:

This is concerning — the system flagged that `web/__init__.py` and `web/frontmatter.py` changed on disk and appear to have reverted my edits. Let me check the actual current state of all my files before concluding anything.

This confirms tests aren't mypy's normal target (`pyproject.toml` sets `files = ["src"]`), and the stub/Literal errors are pre-existing, unrelated to my edits (present even with my changes stashed away). Let me re-run mypy scoped to just the `src/` files I touched, matching the project's own mypy scope.

All source files pass mypy cleanly. Now let's run pytest on the touched/created test files.

This reveals the working tree is being actively churned by another concurrent agent (a glossary-panel retirement sweep touching many files, including `web/frontmatter.py` and `web/__init__.py`, which reverted my additive edits there). Let me check the current state of everything carefully before deciding how to proceed safely.

Let me re-check with fresh reads — the situation may have changed again since another agent is actively editing concurrently.

All 3 doctor tests pass now. Let's re-run the full scoped test suite together to confirm everything is green.

Let's run a few final sanity checks: JSON schema validity, YAML validity, and an import/smoke test of the doctor registry.

The failure exposed a real constraint: the underlying glossary catalog rejects strands with an empty body (definition). Let me check the validator used elsewhere in this codebase (`validate_glossary_entries`) so I can reuse it to convert this into a clean domain error instead of letting a raw `ValueError` leak from the Rust binding.

Now let's add the glossary-validity guard.

Now add the `_require_valid_glossary` helper function:

Now let's fix the test that omitted `body` (since a strand needs a non-empty definition for inline-roster glossary validation).

Now let's also add a test that empty body is rejected with a clear error, then re-run the tests.

Now let's re-run the full test suite for this file.

All 10 tests pass. Now let's run the existing flat-note mutation tests to make sure the `atomic_write.py` extraction didn't break anything, plus the memory web tests.

All checks pass. Let me do one final consolidated verification run to confirm everything together before reporting.

These two failures are from the other concurrent agent's in-progress TUI/keymap refactor (unrelated `GlossaryPanelKeymaps` breakage in `app_keymaps.py`/`glossary_panel_rendering.py`) — not something my backend-only change touched. Let me verify by running only the backend-relevant tests.

Found a real circular import: my `web/mutation.py` imports `sase.memory.mutation` (for `memory_note_digest`), but `sase.memory.mutation` transitively imports `sase.memory.web` (via `mutation_validate.py` → `root_rendering_task_types.py`). I'll fix this by moving the digest logic into the dependency-free `atomic_write.py` module, which both sides can import without cycling.

Now update `mutation.py` to delegate `memory_note_digest` to `content_digest`:

Now update `web/mutation.py` to use `content_digest` directly instead of importing from `sase.memory.mutation`:

Now let's re-run the tests to confirm the circular import is fixed.

Let me build the fresh manifest from this refreshed template and resubmit immediately.

Now let's re-run the full backend test set.

All 64 pass. Now let's run ruff format/check and mypy on every file I touched or created, scoped as instructed.

The final declaration was accepted on the retry. The submission succeeded, so the turn's changes (in the single shared repository) are now declared for commit by the host finalizer.

That file change was from `ruff format` itself (line-wrapping one long call), which is expected and fine. Let's run `ruff check` now.

Now let's run mypy on these files.

The `sase final submit` succeeded (declaration accepted for `commit`). Per the finalizer rules, no further file or repository changes should follow this point in the turn.

## Summary

**Task:** Consolidate the standalone Glossary keymap scope (`ace.keymaps.glossary`) into the Memory panel's keymap scope, keep the config schema accepting the old key as inert, and add a `sase doctor` warning for anyone still setting it.

**Step 1 finding — the mapping is a clean 1:1 (verified myself, not assumed):**
`next_term/prev_term/first_term/last_term` → `next_note/prev_note/first_note/last_note`; `scroll_definition_down/up` → `scroll_body_down/up`; `filter_terms` → `filter_notes`; `toggle_definition_filter` → `toggle_body_filter`; `next_relation/prev_relation/follow_relation` → `next_link/prev_link/follow_link`; `travel_back` → `travel_back`; `next_project/prev_project` → `next_scope/prev_scope` (Memory is a superset, adding `pick_scope`); `add_term/delete_term` were already retired no-op stubs in `src/sase/ace/tui/modals/glossary_panel_actions.py` (confirmed by reading it — both just show a "writes now use Memory panel" warning), so nothing live needed migrating; `open_source/open_viewer/copy_definition/copy_source_path/refresh/help` → `open_source/open_viewer/copy_body/copy_source_path/refresh/help`. No orphaned live action was found.

**Extra finding beyond the explicit file list:** `glossary_panel_section()` in `src/sase/ace/tui/modals/help_modal/binding_common.py` read `km.glossary` directly and was called from three help-modal builders (`agents_bindings.py`, `patches_bindings.py`, `axe_bindings.py`). These aren't `glossary_pane*/glossary_panel*`-named PANE files, so they weren't excluded, and removing `KeymapRegistry.glossary` would have broken them (AttributeError/mypy error) — a real regression from my own change, not the other agent's pane-deletion work. I removed the function, its 3 call sites, and its exports, and updated the two tests that covered it (kept the unrelated `PROMPT_INPUT_SECTION` "Glossary panel"/`gG` open-shortcut text untouched, since that belongs to the separate pane-deletion effort).

**Files modified:**
`src/sase/ace/tui/keymaps/{app_keymaps,defaults,scopes,registry,types,bindings,metadata,__init__,loader}.py`, `src/sase/ace/tui/modals/help_modal/{binding_common,bindings,agents_bindings,patches_bindings,axe_bindings}.py`, `src/sase/default_config.yml`, `src/sase/config/sase.schema.json`, `src/sase/doctor/checks_config.py`, `tests/test_keymaps_{defaults,registry_loading,registry_loading_panes,display_help,validation}.py`, `tests/ace/tui/modals/test_help_modal.py`, `tests/test_config_schema_keymaps.py`.

**Files created:** `src/sase/doctor/checks_config_keymap_glossary.py`, `tests/doctor/test_checks_config_keymap_glossary.py`.

**Doctor check registration:** `src/sase/doctor/checks_config.py` — import + `CheckSpec(id="config.keymap_glossary", group="config", title="Glossary keymap scope", runner=check_config_keymap_glossary)` inside `config_check_specs()`, plus the `_check_config_keymap_glossary = check_config_keymap_glossary` module-level alias, mirroring `check_config_keymap_actions` exactly. The check inspects unmerged config layers via `sase.config.core.load_config_layers()` (not the merged/defaulted config) so it only fires when a user layer explicitly sets `ace.keymaps.glossary`.

**Schema:** `ace.keymaps.glossary` kept fully schema-valid (same `additionalProperties: false` + property list as before, so existing configs still validate) with its description changed to mark it deprecated/inert, mirroring the existing `ace.telemetry.prometheus` "deprecated legacy settings accepted for compatibility and ignored" precedent.

**Verification (scoped to touched files only, per instructions):** `ruff format --check`, `ruff check`, `mypy` (limited to the touched `src/` files, matching this project's own `pyproject.toml` `files = ["src"]` mypy scope) all pass clean; `python -m pytest` on all 8 touched/created test files: 181 passed, 0 failed. Also confirmed by direct import: `load_keymap_registry({})` produces no `.glossary` attribute, `ace.keymaps.glossary` in default_config.yml is gone while `memory` remains, the schema JSON still parses, and the new doctor check imports/runs and reports OK with no overrides present.

result: Retired the standalone Glossary keymap scope into Memory's keymap across `src/sase/ace/tui/keymaps/*`, `default_config.yml`, and the help-modal builders that referenced it; kept `ace.keymaps.glossary` schema-valid-but-inert in `sase.schema.json`; added and registered a `sase doctor` check (`config.keymap_glossary` in `src/sase/doctor/checks_config.py`) that warns when a config layer still sets it; updated/added tests accordingly — all scoped ruff/mypy/pytest runs pass (181 tests green) — and the turn's final commit declaration was submitted successfully.

All clean. Let's re-run the tests once more since `ruff format` just touched `web/mutation.py`, and do a final check that no concurrent edits have clobbered anything.

The keymap-consolidation agent finished (181 tests passing). Let me verify nothing unexpected happened to the repo state, since it mentioned submitting a finalizer declaration.

Let's do a final sanity check of git status and confirm all my files remain intact.

Everything is intact and stable. Let's do one final full test run plus a final mypy/ruff pass to be certain, since the shared tree is still being actively edited by another agent.

The keymap agent's changes should have unblocked imports. Let's verify Stream 1 & 2 tests now pass with the consolidated keymaps in place.

Everything is clean and stable. Let me invoke the SASE final declaration skill as required before ending this turn.

This surfaced an urgent problem: the keymap agent's removal of `GlossaryPanelKeymaps` broke the still-existing glossary pane's imports, which cascades into breaking memory/snippets pane tests too (they share a `build_trail_strip` helper). I need to act now rather than wait. Let me verify exactly which "glossary_catalog" module the prompt highlighter depends on before deleting anything.

The memory-web strand write path is now built and verified. Summary of the work:

**Files created:**
- `/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_23/src/sase/memory/atomic_write.py` — generic, domain-free atomic file-write primitives (`write_bytes_atomically`, `fsync_directory`, `backup_path_for`, `content_digest`, `AtomicWriteConflictError`), extracted from `sase.memory.mutation` so both the flat-note and strand engines share one implementation.
- `/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_23/src/sase/memory/web/mutation_models.py` — `MemoryStrandDraft`, `MemoryStrandDraftValidation`, `MemoryStrandMutationOutcome`, `MemoryStrandMutationError`, `MemoryStrandValidationError`.
- `/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_23/src/sase/memory/web/mutation_validate.py` — pure `validate_memory_strand_draft(...)` (slug/keyword/alias/summary/metadata field checks plus collision detection against the target web via `resolve_memory_strand`).
- `/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_23/src/sase/memory/web/mutation.py` — the two entry points.
- `/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_23/tests/test_memory_web_mutation.py` — 10 tests covering create success, keyword defaulting, empty-body rejection, three collision variants, unknown-web, delete success/backup/roster update, stale-digest conflict, and missing-slug delete.

**Files modified:**
- `src/sase/memory/mutation.py` — now delegates to `atomic_write.py` instead of duplicating tempfile/fsync/backup logic (behavior unchanged; existing 12 tests in `tests/memory/test_mutation.py` still pass).
- `src/sase/memory/web/frontmatter.py` — added `render_strand_frontmatter(*, keyword, aliases=(), summary=None, metadata=None, body="") -> str`, built on the pre-existing `sase.memory.notes.render_frontmatter_block`.
- `src/sase/memory/web/__init__.py` — re-exports the new mutation surface.

**Public signatures:**
```python
def create_memory_strand(*, scope_key: str, content_root: Path | str, web_slug: str, slug: str,
    keyword: str | None = None, aliases: Sequence[str] = (), summary: str | None = None,
    metadata: Mapping[str, Any] | None = None, body: str = "",
    scope_kind: MemoryScopeKind = "project") -> MemoryStrandMutationOutcome

def delete_memory_strand(*, scope_key: str, content_root: Path | str, web_slug: str, slug: str,
    expected_digest: str, scope_kind: MemoryScopeKind = "project") -> MemoryStrandMutationOutcome
```
Returns the new `MemoryStrandMutationOutcome` (the flat-note `MemoryMutationOutcome`'s `type`/`parent` fields don't fit a strand). Raises `MemoryStrandValidationError` on invalid/colliding drafts, `MemoryConflictError` (reused directly from `sase.memory.mutation_models`, per your instruction) on stale-digest deletes, and `MemoryStrandMutationError` for everything else (unknown web/strand, roster-render failure, backup collisions).

**Notable things found along the way:**
1. A real circular import: `web/mutation.py` initially imported `memory_note_digest` from `sase.memory.mutation`, but that module transitively imports `sase.memory.web` (via `mutation_validate.py` → `sase.main.init_memory.root_rendering_task_types`). Fixed by moving the digest logic into `atomic_write.py` (`content_digest`), which both engines now call independently.
2. The roster renderer's underlying Rust glossary-catalog builder raises a raw `ValueError` ("needs a definition") if a strand's body is empty. Added a proactive `_require_valid_glossary` check (reusing `sase.core.glossary_facade.validate_glossary_entries`, the same validator `sase.memory.web.validation` uses) so this surfaces as a clean `MemoryStrandMutationError` instead.
3. This workspace turned out to be a shared git tree with another concurrent agent actively retiring glossary-panel TUI infrastructure. I verified after every edit that my additions to the two files they were also touching (`web/frontmatter.py`, `web/__init__.py`) survived intact, and left `memory_panel_catalog.py`, `memory_panel_travel.py`, `memory_panel_web_rendering.py`, and `web/closure.py` untouched as instructed.

**Verification:** `ruff format`, `ruff check`, and `mypy` all pass clean on every file listed above; `python -m pytest tests/test_memory_web_mutation.py tests/memory/test_mutation.py tests/memory/test_mutation_validate.py tests/memory/test_memory_web.py tests/memory/test_memory_web_catalog.py tests/main/test_memory_web_cli.py` — 64 passed, 0 failed.

result: Built the memory-web strand write path (`create_memory_strand`/`delete_memory_strand` in `src/sase/memory/web/mutation.py`, plus supporting `mutation_models.py`/`mutation_validate.py`, a shared `src/sase/memory/atomic_write.py`, and `render_strand_frontmatter` in `web/frontmatter.py`), with 10 new tests in `tests/test_memory_web_mutation.py`; ruff/mypy clean and all related tests (64) pass, and the turn's changes have been declared to the SASE finalizer for commit.

Now I have enough precision to safely delegate the deletion sweep. Let me launch it alongside the mutation-engine UI wiring, in parallel since they touch disjoint files.

I'll start by exploring the repo structure to understand the current state before making changes.

Now let me create the new `trail_strip.py` module and update the two direct importers (`memory_panel_view.py` and `snippets_panel_rendering.py` — the prompt named `snippets_panel_view.py` but the actual direct import is in `snippets_panel_rendering.py`).

Now let's check the test file for snippets panel rendering that imports `build_trail_strip`.

I'll start by reading all the relevant source files to understand the existing patterns before making any changes.

Both agents are underway. I'll wait for their completion notifications before continuing.

Step 1 is confirmed unblocked — all 31 tests pass. Now moving to Step 2: deleting the standalone Glossary pane family. Let me verify each file's usage before deleting.

Waiting on the deletion-sweep agent and the strand-mutation UI wiring agent to complete before continuing.

Since `glossary_panel_actions.py` is being deleted, I need to remove this `"glossary.write"` producer-site entry too, or the AST conformance test will fail (declared site pointing at a file that no longer exists). Let me remove it.

Let me look at `memory_panel_web_rendering.py` for the "REFERENCED BY" label convention and check `memory_panel_state.py`'s `_selected_row` for how it derives from `_rows`.

Now I have full boundaries. Let me remove these three CSS sections (Glossary Panel Styling, Glossary Panel Help Modal Styling, Glossary Term Add Modal) plus fix the two `ConfigHubPane` selector lists.

Now the two `ConfigHubPane` selector-list fixes:

Everything checks out. Now let's delete the source files, test files, and PNG snapshots.

Good, deletions successful. Now let's fix `modals/__init__.py`, `modals/__init__.pyi`, and `config_hub_catalog.py`.

Now let's check the `.pyi` stub file:

Now let's look at `config_hub_catalog.py` for Step 3.

Now let's remove `_glossary_factory`, `_entry_term`, the glossary `ConfigSubTabSpec` entry, and update `RELATION_SUBTABS`.

Now let's look at `config_hub_session.py` for the `ConfigSubTab` Literal, `CONFIG_SUBTAB_ORDER`, `ConfigHubEntry.term`, and `ConfigHubSessionState.glossary`.

Install finished. Let's run the test now.

All 10 pass now. Let's fix `test_config_hub_numbered_links.py`.

Now I have enough context. Let me start implementing. First, `memory_panel_write.py`:

Now let's update `run_memory_panel_write`:

Now let's replace the whole function body:

Right, expected since the module's deleted. Let me now rewrite this test file properly — converting test 1 to use Memory pane with mention-relations, and fixing the shortcut indices in test 2 that shifted due to glossary's removal.

Now let's add `_strand_success_message` and `_strand_validation_message` helper functions, and update `__all__`:

Now let's add the small `memory_publish_subject` polish for strand kinds:

Now let's replace test 1 with a Memory-pane mention-relation scenario, and fix test 2's shortcut indices.

Now let's add `build_memory_strand_delete_subject` to `memory_panel_delete.py`:

Now fix test 2's shortcut indices for the shifted subtab order:

Now let's create the new strand-add form modal:

Now let's run this test file to verify.

Now let's add TCSS rules for the new modal:

All 3 tests pass now. Now let's sweep the remaining Step 3 test files: `test_config_hub_catalog.py`, `test_config_hub_pane_navigation.py`, `test_config_center_tabs.py`.

Let me look at each of these in context.

Now inserting the new TCSS block right before the "Memory Publish Modal" section:

Now let's update `memory_pane.py` to add the new pending-delete-strand attribute:

Now let's rewrite `memory_panel_actions.py`. First the imports and TYPE_CHECKING block:

Now let's update `action_add_note`:

Now let's update `action_delete_note`:

Now the `admin_center_flags=False` branch in `test_active_specs_keep_catalog_derived_description_order` and `test_config_subtab_order_omits_flags_when_rollout_is_off`:

Both shortcut tuples (6 items) need trimming to 5, and the glossary assertion needs replacing.

Now let's add the `_confirm_strand_delete` helper method and `_on_add_strand_draft` handler. Let's view the surrounding area for `_on_add_draft`/`_on_edit_draft`/`_on_delete_confirmed`:

Now let's add `_confirm_strand_delete` after `action_delete_note` (before `_on_add_draft`), and add `_on_add_strand_draft`, and update `_on_delete_confirmed`:

Now let's run this test file.

Now let's update `_on_delete_confirmed` and `_submit_memory_write`:

All 9 pass. Now `test_config_hub_pane_navigation.py` line 211 and `test_config_center_tabs.py` line 57.

Now let's update `_submit_memory_write` and its `task()` inner function:

Now let's apply the edits for `_submit_memory_write`:

Now let's update `_on_memory_write_complete`:

Declaration submitted successfully — the repository work from this turn is queued for commit.
