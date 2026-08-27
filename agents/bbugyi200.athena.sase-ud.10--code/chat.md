# Chat History - ace-run (sase-ud.10--code)

- **TIMESTAMP:** 2026-08-27 00:15:47 EDT
- **MODEL:** claude/sonnet
- **AGENT:** sase-ud.10--code

## Linked Chats

- 1. --plan — `~/.sase/chats/202608/gh_sase_org__sase-ace_run-sase_ud_10__plan-260826_194336.md`
- **2. --code** — `~/.sase/chats/202608/gh_sase_org__sase-ace_run-sase_ud_10__code-260826_194336.md`

## Prompt

%model:@medium
#gh:gh_sase-org__sase
@plan:202608/questions_migration.md

The above plan has been reviewed and approved. Implement it now.


## Response

I'll start by opening the plans sidecar repo through the required skill to locate the migration plan file.

This is a substantial, detailed plan. Let me first read the parent epic plan sections it references, since they're marked as requirements.

Good, it's not a git repo — it's the live local plans directory, not a separate repo requiring `/sase_repo`. Let me read the epic overview plan for the required sections.

Good, back in the main workspace. Given the scope, I'll delegate broad codebase exploration to research agents in parallel to gather the exact APIs I need before writing code.

All target files exist. Let me read them.

I've launched three research agents in parallel to gather the exact current-state APIs I need (feature flags/gate_shell followup hooks, the questions execution flow, and the gate-shell spec/creation/test patterns). I'll wait for those to land before writing code.

Good, the CLI works from this workspace. Let me run `just install` preemptively since this workspace may be stale (per CLAUDE.md guidance), while the research agents work.

Now let's read the transaction.py file for `create_gate_shell`, the two `update_meta_fields` definitions, `list_gate_shells`, `user_question_actions.py`, and `test_settlement_followup.py`.

Good, this confirms enough for the report. I now have all the material needed.

Now I have complete, verified facts for all eight items. Here is the full report.

## 1. `src/sase/feature_flags/registry.py` — `FeatureFlag` enum + `FeatureFlagDefinition` entries

Full file is 114 lines. Header/imports (lines 1–29):

```python
1  """Code-owned SASE feature flag registry.
2
3  Definition authors must follow two rules:
4
5  - ``remove_by`` never appears here; it lives on the flag bead.
6  - Definitions are added only through ``sase flag new``, never by hand.
7
8  ``default`` is derived from ``kind`` (``FeatureFlagDefinition.default``) and is never
9  passed explicitly: a ``beta`` flag defaults off, a ``sunset`` flag defaults on.
10 """
11
12 from __future__ import annotations
13
14 from collections.abc import Mapping
15 from enum import StrEnum
16 from types import MappingProxyType
17
18 from sase.feature_flags.models import FeatureFlagDefinition, FeatureFlagError
19
20
21 class FeatureFlag(StrEnum):
22     """Every SASE feature flag key. Add members through ``sase flag new``."""
23
24     admin_center_flags = "admin_center_flags"
25     link_pager = "link_pager"
26     link_rail = "link_rail"
27     provider_drain = "provider_drain"
28     ref_sync_gesture = "ref_sync_gesture"
29     typed_launch_units = "typed_launch_units"
```

Two representative `beta`-kind entries (the `link_pager` beta gate and `typed_launch_units` beta gate), lines 42–50 and 83–88:

```python
42     FeatureFlag.link_pager: FeatureFlagDefinition(
43         key=FeatureFlag.link_pager,
44         kind="beta",
45         description=(
46             "Beta gate for the link-traversing SasePager surface, its "
47             "jump-hint keys, and its navigation trail."
48         ),
49         bead="sase-ul",
50     ),
```

```python
83     FeatureFlag.typed_launch_units: FeatureFlagDefinition(
84         key=FeatureFlag.typed_launch_units,
85         kind="beta",
86         description="Beta gate for typed launch units, %if, and %proc.",
87         bead="sase-s7",
88     ),
```

Trailer (lines 91–114) — the exported mapping and self-validation, run at import time:

```python
91  FEATURE_FLAG_DEFINITIONS: Mapping[FeatureFlag, FeatureFlagDefinition] = (
92      MappingProxyType(_FEATURE_FLAG_DEFINITIONS)
93  )
94
95
96  def _validate_registry() -> None:
97      """Fail fast if a hand-edited registry entry is inconsistent."""
98      for key, definition in FEATURE_FLAG_DEFINITIONS.items():
99          if definition.key != key:
100             raise FeatureFlagError(
101                 f"feature flag definition key {definition.key!r} "
102                 f"does not match registry key {key!r}"
103             )
104         definition.validate()
105
106
107 def feature_flag_definitions() -> Mapping[str, FeatureFlagDefinition]:
108     """Return registry definitions keyed by their string flag key."""
109     return MappingProxyType(
110         {str(key): definition for key, definition in FEATURE_FLAG_DEFINITIONS.items()}
111     )
112
113
114 _validate_registry()
```

Note: the file's own docstring explicitly says "Definitions are added only through `sase flag new`, never by hand" — worth flagging to whoever is implementing the plan, since it implies there's a generator CLI command (`sase flag new`) rather than hand-editing this file. I did not locate/inspect that CLI command since it wasn't asked for, but it's the sanctioned path per the file's own comment.

For full context, the `FeatureFlagDefinition` dataclass (in `src/sase/feature_flags/models.py`, lines 44–66):

```python
44  @dataclass(frozen=True)
45  class FeatureFlagDefinition:
46      """A single code-owned feature flag definition."""
47
48      key: FeatureFlag
49      kind: FlagKind
50      description: str
51      bead: str | None = None
52
53      @property
54      def default(self) -> bool:
55          """Return the kind-derived default: a sunset flag defaults on."""
56          return self.kind == "sunset"
57
58      def validate(self) -> None:
59          """Validate registry invariants for this definition."""
60          key = str(self.key)
61          if not is_feature_flag_key(key):
62              raise FeatureFlagError(f"feature flag key must be snake_case: {key!r}")
63          if self.bead is None:
64              raise FeatureFlagError(
65                  f"{self.kind} feature flag {key!r} must reference its flag bead"
66              )
```

`FlagKind = Literal["beta", "sunset"]` (models.py line 15). So a new `gate_shell_handoff` beta flag must use `kind="beta"` and a real `bead=` value (validate() raises if `bead` is `None`).

## 2. `src/sase/pager/flag.py` — full contents (11 lines)

```python
1  """Feature-flag gate for the link-traversing pager surface."""
2
3  from __future__ import annotations
4
5  from sase.feature_flags.registry import FeatureFlag
6  from sase.feature_flags.snapshot import current_flags
7
8  def link_pager_enabled() -> bool:
9      """Return the process-local `link_pager` flag decision."""
10     return current_flags().enabled(FeatureFlag.link_pager)
```

(Line numbering: blank line 4 and 7 collapsed visually above but present in file — confirmed via `cat -n`, the file is exactly this content, 11 lines total.) This is the exact minimal pattern to mimic for a `gate_shell_handoff_enabled()` helper.

## 3. `src/sase/config/sase.schema.json` — generated-file confirmation + flag shape

There is **no in-file "generated, do not edit" comment** — JSON (draft-07 schema) doesn't support comments, so the file itself carries no such header. The "generated" designation instead lives in the surrounding tooling:

- `tools/sync_feature_flags_schema` docstring (line 2): `"""Check or rewrite the generated feature_flags config schema block."""`
- `src/sase/feature_flags/schema.py` marks the two functions that own this block with `# symvision: tools/sync_feature_flags_schema` tags (lines 12 and 44), and `feature_flags_schema_block()`'s docstring says `"""Return the generated ``feature_flags`` JSON Schema block."""` (line 15).
- `tools/check_feature_flags` enforces it as rule 2 in its docstring: `"the generated ``feature_flags`` schema block matches the registry"`.

The JSON shape for a beta flag (`link_pager`, lines 3887–3891):

```json
3887          "link_pager": {
3888            "type": "boolean",
3889            "description": "Beta gate for the link-traversing SasePager surface, its jump-hint keys, and its navigation trail.",
3890            "default": false
3891          },
```

Compare a `sunset` flag, which gets `"deprecated": true` added (line 3884, `admin_center_flags`):

```json
3881          "admin_center_flags": {
3882            "type": "boolean",
3883            "description": "The Config catalog exposes the Flags pane for persistent feature-flag control.",
3884            "default": true,
3885            "deprecated": true
3886          },
```

This exactly matches `feature_flags_schema_block()` in `src/sase/feature_flags/schema.py` (lines 14–36), which builds `{"type": "boolean", "description": ..., "default": definition.default}` and adds `"deprecated": True` only when `definition.kind == "sunset"`. New flags must **not** be hand-added to this JSON file — run `tools/sync_feature_flags_schema --write` after adding the registry entry.

## 4. `tools/sync_feature_flags_schema` and `tools/check_feature_flags`

**`tools/sync_feature_flags_schema`** (133 lines total). Docstring: `"""Check or rewrite the generated feature_flags config schema block."""`. It loads `src/sase/config/sase.schema.json`, and either (a) with `--check`, default mode: calls `feature_flags_schema_drift(document)` and exits 1 printing the drift plus a hint to run with `--write` if any is found (lines 111–121); or (b) with `--write`: calls `_write_schema(document)`, which rewrites the `feature_flags` property in place using a hand-rolled JSON-slice `_upsert_top_level_property_text` splice (not a full-file `json.dump`, to preserve formatting/ordering of the rest of the file), lines 29–45 and 76–93.

**`tools/check_feature_flags`** (1000 lines). Docstring (lines 1–24) states it enforces registry/bead integrity via 9 static + bead-status rules:
```
1  """Enforce feature-flag registry and flag-bead integrity.
...
1. every definition names its flag bead
2. the generated ``feature_flags`` schema block matches the registry
3. every registered key has at least one non-test reference
4. no flag is resolved at module import time
5. no repo-managed config layer overrides an unregistered ``feature_flags`` key
...
6. the named bead exists, is a ``flag`` task bead (or a legacy flag issue-type bead), and its key (and kind, when present) match
7. a closed flag bead whose definition survives is an error
8. a live flag bead with no definition is an error, unless the bead is newer than this checkout (or still inside the landing grace)...
9. an overdue flag is a warning, never an error
"""
```
Key functions: `check_definition_metadata`, `check_schema`, `check_references` (AST-walks `src/` for at least one non-test reference to each flag key — this is why `link_pager` needing a real `flag.py` consumer module matters), `check_import_time` (walks for `_is_import_time_resolution_calls` to forbid flags resolved at module import time — i.e., `current_flags().enabled(...)` must be called inside a function body, not at module scope, matching the pattern in `pager/flag.py`), `check_repo_config`, and `check_bead_status` (talks to the bead store via `BD_COMMAND`/`resolve_bd_command`).

## 5. `src/sase/gate_shell/__init__.py` — full contents (94 lines)

Already the full file was captured above in the tool output; reproducing verbatim:

```python
1  """Gate shells: processless family members that own pending gate decisions."""
2
3  from typing import Any
4
5  from sase.gate_shell.models import (
6      GateShellError,
7      GateShellLaneError,
8      GateShellRecord,
9      GateShellRefError,
10     GateShellState,
11     is_gate_shell_member_record,
12 )
13 from sase.gate_shell.naming import (
14     SHORT_GATE_ID_LENGTH,
15     allocate_gate_suffix,
16     new_gate_shell_id,
17     short_gate_shell_id,
18 )
19
20 _LAZY_EXPORTS: dict[str, tuple[str, str]] = {
21     "GATE_PENDING_MARKER": ("sase.gate_shell.handoff", "GATE_PENDING_MARKER"),
22     "GateShellCreation": ("sase.gate_shell.transaction", "GateShellCreation"),
23     "MIN_GATE_SHELL_REF_LENGTH": (
24         "sase.gate_shell.store",
25         "MIN_GATE_SHELL_REF_LENGTH",
26     ),
27     "cancel_gate_shell": ("sase.gate_shell.cancel", "cancel_gate_shell"),
28     "create_gate_shell": ("sase.gate_shell.transaction", "create_gate_shell"),
29     "find_gate_shell_by_gate_id": (
30         "sase.gate_shell.store",
31         "find_gate_shell_by_gate_id",
32     ),
33     "has_any_gate_shell": ("sase.gate_shell.store", "has_any_gate_shell"),
34     "list_gate_shells": ("sase.gate_shell.store", "list_gate_shells"),
35     "maybe_handoff_gate_from_agent": (
36         "sase.gate_shell.handoff",
37         "maybe_handoff_gate_from_agent",
38     ),
39     "read_gate_shell_marker": ("sase.gate_shell.store", "read_gate_shell_marker"),
40     "resolve_gate_shell_ref": ("sase.gate_shell.store", "resolve_gate_shell_ref"),
41     "settle_gate_shell": ("sase.gate_shell.settlement", "settle_gate_shell"),
42     "will_handoff_gate_to_agent_runner": (
43         "sase.gate_shell.handoff",
44         "will_handoff_gate_to_agent_runner",
45     ),
46 }
47
48
49 def __getattr__(name: str) -> Any:
50     """Lazily load lifecycle helpers that pull in runner dependencies."""
51     target = _LAZY_EXPORTS.get(name)
52     if target is None:
53         raise AttributeError(name)
54     module_name, attribute = target
55     from importlib import import_module
56
57     value = getattr(import_module(module_name), attribute)
58     globals()[name] = value
59     return value
60
61
62 def __dir__() -> list[str]:
63     return sorted({*globals(), *__all__})
64
65
66 # PEP 562 entry points are called by Python, not by normal in-file code.
67 _PEP562_HOOKS = (__getattr__, __dir__)
68
69
70 __all__ = [
71     "GATE_PENDING_MARKER",
72     "MIN_GATE_SHELL_REF_LENGTH",
73     "SHORT_GATE_ID_LENGTH",
74     "GateShellCreation",
75     "GateShellError",
76     "GateShellLaneError",
77     "GateShellRecord",
78     "GateShellRefError",
79     "GateShellState",
80     "allocate_gate_suffix",
81     "cancel_gate_shell",
82     "create_gate_shell",
83     "find_gate_shell_by_gate_id",
84     "has_any_gate_shell",
85     "is_gate_shell_member_record",
86     "list_gate_shells",
87     "maybe_handoff_gate_from_agent",
88     "new_gate_shell_id",
89     "read_gate_shell_marker",
90     "resolve_gate_shell_ref",
91     "settle_gate_shell",
92     "short_gate_shell_id",
93     "will_handoff_gate_to_agent_runner",
94 ]
```

This confirms `create_gate_shell` and `GateShellCreation` are **not** defined here directly — they are lazily re-exported from `sase.gate_shell.transaction` (see item 7).

