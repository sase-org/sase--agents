# Chat History - ace-run (sase-js.4--code)

- **TIMESTAMP:** 2026-08-11 18:20:09 EDT
- **MODEL:** claude/sonnet
- **AGENT:** sase-js.4--code

## Linked Chats

- 1. --plan — `~/.sase/chats/202608/gh_sase_org__sase-ace_run-sase_js_4__plan-260811_132713.md`
- **2. --code** — `~/.sase/chats/202608/gh_sase_org__sase-ace_run-sase_js_4__code-260811_132713.md`

## Prompt

%model:@medium_worker
#gh:gh_sase-org__sase
@sase/repos/plans/202608/builtin_refs_and_prompt_ref_context.md

The above plan has been reviewed and approved. Implement it now.


## Response

I'll start by exploring the existing codebase structure to understand the current state before implementing this plan.

Good, install succeeded. Let me verify the wire schema version and explore the key files.

Now let me dig into the Rust source to understand exact function signatures for the new bindings.

Given the scope, I'll parallelize research across several subsystems while I read the core files myself.

Found it: `/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_13/src/sase`. Let me search for each item in parallel.

Good, found the real src/sase directory. Let me explore it in parallel across the different topics.

Found it: the actual repo root is `/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_13` itself (not the `sase-core` linked repo). Let me read the target files.

Now let's read the two TUI widget files and check `artifact_ref_models.py` around line 14/309, plus whether `ArtifactEntry`, `PromptRefContext`, `completion_artifact_ref_kinds`, `parsable_artifact_ref_kinds` already exist anywhere.

Now I have everything needed. Let me compile the report.

Now let me add the binding wrappers to `artifact_ref_operations.py`.

Note: the actual repo root is `/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_13` (the `src/sase/` path you gave is directly under that, not under the linked `sase-core` checkout). All paths below are absolute under that root.

## 1. `artifact_providers/` pattern

- `src/sase/artifact_providers/__init__.py` (38 lines) — package docstring `"""Declarative artifact provider discovery and registries."""`, imports specific public names from private-named sibling modules (`_builtin.py`, `_hookspec.py`, and non-underscored `registry.py`), then re-exports everything through an explicit `__all__` list (alphabetized apart from grouping conventions — actually simple string-sort with some case grouping).
- `src/sase/artifact_providers/_builtin.py` (64 lines) — module docstring `"""SASE's builtin declarative artifact providers."""`, `from __future__ import annotations`, then stdlib imports, then a single relative import `from ._hookspec import hookimpl`. Defines a module-level constant (`ARTIFACT_REF_PROVIDER_SPEC_SCHEMA_VERSION = 1`), a factory function with a one-line docstring returning a spec dict, a `hookimpl`-decorated class (`BuiltinArtifactProviders`) with a one-line class docstring, and terminates with an explicit `__all__` (3 names, alphabetized).
- `src/sase/artifact_providers/_hookspec.py` (37 lines) — module docstring `"""Pluggy hook specifications for artifact provider plugins."""`, defines `hookspec`/`hookimpl` markers via `pluggy.HookspecMarker("sase_artifact")` / `HookimplMarker("sase_artifact")`, one class `ArtifactProviderHookSpec` with `@hookspec`-decorated stub methods (docstring only, body `...`), ends with `__all__`.

Pattern to replicate for `builtin_entries.py`, `builtin_entry_stitch.py`, `builtin_entry_patch.py`, `builtin_entry_bead.py`, `builtin_entry_agent.py`: each private module (leading underscore would be the convention if these are internal-only, but note your requested names have NO leading underscore — decide based on whether they need to be importable directly; the existing convention uses underscore-prefixed *internal* modules whose public symbols get re-exported through the non-underscored `__init__.py`). Each module: one-line docstring, `from __future__ import annotations`, minimal focused imports, functions/classes with short docstrings, trailing `__all__` list of exactly what's public from that file. The umbrella `__init__.py` then imports from each sibling and republishes via its own `__all__`.

## 2. `src/sase/core/prompt_artifact_staging.py` (442 lines, full read)

- `locked_file` import: `from sase.memory.locks import locked_file` (line 24). Used as a context manager: `with locked_file(lock_path, fcntl.LOCK_EX): ...` (three call sites: `_prune_prompt_artifact_pool`, `_append_manifest_record`, `_store_and_append_record`). Paired with `import fcntl` (stdlib).
- fsync pattern lives in `_append_manifest_record_unlocked` (lines 341-352): opens manifest in append mode (`"a", encoding="utf-8"`), writes the rendered line + `"\n"`, then `stream.flush()` followed by `os.fsync(stream.fileno())`.
- `_NON_FILE_REF_KINDS = frozenset({"agent", "bug", "commit"})` (line 33). In `stage_prompt_artifact`, after building the base record, `if ref_kind in _NON_FILE_REF_KINDS:` short-circuits straight to `_append_manifest_record(...)` and returns, skipping all file-classification/hashing/pooling logic entirely. To add `"stitch"` and `"patch"` you'd change this literal to `frozenset({"agent", "bug", "commit", "stitch", "patch"})`.
- `stage_prompt_artifact(*, raw_ref, expanded_ref, resolved_path, ref_kind, label, locator=None, workspace_root=None, agent_artifacts_dir=None) -> PromptArtifactRecord | None`: resolves the artifacts dir/workspace, builds `staging_root = workspace / ".sase" / "artifacts"`, computes `manifest_path`/`lock_path`, builds a base record via `_base_record`, resolves `source = _resolved_file(...)`, branches on `_NON_FILE_REF_KINDS`, else requires a real file, hashes it (`hash_file`), checks for clean VCS provenance (records repo+relpath, skips pooling) vs. size-limit skip vs. content-addressed pool copy (`_store_and_append_record` → `_store_pool_file`, then prunes pool if over budget). Entire body wrapped in `try/except Exception` that logs at debug and returns `None` — "staging is launch auxiliary work," never raises.
- `PromptArtifactRecord` is a `TypedDict` with fields: `schema_version, recorded_at, agent_artifacts_dir, raw_ref, expanded_ref, ref_kind, label, source_path, sha256, size_bytes, mime_type, pool_relpath, vcs_repo, vcs_relpath, locator, skipped_reason`.
- Module `__all__` = `["PROMPT_ARTIFACT_MANIFEST_NAME", "PROMPT_ARTIFACT_POOL_DIR", "PromptArtifactRecord", "stage_prompt_artifact"]`.

## 3. `src/sase/artifact_cli/references.py` (193 lines, full read)

Imports from `sase.artifact_refs`: `ArtifactRef, ArtifactRefContext, ArtifactRefResolution, artifact_ref_resolution_hint, launch_artifact_ref_context, parse_artifact_ref, resolve_artifact_ref`.

```python
@dataclass(frozen=True, slots=True)
class ResolvedArtifactReference:
    input: str
    canonical_reference: str
    parsed: ArtifactRef
    resolution: ArtifactRefResolution
    file: ArtifactFile | None
    context: ArtifactRefContext | None = None
    consumption: ArtifactConsumptionSummary | None = None

    @property
    def is_filesystem_backed(self) -> bool:
        return self.parsed.kind_type in {"chat", "document", "file", "bead", "agent"}

    def to_json_dict(self) -> dict[str, Any]:
        return {
            "reference": self.canonical_reference,
            "kind": self.parsed.kind,
            "fragment": (None if self.parsed.fragment is None else asdict(self.parsed.fragment)),
            "file": (None if self.file is None else artifact_file_json_dict(self.file)),
            "resolution": _resolution_json_dict(self.resolution),
            "consumption": (None if self.consumption is None else self.consumption.to_json_dict()),
        }
```

`resolve_cli_reference(value, *, context=None) -> ResolvedArtifactReference` (lines 71-95): normalizes bare-file-id sugar (`_normalize_artifact_reference`, regex `_BARE_FILE_ID_RE`), calls `parse_artifact_ref(normalized)`, defaults `context` via `launch_artifact_ref_context(is_home_mode=False)`, calls `resolve_artifact_ref(parsed, context=resolved_context)`, looks up a file record only when `parsed.kind_type == "file"` (via `_find_file_record`), and constructs `ResolvedArtifactReference` — note `entry`/builtin-entry fields are not currently populated anywhere in this constructor call, so adding an `entry: ArtifactEntry | None` field means also wiring a resolution branch into this function before it falls through to `resolve_artifact_ref`.

