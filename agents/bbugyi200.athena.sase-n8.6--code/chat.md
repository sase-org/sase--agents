# Chat History - ace-run (sase-n8.6--code)

- **TIMESTAMP:** 2026-08-16 15:29:53 EDT
- **MODEL:** claude/sonnet
- **AGENT:** sase-n8.6--code

## Linked Chats

- 1. --plan — `~/.sase/chats/202608/gh_sase_org__sase-ace_run-sase_n8_6__plan-260816_114130.md`
- **2. --code** — `~/.sase/chats/202608/gh_sase_org__sase-ace_run-sase_n8_6__code-260816_114130.md`

## Prompt

%model:@medium
#gh:gh_sase-org__sase
@sase/repos/plans/202608/launch_control_alias_history_panel.md

The above plan has been reviewed and approved. Implement it now.


## Response

I'll start by exploring the existing codebase structure to understand the Launch Control panel, the alias history adapter, and related mixins before implementing this plan.

This is a large feature with many moving pieces. Let me parallelize exploration across the existing patterns I need to reuse before writing any code.

I've launched four parallel research agents to explore: (1) modal/mixin/worker patterns, (2) preview/copy/reference helpers, (3) styling and rendering conventions, (4) ModelsPanel row types and footer wiring. While those run, I'll look at a few more directly-relevant files myself.

Good, confirmed exports exist. Now let me check the alias_history.py test file and the wire module for schema details, plus look at test_alias_history.py to understand expected usage patterns.

Found it. Let's read the key files in full.

Good context established. Now let me wait for the parallel research agents to complete since I need their findings before writing the modal code.

Now let's look at models_panel_display.py, models_panel.py, keybinding_footer.py, and models_panel_providers.py (for the `p` key action pattern) plus alias_history.py which seems highly relevant.

Good, that confirms the key data model pieces. Let me view the full `alias_view.py` AliasView class and rest of `models_panel_rows.py`.

`_agent_display_header_metadata.py` looks like exactly the "detail strip" file with Workspace, Retry labels. Let me read it in full.

Now I have a solid picture of the row types. Let me wait for the four research agents to finish before writing code, since their output governs how I structure the modal, styles, and docs.

I'll continue reading this file since it's central to how selection/toast/highlighting work.

Good, this is straightforward. Now let me check on the background research agents' progress.

