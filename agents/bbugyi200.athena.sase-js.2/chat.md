# Chat History - ace-run (sase-js.2)

- **TIMESTAMP:** 2026-08-11 15:35:55 EDT
- **MODEL:** codex/gpt-5.5
- **AGENT:** sase-js.2

## Prompt

#gh:gh_sase-org__sase
%id(2, clan=sase-js, bead=sase-js.2)
%model:@medium_worker
%auto
Can you complete the work for bead sase-js.2? The bead is already reserved for you and assigned to your agent
name: it was set to status=in_progress before you started reading this, either by the `sase bead work` launch
checkpoint or by the runtime promoting an ad-hoc wait-time claim. Do not set the status by hand. Read its
description and design file, do the work, and close the bead with
`sase bead close sase-js.2 --note "<what you verified>"`. Closing an assigned phase bead is unaffected by the
parent-close descendant guard. Do NOT close the parent epic. Do not create beads yourself: record discovered
follow-up work as a `PROPOSED FOLLOW-UP:` entry via
`sase bead note sase-js.2 'PROPOSED FOLLOW-UP: <one-line summary — detail>'`; the epic's land agent triages
these into task beads.

## Response

I'll start by reading the bead's description and design file.

I'll explore the current codebase to scope out exactly what exists for this retirement work.

Now let me dispatch two parallel research agents to map the full scope while I dig into the core Python files myself.

While those research agents run, I'll dig into the core Python files myself — the loader, models, and rendering fallback path.

Now let's look at where `load_ref_xprompts` and `reject_misplaced_ref` are consumed, plus the rendering/parsing files.

No design doc in this repo confirms the exact symbol names the requester listed; those names don't exist verbatim here. Let me confirm the actual data structures/functions around the ref catalog in full detail, plus check the CHANGELOG and pyo3 bindings.

Now let me read the key ref-related methods in full.

Now the ref-specific methods block (1322-1350, 1450-1516, 1655-1710, 1826-1884):

Now the load_refs_from_dir and load_plugin_refs functions:

Now let's check `canonical_ref_input`, `entry_kind_value`, `workflow_reference_prefix`, and other functions near line 506-534 and 2879, plus 2604 and 2854 for the "ref" wire entry conversion, and content_layout.rs for the supporting types.

Now let's check `canonical_ref_input` (line 2879) and the `is_ref`/wire conversion sections at 2604, 2814-2862.

Now let's check `canonical_ref_input` at ~2879 and `xprompt_from_config_entry` at 2814-2862.

Now let's check the test at line 3936 for `misplaced_ref_definitions_are_rejected_in_both_directions`, and also check `xprompt_to_snippet_template` / `workflow_reference_prefix` near 527-534 for how `#ref/` prefix is generated.

Now let's check pyo3 bindings for xprompt catalog and content layout / ref-related surface, and CHANGELOG files, and SCHEMA_VERSION bump patterns via git log.

Confirmed: release process is fully automated via release-plz (version bumps + changelog from Conventional Commits, no manual version file editing needed). Now let's check the SCHEMA_VERSION bump convention via git log/PR history.

Good, that's fully self-contained and safe to delete. Now let's check `content_layout.py` for the `sase/refs/` sources and `resolve_ref_file_sources`.

Confirmed — those are just test fixtures with `ref_kind: None` for unrelated mock entries. Now I have a complete picture. Let me do one final check on `MobileXpromptCatalogEntryWire`'s `ref_kind` field definition location and confirm nothing else in `bead/read.rs`/`host_bridge.rs` ties ref_kind to xprompt_catalog specifically (those were content-artifact-consumption `ref_kind` fields, unrelated — for a different `ArtifactConsumptionEvent.ref_kind` concept).

I now have a complete map. Let me compile the final report.

I have everything needed. Here is the report.

## `#ref/<kind>` Xprompt-Catalog Adapter — Deletion Map

### 1. `crates/sase_core/src/xprompt_catalog.rs` (5287 lines) — the adapter itself

All of the following are purely about scanning `sase/refs/*.md` and turning them into contextual `#ref/<kind>` catalog entries. Safe to delete as a block:

- `SASE_REF_PLUGIN_DIRS_JSON_ENV` const (L41)
- `CatalogXprompt.ref_kind` field (L128-129) and `StructuredSource.ref_kind` field (L155)
- `CatalogLoader` fields: `package_refs_dir` (L936), `plugin_ref_dirs` (L941), `ref_issues: RefCell<Vec<RefPlacementIssueWire>>` (L954)
- `CatalogLoader::new` ref-dir wiring (L972-976, 993-994, 1003, 1008, 1014)
- `ref_directory_sources` (L1322-1343)
- `ref_destination_for_xprompt_dir` (L1450-1458)
- `record_ref_issue` (L1472-1476)
- `reject_reserved_ref_name` (L1490-1495)
- `reject_config_ref` (L1497-1513)
- `load_refs_from_dir` (L1655-1707) — the core "sase/refs/<kind>.md → `ref/<kind>` renderer" loader
- `load_plugin_refs` (L1826-1882)
- ref-issue calls inside `load_xprompts_from_dir`, `load_skills_from_dir`, `load_plugin_xprompts`, `load_plugin_skills`, `load_all_xprompts` (the "refs own the reserved `ref/` namespace" enforcement, e.g. L633-639, 693-699, 827-833, 867-873)
- `canonical_ref_input` (L2879-2900) — per-kind input-type table (`commit`→`line`, `bead`→`bead_id`/`word`, etc.)
- `is_ref` parsing + `ref_kind: is_ref.then(...)` in `load_xprompt_from_markdown` (L2579-2583, 2604) and `xprompt_from_config_entry` (L2854-2857)
- `entry_kind_value`'s `REF_NAMESPACE_SEGMENT` branch (L513-515)
- `structured_entry`'s `ref_kind: entry.ref_kind.clone()` (L418)
- Tests: `ref_markdown_loads_as_contextual_renderer_with_canonical_input` (L3856-3913), `canonical_ref_inputs_cover_builtin_and_document_kinds` (L3915-3933), `misplaced_ref_definitions_are_rejected_in_both_directions` (L3935-3980)

Everything else in this file (skill/memory/workflow loading, snippet composition, `SCHEMA_VERSION = 1` at L36) is unrelated to refs and must stay.

### 2. `sase_xprompt_lsp` crate — completion/hover glue

No dedicated "ref catalog" module; ref support is threaded through the generic xprompt-assist pipeline:
- `crates/sase_xprompt_lsp/src/catalog_cache.rs` calls `load_editor_xprompt_catalog`/`load_editor_snippet_catalog` (L9-16, 613) — generic, keep, but entries will simply stop carrying `ref_kind`.
- `crates/sase_xprompt_lsp/src/server.rs:1168`: filters xprompt-arg-path completion by `entry.ref_kind.is_some()` before calling `editor_build_xprompt_ref_arg_completion_candidates` — this is the bridge from catalog entries into the (kept) artifact-ref payload completion; needs updating, not a clean delete (see Ambiguous below).
- `server.rs:5868-5887`, `3064`: tests/fixtures with `ref_kind`.
- `semantic_tokens.rs` and the rest of the LSP use `ArtifactRefContextWire` for the separate `@kind:` at-reference system — unrelated to `#ref/<kind>`, keep.

### 3. Grep results for requested symbols

