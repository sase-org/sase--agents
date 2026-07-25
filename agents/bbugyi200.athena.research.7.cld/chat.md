# Chat History - ace-run

- **TIMESTAMP:** 2026-07-11 11:55:37 EDT
- **MODEL:** claude/opus
- **AGENT:** research.7.cld
- **PROMPT:** `~/.sase/multi_prompts/202607/gh_sase_org__sase-multiprompt-260711_114618.md`

## Prompt

%name:research.@.cld %m:@research_b %g:research #gh:gh_sase-org__sase I've been thinking about getting rid of the concept of stand-alone xprompts (preficed with `#!` when invoked). I think the idea behind these was that there is no xprompt part inside of a stand-alone xprompt, so there's no way to embed a stand-alone xprompt inside of a prompt that has other text. I don't think that constraint really holds since we can always prepend the text that came before a stand-alone xprompt invocation and append the text that came after to the first agent in that xprompt workflow, right?

Can you do some research to help me confirm or deny these claims? End your analysis with a final recommendation on whether or not I should get rid of the concept of stand-alone xprompt workflows (i.e. get rid of the `` syntax and always use just `#` for xprompts). Once you've concluded your research, express your answer by setting some SASE variables. Write this research to a new markdown file under the $(sase sdd path research)/$(date +%Y%m)/ directory.


## Response

I'll research this thoroughly. Let me start by reading the relevant memory and exploring the codebase in parallel.

The memory read gives me the framework. Now let me dig into the actual implementation. Let me read the key files and spawn exploration agents in parallel.

This is clarifying the architecture. Let me read the swarm logic and the workflow model definitions, and spawn a broad exploration agent in parallel.

I'll research the SASE codebase to map the `#!` standalone-workflow concept. Let me start with broad parallel searches.

Let me look at the workflow model definitions and how embedded expansion handles a no-prompt_part workflow.

Let me examine the core model file and the standalone-specific files in parallel.

Let me read the core model definitions and parsing references files in detail.

Let me read reference_display.py fully and search for the error-message and expansion code.

Let me read the error-message code and the embedded-types file, plus the workflow_runner core sections.

Now let me read the workflow_runner.py key sections and the embedded_expand.py file.

Now let me read the `expand_workflow_for_embedding` function and the embedded_expand.py file (Area 4).

Let me find callers of `expand_workflow_for_embedding` and examine the TUI completion files and query handlers.

Let me read the query_handler embedded workflows, standalone steps, and special_cases files.

Now let me read the TUI completion files and inline expansion (Area 5), plus the _workflow_exec.py and _standalone_steps.py.

Let me read the workflow_exec, standalone_steps, sdd/_expand, and search for reference_prefix / XPromptAssistEntry.

Now let me get empirical data: what standalone workflows actually exist, whether they have agent steps, and the git history of when `#!` was introduced.

Now let me look at xprompt_swarm.py, the ace query parser/tokenizer/highlighting for `#!`, and search for tests and docs.

The ace/query tokenizer "standalone" hits are about query syntax operators, not the `#!` workflow marker. Let me narrow tests to true `#!` workflow behavior and find docs.

Let me examine the docs and memory files describing `#!`, and get one-line context from the key test files.

Let me inspect the actual standalone workflows to understand their structure.

Let me get one-line descriptions of the standalone-related tests and read the key docs sections.

Let me get the specific standalone-workflow test functions from the key identified test files.

Let me check the select_modal and xprompt_handler tests and the completion menu's `#@` selector plus `_workflow_exec.py` marker detection.

Let me look at the select modal insertion logic and verify remaining pieces.

Let me check the validator check context and the `#@` selector's Ctrl+I inline expansion trigger.

This is very revealing. The real standalone workflows are pure-automation (`eval_parallel`, `eval_ifs_loops` are test workflows with no agent step) or automation-with-conditional-agent (`sync`, whose only agent step is conditional, hidden, and appears after python setup steps). Let me verify a couple more mechanics while the explore agent runs.