`__all__` = `["ResolvedArtifactReference", "artifact_file_json_dict", "resolution_error_lines", "resolved_file_path", "resolve_cli_reference"]`.

For your planned change: add builtin-entry resolution as an early branch inside `resolve_cli_reference` (before/instead of unconditionally calling `resolve_artifact_ref`), add `entry: ArtifactEntry | None = None` field to the dataclass, populate it in `to_json_dict()`, and extend `is_filesystem_backed` from `{"chat", "document", "file", "bead", "agent"}` to explicitly exclude `"stitch"`/`"patch"` (i.e. leave those two out of the set, or if `kind_type` for those isn't already one of the five strings, no change needed beyond confirming they're absent — grep showed no `"stitch"`/`"patch"` literal anywhere yet in this set).

## 4. `src/sase/artifact_refs.py` (118 lines, full read — facade)

Currently re-exports from 6 sibling modules: `artifact_ref_context` (context builders: `artifact_ref_context`, `artifact_ref_lsp_catalog_payload`, `launch_artifact_ref_context`, plus `ARTIFACT_REF_LSP_CATALOG_SCHEMA_VERSION`), `artifact_ref_entries` (`design_reference_for_plan_row`, `reference_for_agent_name`, `reference_for_entry_target`), `artifact_ref_lists`, `artifact_ref_models` (includes `BUILTIN_ARTIFACT_REF_KINDS`, `ArtifactRefContext`, etc.), `artifact_ref_operations`, `artifact_ref_prompt`, `artifact_ref_renderers`. Nothing named `ArtifactEntry`, `PromptRefContext`, `completion_artifact_ref_kinds`, or `parsable_artifact_ref_kinds` currently exists anywhere in the repo (confirmed via grep — zero hits) — these are new symbols you'll need to define upstream (presumably in `artifact_ref_models.py` / a new `artifact_ref_entries`-like module) before re-exporting them here. Both the `from ... import (...)` block and `__all__` list must be extended in parallel, matching this file's existing style (imports grouped by source module, `__all__` alphabetized as one flat list).

## 5. TUI widget usages of `BUILTIN_ARTIFACT_REF_KINDS`

- `src/sase/ace/tui/widgets/_artifact_ref_completion_menu.py`: imported at line 13 from `sase.artifact_refs`. Used twice in `kind_inventory()` (lines 251-267): `builtin = {kind.casefold() for kind in BUILTIN_ARTIFACT_REF_KINDS}` (line 255, to flag rows as `"builtin"` in menu output) and `for kind in dict.fromkeys((*BUILTIN_ARTIFACT_REF_KINDS, *catalog.kinds))` (line 266, to seed the ordered kind list for the completion menu). This is a menu/completion context → swap both to `completion_artifact_ref_kinds()`.
- `src/sase/ace/tui/widgets/_artifact_ref_highlight.py`: imported at line 15 from `sase.artifact_refs`. Used in `_load_known_artifact_ref_kinds()` fallback path (lines 87-93, inside an `except Exception:` when `artifact_ref_context(...)` fails): `kinds = frozenset(BUILTIN_ARTIFACT_REF_KINDS)` and `ArtifactRefCompletionCatalog(project, tuple(BUILTIN_ARTIFACT_REF_KINDS))`. This is the syntax-highlighting known-kinds fallback → swap both to `parsable_artifact_ref_kinds()`.

## 6. Complete grep results for `BUILTIN_ARTIFACT_REF_KINDS`

```
src/sase/artifact_refs.py:30:    BUILTIN_ARTIFACT_REF_KINDS,
src/sase/artifact_refs.py:77:    "BUILTIN_ARTIFACT_REF_KINDS",
src/sase/artifact_ref_models.py:14:BUILTIN_ARTIFACT_REF_KINDS = ("commit", "chat", "bug", "file", "bead", "agent")
src/sase/artifact_ref_models.py:309:                    *BUILTIN_ARTIFACT_REF_KINDS,
src/sase/ace/tui/widgets/_artifact_ref_highlight.py:15:    BUILTIN_ARTIFACT_REF_KINDS,
src/sase/ace/tui/widgets/_artifact_ref_highlight.py:87:        kinds = frozenset(BUILTIN_ARTIFACT_REF_KINDS)
src/sase/ace/tui/widgets/_artifact_ref_highlight.py:91:            ArtifactRefCompletionCatalog(project, tuple(BUILTIN_ARTIFACT_REF_KINDS)),
src/sase/ace/tui/widgets/_artifact_ref_completion_menu.py:13:    BUILTIN_ARTIFACT_REF_KINDS,
src/sase/ace/tui/widgets/_artifact_ref_completion_menu.py:255:    builtin = {kind.casefold() for kind in BUILTIN_ARTIFACT_REF_KINDS}
src/sase/ace/tui/widgets/_artifact_ref_completion_menu.py:266:        for kind in dict.fromkeys((*BUILTIN_ARTIFACT_REF_KINDS, *catalog.kinds))
```

Origin definition: `src/sase/artifact_ref_models.py:14` — `BUILTIN_ARTIFACT_REF_KINDS = ("commit", "chat", "bug", "file", "bead", "agent")`. It's also consumed internally at `artifact_ref_models.py:309` inside `ArtifactRefContext.known_kinds` (a `@property` building `dict.fromkeys((*BUILTIN_ARTIFACT_REF_KINDS, *(entry.kind for entry in self.document_roots)))`) — this is a 7th consumer not caught by grepping `artifact_refs.py`/TUI files alone, and since it's the source-of-truth module itself, decide whether `known_kinds` should also move to `parsable_artifact_ref_kinds()` for consistency once "stitch"/"patch" exist as non-`BUILTIN` kinds. Total distinct consumer files: `artifact_refs.py` (facade), `artifact_ref_models.py` (definition + one internal use), `_artifact_ref_highlight.py`, `_artifact_ref_completion_menu.py` — four files, ten grep hits.

This confirms the layout: `agents/<global_name>/{README.md, meta.json, state.json, commits.json, prompt.md, chat.md}` are all siblings under `root = f"agents/{run.global_name}"`. Now let's check `collect_entity_context` for bead_stores ordering and check `tribe` field (metadata key) and V2_METADATA_FIELDS content.

Found it — `validate_patch_name` is a Rust function, not Python. Let's read it.

I now have all the details needed. Here's the report.

## 1. `normalize_vcs_underscore_refs` / `extract_project_from_vcs_tag`