| Symbol | Found? | Location | Role |
|---|---|---|---|
| `ref_kind` | yes | `xprompt_catalog.rs` (adapter), `editor/wire.rs:369`/`host_bridge.rs:719` (`XpromptAssistEntry`/`MobileXpromptCatalogEntryWire` field), `editor/completion.rs:106,1335`, `sase_xprompt_lsp/server.rs:1168`, `sase_gateway` fixtures/contract | Marks a catalog entry as a ref renderer; consumed generically |
| `ref_sidecar_role` | **not found** | — | Does not exist in repo |
| `ref_path_globs` | **not found** | — | Does not exist (repo uses `path_globs` on `ArtifactRefDocumentRootWire`, unrelated to xprompt catalog) |
| `ref_shadowed_sources` | **not found** | — | Does not exist |
| `sidecar_ref_config` | **not found** | — | Does not exist |
| `generated_sidecar_ref` | **not found** | — | Does not exist |
| `reject_misplaced_ref` | **not found** (name differs) | `xprompt_catalog.rs:1497` `reject_config_ref`, `content_layout.rs:522` `ref_placement_issue` | Closest matches; enforce ref-namespace placement rules |
| `effective_sidecar_ref_policies` | **not found** | — | Does not exist |
| `ArtifactRefDocumentRootWire` | yes | `artifact_ref/wire.rs:137`, used throughout `artifact_ref/mod.rs`, `editor/completion.rs`, `editor/diagnostics.rs` | KEEP — general artifact-ref document-root config (`path_globs` etc.) |
| `ArtifactRefContextWire` | yes | `artifact_ref/wire.rs:193`, used throughout `artifact_ref/*`, `editor/completion.rs`, `bead/read.rs`, `sase_xprompt_lsp/server.rs`, `sase_core_py` | KEEP — general artifact-ref context |
| `filter_artifact_ref_path_payloads` | yes | `artifact_ref/filter.rs:76`, re-exported `lib.rs:248`, bound in `sase_core_py/lib.rs:411,3399` | KEEP — general path-glob filter primitive |
| `ARTIFACT_REF_PATH_FILTER_WIRE_SCHEMA_VERSION` | yes | `artifact_ref/wire.rs:10` (`= 1`) | KEEP — wire schema constant for filter payloads |
| `filtered` resolution status | yes | `artifact_ref/mod.rs:633-644` `filtered_resolution()`, `status: "filtered".to_string()` | KEEP — one of the general `resolve_artifact_ref` status values |

None of `ref_sidecar_role`, `ref_path_globs`, `ref_shadowed_sources`, `sidecar_ref_config`, `generated_sidecar_ref`, `reject_misplaced_ref`, `effective_sidecar_ref_policies` exist anywhere in this checkout (verified with both exact and fuzzy/substring greps). They may be names from the not-yet-implemented "ref contract" design doc rather than this repo's current code — worth confirming with whoever wrote the design doc before assuming they need cleanup here.

### 4. Delete vs Keep summary

**Delete** (purely `#ref/<kind>` xprompt-catalog adapter):
- `xprompt_catalog.rs`: everything listed in section 1 above.
- `content_layout.rs`: `REF_DIRECTORY_SEGMENT` (L24), `REF_NAMESPACE_SEGMENT` (L31), `RefSourceWire` (L182) + `ref_sources` field (L251), `RefPlacementRuleWire` (L451), `RefPlacementIssueWire` (L464), `ref_reference_name`/`ref_reference_kind`/`is_reserved_ref_reference`/`is_invokable_ref_kind`/`reserved_ref_namespace_issue`/`ref_placement_issue` (L476-522+), `ref_sources()`/`push_ref_directory_source`/`push_ref_symbolic_source`/`refs_layout_path` (L1026-1171+), plus their tests (L1545-1650ish). Confirmed via grep these are used *only* by `xprompt_catalog.rs` and re-exported through `lib.rs:390-394` — no other caller.
- `MobileXpromptCatalogEntryWire.ref_kind` (`host_bridge.rs:715-719`), `XpromptAssistEntry.ref_kind` (`editor/wire.rs:368-369`), and the `ref_kind:` plumbing in `assist_entries_from_catalog` (`editor/completion.rs:106`) once nothing produces it.
- `sase_gateway/src/contract.rs:583` doc line for `ref_kind`.

**Keep** (general artifact-ref plumbing — explicitly to be re-pointed, not deleted):
- `crates/sase_core/src/artifact_ref/*` entirely: `ArtifactRefContextWire`, `ArtifactRefDocumentRootWire`, `filter_artifact_ref_path_payloads`, `ARTIFACT_REF_PATH_FILTER_WIRE_SCHEMA_VERSION`, `resolve_artifact_ref`/`filtered_resolution`, `editor_build_artifact_ref_payload_inventory`.
- `editor/completion.rs`'s at-reference (`@kind:`) machinery: `known_artifact_ref_kinds` (L856, driven by `ArtifactRefContextWire.document_roots`, unrelated to `#ref/<kind>`), `append_artifact_path_candidates`, `build_artifact_ref_payload_inventory`.

### 5. Ambiguous / doesn't cleanly separate

- `editor/completion.rs:1329-1377` `build_xprompt_ref_arg_completion_candidates` (aka `editor_build_xprompt_ref_arg_completion_candidates`): takes an `XpromptAssistEntry` and reads `entry.ref_kind`, then calls into the kept `build_artifact_ref_payload_inventory`/`ArtifactRefContextWire` machinery. This is the exact seam between the adapter (delete) and the ref-contract plumbing (keep) — it can't be deleted outright since it's the only path that turns a `#ref/<kind>` xprompt's typed input into artifact-payload completions; it will need to be re-pointed once the new ref-contract design supplies kinds another way. Same for `server.rs:1168`'s `.filter(|entry| entry.ref_kind.is_some())` gate.
- `MEMORY_NAMESPACE_SEGMENT`/`ref_kind` share the same `entry_kind_value` dispatcher (L506-517) and the same `CatalogXprompt`/`XpromptAssistEntry`/`MobileXpromptCatalogEntryWire` structs as skill/memory entries — deletion must remove only the `ref_kind` arm/field, not the shared struct or memory-handling code.
- `sase_content_layout` (pyo3-bound, `sase_core_py/src/lib.rs:6676-6692`) returns `ref_sources` as part of a larger shared layout dict also used for skills/memory — Python callers that destructure this dict need updating, though no ref-specific function is separately bound.

### 6. Pyo3 bindings & schema versions

- No pyo3 function binds `load_editor_xprompt_catalog`/`load_editor_snippet_catalog` directly — only `compose_snippet_catalog` (generic, unaffected) is exposed. So the `#ref/<kind>` adapter itself has **no direct Python binding** to remove.
- `sase_content_layout` (pyo3-bound) transitively returns the `ref_sources` field being deleted from `SaseContentLayoutWire`/`ProjectContentLayoutWire`/`HomeContentLayoutWire` — Python-side consumers of that dict need review.
- Constants to consider bumping: `CONTENT_LAYOUT_SCHEMA_VERSION = 5` (`content_layout.rs:5`, bumped for the original `feat(core)!: add reference artifact contract` commit `4071bf0`) and `xprompt_catalog.rs`'s local `SCHEMA_VERSION = 1` (mobile xprompt-catalog response). `ARTIFACT_REF_PATH_FILTER_WIRE_SCHEMA_VERSION = 1` should NOT be touched (it belongs to the kept filter primitive).
- Release process: `release-plz.toml` + `.github/workflows/release-plz.yml` fully automate version bump + `CHANGELOG.md` from Conventional Commits (`feat!`/`fix!`/`BREAKING CHANGE:` footers, e.g. commit `4071bf0`). No manual changelog editing; a `feat(core)!:` or similar commit message with `BREAKING CHANGE:` footer is the established convention for schema-breaking removals like this one.

Good progress on the Rust side. Let me look at the ambiguous seam in the LSP completion code while I wait for the Python-side survey.

I have enough understanding to start executing the core Python retirement now. Let's begin with deleting the packaged renderer files and the loader module.

Now let's look at where `loader_refs` is wired into `xprompt/loader.py`.

Let me now start editing the core files. First, `xprompt/models.py`.

Now `xprompt/workflow_models.py`:

Now `xprompt/loader.py` — remove the `load_ref_xprompts`/`get_sase_package_refs_dir` import and `include_refs` plumbing.

Now let me verify the exact line ranges for the `prompt_catalog.py` surgical edits one more time and double check `_startup_prompt_catalog.py` context lines precisely.

Confirmed. Now I have everything needed to write the complete report.