Important: there is a shared, generic version of this exact PEP-562 lazy-facade helper already factored out at `src/sase/_lazy_exports.py` (`lazy_getattr` / `lazy_dir`), but `gate_shell/__init__.py` and `shells/__init__.py` both currently hand-roll their own `__getattr__`/`__dir__` rather than calling into `_lazy_exports.py`. If you add a new lazy export for a hook registry facade, note this inconsistency — you may want to either match the existing hand-rolled style (for consistency with this file) or adopt `_lazy_exports.lazy_getattr`/`lazy_dir` (which is the more DRY, code-owned shared helper). Neither of the two `__init__.py` lazy facades is defensive against import failure — an import error propagates as a normal exception, it isn't caught/logged.

## 6. `src/sase/gate_shell/followup.py` — relevant sections

Full file is 353 lines (already displayed above in full). Key pieces for wiring in a hook call:

`_base_prompt_kwargs` (lines 192–242) — this is where `"next_action": policy.prompt` is set, at the very end of the returned dict:

```python
192 def _base_prompt_kwargs(
193     artifacts_dir: str,
194     meta: dict[str, Any],
195     *,
196     gate_state: GateShellState,
197     policy: GateFollowupPolicy,
198     envelope: dict[str, Any],
199     response: dict[str, Any],
200     reason: str | None,
201 ) -> dict[str, Any]:
202     answered = gate_state in ("answered", "completed")
203     options = _option_outcomes(envelope, response) if answered else ()
204     outcome_line = format_gate_outcome_line(
205         gate_state=gate_state,
206         selected_labels=tuple(option.label for option in options),
207         gate_timeout_seconds=float(envelope.get("gate_timeout_seconds") or 0.0),
208         reason=reason,
209     )
210     gate_log_path = (
211         str(Path(artifacts_dir) / GATE_SHELL_LOG_FILENAME)
212         if "file" in policy.output
213         else None
214     )
215     feedback = response.get("feedback")
216     from sase.gate_shell.settlement import gate_decision_title
217
218     return {
219         "model": _clean_str(meta.get("model")),
220         "reasoning_effort": _clean_str(meta.get("reasoning_effort")),
221         "next_model": policy.model,
222         "answered": answered,
223         "title": gate_decision_title(envelope, meta),
224         "gate_ref": f"{meta.get('gate_kind') or ''}/{meta.get('gate_id') or ''}",
225         "outcome_line": outcome_line,
226         "answered_via": (
227             str(response["source"]) if answered and response.get("source") else None
228         ),
229         "opened_at": _format_unix(envelope.get("created_at_unix")),
230         "answered_at": (
231             _format_unix(response.get("responded_at_unix")) if answered else None
232         ),
233         "options": options,
234         "reviewer_note": str(feedback) if feedback else None,
235         "output": policy.output,
236         "output_text": (
237             gate_shell_output_tail(artifacts_dir) if "tail" in policy.output else ""
238         ),
239         "tail_lines": 200,
240         "gate_log_path": gate_log_path,
241         "next_action": policy.prompt,
242     }
```