Both live in `src/sase/xprompt/_parsing_vcs_refs.py` and `_parsing_vcs_tags.py` respectively (there's also a compatibility re-export in `xprompt/_parsing.py` that wraps the real impl with cache-sync calls — prefer importing from the `_parsing_vcs_*` modules or `sase.xprompt` public surface).

```python
# src/sase/xprompt/_parsing_vcs_refs.py:28
def normalize_vcs_underscore_refs(prompt: str) -> str:
    """Normalize ``#gh_sase`` to ``#gh:sase`` for known VCS workflow names.
    ... Converting the first ``_`` after a known VCS prefix to ``:`` lets
    downstream patterns correctly split the VCS prefix from the ref name.
    """

# src/sase/xprompt/_parsing_vcs_tags.py:346
def extract_project_from_vcs_tag(tag: str) -> str | None:
    """Extract the project/ref name from a VCS workflow tag.
    Handles formats like ``#gh:sase ``, ``#gh!!:sase ``, ``#git(repo) ``.
    Returns the ref portion (e.g. ``"sase"``, ``"repo"``) or ``None`` if
    no ref is present.
    """
```

## 2. `protect_fenced_blocks` + segment-splitting logic

`protect_fenced_blocks` is in `src/sase/xprompt/_fenced_blocks.py:141`:
```python
def protect_fenced_blocks(text: str, blocks: list[str]) -> str:
    """Replace fenced and inline code with null-byte placeholders."""
    from ._literal_zones import code_literal_ranges
    return _protect_ranges(text, blocks, code_literal_ranges(text))
```
Pair it with `unprotect_fenced_blocks` (same module) to restore.

The splitting logic in `normalize_default_vcs_workflow` (`xprompt/_parsing_vcs_tags.py:214-260`, separator regex at line 22):
```python
_SEGMENT_SEPARATOR_RE = re.compile(r"^---\s*$", re.MULTILINE)

def normalize_default_vcs_workflow(prompt: str) -> str:
    from sase.xprompt._fenced_blocks import protect_fenced_blocks, unprotect_fenced_blocks
    frontmatter, body = _split_frontmatter_block(prompt)
    fenced_blocks: list[str] = []
    protected = protect_fenced_blocks(body, fenced_blocks)
    pieces = _SEGMENT_SEPARATOR_RE.split(protected)
    separators = _SEGMENT_SEPARATOR_RE.findall(protected)
    normalized_pieces = [
        normalize_default_vcs_workflow_segment(unprotect_fenced_blocks(piece, fenced_blocks))
        for piece in pieces
    ]
    rebuilt = normalized_pieces[0] if normalized_pieces else ""
    for sep, piece in zip(separators, normalized_pieces[1:], strict=False):
        rebuilt = f"{rebuilt}{sep}{piece}"
    return f"{frontmatter}{rebuilt}"
```
`_split_frontmatter_block` (same file) strips a leading YAML `---`/`---` block first. `inherit_vcs_workflow_tag` uses the identical pattern.

## 3. `extract_vcs_workflow_tag` vs `find_vcs_workflow_tag`

Both in `xprompt/_parsing_vcs_tags.py:44,61`:
```python
def extract_vcs_workflow_tag(prompt: str) -> str | None:
    """Extract a leading VCS workflow tag... Skips leading %directive tokens..."""
def find_vcs_workflow_tag(prompt: str) -> str | None:
    """Find the first VCS workflow tag anywhere in *prompt*.
    Unlike extract_vcs_workflow_tag, the tag does NOT need to be at the start
    of the prompt. It may appear on a later line or after some text on the
    first line, as long as it is preceded by a token boundary."""
```
`extract_` = anchored (`.match`) after directive prefix; `find_` = "non-leading" search anywhere (`.search`) via the embedded-tag pattern, i.e. a tag not required to lead the prompt.

## 4. `load_project_ref_display_snapshot`

`src/sase/project_display_names.py:231`:
```python
def load_project_ref_display_snapshot(
    projects_root: Path | str | None = None,
) -> ProjectRefDisplaySnapshot:
    """Fresh-load key, label, and alias projections in one inventory read.
    Inventory failures degrade to an empty projection..."""
```
Returns `ProjectRefDisplaySnapshot` (frozen dataclass, `project_display_names.py:141`), method:
```python
def project_key_for_ref(self, project_ref: str | None) -> str | None:
    """Resolve a key, alias, or label to canonical identity for selection."""
```
Usage examples: `ace/tui/actions/_state_init_late.py:27`, `artifact_cli/stats.py:61`, `artifact_cli/prune.py:36`, `artifact_cli/reclaim.py:33`, `artifact_cli/listing.py:30` — all call it with no args: `projects = load_project_ref_display_snapshot()`.

## 5. `list_project_records` / `effective_project_name`

`list_project_records` real impl: `src/sase/core/project_lifecycle_facade.py:49` (note: `main/patch_handler.py:59` has an unrelated stub with `*args/**kwargs` — don't use that one):
```python
def list_project_records(
    projects_root: Path | str,
    include_states: Sequence[str] | str = ("enabled",),
    *,
    include_home: bool = False,
    projects_only: bool = False,
) -> list[ProjectRecordWire]:
    """List lifecycle records under a projects root via ``sase_core_rs``."""
```
`effective_project_name`: `src/sase/core/project_lifecycle_wire.py:168`:
```python
def effective_project_name(record: ProjectRecordWire) -> str:
    """Return the user-facing project name for *record*."""
    return record.display_name or record.project_name
```

## 6. `project_spec_path` module / `sase_projects_dir`

There is no bare function `project_spec_path`; the module `src/sase/ace/patch/project_spec_path.py` exposes `preferred_project_spec_path`:
```python
def preferred_project_spec_path(
    project_dir: str, project_name: str, *, archive: bool = False
) -> str:
    """Resolve a project spec path preferring canonical over legacy.
    Returns the canonical ``.sase`` path if it exists, otherwise the legacy
    ``.gp`` path if it exists, otherwise the canonical path..."""
```
It's always imported lazily as `from sase.ace.patch.project_spec_path import preferred_project_spec_path` (13+ call sites, e.g. `main/utils.py:121`).

`sase_projects_dir`: `src/sase/core/paths.py:116`:
```python
def sase_projects_dir() -> Path:
    """Return the SASE projects directory."""
    return sase_subdir("projects")
```

## 7. `workspace_provider.peek_ref` vs `resolve_ref`

Both in `src/sase/workspace_provider/_registry.py`:
```python
def resolve_ref(ref: str, workflow_type: str) -> ResolvedRef:
    """... Raises: ValueError: If the reference cannot be resolved."""
def peek_ref(ref: str, workflow_type: str) -> ResolvedRef | None:
    """Read-only workspace reference lookup via provider plugins."""
```
`peek_ref` just returns `_get_manager().peek_ref(ref, workflow_type)` directly (no exception) — **returns `None` when no plugin claims the ref**, confirming read-only/non-claiming behavior vs `resolve_ref`'s raise-on-miss + workspace-claiming semantics.

`ResolvedRef` (`workspace_provider/_hookspec.py:43`):
```python
@dataclass(frozen=True)
class ResolvedRef:
    project_file: str
    project_name: str
    primary_workspace_dir: str
    checkout_target: str
    extra: dict[str, str] = field(default_factory=dict)
    canonical_ref: str | None = None
```

## 8. `artifact_ref_launch_context.py` (full file, 54 lines)

`src/sase/artifact_ref_launch_context.py`:
```python
def build_launch_artifact_ref_context[ContextT](
    *,
    artifact_ref_context_fn: Callable[..., ContextT],
    is_home_mode: bool,
    workspace_project_ref_fn: Callable[[Path], str | None],
) -> ContextT:
    workspace = Path.cwd()
    workspace_num = _workspace_num_from_environment()
    project = workspace_project_ref_fn(workspace)
    if workspace_num is None:
        try:
            from sase.main.utils import ensure_project_file_and_get_workspace_num
            _project_file, detected_num, detected_project = (
                ensure_project_file_and_get_workspace_num(create_missing=False)
            )
            workspace_num = detected_num
            project = detected_project or project
        except Exception:
            pass
    if workspace_num is None:
        workspace_num = 0 if is_home_mode else 1
    return artifact_ref_context_fn(workspace, workspace_num, project=project)


def _workspace_num_from_environment() -> int | None:
    for name in ("SASE_AGENT_WORKSPACE_NUM", "SASE_GIT_WORKSPACE_NUM", "SASE_GH_WORKSPACE_NUM"):
        raw = os.environ.get(name)
        if raw is None:
            continue
        try:
            return int(raw)
        except ValueError:
            continue
    return None
```
No `find_marker_from_cwd` usage in this file (that function lives in `workspace_provider/marker.py:138`, unused here — it's used elsewhere for checkout-marker discovery, not in this module).

## 9. `SASE_AGENT_PROJECT_FILE` / `SASE_ACTIVE_PROJECT_DIR`

- **Set**: `axe/runner_artifacts.py:213` — `os.environ["SASE_AGENT_PROJECT_FILE"] = project_file`. `SASE_ACTIVE_PROJECT_DIR` is set in `axe/run_agent_exec_retry.py:190,233`, `axe/run_agent_phases.py:132`, `axe/run_workflow_runner.py:180`, `axe/run_agent_runner_setup.py:364`, `agent/launch_spawn.py:96` (as subprocess env), `xprompt/workflow_executor_utils.py:159`.
- **Read** (not in `artifact_ref_launch_context.py`, which doesn't reference either var): `commit_instructions.py:86`, `workflows/commit_utils/post_commit.py:39`, `workflows/commit/commit_tracking.py:41`, `axe/run_agent_helpers_questions.py:55`, `axe/_process_start.py:291`, `plan_gate.py:484`, `llm_provider/commit_finalizer_state.py:142,335`, `llm_provider/commit_finalizer.py:570`, `file_hooks/engine.py:401,455` (all `SASE_AGENT_PROJECT_FILE`); `llm_provider/codex.py:120` reads `SASE_ACTIVE_PROJECT_DIR_ENV` constant from `env_contracts.py:8` (`SASE_ACTIVE_PROJECT_DIR_ENV = "SASE_ACTIVE_PROJECT_DIR"`).

## 10. `collect_repo_inventory`

`src/sase/repo_inventory.py:75`:
```python
def collect_repo_inventory(
    projects_root: Path | str | None = None,
    *,
    project: str | None = None,
    include_disabled: bool = False,
) -> RepoInventory
```
Returns `RepoInventory(tuple(records), tuple(issues))`. `RepoRecord` (`_repo_inventory_models.py:26`) has field `kind: RepoKind` where `RepoKind = Literal["primary", "sidecar", "linked", "external"]` (line 8). To find the primary repo: `next(r for r in inventory.records if r.kind == "primary")` (records are sorted with `primary` first per `_KIND_ORDER`).

Now let's look at `artifact_refs.py` and the two TUI widget files to update consumers.

Now let's update the two TUI widget consumers.

Found it. The repo root is `/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_13` with `src/sase/`. Let me read the target files directly.

Now I have items 1 and 2. Let's find item 3 (workflow_executor_steps_prompt.py) and item 4 (search for the exact function names), plus item 5 (`extract_vcs_workflow_tag` usage).

Now updating both files to use the memoized kind-catalog functions instead of the deleted constant.

Let's quickly smoke-test that these modules import correctly before moving on.

Task #1 is working. Let me mark it complete and run the existing test suite for a sanity check before continuing.

Here is the precise API reference gathered directly from the source (paths are all under `/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_13/`).

## 1. `sase.ace.patch.cache` — snapshot cache + `Patch`
File: `src/sase/ace/patch/cache.py`
```python
class PatchSnapshotCache:
    def get_file_specs(self, path: Path | str, project_display_name: str | None = None) -> list[Patch]: ...
def get_global_snapshot_cache() -> PatchSnapshotCache
```
Note: the second parameter is named `project_display_name`, not `display_name`. It's used as a cache-key component and stamped onto each returned `Patch.project_display_name`.

`Patch` (file: `src/sase/ace/patch/models/patch.py`, `@dataclass(init=False)`):
```python
name: str
description: str
parent: str | None
pr_url: str | None
pr_origin: str          # "sase"|"external"|"unknown"
status: str
file_path: str
line_number: int
bug: str | None = None
stitches: list[Stitch] | None = None
hooks: list[HookEntry] | None = None
comments: list[CommentEntry] | None = None
mentors: list[MentorEntry] | None = None
timestamps: list[TimestampEntry] | None = None
deltas: list[DeltaEntry] | None = None
project_display_name: str | None = None
refs: list[str] | None = None
stitch_section_header: str | None = None
```
Plus properties: `.cl`/`.commits` (legacy aliases for `pr_url`/`stitches`), `.project_basename`, `.project_name` (cached), `.project_query_name`. `ChangeSpec = Patch` (legacy alias). Confirms `mentors`, `pr_url`, `parent`, `status` all exist as stated.

## 2. `find_all_patches_cached`
File: `src/sase/ace/patch/cache.py:102`:
```python
def find_all_patches_cached(include_states: Sequence[str] | str = ("enabled",)) -> list[Patch]
```
Module-level wrapper around the process-global `_GLOBAL_CACHE.find_all_patches_cached(...)`; returns a flat `list[Patch]` (not per-project grouped) built from `iter_patch_project_file_records`. Each `Patch` has `.project_display_name` and `.name` as shown above.

## 3. `validate_patch_name` — Rust, not Python
Not defined anywhere in `src/sase`. It lives in Rust: `sase/repos/linked/sase-core/crates/sase_core/src/artifact_ref/mod.rs:1265`:
```rust
fn validate_patch_name(name: &str) -> Result<(), ArtifactRefError> {
    if name.is_empty() { ... }
    if name.chars().any(char::is_control) { ... }
    if name.starts_with(char::is_whitespace) || name.ends_with(char::is_whitespace) { ... }
    Ok(())
}
```
Doc comment: *"Patch names may contain spaces and have no reserved separator... project-qualified spellings are not accepted here; that lives on the resolved entry once the provider registry lands."* So: **interior spaces are explicitly permitted**; only empty, control chars, or leading/trailing whitespace are rejected. It's invoked only when building/parsing a `patch:` artifact-ref payload (lines 200, 515), and `patch` kind resolution itself returns `unresolved_kind_resolution("patch", rendered)` → status `"unknown_kind"` with diagnostic `"patch references resolve through the provider registry, not this crate"` — i.e. Rust deliberately defers `patch:` resolution to your new Python provider.

## 4. `sase.core.bead_read_facade`
File: `src/sase/core/bead_read_facade.py`. Parameter name is `beads_dir`, not `store_root`:
```python
def resolve_id(beads_dir: Path | str, issue_id: str) -> str
def show(beads_dir: Path | str, issue_id: str) -> Issue
```
Both call `require_rust_binding(...)` and on `ValueError` run `_raise_key_error_for_missing_issue`:
```python
def _raise_key_error_for_missing_issue(issue_id, exc):
    if "Issue not found:" in str(exc):
        raise KeyError(f"Issue not found: {issue_id}") from exc
    raise  # falls through, re-raises original ValueError
```
Underlying Rust (`crates/sase_core/src/bead/read.rs:752` `resolve_issue_id_in_issues`): if `issue_id` is empty or contains `-`, it's treated as already a full ID and returned unchanged (no lookup). Otherwise it's matched as the suffix after the final `-` of every known issue ID: exactly one match → resolved; zero matches → `BeadError{kind:"not_found", message:"Issue not found: {issue_id}"}`; 2+ matches → `BeadError{kind:"ambiguous", message:"ambiguous bead ID shorthand {id:?}: {candidates}"}`. `BeadError`'s `Display` is `"{kind}: {message}"` and the PyO3 binding wraps it as `PyValueError::new_err(format!("{err}"))`. So: **not-found → Python `KeyError`**, **ambiguous → plain `ValueError`** (message like `"ambiguous: ambiguous bead ID shorthand \"a1\": sase-a1, sase-a2"`), not converted to KeyError.

`sase/memory/sase_beads.md` confirms: *"Any argument naming an existing bead accepts the full ID (`sase-a1`) or the suffix after the final dash (`a1`, `a1.2`). Ambiguous shorthand fails and lists the candidates."*

## 5. `sase.agent.identity.resolve_local_agent_name`
File: `src/sase/agent/identity.py:72`:
```python
def resolve_local_agent_name(env: Mapping[str, str] | None = None) -> str | None
```
Metadata-first: reads `agent_meta.json`'s `name` key from `SASE_ARTIFACTS_DIR` first; falls back to `SASE_AGENT_NAME` env var; returns `None` if neither is present — confirmed `None` for a bare CLI invocation with no agent identity.

## 6. `agent_lanes.lane_name`
File: `src/sase/agent_lanes.py:120`:
```python
def lane_name(name: str) -> str:
    return parse_agent_family_name(name).family_name
```
Bare "lane" projection of a (local or global) agent name; doesn't normalize/globalize.

## 7. `agents_sync.v2_run_io`
File: `src/sase/agents_sync/v2_run_io.py`:
```python
def run_metadata_from_json(value: object) -> V2RunMetadataPayload
def run_state_from_json(value: object) -> V2RunStatePayload
```
`V2RunMetadataPayload` (`src/sase/agents_sync/v2_models.py:79`): `owner: AgentOwnerIdentity`, `project: V2ProjectIdentity` (`key`, `name`), `source_run_id: str`, `local_name: str`, `global_name: str`, `metadata: tuple[tuple[str, Any], ...]`, `schema_version: int`. `model`, `llm_provider`, `tribe` (also `clan_tribe`) are **not top-level fields** — they're keys inside `metadata`, validated against `V2_METADATA_FIELDS` in `src/sase/agents_sync/v2_validation.py:35` (also includes `bead_id`, `patch_name`, `plan`, etc.).

`V2RunStatePayload` (`v2_models.py:101`): `source_run_id: str`, `state: RunState` (Literal from `_STATES = {"active","waiting","completed","failed","stopped","dismissed"}`), `started_at: str | None`, `finished_at: str | None`, `dismissed_at: str | None`, `schema_version: int`.

Layout (from `src/sase/agents_sync/publication_snapshot.py:121,141-153`): all sibling files under one root `agents/<global_name>/`:
```
agents/<name>/README.md
agents/<name>/meta.json
agents/<name>/state.json
agents/<name>/commits.json
agents/<name>/prompt.md
agents/<name>/chat.md
```
(confirmed independently by the Rust resolver's `path = root.join("agents").join(name).join("README.md")`).

## 8. `ArtifactRefBeadStore` / `ArtifactRefAgentRoot`
File: `src/sase/artifact_ref_models.py`:
```python
@dataclass(frozen=True, slots=True)
class ArtifactRefBeadStore:
    project: str
    prefix: str
    root: Path

@dataclass(frozen=True, slots=True)
class ArtifactRefAgentRoot:
    project: str
    root: Path
```
Both have `.project` usable to match `ref_context.project.display_name`-style filtering. Ordering/construction: `src/sase/artifact_ref_context.py:114` calls `collect_entity_context(store, project_filter, projects)` → `src/sase/artifact_ref_entity_context.py:25`. Currently this **always returns at most one** `ArtifactRefBeadStore`/`ArtifactRefAgentRoot` tuple element (single-project resolution: `_collect_bead_stores` reads `store.kind_root(BEADS_SIDECAR_ROLE)` for the one `selected` project and returns a 0- or 1-tuple), so `context.bead_stores` today is effectively `()` or `(one_store,)` for the caller's selected/current project — there's no existing multi-store ordering to rely on; if your resolver needs "every store", you'll need to build that iteration yourself (e.g. across enabled projects).

## 9. `resolve_artifact_ref` for `bead`/`agent`
File: `sase/repos/linked/sase-core/crates/sase_core/src/artifact_ref/mod.rs`. `resolve_bead` (line 935): if `context.bead_stores` is empty → `"missing"`. It derives a lineage-root prefix via `bead_lineage_root(id).rsplit_once('-')`; if that prefix doesn't match **any** store's `.prefix` → `"unknown_project"`. It then checks `<store.root>/pages/<lineage>/{README.md | <id>.md}` across the filtered stores: 0 hits → `"missing"` (candidates = all attempted paths); exactly 1 hit → `"exact"` with `locator = "{store.project}/{id}"`; 2+ hits → `"ambiguous"` (candidates = every matching path).

`resolve_agent` (~line 1002): if `context.agent_roots` is empty → `"missing"`. Tries the raw name and (if `agent_owner` present) its globalized form against `<root.root>/agents/<candidate>/README.md` across all agent roots: 0 hits → `"missing"`; 1 hit → `"exact"` with `locator = "{root.project}/{matched_name}"`; 2+ hits → `"ambiguous"`.

Both share the `resolution(status, rendered)` helper producing `ArtifactRefResolutionWire{schema_version, status, rendered, locator, resolved_path, candidates, diagnostic}` — this maps 1:1 onto the Python `ArtifactRefResolution` dataclass (`artifact_ref_models.py:332`), whose `status` is `Literal["exact","drifted","vcs_backed","ambiguous","missing","unknown_kind","unknown_repo","unknown_project","filtered"]`. To "replicate today's missing/unknown_project result" for bead short-ids that don't resolve in any store, mirror this exact logic: no candidate stores whose `prefix` matches the id's lineage-root prefix ⇒ `unknown_project`; matching stores but no file present ⇒ `missing` with `candidates` listing every attempted page path.

Good, tests pass. Now let's move to task #2: the `ArtifactEntry` dataclass and `quoted` field on `ArtifactRefPromptCandidate`.

All target files read in full. Here is the precise report.

## 1. `src/sase/llm_provider/preprocessing.py` (225 lines, read in full)

**`PreprocessResult` dataclass** (lines 35-49):
```python
@dataclass
class PreprocessResult:
    """Result of prompt preprocessing.

    Attributes:
        prompt: The preprocessed prompt text (after early phase).
        directives: Parsed prompt directives extracted during early phase.
    """

    prompt: str
    directives: PromptDirectives = field(default_factory=PromptDirectives)


# Keep the old name as an alias so existing internal references still work.
_PreprocessResult = PreprocessResult
```
This is the exact dataclass you'd add `segment_vcs_refs: tuple[str | None, ...] = ()` to.

**`preprocess_prompt_early`** (lines 52-110) — does NOT currently extract or return VCS tags anywhere. It operates on a single already-joined prompt string (callers join multi-prompt segments with `"\n---\n"` before calling it — see `xprompt_handler.py` below), and its 3 steps are: (1) optional Jinja2 render via `context`, (2) `canonicalize_project_aliases_in_prompt` + `process_xprompt_references` (xprompt expansion), (3) `extract_prompt_directives` (strips `%id` directives, `strip_disabled_markers=False`). No call to `extract_vcs_workflow_tag`/`find_vcs_workflow_tag` exists in this file at all (verified via `grep -n vcs`, zero hits). Full body:
```python
def preprocess_prompt_early(
    prompt: str,
    *,
    extra_xprompts: dict[str, Any] | None = None,
    scope: dict[str, Any] | None = None,
    context: dict[str, Any] | None = None,
    trace: ExpansionTrace | None = None,
) -> PreprocessResult:
    """Early preprocessing phase: Jinja2 context, xprompt expansion, directives.
    ...
    """
    from sase.xprompt import process_xprompt_references

    # 1. Optional Jinja2 rendering (workflow variables)
    if context is not None:
        from sase.xprompt.workflow_executor_utils import render_template

        fenced_blocks: list[str] = []
        prompt = protect_fenced_blocks(prompt, fenced_blocks)
        disabled_regions: list[str] = []
        prompt = protect_disabled_regions(prompt, disabled_regions)
        prompt = render_template(prompt, context)
        prompt = unprotect_disabled_regions(prompt, disabled_regions)
        prompt = unprotect_fenced_blocks(prompt, fenced_blocks)

    from sase.project_aliases import canonicalize_project_aliases_in_prompt

    prompt = canonicalize_project_aliases_in_prompt(prompt)

    # 2. Expand xprompt references
    prompt = process_xprompt_references(
        prompt, extra_xprompts=extra_xprompts, scope=scope, trace=trace
    )

    # 3. Directive extraction (after xprompt expansion so directives inside
    #    expanded xprompts are also discovered; fenced-block protection is
    #    built into extract_prompt_directives). Preserve disabled region
    #    markers so preprocess_prompt_late can still protect their contents
    #    from command substitution and file-reference validation.
    prompt, directives = extract_prompt_directives(prompt, strip_disabled_markers=False)

    return PreprocessResult(prompt=prompt, directives=directives)
```

**`preprocess_prompt_late`** (lines 113-206) calls `process_artifact_references`/`validate_artifact_references` (imported from `sase.artifact_refs`) at step 3, before file-ref processing at step 4:
```python
def preprocess_prompt_late(
    prompt: str,
    *,
    file_ref_mode: FileRefMode = "process",
    is_home_mode: bool = False,
) -> str:
    """Late preprocessing phase: command sub, artifact/file refs, Jinja2, formatting.
    ...
    """
    from sase.file_references import (
        format_agent_prompt_markdown,
        process_command_substitution,
        process_file_references,
        strip_html_comments,
        validate_file_references,
    )
    from sase.artifact_refs import (
        ArtifactRendererJinjaProtection,
        process_artifact_references,
        validate_artifact_references,
    )
    from sase.xprompt import is_jinja2_template, render_toplevel_jinja2

    # 0. Protect disabled regions (%xprompts_enabled:false/true pairs)
    disabled_regions: list[str] = []
    prompt = protect_disabled_regions(prompt, disabled_regions)

    # 1. Protect fenced code blocks
    fenced_blocks: list[str] = []
    prompt = protect_fenced_blocks(prompt, fenced_blocks)

    # 2. Command substitution
    prompt = process_command_substitution(prompt)

    # 3. Artifact references, before file refs consume their resolved paths.
    staged_artifact_paths: set[str] = set()
    artifact_jinja_protection = ArtifactRendererJinjaProtection()
    if file_ref_mode == "process":
        prompt = process_artifact_references(
            prompt,
            is_home_mode=is_home_mode,
            staged_file_paths=staged_artifact_paths,
            jinja_protection=artifact_jinja_protection,
        )
    elif file_ref_mode == "validate":
        validate_artifact_references(prompt, is_home_mode=is_home_mode)

    # 4. File references
    if file_ref_mode == "process":
        prompt = process_file_references(
            prompt,
            is_home_mode=is_home_mode,
            staged_file_paths=staged_artifact_paths,
        )
    elif file_ref_mode == "validate":
        validate_file_references(prompt)

    # 5. Top-level Jinja2
    if is_jinja2_template(prompt):
        prompt = render_toplevel_jinja2(prompt)
    prompt = artifact_jinja_protection.unprotect(prompt)

    # 6. Prettier formatting (shared agent-prompt Markdown policy)
    prompt = format_agent_prompt_markdown(prompt)

    # 7. HTML comment stripping
    prompt = strip_html_comments(prompt)

    # 8. Restore fenced code blocks
    prompt = unprotect_fenced_blocks(prompt, fenced_blocks)

    # 9. Restore disabled regions and strip markers
    prompt = unprotect_disabled_regions(prompt, disabled_regions)
    prompt = strip_disabled_region_markers(prompt)

    return prompt
```
`process_artifact_references`/`validate_artifact_references` signatures shown above accept `is_home_mode`, `staged_file_paths`, `jinja_protection` — that's where `ref_contexts` would need to thread in.

**`preprocess_prompt`** (lines 209-224) — top-level orchestration; it does NOT call embedded-workflow expansion at all (that's inserted by callers between early/late, this module has zero knowledge of it):
```python
def preprocess_prompt(prompt: str, *, is_home_mode: bool = False) -> PreprocessResult:
    """Apply the full preprocessing pipeline to a raw prompt.
    ...
    """
    early = preprocess_prompt_early(prompt)
    final_prompt = preprocess_prompt_late(early.prompt, is_home_mode=is_home_mode)
    return PreprocessResult(prompt=final_prompt, directives=early.directives)
```

## 2. `src/sase/main/xprompt_handler.py` — `_handle_expand` (full function, lines 30-71)

Note: `expand_embedded_workflows_in_query` is called **between** early and late, and note the prompt segments (`multi.segments`) are **already joined into one string** before `preprocess_prompt_early` ever sees them (`"\n---\n".join(multi.segments)` at line 47) — so per-segment info is lost unless captured before this join.

```python
def _handle_expand(args: argparse.Namespace) -> None:
    """Handle 'sase xprompt expand'."""
    from sase.llm_provider.preprocessing import (
        preprocess_prompt_early,
        preprocess_prompt_late,
    )
    from sase.xprompt._trace import ExpansionTrace, print_trace

    from sase.main.query_handler import expand_embedded_workflows_in_query
    from sase.agent.multi_prompt import parse_multi_prompt

    prompt = args.prompt if args.prompt else sys.stdin.read()

    # Parse frontmatter for local xprompt definitions so that
    # references like #_docs:telegram are expanded correctly.
    multi = parse_multi_prompt(prompt)
    local_xprompts = multi.local_xprompts or None
    prompt_body = "\n---\n".join(multi.segments)
    from sase.project_aliases import canonicalize_project_aliases_in_prompt

    prompt_body = canonicalize_project_aliases_in_prompt(prompt_body)

    trace = ExpansionTrace() if args.trace else None
    early = preprocess_prompt_early(
        prompt_body, extra_xprompts=local_xprompts, trace=trace
    )
    expanded, _post_workflows = expand_embedded_workflows_in_query(early.prompt)
    processed = preprocess_prompt_late(expanded, file_ref_mode="validate")
    print(processed, end="")
    from sase.xprompt.unresolved import (
        find_unresolved_reference_names,
        format_unresolved_reference_warning,
    )

    for name in find_unresolved_reference_names(
        processed,
        extra_xprompts=local_xprompts,
    ):
        print(format_unresolved_reference_warning(name), file=sys.stderr)
    if trace is not None:
        print_trace(trace)
    sys.exit(0)
```

## 3. `src/sase/xprompt/workflow_executor_steps_prompt.py` — `_execute_prompt_step`

Class: `PromptStepMixin` (lines 119-577). Method `_execute_prompt_step` spans lines 156-577 (full text captured above via Read — too long to repeat verbatim twice here, but the load-bearing excerpt around early/late/embedded-expansion ordering, lines 202-243):

```python
        # Early phase: directives, Jinja2 context rendering, xprompt expansion
        early = preprocess_prompt_early(
            step_prompt,
            extra_xprompts=self.workflow.xprompts,
            scope=self.context,
            context=self.context,
        )
        effective_directives = early.directives
        ...
        # Then expand embedded workflows
        # This executes pre-steps and replaces workflow refs with prompt_part content
        expanded_prompt, embedded_workflows, pre_step_count = (
            self._expand_embedded_workflows_in_prompt(early.prompt)
        )

        # Re-expand xprompts after embedded workflow pre-steps. ...
        if embedded_workflows:
            from sase.xprompt import process_xprompt_references

            expanded_prompt = process_xprompt_references(
                expanded_prompt,
                extra_xprompts=self.workflow.xprompts,
                scope=self.context,
            )

        # Late phase: command sub, file refs, Jinja2, prettier, HTML stripping
        expanded_prompt = preprocess_prompt_late(expanded_prompt)
```
Note also line 184-186, before early preprocessing even runs: `step_prompt = inherit_vcs_workflow_tag(step.agent, self.inherited_vcs_tag)` (from `sase.xprompt._parsing`) — this is a distinct, already-existing VCS-tag mechanism (inheriting the parent's tag into an embedded step prompt), separate from what you're adding. I read and captured the complete method body (all 577-156+1=422 lines) in my tool call above; it's available if you need the tail (HITL, post-step, diff-capture logic) — none of it touches VCS tags or `ref_contexts`.

## 4. Exact function names/locations

- **`expand_embedded_workflows_in_query`** — defined in `/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_13/src/sase/main/query_handler/_embedded_workflows.py:33`, re-exported from `sase/main/query_handler/__init__.py`. Signature:
```python
def expand_embedded_workflows_in_query(
    query: str,
    artifacts_dir: str | None = None,
    *,
    only_workflow_names: Collection[str] | None = None,
    preserve_existing_xprompt_metadata: bool = False,
) -> tuple[str, list[EmbeddedWorkflowResult]]:
```
Used by: `xprompt_handler.py:56`, `workflows/mentor.py:327`, `workflows/crs.py:191`, `axe/run_agent_runner_setup.py:307`, `axe/fix_hook_runner.py:188`.

- **`_expand_embedded_workflows_in_prompt`** — this is a **mixin method**, not a free function. Implemented in `/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_13/src/sase/xprompt/workflow_executor_steps_embedded_expand.py:60`. Declared as a required attribute (type `Any`, comment `# (prompt) -> tuple`) on `PromptStepMixin` (`workflow_executor_steps_prompt.py:149`) and on the equivalent mixin in `workflow_executor_parallel.py:53`. Called as `self._expand_embedded_workflows_in_prompt(early.prompt)` at `workflow_executor_steps_prompt.py:225` and `self._expand_embedded_workflows_in_prompt(...)` at `workflow_executor_parallel.py:137`. It returns a 3-tuple `(expanded_prompt, embedded_workflows, pre_step_count)`.

## 5. VCS-tag extraction relative to `preprocess_prompt_early`

**Key finding: `preprocess_prompt_early` does not extract VCS tags today, and no VCS-tag extraction call exists anywhere in `preprocessing.py`.** So there's currently nothing in `preprocessing.py` for `segment_vcs_refs` to piggyback on — you'll be adding new logic, not wiring into existing early-phase output.

Relevant existing VCS-tag machinery, which you'd likely call from wherever you populate `segment_vcs_refs`:
- `extract_vcs_workflow_tag(prompt: str) -> str | None` — defined twice in the codebase with identical bodies/docstrings: `src/sase/xprompt/_parsing.py:176` and the canonical impl `src/sase/xprompt/_parsing_vcs_tags.py:44` (the `_parsing.py` one wraps `_get_vcs_tag_pattern()` from `_parsing_vcs_tags`/`_vcs_tags`). It matches only a **leading** VCS tag (after skipping `%directive` prefixes via `_DIRECTIVE_PREFIX_RE`), returning the tag string (e.g. `"#gh:sase "`) or `None`. Publicly exported from `sase.xprompt.__init__` (line 18/155).
- `find_vcs_workflow_tag(prompt: str) -> str | None` — searches anywhere in the prompt, not just leading position (`_parsing_vcs_tags.py`).
- **Segment-level** VCS resolution already exists in `/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_13/src/sase/agent/multi_prompt_vcs.py`: `extract_vcs_ref(prompt: str) -> tuple[str, str] | None` (returns `(wf_name, ref_value)`, e.g. `("gh", "sase")`) and `resolve_segment_vcs_context(...) -> SegmentVcsContext` (a frozen dataclass with `vcs_ref: tuple[str, str] | None`). This is invoked by the multi-prompt launcher machinery (per-segment), operating on `MultiPrompt.segments: list[str]` from `sase.agent.multi_prompt.parse_multi_prompt` (`src/sase/agent/multi_prompt.py:58`) — i.e. **before** segments get joined into a single string and handed to `preprocess_prompt_early`. This is the natural place segment VCS tags are "still present" as distinct per-segment values; once `xprompt_handler.py` line 47 does `"\n---\n".join(multi.segments)`, segment boundaries (and thus per-segment tag identity) collapse into one prompt string, and only `extract_vcs_workflow_tag`'s single leading-tag result would be recoverable downstream. To populate `segment_vcs_refs: tuple[str | None, ...]` you'll need to extract per-segment before the join (via `multi.segments` + `extract_vcs_workflow_tag`/`extract_vcs_ref` per segment) and pass that tuple explicitly into `preprocess_prompt_early`/`PreprocessResult`, since no current code path threads it through the join point.

Now let's add the `ArtifactEntry` dataclass to `artifact_ref_models.py`.

Now let's smoke-test this and re-export `ArtifactEntry` from `artifact_refs.py` and `artifact_ref_kinds` picks up fine.

Task #2 works correctly. Let's run the full artifact_refs test suite again to confirm nothing broke, then move to task #3.

All green. Marking task #2 complete and starting task #3 (`PromptRefContext`).

Now I have enough detail to write `artifact_ref_prompt_context.py`. Let me check a couple more small things first — the `workspace_provider` module's public exports and `ResolvedRef` shape.

Now let's smoke-test this module directly.

Let me debug why segment tag extraction failed in that last test.

Everything works correctly. Let's also verify the `Path.cwd()` / `find_marker_from_cwd` avoidance guarantee directly.

Excellent, the module works correctly and never touches `cwd`. Let me add the retirement comment on `build_launch_artifact_ref_context` now, then mark task #3 complete.

Now let's run the full test suite once more to make sure nothing regressed, then mark task #3 complete.

Let's smoke-test the expansion formatter with the exact format strings I'll use.

Both format strings work correctly. Now let's write `builtin_entries.py` and the four resolver modules.

Now let's write `builtin_entries.py`:

Good, `Patch` is importable from `sase.ace.patch.models`. Now let's write `builtin_entry_patch.py`.

Now let's write `builtin_entry_agent.py`.

All imports work. Now let's test end-to-end resolution against real repo data (stitch against this repo, bead lookup, patch lookup).

Stitch resolution works end-to-end correctly. Now let's test bead and patch resolution against real repo data.

Patch resolution works. Now let's test the bead resolver against the current bead (`sase-js.4`).

All four resolvers work end-to-end correctly. Now let's test the top-level `resolve_builtin_entry` dispatcher and run the existing test suite to confirm no regressions.

All green. Task #4 is complete. Let's mark it and check line counts for the `toobig` lint tier before moving on.

All well under the 700-line tier. Let's mark task #4 complete and move to task #5.

Now let's rewrite `prompt_ref_contexts_for_prompt` to properly implement the full §3.9 resolution-order algorithm with an explicit `ref_contexts` sequence.

Now let's replace this function with the full §3.9 resolution-order implementation:

Now let's add the `Sequence` import and export `primary_repo_name`.

Now let's re-run the smoke tests for this module to confirm the refactor didn't break anything.

All correct. Now let's write the changes to `artifact_ref_prompt_resolution.py` (add stitch/patch arms).

Now let's update `artifact_ref_prompt_rendering.py` to add the agent transcript pointer.

Now let's add the `_agent_transcript_pointer` helper function.

Let me pause the central rewrite and first build task #6's `core/artifact_ref_uses.py` module, since I'll need it while finishing the `artifact_ref_prompt.py` rewrite. Let's look at the reference pattern.

Let me add the remaining binding wrappers for the use-record manifest to `artifact_ref_operations.py`.

Round trip works correctly. Now let's write `core/artifact_ref_uses.py`.

Task #6's core module is done and verified. Now let's finish the central `artifact_ref_prompt.py` rewrite (task #5), wiring in both the builtin dispatcher and the ref-use recording call together.

Now let's do the full rewrite of `artifact_ref_prompt.py`.

Let me refine the stitch resolver to set `canonical_reference` (the fully-resolved spelling), matching the bead resolver's pattern.

Now let's run the existing test suite to catch regressions from this major rewrite.

Found a bug — the explicit-context branch isn't wrapped in an outer tuple. Let me fix it.

I need to preserve backward compatibility for the ACE authoring tests. Let me revert and instead add an additional document root rather than renaming the existing one.

Let's verify the full pipeline works end-to-end with stitch/patch through explicit context, confirming the wiring in task #5 is functionally correct.

Excellent — `@stitch:` and `@commit:` alias both produce byte-identical expansion output, exactly matching plan §6's requirement. Let's also verify the deprecated `@plans:` alias behavior end-to-end.

Both resolve identically, and only `@plans:` emits the deprecation warning (printed once to stderr). Task #5's wiring is verified correct. Let's mark tasks #5 and #6 complete.

Now let me read the actual files I need to edit for task #7.

Let's add the two new public helpers to `artifact_ref_prompt_context.py`.

Now let's update `__all__` and add these to it.

Now let's smoke-test these new helpers before wiring them into `preprocessing.py`.

Works correctly. Now let's wire this into `preprocessing.py`.

Now let's update `preprocess_prompt_late` to accept `ref_contexts` and thread it through:

Now let's update `preprocess_prompt` to build contexts from `early.segment_vcs_refs`:

Works correctly. Now let's read and update `main/xprompt_handler.py` and `xprompt/workflow_executor_steps_prompt.py`.

No `is_home_mode` concept here — matches `preprocess_prompt_late(expanded_prompt)` defaulting to `False`. Let's wire the `ref_contexts` through here too.

Let's run the actual end-to-end CLI verification command from the plan now that all wiring is in place.

Let's verify the CLI path works correctly for `@patch` and `@bead` (which aren't affected by the stale checkout quirk).

Let me do a comprehensive end-to-end verification simulating a real agent launch, confirming both expansion text and the `ref-uses.jsonl` write.

This confirms one ref-uses row per occurrence (not deduped), full expansion text, and correctly pinned `stable_id`/`canonical_ref` with the full 40-char sha. Task #7's wiring is fully verified. Let's run the full test suite once more, then mark task #7 complete.

All remaining failures are the expected "old assertions need updating" category per plan §6/§9 — pre-existing tests mocking old function signatures or expecting old expansion text. Task #7 is verified working. Let me mark it complete and move to task #8.

Let's factor out a shared `explicit_prompt_ref_context` helper in `artifact_ref_prompt_context.py` and use it from both `artifact_ref_prompt.py` and the CLI.

Now let's simplify `artifact_ref_prompt.py` to use this shared helper.

Now let's update the import and call site.

Now let's update `artifact_cli/references.py`.

Now let's update the dataclass and `resolve_cli_reference` function.

Let's smoke-test the CLI resolver changes.

Excellent — CLI reference resolution works correctly for stitch. Now let's finish task #8 with the `prompt_artifact_staging.py` and `artifact_refs.py` re-export edits.

Now let's update `artifact_refs.py` to re-export `ArtifactEntry`, `PromptRefContext`, and the context builders.

Let's smoke-test the full import chain and re-run the test suite.

Now let's run the full test suite to check overall state.

Good — same 6 known failures (expected test updates), no new regressions from task #8. Let's mark task #8 complete and move to task #9 (the big test-fixing pass).

Let me first fix the 6 known-failing existing tests, starting with a detailed look at each.

Now let's fix the `test_late_preprocessing_expands_artifacts_before_file_refs` mock signature:

Now let's fix `test_commit_expands_to_full_locator_and_checkout` in `test_preprocessing_expansion.py`.

Now let's run the full artifact_refs test suite to confirm all fixes work.

All 57 tests pass. Now let's run the broader test suite to check for regressions in ACE and other areas affected by the "plans"→"plan" fixture changes and known_kinds changes.

Found a real bug — agent resolution loses the Rust-globalized canonical name. Let me fix `resolve_agent_entry`.

Let's fix the `rendered` field construction in both `artifact_ref_prompt.py` and `artifact_cli/references.py` to use the canonical (globalized) form when available.

Now let's fix the JSON envelope test and re-run everything.

Now let's re-run the broader test suite to confirm both fixes work.

All 150 tests pass. Let's now run a wider sweep across the whole test suite to catch any other regressions before moving on to writing the new tests.

While the broader test suite runs in the background, let's continue writing the new test files required by §6. Let's first check the existing test directory structure.

Now let's write the stitch resolver tests.

All 7 stitch tests pass. Let me check on the background test suite run before continuing.

Let's continue with the patch resolver tests.

All 5 patch tests pass. Let me clean up the unused imports.

Let me add the missing "no project context" and "quoted patch name" test cases per §6.

All 9 patch tests pass. Let's check the background test suite status now.

Let's continue with the bead resolver tests, using mocked `bead_read_facade` calls.

All 5 bead tests pass. Now let's write the agent resolver tests.

All 27 `artifact_providers` tests pass. Let's check on the background test suite now.

Let's continue with the `PromptRefContext` test file.

All 6 pass. Let's check on the background test suite now, and continue with the use-records and aliases test files.

Now let's write `tests/test_artifact_ref_uses.py`.

Let's add the integration-level test showing ref-uses vs artifact_consumption dedup contrast.

All 5 use-records tests pass, confirming the dedup contrast. Now let's check on the background test suite.

All 5 alias tests pass. Let's check the background test suite status once more.

Let's add the sha length boundary test, then move on.

Confirmed at the scanner level. Let's add this as a quick test in the stitch test file.

All 8 stitch tests pass. Let's run the full new test suite together and check the background job status once more.

All 101 tests pass. Task #9 is essentially complete — let's mark it done and move to task #10 (symvision).

Let's privatize the symbols only used internally.

Now let's remove it from `__all__`.

Good, not referenced there. Now let's privatize `artifact_ref_kind_descriptors` and `ArtifactRefKindDescriptor` in `artifact_ref_kinds.py`.

Now let's fix `__all__` to remove the now-private names.

Good, clean. Now let's add the `--epic-symbol` entries in the `Justfile` for the remaining legitimate whitelisted symbols.

Now let's re-run symvision to confirm it's clean.

Symvision is clean. Let's mark task #10 complete and check on the background test suite.

Let's re-run the full artifact test suite after the symvision privatization changes.

All 1455 tests pass. Let's move to task #11 (verification suite) while the background full-suite run continues.

Good, this all matches expected changes. Now let's run the full test suite plus lint to confirm everything is clean.

`just lint` passes cleanly with exit code 0 (ruff, mypy across 3019 files, symvision, terminology audit, file sizes). Let's check on the background test suite now.

While `just check-full` runs, let's do the comprehensive end-to-end CLI verification from plan §7 with all four builtin kinds together.

Let's record the three follow-up notes on the bead per plan §8.

All three follow-up notes recorded. Let's mark task #12 complete and check on the background `just check-full` run.

This all matches the plan's scope exactly. Let's check on the background jobs.

Let's wait for the background test suite to complete before proceeding further.

Good, `docs/` untouched as required. Let's do a final review of the complete `artifact_ref_prompt.py` diff for correctness while the background verification runs.

Let me stop the redundant earlier test run since `just check-full` (the authoritative check) is now running properly parallelized.

That was the redundant background job being terminated (expected). Let's continue waiting for `just check-full`, the authoritative run.

Still running, now with resources freed up. I'll wait for the notification rather than poll further.

I've implemented the full plan and am waiting on the final `just check-full` verification run to complete before wrapping up. Summary so far:

- All 12 implementation steps from the plan are complete: the `PromptRefContext` module, the four builtin resolvers (`@stitch`, `@patch`, `@bead`, `@agent`), the dispatcher wiring, the `ref-uses.jsonl` manifest, threading through preprocessing/xprompt_handler/workflow_executor, CLI support, comprehensive new tests (101+ passing), symvision cleanup, and the three follow-up notes recorded on bead `sase-js.4`.
- `just lint` (ruff + mypy across 3019 files + symvision) passes cleanly.
- All targeted test suites (artifact_refs, artifact_providers, ACE completion/highlight, CLI) pass — 1455 tests green.
- `just check-full` is running now as the final authoritative gate; I'll report back once it completes.

I'll start by verifying the actual current state of the repository — the prior work needs to be confirmed with real commands before I close any bead or commit anything.

Install succeeded. Now let's run lint and the targeted test suites in the background so I can verify real results within this turn.

I'll wait for both the lint and targeted test runs to complete before deciding on next steps.

Both verification runs are in progress — lint and the targeted test suite for this phase's changes. I'll report back once they finish.

96 tests passed. Now let's check on the lint run.

Lint completed with exit code 0. Let me check the full output to confirm.

Good — lint is fully clean (ruff, mypy across 3019 files, symvision, terminology audit, file sizes) and the targeted 96-test suite passes. Now let's run the full authoritative verification gate before committing.

The full test suite (`test-cost` lane) passed cleanly — the only failing gate in `check-full` is `flake baseline`, which flags 6 pre-existing reproducible flakes in `test_contract_manifest.py` and `test_core_vcs_log.py` (unrelated to this phase's changes, recorded across the shared cross-workspace store). Per CLAUDE.md and the gate's own message, this needs a filed task bead rather than being ignored. Let me file it.

This is a semantic duplicate of an already-filed, ready task bead (`sase-jq`) with independent +1 evidence from sibling phases `sase-js.1` and `sase-js.5` of the same epic. I'll corroborate it instead of creating a new one.

Now let me verify the bead's current state before closing, including whether the plan's required follow-up notes (§8) are actually present.

Bead closed and published successfully. Now let's confirm the exact file list before committing.

Confirmed gitignored. Now invoking the commit skill with an explicit `-f` for each of the 36 changed files.

Two files have real conflicts. Let's examine them.

Now let's verify no conflict markers remain in this file and confirm the imports section is sane.

Good, clean. Now let's look at the other conflicted file.

Now let's confirm no conflict markers remain and check for orphaned merge state files.

Good, that's exactly copied from the upstream commit unchanged (pre-existing unused-variable pattern, not something I introduced). Both diagnostics are pre-existing style in the code being merged, not new issues. Now let's finish the rebase.

No remaining conflicts. Before continuing the rebase, let's verify the merged code is syntactically and functionally sound.

Both files import cleanly with no duplicate `__all__` entries. Now let's run ruff to check formatting/sorting, then continue the rebase.

Clean. Now let's continue the rebase.

Working tree is clean, one commit ahead of origin/master. Now let's finalize per the skill's conflict-recovery flow.

The push succeeded and the branch is in sync with origin. Since the rebase merge was substantial (hand-merging two independent features in the same functions), let me re-verify the final tree actually works before declaring done.

This is expected — the linked sase-core checkout is one commit behind its own origin, missing the Rust bindings that an already-merged upstream Python commit (not mine) requires. Fast-forwarding this read-only linked checkout is routine sync, not a Rust code change.

Now let's reinstall and re-run verification.

Now let's re-run the targeted verification suite.

All 110 tests pass, including the file-ref e2e suite that exercises the merged upstream feature. Let's run lint once more to fully confirm the merged tree is clean.

Lint is fully clean (exit 0). Everything is verified: merge resolution is correct, all tests pass, lint is clean, and the commit is pushed to origin/master.

## Summary

The `builtins` phase (bead `sase-js.4`) of the artifact-ref-contract epic is implemented, verified, and committed.

**What was verified this turn:**
- `just install`, `just lint` (ruff/mypy across 3019 files/symvision/toobig, all clean), and a 96-test targeted suite all passed on the pre-commit tree.
- `just check-full`'s only failing gate was the shared cross-workspace flake-baseline tracker (`test_contract_manifest.py`/`test_core_vcs_log.py`, unrelated to this diff) — corroborated with independent evidence on the existing duplicate task bead `sase-jq` rather than re-filed.
- Closed and published bead `sase-js.4` with a verification note.

**Commit:** `sase_git_commit` hit a real rebase conflict against `origin/master` (a concurrently-landed `feat: add file refs to prompt artifacts`, commit `341fff97a`) in `src/sase/artifact_ref_prompt.py` and `src/sase/artifact_refs.py`. I hand-merged both features (builtin-ref resolution + prompt-ref-context threading from this phase, file-capture/staging from the other), which also required fast-forwarding the linked `sase-core` checkout by one commit to pick up Rust bindings the other feature needed. Re-verified after merging: 110 targeted tests pass (including the file-ref e2e suite) and `just lint` is clean.

Final state: `feat(artifact-ref)!: resolve @stitch/@patch/@bead/@agent through an explicit prompt ref context` (`0f3569cb4`) is committed and pushed; working tree clean, in sync with `origin/master`.