Confirmed — no hits, so those three files are unrelated to the ref-adapter and need no changes. Now I have a complete picture and can write the final report.

Now `xprompt/_catalog_sources.py`:

Now let's remove the synthetic-source branches in `classify`, `source_path_display`, `_source_definition_path`, and `package_xprompt_dirs`, plus fix `_all_xprompts`.

Now fix `package_xprompt_dirs` and `_all_xprompts`:

# Inventory: `#ref/<kind>` xprompt adapter — ACE + CLI surfaces

Scope note up front: I confirmed the exact fields `ref_kind` / `ref_sidecar_role` / `ref_path_globs` / `ref_shadowed_sources` exist **only** as `XPrompt`/`Workflow` model attributes that mark an xprompt as a synthetic `ref/<kind>` renderer, and flow downstream into ACE's `XPromptAssistEntry`, the mobile-helper JSON, and `sase xprompt list`. Separately, `#ref/<kind>` (the xprompt-syntax spelling) gets rewritten by `rewrite_ref_xprompt_references`/`process_artifact_references` into the equivalent `@<kind>:<payload>` artifact-reference syntax before rendering. **The `@kind:payload` "artifact reference" system itself (scanning, highlighting, `@`-mention completion, consumption ledger, staging) is a separate, more general feature that is *not* part of this adapter and is out of scope** — it's reused by, not owned by, the `#ref/<kind>` xprompt layer. I flag every place the two are intertwined so edits don't accidentally touch the general `@` system.

One important false-friend: `ref_kind` is also an unrelated field name on `ArtifactConsumptionEvent`/`stage_prompt_artifact`/prompt-archive records (`src/sase/core/artifact_consumption.py`, `src/sase/core/prompt_artifact_staging.py`) meaning "the kind of the artifact that was cited" — nothing to do with the XPrompt model field. Tests using that field are **not** part of this adapter (see §7).

---

## 1. `prompt_catalog.py` / `_startup_prompt_catalog.py`

**`src/sase/ace/tui/prompt_catalog.py`** — builds `#ref/<kind>` completion *indirectly*: `get_all_xprompts()` (loader, out of scope) already returns `ref/<kind>` entries as regular xprompts, and `build_xprompt_assist_entries(project=project)` (→ `_xprompt_arg_assist_catalog.py`, see §3) turns them into `XPromptAssistEntry` objects carrying the four `ref_*` fields. This file's *own* ref-specific code is narrower — two helper functions that track ref-renderer source directories purely for cache-invalidation/file-watching:

- `_ref_source_dirs()` (lines 285–304) — resolves `resolve_ref_file_sources(...)` (from `sase.content_layout`) plus `_plugin_ref_source_dirs()`.
- `_plugin_ref_source_dirs()` (lines 307–322) — walks `sase_xprompts` plugin resources for a `refs/` subdirectory.
- Consumers: `_prompt_source_token()` lines 154–158 (`ref_dirs = [...]`) and 165 (`("ref_files", _prompt_file_tokens(ref_dirs))`); `prompt_source_watch_paths()` lines 185–189 (a `*[... for directory in _ref_source_dirs(project)]` spread).
- Import to drop: `resolve_ref_file_sources` from the `sase.content_layout` import block (line 25).

**Classification: surgically strip.** Delete both functions and their 3 call sites; the rest of the file (memory dirs, xprompt dirs, config token, snippet catalog composition) is general and unrelated to refs.