Still running. Let me continue exploring pieces not covered by the delegated agents — the `models_panel_rendering_descriptions.py` and `config_commit.py` push pattern, plus check `docs/ace.md` structure lightly myself (in case the agent's report needs cross-checking) and the test helpers file.

Now I have all the pieces. Let me verify the `models_panel.py` binding list (for `H` context around Launch Control's key table) and confirm there isn't already an `H` binding conflict, plus double check the models_panel_rendering.py usage of provider_styles for row rendering conventions to round out the picture.

I found the "Launch Control" section at line 2540. Let me read it fully.

Good — a helpful template for the nested modal key table format. Now let me check on the background agents.

Let's read the `description_text_for_row` function to see how it distinguishes row types, which is useful context for the H handler's alias-set resolution logic.

Good, that confirms the notify-mocking convention for tests. Now let me check status of the research agents again.

While waiting on the research agents, I'll get the environment ready since this workspace may have stale dependencies (per project instructions, `just install` is required before `just check`).

I'll wait for the install and the four research agents to finish before proceeding with implementation.

Confirmed — `KeybindingFooter` is mounted only in the main app layout (`_app_layout.py`), not inside `ModelsPanel`. Now I have everything needed to write the full report.

I'll wait for the background agents and install task to complete — they'll notify me automatically when done.

Research agents and the dependency install are running in the background. I'll continue once they report back with the modal/worker patterns, styling conventions, and row-type details needed to implement the alias history panel correctly.

# Research Report: `AliasHistoryModal` Dependencies

## 1. `PreviewPanelModal` and `PreviewPayload`

**`PreviewPayload`** — `src/sase/ace/tui/widgets/_prompt_preview_target.py:23-24,54-67`

```python
PreviewKind = Literal["xprompt", "file"]
PreviewDefaultView = Literal["source", "rendered"]
...
@dataclass(frozen=True, slots=True)
class PreviewPayload:
    """Resolved content and metadata for the preview modal."""

    kind_label: str
    icon: str
    title: str
    source_path: str | None
    content: str
    lexer: str
    reference: str | None = None
    default_view: PreviewDefaultView = "source"
    properties: XPromptProperties | None = None
```

For a Markdown payload you want `lexer="markdown"` and `default_view="rendered"` (this is what makes `PreviewPanelModal._is_markdown_payload()` true and pre-selects the rendered Markdown view instead of the raw-source view). `reference` is an optional durable-reference string shown under the title; `source_path` is the on-disk path shown next to/instead of it.

**`PreviewPanelModal`** — `src/sase/ace/tui/modals/preview_panel_modal.py:67-99`

```python
class PreviewPanelModal(
    CopyModeForwardingMixin,
    SourceFileActionsMixin,
    ModalScreen[None],
):
    """Presentational modal for resolved xprompt/file previews and their properties."""

    BINDINGS = [
        ("escape", "escape", "Clear search / close"),
        ("q", "close", "Close"),
        ...
        ("y", "copy_contents", "Copy contents"),
        ("Y", "copy_path", "Copy path"),
        ("R", "toggle_rendered", "Rendered / source"),
        ...
    ]

    def __init__(self, payload: PreviewPayload) -> None:
        super().__init__()
        self._payload = payload
        ...
```

It takes only the `PreviewPayload` in its constructor — you `push_screen(PreviewPanelModal(PreviewPayload(...)))`.

**Call site reading a file off-thread then opening a Markdown preview** — `src/sase/ace/tui/actions/artifacts_files.py:77-148` (`action_files_view_selected`). This is the best model for your Enter handler:

```python
async def open_preview() -> None:
    try:
        materialized = await asyncio.to_thread(
            _materialize_artifact_file_entry,
            entry,
        )
        assert materialized.path is not None
        stored_path = materialized.path
        if view_mode not in {"markdown", "text"}:
            self._open_artifact_file(materialized)
            return
        content = await asyncio.to_thread(
            _read_artifact_file_text,
            stored_path,
        )
    except (OSError, RuntimeError) as exc:
        self.notify(f"Could not read artifact file: {exc}", severity="warning")
        return

    current_pane = self._files_pane()
    current = current_pane.selected_entry if current_pane is not None else None
    if current is None or current.id != selected_id:
        return

    from ..modals.preview_panel_modal import PreviewPanelModal

    lexer = ("markdown" if view_mode == "markdown"
             else _EXTENSION_TO_LEXER.get(Path(stored_path).suffix.lower(), "text"))
    self.push_screen(
        PreviewPanelModal(
            PreviewPayload(
                content=content,
                lexer=lexer,
                title=entry.label,
                kind_label="artifact file",
                icon=FILE_VIEW_MODE_GLYPHS[view_mode],
                source_path=stored_path,
                reference=f"file:{entry.id}",
                default_view=("rendered" if view_mode == "markdown" else "source"),
            )
        )
    )

spawn_pump_free_task(
    self,
    open_preview(),
    name="sase-artifact-file-preview",
    registry_attr="_pump_free_async_tasks",
)
```

Note the "still selected" guard after the `await` (`if current is None or current.id != selected_id: return`) — reapply that idea checking the still-highlighted run before opening the modal. The helper at the bottom of the file, `_read_artifact_file_text` (line 516-519), is a simple `Path(path).expanduser().read_text(encoding="utf-8", errors="replace")` — the same shape you'd use to read `raw_xprompt.md`.

A second, simpler example that builds a `PreviewPayload` directly (no file read, already-in-memory Markdown body) is `_open_cached_issue_body` in `src/sase/ace/tui/actions/_artifacts_beads_issue_actions.py:268-288`, useful for seeing the minimal call shape:

```python
self.push_screen(
    PreviewPanelModal(
        PreviewPayload(
            content=link.issue.body,
            lexer="markdown",
            title=f"{link.display_project} #{link.issue_id}",
            kind_label="external issue",
            icon="○",
            reference=_display_issue_ref(link),
            source_path=None,
            default_view="rendered",
        )
    )
)
```

---

## 2. `reference_for_agent_name`

**Definition** — `src/sase/artifact_ref_entries.py:173-191`

```python
def reference_for_agent_name(name: str) -> str | None:
    """Render one Agents-tab agent name with durable global provenance."""

    if not name:
        return None
    from sase.core.agent_identity_facade import (
        AgentIdentitySnapshot,
        current_owner_agent_name_lookup_candidates,
        globalize_owned_agent_name,
    )

    identity = AgentIdentitySnapshot.current()
    candidates = current_owner_agent_name_lookup_candidates(name, identity)
    global_name = globalize_owned_agent_name(name, identity)
    durable_name = global_name if global_name in candidates else name
    try:
        return parse_artifact_ref(f"agent:{durable_name}").rendered
    except ValueError:
        return None
```

It is re-exported from the stable public facade `src/sase/artifact_refs.py:16,143` (`from sase.artifact_refs import reference_for_agent_name`), which is the import path other call sites use.

**Call site building the durable `@agent:...` string** — `src/sase/ace/tui/actions/clipboard/_artifact_reference_resolution.py:189-195`:

```python
def reference_for_agent_row(agent: Any) -> str | None:
    """Return a durable reference for one concrete Agents-tab row."""

    name = getattr(agent, "agent_name", None)
    if not isinstance(name, str) or not name:
        return None
    return reference_for_agent_name(name)
```

That thin wrapper is then consumed as `reference = reference_for_agent_row(agent)`; the caller prefixes it with `@` before copying (see `_copy_agent_reference` below) — i.e. `reference_for_agent_name` returns the bare `agent:<durable-name>` reference (via `parse_artifact_ref(...).rendered`), and callers add the leading `@` themselves when building the pasteable mention string.

---

## 3. `schedule_copy_delivery`, toast feedback, and the "warn instead of copy" guard pattern

**Definition** — `src/sase/ace/tui/actions/clipboard/_delivery.py:135-154`

```python
def schedule_copy_delivery(
    owner: object,
    value: str | Callable[[], str],
    *,
    copied_label: CopiedLabel,
    task_name: str,
    on_failure: CopyFailurePolicy = "modal",
) -> asyncio.Task[CopyDeliveryOutcome] | None:
    """Schedule one copy outside Textual's pump, tracked by the owning app."""
    return spawn_pump_free_task(
        _app_for(owner),
        deliver_copy(owner, value, copied_label=copied_label, on_failure=on_failure),
        name=task_name,
        registry_attr="_pump_free_clipboard_tasks",
    )
```

`deliver_copy` (same file, lines 88-132) is what actually produces the toast: on success it calls `_notify(owner, f"Copied {label}")`; on OSC-52-only fallback, `f"Copied {label} (OSC 52)"`; on hard failure it opens `CopyFallbackModal` (when `on_failure="modal"`, the default) or notifies with `severity="error"`.

**Exact call site — both the copy-with-toast case and the "warn instead of copying a guessed value" guard** — `src/sase/ace/tui/actions/clipboard/_agents.py:87-124` (`_copy_agent_reference`). This is precisely the pattern you should model your `y` binding on:

```python
def _copy_agent_reference(self) -> None:
    """Copy the durable reference for a concrete Agents-tab agent row."""
    agent = self._get_selected_agent()  # type: ignore[attr-defined]
    if agent is None:
        self.notify("No agent selected", severity="warning")  # type: ignore[attr-defined]
        return
    if agent.is_clan_container:
        self.notify(
            "The selected clan row has no agent reference",
            severity="warning",
        )
        return
    if agent.is_family_container_row:
        self.notify(
            "The selected family container has no agent reference",
            severity="warning",
        )
        return
    if not agent.is_agent_entry:
        row_kind = "workflow step" if agent.is_workflow_step_child else "workflow"
        self.notify(
            f"The selected {row_kind} row has no agent reference",
            severity="warning",
        )
        return
    reference = reference_for_agent_row(agent)
    if reference is None:
        self.notify(
            "The selected agent has no durable agent name",
            severity="warning",
        )
        return
    schedule_copy_delivery(
        self,
        f"@{reference}",
        copied_label=f"agent reference ({reference})",
        task_name="sase-copy-agent-reference",
    )
```

This is exactly the "warn instead of copying a guessed value" guard: rather than falling back to some non-durable/local agent name and copying that, it checks `reference is None` and calls `self.notify(..., severity="warning")` and returns *without* calling `schedule_copy_delivery` at all. Apply the same shape to your `y` handler: resolve `reference_for_agent_name(run.agent_name)` (guarding on `run.agent_name` being present first, same as `agent_name = getattr(agent, "agent_name", None)` check), and only call `schedule_copy_delivery(self, f"@{reference}", copied_label=..., task_name=...)` when it's non-`None`; otherwise `self.notify("...", severity="warning")`.

For a "copy plain text with a toast" example (no guessing/derivation involved) see `_copy_agent_name` in the same file (lines 42-61), and for a lazily-computed value (label depends on work done inside the copy) see `action_files_copy_path` in `src/sase/ace/tui/actions/artifacts_files.py:339-369`, which passes a `value: Callable[[], str]` and a `copied_label: Callable[[], str]` to `schedule_copy_delivery` rather than plain strings.

---

## 4. Detail-strip / field-label rendering conventions for runs/agents

There is no single "detail strip" widget shared across panes, but the field-label + Rich-markup convention is very consistent. The closest and most directly relevant precedent is:

**`src/sase/ace/tui/widgets/prompt_panel/_agent_display_header_metadata.py`** — this builds the Agents-tab detail header field-by-field with exactly the label set you listed. Key excerpts:

- Identity / retry-chain header — `_append_identity_fields` (lines 95-149):
```python
text.append("Name: ", style="bold #87D7FF")
...
if bead_display:
    text.append("Bead: ", style="bold #87D7FF")
    text.append(f"{bead_display}\n", style="bold #FFAF00")
...
if agent.is_retry_attempt or agent.is_retried_parent:
    text.append("Retry chain: ", style="bold #87D7FF")
    text.append("↻ ", style="bold #FFAF00")
    if agent.is_retry_attempt:
        text.append(f"attempt #{agent.retry_attempt}", style="#FFAF00")
```

- Project / Patch / Workspace — `_append_project_fields` (lines 152-193):
```python
elif meta_patch:
    text.append("Patch: ", style="bold #87D7FF")
    text.append(f"{meta_patch}", style="#00D7AF")
    if agent.cl_num:
        text.append(" (")
        text.append(agent.cl_num, style="bold underline #569CD6")
        text.append(")")
    text.append("\n")
elif meta_project:
    text.append("Project: ", style="bold #87D7FF")
    text.append(f"{project_display_label(agent, meta_project)}\n", style="#00D7AF")
...
workspace_num = agent.effective_workspace_num
if workspace_num is not None and workspace_num > 0:
    text.append("Workspace: ", style="bold #87D7FF")
    text.append(f"#{workspace_num}\n", style="#5FD7FF")
```

- Retries/fallback — `_append_retry_fields` (lines 288-309):
```python
text.append("Retries: ", style="bold #87D7FF")
text.append(f"{agent.retry_count}/{agent.max_retries}\n", style="#FF8700")
for record in agent.attempt_history:
    ...
    text.append(
        f"  Attempt {record.attempt_number} · {hhmmss}{fb_marker} · "
        f"{record.status}: {snippet}\n",
        style="dim #FF8700",
    )
```

- Timestamps (start/duration) — `_append_timestamp_fields` (lines 312-333):
```python
text.append("Timestamps: ", style="bold #87D7FF")
text.append(f"{agent.timestamps_display}\n", style="#D7D7FF")
```

- Top-level assembly order — `append_agent_metadata_fields` (lines 336-413) shows the overall ordering: identity → project/patch/workspace → auto-approve → model → xprompts → VCS/PID/BUG → wait → retry → timestamps.

**Field label convention to reuse:** every label is `"<Label>: "` in `style="bold #87D7FF"`, followed by the value in a semantic accent color (`#00D7AF` project/patch, `#5FD7FF` workspace, `bold #FFAF00` bead, `#FF8700` retries, `#D7D7FF` timestamps), each field terminated with `\n`.

**"Hidden" indicator convention** — `src/sase/ace/tui/widgets/_agent_list_styling.py:118-119`:
```python
# Icon for hidden agents (shown when visibility is toggled on)
_HIDDEN_ICON = "◌"
```
used at `src/sase/ace/tui/widgets/_agent_list_render_agent.py:199-201`:
```python
# Hidden icon for agents that are normally hidden
if agent.hidden:
    text.append(f"{_HIDDEN_ICON} ", style="bold #FF5F87")
```
and the retry badge right below it (lines 206-209): `text.append(f"↻{agent.retry_attempt} ", style="bold #FFAF00")`.

**"Xprompt context" rendering** — `src/sase/ace/tui/widgets/prompt_panel/_agent_xprompts.py`, `append_agent_xprompts_section` (lines 23-63):
```python
text.append("Xprompts: ", style=_COLOR_HEADER)   # "bold #87D7FF"
text.append(_summary(xprompts), style=_COLOR_SUMMARY)  # "dim"
text.append("\n")
for item in xprompts:
    ...
    text.append(f"  {glyph} ", style=style)
    text.append(f"#{name}", style=style)
```
with glyphs `⌘` (workflow, `bold #FFAF5F`), `❋` (swarm, `bold #FF87D7`), `▣` (part, `bold #87FFAF`).

**Directly-relevant data model** — worth flagging even though not explicitly asked: the field set you listed (project, workspace, bead, start/duration, retry, Patch, hidden, xprompt context) maps almost 1:1 onto an *existing, not-yet-TUI-consumed* view model built for exactly this feature area:

- `src/sase/llm_provider/alias_history.py` — `AliasHistoryRun` dataclass (lines 77-109) has `project_key`/`project_name`, `workspace_num`, `bead_id`, `started_at`/`finished_at`/`duration_seconds`, `retry_attempt`, `cl_name` (Patch), `hidden`, and `used_xprompts: tuple[UsedXPromptWire, ...]` (xprompt context). It also has `agent_name: str | None` — the field you'd feed into `reference_for_agent_name`.
- `load_alias_history(...)` (same file, lines 214-263) is the loader, and it composes over `src/sase/core/agent_scan_facade.query_agent_alias_history` / `src/sase/core/agent_alias_history_wire.py`'s `AgentAliasRunWire` (lines 50-77), which has the raw `artifact_dir` you'd join with `raw_xprompt.md` for the Enter-key preview.
- No TUI code currently imports `alias_history.py` or `AgentAliasRunWire` (`grep` for `alias_history|AliasHistory|AgentAliasRunWire` under `src/sase/ace/tui/` returned nothing) — `AliasHistoryModal` looks like it will be the first consumer, so `_agent_display_header_metadata.py`'s label/color conventions above are your best style precedent rather than an existing "alias history" detail-strip widget.

---

## Additional structurally-similar modal precedent

For the overall modal shape (`OptionList` + filter + Enter-to-act + a single-letter copy binding + dismiss), `src/sase/ace/tui/modals/prompt_history_modal.py` (`PromptHistoryModal`) is the closest full analog already in the codebase:
- `on_input_submitted` (line 391) / `on_option_list_option_selected` (line 411) drive the Enter/selection path.
- `action_copy_and_cancel` (lines 457-469) is a `ctrl+y`-bound copy action that calls `schedule_copy_delivery(self.app, prompt_text, copied_label="prompt", task_name="sase-copy-prompt-history")` then dismisses — a simpler copy pattern (no derivation/guard needed) than the agent-reference case, useful as a secondary reference alongside `_copy_agent_reference`.

Good, one research agent (preview/copy/reference helpers) finished with detailed findings. Waiting on the other three (modal/worker patterns, styling, and row/footer wiring) before I start writing code.

Still waiting on three. I'll continue waiting for their notifications.

I now have a complete picture. Here is the detailed report.

## 1. `src/sase/ace/tui/modals/model_picker_modal.py` (370 lines, read in full)

**Class hierarchy** (`model_picker_modal.py:103-107`):
```python
class ModelPickerModal(
    KeyedPaneEntryJumpMixin[str],
    OptionListNavigationMixin,
    ModalScreen[str | None],
):
```
MRO order matters: jump mixin first, nav mixin second, `ModalScreen[ResultType]` last.

**Class attrs / BINDINGS** (`:127-133`):
```python
_option_list_id = "model-picker-list"
BINDINGS = [
    ("escape", "cancel", "Cancel"),
    ("enter", "select_model", "Select"),
    ("apostrophe", "jump_to_entry", "Jump"),
]
```
Note it does *not* splice in `OptionListNavigationMixin.NAVIGATION_BINDINGS` — j/k/up/down are instead handled manually in `on_key` (see below), because the filter `Input` needs first crack at those keys via forwarding.

**`__init__`** (`:135-164`): takes only plain config kwargs (`title`, flags, an `alias_context`, an optional `provider_disables: Mapping[...]`). No worker/async here — `build_model_rows(...)` is called synchronously in `__init__` to populate `self._all_rows` / `self._visible_rows`. Everything is precomputed before `compose()`.

**`compose()`** (`:166-201`): a `Container` holding, in order: a `Static` title, a custom `_ModelPickerFilterInput(FilterInput)` (the filter box), an `OptionList` built from `rows_to_options(...)`, and a footer `Static` with hint text (`enter=Select  type=Filter  j/k=Navigate  '=Jump  esc=Clear/Cancel`).

**`_ModelPickerFilterInput`** (`:43-100`): subclass of `FilterInput` (from `.base`) that adds its own `BINDINGS` list (`j/k/down/up/ctrl+n/ctrl+p/enter/escape` all mapped to `"forward('<action>')"`), plus an `action_forward(action_name)` that does `getattr(modal, f"action_{action_name}")()` where `modal = self.screen`. It overrides `_on_key` to intercept jump-mode keys and the apostrophe first (calling `modal.jump_mode_active` / `modal.handle_jump_key(...)` / `modal.action_jump_to_entry()`), then falls back to the explicit key-to-action dict, then `await super()._on_key(event)`.

**On mount** (`:203-205`):
```python
def on_mount(self) -> None:
    self.query_one("#model-picker-filter", _ModelPickerFilterInput).focus()
    self._ensure_highlight()
```

**Rendering / filtering** (`:207-232`):
- `_render_options()` builds `Option` list via `rows_to_options(self._visible_rows, jump_hints=...)`, only passing jump hints when `self.jump_mode_active`.
- `_apply_filter(query)`: captures `previous_id = self._highlighted_option_id()`, recomputes `_visible_rows` via `filter_model_rows`, calls `self.invalidate_jump_hints(identities_changed=True, target_count=0)` (since filtering renames every row), clears+rebuilds the `OptionList`, then `_ensure_highlight(preferred_id=previous_id, prefer_model=bool(query.strip()))`.
- `_highlighted_option_id()`: reads `option_list.highlighted` → `get_option_at_index` → `str(option.id)`, wrapped in try/except returning `None` on failure — this exact "read highlighted → get_option_at_index → str(option.id)" idiom recurs in every modal in this family.

**Jump host hooks** (`:234-259`) — this is the concrete example of implementing `KeyedPaneEntryJumpMixin[str]`:
```python
def _jump_target_keys(self) -> list[str]:
    return [row.option_id for row in self._visible_rows if not row.disabled]

def _jump_current_key(self) -> str | None:
    return self._highlighted_option_id()

def _jump_select_key(self, key: str) -> None:
    self._jump_repaint()  # clears hint prefixes first
    option_list = self.query_one("#model-picker-list", OptionList)
    try:
        option_list.highlighted = option_list.get_option_index(key)
    except Exception:
        return

def _jump_repaint(self) -> None:
    option_list = self.query_one("#model-picker-list", OptionList)
    preferred_id = self._highlighted_option_id()
    option_list.clear_options()
    option_list.add_options(self._render_options())
    self._ensure_highlight(preferred_id=preferred_id)
    self._update_jump_footer()
```
`_update_jump_footer` (`:261-277`) swaps the footer `Static` text to `JUMP ' <back|first>  <esc> cancel` while `jump_mode_active`, else restores the normal hint line.

**Selection / dismissal** (`:311-342`):
```python
def action_select_model(self) -> None:
    option_list = self.query_one("#model-picker-list", OptionList)
    highlighted = option_list.highlighted
    if highlighted is None: return
    option = option_list.get_option_at_index(highlighted)
    if option.disabled: return
    option_id = str(option.id)
    if option_id == DEFAULT_SENTINEL:
        self.dismiss(DEFAULT_SENTINEL if self._distinct_default else None)
    else:
        self.dismiss(option_id)

def action_cancel(self) -> None:
    filter_input = self.query_one("#model-picker-filter", FilterInput)
    if filter_input.value:
        filter_input.value = ""
        self._apply_filter("")
        return
    self.dismiss(None)
```
Escape clears the filter first, cancels only on a second press with an empty filter. `on_input_submitted` (Enter in filter box) calls `action_select_model()`. `on_option_list_option_selected` (double-click/Enter-on-list) also calls `action_select_model()`.

**`on_key`** (`:344-364`) is the modal-level (not filter-level) key router: checks `jump_mode_active` → `handle_jump_key`; else apostrophe → `action_jump_to_entry`; else j/k/down/up/ctrl+n/ctrl+p → `action_next_option`/`action_prev_option`.

---

## 2. `src/sase/ace/tui/modals/saved_agent_group_revival_modal.py` (610 lines, read in full)

Important finding: **this modal does *not* use a background worker/thread.** All of its "loading" (`page_loader`, `group_loader`, `recent_group_loader`, `delete_callback`) are plain synchronous `Callable`s invoked directly on the UI thread inside `_load_more()` / `_load_group()` / `_perform_delete()`, wrapped in try/except with `self.notify(..., severity="error")` on failure. There is no `run_worker`, no `on_worker_state_changed`, no `on_unmount` worker-cancel in this file. So it is **not** the worker-based example you're looking for — see section 5 below for the real pattern.

What it *does* demonstrate well (useful for `AliasHistoryModal` regardless):
- Class hierarchy: `KeyedPaneEntryJumpMixin[str], OptionListNavigationMixin, ModalScreen[SavedAgentGroupRevivalResult | None]` (`:59-63`), same MRO order as `model_picker_modal.py`.
- `BINDINGS` splices `OptionListNavigationMixin.NAVIGATION_BINDINGS` plus custom `Binding` entries with `priority=True` for keys that must win over child-widget bindings (`pagedown` load-more, `ctrl+d` delete) (`:67-72`).
- Composes a two-pane layout: `Horizontal` containing a list `Vertical` (heading + `OptionList`) and a preview `Vertical` (heading + `VerticalScroll` + `Static`) — a pattern to steal if `AliasHistoryModal` wants list+preview.
- `_create_options(*, jump_hints=None)` (`:300-391`) builds the full `Option` list including disabled section headings, empty-state rows, a "Load more..." sentinel, and separators — using a local `labeled(label, option_id)` closure that calls `apply_jump_hint_prefix(label, hint)` when a hint exists for that id.
- `_jump_target_keys()` explicitly **filters out disabled rows** (headings/separators/empty-state) so jump hints never land on them (`:470-482`) — the key convention: only truly-selectable rows are jump targets.
- `_jump_select_key`/`_jump_repaint` both funnel through `_rebuild_options(highlighted_option_id=..., show_jump_hints=...)`, and setting `option_list.highlighted` is noted to emit `OptionHighlighted`, driving the preview panel via the normal highlight-changed handler — i.e. jump selection reuses the same code path as manual navigation rather than duplicating preview-update logic.
- `invalidate_jump_hints(identities_changed=True, target_count=0)` is called after any operation that changes the row set (pagination `_load_more`, delete `_perform_delete`) — same convention as `model_picker_modal.py`.
- `on_key` intercepts jump keys only (`:501-509`); regular navigation relies on `OptionListNavigationMixin` bindings directly since there's no filter-input to fight with.

---

## 3. `src/sase/ace/tui/modals/pane_entry_jump.py` (264 lines, read in full)

Two classes: `PaneEntryJumpMixin` (position/index-based) and `KeyedPaneEntryJumpMixin[K: Hashable]` (key-based adapter over the same state machine).

**State** (`:29-44`): a lazily-created `_JumpState` dataclass (`mode_active`, `pending_prefix`, `hint_to_index`, `index_to_hint`, `back_stack`), stored on `_pane_jump_state: _JumpState | None = None` — lazy so the mixin needs no `__init__` and doesn't perturb Textual's MRO.

**Host hooks a subclass of `PaneEntryJumpMixin` must implement** (`:62-76`, all `raise NotImplementedError`):
```python
def _jump_target_count(self) -> int: ...      # how many rows are jumpable
def _jump_current_index(self) -> int | None: ...  # currently-selected logical index
def _jump_select_index(self, index: int) -> None: ...  # move selection
def _jump_repaint(self) -> None: ...           # rebuild rows + hint line
```

**Host hooks for `KeyedPaneEntryJumpMixin[K]`** (`:217-227`, also `raise NotImplementedError` — these are what `ModelPickerModal` and `SavedAgentGroupRevivalModal` actually implement):
```python
def _jump_target_keys(self) -> list[K]: ...   # keys of jumpable rows, visual order
def _jump_current_key(self) -> K | None: ...  # key of currently selected row
def _jump_select_key(self, key: K) -> None: ...  # move selection to key
# _jump_repaint is still required too (inherited abstract hook, not overridden by KeyedPaneEntryJumpMixin)
```
`KeyedPaneEntryJumpMixin` implements the three `PaneEntryJumpMixin` hooks (`_jump_target_count`, `_jump_current_index`, `_jump_select_index`) in terms of the keyed hooks by doing `keys = self._jump_target_keys(); keys.index(current)` etc. (`:242-255`). It does **not** implement `_jump_repaint` — the host must still supply that directly.

**Host-facing API** (properties/methods a host calls):
- `jump_mode_active: bool` property (`:80-83`)
- `jump_back_stack: list[int]` property (`:86-88`)
- `jump_hint_for(index) -> str | None` (`:90-95`, plain mixin) / `jump_hints_by_key() -> dict[K, str]` (`:231-238`, keyed mixin — builds `{key: hint}` by enumerating `_jump_target_keys()` and calling `jump_hint_for(index)` per position)
- `action_jump_to_entry()` (`:97-111`) — entry point bound to `'`. Builds `indices = range(_jump_target_count())`, calls `build_jump_hint_maps(indices)` (from `..actions.navigation.jump_hints`) to allocate `hint_to_index`/`index_to_hint`, sets `mode_active = True`, clears `pending_prefix`, then calls `self._jump_repaint()`.
- `handle_jump_key(key: str) -> bool` (`:113-144`) — the core state machine, called from the host's `on_key`. Returns `False` immediately if not in jump mode (so callers can fall through to normal key handling). `escape` → `exit_jump_mode()`. `apostrophe` while in jump mode → pop from `back_stack` and jump there without pushing current (i.e. apostrophe again = "go back"; if the stack is empty it falls through to targeting the *first* hint via `next(iter(state.hint_to_index.values()), None)`). Any other key is matched via `match_jump_hint(state.hint_to_index, state.pending_prefix, key)` from `jump_hints.py`, whose `JumpHintMatchOutcome` can be `PENDING` (accumulate `pending_prefix`, return `True`), `INVALID` (`exit_jump_mode()`, return `True`), or a resolved `match.target` index. Terminates by calling `self._perform_jump(target_index, push_current=...)`.
- `clear_jump_hints()` / `exit_jump_mode()` (`:146-153`): `clear_jump_hints` drops mode+hints but preserves the back stack; `exit_jump_mode` also repaints.
- `invalidate_jump_hints(*, identities_changed: bool, target_count: int)` (`:155-171`) — called by hosts any time rows are rebuilt. If `identities_changed`, wipes hints **and** the back stack (stale indices no longer name the same rows). Otherwise only drops hints if any currently-allocated hint now points outside `[0, target_count)`.
- `_perform_jump(target_index, *, push_current)` (`:189-202`) — internal: validates range (exits jump mode if out of range), pushes `current_index` onto `back_stack` (capped at `JUMP_BACK_STACK_LIMIT = 10` via `del state.back_stack[:-JUMP_BACK_STACK_LIMIT]`) if `push_current` and it differs from target, clears hints, calls `self._jump_select_index(target_index)`.

**End-to-end apostrophe flow**: user presses `'` → host's `action_jump_to_entry` bound in `BINDINGS` fires → hints allocated, `mode_active=True`, `_jump_repaint()` shows hint-prefixed labels. Subsequent keystrokes go through the host's `on_key`, which (by convention in every example) checks `self.jump_mode_active` first and calls `self.handle_jump_key(normalize_jump_key(event.key, event.character))`, `event.prevent_default()`/`event.stop()` if consumed. A full/partial hint match resolves or extends `pending_prefix`; a complete match calls `_perform_jump` → `_jump_select_key`/`_jump_select_index` on the host, which typically re-renders without hints and moves the `OptionList.highlighted` index. Pressing `'` again while still in jump mode pops the back stack instead of re-arming.

---

## 4. `src/sase/ace/tui/modals/base.py` (81 lines, read in full — this is the entire file)

```python
class OptionListNavigationMixin:
    _option_list_id: str

    NAVIGATION_BINDINGS = [
        ("escape", "cancel", "Cancel"),
        ("q", "cancel", "Cancel"),
        ("j", "next_option", "Next"),
        ("k", "prev_option", "Previous"),
        ("down", "next_option", "Next"),
        ("up", "prev_option", "Previous"),
        ("ctrl+n", "next_option", "Next"),
        ("ctrl+p", "prev_option", "Previous"),
    ]

    def action_cancel(self) -> None:
        self.dismiss(None)  # type: ignore[attr-defined]

    def action_next_option(self) -> None:
        self.query_one(f"#{self._option_list_id}", OptionList).action_cursor_down()  # type: ignore[attr-defined]

    def action_prev_option(self) -> None:
        self.query_one(f"#{self._option_list_id}", OptionList).action_cursor_up()  # type: ignore[attr-defined]
```
That's the entirety of the navigation help — no `_highlighted_row_id`-style helper lives here (that idiom is defined per-host, e.g. `_highlighted_option_id()` in `model_picker_modal.py`, `_current_highlighted_option_id()` in `saved_agent_group_revival_modal.py`, `_highlighted_row_id()` referenced via `TYPE_CHECKING` protocol in `models_panel_jump.py`). `next_option`/`prev_option` are pure delegation to Textual's built-in `OptionList.action_cursor_down/up`, nothing custom. The file also defines `CopyModeForwardingMixin` (forwards `%`-prefixed copy-mode keys to `AceApp`) and `FilterInput(Input)` (adds `ctrl+f`/`ctrl+b` readline bindings) — neither relevant to your worker/jump question but worth knowing they live here too.

---

## 5. The actual worker + jump combination — nothing combines both *exactly*, here are the closest real examples

I grepped every file in `modals/` for `run_worker(...thread=True...)` and separately for `KeyedPaneEntryJumpMixin`/`PaneEntryJumpMixin`. **No single file in `src/sase/ace/tui/modals/` combines `KeyedPaneEntryJumpMixin` with a `thread=True` worker.** The two conventions exist in disjoint files. The closest matches, in order of relevance:

### 5a. `models_panel_provider_modal.py` — `ProviderRoutingModal` (501 lines, read in full)

This is the best template for a **`ModalScreen` with full worker lifecycle** (though it uses plain `OptionListNavigationMixin`, not the jump mixin — `ModelsPanel` itself, not this child modal, owns the jump mixin for Launch Control's own rows).

```python
class ProviderRoutingModal(OptionListNavigationMixin, ModalScreen[bool]):
    _option_list_id = "provider-routing-list"
```

Worker fields set up in `__init__` (`:96-98`):
```python
self._snapshot_worker: Worker[ProviderRoutingSnapshot] | None = None
self._snapshot_keep_provider: str | None = None
self._write_worker: Worker[ProviderWriteOutcome] | None = None
```

**Launch on mount** (`:119-124`):
```python
def on_mount(self) -> None:
    option_list = self.query_one("#provider-routing-list", OptionList)
    option_list.focus()
    self._restore_highlight(option_list, None)
    self._update_description()
    self._start_snapshot_load()
```

**Worker start, with a `group=` name and cancel-in-flight-before-relaunch guard** (`:203-216`):
```python
def _start_snapshot_load(self, *, keep_provider: str | None = None) -> None:
    if self._snapshot_worker is not None and not self._snapshot_worker.is_finished:
        self._snapshot_worker.cancel()

    def task() -> ProviderRoutingSnapshot:
        return self._load_snapshot()

    self._snapshot_keep_provider = keep_provider
    self._snapshot_worker = self.run_worker(
        task, thread=True, exclusive=True, group=_SNAPSHOT_GROUP,
    )
```
(`_SNAPSHOT_GROUP = "provider-routing-snapshot"`, `_WRITE_GROUP = "provider-routing-write"` — module-level constants at `:49-50`.) A second, independent write worker (`_submit_disable`/`_submit_enable`, `:218-299`) similarly cancels any in-flight snapshot worker before starting, wraps its `task()` body in `try/except Exception as exc` and returns an outcome dataclass carrying `error: str | None` instead of letting the exception propagate — so **all** error surfacing happens via the returned result object plus `WorkerState.ERROR` for genuinely unexpected failures.

**Dispatch by worker identity** (`:301-305`):
```python
def on_worker_state_changed(self, event: Worker.StateChanged) -> None:
    if event.worker is self._snapshot_worker:
        self._on_snapshot_worker(event)
    elif event.worker is self._write_worker:
        self._on_write_worker(event)
```

**Snapshot worker handler — SUCCESS/ERROR/CANCELLED all handled** (`:307-327`):
```python
def _on_snapshot_worker(self, event: Worker.StateChanged) -> None:
    if event.state not in (WorkerState.SUCCESS, WorkerState.ERROR, WorkerState.CANCELLED):
        return
    keep = self._snapshot_keep_provider
    self._snapshot_worker = None
    self._snapshot_keep_provider = None
    if event.state == WorkerState.SUCCESS and event.worker.result is not None:
        self._apply_snapshot(event.worker.result, keep_provider=keep, emit_snapshot=False)
    elif event.state == WorkerState.ERROR:
        self.notify(f"Could not load provider routing: {event.worker.error}", severity="warning")
```
Note: CANCELLED is in the guard tuple purely to clear `_snapshot_worker`/`_snapshot_keep_provider` bookkeeping — no user-visible action beyond that (a cancelled load just silently drops).

**Write worker handler** (`:329-378`) similarly resets `self._write_worker = None`, distinguishes `WorkerState.ERROR` (toast `severity="error"`) vs a `SUCCESS` whose `outcome.error is not None` (same toast path) vs true success (`_apply_snapshot(...)` + a success toast + `self._changed = True`).

**Cancel on unmount** (`:126-129`):
```python
def on_unmount(self) -> None:
    for worker in (self._snapshot_worker, self._write_worker):
        if worker is not None and not worker.is_finished:
            worker.cancel()
```

**Blocking dismissal while a write is in flight** (`:131-137`, `action_back`):
```python
def action_back(self) -> None:
    if self._write_worker is not None and not self._write_worker.is_finished:
        self.notify("A provider-routing update is still in progress.", severity="warning")
        return
    self.dismiss(self._changed)
```

This modal does *not* show an explicit "loading…" placeholder before first paint because its constructor is handed an already-loaded `snapshot: ProviderRoutingSnapshot` synchronously (the caller loads it before pushing the modal) and `_start_snapshot_load` only *refreshes* it in the background.

### 5b. `models_panel_edit.py` — `AliasEditPreviewModal` (313 lines, read in full)

Directly relevant since it's already an alias-related `ModalScreen` in the `ModelsPanel` family, and explicitly documents the "planning…"/"writing…" busy-state convention you'll want for `AliasHistoryModal`:
```python
"""
Planning and writing both run in worker threads so the Rust call and disk IO
never block the event loop; the modal renders `planning…` / `writing…`
states in between.
"""
```
- `self._busy = True` set in `__init__` (line 79, comment `# planning on mount`) and `on_mount` calls `self._start_plan()` which launches `self._plan_worker = self.run_worker(task, thread=True, exclusive=True)` (`:199-204`).
- `_body_text()` (`:109-116`) branches on `self._error`, then `self._busy and self._plan is None` / `self._plan is None` → returns `Text("planning…", style=_MUTED)`; that's the loading-state text shown while the worker runs, rendered via a plain `Static` (`#alias-edit-preview`) updated by `_render_all()`.
- `on_worker_state_changed` dispatches by identity to `_on_plan_worker`/`_on_apply_worker` (`:261-265`), each handling only `SUCCESS`/`ERROR` (no `CANCELLED` branch, and **no `on_unmount` worker-cancel at all** in this file — a gap versus `ProviderRoutingModal`).
- `action_cancel` refuses to dismiss while `self._busy and self._apply_worker is not None` (a write is in flight) — same "don't abandon an in-flight write" idea as `ProviderRoutingModal.action_back`.

### 5c. `project_inventory_loading.py` (`InventoryLoadMixin`) + `project_inventory_pane_base.py` (`InventoryPaneBase`) — the only file combining a **generic worker-lifecycle mixin with `PaneEntryJumpMixin`** in one class, and the most complete lifecycle including `CANCELLED` + reload-coalescing + loading text. Not a `ModalScreen` (it's a `Vertical` embedded pane), but structurally this is the closest thing to "async-loading + jump-mixin host" in the whole codebase.

`InventoryLoadMixin[RecordT, IssueT]` (`project_inventory_loading.py`, full file, 130 lines):
```python
def _start_inventory_load(self) -> None:
    if self._loading:
        self._reload_pending = True
        return
    self._prepare_inventory_load()
    self._loading = True
    self._load_error = ""
    self._update_summary()
    self._worker = self.run_worker(
        self._load_inventory, thread=True, exclusive=False, exit_on_error=False,
    )

def _cancel_inventory_load(self) -> None:
    if self._worker is not None and not self._worker.is_finished:
        self._worker.cancel()

def on_worker_state_changed(self, event: Worker.StateChanged) -> None:
    if event.worker is not self._worker:
        return
    if event.state == WorkerState.SUCCESS:
        ...
        self._loading = False
        ...
    elif event.state == WorkerState.ERROR:
        self._loading = False
        self._load_error = str(event.worker.error) if event.worker.error else "inventory load failed"
        self._update_summary()
    elif event.state == WorkerState.CANCELLED:
        self._loading = False

    if event.state in (WorkerState.SUCCESS, WorkerState.ERROR, WorkerState.CANCELLED) and self._reload_pending:
        self._reload_pending = False
        self.call_later(self._start_inventory_load)
```
Key idiom worth copying: **reload-while-loading coalescing** — if a reload is requested while a load is already in flight, it just sets `_reload_pending = True` instead of launching a second worker, and the terminal-state handler re-triggers the load afterward via `call_later`.

`InventoryPaneBase[RecordT, IssueT](PaneEntryJumpMixin, OptionListNavigationMixin, InventoryLoadMixin[RecordT, IssueT], Vertical)` (`project_inventory_pane_base.py:47-52`) is where the two mixins are actually combined:
- `on_mount` (`:108-111`): `self._refresh_options(); self._start_inventory_load()`.
- `on_unmount` (`:113-116`): cancels a detail-panel debouncer, then `self._cancel_inventory_load()`.
- Loading placeholder text shown directly in the `OptionList` rows themselves rather than a separate `Static`: `_create_options()` (`:191-208`) — when `not self._filtered_records`, checks `if self._loading and not self._records: message = f"Loading {self._prefix} inventory…"` and yields a single disabled `Option(Text(message, style="dim"), id="empty")`.
- Jump hooks use the *plain* `PaneEntryJumpMixin` (index-based, not keyed): `_jump_target_count` → `len(self._filtered_records)`; `_jump_current_index` reads `OptionList.highlighted`; `_jump_select_index(index)` calls `_refresh_options(preferred_id=self._record_id(self._filtered_records[index]))`; `_jump_repaint` calls `_refresh_options()` (`:383-405`).
- `_apply_filters()` (`:162-189`) is the place `invalidate_jump_hints(identities_changed=..., target_count=len(self._filtered_records))` gets called after any row-set change — computing `identities_changed` by comparing before/after id lists, same pattern as the other modals but done generically here.

### 5d. `statistics_pane.py` — best example of the "paint a loading placeholder before the first worker result" UX (not jump-mixin, but very relevant to your "loading state before first result arrives" requirement)

In `compose()` (`:200-211`), tiles and the body `Static` are seeded with a loading placeholder rendered eagerly:
```python
with Horizontal(id="statistics-tiles"):
    for index, (_caption, _target_view) in enumerate(OVERVIEW_TILE_TARGETS):
        yield _StatTile(self._loading_panel("Loading", height=6), id=f"statistics-tile-{index}", classes="statistics-tile")
with VerticalScroll(id="statistics-body-scroll"):
    yield Static(self._loading_panel("Loading statistics", height=8), id="statistics-body")
```
Then `_start_load()` (`:607-636`) only repaints that placeholder if there's no cached result yet:
```python
def _start_load(self) -> None:
    ...
    self._loading = True
    self._last_error = ""
    self._update_heading()
    if self._last_result is None:
        self._paint_loading()

    def task() -> StatisticsViewData:
        return load_statistics_view(view, selected_range, project_filter, xprompt_focus, perf_group_by=perf_group_by)

    self._worker = self.run_worker(task, thread=True, exclusive=True, exit_on_error=False)
```
(so a *refresh* of already-loaded data doesn't flash the loading panel again — only the very first load does). `on_worker_state_changed` (`:638-682`) handles `SUCCESS` (validates the result still matches current view/range/filters before accepting it — stale-result guard, re-triggers `_schedule_load()` if not) and `ERROR` (`_paint_error(message)`), both setting `self._loading = False; self._loaded_once = True`. `on_unmount` (`:224-231`) cancels a debouncer, stops/clears a refresh `Timer`, and calls `self._worker.cancel()` unconditionally if set (no `is_finished` guard here, unlike `ProviderRoutingModal`/`InventoryLoadMixin` — `Worker.cancel()` is itself safe to call on an already-finished worker).

---

## Summary of what to combine for `AliasHistoryModal`

Since no existing file gives you both patterns pre-wired, synthesize:
- **Modal skeleton, `OptionList` building, filter/highlight helpers, `on_key` routing**: copy `model_picker_modal.py`'s structure (`ModelPickerModal`) — it's the cleanest full `KeyedPaneEntryJumpMixin[str] + OptionListNavigationMixin + ModalScreen[...]` example.
- **Worker lifecycle (start/cancel/dispatch/terminal-state handling/`group=`/`on_unmount`)**: copy `models_panel_provider_modal.py`'s `ProviderRoutingModal` pattern almost verbatim — it's a sibling `ModalScreen` in the exact same `models_panel_*` family, with the most complete `SUCCESS`/`ERROR`/`CANCELLED` handling plus `on_unmount` cancellation of in-flight workers.
- **"Loading…" placeholder before first result**: use `AliasEditPreviewModal`'s inline busy-text-in-`_body_text()` idiom (simplest, single `Static`) or, if you want a persistent list widget seeded with a disabled placeholder row, `InventoryPaneBase._create_options()`'s `"Loading {prefix} inventory…"` disabled-`Option` idiom.
- **Reload-while-loading coalescing** (relevant if "re-query actions" can be triggered while a load is already in flight): copy `InventoryLoadMixin`'s `_reload_pending` flag + `call_later` re-trigger.
- Remember `invalidate_jump_hints(identities_changed=True, target_count=0)` must be called any time the background load replaces the row set, exactly as both `model_picker_modal.py._apply_filter` and `saved_agent_group_revival_modal.py._load_more`/`_perform_delete` do — this is a hard convention across every jump-mixin host in the codebase.

# Research Report: AliasHistoryModal Reuse Targets

## 1. `src/sase/ace/tui/provider_styles.py` (full module)

Path: `/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/src/sase/ace/tui/provider_styles.py` (258 lines)

This is the canonical provider-theming module. Key exports (all top-level, no class needed by callers):

- **`_ProviderStyle`** (dataclass, `provider_styles.py:14-22`) — frozen palette record with `name_style`, `delimiter_style`, `model_style`, `secondary_style`, `dim_style` (all Rich style strings).
- **`_PROVIDER_FALLBACK_STYLES`** (`:33-118`) — dict keyed by lowercase provider name (`claude`, `anthropic`, `codex`, `fakey`, `grok`, `openai`, `qwen`, `opencode`, `agy`, `muse`, `meta`, `xai`) mapping to hard-coded hex-color palettes. `_NEUTRAL_PROVIDER_STYLE` (`:25-31`, violet `#AF87D7` family) is the fallback for unknown/`None` providers.
- **`_provider_style_for(provider: str | None) -> _ProviderStyle`** (`:138-154`) — resolves a provider's palette, overriding the fallback's `name_style` primary color with `sase.llm_provider.registry.provider_cli_status_color_map()` when available (`_with_primary`, `:128-135`). Private, but this is the resolution logic behind every public helper below.
- **`provider_emoji_badge(provider: str | None) -> str | None`** (`:157-159`) — thin re-export of `sase.integrations.provider_badges.provider_emoji_badge`.
- **`provider_name_style(provider: str | None) -> str`** (`:162-164`) — returns just the Rich style string for a provider-colored name.
- **`provider_model_badge_markup(llm_provider: str | None, model: str | None) -> str`** (`:186-211`) — **the primary reuse target**. Renders `PROVIDER(model)` as Rich *markup* (a string with `[style]...[/]` tags, already `rich.markup.escape`d), e.g. `[bold #FF5F00]CLAUDE[/][#D75F00]([/][#FFAF00]opus[/][#D75F00])[/]`. Internally calls `_resolve_provider_and_model()` (`:167-183`) which uses `sase.llm_provider.registry.resolve_model_provider` to infer provider from a bare model string when `llm_provider` isn't given, and `format_provider_model_label` for the no-provider-and-no-model-known fallback path.
- **`provider_header_text(provider: str, model_count: int) -> Text`** (`:214-222`) — builds a Rich `Text` group-header line: `"  ━ PROVIDER  N models"` themed with `secondary_style`/`name_style`/`dim_style`.
- **`model_option_text(*, provider, model_id, alias=None, hint=None, advisory_label=None, advisory_severity=None) -> Text`** (`:225-257`) — builds a dense selectable model row (`Text`) with optional leading hint key, alias suffix, and an advisory marker/label styled via `sase.llm_provider.registry.model_advisory_color`/`model_advisory_marker` (deliberately *not* provider-colored, so warnings read as warnings).

**Effort rendering is not in this file.** The effort suffix (`" @ <effort>"`) convention lives in `src/sase/ace/tui/model_alias_styles.py` (see below), which wraps `provider_model_badge_markup`.

### Companion module actually used for "badge + effort": `model_alias_styles.py`

Path: `/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/src/sase/ace/tui/model_alias_styles.py` (118 lines) — this is what Launch Control's own alias rows and the model picker use, and is likely the best single call for history rows:

```python
# model_alias_styles.py:96-104
def provider_model_text(
    provider: str | None,
    model: str | None,
    effort: str = "",
) -> Text:
    """Build a measurable, truncatable ``PROVIDER(model) @ effort`` badge."""
    text = Text.from_markup(provider_model_badge_markup(provider, model))
    append_effort_suffix(text, effort)
    return text
```

Other exports in that file useful for history rows: `append_effort_suffix(text, effort)` (`:42-47`, appends `" @ "` + effort in `_EFFORT_LEVEL_STYLE = "bold #AF87FF"`), `alias_state_text(...)` (`:73-93`, provenance/override/configured/implicit tag styling with `_OVERRIDE_TAG_STYLE`, `_CONFIGURED_TAG_STYLE`, `_IMPLICIT_TAG_STYLE`), `append_alias_reference`, `append_pool_chip`, and the `MODEL_ALIAS_KIND_LABELS`/`MODEL_ALIAS_KIND_STYLES`/`OWNERSHIP_ACCENT` constants.

Consumers of `provider_styles.py` for reference (`grep` hits, non-pycache): `model_alias_styles.py`, `modals/notification_modal_question.py`, `modals/models_panel_selector_builder.py`, `modals/model_picker_options.py`, `modals/plan_approval_modal.py`, `modals/model_picker_rows.py`, `widgets/_prompt_input_bar_completion_rows_directives.py`, `widgets/_agent_list_render_agent.py`. Note `models_panel_rendering.py`/`models_panel_rendering_rows.py` do **not** import `provider_styles` directly — they go through `model_alias_styles.py`'s `provider_model_text`.

## 2. Duration/relative-time helpers

### `src/sase/ace/tui/modals/models_panel_duration.py` (full, 159 lines)

This module is about **override-duration selection UI**, not elapsed/relative-time formatting for history rows:

- `now() -> float` (`:18-20`) — `time.time()` indirection for testability.
- `format_remaining(seconds: float) -> str` (`:23-35`) — formats an integer-second countdown as `"1h30m"`/`"45s"` (drops seconds once minutes/hours present).
- `format_duration_chosen(seconds: float | None) -> str` (`:38-42`) — `"until cleared"` for `None`, else `format_remaining(seconds)`; used for override-confirmation notifications.
- `RelativeOverrideDuration` (frozen dataclass, `.seconds`), `OverrideUntilCleared`/`OVERRIDE_UNTIL_CLEARED` sentinel, `OpenOverrideUntil`/`OPEN_OVERRIDE_UNTIL` sentinel, and the `OverrideDurationResult` union type (`:45-65`).
- `_parse_override_custom(raw) -> OverrideDurationResult` (`:68-75`) — wraps `sase.llm_provider.parse_override_duration`.
- `DurationPickerModal(DurationChoiceModal[...])` (`:78-159`) — the actual duration-choice modal (15m/30m/1h/2h/4h/Until cleared/exact-time/custom), built from `..duration_choice_modal.DurationChoiceModal`/`DurationChoice`.

### `src/sase/ace/tui/modals/models_panel_time.py` (full, 355 lines)

This module is about **absolute local-time entry** for overrides (a focused input modal), not "N ago" relative formatting:

- `OverrideUntilBack`/`OVERRIDE_UNTIL_BACK` sentinel (`:27-31`).
- `ResolvedOverrideUntil` (frozen dataclass, `:34-51`) — `target: datetime`, `expires_at: float`, `target_display`, `notification_display`, `remaining_display`, `timezone_display`, plus a `.preview` property combining them into a two-line confirmation string.
- Parsing helpers: `_parse_clock`, `_valid_local_candidates`, `_localize_wall_time`, `_resolve_override_until(value, *, timezone=None, clock=_clock_now) -> ResolvedOverrideUntil` (`:152-230`) — accepts `5pm`, `17:30`, `1730`, `today 9am`, `tomorrow 9am`, `YYYY-MM-DD HH:MM`, offset-qualified ISO.
- Display formatters: `_format_day` (`:116-122`, `"today, Wed Jul 12"`/`"tomorrow, ..."`), `_format_clock` (`:132-133`, `"5:00 PM"`), `_format_remaining` (`:136-149`, `"<1m"`/`"2d 3h"` style, max 2 components).
- `OverrideUntilModal(ModalScreen[ResolvedOverrideUntil | OverrideUntilBack])` (`:256-346`) — the actual focused time-entry modal (`Escape` → back).
- `__all__` (`:349-354`): `OVERRIDE_UNTIL_BACK`, `OverrideUntilBack`, `OverrideUntilModal`, `ResolvedOverrideUntil`.

### Important: neither file has "3m ago" / elapsed-duration formatting

Since neither named module actually contains relative-time-ago or run-elapsed-duration formatting, here are the real precedents for that (especially relevant since a "history" list is exactly what these were built for):

- **`src/sase/ace/tui/modals/plugins_browser_agent_clis_history.py`** — closest structural precedent to `AliasHistoryModal` (renders a bounded list/table of past runs with status glyph, timestamp, trigger badge, elapsed time). Key functions:
  - `_relative_time(epoch: float, *, now: float) -> str` (`:252-267`) — `"just now"` / `"{s}s ago"` / `"{m}m ago"` / `"{h}h ago"` / `"{d}d ago"` (< 7 days), else falls back to `format_local(epoch, "%b %d %H:%M")` from `sase.core.time`.
  - `_elapsed(seconds: float) -> str` (`:274-275`) — `f"{max(0.0, seconds):.1f}s"`.
  - `build_agent_cli_history_panel(status, runs, *, enabled, error, all_clis, now, max_rows, colors) -> RenderableType` (`:37-111`) — builds a `Panel` with title/subtitle (`"N of M runs · H toggle-hint"`), using a `Table.grid` (`_per_cli_body`, `:138-160`) or a `Group` of `Text` lines (`_all_clis_body`, `:163-184`) depending on mode — a good structural template for a bounded, subtitled history list.
- **`sase.notifications.models.format_relative_time(iso_timestamp: str) -> str`** (`notifications/models.py:109-128`) — canonical ISO-8601-based `"Ns ago"/"Nm ago"/"Nh ago"/"Nd ago"` formatter, tz-aware via `sase.core.time.get_timezone()`; widely reused elsewhere (`modals/notification_modal_options.py`, `modals/notification_modal_report.py`, `modals/report_modal.py`, `modals/prompt_stash_row.py` via `sase.notifications.models.format_relative_time`, `widgets/notification_indicator.py`). Sibling `format_relative_until` (`:188-`) and `format_absolute_time` (`:143-`, four-tier `today/yesterday/same-year/other-year` display) live in the same module.
- **`sase.ace.hooks.timestamps.format_duration(seconds: float) -> str`** (`hooks/timestamps.py:11-29`) — `"1h2m3s"`/`"1m23s"`/`"45s"` style elapsed-duration formatter (different convention than `models_panel_duration.format_remaining`, which omits zero components).
- Other independent `"Nm ago"` implementations exist per-surface: `modals/logs_pane_render.py:64-81` (`_format_relative_age`), `modals/procs_pane_render.py:46-61` (`_relative_time`), `modals/project_inventory_rendering.py:215-218`, `modals/saved_agent_group_revival_rendering.py:64-68`, `widgets/_axe_dashboard_render.py:159-178` (`format_relative_time`, ISO-timestamp based). These show the convention is copy-pasted per module rather than centrally shared beyond `sase.notifications.models`.

**Recommendation for the new render module**: import `format_relative_time`/`format_absolute_time` from `sase.notifications.models` for "ago" timestamps (if run records store ISO strings) or replicate the tiny epoch-based `_relative_time` pattern from `plugins_browser_agent_clis_history.py` (if run records store floats), and use `models_panel_duration.format_remaining` only if you need "remaining" countdown semantics (you likely want an *elapsed* run-duration string instead, for which `hooks/timestamps.format_duration` or `_tools_panel_timeline.py:39-54`'s `format_duration(duration_ms, ...)` — ms-based, `"123ms"/"4.5s"` — are the existing conventions, depending on units available).

## 3. `src/sase/ace/tui/styles.tcss` — Provider Routing modal CSS block (verbatim)

File: `/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/src/sase/ace/tui/styles.tcss`, lines **2381–2432**:

```css
ProviderRoutingModal {
    align: center middle;
}

#provider-routing-container {
    width: 86;
    max-width: 95%;
    height: auto;
    max-height: 34;
    border: double #FFAF5F;
    background: $surface;
    padding: 1 2;
}

#provider-routing-title {
    width: 100%;
    height: 1;
    text-align: center;
    text-style: bold;
    color: #FFAF5F;
    margin-bottom: 1;
}

#provider-routing-summary {
    width: 100%;
    height: 2;
    text-align: center;
    color: $text-muted;
}

#provider-routing-list {
    height: auto;
    max-height: 10;
    margin-top: 1;
}

#provider-routing-description {
    height: 5;
    color: $text-muted;
    border-top: solid $secondary;
    padding-top: 1;
    margin-top: 1;
}

#provider-routing-footer {
    height: auto;
    text-align: center;
    color: $text-muted;
    border-top: solid $secondary;
    padding-top: 1;
    margin-top: 1;
}
```

Notes on the pattern to copy for `AliasHistoryModal`/`#alias-history-*`:
- **Screen-level centering**: `ProviderRoutingModal { align: center middle; }` — the Python `class ProviderRoutingModal` selector, not an id.
- **Centered container + double border + width/chrome budget**: `#provider-routing-container` — fixed `width: 86` with `max-width: 95%` safety, `height: auto` capped by `max-height: 34`, `border: double #FFAF5F` (this modal's accent color; a new modal should pick its own accent hex consistent with its theme), `background: $surface`, `padding: 1 2`.
- **Title**: full-width, height 1, centered, bold, colored to match the border accent, `margin-bottom: 1`.
- **Bounded "OptionList" viewport**: `#provider-routing-list { height: auto; max-height: 10; margin-top: 1; }` — this is the direct precedent for an `#alias-history-list` (or similar) row viewport cap.
- **"Detail-panel"-equivalent border rule**: `#provider-routing-description` uses `border-top: solid $secondary; padding-top: 1; margin-top: 1;` with `color: $text-muted` and a fixed `height: 5` — this is the closest thing to a bounded detail/description strip in this modal (contrast with `#models-panel-description` at `styles.tcss:2355-2370`, which uses `height: auto; min-height: 4;` instead of a fixed height — worth choosing deliberately for the history modal depending on whether detail content is variable-length).
- **Footer treatment**: `#provider-routing-footer` — `height: auto`, centered, `color: $text-muted`, same `border-top: solid $secondary; padding-top: 1; margin-top: 1;` rule reused verbatim from the description block (this triple — border-top/padding-top/margin-top — is the repo-wide "chrome divider" idiom; it's reused identically at `#models-panel-description` and `#models-panel-footer`, `styles.tcss:2355-2379`, just above this block).

`ProviderRoutingModal` is defined in `src/sase/ace/tui/modals/models_panel_provider_modal.py` (class definition location, confirmed via grep), if you want to check id-to-widget wiring alongside the CSS.

## 4. `docs/ace.md` — "Launch Control" section (full)

Heading: `## Launch Control {#launch-control}` at **`docs/ace.md:2540`**, running through **line 2941** (next `##` is `## Notifications Modal` at `:2942`).

### Structure
1. Intro paragraph (`:2542-2546`) — entry point (`,m` from any tab), top-level sections.
2. Row-grid conventions paragraph (`:2548-2552`).
3. "Launch settings" paragraph (`:2554-2560`).
4. Alias-row state-tag paragraph (`:2562-2570`).
5. Built-in vs. custom alias sections paragraph (`:2572-2579`).
6. Custom buckets paragraph (`:2581-2590`).
7. Detail strip paragraph (`:2592-2608`).
8. Misplaced-builtin-alias warning paragraph (`:2610-2619`).
9. **Top-level key table** (`:2621-2636`, `| Key | Action |`), verbatim:

```markdown
| Key                   | Action                                                                                                              |
| --------------------- | ------------------------------------------------------------------------------------------------------------------- |
| `l` / Right / `Enter` | **Open** the highlighted bucket                                                                                     |
| `h` / Left            | **Back** to the top level from an open bucket                                                                       |
| `'`                   | **Jump** — paint adaptive hints; a hint moves the highlight without activating the row, and a second `'` jumps back |
| `o`                   | **Override** — set/change a time-bound temporary alias/default-effort/runner-limit override                         |
| `x`                   | **Clear** — remove the active temporary override on the highlighted override-capable row                            |
| `e`                   | **Edit** — change the persistent configured value                                                                   |
| `r`                   | **Reset** — unset an alias/model setting or the big-epic threshold                                                  |
| `p`                   | **Providers** — disable, extend, or re-enable registered providers for future routing                               |
| `Ctrl+E`              | **Effort** — persistently edit, temporarily override, or clear the global default effort                            |
| `Ctrl+R`              | **Limit** — persistently edit, temporarily override, or clear the global runner limit                               |
| `Esc` / `q`           | Close the panel                                                                                                     |
```

   *(This is where a new `H` binding entry for opening `AliasHistoryModal` from an alias row should be added, e.g. `| \`H\` | **History** — view this alias's agent-run history |`.)*

10. Big-epic-threshold editor paragraph (`:2638-2653`).
11. **`### Default effort controls`** (`:2654-2670`) — prose only, no key table (describes `e`/`o`/`x` inline).
12. **`### Max running agents controls`** (`:2688-2716`) — prose only, no key table.
13. **`### Provider routing controls`** (`:2717-2747`) — prose plus a small *state* table (not a key table):

```markdown
| State                    | Meaning                                                                 |
| ------------------------ | ----------------------------------------------------------------------- |
| `available`              | The provider is registered and its declared CLI is present.             |
| `CLI unavailable`        | Automatic alias routing already skips it because its CLI is missing.    |
| `disabled · <time> left` | You temporarily disabled it; routing skips it until expiry or clearing. |
```

14. **`### Temporary overrides`** (`:2748-2846`) — long prose on override picker/duration flow, top-bar pills, precedence.
15. **`### Persistent edits`** (`:2847-2890`) — Edit/Reset write-path prose, `Pool / fallback...` builder.
16. **`### Examples`** (`:2891-2938`) — bulleted `Highlight X, key, ... — result` walkthrough examples.
17. Closing pointer to `docs/llms.md` (`:2939-2940`).

### Important correction on "nested modal key table" precedent

Within the Launch Control section itself, **none** of the `###` subsections (Default effort, Max running agents, Provider routing) actually include their own `| Key | Action |` table — they only use inline prose (`Press \`e\` to edit...`) or, for Provider routing, a *state* table. So there's no exact in-section precedent to copy structurally for a nested key table.

The clearest actual precedent elsewhere in the doc for "a `##` parent section with an `###` sub-heading that has its own dedicated key table" is **`### Plan Approval Keybindings`** under `## Plan Workflows`, at `docs/ace.md:3817-3833`:

```markdown
### Plan Approval Keybindings

| Key          | Action                                                   |
| ------------ | -------------------------------------------------------- |
| `a`          | Approve and run coder without committing an SDD tale     |
| `t`          | Save as tale and run coder                               |
| `c`          | Open [Custom Approval](#custom-approval)                 |
| `r`          | Reject the plan                                          |
| `f`          | Request feedback (send follow-up questions to the agent) |
| `e`          | Edit the plan file in `$EDITOR`                          |
| `E`          | Mark the plan as an epic (creates bead)                  |
| `y`          | Copy plan content to clipboard                           |
| `Y`          | Copy plan file path to clipboard                         |
| `Ctrl+D`/`U` | Scroll plan content down / up                            |
| `g` / `G`    | Scroll to top / bottom                                   |
| `q` / `Esc`  | Cancel                                                   |
```

with a sibling `### Custom Approval` sub-modal directly below it (`:3836-3848`) that also gets its own small key table. **This `### <Modal Name> Keybindings` pattern is the right template to follow** for documenting `AliasHistoryModal`: add a new `### Alias History Keybindings` (or `### Alias History`) subsection after `### Provider routing controls` (or wherever fits editorially, e.g. right after the alias-row description paragraphs around `:2608`), with its own `| Key | Action |` table for the modal's own bindings (e.g. `Esc`/`q` to close, navigation, maybe a filter/detail key), and reference the new top-level `H` row (step 9 above) to link into it, mirroring how the top-level table's `p` row and `Ctrl+E`/`Ctrl+R` map onto their own `###` subsections.

Two of four research agents are done — modal/worker patterns and preview/copy/reference helpers. Waiting on styling conventions and row/footer wiring before I start writing code.

Three of four research agents are done. Waiting on the last one (ModelsPanel row types and footer wiring), though I've already gathered much of that directly.

Waiting for the final research agent and the `just install` background task.

No conflicting `H`/`shift+h` binding currently exists in `ModelsPanel.BINDINGS`. Here is the full research report.

## 1. `models_panel_types.py` and `models_panel_rows.py`

**`models_panel_types.py`** (`/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/src/sase/ace/tui/modals/models_panel_types.py`) defines only one type:

```python
@dataclass(frozen=True)
class ModelsPanelResult:
    changed: bool = False
    provider_routing_changed: bool = False
```
(lines 8–19) — the dismissal payload for the whole panel. Not a row type.

**`models_panel_rows.py`** (`/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/src/sase/ace/tui/modals/models_panel_rows.py`) defines the scalar-setting row dataclasses and re-exports `AliasView`/`BucketView` (which are *not* defined here — see below) into a combined union:

- `LaunchModelSettingRow` (lines 26–57):
  ```python
  @dataclass(frozen=True)
  class LaunchModelSettingRow:
      field: LaunchModelField
      label: str
      detail: str
      snapshot: LaunchModelSettingSnapshot

      @property
      def row_id(self) -> str: return f"launch:{self.field}"
      @property
      def override_key(self) -> str: return self.snapshot.override_key
      @property
      def config_path(self) -> str: return self.snapshot.config_path
      @property
      def raw_value(self) -> str: return self.snapshot.raw_value
      @property
      def is_overridden(self) -> bool: return self.snapshot.override is not None and not self.is_override_paused
      @property
      def is_override_paused(self) -> bool: return self.snapshot.override_paused_by_provider_disable is not None
  ```
  This is the row type for `default_model` / `epic_lander_model` / `big_epic_lander_model` (the three `LaunchModelField` values, `models_panel_rows.py:24–38` for names, `:103–107` for the `(field, label)` order tuple used to build rows). **It has no `referenced_alias` field of its own** — that field lives one level down, on `LaunchModelSettingSnapshot` (see next section), reached via `row.snapshot.referenced_alias`.

- `DefaultEffortSettingRow` (lines 60–68), `RunnerLimitSettingRow` (71–79), `BigEpicPhaseThresholdSettingRow` (82–91) — all simple frozen dataclasses wrapping a snapshot (or, for the threshold row, a bare `int`) plus fixed `row_id`/`label`/`kind` defaults. `ScalarSettingKind = Literal["default_effort", "runner_limit", "big_epic_phase_threshold"]` (line 21).

- `ModelsPanelDisplayRow` union (lines 94–101):
  ```python
  ModelsPanelDisplayRow = (
      LaunchModelSettingRow
      | DefaultEffortSettingRow
      | RunnerLimitSettingRow
      | BigEpicPhaseThresholdSettingRow
      | AliasView
      | BucketView
  )
  ```
  This is the complete panel row-type union you'll switch on for the `H` handler.

- `build_launch_model_setting_rows(...)` (110–140) builds the three `LaunchModelSettingRow`s plus the `BigEpicPhaseThresholdSettingRow` for display.

**`AliasView` and `BucketView` are NOT in either file you named** — they live in `/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/src/sase/llm_provider/alias_view.py` and are imported into `models_panel_rows.py` via `from sase.llm_provider import AliasView, BucketView, EffectiveDefaultEffortSnapshot` (line 10).

- **`AliasView`** (`alias_view.py:65–168`):
  ```python
  @dataclass(frozen=True)
  class AliasView:
      name: str                     # bare alias name, no "@" marker
      kind: AliasKind                # "role" | "user"
      configured: bool
      configured_value: str | None
      provider: str | None           # currently-effective provider
      model: str                     # currently-effective model
      override: TemporaryLLMOverride | None
      configured_source: str | None = None
      description: str | None = None
      bucket: str | None = None
      implicit_value: str | None = None
      selector_mode: ModelAliasSelectorMode | None = None
      selector_members: tuple[ModelAliasSelectorMember, ...] = ()
      effort: str | None = None      # currently-effective effort
      override_paused_by_provider_disable: TemporaryProviderDisable | None = None
  ```
  So: **bare alias name = `AliasView.name`**; **current effective provider/model/effort = `AliasView.provider` / `.model` / `.effort`** (an active temporary override wins if present — resolved eagerly at `build_alias_views` time, see `alias_view.py:396–442`). Useful properties: `.is_overridden`, `.is_override_paused`, `.is_custom_builtin_shadow`, `.is_user_owned`, `.references` (immediate `@alias` the configured value points to, or `None`), `.raw_value`, `.implicit_fallback`, `.reference_effort`.

- **`BucketView`** (`alias_view.py:171–234`):
  ```python
  @dataclass(frozen=True)
  class BucketView:
      name: str
      description: str | None
      members: tuple[AliasView, ...]
  ```
  Properties: `.alias_count`, `.is_user_owned`, `.user_member_count`, `.override_count`, `.paused_override_count`, `.custom_builtin_shadow_names/_count`, `.model_counts`, `.model_summary`.
  **Member order**: built in `build_models_panel_rows` (`alias_view.py:448–479`), where each bucket's members are `tuple(sorted(members, key=lambda member: member.name))` — **alphabetical by alias name**, not config/insertion order (line 471).

**`LaunchModelSettingSnapshot`** (`/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/src/sase/llm_provider/model_launch_settings.py:57–74`):
```python
@dataclass(frozen=True, slots=True)
class LaunchModelSettingSnapshot:
    field: LaunchModelField
    config_path: str
    raw_value: str
    provider: str
    model: str
    effort: str | None
    provenance: LaunchModelProvenance
    referenced_alias: str | None      # <-- confirmed present
    override_key: str
    alias_trail: tuple[str, ...] = ()
    override: TemporaryLLMOverride | None = None
    selector_mode: str | None = None
    selector_members: tuple[ModelAliasSelectorMember, ...] = ()
    override_paused_by_provider_disable: TemporaryProviderDisable | None = None
```
**`referenced_alias: str | None` confirmed** — it is *how you distinguish an alias-backed launch-model row from a concrete one*: `build_launch_model_setting_snapshot` (`model_launch_settings.py:118–271`) computes `referenced_alias, _alias_effort = normalize_model_alias_reference(raw_value)` (line 167) — `raw_value` is e.g. `"@large"` (alias-backed → `referenced_alias="large"`) vs. `"claude/fable"` (concrete → `referenced_alias=None`). When a temporary override is active on the setting, `referenced_alias` is explicitly forced to `None` (line 162) since a live override always pins to a concrete provider/model. **So: `row.snapshot.referenced_alias is not None` ⇒ alias-backed launch-model row; `is None` ⇒ concrete/override-pinned launch-model row.**

**Other settings rows and how to reject them by type** (this is exactly the `isinstance` dispatch pattern used throughout the codebase — see `models_panel_override.py` and `models_panel_alias_edit.py` below):
- `DefaultEffortSettingRow` — global default reasoning-effort row.
- `RunnerLimitSettingRow` — global running-agent-limit row.
- `BigEpicPhaseThresholdSettingRow` — big-epic authored-phase threshold row (a bare `int`, no alias at all).

None of these three carry any alias reference — they should be the "reject with row-specific warning" branch for `H`, mirroring the existing convention (see `action_override`/`action_clear` in `models_panel_override.py:122–178` and `action_edit`/`action_reset` in `models_panel_alias_edit.py:115–193`, quoted in full below).

## 2. `models_panel_display.py` — selected row + notify convention

File: `/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/src/sase/ace/tui/modals/models_panel_display.py`

Selected-row resolution (lines 314–329):
```python
def _highlighted_row_id(self) -> str | None:
    option_list = self.query_one("#models-panel-list", OptionList)
    highlighted = option_list.highlighted
    if highlighted is None:
        return None
    try:
        option = option_list.get_option_at_index(highlighted)
    except Exception:
        return None
    return str(option.id) if option.id is not None else None

def _selected_row(self) -> ModelsPanelDisplayRow | None:
    row_id = self._highlighted_row_id()
    if row_id is None:
        return None
    return self._row_by_id.get(row_id)
```
`self._row_by_id: dict[str, ModelsPanelDisplayRow]` is populated on the facade (`models_panel.py:170`) and rebuilt whenever rows are redrawn. Two narrowing helpers already exist and are the pattern to follow:
```python
def _selected_alias(self) -> AliasView | None:            # models_panel_display.py:331-338
    row = self._selected_row()
    if isinstance(row, BucketView):
        self.notify("Press `l`/`enter` to open this bucket")
        return None
    if isinstance(row, AliasView):
        return row
    return None

def _selected_model_row(self) -> AliasView | LaunchModelSettingRow | None:   # :340-347
    row = self._selected_row()
    if isinstance(row, BucketView):
        self.notify("Press `l`/`enter` to open this bucket")
        return None
    if isinstance(row, (AliasView, LaunchModelSettingRow)):
        return row
    return None
```
These are exactly the shape a new `_selected_alias_history_targets()`-style helper should take.

**`notify(...)` convention** (grepped across all mixins — 40+ call sites). It's always `self.notify(<message>[, severity="warning"|"error"])`, with **no** severity for success/info toasts. Row-specific-warning examples to match exactly:
```python
self.notify("Press `l`/`enter` to open this bucket")                                  # models_panel_display.py:334
self.notify("An override update is still in progress.", severity="warning")           # models_panel_display.py:380
self.notify("Use e to edit the running-agent limit", severity="warning")              # models_panel_alias_edit.py:154
self.notify(
    "big epic starts at has no temporary override; press e to edit "
    "or r to reset.",
    severity="warning",
)                                                                                       # models_panel_override.py:133-137
self.notify(f"No active override on {label}", severity="warning")                     # models_panel_override.py:189
self.notify(f"@{view.name} has no configured value to reset", severity="warning")     # models_panel_alias_edit.py:175-178
```
So the `H`-on-settings-row rejection should read something like `self.notify("<label> has no alias history to show.", severity="warning")`, dispatched via `isinstance` exactly like `action_override`/`action_edit` do (full code below).

## 3. Launch Control footer — important correction

`keybinding_footer.py` (`/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/src/sase/ace/tui/widgets/keybinding_footer.py`) **contains zero references to `ModelsPanel`** (`grep -n "ModelsPanel\|models_panel\|models-panel"` returns nothing). That widget (`class KeybindingFooter`) is the shared bottom-bar for the **main app screen** (Patch/Agent lists etc.) and is mounted only in `_app_layout.py` — it never appears inside `ModelsPanel`, which is a `ModalScreen`.

`ModelsPanel`'s own footer is a plain `Static(id="models-panel-footer")` (composed in `models_panel_display.py:128`), whose text comes entirely from a bespoke method **in `models_panel_display.py` itself**: `_footer_markup()` (lines 166–228). This is the single place to add `H` to the footer text. It already branches per-row-type:

```python
def _footer_markup(self) -> str:
    if self.jump_mode_active:
        action = "back" if self.jump_back_stack else "first"
        return f"JUMP ' {action}  <esc> cancel"
    row = self._selected_row()
    if self._active_bucket is None and isinstance(row, BucketView):
        return (
            "[green]ctrl+e[/green]=Effort  "
            "[green]ctrl+r[/green]=Limit  "
            "[green]p[/green]=Providers\n"
            "[green]l/enter[/green]=Open  "
            "[dim]j/k[/dim]=Navigate  "
            "[dim]'[/dim]=Jump  "
            "[dim]esc[/dim]=Close"
        )
    if isinstance(row, DefaultEffortSettingRow):
        return (
            "[green]o[/green]=Override  "
            "[green]x[/green]=Clear  "
            "[green]e[/green]=Edit  "
            "[green]r[/green]=Reset  "
            "[green]p[/green]=Providers\n"
            "[green]ctrl+e[/green]=Effort  "
            "[dim]j/k[/dim]=Navigate  "
            "[dim]'[/dim]=Jump  "
            "[dim]esc[/dim]=Close"
        )
    if isinstance(row, RunnerLimitSettingRow):
        return (... "p[/green]=Providers\n" "[green]ctrl+r[/green]=Limit  " ...)
    if isinstance(row, BigEpicPhaseThresholdSettingRow):
        return (... "e/enter[/green]=Edit  " "r[/green]=Reset  " ...)
    footer = (   # the "default" branch: AliasView, LaunchModelSettingRow (concrete or alias-backed)
        "[green]ctrl+e[/green]=Effort  "
        "[green]ctrl+r[/green]=Limit  "
        "[green]p[/green]=Providers\n"
        "[green]o[/green]=Override  "
        "[green]x[/green]=Clear  "
        "[green]e[/green]=Edit  "
        "[green]r[/green]=Reset"
    )
    if self._active_bucket is not None:
        footer += "  [green]h[/green]=Back"
    return footer + (
        "  [dim]j/k[/dim]=Navigate  [dim]'[/dim]=Jump  [dim]esc[/dim]=Close"
    )
```
Note the **`BucketView` branch and the fallthrough "default" branch (`AliasView` + `LaunchModelSettingRow`) are the same code path returned by the final `footer` block for non-bucket-container rows** — the fallthrough currently covers *both* alias rows and launch-model-setting rows (concrete and alias-backed) with no distinction between them. To add `H` to "the alias, alias-backed launch-model, and bucket variants only — not scalar/concrete-model variants" per your spec, you cannot simply append to the shared fallthrough string, because that fallthrough is also hit by *concrete* `LaunchModelSettingRow`s (where `row.snapshot.referenced_alias is None`). You'll need to split that branch (or conditionally append `[green]H[/green]=History` based on `isinstance(row, AliasView) or (isinstance(row, LaunchModelSettingRow) and row.snapshot.referenced_alias is not None)`), then handle the `BucketView` branch separately (which already returns before the fallthrough).

CLAUDE.md's footer convention (`/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/src/sase/ace/CLAUDE.md`, "Footer Keybinding Convention" section, lines 16–33) — this doc's stated implementation location (`keybinding_footer.py`) is **generic app-wide guidance for the main screen's footer**, not literally accurate for `ModelsPanel`'s modal-local footer, but the *same rules* apply and are exactly what `_footer_markup()` already implements by hand:
> 1. A keymap appears in the footer if and only if it has a condition that is sometimes true and sometimes false.
> 2. Global actions (quit, refresh, tab switch, fold, edit query, etc.) belong in the help modal only.
> Formatting: Keymaps sorted alphabetically; symbol keys first. Named keys lowercase angle brackets.

Since `H` is conditional (only alias/alias-backed-launch/bucket rows), it satisfies rule 1 and belongs in the footer, consistent with how `o`/`x`/`e`/`r` (alias-only actions) already only appear in the non-bucket, non-scalar-setting branch.

## 4. Mixin composition and BINDINGS

Confirmed: **`BINDINGS` is centralized as a single flat list on the `ModelsPanel` facade class itself** — no per-mixin `BINDINGS` lists exist anywhere in the Models-panel family. Evidence:

```
$ grep -rln "BINDINGS" src/sase/ace/tui/modals/models_panel*.py
models_panel_edit.py            # separate modal (AliasEditPreviewModal), own BINDINGS, not a ModelsPanel mixin
models_panel_provider_modal.py  # separate modal (ProviderRoutingModal), own BINDINGS
models_panel_selector_builder.py# separate modal (SelectorBuilderModal), own BINDINGS
models_panel.py                 # <-- the only BINDINGS on the ModelsPanel facade
models_panel_runner_limit_cards.py
models_panel_effort_cards.py
models_panel_threshold_cards.py
models_panel_time.py
```
The last five are all *separate* `ModalScreen` subclasses pushed on top of `ModelsPanel` (their own picker/duration modals), not mixins folded into `ModelsPanel`'s bindings. `models_panel_jump.py` (`ModelsPanelJumpMixin`, `models_panel_jump.py:22`) has **no `BINDINGS`** — jump is entirely triggered by the apostrophe key already declared in `ModelsPanel.BINDINGS` plus a raw `on_key` intercept (`models_panel_jump.py:58+`) that runs before Textual's bindings dispatch while `jump_mode_active` is true.

`ModelsPanel` class declaration (`/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/src/sase/ace/tui/modals/models_panel.py:101–138`):
```python
class ModelsPanel(
    ModelsPanelDisplayMixin,
    ModelsPanelRunnerLimitMixin,
    ModelsPanelEffortMixin,
    ModelsPanelProvidersMixin,
    ModelsPanelOverrideMixin,
    ModelsPanelThresholdMixin,
    ModelsPanelAliasEditMixin,
    ModelsPanelJumpMixin,
    OptionListNavigationMixin,
    ModalScreen[ModelsPanelResult],
):
    """View model aliases and manage temporary or persistent values."""

    _option_list_id = "models-panel-list"

    BINDINGS = [
        ("escape", "close", "Close"),
        ("q", "close", "Close"),
        ("j", "next_option", "Next"),
        ("k", "prev_option", "Previous"),
        ("down", "next_option", "Next"),
        ("up", "prev_option", "Previous"),
        ("ctrl+n", "next_option", "Next"),
        ("ctrl+p", "prev_option", "Previous"),
        ("apostrophe", "jump_to_entry", "Jump"),
        ("l", "enter_bucket", "Open bucket"),
        ("right", "enter_bucket", "Open bucket"),
        ("h", "leave_bucket", "Back"),
        ("left", "leave_bucket", "Back"),
        ("o", "override", "Override"),
        ("x", "clear", "Clear"),
        ("e", "edit", "Edit"),
        ("r", "reset", "Reset"),
        ("ctrl+e", "manage_default_effort", "Effort"),
        ("ctrl+r", "manage_runner_limit", "Limit"),
        ("p", "providers", "Providers"),
    ]
```
Note `ModelsPanel` deliberately **re-declares** j/k/up/down/ctrl+n/ctrl+p/escape/q inline rather than spreading `OptionListNavigationMixin.NAVIGATION_BINDINGS` (`base.py:59–68`, itself just `[("escape","cancel",...), ("q","cancel",...), ("j","next_option",...), ...]`) — `OptionListNavigationMixin` is included purely to supply `action_next_option`/`action_prev_option`/`action_cancel` (`base.py:70–80`); `ModelsPanel` overrides `action_cancel` itself (`models_panel_display.py:389–391`) to alias to `action_close`. No conflict currently exists with `H`/`shift+h` (`grep -n "H\b" models_panel.py` → no hits), so adding `("H", "alias_history", "History")` (or similar) to this single list is where the new binding belongs. Every corresponding `action_<name>` method is implemented in whichever mixin owns that concern (e.g., `action_providers` in `ModelsPanelProvidersMixin`, `action_override`/`action_clear` in `ModelsPanelOverrideMixin`, `action_edit`/`action_reset` in `ModelsPanelAliasEditMixin`) — Python's MRO across the 9 mixins resolves the method by name regardless of which mixin file defines it, so a new `action_alias_history` could live in a new small mixin, or in `ModelsPanelDisplayMixin` alongside `_selected_row()`.

## 5. Push-a-modal-without-mutating-parent pattern

The cleanest, most directly analogous example is `action_providers` in `ModelsPanelProvidersMixin` (`/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/src/sase/ace/tui/modals/models_panel_providers.py:197–221`), bound to the `p` key exactly as you described:

```python
def action_providers(self) -> None:
    """Open the provider-routing manager."""
    self.app.push_screen(  # type: ignore[attr-defined]
        ProviderRoutingModal(
            self._provider_snapshot,
            load_snapshot=self._load_provider_routing_snapshot,
            on_snapshot=self._on_provider_modal_snapshot,
        ),
        callback=self._on_provider_modal_dismissed,
    )

def _on_provider_modal_snapshot(
    self,
    snapshot: ProviderRoutingSnapshot,
    _keep_provider: str | None,
) -> None:
    selected = self._highlighted_row_id()  # type: ignore[attr-defined]
    self._apply_provider_snapshot(snapshot, keep=selected, update_rows=True)
    self._changed = True
    self._provider_routing_changed = True

def _on_provider_modal_dismissed(self, changed: bool | None) -> None:
    if changed:
        self._changed = True
        self._provider_routing_changed = True
```

Key conventions to mirror for `H`:
- Always `self.app.push_screen(...)` (not `self.push_screen(...)`) — this is universal across every mixin (`models_panel_alias_edit.py`, `models_panel_override.py`, `models_panel_effort.py`, `models_panel_runner_limit.py`, `models_panel_threshold.py`, `models_panel_selector_builder.py`, `models_panel_provider_modal.py` — all 25+ `push_screen` call sites use `self.app.push_screen`).
- Pass a `callback=` that receives the pushed screen's dismiss value; if the new alias-history modal is purely read-only with nothing for `ModelsPanel` to react to, the callback can be a no-op or omitted entirely, matching `AgentRunLogModal(OptionListNavigationMixin, ModalScreen[None])` (`/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/src/sase/ace/tui/modals/agent_run_log_modal.py:175`) — a `ModalScreen[None]` that composes `OptionListNavigationMixin.NAVIGATION_BINDINGS` for its own escape/q/j/k navigation. This is a good structural template for a new read-only `AliasHistoryModal`, since it never needs to signal `changed`/`provider_routing_changed` back to `ModelsPanel` the way overrides/edits do.
- `ModelsPanel` never rebuilds/mutates its own row state just to open a child modal — state mutation (`self._changed = True`, `self._refresh_rows(...)`) only happens in the *dismissal* callback, after the pushed modal reports something changed, and only for flows that actually change data (override/clear/edit/providers). A pure-viewer `H` action needs none of that — it can be a single `self.app.push_screen(AliasHistoryModal(aliases=...))` call with no callback, or a callback that simply does nothing on `None`.

**Data layer for the alias-history query already exists and is unused by any TUI so far** (`grep` across `src/sase/ace/` found zero references to `alias_history`/`load_alias_history`): `/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/src/sase/llm_provider/alias_history.py`. Its entry point:
```python
def load_alias_history(
    aliases: str | Sequence[str],
    *,
    limit_per_alias: int | None = None,
    include_hidden: bool = False,
    projects: Sequence[str] | None = None,
    freshness: AliasHistoryFreshness = "cached",
    prompt_snippet_bytes: int = DEFAULT_ALIAS_HISTORY_PROMPT_SNIPPET_BYTES,
    index_path: Path | str | None = None,
    snapshot: ProjectDisplaySnapshot | None = None,
) -> AliasHistoryView: ...
```
It already accepts a `Sequence[str]` of alias names (line 215) and returns one `AliasHistoryGroup` per alias inside `AliasHistoryView.groups` (lines 112–135) — i.e., it's already shaped to accept "a set of aliases to query" resolved from whatever row type is selected. Resolving row → alias set for the `H` action would be:
- `AliasView` → `{row.name}`
- `BucketView` → `{member.name for member in row.members}` (already alphabetically ordered per §1)
- `LaunchModelSettingRow` where `row.snapshot.referenced_alias is not None` → `{row.snapshot.referenced_alias}`
- `LaunchModelSettingRow` where `row.snapshot.referenced_alias is None`, or any of `DefaultEffortSettingRow` / `RunnerLimitSettingRow` / `BigEpicPhaseThresholdSettingRow` → reject via `isinstance` dispatch + `self.notify(..., severity="warning")`, matching `action_override`/`action_clear`/`action_edit`/`action_reset`'s existing per-row-type rejection pattern quoted in full in §1/§2 above.

All four research agents are done. Let me check on the `just install` background task before I begin writing code.

`just install` finished. Let me check the existing prompt-preview reading helper for the exact convention to follow.

Now I have everything needed. Let me start writing the implementation, beginning with the pure state module.

Let me simplify this to pass styles directly rather than the append-then-stylize dance.

Both modules import cleanly — the pyright diagnostics were stale from before `just install` finished. Now let's wire the mixin and binding into `ModelsPanel`.

Now let's wire the footer in `models_panel_display.py`.

Good, my changes are restored. Let's just run mypy directly (the project's actual lint gate) rather than relying on the IDE's pyright, to see whether these are real issues.

Now let's run ruff to catch any real lint issues before continuing.

Both ruff and mypy are clean; the pyright import-resolution errors are a stale LSP index (confirmed textual is installed and all these modules import successfully). Let's continue with the footer wiring.

Now let's add the CSS block. Let me find the exact insertion point beside the Provider Routing styles.

Now let's add the dedicated `### Alias History` subsection after the Provider routing controls section.

Now let's write the pure-logic and pure-rendering tests.

Let's run these two pure test files now to catch mistakes early before writing the heavier mounted tests.

Now let's run this test file.

Found the bug: I was setting `_launch_model_rows` after mount, but `_replace_display()` doesn't rebuild `_top_rows` from it — only the initial `compose()` does. Let me fix the test to set it before pushing the screen.

Now let me remove the ineffective `_replace_display()` calls across all four affected tests since setting `_launch_model_rows` before `push_screen` is sufficient.

Good, all four occurrences replaced. Let's run the tests again.

Let me add a `_patch_launch_model_rows` helper and rewrite the four affected tests to use it, avoiding the async provider-snapshot race.

Now let's update the four affected tests to use this helper instead of the racy direct assignment.

All 15 tests pass. Let's run ruff on this file, then move on to the mounted `AliasHistoryModal` tests.

Let me consolidate the test builder helpers into a shared module to avoid duplicating them across the rendering tests and the upcoming mounted-modal tests.

Now let's refactor `test_alias_history_rendering.py` to use these shared helpers.

Now let's run this test file and iterate on failures.

Found the real bug: `OptionList` itself binds `enter` to its own `action_select`, so my screen-level binding never fires — I need `on_option_list_option_selected` like `model_picker_modal.py` uses. Let me fix the modal.

Now let's fix the hidden-toggle test's stub so it echoes back the requested `include_hidden` value.

Now let's re-run the full mounted test file.

All 16 tests pass. Let's clean up the ruff/pyright-flagged unused params and run ruff on all new test files.

Now let's run the full existing Models-panel test suite to check for regressions from the footer and binding changes.

Excellent, no regressions — 408 passed. Now let's run the project's required verification gate.

Symvision's lint step is failing because my new code now genuinely uses symbols that were previously epic-whitelisted as "not yet used." Before touching any epic-symbol whitelist, let me read the required symvision memory note.

This symvision failure has two parts: my new stale whitelist entries (expected — I should remove them) plus unrelated stale entries for `sase-n9`/`sase-na.2` symbols I didn't touch. Let me verify whether those are pre-existing breakage on `master`.

Now let's remove the four entries confirmed as stale by symvision (`AliasHistoryGroup`, `AliasHistoryRun`, `AliasHistoryView`, `load_alias_history`), keeping the two still-legitimate ones (`AgentAliasHistoryLimitWire`, `AliasHistoryProvenance`, `AliasHistoryStatusRollup` — wait, those weren't flagged).

My fix resolved the entries tied to my change. The remaining `sase-n9`/`sase-na.2` failures are pre-existing and unrelated (confirmed identical on `master` before my changes) — per project convention I'll file a task bead for those rather than fix unrelated code.

Both epics now have discovered-issue notes recorded, so no new task bead is needed. Let's confirm the overall lint state now.

My own `sase-n8` fixes are confirmed durable — those errors are gone. The remaining `sase-n9`/`sase-na.2` failures are pre-existing, already tracked on their causal-owning epics, and appear to be actively churning from concurrent agent activity in this shared environment. Let me check how `just check` is structured to see if I can still validate my diff's own gates.

Let's run `just check` directly to see its actual behavior and confirm every gate relevant to my diff passes, despite the pre-existing/actively-churning symvision issue.

Real formatting issues in my new files — let's auto-format and re-run.

Good, `just fmt` reformatted the files. Let's confirm all tests still pass after reformatting, then re-run `just check`.

All 63 tests pass. Now let's re-run `just check`.

Every gate through my diff's actual concerns passes cleanly (fmt, ruff, mypy, feature-flags, pyscripts, test-waits, changelog, terminology). Only the pre-existing, epic-owned symvision staleness blocks the full `just check` run. Let me still verify the scoped test-selection lane directly since `just check` never reached it.

I'll wait for the scoped test run to complete.

I'll pick up where the prior session left off: verify the implementation now within this single turn, then close the bead and commit.

This matches what the prior session reported: removing four stale symvision epic-symbol whitelist entries (`AliasHistoryGroup`, `AliasHistoryRun`, `AliasHistoryView`, `load_alias_history`) now that this new code actually uses them. That's expected and intentional. Let me look at the new files and confirm the full diff is coherent before verifying.

Good, install succeeded. Now let's run the focused test files for this feature.

All 63 tests pass. Now let's run the broader Models-panel regression suite plus ruff/mypy on the touched files, and check for whitespace/diff issues.

No regressions — 336 passed, 1 skipped (pre-existing). Now let's check lint gates on the touched/new files.

Clean. Now let's check for whitespace issues in the diff and confirm the symvision situation is genuinely pre-existing on master (not caused by this work).

Good — no whitespace issues, false alarm from my earlier pipeline test. Now let's confirm the pre-existing symvision failures are indeed unrelated to this diff by checking against master.

All checks pass and the bead is confirmed in progress with the right scope. Now let's close it per the finalizer instructions.

The close published successfully (no "committed locally but NOT published" error). Now let's commit the changes using the git commit skill.

The commit succeeded; the warnings are about unrelated prompt-archive publication housekeeping (pre-existing outbox backlog), not the commit itself. Let's verify the working tree is clean and pushed.

Working tree is clean and the branch is up to date with `origin/master` — the commit landed and pushed successfully.

## Summary

Implemented the Launch Control alias agent-history panel (bead `sase-n8.6`):

- **New modules**: `alias_history_state.py` (immutable snapshot/load-request state), `alias_history_rendering.py` (pure row/detail rendering), `alias_history_modal.py` (the `KeyedPaneEntryJumpMixin`/`OptionListNavigationMixin`/`ModalScreen` modal with threaded worker loads, Ctrl+K paging, `r` revalidate, `.` hidden-toggle, Enter→prompt preview, `y`→durable agent-reference copy), and `models_panel_history.py` (the `H` binding, row resolution, and context-aware footer wiring on `ModelsPanel`).
- **Styling & docs**: `AliasHistoryModal` CSS block in `styles.tcss` alongside Provider Routing, and a new `docs/ace.md` section covering the `H` key, provenance labels, and modal keybindings.
- **Tests**: 4 new test files (63 tests), all passing; full `models_panel` suite (336 passed, 1 pre-existing skip) shows no regressions.

Verified this turn: ruff check/format clean, mypy clean, `git diff --check` clean, no trailing whitespace, and `just symvision` confirms the four newly-used `sase-n8` epic-symbol entries are no longer stale (remaining `sase-n9`/`sase-na.2` symvision failures are pre-existing on `HEAD`, untouched by this diff).

Closed bead `sase-n8.6` with a verification note, then committed as `bc529f11f` via `/sase_git_commit` and confirmed it's pushed to `origin/master`.
