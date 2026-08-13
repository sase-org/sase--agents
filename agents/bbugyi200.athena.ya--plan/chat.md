# Chat History - ace-run (ya--code)

- **TIMESTAMP:** 2026-08-12 08:26:41 EDT
- **MODEL:** claude/sonnet
- **AGENT:** ya--code

## Linked Chats

- 1. --plan — `~/.sase/chats/202608/gh_sase_org__sase-ace_run-ya__plan-260812_073740.md`
- **2. --code** — `~/.sase/chats/202608/gh_sase_org__sase-ace_run-ya__code-260812_073740.md`

## Prompt

%model:@medium_worker
#gh:gh_sase-org__sase @/home/bryan/.sase/plans/202608/plan_toast_tier_and_epic_counts.md

The above plan has been reviewed and approved. Implement it now.


## Response

I'll start by reading the key files referenced in the plan to understand the current state before making changes.

I've kicked off research on the existing types and test scaffolding I'll need (validation result types, color constants, notification plumbing, and existing test structure). While that runs in the background, I'll wait for its findings before writing code since the implementation depends on exact signatures.

I don't actually need to schedule a wakeup — I'll be notified automatically when the research agent finishes. I'll wait for that now.

It's `src/sase/sdd/plan_waves.py`, not `src/sase/plan_waves.py`. Let's read it plus the display rendering file.

Research agent is still running; I'll wait for its completion notification.

That was an accidental empty agent launch on my part — I need to cancel it immediately since it serves no purpose.

Good, that confirms items 4-5. Now let's look at the notification_gates files.

Good, that placeholder agent is cleaned up. Still waiting on the real research agent (a0768728d83459c5a).

Still running. I'll wait for its completion notification rather than poll further.

Now let's find how `n.action` gets set on the Notification object, and where request_kind flows to Notification more precisely (need to see later in service.py where action_data is set onto Notification).

I'll wait for the completion notification rather than continuing to poll.

Now let's look at the test files.

Now I have all the information needed. Here's the full report.

## 1. `require_plan_approval_validation`

Defined in `/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/src/sase/_plan_approval_protocol.py:112-126` (re-exported from `src/sase/plan_approval_actions.py:50` via `from sase._plan_approval_protocol import (require_plan_approval_validation as require_plan_approval_validation,)`).

```python
def require_plan_approval_validation(
    plan_file: str | Path,
    tier: str,
) -> PlanValidationResult:
    """Validate an approval target before notifications or files are mutated."""
    plan_path = Path(plan_file).expanduser()
    validation = _validate_plan_for_approval(plan_path, tier)
    if validation.ok:
        return validation
    raise PlanApprovalValidationError(...)
```

It returns `PlanValidationResult` on success; raises `PlanApprovalValidationError` (a `PlanApprovalActionError`) on failure. `PlanValidationResult` is **not** in `plan_approval_actions.py` — it's defined (and imported into `plan_approval_actions.py:20`) in `/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/src/sase/sdd/plan_validate.py:84-91`:

```python
@dataclass(frozen=True)
class PlanValidationResult:
    """Complete strict-validation result from ``sase-core``."""

    schema_version: int
    ok: bool
    diagnostics: tuple[PlanDiagnostic, ...]
    plan: _ValidatedPlan | None
```

`.plan` is `_ValidatedPlan | None` (`plan_validate.py:66-82`), only populated when validation succeeds (`ok=True`):

```python
@dataclass(frozen=True)
class _ValidatedPlan:
    tier: str
    goal: str
    size: str | None
    model: str | None
    title: str
    phases: tuple[ValidatedPlanPhase, ...]
    patch: str | None
    bug_id: int | None
    parent_bead: str | None
    bead: str | None
    parent: str | None
    proposed_by: str | None
```

So `.plan.phases` is `tuple[ValidatedPlanPhase, ...]`.

## 2. `ValidatedPlanPhase`