**`src/sase/ace/tui/actions/_startup_prompt_catalog.py`** (this is the real path — `src/sase/ace/tui/_startup_prompt_catalog.py` as named in the prompt doesn't exist). This file does **not** build `#ref/` completions; it's the generic catalog-rebuild scheduler/worker orchestrator. Its only ref-adjacent code is inside `_refresh_visible_prompt_catalog_surfaces()`:

```python
402  completion_kind = str(getattr(text_area, "_completion_kind", ""))
403  invalidate_artifact_refs = getattr(text_area, "invalidate_artifact_ref_completion_cache", None)
...
408  if callable(invalidate_artifact_refs):
409      invalidate_artifact_refs()          # general — invalidates the whole @ catalog, keep
410  if (
411      getattr(text_area, "_file_completion_active", False)
412      and completion_kind.startswith("xprompt")
413      and completion_kind != "xprompt_arg_ref"   # ← ref-specific exclusion
414  ):
415      text_area._refresh_file_completion_from_cursor()
```

**Classification: surgically strip one line.** Remove the `and completion_kind != "xprompt_arg_ref"` clause at line 413 (once `"xprompt_arg_ref"` no longer exists as a completion kind, the exclusion is meaningless). The `invalidate_artifact_refs()` call itself stays — it invalidates the general `@` warm catalog used by both features.

---

## 2. `xprompt_browser_helpers.py` — synthetic-source special cases

Two source-path prefixes name a ref renderer that has no standalone `.md` file:

- `SIDECAR_REF_CONFIG_SOURCE_PREFIX` (imported from `sase.sidecar_ref_config`, line 20) — a renderer synthesized from `repos.sidecar.*.<role>.ref` in `sase.yml`.
- `GENERATED_REF_SOURCE_PREFIX` (imported from `sase.xprompt.loader_refs`, line 25) — a renderer with no file at all (built-in default sentence).

In `classify_source()` (lines 79–88):
```python
79  # Contextual ref renderers synthesized from sidecar config have no
80  # standalone definition file, so they are never editable as markdown.
81  if source_path.startswith(SIDECAR_REF_CONFIG_SOURCE_PREFIX):
82      role = source_path.removeprefix(SIDECAR_REF_CONFIG_SOURCE_PREFIX)
83      return "Project sase.yml", f"sase/sase.yml ref renderer for {role}", False
84
85  if source_path.startswith(GENERATED_REF_SOURCE_PREFIX):
86      role = source_path.removeprefix(GENERATED_REF_SOURCE_PREFIX)
87      return "Built-in", f"generated ref renderer for {role}", False
```

In `resolve_source_to_file_path()` (lines 276–284):
```python
276  # sidecar_ref_config:{role} → the sase.yml that owns the ref renderer;
277  # generated_sidecar_ref:{role} has no source file at all.
278  if source_path.startswith(SIDECAR_REF_CONFIG_SOURCE_PREFIX):
279      project_root = discover_project_root() or Path.cwd()
280      path = resolve_project_config_read_path(project_root)
281      return str(path) if path is not None else None
282
283  if source_path.startswith(GENERATED_REF_SOURCE_PREFIX):
284      return None
```

**Classification: surgically strip.** Both branches are self-contained `if`-blocks in otherwise-general dispatch functions (which also classify `plugin:`, `default_config`, `config`, `config_overlay:`, `local_config`, `project_local_config:`, plain filesystem paths, etc.). Remove the two branches from each function plus the two now-unused imports (lines 20, 25). Everything else in the file (`BrowserItem`, `is_yaml_backed_source`, `get_git_root`, `has_git_changes`) is untouched.

---

## 3. Other ACE widget files (`ref_kind`/`ref_sidecar_role`/`ref_path_globs`/`ref_shadowed_sources`/artifact_ref completion)

I verified your 11 candidates plus did my own sweep (`grep -rn '\bref_kind\b|\bxprompt_arg_ref\b|...'` across `src/sase/ace`) and found **6 additional files** that also need surgical edits because they dispatch on the `"xprompt_arg_ref"` completion-kind string (the UI-side marker for "filling in a `#ref/<kind>(...)` argument"), even though they never touch the model fields directly.

### Your 11 candidates

| File | Verdict | Ref-specific parts |
|---|---|---|
| `_artifact_ref_highlight.py` | **Surgical.** | Whole file is the general `@`-syntax highlighter/warm-cache mixin (unrelated to `#ref/<kind>`). Only 2 spots reference `"xprompt_arg_ref"` as a member of a set: line 328 (`on_worker_state_changed`) and line 360 (`invalidate_artifact_ref_completion_cache`) — both `... in {ARTIFACT_REF_COMPLETION_KIND, "xprompt_arg_ref"}`. Drop `"xprompt_arg_ref"` from both sets. |
| `_prompt_input_bar_completion_rows_simple.py` | **Surgical.** | `append_xprompt_completion_row()` line 39: `kind = f"ref/{entry.ref_kind}" if entry.ref_kind else entry.kind` → simplify to `kind = entry.kind`. Lines 46–47: `if entry.ref_sidecar_role: content.append(...)` → delete. The other 3 row-renderer functions in the file (jinja/placeholder/prompt-word) are unrelated. |
| `_xprompt_arg_assist_catalog.py` | **Surgical.** | `build_xprompt_assist_entries()` lines 47–50 and `xprompt_assist_entry_from_workflow()` lines 79–82 each pass through `ref_kind=`, `ref_sidecar_role=`, `ref_path_globs=`, `ref_shadowed_sources=` from the underlying catalog/`Workflow` entry. Delete those 4 kwargs in both call sites (8 lines total); everything else (building assist entries for *all* xprompts, local-xprompt merge logic) stays. |
| `_xprompt_arg_assist_models.py` | **Surgical.** | `XPromptAssistEntry` dataclass fields `ref_kind`/`ref_sidecar_role`/`ref_path_globs`/`ref_shadowed_sources` (lines 40–43) — delete. `XPromptArgCompletionContext.completion_kind` `Literal[...]` (line 85) includes `"xprompt_arg_ref"` — remove that member. Rest of the models (`XPromptInputHint`, `ActiveXPromptArgHint`, `PendingXPromptCompletionSpacer`) untouched. |
| `_xprompt_arg_assist_detection.py` | **Surgical, tiny.** | `_completion_kind_for_input()` (lines 234–252): `Literal[...]` return type includes `"xprompt_arg_ref"` (line 241); body has `if entry.ref_kind is not None: return "xprompt_arg_ref"` (lines 244–245) — delete those 3 lines. All the cursor-detection/colon/paren parsing logic (~440 other lines) is fully general and used by every xprompt argument kind. |
| `_prompt_input_bar_completion_panel_content.py` | **Surgical, tiny.** | `_row_layout()` line 139: `if kinds.artifact_ref or kinds.xprompt_arg_ref` → drop `or kinds.xprompt_arg_ref`. `_append_candidate_row()` line 223: `elif kinds.artifact_ref or kinds.xprompt_arg_ref:` → same. Rest of dispatcher (xprompt/directive/vcs/jinja/placeholder/prompt-word/history rows) untouched. |
| `_prompt_input_bar_completion_rows.py` | **Keep unchanged.** | Pure re-export facade; none of the re-exported names are ref-specific (nothing it imports/exports needs deletion). |
| `_prompt_input_bar_completion_rows_artifacts.py` | **Keep unchanged.** | This *is* the general `@`-mention row renderer (`append_artifact_ref_completion_row`, kind/file/payload rows, badges). It's reused for `#ref/<kind>` arg rows today only because the dispatcher passes the same `ArtifactRefPayloadCompletionMetadata`; nothing inside this file names `ref_kind` or `xprompt_arg_ref`. No edit needed here — it keeps serving the surviving `@` feature. |
| `artifact_ref_completion.py` (widgets/) | **Surgical.** | Stable facade module. Ref-specific: `_build_ref_xprompt_arg_completion_result = _menu.build_ref_xprompt_arg_completion_result` (line 69), the `build_ref_xprompt_arg_completion_result()` wrapper function (lines 122–142), and its `__all__` entry (line 235). Delete all three; the rest (catalog loading, `detect_artifact_ref_completion_context`, `build_artifact_ref_completion_result`, `ARTIFACT_REF_COMPLETION_KIND`) is the general `@` facade and stays. |
| `_file_completion_base.py` | **Surgical.** | One self-contained method: `_ref_xprompt_arg_completion_result(self, ctx: XPromptArgCompletionContext)` (lines 317–353), which reads `ctx.entry.ref_kind` and calls `build_ref_xprompt_arg_completion_result`. Delete the method, its `build_ref_xprompt_arg_completion_result` import (line 17), and (once unused) the `XPromptArgCompletionContext` TYPE_CHECKING import (line 46, used *only* by this method's signature). Everything else — `_artifact_ref_completion_result()` (general `@`), panel state, path/commit/bug snapshot warmers — is shared general infrastructure and stays. |
| `_artifact_ref_completion_menu.py` | **Surgical.** | One function: `build_ref_xprompt_arg_completion_result()` (lines 238–282) — builds payload-only rows for a `#ref/<kind>` argument by prefixing `@{ref_kind}:` and reusing the general menu builder. Delete it; the rest of the file (`ArtifactRefCompletionCatalog`, `build_artifact_ref_completion_result`, `kind_inventory`, `payload_inventory`, `build_catalog_payload_memos`, `payload_rows`, `age_label`, `wire_match_runs`) is the shared `@` engine and stays. |

### 6 additional files found (dispatch on the `"xprompt_arg_ref"` completion-kind string, not in your list)

| File | Verdict | Ref-specific parts |
|---|---|---|
| `_file_completion_accept.py` | **Surgical.** | `_move_file_completion()` lines 264–267 (`if self._completion_kind == "xprompt_arg_ref": ... return True`); `_accept_file_completion()` lines 285–286 (`if self._completion_kind == "xprompt_arg_ref": return self._accept_ref_xprompt_arg_completion(selected)`); whole method `_accept_ref_xprompt_arg_completion()` lines 404–431. Delete all three; VCS/xprompt/placeholder/history-word/`@`-artifact accept logic (~500 other lines) is general. |
| `_file_completion_refresh.py` | **Surgical.** | One `if self._completion_kind == "xprompt_arg_ref": ...` block, lines 95–119, inside `_refresh_file_completion_from_cursor()`. Delete the block; the `ARTIFACT_REF_COMPLETION_KIND` branch right above it (lines 62–93, general `@`) and everything else stays. |
| `_file_completion_tab.py` | **Surgical.** | `_try_xprompt_arg_completion_tab()` lines 409–410 (`if ctx.completion_kind == "xprompt_arg_ref": return self._try_ref_xprompt_arg_completion_tab(ctx)`); whole method `_try_ref_xprompt_arg_completion_tab()` lines 470–536. Delete both; the rest of the Ctrl+T dispatcher (jinja/directive/xprompt/history/VCS tab completion) is general. |
| `_prompt_input_bar_completion_panel_kinds.py` | **Surgical, tiny.** | `CompletionPanelKinds` dataclass field `xprompt_arg_ref: bool` (line 55) and its classification `xprompt_arg_ref=completion_kind == "xprompt_arg_ref"` (line 88). Delete both; the rest of the classifier (xprompt/directive/vcs/jinja/... flags) stays. |
| `_prompt_input_bar_completion_panel_labels.py` | **Surgical.** | `completion_panel_title()` lines 58–59 (`if kinds.xprompt_arg_ref: return _xprompt_ref_arg_panel_title(...)`); helper functions `_xprompt_ref_arg_panel_title()` (lines 83–93) and `_artifact_ref_payload_source_label()` (lines 96–103, used only by the former). Delete all three. Note: `artifact_ref_completion_subtitle()` (lines 160–201) is genuinely shared between `kinds.artifact_ref` and `kinds.xprompt_arg_ref` today — keep this function, just drop the `or kinds.xprompt_arg_ref` condition at its one call site (next row). |
| `_prompt_input_bar_completion_panel.py` | **Surgical, tiny.** | One condition: `elif kinds.artifact_ref or kinds.xprompt_arg_ref:` (line 164) → `elif kinds.artifact_ref:`. Everything else (panel show/hide, subtitle rendering, `show_xprompt_arg_hint` — which is generic to *any* xprompt with required inputs, not ref-specific) stays. |

### Files confirmed as pure general-`@` infrastructure (no ref-specific code at all — checked, not just assumed)

`_artifact_ref_completion_catalog.py`, `_artifact_ref_completion_context.py`, `_artifact_ref_completion_models.py`, `_artifact_ref_entity_catalogs.py` — grepped for `ref_kind`/`ref_sidecar_role`/`ref_path_globs`/`ref_shadowed_sources`/`xprompt_arg_ref`: zero hits. These implement document/file/chat/bead/agent candidate discovery for the `@` mention menu generally and need **no changes**.

---

## 4. `src/sase/integrations/_mobile_helper_catalog.py`

Two response builders: `patch_tags_response()` (Patch tags — unrelated) and `xprompt_catalog_response()` (the mobile client's xprompt catalog JSON). Ref-specific lines are inside the per-entry dict comprehension:

```python
113  "ref_kind": entry.ref_kind,
114  "ref_sidecar_role": entry.ref_sidecar_role,
115  "ref_path_globs": (
116      list(entry.ref_path_globs)
117      if entry.ref_path_globs is not None
118      else None
119  ),
120  "ref_shadowed_sources": list(entry.ref_shadowed_sources),
```
and in the `stats` dict:
```python
151  "ref_count": projection.stats.ref_count,
```

**Classification: surgically strip.** Delete lines 113–120 and line 151; `patch_tags_response()` and the rest of `xprompt_catalog_response()` (name/kind/inputs/skill/source fields) stay untouched.

---

## 5. `src/sase/main/xprompt_handler.py`

`handle_xprompt_command()` dispatches to 6 subcommand handlers. Only `_handle_list()` (`sase xprompt list`) touches refs:

```python
149  "ref_kind": wf.ref_kind,
150  "ref_sidecar_role": wf.ref_sidecar_role,
151  "ref_path_globs": (
152      list(wf.ref_path_globs) if wf.ref_path_globs is not None else None
153  ),
154  "ref_shadowed_sources": list(wf.ref_shadowed_sources),
```

Also related (but a level below "surface"): `_include_refs_or_legacy()` (lines 172–178), used at lines 93–94 to call `get_all_prompts(include_refs=True)` / `get_all_xprompts(include_refs=True)` with a `TypeError` fallback for pre-`include_refs` loader signatures. This helper only exists because the loader (out of scope, being handled separately) currently accepts an `include_refs` kwarg; once that kwarg is removed from the loader, this shim becomes dead code and the two call sites simplify to plain `get_all_prompts()` / `get_all_xprompts()`.

**Classification: surgically strip.** Delete the 4 dict lines above (149–154); delete `_include_refs_or_legacy` and inline its calls once the loader's `include_refs` kwarg is gone (coordinate with your loader work). `_handle_expand`, `_handle_explain`, `_handle_graph`, `_handle_catalog`, `_handle_show` are entirely unrelated and untouched.

---

## 6. Docs

### `docs/xprompt.md`
- **ToC**: line 53, `  - [Artifact Reference XPrompts](#artifact-reference-xprompts)` — remove (sub-item of "Reference Syntax", line 52).
- **`### Artifact Reference XPrompts`** — **lines 522–632** (ends right before `## Arguments` at line 634). This entire subsection is wholly about the adapter: the `@kind:...`/`#ref/kind:...` equivalence example, `ref: true` front matter requirement, the 7-tier precedence table (project `sase/refs/`, sidecar config, home refs, project-specific home refs, plugin `refs/`, packaged built-in, generated default), the canonical-input table, renderer template variable docs (`sidecar`, `fragment`, `ref` mapping), the `repos.sidecar.*.<role>.ref` YAML example, path-glob filter semantics, and the closing note that `sase xprompt list/show`, ACE, and the LSP expose `kind: ref`/`ref_kind`/sidecar filter metadata. **Delete the whole subsection.**
- Line 243 ("Explicit xprompt and artifact references keep precedence over glossary matches.") — generic LSP precedence statement covering *all* xprompt references and `@` artifact references, not specific to `#ref/<kind>`. **No change needed.**

### `docs/content_layout.md`
Scattered mentions across sections that otherwise describe the whole content layout — **surgically edit, don't delete the doc**:
- Top path table, lines 11, 16–17: rows `Project ref renderers | <project>/sase/refs/`, `Home ref renderers | ~/sase/refs/`, `Project-specific home refs | ~/sase/refs/<project>/` — remove these 3 rows.
- `## Paths That Did Not Move`, lines 32–38: bullet mentions `src/sase/xprompts/refs/` package resource path and "contextual ref renderers in a sibling `refs/` resource directory" (plugin bullet) — rewrite to drop the `refs/` clauses.
- `## Migrating A Project`, line 54: `./refs/  -> ./sase/refs/` migration mapping line inside the before/after code block — remove.
- `## Compatibility And Collisions`, lines 103–106: standalone paragraph "`sase/refs/` is the canonical source for contextual `#ref/<kind>` renderer files... See [Artifact Reference XPrompts]..." — remove the paragraph (and the now-dead cross-reference link, once xprompt.md's section is gone).

### `docs/plugins.md`
- Line 7 (intro paragraph): "...resource plugins expose package data such as xprompt files, contextual ref renderers, and `default_config.yml`." — drop the "contextual ref renderers" clause.
- Line 23 (Plugin Groups table, `sase_xprompts` row): "XPrompt templates, workflows, and `refs/` renderers" — drop the "`refs/` renderers" clause.
- Lines 31–35: paragraph entirely about `sase_xprompts`' `refs/<kind>.md` ref-renderer overrides (`ref: true` requirement, precedence, cross-reference to xprompt.md) — remove; keep the surrounding sentence about ordinary `xprompts/` templates.

---

## 7. Tests

I anchored on your two named files, then grepped `tests/` for the precise adapter markers (`\bref_kind\b`, `\bref_sidecar_role\b`, `\bref_path_globs\b`, `\bref_shadowed_sources\b`, `loader_refs`, `sidecar_ref_config`, `generated_sidecar_ref`, `GENERATED_REF_SOURCE_PREFIX`, `SIDECAR_REF_CONFIG_SOURCE_PREFIX`, `xprompt_arg_ref`, `rewrite_ref_xprompt_references`, `#ref/`) rather than the looser `artifact_ref`/`ArtifactRef` pattern, which pulls in the (out-of-scope) general `@` system's own test suite. Word-boundary matching also matters: `artifact_ref_kind_label_width` and `_load_known_artifact_ref_kinds` both contain the substring `ref_kind` but are general-`@` names, not the XPrompt model field — I read each file to confirm before classifying.

| Test file | Tests | Verdict |
|---|---|---|
| `tests/test_xprompt_ref_sources.py` | 5/5 | **Delete whole file.** Tests `loader_refs.py`'s ref registry: packaged-refs loading, project shadowing, sidecar-config-before-generated-default precedence, full precedence chain (project → config → home → plugin → generated), unknown-ref-file load issues, "ref metadata rejected outside ref sources." |
| `tests/test_artifact_ref_xprompt_integration.py` | 2/2 | **Delete whole file.** `test_research_ref_forms_share_rendering_staging_consumption_and_completion` and `test_research_filters_can_opt_into_non_markdown_and_disabled_sidecar_is_unknown` — both explicitly test `#ref/<kind>` vs `@kind:` equivalence end-to-end. |
| `tests/test_sidecar_ref_config.py` | 1/1 | **Delete whole file.** Tests `sidecar_ref_config.py`'s policy derivation (`_sidecar_role_ref_kind`, defaults/overrides). |
| `tests/artifact_refs/test_preprocessing_rendering.py` | 6/6 | **Delete whole file.** Every test name is `test_ref_xprompt_...`/`test_ref_renderer_...`/`test_renderer_...`: colon/named-form equivalence to `@`, primitive renderer context, multi-project renderer context, non-recursive-scan guarantee, Jinja-output protection, undefined-variable failure naming. |
| `tests/ace/tui/widgets/test_artifact_ref_completion_widget.py` | 1/19 | **Surgical.** Only `test_ref_xprompt_arg_completion_uses_artifact_payload_catalog` (lines 98–139) plus its dedicated helper `_ref_xprompt_entry()` (lines 54–73) test `#ref/plans:` arg completion / `"xprompt_arg_ref"`. The other 18 tests (bare `@`, Ctrl+T file reveal, directory drill-down, commit/path snapshot refresh, bug-candidate projection, etc.) are the general `@` widget and stay. |
| `tests/ace/tui/modals/test_xprompt_browser_helpers.py` | 2/11 | **Surgical.** `test_classify_source_marks_synthesized_ref_renderers_read_only` (61–81) and `test_resolve_source_to_file_path_for_synthesized_ref_renderers` (84–94) — delete. Remaining 9 tests cover `classify_source`/`is_yaml_backed_source`/`append_input_args`/browser filtering unrelated to refs. |
| `tests/xprompt/test_cli_show_resolve.py` | 1/14 | **Surgical.** `test_record_json_projection_is_complete_and_serializable` (line 279) asserts `set(projection)` includes `"ref_kind"`, `"ref_sidecar_role"`, `"ref_path_globs"`, `"ref_shadowed_sources"` (lines 317–320) — drop those 4 literal-set entries. The other 13 tests are unrelated (name normalization, shadowing, raw-span exactness, memory/step record projection, source classification). |
| `tests/test_mobile_helpers.py` | 1/3 | **Surgical.** `test_xprompt_catalog_bridge_returns_structured_projection` asserts `"ref_count": 0` (line 102) and the 4 `ref_*` entry keys (lines 114–117) — drop those 5 lines from the expected dict. Other 2 tests (attachment metadata, invalid `include_pdf`) are unaffected. |
| `tests/artifact_refs/test_preprocessing_effects.py` | 1/12 | **Surgical.** Only `test_ref_xprompt_raw_spelling_is_preserved_in_staging` (lines 24–41) tests `#ref/plans:` raw-spelling preservation through staging. The other 11 tests use plain `@kind:` syntax; their `ref_kind`/`event.ref_kind` hits are the *unrelated* `ArtifactConsumptionEvent.ref_kind` field (see false-friend note above) — not ref-adapter code, no change needed there. |
| `tests/artifact_refs/test_preprocessing_expansion.py` | 3 cases in 1/10 tests | **Surgical, fine-grained.** `test_known_reference_failure_exits_clearly` is one `@pytest.mark.parametrize` block (lines 198–207) mixing `@`-only and `#ref/`-only cases; remove only the 3 `#ref/`-form tuples: `("#ref/plans:missing.md", "missing")` (202), `("#ref/plans:../escape.md", "malformed")` (205), `("#ref/unknown:thing.md", "unknown_kind")` (206). Keep the `@plans:...`/`@commit:...` tuples and all 9 other tests. |
| `tests/agents_sync/test_prompt_archive.py` | 0/6 | **No change — false friend.** `ref_kind` here is the prompt-archive record's "kind of the cited artifact" field (agent artifact archiving), unrelated to the XPrompt model field. |
| `tests/agents_sync/test_prompt_archive_validation.py` | 0/8 | **No change — false friend.** Same `ref_kind` archive-record field as above. |
| `tests/artifact_consumption/test_ledger.py` | 0/5 | **No change — false friend.** `ArtifactConsumptionEvent.ref_kind`, unrelated. |
| `tests/test_artifact_file_query_facade.py` | 0/7 | **No change — false friend.** Same `ArtifactConsumptionEvent.ref_kind` construction. |
| `tests/test_prompt_artifact_staging.py` | 0/7 | **No change — false friend.** `stage_prompt_artifact(..., ref_kind="file", ...)`, unrelated. |
| `tests/ace/tui/widgets/test_at_reference_completion_rendering.py` | 0/12 | **No change — false friend.** Matched only because `artifact_ref_kind_label_width` contains the substring `ref_kind`; it's the general `@` row-width helper. |
| `tests/ace/tui/visual/_ace_prompt_png_snapshot_helpers.py`, `tests/ace/tui/visual/test_ace_png_snapshots_prompt_highlighting.py` | — | **No change — false friend.** Matched via `_load_known_artifact_ref_kinds`/`_artifact_ref_kinds_warming` (general `@` highlighter cache), not the XPrompt field. |

---

## Summary — quick-reference by disposition

**Delete whole file:**
- `tests/test_xprompt_ref_sources.py`
- `tests/test_artifact_ref_xprompt_integration.py`
- `tests/test_sidecar_ref_config.py`
- `tests/artifact_refs/test_preprocessing_rendering.py`

**Delete a dedicated doc subsection:**
- `docs/xprompt.md` lines 522–632 (`### Artifact Reference XPrompts`) + ToC line 53.

**Surgically strip ref-specific code, keep the rest:**
- `src/sase/ace/tui/prompt_catalog.py`, `src/sase/ace/tui/actions/_startup_prompt_catalog.py`
- `src/sase/ace/tui/modals/xprompt_browser_helpers.py`
- `src/sase/ace/tui/widgets/_artifact_ref_highlight.py`, `_prompt_input_bar_completion_rows_simple.py`, `_xprompt_arg_assist_catalog.py`, `_xprompt_arg_assist_models.py`, `_xprompt_arg_assist_detection.py`, `_prompt_input_bar_completion_panel_content.py`, `artifact_ref_completion.py`, `_file_completion_base.py`, `_artifact_ref_completion_menu.py`
- `_file_completion_accept.py`, `_file_completion_refresh.py`, `_file_completion_tab.py`, `_prompt_input_bar_completion_panel_kinds.py`, `_prompt_input_bar_completion_panel_labels.py`, `_prompt_input_bar_completion_panel.py` (newly found)
- `src/sase/integrations/_mobile_helper_catalog.py`, `src/sase/main/xprompt_handler.py`
- `docs/content_layout.md`, `docs/plugins.md`
- Tests: `test_artifact_ref_completion_widget.py`, `test_xprompt_browser_helpers.py`, `test_cli_show_resolve.py`, `test_mobile_helpers.py`, `test_preprocessing_effects.py`, `test_preprocessing_expansion.py`

**Keep unchanged (verified, not ref-specific despite superficial keyword matches):**
- `_prompt_input_bar_completion_rows.py`, `_prompt_input_bar_completion_rows_artifacts.py`, `_artifact_ref_completion_catalog.py`, `_artifact_ref_completion_context.py`, `_artifact_ref_completion_models.py`, `_artifact_ref_entity_catalogs.py`
- `tests/agents_sync/test_prompt_archive*.py`, `tests/artifact_consumption/test_ledger.py`, `tests/test_artifact_file_query_facade.py`, `tests/test_prompt_artifact_staging.py`, `tests/ace/tui/widgets/test_at_reference_completion_rendering.py`, `tests/ace/tui/visual/*prompt_highlighting*` (all false-friend `ref_kind`/`artifact_ref` matches — general artifact-consumption or general `@`-highlighter code)

This is very helpful — thorough and precise. Before proceeding with the ACE sweep, let me verify one discrepancy: agent 2 says to delete `tests/test_sidecar_ref_config.py` entirely, but I'd planned to keep `sidecar_ref_config.py` itself (per the plan's "keep the shape of `effective_sidecar_ref_policies`"). Let me check that test file.

Let me continue the `_catalog_models.py` edit I was mid-way through, then work through the ACE files.

Now remove `refs: int` field from `CatalogStats`:

Now `StructuredCatalogStats.ref_count`:

Now `main/xprompt_handler.py`:

Now `cli_show_resolve.py` — let's view the full relevant sections including lines 190-200, 220-235, and 460-475.

Now let's fix the `resolve_show_record` function's ref field usage and remove `_get_all_xprompts_include_refs`:

Now let's view around line 220-235 and 460-475 (originally) for the other two sites:

Good, that edit already landed correctly (diagnostics were stale). Now let's remove `_get_all_xprompts_include_refs` and fix the other two sites.

Now let's fix the remaining site around line 464-466 (the `entry_kind` classifier checking `.ref_kind is not None`):

Now fix `cli_show_render.py`:

Stale (already fixed). Now let's finish `xprompt/loader.py` — fix `get_all_xprompts`/`get_all_prompts`'s `include_refs` params and `__all__`.

Now fix `get_all_xprompts`/`get_all_prompts` signatures and the `include_refs` block:

Now fix `get_all_prompts`'s `include_refs` param:

Good, that part is already correctly fixed — the diagnostics were stale. Now let's fix `get_all_prompts`:

Good, `loader.py` is clean now (stale diagnostic). Now let's remove the `include_refs` reference in `_catalog_sources.py` docstring earlier mentioned, then move to the `content_layout.py`/`content_layout_wire.py` deletions.

Now let's tackle the core rendering fallback. First `artifact_ref_renderers.py`:

Now let's rewrite `artifact_ref_prompt_parsing.py` to drop the `#ref/` rewriting machinery:

Good, clean. Let's remove the unused `sys` import:

Now let's update `artifact_ref_prompt.py` to remove `#ref/` handling and the renderer registry plumbing.

Now the `_expand_artifact_references` body:

This looks clean and correct. Now let's check `sase/artifact_refs.py` (the public facade) and `artifact_ref_context.py`/`content_layout.py` for `known_kinds`/`ref_renderer_registry` references.

Good — only that test file remains, which we're deleting per plan. Let's delete it now, along with the other fully-ref tests, and handle the surgical test edits.

Now remove `resolve_ref_file_sources` function and `RefSource` from the import + `__all__`:

`RefSource` is already removed correctly (stale diagnostic). Just need to remove `resolve_ref_file_sources` from `__all__` still:

Now `content_layout_wire.py` — remove `RefSource`, `ref_sources` field, `_ref_source()`:

Now let's check `RefSource` in `__all__` at the bottom of `content_layout_wire.py`:

Clean (stale diagnostic). Let's check the tests that pin the `SaseContentLayout`/JSON shape to make sure the schema tests don't require `ref_sources`:

Now let's remove this whole test function and the `resolve_ref_file_sources` import:

Now let's fix `ace/tui/prompt_catalog.py` per agent 2's report:

Now let's remove `_ref_source_dirs` and its call sites:

Now let's fix the callers of `_ref_source_dirs` (`_prompt_source_token`, `prompt_source_watch_paths`) and the imports:

Now let's fix the two remaining call sites:

These two tests (`test_prompt_source_token_changes_for_ref_file_create`, `test_prompt_source_watch_paths_include_ref_roots`) test exactly the deleted ref-source watching feature. Let's remove them.

Now let's fix `_startup_prompt_catalog.py`:

Now `xprompt_browser_helpers.py`:

Let's apply the surgical edits agent 2 identified:

Now let's fix the matching test file `tests/ace/tui/modals/test_xprompt_browser_helpers.py`:

Let's work through the ACE widget files. First `_xprompt_arg_assist_models.py`:

It's now unused since I deleted its only two consuming tests. Remove the import:

Now let's fix `_xprompt_arg_assist_models.py`:

Now `_xprompt_arg_assist_catalog.py`:

Now `_xprompt_arg_assist_detection.py`:

Stale, already fixed. Let's fix `_completion_kind_for_input`:

Now let's update the 4 call sites:

Good, `XPromptAssistEntry` is still used elsewhere in the file. Let's now check the test file for `_completion_kind_for_input` direct calls that might need updating:

Now `_prompt_input_bar_completion_rows_simple.py`:

Now `_prompt_input_bar_completion_panel_content.py`:

Now `_prompt_input_bar_completion_panel_kinds.py`:

Now `_prompt_input_bar_completion_panel_labels.py`:

Let's remove the two dead functions and their call site:

Still used at line 150 (in `artifact_ref_completion_subtitle`, which stays per agent 2's note). Good, no further change needed there. Now `_prompt_input_bar_completion_panel.py`:

Now `_artifact_ref_highlight.py`:

Now `artifact_ref_completion.py` (widgets facade):

Pre-existing environment noise. Let's edit the widget facade:

Now `_artifact_ref_completion_menu.py`:

Confirmed — only used by the deleted function. Let's remove that import:

Let's remove this test and its now-unused import:

Right, my read window earlier missed 2 trailing lines. Let's clean those up:

Now `_file_completion_base.py`:

Let's find the `_ref_xprompt_arg_completion_result` method:

Now let's find who calls `_ref_xprompt_arg_completion_result`:

Now remove the now-unused `build_ref_xprompt_arg_completion_result` import and check `XPromptArgCompletionContext` TYPE_CHECKING import usage:

Both confirmed unused now. Let's remove them:

Confirmed, unused now. Remove it:

Now `_file_completion_accept.py`:

Now let's find and remove the `_accept_ref_xprompt_arg_completion` method:

Now `_file_completion_tab.py`:

Let's remove `_try_ref_xprompt_arg_completion_tab` and its call site:

Good — no more `xprompt_arg_ref` references in this file. Now let's check `_file_completion_refresh.py`:

Good, all clear (pre-existing stub noise). Now let's check `_file_completion_open.py` which also calls `_get_xprompt_arg_completion_context`:

Let's do a comprehensive sweep for anything remaining:

All source code is clean except the one test file agent 2 flagged for surgical edit. Let's handle it now:

Let's remove `_ref_xprompt_entry` and its consuming test:

Let's do a final comprehensive sweep across the whole Python tree:

Now `tests/test_mobile_helpers.py`:

Now `tests/artifact_refs/test_preprocessing_effects.py`:

Good, `plan` is in scope. Now let's make all the fixes to `test_preprocessing_effects.py`:

Now let's fix `test_preprocessing_expansion.py`:

Now let's remove the 3 `#ref/`-prefixed parametrize tuples and the now-unused `sidecar_sentence` import:

No longer used anywhere. Let's remove it from the helpers file:

Let's check the remaining `tests/artifact_refs/` files for similar sentence-format assumptions:

Clean. Let's do the final comprehensive sweep for the remaining symbol names:

Now let's move to the docs. First `docs/xprompt.md`:

I'll use `sed` for this precise line-range deletion since the Edit tool's exact-match is fighting whitespace:

I need to restore the `## Arguments` header. Let me fix this:

Clean. Now `docs/content_layout.md`:

Now the "Compatibility And Collisions" paragraph around line 103-106:

Clean, all remaining are unrelated words like "references"/"reference". Now `docs/plugins.md`:

Now let's move to the Rust side. Let's start with `content_layout.rs`:

Now let's remove `RefSourceWire` and the field:

Now let's remove `REF_NAMESPACE_SEGMENT` and update the `REF_DIRECTORY_SEGMENT` doc comment:

Let's delete this whole block (lines 417-539):

Now let's view and remove the `ref_sources()`, `push_ref_directory_source`, `push_ref_symbolic_source` functions:

Now let's delete the `ref_sources()` function and `push_ref_directory_source`/`push_ref_symbolic_source`, keeping `refs_layout_path`:

Let's clean up this re-export block:

Let's fix the import block and remove the const:

Let's remove the ref-related struct fields and constructor wiring:

Let's remove the `ref_kind: None` and `ref_kind: xprompt.ref_kind` lines:

Now let's remove `reject_reserved_ref_name` and `reject_config_ref`:

Now let's fix `placement_warnings` to remove the `ref_issues` chain:

Now let's look at `load_xprompts_from_dir` and the surrounding functions in detail:

Now let's fix `load_skills_from_dir`'s ref rejection block:

Now let's properly delete this whole function:

Now let's handle `load_plugin_xprompts`, `load_plugin_skills`, `load_plugin_refs`:

Let's fix these three functions:

Now let's check `package_refs_dir.clone()` at what's now around line ~2074:

Let's remove all three tests:

Now let's check `xprompt_from_config_entry`'s `ref_kind:` construction:

Excellent, `xprompt_catalog.rs` is completely clean. Now let's check that the file compiles (or at least try `cargo check`):

Good, only one error remaining — the `MobileXpromptCatalogEntryWire.ref_kind` wire field itself needs removing (that's in `host_bridge.rs` per agent 1's report). Let's find it:

Now the `ref_kind: None,` construction site in host_bridge.rs:

Now let's fix `editor/completion.rs`. First the `assist_entries_from_catalog` construction site (line ~106):

Let's remove this whole function:

All 7 confirmed as pure `ref_kind: <value>,` lines with no other code on the line. Safe to remove with sed:

Clean. Now let's re-run `cargo check`:

Progress. Let's fix `editor/mod.rs` re-export and `editor/diagnostics.rs`:

Now `lib.rs`:

Now let's fix `editor/diagnostics.rs`:

Let's re-check the build:

`sase_core` compiles cleanly. Now let's check the other crates (`sase_core_py`, `sase_xprompt_lsp`, `sase_gateway`):

Good, `sase_core`, `sase_gateway`, `sase_core_py` (so far) all pass. Now let's fix `sase_xprompt_lsp/src/server.rs`:

Now let's fix the completion dispatch at line ~1160:

Whole workspace compiles now, just one unused-parameter warning to clean up. Let's check that function's signature and callers:

Let's do a final full-workspace check and then run the test suite:

Clean build across the whole Rust workspace. Now let's do a broader sweep for any remaining `ref_kind`/`ref/<kind>` residue across the whole sase-core repo:

This whole test is testing the deleted `build_xprompt_ref_arg_completion_candidates` function. Let's remove it:

All simple standalone lines. Let's remove them with sed:

Let's look at this test context in `server.rs`:

This whole test is exercising exactly the deleted `#ref/<kind>` argument completion feature. Let's remove it:

The entire workspace, including all tests, now compiles cleanly. Let's run the Rust test suite:

Found it. Let's set `LD_LIBRARY_PATH` and re-run just the `sase_core_py` test:

Let's check for any failures across the full log:

Only one failure — the "committed contract snapshot" test, which is exactly the doc-string change I made. Let's look at it:

There's a proper writer function via the binary. Let's check `main.rs` usage and regenerate properly:

Let's regenerate the committed snapshot properly:

Good, the file regenerated. Let's verify the test now passes:

Now let's re-run the full workspace test suite to confirm everything is green:

All 100% green across the whole Rust workspace. Let's update task tracking and move to running the Python test suite (`just check`).

Now let's switch to the Python repo and run `just install` to pick up the local Rust changes, then `just check`.

The Rust binding rebuilt successfully with my changes and installed into the Python venv. Now let's run `just check`:

Just formatting issues. Let's run auto-format:

`just fmt` applied the formatting fixes. Let's re-run `just check`:

Now let's fix the test file:

Now let's re-run `just check`:

The command is still running in the background. I'll wait for it to complete rather than poll.

I'll wait for the background `just check` run to notify me when it completes.

I'll simply wait — the harness will notify me automatically when the background `just check` run finishes.

The Rust side is fully verified (workspace compiles and all tests pass), and the Python side's `just check` is running in the background — I'll pick back up once it reports back with lint/test results.

This is deprecated but will block-wait for the task properly. Let me use it once:

Great progress — 25,916 tests passed. Let's find the one import error:

Let's view this test file in full to properly retire the ref-related test coverage:

Now let's verify this test file passes and re-check for any other stale references:

All 16 tests pass. Now let's run `just check` again to confirm everything is green:

Now let's wait for this properly-tracked background task.

Still running. I'll wait for the automatic completion notification.

`just check` exited 0 — full lint gates + scoped test suite all green. Let's view the summary output to confirm what ran:

Given the scope of this change (90.6% test selection, cross-repo Rust+Python retirement), let's run `just check-full` for full confidence before closing the bead.

Still running — I'll wait for the completion notification.

`just check-full` exited with code 1 (failure). Let's inspect the log for what failed:

This confirms the `check-full` failure is unrelated to my changes — these are pre-existing flaky tests (from a historical flake-tracking database spanning days, unrelated to xprompt/artifact-refs) that I just verified pass cleanly in isolation. Let me record this as a follow-up note and then close the bead.

Let's do a final review of the complete diff before closing the bead:

Everything is verified and consistent with the plan's scope. Let's close the bead with a detailed verification note.

The bead is closed. Summary of what was done:

**sase-js.2 "Retire the ref xprompt surface"** is complete — this retired the `#ref/<kind>` xprompt adapter from epic `sase-js` (Artifact reference contract), landing as its own reviewable deletion per the design doc.

- **sase repo**: 56 files changed (−1521 net lines). Deleted the packaged ref renderer files, `loader_refs.py`, the `ref_kind`/`ref_sidecar_role`/`ref_path_globs`/`ref_shadowed_sources` fields threaded through every xprompt catalog wire (ACE completion widgets, mobile helper bridge, CLI show/list, LSP launcher env), the `#ref/` rewriting machinery, and the seven-level renderer precedence table. Builtins now fall back to the pre-`sase-ho` hardcoded rendering path — byte-identical for most kinds, with a documented, plan-sanctioned temporary regression for document-kind refs (`@plans:`/`@research:`) until later phases land the new provider projection.
- **sase-core repo**: 17 files changed (−1053 net lines). Removed the matching Rust catalog-loading, content-layout source enumeration, and namespace-policing types, plus the LSP completion seam — while explicitly preserving the primitives the design doc calls out to keep (`ArtifactRefDocumentRootWire`, `ArtifactRefContextWire`, `effective_sidecar_ref_policies`'s shape).
- **Verification**: full Rust workspace (`cargo test --workspace`) is 100% green; Python `just check` is 100% green after rebuilding the binding from the edited linked checkout; `just check-full`'s only failure was 6 pre-existing, unrelated flaky tests (verified to pass in isolation), which I recorded as a `PROPOSED FOLLOW-UP` note on the bead rather than treating as a regression.

I'll start by verifying the current state of both repositories before proceeding with the close-and-commit workflow.

These match the described work exactly, confirming the changes were made for this bead. I'll now close the bead per the finalizer's instructions.

The bead was already closed by the prior pass and is published (no unpublished-close error). Now I'll commit the changes, starting with the main workspace.

All 66 files in the main workspace are part of this change (no unrelated files to exclude). I'll get the full file list and commit them all via the skill.

Now let's invoke the commit skill for the main workspace with every file listed explicitly.

The 10 deleted files are already staged from the prior pass; I only need to pass `-f` for the remaining 56 unstaged files.

This matches — the 10 already-staged deletions plus these 55 unstaged files equal all 65 non-doc... let's just re-run with the correct file list (the already-staged ones will remain staged and get included in the commit automatically).

Commit succeeded. Let's verify the main workspace is clean and pushed.

Main workspace is clean and in sync with origin. Now for the sase-core linked repo.

All 17 files are modified (none staged yet), all part of the same retirement work.

Both repositories are now clean and pushed.

## Summary

Bead **sase-js.2** ("Retire the ref xprompt surface") was already closed and its close published by a prior pass; I confirmed publication (no unpublished-close error from `sase bead close`) and appended a verification note.

Committed the outstanding work in both repos:

- **Main workspace** (`sase`): 66 files (56 modified, 10 deleted) — commit `refactor(xprompt)!: retire the #ref/<kind> contextual renderer adapter`. Removed the packaged `refs/*.md` renderers, `loader_refs.py`, and the `ref_kind`/`ref_sidecar_role`/`ref_path_globs`/`ref_shadowed_sources` fields threaded through ACE completion widgets, the mobile helper bridge, and CLI show/list.
- **Linked repo** (`sase-core`): 17 modified files — commit `refactor(core)!: retire the #ref/<kind> xprompt-catalog adapter`. Removed the matching Rust catalog-loading, content-layout ref-source enumeration, and LSP completion seam, while leaving the general `@kind:payload` artifact-reference primitives untouched.

Both repos verified clean with `git status --short --branch` showing no divergence from `origin/master`.