`launch_gate_followup_agent` (lines 46–157) calls `_base_prompt_kwargs` at line 82 to build `base_kwargs`, then a nested `_compose` closure (lines 92–97) feeds `**base_kwargs` (including `next_action`) into `compose_gate_followup_prompt` (imported from `sase.gate_shell.followup_prompt`, line 12–16). The dict is threaded through unmodified from `_base_prompt_kwargs` to the prompt composer — this is the natural seam to intercept and append/override `next_action` from a settle-time hook registry (e.g., right after line 90, before `_compose` is defined, or by post-processing `base_kwargs["next_action"]` before it's captured by the closure).

`build_suppressed_gate_followup_prompt` (lines 160–189) is the parallel path for the case where the agent is *not* launched (its prompt is only stashed as an artifact) — it also calls `_base_prompt_kwargs` (line 178) and passes `**base_kwargs` into `compose_gate_followup_prompt` (line 187-188) with `fork_target=None`. Any hook wiring at `_base_prompt_kwargs` covers both launch paths for free since both call it.

Consumer of `"## Your next action"`, in `src/sase/gate_shell/followup_prompt.py` line 89 (parameter) and line 144: `sections.extend(["## Your next action", "", next_action])`.

## 7. `create_gate_shell` / `GateShellCreation` — actually live in `src/sase/gate_shell/transaction.py`

There is **no `src/sase/gate_shell/create.py`** — that file doesn't exist. The closest/actual location is `src/sase/gate_shell/transaction.py` (378 lines). Confirmed via directory listing:
```
src/sase/gate_shell/handoff.py, start_claim.py, __init__.py, models.py, settlement.py, followup.py,
state.py, naming.py, transaction.py, store.py, member.py, claims.py, reclaim.py, followup_prompt.py,
log.py, followup_policy.py, cancel.py, status.py, projection.py
```

`GateShellCreation` dataclass (lines 41–66):

```python
41 @dataclass(frozen=True)
42 class GateShellCreation:
43     """Result of creating a gate shell and its gate."""
44
45     gate: GateCreationResult
46     record: GateShellRecord
47     project_file: str | None
48     claim_move: GateClaimMove | None
49     cl_name: str | None
50
51     @property
52     def should_handoff(self) -> bool:
53         """Return whether the creator should hand off to the gate shell."""
54         return not self.record.is_terminal
55
56     def to_dict(self) -> dict[str, Any]:
57         """Return the CLI descriptor with additive gate-shell metadata."""
58         payload = self.gate.to_dict()
59         payload["gate_shell"] = {
60             "gate_id": self.record.gate_id,
61             "member_agent_name": self.record.member_agent_name,
62             "artifacts_dir": self.record.artifacts_dir,
63             "state": self.record.gate_state,
64             "workspace_policy": self.record.workspace_policy,
65         }
66         return payload
```

`create_gate_shell` signature (line 83):

```python
83 def create_gate_shell(request: Mapping[str, Any] | GateSpec) -> GateShellCreation:
84     """Create a gate-shell member, then create the durable gate."""
```

It's a single-argument function taking either a raw mapping or a `GateSpec` (from `sase.notification_gates.model_request`), returning `GateShellCreation`. Both `create_gate_shell` and `GateShellCreation` are re-exported lazily via `gate_shell/__init__.py`'s `_LAZY_EXPORTS` dict (item 5, lines 22 and 28), pointing at `"sase.gate_shell.transaction"`.

## 8. Precedent for a "kind-keyed lazy registry resolved via `importlib.import_module`, defensive against import failure, logged at warning with `exc_info=True`"

I searched `src/sase/gate_shell/`, `src/sase/shells/`, `src/sase/monitor/`, and the rest of `src/sase/` for `importlib.import_module`/`import_module` usage combined with defensive exception handling. **No single existing precedent combines all three properties you described** (kind-keyed dict → module/function tuple → `importlib.import_module` → defensive try/except → `log.warning(..., exc_info=True)`). The closest partial precedents, each missing one property, are:

**(a) Kind-keyed `dict[str, tuple[str, str]]` resolved via `import_module`, but NOT defensive (no try/except, no logging)** — this is the dominant lazy-facade pattern in this repo, used identically in three places:
- `src/sase/gate_shell/__init__.py` lines 20–59 (shown in full above, item 5) — `_LAZY_EXPORTS: dict[str, tuple[str, str]]`, resolved in `__getattr__` via `from importlib import import_module; value = getattr(import_module(module_name), attribute)`. A raw `AttributeError`/`ImportError` propagates uncaught.
- `src/sase/shells/__init__.py` lines 8–61 — `_MODULE_BY_EXPORT: dict[str, str]` (module name only, not full dotted path — it's joined via `f"{__name__}.{module_name}"`), same `__getattr__`/`__dir__` shape, also non-defensive:
  ```python
  54 def __getattr__(name: str) -> Any:
  55     """Load substrate exports lazily to keep light modules cheap to import."""
  56     module_name = _MODULE_BY_EXPORT.get(name)
  57     if module_name is None:
  58         raise AttributeError(f"module {__name__!r} has no attribute {name!r}")
  59     value = getattr(import_module(f"{__name__}.{module_name}"), name)
  60     globals()[name] = value
  61     return value
  ```
- `src/sase/_lazy_exports.py` (32 lines total) — the shared, generic, code-owned version of the same pattern factored into `lazy_getattr`/`lazy_dir` helpers, but currently **unused** by either `gate_shell/__init__.py` or `shells/__init__.py` (both hand-roll their own copy instead of calling into this shared helper):
  ```python
  1  """PEP 562 helpers for package-level lazy re-exports."""
  ...
  9  LazyExportMap = Mapping[str, tuple[str, str]]
  10
  11
  12 def lazy_getattr(
  13     package_name: str,
  14     module_globals: dict[str, Any],
  15     exports: LazyExportMap,
  16     name: str,
  17 ) -> Any:
  18     """Resolve and cache one package-level lazy export."""
  19     target = exports.get(name)
  20     if target is None:
  21         raise AttributeError(f"module {package_name!r} has no attribute {name!r}")
  22     module_name, attr_name = target
  23     value = getattr(import_module(module_name), attr_name)
  24     module_globals[name] = value
  25     return value
  ```
  Also non-defensive — no try/except around the import.

**(b) Defensive import + `log.warning(..., exc_info=True)`, but not kind-keyed / not `importlib`-based** — `src/sase/file_hooks/producer.py` and `src/sase/file_hooks/dispatch.py` establish the "never raises, log at warning with `exc_info=True`, continue" convention used throughout the codebase for best-effort side-channel work (file hooks, closely analogous in spirit to a settle-time hook):
```python
# src/sase/file_hooks/dispatch.py, line 259-260
except Exception as exc:
    logger.warning("File-hook dispatch failed; continuing", exc_info=True)
```
```python
# src/sase/file_hooks/producer.py, lines 68-69, 94-95, 113-114, 150-151 (repeated 4x)
except Exception as exc:
    logger.warning("File-hook config load failed; continuing", exc_info=True)
```
These don't use `importlib.import_module` at all — they call statically-imported functions (`load_file_hooks()`, `capture_artifact_file_event()`) wrapped in try/except, not a kind→module-path lookup table.

**(c) Defensive `importlib.import_module`, but logged at `debug` (not `warning`), and not kind-keyed** — `src/sase/axe/source_skew.py` lines 150–156:
```python
150 def _import_best_effort(module_name: str) -> bool:
151     """Import *module_name*, swallowing any failure. Returns success."""
152     try:
153         importlib.import_module(module_name)
154     except Exception as exc:  # noqa: BLE001 - one bad module must not fail a run
155         logger.debug("Import preload skipped %s: %s", module_name, exc)
156         return False
157     return True
```
This is used for best-effort module preloading (`_PRELOAD_PACKAGES = ("sase.sdd", "sase.bead")`, walked via `pkgutil`), not for kind-dispatched hook resolution, and deliberately logs at `debug` (with a formatted message, no `exc_info=True`) rather than `warning`.

**Conclusion for your plan:** there is no existing "kind-keyed lazy registry, defensive, `log.warning(exc_info=True)` on failure" module to copy wholesale. To build the new settle-time "next action" hook registry, the most faithful synthesis of existing repo conventions would be: reuse the `dict[str, tuple[str, str]]` shape and `importlib.import_module` resolution style from `gate_shell/__init__.py` / `shells/__init__.py` / `_lazy_exports.py` (item a), but wrap the resolution+call in a try/except that logs via `logger.warning("<message>; continuing", exc_info=True)` in the style of `file_hooks/producer.py`/`dispatch.py` (item b) rather than `source_skew.py`'s `debug`-level swallow (item c), since `warning`+`exc_info=True` is the established severity for "something in an optional/best-effort subsystem broke but the main flow must continue."

I now have everything needed to answer all 8 items with verbatim, line-numbered evidence. Here is the full report.

## 1. `src/sase/notification_gates/model_shell.py` (341 lines, quoted in full above already read) — key structures

File: `/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/src/sase/notification_gates/model_shell.py`

Constants/defaults (lines 17–41):
```
17	DEFAULT_GATE_SHELL_PENDING_STATUS = "GATE"
18	DEFAULT_GATE_SHELL_SETTLED_STATUS = "GATED"
19	GATE_SHELL_DEFAULT_TIMEOUT_SECONDS = 24 * 60 * 60.0
20	GATE_SHELL_STATUS_MAX_CHARS = 20
21	GATE_SHELL_STATUS_ELLIPSIS = "\u2026"
22	
23	GATE_SHELL_WORKSPACES = frozenset({"inherit", "release"})
24	GATE_SHELL_NEXT_FORKS = frozenset({"family", "shell", "none"})
25	GATE_SHELL_NEXT_OUTPUTS = frozenset({"none", "results", "tail", "file"})
26	GATE_SHELL_RESERVED_BRANCHES = frozenset({"timeout", "stopped", "failed"})
```
plus a 12-entry `_DEFAULT_ACCENTS` palette (lines 28–41).

`GateShellNext` (lines 44–84): frozen/slots dataclass with `prompt: str|None=None`, `output: tuple[str,...]=("results",)`, `fork: str="family"`, `model: str|None=None`; `from_mapping` rejects unknown fields against `{"prompt","output","fork","model"}`, validates `fork` is in `GATE_SHELL_NEXT_FORKS` (lines 69-74), and delegates output validation to `_next_output`.

`GateShellBranchSpec` (lines 90–140): frozen/slots dataclass `status`, `accent`, plus the same 4 `next` fields flattened. `from_mapping` (109-130) rejects unknown keys against `{"status","accent",*_BRANCH_NEXT_FIELDS}`, builds a `GateShellNext` inheriting from the top-level `inherited_next`, and separately validates `status` via `_optional_status` and `accent` via `validate_color`.

`GateShellSpec` (frozen dataclass, lines 143–224):
```
147	    suffix: str | None = None
148	    pending_status: str = DEFAULT_GATE_SHELL_PENDING_STATUS
149	    settled_status: str = DEFAULT_GATE_SHELL_SETTLED_STATUS
150	    accent: str = field(default_factory=lambda: _default_accent("GATE\x1fGATED"))
151	    workspace: str = "inherit"
152	    next: GateShellNext = field(default_factory=GateShellNext)
153	    branches: dict[str, GateShellBranchSpec] = field(default_factory=dict)
```
`from_mapping` (155–208) takes `value: object, *, branches: tuple[tuple[str,...],...]` (the caller's compiled outcome-branch tuples, e.g. `(("cleanup",), ("reject",))` seen in the test fixture). It:
- rejects unknown top-level keys against `{"suffix","pending_status","settled_status","accent","workspace","next","branches"}` (163–175)
- validates `pending_status`/`settled_status` via `_status` → `clamp_shell_status(..., max_chars=20, ellipsis="…", noun="gate shell status")` (176–183, 258–269)
- builds `next_policy` via `GateShellNext.from_mapping` (184)
- validates `workspace` is in `GATE_SHELL_WORKSPACES` else raises `GateError("invalid_shell","shell.workspace",...)` (185–191)
- validates `suffix` via `_suffix` — must be `None` or a string starting with `--`, canonicalized via `canonical_plan_chain_suffix`, else `GateError` (278–294)
- `accent` defaults via `_default_accent(f"{pending_status.upper()}\x1f{settled_status.upper()}")` when not explicitly given (192–195, 328–331, using `hash_palette_index`)
- `branches` validated via `_branches`/`_valid_branch_keys`, which requires each key to be one of the compiled branch keys (`"+".join(branch)`) or a reserved key (`timeout`, `stopped`, `failed`) (227–255)

`to_dict()` on both `GateShellSpec` and its nested types serialize back to plain dicts (210–224, 78–84, 132–140).

## 2. `create_gate_shell` and `GateShellCreation` — `src/sase/gate_shell/transaction.py`

`GateShellCreation` (lines 41–66):
```python
41	@dataclass(frozen=True)
42	class GateShellCreation:
43	    """Result of creating a gate shell and its gate."""
44	
45	    gate: GateCreationResult
46	    record: GateShellRecord
47	    project_file: str | None
48	    claim_move: GateClaimMove | None
49	    cl_name: str | None
50	
51	    @property
52	    def should_handoff(self) -> bool:
53	        """Return whether the creator should hand off to the gate shell."""
54	        return not self.record.is_terminal
55	
56	    def to_dict(self) -> dict[str, Any]:
57	        """Return the CLI descriptor with additive gate-shell metadata."""
58	        payload = self.gate.to_dict()
59	        payload["gate_shell"] = {
60	            "gate_id": self.record.gate_id,
61	            "member_agent_name": self.record.member_agent_name,
62	            "artifacts_dir": self.record.artifacts_dir,
63	            "state": self.record.gate_state,
64	            "workspace_policy": self.record.workspace_policy,
65	        }
66	        return payload
```

`create_gate_shell` signature (line 83): `def create_gate_shell(request: Mapping[str, Any] | GateSpec) -> GateShellCreation:`. Full body is lines 83–195 (quoted above in the tool output) — key flow: builds `GateSpec` via `_spec_from_request`, resolves project/creator context, takes a per-lane lock, checks for an idempotent replay via `find_gate_shell_by_gate_id`, allocates a suffix via `naming.allocate_gate_suffix`, creates the member via `create_gate_shell_member(...)`, moves the workspace claim, calls `create_gate(spec)`, and on success/failure settles or records the result — auto-resolving (settling as `"answered"`) when `gate_result.auto_resolution.get("state") == "resolved"`.

`update_meta_fields` usage in this file (two call sites):
```python
316	def _record_with_gate_result(
317	    project_name: str,
318	    record: GateShellRecord,
319	    result: GateCreationResult,
320	) -> GateShellRecord:
321	    update_meta_fields(
322	        record.artifacts_dir,
323	        {
324	            "gate_bundle_path": str(result.bundle_path),
325	            "gate_notification_id": result.notification_id,
326	            "gate_request_fingerprint": result.hashes.get("request"),
327	        },
328	    )
329	    return read_gate_shell_marker(project_name, record.artifacts_dir) or record


332	def _record_creator_claim(artifacts_dir: str, move: GateClaimMove) -> None:
333	    claim = move.creator_claim
334	    if claim is None:
335	        return
336	    update_meta_fields(
337	        artifacts_dir,
338	        {
339	            "gate_creator_claim_pid": claim.pid,
340	            "gate_creator_claim_workflow": claim.workflow,
341	            "gate_creator_claim_artifacts_timestamp": claim.artifacts_timestamp,
342	            "gate_creator_claim_pinned": claim.pinned,
343	        },
344	    )
```
Import: `from sase.axe.run_agent_helpers_artifacts import update_meta_fields` (line 14). Pattern is: mutate a plain `dict[str, Any]` of arbitrary keys, call `update_meta_fields(artifacts_dir, {...})`, then optionally re-read via `read_gate_shell_marker` to get the refreshed typed record. This is exactly the mechanism to use to write `question_round_index` onto a member's `agent_meta.json`.

## 3. `update_meta_fields` — definition + call sites

**Canonical definition** — `/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/src/sase/axe/run_agent_helpers_artifacts.py:64-81`:
```python
64	def update_meta_fields(
65	    artifacts_dir: str,
66	    fields: dict[str, Any],
67	    *,
68	    remove_keys: Sequence[str] = (),
69	) -> None:
70	    """Read agent_meta.json, set/remove multiple keys, and write back once."""
71	    if not fields and not remove_keys:
72	        return
73	    meta_path = os.path.join(artifacts_dir, "agent_meta.json")
74	    try:
75	        with open(meta_path, encoding="utf-8") as f:
76	            meta = json.load(f)
77	        for key in remove_keys:
78	            meta.pop(key, None)
78	        meta.update(fields)
80	        write_agent_meta_atomic(
81	            artifacts_dir,
82	            meta,
83	            index_updater=update_agent_artifact_index_for_marker_mutation,
84	        )
85	    except (FileNotFoundError, json.JSONDecodeError, OSError):
86	        pass
```
(Note: it silently no-ops on read errors — no exception propagates.)

**Facade re-export** — `/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/src/sase/axe/run_agent_helpers.py:101-108` — the compatibility facade module that most call sites actually import from:
```python
101	def update_meta_fields(
102	    artifacts_dir: str,
103	    fields: dict[str, Any],
104	    *,
105	    remove_keys: Sequence[str] = (),
106	) -> None:
107	    _sync_patchable_dependencies()
108	    _artifacts.update_meta_fields(artifacts_dir, fields, remove_keys=remove_keys)
```
There is also a single-key sibling `update_meta_field(artifacts_dir, key, value)` (lines 47-58 in `run_agent_helpers_artifacts.py`), used repeatedly in the test fixture (item 6).

**Call sites:**
1. `sase/gate_shell/transaction.py:321-328` and `:336-344` (shown above, item 2) — writing gate bookkeeping fields (`gate_bundle_path`, `gate_notification_id`, `gate_request_fingerprint`, `gate_creator_claim_*`) after member creation.
2. `sase/xprompt/workflow_executor_steps_prompt.py:143`:
```python
141	    redeemed = dict(reservation)
142	    redeemed["redeemed"] = True
143	    update_meta_fields(artifacts_dir, {"model_alias_reservation": redeemed})
```
3. `sase/xprompt/workflow_executor_steps_prompt.py:392-396`:
```python
392	            update_meta_fields(
393	                self.artifacts_dir,
394	                root_meta_fields,
395	                remove_keys=() if step_model_alias_trail else ("model_alias_trail",),
396	            )
```
where `root_meta_fields` is a plain dict of arbitrary custom keys (`model`, `llm_provider`, `model_alias_origin`, optionally `model_alias`, `model_alias_trail`, `reasoning_effort`).

For a new non-wire key like `question_round_index`, the idiomatic call is simply `update_meta_fields(artifacts_dir, {"question_round_index": n})` (or `update_meta_field(artifacts_dir, "question_round_index", n)` for a single key), imported from `sase.axe.run_agent_helpers_artifacts` (as `gate_shell/transaction.py` does) or from the `sase.axe.run_agent_helpers` facade (as tests do). Note this key will not appear as a typed attribute on `AgentMetaWire`/`GateShellRecord` unless you also add it there — `read_gate_shell_marker`/`list_gate_shells` only project fields declared on `AgentMetaWire` (see item 4), so an ad hoc key like `question_round_index` is readable straight off disk (`agent_meta.json`) but won't show up on `GateShellRecord` unless the wire/model classes are extended.

## 4. `list_gate_shells` — definition, return type, call site

Definition — `/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/src/sase/gate_shell/store.py:65-78`:
```python
65	def list_gate_shells(*, project: str | None = None) -> list[GateShellRecord]:
66	    """Return every gate-shell record, newest first."""
67	    records = [
68	        converted
69	        for converted in (
70	            _gate_record_from_wire(record) for record in _gate_records(project)
71	        )
72	        if converted is not None
73	    ]
74	    records.sort(
75	        key=lambda record: (record.timestamp, record.artifacts_dir),
76	        reverse=True,
77	    )
78	    return records
```
It filters the project-wide artifact scan (`_gate_records` → `is_gate_shell_member_record`) and converts each `AgentArtifactRecordWire` via `GateShellRecord.from_record`.

**`GateShellRecord`** — `src/sase/gate_shell/models.py:42-73` (frozen dataclass):
```python
42	@dataclass(frozen=True)
43	class GateShellRecord:
44	    """Projection of one gate-shell family member."""
45	
46	    gate_id: str
47	    member_agent_name: str
48	    lane: str
49	    project_name: str
50	    artifacts_dir: str
51	    timestamp: str
52	    kind: str
53	    gate_state: GateShellState
54	    start_status: str
55	    stop_status: str
56	    accent: str
57	    label: str
58	    reason: str
59	    creator_agent: str | None
60	    bundle_path: str | None
61	    notification_id: str | None
62	    timeout_seconds: float
63	    request_fingerprint: str | None
64	    workspace_policy: str
65	    next_action: str | None = None
66	    next_fork: str | None = None
67	    next_output: str | None = None
68	    next_model: str | None = None
69	    followup_agent: str | None = None
70	    followup_outcome: str | None = None
71	    followup_error: str | None = None
72	    followup_degraded_reason: str | None = None
73	    followup_prompt_path: str | None = None
```
Confirming the specific fields you asked about: `lane` (line 48) — sourced from `meta.agent_family` (line 98: `lane=meta.agent_family or ""`); `timestamp` (line 51) — sourced from `record.timestamp` (the artifact directory's timestamp basename); `kind` (line 52, called `gate_kind` on the meta wire) — `kind=meta.gate_kind or ""` (line 102); there is no field literally named `gate_kind` on the record, it's exposed as `.kind`; `followup_agent` (line 69) — `followup_agent=meta.gate_followup_agent` (line 119), i.e. on disk the meta key is `gate_followup_agent`; `artifacts_dir` (line 50) — `artifacts_dir=record.artifact_dir` (line 100).

`from_record` (lines 85-124) raises `ValueError` if `meta is None or not meta.gate_id`, which is how `list_gate_shells` silently filters non-gate members.

**Call site** — `src/sase/main/gate_shell_handler.py:30-53`:
```python
30	def handle_gate_shell_list(args: argparse.Namespace) -> NoReturn:
31	    """Render gate shells as a table, markdown, or JSON."""
32	    project = getattr(args, "project", None)
33	    agent = getattr(args, "agent", None)
34	    states = set(getattr(args, "state", None) or ())
35	    include_all = bool(getattr(args, "all", False))
36	    limit = getattr(args, "limit", None)
37	    fmt = (
38	        "json"
39	        if bool(getattr(args, "json", False))
40	        else getattr(args, "format", "table")
41	    )
42	
43	    try:
44	        records = list_gate_shells(project=project)
45	    except Exception as exc:
46	        print(f"sase gate list: cannot read gate shells: {exc}", file=sys.stderr)
47	        sys.exit(1)
48	
49	    if agent:
50	        records = [record for record in records if record.lane == agent]
51	    if states:
52	        records = [record for record in records if record.gate_state in states]
53	    elif not include_all:
54	        records = [record for record in records if not record.is_terminal]
```
Other call sites: `gate_shell/reclaim.py:63`, `gate_shell/store.py:101` (self-recursive use inside `find_gate_shell_by_gate_id`), `notification_gates/cli_show.py:92`.

## 5. `create_user_question_gate` full body — `src/sase/user_question_actions.py:51-107`

```python
51	def create_user_question_gate(
52	    questions: list[dict[str, Any]],
53	    *,
54	    session_id: str,
55	    producer: Mapping[str, Any] | None = None,
56	    action_data: Mapping[str, str] | None = None,
57	    auto: bool = False,
58	) -> Any:
59	    """Create a neutral UserQuestion gate for the current agent continuation."""
60	    normalized_questions = validate_user_questions(questions)
61	    response_schema = question_response_schema(normalized_questions)
62	    summary = "; ".join(
63	        str(question.get("question") or "?") for question in normalized_questions[:3]
64	    )
65	
66	    from sase.notification_gates.service import create_gate
67	
68	    return create_gate(
69	        {
70	            "schema_version": 3,
71	            "kind": "question",
72	            "request_id": session_id,
73	            "producer": dict(producer or {}),
74	            "continuation_mode": QUESTION_CONTINUATION_MODE,
75	            "payload": {
76	                "questions": normalized_questions,
77	                "session_id": session_id,
78	                "timestamp": time.time(),
79	            },
80	            "presentation": {
81	                "notes": [summary] if summary else ["Agent is asking a question"],
82	                "tags": ["question"],
83	                "action_data": dict(action_data or {}),
84	            },
85	            "query": QUESTION_OPTION_ID,
86	            "primary_branch": [QUESTION_OPTION_ID],
87	            "options": [
88	                {
89	                    "id": QUESTION_OPTION_ID,
90	                    "label": "Submit answers",
91	                    "icon": "✅",
92	                    "command": {"argv": [QUESTION_COMMAND_PATH]},
93	                    "input_schema": response_schema,
94	                    "result_schema": response_schema,
95	                    "feedback": "optional",
96	                }
97	            ],
98	            "resources": [
99	                {
100	                    "path": QUESTION_COMMAND_PATH,
101	                    "role": "command",
102	                    "content": question_gate_command_script(),
103	                }
104	            ],
105	            "auto": auto,
106	        }
107	    )
```
Important facts for extracting a shared `user_question_gate_spec(...)` helper:
- It calls `create_gate(dict)` directly (not `create_gate_shell`) — there is **no `shell` key** in this dict today, meaning the current question gate is a plain v3 gate, not a gate-shell. To make it gate-shell-backed, you'd add a `"shell": {...}` block (validated by `GateShellSpec.from_mapping`, item 1) into this dict and switch the call from `create_gate` to `create_gate_shell` (from `sase.gate_shell.transaction` / `sase.gate_shell` package, item 2).
- `QUESTION_COMMAND_PATH = "commands/submit"`, `QUESTION_OPTION_ID = "submit"`, `QUESTION_CONTINUATION_MODE = "agent_question"` (lines 15-17).
- `normalized_questions` comes from `validate_user_questions(questions)` (line 60, defined 198-256) — validates each question has non-empty `question` text, an `options` list of objects each with a unique non-"Other" `label`, and a boolean `multiSelect`.
- `response_schema = question_response_schema(normalized_questions)` (line 61, defined 259-335) builds a JSON Schema requiring `answers` (array of per-question answer objects with `question`/`selected`/`custom_feedback`) and `global_note`.
- `producer`, `action_data` default to `{}` via `dict(producer or {})` / `dict(action_data or {})` (lines 73, 83) — these become the gate's `producer` and `presentation.action_data` fields respectively.
- `session_id` is reused as `request_id` (the gate's idempotency key, line 72) and again inside `payload.session_id` (line 77).
- The single `options` entry's `command.argv` points at the same `QUESTION_COMMAND_PATH` resource generated by `question_gate_command_script()` (line 102, defined 411-417), which is a Python shebang script invoking `execute_user_question_gate_command` — the adapter-approved command allowed to run when the option is selected.
- `auto` (default `False`) is passed straight through as the gate's `"auto"` field, driving `create_gate`'s auto-resolution behavior consumed later by `create_gate_shell`'s `gate_result.auto_resolution.get("state") == "resolved"` check (transaction.py:173).

Fields you'd need to extract into a shared spec builder: `schema_version`, `kind`, `request_id`, `producer`, `continuation_mode`, `payload` (questions/session_id/timestamp), `presentation` (notes/tags/action_data), `query`, `primary_branch`, `options` (with its `input_schema`/`result_schema` both set to the same `response_schema`), `resources` (command script), `auto`, and — new for gate-shell support — a `shell` block per `GateShellSpec.from_mapping`.

## 6. `tests/gate_shell/test_settlement_followup.py` — `_make_gate_shell_member` helper

Full helper — `/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/tests/gate_shell/test_settlement_followup.py:77-121`:
```python
77	def _make_gate_shell_member(
78	    request_id: str,
79	    bundle_path: Path,
80	    *,
81	    shell: dict[str, Any],
82	    workspace_num: int | None = None,
83	) -> str:
84	    """Build the gate-shell member from the *same* shell block as the bundle.
85	
86	    Settlement resolves follow-up policy from the durable bundle envelope
87	    (the single source of truth), never from the member's own metadata, so a
88	    test that wants a resolvable policy must give both the same shell block.
89	    """
90	    parsed_shell = GateShellSpec.from_mapping(
91	        shell, branches=(("cleanup",), ("reject",))
92	    )
93	    base_meta: dict[str, Any] = {
94	        "name": "lane--0",
95	        "agent_family": "lane",
96	        "model": "gpt-5",
97	    }
98	    if workspace_num is not None:
99	        base_meta["workspace_dir"] = "/work/lane"
100	    artifacts_dir = create_gate_shell_member(
101	        "proj",
102	        base_meta,
103	        lane="lane",
104	        suffix="--gate",
105	        prev_artifacts_timestamp="20260812120000",
106	        workspace_num=workspace_num,
107	        gate_id=request_id,
108	        gate_kind="custom",
109	        label="Reclaim disk space",
110	        reason="wait for reviewer",
111	        creator_agent="lane--0",
112	        timeout_seconds=86400.0,
113	        request_fingerprint=None,
114	        shell=parsed_shell,
115	    )
116	    from sase.axe.run_agent_helpers_artifacts import update_meta_field
117	
118	    update_meta_field(artifacts_dir, "gate_bundle_path", str(bundle_path))
119	    if workspace_num is not None:
120	        update_meta_field(artifacts_dir, "gate_workspace_policy", "inherit")
121	    return artifacts_dir
```
Companion `_spec` builder for the v3 gate dict (used to call `create_gate(...)` before/alongside the member) is lines 41-74 (quoted in full in the Read output above), and a `_DEFAULT_SHELL` dict constant at lines 34-38: `{"pending_status": "GATE", "settled_status": "GATED", "next": {"prompt": "Verify the cleanup landed."}}`.

Pattern for a "multi-round chain" test: each round would (1) build a `_spec(request_id, shell=...)`, (2) call `create_gate(spec)` to get `gate.bundle_path`, (3) call `_make_gate_shell_member(request_id, gate.bundle_path, shell=...)` to create the member artifacts dir matching that bundle, (4) resolve via `execute_gate_selection(gate.bundle_path, [branch_id], {}, source="test")`, (5) `read_gate_shell_marker("proj", artifacts_dir)` to get the record, (6) call `settle_gate_shell(record, gate_state=..., reason=...)`, monkeypatching `settlement_module.launch_gate_followup_agent` (module `sase.gate_shell.settlement`, imported as `settlement_module`) to fabricate the next round's member/agent as `_fake_launcher` does (lines 124-139), which sets `meta["gate_followup_agent"]` and persists it via `update_meta_field`. A new round's member creation would then need `prev_artifacts_timestamp` pointing at the prior round's timestamp and a fresh `gate_id`/`request_id`, mirroring this same `_make_gate_shell_member` call shape but for the question kind.

## 7. Sibling `*_shell` packages under `src/sase/`

Only **one** kind-specific `*_shell` package currently exists: `src/sase/gate_shell/`. There is no `plan_shell/`, `question_shell/`, or any other kind-specific package yet (confirmed via `find` — no matches for `plan_shell` or `question_shell` anywhere under `src/sase`).

`src/sase/gate_shell/` file listing:
```
__init__.py         handoff.py           start_claim.py
models.py           settlement.py        followup.py
state.py            naming.py            transaction.py
store.py            member.py            claims.py
reclaim.py          followup_prompt.py   log.py
followup_policy.py  cancel.py            status.py
projection.py
```
`__init__.py` (quoted in full above, item 4/8) is a lazy-loading facade: it eagerly imports lightweight pure-data symbols from `models.py` and `naming.py`, and lazily resolves heavier symbols (`GateShellCreation`, `create_gate_shell`, `cancel_gate_shell`, `settle_gate_shell`, handoff helpers, `list_gate_shells`, etc.) via a `_LAZY_EXPORTS` dict + module-level `__getattr__`/`__dir__` (PEP 562), to avoid pulling in runner dependencies at import time. This `gate_shell/` package is exactly the model to clone for `question_shell/`: a thin `__init__.py` facade, `models.py` for the frozen record/state types, `naming.py` for suffix/id allocation (delegating to `sase.shells.naming`), `member.py` for building the member's artifacts dir (delegating to `sase.shells.member.create_family_shell_member`), `transaction.py` for the `create_*_shell` orchestration + `*ShellCreation` dataclass, `store.py` for `list_*_shells`/`read_*_shell_marker`/`find_*_shell_by_*_id`, `settlement.py`/`start_claim.py`/`followup*.py`/`handoff.py`/`cancel.py`/`status.py`/`state.py`/`log.py`/`claims.py`/`reclaim.py`/`projection.py` for the rest of the lifecycle.

The generic, reusable substrate package (not itself a "kind" shell) is `src/sase/shells/` — see item 8.

## 8. `src/sase/shells/` package — files and key contents

File listing:
```
handoff.py    __init__.py    settlement.py    followup.py
state.py      naming.py      member.py        prompt.py
output.py     status.py
```
`__init__.py` (quoted in full above) is the same lazy `_MODULE_BY_EXPORT` + `__getattr__` pattern, re-exporting generic shell mechanics: followup/launch helpers (`followup.py`), handoff markers (`handoff.py`), `create_family_shell_member` (`member.py`), id/suffix allocation (`naming.py`), output capture (`output.py`), prompt routing prefix (`prompt.py`), settlement/claim finalization (`settlement.py`), terminal-state helpers (`state.py`), and status/accent/glyph helpers (`status.py`).

**`member.py`** (full contents quoted above, 68 lines) — single function `create_family_shell_member(project_name, base_meta, *, family, suffix, prev_artifacts_timestamp, workspace_num, shell_kind, family_role, metadata=None, inherited_metadata_fields=())  -> str`. It: builds `member_name = f"{family}{suffix}"`; calls `create_followup_artifacts(...)` (from `sase.axe.run_agent_helpers`) to allocate the new timestamped artifacts dir with `agent_name_override=member_name`, `workflow_name=family`, `agent_family_role=family_role`; reads back `agent_meta.json`; sets `meta["shell_kind"] = shell_kind`; copies any of `inherited_metadata_fields` from `base_meta` when non-empty/non-None (`_has_metadata_value`); merges the caller's `metadata` mapping on top; writes once via `write_agent_meta_atomic`. This is what `gate_shell/member.py::create_gate_shell_member` wraps (passing `shell_kind="gate"`, `family_role="gate"`, and a `gate_metadata` dict built from the `GateShellSpec`) — a `question_shell/member.py::create_question_shell_member` would follow the identical wrapper pattern with `shell_kind="question"` and its own metadata dict (e.g. including your new `question_round_index`).

**`naming.py`** (full contents quoted above, 62 lines) — generic building blocks: `ShellIdSpec` (alphabet/length/short_length), `SequenceSuffixSpec` (first_suffix/sequence_template), `new_shell_id(spec)` (random id via `secrets.choice`), `short_shell_id(shell_id, spec)` (prefix truncation), and:
```python
41	def allocate_shell_suffix(
42	    lane: str,
43	    *,
44	    has_existing_shell: bool,
45	    spec: SequenceSuffixSpec,
46	    allocator: SuffixAllocator | None = None,
47	) -> str:
48	    """Return the next free suffix for a sequential shell kind in *lane*."""
49	    if not has_existing_shell:
50	        return spec.first_suffix
51	    allocate = allocator or allocate_agent_family_child_suffix
52	    return allocate(lane, spec.sequence_template)
```
`gate_shell/naming.py::allocate_gate_suffix(lane, *, has_existing_gate)` (full contents quoted above) is a thin wrapper: it defines `_GATE_ID_ALPHABET`/`_GATE_ID_LENGTH`/`SHORT_GATE_ID_LENGTH`, a `_GATE_ID_SPEC`, and a `_GATE_SUFFIX_SPEC = SequenceSuffixSpec(first_suffix=PLAN_CHAIN_GATE_SUFFIX, sequence_template=f"{PLAN_CHAIN_GATE_SUFFIX}-@")`, then calls `allocate_shell_suffix(lane, has_existing_shell=has_existing_gate, spec=_GATE_SUFFIX_SPEC)`. A `question_shell/naming.py` would mirror this exactly with its own id alphabet/length constants and a `PLAN_CHAIN_QUESTION_SUFFIX`-equivalent (check `sase.plan_chain` for whether a question suffix constant already exists — none was seen in this pass; worth searching `sase/plan_chain.py` for existing `PLAN_CHAIN_*_SUFFIX` constants before inventing one).

**What's reused vs. gate_shell-specific:** everything in `shells/` (`member.py`'s `create_family_shell_member`, `naming.py`'s `allocate_shell_suffix`/`new_shell_id`/`short_shell_id`, plus `followup.py`, `handoff.py`, `settlement.py`, `state.py`, `status.py`, `output.py`, `prompt.py`) is kind-agnostic substrate meant to be called from a kind-specific package. `gate_shell/` supplies only the gate-specific glue: `models.py` (typed `GateShellRecord`/`GateShellState`), the `GateShellSpec` wire-shape validation (in `notification_gates/model_shell.py`, not in `gate_shell/` itself), `member.py`'s `_GATE_INHERITED_METADATA_FIELDS` + `gate_metadata` dict, `naming.py`'s gate-specific ID/suffix constants, `store.py`'s `list_gate_shells`/`read_gate_shell_marker`/`find_gate_shell_by_gate_id` (built on `is_gate_shell_member_record`, which checks `meta.gate_id`), and `transaction.py`'s `create_gate_shell`/`GateShellCreation`. A new `question_shell/` package should follow this exact split: reuse `sase.shells.*` directly, and add only `question_shell/models.py`, `question_shell/member.py`, `question_shell/naming.py`, `question_shell/store.py`, `question_shell/transaction.py` (plus whatever lifecycle files the settle/followup story needs), gated on a `question_id`/`is_question_shell_member_record` analog to `gate_id`/`is_gate_shell_member_record`.

---
Nothing from items 1–6 was skipped. For item 7/8 I did not find any `PLAN_CHAIN_QUESTION_SUFFIX`-style constant already reserved for questions — if you need one, grep `src/sase/plan_chain.py` for the full set of `PLAN_CHAIN_*_SUFFIX` constants before picking a new suffix string, since that file wasn't in scope of this pass beyond the two gate-related imports (`PLAN_CHAIN_GATE_SUFFIX`, `agent_family_base`, `canonical_plan_chain_suffix`) referenced above.

I now have complete, verified information for all 10 items. Here is the full report.

## 1. `src/sase/axe/run_agent_exec_questions.py` (full contents, 284 lines)

Full path: `/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/src/sase/axe/run_agent_exec_questions.py`

Imports (lines 1–46):
```python
1	"""Questions marker handling for the agent execution loop."""
2	
3	from __future__ import annotations
4	
5	import json
6	import logging
7	from datetime import UTC, datetime
8	from pathlib import Path
9	from typing import TYPE_CHECKING, Any
10	
11	from sase.agent.names import render_agent_name_template
12	from sase.axe.run_agent_exec_plan import (
13	    agent_name_for_suffix,
14	    record_workflow_metadata,
15	)
16	from sase.axe.run_agent_exec_plan_artifacts import store_followup_prompt_artifact
17	from sase.axe.run_agent_helpers import (
18	    assemble_question_followup_prompt,
19	    build_qa_round,
20	    create_followup_artifacts,
21	    finalize_handoff_artifacts_as_completed,
22	    handle_questions_flow,
23	    merge_qa_for_prompt,
24	    normalize_handoff_interruption_state,
25	    promote_to_workflow,
26	    update_meta_field,
27	    update_meta_suffix,
28	    update_step_marker_chat_path,
29	)
30	from sase.axe.run_agent_successor import SuccessorRequest, continue_as_successor
31	from sase.axe.run_agent_wait_slots import wait_for_runner_slot
32	from sase.axe.runner_signals import reset_killed
33	from sase.core.runner_slots import normalize_wait_priority
34	from sase.plan_chain import (
35	    AGENT_FAMILY_SEPARATOR,
36	    PLAN_CHAIN_PLAN_SUFFIX,
37	    agent_family_role_for_suffix,
38	    canonical_plan_chain_suffix,
39	    is_root_question_suffix,
40	    question_followup_suffix_template,
41	)
42	
43	if TYPE_CHECKING:
44	    from sase.axe.run_agent_exec import AgentExecContext, LoopState
45	
46	logger = logging.getLogger(__name__)
```

Note: `assemble_question_followup_prompt`, `build_qa_round`, `merge_qa_for_prompt`, and `handle_questions_flow` are re-exported through `sase.axe.run_agent_helpers` (a facade module), not defined there directly — their real homes are `sase.main.qa_prompt` (build_qa_round/merge_qa_for_prompt/assemble_question_followup_prompt) and `sase.axe.run_agent_helpers_questions` (handle_questions_flow).

`_update_sdd_prompt_snapshot_qa` (lines 76–117):
```python
76	def _update_sdd_prompt_snapshot_qa(
77	    ctx: AgentExecContext,
78	    state: LoopState,
79	    merged_qa_text: str,
80	) -> None:
81	    """Update the recorded prompt artifact and commit machine-made store writes.
82	
83	    In-tree prompt files remain part of the agent's normal workspace commit flow.
84	    External stores are committed here so a SASE-authored Q&A update never
85	    becomes unclaimed work for the commit finalizer.
86	    """
87	    if state.sdd_spec_path is None:
88	        return
89	
90	    prompt_path = Path(state.sdd_spec_path)
91	    parts = prompt_path.parts
92	    if len(parts) >= 3 and parts[-3] == "prompts" and parts[-2].isdigit():
93	        from sase.sdd.files import set_prompt_qa
94	
95	        # The commit finalizer recognizes Q&A-only edits at this canonical
96	        # agents-sidecar path and commits them without prompting the agent.
97	        set_prompt_qa(prompt_path, merged_qa_text)
98	        return
99	
100	    # Compatibility for an interrupted run that still points at the legacy
101	    # plans-sidecar prompt location during the cutover.
102	    from sase.sdd.files import commit_sdd_store_files, set_prompt_qa
103	    from sase.sdd.store import resolve_sdd_store
104	
105	    set_prompt_qa(prompt_path, merged_qa_text)
106	
107	    store = resolve_sdd_store(ctx.workspace_dir, ctx.workspace_num or 1)
108	    if store.is_in_tree:
109	        return
110	
111	    commit_sdd_store_files(
112	        store,
113	        f"Add Q&A to {prompt_path.stem} prompt",
114	        auto_commit_type="sdd",
115	        paths=[prompt_path],
116	        artifacts_dir=state.current_artifacts_dir,
117	    )
```

`handle_questions_marker` (lines 120–283) — full body:
```python
120	def handle_questions_marker(
121	    q_data: dict[str, Any],
122	    ctx: AgentExecContext,
123	    state: LoopState,
124	) -> str | None:
125	    """Handle a questions marker left by ``sase questions``.
126	
127	    Returns a loop-outcome string to break the loop, or ``None`` to continue.
128	    """
129	    normalize_handoff_interruption_state(state.current_artifacts_dir)
130	    finalize_handoff_artifacts_as_completed(state.current_artifacts_dir)
131	    previous_role_suffix = state.current_role_suffix
132	    base_meta = _interrupted_phase_meta(state.current_artifacts_dir, ctx.agent_meta)
133	    interrupted_role = _meta_family_role(base_meta)
134	    first_family_agent_question = state.agent_step == 1
135	    first_plan_agent_question = first_family_agent_question and (
136	        canonical_plan_chain_suffix(previous_role_suffix) == PLAN_CHAIN_PLAN_SUFFIX
137	    )
138	    interrupted_suffix: str | None
139	    if first_plan_agent_question:
140	        interrupted_suffix = PLAN_CHAIN_PLAN_SUFFIX
141	    elif first_family_agent_question:
142	        interrupted_suffix = f"{AGENT_FAMILY_SEPARATOR}0"
143	    else:
144	        interrupted_suffix = canonical_plan_chain_suffix(previous_role_suffix)
145	    if interrupted_suffix is None:
146	        interrupted_suffix = (
147	            canonical_plan_chain_suffix(base_meta.get("role_suffix"))
148	            or f"{AGENT_FAMILY_SEPARATOR}0"
149	        )
150	    if first_family_agent_question:
151	        update_meta_suffix(state.current_artifacts_dir, interrupted_suffix)
152	
153	    questions_submitted_at = datetime.now(UTC).isoformat()
154	    update_meta_field(
155	        state.current_artifacts_dir,
156	        "questions_submitted_at",
157	        questions_submitted_at,
158	    )
159	
160	    # Clear the killed flag set by the questions command's
161	    # SIGTERM so the poll loop only exits on a NEW kill signal.
162	    reset_killed()
163	    response = handle_questions_flow(
164	        q_data.get("questions", []),
165	        state.current_artifacts_dir,
166	        reacquire_runner_slot=lambda claim: wait_for_runner_slot(
167	            state.current_artifacts_dir,
168	            ctx.cl_name,
169	            Path(state.current_artifacts_dir).name,
170	            base_meta,
171	            wait_runners=None,
172	            wait_priority=normalize_wait_priority(base_meta.get("wait_priority")),
173	            claim=claim,
174	        ),
175	        run_started_at=(
176	            base_meta.get("run_started_at")
177	            if isinstance(base_meta.get("run_started_at"), str)
178	            else None
179	        ),
180	    )
181	    if response is None:
182	        return "killed"
183	    question_relationships = {
184	        "questions_submitted_at": questions_submitted_at,
185	        "question_request_path": response.get("_question_request_path"),
186	        "question_response_path": response.get("_question_response_path"),
187	        "question_session_id": response.get("_question_session_id"),
188	        "patch_name": ctx.cl_name,
189	        "changespec_name": ctx.cl_name,
190	    }
191	    record_workflow_metadata(state.current_artifacts_dir, question_relationships)
192	
193	    # Save a chat file for the questions step
194	    from sase.history.chat import save_chat_history
195	    from sase.history.chat_extras import format_extra_sections
196	
197	    _q_suffix = interrupted_suffix
198	    _q_agent = agent_name_for_suffix(ctx, _q_suffix)
199	    _q_extra = format_extra_sections(state.current_artifacts_dir)
200	
201	    # Append this round before rendering so the chat transcript and the
202	    # follow-up prompt share the same monotonic merged section.
203	    state.qa_rounds.append(build_qa_round(q_data.get("questions", []), response))
204	    merged_qa_text = merge_qa_for_prompt(state.qa_rounds)
205	
206	    _q_chat = save_chat_history(
207	        prompt=state.current_prompt,
208	        response=merged_qa_text,
209	        workflow="ace-run",
210	        agent=_q_agent,
211	        timestamp=ctx.timestamp,
212	        extra_sections=_q_extra,
213	        branch_or_workspace=ctx.cl_name,
214	        metadata_agent=_q_agent,
215	        metadata_multi_agent_prompt=ctx.multi_agent_prompt_file,
216	    )
217	    state.saved_chat_paths.append((_q_suffix, _q_chat))
218	    update_meta_field(state.current_artifacts_dir, "chat_path", _q_chat)
219	    update_step_marker_chat_path(state.current_artifacts_dir, _q_chat)
220	
221	    root_sequence = (
222	        first_family_agent_question and not first_plan_agent_question
223	    ) or is_root_question_suffix(
224	        interrupted_suffix,
225	        agent_family_role=interrupted_role,
226	    )
227	    suffix_template = (
228	        f"{AGENT_FAMILY_SEPARATOR}@"
229	        if root_sequence
230	        else question_followup_suffix_template(
231	            interrupted_suffix,
232	            agent_family_role=interrupted_role,
233	        )
234	    )
235	    followup_role = (
236	        "q"
237	        if root_sequence
238	        else agent_family_role_for_suffix(
239	            render_agent_name_template(suffix_template, "0"),
240	            agent_family_role=interrupted_role,
241	        )
242	    )
243	    # Rebuild from the current phase base (code/feedback/planner prompt) so a
244	    # code-phase question keeps the code prompt and its ``%model`` directive.
245	    followup_prompt = assemble_question_followup_prompt(
246	        state.question_base_prompt,
247	        state.qa_rounds,
248	    )
249	    continue_as_successor(
250	        ctx,
251	        state,
252	        SuccessorRequest(
253	            base_meta=base_meta,
254	            prompt=followup_prompt,
255	            suffix_template=suffix_template,
256	            extra_reserved_suffixes=(
257	                *(suffix for suffix, _path in state.saved_chat_paths if suffix),
258	                interrupted_suffix,
259	            ),
260	            agent_family_role=followup_role,
261	            relationships={
262	                **question_relationships,
263	                "source_plan_agent_name": _q_agent,
264	            },
265	            prompt_artifact_label="Full question prompt",
266	            promote_role_suffix=interrupted_suffix,
267	            fallback_token="1" if root_sequence else "0",
268	        ),
269	        create_artifacts=create_followup_artifacts,
270	        promote=promote_to_workflow,
271	        store_prompt=_store_followup_prompt_artifact,
272	    )
273	
274	    # Update the recorded prompt artifact with the merged Q&A section so the
275	    # snapshot mirrors the prompt the follow-up agent will see (one
276	    # block, continuous numbering — not an appended per-round delta).
277	    if state.sdd_spec_path is not None:
278	        try:
279	            _update_sdd_prompt_snapshot_qa(ctx, state, merged_qa_text)
280	        except Exception:
281	            logger.warning("SDD prompt Q&A snapshot update failed", exc_info=True)
282	
283	    return None  # continue loop
```

Helper functions `_interrupted_phase_meta` (51–68) and `_meta_family_role` (71–73) are also in this file — see the tool output above for exact text if needed; they're used only to resolve `base_meta`/`interrupted_role`.

---

## 2. `src/sase/axe/run_agent_helpers_questions.py` (full contents, 182 lines)

Full path: `/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/src/sase/axe/run_agent_helpers_questions.py`

```python
1	"""Question flow and Q&A prompt helpers for the agent runner."""
2	
3	from __future__ import annotations
4	
5	import json
6	import os
7	import uuid
8	from collections.abc import Callable
9	from datetime import UTC, datetime
10	from typing import Any
11	
12	from sase.axe.runner_signals import was_killed
13	from sase.core.agent_artifact_index_lifecycle import (
14	    update_agent_artifact_index_for_marker_mutation,
15	)
16	from sase.main.qa_prompt import build_qa_round, merge_qa_for_prompt
17	
18	RunnerSlotReacquirer = Callable[[Callable[[], str]], str]
19	
20	
21	def _remove_pending_question_marker(
22	    artifacts_dir: str,
23	    *,
24	    claimed_at: str | None = None,
25	    strict: bool = False,
26	) -> str:
27	    """Remove the question pause marker and return a slot-claim timestamp."""
28	    marker_path = os.path.join(artifacts_dir, "pending_question.json")
29	    try:
30	        os.unlink(marker_path)
31	        update_agent_artifact_index_for_marker_mutation(artifacts_dir)
32	    except OSError:
33	        if strict:
34	            raise
35	    return claimed_at or datetime.now(UTC).isoformat()
36	
37	
38	def handle_questions_flow(
39	    questions: list[dict[str, Any]],
40	    artifacts_dir: str,
41	    *,
42	    reacquire_runner_slot: RunnerSlotReacquirer | None = None,
43	    run_started_at: str | None = None,
44	) -> dict[str, Any] | None:
45	    """Handle the questions notification, pause, and slot reacquisition flow."""
46	    from sase.main.plan_approve_handler import (
47	        get_tmux_prefix,
48	        is_auto_approve_active,
49	        ring_tmux_bell,
50	        send_desktop_notification,
51	    )
52	
53	    session_id = str(uuid.uuid4())
54	    agent_cl_name = os.environ.get("SASE_AGENT_CL_NAME")
55	    agent_project_file = os.environ.get("SASE_AGENT_PROJECT_FILE")
56	    agent_timestamp = os.environ.get("SASE_AGENT_TIMESTAMP")
57	    agent_root_timestamp = os.environ.get("SASE_AGENT_ROOT_TIMESTAMP")
58	    action_data = {
59	        key: value
60	        for key, value in {
61	            "session_id": session_id,
62	            "agent_cl_name": agent_cl_name,
63	            "agent_project_file": agent_project_file,
64	            "agent_timestamp": agent_timestamp,
65	            "agent_root_timestamp": agent_root_timestamp,
66	        }.items()
67	        if value
68	    }
69	
70	    from sase.user_question_actions import create_user_question_gate
71	
72	    gate = create_user_question_gate(
73	        questions,
74	        session_id=session_id,
75	        producer={
76	            "agent": os.environ.get("SASE_AGENT"),
77	            "artifacts_dir": artifacts_dir,
78	            **action_data,
79	        },
80	        action_data=action_data,
81	        auto=is_auto_approve_active(),
82	    )
83	    request_path = str(gate.request_path)
84	    response_path = str(gate.response_path)
85	
86	    if gate.notification_id is None:
87	        from sase.notification_gates.poller import poll_gate
88	
89	        terminal = poll_gate(gate.bundle_path)
90	        if terminal is None or terminal.status != "responded":
91	            return None
92	        return _question_result(
93	            terminal.payload,
94	            request_path=request_path,
95	            response_path=response_path,
96	            session_id=session_id,
97	        )
98	
99	    prefix = get_tmux_prefix()
100	    send_desktop_notification(
101	        f"{prefix} Agent Question", "Agent has questions in sase ace"
102	    )
103	    ring_tmux_bell()
104	
105	    pending_marker_path = os.path.join(artifacts_dir, "pending_question.json")
106	    marker_written = False
107	    try:
108	        marker_payload = {
109	            "session_id": session_id,
110	            "request_path": request_path,
111	            "submitted_at": datetime.now(UTC).isoformat(),
112	        }
113	        with open(pending_marker_path, "w", encoding="utf-8") as f:
114	            json.dump(marker_payload, f, indent=2)
115	        update_agent_artifact_index_for_marker_mutation(artifacts_dir)
116	        marker_written = True
117	    except OSError:
118	        pass
119	
120	    try:
121	        from sase.notification_gates.poller import wait_for_gate
122	
123	        terminal = wait_for_gate(
124	            gate.bundle_path,
125	            poll_interval=0.2,
126	            cancelled=was_killed,
127	        )
128	        if terminal.status != "responded":
129	            return None
130	        response = _question_result(
131	            terminal.payload,
132	            request_path=request_path,
133	            response_path=response_path,
134	            session_id=session_id,
135	        )
136	        if marker_written and reacquire_runner_slot is not None:
137	            reacquire_runner_slot(
138	                lambda: _remove_pending_question_marker(
139	                    artifacts_dir,
140	                    claimed_at=run_started_at,
141	                    strict=True,
142	                )
143	            )
144	        return response
145	    finally:
146	        _remove_pending_question_marker(artifacts_dir)
147	
148	
149	def _question_result(
150	    response: dict[str, Any],
151	    *,
152	    request_path: str,
153	    response_path: str,
154	    session_id: str,
155	) -> dict[str, Any]:
156	    """Translate a neutral gate response into legacy continuation data."""
157	    from sase.user_question_actions import QUESTION_OPTION_ID
158	
159	    option_results = response.get("option_results")
160	    result = (
161	        next(
162	            (
163	                entry.get("result")
164	                for entry in option_results
165	                if isinstance(entry, dict) and entry.get("id") == QUESTION_OPTION_ID
166	            ),
167	            None,
168	        )
169	        if isinstance(option_results, list)
170	        else None
171	    )
172	    if not isinstance(result, dict):
173	        raise ValueError("question gate response is missing its result")
173	    translated = dict(result)
174	    feedback = response.get("feedback")
175	    if isinstance(feedback, str) and feedback:
176	        translated["global_note"] = feedback
177	    translated["_question_request_path"] = request_path
178	    translated["_question_response_path"] = response_path
179	    translated["_question_session_id"] = session_id
180	    return translated
```

Key facts for the migration:
- `handle_questions_flow` has two paths: **auto-poll** (`gate.notification_id is None`, via `poll_gate`) and **notify+pending-marker** (via `wait_for_gate` + `pending_question.json` marker + runner-slot reacquisition).
- `create_user_question_gate` is called from here, in `sase.user_question_actions` (see item 5) — this is the entry point a gate-shell-flavored questions flow would need to replace or wrap.
- `_question_result` expects the v3 gate response shape: `option_results: [{"id": ..., "result": {...}}]` with the `submit` option id (`QUESTION_OPTION_ID = "submit"`).

---

## 3. `src/sase/axe/run_agent_exec_types.py` — `LoopState`

Full path: `/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/src/sase/axe/run_agent_exec_types.py`

```python
56	@dataclass
57	class LoopState:
58	    """Mutable state for the execution loop."""
59	
60	    current_prompt: str
61	    current_role_suffix: str
62	    current_artifacts_dir: str
63	    loop_outcome: str
64	    sdd_spec_path: str | None
65	    # The bare initial prompt with no accumulated Q&A or feedback appended.
66	    original_prompt: str
67	    # Base prompt for question continuations: the currently executing phase's
68	    # prompt before merged Q&A is appended. Refreshed on phase transitions
69	    # (accepted-plan code/epic handoff and plan-feedback replan) so a
70	    # ``/sase_questions`` interruption from the code phase rebuilds from the
71	    # code-agent prompt rather than the initial planner prompt. Defaults to the
72	    # initial prompt at loop start (see ``__post_init__``). Unlike
73	    # ``original_prompt`` it is mutable, tracking the live phase.
74	    question_base_prompt: str = ""
75	    qa_rounds: list[QARound] = field(default_factory=list)
76	    feedback_bullets: list[str] = field(default_factory=list)
77	    feedback_round: int = 0
78	    agent_step: int = 1
79	    saved_chat_paths: list[tuple[str, str]] = field(default_factory=list)
80	    # Snapshot of SASE_AGENT_TIMESTAMP at loop entry, restored after finalization.
81	    original_agent_timestamp: str | None = None
82	
83	    def __post_init__(self) -> None:
84	        if not self.question_base_prompt:
85	            self.question_base_prompt = self.original_prompt
86	```

`current_artifacts_dir` is a `str` (not `Path`); it is the interrupted agent's own artifacts directory, used throughout `handle_questions_marker`/`handle_gate_marker` for marker read/write, meta updates, and chat history. `sdd_spec_path` is `str | None` — when set, `handle_questions_marker` re-snapshots Q&A into the SDD prompt store after the successor launch (see item 1). `qa_rounds: list[QARound]` accumulates every round for the life of the loop; `question_base_prompt` is the pre-Q&A base the followup prompt is rebuilt from on each round.

`QARound` import is `from sase.main.qa_markdown import QARound` (line 8 of this file).

---

## 4. `src/sase/axe/run_agent_exec_gate.py` (full contents, 165 lines)

Full path: `/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/src/sase/axe/run_agent_exec_gate.py`

```python
1	"""Gate-shell marker handling for the agent execution loop."""
2	
3	from __future__ import annotations
4	
5	import json
6	from pathlib import Path
7	from typing import TYPE_CHECKING, Any
8	
9	from sase.axe.run_agent_helpers import (
10	    finalize_handoff_artifacts_as_completed,
11	    normalize_handoff_interruption_state,
12	    update_meta_field,
13	    update_meta_suffix,
14	    update_step_marker_chat_path,
15	)
16	from sase.axe.runner_signals import reset_killed
17	from sase.history.chat import save_chat_history
18	from sase.history.chat_extras import format_extra_sections
19	from sase.notification_gates.durability import read_json_object
20	from sase.plan_chain import AGENT_FAMILY_SEPARATOR, canonical_plan_chain_suffix
21	
22	if TYPE_CHECKING:
23	    from sase.axe.run_agent_exec import AgentExecContext, LoopState
23	
24	
25	def handle_gate_marker(
26	    gate_data: dict[str, Any],
27	    ctx: AgentExecContext,
28	    state: LoopState,
29	) -> str:
30	    """Adopt a ``.sase_gate_pending`` marker after runner SIGTERM."""
31	    normalize_handoff_interruption_state(state.current_artifacts_dir)
32	    finalize_handoff_artifacts_as_completed(state.current_artifacts_dir)
33	
34	    starter_meta = _read_json_object(
35	        Path(state.current_artifacts_dir) / "agent_meta.json"
36	    )
37	    starter_suffix = _promoted_starter_suffix(ctx.agent_name, starter_meta)
38	    if starter_suffix is not None:
39	        update_meta_suffix(state.current_artifacts_dir, starter_suffix)
40	        state.current_role_suffix = starter_suffix
41	        state.agent_step = max(state.agent_step, 2)
42	        starter_meta["role_suffix"] = canonical_plan_chain_suffix(starter_suffix)
43	
44	    gate_meta = _gate_member_meta(gate_data)
45	    gate_id = _text(gate_data.get("gate_id")) or _text(gate_meta.get("gate_id"))
46	    member_artifacts_dir = _text(gate_data.get("member_artifacts_dir"))
47	    member_agent_name = _text(gate_data.get("member_agent_name")) or _text(
48	        gate_meta.get("name")
49	    )
50	    starter_agent = _text(starter_meta.get("name")) or ctx.agent_name
51	    bundle_path = _text(gate_meta.get("gate_bundle_path"))
52	
53	    response = _format_gate_response(
54	        gate_id=gate_id,
55	        member_agent_name=member_agent_name,
56	        kind=_text(gate_meta.get("gate_kind")),
57	        title=_gate_title(bundle_path, gate_meta),
58	    )
59	    extra = format_extra_sections(state.current_artifacts_dir)
60	    chat_path = save_chat_history(
61	        prompt=state.current_prompt,
62	        response=response,
63	        workflow="ace-run",
64	        agent=starter_agent,
65	        timestamp=ctx.timestamp,
66	        extra_sections=extra,
67	        branch_or_workspace=ctx.cl_name,
68	        metadata_agent=starter_agent,
69	        metadata_model=ctx.agent_model,
70	        metadata_llm_provider=ctx.agent_llm_provider,
71	        metadata_multi_agent_prompt=ctx.multi_agent_prompt_file,
72	    )
73	
74	    state.saved_chat_paths.append(
75	        (starter_suffix or state.current_role_suffix, chat_path)
76	    )
77	    update_meta_field(state.current_artifacts_dir, "chat_path", chat_path)
78	    if gate_id:
79	        update_meta_field(state.current_artifacts_dir, "gate_id", gate_id)
80	    if member_agent_name:
81	        update_meta_field(
82	            state.current_artifacts_dir,
83	            "gate_member_agent_name",
84	            member_agent_name,
85	        )
86	    update_step_marker_chat_path(state.current_artifacts_dir, chat_path)
87	
88	    if member_artifacts_dir and starter_agent:
89	        update_meta_field(member_artifacts_dir, "gate_creator_agent", starter_agent)
90	
91	    reset_killed()
92	    return "gated"
```
(remaining helpers `_format_gate_response`, `_gate_member_meta`, `_gate_title`, `_promoted_starter_suffix`, `_read_json_object`, `_text` follow at lines 96–162, `__all__ = ["handle_gate_marker"]` at line 164 — shown verbatim in the tool output above.)

**Critical fact for the plan**: `handle_gate_marker`'s signature is `(gate_data: dict[str, Any], ctx: AgentExecContext, state: LoopState) -> str`, and it reads exactly these keys off `gate_data`:
- `gate_data["gate_id"]`
- `gate_data["member_artifacts_dir"]`
- `gate_data["member_agent_name"]`

This matches the marker payload actually written by `maybe_handoff_gate_from_agent` in `/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/src/sase/gate_shell/handoff.py` lines 73–79:
```python
73	def _gate_pending_payload(record: GateShellRecord) -> dict[str, str]:
74	    return {
75	        "gate_id": record.gate_id,
76	        "member_artifacts_dir": record.artifacts_dir,
77	        "member_agent_name": record.member_agent_name,
78	        "kind": record.kind,
79	    }
```
`handle_gate_marker` does not consume `kind` directly — it re-reads gate metadata (`gate_kind`, `gate_bundle_path`, `gate_label`) from `member_artifacts_dir/agent_meta.json`. So a synthesized `gate_data` dict for a "gate shell for questions" migration only strictly needs `gate_id`, `member_artifacts_dir`, `member_agent_name` (and, if mirroring the handoff writer, `kind`), and the target `member_artifacts_dir` must already contain a written `agent_meta.json` with `gate_id`/`gate_kind`/`gate_bundle_path`/`name` for `_gate_member_meta`/`_gate_title` to resolve correctly.

`handle_gate_marker`'s caller in `/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/src/sase/axe/run_agent_exec.py`:
```python
160	    gate_data = read_and_delete_marker(
161	        state.current_artifacts_dir,
162	        ".sase_gate_pending",
163	    )
...
175	    if gate_data and _marker_predates_kill(gate_data, kill_time):
176	        return handle_gate_marker(gate_data, ctx, state)
```
The marker filename constant is `GATE_PENDING_MARKER = ".sase_gate_pending"` (`/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/src/sase/agent/pending_handoff.py:8`), alongside `QUESTIONS_PENDING_MARKER = ".sase_questions_pending"` (line 6 of same file). `read_and_delete_marker(artifacts_dir: str, filename: str) -> dict[str, Any] | None` is defined at `/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/src/sase/axe/run_agent_helpers_state.py:202` (re-exported through `run_agent_helpers.py:87`).

---

## 5. `src/sase/user_question_actions.py` (full contents, 564 lines)

Full path: `/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/src/sase/user_question_actions.py`

Module constants (lines 15–19):
```python
15	QUESTION_COMMAND_PATH = "commands/submit"
16	QUESTION_OPTION_ID = "submit"
17	QUESTION_CONTINUATION_MODE = "agent_question"
18	QUESTION_REQUEST_FILE = "question_request.json"
19	QUESTION_RESPONSE_FILE = "question_response.json"
```

`create_user_question_gate` — builds the v3 gate request dict (lines 51–107):
```python
51	def create_user_question_gate(
52	    questions: list[dict[str, Any]],
53	    *,
54	    session_id: str,
55	    producer: Mapping[str, Any] | None = None,
56	    action_data: Mapping[str, str] | None = None,
57	    auto: bool = False,
58	) -> Any:
59	    """Create a neutral UserQuestion gate for the current agent continuation."""
60	    normalized_questions = validate_user_questions(questions)
61	    response_schema = question_response_schema(normalized_questions)
62	    summary = "; ".join(
63	        str(question.get("question") or "?") for question in normalized_questions[:3]
64	    )
65	
66	    from sase.notification_gates.service import create_gate
67	
68	    return create_gate(
69	        {
70	            "schema_version": 3,
71	            "kind": "question",
72	            "request_id": session_id,
73	            "producer": dict(producer or {}),
74	            "continuation_mode": QUESTION_CONTINUATION_MODE,
75	            "payload": {
76	                "questions": normalized_questions,
77	                "session_id": session_id,
78	                "timestamp": time.time(),
79	            },
80	            "presentation": {
81	                "notes": [summary] if summary else ["Agent is asking a question"],
82	                "tags": ["question"],
83	                "action_data": dict(action_data or {}),
84	            },
85	            "query": QUESTION_OPTION_ID,
86	            "primary_branch": [QUESTION_OPTION_ID],
87	            "options": [
88	                {
89	                    "id": QUESTION_OPTION_ID,
90	                    "label": "Submit answers",
91	                    "icon": "✅",
92	                    "command": {"argv": [QUESTION_COMMAND_PATH]},
93	                    "input_schema": response_schema,
94	                    "result_schema": response_schema,
95	                    "feedback": "optional",
96	                }
97	            ],
98	            "resources": [
99	                {
100	                    "path": QUESTION_COMMAND_PATH,
101	                    "role": "command",
102	                    "content": question_gate_command_script(),
103	                }
104	            ],
105	            "auto": auto,
106	        }
107	    )
```
Note: this request dict has **no `"shell"` key** — that is exactly the field `_execute_neutral_launch_approval_response` checks (`isinstance(envelope.get("shell"), dict)`) to decide whether a gate is "shell-backed." A gate-shell-mechanism migration for questions will need to add a `"shell": {...}` block to this request payload (mirroring whatever shape LaunchApproval's shell-backed gates use — not present in this file; it's set elsewhere at gate-shell creation time, see `gate_shell/transaction.py` referenced by `find_gate_shell_by_gate_id`/`GateShellCreation`).

`execute_user_question_response` (lines 110–189) — the non-shell v3 execution path already delegates to `execute_gate_selection`:
```python
110	def execute_user_question_response(
111	    context: UserQuestionActionContext,
112	    response_data: Mapping[str, Any],
113	    *,
114	    source: str = "question_response",
115	) -> _UserQuestionActionResult:
116	    """Resolve a neutral UserQuestion, with legacy in-flight fallback."""
117	    bundle = _resolve_question_bundle(context)
118	    questions = _questions_from_request_root(bundle.root, legacy=bundle.legacy)
119	    normalized = _normalize_user_question_response(questions, response_data)
120	
121	    if bundle.legacy:
122	        response_path = bundle.response
123	        _write_json_once(response_path, normalized, context.notification_id)
124	        response_json = normalized
125	        response_file = QUESTION_RESPONSE_FILE
126	    else:
127	        from sase.notification_gates.executor import execute_gate_selection
128	        from sase.notification_gates.models import GateError
129	        from sase.notification_gates.paths import RESPONSE_FILENAME
130	
131	        try:
132	            shared_feedback = response_data.get("feedback")
133	            if not isinstance(shared_feedback, str):
134	                shared_feedback = normalized.get("global_note")
135	            if not isinstance(shared_feedback, str) or not shared_feedback.strip():
136	                shared_feedback = None
137	            execution = execute_gate_selection(
138	                bundle.root,
139	                [QUESTION_OPTION_ID],
140	                normalized,
141	                feedback=shared_feedback,
142	                source=source,
143	            )
144	        except GateError as exc:
145	            code = (
146	                "conflict_already_handled"
147	                if exc.code in {"already_answered", "gate_cancelled"}
148	                else exc.code
149	            )
150	            raise UserQuestionActionError(code, exc.target, str(exc)) from exc
151	        if execution.already_completed:
152	            raise UserQuestionActionError(
153	                "conflict_already_handled",
154	                context.notification_id or str(bundle.root),
155	                "response already exists",
156	            )
157	        response_json = execution.response
158	        option_results = response_json.get("option_results")
159	        result = (
160	            next(
161	                (
162	                    entry.get("result")
163	                    for entry in option_results
164	                    if isinstance(entry, Mapping)
165	                    and entry.get("id") == QUESTION_OPTION_ID
166	                ),
167	                None,
168	            )
169	            if isinstance(option_results, list)
170	            else None
171	        )
172	        if not isinstance(result, dict):
173	            raise UserQuestionActionError(
174	                "invalid_response",
175	                str(bundle.response),
176	                "question command returned no result object",
177	            )
178	        normalized = _normalize_user_question_response(questions, result)
179	        response_path = bundle.response
180	        response_file = RESPONSE_FILENAME
181	
182	    _run_question_side_effects(context, source=source)
183	    return _UserQuestionActionResult(
184	        notification_id=context.notification_id,
185	        response_file=response_file,
186	        response_path=response_path,
187	        response_json=response_json,
188	        answers=normalized,
189	    )
```
**Note this path does NOT call `find_gate_shell_by_gate_id` / `bind_gate_shell_execution_callbacks` / `settle_gate_shell` at all** — it is the "always synchronous, non-shell" question executor. This is the function that would need shell-awareness added (mirroring `_execute_neutral_launch_approval_response`) if questions move behind a gate-shell mechanism.

`UserQuestionActionContext` dataclass (lines 22–27) and `UserQuestionActionError` (lines 42–48) shown above in full read. Full `__all__` at lines 547–563.

---

## 6. Q&A prompt assembly — `src/sase/main/qa_prompt.py` + `src/sase/main/qa_markdown.py`

`build_qa_round`, `merge_qa_for_prompt`, `assemble_question_followup_prompt` live in `/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/src/sase/main/qa_prompt.py`:
```python
1	"""Shared Q&A follow-up prompt assembly."""
...
7	from sase.main.qa_markdown import QARound, build_merged_qa_markdown
...
10	def build_qa_round(
11	    questions: list[dict[str, Any]],
12	    response: dict[str, Any],
13	) -> QARound:
14	    """Build a QARound from a question list and response dict."""
15	    response_answers = response.get("answers", []) or []
16	    if len(response_answers) == len(questions):
17	        aligned = list(response_answers)
18	    else:
19	        by_text: dict[str, dict[str, Any]] = {
20	            a.get("question", ""): a for a in response_answers if a.get("question")
21	        }
22	        aligned = []
23	        for q in questions:
24	            match = by_text.get(q.get("question", ""))
25	            aligned.append(match if match is not None else {})
26	
27	    return QARound(
28	        questions=list(questions),
29	        answers=aligned,
30	        global_note=response.get("global_note") or None,
31	    )
32	
33	
34	def merge_qa_for_prompt(rounds: list[QARound]) -> str:
35	    """Render accumulated Q&A rounds as a single prompt-bound section."""
36	    body = build_merged_qa_markdown(rounds)
37	    return f"%xprompts_enabled:false\n{body}\n%xprompts_enabled:true"
38	
39	
40	def assemble_question_followup_prompt(
41	    base_prompt: str,
42	    rounds: list[QARound],
43	) -> str:
44	    """Append rendered Q&A rounds to the prompt used by the follow-up agent."""
45	    return base_prompt + "\n\n" + merge_qa_for_prompt(rounds)
```
(Additional helpers `_qa_rounds_from_payload`, `_raw_rounds_from_payload`, `_ensure_mapping_list`, `_qa_round_from_mapping` follow at lines 48–101, for public `#with_q_and_a` xprompt JSON payloads — not central to this migration but shown in full above.)

`QARound` and `build_merged_qa_markdown` live in `/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/src/sase/main/qa_markdown.py`:
```python
21	@dataclass
22	class QARound:
23	    """One round of Q&A — the inputs that produced one rendered section.
24	
25	    A single agent run can accumulate multiple rounds when the agent
26	    enters the question flow more than once (or when a feedback round
27	    follows). The merged renderer (:func:`build_merged_qa_markdown`)
28	    flattens these into a single ``### Questions and Answers`` block.
29	    """
30	
31	    questions: list[dict[str, Any]] = field(default_factory=list)
32	    answers: list[dict[str, Any]] = field(default_factory=list)
33	    global_note: str | None = None
```
`build_merged_qa_markdown(rounds: list[QARound]) -> str` is defined at lines 94–128 (full body shown in the tool output above) — it renders one `### Questions and Answers` header, flattens every round's questions into monotonic `#### Q1`, `#### Q2`, … numbering, and appends only the most recent non-empty `global_note` ("last non-empty wins").

`build_qa_markdown` (a single-round convenience wrapper used by the TUI live-preview modal) is at lines 131–155.

---

## 7. `execute_gate_selection` — `src/sase/notification_gates/executor.py`

Full path: `/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/src/sase/notification_gates/executor.py`

Signature (lines 68–81):
```python
68	def execute_gate_selection(
69	    bundle_path: Path,
70	    selected_option_ids: Sequence[str],
71	    input_data: object | None = None,
72	    *,
73	    feedback: str | None = None,
74	    source: str = "host",
75	    retry: Literal["resume", "restart"] | None = None,
76	    epic_launch_origin: EpicLaunchOrigin | None = None,
77	    option_inputs: Mapping[str, object] | None = None,
78	    on_command_start: Callable[[str, str, str, tuple[str, ...]], None] | None = None,
79	    on_output_line: Callable[[str, str, str, str], None] | None = None,
80	    on_process_state: Callable[[subprocess.Popen[bytes], bool], None] | None = None,
81	) -> GateExecutionResult:
```
Returns `GateExecutionResult` (fields `response: dict[str, Any]`, `already_completed: bool` — defined in `sase.notification_gates.models`). It acquires `bundle_path / ".response.lock"`, and if `response_path.exists()` already, calls `_settle_gate_notification(...)` and returns `already_completed=True` immediately (lines 121–127) — i.e. **the "already answered" short-circuit happens inside `execute_gate_selection` itself**, before any of the three optional streaming callbacks would ever be invoked for that call. This is why callers like `launch_approval_actions.py` and `_mobile_notification_actions.py` still branch on `execution.already_completed` afterward — `execute_gate_selection` never raises for that case, it just returns the flag.

The `on_command_start`/`on_output_line`/`on_process_state` triple is exactly what `_GateShellExecutionCallbacks.as_kwargs()` (item 9) produces, and is threaded through `_execute_one_option` (lines 291–393) to stream one option's command output.

---

## 8. `_execute_neutral_launch_approval_response` — `src/sase/launch_approval_actions.py`

Full path: `/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/src/sase/launch_approval_actions.py`

Full body (lines 129–241):
```python
129	def _execute_neutral_launch_approval_response(
130	    notification: _LaunchApprovalActionContext,
131	    bundle_path: Path,
132	    choice: str,
133	    *,
134	    feedback: str | None,
135	) -> LaunchApprovalActionResult:
136	    """Execute one registered launch option through the common gate executor."""
137	    from sase.gate_shell.log import bind_gate_shell_execution_callbacks
138	    from sase.gate_shell.settlement import settle_gate_shell
139	    from sase.gate_shell.store import find_gate_shell_by_gate_id
140	    from sase.notification_gates.executor import execute_gate_selection
141	    from sase.notification_gates.hashing import load_and_verify_bundle
142	    from sase.notification_gates.models import GateError
143	    from sase.notification_gates.paths import RESPONSE_FILENAME
144	
145	    # Rejecting with a note no longer selects a different option: `feedback`
146	    # is a declared input on `reject`, and the executor injects the note into
147	    # every selected option whose schema declares it.
148	    option_id = choice
149	    envelope, _adapter = load_and_verify_bundle(bundle_path)
150	    shell_backed = isinstance(envelope.get("shell"), dict)
151	    gate_shell = (
152	        find_gate_shell_by_gate_id(None, str(envelope.get("request_id") or ""))
153	        if shell_backed
154	        else None
155	    )
156	    execution_kwargs: dict[str, Any] = (
157	        {}
158	        if gate_shell is None
159	        else bind_gate_shell_execution_callbacks(gate_shell.artifacts_dir).as_kwargs()
160	    )
161	    try:
162	        execution = execute_gate_selection(
163	            bundle_path,
164	            [option_id],
165	            feedback=feedback,
166	            source="launch_response",
167	            **execution_kwargs,
168	        )
169	    except GateError as exc:
170	        code = (
171	            "conflict_already_handled"
172	            if exc.code in {"gate_cancelled", "already_answered"}
173	            else exc.code
174	        )
175	        raise LaunchApprovalActionError(code, exc.target, str(exc)) from exc
176	    if gate_shell is not None:
177	        settle_gate_shell(
178	            gate_shell,
179	            gate_state="answered",
180	            reason="launch approval answered",
181	        )
182	    if execution.already_completed:
183	        raise LaunchApprovalActionError(
184	            "conflict_already_handled",
185	            notification.id,
186	            "response already exists",
187	        )
188	
189	    response_json = execution.response
190	    option_results = response_json.get("option_results")
191	    command_result = (
192	        next(
193	            (
194	                entry.get("result")
195	                for entry in option_results
196	                if isinstance(entry, dict) and entry.get("id") == option_id
197	            ),
198	            None,
199	        )
200	        if isinstance(option_results, list)
201	        else None
202	    )
203	    if not isinstance(command_result, dict):
204	        raise LaunchApprovalActionError(
205	            "invalid_response",
206	            notification.id,
207	            "launch command returned no result object",
208	        )
209	    launched_count = 0
210	    if option_id == "approve":
211	        if command_result.get("dispatch_status") == "failed":
212	            raise LaunchApprovalActionError(
213	                "dispatch_failed",
214	                notification.id,
215	                str(command_result.get("dispatch_error") or "launch dispatch failed"),
216	            )
217	        launched_count = int(command_result.get("launched_count") or 0)
218	        summary = command_result.get("admission_summary")
219	        if isinstance(summary, dict):
220	            message = _admission_message(summary, launched_count)
221	        else:
222	            message = (
223	                f"Launch approved and dispatched {launched_count} agent"
224	                f"{'s' if launched_count != 1 else ''}"
225	            )
226	    elif option_id == "reject":
227	        message = "Feedback received" if feedback else "Launch rejected"
228	    else:  # The registered executor normally rejects this first.
229	        raise LaunchApprovalActionError(
230	            "unsupported_action", option_id, "unsupported launch action option"
231	        )
232	
233	    _run_launch_side_effects(notification, option_id)
234	    return LaunchApprovalActionResult(
235	        notification_id=notification.id,
236	        response_file=RESPONSE_FILENAME,
237	        response_path=bundle_path / RESPONSE_FILENAME,
238	        response_json=response_json,
239	        message=message,
240	        launched_count=launched_count,
241	    )
```

**Ordering confirmed exactly as you described**: `execute_gate_selection` → GateError translation → `settle_gate_shell(...)` (if `gate_shell is not None`) → **then** the `execution.already_completed` check that raises `conflict_already_handled`. This is the one call site among the three (`launch_approval_actions.py`, `integrations/_mobile_notification_actions.py`, `notification_gates/cli_answer.py`) that settles the gate shell *before* checking `already_completed`; the other two (`_mobile_notification_actions.py:108-115` and `cli_answer.py:176-178`) settle *after*/regardless of `already_completed`. A new `_execute_neutral_question_gate_response`-style function should copy this exact ordering per your instructions.

Also note the outer dispatcher `execute_launch_approval_response` (lines 45–66) which decides legacy vs. neutral by checking `resolve_action_bundle(...)`:
```python
45	def execute_launch_approval_response(
46	    notification: _LaunchApprovalActionContext,
47	    choice: str,
48	    *,
49	    feedback: str | None = None,
50	) -> LaunchApprovalActionResult:
51	    """Resolve a neutral LaunchApproval, with legacy in-flight fallback."""
52	    from sase.notification_gates.paths import resolve_action_bundle
53	
54	    bundle = resolve_action_bundle("LaunchApproval", notification.host_action_data)
55	    if bundle is not None and not bundle.legacy:
56	        return _execute_neutral_launch_approval_response(
57	            notification,
58	            bundle.root,
59	            choice,
60	            feedback=feedback,
61	        )
62	    return _execute_legacy_launch_approval_response(
63	        notification,
64	        choice,
65	        feedback=feedback,
66	    )
```
This mirrors the `bundle.legacy` branch inside `execute_user_question_response` (item 5) — the analogous place to insert gate-shell awareness for questions would be the `else:` (non-legacy) branch there.

---

## 9. `bind_gate_shell_execution_callbacks`, `find_gate_shell_by_gate_id`, `settle_gate_shell`

**`bind_gate_shell_execution_callbacks`** — `/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/src/sase/gate_shell/log.py:58-87`:
```python
58	def bind_gate_shell_execution_callbacks(
59	    artifacts_dir: str,
60	) -> _GateShellExecutionCallbacks:
61	    """Bind gate.log streaming and pid recording for one gate shell's execution.
62	
63	    ``on_command_start`` writes a ``$ commands/cleanup``-style header so an AND
64	    branch's multiple commands read as one attributable stream;
65	    ``on_output_line`` appends each line, tagging stderr; ``on_process_state``
66	    records the running command's pid so ``sase gate`` can report and
67	    interrupt a runaway approved command.
68	    """
69	
70	    def on_command_start(
71	        _scope: str, _target_id: str, _label: str, argv: tuple[str, ...]
72	    ) -> None:
73	        _append_gate_shell_log_text(artifacts_dir, f"$ {argv[0]}\n")
74	
75	    def on_output_line(_scope: str, _target_id: str, stream: str, line: str) -> None:
76	        prefix = "! " if stream == "stderr" else ""
77	        _append_gate_shell_log_text(artifacts_dir, f"{prefix}{line}\n")
78	
79	    def on_process_state(process: subprocess.Popen[bytes], started: bool) -> None:
80	        if started:
81	            update_meta_field(artifacts_dir, "pid", process.pid)
82	
83	    return _GateShellExecutionCallbacks(
84	        on_command_start=on_command_start,
85	        on_output_line=on_output_line,
86	        on_process_state=on_process_state,
87	    )
```
Returns a `_GateShellExecutionCallbacks` frozen dataclass (lines 41–55) with `.as_kwargs() -> dict[str, Callable[..., None]]` producing exactly the `on_command_start`/`on_output_line`/`on_process_state` kwargs `execute_gate_selection` accepts.

**`find_gate_shell_by_gate_id`** — `/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/src/sase/gate_shell/store.py:89-104`:
```python
89	def find_gate_shell_by_gate_id(
90	    project_name: str | None,
91	    gate_id: str,
92	) -> GateShellRecord | None:
93	    """Return the newest gate-shell member for ``gate_id``, if present.
94	
95	    A ``None`` project searches every project's artifact index, the same
96	    unscoped lookup :func:`list_gate_shells` already performs for the
97	    reclaim chop.
98	    """
99	    matches = [
100	        record
101	        for record in list_gate_shells(project=project_name)
102	        if record.gate_id == gate_id
103	    ]
104	    return matches[0] if matches else None
```

**`settle_gate_shell`** — `/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/src/sase/gate_shell/settlement.py:64-93` (signature + docstring; full body shown in the tool output above runs through decision-record writing, done-marker writing, workflow finalization, and either follow-up launch or suppressed-follow-up handling):
```python
64	def settle_gate_shell(
65	    record: GateShellRecord,
66	    *,
67	    gate_state: GateShellState,
68	    reason: str | None = None,
69	    creator_live: bool = False,
70	) -> GateShellRecord:
71	    """Settle a gate-shell member into ``gate_state``.
72	
73	    Never launches a follow-up, releases a claim, or notifies until the shell
74	    itself is terminal and its artifact index is visible -- otherwise a
75	    forked successor could resolve ``#fork`` before this shell's own
76	    decision record and chat exist.
77	
78	    ``creator_live=True`` marks a settlement that runs inside the still-live
79	    creator's own process (the ``%auto`` short-circuit, or after a failed
80	    handoff): no follow-up is launched and no claim is disposed of, because
81	    the creator itself still owns the lane and the workspace. A policy that
82	    would otherwise have launched is stashed as an artifact instead, so
83	    nothing the shell's author declared is silently lost.
84	    """
```
`GateShellState` is a literal type (imported from `sase.gate_shell.models`) — observed values in call sites: `"answered"`, `"stopped"`, `"lost"`, `"timeout"`.

**All current call sites** (grep -rn):
```
src/sase/launch_approval_actions.py:137,159    bind_gate_shell_execution_callbacks
src/sase/integrations/_mobile_notification_actions.py:56,90
src/sase/notification_gates/cli_answer.py:22,164

src/sase/launch_approval_actions.py:139,152    find_gate_shell_by_gate_id
src/sase/integrations/_mobile_notification_actions.py:58,83
src/sase/gate_shell/transaction.py:29,94
src/sase/notification_gates/cli_show.py:22,116
src/sase/notification_gates/cli_answer.py:24,158

src/sase/launch_approval_actions.py:138,177    settle_gate_shell
src/sase/integrations/_mobile_notification_actions.py:57,115
src/sase/gate_shell/handoff.py:10,65
src/sase/gate_shell/cancel.py:8,32,36,41,45
src/sase/notification_gates/cli_answer.py:23,177
src/sase/gate_shell/transaction.py:22,141,155,174
src/sase/gate_shell/reclaim.py:12,91,96,101,108,110,117,123
```
So the three neutral-gate-answer call sites that pair `find_gate_shell_by_gate_id` + `bind_gate_shell_execution_callbacks` + `execute_gate_selection` + `settle_gate_shell` together are: `launch_approval_actions.py` (item 8, above), `integrations/_mobile_notification_actions.py:execute_mobile_gate_action` (lines 47–125), and `notification_gates/cli_answer.py:_answer` (lines 108–178). All three check `isinstance(envelope.get("shell"), dict)` first to decide whether to even attempt the gate-shell lookup — none of them assume every gate is shell-backed.

The `_mobile_notification_actions.py` variant (lines 47–125), for contrast on ordering:
```python
92	    try:
93	        execution = execute_gate_selection(
94	            bundle.root,
95	            selected_option_ids,
96	            feedback=feedback,
97	            source="mobile",
98	            option_inputs=option_inputs,
99	            **execution_kwargs,
100	        )
101	    except GateError as exc:
...
107	        raise MobileGateActionError(code, exc.target, str(exc)) from exc
108	    if execution.already_completed:
109	        raise MobileGateActionError(
110	            "conflict_already_handled",
111	            notification.id,
112	            "response already exists",
113	        )
114	    if gate_shell is not None:
115	        settle_gate_shell(gate_shell, gate_state="answered", reason="gate answered")
```
This settles *after* the `already_completed` check — the opposite order from `launch_approval_actions.py`. Since you specifically asked for the `launch_approval_actions.py` ordering to be mirrored, use that one as the template, not this one.

---

## 10. `record_workflow_metadata`

Defined in `/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/src/sase/axe/run_agent_exec_plan.py`:
```python
def record_workflow_metadata(
    artifacts_dir: str,
    relationships: dict[str, Any],
) -> None:
    retained_fields = {
        "plan_submitted_at",
        "plan_path",
        "patch_name",
        "changespec_name",
        "feedback_submitted_at",
        "sdd_prompt_path",
        "sdd_plan_path",
        "plan_archive_ref",
        "epic_plan_ref",
        "plan_committed",
        "questions_submitted_at",
        "question_request_path",
        "question_response_path",
        "question_session_id",
        "followup_agent_name",
    }
    for key, value in relationships.items():
        if key in retained_fields and value is not None and value != "":
            update_meta_field(artifacts_dir, key, value)
```
It's a **filtering** writer: any key in `relationships` not in `retained_fields` is silently dropped, and `None`/`""` values are skipped. **If a new gate-shell-backed questions flow wants to persist new metadata fields (e.g. a `gate_id` for the question gate shell), that key must be added to `retained_fields` here, or it will be silently dropped.**

Example call site from `run_agent_exec_questions.py:183-191` (the current questions flow) — this is the "kind of fields questions currently records":
```python
183	    question_relationships = {
184	        "questions_submitted_at": questions_submitted_at,
185	        "question_request_path": response.get("_question_request_path"),
186	        "question_response_path": response.get("_question_response_path"),
187	        "question_session_id": response.get("_question_session_id"),
188	        "patch_name": ctx.cl_name,
189	        "changespec_name": ctx.cl_name,
190	    }
191	    record_workflow_metadata(state.current_artifacts_dir, question_relationships)
```
A second call site, from the same module (`run_agent_exec_plan.py`, plan-marker handling) for contrast on shape:
```python
    record_workflow_metadata(
        state.current_artifacts_dir,
        {
            "plan_submitted_at": plan_submitted_at,
            "plan_path": plan_data.get("plan_file"),
            "patch_name": ctx.cl_name,
            "changespec_name": ctx.cl_name,
        },
    )
```
`update_meta_field(artifacts_dir: str, key: str, value: Any) -> None` (imported from `sase.axe.run_agent_helpers`, actual home in `run_agent_helpers_artifacts.py` per the `gate_shell/log.py`/`gate_shell/settlement.py` imports) is the underlying single-field `agent_meta.json` writer both `record_workflow_metadata` and `handle_gate_marker`/`handle_questions_marker` call directly for fields outside the `retained_fields` allowlist (e.g. `handle_gate_marker` calls `update_meta_field(..., "gate_id", gate_id)` directly rather than through `record_workflow_metadata`, since `gate_id` isn't in `retained_fields`).

---

### Summary of the key seams for your gate-shell migration

1. **Marker contract**: `handle_gate_marker(gate_data, ctx, state)` only needs `gate_data["gate_id"]`, `["member_artifacts_dir"]`, `["member_agent_name"]` — plus a real `agent_meta.json` already written at `member_artifacts_dir` with `gate_id`/`gate_kind`/`gate_bundle_path`/`name`. A new questions-via-gate-shell path would presumably write a `.sase_gate_pending` marker (or call `handle_gate_marker` directly with a synthesized dict) instead of `.sase_questions_pending` + `handle_questions_flow`.
2. **Request-dict seam**: `create_user_question_gate` in `user_question_actions.py` builds a v3 request dict with no `"shell"` key — that key is what `_execute_neutral_launch_approval_response` gates its gate-shell lookup on (`isinstance(envelope.get("shell"), dict)`).
3. **Execution-ordering seam**: `_execute_neutral_launch_approval_response` in `launch_approval_actions.py` is the exact template to mirror — find shell → bind execution callbacks → `execute_gate_selection` → GateError translation → `settle_gate_shell` → **then** `already_completed` check.
4. **Metadata seam**: `record_workflow_metadata`'s `retained_fields` allowlist in `run_agent_exec_plan.py` will need a new key added if the plan wants to persist e.g. `question_gate_id` through it, or the code should call `update_meta_field` directly instead (as `handle_gate_marker` already does for `gate_id`/`gate_member_agent_name`).
5. **Q&A merge seam**: `handle_questions_marker` builds `state.qa_rounds` via `build_qa_round`/`merge_qa_for_prompt` (in `main/qa_prompt.py`) using `QARound`/`build_merged_qa_markdown` (in `main/qa_markdown.py`) — any gate-shell replacement must still produce a response shape `_question_result`-compatible (`option_results` keyed by `QUESTION_OPTION_ID = "submit"`, containing `answers`/`global_note`) so `build_qa_round` continues to work unmodified.

All three research agents came back with the precise APIs I need. Now let me begin implementation, starting with the feature flag.

Now let me add this entry to the registry file.

Now let's regenerate the schema and check the flags:

Now let's add `src/sase/gate_shell/flag.py`, mirroring `src/sase/pager/flag.py`.

No output means it passed. Let's confirm exit code and also run `sase flag list` to verify the flag is now registered.

Now let's create the settle-time next-action hook registry.

Now let's wire it into `followup.py::_base_prompt_kwargs`. Let me look at the full file first.

Now let's examine the gate_shell package's supporting modules in detail to model `question_shell/` on them.

Good, that's just a stale LSP cache; the module resolves fine. Now let's look at gate_shell's `member.py`, `naming.py`, `store.py`, `transaction.py`, and `settlement.py` to build the question_shell equivalents.

Let me read the full actual file directly since I'm about to make substantial edits to it.

Now let's write the `question_shell` package files.

Now let's extract the shared spec-building helper in `user_question_actions.py`:

Good, alphabetical order is maintained. Now let's write `question_shell/create.py`.

Now let's write `question_shell/rounds.py`.

Now `question_shell/followup.py`.

Now let's add the new `LoopState` field.

Now let's wire the flag branch into `run_agent_exec_questions.py`. First, update its imports.

Now let's add the new function and wire the flag branch. First view current state of the file around `handle_questions_marker`.

Now let's view the current `handle_questions_marker` function signature to insert the flag branch.

Now let's append the new `_handle_questions_via_gate_shell` function at the end of the file.

Now let's write the full new function.

All resolve correctly — the pyright warnings are stale-cache artifacts. Now let's handle the "settle the shell from every answering surface" piece in `user_question_actions.py`.

All modules import cleanly. Now let's run ruff/mypy lint on the touched files to catch style issues before writing tests.

Good — mypy and ruff both pass. Now let's update the skill template for `/sase_questions` per plan section 6.

Now let's update the test asserting the skill's phrases.

Test passes. Now let's write the test suite. Let's first examine the existing `tests/gate_shell/test_settlement_followup.py` fixture pattern fully to model the new tests.

All 6 pass. Now let's write `tests/question_shell/test_create.py`. Let's check `GateShellSpec.from_mapping`'s validation for the branch tuple format and `list_gate_shells` filtering by `is_terminal`/`followup_agent` more closely first.

Now let's run this test file.

Now let's write `tests/question_shell/test_rounds_rebuild.py` — the golden multi-round chain test.

Good, matches my expectation. Now let's write the golden test.

All 4 golden tests pass. Now let's write `tests/question_shell/test_followup_prompt.py` for `question_next_action`.

I caught an important bug — decision 3 in the plan requires `build_merged_qa_markdown` (unwrapped) for the composed prompt, not `merge_qa_for_prompt` (which self-wraps in disabled-region markers). Let me fix `question_shell/followup.py`.

Now let's write `tests/question_shell/test_followup_prompt.py`, modeled on `tests/gate_shell/test_followup_launch.py`.

Now fix the fragile `## Results` JSON assertion:

Now let's re-run the full `tests/question_shell/` and `tests/gate_shell/` suites together to check for regressions.

All 78 pass. Now let's write `tests/test_axe_run_agent_exec_questions_gate_shell.py` covering both flag states for `handle_questions_marker`. Let's check the existing off-branch test file for conventions first.

Now let's write the test file.

Good — mypy only targets `src/`, so those are pre-existing and irrelevant. Now let's add the shell-backed settlement test to `tests/test_user_question_gates.py`.

Good, both surfaces route through it. Now let's write the additions to `tests/test_user_question_gates.py`.

Fast now. Let's run ruff/mypy on this test file and the full suite once more.

All 7 pass fast now. Now let's run `just check` to catch any remaining lint/type/test issues across the whole change.

Just formatting differences. Let's run `just fmt` to auto-format, then re-run `just check`.

Good, `just fmt` applied auto-formatting to my files (as expected — deliberate). Let's re-run `just check` now.

The plan's memory instructions require reading the symvision reference before fixing this. Let me do that.

Right, as expected — the def line wasn't matched. Let me rename it directly.

Now update `__all__`:

Good, that's updated correctly. Now let's fix `question_gate_shell_spec` → private, and update `question_shell/__init__.py`.

Good, both def and call site got renamed. Now fix `__all__`:

Now update the tests using `question_gate_shell_spec` to use the private name.

Now let's add the symvision pragma for `question_next_action`.

Now let's re-run `just fmt` (for import ordering) and `just check` to see if this resolves symvision.

Now let's re-run `just check` (or at least symvision + tests) to verify.

Now let's remove the pragma comment I added (since it was rejected) and re-run symvision.

Symvision passes now. Let's run the full `just check` again.

That fixed it cleanly with no audit-registry pollution. Now let's investigate the two `test_snapshot.py` failures.

All fixed. Now let's run the full `just check` one more time to confirm everything is clean.

`just check` passes cleanly — it escalated to the full test suite (since I touched the Justfile and src data assets) and everything passed. Given CLAUDE.md's guidance, since this touches the runner/gate-shell/feature-flag registry (the "broadening set"), let's run `just check-full` through the monitor skill before considering this done.

Implementation and the fast `just check` gate are complete. Before deciding on `just check-full` (which requires a session-ending monitor handoff per this project's convention), let me finalize this turn properly.

Implementation is complete and the final declaration has been submitted — the host finalizer will commit this turn's work.

## Summary

I implemented the `questions-migration` phase (bead `sase-ud.10`) from `plans/202608/questions_migration.md`: `/sase_questions` now becomes a gate shell behind a new `gate_shell_handoff` beta flag (bead `sase-uo`).

**New code:**
- `src/sase/gate_shell/flag.py` — the flag accessor
- `src/sase/gate_shell/kind_next_action.py` — settle-time hook registry so a gate kind can rebuild its follow-up prompt from durable state, wired into `gate_shell/followup.py`
- `src/sase/question_shell/` — new package: builds the question gate shell's request spec (`create.py`), rebuilds the Q&A chain from durable gate-shell metadata (`rounds.py`), and rebuilds the settlement-time follow-up prompt (`followup.py`)
- `run_agent_exec_questions.py::handle_questions_marker` — flag branch: On, the runner creates a question gate shell and ends `DONE` (or continues in-process on the `%auto` short-circuit); Off, today's blocking behavior is untouched
- `user_question_actions.py` — extracted the shared `user_question_gate_spec` builder; `execute_user_question_response`'s neutral branch now settles a shell-backed question gate (mirroring the launch-approval ordering)
- Updated the `/sase_questions` skill template for both branches

**Tests:** new `tests/question_shell/` package (shell-block validation, golden 2-and-3-round chain rebuilds with simulated runner death, composed follow-up prompt with no leaked disabled-region markers), `tests/gate_shell/test_kind_next_action.py`, both-flag-state coverage in `tests/test_axe_run_agent_exec_questions_gate_shell.py`, and shell-backed/non-shell/chokepoint coverage added to `tests/test_user_question_gates.py`.

`just check` passes clean (37.6k+ tests, symvision, mypy, ruff, feature-flag lint, completion-spec sync all green).

**Not yet done:** `just check-full` (the exhaustive pre-landing gate) and closing bead `sase-ud.10` — per this repo's convention that's run via `/sase_monitor` since it can outrun a single turn. Want me to kick that off now?