`expand_workflow_for_embedding` (the "no prompt_part → all steps as post_steps" function that would enable the user's proposal) has **no non-test callers** — it's an unused API. The live embedding path raises instead. Let me check the design intent in the beads for the sase-1g epic that introduced `#!`.

The marker semantics have already churned — commit `03b5367e6` "require bang marker for multi-agent xprompts" but the current code *rejects* `#!` for swarms. Let me confirm this reversal and check dates.

I have a comprehensive, well-grounded picture now. Let me verify the completion/help UX surface myself while the explore agent finishes, then synthesize.

I now have a complete map. Here is the thorough breakdown across all 7 areas.

---

# Map of the `#!` / standalone-workflow concept in SASE

## Area 1 — `WorkflowKind` enum and Workflow classification methods

All in `src/sase/xprompt/workflow_models.py`:

- **`WorkflowKind` enum** — `workflow_models.py:26-31`. Three kinds:
  - `SIMPLE_XPROMPT = "simple_xprompt"` (single `prompt_part` step; the `.md`-derived xprompt)
  - `EMBEDDABLE_WORKFLOW = "embeddable_workflow"` (`.yml` that HAS a `prompt_part` step + pre/post steps)
  - `STANDALONE_WORKFLOW = "standalone_workflow"` (`.yml` with NO `prompt_part` step → `#!`)
- **`WorkflowStep.is_prompt_part_step()`** — `:125-127` (`return self.prompt_part is not None`)
- **`Workflow` dataclass** — `:131`
- **`get_prompt_part_index()`** — `:180-189` (finds the single prompt_part step index, else None)
- **`has_prompt_part()`** — `:191-197` (the embeddability predicate: `get_prompt_part_index() is not None`)
- **`get_prompt_part_content()`** — `:199-208`
- **`get_pre_prompt_steps()`** — `:210-219` (steps before prompt_part; `[]` when no prompt_part)
- **`get_post_prompt_steps()`** — `:221-230` (steps after prompt_part; **all steps** when no prompt_part — the Area 4 mechanism)
- **`is_anonymous()`** — `:241-243` (`self.name.startswith("tmp_")`)
- **`is_simple_xprompt()`** — `:245-259` (`len(self.steps) == 1 and self.has_prompt_part()`)
- **`prompt_kind()`** — `:261-267` — the central classifier:
  ```python
  if self.is_simple_xprompt(): return WorkflowKind.SIMPLE_XPROMPT
  if self.has_prompt_part():   return WorkflowKind.EMBEDDABLE_WORKFLOW
  return WorkflowKind.STANDALONE_WORKFLOW
  ```

---

## Area 2 — Where the `#!` (STANDALONE) marker is parsed / carried / displayed / inserted / autocompleted

### Lexical parsing (the source of truth)
`src/sase/xprompt/_parsing_references.py`:
- `XPROMPT_REFERENCE_MARKER_FRAGMENT = r"(?P<marker>#!|#)"` — `:18-19`
- `XPROMPT_REFERENCE_PATTERN` compiled regex — `:36-44` (shared matcher for both markers)
- `class XPromptReferenceMarker(Enum): INLINE = "#"; STANDALONE = "#!"` — `:47-51`
- `XPromptReference.is_standalone_marker` property — `:78-81`
- `xprompt_reference_from_match()` builds the marker from the match group — `:156-173`
- `iter_xprompt_references()` — `:176-186` (entry point; re-exported via `sase.xprompt._parsing`)

A second, older inline regex that also accepts `#!` (`#!?`) lives at `src/sase/xprompt/workflow_executor_steps_embedded_types.py:21-25` (`_WORKFLOW_REF_PATTERN`).

### Consumers of `is_standalone_marker`
- `src/sase/xprompt/workflow_runner.py:113` and `:223`
- `src/sase/xprompt/workflow_executor_steps_embedded_expand.py:147`
- `src/sase/main/query_handler/_embedded_workflows.py:100`
- `src/sase/main/query_handler/special_cases.py:116`
- `src/sase/ace/tui/actions/agent_workflow/_workflow_exec.py:78`
- `src/sase/sdd/_expand.py:64`, `:74`
- `src/sase/agent/xprompt_swarm.py:366`

### Display / insertion helpers
`src/sase/xprompt/reference_display.py` (entire file, 37 lines):
- `_workflow_uses_standalone_reference_marker()` — `:8-10` (`prompt_kind() is STANDALONE_WORKFLOW`)
- `workflow_kind_value()` — `:13-18` (maps SIMPLE_XPROMPT→`"xprompt"`, else `kind.value`)
- `workflow_reference_prefix()` — `:21-25` (returns `"#!"` for standalone, else `"#"`)
- `workflow_reference_insertion()` — `:28-30` (`f"{prefix}{name}"`)
- `workflow_reference_suffix()` — `:33-36` (insertion minus the leading `#`, for completing after a typed `#`)

Catalog/insertion consumers of those helpers: `src/sase/main/xprompt_handler.py:84-86,152-154`; `src/sase/xprompt/_catalog_structured.py:27-29,156-158`; `src/sase/ace/tui/modals/xprompt_select_modal.py:23-25,141,246,473,482`; `src/sase/ace/tui/modals/xprompt_browser_options.py:8,43`; `src/sase/ace/tui/modals/xprompt_browser_catalog.py:9-10,48,59`; `src/sase/ace/tui/widgets/_xprompt_arg_assist_catalog.py:8-10,63-65`; `src/sase/integrations/_mobile_helper_catalog.py:110`.

The `reference_prefix` field that carries `"#!"` through the catalog: `src/sase/xprompt/_catalog_models.py:62` and `src/sase/ace/tui/widgets/_xprompt_arg_assist_models.py:27`.

### Not related (false positives)
The many `"standalone"` hits in `src/sase/ace/query/{parser,tokenizer,highlighting}.py` and `src/sase/ace/hints.py:134` refer to **query operators** (`standalone !`, `@`, `$`, `%`), NOT the `#!` workflow marker.

---

## Area 3 — "standalone cannot be embedded" errors / has-prompt_part embeddability branches

### Error-message factories
- **`format_inline_workflow_reference_error(name, raw, has_prompt_part)`** — `src/sase/xprompt/workflow_executor_steps_embedded_types.py:28-48`. Three marker-aware branches:
  - `#!` + has prompt_part → "only standalone workflows use `#!` … Use `#name`" (`:35-39`)
  - `#!` + no prompt_part → "is a standalone workflow and cannot be embedded … Run it as a standalone workflow instead" (`:40-44`)
  - `#` + standalone → "cannot be embedded … Use `#!name` as a standalone workflow reference" (`:45-48`)
- **`invalid_explicit_standalone_message(name)`** — `src/sase/xprompt/workflow_runner.py:42-46` ("Only standalone workflows use '#!'; '{name}' has a prompt_part…")
- **`_ambiguous_standalone_message(names)`** — `workflow_runner.py:49-54`
- **`standalone_deprecation_message(name)` / `_warn_legacy_standalone_reference()`** — `workflow_runner.py:32-39` (legacy `#name` for a standalone workflow is deprecated in favor of `#!name`)
- **`_first_invalid_standalone_xprompt_reference()` / `_invalid_explicit_xprompt_message()`** — `src/sase/agent/xprompt_swarm.py:358-379` (rejects `#!` on an ordinary embeddable xprompt swarm)

### Raise/branch sites (inline embed → reject standalone)
- `src/sase/xprompt/workflow_executor_steps_embedded_expand.py:147-154` — `if ref.is_standalone_marker or not workflow.has_prompt_part(): raise …format_inline_workflow_reference_error(...)`
- `src/sase/main/query_handler/_embedded_workflows.py:100-107` — same guard
- `src/sase/sdd/_expand.py:63-81` — dry expansion: standalone `#!` refs preserved (`:64-65`), legacy `#` standalone raises (`:66-72`), `#!`+prompt_part raises (`:74-81`)
- `src/sase/xprompt/workflow_runner.py:114-117` and `:224-227` — explicit `#!` on a prompt_part workflow raises `invalid_explicit_standalone_message`
- `src/sase/ace/tui/actions/agent_workflow/_workflow_exec.py:111-118` — TUI notify with the same message
- `src/sase/main/query_handler/special_cases.py:132-134` — `sase run "#!name"` where name has prompt_part → prints error + exit 1
- `src/sase/ace/tui/widgets/xprompt_inline_expansion.py:94-99` — Ctrl+I inline expand rejects STANDALONE_WORKFLOW

### Tangential embeddability branch
`src/sase/xprompt/workflow_validator_checks.py:174-181` branches on `has_prompt_part()` to pick the "exempt last step" for output-reference validation (not an error path, but a prompt_part-vs-not decision).

---

## Area 4 — Expansion of a workflow with NO prompt_part ("all steps become post_steps")

- **`get_post_prompt_steps()`** — `workflow_models.py:221-230` is the actual "all steps become post_steps" implementation: when `get_prompt_part_index()` is None it returns `list(self.steps)`; `get_pre_prompt_steps()` (`:210-219`) returns `[]`.
- **`expand_workflow_for_embedding(workflow_name, positional_args, named_args)`** — `src/sase/xprompt/workflow_runner.py:588-650`. Docstring `:601`: "If the workflow has no prompt_part, all steps are returned as post-steps." It maps args, applies defaults, and returns `(prompt_part_content, pre_steps, post_steps)` via the two helpers above (`:637-650`). Note: this is exported public API (`src/sase/xprompt/__init__.py:89,179`; `workflow_runner.py:657`) but has **no in-src callers** — the live inline-embed paths (`_expand_embedded_workflows_in_prompt`, `_embedded_workflows.py`) instead **raise** for a no-prompt_part workflow (see Area 3), which is exactly the "cannot currently be embedded" gap you described.
- **Live embedded-execution engine** — `src/sase/xprompt/workflow_executor_steps_embedded_expand.py` (`EmbeddedWorkflowExpandMixin._expand_embedded_workflows_in_prompt`, `:60-393`). Five phases (collection/validation/pre-step exec/text-replace/post-step list). Standalone guard at `:140-154`; pre-step execution `:221-245`; prompt_part render `:254-318`; post-step `EmbeddedWorkflowInfo` build `:344-368`.
- **`execute_standalone_steps(pre_steps, context, name, artifacts_dir)`** — `src/sase/main/query_handler/_standalone_steps.py:37` (with `_evaluate_standalone_condition` `:10`), used by `_embedded_workflows.py:156` to run an embedded workflow's pre-steps. "Standalone" here means "isolated mini-executor," distinct from the `#!` marker.
- `EmbeddedWorkflowInfo` (pre_steps/post_steps/context) — `src/sase/xprompt/workflow_executor_steps_embedded_types.py:69-85`; `PendingEmbeddedWorkflow` `:88-110`.

---

## Area 5 — TUI completion / menu deciding `#` vs `#!` and filtering by marker

- **`src/sase/ace/tui/widgets/xprompt_completion.py:43-54`** — `standalone_only = token.startswith("#!")` (`:43`); strips 2 vs 1 chars (`:44`); when standalone, **filters the menu** to entries whose `entry.reference_prefix == "#!"` (`:53-54`). `is_xprompt_like_token()` (`:16-26`) accepts `#!` tokens.
- **`src/sase/ace/tui/widgets/xprompt_inline_expansion.py`** — Ctrl+I "expand in place" decision. `expand_inline_xprompt()` classifies via `prompt_kind()` (`:93`) and returns errors for `STANDALONE_WORKFLOW` (`:94-99`, "Press Enter to insert the reference") and `EMBEDDABLE_WORKFLOW` (`:100-104`). `_InlineExpansionReason` enum includes `STANDALONE_WORKFLOW` (`:40`).
- **`src/sase/ace/tui/modals/xprompt_select_modal.py`** — the `#@` selector menu: `_create_styled_label` renders a `▶` glyph + `workflow_reference_prefix(...)` for `standalone_workflow`, `⚙` for `embeddable_workflow` (`:244-254`); `_selection_for_name`/`_insertion_suffix` return `workflow_reference_suffix(...)` so selecting inserts `#!name` (`:467-482`); Ctrl+I bindings/routing at `:60,97,313-326,397-398`.
- **`reference_display.py`** helpers (Area 2) are the shared prefix/insertion logic all menus call.
- Catalog entry plumbing carrying `reference_prefix`/`insertion`/`kind`: `_xprompt_arg_assist_catalog.py:63-65`, `_xprompt_arg_assist_models.py:27`, `_catalog_structured.py:156-158`, `_catalog_models.py:62`.

---

## Area 6 — Tests exercising `#!` standalone behavior

- `tests/test_xprompt_references.py` — parses `#!` refs (plain `:31`, HITL suffix `:41`, namespaced colon-arg `:58`, paren args `:98`) and asserts `prompt_kind()` for embeddable vs standalone (`:137`, `:150`).
- `tests/test_workflow_executor.py:527` (`test_standalone_workflow_reference_errors_in_inline_prompt`) and `:548` (`test_bang_embeddable_workflow_reference_errors_in_inline_prompt`) — inline-embed guard raises the right marker-aware errors.
- `tests/test_special_cases.py:62,79,99` — `sase run "#!x"`: executes explicit standalone, warns on legacy `#name`, rejects `#!` for an embeddable workflow.
- `tests/test_xprompt_processor_workflow_flatten.py:123,169,188,241,266,289` — anonymous-wrapper flattening: accepts explicit `#!`, warns on legacy, rejects `#!` for embeddable, slow-path prefers/handles missing/multiple standalone refs.
- `tests/test_expand_for_spec.py:156,164,172,181` — dry expansion: legacy standalone errors, explicit `#!` preserved, fenced-block protection, `#!` on embeddable errors.
- `tests/ace/tui/widgets/test_xprompt_completion.py:69,99,262` — token accepts `#!`, completion menu filters to standalone workflows, single candidate inserts canonical `#!` reference.
- `tests/ace/tui/widgets/test_xprompt_inline_expansion.py:195,206` — Ctrl+I returns error for standalone workflow and for embeddable workflow-with-steps.
- `tests/ace/tui/modals/test_xprompt_select_modal.py:61,77,118` — menu builds `_standalone_workflow`, asserts `insertion == "#!sync"`.
- `tests/main/test_xprompt_handler.py:37-80` — `sase xprompt` list output: standalone rows carry `kind == "standalone_workflow"`, `prefix == "#!"`, `insertion == "#!sync"`; embeddable rows use `#`.
- `tests/test_xprompt_catalog_structured.py:441` — structured catalog uses canonical `#!` insertion.
- `tests/test_workflow_validator_xprompt_calls.py:79,158` — extraction/validation preserve the original `!` (bang) marker.
- `tests/ace/tui/test_try_execute_workflow_vcs_ref.py`, `tests/ace/tui/agent_launch_vcs/test_resolution.py`, `tests/ace/tui/test_failed_launch_stash.py`, `tests/ace/tui/test_prompt_bar_xprompt_selector_requests.py`, `tests/ace/tui/widgets/test_auto_xprompt_completion.py` — TUI launch/selector flows that include `#!` references (VCS-prefixed `#gh:sase #!…` and standalone-marker handling).
- Tangential (standalone *step* execution, not the `#!` marker): `tests/test_xprompt_jinja_and_standalone.py:30,325` (`execute_standalone_steps` conditions / chdir).

---

## Area 7 — Docs / help / memory describing `#!` vs `#`

- **`docs/xprompt.md`** — the primary reference:
  - `:5` "Inline prompt fragments use `#name`; standalone workflows use `#!name`…"
  - `:99-100` catalog: "embeddable_workflow entries insert as `#name`… standalone workflows insert as `#!name`."
  - `:205-210` project-namespaced `#!foo/bar`, `#!myapp/deploy`
  - `:256-257` "`#!name` is still accepted for xprompt swarms, but new prompts should use `#name`."
  - `:268-271` syntax table (`#!name`, `#!name(args)`, `#!name:arg`, `#!name!!`/`#!name??`)
  - `:276-281` examples (`sase run '#!sync'`, `#gh:sase #!sase/pylimit_split %auto`) and "Inline expansion contexts reject standalone workflows"
  - `:828`, `:905-921` catalog tables of concrete `#!` workflows (`#!sync`, `#!sase/fix_just`, `#!sase/pylimit_split`, `#!sase/refresh_docs`, etc.)
- **`docs/workflow_spec.md:158-160`** — "Standalone workflows, which have no `prompt_part` step, cannot be embedded inside an `agent` prompt. Launch them with `#!workflow_name(args)`…"; `:167-195` describes the `prompt_part` step and inline embedding.
- **`docs/cli.md:187`** — "Use `#name(...)` for inline xprompt expansion and `#!workflow(...)` for standalone workflow references."
- **`docs/architecture.md:43`** and **`docs/workspace.md:151,169`** — mention standalone-workflow reference expansion and `#gh:sase #!some/workflow` shorthand.
- **`memory/xprompts.md:11`** — "`#name` expands inline xprompts/workflows with `prompt_part`; `#!name` launches standalone YAML workflows."
- **`CHANGELOG.md:36`** — "resolve standalone workflow scope from workspace."
- User-facing help text is generated from the error factories in Area 3 (e.g. `format_inline_workflow_reference_error`, `invalid_explicit_standalone_message`, `standalone_deprecation_message`), surfaced via `sase run` stderr (`special_cases.py`) and TUI notifications (`_workflow_exec.py`).

---

### Key takeaway for your research question
The `#!` marker is fully plumbed through **parsing** (`_parsing_references.py`), **classification** (`workflow_models.prompt_kind`), **display/insertion** (`reference_display.py`), **completion/menu filtering** (`xprompt_completion.py`, `xprompt_select_modal.py`, `xprompt_inline_expansion.py`), and **launch/validation** (`workflow_runner.py`, `special_cases.py`, `_workflow_exec.py`). The specific limitation you named — a standalone workflow "cannot currently be embedded inside surrounding prompt text" — is enforced at `workflow_executor_steps_embedded_expand.py:147-154` and `_embedded_workflows.py:100-107` (both raise via `format_inline_workflow_reference_error`), while the only code that *would* handle a no-prompt_part workflow by turning all steps into post-steps (`expand_workflow_for_embedding` + `get_post_prompt_steps`) is currently unreferenced public API.

The completion widget confirms `#!` filters the menu to standalone-only. I now have everything I need. Let me check the research directory conventions and the `sase_var` interface, then wait briefly for the explore agent's full map.

I now have a complete picture from all angles: the code surface, the empirical workflow inventory, the git history, and the design intent. Let me write the research document.

Now let me set the SASE variables to express the answer, as requested.

Variables set on agent `research.7.cld`. My only file change is a markdown file under `sdd/research/`, which is exempt from `just check`.

---

## Research summary

I traced the `#!` concept through parsing, classification, embedding, the TUI, git history, and the actual workflow inventory. Here's what I found on your two claims.

### Claim 1 — "standalone xprompts exist only because there's no `prompt_part` slot to embed into" → ✅ **Confirmed**

That's the *entire* definition, not a side effect. `prompt_kind()` (`workflow_models.py:261-267`) classifies purely on `has_prompt_part()`, and the embed guard (`workflow_executor_steps_embedded_expand.py:147`) raises exactly when there's no `prompt_part`. The `prompt_part` step is the author's explicit opt-in to embeddability; `#!` is just a call-site echo of that decision.

### Claim 2 — "we can always prepend before-text / append after-text onto the first agent" → ⚠️ **Partially confirmed**

The **mechanism is real and already exists** — the xprompt-swarm path does precisely this (`xprompt_swarm.py:424`), and the workflow-side helper `expand_workflow_for_embedding` (which turns "all steps → post-steps" for no-`prompt_part` workflows) is already written… but **has zero non-test callers** — it's dormant. So you're right that the constraint isn't fundamental; it's ~90% plumbed.

But **"always" is false.** Looking at the real standalone workflows:
- `eval_parallel`, `eval_ifs_loops` — **no agent step at all** (pure bash/python). Nowhere to attach prose.
- `sync` — its *only* agent step is conditional (`if: has_conflicts`), hidden, and not first. `please be careful #!sync then report back` would attach your text to a step that **doesn't run on the common no-conflict path** — silent data loss.

The reason the swarm case works and the workflow case doesn't: swarm segments are **homogeneous** (all agent text), whereas YAML steps are **heterogeneous** (bash/python/agent/parallel), so "the first agent" is often absent, ambiguous (parallel), or misleading (conditional).

### Also worth knowing: the marker has already churned twice in ~10 weeks
Introduced 2026-04-29 for standalone → required for swarms too on 2026-05-04 (`03b5367e6`) → reverted back to standalone-only by 2026-07-08. A distinction that keeps getting re-scoped isn't paying rent.

### Recommendation → **Yes, remove `#!` and unify on `#`**

The marker is **redundant** with the `prompt_part` structure that already determines behavior; its dominant effect is a *symmetric* wrong-sigil error class (`#` on standalone errors one way, `#!` on embeddable errors the other) that catches zero real bugs. Concretely:

- **Do it (Option 1, minimal):** accept `#` everywhere, delete both validation directions, and keep **one** clear fail-fast error for the residual case — embedding a no-slot/no-agent workflow mid-prose. Strictly less friction than today.
- **Optionally (Option 2):** wire up the dormant `expand_workflow_for_embedding` to implement your prepend/append idea *for workflows with a real agent entry point*, still erroring on the ill-defined cases.

Just don't market it as "everything is now embeddable" — a small residual class genuinely can't absorb prose, so a guard has to remain.

**Variables set:** `recommendation=remove_bang_marker`, `claim1_why_standalone_exists=confirmed`, `claim2_prepend_to_first_agent=partially_confirmed`, plus `verdict`, `caveat`, and `research_doc`.

**Full write-up:** `.sase/sdd/research/202607/standalone_xprompt_bang_marker_removal_20260711.md`