Also defined in `src/sase/sdd/plan_validate.py:54-63` (not in `plan_waves.py` — that file's docstring just references it structurally):

```python
@dataclass(frozen=True)
class ValidatedPlanPhase:
    """Normalized epic-phase data returned by the Rust validator."""

    id: str
    title: str
    depends_on: tuple[str, ...]
    description: str | None
    size: str
    model: str | None
```

- `id: str`
- `depends_on: tuple[str, ...]`
- `size: str` (not optional — always populated by the "launch" mode validator)

The `_WavePhase` Protocol it structurally satisfies is in `/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/src/sase/sdd/plan_waves.py:9-21` (note: it's `src/sase/sdd/plan_waves.py`, not `src/sase/plan_waves.py`):

```python
class _WavePhase(Protocol):
    @property
    def id(self) -> str: ...

    @property
    def depends_on(self) -> tuple[str, ...]: ...
```

`plan_phase_waves(phases: Iterable[_WavePhase]) -> tuple[tuple[str, ...], ...] | None` (same file, lines 24-52) does Kahn-style layering keyed on `.id`/`.depends_on` only; it does not use `.size`.

## 3. `normalize_plan_tier`

`/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/src/sase/sdd/plan_tiers.py:23-28`:

```python
def normalize_plan_tier(value: object) -> str | None:
    """Return a normalized supported plan-file tier, or ``None``."""
    if not isinstance(value, str):
        return None
    normalized = value.strip().lower()
    return normalized if normalized in PLAN_TIERS else None
```

`PLAN_TIERS = ("tale", "epic")` (line 13, same file). Accepts `object`; any non-`str` input, or a stripped/lowercased string not in `{"tale", "epic"}`, returns `None`. Returns `str | None`.

## 4. `_counts_value` idiom in `_plan_display_rendering.py`

Lines 483-509 of `/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/src/sase/sdd/_plan_display_rendering.py`:

```python
def _counts_value(summary: PlanDisplay) -> Text:
    if summary.phase_availability == "unavailable":
        return Text("unavailable", style=COLOR_PLAN_EMPTY)
    text = _count_phrase_text(len(summary.phases), "phase")
    text.append(" · ", style=COLOR_PLAN_SUMMARY)
    waves = plan_phase_waves(summary.phases)
    if waves is None:
        text.append("waves unavailable", style=COLOR_PLAN_EMPTY)
    else:
        text.append_text(_count_phrase_text(len(waves), "wave"))
    return text


def _count_phrase_text(count: int, singular: str) -> Text:
    text = Text()
    text.append(str(count), style=COLOR_PLAN_PRIMARY)
    text.append(f" {_pluralized_unit(count, singular)}", style=COLOR_PLAN_SUMMARY)
    return text


def _count_phrase(count: int, singular: str) -> str:
    return f"{count} {_pluralized_unit(count, singular)}"


def _pluralized_unit(count: int, singular: str) -> str:
    return singular if count == 1 else f"{singular}s"
```

Used at line 133: `rows.append((" Counts: ", _counts_value(summary)))`, and a plain-string variant `_count_phrase` used at line 100.

Colors are module-level constants (lines 33-40 of the same file):

```python
COLOR_PLAN_SUBHEADER = "bold #AF87FF"
COLOR_PLAN_PRIMARY = "bold #D7AFFF"
COLOR_PLAN_PATH = "#87AFFF"
COLOR_PLAN_PATH_BASENAME = "bold #87AFFF"
COLOR_PLAN_REASON = "#D7D7AF"
COLOR_PLAN_SUMMARY = "dim"
COLOR_PLAN_EMPTY = "dim italic"
PLAN_MISSING_SUFFIX_STYLE = "dim italic #FF8787"
```

So the idiom is: the number gets `COLOR_PLAN_PRIMARY` ("bold #D7AFFF"), the unit word gets `COLOR_PLAN_SUMMARY` ("dim"), and `·` separators between count-phrases also get `COLOR_PLAN_SUMMARY`.

## 5. `PLAN_PROVENANCE_AGENT_STYLE` and `COLOR_PLAN_PATH_BASENAME`

Both defined in `/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/src/sase/sdd/_plan_display_rendering.py`:
- `COLOR_PLAN_PATH_BASENAME = "bold #87AFFF"` — line 35
- `PLAN_PROVENANCE_AGENT_STYLE = "#87D7AF"` — line 42

Both are re-exported from `src/sase/sdd/plan_display.py` (imported at lines 26 and 35, listed in `__all__` at lines 58/67), which is the public-facing module other code should import from.

## 6. `_build_notification` — `src/sase/notification_gates/service.py:314-379`

```python
def _build_notification(
    spec: GateSpec,
    adapter: GateAdapter,
    paths: Any,
    notification_id: str,
) -> Notification:
    presentation = spec.presentation
    ...
    raw_action_data = presentation.get("action_data", {})
    action_data = {str(key): str(value) for key, value in dict(raw_action_data).items()}
    action_data.update(
        {
            "request_id": paths.root.name,
            "request_kind": adapter.kind,
            "bundle_path": str(paths.root),
            "request_path": str(paths.request),
            "response_path": str(paths.response),
            adapter.legacy_directory_key: str(paths.root),
        }
    )
    panel = normalize_gate_panel(presentation.get("panel"))
    if panel is not None:
        action_data[GATE_PANEL_ACTION_DATA_KEY] = panel
    panel_icon = normalize_gate_panel_icon(presentation.get("panel_icon"))
    if panel_icon is not None:
        action_data[GATE_PANEL_ICON_ACTION_DATA_KEY] = panel_icon
    origin_agent = normalize_gate_origin_agent(presentation.get("origin_agent"))
    if origin_agent is not None:
        action_data[GATE_ORIGIN_AGENT_ACTION_DATA_KEY] = origin_agent
    title = normalize_gate_title(presentation.get("title"))
    if title is not None:
        action_data[GATE_TITLE_ACTION_DATA_KEY] = title
    if preview is not None:
        action_data["preview_path"] = str(owned_resource_path(paths.root, preview))
    sender = str(presentation.get("sender", adapter.sender)).strip()
    ...
    return Notification(
        id=notification_id,
        timestamp=datetime.now(get_timezone()).isoformat(),
        sender=sender,
        muted=snooze_until is not None,
        snooze_until=snooze_until,
        icon=(...),
        color=validate_color(presentation.get("color"), "presentation.color"),
        notes=notes,
        files=files,
        tags=normalize_notification_tags(tags),
        action=adapter.action,
        action_data=action_data,
        silent=bool(presentation.get("silent", False)),
    )
```

Key takeaways for your plan:
- Every arbitrary string key in `presentation["action_data"]` (i.e. whatever your gate spec puts there) flows straight through onto `Notification.action_data`, stringified via `{str(key): str(value) ...}` — so `plan_tier`, `plan_phase_count`, `plan_wave_count`, `plan_phase_sizes` would need to be strings when placed in `presentation["action_data"]`.
- `action_data["request_kind"]` (line 337) is always set to `adapter.kind` — for the "plan" adapter that's `"plan"`, for "epic_plan" it's `"epic_plan"` (see item 7 for where those adapters are declared). This is unconditional and overwrites anything the caller put under `"request_kind"` (also enforced as reserved — see item 8).
- `Notification.action` (line 376) is `adapter.action`, not `adapter.kind` — that's `"PlanApproval"` / `"EpicApproval"` respectively (item 7).

## 7. `n.action` = `"EpicApproval"` vs `"PlanApproval"`

`/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/src/sase/notification_gates/adapters.py:262-284`:

```python
_ADAPTERS = (
    GateAdapter(
        kind="plan",
        display_title="Plan Approval",
        action="PlanApproval",
        pending_action_kind="plan_approval",
        sender="plan",
        request_filename="plan_request.json",
        response_filename="plan_response.json",
        legacy_directory_key="response_dir",
        auto_policy="approval",
    ),
    GateAdapter(
        kind="epic_plan",
        display_title="Epic Approval",
        action="EpicApproval",
        pending_action_kind="epic_approval",
        sender="epic",
        request_filename="plan_request.json",
        response_filename="plan_response.json",
        legacy_directory_key="response_dir",
        auto_policy="approval",
    ),
    ...
```

`adapter.action` is plumbed onto the `Notification.action` field in `service.py:376` (`action=adapter.action,`), and also stamped onto the outgoing envelope's `presentation["action"]` at `service.py:285` (`presentation["action"] = adapter.action`). So the `kind` ("plan"/"epic_plan") drives `request_kind` in `action_data`, while `action` ("PlanApproval"/"EpicApproval") drives `Notification.action` — two distinct discriminators consumers key off of (toasts key off `Notification.action`; gate/adapter dispatch keys off `kind`).

## 8. Reserved `action_data` keys — `src/sase/notification_gates/validation.py:143-161`

```python
    protected = {
        "bundle_path",
        GATE_ORIGIN_AGENT_ACTION_DATA_KEY,
        GATE_PANEL_ACTION_DATA_KEY,
        GATE_PANEL_ICON_ACTION_DATA_KEY,
        GATE_TITLE_ACTION_DATA_KEY,
        "request_id",
        "request_kind",
        "request_path",
        "response_path",
        adapter.legacy_directory_key,
    }
    overwritten = protected & set(action_data)
    if overwritten:
        raise GateError(
            "reserved_action_data",
            "presentation.action_data",
            f"reserved action_data key(s): {', '.join(sorted(overwritten))}",
        )
```

`adapter.legacy_directory_key` for both plan adapters is `"response_dir"`. None of `plan_tier`, `plan_phase_count`, `plan_wave_count`, `plan_phase_sizes` collide with this reserved set (or with the `GATE_*_ACTION_DATA_KEY` constants, which are `panel`, `panel_icon`, `origin_agent`, `title` — confirm by grepping those constants' string values if you want extra certainty, but none plausibly match).

## 9. Existing test structure for Plan/Epic toast paths

**`/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/tests/test_notification_toasts.py`** (284 lines) — tests `_format_notification_toast` and `format_batch_toasts` from `sase.ace.tui.actions.agents._toasts`. Uses shared `_make()` helper from `tests/_notification_toasts_helpers.py` (builds a bare `Notification` with `action`, `notes`, `action_data`, `files`, etc.). Relevant cases:
- `test_plan_approval_uses_original_plan_file_basename` (line 14) — action=`"PlanApproval"`, uses `action_data["original_plan_file"]` basename, asserts message format `"Plan ready for @{agent}: {basename}"`, severity `"warning"`.
- `test_epic_approval_uses_original_plan_file_basename` (line 33) — same but action=`"EpicApproval"`.
- Several fallback-basename / missing-agent-name / empty-notes variants (lines 46-83), all severity `"warning"`.
- `TestFormatBatchToasts` (line 228+) groups by severity, pluralizes labels e.g. `"2 plans"` (line 260) — batch tests use `_make(action="PlanApproval", ...)` repeatedly; no epic-specific batch test currently.

None of the current tests pass `plan_tier`/`plan_phase_count`/etc. through `action_data`, so anything relying on new fields is net-new coverage territory — no existing assertion needs revision for absence, but any new toast-formatting logic keying off these fields would need new test cases in this file's `TestFormatNotificationToast` class (and possibly `TestFormatBatchToasts` if grouping labels change per-tier).

**`/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/tests/test_notification_toast_polling.py`** (558 lines) — tests polling/alerting behavior via a `_FakeApp(LifecycleMixin, AgentNotificationMixin)` harness and `_patch_snapshot(...)`. Relevant cases:
- `test_single_new_plan_review_warns_and_rings` (line 43-44) is parametrized `@pytest.mark.parametrize("action", ["PlanApproval", "EpicApproval"])` — asserts `"Plan ready for @sase-n.4"` appears.
- `test_plan_and_epic_only_batch_rings_once` (line 111) — mixes `PlanApproval` + `EpicApproval` notifications, checks bell rings once and both messages ("Tale ready"/"Epic ready") land.
- `test_disappeared_plan_reviews_schedule_one_exact_artifact_delta` (line 213) — uses both a `PlanApproval` and an `EpicApproval` (`id="epic-review"`) notification together.
- No test here currently reads/asserts on `plan_tier`/`plan_phase_count`/etc. — same story, this is a place to add coverage rather than update existing assertions, unless your new code changes the toast text itself (in which case the message-content asserts above would need updating).

**`/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/tests/test_plan_approval_responses.py`** — around line 191-193 specifically:

```python
    desktop.assert_called_once_with(
        "[test] Plan Complete", "Plan ready for review in sase ace"
    )
```

(inside `test_manual_plan_gate_sends_desktop_notification_without_terminal_bell`, lines 164-194). This is the OS-level desktop-notification text (via `send_desktop_notification`), separate from the ACE in-app toast tested in files above — it's a fixed generic string, parametrized over both tale (`"approve"`) and epic (`"epic"`) choices (see the `@pytest.mark.parametrize` at lines 157-162), and does not currently vary by plan tier or phase/wave counts. If your plan adds tier-aware desktop-notification text, this assertion will need updating. Other tests in this file (`test_handle_plan_approval_forwards_agent_metadata` line 102, `test_handle_plan_approval_passes_agent_routing_timestamps` line 128) show the established pattern for asserting new `action_data` keys land in the gate's `request.presentation.action_data` via the `captured` dict — useful as a template for asserting your new `plan_tier`/`plan_phase_count`/`plan_wave_count`/`plan_phase_sizes` keys reach the request payload.

## 10. `tests/ace/tui/visual/test_ace_png_snapshots_update_toast.py` — full structure (already reproduced above; key points for mirroring)

- Module docstring + `pytestmark = pytest.mark.visual`.
- Imports `AcePage` from `sase.ace.testing`, the target mixin (`UpdateToastMixin`) and module (`update_toast`) under test, plus shared visual helpers from `tests.ace.tui.visual._ace_png_snapshot_helpers` (`patches`, `patch_startup_loaders`, `wait_for_visual_idle`) and `tests.ace.tui.visual.png_diff.AcePngSnapshotFixture`.
- Builds fixture data via plain helper functions (`_toast_status()`, `_grouped_toast_status()`, `_visual_incoming_commits()`) returning the domain dataclasses (`UpdateStatus`, `OutdatedComponent`, `ProviderUpdateCandidate`, `IncomingCommits`, `CommitSummary`).
- A small predicate helper `_toast_is_mounted(page)` polls `page.app.screen.query(Toast)`.
- Each `async def test_...(ace_png_visual: AcePngSnapshotFixture, monkeypatch)`:
  1. `patch_startup_loaders(monkeypatch)`.
  2. Builds/injects fixture status via `monkeypatch.setattr(update_toast, "_load_update_toast_config", ...)` and `monkeypatch.setattr(update_toast, "get_cached_update_status", lambda **_: status)`.
  3. Disables the real scheduling (`monkeypatch.setattr(UpdateToastMixin, "_schedule_startup_update_toast_check", lambda _self: None)`) but keeps a reference to the original callable to invoke manually later.
  4. Opens `async with AcePage(query='"visual"', patches=patches(), notifications=True, startup_policy="real") as page:`.
  5. Drives the UI (`page.press(...)`, `page.expect_state(...)`), manually calls the saved schedule function, `page.wait_for(...)` until the notification/toast is present, clears focus, `wait_for_visual_idle(page)`.
  6. Calls `ace_png_visual.assert_page_png(page, "<snapshot_name>", title="...")` — signature at `tests/ace/tui/visual/png_diff.py:74-85`, `assert_page_png(page, name, *, title=None, simplify=True, max_diff_pixels=None, max_diff_ratio=None, material_diff_threshold=None, max_material_diff_pixels=None)`.

This is the template to follow for a new plan/epic-toast PNG snapshot test: swap in plan/epic notification-producing fixtures and drive `AgentNotificationMixin`'s toast path instead of `UpdateToastMixin`.

## 11. `src/sase/notification_gates/kind_validation/plan.py` — confirms no `action_data` constraint

Read in full (152 lines). `validate_plan_spec(spec, adapter)` (lines 15-22) only calls:
- `_validate_plan_payload` — checks `spec.payload["authored_tier"]` and `spec.payload["plan_resource"]`.
- `_validate_plan_options` — checks `spec.query`/`spec.branches`/`spec.options` against `plan_gate_query`/`plan_gate_option_ids`.
- `_validate_plan_groups` — checks `spec.groups`.
- `_validate_plan_operations` — checks `spec.operations` against `plan_gate_edit_operation`.
- `_validate_plan_resources` — checks `spec.resources` (the plan.md resource + command resources).

None of these five helpers reference `spec.presentation` or `action_data` at all — confirmed the plan/epic kind-validation module places no constraints on `action_data` contents. The only `action_data` gate is the generic reserved-key check in `validation.py` (item 8), which applies uniformly across all gate kinds, not specifically plan/epic. This means adding `plan_tier`, `plan_phase_count`, `plan_wave_count`, `plan_phase_sizes` to a plan/epic gate's `presentation["action_data"]` is unconstrained by `kind_validation/plan.py` and only needs to avoid the reserved-key set in item 8 (which it does).

That was an error on my part — `ScheduleWakeup` is meant for `/loop` mode, not regular tasks. I'll cancel the pending wakeup and proceed directly with implementation now that I have the research results.

Now I have everything needed. Let me look at a couple more supporting files before writing code: the plan_display module's `__all__` exports and an existing sibling test file for structure reference.

Now writing the new `plan_tier_presentation.py` module, mirroring `bead_type_presentation.py`'s structure.

Now updating `_AUTO_APPROVE_KIND_STYLES` to build tale/epic entries from the new module:

This one already has an explicit return-type annotation on the function, which should give pyright the same bidirectional inference. Now let's finish updating `_build_plan_gate_spec` in plan_gate.py.

Now fix the note wording and add the `PlanValidationResult` type import:

Now let's mark task 3 and 4 complete/in-progress appropriately, and verify the plan_gate.py file overall looks correct.

That import-resolution diagnostic is likely a stale LSP cache since the file exists on disk — I'll confirm with `just check`/mypy later. Moving to the toast formatter now.

Now I'll rewrite `_toasts.py` with the markup-safety helper and the tier-aware plan/epic toast builder.

Let me verify this import issue is just stale IDE diagnostics rather than a real problem by running mypy directly.

Per this workspace's setup notes, I need to run `just install` first since this is an ephemeral workspace that may not have been used recently.

Now let's verify the module imports correctly and check the specific new modules with the venv's Python.

All modules import cleanly — the pyright diagnostics were just stale IDE cache. Let's quickly sanity-check the tier resolution and encode/decode round-trip logic before writing tests.

All working as designed. Now let's check the toast formatter output visually.

Both render exactly as the plan's goal examples specify. Now let's write the tests. First, the two new unit-test files.

Now let's update `test_notification_toast_polling.py`'s parametrized test:

Since I'm about to write a test that references a private (`_`-prefixed) class from another module, this touches the Symvision lint domain — let me check that memory before proceeding, as instructed by CLAUDE.md.

Good, I have the full picture now. Let me add the new plan-gate test after `test_authored_tier_routes_to_distinct_typed_actions`.

Now let's write the two new unit-test files.

All 35 pass. That stale-import diagnostic keeps popping up for `plan_summary` but the tests actually run and import it successfully, confirming it's just an LSP cache lag. Now let's run the updated plan-gate tests.

All 10 pass. Now let's rewrite `tests/test_notification_toasts.py` with the tier-aware assertions.

Now let's add the UserQuestion bracket-safety test and update the batch test's `"2 plans"` → `"2 tales"` plus a mixed tale/epic batch test.

Now let's update the batch-toast tests for the `"plans"` → `"tales"` label change, and add a mixed tale/epic grouping test.

Now let's run the full toasts test suite.

Let's run the full plan-gate and plan-approval test suites to make sure nothing else broke, plus the visual snapshot module for `_agent_display_header_metadata.py`.

Now let's re-run the full plan-gate test suite to confirm these fixes work and search more broadly for any other direct `_build_plan_gate_spec` callers I might have missed.

All 4 call sites are fixed. Let's re-run the full test suite to confirm.

All 55 pass. Now let's mark task 6 in-progress still and write the PNG snapshot test.

Now let's write the new PNG snapshot test file for the plan/epic toasts.

Now let's generate the golden PNGs and inspect them.

Both tests pass and generated golden PNGs. Let's view them to visually confirm the design looks right.

The toasts render exactly as designed — tier word as anchor, epic detail line legible with distinguishable size accents. Marking tests complete and moving to full verification.

Now let's run the full `just check` verification.

This is a pre-existing environment issue — the linked `sase-core` repo checkout is stale and missing Rust bindings that unrelated recent commits in this repo already depend on (unrelated to my toast-tier work). Let me sync it via the proper `/sase_repo` workflow.

The `sase repo open` command hit an unrelated config resolution issue. Since the Justfile's own error message explicitly permits updating the checkout directly as a fallback, I'll sync the already-cloned linked repo with git directly.

Fast-forwarded successfully with exactly the artifact-ref implementation. Now let's rerun `just check`.

Environment issue resolved. Now there's a real formatting nit in my test file — let's auto-fix with `just fmt`.

Formatting auto-fixed. Now let's rerun `just check` in full.

Let's check whether the stale symvision epic-symbol entries are safe to remove — i.e., whether those symbols already have real consumers now that the artifact-ref epic has landed.

Good — this surfaces a real, legitimate finding in my own code: `PlanCountsSummary` has no non-test consumer outside its defining file. Per the Symvision convention, I should make it private. Let me check all references first.

Confirmed — only used in its own file plus tests. I'll make it private, following the exact `_ValidatedPlan` precedent from `plan_validate.py`.

Now let's remove `_PlanCountsSummary` from `plan_summary.py`'s `__all__` since it's private now.

Good, the file looks clean. Now let's re-run the affected tests and symvision to confirm the fix.

All pass. Now let's re-run symvision to confirm my code is clean, and check whether the pre-existing artifact-ref findings remain (expected, since those are unrelated).

This confirms my own code is fully clean under Symvision — only pre-existing, unrelated artifact-ref findings remain, plus a stale Justfile whitelist entry (`sase-js`) that's now crashing the gate entirely for everyone. This blocks `just check` regardless of my changes, so I'll file a task bead for it rather than attempt to redesign an unrelated epic's symbol architecture myself.

Now let's search for existing duplicate task beads before creating a new one.

This is an exact match for the already-tracked, already-reopened bug `sase-it` (same bead `sase-js`, same symbol `ArtifactRefKindAlias`, corroborated by this same account just hours ago). No new task needed — I'll add a supplementary note with my own reproduction detail instead of a duplicate report.

Since this is a known *transient* lookup miss (not a real stale whitelist), a retry should succeed. Let's rerun `just check`.

All lint gates pass now. The scoped test lane escalated to the full suite (expected, since updating sase-core counts as a core-identity change). Let's wait for it to finish.

This will take a while since it escalated to the full test suite. I'll wait for it to complete rather than poll.

I'll wait for the background `just check` run to finish before continuing.

I'll stop issuing unnecessary filler actions and simply wait for the background `just check` task to notify me when it completes.

I'll verify the current repository state, then commit the completed work using the sase_git_commit skill.

This matches the plan implementation described in the prior session's terminated output — all files are the tier-aware plan toast feature. Let me quickly sanity-check the diffs on the core files before committing.

This matches the plan exactly (Step 3). The diff looks clean and correct. Now let's commit using the required skill.

The commit succeeded (the two warnings are about unrelated sidecar publication targets, not the commit itself). Let's confirm the working tree is clean and pushed.

Commit `09e5fc43e` is in place, working tree is clean, and the branch is up to date with `origin/master` (no ahead/behind markers).

## Summary

Implemented the approved plan (`plan_toast_tier_and_epic_counts.md`): plan approval toasts in ACE now name the tier ("Tale"/"Epic") instead of the generic "Plan", and epic toasts append a second line with phase/wave/size counts. Key changes:

- **New** `src/sase/plan_tier_presentation.py` — shared tale/epic label + accent colors, also now backing `_agent_display_header_metadata.py`'s auto-approve chips.
- **New** `src/sase/sdd/plan_summary.py` — derives phase/wave/size counts from plan validation and encodes/decodes them on notification `action_data`.
- `src/sase/plan_gate.py` — threads the validation result through to build the counts and fixes tale note wording ("Tale ready for review: ").
- `src/sase/ace/tui/actions/agents/_toasts.py` — tier-aware toast builder plus a markup-escaping fix for bracketed text (`[URGENT]`-style) that Textual was silently dropping.
- Corresponding test updates/additions, including two new PNG visual snapshots for the tale and epic toast designs.

All work from the prior session was already complete and verified (`just check` passing per the terminated output); this turn's job was solely to commit it, which is now done and pushed.
